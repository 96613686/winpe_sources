# CDownloadSession::MakeRequest(wchar_t const *,WinHttpRequestVerbType,void *,wchar_t const *,ulong)

- ea: `0x140031d1c`
- end: `0x1400320ad`
- name: `?MakeRequest@CDownloadSession@@AEAAJPEB_WW4WinHttpRequestVerbType@@PEAX0K@Z`
- size: `913`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140030dd8`
- `0x1400318f8`

## callees

- `0x1400154b4`
- `0x14002cbd8`
- `0x140031d1c`
- `0x14003261c`
- `0x140039278`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031f56`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140031dd3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140031dd3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140031e6d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140031f4c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140031e6d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140031f4c`
- `WINHTTP!WinHttpOpenRequest` at `0x140031eb8`
- `WINHTTP!WinHttpOpenRequest` at `0x140031eb8`
- `WINHTTP!WinHttpQueryOption` at `0x140031fea`
- `WINHTTP!WinHttpQueryOption` at `0x140031fea`
- `WINHTTP!WinHttpSetOption` at `0x140031e3c`
- `WINHTTP!WinHttpSetOption` at `0x140031f36`
- `WINHTTP!WinHttpSetOption` at `0x140031e3c`
- `WINHTTP!WinHttpSetOption` at `0x140031f36`
- `CRYPT32!CertFreeCertificateContext` at `0x14003201f`
- `CRYPT32!CertFreeCertificateContext` at `0x14003201f`

## string_xrefs

- `0x140031ee2`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`

## pseudocode

```c
__int64 __fastcall CDownloadSession::MakeRequest(
        __int64 a1,
        const wchar_t *a2,
        unsigned int a3,
        __int64 a4,
        wchar_t *a5,
        unsigned int a6)
{
  __int64 v6; // rbx
  int v9; // ebx
  const wchar_t *v10; // rcx
  void *v11; // rcx
  bool v12; // si
  BOOL v13; // eax
  signed int v14; // eax
  void *v15; // rcx
  signed int LastError; // eax
  HINTERNET v17; // rax
  HKEY v18; // rcx
  const wchar_t *v19; // r8
  void *v20; // rcx
  void *v21; // rcx
  int v22; // ecx
  LPCWSTR pwszReferrer; // [rsp+20h] [rbp-60h]
  wchar_t *dwFlags; // [rsp+30h] [rbp-50h]
  unsigned int v26[2]; // [rsp+38h] [rbp-48h]
  unsigned int v27; // [rsp+40h] [rbp-40h]
  void *v28; // [rsp+48h] [rbp-38h]
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp-30h] BYREF
  int Buffer; // [rsp+58h] [rbp-28h] BYREF
  LPCWSTR ppwszAcceptTypes[2]; // [rsp+60h] [rbp-20h] BYREF

  v6 = (int)a3;
  ppwszAcceptTypes[0] = L"*/*";
  ppwszAcceptTypes[1] = 0;
  if ( a3 > 1 )
    return (unsigned int)-2147024809;
  v10 = L"NULL";
  if ( !a3 )
    v10 = L"HEAD";
  *(_QWORD *)v26 = *(_QWORD *)(a1 + 40);
  dwFlags = (wchar_t *)v10;
  WUTrace(0, 0, 32, 5, 0, L"WinHttp: Making %ls request for %ls");
  if ( !*(_QWORD *)(a1 + 16) )
  {
    v11 = *(void **)(a1 + 120);
    v12 = 0;
    if ( v11 )
    {
      v13 = ImpersonateLoggedOnUser(v11);
      v12 = v13;
      if ( !v13 )
        goto LABEL_8;
    }
    if ( (*(_BYTE *)(a1 + 188) & 4) == 0
      || (*(_DWORD *)(a1 + 160) & 0x800000) == 0
      || *(_DWORD *)(a1 + 180)
      || (v15 = *(void **)a1, Buffer = 2048, WinHttpSetOption(v15, 0x54u, &Buffer, 4u)) )
    {
      v17 = WinHttpOpenRequest(
              *(HINTERNET *)(a1 + 8),
              (LPCWSTR)(&CDownloadSession::c_WinhttpRequestVerbs)[v6],
              *(LPCWSTR *)(a1 + 40),
              0,
              0,
              ppwszAcceptTypes,
              *(_DWORD *)(a1 + 160));
      *(_QWORD *)(a1 + 16) = v17;
      if ( v17 )
      {
        if ( (*(_DWORD *)(a1 + 160) & 0x800000) == 0 )
        {
LABEL_29:
          *(_DWORD *)(a1 + 24) = v6;
          if ( v12 && !RevertToSelf() )
            GetLastError();
          goto LABEL_32;
        }
        Buffer = 0;
        ReadDwordPolicyAsBool(v18, L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate", v19, &Buffer);
        if ( Buffer )
        {
          WUTrace(0, 0, 32, 5, 0, L"WinHttp: SSL revocation checking was disabled by policy.");
          goto LABEL_29;
        }
        v20 = *(void **)(a1 + 16);
        Buffer = 1;
        if ( WinHttpSetOption(v20, 0x4Fu, &Buffer, 4u) )
          goto LABEL_29;
      }
    }
    LastError = GetLastError();
    v9 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v9 = LastError;
    if ( v9 >= 0 )
      v9 = -2147418113;
    if ( v12 && !RevertToSelf() )
      GetLastError();
    return (unsigned int)v9;
  }
LABEL_32:
  v9 = SendRequestWithAuthRetry(
         *(void **)(a1 + 120),
         a2,
         *(void **)a1,
         *(void **)(a1 + 16),
         a5,
         a6,
         dwFlags,
         v26[0],
         v27,
         v28);
  if ( v9 < 0 )
  {
    LODWORD(pwszReferrer) = v9;
    WUTrace(0, 0, 32, 3, pwszReferrer, L"WinHttp: SendRequestWithAuthRetry using proxy failed for <%ws>");
    return (unsigned int)v9;
  }
  if ( (*(_DWORD *)(a1 + 160) & 0x800000) != 0 && (*(_BYTE *)(a1 + 188) & 7) != 0 )
  {
    v21 = *(void **)(a1 + 16);
    pCertContext = 0;
    Buffer = 8;
    if ( !WinHttpQueryOption(v21, 0x4Eu, &pCertContext, (LPDWORD)&Buffer) )
    {
LABEL_8:
      v14 = GetLastError();
      v9 = (unsigned __int16)v14 | 0x80070000;
      if ( v14 <= 0 )
        v9 = v14;
      if ( v9 >= 0 )
        return (unsigned int)-2147418113;
      return (unsigned int)v9;
    }
    if ( *(_DWORD *)(a1 + 180) )
      LOBYTE(v22) = 0;
    else
      v22 = *(_DWORD *)(a1 + 188);
    v9 = CheckSSLCertificateTrustImp(v22, pCertContext);
    if ( pCertContext )
      CertFreeCertificateContext(pCertContext);
    if ( *(_DWORD *)(a1 + 176) && v9 == -2143485942 )
    {
      LODWORD(pwszReferrer) = -2143485942;
      WUTrace(0, 0, 32, 5, pwszReferrer, L"WinHttp: Downloaded on weak SSL");
      v9 = 0;
      *(_DWORD *)(a1 + 220) = 1;
    }
    else if ( v9 < 0 )
    {
      LODWORD(pwszReferrer) = v9;
      WUTrace(0, 0, 32, 5, pwszReferrer, L"WinHttp: CheckSSLCertificateTrust failed");
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140031d1c  push    rbp
0x140031d1e  push    rbx
0x140031d1f  push    rsi
0x140031d20  push    rdi
0x140031d21  push    r13
0x140031d23  push    r14
0x140031d25  push    r15
0x140031d27  mov     rbp, rsp
0x140031d2a  sub     rsp, 80h
0x140031d31  mov     rax, cs:__security_cookie
0x140031d38  xor     rax, rsp
0x140031d3b  mov     [rbp+var_10], rax
0x140031d3f  mov     r15, [rbp+arg_20]
0x140031d43  lea     rax, asc_14006B4C8; "*/*"
0x140031d4a  movsxd  rbx, r8d
0x140031d4d  mov     r14, rdx
0x140031d50  mov     [rbp+var_20], rax
0x140031d54  mov     rdi, rcx
0x140031d57  mov     [rbp+var_18], 0
0x140031d5f  cmp     ebx, 1
0x140031d62  jbe     short loc_140031D6E
0x140031d64  mov     ebx, 80070057h
0x140031d69  jmp     loc_14003208D
0x140031d6e  test    r8d, r8d
0x140031d71  lea     rax, aHead; "HEAD"
0x140031d78  mov     r9d, 5
0x140031d7e  lea     rcx, aNull; "NULL"
0x140031d85  cmovz   rcx, rax
0x140031d89  mov     rax, [rdi+28h]
0x140031d8d  mov     qword ptr [rsp+80h+var_48], rax; unsigned int
0x140031d92  xor     edx, edx
0x140031d94  mov     qword ptr [rsp+80h+dwFlags], rcx
0x140031d99  lea     rax, aWinhttpMakingL; "WinHttp: Making %ls request for %ls"
0x140031da0  lea     r13d, [r9+1Bh]
0x140031da4  mov     [rsp+80h+ppwszAcceptTypes], rax
0x140031da9  mov     r8d, r13d
0x140031dac  mov     [rsp+80h+pwszReferrer], 0
0x140031db5  xor     ecx, ecx
0x140031db7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140031dbc  cmp     qword ptr [rdi+10h], 0
0x140031dc1  jnz     loc_140031F5C
0x140031dc7  mov     rcx, [rdi+78h]; hToken
0x140031dcb  xor     sil, sil
0x140031dce  test    rcx, rcx
0x140031dd1  jz      short loc_140031E06
0x140031dd3  call    cs:__imp_ImpersonateLoggedOnUser
0x140031dd9  test    eax, eax
0x140031ddb  setnz   sil
0x140031ddf  test    eax, eax
0x140031de1  jnz     short loc_140031E06
0x140031de3  call    cs:__imp_GetLastError
0x140031de9  movzx   ebx, ax
0x140031dec  or      ebx, 80070000h
0x140031df2  test    eax, eax
0x140031df4  cmovle  ebx, eax
0x140031df7  mov     eax, 8000FFFFh
0x140031dfc  test    ebx, ebx
0x140031dfe  cmovns  ebx, eax
0x140031e01  jmp     loc_14003208D
0x140031e06  test    byte ptr [rdi+0BCh], 4
0x140031e0d  jz      short loc_140031E86
0x140031e0f  test    dword ptr [rdi+0A0h], 800000h
0x140031e19  jz      short loc_140031E86
0x140031e1b  cmp     dword ptr [rdi+0B4h], 0
0x140031e22  jnz     short loc_140031E86
0x140031e24  mov     rcx, [rdi]; hInternet
0x140031e27  lea     r8, [rbp+Buffer]; lpBuffer
0x140031e2b  mov     r9d, 4; dwBufferLength
0x140031e31  mov     [rbp+Buffer], 800h
0x140031e38  lea     edx, [r9+50h]; dwOption
0x140031e3c  call    cs:__imp_WinHttpSetOption
0x140031e42  test    eax, eax
0x140031e44  jnz     short loc_140031E86
0x140031e46  call    cs:__imp_GetLastError
0x140031e4c  movzx   ebx, ax
0x140031e4f  or      ebx, 80070000h
0x140031e55  test    eax, eax
0x140031e57  cmovle  ebx, eax
0x140031e5a  mov     eax, 8000FFFFh
0x140031e5f  test    ebx, ebx
0x140031e61  cmovns  ebx, eax
0x140031e64  test    sil, sil
0x140031e67  jz      loc_14003208D
0x140031e6d  call    cs:__imp_RevertToSelf
0x140031e73  test    eax, eax
0x140031e75  jnz     loc_14003208D
0x140031e7b  call    cs:__imp_GetLastError
0x140031e81  jmp     loc_14003208D
0x140031e86  mov     eax, [rdi+0A0h]
0x140031e8c  lea     rcx, ?c_WinhttpRequestVerbs@CDownloadSession@@0QBQEB_WB; wchar_t const * const near * const CDownloadSession::c_WinhttpRequestVerbs
0x140031e93  mov     rdx, [rcx+rbx*8]; pwszVerb
0x140031e97  xor     r9d, r9d; pwszVersion
0x140031e9a  mov     r8, [rdi+28h]; pwszObjectName
0x140031e9e  mov     rcx, [rdi+8]; hConnect
0x140031ea2  mov     [rsp+80h+dwFlags], eax; void *
0x140031ea6  lea     rax, [rbp+var_20]
0x140031eaa  mov     [rsp+80h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x140031eaf  mov     [rsp+80h+pwszReferrer], 0; pwszReferrer
0x140031eb8  call    cs:__imp_WinHttpOpenRequest
0x140031ebe  mov     [rdi+10h], rax
0x140031ec2  test    rax, rax
0x140031ec5  jz      loc_140031E46
0x140031ecb  test    dword ptr [rdi+0A0h], 800000h
0x140031ed5  jz      short loc_140031F44
0x140031ed7  lea     r9, [rbp+Buffer]; int *
0x140031edb  mov     [rbp+Buffer], 0
0x140031ee2  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x140031ee9  call    ?ReadDwordPolicyAsBool@@YAJPEAUHKEY__@@PEB_W1PEAH@Z; ReadDwordPolicyAsBool(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x140031eee  cmp     [rbp+Buffer], 0
0x140031ef2  jz      short loc_140031F1D
0x140031ef4  lea     rax, aWinhttpSslRevo; "WinHttp: SSL revocation checking was di"...
0x140031efb  mov     r9d, 5
0x140031f01  mov     [rsp+80h+ppwszAcceptTypes], rax
0x140031f06  mov     r8d, r13d
0x140031f09  xor     edx, edx
0x140031f0b  mov     [rsp+80h+pwszReferrer], 0
0x140031f14  xor     ecx, ecx
0x140031f16  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140031f1b  jmp     short loc_140031F44
0x140031f1d  mov     rcx, [rdi+10h]; hInternet
0x140031f21  lea     r8, [rbp+Buffer]; lpBuffer
0x140031f25  mov     r9d, 4; dwBufferLength
0x140031f2b  mov     [rbp+Buffer], 1
0x140031f32  lea     edx, [r9+4Bh]; dwOption
0x140031f36  call    cs:__imp_WinHttpSetOption
0x140031f3c  test    eax, eax
0x140031f3e  jz      loc_140031E46
0x140031f44  mov     [rdi+18h], ebx
0x140031f47  test    sil, sil
0x140031f4a  jz      short loc_140031F5C
0x140031f4c  call    cs:__imp_RevertToSelf
0x140031f52  test    eax, eax
0x140031f54  jnz     short loc_140031F5C
0x140031f56  call    cs:__imp_GetLastError
0x140031f5c  mov     eax, [rbp+arg_28]
0x140031f5f  mov     rdx, r14; wchar_t *
0x140031f62  mov     r9, [rdi+10h]; void *
0x140031f66  mov     r8, [rdi]; void *
0x140031f69  mov     rcx, [rdi+78h]; void *
0x140031f6d  mov     dword ptr [rsp+80h+ppwszAcceptTypes], eax; unsigned int
0x140031f71  mov     [rsp+80h+pwszReferrer], r15; wchar_t *
0x140031f76  call    ?SendRequestWithAuthRetry@@YAJPEAXPEB_W001K0KK0@Z; SendRequestWithAuthRetry(void *,wchar_t const *,void *,void *,wchar_t const *,ulong,void *,ulong,ulong,void *)
0x140031f7b  mov     ebx, eax
0x140031f7d  test    eax, eax
0x140031f7f  jns     short loc_140031FAD
0x140031f81  lea     rax, aWinhttpSendreq_0; "WinHttp: SendRequestWithAuthRetry using"...
0x140031f88  mov     qword ptr [rsp+80h+dwFlags], r14
0x140031f8d  mov     [rsp+80h+ppwszAcceptTypes], rax
0x140031f92  mov     r9d, 3
0x140031f98  mov     r8d, r13d
0x140031f9b  mov     dword ptr [rsp+80h+pwszReferrer], ebx
0x140031f9f  xor     edx, edx
0x140031fa1  xor     ecx, ecx
0x140031fa3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140031fa8  jmp     loc_14003208D
0x140031fad  test    dword ptr [rdi+0A0h], 800000h
0x140031fb7  jz      loc_14003208D
0x140031fbd  test    byte ptr [rdi+0BCh], 7
0x140031fc4  jz      loc_14003208D
0x140031fca  mov     rcx, [rdi+10h]; hInternet
0x140031fce  lea     r9, [rbp+Buffer]; lpdwBufferLength
0x140031fd2  lea     r8, [rbp+pCertContext]; lpBuffer
0x140031fd6  mov     [rbp+pCertContext], 0
0x140031fde  mov     edx, 4Eh ; 'N'; dwOption
0x140031fe3  mov     [rbp+Buffer], 8
0x140031fea  call    cs:__imp_WinHttpQueryOption
0x140031ff0  test    eax, eax
0x140031ff2  jz      loc_140031DE3
0x140031ff8  cmp     dword ptr [rdi+0B4h], 0
0x140031fff  jz      short loc_140032005
0x140032001  xor     ecx, ecx
0x140032003  jmp     short loc_14003200B
0x140032005  mov     ecx, [rdi+0BCh]; unsigned int
0x14003200b  mov     rdx, [rbp+pCertContext]; struct _CERT_CONTEXT *
0x14003200f  call    ?CheckSSLCertificateTrustImp@@YAJKPEBU_CERT_CONTEXT@@_N@Z; CheckSSLCertificateTrustImp(ulong,_CERT_CONTEXT const *,bool)
0x140032014  mov     rcx, [rbp+pCertContext]; pCertContext
0x140032018  mov     ebx, eax
0x14003201a  test    rcx, rcx
0x14003201d  jz      short loc_140032025
0x14003201f  call    cs:__imp_CertFreeCertificateContext
0x140032025  cmp     dword ptr [rdi+0B0h], 0
0x14003202c  jz      short loc_140032067
0x14003202e  mov     ecx, 803D000Ah
0x140032033  cmp     ebx, ecx
0x140032035  jnz     short loc_140032067
0x140032037  lea     rax, aWinhttpDownloa_0; "WinHttp: Downloaded on weak SSL"
0x14003203e  mov     r9d, 5
0x140032044  mov     [rsp+80h+ppwszAcceptTypes], rax
0x140032049  mov     r8d, r13d
0x14003204c  mov     dword ptr [rsp+80h+pwszReferrer], ecx
0x140032050  xor     edx, edx
0x140032052  xor     ecx, ecx
0x140032054  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140032059  xor     ebx, ebx
0x14003205b  mov     dword ptr [rdi+0DCh], 1
0x140032065  jmp     short loc_14003208D
0x140032067  test    ebx, ebx
0x140032069  jns     short loc_14003208D
0x14003206b  lea     rax, aWinhttpCheckss; "WinHttp: CheckSSLCertificateTrust faile"...
0x140032072  mov     r9d, 5
0x140032078  mov     [rsp+80h+ppwszAcceptTypes], rax
0x14003207d  mov     r8d, r13d
0x140032080  xor     edx, edx
0x140032082  mov     dword ptr [rsp+80h+pwszReferrer], ebx
0x140032086  xor     ecx, ecx
0x140032088  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003208d  mov     eax, ebx
0x14003208f  mov     rcx, [rbp+var_10]
0x140032093  xor     rcx, rsp; StackCookie
0x140032096  call    __security_check_cookie
0x14003209b  add     rsp, 80h
0x1400320a2  pop     r15
0x1400320a4  pop     r14
0x1400320a6  pop     r13
0x1400320a8  pop     rdi
0x1400320a9  pop     rsi
0x1400320aa  pop     rbx
0x1400320ab  pop     rbp
0x1400320ac  retn
```
