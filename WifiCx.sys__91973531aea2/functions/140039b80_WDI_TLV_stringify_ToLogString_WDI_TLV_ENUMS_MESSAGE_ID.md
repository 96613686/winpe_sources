# WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)

- ea: `0x140039b80`
- end: `0x14003a404`
- name: `?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z`
- size: `2180`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140024f60`
- `0x1400257a0`
- `0x1400623b8`
- `0x140062ef0`

## callees

- `0x1400032f0`
- `0x140039b80`
- `0x14003a40c`

## string_xrefs

- `0x140039c39`: `WDI_TASK_OPEN`
- `0x140039c2d`: `WDI_TASK_CLOSE`
- `0x140039c15`: `WDI_TASK_SCAN`
- `0x140039c09`: `WDI_TASK_P2P_DISCOVER`
- `0x140039bfd`: `WDI_TASK_CONNECT`
- `0x140039bf1`: `WDI_TASK_DOT11_RESET`
- `0x140039c45`: `WDI_TASK_DISCONNECT`
- `0x140039cc0`: `WDI_TASK_P2P_SEND_REQUEST_ACTION_FRAME`
- `0x140039cb4`: `WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME`
- `0x140039ca8`: `WDI_TASK_SET_RADIO_STATE`
- `0x140039c9c`: `WDI_TASK_CREATE_PORT`
- `0x140039c90`: `WDI_TASK_DELETE_PORT`
- `0x140039c84`: `WDI_TASK_START_AP`
- `0x140039c78`: `WDI_TASK_STOP_AP`
- `0x140039ccc`: `WDI_TASK_SEND_AP_ASSOCIATION_RESPONSE`
- `0x140039d52`: `WDI_TASK_SET_READY_TO_RECEIVE_INDICATIONS`
- `0x140039d3a`: `WDI_INDICATION_DISCONNECT_COMPLETE`
- `0x140039d2e`: `WDI_INDICATION_SET_RADIO_STATE_COMPLETE`
- `0x140039d22`: `WDI_INDICATION_SET_READY_TO_RECEIVE_INDICATIONS_COMPLETE`
- `0x140039dcd`: `WDI_SET_DELETE_CIPHER_KEYS`
- `0x140039e4e`: `WDI_INDICATION_LINK_STATE_CHANGE`
- `0x140039ea2`: `WDI_INDICATION_SCAN_COMPLETE`
- `0x140039ed2`: `WDI_INDICATION_P2P_DISCOVERY_COMPLETE`
- `0x140039f67`: `WDI_INDICATION_DOT11_RESET_COMPLETE`
- `0x140039f5b`: `WDI_INDICATION_CONNECT_COMPLETE`
- `0x140039f4f`: `WDI_INDICATION_P2P_SEND_REQUEST_ACTION_FRAME_COMPLETE`
- `0x140039f43`: `WDI_INDICATION_P2P_SEND_RESPONSE_ACTION_FRAME_COMPLETE`
- `0x140039f2b`: `WDI_INDICATION_CREATE_PORT_COMPLETE`
- `0x140039f1f`: `WDI_INDICATION_DELETE_PORT_COMPLETE`
- `0x140039f13`: `WDI_INDICATION_START_AP_COMPLETE`
- `0x140039f7f`: `WDI_INDICATION_STOP_AP_COMPLETE`
- `0x140039fee`: `WDI_INDICATION_SEND_AP_ASSOCIATION_RESPONSE_COMPLETE`
- `0x140039ffa`: `WDI_SET_REMOVE_WOL_PATTERN`
- `0x14003a036`: `WDI_SET_ADD_PM_PROTOCOL_OFFLOAD`
- `0x14003a02a`: `WDI_SET_REMOVE_PM_PROTOCOL_OFFLOAD`
- `0x14003a04e`: `WDI_SET_ADAPTER_CONFIGURATION`
- `0x14003a0d7`: `WDI_GET_PM_PROTOCOL_OFFLOAD`
- `0x14003a0bf`: `WDI_TASK_CHANGE_OPERATION_MODE`
- `0x14003a0b3`: `WDI_INDICATION_CHANGE_OPERATION_MODE_COMPLETE`
- `0x14003a08f`: `WDI_INDICATION_OPEN_COMPLETE`
- `0x14003a0fb`: `WDI_INDICATION_CLOSE_COMPLETE`
- `0x14003a1a9`: `WDI_TASK_ROAM`
- `0x14003a19d`: `WDI_INDICATION_ROAM_COMPLETE`
- `0x14003a191`: `WDI_TASK_SEND_REQUEST_ACTION_FRAME`
- `0x14003a179`: `WDI_INDICATION_TASK_OFFLOAD_CURRENT_CONFIG`
- `0x14003a16d`: `WDI_TASK_SEND_RESPONSE_ACTION_FRAME`
- `0x14003a1d9`: `WDI_INDICATION_SEND_REQUEST_ACTION_FRAME_COMPLETE`
- `0x14003a27a`: `WDI_INDICATION_SEND_RESPONSE_ACTION_FRAME_COMPLETE`
- `0x14003a26e`: `WDI_GET_NEXT_ACTION_FRAME_DIALOG_TOKEN`
- `0x14003a262`: `WDI_TASK_IHV`
- `0x14003a3a6`: `WDI_TASK_REQUEST_FTM`
- `0x14003a39d`: `WDI_INDICATION_REQUEST_FTM_COMPLETE`
- `0x14003a256`: `WDI_INDICATION_IHV_TASK_REQUEST`
- `0x14003a24a`: `WDI_INDICATION_IHV_TASK_COMPLETE`
- `0x140039fe2`: `WDI_ABORT_TASK`
- `0x14003a346`: `WDI_GET_SUPPORTED_DEVICE_SERVICES`
- `0x14003a3d3`: `WDI_DEVICE_SERVICE_COMMAND`
- `0x14003a3ca`: `WDI_INDICATION_CIPHER_KEY_UPDATED`
- `0x14003a3c1`: `WDI_INDICATION_DEVICE_SERVICE_EVENT`
- `0x14003a3f2`: `WDI_TEST_TASK`

## pseudocode

```c
const char *__fastcall WDI_TLV::stringify::ToLogString(unsigned __int16 a1)
{
  unsigned int v1; // ebx
  const char *result; // rax

  v1 = a1;
  if ( (unsigned int)Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline() )
    return WiFiCxTLVStaging::WDI_TLV::stringify::ToLogString(v1);
  if ( v1 <= 0x29 )
  {
    if ( v1 == 41 )
      return "WDI_SET_NETWORK_LIST_OFFLOAD";
    if ( v1 > 0x11 )
    {
      if ( v1 > 0x1C )
      {
        switch ( v1 )
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
        switch ( v1 )
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
      if ( v1 == 17 )
        return "WDI_TASK_SEND_AP_ASSOCIATION_RESPONSE";
      if ( v1 > 8 )
      {
        switch ( v1 )
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
        switch ( v1 )
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
    return "Unknown";
  }
  if ( v1 > 0x60 )
  {
    if ( v1 > 0xC8 )
    {
      result = "WDI_TEST_TASK";
      if ( v1 != 65504 )
        return "Unknown";
    }
    else if ( v1 == 200 )
    {
      return "WDI_INDICATION_SECONDARY_STA_CONNECTIVITY";
    }
    else if ( v1 > 0x77 )
    {
      if ( v1 <= 0x82 )
      {
        switch ( v1 )
        {
          case 0x82u:
            return "WDI_GET_SUPPORTED_DEVICE_SERVICES";
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
          case 0x80u:
            return "WDI_SET_NEIGHBOR_REPORT_ENTRIES";
        }
        return "Unknown";
      }
      switch ( v1 )
      {
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
        case 0x8Bu:
          return "WDI_SET_OWE_DH_IE";
        default:
          return "Unknown";
      }
    }
    else
    {
      if ( v1 == 119 )
        return "WDI_SET_P2P_START_BACKGROUND_DISCOVERY";
      if ( v1 > 0x6A )
      {
        switch ( v1 )
        {
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
          case 'v':
            return "WDI_TCP_RSC_STATISTICS";
        }
        return "Unknown";
      }
      switch ( v1 )
      {
        case 'j':
          return "WDI_INDICATION_SEND_REQUEST_ACTION_FRAME_COMPLETE";
        case 'a':
          return "WDI_SET_FLUSH_BSS_ENTRY";
        case 'b':
          return "WDI_INDICATION_ASSOCIATION_PARAMETERS_REQUEST";
        case 'c':
          return "WDI_SET_ASSOCIATION_PARAMETERS";
        case 'd':
          return "WDI_TASK_ROAM";
        case 'e':
          return "WDI_INDICATION_ROAM_COMPLETE";
        case 'f':
          return "WDI_TASK_SEND_REQUEST_ACTION_FRAME";
        case 'g':
          return "WDI_INDICATION_ACTION_FRAME_RECEIVED";
        case 'h':
          return "WDI_INDICATION_TASK_OFFLOAD_CURRENT_CONFIG";
        default:
          return "WDI_TASK_SEND_RESPONSE_ACTION_FRAME";
      }
    }
  }
  else
  {
    if ( v1 == 96 )
      return "WDI_INDICATION_CLOSE_COMPLETE";
    if ( v1 > 0x47 )
    {
      if ( v1 > 0x55 )
      {
        switch ( v1 )
        {
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
          case '^':
            return "WDI_INDICATION_IHV_EVENT";
          case '_':
            return "WDI_INDICATION_OPEN_COMPLETE";
        }
        return "Unknown";
      }
      if ( v1 == 85 )
        return "WDI_SET_ADAPTER_CONFIGURATION";
      if ( v1 <= 0x50 )
      {
        switch ( v1 )
        {
          case 'P':
            return "WDI_SET_REMOVE_WOL_PATTERN";
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
        }
        return "Unknown";
      }
      switch ( v1 )
      {
        case 'Q':
          return "WDI_SET_MULTICAST_LIST";
        case 'R':
          return "WDI_SET_ADD_PM_PROTOCOL_OFFLOAD";
        case 'S':
          return "WDI_SET_REMOVE_PM_PROTOCOL_OFFLOAD";
        default:
          return "WDI_INDICATION_P2P_GROUP_OPERATING_CHANNEL";
      }
    }
    else
    {
      if ( v1 == 71 )
        return "WDI_INDICATION_STOP_AP_COMPLETE";
      if ( v1 <= 0x3D )
      {
        if ( v1 == 61 )
          return "WDI_INDICATION_P2P_DISCOVERY_COMPLETE";
        if ( v1 > 0x37 )
        {
          switch ( v1 )
          {
            case '8':
              return "WDI_INDICATION_NLO_DISCOVERY";
            case '9':
              return "WDI_INDICATION_WAKE_REASON";
            case ';':
              return "WDI_INDICATION_TKIP_MIC_FAILURE";
            case '<':
              return "WDI_INDICATION_SCAN_COMPLETE";
          }
        }
        else
        {
          switch ( v1 )
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
        return "Unknown";
      }
      switch ( v1 )
      {
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
        default:
          return "WDI_INDICATION_START_AP_COMPLETE";
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140039b80  push    rbx
0x140039b82  sub     rsp, 20h
0x140039b86  movzx   ebx, cx
0x140039b89  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x140039b8e  test    eax, eax
0x140039b90  jz      short loc_140039B9F
0x140039b92  movzx   ecx, bx
0x140039b95  call    ?ToLogString@stringify@WDI_TLV@WiFiCxTLVStaging@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WiFiCxTLVStaging::WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x140039b9a  jmp     loc_14003A3FD
0x140039b9f  mov     ecx, ebx
0x140039ba1  cmp     ebx, 29h ; ')'
0x140039ba4  ja      loc_140039DF1
0x140039baa  jz      loc_140039DE5
0x140039bb0  cmp     ebx, 11h
0x140039bb3  ja      loc_140039CD8
0x140039bb9  jz      loc_140039CCC
0x140039bbf  cmp     ebx, 8
0x140039bc2  ja      loc_140039C51
0x140039bc8  jz      short loc_140039C45
0x140039bca  sub     ecx, 1
0x140039bcd  jz      short loc_140039C39
0x140039bcf  sub     ecx, 1
0x140039bd2  jz      short loc_140039C2D
0x140039bd4  sub     ecx, 1
0x140039bd7  jz      short loc_140039C21
0x140039bd9  sub     ecx, 1
0x140039bdc  jz      short loc_140039C15
0x140039bde  sub     ecx, 1
0x140039be1  jz      short loc_140039C09
0x140039be3  sub     ecx, 1
0x140039be6  jz      short loc_140039BFD
0x140039be8  cmp     ecx, 1
0x140039beb  jnz     loc_14003A382
0x140039bf1  lea     rax, aWdiTaskDot11Re; "WDI_TASK_DOT11_RESET"
0x140039bf8  jmp     loc_14003A3FD
0x140039bfd  lea     rax, aWdiTaskConnect; "WDI_TASK_CONNECT"
0x140039c04  jmp     loc_14003A3FD
0x140039c09  lea     rax, aWdiTaskP2pDisc; "WDI_TASK_P2P_DISCOVER"
0x140039c10  jmp     loc_14003A3FD
0x140039c15  lea     rax, aWdiTaskScan; "WDI_TASK_SCAN"
0x140039c1c  jmp     loc_14003A3FD
0x140039c21  lea     rax, aWdiSetHostDete; "WDI_SET_HOST_DETECT_ERROR"
0x140039c28  jmp     loc_14003A3FD
0x140039c2d  lea     rax, aWdiTaskClose; "WDI_TASK_CLOSE"
0x140039c34  jmp     loc_14003A3FD
0x140039c39  lea     rax, aWdiTaskOpen; "WDI_TASK_OPEN"
0x140039c40  jmp     loc_14003A3FD
0x140039c45  lea     rax, aWdiTaskDisconn; "WDI_TASK_DISCONNECT"
0x140039c4c  jmp     loc_14003A3FD
0x140039c51  sub     ecx, 9
0x140039c54  jz      short loc_140039CC0
0x140039c56  sub     ecx, 1
0x140039c59  jz      short loc_140039CB4
0x140039c5b  sub     ecx, 1
0x140039c5e  jz      short loc_140039CA8
0x140039c60  sub     ecx, 1
0x140039c63  jz      short loc_140039C9C
0x140039c65  sub     ecx, 1
0x140039c68  jz      short loc_140039C90
0x140039c6a  sub     ecx, 1
0x140039c6d  jz      short loc_140039C84
0x140039c6f  cmp     ecx, 1
0x140039c72  jnz     loc_14003A382
0x140039c78  lea     rax, aWdiTaskStopAp; "WDI_TASK_STOP_AP"
0x140039c7f  jmp     loc_14003A3FD
0x140039c84  lea     rax, aWdiTaskStartAp; "WDI_TASK_START_AP"
0x140039c8b  jmp     loc_14003A3FD
0x140039c90  lea     rax, aWdiTaskDeleteP; "WDI_TASK_DELETE_PORT"
0x140039c97  jmp     loc_14003A3FD
0x140039c9c  lea     rax, aWdiTaskCreateP; "WDI_TASK_CREATE_PORT"
0x140039ca3  jmp     loc_14003A3FD
0x140039ca8  lea     rax, aWdiTaskSetRadi; "WDI_TASK_SET_RADIO_STATE"
0x140039caf  jmp     loc_14003A3FD
0x140039cb4  lea     rax, aWdiTaskP2pSend_0; "WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME"
0x140039cbb  jmp     loc_14003A3FD
0x140039cc0  lea     rax, aWdiTaskP2pSend; "WDI_TASK_P2P_SEND_REQUEST_ACTION_FRAME"
0x140039cc7  jmp     loc_14003A3FD
0x140039ccc  lea     rax, aWdiTaskSendApA; "WDI_TASK_SEND_AP_ASSOCIATION_RESPONSE"
0x140039cd3  jmp     loc_14003A3FD
0x140039cd8  cmp     ecx, 1Ch
0x140039cdb  ja      loc_140039D6A
0x140039ce1  jz      short loc_140039D5E
0x140039ce3  sub     ecx, 12h
0x140039ce6  jz      short loc_140039D52
0x140039ce8  sub     ecx, 1
0x140039ceb  jz      short loc_140039D46
0x140039ced  sub     ecx, 2
0x140039cf0  jz      short loc_140039D3A
0x140039cf2  sub     ecx, 1
0x140039cf5  jz      short loc_140039D2E
0x140039cf7  sub     ecx, 1
0x140039cfa  jz      short loc_140039D22
0x140039cfc  sub     ecx, 1
0x140039cff  jz      short loc_140039D16
0x140039d01  cmp     ecx, 2
0x140039d04  jnz     loc_14003A382
0x140039d0a  lea     rax, aWdiSetP2pListe; "WDI_SET_P2P_LISTEN_STATE"
0x140039d11  jmp     loc_14003A3FD
0x140039d16  lea     rax, aWdiSetOperatio; "WDI_SET_OPERATION_MODE"
0x140039d1d  jmp     loc_14003A3FD
0x140039d22  lea     rax, aWdiIndicationS_1; "WDI_INDICATION_SET_READY_TO_RECEIVE_IND"...
0x140039d29  jmp     loc_14003A3FD
0x140039d2e  lea     rax, aWdiIndicationS_7; "WDI_INDICATION_SET_RADIO_STATE_COMPLETE"
0x140039d35  jmp     loc_14003A3FD
0x140039d3a  lea     rax, aWdiIndicationD_3; "WDI_INDICATION_DISCONNECT_COMPLETE"
0x140039d41  jmp     loc_14003A3FD
0x140039d46  lea     rax, aWdiSetPowerSta; "WDI_SET_POWER_STATE"
0x140039d4d  jmp     loc_14003A3FD
0x140039d52  lea     rax, aWdiTaskSetRead; "WDI_TASK_SET_READY_TO_RECEIVE_INDICATIO"...
0x140039d59  jmp     loc_14003A3FD
0x140039d5e  lea     rax, aWdiSetPrivacyE; "WDI_SET_PRIVACY_EXEMPTION_LIST"
0x140039d65  jmp     loc_14003A3FD
0x140039d6a  sub     ecx, 1Dh
0x140039d6d  jz      short loc_140039DD9
0x140039d6f  sub     ecx, 1
0x140039d72  jz      short loc_140039DCD
0x140039d74  sub     ecx, 1
0x140039d77  jz      short loc_140039DC1
0x140039d79  sub     ecx, 1
0x140039d7c  jz      short loc_140039DB5
0x140039d7e  sub     ecx, 2
0x140039d81  jz      short loc_140039DA9
0x140039d83  sub     ecx, 2
0x140039d86  jz      short loc_140039D9D
0x140039d88  cmp     ecx, 1
0x140039d8b  jnz     loc_14003A382
0x140039d91  lea     rax, aWdiGetAdapterC; "WDI_GET_ADAPTER_CAPABILITIES"
0x140039d98  jmp     loc_14003A3FD
0x140039d9d  lea     rax, aWdiSetReceiveP; "WDI_SET_RECEIVE_PACKET_FILTER"
0x140039da4  jmp     loc_14003A3FD
0x140039da9  lea     rax, aWdiGetStatisti; "WDI_GET_STATISTICS"
0x140039db0  jmp     loc_14003A3FD
0x140039db5  lea     rax, aWdiSetConnecti; "WDI_SET_CONNECTION_QUALITY"
0x140039dbc  jmp     loc_14003A3FD
0x140039dc1  lea     rax, aWdiSetDefaultK; "WDI_SET_DEFAULT_KEY_ID"
0x140039dc8  jmp     loc_14003A3FD
0x140039dcd  lea     rax, aWdiSetDeleteCi; "WDI_SET_DELETE_CIPHER_KEYS"
0x140039dd4  jmp     loc_14003A3FD
0x140039dd9  lea     rax, aWdiSetAddCiphe; "WDI_SET_ADD_CIPHER_KEYS"
0x140039de0  jmp     loc_14003A3FD
0x140039de5  lea     rax, aWdiSetNetworkL; "WDI_SET_NETWORK_LIST_OFFLOAD"
0x140039dec  jmp     loc_14003A3FD
0x140039df1  cmp     ecx, 60h ; '`'
0x140039df4  ja      loc_14003A107
0x140039dfa  jz      loc_14003A0FB
0x140039e00  cmp     ecx, 47h ; 'G'
0x140039e03  ja      loc_140039F8B
0x140039e09  jz      loc_140039F7F
0x140039e0f  cmp     ecx, 3Dh ; '='
0x140039e12  ja      loc_140039EDE
0x140039e18  jz      loc_140039ED2
0x140039e1e  cmp     ecx, 37h ; '7'
0x140039e21  ja      short loc_140039E8A
0x140039e23  jz      short loc_140039E7E
0x140039e25  sub     ecx, 2Fh ; '/'
0x140039e28  jz      short loc_140039E72
0x140039e2a  sub     ecx, 4
0x140039e2d  jz      short loc_140039E66
0x140039e2f  sub     ecx, 1
0x140039e32  jz      short loc_140039E5A
0x140039e34  sub     ecx, 1
0x140039e37  jz      short loc_140039E4E
0x140039e39  cmp     ecx, 1
0x140039e3c  jnz     loc_14003A382
0x140039e42  lea     rax, aWdiIndicationP_1; "WDI_INDICATION_P2P_ACTION_FRAME_RECEIVE"...
0x140039e49  jmp     loc_14003A3FD
0x140039e4e  lea     rax, aWdiIndicationL; "WDI_INDICATION_LINK_STATE_CHANGE"
0x140039e55  jmp     loc_14003A3FD
0x140039e5a  lea     rax, aWdiIndicationR; "WDI_INDICATION_ROAMING_NEEDED"
0x140039e61  jmp     loc_14003A3FD
0x140039e66  lea     rax, aWdiIndicationD_2; "WDI_INDICATION_DISASSOCIATION"
0x140039e6d  jmp     loc_14003A3FD
0x140039e72  lea     rax, aWdiGetBssEntry; "WDI_GET_BSS_ENTRY_LIST"
0x140039e79  jmp     loc_14003A3FD
0x140039e7e  lea     rax, aWdiIndicationA_1; "WDI_INDICATION_AP_ASSOCIATION_REQUEST_R"...
0x140039e85  jmp     loc_14003A3FD
0x140039e8a  sub     ecx, 38h ; '8'
0x140039e8d  jz      short loc_140039EC6
0x140039e8f  sub     ecx, 1
0x140039e92  jz      short loc_140039EBA
0x140039e94  sub     ecx, 2
0x140039e97  jz      short loc_140039EAE
0x140039e99  cmp     ecx, 1
0x140039e9c  jnz     loc_14003A382
0x140039ea2  lea     rax, aWdiIndicationS_3; "WDI_INDICATION_SCAN_COMPLETE"
0x140039ea9  jmp     loc_14003A3FD
0x140039eae  lea     rax, aWdiIndicationT; "WDI_INDICATION_TKIP_MIC_FAILURE"
0x140039eb5  jmp     loc_14003A3FD
0x140039eba  lea     rax, aWdiIndicationW; "WDI_INDICATION_WAKE_REASON"
0x140039ec1  jmp     loc_14003A3FD
0x140039ec6  lea     rax, aWdiIndicationN; "WDI_INDICATION_NLO_DISCOVERY"
0x140039ecd  jmp     loc_14003A3FD
0x140039ed2  lea     rax, aWdiIndicationP_4; "WDI_INDICATION_P2P_DISCOVERY_COMPLETE"
0x140039ed9  jmp     loc_14003A3FD
0x140039ede  sub     ecx, 3Eh ; '>'
0x140039ee1  jz      loc_140039F73
0x140039ee7  sub     ecx, 1
0x140039eea  jz      short loc_140039F67
0x140039eec  sub     ecx, 1
0x140039eef  jz      short loc_140039F5B
0x140039ef1  sub     ecx, 1
0x140039ef4  jz      short loc_140039F4F
0x140039ef6  sub     ecx, 1
0x140039ef9  jz      short loc_140039F43
0x140039efb  sub     ecx, 1
0x140039efe  jz      short loc_140039F37
0x140039f00  sub     ecx, 1
0x140039f03  jz      short loc_140039F2B
0x140039f05  sub     ecx, 1
0x140039f08  jz      short loc_140039F1F
0x140039f0a  cmp     ecx, 1
0x140039f0d  jnz     loc_14003A382
0x140039f13  lea     rax, aWdiIndicationS_2; "WDI_INDICATION_START_AP_COMPLETE"
0x140039f1a  jmp     loc_14003A3FD
0x140039f1f  lea     rax, aWdiIndicationD_1; "WDI_INDICATION_DELETE_PORT_COMPLETE"
0x140039f26  jmp     loc_14003A3FD
0x140039f2b  lea     rax, aWdiIndicationC_1; "WDI_INDICATION_CREATE_PORT_COMPLETE"
0x140039f32  jmp     loc_14003A3FD
0x140039f37  lea     rax, aWdiIndicationR_0; "WDI_INDICATION_RADIO_STATUS"
0x140039f3e  jmp     loc_14003A3FD
0x140039f43  lea     rax, aWdiIndicationP_0; "WDI_INDICATION_P2P_SEND_RESPONSE_ACTION"...
0x140039f4a  jmp     loc_14003A3FD
0x140039f4f  lea     rax, aWdiIndicationP_3; "WDI_INDICATION_P2P_SEND_REQUEST_ACTION_"...
0x140039f56  jmp     loc_14003A3FD
0x140039f5b  lea     rax, aWdiIndicationC_3; "WDI_INDICATION_CONNECT_COMPLETE"
0x140039f62  jmp     loc_14003A3FD
0x140039f67  lea     rax, aWdiIndicationD; "WDI_INDICATION_DOT11_RESET_COMPLETE"
0x140039f6e  jmp     loc_14003A3FD
0x140039f73  lea     rax, aWdiIndicationB; "WDI_INDICATION_BSS_ENTRY_LIST"
0x140039f7a  jmp     loc_14003A3FD
0x140039f7f  lea     rax, aWdiIndicationS_6; "WDI_INDICATION_STOP_AP_COMPLETE"
0x140039f86  jmp     loc_14003A3FD
0x140039f8b  cmp     ecx, 55h ; 'U'
0x140039f8e  ja      loc_14003A05A
0x140039f94  jz      loc_14003A04E
0x140039f9a  cmp     ecx, 50h ; 'P'
0x140039f9d  ja      short loc_14003A006
0x140039f9f  jz      short loc_140039FFA
0x140039fa1  sub     ecx, 49h ; 'I'
0x140039fa4  jz      short loc_140039FEE
0x140039fa6  sub     ecx, 2
0x140039fa9  jz      short loc_140039FE2
0x140039fab  sub     ecx, 1
0x140039fae  jz      short loc_140039FD6
0x140039fb0  sub     ecx, 2
0x140039fb3  jz      short loc_140039FCA
0x140039fb5  cmp     ecx, 1
0x140039fb8  jnz     loc_14003A382
0x140039fbe  lea     rax, aWdiSetAddWolPa; "WDI_SET_ADD_WOL_PATTERN"
0x140039fc5  jmp     loc_14003A3FD
0x140039fca  lea     rax, aWdiGetAutoPowe; "WDI_GET_AUTO_POWER_SAVE"
0x140039fd1  jmp     loc_14003A3FD
0x140039fd6  lea     rax, aWdiIndicationA_2; "WDI_INDICATION_ASSOCIATION_RESULT"
0x140039fdd  jmp     loc_14003A3FD
0x140039fe2  lea     rax, aWdiAbortTask; "WDI_ABORT_TASK"
0x140039fe9  jmp     loc_14003A3FD
0x140039fee  lea     rax, aWdiIndicationS_8; "WDI_INDICATION_SEND_AP_ASSOCIATION_RESP"...
0x140039ff5  jmp     loc_14003A3FD
0x140039ffa  lea     rax, aWdiSetRemoveWo; "WDI_SET_REMOVE_WOL_PATTERN"
0x14003a001  jmp     loc_14003A3FD
0x14003a006  sub     ecx, 51h ; 'Q'
0x14003a009  jz      short loc_14003A042
0x14003a00b  sub     ecx, 1
0x14003a00e  jz      short loc_14003A036
0x14003a010  sub     ecx, 1
0x14003a013  jz      short loc_14003A02A
0x14003a015  cmp     ecx, 1
0x14003a018  jnz     loc_14003A382
0x14003a01e  lea     rax, aWdiIndicationP; "WDI_INDICATION_P2P_GROUP_OPERATING_CHAN"...
0x14003a025  jmp     loc_14003A3FD
0x14003a02a  lea     rax, aWdiSetRemovePm; "WDI_SET_REMOVE_PM_PROTOCOL_OFFLOAD"
0x14003a031  jmp     loc_14003A3FD
0x14003a036  lea     rax, aWdiSetAddPmPro; "WDI_SET_ADD_PM_PROTOCOL_OFFLOAD"
0x14003a03d  jmp     loc_14003A3FD
0x14003a042  lea     rax, aWdiSetMulticas; "WDI_SET_MULTICAST_LIST"
0x14003a049  jmp     loc_14003A3FD
0x14003a04e  lea     rax, aWdiSetAdapterC; "WDI_SET_ADAPTER_CONFIGURATION"
0x14003a055  jmp     loc_14003A3FD
0x14003a05a  sub     ecx, 56h ; 'V'
0x14003a05d  jz      loc_14003A0EF
0x14003a063  sub     ecx, 1
0x14003a066  jz      short loc_14003A0E3
0x14003a068  sub     ecx, 1
0x14003a06b  jz      short loc_14003A0D7
0x14003a06d  sub     ecx, 1
0x14003a070  jz      short loc_14003A0CB
0x14003a072  sub     ecx, 1
0x14003a075  jz      short loc_14003A0BF
0x14003a077  sub     ecx, 1
0x14003a07a  jz      short loc_14003A0B3
0x14003a07c  sub     ecx, 2
0x14003a07f  jz      short loc_14003A0A7
0x14003a081  sub     ecx, 1
0x14003a084  jz      short loc_14003A09B
0x14003a086  cmp     ecx, 1
0x14003a089  jnz     loc_14003A382
0x14003a08f  lea     rax, aWdiIndicationO; "WDI_INDICATION_OPEN_COMPLETE"
0x14003a096  jmp     loc_14003A3FD
0x14003a09b  lea     rax, aWdiIndicationI; "WDI_INDICATION_IHV_EVENT"
0x14003a0a2  jmp     loc_14003A3FD
  ... truncated ...
```
