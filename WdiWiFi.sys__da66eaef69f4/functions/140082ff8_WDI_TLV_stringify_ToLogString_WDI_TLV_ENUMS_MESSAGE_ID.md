# WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)

- ea: `0x140082ff8`
- end: `0x1400836ea`
- name: `?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z`
- size: `1778`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400020a8`
- `0x14002ace4`
- `0x14006e8e8`
- `0x1400a6600`

## callees

- `0x140082ff8`

## string_xrefs

- `0x14008307d`: `WDI_TASK_OPEN`
- `0x140083074`: `WDI_TASK_CLOSE`
- `0x140083062`: `WDI_TASK_SCAN`
- `0x140083059`: `WDI_TASK_P2P_DISCOVER`
- `0x140083050`: `WDI_TASK_CONNECT`
- `0x140083047`: `WDI_TASK_DOT11_RESET`
- `0x140083086`: `WDI_TASK_DISCONNECT`
- `0x1400830ec`: `WDI_TASK_P2P_SEND_REQUEST_ACTION_FRAME`
- `0x1400830e3`: `WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME`
- `0x1400830da`: `WDI_TASK_SET_RADIO_STATE`
- `0x1400830d1`: `WDI_TASK_CREATE_PORT`
- `0x1400830c8`: `WDI_TASK_DELETE_PORT`
- `0x1400830bf`: `WDI_TASK_START_AP`
- `0x1400830b6`: `WDI_TASK_STOP_AP`
- `0x1400830f5`: `WDI_TASK_SEND_AP_ASSOCIATION_RESPONSE`
- `0x140083162`: `WDI_TASK_SET_READY_TO_RECEIVE_INDICATIONS`
- `0x140083150`: `WDI_INDICATION_DISCONNECT_COMPLETE`
- `0x140083147`: `WDI_INDICATION_SET_RADIO_STATE_COMPLETE`
- `0x14008313e`: `WDI_INDICATION_SET_READY_TO_RECEIVE_INDICATIONS_COMPLETE`
- `0x1400831c8`: `WDI_SET_DELETE_CIPHER_KEYS`
- `0x140083247`: `WDI_INDICATION_LINK_STATE_CHANGE`
- `0x1400832b9`: `WDI_INDICATION_SCAN_COMPLETE`
- `0x14008333b`: `WDI_INDICATION_P2P_DISCOVERY_COMPLETE`
- `0x140083329`: `WDI_INDICATION_DOT11_RESET_COMPLETE`
- `0x140083320`: `WDI_INDICATION_CONNECT_COMPLETE`
- `0x140083317`: `WDI_INDICATION_P2P_SEND_REQUEST_ACTION_FRAME_COMPLETE`
- `0x14008330e`: `WDI_INDICATION_P2P_SEND_RESPONSE_ACTION_FRAME_COMPLETE`
- `0x1400832fc`: `WDI_INDICATION_CREATE_PORT_COMPLETE`
- `0x1400832f3`: `WDI_INDICATION_DELETE_PORT_COMPLETE`
- `0x140083344`: `WDI_INDICATION_START_AP_COMPLETE`
- `0x1400833d5`: `WDI_INDICATION_STOP_AP_COMPLETE`
- `0x1400833cc`: `WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE`
- `0x14008339f`: `WDI_SET_REMOVE_WOL_PATTERN`
- `0x14008338d`: `WDI_SET_ADD_PM_PROTOCOL_OFFLOAD`
- `0x1400833de`: `WDI_SET_REMOVE_PM_PROTOCOL_OFFLOAD`
- `0x140083457`: `WDI_SET_ADAPTER_CONFIGURATION`
- `0x14008343c`: `WDI_GET_PM_PROTOCOL_OFFLOAD`
- `0x14008342a`: `WDI_TASK_CHANGE_OPERATION_MODE`
- `0x140083421`: `WDI_INDICATION_CHANGE_OPERATION_MODE_COMPLETE`
- `0x1400834d8`: `WDI_INDICATION_OPEN_COMPLETE`
- `0x1400834cf`: `WDI_INDICATION_CLOSE_COMPLETE`
- `0x1400834e1`: `WDI_TASK_ROAM`
- `0x14008351d`: `WDI_INDICATION_ROAM_COMPLETE`
- `0x140083514`: `WDI_TASK_SEND_REQUEST_ACTION_FRAME`
- `0x140083502`: `WDI_INDICATION_TASK_OFFLOAD_CURRENT_CONFIG`
- `0x140083526`: `WDI_TASK_SEND_RESPONSE_ACTION_FRAME`
- `0x1400835a8`: `WDI_INDICATION_SEND_REQUEST_ACTION_FRAME_COMPLETE`
- `0x14008359f`: `WDI_INDICATION_SEND_RESPONSE_ACTION_FRAME_COMPLETE`
- `0x140083596`: `WDI_GET_NEXT_ACTION_FRAME_DIALOG_TOKEN`
- `0x14008358d`: `WDI_TASK_IHV`
- `0x14008369a`: `WDI_TASK_REQUEST_FTM`
- `0x140083691`: `WDI_INDICATION_REQUEST_FTM_COMPLETE`
- `0x140083584`: `WDI_INDICATION_IHV_TASK_REQUEST`
- `0x14008357b`: `WDI_INDICATION_IHV_TASK_COMPLETE`
- `0x1400833c3`: `WDI_ABORT_TASK`
- `0x1400836d0`: `WDI_GET_SUPPORTED_DEVICE_SERVICES`
- `0x1400836c7`: `WDI_DEVICE_SERVICE_COMMAND`
- `0x1400836be`: `WDI_INDICATION_CIPHER_KEY_UPDATED`
- `0x1400836b5`: `WDI_INDICATION_DEVICE_SERVICE_EVENT`
- `0x1400836d9`: `WDI_TEST_TASK`

## pseudocode

```c
const char *__fastcall WDI_TLV::stringify::ToLogString(unsigned __int16 a1)
{
  if ( a1 > 0x29u )
  {
    if ( a1 <= 0xFFE0u )
    {
      if ( a1 == 65504 )
        return "WDI_TEST_TASK";
      if ( a1 > 0x5Eu )
      {
        if ( a1 > 0x76u )
        {
          if ( a1 > 0x80u )
          {
            switch ( a1 )
            {
              case 0x82u:
                return "WDI_GET_SUPPORTED_DEVICE_SERVICES";
              case 0x83u:
                return "WDI_DEVICE_SERVICE_COMMAND";
              case 0x84u:
                return "WDI_INDICATION_CIPHER_KEY_UPDATED";
              case 0x85u:
                return "WDI_INDICATION_DEVICE_SERVICE_EVENT";
              case 0x86u:
                return "WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED";
              case 0x87u:
                return "WDI_SET_SAE_AUTH_PARAMS";
              case 0x88u:
                return "WDI_TASK_REQUEST_FTM";
              case 0x89u:
                return "WDI_INDICATION_REQUEST_FTM_COMPLETE";
              case 0x8Au:
                return "WDI_SET_LOCATION_PRIVACY";
            }
          }
          else
          {
            switch ( a1 )
            {
              case 0x80u:
                return "WDI_SET_NEIGHBOR_REPORT_ENTRIES";
              case 0x77u:
                return "WDI_SET_P2P_START_BACKGROUND_DISCOVERY";
              case 0x78u:
                return "WDI_SET_P2P_STOP_BACKGROUND_DISCOVERY";
              case 0x79u:
                return "WDI_INDICATION_FIRMWARE_STALLED";
              case 0x7Au:
                return "WDI_INDICATION_P2P_OPERATING_CHANNEL_ATTRIBUTES";
              case 0x7Bu:
                return "WDI_SET_P2P_WPS_ENABLED";
              case 0x7Cu:
                return "WDI_SET_ENCAPSULATION_OFFLOAD";
              case 0x7Du:
                return "WDI_SET_END_DWELL_TIME";
              case 0x7Eu:
                return "WDI_INDICATION_FT_ASSOC_PARAMS_NEEDED";
              case 0x7Fu:
                return "WDI_SET_FAST_BSS_TRANSITION_PARAMETERS";
            }
          }
        }
        else
        {
          if ( a1 == 118 )
            return "WDI_TCP_RSC_STATISTICS";
          if ( a1 > 0x69u )
          {
            switch ( a1 )
            {
              case 'j':
                return "WDI_INDICATION_SEND_REQUEST_ACTION_FRAME_COMPLETE";
              case 'k':
                return "WDI_INDICATION_SEND_RESPONSE_ACTION_FRAME_COMPLETE";
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
              case 't':
                return "WDI_INDICATION_CAN_SUSTAIN_AP";
              case 'u':
                return "WDI_SET_TCP_OFFLOAD_PARAMETERS";
            }
          }
          else
          {
            if ( a1 == 105 )
              return "WDI_TASK_SEND_RESPONSE_ACTION_FRAME";
            if ( a1 > 0x64u )
            {
              switch ( a1 )
              {
                case 'e':
                  return "WDI_INDICATION_ROAM_COMPLETE";
                case 'f':
                  return "WDI_TASK_SEND_REQUEST_ACTION_FRAME";
                case 'g':
                  return "WDI_INDICATION_ACTION_FRAME_RECEIVED";
                case 'h':
                  return "WDI_INDICATION_TASK_OFFLOAD_CURRENT_CONFIG";
              }
            }
            else
            {
              switch ( a1 )
              {
                case 'd':
                  return "WDI_TASK_ROAM";
                case '_':
                  return "WDI_INDICATION_OPEN_COMPLETE";
                case '`':
                  return "WDI_INDICATION_CLOSE_COMPLETE";
                case 'a':
                  return "WDI_SET_FLUSH_BSS_ENTRY";
                case 'b':
                  return "WDI_INDICATION_ASSOCIATION_PARAMETERS_REQUEST";
                case 'c':
                  return "WDI_SET_ASSOCIATION_PARAMETERS";
              }
            }
          }
        }
      }
      else
      {
        if ( a1 == 94 )
          return "WDI_INDICATION_IHV_EVENT";
        if ( a1 > 0x46u )
        {
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
              case 'Y':
                return "WDI_SET_ADVERTISEMENT_INFORMATION";
              case 'Z':
                return "WDI_TASK_CHANGE_OPERATION_MODE";
              case '[':
                return "WDI_INDICATION_CHANGE_OPERATION_MODE_COMPLETE";
              case ']':
                return "WDI_IHV_REQUEST";
            }
          }
          else
          {
            switch ( a1 )
            {
              case 'S':
                return "WDI_SET_REMOVE_PM_PROTOCOL_OFFLOAD";
              case 'G':
                return "WDI_INDICATION_STOP_AP_COMPLETE";
              case 'I':
                return "WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE";
              case 'K':
                return "WDI_ABORT_TASK";
              case 'L':
                return "WDI_INDICATION_ASSOCIATION_RESULT";
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
        else
        {
          if ( a1 == 70 )
            return "WDI_INDICATION_START_AP_COMPLETE";
          if ( a1 > 0x3Cu )
          {
            switch ( a1 )
            {
              case '=':
                return "WDI_INDICATION_P2P_DISCOVERY_COMPLETE";
              case '>':
                return "WDI_INDICATION_BSS_ENTRY_LIST";
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
              case 'D':
                return "WDI_INDICATION_CREATE_PORT_COMPLETE";
              case 'E':
                return "WDI_INDICATION_DELETE_PORT_COMPLETE";
            }
          }
          else
          {
            if ( a1 == 60 )
              return "WDI_INDICATION_SCAN_COMPLETE";
            if ( a1 > 0x36u )
            {
              switch ( a1 )
              {
                case '7':
                  return "WDI_INDICATION_AP_ASSOCIATION_REQUEST_RECEIVED";
                case '8':
                  return "WDI_INDICATION_NLO_DISCOVERY";
                case '9':
                  return "WDI_INDICATION_WAKE_REASON";
                case ';':
                  return "WDI_INDICATION_TKIP_MIC_FAILURE";
              }
            }
            else
            {
              switch ( a1 )
              {
                case '6':
                  return "WDI_INDICATION_P2P_ACTION_FRAME_RECEIVED";
                case '.':
                  return "WDI_SET_RECEIVE_COALESCING";
                case '/':
                  return "WDI_GET_BSS_ENTRY_LIST";
                case '3':
                  return "WDI_INDICATION_DISASSOCIATION";
                case '4':
                  return "WDI_INDICATION_ROAMING_NEEDED";
                case '5':
                  return "WDI_INDICATION_LINK_STATE_CHANGE";
              }
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
0x140082ff8  movzx   edx, cx
0x140082ffb  cmp     edx, 29h ; ')'
0x140082ffe  ja      loc_1400831E3
0x140083004  jz      loc_1400831DA
0x14008300a  cmp     edx, 11h
0x14008300d  ja      loc_1400830FE
0x140083013  jz      loc_1400830F5
0x140083019  cmp     edx, 8
0x14008301c  ja      short loc_14008308F
0x14008301e  jz      short loc_140083086
0x140083020  sub     edx, 1
0x140083023  jz      short loc_14008307D
0x140083025  sub     edx, 1
0x140083028  jz      short loc_140083074
0x14008302a  sub     edx, 1
0x14008302d  jz      short loc_14008306B
0x14008302f  sub     edx, 1
0x140083032  jz      short loc_140083062
0x140083034  sub     edx, 1
0x140083037  jz      short loc_140083059
0x140083039  sub     edx, 1
0x14008303c  jz      short loc_140083050
0x14008303e  cmp     edx, 1
0x140083041  jnz     loc_1400836E2
0x140083047  lea     rax, aWdiTaskDot11Re; "WDI_TASK_DOT11_RESET"
0x14008304e  retn
0x140083050  lea     rax, aWdiTaskConnect; "WDI_TASK_CONNECT"
0x140083057  retn
0x140083059  lea     rax, aWdiTaskP2pDisc; "WDI_TASK_P2P_DISCOVER"
0x140083060  retn
0x140083062  lea     rax, aWdiTaskScan; "WDI_TASK_SCAN"
0x140083069  retn
0x14008306b  lea     rax, aWdiSetHostDete; "WDI_SET_HOST_DETECT_ERROR"
0x140083072  retn
0x140083074  lea     rax, aWdiTaskClose; "WDI_TASK_CLOSE"
0x14008307b  retn
0x14008307d  lea     rax, aWdiTaskOpen; "WDI_TASK_OPEN"
0x140083084  retn
0x140083086  lea     rax, aWdiTaskDisconn; "WDI_TASK_DISCONNECT"
0x14008308d  retn
0x14008308f  sub     edx, 9
0x140083092  jz      short loc_1400830EC
0x140083094  sub     edx, 1
0x140083097  jz      short loc_1400830E3
0x140083099  sub     edx, 1
0x14008309c  jz      short loc_1400830DA
0x14008309e  sub     edx, 1
0x1400830a1  jz      short loc_1400830D1
0x1400830a3  sub     edx, 1
0x1400830a6  jz      short loc_1400830C8
0x1400830a8  sub     edx, 1
0x1400830ab  jz      short loc_1400830BF
0x1400830ad  cmp     edx, 1
0x1400830b0  jnz     loc_1400836E2
0x1400830b6  lea     rax, aWdiTaskStopAp; "WDI_TASK_STOP_AP"
0x1400830bd  retn
0x1400830bf  lea     rax, aWdiTaskStartAp; "WDI_TASK_START_AP"
0x1400830c6  retn
0x1400830c8  lea     rax, aWdiTaskDeleteP; "WDI_TASK_DELETE_PORT"
0x1400830cf  retn
0x1400830d1  lea     rax, aWdiTaskCreateP; "WDI_TASK_CREATE_PORT"
0x1400830d8  retn
0x1400830da  lea     rax, aWdiTaskSetRadi; "WDI_TASK_SET_RADIO_STATE"
0x1400830e1  retn
0x1400830e3  lea     rax, aWdiTaskP2pSend_0; "WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME"
0x1400830ea  retn
0x1400830ec  lea     rax, aWdiTaskP2pSend; "WDI_TASK_P2P_SEND_REQUEST_ACTION_FRAME"
0x1400830f3  retn
0x1400830f5  lea     rax, aWdiTaskSendApA; "WDI_TASK_SEND_AP_ASSOCIATION_RESPONSE"
0x1400830fc  retn
0x1400830fe  cmp     edx, 1Ch
0x140083101  ja      short loc_140083174
0x140083103  jz      short loc_14008316B
0x140083105  sub     edx, 12h
0x140083108  jz      short loc_140083162
0x14008310a  sub     edx, 1
0x14008310d  jz      short loc_140083159
0x14008310f  sub     edx, 2
0x140083112  jz      short loc_140083150
0x140083114  sub     edx, 1
0x140083117  jz      short loc_140083147
0x140083119  sub     edx, 1
0x14008311c  jz      short loc_14008313E
0x14008311e  sub     edx, 1
0x140083121  jz      short loc_140083135
0x140083123  cmp     edx, 2
0x140083126  jnz     loc_1400836E2
0x14008312c  lea     rax, aWdiSetP2pListe; "WDI_SET_P2P_LISTEN_STATE"
0x140083133  retn
0x140083135  lea     rax, aWdiSetOperatio; "WDI_SET_OPERATION_MODE"
0x14008313c  retn
0x14008313e  lea     rax, aWdiIndicationS_0; "WDI_INDICATION_SET_READY_TO_RECEIVE_IND"...
0x140083145  retn
0x140083147  lea     rax, aWdiIndicationS_6; "WDI_INDICATION_SET_RADIO_STATE_COMPLETE"
0x14008314e  retn
0x140083150  lea     rax, aWdiIndicationD_3; "WDI_INDICATION_DISCONNECT_COMPLETE"
0x140083157  retn
0x140083159  lea     rax, aWdiSetPowerSta; "WDI_SET_POWER_STATE"
0x140083160  retn
0x140083162  lea     rax, aWdiTaskSetRead; "WDI_TASK_SET_READY_TO_RECEIVE_INDICATIO"...
0x140083169  retn
0x14008316b  lea     rax, aWdiSetPrivacyE; "WDI_SET_PRIVACY_EXEMPTION_LIST"
0x140083172  retn
0x140083174  sub     edx, 1Dh
0x140083177  jz      short loc_1400831D1
0x140083179  sub     edx, 1
0x14008317c  jz      short loc_1400831C8
0x14008317e  sub     edx, 1
0x140083181  jz      short loc_1400831BF
0x140083183  sub     edx, 1
0x140083186  jz      short loc_1400831B6
0x140083188  sub     edx, 2
0x14008318b  jz      short loc_1400831AD
0x14008318d  sub     edx, 2
0x140083190  jz      short loc_1400831A4
0x140083192  cmp     edx, 1
0x140083195  jnz     loc_1400836E2
0x14008319b  lea     rax, aWdiGetAdapterC; "WDI_GET_ADAPTER_CAPABILITIES"
0x1400831a2  retn
0x1400831a4  lea     rax, aWdiSetReceiveP; "WDI_SET_RECEIVE_PACKET_FILTER"
0x1400831ab  retn
0x1400831ad  lea     rax, aWdiGetStatisti; "WDI_GET_STATISTICS"
0x1400831b4  retn
0x1400831b6  lea     rax, aWdiSetConnecti; "WDI_SET_CONNECTION_QUALITY"
0x1400831bd  retn
0x1400831bf  lea     rax, aWdiSetDefaultK; "WDI_SET_DEFAULT_KEY_ID"
0x1400831c6  retn
0x1400831c8  lea     rax, aWdiSetDeleteCi; "WDI_SET_DELETE_CIPHER_KEYS"
0x1400831cf  retn
0x1400831d1  lea     rax, aWdiSetAddCiphe; "WDI_SET_ADD_CIPHER_KEYS"
0x1400831d8  retn
0x1400831da  lea     rax, aWdiSetNetworkL; "WDI_SET_NETWORK_LIST_OFFLOAD"
0x1400831e1  retn
0x1400831e3  mov     eax, 0FFE0h
0x1400831e8  cmp     edx, eax
0x1400831ea  ja      loc_1400836E2
0x1400831f0  jz      loc_1400836D9
0x1400831f6  cmp     edx, 5Eh ; '^'
0x1400831f9  ja      loc_140083472
0x1400831ff  jz      loc_140083469
0x140083205  cmp     edx, 46h ; 'F'
0x140083208  ja      loc_14008334D
0x14008320e  jz      loc_140083344
0x140083214  cmp     edx, 3Ch ; '<'
0x140083217  ja      loc_1400832C2
0x14008321d  jz      loc_1400832B9
0x140083223  cmp     edx, 36h ; '6'
0x140083226  ja      short loc_14008327D
0x140083228  jz      short loc_140083274
0x14008322a  sub     edx, 2Eh ; '.'
0x14008322d  jz      short loc_14008326B
0x14008322f  sub     edx, 1
0x140083232  jz      short loc_140083262
0x140083234  sub     edx, 4
0x140083237  jz      short loc_140083259
0x140083239  sub     edx, 1
0x14008323c  jz      short loc_140083250
0x14008323e  cmp     edx, 1
0x140083241  jnz     loc_1400836E2
0x140083247  lea     rax, aWdiIndicationL; "WDI_INDICATION_LINK_STATE_CHANGE"
0x14008324e  retn
0x140083250  lea     rax, aWdiIndicationR; "WDI_INDICATION_ROAMING_NEEDED"
0x140083257  retn
0x140083259  lea     rax, aWdiIndicationD_2; "WDI_INDICATION_DISASSOCIATION"
0x140083260  retn
0x140083262  lea     rax, aWdiGetBssEntry; "WDI_GET_BSS_ENTRY_LIST"
0x140083269  retn
0x14008326b  lea     rax, aWdiSetReceiveC; "WDI_SET_RECEIVE_COALESCING"
0x140083272  retn
0x140083274  lea     rax, aWdiIndicationP_1; "WDI_INDICATION_P2P_ACTION_FRAME_RECEIVE"...
0x14008327b  retn
0x14008327d  sub     edx, 37h ; '7'
0x140083280  jz      short loc_1400832B0
0x140083282  sub     edx, 1
0x140083285  jz      short loc_1400832A7
0x140083287  sub     edx, 1
0x14008328a  jz      short loc_14008329E
0x14008328c  cmp     edx, 2
0x14008328f  jnz     loc_1400836E2
0x140083295  lea     rax, aWdiIndicationT; "WDI_INDICATION_TKIP_MIC_FAILURE"
0x14008329c  retn
0x14008329e  lea     rax, aWdiIndicationW; "WDI_INDICATION_WAKE_REASON"
0x1400832a5  retn
0x1400832a7  lea     rax, aWdiIndicationN; "WDI_INDICATION_NLO_DISCOVERY"
0x1400832ae  retn
0x1400832b0  lea     rax, aWdiIndicationA_0; "WDI_INDICATION_AP_ASSOCIATION_REQUEST_R"...
0x1400832b7  retn
0x1400832b9  lea     rax, aWdiIndicationS_2; "WDI_INDICATION_SCAN_COMPLETE"
0x1400832c0  retn
0x1400832c2  sub     edx, 3Dh ; '='
0x1400832c5  jz      short loc_14008333B
0x1400832c7  sub     edx, 1
0x1400832ca  jz      short loc_140083332
0x1400832cc  sub     edx, 1
0x1400832cf  jz      short loc_140083329
0x1400832d1  sub     edx, 1
0x1400832d4  jz      short loc_140083320
0x1400832d6  sub     edx, 1
0x1400832d9  jz      short loc_140083317
0x1400832db  sub     edx, 1
0x1400832de  jz      short loc_14008330E
0x1400832e0  sub     edx, 1
0x1400832e3  jz      short loc_140083305
0x1400832e5  sub     edx, 1
0x1400832e8  jz      short loc_1400832FC
0x1400832ea  cmp     edx, 1
0x1400832ed  jnz     loc_1400836E2
0x1400832f3  lea     rax, aWdiIndicationD_1; "WDI_INDICATION_DELETE_PORT_COMPLETE"
0x1400832fa  retn
0x1400832fc  lea     rax, aWdiIndicationC_1; "WDI_INDICATION_CREATE_PORT_COMPLETE"
0x140083303  retn
0x140083305  lea     rax, aWdiIndicationR_0; "WDI_INDICATION_RADIO_STATUS"
0x14008330c  retn
0x14008330e  lea     rax, aWdiIndicationP_0; "WDI_INDICATION_P2P_SEND_RESPONSE_ACTION"...
0x140083315  retn
0x140083317  lea     rax, aWdiIndicationP_3; "WDI_INDICATION_P2P_SEND_REQUEST_ACTION_"...
0x14008331e  retn
0x140083320  lea     rax, aWdiIndicationC_3; "WDI_INDICATION_CONNECT_COMPLETE"
0x140083327  retn
0x140083329  lea     rax, aWdiIndicationD; "WDI_INDICATION_DOT11_RESET_COMPLETE"
0x140083330  retn
0x140083332  lea     rax, aWdiIndicationB; "WDI_INDICATION_BSS_ENTRY_LIST"
0x140083339  retn
0x14008333b  lea     rax, aWdiIndicationP_4; "WDI_INDICATION_P2P_DISCOVERY_COMPLETE"
0x140083342  retn
0x140083344  lea     rax, aWdiIndicationS_1; "WDI_INDICATION_START_AP_COMPLETE"
0x14008334b  retn
0x14008334d  cmp     edx, 53h ; 'S'
0x140083350  ja      loc_1400833E7
0x140083356  jz      loc_1400833DE
0x14008335c  sub     edx, 47h ; 'G'
0x14008335f  jz      short loc_1400833D5
0x140083361  sub     edx, 2
0x140083364  jz      short loc_1400833CC
0x140083366  sub     edx, 2
0x140083369  jz      short loc_1400833C3
0x14008336b  sub     edx, 1
0x14008336e  jz      short loc_1400833BA
0x140083370  sub     edx, 2
0x140083373  jz      short loc_1400833B1
0x140083375  sub     edx, 1
0x140083378  jz      short loc_1400833A8
0x14008337a  sub     edx, 1
0x14008337d  jz      short loc_14008339F
0x14008337f  sub     edx, 1
0x140083382  jz      short loc_140083396
0x140083384  cmp     edx, 1
0x140083387  jnz     loc_1400836E2
0x14008338d  lea     rax, aWdiSetAddPmPro; "WDI_SET_ADD_PM_PROTOCOL_OFFLOAD"
0x140083394  retn
0x140083396  lea     rax, aWdiSetMulticas; "WDI_SET_MULTICAST_LIST"
0x14008339d  retn
0x14008339f  lea     rax, aWdiSetRemoveWo; "WDI_SET_REMOVE_WOL_PATTERN"
0x1400833a6  retn
0x1400833a8  lea     rax, aWdiSetAddWolPa; "WDI_SET_ADD_WOL_PATTERN"
0x1400833af  retn
0x1400833b1  lea     rax, aWdiGetAutoPowe; "WDI_GET_AUTO_POWER_SAVE"
0x1400833b8  retn
0x1400833ba  lea     rax, aWdiIndicationA_1; "WDI_INDICATION_ASSOCIATION_RESULT"
0x1400833c1  retn
0x1400833c3  lea     rax, aWdiAbortTask; "WDI_ABORT_TASK"
0x1400833ca  retn
0x1400833cc  lea     rax, aWdiIndicationS_7; "WDI_INDICATION_SEND_AP_ASSOCIATION_RESP"...
0x1400833d3  retn
0x1400833d5  lea     rax, aWdiIndicationS_5; "WDI_INDICATION_STOP_AP_COMPLETE"
0x1400833dc  retn
0x1400833de  lea     rax, aWdiSetRemovePm; "WDI_SET_REMOVE_PM_PROTOCOL_OFFLOAD"
0x1400833e5  retn
0x1400833e7  sub     edx, 54h ; 'T'
0x1400833ea  jz      short loc_140083460
0x1400833ec  sub     edx, 1
0x1400833ef  jz      short loc_140083457
0x1400833f1  sub     edx, 1
0x1400833f4  jz      short loc_14008344E
0x1400833f6  sub     edx, 1
0x1400833f9  jz      short loc_140083445
0x1400833fb  sub     edx, 1
0x1400833fe  jz      short loc_14008343C
0x140083400  sub     edx, 1
0x140083403  jz      short loc_140083433
0x140083405  sub     edx, 1
0x140083408  jz      short loc_14008342A
0x14008340a  sub     edx, 1
0x14008340d  jz      short loc_140083421
0x14008340f  cmp     edx, 2
0x140083412  jnz     loc_1400836E2
0x140083418  lea     rax, aWdiIhvRequest; "WDI_IHV_REQUEST"
0x14008341f  retn
0x140083421  lea     rax, aWdiIndicationC; "WDI_INDICATION_CHANGE_OPERATION_MODE_CO"...
0x140083428  retn
0x14008342a  lea     rax, aWdiTaskChangeO; "WDI_TASK_CHANGE_OPERATION_MODE"
0x140083431  retn
0x140083433  lea     rax, aWdiSetAdvertis; "WDI_SET_ADVERTISEMENT_INFORMATION"
0x14008343a  retn
0x14008343c  lea     rax, aWdiGetPmProtoc; "WDI_GET_PM_PROTOCOL_OFFLOAD"
0x140083443  retn
0x140083445  lea     rax, aWdiSetClearRec; "WDI_SET_CLEAR_RECEIVE_COALESCING"
0x14008344c  retn
0x14008344e  lea     rax, aWdiGetReceiveC; "WDI_GET_RECEIVE_COALESCING_MATCH_COUNT"
0x140083455  retn
  ... truncated ...
```
