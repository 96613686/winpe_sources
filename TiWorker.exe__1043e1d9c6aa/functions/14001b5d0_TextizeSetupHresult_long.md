# TextizeSetupHresult(long)

- ea: `0x14001b5d0`
- end: `0x14001bef8`
- name: `?TextizeSetupHresult@@YAPEBDJ@Z`
- size: `2344`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000e27c`

## callees

- `0x14001b5d0`

## string_xrefs

- `0x14001bee8`: `CBS_S_ALREADY_EXISTS`
- `0x14001b9f6`: `CBS_E_ALREADY_INITIALIZED`
- `0x14001ba06`: `CBS_E_OPEN_FAILED`
- `0x14001ba1e`: `CBS_E_NOT_INSTALLABLE`
- `0x14001ba26`: `CBS_E_IMAGE_NOT_ACCESSIBLE`
- `0x14001ba46`: `CBS_E_UNKNOWN_UPDATE`
- `0x14001ba4e`: `CBS_E_MANIFEST_INVALID_ITEM`
- `0x14001ba56`: `CBS_E_MANIFEST_VALIDATION_DUPLICATE_ATTRIBUTES`
- `0x14001ba5e`: `CBS_E_MANIFEST_VALIDATION_DUPLICATE_ELEMENT`
- `0x14001ba66`: `CBS_E_MANIFEST_VALIDATION_MISSING_REQUIRED_ATTRIBUTES`
- `0x14001ba6e`: `CBS_E_MANIFEST_VALIDATION_MISSING_REQUIRED_ELEMENTS`
- `0x14001ba76`: `CBS_E_MANIFEST_VALIDATION_UPDATES_PARENT_MISSING`
- `0x14001ba7e`: `CBS_E_INVALID_INSTALL_STATE`
- `0x14001ba86`: `CBS_E_INVALID_CONFIG_VALUE`
- `0x14001ba9e`: `CBS_E_PACKAGE_DELETED`
- `0x14001baae`: `CBS_E_DUPLICATE_UPDATENAME`
- `0x14001bb2e`: `CBS_E_ILLEGAL_COMPONENT_UPDATE`
- `0x14001bb46`: `CBS_E_CANNOT_REMOVE`
- `0x14001bb6e`: `CBS_E_STACK_UPDATE_FAILED_REBOOT_REQUIRED`
- `0x14001bb9e`: `CBS_E_IMAGE_UNSERVICEABLE`
- `0x14001bbd6`: `CBS_E_POSTPONED_INSTALL_CONSIDERED`
- `0x14001bc06`: `CBS_E_SESSION_READONLY`
- `0x14001bc56`: `CBS_E_XML_PARSER_FAILURE`
- `0x14001bc5e`: `CBS_E_MANIFEST_VALIDATION_MULTIPLE_UPDATE_COMPONENT_ON_SAME_FAMILY_NOT_ALLOWED`
- `0x14001bc9e`: `CBS_E_REPAIR_PACKAGE_CORRUPT`
- `0x14001bca6`: `CBS_E_COMPONENT_NOT_INSTALLED_BY_CBS`
- `0x14001bcbe`: `CBS_E_WINDOWS_UPDATE_SEARCH_FAILURE`
- `0x14001bcc6`: `CBS_E_WINDOWS_AUTOMATIC_UPDATE_SETTING_DISALLOWED`
- `0x14001bce6`: `CBS_E_REPAIR_CONTENT_MISSING`
- `0x14001bd06`: `CBS_E_INSTALLERS_FAILED`
- `0x14001bd26`: `CBS_E_CANNOT_REMOVE_CONTAINER_DEPENDENCY`
- `0x14001be1e`: `CBS_E_INVALID_ACTION_LIST_INSTALL_REASON`
- `0x14001be26`: `CBS_E_NO_OPTIONAL_CONTENT_FOUND_ON_UPDATE_SERVERS`
- `0x14001be36`: `CBS_E_INVALID_ACTION_LIST_INSTALL_ACTION`
- `0x14001be3e`: `PSFX_E_DELTA_NOT_SUPPORTED_FOR_COMPONENT`
- `0x14001be4e`: `PSFX_E_MATCHING_COMPONENT_NOT_FOUND`
- `0x14001be56`: `PSFX_E_MATCHING_COMPONENT_DIRECTORY_MISSING`
- `0x14001be7e`: `PSFX_E_INVALID_DELTA_COMBINATION`
- `0x14001be8e`: `PSFX_E_UNSUPPORTED_COMPRESSION_SWITCH`
- `0x14001b72c`: `SPAPI_E_DEVINST_ALREADY_EXISTS`
- `0x14001b75c`: `SPAPI_E_INVALID_CLASS_INSTALLER`
- `0x14001b76c`: `SPAPI_E_DI_NOFILECOPY`
- `0x14001b7b9`: `SPAPI_E_DI_BAD_PATH`
- `0x14001b7c1`: `SPAPI_E_NO_CLASSINSTALL_PARAMS`
- `0x14001b7d1`: `SPAPI_E_BAD_SERVICE_INSTALLSECT`
- `0x14001b7e1`: `SPAPI_E_NO_ASSOCIATED_SERVICE`
- `0x14001b7f9`: `SPAPI_E_DEVICE_INTERFACE_REMOVED`
- `0x14001b801`: `SPAPI_E_BAD_INTERFACE_INSTALLSECT`
- `0x14001b821`: `SPAPI_E_REMOTE_COMM_FAILURE`
- `0x14001b831`: `SPAPI_E_NO_CONFIGMGR_SERVICES`
- `0x14001b851`: `SPAPI_E_INVALID_COINSTALLER`
- `0x14001b859`: `SPAPI_E_NO_COMPAT_DRIVERS`
- `0x14001b869`: `SPAPI_E_INVALID_INF_LOGCONFIG`
- `0x14001b871`: `SPAPI_E_DI_DONT_INSTALL`
- `0x14001b8d1`: `SPAPI_E_DEVINSTALL_QUEUE_NONNATIVE`
- `0x14001b8e1`: `SPAPI_E_CANT_REMOVE_DEVINST`
- `0x14001b921`: `SPAPI_E_PNP_REGISTRY_ERROR`
- `0x14001b931`: `SPAPI_E_NOT_AN_INSTALLED_OEM_INF`
- `0x14001b981`: `SPAPI_E_DEVICE_INSTALLER_NOT_READY`
- `0x14001b991`: `SPAPI_E_DEVICE_INSTALL_BLOCKED`
- `0x14001b999`: `SPAPI_E_DRIVER_INSTALL_BLOCKED`
- `0x14001b9b1`: `SPAPI_E_DRIVER_STORE_DELETE_FAILED`
- `0x14001bebe`: `SPAPI_E_ERROR_NOT_INSTALLED`

## pseudocode

```c
const char *__fastcall TextizeSetupHresult(int a1)
{
  const char *v1; // rdx
  bool v2; // zf
  const char *result; // rax
  int v4; // ecx
  int v5; // ecx

  if ( a1 > -2146498535 )
  {
    if ( a1 > -2146498481 )
    {
      if ( a1 > -2146498256 )
      {
        if ( a1 > -2146496512 )
        {
          v4 = a1 - 985089;
          if ( v4 )
          {
            v5 = v4 - 1;
            if ( v5 )
            {
              if ( v5 == 1 )
                return "CBS_S_STACK_SHUTDOWN_REQUIRED";
              else
                return "Unknown Error";
            }
            else
            {
              return "CBS_S_ALREADY_EXISTS";
            }
          }
          else
          {
            return "CBS_S_BUSY";
          }
        }
        else if ( a1 == -2146496512 )
        {
          return "SPAPI_E_ERROR_NOT_INSTALLED";
        }
        else
        {
          switch ( a1 )
          {
            case -2146498240:
              result = "CBS_E_WUSUS_MAPPING_UNAVAILABLE";
              break;
            case -2146498239:
              result = "CBS_E_WU_MAPPING_UNAVAILABLE";
              break;
            case -2146498238:
              result = "CBS_E_WUSUS_BYPASS_MAPPING_UNAVAILABLE";
              break;
            case -2146498237:
              result = "CBS_E_WUSUS_MISSING_PACKAGE_MAPPING_INDEX";
              break;
            case -2146498236:
              result = "CBS_E_WU_MISSING_PACKAGE_MAPPING_INDEX";
              break;
            case -2146498235:
              result = "CBS_E_WUSUS_BYPASS_MISSING_PACKAGE_MAPPING_INDEX";
              break;
            case -2146498234:
              result = "CBS_E_SOURCE_MISSING_FROM_WUSUS_CAB";
              break;
            case -2146498233:
              result = "CBS_E_SOURCE_MISSING_FROM_WUSUS_EXPRESS";
              break;
            case -2146498232:
              result = "CBS_E_SOURCE_MISSING_FROM_WU_CAB";
              break;
            case -2146498231:
              result = "CBS_E_SOURCE_MISSING_FROM_WU_EXPRESS";
              break;
            case -2146498230:
              result = "CBS_E_SOURCE_MISSING_FROM_WUSUS_BYPASS_CAB";
              break;
            case -2146498229:
              result = "CBS_E_SOURCE_MISSING_FROM_WUSUS_BYPASS_EXPRESS";
              break;
            case -2146498228:
              result = "CBS_E_3RD_PARTY_MAPPING_UNAVAILABLE";
              break;
            case -2146498227:
              result = "CBS_E_3RD_PARTY_MISSING_PACKAGE_MAPPING_INDEX";
              break;
            case -2146498226:
              result = "CBS_E_SOURCE_MISSING_FROM_3RD_PARTY_CAB";
              break;
            case -2146498225:
              result = "CBS_E_SOURCE_MISSING_FROM_3RD_PARTY_EXPRESS";
              break;
            case -2146498224:
              result = "CBS_E_NO_OPTIONAL_CONTENT_FOUND_FOR_BUILD";
              break;
            case -2146498223:
              result = "CBS_E_INVALID_NO_PRODUCT_REGISTERED";
              break;
            case -2146498222:
              result = "CBS_E_INVALID_ACTION_LIST_PACKAGE_COUNT";
              break;
            case -2146498221:
              result = "CBS_E_INVALID_ACTION_LIST_INSTALL_REASON";
              break;
            case -2146498220:
              result = "CBS_E_NO_OPTIONAL_CONTENT_FOUND_ON_UPDATE_SERVERS";
              break;
            case -2146498219:
              result = "CBS_E_INVALID_PACKAGE_REQUEST_ON_MULTILINGUAL_FOD";
              break;
            case -2146498218:
              result = "CBS_E_INVALID_ACTION_LIST_INSTALL_ACTION";
              break;
            case -2146498176:
              result = "PSFX_E_DELTA_NOT_SUPPORTED_FOR_COMPONENT";
              break;
            case -2146498175:
              result = "PSFX_E_REVERSE_AND_FORWARD_DELTAS_MISSING";
              break;
            case -2146498174:
              result = "PSFX_E_MATCHING_COMPONENT_NOT_FOUND";
              break;
            case -2146498173:
              result = "PSFX_E_MATCHING_COMPONENT_DIRECTORY_MISSING";
              break;
            case -2146498172:
              result = "PSFX_E_MATCHING_BINARY_MISSING";
              break;
            case -2146498171:
              result = "PSFX_E_APPLY_REVERSE_DELTA_FAILED";
              break;
            case -2146498170:
              result = "PSFX_E_APPLY_FORWARD_DELTA_FAILED";
              break;
            case -2146498169:
              result = "PSFX_E_NULL_DELTA_HYDRATION_FAILED";
              break;
            case -2146498168:
              result = "PSFX_E_INVALID_DELTA_COMBINATION";
              break;
            case -2146498167:
              result = "PSFX_E_REVERSE_DELTA_MISSING";
              break;
            case -2146498160:
              result = "PSFX_E_UNSUPPORTED_COMPRESSION_SWITCH";
              break;
            case -2146498159:
              result = "PSFX_E_MISSING_PAYLOAD_FILE";
              break;
            case -2146498158:
              result = "PSFX_E_PARTIAL_HYDRATION";
              break;
            case -2146498157:
              result = "PSFX_E_REBASE_HYDRATION_CANDIDATES_MISSING";
              break;
            case -2146498156:
              result = "PSFX_E_REBASE_HASH_ALG_NOT_SUPPORTED";
              break;
            case -2146498155:
              result = "PSFX_E_REBASE_MISSING_BASE_FILE";
              break;
            default:
              return "Unknown Error";
          }
        }
      }
      else if ( a1 == -2146498256 )
      {
        return "CBS_E_UNO_PACKAGE_CAB_MISSING";
      }
      else
      {
        switch ( a1 )
        {
          case -2146498304:
            result = "CBS_E_XML_PARSER_FAILURE";
            break;
          case -2146498303:
            result = "CBS_E_MANIFEST_VALIDATION_MULTIPLE_UPDATE_COMPONENT_ON_SAME_FAMILY_NOT_ALLOWED";
            break;
          case -2146498302:
            result = "CBS_E_BUSY";
            break;
          case -2146498300:
            result = "CBS_E_MORE_THAN_ONE_ACTIVE_EDITION";
            break;
          case -2146498299:
            result = "CBS_E_NO_ACTIVE_EDITION";
            break;
          case -2146498298:
            result = "CBS_E_DOWNLOAD_FAILURE";
            break;
          case -2146498297:
            result = "CBS_E_GROUPPOLICY_DISALLOWED";
            break;
          case -2146498296:
            result = "CBS_E_METERED_NETWORK";
            break;
          case -2146498295:
            result = "CBS_E_PUBLIC_OBJECT_LEAK";
            break;
          case -2146498293:
            result = "CBS_E_REPAIR_PACKAGE_CORRUPT";
            break;
          case -2146498292:
            result = "CBS_E_COMPONENT_NOT_INSTALLED_BY_CBS";
            break;
          case -2146498291:
            result = "CBS_E_MISSING_PACKAGE_MAPPING_INDEX";
            break;
          case -2146498290:
            result = "CBS_E_EMPTY_PACKAGE_MAPPING_INDEX";
            break;
          case -2146498289:
            result = "CBS_E_WINDOWS_UPDATE_SEARCH_FAILURE";
            break;
          case -2146498288:
            result = "CBS_E_WINDOWS_AUTOMATIC_UPDATE_SETTING_DISALLOWED";
            break;
          case -2146498287:
            result = "CBS_E_SOURCE_MODIFIED";
            break;
          case -2146498286:
            result = "CBS_E_ONDEMAND_LOCALSOURCE_NOT_FOUND";
            break;
          case -2146498284:
            result = "CBS_E_WINRE_NOT_ENABLED";
            break;
          case -2146498283:
            result = "CBS_E_REPAIR_CONTENT_MISSING";
            break;
          case -2146498282:
            result = "CBS_E_PAYLOAD_FILE_MISSING";
            break;
          case -2146498272:
            result = "CBS_E_HANG_DETECTED";
            break;
          case -2146498271:
            result = "CBS_E_PRIMITIVES_FAILED";
            break;
          case -2146498270:
            result = "CBS_E_INSTALLERS_FAILED";
            break;
          case -2146498269:
            result = "CBS_E_SAFEMODE_ENTERED";
            break;
          case -2146498268:
            result = "CBS_E_SESSIONS_LEAKED";
            break;
          case -2146498267:
            result = "CBS_E_INVALID_EXECUTESTATE";
            break;
          case -2146498266:
            result = "CBS_E_CANNOT_REMOVE_CONTAINER_DEPENDENCY";
            break;
          case -2146498265:
            result = "CBS_E_ONDEMAND_RESERVICING_REQUIRED";
            break;
          case -2146498264:
            result = "CBS_E_ONLINE_ACTIONS_POSTPONED";
            break;
          default:
            return "Unknown Error";
        }
      }
    }
    else if ( a1 == -2146498481 )
    {
      return "CBS_E_RESOLVE_FAILED";
    }
    else
    {
      switch ( a1 )
      {
        case -2146498534:
          result = "CBS_E_INVALID_DRIVER_OPERATION_KEY";
          break;
        case -2146498533:
          result = "CBS_E_UNEXPECTED_PROCESSOR_ARCHITECTURE";
          break;
        case -2146498532:
          result = "CBS_E_EXCESSIVE_EVALUATION";
          break;
        case -2146498531:
          result = "CBS_E_CYCLE_EVALUATION";
          break;
        case -2146498530:
          result = "CBS_E_NOT_APPLICABLE ";
          break;
        case -2146498529:
          result = "CBS_E_SOURCE_MISSING";
          break;
        case -2146498528:
          result = "CBS_E_CANCEL";
          break;
        case -2146498527:
          result = "CBS_E_ABORT";
          break;
        case -2146498526:
          result = "CBS_E_ILLEGAL_COMPONENT_UPDATE";
          break;
        case -2146498525:
          result = "CBS_E_NEW_SERVICING_STACK_REQUIRED";
          break;
        case -2146498524:
          result = "CBS_E_SOURCE_NOT_IN_LIST";
          break;
        case -2146498523:
          result = "CBS_E_CANNOT_REMOVE";
          break;
        case -2146498522:
          result = "CBS_E_PENDING_VICTIM";
          break;
        case -2146498521:
          result = "CBS_E_STACK_SHUTDOWN_REQUIRED";
          break;
        case -2146498520:
          result = "CBS_E_INSUFFICIENT_DISK_SPACE";
          break;
        case -2146498519:
          result = "CBS_E_AC_POWER_REQUIRED";
          break;
        case -2146498518:
          result = "CBS_E_STACK_UPDATE_FAILED_REBOOT_REQUIRED";
          break;
        case -2146498517:
          result = "CBS_E_SQM_REPORT_IGNORED_AI_FAILURES_ON_TRANSACTION_RESOLVE";
          break;
        case -2146498516:
          result = "CBS_E_DEPENDENT_FAILURE";
          break;
        case -2146498515:
          result = "CBS_E_PAC_INITIAL_FAILURE";
          break;
        case -2146498514:
          result = "CBS_E_NOT_ALLOWED_OFFLINE";
          break;
        case -2146498513:
          result = "CBS_E_EXCLUSIVE_WOULD_MERGE";
          break;
        case -2146498512:
          result = "CBS_E_IMAGE_UNSERVICEABLE";
          break;
        case -2146498511:
          result = "CBS_E_STORE_CORRUPTION";
          break;
        case -2146498510:
          result = "CBS_E_STORE_TOO_MUCH_CORRUPTION";
          break;
        case -2146498509:
          result = "CBS_S_STACK_RESTART_REQUIRED";
          break;
        case -2146498508:
          result = "CBS_E_CANNOT_USE_PNP_DRIVER_ON_DECONSTRUCTED_DRIVER_IMAGE";
          break;
        case -2146498507:
          result = "CBS_E_STACK_SHUTTING_DOWN";
          break;
        case -2146498506:
          result = "CBS_E_MUV6_STACK_SHUTDOWN_NEEDED";
          break;
        case -2146498505:
          result = "CBS_E_POSTPONED_INSTALL_CONSIDERED";
          break;
        case -2146498504:
          result = "CBS_E_RESERVICING_REQUIRED_BASELINE";
          break;
        case -2146498503:
          result = "CBS_E_RPT_CRASHED";
          break;
        case -2146498496:
          result = "CBS_E_SESSION_CORRUPT";
          break;
        case -2146498495:
          result = "CBS_E_SESSION_INTERRUPTED";
          break;
        case -2146498494:
          result = "CBS_E_SESSION_FINALIZED";
          break;
        case -2146498493:
          result = "CBS_E_SESSION_READONLY";
          break;
        case -2146498490:
          result = "CBS_E_NOT_SUPPORTED_ON_IMAGE_TYPE";
          break;
        default:
          return "Unknown Error";
      }
    }
  }
  else if ( a1 == -2146498535 )
  {
    return "CBS_E_DUPLICATE_UPDATENAME";
  }
  else if ( a1 > -2146500049 )
  {
    if ( a1 > -2146499840 )
    {
      switch ( a1 )
      {
        case -2146498560:
          result = "CBS_E_INTERNAL_ERROR";
          break;
        case -2146498559:
          result = "CBS_E_NOT_INITIALIZED";
          break;
        case -2146498558:
          result = "CBS_E_ALREADY_INITIALIZED";
          break;
        case -2146498557:
          result = "CBS_E_INVALID_PARAMETER";
          break;
        case -2146498556:
          result = "CBS_E_OPEN_FAILED";
          break;
        case -2146498555:
          result = "CBS_E_INVALID_PACKAGE";
          break;
        case -2146498554:
          result = "CBS_E_PENDING";
          break;
        case -2146498553:
          result = "CBS_E_NOT_INSTALLABLE";
          break;
        case -2146498552:
          result = "CBS_E_IMAGE_NOT_ACCESSIBLE";
          break;
        case -2146498551:
          result = "CBS_E_ARRAY_ELEMENT_MISSING";
          break;
        case -2146498550:
          result = "CBS_E_REESTABLISH_SESSION";
          break;
        case -2146498549:
          result = "CBS_E_PROPERTY_NOT_AVAILABLE";
          break;
        case -2146498548:
          result = "CBS_E_UNKNOWN_UPDATE";
          break;
        case -2146498547:
          result = "CBS_E_MANIFEST_INVALID_ITEM";
          break;
        case -2146498546:
          result = "CBS_E_MANIFEST_VALIDATION_DUPLICATE_ATTRIBUTES";
          break;
        case -2146498545:
          result = "CBS_E_MANIFEST_VALIDATION_DUPLICATE_ELEMENT";
          break;
        case -2146498544:
          result = "CBS_E_MANIFEST_VALIDATION_MISSING_REQUIRED_ATTRIBUTES";
          break;
        case -2146498543:
          result = "CBS_E_MANIFEST_VALIDATION_MISSING_REQUIRED_ELEMENTS";
          break;
        case -2146498542:
          result = "CBS_E_MANIFEST_VALIDATION_UPDATES_PARENT_MISSING";
          break;
        case -2146498541:
          result = "CBS_E_INVALID_INSTALL_STATE";
          break;
        case -2146498540:
          result = "CBS_E_INVALID_CONFIG_VALUE";
          break;
        case -2146498539:
          result = "CBS_E_INVALID_CARDINALITY";
          break;
        case -2146498538:
          result = "CBS_E_DPX_JOB_STATE_SAVED";
          break;
        case -2146498537:
          result = "CBS_E_PACKAGE_DELETED";
          break;
        case -2146498536:
          result = "CBS_E_IDENTITY_MISMATCH";
          break;
        default:
          return "Unknown Error";
      }
    }
    else if ( a1 == -2146499840 )
    {
      return "SPAPI_E_UNRECOVERABLE_STACK_OVERFLOW";
    }
    else
    {
      switch ( a1 )
      {
        case -2146500048:
          result = "SPAPI_E_DEVINSTALL_QUEUE_NONNATIVE";
          break;
        case -2146500047:
          result = "SPAPI_E_NOT_DISABLEABLE";
          break;
        case -2146500046:
          result = "SPAPI_E_CANT_REMOVE_DEVINST";
          break;
        case -2146500045:
          result = "SPAPI_E_INVALID_TARGET";
          break;
        case -2146500044:
          result = "SPAPI_E_DRIVER_NONNATIVE";
          break;
        case -2146500043:
          result = "SPAPI_E_IN_WOW64";
          break;
        case -2146500042:
          result = "SPAPI_E_SET_SYSTEM_RESTORE_POINT";
          break;
        case -2146500041:
          result = "SPAPI_E_INCORRECTLY_COPIED_INF";
          break;
        case -2146500040:
          result = "SPAPI_E_SCE_DISABLED";
          break;
        case -2146500039:
          result = "SPAPI_E_UNKNOWN_EXCEPTION";
          break;
        case -2146500038:
          result = "SPAPI_E_PNP_REGISTRY_ERROR";
          break;
        case -2146500037:
          result = "SPAPI_E_REMOTE_REQUEST_UNSUPPORTED";
          break;
        case -2146500036:
          result = "SPAPI_E_NOT_AN_INSTALLED_OEM_INF";
          break;
        case -2146500035:
          result = "SPAPI_E_INF_IN_USE_BY_DEVICES";
          break;
        case -2146500034:
          result = "SPAPI_E_DI_FUNCTION_OBSOLETE";
          break;
        case -2146500033:
          result = "SPAPI_E_NO_AUTHENTICODE_CATALOG";
          break;
        case -2146500032:
          result = "SPAPI_E_AUTHENTICODE_DISALLOWED";
          break;
        case -2146500031:
          result = "SPAPI_E_AUTHENTICODE_TRUSTED_PUBLISHER";
          break;
        case -2146500030:
          result = "SPAPI_E_AUTHENTICODE_TRUST_NOT_ESTABLISHED";
          break;
        case -2146500029:
          result = "SPAPI_E_AUTHENTICODE_PUBLISHER_NOT_TRUSTED";
          break;
        case -2146500028:
          result = "SPAPI_E_SIGNATURE_OSATTRIBUTE_MISMATCH";
          break;
        case -2146500027:
          result = "SPAPI_E_ONLY_VALIDATE_VIA_AUTHENTICODE";
          break;
        case -2146500026:
          result = "SPAPI_E_DEVICE_INSTALLER_NOT_READY";
          break;
        case -2146500025:
          result = "SPAPI_E_DRIVER_STORE_ADD_FAILED";
          break;
        case -2146500024:
          result = "SPAPI_E_DEVICE_INSTALL_BLOCKED";
          break;
        case -2146500023:
          result = "SPAPI_E_DRIVER_INSTALL_BLOCKED";
          break;
        case -2146500022:
          result = "SPAPI_E_WRONG_INF_TYPE";
          break;
        case -2146500021:
          result = "SPAPI_E_FILE_HASH_NOT_IN_CATALOG";
          break;
        case -2146500020:
          result = "SPAPI_E_DRIVER_STORE_DELETE_FAILED";
          break;
        default:
          return "Unknown Error";
      }
    }
  }
  else if ( a1 == -2146500049 )
  {
    return "SPAPI_E_NO_CATALOG_FOR_OEM_INF";
  }
  else if ( a1 > -2146500077 )
  {
    switch ( a1 )
    {
      case -2146500076:
        result = "SPAPI_E_DI_BAD_PATH";
        break;
      case -2146500075:
        result = "SPAPI_E_NO_CLASSINSTALL_PARAMS";
        break;
      case -2146500074:
        result = "SPAPI_E_FILEQUEUE_LOCKED";
        break;
      case -2146500073:
        result = "SPAPI_E_BAD_SERVICE_INSTALLSECT";
        break;
      case -2146500072:
        result = "SPAPI_E_NO_CLASS_DRIVER_LIST";
        break;
      case -2146500071:
        result = "SPAPI_E_NO_ASSOCIATED_SERVICE";
        break;
      case -2146500070:
        result = "SPAPI_E_NO_DEFAULT_DEVICE_INTERFACE";
        break;
      case -2146500069:
        result = "SPAPI_E_DEVICE_INTERFACE_ACTIVE";
        break;
      case -2146500068:
        result = "SPAPI_E_DEVICE_INTERFACE_REMOVED";
        break;
      case -2146500067:
        result = "SPAPI_E_BAD_INTERFACE_INSTALLSECT";
        break;
      case -2146500066:
        result = "SPAPI_E_NO_SUCH_INTERFACE_CLASS";
        break;
      case -2146500065:
        result = "SPAPI_E_INVALID_REFERENCE_STRING";
        break;
      case -2146500064:
        result = "SPAPI_E_INVALID_MACHINENAME";
        break;
      case -2146500063:
        result = "SPAPI_E_REMOTE_COMM_FAILURE";
        break;
      case -2146500062:
        result = "SPAPI_E_MACHINE_UNAVAILABLE";
        break;
      case -2146500061:
        result = "SPAPI_E_NO_CONFIGMGR_SERVICES";
        break;
      case -2146500060:
        result = "SPAPI_E_INVALID_PROPPAGE_PROVIDER";
        break;
      case -2146500059:
        result = "SPAPI_E_NO_SUCH_DEVICE_INTERFACE";
        break;
      case -2146500058:
        result = "SPAPI_E_DI_POSTPROCESSING_REQUIRED";
        break;
      case -2146500057:
        result = "SPAPI_E_INVALID_COINSTALLER";
        break;
      case -2146500056:
        result = "SPAPI_E_NO_COMPAT_DRIVERS";
        break;
      case -2146500055:
        result = "SPAPI_E_NO_DEVICE_ICON";
        break;
      case -2146500054:
        result = "SPAPI_E_INVALID_INF_LOGCONFIG";
        break;
      case -2146500053:
        result = "SPAPI_E_DI_DONT_INSTALL";
        break;
      case -2146500052:
        result = "SPAPI_E_INVALID_FILTER_DRIVER";
        break;
      case -2146500051:
        result = "SPAPI_E_NON_WINDOWS_NT_DRIVER";
        break;
      case -2146500050:
        result = "SPAPI_E_NON_WINDOWS_DRIVER";
        break;
      default:
        return "Unknown Error";
    }
  }
  else if ( a1 == -2146500077 )
  {
    return "SPAPI_E_DEVINFO_DATA_LOCKED";
  }
  else if ( a1 > -2146500091 )
  {
    switch ( a1 )
    {
      case -2146500090:
        result = "SPAPI_E_INVALID_CLASS";
        break;
      case -2146500089:
        result = "SPAPI_E_DEVINST_ALREADY_EXISTS";
        break;
      case -2146500088:
        result = "SPAPI_E_DEVINFO_NOT_REGISTERED";
        break;
      case -2146500087:
        result = "SPAPI_E_INVALID_REG_PROPERTY";
        break;
      case -2146500086:
        result = "SPAPI_E_NO_INF";
        break;
      case -2146500085:
        result = "SPAPI_E_NO_SUCH_DEVINST";
        break;
      case -2146500084:
        result = "SPAPI_E_CANT_LOAD_CLASS_ICON";
        break;
      case -2146500083:
        result = "SPAPI_E_INVALID_CLASS_INSTALLER";
        break;
      case -2146500082:
        result = "SPAPI_E_DI_DO_DEFAULT";
        break;
      case -2146500081:
        result = "SPAPI_E_DI_NOFILECOPY";
        break;
      case -2146500080:
        result = "SPAPI_E_INVALID_HWPROFILE";
        break;
      case -2146500079:
        result = "SPAPI_E_NO_DEVICE_SELECTED";
        break;
      case -2146500078:
        result = "SPAPI_E_DEVINFO_LIST_LOCKED";
        break;
      default:
        return "Unknown Error";
    }
  }
  else if ( a1 == -2146500091 )
  {
    return "SPAPI_E_INVALID_DEVINST_NAME";
  }
  else
  {
    if ( a1 > -2146500350 )
    {
      switch ( a1 )
      {
        case -2146500349:
          return "SPAPI_E_NO_BACKUP";
        case -2146500096:
          return "SPAPI_E_NO_ASSOCIATED_CLASS";
        case -2146500095:
          return "SPAPI_E_CLASS_MISMATCH";
        case -2146500094:
          return "SPAPI_E_DUPLICATE_FOUND";
        case -2146500093:
          return "SPAPI_E_NO_DRIVER_SELECTED";
      }
      v1 = "SPAPI_E_KEY_DOES_NOT_EXIST";
      v2 = a1 == -2146500092;
    }
    else
    {
      switch ( a1 )
      {
        case -2146500350:
          return "SPAPI_E_LINE_NOT_FOUND";
        case -2146500608:
          return "SPAPI_E_EXPECTED_SECTION_NAME";
        case -2146500607:
          return "SPAPI_E_BAD_SECTION_NAME_LINE";
        case -2146500606:
          return "SPAPI_E_SECTION_NAME_TOO_LONG";
        case -2146500605:
          return "SPAPI_E_GENERAL_SYNTAX";
        case -2146500352:
          return "SPAPI_E_WRONG_INF_STYLE";
      }
      v1 = "SPAPI_E_SECTION_NOT_FOUND";
      v2 = a1 == -2146500351;
    }
    result = "Unknown Error";
    if ( v2 )
      return v1;
  }
  return result;
}

```

## disassembly

```asm
0x14001b5d0  mov     eax, 800F0819h
0x14001b5d5  cmp     ecx, eax
0x14001b5d7  jg      loc_14001BAB6
0x14001b5dd  jz      loc_14001BAAE
0x14001b5e3  mov     eax, 800F022Fh
0x14001b5e8  cmp     ecx, eax
0x14001b5ea  jg      loc_14001B899
0x14001b5f0  jz      loc_14001B891
0x14001b5f6  mov     eax, 800F0213h
0x14001b5fb  cmp     ecx, eax
0x14001b5fd  jg      loc_14001B794
0x14001b603  jz      loc_14001B78C
0x14001b609  mov     eax, 800F0205h
0x14001b60e  cmp     ecx, eax
0x14001b610  jg      loc_14001B6FF
0x14001b616  jz      loc_14001B6F7
0x14001b61c  mov     eax, 800F0102h
0x14001b621  cmp     ecx, eax
0x14001b623  jg      short loc_14001B68E
0x14001b625  jz      short loc_14001B686
0x14001b627  cmp     ecx, 800F0000h
0x14001b62d  jz      short loc_14001B67E
0x14001b62f  cmp     ecx, 800F0001h
0x14001b635  jz      short loc_14001B676
0x14001b637  cmp     ecx, 800F0002h
0x14001b63d  jz      short loc_14001B66E
0x14001b63f  cmp     ecx, 800F0003h
0x14001b645  jz      short loc_14001B666
0x14001b647  cmp     ecx, 800F0100h
0x14001b64d  jz      short loc_14001B65E
0x14001b64f  lea     rdx, aSpapiESectionN_0; "SPAPI_E_SECTION_NOT_FOUND"
0x14001b656  cmp     ecx, 800F0101h
0x14001b65c  jmp     short loc_14001B6C3
0x14001b65e  lea     rax, aSpapiEWrongInf; "SPAPI_E_WRONG_INF_STYLE"
0x14001b665  retn
0x14001b666  lea     rax, aSpapiEGeneralS; "SPAPI_E_GENERAL_SYNTAX"
0x14001b66d  retn
0x14001b66e  lea     rax, aSpapiESectionN; "SPAPI_E_SECTION_NAME_TOO_LONG"
0x14001b675  retn
0x14001b676  lea     rax, aSpapiEBadSecti; "SPAPI_E_BAD_SECTION_NAME_LINE"
0x14001b67d  retn
0x14001b67e  lea     rax, aSpapiEExpected; "SPAPI_E_EXPECTED_SECTION_NAME"
0x14001b685  retn
0x14001b686  lea     rax, aSpapiELineNotF; "SPAPI_E_LINE_NOT_FOUND"
0x14001b68d  retn
0x14001b68e  cmp     ecx, 800F0103h
0x14001b694  jz      short loc_14001B6EF
0x14001b696  cmp     ecx, 800F0200h
0x14001b69c  jz      short loc_14001B6E7
0x14001b69e  cmp     ecx, 800F0201h
0x14001b6a4  jz      short loc_14001B6DF
0x14001b6a6  cmp     ecx, 800F0202h
0x14001b6ac  jz      short loc_14001B6D7
0x14001b6ae  cmp     ecx, 800F0203h
0x14001b6b4  jz      short loc_14001B6CF
0x14001b6b6  lea     rdx, aSpapiEKeyDoesN; "SPAPI_E_KEY_DOES_NOT_EXIST"
0x14001b6bd  cmp     ecx, 800F0204h
0x14001b6c3  lea     rax, Str2; "Unknown Error"
0x14001b6ca  cmovz   rax, rdx
0x14001b6ce  retn
0x14001b6cf  lea     rax, aSpapiENoDriver; "SPAPI_E_NO_DRIVER_SELECTED"
0x14001b6d6  retn
0x14001b6d7  lea     rax, aSpapiEDuplicat; "SPAPI_E_DUPLICATE_FOUND"
0x14001b6de  retn
0x14001b6df  lea     rax, aSpapiEClassMis; "SPAPI_E_CLASS_MISMATCH"
0x14001b6e6  retn
0x14001b6e7  lea     rax, aSpapiENoAssoci_0; "SPAPI_E_NO_ASSOCIATED_CLASS"
0x14001b6ee  retn
0x14001b6ef  lea     rax, aSpapiENoBackup; "SPAPI_E_NO_BACKUP"
0x14001b6f6  retn
0x14001b6f7  lea     rax, aSpapiEInvalidD; "SPAPI_E_INVALID_DEVINST_NAME"
0x14001b6fe  retn
0x14001b6ff  add     ecx, 7FF0FDFAh; switch 13 cases
0x14001b705  cmp     ecx, 0Ch
0x14001b708  ja      def_14001B722; jumptable 000000014001B722 default case
0x14001b70e  lea     rdx, cs:140000000h
0x14001b715  movsxd  rax, ecx
0x14001b718  mov     eax, ds:(jpt_14001B722 - 140000000h)[rdx+rax*4]
0x14001b71f  add     rax, rdx
0x14001b722  jmp     rax; switch jump
0x14001b724  lea     rax, aSpapiEInvalidC_0; jumptable 000000014001B722 case -2146500090
0x14001b72b  retn
0x14001b72c  lea     rax, aSpapiEDevinstA; jumptable 000000014001B722 case -2146500089
0x14001b733  retn
0x14001b734  lea     rax, aSpapiEDevinfoN; jumptable 000000014001B722 case -2146500088
0x14001b73b  retn
0x14001b73c  lea     rax, aSpapiEInvalidR; jumptable 000000014001B722 case -2146500087
0x14001b743  retn
0x14001b744  lea     rax, aSpapiENoInf; jumptable 000000014001B722 case -2146500086
0x14001b74b  retn
0x14001b74c  lea     rax, aSpapiENoSuchDe; jumptable 000000014001B722 case -2146500085
0x14001b753  retn
0x14001b754  lea     rax, aSpapiECantLoad; jumptable 000000014001B722 case -2146500084
0x14001b75b  retn
0x14001b75c  lea     rax, aSpapiEInvalidC; jumptable 000000014001B722 case -2146500083
0x14001b763  retn
0x14001b764  lea     rax, aSpapiEDiDoDefa; jumptable 000000014001B722 case -2146500082
0x14001b76b  retn
0x14001b76c  lea     rax, aSpapiEDiNofile; jumptable 000000014001B722 case -2146500081
0x14001b773  retn
0x14001b774  lea     rax, aSpapiEInvalidH; jumptable 000000014001B722 case -2146500080
0x14001b77b  retn
0x14001b77c  lea     rax, aSpapiENoDevice; jumptable 000000014001B722 case -2146500079
0x14001b783  retn
0x14001b784  lea     rax, aSpapiEDevinfoL; jumptable 000000014001B722 case -2146500078
0x14001b78b  retn
0x14001b78c  lea     rax, aSpapiEDevinfoD; "SPAPI_E_DEVINFO_DATA_LOCKED"
0x14001b793  retn
0x14001b794  add     ecx, 7FF0FDECh; switch 27 cases
0x14001b79a  cmp     ecx, 1Ah
0x14001b79d  ja      def_14001B722; jumptable 000000014001B722 default case
0x14001b7a3  lea     rdx, cs:140000000h
0x14001b7aa  movsxd  rax, ecx
0x14001b7ad  mov     eax, ds:(jpt_14001B7B7 - 140000000h)[rdx+rax*4]
0x14001b7b4  add     rax, rdx
0x14001b7b7  jmp     rax; switch jump
0x14001b7b9  lea     rax, aSpapiEDiBadPat; jumptable 000000014001B7B7 case -2146500076
0x14001b7c0  retn
0x14001b7c1  lea     rax, aSpapiENoClassi; jumptable 000000014001B7B7 case -2146500075
0x14001b7c8  retn
0x14001b7c9  lea     rax, aSpapiEFilequeu; jumptable 000000014001B7B7 case -2146500074
0x14001b7d0  retn
0x14001b7d1  lea     rax, aSpapiEBadServi; jumptable 000000014001B7B7 case -2146500073
0x14001b7d8  retn
0x14001b7d9  lea     rax, aSpapiENoClassD; jumptable 000000014001B7B7 case -2146500072
0x14001b7e0  retn
0x14001b7e1  lea     rax, aSpapiENoAssoci; jumptable 000000014001B7B7 case -2146500071
0x14001b7e8  retn
0x14001b7e9  lea     rax, aSpapiENoDefaul; jumptable 000000014001B7B7 case -2146500070
0x14001b7f0  retn
0x14001b7f1  lea     rax, aSpapiEDeviceIn_1; jumptable 000000014001B7B7 case -2146500069
0x14001b7f8  retn
0x14001b7f9  lea     rax, aSpapiEDeviceIn_0; jumptable 000000014001B7B7 case -2146500068
0x14001b800  retn
0x14001b801  lea     rax, aSpapiEBadInter; jumptable 000000014001B7B7 case -2146500067
0x14001b808  retn
0x14001b809  lea     rax, aSpapiENoSuchIn; jumptable 000000014001B7B7 case -2146500066
0x14001b810  retn
0x14001b811  lea     rax, aSpapiEInvalidR_0; jumptable 000000014001B7B7 case -2146500065
0x14001b818  retn
0x14001b819  lea     rax, aSpapiEInvalidM; jumptable 000000014001B7B7 case -2146500064
0x14001b820  retn
0x14001b821  lea     rax, aSpapiERemoteCo; jumptable 000000014001B7B7 case -2146500063
0x14001b828  retn
0x14001b829  lea     rax, aSpapiEMachineU; jumptable 000000014001B7B7 case -2146500062
0x14001b830  retn
0x14001b831  lea     rax, aSpapiENoConfig; jumptable 000000014001B7B7 case -2146500061
0x14001b838  retn
0x14001b839  lea     rax, aSpapiEInvalidP; jumptable 000000014001B7B7 case -2146500060
0x14001b840  retn
0x14001b841  lea     rax, aSpapiENoSuchDe_0; jumptable 000000014001B7B7 case -2146500059
0x14001b848  retn
0x14001b849  lea     rax, aSpapiEDiPostpr; jumptable 000000014001B7B7 case -2146500058
0x14001b850  retn
0x14001b851  lea     rax, aSpapiEInvalidC_1; jumptable 000000014001B7B7 case -2146500057
0x14001b858  retn
0x14001b859  lea     rax, aSpapiENoCompat; jumptable 000000014001B7B7 case -2146500056
0x14001b860  retn
0x14001b861  lea     rax, aSpapiENoDevice_0; jumptable 000000014001B7B7 case -2146500055
0x14001b868  retn
0x14001b869  lea     rax, aSpapiEInvalidI; jumptable 000000014001B7B7 case -2146500054
0x14001b870  retn
0x14001b871  lea     rax, aSpapiEDiDontIn; jumptable 000000014001B7B7 case -2146500053
0x14001b878  retn
0x14001b879  lea     rax, aSpapiEInvalidF; jumptable 000000014001B7B7 case -2146500052
0x14001b880  retn
0x14001b881  lea     rax, aSpapiENonWindo_0; jumptable 000000014001B7B7 case -2146500051
0x14001b888  retn
0x14001b889  lea     rax, aSpapiENonWindo; jumptable 000000014001B7B7 case -2146500050
0x14001b890  retn
0x14001b891  lea     rax, aSpapiENoCatalo; "SPAPI_E_NO_CATALOG_FOR_OEM_INF"
0x14001b898  retn
0x14001b899  mov     eax, 800F0300h
0x14001b89e  cmp     ecx, eax
0x14001b8a0  jg      loc_14001B9C1
0x14001b8a6  jz      loc_14001B9B9
0x14001b8ac  add     ecx, 7FF0FDD0h; switch 29 cases
0x14001b8b2  cmp     ecx, 1Ch
0x14001b8b5  ja      def_14001B722; jumptable 000000014001B722 default case
0x14001b8bb  lea     rdx, cs:140000000h
0x14001b8c2  movsxd  rax, ecx
0x14001b8c5  mov     eax, ds:(jpt_14001B8CF - 140000000h)[rdx+rax*4]
0x14001b8cc  add     rax, rdx
0x14001b8cf  jmp     rax; switch jump
0x14001b8d1  lea     rax, aSpapiEDevinsta; jumptable 000000014001B8CF case -2146500048
0x14001b8d8  retn
0x14001b8d9  lea     rax, aSpapiENotDisab; jumptable 000000014001B8CF case -2146500047
0x14001b8e0  retn
0x14001b8e1  lea     rax, aSpapiECantRemo; jumptable 000000014001B8CF case -2146500046
0x14001b8e8  retn
0x14001b8e9  lea     rax, aSpapiEInvalidT; jumptable 000000014001B8CF case -2146500045
0x14001b8f0  retn
0x14001b8f1  lea     rax, aSpapiEDriverNo; jumptable 000000014001B8CF case -2146500044
0x14001b8f8  retn
0x14001b8f9  lea     rax, aSpapiEInWow64; jumptable 000000014001B8CF case -2146500043
0x14001b900  retn
0x14001b901  lea     rax, aSpapiESetSyste; jumptable 000000014001B8CF case -2146500042
0x14001b908  retn
0x14001b909  lea     rax, aSpapiEIncorrec; jumptable 000000014001B8CF case -2146500041
0x14001b910  retn
0x14001b911  lea     rax, aSpapiESceDisab; jumptable 000000014001B8CF case -2146500040
0x14001b918  retn
0x14001b919  lea     rax, aSpapiEUnknownE; jumptable 000000014001B8CF case -2146500039
0x14001b920  retn
0x14001b921  lea     rax, aSpapiEPnpRegis; jumptable 000000014001B8CF case -2146500038
0x14001b928  retn
0x14001b929  lea     rax, aSpapiERemoteRe; jumptable 000000014001B8CF case -2146500037
0x14001b930  retn
0x14001b931  lea     rax, aSpapiENotAnIns; jumptable 000000014001B8CF case -2146500036
0x14001b938  retn
0x14001b939  lea     rax, aSpapiEInfInUse; jumptable 000000014001B8CF case -2146500035
0x14001b940  retn
0x14001b941  lea     rax, aSpapiEDiFuncti; jumptable 000000014001B8CF case -2146500034
0x14001b948  retn
0x14001b949  lea     rax, aSpapiENoAuthen; jumptable 000000014001B8CF case -2146500033
0x14001b950  retn
0x14001b951  lea     rax, aSpapiEAuthenti_1; jumptable 000000014001B8CF case -2146500032
0x14001b958  retn
0x14001b959  lea     rax, aSpapiEAuthenti_2; jumptable 000000014001B8CF case -2146500031
0x14001b960  retn
0x14001b961  lea     rax, aSpapiEAuthenti; jumptable 000000014001B8CF case -2146500030
0x14001b968  retn
0x14001b969  lea     rax, aSpapiEAuthenti_0; jumptable 000000014001B8CF case -2146500029
0x14001b970  retn
0x14001b971  lea     rax, aSpapiESignatur; jumptable 000000014001B8CF case -2146500028
0x14001b978  retn
0x14001b979  lea     rax, aSpapiEOnlyVali; jumptable 000000014001B8CF case -2146500027
0x14001b980  retn
0x14001b981  lea     rax, aSpapiEDeviceIn; jumptable 000000014001B8CF case -2146500026
0x14001b988  retn
0x14001b989  lea     rax, aSpapiEDriverSt; jumptable 000000014001B8CF case -2146500025
0x14001b990  retn
0x14001b991  lea     rax, aSpapiEDeviceIn_2; jumptable 000000014001B8CF case -2146500024
0x14001b998  retn
0x14001b999  lea     rax, aSpapiEDriverIn; jumptable 000000014001B8CF case -2146500023
0x14001b9a0  retn
0x14001b9a1  lea     rax, aSpapiEWrongInf_0; jumptable 000000014001B8CF case -2146500022
0x14001b9a8  retn
0x14001b9a9  lea     rax, aSpapiEFileHash; jumptable 000000014001B8CF case -2146500021
0x14001b9b0  retn
0x14001b9b1  lea     rax, aSpapiEDriverSt_0; jumptable 000000014001B8CF case -2146500020
0x14001b9b8  retn
0x14001b9b9  lea     rax, aSpapiEUnrecove; "SPAPI_E_UNRECOVERABLE_STACK_OVERFLOW"
0x14001b9c0  retn
0x14001b9c1  add     ecx, 7FF0F800h; switch 25 cases
0x14001b9c7  cmp     ecx, 18h
0x14001b9ca  ja      def_14001B722; jumptable 000000014001B722 default case
0x14001b9d0  lea     rdx, cs:140000000h
0x14001b9d7  movsxd  rax, ecx
0x14001b9da  mov     eax, ds:(jpt_14001B9E4 - 140000000h)[rdx+rax*4]
0x14001b9e1  add     rax, rdx
0x14001b9e4  jmp     rax; switch jump
0x14001b9e6  lea     rax, aCbsEInternalEr; jumptable 000000014001B9E4 case -2146498560
0x14001b9ed  retn
0x14001b9ee  lea     rax, aCbsENotInitial; jumptable 000000014001B9E4 case -2146498559
0x14001b9f5  retn
0x14001b9f6  lea     rax, aCbsEAlreadyIni; jumptable 000000014001B9E4 case -2146498558
0x14001b9fd  retn
0x14001b9fe  lea     rax, aCbsEInvalidPar; jumptable 000000014001B9E4 case -2146498557
0x14001ba05  retn
0x14001ba06  lea     rax, aCbsEOpenFailed; jumptable 000000014001B9E4 case -2146498556
0x14001ba0d  retn
0x14001ba0e  lea     rax, aCbsEInvalidPac; jumptable 000000014001B9E4 case -2146498555
0x14001ba15  retn
0x14001ba16  lea     rax, aCbsEPending; jumptable 000000014001B9E4 case -2146498554
0x14001ba1d  retn
0x14001ba1e  lea     rax, aCbsENotInstall; jumptable 000000014001B9E4 case -2146498553
0x14001ba25  retn
0x14001ba26  lea     rax, aCbsEImageNotAc; jumptable 000000014001B9E4 case -2146498552
0x14001ba2d  retn
0x14001ba2e  lea     rax, aCbsEArrayEleme; jumptable 000000014001B9E4 case -2146498551
0x14001ba35  retn
0x14001ba36  lea     rax, aCbsEReestablis; jumptable 000000014001B9E4 case -2146498550
0x14001ba3d  retn
0x14001ba3e  lea     rax, aCbsEPropertyNo; jumptable 000000014001B9E4 case -2146498549
0x14001ba45  retn
0x14001ba46  lea     rax, aCbsEUnknownUpd; jumptable 000000014001B9E4 case -2146498548
0x14001ba4d  retn
0x14001ba4e  lea     rax, aCbsEManifestIn; jumptable 000000014001B9E4 case -2146498547
0x14001ba55  retn
0x14001ba56  lea     rax, aCbsEManifestVa; jumptable 000000014001B9E4 case -2146498546
0x14001ba5d  retn
0x14001ba5e  lea     rax, aCbsEManifestVa_4; jumptable 000000014001B9E4 case -2146498545
0x14001ba65  retn
0x14001ba66  lea     rax, aCbsEManifestVa_2; jumptable 000000014001B9E4 case -2146498544
0x14001ba6d  retn
0x14001ba6e  lea     rax, aCbsEManifestVa_0; jumptable 000000014001B9E4 case -2146498543
0x14001ba75  retn
0x14001ba76  lea     rax, aCbsEManifestVa_1; jumptable 000000014001B9E4 case -2146498542
0x14001ba7d  retn
0x14001ba7e  lea     rax, aCbsEInvalidIns; jumptable 000000014001B9E4 case -2146498541
0x14001ba85  retn
0x14001ba86  lea     rax, aCbsEInvalidCon; jumptable 000000014001B9E4 case -2146498540
0x14001ba8d  retn
0x14001ba8e  lea     rax, aCbsEInvalidCar; jumptable 000000014001B9E4 case -2146498539
0x14001ba95  retn
0x14001ba96  lea     rax, aCbsEDpxJobStat; jumptable 000000014001B9E4 case -2146498538
0x14001ba9d  retn
0x14001ba9e  lea     rax, aCbsEPackageDel; jumptable 000000014001B9E4 case -2146498537
0x14001baa5  retn
  ... truncated ...
```
