# NetrUseGetInfo

- ea: `0x180003b70`
- end: `0x180004a36`
- name: `NetrUseGetInfo`
- size: `3782`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800024f0`
- `0x180003b70`
- `0x180004a40`
- `0x1800051c0`
- `0x1800054d0`
- `0x180009ef0`
- `0x18001e420`
- `0x18001ed46`
- `0x18002ecc0`
- `0x18002ed4c`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180003cbe`
- `ntdll!RtlAcquireResourceShared` at `0x180003cbe`
- `ntdll!RtlCopyLuid` at `0x180003e96`
- `ntdll!RtlCopyLuid` at `0x18000411d`
- `ntdll!RtlCopyLuid` at `0x18000417e`
- `ntdll!RtlCopyLuid` at `0x180003e96`
- `ntdll!RtlCopyLuid` at `0x18000411d`
- `ntdll!RtlCopyLuid` at `0x18000417e`
- `ntdll!NtOpenThreadToken` at `0x180003c6f`
- `ntdll!NtOpenThreadToken` at `0x180003c6f`
- `ntdll!RtlNtStatusToDosError` at `0x1800044ab`
- `ntdll!RtlNtStatusToDosError` at `0x180004642`
- `ntdll!RtlNtStatusToDosError` at `0x1800044ab`
- `ntdll!RtlNtStatusToDosError` at `0x180004642`
- `ntdll!NtClose` at `0x180004127`
- `ntdll!NtClose` at `0x180004312`
- `ntdll!NtClose` at `0x180004127`
- `ntdll!NtClose` at `0x180004312`
- `ntdll!RtlReleaseResource` at `0x180003e4e`
- `ntdll!RtlReleaseResource` at `0x18000406f`
- `ntdll!RtlReleaseResource` at `0x180003e4e`
- `ntdll!RtlReleaseResource` at `0x18000406f`
- `ntdll!RtlCompareUnicodeString` at `0x180003daa`
- `ntdll!RtlCompareUnicodeString` at `0x180003daa`
- `ntdll!NtQueryInformationToken` at `0x1800040f8`
- `ntdll!NtQueryInformationToken` at `0x1800040f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003be2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003f94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003be2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003f94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004059`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004081`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004229`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000432d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004764`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004059`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004081`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004229`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000432d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004764`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047bb`
- `RPCRT4!RpcImpersonateClient` at `0x180003c4e`
- `RPCRT4!RpcImpersonateClient` at `0x180003c4e`
- `RPCRT4!RpcRevertToSelf` at `0x180003c91`
- `RPCRT4!RpcRevertToSelf` at `0x180003c91`
- `netutils!NetpwPathCanonicalize` at `0x180003c11`
- `netutils!NetpwPathCanonicalize` at `0x180003c11`

## pseudocode

```c
DWORD __fastcall NetrUseGetInfo(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  __int64 *v4; // r14
  unsigned int v5; // r12d
  int Info; // ebx
  bool v8; // r13
  _WORD *v9; // rdi
  RPC_STATUS v10; // eax
  int v11; // r8d
  int v12; // eax
  int v13; // esi
  RPC_STATUS v14; // eax
  int v15; // r8d
  char *v16; // r15
  unsigned int v17; // edx
  __int64 LowPart; // r8
  __int64 **v19; // rax
  unsigned __int8 v20; // si
  _WORD *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  HANDLE v24; // rsi
  DWORD v25; // ebx
  int v26; // eax
  _WORD *v27; // rsi
  unsigned int v28; // edx
  unsigned int v29; // ecx
  int v30; // r8d
  int v31; // ecx
  int v32; // ecx
  SIZE_T v33; // rdx
  __int64 v34; // rbx
  char *v35; // rax
  __int16 v36; // cx
  unsigned int v37; // ecx
  int InformationToken; // eax
  int v40; // esi
  __int64 v41; // r14
  char *v42; // rax
  void *v43; // r15
  unsigned int v44; // r12d
  char *v45; // r13
  char *v46; // rcx
  bool v47; // zf
  int v48; // eax
  ULONG v49; // eax
  ULONG v50; // eax
  __int64 v51; // rdx
  char v52; // [rsp+90h] [rbp-80h]
  ULONG ReturnLength[2]; // [rsp+98h] [rbp-78h] BYREF
  void *TokenHandle[2]; // [rsp+A0h] [rbp-70h] BYREF
  struct _LUID SourceLuid; // [rsp+B0h] [rbp-60h] BYREF
  UNICODE_STRING String2; // [rsp+B8h] [rbp-58h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp-48h] BYREF
  int v58; // [rsp+D0h] [rbp-40h] BYREF
  unsigned int v59; // [rsp+D4h] [rbp-3Ch]
  _QWORD *v60; // [rsp+D8h] [rbp-38h]
  _DWORD v61[2]; // [rsp+E0h] [rbp-30h] BYREF
  struct _LUID v62[2]; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v63; // [rsp+F8h] [rbp-18h]
  int v64; // [rsp+100h] [rbp-10h]
  struct _LUID DestinationLuid[7]; // [rsp+108h] [rbp-8h] BYREF

  v4 = 0;
  v5 = (unsigned __int16)a3;
  v60 = a4;
  Info = a3 & 0x10000;
  v59 = (unsigned __int16)a3;
  SourceLuid = 0;
  v8 = (a3 & 0x10000) != 0;
  Handle = 0;
  v52 = v8;
  v58 = 0;
  *a4 = 0;
  if ( (unsigned __int16)a3 > 5u )
    return 124;
  v9 = LocalAlloc(0x40u, 0x20Au);
  if ( !v9 )
    return GetLastError();
  if ( (unsigned int)NetpwPathCanonicalize(a2, v9, 522, 0, &v58, 0) )
  {
    LocalFree(v9);
    return 2250;
  }
  if ( Info )
  {
    v16 = 0;
    *(_QWORD *)ReturnLength = 0;
    SourceLuid = (struct _LUID)-1LL;
    while ( 1 )
    {
LABEL_11:
      if ( !RtlAcquireResourceShared(&Resource, 1u) )
      {
        LocalFree(v9);
        return 2140;
      }
      v17 = 0;
      LowPart = SourceLuid.LowPart;
      while ( v17 < dword_18004F110 )
      {
        v19 = (__int64 **)(Use + 24LL * v17);
        if ( *(__int64 **)&SourceLuid == v19[1] || *(__int64 **)&SourceLuid == v19[2] )
        {
          v4 = *v19;
          break;
        }
        ++v17;
      }
      v20 = 0;
      if ( SourceLuid.HighPart == -1 )
        v20 = SourceLuid.LowPart == -1;
      if ( v9[1] != 92 )
      {
        while ( v4 )
        {
          v21 = (_WORD *)v4[2];
          if ( v21 )
          {
            *(_OWORD *)TokenHandle = 0;
            v22 = -1;
            String2 = 0;
            do
              ++v22;
            while ( v21[v22] );
            TokenHandle[1] = v21;
            WORD1(TokenHandle[0]) = 2 * (v22 + 1);
            LOWORD(TokenHandle[0]) = WORD1(TokenHandle[0]);
            v23 = -1;
            do
              ++v23;
            while ( v9[v23] );
            String2.Buffer = v9;
            String2.MaximumLength = 2 * (v23 + 1);
            String2.Length = String2.MaximumLength;
            if ( !RtlCompareUnicodeString((PCUNICODE_STRING)TokenHandle, &String2, 1u) )
              goto LABEL_29;
          }
          v4 = (__int64 *)*v4;
        }
        Info = 2250;
LABEL_65:
        RtlReleaseResource(&Resource);
        goto LABEL_66;
      }
      while ( v4 )
      {
        if ( !v4[2] && !(unsigned int)FULLSTRICMP(v4[1] + 8, v9, LowPart) )
        {
LABEL_29:
          v24 = (HANDLE)v4[4];
          Handle = v24;
          goto LABEL_32;
        }
        v4 = (__int64 *)*v4;
      }
      *(_OWORD *)&v62[0].LowPart = 0;
      v63 = 0;
      v41 = -1;
      v64 = 0;
      TokenHandle[0] = 0;
      do
        ++v41;
      while ( v9[v41] );
      v61[0] = 1;
      v61[1] = 6;
      String2 = 0;
      RtlCopyLuid((PLUID)&v62[0].HighPart, &SourceLuid);
      v62[0].LowPart = 0;
      v64 = 0;
      Info = WsDeviceControlGetInfo(0, WsRedirDeviceHandle, 1311143, v61, 36, TokenHandle, -1, 0);
      if ( Info )
        goto LABEL_65;
      v42 = (char *)TokenHandle[0];
      v43 = TokenHandle[0];
      if ( v62[1].HighPart )
      {
        v44 = 0;
        v45 = (char *)TokenHandle[0];
        v46 = (char *)TokenHandle[0];
        do
        {
          if ( Info )
            break;
          v47 = (unsigned int)WsCompareStringU(
                                *((_QWORD *)v46 + 1),
                                *(unsigned __int16 *)v42 >> 1,
                                v9,
                                (unsigned int)v41) == 0;
          v42 = v45 + 24;
          v45 = v42;
          v46 = v42;
          Info = v47;
          ++v44;
        }
        while ( v44 < v62[1].HighPart );
        v43 = TokenHandle[0];
        v5 = v59;
        v8 = v52;
      }
      LocalFree(v43);
      if ( !Info )
      {
        Info = 2250;
LABEL_204:
        v16 = *(char **)ReturnLength;
        goto LABEL_65;
      }
      v51 = -1;
      do
        ++v51;
      while ( v9[v51] );
      Info = WsCreateTreeConnectName((int)v9, v51, 0, v20, &String2);
      if ( Info )
        goto LABEL_204;
      v4 = 0;
      Info = WsOpenCreateConnectionSpecifyImpersonation(
               (int)&String2,
               0,
               0,
               0,
               0,
               0,
               0,
               0,
               0,
               0,
               0,
               1u,
               -1,
               v20,
               1,
               0,
               &Handle);
      LocalFree(String2.Buffer);
      if ( Info )
        goto LABEL_204;
      RtlReleaseResource(&Resource);
      v24 = Handle;
      v16 = *(char **)ReturnLength;
LABEL_32:
      DestinationLuid[0].LowPart = 1;
      TokenHandle[0] = 0;
      DestinationLuid[3] = 0;
      DestinationLuid[4].LowPart = 0;
      v25 = v5;
      DestinationLuid[0].HighPart = 6;
      if ( v5 > 2 )
        v25 = 2;
      *(_OWORD *)&DestinationLuid[1].LowPart = 0;
      RtlCopyLuid((PLUID)&DestinationLuid[1].HighPart, &SourceLuid);
      DestinationLuid[1].LowPart = v25;
      *(_QWORD *)&DestinationLuid[3].HighPart = 0;
      v26 = 552;
      if ( v25 != 1 )
        v26 = 1136;
      Info = WsDeviceControlGetInfo(0, v24, 1311139, DestinationLuid, 36, TokenHandle, -1, v26);
      if ( !Info )
        break;
LABEL_64:
      if ( v4 )
        goto LABEL_65;
      NtClose(Handle);
LABEL_66:
      if ( v8 || !Info )
      {
        LocalFree(v9);
        *v60 = v16;
        return Info;
      }
      v8 = 1;
      SourceLuid = (struct _LUID)-1LL;
      v52 = 1;
      v4 = 0;
    }
    v27 = TokenHandle[0];
    if ( v4 )
    {
      v28 = *((_DWORD *)v4 + 6);
      if ( v28 > 0xFFFF || (v29 = *(_DWORD *)(v4[1] + 4), v29 > 0xFFFF) )
      {
        Info = 2317;
        goto LABEL_65;
      }
      v30 = 2 * (v29 + v28);
    }
    else
    {
      v30 = *(unsigned __int16 *)TokenHandle[0];
    }
    switch ( v5 )
    {
      case 5u:
        v31 = 112;
        break;
      case 4u:
        v31 = 80;
        break;
      case 3u:
        v31 = 64;
        break;
      case 2u:
        v31 = 56;
        break;
      default:
        if ( v5 == 1 || (v31 = 16, v5 < 2) )
        {
          v32 = 40;
          if ( v5 != 1 )
            v32 = 16;
          goto LABEL_48;
        }
        break;
    }
    v32 = *((unsigned __int16 *)TokenHandle[0] + 16) + 2 + v31;
LABEL_48:
    v33 = (unsigned int)(v30 + v32 + 4);
    if ( v5 >= 2 )
    {
      v48 = *((unsigned __int16 *)TokenHandle[0] + 24);
      if ( (_WORD)v48 )
        v33 = (unsigned int)(v48 + 2 + v33);
    }
    if ( v5 >= 5 )
      v33 = ((_DWORD)v33 + 67) & 0xFFFFFFFC;
    v34 = (unsigned int)v33;
    v35 = (char *)LocalAlloc(0x40u, v33);
    *(_QWORD *)ReturnLength = v35;
    v16 = v35;
    if ( v35 )
    {
      memset_0(v35, 0, (unsigned int)v34);
      *(_QWORD *)&String2.Length = v16;
      TokenHandle[0] = &v16[v34];
      if ( v4 )
      {
        v36 = 2 * *(_WORD *)(v4[1] + 4);
        v27[1] = v36;
        *v27 = v36;
        *((_QWORD *)v27 + 1) = v4[1] + 8;
      }
      switch ( v5 )
      {
        case 5u:
          v37 = 112;
          break;
        case 4u:
          v37 = 80;
          break;
        case 3u:
          v37 = 64;
          break;
        case 2u:
          v37 = 56;
          break;
        default:
          v37 = 16;
          if ( v5 == 1 )
            v37 = 40;
          break;
      }
      if ( &v16[v37] < &v16[v34]
        && (unsigned int)WsFillUseBuffer(v5, (_DWORD)v4, (_DWORD)v27, (unsigned int)&String2, (__int64)TokenHandle, v37) )
      {
        Info = 0;
      }
      else
      {
        Info = 234;
        LocalFree(v16);
        v16 = 0;
        *(_QWORD *)ReturnLength = 0;
      }
      LocalFree(v27);
    }
    else
    {
      Info = 8;
    }
    goto LABEL_64;
  }
  TokenHandle[0] = 0;
  ReturnLength[0] = 0;
  memset(DestinationLuid, 0, sizeof(DestinationLuid));
  v10 = RpcImpersonateClient(0);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v11, (unsigned int)"unknown", 0, v10);
    }
    Info = 5;
    goto LABEL_215;
  }
  v12 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, TokenHandle);
  v13 = v12;
  if ( !v12 )
    goto LABEL_72;
  if ( v12 == -2147483611 )
    goto LABEL_8;
  if ( v12 > -1073741531 )
  {
    if ( v12 > -1073741495 )
    {
      switch ( v12 )
      {
        case -1073741433:
LABEL_150:
          Info = 2226;
          goto LABEL_71;
        case -1073741421:
          Info = 2239;
          goto LABEL_8;
        case -1073741261:
          Info = 2453;
          goto LABEL_8;
      }
    }
    else
    {
      switch ( v12 )
      {
        case -1073741495:
          Info = 2403;
          goto LABEL_8;
        case -1073741529:
          goto LABEL_140;
        case -1073741518:
          Info = 2210;
          goto LABEL_8;
        case -1073741517:
          Info = 2457;
          goto LABEL_8;
        case -1073741516:
          Info = 2249;
          goto LABEL_8;
      }
    }
LABEL_146:
    v49 = RtlNtStatusToDosError(v12);
    Info = 2140;
    if ( v49 != v13 )
      Info = v49;
LABEL_71:
    if ( v13 < 0 )
      goto LABEL_8;
LABEL_72:
    InformationToken = NtQueryInformationToken(TokenHandle[0], TokenStatistics, DestinationLuid, 0x38u, ReturnLength);
    v40 = InformationToken;
    if ( !InformationToken )
    {
      Info = 0;
LABEL_76:
      RtlCopyLuid(&SourceLuid, &DestinationLuid[1]);
      goto LABEL_77;
    }
    if ( InformationToken == -2147483611 )
    {
      Info = 0;
LABEL_77:
      NtClose(TokenHandle[0]);
      goto LABEL_8;
    }
    if ( InformationToken <= -1073741531 )
    {
      if ( InformationToken != -1073741531 )
      {
        switch ( InformationToken )
        {
          case -1073741789:
            Info = 2123;
            break;
          case -1073741727:
            Info = 5;
            break;
          case -1073741726:
            Info = 2202;
            break;
          case -1073741725:
            Info = 2224;
            break;
          case -1073741724:
            Info = 2221;
            break;
          case -1073741723:
            Info = 2223;
            break;
          case -1073741722:
          case -1073741709:
            Info = 2220;
            break;
          case -1073741721:
            Info = 2236;
            break;
          case -1073741720:
            Info = 2237;
            break;
          case -1073741716:
            Info = 2245;
            break;
          case -1073741713:
            Info = 2241;
            break;
          case -1073741712:
            Info = 2240;
            break;
          case -1073741711:
            Info = 2242;
            break;
          case -1073741604:
          case -1073741602:
            goto LABEL_191;
          case -1073741603:
            Info = 2227;
            break;
          case -1073741596:
            Info = 2247;
            break;
          case -1073741573:
            Info = 2102;
            break;
          case -1073741561:
            Info = 2401;
            break;
          case -1073741560:
            Info = 2404;
            break;
          default:
            goto LABEL_187;
        }
        goto LABEL_77;
      }
LABEL_181:
      Info = 2234;
      goto LABEL_107;
    }
    if ( InformationToken > -1073741495 )
    {
      switch ( InformationToken )
      {
        case -1073741433:
LABEL_191:
          Info = 2226;
          goto LABEL_107;
        case -1073741421:
          Info = 2239;
          goto LABEL_77;
        case -1073741261:
          Info = 2453;
          goto LABEL_77;
      }
    }
    else
    {
      switch ( InformationToken )
      {
        case -1073741495:
          Info = 2403;
          goto LABEL_77;
        case -1073741529:
          goto LABEL_181;
        case -1073741518:
          Info = 2210;
          goto LABEL_77;
        case -1073741517:
          Info = 2457;
          goto LABEL_77;
        case -1073741516:
          Info = 2249;
          goto LABEL_77;
      }
    }
LABEL_187:
    v50 = RtlNtStatusToDosError(InformationToken);
    Info = 2140;
    if ( v50 != v40 )
      Info = v50;
LABEL_107:
    if ( v40 < 0 )
      goto LABEL_77;
    goto LABEL_76;
  }
  if ( v12 == -1073741531 )
  {
LABEL_140:
    Info = 2234;
    goto LABEL_71;
  }
  switch ( v12 )
  {
    case -1073741789:
      Info = 2123;
      break;
    case -1073741727:
      Info = 5;
      break;
    case -1073741726:
      Info = 2202;
      break;
    case -1073741725:
      Info = 2224;
      break;
    case -1073741724:
      Info = 2221;
      break;
    case -1073741723:
      Info = 2223;
      break;
    case -1073741722:
    case -1073741709:
      Info = 2220;
      break;
    case -1073741721:
      Info = 2236;
      break;
    case -1073741720:
      Info = 2237;
      break;
    case -1073741716:
      Info = 2245;
      break;
    case -1073741713:
      Info = 2241;
      break;
    case -1073741712:
      Info = 2240;
      break;
    case -1073741711:
      Info = 2242;
      break;
    case -1073741604:
    case -1073741602:
      goto LABEL_150;
    case -1073741603:
      Info = 2227;
      break;
    case -1073741596:
      Info = 2247;
      break;
    case -1073741573:
      Info = 2102;
      break;
    case -1073741561:
      Info = 2401;
      break;
    case -1073741560:
      Info = 2404;
      break;
    default:
      goto LABEL_146;
  }
LABEL_8:
  v14 = RpcRevertToSelf();
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v15, (unsigned int)"unknown", 0, v14);
    }
    __fastfail(7u);
  }
  v4 = 0;
  if ( !Info )
  {
    v16 = 0;
    *(_QWORD *)ReturnLength = 0;
    v52 = v8;
    goto LABEL_11;
  }
LABEL_215:
  LocalFree(v9);
  return Info;
}

```

## disassembly

```asm
0x180003b70  push    rbp
0x180003b72  push    rbx
0x180003b73  push    rsi
0x180003b74  push    r12
0x180003b76  push    r13
0x180003b78  push    r14
0x180003b7a  lea     rbp, [rsp-48h]
0x180003b7f  sub     rsp, 158h
0x180003b86  mov     rax, cs:__security_cookie
0x180003b8d  xor     rax, rsp
0x180003b90  mov     [rbp+70h+var_40], rax
0x180003b94  xor     r14d, r14d
0x180003b97  movzx   r12d, r8w
0x180003b9b  mov     ebx, r8d
0x180003b9e  mov     [rbp+70h+var_A8], r9
0x180003ba2  and     ebx, 10000h
0x180003ba8  mov     [rbp+70h+var_AC], r12d
0x180003bac  mov     rsi, rdx
0x180003baf  mov     qword ptr [rbp+70h+SourceLuid.LowPart], r14
0x180003bb3  setnz   r13b
0x180003bb7  mov     [rbp+70h+Handle], r14
0x180003bbb  mov     [rbp+70h+var_F0], r13b
0x180003bbf  mov     [rbp+70h+var_B0], r14d
0x180003bc3  mov     [r9], r14
0x180003bc6  cmp     r12d, 5
0x180003bca  ja      loc_180004279
0x180003bd0  mov     edx, 20Ah; uBytes
0x180003bd5  mov     [rsp+180h+arg_0], rdi
0x180003bdd  mov     ecx, 40h ; '@'; uFlags
0x180003be2  call    cs:__imp_LocalAlloc
0x180003be8  mov     rdi, rax
0x180003beb  test    rax, rax
0x180003bee  jz      loc_1800042A0
0x180003bf4  lea     rax, [rbp+70h+var_B0]
0x180003bf8  mov     dword ptr [rsp+180h+hMem], r14d
0x180003bfd  xor     r9d, r9d
0x180003c00  mov     [rsp+180h+ReturnLength], rax
0x180003c05  mov     r8d, 20Ah
0x180003c0b  mov     rdx, rdi
0x180003c0e  mov     rcx, rsi
0x180003c11  call    cs:__imp_NetpwPathCanonicalize
0x180003c17  test    eax, eax
0x180003c19  jnz     loc_18000432A
0x180003c1f  mov     [rsp+180h+var_30], r15
0x180003c27  test    ebx, ebx
0x180003c29  jnz     loc_180004241
0x180003c2f  xorps   xmm0, xmm0
0x180003c32  mov     [rbp+70h+TokenHandle], r14
0x180003c36  xor     eax, eax
0x180003c38  mov     [rbp+70h+var_E8], r14d
0x180003c3c  xor     ecx, ecx; BindingHandle
0x180003c3e  mov     [rbp+70h+var_48], rax
0x180003c42  movups  xmmword ptr [rbp+70h+DestinationLuid.LowPart], xmm0
0x180003c46  movups  [rbp+70h+var_68], xmm0
0x180003c4a  movups  [rbp+70h+var_58], xmm0
0x180003c4e  call    cs:__imp_RpcImpersonateClient
0x180003c54  test    eax, eax
0x180003c56  jnz     loc_180004776
0x180003c5c  lea     r9, [rbp+70h+TokenHandle]; TokenHandle
0x180003c60  mov     r8b, 1; OpenAsSelf
0x180003c63  mov     edx, 8; DesiredAccess
0x180003c68  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180003c6f  call    cs:__imp_NtOpenThreadToken
0x180003c75  lea     r14, __ImageBase
0x180003c7c  mov     esi, eax
0x180003c7e  test    eax, eax
0x180003c80  jz      loc_1800040DC
0x180003c86  cmp     eax, 80000025h
0x180003c8b  jnz     loc_18000433D
0x180003c91  call    cs:__imp_RpcRevertToSelf
0x180003c97  test    eax, eax
0x180003c99  jnz     loc_18000466B
0x180003c9f  xor     r14d, r14d
0x180003ca2  test    ebx, ebx
0x180003ca4  jnz     loc_1800047B8
0x180003caa  mov     r15, r14
0x180003cad  mov     qword ptr [rbp+70h+var_E8], r14
0x180003cb1  mov     [rbp+70h+var_F0], r13b
0x180003cb5  mov     dl, 1; Wait
0x180003cb7  lea     rcx, Resource; Resource
0x180003cbe  call    cs:__imp_RtlAcquireResourceShared
0x180003cc4  test    al, al
0x180003cc6  jz      loc_180004283
0x180003ccc  mov     r11d, [rbp+70h+SourceLuid.HighPart]
0x180003cd0  mov     edx, r14d
0x180003cd3  mov     r8d, [rbp+70h+SourceLuid.LowPart]
0x180003cd7  mov     r9d, cs:dword_18004F110
0x180003cde  mov     r10, cs:Use
0x180003ce5  cmp     edx, r9d
0x180003ce8  jnb     short loc_180003D12
0x180003cea  mov     eax, edx
0x180003cec  lea     rcx, [rax+rax*2]
0x180003cf0  cmp     r8d, [r10+rcx*8+8]
0x180003cf5  lea     rax, [r10+rcx*8]
0x180003cf9  jz      short loc_180003D09
0x180003cfb  cmp     r8d, [rax+10h]
0x180003cff  jz      loc_1800042AB
0x180003d05  inc     edx
0x180003d07  jmp     short loc_180003CE5
0x180003d09  cmp     r11d, [rax+0Ch]
0x180003d0d  jnz     short loc_180003CFB
0x180003d0f  mov     r14, [rax]
0x180003d12  xor     sil, sil
0x180003d15  cmp     r11d, 0FFFFFFFFh
0x180003d19  jz      loc_1800042BA
0x180003d1f  cmp     word ptr [rdi+2], 5Ch ; '\'
0x180003d24  jz      loc_180004132
0x180003d2a  nop     word ptr [rax+rax+00h]
0x180003d30  test    r14, r14
0x180003d33  jz      loc_1800046BC
0x180003d39  mov     rcx, [r14+10h]
0x180003d3d  test    rcx, rcx
0x180003d40  jz      short loc_180003DB4
0x180003d42  xorps   xmm0, xmm0
0x180003d45  xorps   xmm1, xmm1
0x180003d48  movups  xmmword ptr [rbp+70h+TokenHandle], xmm0
0x180003d4c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003d53  movups  xmmword ptr [rbp+70h+String2.Length], xmm1
0x180003d57  nop     word ptr [rax+rax+00000000h]
0x180003d60  inc     rax
0x180003d63  cmp     word ptr [rcx+rax*2], 0
0x180003d68  jnz     short loc_180003D60
0x180003d6a  inc     ax
0x180003d6d  mov     [rbp+70h+TokenHandle+8], rcx
0x180003d71  add     ax, ax
0x180003d74  mov     word ptr [rbp+70h+TokenHandle+2], ax
0x180003d78  mov     word ptr [rbp+70h+TokenHandle], ax
0x180003d7c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003d83  inc     rax
0x180003d86  cmp     word ptr [rdi+rax*2], 0
0x180003d8b  jnz     short loc_180003D83
0x180003d8d  inc     ax
0x180003d90  mov     [rbp+70h+String2.Buffer], rdi
0x180003d94  add     ax, ax
0x180003d97  lea     rdx, [rbp+70h+String2]; String2
0x180003d9b  mov     r8b, 1; CaseInsensitive
0x180003d9e  mov     [rbp+70h+String2.MaximumLength], ax
0x180003da2  lea     rcx, [rbp+70h+TokenHandle]; String1
0x180003da6  mov     [rbp+70h+String2.Length], ax
0x180003daa  call    cs:__imp_RtlCompareUnicodeString
0x180003db0  test    eax, eax
0x180003db2  jz      short loc_180003DBC
0x180003db4  mov     r14, [r14]
0x180003db7  jmp     loc_180003D30
0x180003dbc  mov     rsi, [r14+20h]
0x180003dc0  mov     [rbp+70h+Handle], rsi
0x180003dc4  jmp     loc_180003E5C
0x180003dc9  xor     r14d, r14d
0x180003dcc  lea     rax, [rbp+70h+Handle]
0x180003dd0  mov     [rsp+180h+var_F8], r14
0x180003dd8  lea     rcx, [rbp+70h+String2]; int
0x180003ddc  mov     [rsp+180h+FileHandle], rax; FileHandle
0x180003de4  xor     r9d, r9d; int
0x180003de7  mov     [rsp+180h+var_108], r14b; char
0x180003dec  xor     r8d, r8d; int
0x180003def  mov     [rsp+180h+var_110], 1; char
0x180003df4  xor     edx, edx; int
0x180003df6  mov     [rsp+180h+var_118], sil; char
0x180003dfb  mov     [rsp+180h+var_120], 0FFFFFFFFh; int
0x180003e03  mov     [rsp+180h+var_128], 1; ULONG
0x180003e0b  mov     [rsp+180h+var_130], r14d; ULONG
0x180003e10  mov     [rsp+180h+var_138], r14; __int64
0x180003e15  mov     [rsp+180h+var_140], r14; __int64
0x180003e1a  mov     [rsp+180h+var_148], r14; __int64
0x180003e1f  mov     [rsp+180h+var_150], r14; __int64
0x180003e24  mov     [rsp+180h+hMem], r14; hMem
0x180003e29  mov     [rsp+180h+ReturnLength], r14; __int64
0x180003e2e  call    WsOpenCreateConnectionSpecifyImpersonation
0x180003e33  mov     rcx, [rbp+70h+String2.Buffer]; hMem
0x180003e37  mov     ebx, eax
0x180003e39  call    cs:__imp_LocalFree
0x180003e3f  test    ebx, ebx
0x180003e41  jnz     loc_180004720
0x180003e47  lea     rcx, Resource; Resource
0x180003e4e  call    cs:__imp_RtlReleaseResource
0x180003e54  mov     rsi, [rbp+70h+Handle]
0x180003e58  mov     r15, qword ptr [rbp+70h+var_E8]
0x180003e5c  xor     eax, eax
0x180003e5e  mov     [rbp+70h+DestinationLuid.LowPart], 1
0x180003e65  mov     ecx, 2
0x180003e6a  mov     [rbp+70h+TokenHandle], rax
0x180003e6e  xorps   xmm0, xmm0
0x180003e71  mov     qword ptr [rbp+70h+var_68+8], rax
0x180003e75  cmp     r12d, 2
0x180003e79  mov     dword ptr [rbp+70h+var_58], eax
0x180003e7c  mov     ebx, r12d
0x180003e7f  mov     [rbp+70h+DestinationLuid.HighPart], 6
0x180003e86  cmova   ebx, ecx
0x180003e89  lea     rdx, [rbp+70h+SourceLuid]; SourceLuid
0x180003e8d  lea     rcx, [rbp+70h+DestinationLuid.HighPart+8]; DestinationLuid
0x180003e91  movdqu  xmmword ptr [rbp+70h+DestinationLuid.LowPart+8], xmm0
0x180003e96  call    cs:__imp_RtlCopyLuid
0x180003e9c  xor     eax, eax
0x180003e9e  mov     [rbp+70h+DestinationLuid.LowPart+8], ebx
0x180003ea1  mov     qword ptr [rbp+70h+var_68+0Ch], rax
0x180003ea5  lea     r9, [rbp+70h+DestinationLuid]
0x180003ea9  mov     ecx, 470h
0x180003eae  mov     eax, 228h
0x180003eb3  cmp     ebx, 1
0x180003eb6  mov     r8d, 1401A3h
0x180003ebc  mov     rdx, rsi
0x180003ebf  cmovnz  eax, ecx
0x180003ec2  xor     ecx, ecx
0x180003ec4  mov     dword ptr [rsp+180h+var_148], eax
0x180003ec8  lea     rax, [rbp+70h+TokenHandle]
0x180003ecc  mov     dword ptr [rsp+180h+var_150], 0FFFFFFFFh
0x180003ed4  mov     [rsp+180h+hMem], rax
0x180003ed9  mov     dword ptr [rsp+180h+ReturnLength], 24h ; '$'
0x180003ee1  call    WsDeviceControlGetInfo
0x180003ee6  mov     ebx, eax
0x180003ee8  test    eax, eax
0x180003eea  jnz     loc_18000405F
0x180003ef0  mov     rsi, [rbp+70h+TokenHandle]
0x180003ef4  test    r14, r14
0x180003ef7  jz      loc_180004266
0x180003efd  mov     edx, [r14+18h]
0x180003f01  cmp     edx, 0FFFFh
0x180003f07  ja      loc_18000426F
0x180003f0d  mov     rax, [r14+8]
0x180003f11  mov     ecx, [rax+4]
0x180003f14  cmp     ecx, 0FFFFh
0x180003f1a  ja      loc_18000426F
0x180003f20  lea     r8d, [rcx+rdx]
0x180003f24  add     r8d, r8d
0x180003f27  cmp     r12d, 5
0x180003f2b  jz      loc_1800042FA
0x180003f31  cmp     r12d, 4
0x180003f35  jz      loc_180004729
0x180003f3b  cmp     r12d, 3
0x180003f3f  jz      loc_1800042CF
0x180003f45  cmp     r12d, 2
0x180003f49  jz      loc_180004733
0x180003f4f  mov     eax, 10h
0x180003f54  cmp     r12d, 1
0x180003f58  jz      loc_180004255
0x180003f5e  mov     ecx, eax
0x180003f60  cmp     r12d, 2
0x180003f64  jb      loc_180004255
0x180003f6a  movzx   eax, word ptr [rsi+20h]
0x180003f6e  add     eax, 2
0x180003f71  add     ecx, eax
0x180003f73  lea     edx, [rcx+4]
0x180003f76  add     edx, r8d; uBytes
0x180003f79  cmp     r12d, 2
0x180003f7d  jnb     loc_1800042E3
0x180003f83  cmp     r12d, 5
0x180003f87  jnb     loc_18000473D
0x180003f8d  mov     ecx, 40h ; '@'; uFlags
0x180003f92  mov     ebx, edx
0x180003f94  call    cs:__imp_LocalAlloc
0x180003f9a  mov     qword ptr [rbp+70h+var_E8], rax
0x180003f9e  mov     r15, rax
0x180003fa1  test    rax, rax
0x180003fa4  jz      loc_180004296
0x180003faa  mov     r8d, ebx; Size
0x180003fad  xor     edx, edx; Val
0x180003faf  mov     rcx, rax; void *
0x180003fb2  call    memset_0
0x180003fb7  mov     qword ptr [rbp+70h+String2.Length], r15
0x180003fbb  lea     rdx, [rbx+r15]
0x180003fbf  mov     [rbp+70h+TokenHandle], rdx
0x180003fc3  test    r14, r14
0x180003fc6  jz      short loc_180003FE6
0x180003fc8  mov     rax, [r14+8]
0x180003fcc  movzx   ecx, word ptr [rax+4]
0x180003fd0  add     cx, cx
0x180003fd3  mov     [rsi+2], cx
0x180003fd7  mov     [rsi], cx
0x180003fda  mov     rax, [r14+8]
0x180003fde  add     rax, 8
0x180003fe2  mov     [rsi+8], rax
0x180003fe6  cmp     r12d, 5
0x180003fea  jz      loc_180004304
0x180003ff0  cmp     r12d, 4
0x180003ff4  jz      loc_180004748
0x180003ffa  cmp     r12d, 3
0x180003ffe  jz      loc_1800042D9
0x180004004  cmp     r12d, 2
0x180004008  jz      loc_180004752
0x18000400e  cmp     r12d, 1
0x180004012  mov     ecx, 10h
0x180004017  mov     eax, 28h ; '('
0x18000401c  cmovz   ecx, eax
0x18000401f  mov     eax, ecx
0x180004021  add     rax, r15
0x180004024  cmp     rax, rdx
0x180004027  jnb     loc_18000475C
0x18000402d  mov     dword ptr [rsp+180h+hMem], ecx
0x180004031  lea     rax, [rbp+70h+TokenHandle]
0x180004035  mov     ecx, r12d
0x180004038  mov     [rsp+180h+ReturnLength], rax
0x18000403d  lea     r9, [rbp+70h+String2]
0x180004041  mov     r8, rsi
0x180004044  mov     rdx, r14
0x180004047  call    WsFillUseBuffer
0x18000404c  test    eax, eax
0x18000404e  jz      loc_18000475C
0x180004054  xor     ebx, ebx
0x180004056  mov     rcx, rsi; hMem
0x180004059  call    cs:__imp_LocalFree
  ... truncated ...
```
