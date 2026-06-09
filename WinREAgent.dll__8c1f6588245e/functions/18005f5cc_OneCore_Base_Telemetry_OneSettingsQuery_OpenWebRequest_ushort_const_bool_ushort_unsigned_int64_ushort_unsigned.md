# OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x18005f5cc`
- end: `0x18005f74c`
- name: `?OpenWebRequest@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG_NPEAG_K23@Z`
- size: `384`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x18005c9b4`

## callees

- `0x180012864`
- `0x18005bf98`
- `0x18005f5cc`
- `0x18006189c`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005f63c`
- `KERNEL32!GetLastError` at `0x18005f63c`
- `WINHTTP!WinHttpOpen` at `0x18005f62e`
- `WINHTTP!WinHttpOpen` at `0x18005f62e`
- `WINHTTP!WinHttpConnect` at `0x18005f666`
- `WINHTTP!WinHttpConnect` at `0x18005f666`
- `WINHTTP!WinHttpSetOption` at `0x18005f6a7`
- `WINHTTP!WinHttpSetOption` at `0x18005f6a7`
- `WINHTTP!WinHttpOpenRequest` at `0x18005f719`
- `WINHTTP!WinHttpOpenRequest` at `0x18005f719`

## pseudocode

```c
signed int __fastcall OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        WCHAR *a2,
        char a3,
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
          a6),
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
0x18005f5cc  push    rbx
0x18005f5ce  push    rbp
0x18005f5cf  push    rsi
0x18005f5d0  push    rdi
0x18005f5d1  push    r14
0x18005f5d3  sub     rsp, 460h
0x18005f5da  mov     rax, cs:__security_cookie
0x18005f5e1  xor     rax, rsp
0x18005f5e4  mov     [rsp+488h+var_38], rax
0x18005f5ec  mov     r14, [rsp+488h+arg_28]
0x18005f5f4  mov     bpl, r8b
0x18005f5f7  mov     rdi, rdx
0x18005f5fa  mov     rbx, rcx
0x18005f5fd  xor     edx, edx; Val
0x18005f5ff  lea     rcx, [rsp+488h+pwszObjectName]; void *
0x18005f604  mov     r8d, 400h; Size
0x18005f60a  mov     rsi, r9
0x18005f60d  call    memset_0
0x18005f612  xor     eax, eax
0x18005f614  lea     rcx, pszAgentW; "OneSettingsQuery"
0x18005f61b  mov     [rsi], ax
0x18005f61e  xor     r9d, r9d; pszProxyBypassW
0x18005f621  xor     r8d, r8d; pszProxyW
0x18005f624  mov     [r14], ax
0x18005f628  xor     edx, edx; dwAccessType
0x18005f62a  mov     [rsp+488h+dwFlags], eax; dwFlags
0x18005f62e  call    cs:__imp_WinHttpOpen
0x18005f634  mov     [rbx], rax
0x18005f637  test    rax, rax
0x18005f63a  jnz     short loc_18005F657
0x18005f63c  call    cs:__imp_GetLastError
0x18005f642  test    eax, eax
0x18005f644  jle     loc_18005F72E
0x18005f64a  movzx   eax, ax
0x18005f64d  or      eax, 80070000h
0x18005f652  jmp     loc_18005F72E
0x18005f657  mov     r8d, 1BBh; nServerPort
0x18005f65d  xor     r9d, r9d; dwReserved
0x18005f660  mov     rdx, rdi; pswzServerName
0x18005f663  mov     rcx, rax; hSession
0x18005f666  call    cs:__imp_WinHttpConnect
0x18005f66c  mov     [rbx+8], rax
0x18005f670  test    rax, rax
0x18005f673  jz      short loc_18005F63C
0x18005f675  mov     qword ptr [rsp+488h+var_458], r14; unsigned __int16 *
0x18005f67a  mov     r9b, bpl; bool
0x18005f67d  mov     r8, rdi; unsigned __int16 *
0x18005f680  mov     qword ptr [rsp+488h+dwFlags], rsi; unsigned __int16 *
0x18005f685  mov     rdx, rbx; void **
0x18005f688  call    ?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z; OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18005f68d  mov     rcx, [rbx]; hInternet
0x18005f690  lea     r8, [rsp+488h+Buffer]; lpBuffer
0x18005f695  mov     r9d, 4; dwBufferLength
0x18005f69b  mov     [rsp+488h+Buffer], 800h
0x18005f6a3  lea     edx, [r9+50h]; dwOption
0x18005f6a7  call    cs:__imp_WinHttpSetOption
0x18005f6ad  test    eax, eax
0x18005f6af  jz      short loc_18005F63C
0x18005f6b1  lea     rax, [rbx+230h]
0x18005f6b8  mov     edx, 200h; unsigned __int64
0x18005f6bd  lea     r9, [rbx+28h]
0x18005f6c1  mov     qword ptr [rsp+488h+dwFlags], rax
0x18005f6c6  lea     r8, aSettingsV20LsL; "settings/v2.0/%ls/%ls"
0x18005f6cd  lea     rcx, [rsp+488h+pwszObjectName]; unsigned __int16 *
0x18005f6d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005f6d7  test    eax, eax
0x18005f6d9  js      short loc_18005F72E
0x18005f6db  lea     rdx, [rsp+488h+pwszObjectName]; unsigned __int16 *
0x18005f6e0  mov     rcx, rbx; this
0x18005f6e3  call    ?AppendQueryString@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(ushort *,ulong)
0x18005f6e8  test    eax, eax
0x18005f6ea  js      short loc_18005F72E
0x18005f6ec  mov     rcx, [rbx+8]; hConnect
0x18005f6f0  lea     r8, [rsp+488h+pwszObjectName]; pwszObjectName
0x18005f6f5  mov     [rsp+488h+var_458], 800000h; dwFlags
0x18005f6fd  lea     rdx, pwszVerb; "GET"
0x18005f704  mov     [rsp+488h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18005f70d  xor     r9d, r9d; pwszVersion
0x18005f710  mov     qword ptr [rsp+488h+dwFlags], 0; pwszReferrer
0x18005f719  call    cs:__imp_WinHttpOpenRequest
0x18005f71f  mov     [rbx+10h], rax
0x18005f723  test    rax, rax
0x18005f726  jz      loc_18005F63C
0x18005f72c  xor     eax, eax
0x18005f72e  mov     rcx, [rsp+488h+var_38]
0x18005f736  xor     rcx, rsp; StackCookie
0x18005f739  call    __security_check_cookie
0x18005f73e  add     rsp, 460h
0x18005f745  pop     r14
0x18005f747  pop     rdi
0x18005f748  pop     rsi
0x18005f749  pop     rbp
0x18005f74a  pop     rbx
0x18005f74b  retn
```
