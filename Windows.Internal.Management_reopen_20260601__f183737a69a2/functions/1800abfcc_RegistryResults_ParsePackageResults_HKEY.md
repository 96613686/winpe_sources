# RegistryResults::ParsePackageResults(HKEY__ *)

- ea: `0x1800abfcc`
- end: `0x1800ac22a`
- name: `?ParsePackageResults@RegistryResults@@AEAA?AV?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@PEAUHKEY__@@@Z`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800abbc0`

## callees

- `0x180003884`
- `0x180004eb0`
- `0x1800131a8`
- `0x180016698`
- `0x180017118`
- `0x18003973c`
- `0x18003a394`
- `0x1800aba78`
- `0x1800abb54`
- `0x1800abe04`
- `0x1800abfcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ac0ca`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ac0ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ac10d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ac10d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ac05d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ac05d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall RegistryResults::ParsePackageResults(__int64 a1, _QWORD *a2, HKEY a3)
{
  HKEY v3; // r14
  _QWORD *v4; // rsi
  DWORD v5; // edi
  __int64 v6; // rcx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // r8
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-94h] BYREF
  DWORD v13; // [rsp+68h] [rbp-90h]
  HKEY phkResult; // [rsp+70h] [rbp-88h] BYREF
  int v15; // [rsp+78h] [rbp-80h]
  DWORD cSubKeys; // [rsp+7Ch] [rbp-7Ch] BYREF
  LPWSTR v17; // [rsp+80h] [rbp-78h] BYREF
  LPWSTR lpName[2]; // [rsp+88h] [rbp-70h] BYREF
  __int64 v19; // [rsp+98h] [rbp-60h]
  _QWORD *v20; // [rsp+A0h] [rbp-58h]
  HKEY v21; // [rsp+A8h] [rbp-50h]
  _BYTE v22[40]; // [rsp+B0h] [rbp-48h] BYREF

  v3 = a3;
  v4 = a2;
  v20 = a2;
  v21 = a3;
  std::list<CommandResult>::list<CommandResult>(a2);
  v15 = 1;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( !RegQueryInfoKeyW(v3, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    *(_OWORD *)lpName = 0;
    v19 = 0;
    cchName = cbMaxSubKeyLen + 1;
    std::vector<unsigned short>::reserve(lpName, cbMaxSubKeyLen + 1);
    v5 = 0;
    v13 = 0;
    while ( !RegEnumKeyExW(v3, v5, lpName[0], &cchName, 0, 0, 0, 0) )
    {
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      if ( RegOpenKeyExW(v3, lpName[0], 0, 0x20019u, &phkResult) )
      {
        if ( (unsigned int)dword_1800FE488 > 2 )
        {
          v17 = lpName[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v6,
            (unsigned int)&unk_1800EDFC0,
            v7,
            v8,
            (__int64)&v17);
        }
      }
      else
      {
        if ( (unsigned int)dword_1800FE488 > 4 )
        {
          v17 = lpName[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v6,
            (unsigned int)&word_1800EDDBE,
            v7,
            v8,
            (__int64)&v17);
        }
        try
        {
          v9 = RegistryResults::ParseCommandResult(v6, v22, phkResult, lpName[0]);
          std::list<CommandResult>::_Emplace<CommandResult>(v4, *v4, v9);
          std::wstring::_Tidy_deallocate(v22);
        }
        catch ( ... )
        {
          v5 = v13;
          v4 = v20;
          v3 = v21;
        }
      }
      cchName = cbMaxSubKeyLen + 1;
      v13 = ++v5;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    std::vector<unsigned short>::_Tidy(lpName);
  }
  return v4;
}

```

## disassembly

```asm
0x1800abfcc  mov     r11, rsp
0x1800abfcf  mov     [r11+8], rbx
0x1800abfd3  push    rsi
0x1800abfd4  push    rdi
0x1800abfd5  push    r14
0x1800abfd7  sub     rsp, 0E0h
0x1800abfde  mov     rax, cs:__security_cookie
0x1800abfe5  xor     rax, rsp
0x1800abfe8  mov     [rsp+0F8h+var_20], rax
0x1800abff0  mov     r14, r8
0x1800abff3  mov     rsi, rdx
0x1800abff6  mov     [r11-58h], rdx
0x1800abffa  mov     [rsp+0F8h+var_50], r8
0x1800ac002  xor     ebx, ebx
0x1800ac004  mov     [rsp+0F8h+var_80], ebx
0x1800ac008  mov     rcx, rdx
0x1800ac00b  call    ??0?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@XZ; std::list<CommandResult>::list<CommandResult>(void)
0x1800ac010  mov     [rsp+0F8h+var_80], 1
0x1800ac018  mov     [rsp+0F8h+cSubKeys], ebx
0x1800ac01c  mov     [rsp+0F8h+cbMaxSubKeyLen], ebx
0x1800ac020  mov     [rsp+0F8h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1800ac025  mov     [rsp+0F8h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x1800ac02a  mov     [rsp+0F8h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x1800ac02f  mov     [rsp+0F8h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x1800ac034  mov     [rsp+0F8h+lpcValues], rbx; lpcValues
0x1800ac039  mov     [rsp+0F8h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x1800ac03e  lea     rax, [rsp+0F8h+cbMaxSubKeyLen]
0x1800ac043  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800ac048  lea     rax, [rsp+0F8h+cSubKeys]
0x1800ac04d  mov     [rsp+0F8h+lpcSubKeys], rax; lpcSubKeys
0x1800ac052  xor     r9d, r9d; lpReserved
0x1800ac055  xor     r8d, r8d; lpcchClass
0x1800ac058  xor     edx, edx; lpClass
0x1800ac05a  mov     rcx, r14; hKey
0x1800ac05d  call    cs:__imp_RegQueryInfoKeyW
0x1800ac064  nop     dword ptr [rax+rax+00h]
0x1800ac069  test    eax, eax
0x1800ac06b  jnz     loc_1800AC202
0x1800ac071  xorps   xmm0, xmm0
0x1800ac074  movdqu  xmmword ptr [rsp+0F8h+lpName], xmm0
0x1800ac07d  mov     [rsp+0F8h+var_60], rbx
0x1800ac085  mov     eax, [rsp+0F8h+cbMaxSubKeyLen]
0x1800ac089  inc     eax
0x1800ac08b  mov     [rsp+0F8h+cchName], eax
0x1800ac08f  mov     edx, eax
0x1800ac091  lea     rcx, [rsp+0F8h+lpName]
0x1800ac099  call    ?reserve@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::reserve(unsigned __int64)
0x1800ac09e  mov     edi, ebx
0x1800ac0a0  mov     [rsp+0F8h+var_90], ebx
0x1800ac0a4  mov     [rsp+0F8h+lpcValues], rbx; lpftLastWriteTime
0x1800ac0a9  mov     [rsp+0F8h+lpcbMaxClassLen], rbx; lpcchClass
0x1800ac0ae  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rbx; lpClass
0x1800ac0b3  mov     [rsp+0F8h+lpcSubKeys], rbx; lpReserved
0x1800ac0b8  lea     r9, [rsp+0F8h+cchName]; lpcchName
0x1800ac0bd  mov     r8, [rsp+0F8h+lpName]; lpName
0x1800ac0c5  mov     edx, edi; dwIndex
0x1800ac0c7  mov     rcx, r14; hKey
0x1800ac0ca  call    cs:__imp_RegEnumKeyExW
0x1800ac0d1  nop     dword ptr [rax+rax+00h]
0x1800ac0d6  test    eax, eax
0x1800ac0d8  jnz     loc_1800AC1F5
0x1800ac0de  mov     [rsp+0F8h+phkResult], rbx
0x1800ac0e3  xor     edx, edx
0x1800ac0e5  lea     rcx, [rsp+0F8h+phkResult]
0x1800ac0ea  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ac0ef  lea     rax, [rsp+0F8h+phkResult]
0x1800ac0f4  mov     [rsp+0F8h+lpcSubKeys], rax; phkResult
0x1800ac0f9  mov     r9d, 20019h; samDesired
0x1800ac0ff  xor     r8d, r8d; ulOptions
0x1800ac102  mov     rdx, [rsp+0F8h+lpName]; lpSubKey
0x1800ac10a  mov     rcx, r14; hKey
0x1800ac10d  call    cs:__imp_RegOpenKeyExW
0x1800ac114  nop     dword ptr [rax+rax+00h]
0x1800ac119  test    eax, eax
0x1800ac11b  mov     eax, cs:dword_1800FE488
0x1800ac121  jnz     loc_1800AC1A8
0x1800ac127  cmp     eax, 4
0x1800ac12a  jbe     short loc_1800AC156
0x1800ac12c  mov     rax, [rsp+0F8h+lpName]
0x1800ac134  mov     [rsp+0F8h+var_78], rax
0x1800ac13c  lea     rax, [rsp+0F8h+var_78]
0x1800ac144  mov     [rsp+0F8h+lpcSubKeys], rax
0x1800ac149  lea     rdx, word_1800EDDBE
0x1800ac150  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800ac155  nop
0x1800ac156  mov     r9, [rsp+0F8h+lpName]
0x1800ac15e  mov     r8, [rsp+0F8h+phkResult]
0x1800ac163  lea     rdx, [rsp+0F8h+var_48]
0x1800ac16b  call    ?ParseCommandResult@RegistryResults@@AEAA?AUCommandResult@@PEAUHKEY__@@PEBG@Z; RegistryResults::ParseCommandResult(HKEY__ *,ushort const *)
0x1800ac170  nop
0x1800ac171  mov     r8, rax
0x1800ac174  mov     rdx, [rsi]
0x1800ac177  mov     rcx, rsi
0x1800ac17a  call    ??$_Emplace@UCommandResult@@@?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAAPEAU?$_List_node@UCommandResult@@PEAX@1@QEAU21@$$QEAUCommandResult@@@Z; std::list<CommandResult>::_Emplace<CommandResult>(std::_List_node<CommandResult,void *> * const,CommandResult &&)
0x1800ac17f  nop
0x1800ac180  lea     rcx, [rsp+0F8h+var_48]
0x1800ac188  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ac18d  nop
0x1800ac18e  jmp     short loc_1800AC1D6
0x1800ac190  xor     ebx, ebx
0x1800ac192  mov     edi, [rsp+0F8h+var_90]
0x1800ac196  mov     rsi, [rsp+0F8h+var_58]
0x1800ac19e  mov     r14, [rsp+0F8h+var_50]
0x1800ac1a6  jmp     short loc_1800AC1D6
0x1800ac1a8  cmp     eax, 2
0x1800ac1ab  jbe     short loc_1800AC1D6
0x1800ac1ad  mov     rax, [rsp+0F8h+lpName]
0x1800ac1b5  mov     [rsp+0F8h+var_78], rax
0x1800ac1bd  lea     rax, [rsp+0F8h+var_78]
0x1800ac1c5  mov     [rsp+0F8h+lpcSubKeys], rax
0x1800ac1ca  lea     rdx, unk_1800EDFC0
0x1800ac1d1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800ac1d6  mov     eax, [rsp+0F8h+cbMaxSubKeyLen]
0x1800ac1da  inc     eax
0x1800ac1dc  mov     [rsp+0F8h+cchName], eax
0x1800ac1e0  inc     edi
0x1800ac1e2  mov     [rsp+0F8h+var_90], edi
0x1800ac1e6  lea     rcx, [rsp+0F8h+phkResult]
0x1800ac1eb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ac1f0  jmp     loc_1800AC0A4
0x1800ac1f5  lea     rcx, [rsp+0F8h+lpName]
0x1800ac1fd  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800ac202  mov     rax, rsi
0x1800ac205  mov     rcx, [rsp+0F8h+var_20]
0x1800ac20d  xor     rcx, rsp; StackCookie
0x1800ac210  call    __security_check_cookie
0x1800ac215  mov     rbx, [rsp+0F8h+arg_0]
0x1800ac21d  add     rsp, 0E0h
0x1800ac224  pop     r14
0x1800ac226  pop     rdi
0x1800ac227  pop     rsi
0x1800ac228  retn
```
