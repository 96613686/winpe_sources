# SetDevicePasswordLessData(PasswordLessDataType,ulong)

- ea: `0x14007395c`
- end: `0x140073a54`
- name: `?SetDevicePasswordLessData@@YAJW4PasswordLessDataType@@K@Z`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x14000ed38`
- `0x14001f3f8`
- `0x14002c070`
- `0x140073938`
- `0x14007395c`

## import_xrefs

- `KERNEL32!RegCreateKeyExW` at `0x1400739bb`
- `KERNEL32!RegCreateKeyExW` at `0x1400739bb`
- `KERNEL32!RegSetValueExW` at `0x140073a0f`
- `KERNEL32!RegSetValueExW` at `0x140073a0f`

## string_xrefs

- `0x1400739cd`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x140073a21`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetDevicePasswordLessData(__int64 a1, int a2)
{
  const WCHAR *StringName; // rbx
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  unsigned int v5; // ebx
  unsigned int v7; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  Data = a2;
  hKey = 0;
  StringName = (const WCHAR *)GetStringName();
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\Device",
          0,
          0,
          0,
          0x20006u,
          0,
          phkResult,
          0);
  if ( Key )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x170,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)Key,
           dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v5;
  }
  v7 = RegSetValueExW(hKey, StringName, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v7 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x178,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v7,
           dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v5;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x14007395c  mov     [rsp+Data], edx
0x140073960  push    rbx
0x140073961  sub     rsp, 50h
0x140073965  mov     [rsp+58h+hKey], 0
0x14007396e  call    ?GetStringName@@YAPEBGW4PasswordLessDataType@@@Z; GetStringName(PasswordLessDataType)
0x140073973  mov     rbx, rax
0x140073976  lea     rcx, [rsp+58h+hKey]
0x14007397b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140073980  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x140073989  mov     [rsp+58h+phkResult], rax; phkResult
0x14007398e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140073997  mov     [rsp+58h+samDesired], 20006h; samDesired
0x14007399f  mov     [rsp+58h+dwOptions], 0; unsigned int
0x1400739a7  xor     r9d, r9d; lpClass
0x1400739aa  xor     r8d, r8d; Reserved
0x1400739ad  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400739b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400739bb  call    cs:__imp_RegCreateKeyExW
0x1400739c1  test    eax, eax
0x1400739c3  jz      short loc_1400739EF
0x1400739c5  mov     rcx, [rsp+58h]; this
0x1400739ca  mov     r9d, eax; char *
0x1400739cd  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1400739d4  mov     edx, 170h; void *
0x1400739d9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400739de  mov     ebx, eax
0x1400739e0  lea     rcx, [rsp+58h+hKey]
0x1400739e5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400739ea  nop
0x1400739eb  mov     eax, ebx
0x1400739ed  jmp     short loc_140073A4E
0x1400739ef  mov     r9d, 4; dwType
0x1400739f5  mov     [rsp+58h+samDesired], r9d; cbData
0x1400739fa  lea     rax, [rsp+58h+Data]
0x1400739ff  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int
0x140073a04  xor     r8d, r8d; Reserved
0x140073a07  mov     rdx, rbx; lpValueName
0x140073a0a  mov     rcx, [rsp+58h+hKey]; hKey
0x140073a0f  call    cs:__imp_RegSetValueExW
0x140073a15  test    eax, eax
0x140073a17  jz      short loc_140073A41
0x140073a19  mov     rcx, [rsp+58h]; this
0x140073a1e  mov     r9d, eax; char *
0x140073a21  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x140073a28  mov     edx, 178h; void *
0x140073a2d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140073a32  mov     ebx, eax
0x140073a34  lea     rcx, [rsp+58h+hKey]
0x140073a39  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140073a3e  nop
0x140073a3f  jmp     short loc_1400739EB
0x140073a41  lea     rcx, [rsp+58h+hKey]
0x140073a46  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140073a4b  nop
0x140073a4c  xor     eax, eax
0x140073a4e  add     rsp, 50h
0x140073a52  pop     rbx
0x140073a53  retn
```
