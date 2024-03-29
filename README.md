  "Serilog": {
    "Using": [
      "Serilog.Sinks.Console",
      "Serilog.Sinks.File"
    ],
    "MinimumLevel": {
      "Default": "Information",
      "Microsoft": "Information",
      "System": "Information",
      "Override": {
        "Microsoft.AspNetCore.Authentication.JwtBearer.JwtBearerHandler": "Warning",
        "Microsoft.AspNetCore.Authorization.DefaultAuthorizationService": "Warning",
        "Microsoft.AspNetCore.Cors.Infrastructure.CorsService": "Warning",
        "Microsoft.AspNetCore.DataProtection.KeyManagement.XmlKeyManager": "Warning",
        "Microsoft.AspNetCore.Mvc.Infrastructure.ControllerActionInvoker": "Warning",
        "Microsoft.AspNetCore.Mvc.Infrastructure.ObjectResultExecutor": "Warning",
        "Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware": "Warning",
        "Microsoft.AspNetCore.Routing.EndpointMiddleware": "Warning",
        "Microsoft.EntityFrameworkCore.Infrastructure": "Warning"
      }
    },
    "WriteTo": [
      {
        "Name": "Console",
        "Args": {
          "outputTemplate": "[{Timestamp:HH:mm:ss}] [{Level:u}] {Message:lj}{NewLine}{Exception}{NewLine}"
        }
      },
      {
        "Name": "File",
        "Args": {
          "formatter": "Serilog.Formatting.Json.JsonFormatter, Serilog",
          "path": "Logs\\.log",
          "restrictedToMinimumLevel": "Error",
          "rollingInterval": "Day",
          "rollOnFileSizeLimit": "true",
          "shared": "true"
        }
      }
    ]
  }
