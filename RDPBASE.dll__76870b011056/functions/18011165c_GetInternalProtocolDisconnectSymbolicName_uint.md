# GetInternalProtocolDisconnectSymbolicName(uint)

- ea: `0x18011165c`
- end: `0x180111a33`
- name: `?GetInternalProtocolDisconnectSymbolicName@@YAPEBDI@Z`
- size: `983`
- prototype: `const char *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180111ca0`

## callees

- `0x18011165c`

## string_xrefs

- `0x18011180c`: `AgentCommunicationError`
- `0x1801117d4`: `ProtocolInvalidData`
- `0x18011191c`: `ProtocolDecryptFailed`
- `0x1801117c4`: `CloseStackOnTransportSecurityError`
- `0x180111761`: `CloseStackOnUnexpectedProtocolError`
- `0x18011194c`: `CreateInputDevicesErrorDeviceNotAvailable`
- `0x1801117ac`: `CreateInputDevicesError`
- `0x180111824`: `CreateFakeGraphicsChannelError`
- `0x18011181c`: `CreateGraphicsPipePluginError`
- `0x1801118e2`: `InvalidAuthToken`
- `0x1801118da`: `LocalSecurityAuthorityError`
- `0x1801116f7`: `VirtualChannelDecompressionErr`
- `0x18011193c`: `SSPISideTransportError`
- `0x180111855`: `SideTransportError`
- `0x180111944`: `SideTransportTurnServerShutdown`
- `0x1801118c2`: `SideTransportListenerInternalError`
- `0x180111954`: `RDPProtocolEncryptFailed`
- `0x1801116ef`: `X224DataIncompleteMCSPacket`
- `0x18011199d`: `Log_Multipath_InvalidRequest`
- `0x1801119ad`: `Log_Multipath_ProtocolInternalError`
- `0x18011198d`: `Log_Multipath_TransportShutdown`
- `0x180111995`: `Log_Multipath_RequestDenied`
- `0x1801119a5`: `Log_Multipath_InvalidPacketBufferSize`
- `0x1801119c5`: `Log_Multipath_SideTransportError`
- `0x180111a1b`: `Log_Multipath_Websocket_ResponseError`
- `0x180111a2b`: `Log_Multipath_Websocket_GenericError`
- `0x180111a13`: `Log_Multipath_Websocket_InvalidRequest`
- `0x180111a23`: `Log_Multipath_Websocket_ServerError`
- `0x180111a03`: `Log_Multipath_Websocket_TransportShutdown`
- `0x180111a0b`: `Log_Multipath_Websocket_RequestDenied`
- `0x18011192c`: `Log_RDP_SideTransportPacketWriteToWinsockFailed`
- `0x1801119fb`: `Log_Multipath_Websocket_SideTransportError`
- `0x180111934`: `Log_RDP_SideTransportWriteThreadHang`
- `0x1801119f3`: `InternalProtocolDisconnect`

## pseudocode

```c
const char *__fastcall GetInternalProtocolDisconnectSymbolicName(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx

  if ( a1 <= 0x115C )
  {
    if ( a1 == 4444 )
      return "SideTransportError";
    if ( a1 > 0x1139 )
    {
      if ( a1 > 0x1156 )
      {
        v24 = a1 - 4442;
        if ( !v24 )
          return "LogonOperationFailure";
        if ( v24 == 1 )
          return "GraphicsDecodingClientMessageError";
      }
      else
      {
        if ( a1 == 4438 )
          return "AutoReconnectLogonFailure";
        if ( a1 > 0x114B )
        {
          v20 = a1 - 4428;
          if ( !v20 )
            return "CreateFakeGraphicsChannelError";
          v21 = v20 - 1;
          if ( !v21 )
            return "CreateGraphicsPipePluginError";
          v22 = v21 - 1;
          if ( !v22 )
            return "EstablishingSessionError";
          v23 = v22 - 1;
          if ( !v23 )
            return "AgentCommunicationError";
          if ( v23 == 3 )
            return "AutoReconnectCookieExpired";
        }
        else
        {
          if ( a1 == 4427 )
            return "GraphicsInitializationTimeout";
          v15 = a1 - 4420;
          if ( !v15 )
            return "ProtocolInvalidData";
          v16 = v15 - 2;
          if ( !v16 )
            return "CloseStackOnWebsocketTransportError";
          v17 = v16 - 1;
          if ( !v17 )
            return "CloseStackOnTransportSecurityError";
          v18 = v17 - 1;
          if ( !v18 )
            return "HttpInternalError";
          v19 = v18 - 1;
          if ( !v19 )
            return "InvalidHttpServerResponse";
          if ( v19 == 1 )
            return "CreateInputDevicesError";
        }
      }
    }
    else
    {
      if ( a1 == 4409 )
        return "CloseStackOnUnexpectedProtocolError";
      if ( a1 > 0x10EC )
      {
        v9 = a1 - 4395;
        if ( !v9 )
          return "VCDataTooLong";
        v10 = v9 - 2;
        if ( !v10 )
          return "GraphicsModeNotSupported";
        v11 = v10 - 2;
        if ( !v11 )
          return "GraphicsSubsystemFailed";
        v12 = v11 - 4;
        if ( !v12 )
          return "VCDecodingError";
        v13 = v12 - 2;
        if ( !v13 )
          return "RemoteAppMonitorGeometryValidationFailed";
        v14 = v13 - 1;
        if ( !v14 )
          return "RemoteAppInvalidMonitorCount";
        if ( v14 == 2 )
          return "CloseStackOnTransportInternalError";
      }
      else
      {
        if ( a1 == 4332 )
          return "VirtualChannelDecompressionErr";
        v1 = a1 - 4105;
        if ( !v1 )
          return "X224DataIncompleteMCSPacket";
        v2 = v1 - 2;
        if ( !v2 )
          return "X224UnknownPacketType";
        v3 = v2 - 21;
        if ( !v3 )
          return "X224SecFilterFailedActivate";
        v4 = v3 - 1;
        if ( !v4 )
          return "X224SecFilterFailedActivate";
        v5 = v4 - 1;
        if ( !v5 )
          return "SSLRequiredByServerNoClientAuthNego";
        v6 = v5 - 168;
        if ( !v6 )
          return "UnknownPDUType";
        v7 = v6 - 20;
        if ( !v7 )
          return "InputPDUBadLength";
        if ( v7 == 12 )
          return "BadCapabilities";
      }
    }
    return "InternalProtocolDisconnect";
  }
  if ( a1 <= 0x1193 )
  {
    if ( a1 == 4499 )
      return "RDPProtocolEncryptFailed";
    if ( a1 > 0x1171 )
    {
      v32 = a1 - 4469;
      if ( !v32 )
        return "CreateInputDevicesErrorDeviceNotAvailable";
      v33 = v32 - 1;
      if ( !v33 )
        return "SideTransportTurnServerShutdown";
      v34 = v33 - 1;
      if ( !v34 )
        return "SSPISideTransportError";
      v35 = v34 - 18;
      if ( !v35 )
        return "Log_RDP_SideTransportWriteThreadHang";
      v36 = v35 - 2;
      if ( !v36 )
        return "Log_RDP_SideTransportPacketWriteToWinsockFailed";
      v37 = v36 - 1;
      if ( !v37 )
        return "Log_RDP_UserDisconnectedBeforeLogon";
      if ( v37 == 6 )
        return "ProtocolDecryptFailed";
    }
    else
    {
      if ( a1 == 4465 )
        return "GraphicsCapsNotReceived";
      v25 = a1 - 4445;
      if ( !v25 )
        return "InvalidAuthToken";
      v26 = v25 - 1;
      if ( !v26 )
        return "LocalSecurityAuthorityError";
      v27 = v26 - 1;
      if ( !v27 )
        return "HttpTransportInvalidState";
      v28 = v27 - 6;
      if ( !v28 )
        return "GraphicsPipeClientAckTimeout";
      v29 = v28 - 4;
      if ( !v29 )
        return "SideTransportListenerInternalError";
      v30 = v29 - 3;
      if ( !v30 )
        return "GraphicsSubsystemInitFailed";
      v31 = v30 - 1;
      if ( !v31 )
        return "GraphicsPipelineRestartFailed";
      if ( v31 == 2 )
        return "GetInputDeviceHandlesError";
    }
    return "InternalProtocolDisconnect";
  }
  if ( a1 <= 0x1266 )
  {
    if ( a1 == 4710 )
      return "Log_Multipath_SideTransportError";
    v38 = a1 - 4597;
    if ( !v38 )
      return "Log_RDP_WCIO_DisplayProtectionNotSupportedByClient";
    v39 = v38 - 1;
    if ( !v39 )
      return "Log_RDP_WCIO_DisplayProtectionLicenseIssueingFailed";
    v40 = v39 - 99;
    if ( !v40 )
      return "Log_Multipath_ProtocolInternalError";
    v41 = v40 - 4;
    if ( !v41 )
      return "Log_Multipath_InvalidPacketBufferSize";
    v42 = v41 - 2;
    if ( !v42 )
      return "Log_Multipath_InvalidRequest";
    v43 = v42 - 2;
    if ( !v43 )
      return "Log_Multipath_RequestDenied";
    if ( v43 == 1 )
      return "Log_Multipath_TransportShutdown";
    return "InternalProtocolDisconnect";
  }
  v44 = a1 - 4738;
  if ( !v44 )
    return "Log_Multipath_Websocket_GenericError";
  v45 = v44 - 1;
  if ( !v45 )
    return "Log_Multipath_Websocket_ServerError";
  v46 = v45 - 1;
  if ( !v46 )
    return "Log_Multipath_Websocket_ResponseError";
  v47 = v46 - 3;
  if ( !v47 )
    return "Log_Multipath_Websocket_InvalidRequest";
  v48 = v47 - 2;
  if ( !v48 )
    return "Log_Multipath_Websocket_RequestDenied";
  v49 = v48 - 1;
  if ( !v49 )
    return "Log_Multipath_Websocket_TransportShutdown";
  if ( v49 != 4 )
    return "InternalProtocolDisconnect";
  return "Log_Multipath_Websocket_SideTransportError";
}

```

## disassembly

```asm
0x18011165c  mov     eax, 115Ch
0x180111661  cmp     ecx, eax
0x180111663  ja      loc_18011185D
0x180111669  jz      loc_180111855
0x18011166f  mov     eax, 1139h
0x180111674  cmp     ecx, eax
0x180111676  ja      loc_180111769
0x18011167c  jz      loc_180111761
0x180111682  mov     eax, 10ECh
0x180111687  cmp     ecx, eax
0x180111689  ja      short loc_1801116FF
0x18011168b  jz      short loc_1801116F7
0x18011168d  sub     ecx, 1009h
0x180111693  jz      short loc_1801116EF
0x180111695  sub     ecx, 2
0x180111698  jz      short loc_1801116E7
0x18011169a  sub     ecx, 15h
0x18011169d  jz      short loc_1801116DF
0x18011169f  sub     ecx, 1
0x1801116a2  jz      short loc_1801116DF
0x1801116a4  sub     ecx, 1
0x1801116a7  jz      short loc_1801116D7
0x1801116a9  sub     ecx, 0A8h
0x1801116af  jz      short loc_1801116CF
0x1801116b1  sub     ecx, 14h
0x1801116b4  jz      short loc_1801116C7
0x1801116b6  cmp     ecx, 0Ch
0x1801116b9  jnz     loc_1801119F3
0x1801116bf  lea     rax, aBadcapabilitie; "BadCapabilities"
0x1801116c6  retn
0x1801116c7  lea     rax, aInputpdubadlen; "InputPDUBadLength"
0x1801116ce  retn
0x1801116cf  lea     rax, aUnknownpdutype; "UnknownPDUType"
0x1801116d6  retn
0x1801116d7  lea     rax, aSslrequiredbys; "SSLRequiredByServerNoClientAuthNego"
0x1801116de  retn
0x1801116df  lea     rax, aX224secfilterf; "X224SecFilterFailedActivate"
0x1801116e6  retn
0x1801116e7  lea     rax, aX224unknownpac; "X224UnknownPacketType"
0x1801116ee  retn
0x1801116ef  lea     rax, aX224dataincomp; "X224DataIncompleteMCSPacket"
0x1801116f6  retn
0x1801116f7  lea     rax, aVirtualchannel; "VirtualChannelDecompressionErr"
0x1801116fe  retn
0x1801116ff  sub     ecx, 112Bh
0x180111705  jz      short loc_180111759
0x180111707  sub     ecx, 2
0x18011170a  jz      short loc_180111751
0x18011170c  sub     ecx, 2
0x18011170f  jz      short loc_180111749
0x180111711  sub     ecx, 4
0x180111714  jz      short loc_180111741
0x180111716  sub     ecx, 2
0x180111719  jz      short loc_180111739
0x18011171b  sub     ecx, 1
0x18011171e  jz      short loc_180111731
0x180111720  cmp     ecx, 2
0x180111723  jnz     loc_1801119F3
0x180111729  lea     rax, aClosestackontr_0; "CloseStackOnTransportInternalError"
0x180111730  retn
0x180111731  lea     rax, aRemoteappinval; "RemoteAppInvalidMonitorCount"
0x180111738  retn
0x180111739  lea     rax, aRemoteappmonit; "RemoteAppMonitorGeometryValidationFaile"...
0x180111740  retn
0x180111741  lea     rax, aVcdecodingerro; "VCDecodingError"
0x180111748  retn
0x180111749  lea     rax, aGraphicssubsys_0; "GraphicsSubsystemFailed"
0x180111750  retn
0x180111751  lea     rax, aGraphicsmodeno; "GraphicsModeNotSupported"
0x180111758  retn
0x180111759  lea     rax, aVcdatatoolong; "VCDataTooLong"
0x180111760  retn
0x180111761  lea     rax, aClosestackonun; "CloseStackOnUnexpectedProtocolError"
0x180111768  retn
0x180111769  mov     eax, 1156h
0x18011176e  cmp     ecx, eax
0x180111770  ja      loc_180111834
0x180111776  jz      loc_18011182C
0x18011177c  mov     eax, 114Bh
0x180111781  cmp     ecx, eax
0x180111783  ja      short loc_1801117E4
0x180111785  jz      short loc_1801117DC
0x180111787  sub     ecx, 1144h
0x18011178d  jz      short loc_1801117D4
0x18011178f  sub     ecx, 2
0x180111792  jz      short loc_1801117CC
0x180111794  sub     ecx, 1
0x180111797  jz      short loc_1801117C4
0x180111799  sub     ecx, 1
0x18011179c  jz      short loc_1801117BC
0x18011179e  sub     ecx, 1
0x1801117a1  jz      short loc_1801117B4
0x1801117a3  cmp     ecx, 1
0x1801117a6  jnz     loc_1801119F3
0x1801117ac  lea     rax, aCreateinputdev_0; "CreateInputDevicesError"
0x1801117b3  retn
0x1801117b4  lea     rax, aInvalidhttpser; "InvalidHttpServerResponse"
0x1801117bb  retn
0x1801117bc  lea     rax, aHttpinternaler; "HttpInternalError"
0x1801117c3  retn
0x1801117c4  lea     rax, aClosestackontr; "CloseStackOnTransportSecurityError"
0x1801117cb  retn
0x1801117cc  lea     rax, aClosestackonwe; "CloseStackOnWebsocketTransportError"
0x1801117d3  retn
0x1801117d4  lea     rax, aProtocolinvali; "ProtocolInvalidData"
0x1801117db  retn
0x1801117dc  lea     rax, aGraphicsinitia; "GraphicsInitializationTimeout"
0x1801117e3  retn
0x1801117e4  sub     ecx, 114Ch
0x1801117ea  jz      short loc_180111824
0x1801117ec  sub     ecx, 1
0x1801117ef  jz      short loc_18011181C
0x1801117f1  sub     ecx, 1
0x1801117f4  jz      short loc_180111814
0x1801117f6  sub     ecx, 1
0x1801117f9  jz      short loc_18011180C
0x1801117fb  cmp     ecx, 3
0x1801117fe  jnz     loc_1801119F3
0x180111804  lea     rax, aAutoreconnectc; "AutoReconnectCookieExpired"
0x18011180b  retn
0x18011180c  lea     rax, aAgentcommunica; "AgentCommunicationError"
0x180111813  retn
0x180111814  lea     rax, aEstablishingse; "EstablishingSessionError"
0x18011181b  retn
0x18011181c  lea     rax, aCreategraphics; "CreateGraphicsPipePluginError"
0x180111823  retn
0x180111824  lea     rax, aCreatefakegrap; "CreateFakeGraphicsChannelError"
0x18011182b  retn
0x18011182c  lea     rax, aAutoreconnectl; "AutoReconnectLogonFailure"
0x180111833  retn
0x180111834  sub     ecx, 115Ah
0x18011183a  jz      short loc_18011184D
0x18011183c  cmp     ecx, 1
0x18011183f  jnz     loc_1801119F3
0x180111845  lea     rax, aGraphicsdecodi; "GraphicsDecodingClientMessageError"
0x18011184c  retn
0x18011184d  lea     rax, aLogonoperation; "LogonOperationFailure"
0x180111854  retn
0x180111855  lea     rax, aSidetransporte; "SideTransportError"
0x18011185c  retn
0x18011185d  mov     eax, 1193h
0x180111862  cmp     ecx, eax
0x180111864  ja      loc_18011195C
0x18011186a  jz      loc_180111954
0x180111870  mov     eax, 1171h
0x180111875  cmp     ecx, eax
0x180111877  ja      short loc_1801118F2
0x180111879  jz      short loc_1801118EA
0x18011187b  sub     ecx, 115Dh
0x180111881  jz      short loc_1801118E2
0x180111883  sub     ecx, 1
0x180111886  jz      short loc_1801118DA
0x180111888  sub     ecx, 1
0x18011188b  jz      short loc_1801118D2
0x18011188d  sub     ecx, 6
0x180111890  jz      short loc_1801118CA
0x180111892  sub     ecx, 4
0x180111895  jz      short loc_1801118C2
0x180111897  sub     ecx, 3
0x18011189a  jz      short loc_1801118BA
0x18011189c  sub     ecx, 1
0x18011189f  jz      short loc_1801118B2
0x1801118a1  cmp     ecx, 2
0x1801118a4  jnz     loc_1801119F3
0x1801118aa  lea     rax, aGetinputdevice; "GetInputDeviceHandlesError"
0x1801118b1  retn
0x1801118b2  lea     rax, aGraphicspipeli; "GraphicsPipelineRestartFailed"
0x1801118b9  retn
0x1801118ba  lea     rax, aGraphicssubsys; "GraphicsSubsystemInitFailed"
0x1801118c1  retn
0x1801118c2  lea     rax, aSidetransportl; "SideTransportListenerInternalError"
0x1801118c9  retn
0x1801118ca  lea     rax, aGraphicspipecl; "GraphicsPipeClientAckTimeout"
0x1801118d1  retn
0x1801118d2  lea     rax, aHttptransporti; "HttpTransportInvalidState"
0x1801118d9  retn
0x1801118da  lea     rax, aLocalsecuritya; "LocalSecurityAuthorityError"
0x1801118e1  retn
0x1801118e2  lea     rax, aInvalidauthtok; "InvalidAuthToken"
0x1801118e9  retn
0x1801118ea  lea     rax, aGraphicscapsno; "GraphicsCapsNotReceived"
0x1801118f1  retn
0x1801118f2  sub     ecx, 1175h
0x1801118f8  jz      short loc_18011194C
0x1801118fa  sub     ecx, 1
0x1801118fd  jz      short loc_180111944
0x1801118ff  sub     ecx, 1
0x180111902  jz      short loc_18011193C
0x180111904  sub     ecx, 12h
0x180111907  jz      short loc_180111934
0x180111909  sub     ecx, 2
0x18011190c  jz      short loc_18011192C
0x18011190e  sub     ecx, 1
0x180111911  jz      short loc_180111924
0x180111913  cmp     ecx, 6
0x180111916  jnz     loc_1801119F3
0x18011191c  lea     rax, aProtocoldecryp; "ProtocolDecryptFailed"
0x180111923  retn
0x180111924  lea     rax, aLogRdpUserdisc; "Log_RDP_UserDisconnectedBeforeLogon"
0x18011192b  retn
0x18011192c  lea     rax, aLogRdpSidetran; "Log_RDP_SideTransportPacketWriteToWinso"...
0x180111933  retn
0x180111934  lea     rax, aLogRdpSidetran_0; "Log_RDP_SideTransportWriteThreadHang"
0x18011193b  retn
0x18011193c  lea     rax, aSspisidetransp; "SSPISideTransportError"
0x180111943  retn
0x180111944  lea     rax, aSidetransportt; "SideTransportTurnServerShutdown"
0x18011194b  retn
0x18011194c  lea     rax, aCreateinputdev; "CreateInputDevicesErrorDeviceNotAvailab"...
0x180111953  retn
0x180111954  lea     rax, aRdpprotocolenc; "RDPProtocolEncryptFailed"
0x18011195b  retn
0x18011195c  mov     eax, 1266h
0x180111961  cmp     ecx, eax
0x180111963  ja      short loc_1801119CD
0x180111965  jz      short loc_1801119C5
0x180111967  sub     ecx, 11F5h
0x18011196d  jz      short loc_1801119BD
0x18011196f  sub     ecx, 1
0x180111972  jz      short loc_1801119B5
0x180111974  sub     ecx, 63h ; 'c'
0x180111977  jz      short loc_1801119AD
0x180111979  sub     ecx, 4
0x18011197c  jz      short loc_1801119A5
0x18011197e  sub     ecx, 2
0x180111981  jz      short loc_18011199D
0x180111983  sub     ecx, 2
0x180111986  jz      short loc_180111995
0x180111988  cmp     ecx, 1
0x18011198b  jnz     short loc_1801119F3
0x18011198d  lea     rax, aLogMultipathTr; "Log_Multipath_TransportShutdown"
0x180111994  retn
0x180111995  lea     rax, aLogMultipathRe; "Log_Multipath_RequestDenied"
0x18011199c  retn
0x18011199d  lea     rax, aLogMultipathIn_0; "Log_Multipath_InvalidRequest"
0x1801119a4  retn
0x1801119a5  lea     rax, aLogMultipathIn; "Log_Multipath_InvalidPacketBufferSize"
0x1801119ac  retn
0x1801119ad  lea     rax, aLogMultipathPr; "Log_Multipath_ProtocolInternalError"
0x1801119b4  retn
0x1801119b5  lea     rax, aLogRdpWcioDisp_0; "Log_RDP_WCIO_DisplayProtectionLicenseIs"...
0x1801119bc  retn
0x1801119bd  lea     rax, aLogRdpWcioDisp; "Log_RDP_WCIO_DisplayProtectionNotSuppor"...
0x1801119c4  retn
0x1801119c5  lea     rax, aLogMultipathSi; "Log_Multipath_SideTransportError"
0x1801119cc  retn
0x1801119cd  sub     ecx, 1282h
0x1801119d3  jz      short loc_180111A2B
0x1801119d5  sub     ecx, 1
0x1801119d8  jz      short loc_180111A23
0x1801119da  sub     ecx, 1
0x1801119dd  jz      short loc_180111A1B
0x1801119df  sub     ecx, 3
0x1801119e2  jz      short loc_180111A13
0x1801119e4  sub     ecx, 2
0x1801119e7  jz      short loc_180111A0B
0x1801119e9  sub     ecx, 1
0x1801119ec  jz      short loc_180111A03
0x1801119ee  cmp     ecx, 4
0x1801119f1  jz      short loc_1801119FB
0x1801119f3  lea     rax, aInternalprotoc; "InternalProtocolDisconnect"
0x1801119fa  retn
0x1801119fb  lea     rax, aLogMultipathWe; "Log_Multipath_Websocket_SideTransportEr"...
0x180111a02  retn
0x180111a03  lea     rax, aLogMultipathWe_0; "Log_Multipath_Websocket_TransportShutdo"...
0x180111a0a  retn
0x180111a0b  lea     rax, aLogMultipathWe_3; "Log_Multipath_Websocket_RequestDenied"
0x180111a12  retn
0x180111a13  lea     rax, aLogMultipathWe_5; "Log_Multipath_Websocket_InvalidRequest"
0x180111a1a  retn
0x180111a1b  lea     rax, aLogMultipathWe_2; "Log_Multipath_Websocket_ResponseError"
0x180111a22  retn
0x180111a23  lea     rax, aLogMultipathWe_1; "Log_Multipath_Websocket_ServerError"
0x180111a2a  retn
0x180111a2b  lea     rax, aLogMultipathWe_4; "Log_Multipath_Websocket_GenericError"
0x180111a32  retn
```
