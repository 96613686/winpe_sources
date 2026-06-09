# WSManHttpListenerRequest::ProcessAuthorizationBasicAuth(char const *,ushort,WSManHttpListenerConnection *)

- ea: `0x180059ec0`
- end: `0x18005a5a7`
- name: `?ProcessAuthorizationBasicAuth@WSManHttpListenerRequest@@AEAAXPEBDGPEAVWSManHttpListenerConnection@@@Z`
- size: `1767`
- prototype: `void __fastcall(WSManHttpListenerRequest *this, const char *, unsigned __int16, struct WSManHttpListenerConnection *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180058e84`

## callees

- `0x180005d10`
- `0x180013760`
- `0x180019950`
- `0x180033c90`
- `0x180059ec0`
- `0x18005a8c8`
- `0x1800621e0`
- `0x180071400`
- `0x1800723d4`
- `0x180077490`
- `0x18007e410`
- `0x18008d16c`
- `0x18008e040`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x180122180`
- `0x1801ba1b0`

## import_xrefs

- `msvcrt!strchr` at `0x18005a10e`
- `msvcrt!strchr` at `0x18005a10e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a484`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005a47a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005a47a`
- `ntdll!RtlFreeUnicodeString` at `0x18005a1da`
- `ntdll!RtlFreeUnicodeString` at `0x18005a20b`
- `ntdll!RtlFreeUnicodeString` at `0x18005a1da`
- `ntdll!RtlFreeUnicodeString` at `0x18005a20b`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18005a169`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18005a17b`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18005a169`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18005a17b`
- `CRYPT32!CryptStringToBinaryA` at `0x180059fb9`
- `CRYPT32!CryptStringToBinaryA` at `0x18005a0ca`
- `CRYPT32!CryptStringToBinaryA` at `0x180059fb9`
- `CRYPT32!CryptStringToBinaryA` at `0x18005a0ca`
- `SspiCli!LogonUserExExW` at `0x18005a1c5`
- `SspiCli!LogonUserExExW` at `0x18005a1c5`

## string_xrefs

- `0x180059f51`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005a34f`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005a3c9`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`

## pseudocode

```c
void __fastcall WSManHttpListenerRequest::ProcessAuthorizationBasicAuth(
        WSManHttpListenerRequest *this,
        const char *a2,
        unsigned __int16 a3,
        struct WSManHttpListenerConnection *a4)
{
  DWORD v5; // r14d
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  const char *v12; // r15
  char *v13; // rax
  const char *v14; // rsi
  int v15; // r14d
  int v16; // r12d
  __int64 Length; // rcx
  PWSTR Buffer; // rax
  __int64 v19; // rax
  DWORD v20; // edi
  __int64 v21; // rax
  int v22; // r14d
  __int64 v23; // rax
  unsigned __int64 v24; // kr00_8
  __int64 v25; // rax
  WCHAR *v26; // rax
  DWORD LastError; // eax
  unsigned int v28; // edi
  void *v29; // rdx
  DWORD pcbBinary; // [rsp+60h] [rbp-A0h] BYREF
  void *v31; // [rsp+68h] [rbp-98h] BYREF
  DWORD pdwFlags; // [rsp+70h] [rbp-90h] BYREF
  DWORD pdwSkip; // [rsp+74h] [rbp-8Ch] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-88h] BYREF
  _UNICODE_STRING Destination; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v36[72]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = a3;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 263, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x12B4u, L"4788", 0x54Fu, 0);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (unsigned __int16)(v5 - 1) > 0x300u )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x400) == 0 )
      goto LABEL_79;
    v9 = 264;
    goto LABEL_78;
  }
  pcbBinary = 0;
  pdwSkip = 0;
  pdwFlags = 0;
  if ( !CryptStringToBinaryA(a2, v5, 1u, 0, &pcbBinary, &pdwSkip, &pdwFlags) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      goto LABEL_79;
    v9 = 265;
LABEL_78:
    WPP_SF_(v8[2], v9, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
LABEL_79:
    WSManHttpListenerRequest::Send401(this, 0, 0);
    return;
  }
  v10 = *((_QWORD *)this + 52);
  if ( v10 )
    v11 = WSManMemory::ReAlloc(v10, pcbBinary + 1, 0, 0);
  else
    v11 = WSManMemory::Alloc(pcbBinary + 1, 0, 0);
  if ( v11 )
  {
    *((_QWORD *)this + 52) = v11;
    *(_BYTE *)(pcbBinary + v11) = 0;
    if ( !CryptStringToBinaryA(a2, v5, 1u, *((BYTE **)this + 52), &pcbBinary, &pdwSkip, &pdwFlags) )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        goto LABEL_79;
      v9 = 267;
      goto LABEL_78;
    }
    v12 = (const char *)*((_QWORD *)this + 52);
    v13 = strchr(v12, 58);
    if ( !v13 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        goto LABEL_79;
      v9 = 268;
      goto LABEL_78;
    }
    *v13 = 0;
    v14 = v13 + 1;
    v31 = 0;
    Destination = 0;
    UnicodeString = 0;
    if ( RtlCreateUnicodeStringFromAsciiz(&Destination, v12) && RtlCreateUnicodeStringFromAsciiz(&UnicodeString, v14) )
    {
      v15 = 1;
      v16 = LogonUserExExW(Destination.Buffer, L".", UnicodeString.Buffer, 3, 0, 0, &v31, 0, 0, 0, 0);
    }
    else
    {
      v16 = 0;
      v15 = 0;
    }
    RtlFreeUnicodeString(&Destination);
    if ( UnicodeString.Length )
    {
      Length = UnicodeString.Length;
      Buffer = UnicodeString.Buffer;
      do
      {
        *(_BYTE *)Buffer = 0;
        Buffer = (PWSTR)((char *)Buffer + 1);
        --Length;
      }
      while ( Length );
    }
    RtlFreeUnicodeString(&UnicodeString);
    if ( v15 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v14[v19] );
      for ( ; v19; --v19 )
        *v14++ = 0;
      if ( v16 )
      {
        if ( a4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
          WSManHttpListenerRequest::s_logonFailure = 0;
          if ( !*(_DWORD *)(*((_QWORD *)this + 14) + 72LL)
            && (int)WSManHttpListener::DecrementUnauthenticatedConnections(*((WSManHttpListener **)this + 10)) > 256 )
          {
            WSManError(
              (wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp",
              0x1357u,
              L"4951",
              0x54Fu,
              0);
          }
          *((_DWORD *)a4 + 18) = 2;
          v21 = -1;
          do
            ++v21;
          while ( v12[v21] );
          v22 = v21 + 1;
          v24 = (unsigned int)(v21 + 1);
          v23 = 2 * v24;
          if ( !is_mul_ok(v24, 2u) )
            v23 = -1;
          v25 = WSManMemory::Alloc(v23, 0, 0);
          AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=((char *)a4 + 184, v25);
          v26 = (WCHAR *)*((_QWORD *)a4 + 23);
          if ( v26 )
          {
            if ( MultiByteToWideChar(3u, 0, v12, -1, v26, v22) )
            {
              *((_QWORD *)a4 + 29) = L"Basic";
              *((_QWORD *)a4 + 28) = *((_QWORD *)a4 + 23);
              *((_QWORD *)a4 + 31) = v31;
              *((_QWORD *)a4 + 32) = (char *)this + 448;
              if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTHENTICATION_DONE) )
                WSMan::LogEvent<unsigned short *,unsigned short *>((struct _EVENT_DESCRIPTOR *)&LOG_WSMAN_AN_AUTHENTICATION_DONE);
              v29 = v31;
              v31 = 0;
              WSManHttpListenerRequest::DoUserAuthzCheck(this, v29, 1);
            }
            else
            {
              LastError = GetLastError();
              v28 = LastError;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  272,
                  &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
                  LastError);
              WSManHttpListenerRequest::SendHttpError(
                this,
                0x1F4u,
                1,
                0,
                0,
                v28,
                L"Failed to convert authentication information to unicode",
                &Class);
            }
          }
          else
          {
            WSManHttpListenerRequest::SendHttpError(
              this,
              0x1F4u,
              1,
              0,
              0,
              0xEu,
              L"Not enough memory to carry out the request",
              &Class);
          }
        }
        else
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp",
            0x134Du,
            L"4941",
            0x54Fu,
            0);
        }
        goto LABEL_39;
      }
      v20 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 270, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v20);
      if ( v20 == 5 )
      {
        WSManHttpListenerRequest::s_logonFailure = 0;
      }
      else if ( !_InterlockedCompareExchange(&WSManHttpListenerRequest::s_logonFailure, 1, 0)
             && (int)StringCchPrintfW(v36, 0x41u, L"%d", v20) >= 0 )
      {
        *(_QWORD *)&UnicodeString.Length = v36;
        EventLog::ReportEventW(2u, 0x7277Fu, 1u, (const unsigned __int16 **)&UnicodeString);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    }
    WSManHttpListenerRequest::Send401(this, 0, 0);
LABEL_39:
    AutoCleanup<AutoHandle,void *>::ReleasePtr(&v31);
    return;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 266, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
  WSManHttpListenerRequest::SendHttpError(
    this,
    0x1F7u,
    1,
    0,
    0,
    0xEu,
    L"Not enough memory to carry out the request",
    &Class);
}

```

## disassembly

```asm
0x180059ec0  push    rbp
0x180059ec2  push    rbx
0x180059ec3  push    rsi
0x180059ec4  push    rdi
0x180059ec5  push    r12
0x180059ec7  push    r13
0x180059ec9  push    r14
0x180059ecb  push    r15
0x180059ecd  lea     rbp, [rsp-48h]
0x180059ed2  sub     rsp, 148h
0x180059ed9  mov     rax, cs:__security_cookie
0x180059ee0  xor     rax, rsp
0x180059ee3  mov     [rbp+80h+var_50], rax
0x180059ee7  mov     rdi, r9
0x180059eea  movzx   r14d, r8w
0x180059eee  mov     rsi, rdx
0x180059ef1  mov     rbx, rcx
0x180059ef4  lea     rax, WPP_GLOBAL_Control
0x180059efb  mov     r15d, 400h
0x180059f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f08  cmp     rcx, rax
0x180059f0b  jz      short loc_180059F32
0x180059f0d  test    [rcx+1Ch], r15d
0x180059f11  jz      short loc_180059F32
0x180059f13  mov     edx, 107h
0x180059f18  mov     r9, rbx
0x180059f1b  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x180059f22  mov     rcx, [rcx+10h]
0x180059f26  call    WPP_SF_q
0x180059f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f32  xor     r13d, r13d
0x180059f35  test    rsi, rsi
0x180059f38  jnz     short loc_180059F64
0x180059f3a  mov     [rsp+180h+pcbBinary], r13; struct IRequestContext *
0x180059f3f  mov     r9d, 54Fh; unsigned int
0x180059f45  lea     r8, a4788; "4788"
0x180059f4c  mov     edx, 12B4h; unsigned int
0x180059f51  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x180059f58  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180059f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f64  movzx   eax, r14w
0x180059f68  mov     r12d, 1
0x180059f6e  sub     ax, r12w
0x180059f72  mov     edx, 300h
0x180059f77  cmp     ax, dx
0x180059f7a  ja      loc_18005A553
0x180059f80  mov     [rsp+180h+var_120], r13d
0x180059f85  mov     [rsp+180h+var_10C], r13d
0x180059f8a  mov     [rsp+180h+var_110], r13d
0x180059f8f  lea     rax, [rsp+180h+var_110]
0x180059f94  mov     [rsp+180h+pdwFlags], rax; pdwFlags
0x180059f99  lea     rax, [rsp+180h+var_10C]
0x180059f9e  mov     [rsp+180h+pdwSkip], rax; pdwSkip
0x180059fa3  lea     rax, [rsp+180h+var_120]
0x180059fa8  mov     [rsp+180h+pcbBinary], rax; pcbBinary
0x180059fad  xor     r9d, r9d; pbBinary
0x180059fb0  mov     r8d, r12d; dwFlags
0x180059fb3  mov     edx, r14d; cchString
0x180059fb6  mov     rcx, rsi; pszString
0x180059fb9  call    cs:__imp_CryptStringToBinaryA
0x180059fbf  test    eax, eax
0x180059fc1  jnz     short loc_180059FEE
0x180059fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180059fca  lea     rax, WPP_GLOBAL_Control
0x180059fd1  cmp     rcx, rax
0x180059fd4  jz      loc_18005A57A
0x180059fda  test    [rcx+1Ch], r15d
0x180059fde  jz      loc_18005A57A
0x180059fe4  mov     edx, 109h
0x180059fe9  jmp     loc_18005A56A
0x180059fee  mov     rcx, [rbx+1A0h]
0x180059ff5  xor     r8d, r8d
0x180059ff8  test    rcx, rcx
0x180059ffb  jnz     short loc_18005A00C
0x180059ffd  mov     ecx, [rsp+180h+var_120]
0x18005a001  inc     ecx
0x18005a003  xor     edx, edx
0x18005a005  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18005a00a  jmp     short loc_18005A01A
0x18005a00c  mov     edx, [rsp+180h+var_120]
0x18005a010  inc     edx
0x18005a012  xor     r9d, r9d
0x18005a015  call    ?ReAlloc@WSManMemory@@SAPEAXPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::ReAlloc(void *,unsigned __int64,int,_NitsFaultMode)
0x18005a01a  mov     rcx, rax
0x18005a01d  test    rax, rax
0x18005a020  jnz     short loc_18005A08D
0x18005a022  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a029  lea     rax, WPP_GLOBAL_Control
0x18005a030  cmp     rcx, rax
0x18005a033  jz      short loc_18005A050
0x18005a035  test    [rcx+1Ch], r15d
0x18005a039  jz      short loc_18005A050
0x18005a03b  mov     edx, 10Ah
0x18005a040  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005a047  mov     rcx, [rcx+10h]
0x18005a04b  call    WPP_SF_
0x18005a050  mov     edx, 1F7h; unsigned __int16
0x18005a055  lea     rax, Class
0x18005a05c  mov     [rsp+180h+var_148], rax; unsigned __int16 *
0x18005a061  lea     rax, aNotEnoughMemor; "Not enough memory to carry out the requ"...
0x18005a068  mov     [rsp+180h+pdwFlags], rax; unsigned __int16 *
0x18005a06d  mov     dword ptr [rsp+180h+pdwSkip], 0Eh; unsigned int
0x18005a075  mov     [rsp+180h+pcbBinary], r13; char *
0x18005a07a  xor     r9d, r9d; unsigned int
0x18005a07d  mov     r8b, r12b; bool
0x18005a080  mov     rcx, rbx; this
0x18005a083  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x18005a088  jmp     loc_18005A587
0x18005a08d  mov     [rbx+1A0h], rcx
0x18005a094  mov     eax, [rsp+180h+var_120]
0x18005a098  mov     [rax+rcx], r13b
0x18005a09c  lea     rax, [rsp+180h+var_110]
0x18005a0a1  mov     [rsp+180h+pdwFlags], rax; pdwFlags
0x18005a0a6  lea     rax, [rsp+180h+var_10C]
0x18005a0ab  mov     [rsp+180h+pdwSkip], rax; pdwSkip
0x18005a0b0  lea     rax, [rsp+180h+var_120]
0x18005a0b5  mov     [rsp+180h+pcbBinary], rax; pcbBinary
0x18005a0ba  mov     r9, [rbx+1A0h]; pbBinary
0x18005a0c1  mov     r8d, r12d; dwFlags
0x18005a0c4  mov     edx, r14d; cchString
0x18005a0c7  mov     rcx, rsi; pszString
0x18005a0ca  call    cs:__imp_CryptStringToBinaryA
0x18005a0d0  test    eax, eax
0x18005a0d2  jnz     short loc_18005A0FF
0x18005a0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a0db  lea     rax, WPP_GLOBAL_Control
0x18005a0e2  cmp     rcx, rax
0x18005a0e5  jz      loc_18005A57A
0x18005a0eb  test    [rcx+1Ch], r15d
0x18005a0ef  jz      loc_18005A57A
0x18005a0f5  mov     edx, 10Bh
0x18005a0fa  jmp     loc_18005A56A
0x18005a0ff  mov     r15, [rbx+1A0h]
0x18005a106  mov     edx, 3Ah ; ':'; Val
0x18005a10b  mov     rcx, r15; Str
0x18005a10e  call    cs:__imp_strchr
0x18005a114  test    rax, rax
0x18005a117  jnz     short loc_18005A147
0x18005a119  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a120  lea     rax, WPP_GLOBAL_Control
0x18005a127  cmp     rcx, rax
0x18005a12a  jz      loc_18005A57A
0x18005a130  test    dword ptr [rcx+1Ch], 400h
0x18005a137  jz      loc_18005A57A
0x18005a13d  mov     edx, 10Ch
0x18005a142  jmp     loc_18005A56A
0x18005a147  mov     [rax], r13b
0x18005a14a  lea     rsi, [rax+1]
0x18005a14e  mov     [rsp+180h+var_118], r13
0x18005a153  xorps   xmm0, xmm0
0x18005a156  movups  xmmword ptr [rbp+80h+Destination.Length], xmm0
0x18005a15a  xorps   xmm1, xmm1
0x18005a15d  movups  xmmword ptr [rsp+180h+UnicodeString.Length], xmm1
0x18005a162  mov     rdx, r15; Source
0x18005a165  lea     rcx, [rbp+80h+Destination]; Destination
0x18005a169  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18005a16f  test    al, al
0x18005a171  jz      short loc_18005A1D0
0x18005a173  mov     rdx, rsi; Source
0x18005a176  lea     rcx, [rsp+180h+UnicodeString]; Destination
0x18005a17b  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18005a181  test    al, al
0x18005a183  jz      short loc_18005A1D0
0x18005a185  mov     r14d, r12d
0x18005a188  mov     [rsp+180h+var_130], r13
0x18005a18d  mov     [rsp+180h+var_138], r13
0x18005a192  mov     [rsp+180h+var_140], r13
0x18005a197  mov     [rsp+180h+var_148], r13
0x18005a19c  lea     rax, [rsp+180h+var_118]
0x18005a1a1  mov     [rsp+180h+pdwFlags], rax
0x18005a1a6  mov     [rsp+180h+pdwSkip], r13
0x18005a1ab  mov     dword ptr [rsp+180h+pcbBinary], r13d
0x18005a1b0  mov     r9d, 3
0x18005a1b6  mov     r8, [rbp+80h+UnicodeString.Buffer]
0x18005a1ba  lea     rdx, asc_1801D9F5C; "."
0x18005a1c1  mov     rcx, [rbp+80h+Destination.Buffer]
0x18005a1c5  call    cs:__imp_LogonUserExExW
0x18005a1cb  mov     r12d, eax
0x18005a1ce  jmp     short loc_18005A1D6
0x18005a1d0  mov     r12d, r13d
0x18005a1d3  mov     r14d, r13d
0x18005a1d6  lea     rcx, [rbp+80h+Destination]; UnicodeString
0x18005a1da  call    cs:__imp_RtlFreeUnicodeString
0x18005a1e0  movzx   eax, [rsp+180h+UnicodeString.Length]
0x18005a1e5  test    ax, ax
0x18005a1e8  jz      short loc_18005A206
0x18005a1ea  mov     ecx, eax
0x18005a1ec  mov     rax, [rbp+80h+UnicodeString.Buffer]
0x18005a1f0  test    rcx, rcx
0x18005a1f3  jz      short loc_18005A206
0x18005a1f5  mov     r8d, 1
0x18005a1fb  mov     [rax], r13b
0x18005a1fe  add     rax, r8
0x18005a201  sub     rcx, r8
0x18005a204  jnz     short loc_18005A1FB
0x18005a206  lea     rcx, [rsp+180h+UnicodeString]; UnicodeString
0x18005a20b  call    cs:__imp_RtlFreeUnicodeString
0x18005a211  test    r14d, r14d
0x18005a214  jnz     short loc_18005A264
0x18005a216  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a21d  lea     rax, WPP_GLOBAL_Control
0x18005a224  cmp     rcx, rax
0x18005a227  jz      short loc_18005A247
0x18005a229  test    dword ptr [rcx+1Ch], 400h
0x18005a230  jz      short loc_18005A247
0x18005a232  mov     edx, 10Dh
0x18005a237  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005a23e  mov     rcx, [rcx+10h]
0x18005a242  call    WPP_SF_
0x18005a247  xor     r8d, r8d; unsigned int
0x18005a24a  xor     edx, edx; char *
0x18005a24c  mov     rcx, rbx; this
0x18005a24f  call    ?Send401@WSManHttpListenerRequest@@IEAAKPEBDK@Z; WSManHttpListenerRequest::Send401(char const *,ulong)
0x18005a254  nop
0x18005a255  lea     rcx, [rsp+180h+var_118]
0x18005a25a  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x18005a25f  jmp     loc_18005A587
0x18005a264  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005a268  inc     rax
0x18005a26b  cmp     [rsi+rax], r13b
0x18005a26f  jnz     short loc_18005A268
0x18005a271  mov     r14d, 1
0x18005a277  test    rax, rax
0x18005a27a  jz      short loc_18005A287
0x18005a27c  mov     [rsi], r13b
0x18005a27f  add     rsi, r14
0x18005a282  sub     rax, r14
0x18005a285  jnz     short loc_18005A27C
0x18005a287  test    r12d, r12d
0x18005a28a  jnz     loc_18005A333
0x18005a290  call    cs:__imp_GetLastError
0x18005a296  mov     edi, eax
0x18005a298  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a29f  lea     rax, WPP_GLOBAL_Control
0x18005a2a6  cmp     rcx, rax
0x18005a2a9  jz      short loc_18005A2CC
0x18005a2ab  test    dword ptr [rcx+1Ch], 400h
0x18005a2b2  jz      short loc_18005A2CC
0x18005a2b4  mov     edx, 10Eh
0x18005a2b9  mov     r9d, edi
0x18005a2bc  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005a2c3  mov     rcx, [rcx+10h]
0x18005a2c7  call    WPP_SF_d
0x18005a2cc  cmp     edi, 5
0x18005a2cf  jz      short loc_18005A327
0x18005a2d1  xor     eax, eax
0x18005a2d3  lock cmpxchg cs:?s_logonFailure@WSManHttpListenerRequest@@0HA, r14d; int WSManHttpListenerRequest::s_logonFailure
0x18005a2dc  jnz     loc_18005A247
0x18005a2e2  mov     r9d, edi
0x18005a2e5  lea     r8, aD; "%d"
0x18005a2ec  mov     edx, 41h ; 'A'; unsigned __int64
0x18005a2f1  lea     rcx, [rbp+80h+var_E0]; unsigned __int16 *
0x18005a2f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005a2fa  test    eax, eax
0x18005a2fc  js      loc_18005A247
0x18005a302  lea     rax, [rbp+80h+var_E0]
0x18005a306  mov     qword ptr [rsp+180h+UnicodeString.Length], rax
0x18005a30b  mov     r8d, r14d; unsigned __int16
0x18005a30e  mov     ecx, 2; unsigned __int16
0x18005a313  lea     r9, [rsp+180h+UnicodeString]; unsigned __int16 **
0x18005a318  mov     edx, 7277Fh; unsigned int
0x18005a31d  call    ?ReportEventW@EventLog@@SAXGKGPEAPEBG@Z; EventLog::ReportEventW(ushort,ulong,ushort,ushort const * *)
0x18005a322  jmp     loc_18005A247
0x18005a327  mov     cs:?s_logonFailure@WSManHttpListenerRequest@@0HA, r13d; int WSManHttpListenerRequest::s_logonFailure
0x18005a32e  jmp     loc_18005A247
0x18005a333  test    rdi, rdi
0x18005a336  jnz     short loc_18005A360
0x18005a338  mov     [rsp+180h+pcbBinary], r13; struct IRequestContext *
0x18005a33d  mov     r9d, 54Fh; unsigned int
0x18005a343  lea     r8, a4941; "4941"
0x18005a34a  mov     edx, 134Dh; unsigned int
0x18005a34f  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x18005a356  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18005a35b  jmp     loc_18005A255
0x18005a360  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a367  lea     r12, WPP_GLOBAL_Control
0x18005a36e  cmp     rcx, r12
0x18005a371  jz      short loc_18005A391
0x18005a373  test    dword ptr [rcx+1Ch], 400h
0x18005a37a  jz      short loc_18005A391
0x18005a37c  mov     edx, 10Fh
0x18005a381  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005a388  mov     rcx, [rcx+10h]
0x18005a38c  call    WPP_SF_
0x18005a391  mov     cs:?s_logonFailure@WSManHttpListenerRequest@@0HA, r13d; int WSManHttpListenerRequest::s_logonFailure
0x18005a398  mov     rax, [rbx+70h]
0x18005a39c  cmp     [rax+48h], r13d
0x18005a3a0  jnz     short loc_18005A3D5
0x18005a3a2  mov     rcx, [rbx+50h]; this
0x18005a3a6  call    ?DecrementUnauthenticatedConnections@WSManHttpListener@@QEAAJXZ; WSManHttpListener::DecrementUnauthenticatedConnections(void)
0x18005a3ab  cmp     eax, 100h
0x18005a3b0  jle     short loc_18005A3D5
0x18005a3b2  mov     [rsp+180h+pcbBinary], r13; struct IRequestContext *
0x18005a3b7  mov     r9d, 54Fh; unsigned int
0x18005a3bd  lea     r8, a4951; "4951"
0x18005a3c4  mov     edx, 1357h; unsigned int
0x18005a3c9  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x18005a3d0  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18005a3d5  mov     dword ptr [rdi+48h], 2
0x18005a3dc  or      r8, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
