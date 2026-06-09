# TextizeSLErrorHresult(long)

- ea: `0x14001a9a0`
- end: `0x14001b35c`
- name: `?TextizeSLErrorHresult@@YAPEBDJ@Z`
- size: `2492`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000e27c`

## callees

- `0x14001a9a0`

## string_xrefs

- `0x14001ab27`: `SL_E_SRV_INVALID_SECURITY_PROCESSOR_LICENSE`
- `0x14001ab94`: `SL_E_CHPA_ACTCONFIG_ID_NOT_FOUND`
- `0x14001abb4`: `SL_E_CHPA_INVALID_ACTCONFIG_ID`
- `0x14001ac54`: `SL_E_CHPA_INVALID_BINDING_URI`
- `0x14001acde`: `SL_E_CHPA_DMAK_EXTENSION_LIMIT_EXCEEDED`
- `0x14001aca4`: `SL_E_CHPA_TIMEBASED_PRODUCT_KEY_NOT_CONFIGURED`
- `0x14001adbb`: `SL_E_CHPA_FAILED_TO_UPDATE_PRODUCTKEY_BINDING`
- `0x14001adab`: `SL_E_CHPA_FAILED_TO_DELETE_PRODUCTKEY_BINDING`
- `0x14001ad99`: `SL_E_CHPA_FAILED_TO_PROCESS_PRODUCT_KEY_BINDINGS_XML`
- `0x14001ae1d`: `SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_PROPERTY`
- `0x14001ae15`: `SL_E_CHPA_FAILED_TO_DELETE_PRODUCT_KEY_PROPERTY`
- `0x14001ae25`: `SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_RECORD`
- `0x14001ae5a`: `SL_E_TOKEN_STORE_INVALID_STATE`
- `0x14001ae82`: `SL_E_TOKSTO_TOKEN_NOT_FOUND`
- `0x14001ae9a`: `SL_E_TOKSTO_ALREADY_INITIALIZED`
- `0x14001aee2`: `SL_E_TOKSTO_CANT_CREATE_FILE`
- `0x14001aeea`: `SL_E_TOKSTO_CANT_WRITE_TO_FILE`
- `0x14001aef2`: `SL_E_TOKSTO_CANT_READ_FILE`
- `0x14001af12`: `SL_E_TOKSTO_CANT_CREATE_MUTEX`
- `0x14001af22`: `SL_E_TOKSTO_NO_TOKEN_DATA`
- `0x14001af32`: `SL_E_PKEY_INVALID_CONFIG`
- `0x14001a9ec`: `SL_E_SFS_BAD_TOKEN_NAME`
- `0x14001a9f4`: `SL_E_SFS_BAD_TOKEN_EXT`
- `0x14001a9fc`: `SL_E_SFS_DUPLICATE_TOKEN_NAME`
- `0x14001aa04`: `SL_E_SFS_TOKEN_SIZE_MISMATCH`
- `0x14001aa0c`: `SL_E_SFS_INVALID_TOKEN_DATA_HASH`
- `0x14001aa14`: `SL_E_SFS_FILE_READ_ERROR`
- `0x14001aa1c`: `SL_E_SFS_FILE_WRITE_ERROR`
- `0x14001af9c`: `SL_E_USE_LICENSE_NOT_INSTALLED`
- `0x14001b014`: `SL_E_NO_PID_CONFIG_DATA`
- `0x14001b01c`: `SL_E_MISMATCHED_SECURITY_PROCESSOR`
- `0x14001b034`: `SL_E_LICENSE_FILE_NOT_INSTALLED`
- `0x14001b04c`: `SL_E_PKEY_NOT_INSTALLED`
- `0x14001b054`: `SL_E_PRODUCT_SKU_NOT_INSTALLED`
- `0x14001b064`: `SL_E_PUBLISHING_LICENSE_NOT_INSTALLED`
- `0x14001b084`: `SL_E_EVENT_ALREADY_REGISTERED`
- `0x14001b0d4`: `SL_E_LUA_ACCESSDENIED`
- `0x14001b0ec`: `SL_E_POLICY_CACHE_INVALID`
- `0x14001b13c`: `SL_E_PRODUCT_KEY_INSTALLATION_NOT_ALLOWED`
- `0x14001b15c`: `SL_E_VL_BINDING_SERVICE_NOT_ENABLED`
- `0x14001b164`: `SL_E_VL_KEY_MANAGEMENT_SERVICE_NOT_ACTIVATED`
- `0x14001b16c`: `SL_E_VL_KEY_MANAGEMENT_SERVICE_ID_MISMATCH`
- `0x14001b174`: `SL_E_PROXY_POLICY_NOT_UPDATED`
- `0x14001b224`: `SL_E_ISSUANCE_LICENSE_NOT_INSTALLED`
- `0x14001b25c`: `SL_E_VL_KEY_MANAGEMENT_SERVICE_VM_NOT_SUPPORTED`
- `0x14001b26c`: `SL_E_PLUGIN_ALREADY_REGISTERED`
- `0x14001b274`: `SL_E_PLUGIN_INVALID_MANIFEST`
- `0x14001b28c`: `SL_E_VL_BINDING_SERVICE_UNAVAILABLE`

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
0x14001a9a0  mov     eax, 0C004B001h
0x14001a9a5  cmp     ecx, eax
0x14001a9a7  jg      loc_14001AA34
0x14001a9ad  jz      short loc_14001AA2C
0x14001a9af  add     ecx, 7FFB1EFFh; switch 11 cases
0x14001a9b5  cmp     ecx, 0Ah
0x14001a9b8  ja      def_14001A9D2; jumptable 000000014001A9D2 default case
0x14001a9be  movsxd  rax, ecx
0x14001a9c1  lea     rcx, cs:140000000h
0x14001a9c8  mov     eax, ds:(jpt_14001A9D2 - 140000000h)[rcx+rax*4]
0x14001a9cf  add     rax, rcx
0x14001a9d2  jmp     rax; switch jump
0x14001a9d4  lea     rax, aSlESfsInvalidF_0; jumptable 000000014001A9D2 case -2147163903
0x14001a9db  retn
0x14001a9dc  lea     rax, aSlESfsInvalidF; jumptable 000000014001A9D2 case -2147163902
0x14001a9e3  retn
0x14001a9e4  lea     rax, aSlESfsInvalidS; jumptable 000000014001A9D2 case -2147163901
0x14001a9eb  retn
0x14001a9ec  lea     rax, aSlESfsBadToken; jumptable 000000014001A9D2 case -2147163900
0x14001a9f3  retn
0x14001a9f4  lea     rax, aSlESfsBadToken_0; jumptable 000000014001A9D2 case -2147163899
0x14001a9fb  retn
0x14001a9fc  lea     rax, aSlESfsDuplicat; jumptable 000000014001A9D2 case -2147163898
0x14001aa03  retn
0x14001aa04  lea     rax, aSlESfsTokenSiz; jumptable 000000014001A9D2 case -2147163897
0x14001aa0b  retn
0x14001aa0c  lea     rax, aSlESfsInvalidT; jumptable 000000014001A9D2 case -2147163896
0x14001aa13  retn
0x14001aa14  lea     rax, aSlESfsFileRead; jumptable 000000014001A9D2 case -2147163895
0x14001aa1b  retn
0x14001aa1c  lea     rax, aSlESfsFileWrit; jumptable 000000014001A9D2 case -2147163894
0x14001aa23  retn
0x14001aa24  lea     rax, aSlESfsInvalidF_1; jumptable 000000014001A9D2 case -2147163893
0x14001aa2b  retn
0x14001aa2c  lea     rax, aSlESrvInvalidP_0; "SL_E_SRV_INVALID_PUBLISH_LICENSE"
0x14001aa33  retn
0x14001aa34  mov     eax, 0C004F003h
0x14001aa39  cmp     ecx, eax
0x14001aa3b  jg      loc_14001AFA4
0x14001aa41  jz      loc_14001AF9C
0x14001aa47  mov     eax, 0C004C751h
0x14001aa4c  cmp     ecx, eax
0x14001aa4e  jg      loc_14001AD48
0x14001aa54  jz      loc_14001AD40
0x14001aa5a  mov     eax, 0C004C00Eh
0x14001aa5f  cmp     ecx, eax
0x14001aa61  jg      loc_14001ABC4
0x14001aa67  jz      loc_14001ABBC
0x14001aa6d  mov     eax, 0C004C002h
0x14001aa72  cmp     ecx, eax
0x14001aa74  jg      loc_14001AB3F
0x14001aa7a  jz      loc_14001AB37
0x14001aa80  mov     eax, 0C004B007h
0x14001aa85  cmp     ecx, eax
0x14001aa87  jg      short loc_14001AAE5
0x14001aa89  jz      short loc_14001AADD
0x14001aa8b  cmp     ecx, 0C004B002h
0x14001aa91  jz      short loc_14001AAD5
0x14001aa93  cmp     ecx, 0C004B003h
0x14001aa99  jz      short loc_14001AACD
0x14001aa9b  cmp     ecx, 0C004B004h
0x14001aaa1  jz      short loc_14001AAC5
0x14001aaa3  cmp     ecx, 0C004B005h
0x14001aaa9  jz      short loc_14001AABD
0x14001aaab  lea     rax, aSlESrvInvalidB; "SL_E_SRV_INVALID_BINDING"
0x14001aab2  cmp     ecx, 0C004B006h
0x14001aab8  jmp     loc_14001B2DC
0x14001aabd  lea     rax, aSlESrvAuthoriz; "SL_E_SRV_AUTHORIZATION_FAILED"
0x14001aac4  retn
0x14001aac5  lea     rax, aSlESrvInvalidL; "SL_E_SRV_INVALID_LICENSE_STRUCTURE"
0x14001aacc  retn
0x14001aacd  lea     rax, aSlESrvInvalidR; "SL_E_SRV_INVALID_RIGHTS_ACCOUNT_LICENSE"
0x14001aad4  retn
0x14001aad5  lea     rax, aSlESrvInvalidP; "SL_E_SRV_INVALID_PRODUCT_KEY_LICENSE"
0x14001aadc  retn
0x14001aadd  lea     rax, aSlESrvServerPo; "SL_E_SRV_SERVER_PONG"
0x14001aae4  retn
0x14001aae5  cmp     ecx, 0C004B008h
0x14001aaeb  jz      short loc_14001AB2F
0x14001aaed  cmp     ecx, 0C004B009h
0x14001aaf3  jz      short loc_14001AB27
0x14001aaf5  cmp     ecx, 0C004B011h
0x14001aafb  jz      short loc_14001AB1F
0x14001aafd  cmp     ecx, 0C004B100h
0x14001ab03  jz      short loc_14001AB17
0x14001ab05  lea     rax, aSlEChpaProduct; "SL_E_CHPA_PRODUCT_KEY_OUT_OF_RANGE"
0x14001ab0c  cmp     ecx, 0C004C001h
0x14001ab12  jmp     loc_14001B2DC
0x14001ab17  lea     rax, aSlESrvGeneralE; "SL_E_SRV_GENERAL_ERROR"
0x14001ab1e  retn
0x14001ab1f  lea     rax, aSlESrvClientCl; "SL_E_SRV_CLIENT_CLOCK_OUT_OF_SYNC"
0x14001ab26  retn
0x14001ab27  lea     rax, aSlESrvInvalidS; "SL_E_SRV_INVALID_SECURITY_PROCESSOR_LIC"...
0x14001ab2e  retn
0x14001ab2f  lea     rax, aSlESrvInvalidP_1; "SL_E_SRV_INVALID_PAYLOAD"
0x14001ab36  retn
0x14001ab37  lea     rax, aSlEChpaInvalid_5; "SL_E_CHPA_INVALID_BINDING"
0x14001ab3e  retn
0x14001ab3f  add     ecx, 3FFB3FFDh; switch 11 cases
0x14001ab45  cmp     ecx, 0Ah
0x14001ab48  ja      def_14001A9D2; jumptable 000000014001A9D2 default case
0x14001ab4e  movsxd  rax, ecx
0x14001ab51  lea     rcx, cs:140000000h
0x14001ab58  mov     eax, ds:(jpt_14001AB62 - 140000000h)[rcx+rax*4]
0x14001ab5f  add     rax, rcx
0x14001ab62  jmp     rax; switch jump
0x14001ab64  lea     rax, aSlEChpaProduct_0; jumptable 000000014001AB62 case -1073430525
0x14001ab6b  retn
0x14001ab6c  lea     rax, aSlEChpaInvalid_8; jumptable 000000014001AB62 case -1073430524
0x14001ab73  retn
0x14001ab74  lea     rax, aSlEChpaBinding_0; jumptable 000000014001AB62 case -1073430523
0x14001ab7b  retn
0x14001ab7c  lea     rax, aSlEChpaBinding; jumptable 000000014001AB62 case -1073430522
0x14001ab83  retn
0x14001ab84  lea     rax, aSlEChpaUnsuppo; jumptable 000000014001AB62 case -1073430521
0x14001ab8b  retn
0x14001ab8c  lea     rax, aSlEChpaMaximum; jumptable 000000014001AB62 case -1073430520
0x14001ab93  retn
0x14001ab94  lea     rax, aSlEChpaActconf; jumptable 000000014001AB62 case -1073430519
0x14001ab9b  retn
0x14001ab9c  lea     rax, aSlEChpaInvalid; jumptable 000000014001AB62 case -1073430518
0x14001aba3  retn
0x14001aba4  lea     rax, aSlEChpaInvalid_6; jumptable 000000014001AB62 case -1073430517
0x14001abab  retn
0x14001abac  lea     rax, aSlEChpaSystemE; jumptable 000000014001AB62 case -1073430516
0x14001abb3  retn
0x14001abb4  lea     rax, aSlEChpaInvalid_3; jumptable 000000014001AB62 case -1073430515
0x14001abbb  retn
0x14001abbc  lea     rax, aSlEChpaInvalid_4; "SL_E_CHPA_INVALID_PRODUCT_KEY_LENGTH"
0x14001abc3  retn
0x14001abc4  mov     eax, 0C004C04Fh
0x14001abc9  cmp     ecx, eax
0x14001abcb  jg      loc_14001ACEE
0x14001abd1  jz      loc_14001ACE6
0x14001abd7  mov     eax, 0C004C020h
0x14001abdc  cmp     ecx, eax
0x14001abde  jg      loc_14001AC74
0x14001abe4  jz      loc_14001AC6C
0x14001abea  cmp     ecx, 0C004C00Fh
0x14001abf0  jz      short loc_14001AC64
0x14001abf2  cmp     ecx, 0C004C010h
0x14001abf8  jz      short loc_14001AC5C
0x14001abfa  cmp     ecx, 0C004C011h
0x14001ac00  jz      short loc_14001AC54
0x14001ac02  cmp     ecx, 0C004C012h
0x14001ac08  jz      short loc_14001AC4C
0x14001ac0a  cmp     ecx, 0C004C013h
0x14001ac10  jz      short loc_14001AC44
0x14001ac12  cmp     ecx, 0C004C014h
0x14001ac18  jz      short loc_14001AC3C
0x14001ac1a  cmp     ecx, 0C004C015h
0x14001ac20  jz      short loc_14001AC34
0x14001ac22  lea     rax, aSlEChpaOemSlpC; "SL_E_CHPA_OEM_SLP_COA0"
0x14001ac29  cmp     ecx, 0C004C016h
0x14001ac2f  jmp     loc_14001B2DC
0x14001ac34  lea     rax, aSlEChpaRespons; "SL_E_CHPA_RESPONSE_NOT_AVAILABLE"
0x14001ac3b  retn
0x14001ac3c  lea     rax, aSlEChpaInvalid_1; "SL_E_CHPA_INVALID_ARGUMENT"
0x14001ac43  retn
0x14001ac44  lea     rax, aSlEChpaDatabas; "SL_E_CHPA_DATABASE_ERROR"
0x14001ac4b  retn
0x14001ac4c  lea     rax, aSlEChpaNetwork; "SL_E_CHPA_NETWORK_ERROR"
0x14001ac53  retn
0x14001ac54  lea     rax, aSlEChpaInvalid_0; "SL_E_CHPA_INVALID_BINDING_URI"
0x14001ac5b  retn
0x14001ac5c  lea     rax, aSlEChpaInvalid_7; "SL_E_CHPA_INVALID_PRODUCT_KEY_CHAR"
0x14001ac63  retn
0x14001ac64  lea     rax, aSlEChpaInvalid_2; "SL_E_CHPA_INVALID_PRODUCT_KEY_FORMAT"
0x14001ac6b  retn
0x14001ac6c  lea     rax, aSlEChpaDmakLim; "SL_E_CHPA_DMAK_LIMIT_EXCEEDED"
0x14001ac73  retn
0x14001ac74  cmp     ecx, 0C004C021h
0x14001ac7a  jz      short loc_14001ACDE
0x14001ac7c  cmp     ecx, 0C004C022h
0x14001ac82  jz      short loc_14001ACD6
0x14001ac84  cmp     ecx, 0C004C023h
0x14001ac8a  jz      short loc_14001ACCE
0x14001ac8c  cmp     ecx, 0C004C030h
0x14001ac92  jz      short loc_14001ACC6
0x14001ac94  cmp     ecx, 0C004C031h
0x14001ac9a  jz      short loc_14001ACBE
0x14001ac9c  cmp     ecx, 0C004C032h
0x14001aca2  jz      short loc_14001ACB6
0x14001aca4  lea     rax, aSlEChpaTimebas_1; "SL_E_CHPA_TIMEBASED_PRODUCT_KEY_NOT_CON"...
0x14001acab  cmp     ecx, 0C004C033h
0x14001acb1  jmp     loc_14001B2DC
0x14001acb6  lea     rax, aSlEChpaTimebas; "SL_E_CHPA_TIMEBASED_ACTIVATION_NOT_AVAI"...
0x14001acbd  retn
0x14001acbe  lea     rax, aSlEChpaTimebas_0; "SL_E_CHPA_TIMEBASED_ACTIVATION_AFTER_EN"...
0x14001acc5  retn
0x14001acc6  lea     rax, aSlEChpaTimebas_2; "SL_E_CHPA_TIMEBASED_ACTIVATION_BEFORE_S"...
0x14001accd  retn
0x14001acce  lea     rax, aSlEChpaOverrid; "SL_E_CHPA_OVERRIDE_REQUEST_NOT_FOUND"
0x14001acd5  retn
0x14001acd6  lea     rax, aSlEChpaReissua; "SL_E_CHPA_REISSUANCE_LIMIT_NOT_FOUND"
0x14001acdd  retn
0x14001acde  lea     rax, aSlEChpaDmakExt; "SL_E_CHPA_DMAK_EXTENSION_LIMIT_EXCEEDED"
0x14001ace5  retn
0x14001ace6  lea     rax, aSlEChpaNoRules; "SL_E_CHPA_NO_RULES_TO_ACTIVATE"
0x14001aced  retn
0x14001acee  cmp     ecx, 0C004C050h
0x14001acf4  jz      short loc_14001AD38
0x14001acf6  cmp     ecx, 0C004C401h
0x14001acfc  jz      short loc_14001AD30
0x14001acfe  cmp     ecx, 0C004C600h
0x14001ad04  jz      short loc_14001AD28
0x14001ad06  cmp     ecx, 0C004C700h
0x14001ad0c  jz      short loc_14001AD20
0x14001ad0e  lea     rax, aSlEChpaNullVal; "SL_E_CHPA_NULL_VALUE_FOR_PROPERTY_NAME_"...
0x14001ad15  cmp     ecx, 0C004C750h
0x14001ad1b  jmp     loc_14001B2DC
0x14001ad20  lea     rax, aSlEChpaBusines; "SL_E_CHPA_BUSINESS_RULE_INPUT_NOT_FOUND"
0x14001ad27  retn
0x14001ad28  lea     rax, aSlEVgaNonGenui_0; "SL_E_VGA_NON_GENUINE_STATUS_LAST"
0x14001ad2f  retn
0x14001ad30  lea     rax, aSlEVgaNonGenui; "SL_E_VGA_NON_GENUINE_STATUS_FIRST"
0x14001ad37  retn
0x14001ad38  lea     rax, aSlEChpaGeneral; "SL_E_CHPA_GENERAL_ERROR"
0x14001ad3f  retn
0x14001ad40  lea     rax, aSlEChpaUnknown; "SL_E_CHPA_UNKNOWN_PROPERTY_NAME"
0x14001ad47  retn
0x14001ad48  mov     eax, 0C004E00Bh
0x14001ad4d  cmp     ecx, eax
0x14001ad4f  jg      loc_14001AEAA
0x14001ad55  jz      loc_14001AEA2
0x14001ad5b  mov     eax, 0C004C781h
0x14001ad60  cmp     ecx, eax
0x14001ad62  jg      loc_14001AE2D
0x14001ad68  jz      loc_14001AE25
0x14001ad6e  mov     eax, 0C004C75Ah
0x14001ad73  cmp     ecx, eax
0x14001ad75  jg      short loc_14001ADD3
0x14001ad77  jz      short loc_14001ADCB
0x14001ad79  cmp     ecx, 0C004C752h
0x14001ad7f  jz      short loc_14001ADC3
0x14001ad81  cmp     ecx, 0C004C755h
0x14001ad87  jz      short loc_14001ADBB
0x14001ad89  cmp     ecx, 0C004C756h
0x14001ad8f  jz      short loc_14001ADB3
0x14001ad91  cmp     ecx, 0C004C757h
0x14001ad97  jz      short loc_14001ADAB
0x14001ad99  lea     rax, aSlEChpaFailedT; "SL_E_CHPA_FAILED_TO_PROCESS_PRODUCT_KEY"...
0x14001ada0  cmp     ecx, 0C004C758h
0x14001ada6  jmp     loc_14001B2DC
0x14001adab  lea     rax, aSlEChpaFailedT_0; "SL_E_CHPA_FAILED_TO_DELETE_PRODUCTKEY_B"...
0x14001adb2  retn
0x14001adb3  lea     rax, aSlEChpaFailedT_4; "SL_E_CHPA_FAILED_TO_INSERT_PRODUCTKEY_B"...
0x14001adba  retn
0x14001adbb  lea     rax, aSlEChpaFailedT_2; "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCTKEY_B"...
0x14001adc2  retn
0x14001adc3  lea     rax, aSlEChpaUnknown_0; "SL_E_CHPA_UNKNOWN_PROPERTY_ID"
0x14001adca  retn
0x14001adcb  lea     rax, aSlEChpaFailedT_7; "SL_E_CHPA_FAILED_TO_INSERT_PRODUCT_KEY_"...
0x14001add2  retn
0x14001add3  cmp     ecx, 0C004C75Bh
0x14001add9  jz      short loc_14001AE1D
0x14001addb  cmp     ecx, 0C004C75Ch
0x14001ade1  jz      short loc_14001AE15
0x14001ade3  cmp     ecx, 0C004C764h
0x14001ade9  jz      short loc_14001AE0D
0x14001adeb  cmp     ecx, 0C004C770h
0x14001adf1  jz      short loc_14001AE05
0x14001adf3  lea     rax, aSlEChpaFailedT_1; "SL_E_CHPA_FAILED_TO_INSERT_PRODUCT_KEY_"...
0x14001adfa  cmp     ecx, 0C004C780h
0x14001ae00  jmp     loc_14001B2DC
0x14001ae05  lea     rax, aSlEChpaProduct_1; "SL_E_CHPA_PRODUCT_KEY_BEING_USED"
0x14001ae0c  retn
0x14001ae0d  lea     rax, aSlEChpaUnknown_1; "SL_E_CHPA_UNKNOWN_PRODUCT_KEY_TYPE"
0x14001ae14  retn
0x14001ae15  lea     rax, aSlEChpaFailedT_5; "SL_E_CHPA_FAILED_TO_DELETE_PRODUCT_KEY_"...
0x14001ae1c  retn
0x14001ae1d  lea     rax, aSlEChpaFailedT_3; "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_"...
0x14001ae24  retn
0x14001ae25  lea     rax, aSlEChpaFailedT_6; "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_"...
0x14001ae2c  retn
0x14001ae2d  add     ecx, 3FFB1FFFh; switch 10 cases
0x14001ae33  cmp     ecx, 9
0x14001ae36  ja      def_14001A9D2; jumptable 000000014001A9D2 default case
0x14001ae3c  movsxd  rax, ecx
0x14001ae3f  lea     rcx, cs:140000000h
0x14001ae46  mov     eax, ds:(jpt_14001AE50 - 140000000h)[rcx+rax*4]
0x14001ae4d  add     rax, rcx
0x14001ae50  jmp     rax; switch jump
0x14001ae52  lea     rax, aSlEInvalidCont; jumptable 000000014001AE50 case -1073422335
0x14001ae59  retn
0x14001ae5a  lea     rax, aSlETokenStoreI; jumptable 000000014001AE50 case -1073422334
0x14001ae61  retn
0x14001ae62  lea     rax, aSlEEvaluationF; jumptable 000000014001AE50 case -1073422333
0x14001ae69  retn
0x14001ae6a  lea     rax, aSlENotEvaluate; jumptable 000000014001AE50 case -1073422332
0x14001ae71  retn
0x14001ae72  lea     rax, aSlENotActivate; jumptable 000000014001AE50 case -1073422331
0x14001ae79  retn
0x14001ae7a  lea     rax, aSlEInvalidGuid; jumptable 000000014001AE50 case -1073422330
0x14001ae81  retn
0x14001ae82  lea     rax, aSlETokstoToken; jumptable 000000014001AE50 case -1073422329
0x14001ae89  retn
0x14001ae8a  lea     rax, aSlETokstoNoPro; jumptable 000000014001AE50 case -1073422328
0x14001ae91  retn
0x14001ae92  lea     rax, aSlETokstoNotIn; jumptable 000000014001AE50 case -1073422327
  ... truncated ...
```
