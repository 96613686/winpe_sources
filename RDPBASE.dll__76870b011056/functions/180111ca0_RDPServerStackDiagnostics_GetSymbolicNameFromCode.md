# RDPServerStackDiagnostics_GetSymbolicNameFromCode

- ea: `0x180111ca0`
- end: `0x180112407`
- name: `RDPServerStackDiagnostics_GetSymbolicNameFromCode`
- size: `1895`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180112670`
- `0x180112740`

## callees

- `0x1801115a8`
- `0x18011165c`
- `0x180111ca0`

## string_xrefs

- `0x180112231`: `SideTransportTurnServerShutdown`
- `0x180111d23`: `RailReadyTimeout`
- `0x180111d80`: `InsufficientUserPrivileges`
- `0x180111e1c`: `BrokeringFailure`
- `0x180111f08`: `LicenseStoreAccessDeniedOnClient`
- `0x1801120d2`: `BrokeringFailureInvalidSettings`
- `0x180112167`: `MultipathTransportNetworkDrop`
- `0x18011210e`: `MultipathTransportGracefulCloseByPeer`
- `0x1801122a5`: `MultipathTransportWritePostIncomplete`
- `0x180112299`: `MultipathTransportWriteThreadHang`
- `0x18011215b`: `MultipathTransportReliabilityThresholdFailure`
- `0x1801122e1`: `MultipathTransportWriteToWinsockFailed`
- `0x1801121d8`: `MultipathTransportAuthenticationFailure`
- `0x1801121e4`: `MultipathTransportReceivedCorruptedPacket`
- `0x1801121cc`: `MultipathTransportResourcesExhausted`
- `0x1801121a8`: `MultipathTransportGracefulCloseFailure`
- `0x1801121b4`: `UnsupportedSecurityFunction`
- `0x18011223d`: `TokenLogonFailed`
- `0x180112225`: `MultipathTransportNetworkDropNotConnected`
- `0x18011232e`: `MultipathTransportNetworkOperationBlocked`
- `0x180112255`: `MultipathTransportRemoteUnreachable`
- `0x180112219`: `MultipathTransportResponseTimeout`
- `0x1801122c9`: `MultipathTransportConnectionRemoteReset`
- `0x1801122d5`: `MultipathTransportConnectionCancelled`
- `0x18011239e`: `MultipathWebsocketTransportNetworkOperationBlocked`
- `0x1801122bd`: `MultipathWebsocketTransportNetworkDropOnPeerLeg`
- `0x180112316`: `MultipathWebsocketTransportResponseTimeout`
- `0x180112322`: `MultipathWebsocketTransportNetworkDropNotConnected`
- `0x180112346`: `MultipathWebsocketTransportConnectionCancelled`
- `0x18011230a`: `MultipathWebsocketTransportRemoteUnreachable`
- `0x180112395`: `MultipathWebsocketReceivedCorruptedPacket`
- `0x1801123a7`: `MultipathWebsocketTransportConnectionRemoteReset`
- `0x18011238c`: `MultipathWebsocketTransportDeniedByWebProxy`

## pseudocode

```c
const char *__fastcall RDPServerStackDiagnostics_GetSymbolicNameFromCode(int a1, unsigned int a2)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  const char *result; // rax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  int v59; // ecx
  int v60; // ecx
  int v61; // ecx
  int v62; // ecx
  int v63; // ecx
  int v64; // ecx
  int v65; // ecx
  int v66; // ecx
  int v67; // ecx
  int v68; // ecx
  int v69; // ecx
  int v70; // ecx
  int v71; // ecx
  int v72; // ecx
  int v73; // ecx
  int v74; // ecx

  if ( a1 > 59 )
  {
    if ( a1 <= 87 )
    {
      if ( a1 == 87 )
        return "MultipathTransportRemoteUnreachable";
      if ( a1 > 73 )
      {
        if ( a1 > 80 )
        {
          v53 = a1 - 81;
          if ( !v53 )
            return "AuthenticationFailed";
          v54 = v53 - 1;
          if ( !v54 )
            return "TokenLogonFailed";
          v55 = v54 - 2;
          if ( !v55 )
            return "SideTransportTurnServerShutdown";
          v56 = v55 - 1;
          if ( !v56 )
            return "MultipathTransportNetworkDropNotConnected";
          if ( v56 == 1 )
            return "MultipathTransportResponseTimeout";
        }
        else
        {
          if ( a1 == 80 )
            return "UserAccountExpired";
          v48 = a1 - 74;
          if ( !v48 )
            return "MultipathTransportReceivedCorruptedPacket";
          v49 = v48 - 1;
          if ( !v49 )
            return "MultipathTransportAuthenticationFailure";
          v50 = v49 - 1;
          if ( !v50 )
            return "MultipathTransportResourcesExhausted";
          v51 = v50 - 1;
          if ( !v51 )
            return "LockedSession";
          v52 = v51 - 1;
          if ( !v52 )
            return "UnsupportedSecurityFunction";
          if ( v52 == 1 )
            return "MultipathTransportGracefulCloseFailure";
        }
      }
      else
      {
        if ( a1 == 73 )
          return "ErrorHandlingConnectionInTermSrv";
        if ( a1 > 67 )
        {
          v44 = a1 - 68;
          if ( !v44 )
            return "MultipathTransportNetworkDrop";
          v45 = v44 - 1;
          if ( !v45 )
            return "MultipathTransportReliabilityThresholdFailure";
          v46 = v45 - 1;
          if ( !v46 )
            return "NotAuthorizedForLogonWrongUser";
          v47 = v46 - 1;
          if ( !v47 )
            return "WatermarkingNotSupportedByClient";
          if ( v47 == 1 )
            return "ReverseConnectDeniedByWebProxy";
        }
        else
        {
          if ( a1 == 67 )
            return "MultipathTransportGracefulCloseByPeer";
          v39 = a1 - 60;
          if ( !v39 )
            return "ConnectionInitiationSequenceTimeout";
          v40 = v39 - 1;
          if ( !v40 )
            return "ScreenCaptureProtectionNotSupportedByClient";
          v41 = v40 - 1;
          if ( !v41 )
            return "ServerShutdown";
          v42 = v41 - 1;
          if ( !v42 )
            return "ServerReboot";
          v43 = v42 - 2;
          if ( !v43 )
            return "BrokeringFailureInvalidSettings";
          if ( v43 == 1 )
            return "ReverseConnectGracefulCloseByPeer";
        }
      }
      return "Unknown";
    }
    if ( a1 <= 105 )
    {
      if ( a1 == 105 )
        return "MultipathWebsocketTransportConnectionCancelled";
      if ( a1 > 97 )
      {
        v62 = a1 - 98;
        if ( !v62 )
          return "UserDisconnectedBeforeLogon";
        v63 = v62 - 3;
        if ( !v63 )
          return "MultipathTransportNetworkOperationBlocked";
        v64 = v63 - 1;
        if ( !v64 )
          return "MultipathWebsocketTransportNetworkDropNotConnected";
        v65 = v64 - 1;
        if ( !v65 )
          return "MultipathWebsocketTransportResponseTimeout";
        if ( v65 == 1 )
          return "MultipathWebsocketTransportRemoteUnreachable";
      }
      else
      {
        if ( a1 == 97 )
          return "MultipathTransportWriteToWinsockFailed";
        v57 = a1 - 88;
        if ( !v57 )
          return "MultipathTransportConnectionCancelled";
        v58 = v57 - 1;
        if ( !v58 )
          return "MultipathTransportConnectionRemoteReset";
        v59 = v58 - 1;
        if ( !v59 )
          return "MultipathWebsocketTransportNetworkDropOnPeerLeg";
        v60 = v59 - 1;
        if ( !v60 )
          return "LogonTypeNotGranted";
        v61 = v60 - 4;
        if ( !v61 )
          return "MultipathTransportWritePostIncomplete";
        if ( v61 == 1 )
          return "MultipathTransportWriteThreadHang";
      }
      return "Unknown";
    }
    if ( a1 <= 116 )
    {
      if ( a1 == 116 )
        return "DirectStreamGeneralError";
      v66 = a1 - 106;
      if ( !v66 )
        return "MultipathWebsocketTransportConnectionRemoteReset";
      v67 = v66 - 1;
      if ( !v67 )
        return "MultipathWebsocketTransportNetworkOperationBlocked";
      v68 = v67 - 1;
      if ( !v68 )
        return "MultipathWebsocketReceivedCorruptedPacket";
      v69 = v68 - 1;
      if ( !v69 )
        return "MultipathWebsocketTransportDeniedByWebProxy";
      v70 = v69 - 5;
      if ( !v70 )
        return "DirectStreamConnectionCanceledOnTimeout";
      if ( v70 == 1 )
        return "DirectStreamConnectionTimeoutAfterAttach";
      return "Unknown";
    }
    v71 = a1 - 117;
    if ( v71 )
    {
      v72 = v71 - 1;
      if ( v72 )
      {
        v73 = v72 - 1;
        if ( v73 )
        {
          v74 = v73 - 1;
          if ( v74 )
          {
            if ( v74 != 1 )
              return "Unknown";
            return "DirectStreamExceededMaxCallLifetime";
          }
          else
          {
            return "DirectStreamMediaError";
          }
        }
        else
        {
          return "DirectStreamConnectionMediaError";
        }
      }
      else
      {
        return "DirectStreamGeneralMediaError";
      }
    }
    else
    {
      return "DirectStreamConnectionTimeout";
    }
  }
  else
  {
    if ( a1 == 59 )
      return "NoLogonServers";
    if ( a1 > 33 )
    {
      if ( a1 > 46 )
      {
        if ( a1 > 53 )
        {
          v35 = a1 - 54;
          if ( !v35 )
            return "UserAccountLocked";
          v36 = v35 - 1;
          if ( !v36 )
            return "UserAccountInvalidLogonHours";
          v37 = v36 - 1;
          if ( !v37 )
            return "NotAuthorizedForWorkstation";
          v38 = v37 - 1;
          if ( !v38 )
            return "ReverseConnectReceivedCorruptedPacket";
          if ( v38 == 1 )
            return "ReverseConnectResponseTimeout";
        }
        else
        {
          if ( a1 == 53 )
            return "UserAccountDisabled";
          v30 = a1 - 47;
          if ( !v30 )
            return "AutoReconnectCookieExpired";
          v31 = v30 - 1;
          if ( !v31 )
            return "AutoReconnectCookieMismatched";
          v32 = v31 - 1;
          if ( !v32 )
            return "AutoReconnectNoCookie";
          v33 = v32 - 1;
          if ( !v33 )
            return "AutoReconnectCookieInvalid";
          v34 = v33 - 1;
          if ( !v34 )
            return "AutoReconnectLogonFailure";
          if ( v34 == 1 )
            return "SpecifiedLogonSessionDoesNotExist";
        }
      }
      else
      {
        if ( a1 == 46 )
          return "ReverseConnectConnectionCancelled";
        if ( a1 > 40 )
        {
          v26 = a1 - 41;
          if ( !v26 )
            return "ReverseConnectInvalidCertificate";
          v27 = v26 - 1;
          if ( !v27 )
            return "ReverseConnectSChannelFailure";
          v28 = v27 - 1;
          if ( !v28 )
            return "ReverseConnectGatewayUnreacheable";
          v29 = v28 - 1;
          if ( !v29 )
            return "ReverseConnectRefused";
          if ( v29 == 1 )
            return "ReverseConnectClosedByGateway";
        }
        else
        {
          if ( a1 == 40 )
            return "ReverseConnectTimeout";
          v21 = a1 - 34;
          if ( !v21 )
            return "UserLogoff";
          v22 = v21 - 1;
          if ( !v22 )
            return "CantUpgradeLicense";
          v23 = v22 - 1;
          if ( !v23 )
            return "LicenseStoreAccessDeniedOnClient";
          v24 = v23 - 1;
          if ( !v24 )
            return "ServerAdminInitiatedDisconnect";
          v25 = v24 - 1;
          if ( !v25 )
            return "AutoReconnectEnforced";
          if ( v25 == 1 )
            return "ReverseConnectDnsLookupFailed";
        }
      }
      return "Unknown";
    }
    if ( a1 == 33 )
      return "RedirectedCredentialsFailure";
    if ( a1 > 20 )
    {
      if ( a1 > 27 )
      {
        v17 = a1 - 28;
        if ( !v17 )
          return "NoLicenseServer";
        v18 = v17 - 1;
        if ( !v18 )
          return "NoConnectionLicense";
        v19 = v18 - 1;
        if ( !v19 )
          return "InvalidLicense";
        v20 = v19 - 1;
        if ( !v20 )
          return "LicenseProcessingFailure";
        if ( v20 == 1 )
          return "OutOfMemory";
      }
      else
      {
        if ( a1 == 27 )
          return GetInternalProtocolDisconnectSymbolicName(a2);
        v12 = a1 - 21;
        if ( !v12 )
          return "LogonTimeout";
        v13 = v12 - 1;
        if ( !v13 )
          return "UserInitiatedDisconnect";
        v14 = v13 - 1;
        if ( !v14 )
          return "BrokeringFailure";
        v15 = v14 - 1;
        if ( !v15 )
          return "ReverseConnectFailed";
        v16 = v15 - 1;
        if ( !v16 )
          return "IdleTimeout";
        if ( v16 == 1 )
          return GetInternalDisconnectSymbolicName(a2);
      }
      return "Unknown";
    }
    if ( a1 == 20 )
      return "SavedCredentialsNotAllowed";
    if ( a1 > 13 )
    {
      v7 = a1 - 14;
      if ( !v7 )
        return "UnexpectedNetworkDisconnect";
      v8 = v7 - 1;
      if ( !v8 )
        return "ClientInitiatedDisconnect";
      v9 = v8 - 1;
      if ( !v9 )
        return "LogoffByOtherConnection";
      v10 = v9 - 1;
      if ( !v10 )
        return "ConnectionDeniedByServer";
      v11 = v10 - 1;
      if ( !v11 )
        return "FipsNotSupportedOnServer";
      if ( v11 == 1 )
        return "InsufficientUserPrivileges";
      return "Unknown";
    }
    if ( a1 == 13 )
      return "NoLicense";
    if ( !a1 )
      return "Success";
    v2 = a1 - 1;
    if ( !v2 )
      return "Unspecified";
    v3 = v2 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( !v4 )
        return "InvalidCredentials";
      v5 = v4 - 1;
      if ( !v5 )
        return "PasswordExpired";
      if ( v5 == 8 )
        return "NotAuthorizedForLogon";
      return "Unknown";
    }
    result = "HRESULT";
    if ( a2 == 1280 )
      return "RailReadyTimeout";
  }
  return result;
}

```

## disassembly

```asm
0x180111ca0  cmp     ecx, 3Bh ; ';'
0x180111ca3  jg      loc_18011207F
0x180111ca9  jz      loc_180112073
0x180111caf  cmp     ecx, 21h ; '!'
0x180111cb2  jg      loc_180111EAC
0x180111cb8  jz      loc_180111EA0
0x180111cbe  cmp     ecx, 14h
0x180111cc1  jg      loc_180111DD4
0x180111cc7  jz      loc_180111DC8
0x180111ccd  cmp     ecx, 0Dh
0x180111cd0  jg      loc_180111D5E
0x180111cd6  jz      short loc_180111D52
0x180111cd8  test    ecx, ecx
0x180111cda  jz      short loc_180111D46
0x180111cdc  sub     ecx, 1
0x180111cdf  jz      short loc_180111D3A
0x180111ce1  sub     ecx, 1
0x180111ce4  jz      short loc_180111D1D
0x180111ce6  sub     ecx, 1
0x180111ce9  jz      short loc_180111D11
0x180111ceb  sub     ecx, 1
0x180111cee  jz      short loc_180111D05
0x180111cf0  cmp     ecx, 8
0x180111cf3  jnz     loc_1801123D2
0x180111cf9  lea     rax, aNotauthorizedf_0; "NotAuthorizedForLogon"
0x180111d00  jmp     locret_180112406
0x180111d05  lea     rax, aPasswordexpire; "PasswordExpired"
0x180111d0c  jmp     locret_180112406
0x180111d11  lea     rax, aInvalidcredent; "InvalidCredentials"
0x180111d18  jmp     locret_180112406
0x180111d1d  cmp     edx, 500h
0x180111d23  lea     rcx, aRailreadytimeo; "RailReadyTimeout"
0x180111d2a  lea     rax, aHresult; "HRESULT"
0x180111d31  cmovz   rax, rcx
0x180111d35  jmp     locret_180112406
0x180111d3a  lea     rax, aUnspecified; "Unspecified"
0x180111d41  jmp     locret_180112406
0x180111d46  lea     rax, aSuccess_0; "Success"
0x180111d4d  jmp     locret_180112406
0x180111d52  lea     rax, aNolicense; "NoLicense"
0x180111d59  jmp     locret_180112406
0x180111d5e  sub     ecx, 0Eh
0x180111d61  jz      short loc_180111DBC
0x180111d63  sub     ecx, 1
0x180111d66  jz      short loc_180111DB0
0x180111d68  sub     ecx, 1
0x180111d6b  jz      short loc_180111DA4
0x180111d6d  sub     ecx, 1
0x180111d70  jz      short loc_180111D98
0x180111d72  sub     ecx, 1
0x180111d75  jz      short loc_180111D8C
0x180111d77  cmp     ecx, 1
0x180111d7a  jnz     loc_1801123D2
0x180111d80  lea     rax, aInsufficientus; "InsufficientUserPrivileges"
0x180111d87  jmp     locret_180112406
0x180111d8c  lea     rax, aFipsnotsupport; "FipsNotSupportedOnServer"
0x180111d93  jmp     locret_180112406
0x180111d98  lea     rax, aConnectiondeni; "ConnectionDeniedByServer"
0x180111d9f  jmp     locret_180112406
0x180111da4  lea     rax, aLogoffbyotherc; "LogoffByOtherConnection"
0x180111dab  jmp     locret_180112406
0x180111db0  lea     rax, aClientinitiate; "ClientInitiatedDisconnect"
0x180111db7  jmp     locret_180112406
0x180111dbc  lea     rax, aUnexpectednetw; "UnexpectedNetworkDisconnect"
0x180111dc3  jmp     locret_180112406
0x180111dc8  lea     rax, aSavedcredentia; "SavedCredentialsNotAllowed"
0x180111dcf  jmp     locret_180112406
0x180111dd4  cmp     ecx, 1Bh
0x180111dd7  jg      short loc_180111E47
0x180111dd9  jz      short loc_180111E40
0x180111ddb  sub     ecx, 15h
0x180111dde  jz      short loc_180111E34
0x180111de0  sub     ecx, 1
0x180111de3  jz      short loc_180111E28
0x180111de5  sub     ecx, 1
0x180111de8  jz      short loc_180111E1C
0x180111dea  sub     ecx, 1
0x180111ded  jz      short loc_180111E10
0x180111def  sub     ecx, 1
0x180111df2  jz      short loc_180111E04
0x180111df4  cmp     ecx, 1
0x180111df7  jnz     loc_1801123D2
0x180111dfd  mov     ecx, edx; unsigned int
0x180111dff  jmp     ?GetInternalDisconnectSymbolicName@@YAPEBDI@Z; GetInternalDisconnectSymbolicName(uint)
0x180111e04  lea     rax, aIdletimeout; "IdleTimeout"
0x180111e0b  jmp     locret_180112406
0x180111e10  lea     rax, aReverseconnect_4; "ReverseConnectFailed"
0x180111e17  jmp     locret_180112406
0x180111e1c  lea     rax, aBrokeringfailu_0; "BrokeringFailure"
0x180111e23  jmp     locret_180112406
0x180111e28  lea     rax, aUserinitiatedd; "UserInitiatedDisconnect"
0x180111e2f  jmp     locret_180112406
0x180111e34  lea     rax, aLogontimeout; "LogonTimeout"
0x180111e3b  jmp     locret_180112406
0x180111e40  mov     ecx, edx; unsigned int
0x180111e42  jmp     ?GetInternalProtocolDisconnectSymbolicName@@YAPEBDI@Z; GetInternalProtocolDisconnectSymbolicName(uint)
0x180111e47  sub     ecx, 1Ch
0x180111e4a  jz      short loc_180111E94
0x180111e4c  sub     ecx, 1
0x180111e4f  jz      short loc_180111E88
0x180111e51  sub     ecx, 1
0x180111e54  jz      short loc_180111E7C
0x180111e56  sub     ecx, 1
0x180111e59  jz      short loc_180111E70
0x180111e5b  cmp     ecx, 1
0x180111e5e  jnz     loc_1801123D2
0x180111e64  lea     rax, aOutofmemory; "OutOfMemory"
0x180111e6b  jmp     locret_180112406
0x180111e70  lea     rax, aLicenseprocess; "LicenseProcessingFailure"
0x180111e77  jmp     locret_180112406
0x180111e7c  lea     rax, aInvalidlicense; "InvalidLicense"
0x180111e83  jmp     locret_180112406
0x180111e88  lea     rax, aNoconnectionli; "NoConnectionLicense"
0x180111e8f  jmp     locret_180112406
0x180111e94  lea     rax, aNolicenseserve; "NoLicenseServer"
0x180111e9b  jmp     locret_180112406
0x180111ea0  lea     rax, aRedirectedcred; "RedirectedCredentialsFailure"
0x180111ea7  jmp     locret_180112406
0x180111eac  cmp     ecx, 2Eh ; '.'
0x180111eaf  jg      loc_180111F9D
0x180111eb5  jz      loc_180111F91
0x180111ebb  cmp     ecx, 28h ; '('
0x180111ebe  jg      short loc_180111F38
0x180111ec0  jz      short loc_180111F2C
0x180111ec2  sub     ecx, 22h ; '"'
0x180111ec5  jz      short loc_180111F20
0x180111ec7  sub     ecx, 1
0x180111eca  jz      short loc_180111F14
0x180111ecc  sub     ecx, 1
0x180111ecf  jz      short loc_180111F08
0x180111ed1  sub     ecx, 1
0x180111ed4  jz      short loc_180111EFC
0x180111ed6  sub     ecx, 1
0x180111ed9  jz      short loc_180111EF0
0x180111edb  cmp     ecx, 1
0x180111ede  jnz     loc_1801123D2
0x180111ee4  lea     rax, aReverseconnect; "ReverseConnectDnsLookupFailed"
0x180111eeb  jmp     locret_180112406
0x180111ef0  lea     rax, aAutoreconnecte; "AutoReconnectEnforced"
0x180111ef7  jmp     locret_180112406
0x180111efc  lea     rax, aServeradminini; "ServerAdminInitiatedDisconnect"
0x180111f03  jmp     locret_180112406
0x180111f08  lea     rax, aLicensestoreac; "LicenseStoreAccessDeniedOnClient"
0x180111f0f  jmp     locret_180112406
0x180111f14  lea     rax, aCantupgradelic; "CantUpgradeLicense"
0x180111f1b  jmp     locret_180112406
0x180111f20  lea     rax, aUserlogoff; "UserLogoff"
0x180111f27  jmp     locret_180112406
0x180111f2c  lea     rax, aReverseconnect_1; "ReverseConnectTimeout"
0x180111f33  jmp     locret_180112406
0x180111f38  sub     ecx, 29h ; ')'
0x180111f3b  jz      short loc_180111F85
0x180111f3d  sub     ecx, 1
0x180111f40  jz      short loc_180111F79
0x180111f42  sub     ecx, 1
0x180111f45  jz      short loc_180111F6D
0x180111f47  sub     ecx, 1
0x180111f4a  jz      short loc_180111F61
0x180111f4c  cmp     ecx, 1
0x180111f4f  jnz     loc_1801123D2
0x180111f55  lea     rax, aReverseconnect_6; "ReverseConnectClosedByGateway"
0x180111f5c  jmp     locret_180112406
0x180111f61  lea     rax, aReverseconnect_2; "ReverseConnectRefused"
0x180111f68  jmp     locret_180112406
0x180111f6d  lea     rax, aReverseconnect_3; "ReverseConnectGatewayUnreacheable"
0x180111f74  jmp     locret_180112406
0x180111f79  lea     rax, aReverseconnect_7; "ReverseConnectSChannelFailure"
0x180111f80  jmp     locret_180112406
0x180111f85  lea     rax, aReverseconnect_8; "ReverseConnectInvalidCertificate"
0x180111f8c  jmp     locret_180112406
0x180111f91  lea     rax, aReverseconnect_9; "ReverseConnectConnectionCancelled"
0x180111f98  jmp     locret_180112406
0x180111f9d  cmp     ecx, 35h ; '5'
0x180111fa0  jg      short loc_18011201A
0x180111fa2  jz      short loc_18011200E
0x180111fa4  sub     ecx, 2Fh ; '/'
0x180111fa7  jz      short loc_180112002
0x180111fa9  sub     ecx, 1
0x180111fac  jz      short loc_180111FF6
0x180111fae  sub     ecx, 1
0x180111fb1  jz      short loc_180111FEA
0x180111fb3  sub     ecx, 1
0x180111fb6  jz      short loc_180111FDE
0x180111fb8  sub     ecx, 1
0x180111fbb  jz      short loc_180111FD2
0x180111fbd  cmp     ecx, 1
0x180111fc0  jnz     loc_1801123D2
0x180111fc6  lea     rax, aSpecifiedlogon; "SpecifiedLogonSessionDoesNotExist"
0x180111fcd  jmp     locret_180112406
0x180111fd2  lea     rax, aAutoreconnectl; "AutoReconnectLogonFailure"
0x180111fd9  jmp     locret_180112406
0x180111fde  lea     rax, aAutoreconnectc_0; "AutoReconnectCookieInvalid"
0x180111fe5  jmp     locret_180112406
0x180111fea  lea     rax, aAutoreconnectn; "AutoReconnectNoCookie"
0x180111ff1  jmp     locret_180112406
0x180111ff6  lea     rax, aAutoreconnectc_1; "AutoReconnectCookieMismatched"
0x180111ffd  jmp     locret_180112406
0x180112002  lea     rax, aAutoreconnectc; "AutoReconnectCookieExpired"
0x180112009  jmp     locret_180112406
0x18011200e  lea     rax, aUseraccountdis; "UserAccountDisabled"
0x180112015  jmp     locret_180112406
0x18011201a  sub     ecx, 36h ; '6'
0x18011201d  jz      short loc_180112067
0x18011201f  sub     ecx, 1
0x180112022  jz      short loc_18011205B
0x180112024  sub     ecx, 1
0x180112027  jz      short loc_18011204F
0x180112029  sub     ecx, 1
0x18011202c  jz      short loc_180112043
0x18011202e  cmp     ecx, 1
0x180112031  jnz     loc_1801123D2
0x180112037  lea     rax, aReverseconnect_5; "ReverseConnectResponseTimeout"
0x18011203e  jmp     locret_180112406
0x180112043  lea     rax, aReverseconnect_12; "ReverseConnectReceivedCorruptedPacket"
0x18011204a  jmp     locret_180112406
0x18011204f  lea     rax, aNotauthorizedf; "NotAuthorizedForWorkstation"
0x180112056  jmp     locret_180112406
0x18011205b  lea     rax, aUseraccountinv; "UserAccountInvalidLogonHours"
0x180112062  jmp     locret_180112406
0x180112067  lea     rax, aUseraccountloc; "UserAccountLocked"
0x18011206e  jmp     locret_180112406
0x180112073  lea     rax, aNologonservers; "NoLogonServers"
0x18011207a  jmp     locret_180112406
0x18011207f  cmp     ecx, 57h ; 'W'
0x180112082  jg      loc_180112261
0x180112088  jz      loc_180112255
0x18011208e  cmp     ecx, 49h ; 'I'
0x180112091  jg      loc_18011217F
0x180112097  jz      loc_180112173
0x18011209d  cmp     ecx, 43h ; 'C'
0x1801120a0  jg      short loc_18011211A
0x1801120a2  jz      short loc_18011210E
0x1801120a4  sub     ecx, 3Ch ; '<'
0x1801120a7  jz      short loc_180112102
0x1801120a9  sub     ecx, 1
0x1801120ac  jz      short loc_1801120F6
0x1801120ae  sub     ecx, 1
0x1801120b1  jz      short loc_1801120EA
0x1801120b3  sub     ecx, 1
0x1801120b6  jz      short loc_1801120DE
0x1801120b8  sub     ecx, 2
0x1801120bb  jz      short loc_1801120D2
0x1801120bd  cmp     ecx, 1
0x1801120c0  jnz     loc_1801123D2
0x1801120c6  lea     rax, aReverseconnect_10; "ReverseConnectGracefulCloseByPeer"
0x1801120cd  jmp     locret_180112406
0x1801120d2  lea     rax, aBrokeringfailu; "BrokeringFailureInvalidSettings"
0x1801120d9  jmp     locret_180112406
0x1801120de  lea     rax, aServerreboot; "ServerReboot"
0x1801120e5  jmp     locret_180112406
0x1801120ea  lea     rax, aServershutdown; "ServerShutdown"
0x1801120f1  jmp     locret_180112406
0x1801120f6  lea     rax, aScreencapturep; "ScreenCaptureProtectionNotSupportedByCl"...
0x1801120fd  jmp     locret_180112406
0x180112102  lea     rax, aConnectioninit; "ConnectionInitiationSequenceTimeout"
0x180112109  jmp     locret_180112406
0x18011210e  lea     rax, aMultipathtrans_3; "MultipathTransportGracefulCloseByPeer"
0x180112115  jmp     locret_180112406
0x18011211a  sub     ecx, 44h ; 'D'
0x18011211d  jz      short loc_180112167
0x18011211f  sub     ecx, 1
0x180112122  jz      short loc_18011215B
0x180112124  sub     ecx, 1
0x180112127  jz      short loc_18011214F
0x180112129  sub     ecx, 1
0x18011212c  jz      short loc_180112143
0x18011212e  cmp     ecx, 1
0x180112131  jnz     loc_1801123D2
0x180112137  lea     rax, aReverseconnect_0; "ReverseConnectDeniedByWebProxy"
0x18011213e  jmp     locret_180112406
0x180112143  lea     rax, aWatermarkingno; "WatermarkingNotSupportedByClient"
0x18011214a  jmp     locret_180112406
0x18011214f  lea     rax, aNotauthorizedf_1; "NotAuthorizedForLogonWrongUser"
0x180112156  jmp     locret_180112406
0x18011215b  lea     rax, aMultipathtrans_6; "MultipathTransportReliabilityThresholdF"...
0x180112162  jmp     locret_180112406
0x180112167  lea     rax, aMultipathtrans_1; "MultipathTransportNetworkDrop"
0x18011216e  jmp     locret_180112406
0x180112173  lea     rax, aErrorhandlingc; "ErrorHandlingConnectionInTermSrv"
0x18011217a  jmp     locret_180112406
0x18011217f  cmp     ecx, 50h ; 'P'
0x180112182  jg      short loc_1801121FC
0x180112184  jz      short loc_1801121F0
0x180112186  sub     ecx, 4Ah ; 'J'
0x180112189  jz      short loc_1801121E4
0x18011218b  sub     ecx, 1
0x18011218e  jz      short loc_1801121D8
0x180112190  sub     ecx, 1
0x180112193  jz      short loc_1801121CC
0x180112195  sub     ecx, 1
0x180112198  jz      short loc_1801121C0
0x18011219a  sub     ecx, 1
0x18011219d  jz      short loc_1801121B4
0x18011219f  cmp     ecx, 1
0x1801121a2  jnz     loc_1801123D2
0x1801121a8  lea     rax, aMultipathtrans_7; "MultipathTransportGracefulCloseFailure"
0x1801121af  jmp     locret_180112406
0x1801121b4  lea     rax, aUnsupportedsec; "UnsupportedSecurityFunction"
0x1801121bb  jmp     locret_180112406
0x1801121c0  lea     rax, aLockedsession; "LockedSession"
  ... truncated ...
```
