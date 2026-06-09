# GetUserSidFromToken

- ea: `0x18004dd18`
- end: `0x18004e1f8`
- name: `GetUserSidFromToken`
- size: `1248`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004da0c`
- `0x1800532d4`
- `0x18005857c`
- `0x1801c1c0c`

## callees

- `0x18004dd18`
- `0x18004f454`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1801026fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004de2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004de2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e0a5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004e091`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004e091`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004dfb3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004dfb3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e034`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e034`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004de17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004df09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004de17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004df09`

## string_xrefs

- `0x18004dd59`: `No token specified`
- `0x18004df3c`: `Failed to get token information for user token.`
- `0x18004dfdf`: `Invalid SID returned from user token information.`
- `0x18004ddbe`: `No sid result specified`
- `0x18004de53`: `Failed to determine size of token information for user token.`
- `0x18004e187`: `Failed to determine size of token information for user token.`
- `0x18004e0c4`: `Failed to copy SID to new SID`

## pseudocode

```c
int __fastcall GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  signed int LastError; // ebx
  unsigned int v7; // eax
  __int64 v9; // rdx
  PSID *v10; // rbx
  signed int v11; // ebx
  unsigned int v12; // eax
  DWORD LengthSid; // eax
  DWORD v14; // edi
  PSID v15; // r8
  PSID v16; // rbx
  signed int v17; // ebx
  unsigned int v18; // eax
  unsigned int ReturnLength; // [rsp+20h] [rbp-40h]
  PSID pDestinationSid; // [rsp+30h] [rbp-30h] BYREF
  LPVOID TokenInformation; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v22[2]; // [rsp+40h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+48h] [rbp-18h] BYREF
  int v24; // [rsp+4Ch] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( !TokenHandle )
  {
    v4 = -2147024809;
    v24 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No token specified");
      TokenInformation = &v24;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&TokenInformation);
    }
    v5 = 182;
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
      (const char *)v4,
      ReturnLength);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    v24 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No sid result specified");
      TokenInformation = &v24;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&TokenInformation);
    }
    v5 = 183;
    goto LABEL_52;
  }
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v4 = -2147418113;
    v24 = -2147418113;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to determine size of token information for user token.");
      *(_QWORD *)v22 = &v24;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v22);
    }
    v5 = 198;
    goto LABEL_52;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to determine size of token information for user token.");
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      else
        v7 = LastError;
      v24 = v7;
      TokenInformation = &v24;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)&TokenInformation);
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xC0,
               (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
               (const char *)(unsigned int)LastError,
               ReturnLength);
    return 0;
  }
  TokenInformation = 0;
  if ( !Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(
          &TokenInformation,
          TokenInformationLength) )
  {
    v4 = -2147024882;
    v9 = 202;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
      (const char *)v4,
      ReturnLength);
    goto LABEL_46;
  }
  v10 = (PSID *)TokenInformation;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    if ( !IsValidSid(*v10) )
    {
      v4 = -2147418113;
      v24 = -2147418113;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid SID returned from user token information.");
        pDestinationSid = &v24;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&pDestinationSid);
      }
      v9 = 209;
      goto LABEL_32;
    }
    LengthSid = GetLengthSid(*v10);
    pDestinationSid = 0;
    v14 = LengthSid;
    if ( Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(&pDestinationSid, LengthSid) )
    {
      v15 = *v10;
      v16 = pDestinationSid;
      if ( CopySid(v14, pDestinationSid, v15) )
      {
        pDestinationSid = 0;
        *a2 = v16;
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&pDestinationSid);
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&TokenInformation);
        return 0;
      }
      v17 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy SID to new SID");
        if ( v17 > 0 )
          v18 = (unsigned __int16)v17 | 0x80070000;
        else
          v18 = v17;
        v24 = v18;
        *(_QWORD *)v22 = &v24;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v22);
      }
      if ( !v17 )
      {
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&pDestinationSid);
LABEL_45:
        v4 = 0;
        goto LABEL_46;
      }
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xD8,
             (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
             (const char *)(unsigned int)v17,
             ReturnLength);
    }
    else
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
        (const char *)0x8007000ELL,
        ReturnLength);
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&pDestinationSid);
    goto LABEL_46;
  }
  v11 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get token information for user token.");
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    else
      v12 = v11;
    v24 = v12;
    pDestinationSid = &v24;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {0}",
      (__int64)&pDestinationSid);
  }
  if ( !v11 )
    goto LABEL_45;
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0xCF,
         (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
         (const char *)(unsigned int)v11,
         ReturnLength);
LABEL_46:
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&TokenInformation);
  return v4;
}

```

## disassembly

```asm
0x18004dd18  mov     [rsp-18h+arg_10], rbx
0x18004dd1d  push    rbp
0x18004dd1e  push    rsi
0x18004dd1f  push    rdi
0x18004dd20  mov     rbp, rsp
0x18004dd23  sub     rsp, 60h
0x18004dd27  mov     rax, cs:__security_cookie
0x18004dd2e  xor     rax, rsp
0x18004dd31  mov     [rbp+var_10], rax
0x18004dd35  mov     rsi, rdx
0x18004dd38  mov     rdi, rcx
0x18004dd3b  test    rcx, rcx
0x18004dd3e  jnz     short loc_18004DD9D
0x18004dd40  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dd47  mov     ebx, 80070057h
0x18004dd4c  mov     [rbp+var_14], ebx
0x18004dd4f  test    rcx, rcx
0x18004dd52  jz      short loc_18004DD93
0x18004dd54  mov     edi, 3
0x18004dd59  lea     r9, aNoTokenSpecifi; "No token specified"
0x18004dd60  mov     r8d, edi
0x18004dd63  xor     edx, edx
0x18004dd65  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004dd6a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dd71  lea     rax, [rbp+var_14]
0x18004dd75  mov     [rbp+TokenInformation], rax
0x18004dd79  lea     r9, asc_1802EE7AC; ": {}"
0x18004dd80  lea     rax, [rbp+TokenInformation]
0x18004dd84  mov     r8d, edi
0x18004dd87  mov     dl, 1
0x18004dd89  mov     qword ptr [rsp+60h+ReturnLength], rax
0x18004dd8e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004dd93  mov     edx, 0B6h
0x18004dd98  jmp     loc_18004E1C6
0x18004dd9d  test    rsi, rsi
0x18004dda0  jnz     short loc_18004DDFD
0x18004dda2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dda9  mov     ebx, 80004003h
0x18004ddae  mov     [rbp+var_14], ebx
0x18004ddb1  test    rcx, rcx
0x18004ddb4  jz      short loc_18004DDF3
0x18004ddb6  lea     edi, [rsi+3]
0x18004ddb9  xor     edx, edx
0x18004ddbb  mov     r8d, edi
0x18004ddbe  lea     r9, aNoSidResultSpe; "No sid result specified"
0x18004ddc5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004ddca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ddd1  lea     rax, [rbp+var_14]
0x18004ddd5  mov     [rbp+TokenInformation], rax
0x18004ddd9  lea     r9, asc_1802EE7AC; ": {}"
0x18004dde0  lea     rax, [rbp+TokenInformation]
0x18004dde4  mov     r8d, edi
0x18004dde7  mov     dl, 1
0x18004dde9  mov     qword ptr [rsp+60h+ReturnLength], rax
0x18004ddee  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004ddf3  mov     edx, 0B7h
0x18004ddf8  jmp     loc_18004E1C6
0x18004ddfd  xor     r9d, r9d; TokenInformationLength
0x18004de00  mov     [rbp+TokenInformationLength], 0
0x18004de07  lea     rax, [rbp+TokenInformationLength]
0x18004de0b  xor     r8d, r8d; TokenInformation
0x18004de0e  mov     qword ptr [rsp+60h+ReturnLength], rax; ReturnLength
0x18004de13  lea     edx, [r9+1]; TokenInformationClass
0x18004de17  call    cs:__imp_GetTokenInformation
0x18004de1e  nop     dword ptr [rax+rax+00h]
0x18004de23  test    eax, eax
0x18004de25  jnz     loc_18004E16E
0x18004de2b  call    cs:__imp_GetLastError
0x18004de32  nop     dword ptr [rax+rax+00h]
0x18004de37  mov     ebx, eax
0x18004de39  cmp     eax, 7Ah ; 'z'
0x18004de3c  jz      loc_18004DEC5
0x18004de42  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004de49  test    rcx, rcx
0x18004de4c  jz      short loc_18004DEA0
0x18004de4e  mov     edi, 3
0x18004de53  lea     r9, aFailedToDeterm_5; "Failed to determine size of token infor"...
0x18004de5a  mov     r8d, edi
0x18004de5d  xor     edx, edx
0x18004de5f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004de64  test    ebx, ebx
0x18004de66  jg      short loc_18004DE6C
0x18004de68  mov     eax, ebx
0x18004de6a  jmp     short loc_18004DE74
0x18004de6c  movzx   eax, bx
0x18004de6f  or      eax, 80070000h
0x18004de74  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004de7b  lea     r9, a0; ": {0}"
0x18004de82  mov     [rbp+var_14], eax
0x18004de85  mov     r8d, edi
0x18004de88  lea     rax, [rbp+var_14]
0x18004de8c  mov     dl, 1
0x18004de8e  mov     [rbp+TokenInformation], rax
0x18004de92  lea     rax, [rbp+TokenInformation]
0x18004de96  mov     qword ptr [rsp+60h+ReturnLength], rax; unsigned int
0x18004de9b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004dea0  test    ebx, ebx
0x18004dea2  jz      loc_18004E16A
0x18004dea8  mov     rcx, [rbp+18h]; this
0x18004deac  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x18004deb3  mov     r9d, ebx; char *
0x18004deb6  mov     edx, 0C0h; void *
0x18004debb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004dec0  jmp     loc_18004E1DB
0x18004dec5  mov     edx, [rbp+TokenInformationLength]
0x18004dec8  lea     rcx, [rbp+TokenInformation]
0x18004decc  mov     [rbp+TokenInformation], 0
0x18004ded4  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x18004ded9  test    rax, rax
0x18004dedc  jnz     short loc_18004DEED
0x18004dede  mov     ebx, 8007000Eh
0x18004dee3  mov     edx, 0CAh
0x18004dee8  jmp     loc_18004E019
0x18004deed  mov     rbx, [rbp+TokenInformation]
0x18004def1  lea     rax, [rbp+TokenInformationLength]
0x18004def5  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18004def9  mov     r8, rbx; TokenInformation
0x18004defc  mov     edx, 1; TokenInformationClass
0x18004df01  mov     qword ptr [rsp+60h+ReturnLength], rax; int
0x18004df06  mov     rcx, rdi; TokenHandle
0x18004df09  call    cs:__imp_GetTokenInformation
0x18004df10  nop     dword ptr [rax+rax+00h]
0x18004df15  test    eax, eax
0x18004df17  jnz     loc_18004DFB0
0x18004df1d  call    cs:__imp_GetLastError
0x18004df24  nop     dword ptr [rax+rax+00h]
0x18004df29  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004df30  mov     ebx, eax
0x18004df32  test    rcx, rcx
0x18004df35  jz      short loc_18004DF89
0x18004df37  mov     edi, 3
0x18004df3c  lea     r9, aFailedToGetTok; "Failed to get token information for use"...
0x18004df43  mov     r8d, edi
0x18004df46  xor     edx, edx
0x18004df48  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004df4d  test    ebx, ebx
0x18004df4f  jg      short loc_18004DF55
0x18004df51  mov     eax, ebx
0x18004df53  jmp     short loc_18004DF5D
0x18004df55  movzx   eax, bx
0x18004df58  or      eax, 80070000h
0x18004df5d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004df64  lea     r9, a0; ": {0}"
0x18004df6b  mov     [rbp+var_14], eax
0x18004df6e  mov     r8d, edi
0x18004df71  lea     rax, [rbp+var_14]
0x18004df75  mov     dl, 1
0x18004df77  mov     [rbp+pDestinationSid], rax
0x18004df7b  lea     rax, [rbp+pDestinationSid]
0x18004df7f  mov     qword ptr [rsp+60h+ReturnLength], rax; unsigned int
0x18004df84  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004df89  test    ebx, ebx
0x18004df8b  jz      loc_18004E13D
0x18004df91  mov     rcx, [rbp+18h]; this
0x18004df95  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x18004df9c  mov     r9d, ebx; char *
0x18004df9f  mov     edx, 0CFh; void *
0x18004dfa4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004dfa9  mov     ebx, eax
0x18004dfab  jmp     loc_18004E13F
0x18004dfb0  mov     rcx, [rbx]; pSid
0x18004dfb3  call    cs:__imp_IsValidSid
0x18004dfba  nop     dword ptr [rax+rax+00h]
0x18004dfbf  test    eax, eax
0x18004dfc1  jnz     short loc_18004E031
0x18004dfc3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dfca  mov     ebx, 8000FFFFh
0x18004dfcf  mov     [rbp+var_14], ebx
0x18004dfd2  test    rcx, rcx
0x18004dfd5  jz      short loc_18004E014
0x18004dfd7  lea     edi, [rax+3]
0x18004dfda  xor     edx, edx
0x18004dfdc  mov     r8d, edi
0x18004dfdf  lea     r9, aInvalidSidRetu; "Invalid SID returned from user token in"...
0x18004dfe6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004dfeb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004dff2  lea     rax, [rbp+var_14]
0x18004dff6  mov     [rbp+pDestinationSid], rax
0x18004dffa  lea     r9, asc_1802EE7AC; ": {}"
0x18004e001  lea     rax, [rbp+pDestinationSid]
0x18004e005  mov     r8d, edi
0x18004e008  mov     dl, 1
0x18004e00a  mov     qword ptr [rsp+60h+ReturnLength], rax; int
0x18004e00f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e014  mov     edx, 0D1h; void *
0x18004e019  mov     rcx, [rbp+18h]; this
0x18004e01d  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x18004e024  mov     r9d, ebx; char *
0x18004e027  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e02c  jmp     loc_18004E13F
0x18004e031  mov     rcx, [rbx]; pSid
0x18004e034  call    cs:__imp_GetLengthSid
0x18004e03b  nop     dword ptr [rax+rax+00h]
0x18004e040  lea     rcx, [rbp+pDestinationSid]
0x18004e044  mov     [rbp+pDestinationSid], 0
0x18004e04c  mov     edx, eax
0x18004e04e  mov     edi, eax
0x18004e050  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x18004e055  test    rax, rax
0x18004e058  jnz     short loc_18004E085
0x18004e05a  mov     rcx, [rbp+18h]; this
0x18004e05e  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x18004e065  mov     ebx, 8007000Eh
0x18004e06a  mov     edx, 0D5h; void *
0x18004e06f  mov     r9d, ebx; char *
0x18004e072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e077  lea     rcx, [rbp+pDestinationSid]
0x18004e07b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18004e080  jmp     loc_18004E13F
0x18004e085  mov     r8, [rbx]; pSourceSid
0x18004e088  mov     ecx, edi; nDestinationSidLength
0x18004e08a  mov     rbx, [rbp+pDestinationSid]
0x18004e08e  mov     rdx, rbx; pDestinationSid
0x18004e091  call    cs:__imp_CopySid
0x18004e098  nop     dword ptr [rax+rax+00h]
0x18004e09d  test    eax, eax
0x18004e09f  jnz     loc_18004E14D
0x18004e0a5  call    cs:__imp_GetLastError
0x18004e0ac  nop     dword ptr [rax+rax+00h]
0x18004e0b1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e0b8  mov     ebx, eax
0x18004e0ba  test    rcx, rcx
0x18004e0bd  jz      short loc_18004E111
0x18004e0bf  mov     edi, 3
0x18004e0c4  lea     r9, aFailedToCopySi; "Failed to copy SID to new SID"
0x18004e0cb  mov     r8d, edi
0x18004e0ce  xor     edx, edx
0x18004e0d0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e0d5  test    ebx, ebx
0x18004e0d7  jg      short loc_18004E0DD
0x18004e0d9  mov     eax, ebx
0x18004e0db  jmp     short loc_18004E0E5
0x18004e0dd  movzx   eax, bx
0x18004e0e0  or      eax, 80070000h
0x18004e0e5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e0ec  lea     r9, a0; ": {0}"
0x18004e0f3  mov     [rbp+var_14], eax
0x18004e0f6  mov     r8d, edi
0x18004e0f9  lea     rax, [rbp+var_14]
0x18004e0fd  mov     dl, 1
0x18004e0ff  mov     qword ptr [rbp+var_20], rax
0x18004e103  lea     rax, [rbp+var_20]
0x18004e107  mov     qword ptr [rsp+60h+ReturnLength], rax; unsigned int
0x18004e10c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e111  test    ebx, ebx
0x18004e113  jz      short loc_18004E134
0x18004e115  mov     rcx, [rbp+18h]; this
0x18004e119  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x18004e120  mov     r9d, ebx; char *
0x18004e123  mov     edx, 0D8h; void *
0x18004e128  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e12d  mov     ebx, eax
0x18004e12f  jmp     loc_18004E077
0x18004e134  lea     rcx, [rbp+pDestinationSid]
0x18004e138  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18004e13d  xor     ebx, ebx
0x18004e13f  lea     rcx, [rbp+TokenInformation]
0x18004e143  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18004e148  jmp     loc_18004E1D9
0x18004e14d  lea     rcx, [rbp+pDestinationSid]
0x18004e151  mov     [rbp+pDestinationSid], 0
0x18004e159  mov     [rsi], rbx
0x18004e15c  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18004e161  lea     rcx, [rbp+TokenInformation]
0x18004e165  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18004e16a  xor     eax, eax
0x18004e16c  jmp     short loc_18004E1DB
0x18004e16e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e175  mov     ebx, 8000FFFFh
0x18004e17a  mov     [rbp+var_14], ebx
0x18004e17d  test    rcx, rcx
0x18004e180  jz      short loc_18004E1C1
0x18004e182  mov     edi, 3
0x18004e187  lea     r9, aFailedToDeterm_5; "Failed to determine size of token infor"...
0x18004e18e  mov     r8d, edi
0x18004e191  xor     edx, edx
0x18004e193  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e198  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e19f  lea     rax, [rbp+var_14]
0x18004e1a3  mov     qword ptr [rbp+var_20], rax
0x18004e1a7  lea     r9, asc_1802EE7AC; ": {}"
0x18004e1ae  lea     rax, [rbp+var_20]
0x18004e1b2  mov     r8d, edi
0x18004e1b5  mov     dl, 1
0x18004e1b7  mov     qword ptr [rsp+60h+ReturnLength], rax; int
0x18004e1bc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e1c1  mov     edx, 0C6h; void *
0x18004e1c6  mov     rcx, [rbp+18h]; this
0x18004e1ca  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x18004e1d1  mov     r9d, ebx; char *
0x18004e1d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e1d9  mov     eax, ebx
0x18004e1db  mov     rcx, [rbp+var_10]
0x18004e1df  xor     rcx, rsp; StackCookie
0x18004e1e2  call    __security_check_cookie
0x18004e1e7  mov     rbx, [rsp+60h+arg_10]
0x18004e1ef  add     rsp, 60h
0x18004e1f3  pop     rdi
0x18004e1f4  pop     rsi
0x18004e1f5  pop     rbp
  ... truncated ...
```
