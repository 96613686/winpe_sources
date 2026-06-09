# GetUserNgcWasEnrolledRegKey(ushort const *,int *)

- ea: `0x18005bea0`
- end: `0x18005c10a`
- name: `?GetUserNgcWasEnrolledRegKey@@YAJPEBGPEAH@Z`
- size: `618`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005f3e0`

## callees

- `0x18000ba40`
- `0x18000baa4`
- `0x1800325c0`
- `0x180032640`
- `0x18005bea0`
- `0x18005d488`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bfe0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bfe0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c05e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c05e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bfa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c02a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c08a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c0bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c0dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bfa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c02a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c08a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c0bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c0dd`

## string_xrefs

- `0x18005bf22`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18005bf6b`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18005c00e`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18005c09f`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
__int64 __fastcall GetUserNgcWasEnrolledRegKey(const unsigned __int16 *a1, int *a2)
{
  int v3; // eax
  const unsigned __int16 *v4; // r10
  unsigned __int64 v5; // r11
  unsigned int v6; // ebx
  int v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  hKey = 0;
  *a2 = 0;
  v3 = StringCchCopyW(SubKey, 0x104u, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\NgcStatus\\");
  v6 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)(unsigned int)(v5 - 110),
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v3,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v8 = StringCchCatW(SubKey, v5, v4);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v8,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v18);
    RegCloseKey(hKey);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
  }
  hKey = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( v6 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v6,
        phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      return v6;
    }
    goto LABEL_22;
  }
  v10 = RegQueryValueExW(hKey, L"NgcSetup", 0, &Type, Data, &cbData);
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( v6 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v6,
        phkResultb);
      if ( hKey )
        RegCloseKey(hKey);
      return v6;
    }
LABEL_22:
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  *a2 = *(_DWORD *)Data == 1;
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18005bea0  mov     [rsp-8+arg_10], rbx
0x18005bea5  mov     [rsp-8+arg_18], rdi
0x18005beaa  push    rbp
0x18005beab  lea     rbp, [rsp-170h]
0x18005beb3  sub     rsp, 270h
0x18005beba  mov     rax, cs:__security_cookie
0x18005bec1  xor     rax, rsp
0x18005bec4  mov     [rbp+170h+var_10], rax
0x18005becb  mov     rdi, rdx
0x18005bece  mov     r10, rcx
0x18005bed1  mov     dword ptr [rsp+270h+Data], 0
0x18005bed9  mov     [rsp+270h+cbData], 4
0x18005bee1  mov     [rsp+270h+Type], 0
0x18005bee9  mov     [rsp+270h+hKey], 0
0x18005bef2  mov     dword ptr [rdx], 0
0x18005bef8  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18005beff  mov     r11d, 104h
0x18005bf05  mov     edx, r11d; unsigned __int64
0x18005bf08  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x18005bf0d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005bf12  mov     ebx, eax
0x18005bf14  test    eax, eax
0x18005bf16  jns     short loc_18005BF4B
0x18005bf18  mov     rcx, [rbp+178h]; this
0x18005bf1f  mov     r9d, eax; char *
0x18005bf22  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005bf29  lea     edx, [r11-6Eh]; void *
0x18005bf2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bf32  nop
0x18005bf33  mov     rcx, [rsp+270h+hKey]; hKey
0x18005bf38  test    rcx, rcx
0x18005bf3b  jz      short loc_18005BF44
0x18005bf3d  call    cs:__imp_RegCloseKey
0x18005bf43  nop
0x18005bf44  mov     eax, ebx
0x18005bf46  jmp     loc_18005C0E6
0x18005bf4b  mov     r8, r10; unsigned __int16 *
0x18005bf4e  mov     rdx, r11; unsigned __int64
0x18005bf51  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x18005bf56  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005bf5b  mov     ebx, eax
0x18005bf5d  test    eax, eax
0x18005bf5f  jns     short loc_18005BF90
0x18005bf61  mov     rcx, [rbp+178h]; this
0x18005bf68  mov     r9d, eax; char *
0x18005bf6b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005bf72  mov     edx, 98h; void *
0x18005bf77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bf7c  nop
0x18005bf7d  mov     rcx, [rsp+270h+hKey]; hKey
0x18005bf82  test    rcx, rcx
0x18005bf85  jz      short loc_18005BF8E
0x18005bf87  call    cs:__imp_RegCloseKey
0x18005bf8d  nop
0x18005bf8e  jmp     short loc_18005BF44
0x18005bf90  mov     rbx, [rsp+270h+hKey]
0x18005bf95  test    rbx, rbx
0x18005bf98  jz      short loc_18005BFB8
0x18005bf9a  lea     rcx, [rsp+270h+var_228]; this
0x18005bf9f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005bfa4  mov     rcx, rbx; hKey
0x18005bfa7  call    cs:__imp_RegCloseKey
0x18005bfad  lea     rcx, [rsp+270h+var_228]; this
0x18005bfb2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005bfb7  nop
0x18005bfb8  mov     [rsp+270h+hKey], 0
0x18005bfc1  lea     rax, [rsp+270h+hKey]
0x18005bfc6  mov     [rsp+270h+phkResult], rax; int
0x18005bfcb  mov     r9d, 20019h; samDesired
0x18005bfd1  xor     r8d, r8d; ulOptions
0x18005bfd4  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x18005bfd9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005bfe0  call    cs:__imp_RegOpenKeyExW
0x18005bfe6  mov     ebx, eax
0x18005bfe8  test    eax, eax
0x18005bfea  jle     short loc_18005BFF5
0x18005bfec  movzx   ebx, ax
0x18005bfef  or      ebx, 80070000h
0x18005bff5  test    ebx, ebx
0x18005bff7  jns     short loc_18005C036
0x18005bff9  mov     edi, 80070002h
0x18005bffe  cmp     ebx, edi
0x18005c000  jnz     short loc_18005C004
0x18005c002  jmp     short loc_18005C080
0x18005c004  mov     rcx, [rbp+178h]; this
0x18005c00b  mov     r9d, ebx; char *
0x18005c00e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005c015  mov     edx, 9Ch; void *
0x18005c01a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c01f  nop
0x18005c020  mov     rcx, [rsp+270h+hKey]; hKey
0x18005c025  test    rcx, rcx
0x18005c028  jz      short loc_18005C031
0x18005c02a  call    cs:__imp_RegCloseKey
0x18005c030  nop
0x18005c031  jmp     loc_18005BF44
0x18005c036  lea     rax, [rsp+270h+cbData]
0x18005c03b  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18005c040  lea     rax, [rsp+270h+Data]
0x18005c045  mov     [rsp+270h+phkResult], rax; int
0x18005c04a  lea     r9, [rsp+270h+Type]; lpType
0x18005c04f  xor     r8d, r8d; lpReserved
0x18005c052  lea     rdx, aNgcsetup; "NgcSetup"
0x18005c059  mov     rcx, [rsp+270h+hKey]; hKey
0x18005c05e  call    cs:__imp_RegQueryValueExW
0x18005c064  mov     ebx, eax
0x18005c066  test    eax, eax
0x18005c068  jle     short loc_18005C073
0x18005c06a  movzx   ebx, ax
0x18005c06d  or      ebx, 80070000h
0x18005c073  test    ebx, ebx
0x18005c075  jns     short loc_18005C0C7
0x18005c077  mov     edi, 80070002h
0x18005c07c  cmp     ebx, edi
0x18005c07e  jnz     short loc_18005C095
0x18005c080  mov     rcx, [rsp+270h+hKey]; hKey
0x18005c085  test    rcx, rcx
0x18005c088  jz      short loc_18005C091
0x18005c08a  call    cs:__imp_RegCloseKey
0x18005c090  nop
0x18005c091  mov     eax, edi
0x18005c093  jmp     short loc_18005C0E6
0x18005c095  mov     rcx, [rbp+178h]; this
0x18005c09c  mov     r9d, ebx; char *
0x18005c09f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005c0a6  mov     edx, 0A0h; void *
0x18005c0ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c0b0  nop
0x18005c0b1  mov     rcx, [rsp+270h+hKey]; hKey
0x18005c0b6  test    rcx, rcx
0x18005c0b9  jz      short loc_18005C0C2
0x18005c0bb  call    cs:__imp_RegCloseKey
0x18005c0c1  nop
0x18005c0c2  jmp     loc_18005BF44
0x18005c0c7  xor     eax, eax
0x18005c0c9  cmp     dword ptr [rsp+270h+Data], 1
0x18005c0ce  setz    al
0x18005c0d1  mov     [rdi], eax
0x18005c0d3  mov     rcx, [rsp+270h+hKey]; hKey
0x18005c0d8  test    rcx, rcx
0x18005c0db  jz      short loc_18005C0E4
0x18005c0dd  call    cs:__imp_RegCloseKey
0x18005c0e3  nop
0x18005c0e4  xor     eax, eax
0x18005c0e6  mov     rcx, [rbp+170h+var_10]
0x18005c0ed  xor     rcx, rsp; StackCookie
0x18005c0f0  call    __security_check_cookie
0x18005c0f5  lea     r11, [rsp+270h+var_s0]
0x18005c0fd  mov     rbx, [r11+20h]
0x18005c101  mov     rdi, [r11+28h]
0x18005c105  mov     rsp, r11
0x18005c108  pop     rbp
0x18005c109  retn
```
