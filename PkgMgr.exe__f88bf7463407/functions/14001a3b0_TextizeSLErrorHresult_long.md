# TextizeSLErrorHresult(long)

- ea: `0x14001a3b0`
- end: `0x14001ad6c`
- name: `?TextizeSLErrorHresult@@YAPEBDJ@Z`
- size: `2492`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14001272c`

## callees

- `0x14001a3b0`

## string_xrefs

- `0x14001a537`: `SL_E_SRV_INVALID_SECURITY_PROCESSOR_LICENSE`
- `0x14001a5a4`: `SL_E_CHPA_ACTCONFIG_ID_NOT_FOUND`
- `0x14001a5c4`: `SL_E_CHPA_INVALID_ACTCONFIG_ID`
- `0x14001a664`: `SL_E_CHPA_INVALID_BINDING_URI`
- `0x14001a6ee`: `SL_E_CHPA_DMAK_EXTENSION_LIMIT_EXCEEDED`
- `0x14001a6b4`: `SL_E_CHPA_TIMEBASED_PRODUCT_KEY_NOT_CONFIGURED`
- `0x14001a7cb`: `SL_E_CHPA_FAILED_TO_UPDATE_PRODUCTKEY_BINDING`
- `0x14001a7bb`: `SL_E_CHPA_FAILED_TO_DELETE_PRODUCTKEY_BINDING`
- `0x14001a7a9`: `SL_E_CHPA_FAILED_TO_PROCESS_PRODUCT_KEY_BINDINGS_XML`
- `0x14001a82d`: `SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_PROPERTY`
- `0x14001a825`: `SL_E_CHPA_FAILED_TO_DELETE_PRODUCT_KEY_PROPERTY`
- `0x14001a835`: `SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_RECORD`
- `0x14001a86a`: `SL_E_TOKEN_STORE_INVALID_STATE`
- `0x14001a892`: `SL_E_TOKSTO_TOKEN_NOT_FOUND`
- `0x14001a8aa`: `SL_E_TOKSTO_ALREADY_INITIALIZED`
- `0x14001a8f2`: `SL_E_TOKSTO_CANT_CREATE_FILE`
- `0x14001a8fa`: `SL_E_TOKSTO_CANT_WRITE_TO_FILE`
- `0x14001a902`: `SL_E_TOKSTO_CANT_READ_FILE`
- `0x14001a922`: `SL_E_TOKSTO_CANT_CREATE_MUTEX`
- `0x14001a932`: `SL_E_TOKSTO_NO_TOKEN_DATA`
- `0x14001a942`: `SL_E_PKEY_INVALID_CONFIG`
- `0x14001a3fc`: `SL_E_SFS_BAD_TOKEN_NAME`
- `0x14001a404`: `SL_E_SFS_BAD_TOKEN_EXT`
- `0x14001a40c`: `SL_E_SFS_DUPLICATE_TOKEN_NAME`
- `0x14001a414`: `SL_E_SFS_TOKEN_SIZE_MISMATCH`
- `0x14001a41c`: `SL_E_SFS_INVALID_TOKEN_DATA_HASH`
- `0x14001a424`: `SL_E_SFS_FILE_READ_ERROR`
- `0x14001a42c`: `SL_E_SFS_FILE_WRITE_ERROR`
- `0x14001a9ac`: `SL_E_USE_LICENSE_NOT_INSTALLED`
- `0x14001aa24`: `SL_E_NO_PID_CONFIG_DATA`
- `0x14001aa2c`: `SL_E_MISMATCHED_SECURITY_PROCESSOR`
- `0x14001aa44`: `SL_E_LICENSE_FILE_NOT_INSTALLED`
- `0x14001aa5c`: `SL_E_PKEY_NOT_INSTALLED`
- `0x14001aa64`: `SL_E_PRODUCT_SKU_NOT_INSTALLED`
- `0x14001aa74`: `SL_E_PUBLISHING_LICENSE_NOT_INSTALLED`
- `0x14001aa94`: `SL_E_EVENT_ALREADY_REGISTERED`
- `0x14001aae4`: `SL_E_LUA_ACCESSDENIED`
- `0x14001aafc`: `SL_E_POLICY_CACHE_INVALID`
- `0x14001ab4c`: `SL_E_PRODUCT_KEY_INSTALLATION_NOT_ALLOWED`
- `0x14001ab6c`: `SL_E_VL_BINDING_SERVICE_NOT_ENABLED`
- `0x14001ab74`: `SL_E_VL_KEY_MANAGEMENT_SERVICE_NOT_ACTIVATED`
- `0x14001ab7c`: `SL_E_VL_KEY_MANAGEMENT_SERVICE_ID_MISMATCH`
- `0x14001ab84`: `SL_E_PROXY_POLICY_NOT_UPDATED`
- `0x14001ac34`: `SL_E_ISSUANCE_LICENSE_NOT_INSTALLED`
- `0x14001ac6c`: `SL_E_VL_KEY_MANAGEMENT_SERVICE_VM_NOT_SUPPORTED`
- `0x14001ac7c`: `SL_E_PLUGIN_ALREADY_REGISTERED`
- `0x14001ac84`: `SL_E_PLUGIN_INVALID_MANIFEST`
- `0x14001ac9c`: `SL_E_VL_BINDING_SERVICE_UNAVAILABLE`

## pseudocode

```c
const char *__fastcall TextizeSLErrorHresult(int a1)
{
  const char *result; // rax
  const char *v2; // rax
  bool v3; // zf
  const char *v4; // rdx

  if ( a1 <= -1073434623 )
  {
    if ( a1 == -1073434623 )
      return "SL_E_SRV_INVALID_PUBLISH_LICENSE";
    switch ( a1 )
    {
      case -2147163903:
        result = "SL_E_SFS_INVALID_FS_VERSION";
        break;
      case -2147163902:
        result = "SL_E_SFS_INVALID_FD_TABLE";
        break;
      case -2147163901:
        result = "SL_E_SFS_INVALID_SYNC";
        break;
      case -2147163900:
        result = "SL_E_SFS_BAD_TOKEN_NAME";
        break;
      case -2147163899:
        result = "SL_E_SFS_BAD_TOKEN_EXT";
        break;
      case -2147163898:
        result = "SL_E_SFS_DUPLICATE_TOKEN_NAME";
        break;
      case -2147163897:
        result = "SL_E_SFS_TOKEN_SIZE_MISMATCH";
        break;
      case -2147163896:
        result = "SL_E_SFS_INVALID_TOKEN_DATA_HASH";
        break;
      case -2147163895:
        result = "SL_E_SFS_FILE_READ_ERROR";
        break;
      case -2147163894:
        result = "SL_E_SFS_FILE_WRITE_ERROR";
        break;
      case -2147163893:
        result = "SL_E_SFS_INVALID_FILE_POSITION";
        break;
      default:
        goto LABEL_253;
    }
    return result;
  }
  if ( a1 > -1073418237 )
  {
    if ( a1 > -1073418169 )
    {
      if ( a1 > -1073415163 )
      {
        if ( a1 <= -1073414906 )
        {
          switch ( a1 )
          {
            case -1073414906:
              return "SL_E_CAL_STORE_ENDOFROWSET";
            case -1073414911:
              return "SL_E_CAL_NOT_FOUND";
            case -1073414910:
              return "SL_E_FREE_CAL_NOT_FOUND";
            case -1073414909:
              return "SL_E_CAL_CLASS_UNKNOWN";
            case -1073414908:
              return "SL_E_CAL_PRINCIPAL_UNKNOWN";
          }
          v2 = "SL_E_CAL_PRINCIPAL_UNEXPECTED_TYPE";
          v3 = a1 == -1073414907;
          goto LABEL_262;
        }
        switch ( a1 )
        {
          case -1073414905:
            return "SL_E_CAL_STORE_COLUMNISNULL";
          case -1073414904:
            return "SL_E_CAL_PRINCIPAL_INVALID";
          case -1073414903:
            return "SL_E_TAMPER_RECOVERY_REQUIRES_ACTIVATION";
          default:
            result = "SL_E_VL_INFO_PRODUCT_USER_RIGHT";
            if ( a1 != 1074065472 )
              return "Unknown Error";
            break;
        }
      }
      else if ( a1 == -1073415163 )
      {
        return "SL_E_VALIDITY_PERIOD_EXPIRED";
      }
      else
      {
        switch ( a1 )
        {
          case -1073418163:
            result = "SL_E_CIDIID_INVALID_CHECK_DIGITS";
            break;
          case -1073418161:
            result = "SL_E_LICENSE_MANAGEMENT_DATA_NOT_FOUND";
            break;
          case -1073418160:
            result = "SL_E_INVALID_PRODUCT_KEY";
            break;
          case -1073418159:
            result = "SL_E_BLOCKED_PRODUCT_KEY";
            break;
          case -1073418158:
            result = "SL_E_DUPLICATE_POLICY";
            break;
          case -1073418157:
            result = "SL_E_MISSING_OVERRIDE_ONLY_ATTRIBUTE";
            break;
          case -1073418156:
            result = "SL_E_LICENSE_MANAGEMENT_DATA_DUPLICATED";
            break;
          case -1073418155:
            result = "SL_E_BASE_SKU_NOT_AVAILABLE";
            break;
          case -1073418154:
            result = "SL_E_VL_MACHINE_NOT_BOUND";
            break;
          case -1073418153:
            result = "SL_E_SLP_MISSING_ACPI_SLIC";
            break;
          case -1073418152:
            result = "SL_E_SLP_MISSING_SLP_MARKER";
            break;
          case -1073418151:
            result = "SL_E_SLP_BAD_FORMAT";
            break;
          case -1073418144:
            result = "SL_E_INVALID_PACKAGE_VERSION";
            break;
          case -1073418143:
            result = "SL_E_PKEY_INVALID_UPGRADE";
            break;
          case -1073418142:
            result = "SL_E_ISSUANCE_LICENSE_NOT_INSTALLED";
            break;
          case -1073418141:
            result = "SL_E_SLP_OEM_CERT_MISSING";
            break;
          case -1073418140:
            result = "SL_E_NONGENUINE_GRACE_TIME_EXPIRED";
            break;
          case -1073418138:
            result = "SL_E_DEPENDENT_PROPERTY_NOT_SET";
            break;
          case -1073418137:
            result = "SL_E_NONGENUINE_GRACE_TIME_EXPIRED_2";
            break;
          case -1073418135:
            result = "SL_E_MISMATCHED_PRODUCT_SKU";
            break;
          case -1073418134:
            result = "SL_E_OPERATION_NOT_ALLOWED";
            break;
          case -1073418133:
            result = "SL_E_VL_KEY_MANAGEMENT_SERVICE_VM_NOT_SUPPORTED";
            break;
          case -1073418132:
            result = "SL_E_VL_INVALID_TIMESTAMP";
            break;
          case -1073418128:
            result = "SL_E_PLUGIN_ALREADY_REGISTERED";
            break;
          case -1073418127:
            result = "SL_E_PLUGIN_INVALID_MANIFEST";
            break;
          case -1073418126:
            result = "SL_E_APPLICATION_POLICIES_MISSING";
            break;
          case -1073418125:
            result = "SL_E_APPLICATION_POLICIES_NOT_LOADED";
            break;
          case -1073418124:
            result = "SL_E_VL_BINDING_SERVICE_UNAVAILABLE";
            break;
          default:
LABEL_253:
            result = "Unknown Error";
            break;
        }
      }
    }
    else if ( a1 == -1073418169 )
    {
      return "SL_E_PROXY_POLICY_NOT_UPDATED";
    }
    else
    {
      switch ( a1 )
      {
        case -1073418236:
          result = "SL_E_MISMATCHED_PKEY_RANGE";
          break;
        case -1073418235:
          result = "SL_E_MISMATCHED_PID";
          break;
        case -1073418234:
          result = "SL_E_EXTERNAL_SIGNATURE_NOT_FOUND";
          break;
        case -1073418233:
          result = "SL_E_RAC_NOT_AVAILABLE";
          break;
        case -1073418232:
          result = "SL_E_SPC_NOT_AVAILABLE";
          break;
        case -1073418231:
          result = "SL_E_GRACE_TIME_EXPIRED";
          break;
        case -1073418230:
          result = "SL_E_MISMATCHED_APPID";
          break;
        case -1073418229:
          result = "SL_E_NO_PID_CONFIG_DATA";
          break;
        case -1073418226:
          result = "SL_E_MISMATCHED_SECURITY_PROCESSOR";
          break;
        case -1073418225:
          result = "SL_E_OUT_OF_TOLERANCE";
          break;
        case -1073418224:
          result = "SL_E_INVALID_PKEY";
          break;
        case -1073418223:
          result = "SL_E_LICENSE_FILE_NOT_INSTALLED";
          break;
        case -1073418222:
          result = "SL_E_VALUE_NOT_FOUND";
          break;
        case -1073418221:
          result = "SL_E_RIGHT_NOT_GRANTED";
          break;
        case -1073418220:
          result = "SL_E_PKEY_NOT_INSTALLED";
          break;
        case -1073418219:
          result = "SL_E_PRODUCT_SKU_NOT_INSTALLED";
          break;
        case -1073418218:
          result = "SL_E_NOT_SUPPORTED";
          break;
        case -1073418217:
          result = "SL_E_PUBLISHING_LICENSE_NOT_INSTALLED";
          break;
        case -1073418216:
          result = "SL_E_LICENSE_SERVER_URL_NOT_FOUND";
          break;
        case -1073418215:
          result = "SL_E_INVALID_EVENT_ID";
          break;
        case -1073418214:
          result = "SL_E_EVENT_NOT_REGISTERED";
          break;
        case -1073418213:
          result = "SL_E_EVENT_ALREADY_REGISTERED";
          break;
        case -1073418212:
          result = "SL_E_DECRYPTION_LICENSES_NOT_AVAILABLE";
          break;
        case -1073418211:
          result = "SL_E_LICENSE_SIGNATURE_VERIFICATION_FAILED";
          break;
        case -1073418210:
          result = "SL_E_DATATYPE_MISMATCHED";
          break;
        case -1073418209:
          result = "SL_E_INVALID_LICENSE";
          break;
        case -1073418208:
          result = "SL_E_INVALID_PACKAGE";
          break;
        case -1073418207:
          result = "SL_E_VALIDITY_TIME_EXPIRED";
          break;
        case -1073418206:
          result = "SL_E_LICENSE_AUTHORIZATION_FAILED";
          break;
        case -1073418205:
          result = "SL_E_LICENSE_DECRYPTION_FAILED";
          break;
        case -1073418204:
          result = "SL_E_WINDOWS_INVALID_LICENSE_STATE";
          break;
        case -1073418203:
          result = "SL_E_LUA_ACCESSDENIED";
          break;
        case -1073418202:
          result = "SL_E_PROXY_KEY_NOT_FOUND";
          break;
        case -1073418201:
          result = "SL_E_TAMPER_DETECTED";
          break;
        case -1073418200:
          result = "SL_E_POLICY_CACHE_INVALID";
          break;
        case -1073418199:
          result = "SL_E_INVALID_RUNNING_MODE";
          break;
        case -1073418198:
          result = "SL_E_SLP_NOT_SIGNED";
          break;
        case -1073418196:
          result = "SL_E_CIDIID_INVALID_DATA";
          break;
        case -1073418195:
          result = "SL_E_CIDIID_INVALID_VERSION";
          break;
        case -1073418194:
          result = "SL_E_CIDIID_VERSION_NOT_SUPPORTED";
          break;
        case -1073418193:
          result = "SL_E_CIDIID_INVALID_DATA_LENGTH";
          break;
        case -1073418192:
          result = "SL_E_CIDIID_NOT_DEPOSITED";
          break;
        case -1073418191:
          result = "SL_E_CIDIID_MISMATCHED";
          break;
        case -1073418190:
          result = "SL_E_INVALID_BINDING_BLOB";
          break;
        case -1073418189:
          result = "SL_E_PRODUCT_KEY_INSTALLATION_NOT_ALLOWED";
          break;
        case -1073418188:
          result = "SL_E_EUL_NOT_AVAILABLE";
          break;
        case -1073418187:
          result = "SL_E_VL_NOT_WINDOWS_SLP";
          break;
        case -1073418184:
          result = "SL_E_VL_NOT_ENOUGH_COUNT";
          break;
        case -1073418183:
          result = "SL_E_VL_BINDING_SERVICE_NOT_ENABLED";
          break;
        case -1073418175:
          result = "SL_E_VL_KEY_MANAGEMENT_SERVICE_NOT_ACTIVATED";
          break;
        case -1073418174:
          result = "SL_E_VL_KEY_MANAGEMENT_SERVICE_ID_MISMATCH";
          break;
        default:
          goto LABEL_253;
      }
    }
  }
  else
  {
    if ( a1 == -1073418237 )
      return "SL_E_USE_LICENSE_NOT_INSTALLED";
    if ( a1 > -1073428655 )
    {
      if ( a1 > -1073422325 )
      {
        if ( a1 > -1073418239 )
        {
          v2 = "SL_E_RIGHT_NOT_CONSUMED";
          v3 = a1 == -1073418238;
LABEL_262:
          v4 = "Unknown Error";
          if ( v3 )
            return v2;
          return v4;
        }
        if ( a1 == -1073418239 )
        {
          return "SL_E_INTERNAL_ERROR";
        }
        else
        {
          switch ( a1 )
          {
            case -1073422324:
              result = "SL_E_TOKSTO_CANT_CREATE_FILE";
              break;
            case -1073422323:
              result = "SL_E_TOKSTO_CANT_WRITE_TO_FILE";
              break;
            case -1073422322:
              result = "SL_E_TOKSTO_CANT_READ_FILE";
              break;
            case -1073422321:
              result = "SL_E_TOKSTO_CANT_PARSE_PROPERTIES";
              break;
            case -1073422320:
              result = "SL_E_TOKSTO_PROPERTY_NOT_FOUND";
              break;
            case -1073422319:
              result = "SL_E_TOKSTO_INVALID_FILE";
              break;
            case -1073422318:
              result = "SL_E_TOKSTO_CANT_CREATE_MUTEX";
              break;
            case -1073422317:
              result = "SL_E_TOKSTO_CANT_ACQUIRE_MUTEX";
              break;
            case -1073422316:
              result = "SL_E_TOKSTO_NO_TOKEN_DATA";
              break;
            case -1073422315:
              result = "SL_E_EUL_CONSUMPTION_FAILED";
              break;
            case -1073422314:
              result = "SL_E_PKEY_INVALID_CONFIG";
              break;
            case -1073422313:
              result = "SL_E_PKEY_INVALID_UNIQUEID";
              break;
            case -1073422312:
              result = "SL_E_PKEY_INVALID_ALGORITHM";
              break;
            case -1073422311:
              result = "SL_E_PKEY_INTERNAL_ERROR";
              break;
            case -1073422310:
              result = "SL_E_LICENSE_INVALID_ADDON_INFO";
              break;
            case -1073422309:
              result = "SL_E_HWID_ERROR";
              break;
            case -1073422308:
              result = "SL_E_PKEY_INVALID_KEYCHANGE1";
              break;
            case -1073422307:
              result = "SL_E_PKEY_INVALID_KEYCHANGE2";
              break;
            case -1073422306:
              result = "SL_E_PKEY_INVALID_KEYCHANGE3";
              break;
            case -1073422305:
              result = "SL_E_PKEY_INVALID_KEYCHANGE4";
              break;
            default:
              goto LABEL_253;
          }
        }
      }
      else
      {
        if ( a1 == -1073422325 )
          return "SL_E_TOKSTO_NO_ID_SET";
        if ( a1 <= -1073428607 )
        {
          if ( a1 == -1073428607 )
            return "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_RECORD";
          if ( a1 > -1073428646 )
          {
            switch ( a1 )
            {
              case -1073428645:
                return "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_PROPERTY";
              case -1073428644:
                return "SL_E_CHPA_FAILED_TO_DELETE_PRODUCT_KEY_PROPERTY";
              case -1073428636:
                return "SL_E_CHPA_UNKNOWN_PRODUCT_KEY_TYPE";
              case -1073428624:
                return "SL_E_CHPA_PRODUCT_KEY_BEING_USED";
            }
            v2 = "SL_E_CHPA_FAILED_TO_INSERT_PRODUCT_KEY_RECORD";
            v3 = a1 == -1073428608;
          }
          else
          {
            switch ( a1 )
            {
              case -1073428646:
                return "SL_E_CHPA_FAILED_TO_INSERT_PRODUCT_KEY_PROPERTY";
              case -1073428654:
                return "SL_E_CHPA_UNKNOWN_PROPERTY_ID";
              case -1073428651:
                return "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCTKEY_BINDING";
              case -1073428650:
                return "SL_E_CHPA_FAILED_TO_INSERT_PRODUCTKEY_BINDING";
              case -1073428649:
                return "SL_E_CHPA_FAILED_TO_DELETE_PRODUCTKEY_BINDING";
            }
            v2 = "SL_E_CHPA_FAILED_TO_PROCESS_PRODUCT_KEY_BINDINGS_XML";
            v3 = a1 == -1073428648;
          }
          goto LABEL_262;
        }
        switch ( a1 )
        {
          case -1073422335:
            result = "SL_E_INVALID_CONTEXT";
            break;
          case -1073422334:
            result = "SL_E_TOKEN_STORE_INVALID_STATE";
            break;
          case -1073422333:
            result = "SL_E_EVALUATION_FAILED";
            break;
          case -1073422332:
            result = "SL_E_NOT_EVALUATED";
            break;
          case -1073422331:
            result = "SL_E_NOT_ACTIVATED";
            break;
          case -1073422330:
            result = "SL_E_INVALID_GUID";
            break;
          case -1073422329:
            result = "SL_E_TOKSTO_TOKEN_NOT_FOUND";
            break;
          case -1073422328:
            result = "SL_E_TOKSTO_NO_PROPERTIES";
            break;
          case -1073422327:
            result = "SL_E_TOKSTO_NOT_INITIALIZED";
            break;
          case -1073422326:
            result = "SL_E_TOKSTO_ALREADY_INITIALIZED";
            break;
          default:
            goto LABEL_253;
        }
      }
    }
    else
    {
      if ( a1 == -1073428655 )
        return "SL_E_CHPA_UNKNOWN_PROPERTY_NAME";
      if ( a1 > -1073430514 )
      {
        if ( a1 > -1073430449 )
        {
          switch ( a1 )
          {
            case -1073430448:
              return "SL_E_CHPA_GENERAL_ERROR";
            case -1073429503:
              return "SL_E_VGA_NON_GENUINE_STATUS_FIRST";
            case -1073428992:
              return "SL_E_VGA_NON_GENUINE_STATUS_LAST";
            case -1073428736:
              return "SL_E_CHPA_BUSINESS_RULE_INPUT_NOT_FOUND";
          }
          v2 = "SL_E_CHPA_NULL_VALUE_FOR_PROPERTY_NAME_OR_ID";
          v3 = a1 == -1073428656;
        }
        else
        {
          if ( a1 == -1073430449 )
            return "SL_E_CHPA_NO_RULES_TO_ACTIVATE";
          if ( a1 > -1073430496 )
          {
            switch ( a1 )
            {
              case -1073430495:
                return "SL_E_CHPA_DMAK_EXTENSION_LIMIT_EXCEEDED";
              case -1073430494:
                return "SL_E_CHPA_REISSUANCE_LIMIT_NOT_FOUND";
              case -1073430493:
                return "SL_E_CHPA_OVERRIDE_REQUEST_NOT_FOUND";
              case -1073430480:
                return "SL_E_CHPA_TIMEBASED_ACTIVATION_BEFORE_START_DATE";
              case -1073430479:
                return "SL_E_CHPA_TIMEBASED_ACTIVATION_AFTER_END_DATE";
              case -1073430478:
                return "SL_E_CHPA_TIMEBASED_ACTIVATION_NOT_AVAILABLE";
            }
            v2 = "SL_E_CHPA_TIMEBASED_PRODUCT_KEY_NOT_CONFIGURED";
            v3 = a1 == -1073430477;
          }
          else
          {
            switch ( a1 )
            {
              case -1073430496:
                return "SL_E_CHPA_DMAK_LIMIT_EXCEEDED";
              case -1073430513:
                return "SL_E_CHPA_INVALID_PRODUCT_KEY_FORMAT";
              case -1073430512:
                return "SL_E_CHPA_INVALID_PRODUCT_KEY_CHAR";
              case -1073430511:
                return "SL_E_CHPA_INVALID_BINDING_URI";
              case -1073430510:
                return "SL_E_CHPA_NETWORK_ERROR";
              case -1073430509:
                return "SL_E_CHPA_DATABASE_ERROR";
              case -1073430508:
                return "SL_E_CHPA_INVALID_ARGUMENT";
              case -1073430507:
                return "SL_E_CHPA_RESPONSE_NOT_AVAILABLE";
            }
            v2 = "SL_E_CHPA_OEM_SLP_COA0";
            v3 = a1 == -1073430506;
          }
        }
        goto LABEL_262;
      }
      if ( a1 == -1073430514 )
        return "SL_E_CHPA_INVALID_PRODUCT_KEY_LENGTH";
      if ( a1 <= -1073430526 )
      {
        if ( a1 == -1073430526 )
          return "SL_E_CHPA_INVALID_BINDING";
        if ( a1 > -1073434617 )
        {
          switch ( a1 )
          {
            case -1073434616:
              return "SL_E_SRV_INVALID_PAYLOAD";
            case -1073434615:
              return "SL_E_SRV_INVALID_SECURITY_PROCESSOR_LICENSE";
            case -1073434607:
              return "SL_E_SRV_CLIENT_CLOCK_OUT_OF_SYNC";
            case -1073434368:
              return "SL_E_SRV_GENERAL_ERROR";
          }
          v2 = "SL_E_CHPA_PRODUCT_KEY_OUT_OF_RANGE";
          v3 = a1 == -1073430527;
        }
        else
        {
          switch ( a1 )
          {
            case -1073434617:
              return "SL_E_SRV_SERVER_PONG";
            case -1073434622:
              return "SL_E_SRV_INVALID_PRODUCT_KEY_LICENSE";
            case -1073434621:
              return "SL_E_SRV_INVALID_RIGHTS_ACCOUNT_LICENSE";
            case -1073434620:
              return "SL_E_SRV_INVALID_LICENSE_STRUCTURE";
            case -1073434619:
              return "SL_E_SRV_AUTHORIZATION_FAILED";
          }
          v2 = "SL_E_SRV_INVALID_BINDING";
          v3 = a1 == -1073434618;
        }
        goto LABEL_262;
      }
      switch ( a1 )
      {
        case -1073430525:
          result = "SL_E_CHPA_PRODUCT_KEY_BLOCKED";
          break;
        case -1073430524:
          result = "SL_E_CHPA_INVALID_PRODUCT_KEY";
          break;
        case -1073430523:
          result = "SL_E_CHPA_BINDING_NOT_FOUND";
          break;
        case -1073430522:
          result = "SL_E_CHPA_BINDING_MAPPING_NOT_FOUND";
          break;
        case -1073430521:
          result = "SL_E_CHPA_UNSUPPORTED_PRODUCT_KEY";
          break;
        case -1073430520:
          result = "SL_E_CHPA_MAXIMUM_UNLOCK_EXCEEDED";
          break;
        case -1073430519:
          result = "SL_E_CHPA_ACTCONFIG_ID_NOT_FOUND";
          break;
        case -1073430518:
          result = "SL_E_CHPA_INVALID_PRODUCT_DATA_ID";
          break;
        case -1073430517:
          result = "SL_E_CHPA_INVALID_PRODUCT_DATA";
          break;
        case -1073430516:
          result = "SL_E_CHPA_SYSTEM_ERROR";
          break;
        case -1073430515:
          result = "SL_E_CHPA_INVALID_ACTCONFIG_ID";
          break;
        default:
          goto LABEL_253;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001a3b0  mov     eax, 0C004B001h
0x14001a3b5  cmp     ecx, eax
0x14001a3b7  jg      loc_14001A444
0x14001a3bd  jz      short loc_14001A43C
0x14001a3bf  add     ecx, 7FFB1EFFh; switch 11 cases
0x14001a3c5  cmp     ecx, 0Ah
0x14001a3c8  ja      def_14001A3E2; jumptable 000000014001A3E2 default case
0x14001a3ce  movsxd  rax, ecx
0x14001a3d1  lea     rcx, cs:140000000h
0x14001a3d8  mov     eax, ds:(jpt_14001A3E2 - 140000000h)[rcx+rax*4]
0x14001a3df  add     rax, rcx
0x14001a3e2  jmp     rax; switch jump
0x14001a3e4  lea     rax, aSlESfsInvalidF_0; jumptable 000000014001A3E2 case -2147163903
0x14001a3eb  retn
0x14001a3ec  lea     rax, aSlESfsInvalidF; jumptable 000000014001A3E2 case -2147163902
0x14001a3f3  retn
0x14001a3f4  lea     rax, aSlESfsInvalidS; jumptable 000000014001A3E2 case -2147163901
0x14001a3fb  retn
0x14001a3fc  lea     rax, aSlESfsBadToken; jumptable 000000014001A3E2 case -2147163900
0x14001a403  retn
0x14001a404  lea     rax, aSlESfsBadToken_0; jumptable 000000014001A3E2 case -2147163899
0x14001a40b  retn
0x14001a40c  lea     rax, aSlESfsDuplicat; jumptable 000000014001A3E2 case -2147163898
0x14001a413  retn
0x14001a414  lea     rax, aSlESfsTokenSiz; jumptable 000000014001A3E2 case -2147163897
0x14001a41b  retn
0x14001a41c  lea     rax, aSlESfsInvalidT; jumptable 000000014001A3E2 case -2147163896
0x14001a423  retn
0x14001a424  lea     rax, aSlESfsFileRead; jumptable 000000014001A3E2 case -2147163895
0x14001a42b  retn
0x14001a42c  lea     rax, aSlESfsFileWrit; jumptable 000000014001A3E2 case -2147163894
0x14001a433  retn
0x14001a434  lea     rax, aSlESfsInvalidF_1; jumptable 000000014001A3E2 case -2147163893
0x14001a43b  retn
0x14001a43c  lea     rax, aSlESrvInvalidP_0; "SL_E_SRV_INVALID_PUBLISH_LICENSE"
0x14001a443  retn
0x14001a444  mov     eax, 0C004F003h
0x14001a449  cmp     ecx, eax
0x14001a44b  jg      loc_14001A9B4
0x14001a451  jz      loc_14001A9AC
0x14001a457  mov     eax, 0C004C751h
0x14001a45c  cmp     ecx, eax
0x14001a45e  jg      loc_14001A758
0x14001a464  jz      loc_14001A750
0x14001a46a  mov     eax, 0C004C00Eh
0x14001a46f  cmp     ecx, eax
0x14001a471  jg      loc_14001A5D4
0x14001a477  jz      loc_14001A5CC
0x14001a47d  mov     eax, 0C004C002h
0x14001a482  cmp     ecx, eax
0x14001a484  jg      loc_14001A54F
0x14001a48a  jz      loc_14001A547
0x14001a490  mov     eax, 0C004B007h
0x14001a495  cmp     ecx, eax
0x14001a497  jg      short loc_14001A4F5
0x14001a499  jz      short loc_14001A4ED
0x14001a49b  cmp     ecx, 0C004B002h
0x14001a4a1  jz      short loc_14001A4E5
0x14001a4a3  cmp     ecx, 0C004B003h
0x14001a4a9  jz      short loc_14001A4DD
0x14001a4ab  cmp     ecx, 0C004B004h
0x14001a4b1  jz      short loc_14001A4D5
0x14001a4b3  cmp     ecx, 0C004B005h
0x14001a4b9  jz      short loc_14001A4CD
0x14001a4bb  lea     rax, aSlESrvInvalidB; "SL_E_SRV_INVALID_BINDING"
0x14001a4c2  cmp     ecx, 0C004B006h
0x14001a4c8  jmp     loc_14001ACEC
0x14001a4cd  lea     rax, aSlESrvAuthoriz; "SL_E_SRV_AUTHORIZATION_FAILED"
0x14001a4d4  retn
0x14001a4d5  lea     rax, aSlESrvInvalidL; "SL_E_SRV_INVALID_LICENSE_STRUCTURE"
0x14001a4dc  retn
0x14001a4dd  lea     rax, aSlESrvInvalidR; "SL_E_SRV_INVALID_RIGHTS_ACCOUNT_LICENSE"
0x14001a4e4  retn
0x14001a4e5  lea     rax, aSlESrvInvalidP; "SL_E_SRV_INVALID_PRODUCT_KEY_LICENSE"
0x14001a4ec  retn
0x14001a4ed  lea     rax, aSlESrvServerPo; "SL_E_SRV_SERVER_PONG"
0x14001a4f4  retn
0x14001a4f5  cmp     ecx, 0C004B008h
0x14001a4fb  jz      short loc_14001A53F
0x14001a4fd  cmp     ecx, 0C004B009h
0x14001a503  jz      short loc_14001A537
0x14001a505  cmp     ecx, 0C004B011h
0x14001a50b  jz      short loc_14001A52F
0x14001a50d  cmp     ecx, 0C004B100h
0x14001a513  jz      short loc_14001A527
0x14001a515  lea     rax, aSlEChpaProduct; "SL_E_CHPA_PRODUCT_KEY_OUT_OF_RANGE"
0x14001a51c  cmp     ecx, 0C004C001h
0x14001a522  jmp     loc_14001ACEC
0x14001a527  lea     rax, aSlESrvGeneralE; "SL_E_SRV_GENERAL_ERROR"
0x14001a52e  retn
0x14001a52f  lea     rax, aSlESrvClientCl; "SL_E_SRV_CLIENT_CLOCK_OUT_OF_SYNC"
0x14001a536  retn
0x14001a537  lea     rax, aSlESrvInvalidS; "SL_E_SRV_INVALID_SECURITY_PROCESSOR_LIC"...
0x14001a53e  retn
0x14001a53f  lea     rax, aSlESrvInvalidP_1; "SL_E_SRV_INVALID_PAYLOAD"
0x14001a546  retn
0x14001a547  lea     rax, aSlEChpaInvalid_5; "SL_E_CHPA_INVALID_BINDING"
0x14001a54e  retn
0x14001a54f  add     ecx, 3FFB3FFDh; switch 11 cases
0x14001a555  cmp     ecx, 0Ah
0x14001a558  ja      def_14001A3E2; jumptable 000000014001A3E2 default case
0x14001a55e  movsxd  rax, ecx
0x14001a561  lea     rcx, cs:140000000h
0x14001a568  mov     eax, ds:(jpt_14001A572 - 140000000h)[rcx+rax*4]
0x14001a56f  add     rax, rcx
0x14001a572  jmp     rax; switch jump
0x14001a574  lea     rax, aSlEChpaProduct_0; jumptable 000000014001A572 case -1073430525
0x14001a57b  retn
0x14001a57c  lea     rax, aSlEChpaInvalid_8; jumptable 000000014001A572 case -1073430524
0x14001a583  retn
0x14001a584  lea     rax, aSlEChpaBinding_0; jumptable 000000014001A572 case -1073430523
0x14001a58b  retn
0x14001a58c  lea     rax, aSlEChpaBinding; jumptable 000000014001A572 case -1073430522
0x14001a593  retn
0x14001a594  lea     rax, aSlEChpaUnsuppo; jumptable 000000014001A572 case -1073430521
0x14001a59b  retn
0x14001a59c  lea     rax, aSlEChpaMaximum; jumptable 000000014001A572 case -1073430520
0x14001a5a3  retn
0x14001a5a4  lea     rax, aSlEChpaActconf; jumptable 000000014001A572 case -1073430519
0x14001a5ab  retn
0x14001a5ac  lea     rax, aSlEChpaInvalid; jumptable 000000014001A572 case -1073430518
0x14001a5b3  retn
0x14001a5b4  lea     rax, aSlEChpaInvalid_6; jumptable 000000014001A572 case -1073430517
0x14001a5bb  retn
0x14001a5bc  lea     rax, aSlEChpaSystemE; jumptable 000000014001A572 case -1073430516
0x14001a5c3  retn
0x14001a5c4  lea     rax, aSlEChpaInvalid_3; jumptable 000000014001A572 case -1073430515
0x14001a5cb  retn
0x14001a5cc  lea     rax, aSlEChpaInvalid_4; "SL_E_CHPA_INVALID_PRODUCT_KEY_LENGTH"
0x14001a5d3  retn
0x14001a5d4  mov     eax, 0C004C04Fh
0x14001a5d9  cmp     ecx, eax
0x14001a5db  jg      loc_14001A6FE
0x14001a5e1  jz      loc_14001A6F6
0x14001a5e7  mov     eax, 0C004C020h
0x14001a5ec  cmp     ecx, eax
0x14001a5ee  jg      loc_14001A684
0x14001a5f4  jz      loc_14001A67C
0x14001a5fa  cmp     ecx, 0C004C00Fh
0x14001a600  jz      short loc_14001A674
0x14001a602  cmp     ecx, 0C004C010h
0x14001a608  jz      short loc_14001A66C
0x14001a60a  cmp     ecx, 0C004C011h
0x14001a610  jz      short loc_14001A664
0x14001a612  cmp     ecx, 0C004C012h
0x14001a618  jz      short loc_14001A65C
0x14001a61a  cmp     ecx, 0C004C013h
0x14001a620  jz      short loc_14001A654
0x14001a622  cmp     ecx, 0C004C014h
0x14001a628  jz      short loc_14001A64C
0x14001a62a  cmp     ecx, 0C004C015h
0x14001a630  jz      short loc_14001A644
0x14001a632  lea     rax, aSlEChpaOemSlpC; "SL_E_CHPA_OEM_SLP_COA0"
0x14001a639  cmp     ecx, 0C004C016h
0x14001a63f  jmp     loc_14001ACEC
0x14001a644  lea     rax, aSlEChpaRespons; "SL_E_CHPA_RESPONSE_NOT_AVAILABLE"
0x14001a64b  retn
0x14001a64c  lea     rax, aSlEChpaInvalid_1; "SL_E_CHPA_INVALID_ARGUMENT"
0x14001a653  retn
0x14001a654  lea     rax, aSlEChpaDatabas; "SL_E_CHPA_DATABASE_ERROR"
0x14001a65b  retn
0x14001a65c  lea     rax, aSlEChpaNetwork; "SL_E_CHPA_NETWORK_ERROR"
0x14001a663  retn
0x14001a664  lea     rax, aSlEChpaInvalid_0; "SL_E_CHPA_INVALID_BINDING_URI"
0x14001a66b  retn
0x14001a66c  lea     rax, aSlEChpaInvalid_7; "SL_E_CHPA_INVALID_PRODUCT_KEY_CHAR"
0x14001a673  retn
0x14001a674  lea     rax, aSlEChpaInvalid_2; "SL_E_CHPA_INVALID_PRODUCT_KEY_FORMAT"
0x14001a67b  retn
0x14001a67c  lea     rax, aSlEChpaDmakLim; "SL_E_CHPA_DMAK_LIMIT_EXCEEDED"
0x14001a683  retn
0x14001a684  cmp     ecx, 0C004C021h
0x14001a68a  jz      short loc_14001A6EE
0x14001a68c  cmp     ecx, 0C004C022h
0x14001a692  jz      short loc_14001A6E6
0x14001a694  cmp     ecx, 0C004C023h
0x14001a69a  jz      short loc_14001A6DE
0x14001a69c  cmp     ecx, 0C004C030h
0x14001a6a2  jz      short loc_14001A6D6
0x14001a6a4  cmp     ecx, 0C004C031h
0x14001a6aa  jz      short loc_14001A6CE
0x14001a6ac  cmp     ecx, 0C004C032h
0x14001a6b2  jz      short loc_14001A6C6
0x14001a6b4  lea     rax, aSlEChpaTimebas_1; "SL_E_CHPA_TIMEBASED_PRODUCT_KEY_NOT_CON"...
0x14001a6bb  cmp     ecx, 0C004C033h
0x14001a6c1  jmp     loc_14001ACEC
0x14001a6c6  lea     rax, aSlEChpaTimebas; "SL_E_CHPA_TIMEBASED_ACTIVATION_NOT_AVAI"...
0x14001a6cd  retn
0x14001a6ce  lea     rax, aSlEChpaTimebas_0; "SL_E_CHPA_TIMEBASED_ACTIVATION_AFTER_EN"...
0x14001a6d5  retn
0x14001a6d6  lea     rax, aSlEChpaTimebas_2; "SL_E_CHPA_TIMEBASED_ACTIVATION_BEFORE_S"...
0x14001a6dd  retn
0x14001a6de  lea     rax, aSlEChpaOverrid; "SL_E_CHPA_OVERRIDE_REQUEST_NOT_FOUND"
0x14001a6e5  retn
0x14001a6e6  lea     rax, aSlEChpaReissua; "SL_E_CHPA_REISSUANCE_LIMIT_NOT_FOUND"
0x14001a6ed  retn
0x14001a6ee  lea     rax, aSlEChpaDmakExt; "SL_E_CHPA_DMAK_EXTENSION_LIMIT_EXCEEDED"
0x14001a6f5  retn
0x14001a6f6  lea     rax, aSlEChpaNoRules; "SL_E_CHPA_NO_RULES_TO_ACTIVATE"
0x14001a6fd  retn
0x14001a6fe  cmp     ecx, 0C004C050h
0x14001a704  jz      short loc_14001A748
0x14001a706  cmp     ecx, 0C004C401h
0x14001a70c  jz      short loc_14001A740
0x14001a70e  cmp     ecx, 0C004C600h
0x14001a714  jz      short loc_14001A738
0x14001a716  cmp     ecx, 0C004C700h
0x14001a71c  jz      short loc_14001A730
0x14001a71e  lea     rax, aSlEChpaNullVal; "SL_E_CHPA_NULL_VALUE_FOR_PROPERTY_NAME_"...
0x14001a725  cmp     ecx, 0C004C750h
0x14001a72b  jmp     loc_14001ACEC
0x14001a730  lea     rax, aSlEChpaBusines; "SL_E_CHPA_BUSINESS_RULE_INPUT_NOT_FOUND"
0x14001a737  retn
0x14001a738  lea     rax, aSlEVgaNonGenui_0; "SL_E_VGA_NON_GENUINE_STATUS_LAST"
0x14001a73f  retn
0x14001a740  lea     rax, aSlEVgaNonGenui; "SL_E_VGA_NON_GENUINE_STATUS_FIRST"
0x14001a747  retn
0x14001a748  lea     rax, aSlEChpaGeneral; "SL_E_CHPA_GENERAL_ERROR"
0x14001a74f  retn
0x14001a750  lea     rax, aSlEChpaUnknown; "SL_E_CHPA_UNKNOWN_PROPERTY_NAME"
0x14001a757  retn
0x14001a758  mov     eax, 0C004E00Bh
0x14001a75d  cmp     ecx, eax
0x14001a75f  jg      loc_14001A8BA
0x14001a765  jz      loc_14001A8B2
0x14001a76b  mov     eax, 0C004C781h
0x14001a770  cmp     ecx, eax
0x14001a772  jg      loc_14001A83D
0x14001a778  jz      loc_14001A835
0x14001a77e  mov     eax, 0C004C75Ah
0x14001a783  cmp     ecx, eax
0x14001a785  jg      short loc_14001A7E3
0x14001a787  jz      short loc_14001A7DB
0x14001a789  cmp     ecx, 0C004C752h
0x14001a78f  jz      short loc_14001A7D3
0x14001a791  cmp     ecx, 0C004C755h
0x14001a797  jz      short loc_14001A7CB
0x14001a799  cmp     ecx, 0C004C756h
0x14001a79f  jz      short loc_14001A7C3
0x14001a7a1  cmp     ecx, 0C004C757h
0x14001a7a7  jz      short loc_14001A7BB
0x14001a7a9  lea     rax, aSlEChpaFailedT; "SL_E_CHPA_FAILED_TO_PROCESS_PRODUCT_KEY"...
0x14001a7b0  cmp     ecx, 0C004C758h
0x14001a7b6  jmp     loc_14001ACEC
0x14001a7bb  lea     rax, aSlEChpaFailedT_0; "SL_E_CHPA_FAILED_TO_DELETE_PRODUCTKEY_B"...
0x14001a7c2  retn
0x14001a7c3  lea     rax, aSlEChpaFailedT_4; "SL_E_CHPA_FAILED_TO_INSERT_PRODUCTKEY_B"...
0x14001a7ca  retn
0x14001a7cb  lea     rax, aSlEChpaFailedT_2; "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCTKEY_B"...
0x14001a7d2  retn
0x14001a7d3  lea     rax, aSlEChpaUnknown_0; "SL_E_CHPA_UNKNOWN_PROPERTY_ID"
0x14001a7da  retn
0x14001a7db  lea     rax, aSlEChpaFailedT_7; "SL_E_CHPA_FAILED_TO_INSERT_PRODUCT_KEY_"...
0x14001a7e2  retn
0x14001a7e3  cmp     ecx, 0C004C75Bh
0x14001a7e9  jz      short loc_14001A82D
0x14001a7eb  cmp     ecx, 0C004C75Ch
0x14001a7f1  jz      short loc_14001A825
0x14001a7f3  cmp     ecx, 0C004C764h
0x14001a7f9  jz      short loc_14001A81D
0x14001a7fb  cmp     ecx, 0C004C770h
0x14001a801  jz      short loc_14001A815
0x14001a803  lea     rax, aSlEChpaFailedT_1; "SL_E_CHPA_FAILED_TO_INSERT_PRODUCT_KEY_"...
0x14001a80a  cmp     ecx, 0C004C780h
0x14001a810  jmp     loc_14001ACEC
0x14001a815  lea     rax, aSlEChpaProduct_1; "SL_E_CHPA_PRODUCT_KEY_BEING_USED"
0x14001a81c  retn
0x14001a81d  lea     rax, aSlEChpaUnknown_1; "SL_E_CHPA_UNKNOWN_PRODUCT_KEY_TYPE"
0x14001a824  retn
0x14001a825  lea     rax, aSlEChpaFailedT_5; "SL_E_CHPA_FAILED_TO_DELETE_PRODUCT_KEY_"...
0x14001a82c  retn
0x14001a82d  lea     rax, aSlEChpaFailedT_3; "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_"...
0x14001a834  retn
0x14001a835  lea     rax, aSlEChpaFailedT_6; "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_"...
0x14001a83c  retn
0x14001a83d  add     ecx, 3FFB1FFFh; switch 10 cases
0x14001a843  cmp     ecx, 9
0x14001a846  ja      def_14001A3E2; jumptable 000000014001A3E2 default case
0x14001a84c  movsxd  rax, ecx
0x14001a84f  lea     rcx, cs:140000000h
0x14001a856  mov     eax, ds:(jpt_14001A860 - 140000000h)[rcx+rax*4]
0x14001a85d  add     rax, rcx
0x14001a860  jmp     rax; switch jump
0x14001a862  lea     rax, aSlEInvalidCont; jumptable 000000014001A860 case -1073422335
0x14001a869  retn
0x14001a86a  lea     rax, aSlETokenStoreI; jumptable 000000014001A860 case -1073422334
0x14001a871  retn
0x14001a872  lea     rax, aSlEEvaluationF; jumptable 000000014001A860 case -1073422333
0x14001a879  retn
0x14001a87a  lea     rax, aSlENotEvaluate; jumptable 000000014001A860 case -1073422332
0x14001a881  retn
0x14001a882  lea     rax, aSlENotActivate; jumptable 000000014001A860 case -1073422331
0x14001a889  retn
0x14001a88a  lea     rax, aSlEInvalidGuid; jumptable 000000014001A860 case -1073422330
0x14001a891  retn
0x14001a892  lea     rax, aSlETokstoToken; jumptable 000000014001A860 case -1073422329
0x14001a899  retn
0x14001a89a  lea     rax, aSlETokstoNoPro; jumptable 000000014001A860 case -1073422328
0x14001a8a1  retn
0x14001a8a2  lea     rax, aSlETokstoNotIn; jumptable 000000014001A860 case -1073422327
  ... truncated ...
```
