# QueryDevicePasswordLessData(PasswordLessDataType,ulong *)

- ea: `0x18005d9a8`
- end: `0x18005db56`
- name: `?QueryDevicePasswordLessData@@YAJW4PasswordLessDataType@@PEAK@Z`
- size: `430`
- prototype: `__int64 __fastcall(__int64, BYTE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005f5b4`
- `0x1800935e0`

## callees

- `0x18000ba40`
- `0x18000baa4`
- `0x18005d488`
- `0x18005d9a8`
- `0x18005f3bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005da57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005da57`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005dad3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005dad3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d9f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005da1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005da9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dafe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d9f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005da1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005da9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dafe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db40`

## string_xrefs

- `0x18005d9db`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18005da82`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x18005db10`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
__int64 __fastcall QueryDevicePasswordLessData(__int64 a1, BYTE *a2)
{
  const WCHAR *StringName; // rsi
  unsigned int v4; // ebx
  HKEY v6; // rbx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  int phkResultb; // [rsp+20h] [rbp-20h]
  _BYTE v12[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  StringName = (const WCHAR *)GetStringName();
  if ( !a2 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)0x80004003LL,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  *(_DWORD *)a2 = 0;
  v6 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v12);
    RegCloseKey(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v12);
  }
  hKey = 0;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\Device",
         0,
         0x20019u,
         &hKey);
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v4 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v4,
        phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      return v4;
    }
    goto LABEL_18;
  }
  Type = 0;
  cbData = 4;
  v8 = RegQueryValueExW(hKey, StringName, 0, &Type, a2, &cbData);
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v4 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A0,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v4,
        phkResultb);
      if ( hKey )
        RegCloseKey(hKey);
      return v4;
    }
LABEL_18:
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18005d9a8  mov     [rsp-18h+arg_0], rbx
0x18005d9ad  push    rbp
0x18005d9ae  push    rsi
0x18005d9af  push    rdi
0x18005d9b0  mov     rbp, rsp
0x18005d9b3  sub     rsp, 40h
0x18005d9b7  mov     rdi, rdx
0x18005d9ba  mov     [rbp+hKey], 0
0x18005d9c2  call    ?GetStringName@@YAPEBGW4PasswordLessDataType@@@Z; GetStringName(PasswordLessDataType)
0x18005d9c7  mov     rsi, rax
0x18005d9ca  test    rdi, rdi
0x18005d9cd  jnz     short loc_18005DA04
0x18005d9cf  mov     rcx, [rbp+18h]; this
0x18005d9d3  mov     ebx, 80004003h
0x18005d9d8  mov     r9d, ebx; char *
0x18005d9db  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005d9e2  mov     edx, 189h; void *
0x18005d9e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d9ec  nop
0x18005d9ed  mov     rcx, [rbp+hKey]; hKey
0x18005d9f1  test    rcx, rcx
0x18005d9f4  jz      short loc_18005D9FD
0x18005d9f6  call    cs:__imp_RegCloseKey
0x18005d9fc  nop
0x18005d9fd  mov     eax, ebx
0x18005d9ff  jmp     loc_18005DB49
0x18005da04  mov     dword ptr [rdi], 0
0x18005da0a  mov     rbx, [rbp+hKey]
0x18005da0e  test    rbx, rbx
0x18005da11  jz      short loc_18005DA2F
0x18005da13  lea     rcx, [rbp+var_10]; this
0x18005da17  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005da1c  mov     rcx, rbx; hKey
0x18005da1f  call    cs:__imp_RegCloseKey
0x18005da25  lea     rcx, [rbp+var_10]; this
0x18005da29  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005da2e  nop
0x18005da2f  mov     [rbp+hKey], 0
0x18005da37  lea     rax, [rbp+hKey]
0x18005da3b  mov     [rsp+40h+phkResult], rax; int
0x18005da40  mov     r9d, 20019h; samDesired
0x18005da46  xor     r8d, r8d; ulOptions
0x18005da49  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18005da50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005da57  call    cs:__imp_RegOpenKeyExW
0x18005da5d  mov     ebx, eax
0x18005da5f  test    eax, eax
0x18005da61  jle     short loc_18005DA6C
0x18005da63  movzx   ebx, ax
0x18005da66  or      ebx, 80070000h
0x18005da6c  test    ebx, ebx
0x18005da6e  jns     short loc_18005DAA9
0x18005da70  mov     edi, 80070002h
0x18005da75  cmp     ebx, edi
0x18005da77  jnz     short loc_18005DA7B
0x18005da79  jmp     short loc_18005DAF5
0x18005da7b  mov     rcx, [rbp+18h]; this
0x18005da7f  mov     r9d, ebx; char *
0x18005da82  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005da89  mov     edx, 193h; void *
0x18005da8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005da93  nop
0x18005da94  mov     rcx, [rbp+hKey]; hKey
0x18005da98  test    rcx, rcx
0x18005da9b  jz      short loc_18005DAA4
0x18005da9d  call    cs:__imp_RegCloseKey
0x18005daa3  nop
0x18005daa4  jmp     loc_18005D9FD
0x18005daa9  mov     [rbp+Type], 0
0x18005dab0  mov     [rbp+cbData], 4
0x18005dab7  lea     rax, [rbp+cbData]
0x18005dabb  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18005dac0  mov     [rsp+40h+phkResult], rdi; int
0x18005dac5  lea     r9, [rbp+Type]; lpType
0x18005dac9  xor     r8d, r8d; lpReserved
0x18005dacc  mov     rdx, rsi; lpValueName
0x18005dacf  mov     rcx, [rbp+hKey]; hKey
0x18005dad3  call    cs:__imp_RegQueryValueExW
0x18005dad9  mov     ebx, eax
0x18005dadb  test    eax, eax
0x18005dadd  jle     short loc_18005DAE8
0x18005dadf  movzx   ebx, ax
0x18005dae2  or      ebx, 80070000h
0x18005dae8  test    ebx, ebx
0x18005daea  jns     short loc_18005DB37
0x18005daec  mov     edi, 80070002h
0x18005daf1  cmp     ebx, edi
0x18005daf3  jnz     short loc_18005DB09
0x18005daf5  mov     rcx, [rbp+hKey]; hKey
0x18005daf9  test    rcx, rcx
0x18005dafc  jz      short loc_18005DB05
0x18005dafe  call    cs:__imp_RegCloseKey
0x18005db04  nop
0x18005db05  mov     eax, edi
0x18005db07  jmp     short loc_18005DB49
0x18005db09  mov     rcx, [rbp+18h]; this
0x18005db0d  mov     r9d, ebx; char *
0x18005db10  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18005db17  mov     edx, 1A0h; void *
0x18005db1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005db21  nop
0x18005db22  mov     rcx, [rbp+hKey]; hKey
0x18005db26  test    rcx, rcx
0x18005db29  jz      short loc_18005DB32
0x18005db2b  call    cs:__imp_RegCloseKey
0x18005db31  nop
0x18005db32  jmp     loc_18005D9FD
0x18005db37  mov     rcx, [rbp+hKey]; hKey
0x18005db3b  test    rcx, rcx
0x18005db3e  jz      short loc_18005DB47
0x18005db40  call    cs:__imp_RegCloseKey
0x18005db46  nop
0x18005db47  xor     eax, eax
0x18005db49  mov     rbx, [rsp+40h+arg_0]
0x18005db4e  add     rsp, 40h
0x18005db52  pop     rdi
0x18005db53  pop     rsi
0x18005db54  pop     rbp
0x18005db55  retn
```
