# OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180044318`
- end: `0x180044498`
- name: `?OpenWebRequest@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG_NPEAG_K23@Z`
- size: `384`
- prototype: `signed int __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *this, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x180041594`

## callees

- `0x18001c5bc`
- `0x180040d3c`
- `0x180044318`
- `0x1800467b8`
- `0x1800502c2`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044388`
- `WINHTTP!WinHttpOpen` at `0x18004437a`
- `WINHTTP!WinHttpOpen` at `0x18004437a`
- `WINHTTP!WinHttpConnect` at `0x1800443b2`
- `WINHTTP!WinHttpConnect` at `0x1800443b2`
- `WINHTTP!WinHttpSetOption` at `0x1800443f3`
- `WINHTTP!WinHttpSetOption` at `0x1800443f3`
- `WINHTTP!WinHttpOpenRequest` at `0x180044465`
- `WINHTTP!WinHttpOpenRequest` at `0x180044465`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
signed int __fastcall OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        const unsigned __int16 *a2,
        bool a3,
        unsigned __int16 *a4,
        unsigned __int64 a5,
        unsigned __int16 *a6)
{
  void *v10; // rax
  signed int result; // eax
  HINTERNET v12; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v13; // rcx
  void *v14; // rcx
  unsigned int v15; // r8d
  HINTERNET v16; // rax
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-460h]
  unsigned __int64 v18; // [rsp+38h] [rbp-450h]
  int Buffer[4]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR pwszObjectName[512]; // [rsp+50h] [rbp-438h] BYREF

  memset_0(pwszObjectName, 0, sizeof(pwszObjectName));
  *a4 = 0;
  *a6 = 0;
  v10 = WinHttpOpen(L"OneSettingsQuery", 0, 0, 0, 0);
  *(_QWORD *)this = v10;
  if ( !v10
    || (v12 = WinHttpConnect(v10, a2, 0x1BBu, 0), (*((_QWORD *)this + 1) = v12) == 0)
    || (OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(
          v13,
          (void **)this,
          a2,
          a3,
          a4,
          (unsigned __int64)ppwszAcceptTypes,
          a6,
          v18),
        v14 = *(void **)this,
        Buffer[0] = 2048,
        !WinHttpSetOption(v14, 0x54u, Buffer, 4u)) )
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  result = StringCchPrintfW(pwszObjectName, 0x200u, L"settings/v2.0/%ls/%ls", (char *)this + 40, (char *)this + 560);
  if ( result >= 0 )
  {
    result = OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(this, pwszObjectName, v15);
    if ( result >= 0 )
    {
      v16 = WinHttpOpenRequest(*((HINTERNET *)this + 1), L"GET", pwszObjectName, 0, 0, 0, 0x800000u);
      *((_QWORD *)this + 2) = v16;
      if ( v16 )
        return 0;
      goto LABEL_2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180044318  push    rbx
0x18004431a  push    rbp
0x18004431b  push    rsi
0x18004431c  push    rdi
0x18004431d  push    r14
0x18004431f  sub     rsp, 460h
0x180044326  mov     rax, cs:__security_cookie
0x18004432d  xor     rax, rsp
0x180044330  mov     [rsp+488h+var_38], rax
0x180044338  mov     r14, [rsp+488h+arg_28]
0x180044340  mov     bpl, r8b
0x180044343  mov     rdi, rdx
0x180044346  mov     rbx, rcx
0x180044349  xor     edx, edx; Val
0x18004434b  lea     rcx, [rsp+488h+pwszObjectName]; void *
0x180044350  mov     r8d, 400h; Size
0x180044356  mov     rsi, r9
0x180044359  call    memset_0
0x18004435e  xor     eax, eax
0x180044360  lea     rcx, pszAgentW; "OneSettingsQuery"
0x180044367  mov     [rsi], ax
0x18004436a  xor     r9d, r9d; pszProxyBypassW
0x18004436d  xor     r8d, r8d; pszProxyW
0x180044370  mov     [r14], ax
0x180044374  xor     edx, edx; dwAccessType
0x180044376  mov     [rsp+488h+dwFlags], eax; dwFlags
0x18004437a  call    cs:__imp_WinHttpOpen
0x180044380  mov     [rbx], rax
0x180044383  test    rax, rax
0x180044386  jnz     short loc_1800443A3
0x180044388  call    cs:__imp_GetLastError
0x18004438e  test    eax, eax
0x180044390  jle     loc_18004447A
0x180044396  movzx   eax, ax
0x180044399  or      eax, 80070000h
0x18004439e  jmp     loc_18004447A
0x1800443a3  mov     r8d, 1BBh; nServerPort
0x1800443a9  xor     r9d, r9d; dwReserved
0x1800443ac  mov     rdx, rdi; pswzServerName
0x1800443af  mov     rcx, rax; hSession
0x1800443b2  call    cs:__imp_WinHttpConnect
0x1800443b8  mov     [rbx+8], rax
0x1800443bc  test    rax, rax
0x1800443bf  jz      short loc_180044388
0x1800443c1  mov     qword ptr [rsp+488h+var_458], r14; unsigned __int16 *
0x1800443c6  mov     r9b, bpl; bool
0x1800443c9  mov     r8, rdi; unsigned __int16 *
0x1800443cc  mov     qword ptr [rsp+488h+dwFlags], rsi; unsigned __int16 *
0x1800443d1  mov     rdx, rbx; void **
0x1800443d4  call    ?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z; OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x1800443d9  mov     rcx, [rbx]; hInternet
0x1800443dc  lea     r8, [rsp+488h+Buffer]; lpBuffer
0x1800443e1  mov     r9d, 4; dwBufferLength
0x1800443e7  mov     [rsp+488h+Buffer], 800h
0x1800443ef  lea     edx, [r9+50h]; dwOption
0x1800443f3  call    cs:__imp_WinHttpSetOption
0x1800443f9  test    eax, eax
0x1800443fb  jz      short loc_180044388
0x1800443fd  lea     rax, [rbx+230h]
0x180044404  mov     edx, 200h; unsigned __int64
0x180044409  lea     r9, [rbx+28h]
0x18004440d  mov     qword ptr [rsp+488h+dwFlags], rax
0x180044412  lea     r8, aSettingsV20LsL; "settings/v2.0/%ls/%ls"
0x180044419  lea     rcx, [rsp+488h+pwszObjectName]; unsigned __int16 *
0x18004441e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044423  test    eax, eax
0x180044425  js      short loc_18004447A
0x180044427  lea     rdx, [rsp+488h+pwszObjectName]; unsigned __int16 *
0x18004442c  mov     rcx, rbx; this
0x18004442f  call    ?AppendQueryString@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(ushort *,ulong)
0x180044434  test    eax, eax
0x180044436  js      short loc_18004447A
0x180044438  mov     rcx, [rbx+8]; hConnect
0x18004443c  lea     r8, [rsp+488h+pwszObjectName]; pwszObjectName
0x180044441  mov     [rsp+488h+var_458], 800000h; dwFlags
0x180044449  lea     rdx, pwszVerb; "GET"
0x180044450  mov     [rsp+488h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x180044459  xor     r9d, r9d; pwszVersion
0x18004445c  mov     qword ptr [rsp+488h+dwFlags], 0; pwszReferrer
0x180044465  call    cs:__imp_WinHttpOpenRequest
0x18004446b  mov     [rbx+10h], rax
0x18004446f  test    rax, rax
0x180044472  jz      loc_180044388
0x180044478  xor     eax, eax
0x18004447a  mov     rcx, [rsp+488h+var_38]
0x180044482  xor     rcx, rsp; StackCookie
0x180044485  call    __security_check_cookie
0x18004448a  add     rsp, 460h
0x180044491  pop     r14
0x180044493  pop     rdi
0x180044494  pop     rsi
0x180044495  pop     rbp
0x180044496  pop     rbx
0x180044497  retn
```
