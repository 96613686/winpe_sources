# WiFiCxTLVStaging::WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)

- ea: `0x14003a40c`
- end: `0x14003abb2`
- name: `?ToLogString@stringify@WDI_TLV@WiFiCxTLVStaging@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z`
- size: `1958`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140039b80`

## callees

- `0x14003a40c`

## string_xrefs

- `0x14003a491`: `WDI_TASK_OPEN`
- `0x14003a488`: `WDI_TASK_CLOSE`
- `0x14003a476`: `WDI_TASK_SCAN`
- `0x14003a46d`: `WDI_TASK_P2P_DISCOVER`
- `0x14003a464`: `WDI_TASK_CONNECT`
- `0x14003a45b`: `WDI_TASK_DOT11_RESET`
- `0x14003a49a`: `WDI_TASK_DISCONNECT`
- `0x14003a500`: `WDI_TASK_P2P_SEND_REQUEST_ACTION_FRAME`
- `0x14003a4f7`: `WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME`
- `0x14003a4ee`: `WDI_TASK_SET_RADIO_STATE`
- `0x14003a4e5`: `WDI_TASK_CREATE_PORT`
- `0x14003a4dc`: `WDI_TASK_DELETE_PORT`
- `0x14003a4d3`: `WDI_TASK_START_AP`
- `0x14003a4ca`: `WDI_TASK_STOP_AP`
- `0x14003a509`: `WDI_TASK_SEND_AP_ASSOCIATION_RESPONSE`
- `0x14003a576`: `WDI_TASK_SET_READY_TO_RECEIVE_INDICATIONS`
- `0x14003a564`: `WDI_INDICATION_DISCONNECT_COMPLETE`
- `0x14003a55b`: `WDI_INDICATION_SET_RADIO_STATE_COMPLETE`
- `0x14003a552`: `WDI_INDICATION_SET_READY_TO_RECEIVE_INDICATIONS_COMPLETE`
- `0x14003a5dc`: `WDI_SET_DELETE_CIPHER_KEYS`
- `0x14003a651`: `WDI_INDICATION_LINK_STATE_CHANGE`
- `0x14003a6a4`: `WDI_INDICATION_SCAN_COMPLETE`
- `0x14003a69b`: `WDI_INDICATION_P2P_DISCOVERY_COMPLETE`
- `0x14003a719`: `WDI_INDICATION_DOT11_RESET_COMPLETE`
- `0x14003a710`: `WDI_INDICATION_CONNECT_COMPLETE`
- `0x14003a707`: `WDI_INDICATION_P2P_SEND_REQUEST_ACTION_FRAME_COMPLETE`
- `0x14003a6fe`: `WDI_INDICATION_P2P_SEND_RESPONSE_ACTION_FRAME_COMPLETE`
- `0x14003a722`: `WDI_INDICATION_CREATE_PORT_COMPLETE`
- `0x14003a76c`: `WDI_INDICATION_DELETE_PORT_COMPLETE`
- `0x14003a763`: `WDI_INDICATION_START_AP_COMPLETE`
- `0x14003a75a`: `WDI_INDICATION_STOP_AP_COMPLETE`
- `0x14003a751`: `WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE`
- `0x14003a7c3`: `WDI_SET_REMOVE_WOL_PATTERN`
- `0x14003a7b1`: `WDI_SET_ADD_PM_PROTOCOL_OFFLOAD`
- `0x14003a7de`: `WDI_SET_REMOVE_PM_PROTOCOL_OFFLOAD`
- `0x14003a81f`: `WDI_SET_ADAPTER_CONFIGURATION`
- `0x14003a804`: `WDI_GET_PM_PROTOCOL_OFFLOAD`
- `0x14003a882`: `WDI_TASK_CHANGE_OPERATION_MODE`
- `0x14003a879`: `WDI_INDICATION_CHANGE_OPERATION_MODE_COMPLETE`
- `0x14003a85e`: `WDI_INDICATION_OPEN_COMPLETE`
- `0x14003a88b`: `WDI_INDICATION_CLOSE_COMPLETE`
- `0x14003a8ac`: `WDI_TASK_ROAM`
- `0x14003a8d0`: `WDI_INDICATION_ROAM_COMPLETE`
- `0x14003a952`: `WDI_TASK_SEND_REQUEST_ACTION_FRAME`
- `0x14003a940`: `WDI_INDICATION_TASK_OFFLOAD_CURRENT_CONFIG`
- `0x14003a937`: `WDI_TASK_SEND_RESPONSE_ACTION_FRAME`
- `0x14003a92e`: `WDI_INDICATION_SEND_REQUEST_ACTION_FRAME_COMPLETE`
- `0x14003a95b`: `WDI_INDICATION_SEND_RESPONSE_ACTION_FRAME_COMPLETE`
- `0x14003a9a5`: `WDI_GET_NEXT_ACTION_FRAME_DIALOG_TOKEN`
- `0x14003a99c`: `WDI_TASK_IHV`
- `0x14003ab05`: `WDI_TASK_REQUEST_FTM`
- `0x14003aafc`: `WDI_INDICATION_REQUEST_FTM_COMPLETE`
- `0x14003a993`: `WDI_INDICATION_IHV_TASK_REQUEST`
- `0x14003a98a`: `WDI_INDICATION_IHV_TASK_COMPLETE`
- `0x14003a748`: `WDI_ABORT_TASK`
- `0x14003aaaf`: `WDI_GET_SUPPORTED_DEVICE_SERVICES`
- `0x14003aaa6`: `WDI_DEVICE_SERVICE_COMMAND`
- `0x14003aa9d`: `WDI_INDICATION_CIPHER_KEY_UPDATED`
- `0x14003aa94`: `WDI_INDICATION_DEVICE_SERVICE_EVENT`
- `0x14003aba1`: `WDI_TEST_TASK`
- `0x14003ab98`: `WDI_TASK_SEND_AUTHENTICATION_FRAME`
- `0x14003ab8f`: `WDI_INDICATION_SEND_AUTHENTICATION_FRAME_COMPLETE`

## pseudocode

```c
const char *__fastcall WiFiCxTLVStaging::WDI_TLV::stringify::ToLogString(unsigned __int16 a1)
{
  if ( a1 > 0x29u )
  {
    if ( a1 > 0x65u )
    {
      if ( a1 <= 0xFFE0u )
      {
        if ( a1 == 65504 )
          return "WDI_TEST_TASK";
        if ( a1 > 0x7Fu )
        {
          if ( a1 > 0xC8u )
          {
            switch ( a1 )
            {
              case 0xC9u:
                return "WDI_TASK_SEND_AUTHENTICATION_FRAME";
              case 0xCAu:
                return "WDI_INDICATION_SEND_AUTHENTICATION_FRAME_COMPLETE";
              case 0xCBu:
                return "WDI_INDICATION_AUTHENTICATION_FRAME_RECEIVED";
              case 0xCCu:
                return "WDI_GET_P2P_DFS_CHANNELS";
              case 0xCDu:
                return "WDI_GET_P2P_OUTGOING_ACTION_FRAME_DETAILS";
              case 0xCEu:
                return "WDI_GET_PCEA";
              case 0xCFu:
                return "WDI_SET_AUTHENTICATION_FRAME_SUBSCRIPTION";
              case 0xD0u:
                return "WDI_SET_P2P_EXPECTED_TRAFFIC_CHARACTERISTICS";
              case 0xD1u:
                return "WDI_SET_USD_ADVERTISEMENTS";
            }
          }
          else
          {
            if ( a1 == 200 )
              return "WDI_INDICATION_SECONDARY_STA_CONNECTIVITY";
            if ( a1 > 0x86u )
            {
              switch ( a1 )
              {
                case 0x87u:
                  return "WDI_SET_SAE_AUTH_PARAMS";
                case 0x88u:
                  return "WDI_TASK_REQUEST_FTM";
                case 0x89u:
                  return "WDI_INDICATION_REQUEST_FTM_COMPLETE";
                case 0x8Au:
                  return "WDI_SET_LOCATION_PRIVACY";
                case 0x8Bu:
                  return "WDI_SET_OWE_DH_IE";
              }
            }
            else
            {
              switch ( a1 )
              {
                case 0x86u:
                  return "WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED";
                case 0x80u:
                  return "WDI_SET_NEIGHBOR_REPORT_ENTRIES";
                case 0x82u:
                  return "WDI_GET_SUPPORTED_DEVICE_SERVICES";
                case 0x83u:
                  return "WDI_DEVICE_SERVICE_COMMAND";
                case 0x84u:
                  return "WDI_INDICATION_CIPHER_KEY_UPDATED";
                case 0x85u:
                  return "WDI_INDICATION_DEVICE_SERVICE_EVENT";
              }
            }
          }
        }
        else
        {
          if ( a1 == 127 )
            return "WDI_SET_FAST_BSS_TRANSITION_PARAMETERS";
          if ( a1 > 0x74u )
          {
            if ( a1 > 0x7Au )
            {
              switch ( a1 )
              {
                case '{':
                  return "WDI_SET_P2P_WPS_ENABLED";
                case '|':
                  return "WDI_SET_ENCAPSULATION_OFFLOAD";
                case '}':
                  return "WDI_SET_END_DWELL_TIME";
                case '~':
                  return "WDI_INDICATION_FT_ASSOC_PARAMS_NEEDED";
              }
            }
            else
            {
              switch ( a1 )
              {
                case 'z':
                  return "WDI_INDICATION_P2P_OPERATING_CHANNEL_ATTRIBUTES";
                case 'u':
                  return "WDI_SET_TCP_OFFLOAD_PARAMETERS";
                case 'v':
                  return "WDI_TCP_RSC_STATISTICS";
                case 'w':
                  return "WDI_SET_P2P_START_BACKGROUND_DISCOVERY";
                case 'x':
                  return "WDI_SET_P2P_STOP_BACKGROUND_DISCOVERY";
                case 'y':
                  return "WDI_INDICATION_FIRMWARE_STALLED";
              }
            }
          }
          else
          {
            if ( a1 == 116 )
              return "WDI_INDICATION_CAN_SUSTAIN_AP";
            if ( a1 > 0x6Bu )
            {
              switch ( a1 )
              {
                case 'l':
                  return "WDI_GET_NEXT_ACTION_FRAME_DIALOG_TOKEN";
                case 'm':
                  return "WDI_TASK_IHV";
                case 'n':
                  return "WDI_INDICATION_IHV_TASK_REQUEST";
                case 'o':
                  return "WDI_INDICATION_IHV_TASK_COMPLETE";
                case 's':
                  return "WDI_INDICATION_STOP_AP";
              }
            }
            else
            {
              switch ( a1 )
              {
                case 'k':
                  return "WDI_INDICATION_SEND_RESPONSE_ACTION_FRAME_COMPLETE";
                case 'f':
                  return "WDI_TASK_SEND_REQUEST_ACTION_FRAME";
                case 'g':
                  return "WDI_INDICATION_ACTION_FRAME_RECEIVED";
                case 'h':
                  return "WDI_INDICATION_TASK_OFFLOAD_CURRENT_CONFIG";
                case 'i':
                  return "WDI_TASK_SEND_RESPONSE_ACTION_FRAME";
                case 'j':
                  return "WDI_INDICATION_SEND_REQUEST_ACTION_FRAME_COMPLETE";
              }
            }
          }
        }
      }
    }
    else
    {
      if ( a1 == 101 )
        return "WDI_INDICATION_ROAM_COMPLETE";
      if ( a1 > 0x4Cu )
      {
        if ( a1 > 0x59u )
        {
          if ( a1 > 0x60u )
          {
            switch ( a1 )
            {
              case 'a':
                return "WDI_SET_FLUSH_BSS_ENTRY";
              case 'b':
                return "WDI_INDICATION_ASSOCIATION_PARAMETERS_REQUEST";
              case 'c':
                return "WDI_SET_ASSOCIATION_PARAMETERS";
              case 'd':
                return "WDI_TASK_ROAM";
            }
          }
          else
          {
            switch ( a1 )
            {
              case '`':
                return "WDI_INDICATION_CLOSE_COMPLETE";
              case 'Z':
                return "WDI_TASK_CHANGE_OPERATION_MODE";
              case '[':
                return "WDI_INDICATION_CHANGE_OPERATION_MODE_COMPLETE";
              case ']':
                return "WDI_IHV_REQUEST";
              case '^':
                return "WDI_INDICATION_IHV_EVENT";
              case '_':
                return "WDI_INDICATION_OPEN_COMPLETE";
            }
          }
        }
        else
        {
          if ( a1 == 89 )
            return "WDI_SET_ADVERTISEMENT_INFORMATION";
          if ( a1 > 0x53u )
          {
            switch ( a1 )
            {
              case 'T':
                return "WDI_INDICATION_P2P_GROUP_OPERATING_CHANNEL";
              case 'U':
                return "WDI_SET_ADAPTER_CONFIGURATION";
              case 'V':
                return "WDI_GET_RECEIVE_COALESCING_MATCH_COUNT";
              case 'W':
                return "WDI_SET_CLEAR_RECEIVE_COALESCING";
              case 'X':
                return "WDI_GET_PM_PROTOCOL_OFFLOAD";
            }
          }
          else
          {
            switch ( a1 )
            {
              case 'S':
                return "WDI_SET_REMOVE_PM_PROTOCOL_OFFLOAD";
              case 'N':
                return "WDI_GET_AUTO_POWER_SAVE";
              case 'O':
                return "WDI_SET_ADD_WOL_PATTERN";
              case 'P':
                return "WDI_SET_REMOVE_WOL_PATTERN";
              case 'Q':
                return "WDI_SET_MULTICAST_LIST";
              case 'R':
                return "WDI_SET_ADD_PM_PROTOCOL_OFFLOAD";
            }
          }
        }
      }
      else
      {
        if ( a1 == 76 )
          return "WDI_INDICATION_ASSOCIATION_RESULT";
        if ( a1 > 0x3Eu )
        {
          if ( a1 > 0x44u )
          {
            switch ( a1 )
            {
              case 'E':
                return "WDI_INDICATION_DELETE_PORT_COMPLETE";
              case 'F':
                return "WDI_INDICATION_START_AP_COMPLETE";
              case 'G':
                return "WDI_INDICATION_STOP_AP_COMPLETE";
              case 'I':
                return "WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE";
              case 'K':
                return "WDI_ABORT_TASK";
            }
          }
          else
          {
            switch ( a1 )
            {
              case 'D':
                return "WDI_INDICATION_CREATE_PORT_COMPLETE";
              case '?':
                return "WDI_INDICATION_DOT11_RESET_COMPLETE";
              case '@':
                return "WDI_INDICATION_CONNECT_COMPLETE";
              case 'A':
                return "WDI_INDICATION_P2P_SEND_REQUEST_ACTION_FRAME_COMPLETE";
              case 'B':
                return "WDI_INDICATION_P2P_SEND_RESPONSE_ACTION_FRAME_COMPLETE";
              case 'C':
                return "WDI_INDICATION_RADIO_STATUS";
            }
          }
        }
        else
        {
          if ( a1 == 62 )
            return "WDI_INDICATION_BSS_ENTRY_LIST";
          if ( a1 > 0x37u )
          {
            switch ( a1 )
            {
              case '8':
                return "WDI_INDICATION_NLO_DISCOVERY";
              case '9':
                return "WDI_INDICATION_WAKE_REASON";
              case ';':
                return "WDI_INDICATION_TKIP_MIC_FAILURE";
              case '<':
                return "WDI_INDICATION_SCAN_COMPLETE";
              case '=':
                return "WDI_INDICATION_P2P_DISCOVERY_COMPLETE";
            }
          }
          else
          {
            switch ( a1 )
            {
              case '7':
                return "WDI_INDICATION_AP_ASSOCIATION_REQUEST_RECEIVED";
              case '/':
                return "WDI_GET_BSS_ENTRY_LIST";
              case '3':
                return "WDI_INDICATION_DISASSOCIATION";
              case '4':
                return "WDI_INDICATION_ROAMING_NEEDED";
              case '5':
                return "WDI_INDICATION_LINK_STATE_CHANGE";
              case '6':
                return "WDI_INDICATION_P2P_ACTION_FRAME_RECEIVED";
            }
          }
        }
      }
    }
  }
  else
  {
    if ( a1 == 41 )
      return "WDI_SET_NETWORK_LIST_OFFLOAD";
    if ( a1 > 0x11u )
    {
      if ( a1 > 0x1Cu )
      {
        switch ( a1 )
        {
          case 0x1Du:
            return "WDI_SET_ADD_CIPHER_KEYS";
          case 0x1Eu:
            return "WDI_SET_DELETE_CIPHER_KEYS";
          case 0x1Fu:
            return "WDI_SET_DEFAULT_KEY_ID";
          case 0x20u:
            return "WDI_SET_CONNECTION_QUALITY";
          case 0x22u:
            return "WDI_GET_STATISTICS";
          case 0x24u:
            return "WDI_SET_RECEIVE_PACKET_FILTER";
          case 0x25u:
            return "WDI_GET_ADAPTER_CAPABILITIES";
        }
      }
      else
      {
        switch ( a1 )
        {
          case 0x1Cu:
            return "WDI_SET_PRIVACY_EXEMPTION_LIST";
          case 0x12u:
            return "WDI_TASK_SET_READY_TO_RECEIVE_INDICATIONS";
          case 0x13u:
            return "WDI_SET_POWER_STATE";
          case 0x15u:
            return "WDI_INDICATION_DISCONNECT_COMPLETE";
          case 0x16u:
            return "WDI_INDICATION_SET_RADIO_STATE_COMPLETE";
          case 0x17u:
            return "WDI_INDICATION_SET_READY_TO_RECEIVE_INDICATIONS_COMPLETE";
          case 0x18u:
            return "WDI_SET_OPERATION_MODE";
          case 0x1Au:
            return "WDI_SET_P2P_LISTEN_STATE";
        }
      }
    }
    else
    {
      if ( a1 == 17 )
        return "WDI_TASK_SEND_AP_ASSOCIATION_RESPONSE";
      if ( a1 > 8u )
      {
        switch ( a1 )
        {
          case 9u:
            return "WDI_TASK_P2P_SEND_REQUEST_ACTION_FRAME";
          case 0xAu:
            return "WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME";
          case 0xBu:
            return "WDI_TASK_SET_RADIO_STATE";
          case 0xCu:
            return "WDI_TASK_CREATE_PORT";
          case 0xDu:
            return "WDI_TASK_DELETE_PORT";
          case 0xEu:
            return "WDI_TASK_START_AP";
          case 0xFu:
            return "WDI_TASK_STOP_AP";
        }
      }
      else
      {
        switch ( a1 )
        {
          case 8u:
            return "WDI_TASK_DISCONNECT";
          case 1u:
            return "WDI_TASK_OPEN";
          case 2u:
            return "WDI_TASK_CLOSE";
          case 3u:
            return "WDI_SET_HOST_DETECT_ERROR";
          case 4u:
            return "WDI_TASK_SCAN";
          case 5u:
            return "WDI_TASK_P2P_DISCOVER";
          case 6u:
            return "WDI_TASK_CONNECT";
          case 7u:
            return "WDI_TASK_DOT11_RESET";
        }
      }
    }
  }
  return "Unknown";
}

```

## disassembly

```asm
0x14003a40c  movzx   edx, cx
0x14003a40f  cmp     edx, 29h ; ')'
0x14003a412  ja      loc_14003A5F7
0x14003a418  jz      loc_14003A5EE
0x14003a41e  cmp     edx, 11h
0x14003a421  ja      loc_14003A512
0x14003a427  jz      loc_14003A509
0x14003a42d  cmp     edx, 8
0x14003a430  ja      short loc_14003A4A3
0x14003a432  jz      short loc_14003A49A
0x14003a434  sub     edx, 1
0x14003a437  jz      short loc_14003A491
0x14003a439  sub     edx, 1
0x14003a43c  jz      short loc_14003A488
0x14003a43e  sub     edx, 1
0x14003a441  jz      short loc_14003A47F
0x14003a443  sub     edx, 1
0x14003a446  jz      short loc_14003A476
0x14003a448  sub     edx, 1
0x14003a44b  jz      short loc_14003A46D
0x14003a44d  sub     edx, 1
0x14003a450  jz      short loc_14003A464
0x14003a452  cmp     edx, 1
0x14003a455  jnz     loc_14003ABAA
0x14003a45b  lea     rax, aWdiTaskDot11Re; "WDI_TASK_DOT11_RESET"
0x14003a462  retn
0x14003a464  lea     rax, aWdiTaskConnect; "WDI_TASK_CONNECT"
0x14003a46b  retn
0x14003a46d  lea     rax, aWdiTaskP2pDisc; "WDI_TASK_P2P_DISCOVER"
0x14003a474  retn
0x14003a476  lea     rax, aWdiTaskScan; "WDI_TASK_SCAN"
0x14003a47d  retn
0x14003a47f  lea     rax, aWdiSetHostDete; "WDI_SET_HOST_DETECT_ERROR"
0x14003a486  retn
0x14003a488  lea     rax, aWdiTaskClose; "WDI_TASK_CLOSE"
0x14003a48f  retn
0x14003a491  lea     rax, aWdiTaskOpen; "WDI_TASK_OPEN"
0x14003a498  retn
0x14003a49a  lea     rax, aWdiTaskDisconn; "WDI_TASK_DISCONNECT"
0x14003a4a1  retn
0x14003a4a3  sub     edx, 9
0x14003a4a6  jz      short loc_14003A500
0x14003a4a8  sub     edx, 1
0x14003a4ab  jz      short loc_14003A4F7
0x14003a4ad  sub     edx, 1
0x14003a4b0  jz      short loc_14003A4EE
0x14003a4b2  sub     edx, 1
0x14003a4b5  jz      short loc_14003A4E5
0x14003a4b7  sub     edx, 1
0x14003a4ba  jz      short loc_14003A4DC
0x14003a4bc  sub     edx, 1
0x14003a4bf  jz      short loc_14003A4D3
0x14003a4c1  cmp     edx, 1
0x14003a4c4  jnz     loc_14003ABAA
0x14003a4ca  lea     rax, aWdiTaskStopAp; "WDI_TASK_STOP_AP"
0x14003a4d1  retn
0x14003a4d3  lea     rax, aWdiTaskStartAp; "WDI_TASK_START_AP"
0x14003a4da  retn
0x14003a4dc  lea     rax, aWdiTaskDeleteP; "WDI_TASK_DELETE_PORT"
0x14003a4e3  retn
0x14003a4e5  lea     rax, aWdiTaskCreateP; "WDI_TASK_CREATE_PORT"
0x14003a4ec  retn
0x14003a4ee  lea     rax, aWdiTaskSetRadi; "WDI_TASK_SET_RADIO_STATE"
0x14003a4f5  retn
0x14003a4f7  lea     rax, aWdiTaskP2pSend_0; "WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME"
0x14003a4fe  retn
0x14003a500  lea     rax, aWdiTaskP2pSend; "WDI_TASK_P2P_SEND_REQUEST_ACTION_FRAME"
0x14003a507  retn
0x14003a509  lea     rax, aWdiTaskSendApA; "WDI_TASK_SEND_AP_ASSOCIATION_RESPONSE"
0x14003a510  retn
0x14003a512  cmp     edx, 1Ch
0x14003a515  ja      short loc_14003A588
0x14003a517  jz      short loc_14003A57F
0x14003a519  sub     edx, 12h
0x14003a51c  jz      short loc_14003A576
0x14003a51e  sub     edx, 1
0x14003a521  jz      short loc_14003A56D
0x14003a523  sub     edx, 2
0x14003a526  jz      short loc_14003A564
0x14003a528  sub     edx, 1
0x14003a52b  jz      short loc_14003A55B
0x14003a52d  sub     edx, 1
0x14003a530  jz      short loc_14003A552
0x14003a532  sub     edx, 1
0x14003a535  jz      short loc_14003A549
0x14003a537  cmp     edx, 2
0x14003a53a  jnz     loc_14003ABAA
0x14003a540  lea     rax, aWdiSetP2pListe; "WDI_SET_P2P_LISTEN_STATE"
0x14003a547  retn
0x14003a549  lea     rax, aWdiSetOperatio; "WDI_SET_OPERATION_MODE"
0x14003a550  retn
0x14003a552  lea     rax, aWdiIndicationS_1; "WDI_INDICATION_SET_READY_TO_RECEIVE_IND"...
0x14003a559  retn
0x14003a55b  lea     rax, aWdiIndicationS_7; "WDI_INDICATION_SET_RADIO_STATE_COMPLETE"
0x14003a562  retn
0x14003a564  lea     rax, aWdiIndicationD_3; "WDI_INDICATION_DISCONNECT_COMPLETE"
0x14003a56b  retn
0x14003a56d  lea     rax, aWdiSetPowerSta; "WDI_SET_POWER_STATE"
0x14003a574  retn
0x14003a576  lea     rax, aWdiTaskSetRead; "WDI_TASK_SET_READY_TO_RECEIVE_INDICATIO"...
0x14003a57d  retn
0x14003a57f  lea     rax, aWdiSetPrivacyE; "WDI_SET_PRIVACY_EXEMPTION_LIST"
0x14003a586  retn
0x14003a588  sub     edx, 1Dh
0x14003a58b  jz      short loc_14003A5E5
0x14003a58d  sub     edx, 1
0x14003a590  jz      short loc_14003A5DC
0x14003a592  sub     edx, 1
0x14003a595  jz      short loc_14003A5D3
0x14003a597  sub     edx, 1
0x14003a59a  jz      short loc_14003A5CA
0x14003a59c  sub     edx, 2
0x14003a59f  jz      short loc_14003A5C1
0x14003a5a1  sub     edx, 2
0x14003a5a4  jz      short loc_14003A5B8
0x14003a5a6  cmp     edx, 1
0x14003a5a9  jnz     loc_14003ABAA
0x14003a5af  lea     rax, aWdiGetAdapterC; "WDI_GET_ADAPTER_CAPABILITIES"
0x14003a5b6  retn
0x14003a5b8  lea     rax, aWdiSetReceiveP; "WDI_SET_RECEIVE_PACKET_FILTER"
0x14003a5bf  retn
0x14003a5c1  lea     rax, aWdiGetStatisti; "WDI_GET_STATISTICS"
0x14003a5c8  retn
0x14003a5ca  lea     rax, aWdiSetConnecti; "WDI_SET_CONNECTION_QUALITY"
0x14003a5d1  retn
0x14003a5d3  lea     rax, aWdiSetDefaultK; "WDI_SET_DEFAULT_KEY_ID"
0x14003a5da  retn
0x14003a5dc  lea     rax, aWdiSetDeleteCi; "WDI_SET_DELETE_CIPHER_KEYS"
0x14003a5e3  retn
0x14003a5e5  lea     rax, aWdiSetAddCiphe; "WDI_SET_ADD_CIPHER_KEYS"
0x14003a5ec  retn
0x14003a5ee  lea     rax, aWdiSetNetworkL; "WDI_SET_NETWORK_LIST_OFFLOAD"
0x14003a5f5  retn
0x14003a5f7  cmp     edx, 65h ; 'e'
0x14003a5fa  ja      loc_14003A8D9
0x14003a600  jz      loc_14003A8D0
0x14003a606  cmp     edx, 4Ch ; 'L'
0x14003a609  ja      loc_14003A77E
0x14003a60f  jz      loc_14003A775
0x14003a615  cmp     edx, 3Eh ; '>'
0x14003a618  ja      loc_14003A6D1
0x14003a61e  jz      loc_14003A6C8
0x14003a624  cmp     edx, 37h ; '7'
0x14003a627  ja      short loc_14003A67E
0x14003a629  jz      short loc_14003A675
0x14003a62b  sub     edx, 2Fh ; '/'
0x14003a62e  jz      short loc_14003A66C
0x14003a630  sub     edx, 4
0x14003a633  jz      short loc_14003A663
0x14003a635  sub     edx, 1
0x14003a638  jz      short loc_14003A65A
0x14003a63a  sub     edx, 1
0x14003a63d  jz      short loc_14003A651
0x14003a63f  cmp     edx, 1
0x14003a642  jnz     loc_14003ABAA
0x14003a648  lea     rax, aWdiIndicationP_1; "WDI_INDICATION_P2P_ACTION_FRAME_RECEIVE"...
0x14003a64f  retn
0x14003a651  lea     rax, aWdiIndicationL; "WDI_INDICATION_LINK_STATE_CHANGE"
0x14003a658  retn
0x14003a65a  lea     rax, aWdiIndicationR; "WDI_INDICATION_ROAMING_NEEDED"
0x14003a661  retn
0x14003a663  lea     rax, aWdiIndicationD_2; "WDI_INDICATION_DISASSOCIATION"
0x14003a66a  retn
0x14003a66c  lea     rax, aWdiGetBssEntry; "WDI_GET_BSS_ENTRY_LIST"
0x14003a673  retn
0x14003a675  lea     rax, aWdiIndicationA_1; "WDI_INDICATION_AP_ASSOCIATION_REQUEST_R"...
0x14003a67c  retn
0x14003a67e  sub     edx, 38h ; '8'
0x14003a681  jz      short loc_14003A6BF
0x14003a683  sub     edx, 1
0x14003a686  jz      short loc_14003A6B6
0x14003a688  sub     edx, 2
0x14003a68b  jz      short loc_14003A6AD
0x14003a68d  sub     edx, 1
0x14003a690  jz      short loc_14003A6A4
0x14003a692  cmp     edx, 1
0x14003a695  jnz     loc_14003ABAA
0x14003a69b  lea     rax, aWdiIndicationP_4; "WDI_INDICATION_P2P_DISCOVERY_COMPLETE"
0x14003a6a2  retn
0x14003a6a4  lea     rax, aWdiIndicationS_3; "WDI_INDICATION_SCAN_COMPLETE"
0x14003a6ab  retn
0x14003a6ad  lea     rax, aWdiIndicationT; "WDI_INDICATION_TKIP_MIC_FAILURE"
0x14003a6b4  retn
0x14003a6b6  lea     rax, aWdiIndicationW; "WDI_INDICATION_WAKE_REASON"
0x14003a6bd  retn
0x14003a6bf  lea     rax, aWdiIndicationN; "WDI_INDICATION_NLO_DISCOVERY"
0x14003a6c6  retn
0x14003a6c8  lea     rax, aWdiIndicationB; "WDI_INDICATION_BSS_ENTRY_LIST"
0x14003a6cf  retn
0x14003a6d1  cmp     edx, 44h ; 'D'
0x14003a6d4  ja      short loc_14003A72B
0x14003a6d6  jz      short loc_14003A722
0x14003a6d8  sub     edx, 3Fh ; '?'
0x14003a6db  jz      short loc_14003A719
0x14003a6dd  sub     edx, 1
0x14003a6e0  jz      short loc_14003A710
0x14003a6e2  sub     edx, 1
0x14003a6e5  jz      short loc_14003A707
0x14003a6e7  sub     edx, 1
0x14003a6ea  jz      short loc_14003A6FE
0x14003a6ec  cmp     edx, 1
0x14003a6ef  jnz     loc_14003ABAA
0x14003a6f5  lea     rax, aWdiIndicationR_0; "WDI_INDICATION_RADIO_STATUS"
0x14003a6fc  retn
0x14003a6fe  lea     rax, aWdiIndicationP_0; "WDI_INDICATION_P2P_SEND_RESPONSE_ACTION"...
0x14003a705  retn
0x14003a707  lea     rax, aWdiIndicationP_3; "WDI_INDICATION_P2P_SEND_REQUEST_ACTION_"...
0x14003a70e  retn
0x14003a710  lea     rax, aWdiIndicationC_3; "WDI_INDICATION_CONNECT_COMPLETE"
0x14003a717  retn
0x14003a719  lea     rax, aWdiIndicationD; "WDI_INDICATION_DOT11_RESET_COMPLETE"
0x14003a720  retn
0x14003a722  lea     rax, aWdiIndicationC_1; "WDI_INDICATION_CREATE_PORT_COMPLETE"
0x14003a729  retn
0x14003a72b  sub     edx, 45h ; 'E'
0x14003a72e  jz      short loc_14003A76C
0x14003a730  sub     edx, 1
0x14003a733  jz      short loc_14003A763
0x14003a735  sub     edx, 1
0x14003a738  jz      short loc_14003A75A
0x14003a73a  sub     edx, 2
0x14003a73d  jz      short loc_14003A751
0x14003a73f  cmp     edx, 2
0x14003a742  jnz     loc_14003ABAA
0x14003a748  lea     rax, aWdiAbortTask; "WDI_ABORT_TASK"
0x14003a74f  retn
0x14003a751  lea     rax, aWdiIndicationS_8; "WDI_INDICATION_SEND_AP_ASSOCIATION_RESP"...
0x14003a758  retn
0x14003a75a  lea     rax, aWdiIndicationS_6; "WDI_INDICATION_STOP_AP_COMPLETE"
0x14003a761  retn
0x14003a763  lea     rax, aWdiIndicationS_2; "WDI_INDICATION_START_AP_COMPLETE"
0x14003a76a  retn
0x14003a76c  lea     rax, aWdiIndicationD_1; "WDI_INDICATION_DELETE_PORT_COMPLETE"
0x14003a773  retn
0x14003a775  lea     rax, aWdiIndicationA_2; "WDI_INDICATION_ASSOCIATION_RESULT"
0x14003a77c  retn
0x14003a77e  cmp     edx, 59h ; 'Y'
0x14003a781  ja      loc_14003A83A
0x14003a787  jz      loc_14003A831
0x14003a78d  cmp     edx, 53h ; 'S'
0x14003a790  ja      short loc_14003A7E7
0x14003a792  jz      short loc_14003A7DE
0x14003a794  sub     edx, 4Eh ; 'N'
0x14003a797  jz      short loc_14003A7D5
0x14003a799  sub     edx, 1
0x14003a79c  jz      short loc_14003A7CC
0x14003a79e  sub     edx, 1
0x14003a7a1  jz      short loc_14003A7C3
0x14003a7a3  sub     edx, 1
0x14003a7a6  jz      short loc_14003A7BA
0x14003a7a8  cmp     edx, 1
0x14003a7ab  jnz     loc_14003ABAA
0x14003a7b1  lea     rax, aWdiSetAddPmPro; "WDI_SET_ADD_PM_PROTOCOL_OFFLOAD"
0x14003a7b8  retn
0x14003a7ba  lea     rax, aWdiSetMulticas; "WDI_SET_MULTICAST_LIST"
0x14003a7c1  retn
0x14003a7c3  lea     rax, aWdiSetRemoveWo; "WDI_SET_REMOVE_WOL_PATTERN"
0x14003a7ca  retn
0x14003a7cc  lea     rax, aWdiSetAddWolPa; "WDI_SET_ADD_WOL_PATTERN"
0x14003a7d3  retn
0x14003a7d5  lea     rax, aWdiGetAutoPowe; "WDI_GET_AUTO_POWER_SAVE"
0x14003a7dc  retn
0x14003a7de  lea     rax, aWdiSetRemovePm; "WDI_SET_REMOVE_PM_PROTOCOL_OFFLOAD"
0x14003a7e5  retn
0x14003a7e7  sub     edx, 54h ; 'T'
0x14003a7ea  jz      short loc_14003A828
0x14003a7ec  sub     edx, 1
0x14003a7ef  jz      short loc_14003A81F
0x14003a7f1  sub     edx, 1
0x14003a7f4  jz      short loc_14003A816
0x14003a7f6  sub     edx, 1
0x14003a7f9  jz      short loc_14003A80D
0x14003a7fb  cmp     edx, 1
0x14003a7fe  jnz     loc_14003ABAA
0x14003a804  lea     rax, aWdiGetPmProtoc; "WDI_GET_PM_PROTOCOL_OFFLOAD"
0x14003a80b  retn
0x14003a80d  lea     rax, aWdiSetClearRec; "WDI_SET_CLEAR_RECEIVE_COALESCING"
0x14003a814  retn
0x14003a816  lea     rax, aWdiGetReceiveC; "WDI_GET_RECEIVE_COALESCING_MATCH_COUNT"
0x14003a81d  retn
0x14003a81f  lea     rax, aWdiSetAdapterC; "WDI_SET_ADAPTER_CONFIGURATION"
0x14003a826  retn
0x14003a828  lea     rax, aWdiIndicationP; "WDI_INDICATION_P2P_GROUP_OPERATING_CHAN"...
0x14003a82f  retn
0x14003a831  lea     rax, aWdiSetAdvertis; "WDI_SET_ADVERTISEMENT_INFORMATION"
0x14003a838  retn
0x14003a83a  cmp     edx, 60h ; '`'
0x14003a83d  ja      short loc_14003A894
0x14003a83f  jz      short loc_14003A88B
0x14003a841  sub     edx, 5Ah ; 'Z'
0x14003a844  jz      short loc_14003A882
0x14003a846  sub     edx, 1
0x14003a849  jz      short loc_14003A879
0x14003a84b  sub     edx, 2
0x14003a84e  jz      short loc_14003A870
0x14003a850  sub     edx, 1
0x14003a853  jz      short loc_14003A867
0x14003a855  cmp     edx, 1
0x14003a858  jnz     loc_14003ABAA
0x14003a85e  lea     rax, aWdiIndicationO; "WDI_INDICATION_OPEN_COMPLETE"
  ... truncated ...
```
