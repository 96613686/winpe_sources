# WcmSvcInitRPCServer

- ea: `0x1800adf74`
- end: `0x1800ae53b`
- name: `WcmSvcInitRPCServer`
- size: `1479`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b0d60`

## callees

- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180017ad0`
- `0x1800277c0`
- `0x180085bc4`
- `0x1800aacc8`
- `0x1800abdc0`
- `0x1800adf74`
- `0x1800e647c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800adfe9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800adfe9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ae432`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ae432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae06a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae14a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae1be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae229`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae2ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae36a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae06a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae14a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae1be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae229`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae2ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae36a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae19c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae207`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae272`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae2dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae348`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae19c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae207`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae272`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae2dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ae348`

## pseudocode

```c
__int64 WcmSvcInitRPCServer()
{
  unsigned int WellKnownSid; // edi
  __int64 v1; // rcx
  DWORD LastError; // eax
  __int64 v3; // rdx
  char v4; // al
  char v5; // al
  char v6; // al
  char v7; // al
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  char v11; // al

  WellKnownSid = 0;
  v1 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      54,
      WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
      "WcmSvcInitRPCServer");
    v1 = WPP_GLOBAL_Control;
  }
  if ( !g_bRpcServerStarted )
  {
    memset_0(&g_RpcServerContext, 0, 0xA0u);
    InitializeCriticalSection(&stru_18013F4A0);
    if ( LocalCreateWellKnownSid(WinLocalSystemSid, &qword_18013F450) )
    {
      LastError = GetLastError();
      WellKnownSid = LastError;
      v1 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v3 = 56;
LABEL_11:
        WPP_SF_d(*(_QWORD *)(v1 + 16), v3, WPP_59cb1c30c417333f98d499625c161da5_Traceguids, LastError);
LABEL_12:
        v1 = WPP_GLOBAL_Control;
      }
    }
    else if ( LocalCreateWellKnownSid(WinLocalServiceSid, &qword_18013F458) )
    {
      LastError = GetLastError();
      WellKnownSid = LastError;
      v1 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v3 = 57;
        goto LABEL_11;
      }
    }
    else if ( LocalCreateWellKnownSid(WinNetworkServiceSid, &qword_18013F460) )
    {
      LastError = GetLastError();
      WellKnownSid = LastError;
      v1 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v3 = 58;
        goto LABEL_11;
      }
    }
    else if ( LocalCreateWellKnownSid(WinBuiltinAdministratorsSid, &qword_18013F468) )
    {
      LastError = GetLastError();
      WellKnownSid = LastError;
      v1 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v3 = 59;
        goto LABEL_11;
      }
    }
    else
    {
      WellKnownSid = LocalCreateWellKnownSid(WinBuiltinNetworkConfigurationOperatorsSid, &qword_18013F470);
      if ( !WellKnownSid )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &Sid,
          0);
        if ( !ConvertStringSidToSidW(L"S-1-5-80-2940520708-3855866260-481812779-327648279-1710889582", &Sid)
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v4 = GetLastError();
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            61,
            (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
            (unsigned int)L"S-1-5-80-2940520708-3855866260-481812779-327648279-1710889582",
            v4);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &qword_18013F480,
          0);
        if ( !ConvertStringSidToSidW(L"S-1-5-80-3635958274-2059881490-2225992882-984577281-633327304", &qword_18013F480)
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v5 = GetLastError();
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            62,
            (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
            (unsigned int)L"S-1-5-80-3635958274-2059881490-2225992882-984577281-633327304",
            v5);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &qword_18013F488,
          0);
        if ( !ConvertStringSidToSidW(
                L"S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142",
                &qword_18013F488)
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v6 = GetLastError();
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            63,
            (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
            (unsigned int)L"S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142",
            v6);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &qword_18013F490,
          0);
        if ( !ConvertStringSidToSidW(L"S-1-5-80-3981856537-581775623-1136376035-2066872258-409572886", &qword_18013F490)
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v7 = GetLastError();
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            64,
            (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
            (unsigned int)L"S-1-5-80-3981856537-581775623-1136376035-2066872258-409572886",
            v7);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &qword_18013F498,
          0);
        if ( !ConvertStringSidToSidW(L"S-1-5-80-3578261754-285310837-913589462-2834155770-667502746", &qword_18013F498)
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v11 = GetLastError();
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            65,
            (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
            (unsigned int)L"S-1-5-80-3578261754-285310837-913589462-2834155770-667502746",
            v11);
        }
        qword_18013F440 = (__int64)&qword_18013F438;
        qword_18013F438 = (struct RPC_CLIENT_INFO *)&qword_18013F438;
        TrInitTraceHeader(v9, v8, v10, (unsigned int)&stru_18013F4A0, (__int64)&qword_18013F4C8);
        g_RpcServerContext = 1;
        goto LABEL_12;
      }
      LastError = GetLastError();
      WellKnownSid = LastError;
      v1 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v3 = 60;
        goto LABEL_11;
      }
    }
  }
  if ( WellKnownSid )
  {
    if ( g_RpcServerContext )
    {
      DeleteCriticalSection(&stru_18013F4A0);
      v1 = WPP_GLOBAL_Control;
    }
    if ( qword_18013F450 )
    {
      WcmFree(qword_18013F450);
      qword_18013F450 = 0;
      v1 = WPP_GLOBAL_Control;
    }
    if ( qword_18013F458 )
    {
      WcmFree(qword_18013F458);
      qword_18013F458 = 0;
      v1 = WPP_GLOBAL_Control;
    }
    if ( qword_18013F460 )
    {
      WcmFree(qword_18013F460);
      qword_18013F460 = 0;
      v1 = WPP_GLOBAL_Control;
    }
    if ( qword_18013F468 )
    {
      WcmFree(qword_18013F468);
      qword_18013F468 = 0;
      v1 = WPP_GLOBAL_Control;
    }
    if ( qword_18013F470 )
    {
      WcmFree(qword_18013F470);
      qword_18013F470 = 0;
      v1 = WPP_GLOBAL_Control;
    }
  }
  if ( (_UNKNOWN *)v1 != &WPP_GLOBAL_Control && *(_BYTE *)(v1 + 25) >= 5u && (*(_BYTE *)(v1 + 28) & 1) != 0 )
    WPP_SF_sL(
      *(_QWORD *)(v1 + 16),
      66,
      (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
      (unsigned int)"WcmSvcInitRPCServer",
      WellKnownSid);
  return WellKnownSid;
}

```

## disassembly

```asm
0x1800adf74  mov     [rsp+arg_0], rsi
0x1800adf79  push    rdi
0x1800adf7a  sub     rsp, 30h
0x1800adf7e  xor     edi, edi
0x1800adf80  lea     rsi, WPP_GLOBAL_Control
0x1800adf87  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adf8e  cmp     rcx, rsi
0x1800adf91  jz      short loc_1800ADFC0
0x1800adf93  cmp     byte ptr [rcx+19h], 5
0x1800adf97  jb      short loc_1800ADFC0
0x1800adf99  test    byte ptr [rcx+1Ch], 1
0x1800adf9d  jz      short loc_1800ADFC0
0x1800adf9f  lea     edx, [rdi+36h]
0x1800adfa2  lea     r9, aWcmsvcinitrpcs; "WcmSvcInitRPCServer"
0x1800adfa9  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800adfb0  mov     rcx, [rcx+10h]
0x1800adfb4  call    WPP_SF_s
0x1800adfb9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adfc0  cmp     cs:?g_bRpcServerStarted@@3EA, dil; uchar g_bRpcServerStarted
0x1800adfc7  jnz     loc_1800AE41A
0x1800adfcd  xor     edx, edx; Val
0x1800adfcf  mov     r8d, 0A0h; Size
0x1800adfd5  lea     rcx, ?g_RpcServerContext@@3URPC_SERVER_CONTEXT@@A; void *
0x1800adfdc  call    memset_0
0x1800adfe1  nop
0x1800adfe2  lea     rcx, stru_18013F4A0; lpCriticalSection
0x1800adfe9  call    cs:__imp_InitializeCriticalSection
0x1800adfef  nop
0x1800adff0  lea     rdx, qword_18013F450; void **
0x1800adff7  mov     ecx, 16h; WellKnownSidType
0x1800adffc  call    ?LocalCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; LocalCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800ae001  test    eax, eax
0x1800ae003  jz      short loc_1800AE055
0x1800ae005  call    cs:__imp_GetLastError
0x1800ae00b  mov     edi, eax
0x1800ae00d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae014  cmp     rcx, rsi
0x1800ae017  jz      loc_1800AE41A
0x1800ae01d  cmp     byte ptr [rcx+19h], 1
0x1800ae021  jb      loc_1800AE41A
0x1800ae027  test    byte ptr [rcx+1Ch], 1
0x1800ae02b  jz      loc_1800AE41A
0x1800ae031  mov     edx, 38h ; '8'
0x1800ae036  mov     r9d, eax
0x1800ae039  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800ae040  mov     rcx, [rcx+10h]
0x1800ae044  call    WPP_SF_d
0x1800ae049  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae050  jmp     loc_1800AE41A
0x1800ae055  lea     rdx, qword_18013F458; void **
0x1800ae05c  mov     ecx, 17h; WellKnownSidType
0x1800ae061  call    ?LocalCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; LocalCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800ae066  test    eax, eax
0x1800ae068  jz      short loc_1800AE09D
0x1800ae06a  call    cs:__imp_GetLastError
0x1800ae070  mov     edi, eax
0x1800ae072  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae079  cmp     rcx, rsi
0x1800ae07c  jz      loc_1800AE41A
0x1800ae082  cmp     byte ptr [rcx+19h], 1
0x1800ae086  jb      loc_1800AE41A
0x1800ae08c  test    byte ptr [rcx+1Ch], 1
0x1800ae090  jz      loc_1800AE41A
0x1800ae096  mov     edx, 39h ; '9'
0x1800ae09b  jmp     short loc_1800AE036
0x1800ae09d  lea     rdx, qword_18013F460; void **
0x1800ae0a4  mov     ecx, 18h; WellKnownSidType
0x1800ae0a9  call    ?LocalCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; LocalCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800ae0ae  test    eax, eax
0x1800ae0b0  jz      short loc_1800AE0E8
0x1800ae0b2  call    cs:__imp_GetLastError
0x1800ae0b8  mov     edi, eax
0x1800ae0ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae0c1  cmp     rcx, rsi
0x1800ae0c4  jz      loc_1800AE41A
0x1800ae0ca  cmp     byte ptr [rcx+19h], 1
0x1800ae0ce  jb      loc_1800AE41A
0x1800ae0d4  test    byte ptr [rcx+1Ch], 1
0x1800ae0d8  jz      loc_1800AE41A
0x1800ae0de  mov     edx, 3Ah ; ':'
0x1800ae0e3  jmp     loc_1800AE036
0x1800ae0e8  lea     rdx, qword_18013F468; void **
0x1800ae0ef  mov     ecx, 1Ah; WellKnownSidType
0x1800ae0f4  call    ?LocalCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; LocalCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800ae0f9  test    eax, eax
0x1800ae0fb  jz      short loc_1800AE133
0x1800ae0fd  call    cs:__imp_GetLastError
0x1800ae103  mov     edi, eax
0x1800ae105  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae10c  cmp     rcx, rsi
0x1800ae10f  jz      loc_1800AE41A
0x1800ae115  cmp     byte ptr [rcx+19h], 1
0x1800ae119  jb      loc_1800AE41A
0x1800ae11f  test    byte ptr [rcx+1Ch], 1
0x1800ae123  jz      loc_1800AE41A
0x1800ae129  mov     edx, 3Bh ; ';'
0x1800ae12e  jmp     loc_1800AE036
0x1800ae133  lea     rdx, qword_18013F470; void **
0x1800ae13a  mov     ecx, 25h ; '%'; WellKnownSidType
0x1800ae13f  call    ?LocalCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; LocalCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800ae144  mov     edi, eax
0x1800ae146  test    eax, eax
0x1800ae148  jz      short loc_1800AE180
0x1800ae14a  call    cs:__imp_GetLastError
0x1800ae150  mov     edi, eax
0x1800ae152  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae159  cmp     rcx, rsi
0x1800ae15c  jz      loc_1800AE41A
0x1800ae162  cmp     byte ptr [rcx+19h], 1
0x1800ae166  jb      loc_1800AE41A
0x1800ae16c  test    byte ptr [rcx+1Ch], 1
0x1800ae170  jz      loc_1800AE41A
0x1800ae176  mov     edx, 3Ch ; '<'
0x1800ae17b  jmp     loc_1800AE036
0x1800ae180  xor     edx, edx
0x1800ae182  lea     rcx, Sid
0x1800ae189  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800ae18e  lea     rdx, Sid; Sid
0x1800ae195  lea     rcx, StringSid; "S-1-5-80-2940520708-3855866260-48181277"...
0x1800ae19c  call    cs:__imp_ConvertStringSidToSidW
0x1800ae1a2  test    eax, eax
0x1800ae1a4  jnz     short loc_1800AE1EB
0x1800ae1a6  mov     rax, cs:WPP_GLOBAL_Control
0x1800ae1ad  cmp     rax, rsi
0x1800ae1b0  jz      short loc_1800AE1EB
0x1800ae1b2  cmp     byte ptr [rax+19h], 3
0x1800ae1b6  jb      short loc_1800AE1EB
0x1800ae1b8  test    byte ptr [rax+1Ch], 1
0x1800ae1bc  jz      short loc_1800AE1EB
0x1800ae1be  call    cs:__imp_GetLastError
0x1800ae1c4  mov     edx, 3Dh ; '='
0x1800ae1c9  mov     dword ptr [rsp+38h+var_18], eax
0x1800ae1cd  lea     r9, StringSid; "S-1-5-80-2940520708-3855866260-48181277"...
0x1800ae1d4  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800ae1db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae1e2  mov     rcx, [rcx+10h]
0x1800ae1e6  call    WPP_SF_Sd
0x1800ae1eb  xor     edx, edx
0x1800ae1ed  lea     rcx, qword_18013F480
0x1800ae1f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800ae1f9  lea     rdx, qword_18013F480; Sid
0x1800ae200  lea     rcx, aS1580363595827; "S-1-5-80-3635958274-2059881490-22259928"...
0x1800ae207  call    cs:__imp_ConvertStringSidToSidW
0x1800ae20d  test    eax, eax
0x1800ae20f  jnz     short loc_1800AE256
0x1800ae211  mov     rax, cs:WPP_GLOBAL_Control
0x1800ae218  cmp     rax, rsi
0x1800ae21b  jz      short loc_1800AE256
0x1800ae21d  cmp     byte ptr [rax+19h], 3
0x1800ae221  jb      short loc_1800AE256
0x1800ae223  test    byte ptr [rax+1Ch], 1
0x1800ae227  jz      short loc_1800AE256
0x1800ae229  call    cs:__imp_GetLastError
0x1800ae22f  mov     edx, 3Eh ; '>'
0x1800ae234  mov     dword ptr [rsp+38h+var_18], eax
0x1800ae238  lea     r9, aS1580363595827; "S-1-5-80-3635958274-2059881490-22259928"...
0x1800ae23f  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800ae246  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae24d  mov     rcx, [rcx+10h]
0x1800ae251  call    WPP_SF_Sd
0x1800ae256  xor     edx, edx
0x1800ae258  lea     rcx, qword_18013F488
0x1800ae25f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800ae264  lea     rdx, qword_18013F488; Sid
0x1800ae26b  lea     rcx, aS1580142802753; "S-1-5-80-1428027539-3309602793-26783530"...
0x1800ae272  call    cs:__imp_ConvertStringSidToSidW
0x1800ae278  test    eax, eax
0x1800ae27a  jnz     short loc_1800AE2C1
0x1800ae27c  mov     rax, cs:WPP_GLOBAL_Control
0x1800ae283  cmp     rax, rsi
0x1800ae286  jz      short loc_1800AE2C1
0x1800ae288  cmp     byte ptr [rax+19h], 3
0x1800ae28c  jb      short loc_1800AE2C1
0x1800ae28e  test    byte ptr [rax+1Ch], 1
0x1800ae292  jz      short loc_1800AE2C1
0x1800ae294  call    cs:__imp_GetLastError
0x1800ae29a  mov     edx, 3Fh ; '?'
0x1800ae29f  mov     dword ptr [rsp+38h+var_18], eax
0x1800ae2a3  lea     r9, aS1580142802753; "S-1-5-80-1428027539-3309602793-26783530"...
0x1800ae2aa  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800ae2b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae2b8  mov     rcx, [rcx+10h]
0x1800ae2bc  call    WPP_SF_Sd
0x1800ae2c1  xor     edx, edx
0x1800ae2c3  lea     rcx, qword_18013F490
0x1800ae2ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800ae2cf  lea     rdx, qword_18013F490; Sid
0x1800ae2d6  lea     rcx, aS1580398185653; "S-1-5-80-3981856537-581775623-113637603"...
0x1800ae2dd  call    cs:__imp_ConvertStringSidToSidW
0x1800ae2e3  test    eax, eax
0x1800ae2e5  jnz     short loc_1800AE32C
0x1800ae2e7  mov     rax, cs:WPP_GLOBAL_Control
0x1800ae2ee  cmp     rax, rsi
0x1800ae2f1  jz      short loc_1800AE32C
0x1800ae2f3  cmp     byte ptr [rax+19h], 3
0x1800ae2f7  jb      short loc_1800AE32C
0x1800ae2f9  test    byte ptr [rax+1Ch], 1
0x1800ae2fd  jz      short loc_1800AE32C
0x1800ae2ff  call    cs:__imp_GetLastError
0x1800ae305  mov     edx, 40h ; '@'
0x1800ae30a  mov     dword ptr [rsp+38h+var_18], eax
0x1800ae30e  lea     r9, aS1580398185653; "S-1-5-80-3981856537-581775623-113637603"...
0x1800ae315  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800ae31c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae323  mov     rcx, [rcx+10h]
0x1800ae327  call    WPP_SF_Sd
0x1800ae32c  xor     edx, edx
0x1800ae32e  lea     rcx, qword_18013F498
0x1800ae335  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800ae33a  lea     rdx, qword_18013F498; Sid
0x1800ae341  lea     rcx, aS1580357826175; "S-1-5-80-3578261754-285310837-913589462"...
0x1800ae348  call    cs:__imp_ConvertStringSidToSidW
0x1800ae34e  test    eax, eax
0x1800ae350  jnz     short loc_1800AE397
0x1800ae352  mov     rax, cs:WPP_GLOBAL_Control
0x1800ae359  cmp     rax, rsi
0x1800ae35c  jz      short loc_1800AE397
0x1800ae35e  cmp     byte ptr [rax+19h], 3
0x1800ae362  jb      short loc_1800AE397
0x1800ae364  test    byte ptr [rax+1Ch], 1
0x1800ae368  jz      short loc_1800AE397
0x1800ae36a  call    cs:__imp_GetLastError
0x1800ae370  mov     edx, 41h ; 'A'
0x1800ae375  mov     dword ptr [rsp+38h+var_18], eax
0x1800ae379  lea     r9, aS1580357826175; "S-1-5-80-3578261754-285310837-913589462"...
0x1800ae380  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800ae387  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae38e  mov     rcx, [rcx+10h]
0x1800ae392  call    WPP_SF_Sd
0x1800ae397  lea     rax, qword_18013F438
0x1800ae39e  mov     cs:qword_18013F440, rax
0x1800ae3a5  mov     cs:qword_18013F438, rax
0x1800ae3ac  lea     rax, qword_18013F4C8
0x1800ae3b3  mov     [rsp+38h+var_18], rax
0x1800ae3b8  lea     r9, stru_18013F4A0
0x1800ae3bf  call    TrInitTraceHeader
0x1800ae3c4  mov     cs:?g_RpcServerContext@@3URPC_SERVER_CONTEXT@@A, 1; RPC_SERVER_CONTEXT g_RpcServerContext
0x1800ae3ce  jmp     loc_1800AE049
0x1800ae3d3  mov     edi, eax
0x1800ae3d5  lea     rax, WPP_GLOBAL_Control
0x1800ae3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae3e3  cmp     rcx, rax
0x1800ae3e6  jz      short loc_1800AE413
0x1800ae3e8  cmp     byte ptr [rcx+19h], 1
0x1800ae3ec  jb      short loc_1800AE413
0x1800ae3ee  test    byte ptr [rcx+1Ch], 1
0x1800ae3f2  jz      short loc_1800AE413
0x1800ae3f4  mov     edx, 37h ; '7'
0x1800ae3f9  mov     r9d, edi
0x1800ae3fc  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800ae403  mov     rcx, [rcx+10h]
0x1800ae407  call    WPP_SF_d
0x1800ae40c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae413  lea     rsi, WPP_GLOBAL_Control
0x1800ae41a  test    edi, edi
0x1800ae41c  jz      loc_1800AE4FD
0x1800ae422  cmp     cs:?g_RpcServerContext@@3URPC_SERVER_CONTEXT@@A, 0; RPC_SERVER_CONTEXT g_RpcServerContext
0x1800ae429  jz      short loc_1800AE43F
0x1800ae42b  lea     rcx, stru_18013F4A0; lpCriticalSection
0x1800ae432  call    cs:__imp_DeleteCriticalSection
0x1800ae438  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae43f  mov     rax, cs:qword_18013F450
0x1800ae446  test    rax, rax
0x1800ae449  jz      short loc_1800AE465
0x1800ae44b  mov     rcx, rax; lpMem
0x1800ae44e  call    WcmFree
0x1800ae453  mov     cs:qword_18013F450, 0
0x1800ae45e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae465  mov     rax, cs:qword_18013F458
0x1800ae46c  test    rax, rax
0x1800ae46f  jz      short loc_1800AE48B
0x1800ae471  mov     rcx, rax; lpMem
0x1800ae474  call    WcmFree
0x1800ae479  mov     cs:qword_18013F458, 0
0x1800ae484  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae48b  mov     rax, cs:qword_18013F460
0x1800ae492  test    rax, rax
0x1800ae495  jz      short loc_1800AE4B1
0x1800ae497  mov     rcx, rax; lpMem
0x1800ae49a  call    WcmFree
0x1800ae49f  mov     cs:qword_18013F460, 0
0x1800ae4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae4b1  mov     rax, cs:qword_18013F468
0x1800ae4b8  test    rax, rax
0x1800ae4bb  jz      short loc_1800AE4D7
0x1800ae4bd  mov     rcx, rax; lpMem
0x1800ae4c0  call    WcmFree
0x1800ae4c5  mov     cs:qword_18013F468, 0
0x1800ae4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae4d7  mov     rax, cs:qword_18013F470
0x1800ae4de  test    rax, rax
0x1800ae4e1  jz      short loc_1800AE4FD
0x1800ae4e3  mov     rcx, rax; lpMem
0x1800ae4e6  call    WcmFree
0x1800ae4eb  mov     cs:qword_18013F470, 0
0x1800ae4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae4fd  cmp     rcx, rsi
0x1800ae500  jz      short loc_1800AE52E
0x1800ae502  cmp     byte ptr [rcx+19h], 5
0x1800ae506  jb      short loc_1800AE52E
  ... truncated ...
```
