# TextizeSLErrorHresult(long)

- ea: `0x180111be4`
- end: `0x180112678`
- name: `?TextizeSLErrorHresult@@YAPEBDJ@Z`
- size: `2708`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180035970`

## callees

- `0x180111be4`

## string_xrefs

- `0x180111d86`: `SL_E_SRV_INVALID_SECURITY_PROCESSOR_LICENSE`
- `0x180111e00`: `SL_E_CHPA_ACTCONFIG_ID_NOT_FOUND`
- `0x180111e24`: `SL_E_CHPA_INVALID_ACTCONFIG_ID`
- `0x180111eca`: `SL_E_CHPA_INVALID_BINDING_URI`
- `0x180111f5d`: `SL_E_CHPA_DMAK_EXTENSION_LIMIT_EXCEEDED`
- `0x180111f1e`: `SL_E_CHPA_TIMEBASED_PRODUCT_KEY_NOT_CONFIGURED`
- `0x180112031`: `SL_E_CHPA_FAILED_TO_DELETE_PRODUCTKEY_BINDING`
- `0x180112043`: `SL_E_CHPA_FAILED_TO_UPDATE_PRODUCTKEY_BINDING`
- `0x1801120a2`: `SL_E_CHPA_FAILED_TO_DELETE_PRODUCT_KEY_PROPERTY`
- `0x1801120ab`: `SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_PROPERTY`
- `0x18011201f`: `SL_E_CHPA_FAILED_TO_PROCESS_PRODUCT_KEY_BINDINGS_XML`
- `0x1801120b4`: `SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_RECORD`
- `0x1801120ef`: `SL_E_TOKEN_STORE_INVALID_STATE`
- `0x180112137`: `SL_E_TOKSTO_ALREADY_INITIALIZED`
- `0x18011211c`: `SL_E_TOKSTO_TOKEN_NOT_FOUND`
- `0x180112197`: `SL_E_TOKSTO_CANT_READ_FILE`
- `0x18011218e`: `SL_E_TOKSTO_CANT_WRITE_TO_FILE`
- `0x180112185`: `SL_E_TOKSTO_CANT_CREATE_FILE`
- `0x1801121bb`: `SL_E_TOKSTO_CANT_CREATE_MUTEX`
- `0x1801121df`: `SL_E_PKEY_INVALID_CONFIG`
- `0x1801121cd`: `SL_E_TOKSTO_NO_TOKEN_DATA`
- `0x180111c56`: `SL_E_SFS_TOKEN_SIZE_MISMATCH`
- `0x180111c4d`: `SL_E_SFS_DUPLICATE_TOKEN_NAME`
- `0x180111c44`: `SL_E_SFS_BAD_TOKEN_EXT`
- `0x180111c3b`: `SL_E_SFS_BAD_TOKEN_NAME`
- `0x180111c71`: `SL_E_SFS_FILE_WRITE_ERROR`
- `0x180111c68`: `SL_E_SFS_FILE_READ_ERROR`
- `0x180111c5f`: `SL_E_SFS_INVALID_TOKEN_DATA_HASH`
- `0x180112254`: `SL_E_USE_LICENSE_NOT_INSTALLED`
- `0x1801122e1`: `SL_E_MISMATCHED_SECURITY_PROCESSOR`
- `0x1801122d8`: `SL_E_NO_PID_CONFIG_DATA`
- `0x1801122fc`: `SL_E_LICENSE_FILE_NOT_INSTALLED`
- `0x180112320`: `SL_E_PRODUCT_SKU_NOT_INSTALLED`
- `0x180112317`: `SL_E_PKEY_NOT_INSTALLED`
- `0x180112332`: `SL_E_PUBLISHING_LICENSE_NOT_INSTALLED`
- `0x180112356`: `SL_E_EVENT_ALREADY_REGISTERED`
- `0x1801123b0`: `SL_E_LUA_ACCESSDENIED`
- `0x1801123cb`: `SL_E_POLICY_CACHE_INVALID`
- `0x180112425`: `SL_E_PRODUCT_KEY_INSTALLATION_NOT_ALLOWED`
- `0x180112449`: `SL_E_VL_BINDING_SERVICE_NOT_ENABLED`
- `0x180112464`: `SL_E_PROXY_POLICY_NOT_UPDATED`
- `0x18011245b`: `SL_E_VL_KEY_MANAGEMENT_SERVICE_ID_MISMATCH`
- `0x180112452`: `SL_E_VL_KEY_MANAGEMENT_SERVICE_NOT_ACTIVATED`
- `0x180112527`: `SL_E_ISSUANCE_LICENSE_NOT_INSTALLED`
- `0x180112578`: `SL_E_PLUGIN_ALREADY_REGISTERED`
- `0x180112566`: `SL_E_VL_KEY_MANAGEMENT_SERVICE_VM_NOT_SUPPORTED`
- `0x18011259c`: `SL_E_VL_BINDING_SERVICE_UNAVAILABLE`
- `0x180112581`: `SL_E_PLUGIN_INVALID_MANIFEST`

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
0x180111be4  mov     eax, 0C004B001h
0x180111be9  cmp     ecx, eax
0x180111beb  jg      loc_180111C8C
0x180111bf1  jz      loc_180111C83
0x180111bf7  add     ecx, 7FFB1EFFh; switch 11 cases
0x180111bfd  cmp     ecx, 0Ah
0x180111c00  ja      def_180111C1A; jumptable 0000000180111C1A default case
0x180111c06  movsxd  rax, ecx
0x180111c09  lea     rcx, __ImageBase
0x180111c10  mov     eax, ds:(jpt_180111C1A - 180000000h)[rcx+rax*4]
0x180111c17  add     rax, rcx
0x180111c1a  jmp     rax; switch jump
0x180111c20  lea     rax, aSlESfsInvalidF_0; jumptable 0000000180111C1A case -2147163903
0x180111c27  retn
0x180111c29  lea     rax, aSlESfsInvalidF; jumptable 0000000180111C1A case -2147163902
0x180111c30  retn
0x180111c32  lea     rax, aSlESfsInvalidS; jumptable 0000000180111C1A case -2147163901
0x180111c39  retn
0x180111c3b  lea     rax, aSlESfsBadToken; jumptable 0000000180111C1A case -2147163900
0x180111c42  retn
0x180111c44  lea     rax, aSlESfsBadToken_0; jumptable 0000000180111C1A case -2147163899
0x180111c4b  retn
0x180111c4d  lea     rax, aSlESfsDuplicat; jumptable 0000000180111C1A case -2147163898
0x180111c54  retn
0x180111c56  lea     rax, aSlESfsTokenSiz; jumptable 0000000180111C1A case -2147163897
0x180111c5d  retn
0x180111c5f  lea     rax, aSlESfsInvalidT; jumptable 0000000180111C1A case -2147163896
0x180111c66  retn
0x180111c68  lea     rax, aSlESfsFileRead; jumptable 0000000180111C1A case -2147163895
0x180111c6f  retn
0x180111c71  lea     rax, aSlESfsFileWrit; jumptable 0000000180111C1A case -2147163894
0x180111c78  retn
0x180111c7a  lea     rax, aSlESfsInvalidF_1; jumptable 0000000180111C1A case -2147163893
0x180111c81  retn
0x180111c83  lea     rax, aSlESrvInvalidP_0; "SL_E_SRV_INVALID_PUBLISH_LICENSE"
0x180111c8a  retn
0x180111c8c  mov     eax, 0C004F003h
0x180111c91  cmp     ecx, eax
0x180111c93  jg      loc_18011225D
0x180111c99  jz      loc_180112254
0x180111c9f  mov     eax, 0C004C751h
0x180111ca4  cmp     ecx, eax
0x180111ca6  jg      loc_180111FCE
0x180111cac  jz      loc_180111FC5
0x180111cb2  mov     eax, 0C004C00Eh
0x180111cb7  cmp     ecx, eax
0x180111cb9  jg      loc_180111E36
0x180111cbf  jz      loc_180111E2D
0x180111cc5  mov     eax, 0C004C002h
0x180111cca  cmp     ecx, eax
0x180111ccc  jg      loc_180111DA1
0x180111cd2  jz      loc_180111D98
0x180111cd8  mov     eax, 0C004B007h
0x180111cdd  cmp     ecx, eax
0x180111cdf  jg      short loc_180111D42
0x180111ce1  jz      short loc_180111D39
0x180111ce3  cmp     ecx, 0C004B002h
0x180111ce9  jz      short loc_180111D30
0x180111ceb  cmp     ecx, 0C004B003h
0x180111cf1  jz      short loc_180111D27
0x180111cf3  cmp     ecx, 0C004B004h
0x180111cf9  jz      short loc_180111D1E
0x180111cfb  cmp     ecx, 0C004B005h
0x180111d01  jz      short loc_180111D15
0x180111d03  lea     rax, aSlESrvInvalidB; "SL_E_SRV_INVALID_BINDING"
0x180111d0a  cmp     ecx, 0C004B006h
0x180111d10  jmp     loc_1801125EF
0x180111d15  lea     rax, aSlESrvAuthoriz; "SL_E_SRV_AUTHORIZATION_FAILED"
0x180111d1c  retn
0x180111d1e  lea     rax, aSlESrvInvalidL; "SL_E_SRV_INVALID_LICENSE_STRUCTURE"
0x180111d25  retn
0x180111d27  lea     rax, aSlESrvInvalidR; "SL_E_SRV_INVALID_RIGHTS_ACCOUNT_LICENSE"
0x180111d2e  retn
0x180111d30  lea     rax, aSlESrvInvalidP; "SL_E_SRV_INVALID_PRODUCT_KEY_LICENSE"
0x180111d37  retn
0x180111d39  lea     rax, aSlESrvServerPo; "SL_E_SRV_SERVER_PONG"
0x180111d40  retn
0x180111d42  cmp     ecx, 0C004B008h
0x180111d48  jz      short loc_180111D8F
0x180111d4a  cmp     ecx, 0C004B009h
0x180111d50  jz      short loc_180111D86
0x180111d52  cmp     ecx, 0C004B011h
0x180111d58  jz      short loc_180111D7D
0x180111d5a  cmp     ecx, 0C004B100h
0x180111d60  jz      short loc_180111D74
0x180111d62  lea     rax, aSlEChpaProduct; "SL_E_CHPA_PRODUCT_KEY_OUT_OF_RANGE"
0x180111d69  cmp     ecx, 0C004C001h
0x180111d6f  jmp     loc_1801125EF
0x180111d74  lea     rax, aSlESrvGeneralE; "SL_E_SRV_GENERAL_ERROR"
0x180111d7b  retn
0x180111d7d  lea     rax, aSlESrvClientCl; "SL_E_SRV_CLIENT_CLOCK_OUT_OF_SYNC"
0x180111d84  retn
0x180111d86  lea     rax, aSlESrvInvalidS; "SL_E_SRV_INVALID_SECURITY_PROCESSOR_LIC"...
0x180111d8d  retn
0x180111d8f  lea     rax, aSlESrvInvalidP_1; "SL_E_SRV_INVALID_PAYLOAD"
0x180111d96  retn
0x180111d98  lea     rax, aSlEChpaInvalid_5; "SL_E_CHPA_INVALID_BINDING"
0x180111d9f  retn
0x180111da1  add     ecx, 3FFB3FFDh; switch 11 cases
0x180111da7  cmp     ecx, 0Ah
0x180111daa  ja      def_180111C1A; jumptable 0000000180111C1A default case
0x180111db0  movsxd  rax, ecx
0x180111db3  lea     rcx, __ImageBase
0x180111dba  mov     eax, ds:(jpt_180111DC4 - 180000000h)[rcx+rax*4]
0x180111dc1  add     rax, rcx
0x180111dc4  jmp     rax; switch jump
0x180111dca  lea     rax, aSlEChpaProduct_0; jumptable 0000000180111DC4 case -1073430525
0x180111dd1  retn
0x180111dd3  lea     rax, aSlEChpaInvalid_8; jumptable 0000000180111DC4 case -1073430524
0x180111dda  retn
0x180111ddc  lea     rax, aSlEChpaBinding_0; jumptable 0000000180111DC4 case -1073430523
0x180111de3  retn
0x180111de5  lea     rax, aSlEChpaBinding; jumptable 0000000180111DC4 case -1073430522
0x180111dec  retn
0x180111dee  lea     rax, aSlEChpaUnsuppo; jumptable 0000000180111DC4 case -1073430521
0x180111df5  retn
0x180111df7  lea     rax, aSlEChpaMaximum; jumptable 0000000180111DC4 case -1073430520
0x180111dfe  retn
0x180111e00  lea     rax, aSlEChpaActconf; jumptable 0000000180111DC4 case -1073430519
0x180111e07  retn
0x180111e09  lea     rax, aSlEChpaInvalid; jumptable 0000000180111DC4 case -1073430518
0x180111e10  retn
0x180111e12  lea     rax, aSlEChpaInvalid_6; jumptable 0000000180111DC4 case -1073430517
0x180111e19  retn
0x180111e1b  lea     rax, aSlEChpaSystemE; jumptable 0000000180111DC4 case -1073430516
0x180111e22  retn
0x180111e24  lea     rax, aSlEChpaInvalid_3; jumptable 0000000180111DC4 case -1073430515
0x180111e2b  retn
0x180111e2d  lea     rax, aSlEChpaInvalid_4; "SL_E_CHPA_INVALID_PRODUCT_KEY_LENGTH"
0x180111e34  retn
0x180111e36  mov     eax, 0C004C04Fh
0x180111e3b  cmp     ecx, eax
0x180111e3d  jg      loc_180111F6F
0x180111e43  jz      loc_180111F66
0x180111e49  mov     eax, 0C004C020h
0x180111e4e  cmp     ecx, eax
0x180111e50  jg      loc_180111EEE
0x180111e56  jz      loc_180111EE5
0x180111e5c  cmp     ecx, 0C004C00Fh
0x180111e62  jz      short loc_180111EDC
0x180111e64  cmp     ecx, 0C004C010h
0x180111e6a  jz      short loc_180111ED3
0x180111e6c  cmp     ecx, 0C004C011h
0x180111e72  jz      short loc_180111ECA
0x180111e74  cmp     ecx, 0C004C012h
0x180111e7a  jz      short loc_180111EC1
0x180111e7c  cmp     ecx, 0C004C013h
0x180111e82  jz      short loc_180111EB8
0x180111e84  cmp     ecx, 0C004C014h
0x180111e8a  jz      short loc_180111EAF
0x180111e8c  cmp     ecx, 0C004C015h
0x180111e92  jz      short loc_180111EA6
0x180111e94  lea     rax, aSlEChpaOemSlpC; "SL_E_CHPA_OEM_SLP_COA0"
0x180111e9b  cmp     ecx, 0C004C016h
0x180111ea1  jmp     loc_1801125EF
0x180111ea6  lea     rax, aSlEChpaRespons; "SL_E_CHPA_RESPONSE_NOT_AVAILABLE"
0x180111ead  retn
0x180111eaf  lea     rax, aSlEChpaInvalid_1; "SL_E_CHPA_INVALID_ARGUMENT"
0x180111eb6  retn
0x180111eb8  lea     rax, aSlEChpaDatabas; "SL_E_CHPA_DATABASE_ERROR"
0x180111ebf  retn
0x180111ec1  lea     rax, aSlEChpaNetwork; "SL_E_CHPA_NETWORK_ERROR"
0x180111ec8  retn
0x180111eca  lea     rax, aSlEChpaInvalid_0; "SL_E_CHPA_INVALID_BINDING_URI"
0x180111ed1  retn
0x180111ed3  lea     rax, aSlEChpaInvalid_7; "SL_E_CHPA_INVALID_PRODUCT_KEY_CHAR"
0x180111eda  retn
0x180111edc  lea     rax, aSlEChpaInvalid_2; "SL_E_CHPA_INVALID_PRODUCT_KEY_FORMAT"
0x180111ee3  retn
0x180111ee5  lea     rax, aSlEChpaDmakLim; "SL_E_CHPA_DMAK_LIMIT_EXCEEDED"
0x180111eec  retn
0x180111eee  cmp     ecx, 0C004C021h
0x180111ef4  jz      short loc_180111F5D
0x180111ef6  cmp     ecx, 0C004C022h
0x180111efc  jz      short loc_180111F54
0x180111efe  cmp     ecx, 0C004C023h
0x180111f04  jz      short loc_180111F4B
0x180111f06  cmp     ecx, 0C004C030h
0x180111f0c  jz      short loc_180111F42
0x180111f0e  cmp     ecx, 0C004C031h
0x180111f14  jz      short loc_180111F39
0x180111f16  cmp     ecx, 0C004C032h
0x180111f1c  jz      short loc_180111F30
0x180111f1e  lea     rax, aSlEChpaTimebas_1; "SL_E_CHPA_TIMEBASED_PRODUCT_KEY_NOT_CON"...
0x180111f25  cmp     ecx, 0C004C033h
0x180111f2b  jmp     loc_1801125EF
0x180111f30  lea     rax, aSlEChpaTimebas; "SL_E_CHPA_TIMEBASED_ACTIVATION_NOT_AVAI"...
0x180111f37  retn
0x180111f39  lea     rax, aSlEChpaTimebas_0; "SL_E_CHPA_TIMEBASED_ACTIVATION_AFTER_EN"...
0x180111f40  retn
0x180111f42  lea     rax, aSlEChpaTimebas_2; "SL_E_CHPA_TIMEBASED_ACTIVATION_BEFORE_S"...
0x180111f49  retn
0x180111f4b  lea     rax, aSlEChpaOverrid; "SL_E_CHPA_OVERRIDE_REQUEST_NOT_FOUND"
0x180111f52  retn
0x180111f54  lea     rax, aSlEChpaReissua; "SL_E_CHPA_REISSUANCE_LIMIT_NOT_FOUND"
0x180111f5b  retn
0x180111f5d  lea     rax, aSlEChpaDmakExt; "SL_E_CHPA_DMAK_EXTENSION_LIMIT_EXCEEDED"
0x180111f64  retn
0x180111f66  lea     rax, aSlEChpaNoRules; "SL_E_CHPA_NO_RULES_TO_ACTIVATE"
0x180111f6d  retn
0x180111f6f  cmp     ecx, 0C004C050h
0x180111f75  jz      short loc_180111FBC
0x180111f77  cmp     ecx, 0C004C401h
0x180111f7d  jz      short loc_180111FB3
0x180111f7f  cmp     ecx, 0C004C600h
0x180111f85  jz      short loc_180111FAA
0x180111f87  cmp     ecx, 0C004C700h
0x180111f8d  jz      short loc_180111FA1
0x180111f8f  lea     rax, aSlEChpaNullVal; "SL_E_CHPA_NULL_VALUE_FOR_PROPERTY_NAME_"...
0x180111f96  cmp     ecx, 0C004C750h
0x180111f9c  jmp     loc_1801125EF
0x180111fa1  lea     rax, aSlEChpaBusines; "SL_E_CHPA_BUSINESS_RULE_INPUT_NOT_FOUND"
0x180111fa8  retn
0x180111faa  lea     rax, aSlEVgaNonGenui_0; "SL_E_VGA_NON_GENUINE_STATUS_LAST"
0x180111fb1  retn
0x180111fb3  lea     rax, aSlEVgaNonGenui; "SL_E_VGA_NON_GENUINE_STATUS_FIRST"
0x180111fba  retn
0x180111fbc  lea     rax, aSlEChpaGeneral; "SL_E_CHPA_GENERAL_ERROR"
0x180111fc3  retn
0x180111fc5  lea     rax, aSlEChpaUnknown; "SL_E_CHPA_UNKNOWN_PROPERTY_NAME"
0x180111fcc  retn
0x180111fce  mov     eax, 0C004E00Bh
0x180111fd3  cmp     ecx, eax
0x180111fd5  jg      loc_180112149
0x180111fdb  jz      loc_180112140
0x180111fe1  mov     eax, 0C004C781h
0x180111fe6  cmp     ecx, eax
0x180111fe8  jg      loc_1801120BD
0x180111fee  jz      loc_1801120B4
0x180111ff4  mov     eax, 0C004C75Ah
0x180111ff9  cmp     ecx, eax
0x180111ffb  jg      short loc_18011205E
0x180111ffd  jz      short loc_180112055
0x180111fff  cmp     ecx, 0C004C752h
0x180112005  jz      short loc_18011204C
0x180112007  cmp     ecx, 0C004C755h
0x18011200d  jz      short loc_180112043
0x18011200f  cmp     ecx, 0C004C756h
0x180112015  jz      short loc_18011203A
0x180112017  cmp     ecx, 0C004C757h
0x18011201d  jz      short loc_180112031
0x18011201f  lea     rax, aSlEChpaFailedT; "SL_E_CHPA_FAILED_TO_PROCESS_PRODUCT_KEY"...
0x180112026  cmp     ecx, 0C004C758h
0x18011202c  jmp     loc_1801125EF
0x180112031  lea     rax, aSlEChpaFailedT_0; "SL_E_CHPA_FAILED_TO_DELETE_PRODUCTKEY_B"...
0x180112038  retn
0x18011203a  lea     rax, aSlEChpaFailedT_4; "SL_E_CHPA_FAILED_TO_INSERT_PRODUCTKEY_B"...
0x180112041  retn
0x180112043  lea     rax, aSlEChpaFailedT_2; "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCTKEY_B"...
0x18011204a  retn
0x18011204c  lea     rax, aSlEChpaUnknown_0; "SL_E_CHPA_UNKNOWN_PROPERTY_ID"
0x180112053  retn
0x180112055  lea     rax, aSlEChpaFailedT_7; "SL_E_CHPA_FAILED_TO_INSERT_PRODUCT_KEY_"...
0x18011205c  retn
0x18011205e  cmp     ecx, 0C004C75Bh
0x180112064  jz      short loc_1801120AB
0x180112066  cmp     ecx, 0C004C75Ch
0x18011206c  jz      short loc_1801120A2
0x18011206e  cmp     ecx, 0C004C764h
0x180112074  jz      short loc_180112099
0x180112076  cmp     ecx, 0C004C770h
0x18011207c  jz      short loc_180112090
0x18011207e  lea     rax, aSlEChpaFailedT_1; "SL_E_CHPA_FAILED_TO_INSERT_PRODUCT_KEY_"...
0x180112085  cmp     ecx, 0C004C780h
0x18011208b  jmp     loc_1801125EF
0x180112090  lea     rax, aSlEChpaProduct_1; "SL_E_CHPA_PRODUCT_KEY_BEING_USED"
0x180112097  retn
0x180112099  lea     rax, aSlEChpaUnknown_1; "SL_E_CHPA_UNKNOWN_PRODUCT_KEY_TYPE"
0x1801120a0  retn
0x1801120a2  lea     rax, aSlEChpaFailedT_5; "SL_E_CHPA_FAILED_TO_DELETE_PRODUCT_KEY_"...
0x1801120a9  retn
0x1801120ab  lea     rax, aSlEChpaFailedT_3; "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_"...
0x1801120b2  retn
0x1801120b4  lea     rax, aSlEChpaFailedT_6; "SL_E_CHPA_FAILED_TO_UPDATE_PRODUCT_KEY_"...
0x1801120bb  retn
0x1801120bd  add     ecx, 3FFB1FFFh; switch 10 cases
0x1801120c3  cmp     ecx, 9
0x1801120c6  ja      def_180111C1A; jumptable 0000000180111C1A default case
0x1801120cc  movsxd  rax, ecx
0x1801120cf  lea     rcx, __ImageBase
0x1801120d6  mov     eax, ds:(jpt_1801120E0 - 180000000h)[rcx+rax*4]
0x1801120dd  add     rax, rcx
0x1801120e0  jmp     rax; switch jump
0x1801120e6  lea     rax, aSlEInvalidCont; jumptable 00000001801120E0 case -1073422335
0x1801120ed  retn
0x1801120ef  lea     rax, aSlETokenStoreI; jumptable 00000001801120E0 case -1073422334
0x1801120f6  retn
0x1801120f8  lea     rax, aSlEEvaluationF; jumptable 00000001801120E0 case -1073422333
0x1801120ff  retn
0x180112101  lea     rax, aSlENotEvaluate; jumptable 00000001801120E0 case -1073422332
0x180112108  retn
0x18011210a  lea     rax, aSlENotActivate; jumptable 00000001801120E0 case -1073422331
0x180112111  retn
0x180112113  lea     rax, aSlEInvalidGuid; jumptable 00000001801120E0 case -1073422330
0x18011211a  retn
0x18011211c  lea     rax, aSlETokstoToken; jumptable 00000001801120E0 case -1073422329
0x180112123  retn
0x180112125  lea     rax, aSlETokstoNoPro; jumptable 00000001801120E0 case -1073422328
0x18011212c  retn
0x18011212e  lea     rax, aSlETokstoNotIn; jumptable 00000001801120E0 case -1073422327
  ... truncated ...
```
