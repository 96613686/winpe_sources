# GetPasskeyLocationVariantFromRegistry(void *)

- ea: `0x18011e2fc`
- end: `0x18011e470`
- name: `?GetPasskeyLocationVariantFromRegistry@@YA?AUPasskeyLocationSelectionOutput@FidoCredProvHelper@@PEAX@Z`
- size: `372`
- prototype: ``
- caller_count: `7`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043ad4`
- `0x18009fc18`
- `0x1800a0158`
- `0x1800a8a78`
- `0x1800ab90c`
- `0x1800ac6d4`
- `0x180118b14`

## callees

- `0x18002a2f0`
- `0x18003a9e8`
- `0x180042df8`
- `0x18004349c`
- `0x18006b260`
- `0x18006c82c`
- `0x18010bfa8`
- `0x18010d610`
- `0x18011e2fc`
- `0x18013b0cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011e358`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011e358`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011e398`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011e3ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011e398`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011e3ee`

## string_xrefs

- `0x18011e3a9`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011e449`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011e45e`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetPasskeyLocationVariantFromRegistry(__int64 a1, __int64 a2)
{
  int UserRegKey; // eax
  HKEY *v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // eax
  int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  unsigned int phkResultb; // [rsp+20h] [rbp-40h]
  HKEY v11; // [rsp+38h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  LPBYTE lpData[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  DWORD cbData; // [rsp+80h] [rbp+20h] BYREF
  DWORD Type; // [rsp+88h] [rbp+28h] BYREF

  hKey = 0;
  UserRegKey = CtapPluginInternal::GetUserRegKey(a2, (__int64)&hKey);
  if ( UserRegKey < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)UserRegKey,
      phkResult);
  v11 = 0;
  v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v11);
  if ( RegOpenKeyExW(hKey, L"LastUsedPasskeyLocationVariant", 0, 0x20019u, v4) )
    goto LABEL_3;
  Type = 0;
  cbData = 0;
  v5 = RegQueryValueExW(v11, 0, 0, &Type, 0, &cbData);
  if ( v5 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)v5,
      phkResulta);
  if ( Type != 1 )
  {
LABEL_3:
    *(_BYTE *)(a1 + 64) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
    *(_QWORD *)(a1 + 88) = 0;
  }
  else
  {
    std::vector<unsigned short>::vector<unsigned short>(lpData, (unsigned __int64)cbData >> 1);
    v6 = RegQueryValueExW(v11, 0, 0, 0, lpData[0], &cbData);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x137,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
        (const char *)v6,
        phkResultb);
    FidoCredProvHelper::PasskeyLocationSelectionOutput::Deserialize(a1, lpData[0], 2 * ((lpData[1] - lpData[0]) >> 1));
    std::vector<unsigned short>::_Tidy(lpData);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a1;
}

```

## disassembly

```asm
0x18011e2fc  mov     [rsp-8+arg_0], rbx
0x18011e301  mov     [rsp-8+arg_8], rdi
0x18011e306  push    rbp
0x18011e307  mov     rbp, rsp
0x18011e30a  sub     rsp, 60h
0x18011e30e  mov     rax, rdx
0x18011e311  mov     rbx, rcx
0x18011e314  xor     edi, edi
0x18011e316  mov     [rbp+hKey], rdi
0x18011e31a  lea     rdx, [rbp+hKey]
0x18011e31e  mov     rcx, rax
0x18011e321  call    ?GetUserRegKey@CtapPluginInternal@@YAJQEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CtapPluginInternal::GetUserRegKey(void * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x18011e326  mov     rcx, [rbp+8]; this
0x18011e32a  test    eax, eax
0x18011e32c  js      loc_18011E45B
0x18011e332  mov     [rbp+var_28], rdi
0x18011e336  lea     rcx, [rbp+var_28]
0x18011e33a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18011e33f  mov     [rsp+60h+phkResult], rax; phkResult
0x18011e344  mov     r9d, 20019h; samDesired
0x18011e34a  xor     r8d, r8d; ulOptions
0x18011e34d  lea     rdx, aLastusedpasske; "LastUsedPasskeyLocationVariant"
0x18011e354  mov     rcx, [rbp+hKey]; hKey
0x18011e358  call    cs:__imp_RegOpenKeyExW
0x18011e35e  test    eax, eax
0x18011e360  jz      short loc_18011E377
0x18011e362  mov     [rbx+40h], dil
0x18011e366  mov     [rbx+48h], rdi
0x18011e36a  mov     [rbx+50h], rdi
0x18011e36e  mov     [rbx+58h], rdi
0x18011e372  jmp     loc_18011E420
0x18011e377  mov     [rbp+Type], edi
0x18011e37a  mov     [rbp+cbData], edi
0x18011e37d  lea     rax, [rbp+cbData]
0x18011e381  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18011e386  mov     [rsp+60h+phkResult], rdi; unsigned int
0x18011e38b  lea     r9, [rbp+Type]; lpType
0x18011e38f  xor     r8d, r8d; lpReserved
0x18011e392  xor     edx, edx; lpValueName
0x18011e394  mov     rcx, [rbp+var_28]; hKey
0x18011e398  call    cs:__imp_RegQueryValueExW
0x18011e39e  mov     rcx, [rbp+8]; this
0x18011e3a2  test    eax, eax
0x18011e3a4  jz      short loc_18011E3BA
0x18011e3a6  mov     r9d, eax; char *
0x18011e3a9  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011e3b0  mov     edx, 130h; void *
0x18011e3b5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18011e3ba  cmp     [rbp+Type], 1
0x18011e3be  jnz     short loc_18011E362
0x18011e3c0  mov     edx, [rbp+cbData]
0x18011e3c3  shr     rdx, 1
0x18011e3c6  lea     rcx, [rbp+lpData]
0x18011e3ca  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18011e3cf  nop
0x18011e3d0  mov     rax, [rbp+lpData]
0x18011e3d4  lea     rcx, [rbp+cbData]
0x18011e3d8  mov     [rsp+60h+lpcbData], rcx; lpcbData
0x18011e3dd  mov     [rsp+60h+phkResult], rax; unsigned int
0x18011e3e2  xor     r9d, r9d; lpType
0x18011e3e5  xor     r8d, r8d; lpReserved
0x18011e3e8  xor     edx, edx; lpValueName
0x18011e3ea  mov     rcx, [rbp+var_28]; hKey
0x18011e3ee  call    cs:__imp_RegQueryValueExW
0x18011e3f4  mov     rcx, [rbp+8]; this
0x18011e3f8  test    eax, eax
0x18011e3fa  jnz     short loc_18011E446
0x18011e3fc  mov     r8, [rbp+var_10]
0x18011e400  mov     rdx, [rbp+lpData]
0x18011e404  sub     r8, rdx
0x18011e407  sar     r8, 1
0x18011e40a  add     r8, r8
0x18011e40d  mov     rcx, rbx
0x18011e410  call    ?Deserialize@PasskeyLocationSelectionOutput@FidoCredProvHelper@@SA?AU12@PEBE_K@Z; FidoCredProvHelper::PasskeyLocationSelectionOutput::Deserialize(uchar const *,unsigned __int64)
0x18011e415  nop
0x18011e416  lea     rcx, [rbp+lpData]
0x18011e41a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18011e41f  nop
0x18011e420  lea     rcx, [rbp+var_28]
0x18011e424  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011e429  nop
0x18011e42a  lea     rcx, [rbp+hKey]
0x18011e42e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011e433  mov     rax, rbx
0x18011e436  mov     rbx, [rsp+60h+arg_0]
0x18011e43b  mov     rdi, [rsp+60h+arg_8]
0x18011e440  add     rsp, 60h
0x18011e444  pop     rbp
0x18011e445  retn
0x18011e446  mov     r9d, eax; char *
0x18011e449  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011e450  mov     edx, 137h; void *
0x18011e455  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18011e45b  mov     r9d, eax; char *
0x18011e45e  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011e465  mov     edx, 127h; void *
0x18011e46a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
