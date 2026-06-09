# OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x18001eac8`
- end: `0x18001ec48`
- name: `?OpenWebRequest@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG_NPEAG_K23@Z`
- size: `384`
- prototype: `signed int __fastcall(void **this, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x18001acb4`

## callees

- `0x180003850`
- `0x18001a1e4`
- `0x18001eac8`
- `0x180022678`
- `0x1800322d2`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb38`
- `WINHTTP!WinHttpSetOption` at `0x18001eba3`
- `WINHTTP!WinHttpSetOption` at `0x18001eba3`
- `WINHTTP!WinHttpConnect` at `0x18001eb62`
- `WINHTTP!WinHttpConnect` at `0x18001eb62`
- `WINHTTP!WinHttpOpen` at `0x18001eb2a`
- `WINHTTP!WinHttpOpen` at `0x18001eb2a`
- `WINHTTP!WinHttpOpenRequest` at `0x18001ec15`
- `WINHTTP!WinHttpOpenRequest` at `0x18001ec15`

## pseudocode

```c
signed int __fastcall OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(
        void **this,
        const unsigned __int16 *a2,
        bool a3,
        unsigned __int16 *a4,
        unsigned __int64 a5,
        unsigned __int16 *a6)
{
  void *v10; // rax
  signed int result; // eax
  void *v12; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v13; // rcx
  void *v14; // rcx
  unsigned int v15; // r8d
  void *v16; // rax
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-460h]
  unsigned __int64 v18; // [rsp+38h] [rbp-450h]
  int Buffer[4]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR pwszObjectName[512]; // [rsp+50h] [rbp-438h] BYREF

  memset_0(pwszObjectName, 0, sizeof(pwszObjectName));
  *a4 = 0;
  *a6 = 0;
  v10 = WinHttpOpen(L"OneSettingsQuery", 0, 0, 0, 0);
  *this = v10;
  if ( !v10
    || (v12 = WinHttpConnect(v10, a2, 0x1BBu, 0), (this[1] = v12) == 0)
    || (OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(
          v13,
          this,
          a2,
          a3,
          a4,
          (unsigned __int64)ppwszAcceptTypes,
          a6,
          v18),
        v14 = *this,
        Buffer[0] = 2048,
        !WinHttpSetOption(v14, 0x54u, Buffer, 4u)) )
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  result = StringCchPrintfW(pwszObjectName, 0x200u, L"settings/v2.0/%ls/%ls", this + 5, this + 70);
  if ( result >= 0 )
  {
    result = OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(
               (OneCore::Base::Telemetry::OneSettingsQuery *)this,
               pwszObjectName,
               v15);
    if ( result >= 0 )
    {
      v16 = WinHttpOpenRequest(this[1], L"GET", pwszObjectName, 0, 0, 0, 0x800000u);
      this[2] = v16;
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
0x18001eac8  push    rbx
0x18001eaca  push    rbp
0x18001eacb  push    rsi
0x18001eacc  push    rdi
0x18001eacd  push    r14
0x18001eacf  sub     rsp, 460h
0x18001ead6  mov     rax, cs:__security_cookie
0x18001eadd  xor     rax, rsp
0x18001eae0  mov     [rsp+488h+var_38], rax
0x18001eae8  mov     r14, [rsp+488h+arg_28]
0x18001eaf0  mov     bpl, r8b
0x18001eaf3  mov     rdi, rdx
0x18001eaf6  mov     rbx, rcx
0x18001eaf9  xor     edx, edx; Val
0x18001eafb  lea     rcx, [rsp+488h+pwszObjectName]; void *
0x18001eb00  mov     r8d, 400h; Size
0x18001eb06  mov     rsi, r9
0x18001eb09  call    memset_0
0x18001eb0e  xor     eax, eax
0x18001eb10  lea     rcx, pszAgentW; "OneSettingsQuery"
0x18001eb17  mov     [rsi], ax
0x18001eb1a  xor     r9d, r9d; pszProxyBypassW
0x18001eb1d  xor     r8d, r8d; pszProxyW
0x18001eb20  mov     [r14], ax
0x18001eb24  xor     edx, edx; dwAccessType
0x18001eb26  mov     [rsp+488h+dwFlags], eax; dwFlags
0x18001eb2a  call    cs:__imp_WinHttpOpen
0x18001eb30  mov     [rbx], rax
0x18001eb33  test    rax, rax
0x18001eb36  jnz     short loc_18001EB53
0x18001eb38  call    cs:__imp_GetLastError
0x18001eb3e  test    eax, eax
0x18001eb40  jle     loc_18001EC2A
0x18001eb46  movzx   eax, ax
0x18001eb49  or      eax, 80070000h
0x18001eb4e  jmp     loc_18001EC2A
0x18001eb53  mov     r8d, 1BBh; nServerPort
0x18001eb59  xor     r9d, r9d; dwReserved
0x18001eb5c  mov     rdx, rdi; pswzServerName
0x18001eb5f  mov     rcx, rax; hSession
0x18001eb62  call    cs:__imp_WinHttpConnect
0x18001eb68  mov     [rbx+8], rax
0x18001eb6c  test    rax, rax
0x18001eb6f  jz      short loc_18001EB38
0x18001eb71  mov     qword ptr [rsp+488h+var_458], r14; unsigned __int16 *
0x18001eb76  mov     r9b, bpl; bool
0x18001eb79  mov     r8, rdi; unsigned __int16 *
0x18001eb7c  mov     qword ptr [rsp+488h+dwFlags], rsi; unsigned __int16 *
0x18001eb81  mov     rdx, rbx; void **
0x18001eb84  call    ?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z; OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18001eb89  mov     rcx, [rbx]; hInternet
0x18001eb8c  lea     r8, [rsp+488h+Buffer]; lpBuffer
0x18001eb91  mov     r9d, 4; dwBufferLength
0x18001eb97  mov     [rsp+488h+Buffer], 800h
0x18001eb9f  lea     edx, [r9+50h]; dwOption
0x18001eba3  call    cs:__imp_WinHttpSetOption
0x18001eba9  test    eax, eax
0x18001ebab  jz      short loc_18001EB38
0x18001ebad  lea     rax, [rbx+230h]
0x18001ebb4  mov     edx, 200h; unsigned __int64
0x18001ebb9  lea     r9, [rbx+28h]
0x18001ebbd  mov     qword ptr [rsp+488h+dwFlags], rax
0x18001ebc2  lea     r8, aSettingsV20LsL; "settings/v2.0/%ls/%ls"
0x18001ebc9  lea     rcx, [rsp+488h+pwszObjectName]; unsigned __int16 *
0x18001ebce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ebd3  test    eax, eax
0x18001ebd5  js      short loc_18001EC2A
0x18001ebd7  lea     rdx, [rsp+488h+pwszObjectName]; unsigned __int16 *
0x18001ebdc  mov     rcx, rbx; this
0x18001ebdf  call    ?AppendQueryString@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(ushort *,ulong)
0x18001ebe4  test    eax, eax
0x18001ebe6  js      short loc_18001EC2A
0x18001ebe8  mov     rcx, [rbx+8]; hConnect
0x18001ebec  lea     r8, [rsp+488h+pwszObjectName]; pwszObjectName
0x18001ebf1  mov     [rsp+488h+var_458], 800000h; dwFlags
0x18001ebf9  lea     rdx, pwszVerb; "GET"
0x18001ec00  mov     [rsp+488h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18001ec09  xor     r9d, r9d; pwszVersion
0x18001ec0c  mov     qword ptr [rsp+488h+dwFlags], 0; pwszReferrer
0x18001ec15  call    cs:__imp_WinHttpOpenRequest
0x18001ec1b  mov     [rbx+10h], rax
0x18001ec1f  test    rax, rax
0x18001ec22  jz      loc_18001EB38
0x18001ec28  xor     eax, eax
0x18001ec2a  mov     rcx, [rsp+488h+var_38]
0x18001ec32  xor     rcx, rsp; StackCookie
0x18001ec35  call    __security_check_cookie
0x18001ec3a  add     rsp, 460h
0x18001ec41  pop     r14
0x18001ec43  pop     rdi
0x18001ec44  pop     rsi
0x18001ec45  pop     rbp
0x18001ec46  pop     rbx
0x18001ec47  retn
```
