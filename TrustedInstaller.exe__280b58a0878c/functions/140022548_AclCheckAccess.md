# AclCheckAccess

- ea: `0x140022548`
- end: `0x1400228b3`
- name: `AclCheckAccess`
- size: `875`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400200b8`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400184fc`
- `0x140022548`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400227fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400227fb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002288e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002288e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400227ed`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400227ed`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140022749`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140022749`

## string_xrefs

- `0x1400225cc`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x1400227c2`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x140022866`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x140022589`: `No ACL specified`
- `0x140022658`: `Invalid ACL; dwAccessMask must not be specified`
- `0x1400225fb`: `Invalid ACL; DenyAccess must not be specified`
- `0x14002276d`: `Failed to allocate SID to check membership.`
- `0x1400226ba`: `Failed to get SID for account: {}`

## pseudocode

```c
int __fastcall AclCheckAccess(HANDLE TokenHandle, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  DWORD v10; // r9d
  DWORD v11; // r8d
  struct _SID_IDENTIFIER_AUTHORITY *v12; // rcx
  DWORD v13; // eax
  BYTE v14; // dl
  signed int v15; // ebx
  __int64 v16; // rdx
  unsigned int v17; // eax
  signed int LastError; // ebx
  __int64 v20; // rdx
  unsigned int v21; // eax
  int v22; // eax
  int nSubAuthority2; // [rsp+20h] [rbp-60h]
  unsigned int nSubAuthority2a; // [rsp+20h] [rbp-60h]
  DWORD nSubAuthority3; // [rsp+28h] [rbp-58h]
  DWORD nSubAuthority4; // [rsp+30h] [rbp-50h]
  DWORD nSubAuthority5; // [rsp+38h] [rbp-48h]
  DWORD nSubAuthority6; // [rsp+40h] [rbp-40h]
  DWORD nSubAuthority7; // [rsp+48h] [rbp-38h]
  unsigned int v30[2]; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  int v32; // [rsp+70h] [rbp-10h] BYREF
  WINBOOL IsMember; // [rsp+74h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  IsMember = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    v32 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No ACL specified");
      *(_QWORD *)v30 = &v32;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v30);
    }
    v6 = 71;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
      (const char *)v4,
      nSubAuthority2);
    return v4;
  }
  if ( *(_DWORD *)a2 )
  {
    v4 = -2147024809;
    v32 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid ACL; DenyAccess must not be specified");
      *(_QWORD *)v30 = &v32;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v30);
    }
    v6 = 72;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(a2 + 4) )
  {
    v4 = -2147024809;
    v32 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid ACL; dwAccessMask must not be specified");
      *(_QWORD *)v30 = &v32;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v30);
    }
    v6 = 73;
    goto LABEL_5;
  }
  if ( *(_QWORD *)(a2 + 8) )
  {
    v4 = -2147467263;
    v32 = -2147467263;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        a2,
        a3,
        (__int64)"Failed to get SID for account: {}",
        a2 + 8);
      *(_QWORD *)v30 = &v32;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v30);
    }
    v6 = 77;
    goto LABEL_5;
  }
  v10 = *(_DWORD *)(a2 + 28);
  v11 = *(_DWORD *)(a2 + 24);
  v12 = (struct _SID_IDENTIFIER_AUTHORITY *)(a2 + 16);
  nSubAuthority7 = *(_DWORD *)(a2 + 52);
  nSubAuthority6 = *(_DWORD *)(a2 + 48);
  nSubAuthority5 = *(_DWORD *)(a2 + 44);
  nSubAuthority4 = *(_DWORD *)(a2 + 40);
  nSubAuthority3 = *(_DWORD *)(a2 + 36);
  v13 = *(_DWORD *)(a2 + 32);
  v14 = *(_BYTE *)(a2 + 22);
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(
         v12,
         v14,
         v11,
         v10,
         v13,
         nSubAuthority3,
         nSubAuthority4,
         nSubAuthority5,
         nSubAuthority6,
         nSubAuthority7,
         &SidToCheck) )
  {
    if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
    {
      v22 = IsMember == 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to check membership");
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        else
          v21 = LastError;
        v32 = v21;
        *(_QWORD *)v30 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v20,
          3,
          (__int64)": {0}",
          (__int64)v30);
      }
      if ( !LastError )
      {
        v4 = 0;
LABEL_38:
        FreeSid(SidToCheck);
        return v4;
      }
      v22 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x63,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
              (const char *)(unsigned int)LastError,
              nSubAuthority2a);
    }
    v4 = v22;
    goto LABEL_38;
  }
  v15 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate SID to check membership.");
    if ( v15 > 0 )
      v17 = (unsigned __int16)v15 | 0x80070000;
    else
      v17 = v15;
    v32 = v17;
    *(_QWORD *)v30 = &v32;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v16,
      3,
      (__int64)": {0}",
      (__int64)v30);
  }
  if ( v15 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x5E,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
             (const char *)(unsigned int)v15,
             nSubAuthority2a);
  else
    return 0;
}

```

## disassembly

```asm
0x140022548  mov     [rsp-8+arg_10], rbx
0x14002254d  push    rbp
0x14002254e  mov     rbp, rsp
0x140022551  sub     rsp, 80h
0x140022558  mov     rax, cs:__security_cookie
0x14002255f  xor     rax, rsp
0x140022562  mov     [rbp+var_8], rax
0x140022566  mov     [rbp+IsMember], 0
0x14002256d  mov     rbx, rcx
0x140022570  test    rdx, rdx
0x140022573  jnz     short loc_1400225E0
0x140022575  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002257c  mov     ebx, 80070057h
0x140022581  mov     [rbp+var_10], ebx
0x140022584  test    rcx, rcx
0x140022587  jz      short loc_1400225C3
0x140022589  lea     r9, aNoAclSpecified; "No ACL specified"
0x140022590  lea     r8d, [rdx+3]
0x140022594  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140022599  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400225a0  lea     rax, [rbp+var_10]
0x1400225a4  mov     qword ptr [rbp+var_20], rax
0x1400225a8  lea     r9, asc_1400353E8; ": {}"
0x1400225af  lea     rax, [rbp+var_20]
0x1400225b3  mov     r8d, 3
0x1400225b9  mov     qword ptr [rsp+80h+nSubAuthority2], rax; int
0x1400225be  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400225c3  mov     edx, 47h ; 'G'; void *
0x1400225c8  mov     rcx, [rbp+8]; this
0x1400225cc  lea     r8, aOnecoreBaseCbs_12; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x1400225d3  mov     r9d, ebx; char *
0x1400225d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400225db  jmp     loc_140022894
0x1400225e0  cmp     dword ptr [rdx], 0
0x1400225e3  jz      short loc_14002263C
0x1400225e5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400225ec  mov     ebx, 80070057h
0x1400225f1  mov     [rbp+var_10], ebx
0x1400225f4  test    rcx, rcx
0x1400225f7  jz      short loc_140022635
0x1400225f9  xor     edx, edx
0x1400225fb  lea     r9, aInvalidAclDeny; "Invalid ACL; DenyAccess must not be spe"...
0x140022602  lea     r8d, [rdx+3]
0x140022606  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002260b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022612  lea     rax, [rbp+var_10]
0x140022616  mov     qword ptr [rbp+var_20], rax
0x14002261a  lea     r9, asc_1400353E8; ": {}"
0x140022621  lea     rax, [rbp+var_20]
0x140022625  mov     r8d, 3
0x14002262b  mov     qword ptr [rsp+80h+nSubAuthority2], rax
0x140022630  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022635  mov     edx, 48h ; 'H'
0x14002263a  jmp     short loc_1400225C8
0x14002263c  cmp     dword ptr [rdx+4], 0
0x140022640  jz      short loc_14002269C
0x140022642  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022649  mov     ebx, 80070057h
0x14002264e  mov     [rbp+var_10], ebx
0x140022651  test    rcx, rcx
0x140022654  jz      short loc_140022692
0x140022656  xor     edx, edx
0x140022658  lea     r9, aInvalidAclDwac; "Invalid ACL; dwAccessMask must not be s"...
0x14002265f  lea     r8d, [rdx+3]
0x140022663  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140022668  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002266f  lea     rax, [rbp+var_10]
0x140022673  mov     qword ptr [rbp+var_20], rax
0x140022677  lea     r9, asc_1400353E8; ": {}"
0x14002267e  lea     rax, [rbp+var_20]
0x140022682  mov     r8d, 3
0x140022688  mov     qword ptr [rsp+80h+nSubAuthority2], rax
0x14002268d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140022692  mov     edx, 49h ; 'I'
0x140022697  jmp     loc_1400225C8
0x14002269c  lea     rax, [rdx+8]
0x1400226a0  cmp     qword ptr [rax], 0
0x1400226a4  jz      short loc_1400226FF
0x1400226a6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400226ad  mov     ebx, 80004001h
0x1400226b2  mov     [rbp+var_10], ebx
0x1400226b5  test    rcx, rcx
0x1400226b8  jz      short loc_1400226F5
0x1400226ba  lea     r9, aFailedToGetSid; "Failed to get SID for account: {}"
0x1400226c1  mov     qword ptr [rsp+80h+nSubAuthority2], rax
0x1400226c6  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400226cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400226d2  lea     rax, [rbp+var_10]
0x1400226d6  mov     qword ptr [rbp+var_20], rax
0x1400226da  lea     r9, asc_1400353E8; ": {}"
0x1400226e1  lea     rax, [rbp+var_20]
0x1400226e5  mov     r8d, 3
0x1400226eb  mov     qword ptr [rsp+80h+nSubAuthority2], rax
0x1400226f0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400226f5  mov     edx, 4Dh ; 'M'
0x1400226fa  jmp     loc_1400225C8
0x1400226ff  mov     r9d, [rdx+1Ch]; nSubAuthority1
0x140022703  lea     rax, [rbp+SidToCheck]
0x140022707  mov     r8d, [rdx+18h]; nSubAuthority0
0x14002270b  lea     rcx, [rdx+10h]; pIdentifierAuthority
0x14002270f  mov     [rsp+80h+pSid], rax; pSid
0x140022714  mov     eax, [rdx+34h]
0x140022717  mov     [rsp+80h+nSubAuthority7], eax; nSubAuthority7
0x14002271b  mov     eax, [rdx+30h]
0x14002271e  mov     [rsp+80h+nSubAuthority6], eax; nSubAuthority6
0x140022722  mov     eax, [rdx+2Ch]
0x140022725  mov     [rsp+80h+nSubAuthority5], eax; nSubAuthority5
0x140022729  mov     eax, [rdx+28h]
0x14002272c  mov     [rsp+80h+nSubAuthority4], eax; nSubAuthority4
0x140022730  mov     eax, [rdx+24h]
0x140022733  mov     [rsp+80h+nSubAuthority3], eax; nSubAuthority3
0x140022737  mov     eax, [rdx+20h]
0x14002273a  mov     dl, [rdx+16h]; nSubAuthorityCount
0x14002273d  mov     [rbp+SidToCheck], 0
0x140022745  mov     [rsp+80h+nSubAuthority2], eax; nSubAuthority2
0x140022749  call    cs:__imp_AllocateAndInitializeSid
0x14002274f  test    eax, eax
0x140022751  jnz     loc_1400227E2
0x140022757  call    cs:__imp_GetLastError
0x14002275d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022764  mov     ebx, eax
0x140022766  test    rcx, rcx
0x140022769  jz      short loc_1400227BA
0x14002276b  xor     edx, edx
0x14002276d  lea     r9, aFailedToAlloca_7; "Failed to allocate SID to check members"...
0x140022774  lea     r8d, [rdx+3]
0x140022778  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002277d  test    ebx, ebx
0x14002277f  jg      short loc_140022785
0x140022781  mov     eax, ebx
0x140022783  jmp     short loc_14002278D
0x140022785  movzx   eax, bx
0x140022788  or      eax, 80070000h
0x14002278d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022794  lea     r9, a0; ": {0}"
0x14002279b  mov     [rbp+var_10], eax
0x14002279e  mov     r8d, 3
0x1400227a4  lea     rax, [rbp+var_10]
0x1400227a8  mov     qword ptr [rbp+var_20], rax
0x1400227ac  lea     rax, [rbp+var_20]
0x1400227b0  mov     qword ptr [rsp+80h+nSubAuthority2], rax; unsigned int
0x1400227b5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400227ba  test    ebx, ebx
0x1400227bc  jz      short loc_1400227DB
0x1400227be  mov     rcx, [rbp+8]; this
0x1400227c2  lea     r8, aOnecoreBaseCbs_12; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x1400227c9  mov     r9d, ebx; char *
0x1400227cc  mov     edx, 5Eh ; '^'; void *
0x1400227d1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400227d6  jmp     loc_140022896
0x1400227db  xor     eax, eax
0x1400227dd  jmp     loc_140022896
0x1400227e2  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1400227e6  lea     r8, [rbp+IsMember]; IsMember
0x1400227ea  mov     rcx, rbx; TokenHandle
0x1400227ed  call    cs:__imp_CheckTokenMembership
0x1400227f3  test    eax, eax
0x1400227f5  jnz     loc_140022880
0x1400227fb  call    cs:__imp_GetLastError
0x140022801  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022808  mov     ebx, eax
0x14002280a  test    rcx, rcx
0x14002280d  jz      short loc_14002285E
0x14002280f  xor     edx, edx
0x140022811  lea     r9, aFailedToCheckM; "Failed to check membership"
0x140022818  lea     r8d, [rdx+3]
0x14002281c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140022821  test    ebx, ebx
0x140022823  jg      short loc_140022829
0x140022825  mov     eax, ebx
0x140022827  jmp     short loc_140022831
0x140022829  movzx   eax, bx
0x14002282c  or      eax, 80070000h
0x140022831  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140022838  lea     r9, a0; ": {0}"
0x14002283f  mov     [rbp+var_10], eax
0x140022842  mov     r8d, 3
0x140022848  lea     rax, [rbp+var_10]
0x14002284c  mov     qword ptr [rbp+var_20], rax
0x140022850  lea     rax, [rbp+var_20]
0x140022854  mov     qword ptr [rsp+80h+nSubAuthority2], rax; unsigned int
0x140022859  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002285e  test    ebx, ebx
0x140022860  jz      short loc_14002287C
0x140022862  mov     rcx, [rbp+8]; this
0x140022866  lea     r8, aOnecoreBaseCbs_12; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x14002286d  mov     r9d, ebx; char *
0x140022870  mov     edx, 63h ; 'c'; void *
0x140022875  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14002287a  jmp     short loc_140022888
0x14002287c  xor     ebx, ebx
0x14002287e  jmp     short loc_14002288A
0x140022880  xor     eax, eax
0x140022882  cmp     [rbp+IsMember], eax
0x140022885  setz    al
0x140022888  mov     ebx, eax
0x14002288a  mov     rcx, [rbp+SidToCheck]; pSid
0x14002288e  call    cs:__imp_FreeSid
0x140022894  mov     eax, ebx
0x140022896  mov     rcx, [rbp+var_8]
0x14002289a  xor     rcx, rsp; StackCookie
0x14002289d  call    __security_check_cookie
0x1400228a2  mov     rbx, [rsp+80h+arg_10]
0x1400228aa  add     rsp, 80h
0x1400228b1  pop     rbp
0x1400228b2  retn
```
