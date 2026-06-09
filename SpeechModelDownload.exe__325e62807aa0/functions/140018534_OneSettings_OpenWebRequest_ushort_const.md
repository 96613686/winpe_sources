# OneSettings::OpenWebRequest(ushort const *)

- ea: `0x140018534`
- end: `0x140018679`
- name: `?OpenWebRequest@OneSettings@@AEAAJPEBG@Z`
- size: `325`
- prototype: `__int64 __fastcall(HINTERNET *this, LPCWSTR pswzServerName)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x140018a94`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x140015ed4`
- `0x140016270`
- `0x140018534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001863a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001863a`
- `WINHTTP!WinHttpOpen` at `0x14001858e`
- `WINHTTP!WinHttpOpen` at `0x14001858e`
- `WINHTTP!WinHttpSetTimeouts` at `0x1400185b6`
- `WINHTTP!WinHttpSetTimeouts` at `0x1400185b6`
- `WINHTTP!WinHttpOpenRequest` at `0x140018628`
- `WINHTTP!WinHttpOpenRequest` at `0x140018628`
- `WINHTTP!WinHttpConnect` at `0x1400185d3`
- `WINHTTP!WinHttpConnect` at `0x1400185d3`

## pseudocode

```c
__int64 __fastcall OneSettings::OpenWebRequest(HINTERNET *this, LPCWSTR pswzServerName)
{
  const WCHAR *v4; // rcx
  void *v5; // rax
  HINTERNET v6; // rax
  int QueryString; // ebx
  HINTERNET v8; // rax
  signed int LastError; // eax
  WCHAR pwszObjectName[512]; // [rsp+40h] [rbp-418h] BYREF

  OneSettings::CloseOpenConnections((OneSettings *)this);
  memset_0(pwszObjectName, 0, sizeof(pwszObjectName));
  v4 = (const WCHAR *)(this + 12);
  if ( (unsigned __int64)this[15] > 7 )
    v4 = *(const WCHAR **)v4;
  v5 = WinHttpOpen(v4, 0, 0, 0, 0);
  this[21] = v5;
  if ( !v5
    || !WinHttpSetTimeouts(v5, 10000, 10000, 10000, 10000)
    || (v6 = WinHttpConnect(this[21], pswzServerName, 0x1BBu, 0), (this[22] = v6) == 0)
    || (QueryString = OneSettings::CreateQueryString((OneSettings *)this, pwszObjectName), QueryString >= 0)
    && (v8 = WinHttpOpenRequest(this[22], L"GET", pwszObjectName, 0, 0, 0, 0x800000u), (this[23] = v8) == 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    QueryString = -2147467259;
    if ( LastError < 0 )
      return (unsigned int)LastError;
  }
  return (unsigned int)QueryString;
}

```

## disassembly

```asm
0x140018534  mov     [rsp+arg_10], rbx
0x140018539  push    rdi
0x14001853a  sub     rsp, 450h
0x140018541  mov     rax, cs:__security_cookie
0x140018548  xor     rax, rsp
0x14001854b  mov     [rsp+458h+var_18], rax
0x140018553  mov     rbx, rdx
0x140018556  mov     rdi, rcx
0x140018559  call    ?CloseOpenConnections@OneSettings@@AEAAJXZ; OneSettings::CloseOpenConnections(void)
0x14001855e  xor     edx, edx; Val
0x140018560  lea     rcx, [rsp+458h+pwszObjectName]; void *
0x140018565  mov     r8d, 400h; Size
0x14001856b  call    memset_0
0x140018570  lea     rcx, [rdi+60h]
0x140018574  cmp     qword ptr [rcx+18h], 7
0x140018579  jbe     short loc_14001857E
0x14001857b  mov     rcx, [rcx]; pszAgentW
0x14001857e  xor     r9d, r9d; pszProxyBypassW
0x140018581  mov     [rsp+458h+dwFlags], 0; dwFlags
0x140018589  xor     r8d, r8d; pszProxyW
0x14001858c  xor     edx, edx; dwAccessType
0x14001858e  call    cs:__imp_WinHttpOpen
0x140018594  mov     [rdi+0A8h], rax
0x14001859b  test    rax, rax
0x14001859e  jz      loc_14001863A
0x1400185a4  mov     edx, 2710h; nResolveTimeout
0x1400185a9  mov     rcx, rax; hInternet
0x1400185ac  mov     r9d, edx; nSendTimeout
0x1400185af  mov     [rsp+458h+dwFlags], edx; nReceiveTimeout
0x1400185b3  mov     r8d, edx; nConnectTimeout
0x1400185b6  call    cs:__imp_WinHttpSetTimeouts
0x1400185bc  test    eax, eax
0x1400185be  jz      short loc_14001863A
0x1400185c0  mov     rcx, [rdi+0A8h]; hSession
0x1400185c7  mov     r8d, 1BBh; nServerPort
0x1400185cd  xor     r9d, r9d; dwReserved
0x1400185d0  mov     rdx, rbx; pswzServerName
0x1400185d3  call    cs:__imp_WinHttpConnect
0x1400185d9  mov     [rdi+0B0h], rax
0x1400185e0  test    rax, rax
0x1400185e3  jz      short loc_14001863A
0x1400185e5  lea     rdx, [rsp+458h+pwszObjectName]; unsigned __int16 *
0x1400185ea  mov     rcx, rdi; this
0x1400185ed  call    ?CreateQueryString@OneSettings@@AEAAJPEAGK@Z; OneSettings::CreateQueryString(ushort *,ulong)
0x1400185f2  mov     ebx, eax
0x1400185f4  test    eax, eax
0x1400185f6  js      short loc_140018656
0x1400185f8  mov     rcx, [rdi+0B0h]; hConnect
0x1400185ff  lea     r8, [rsp+458h+pwszObjectName]; pwszObjectName
0x140018604  mov     [rsp+458h+var_428], 800000h; dwFlags
0x14001860c  lea     rdx, pwszVerb; "GET"
0x140018613  mov     [rsp+458h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x14001861c  xor     r9d, r9d; pwszVersion
0x14001861f  mov     qword ptr [rsp+458h+dwFlags], 0; pwszReferrer
0x140018628  call    cs:__imp_WinHttpOpenRequest
0x14001862e  mov     [rdi+0B8h], rax
0x140018635  test    rax, rax
0x140018638  jnz     short loc_140018656
0x14001863a  call    cs:__imp_GetLastError
0x140018640  test    eax, eax
0x140018642  jle     short loc_14001864C
0x140018644  movzx   eax, ax
0x140018647  or      eax, 80070000h
0x14001864c  test    eax, eax
0x14001864e  mov     ebx, 80004005h
0x140018653  cmovs   ebx, eax
0x140018656  mov     eax, ebx
0x140018658  mov     rcx, [rsp+458h+var_18]
0x140018660  xor     rcx, rsp; StackCookie
0x140018663  call    __security_check_cookie
0x140018668  mov     rbx, [rsp+458h+arg_10]
0x140018670  add     rsp, 450h
0x140018677  pop     rdi
0x140018678  retn
```
