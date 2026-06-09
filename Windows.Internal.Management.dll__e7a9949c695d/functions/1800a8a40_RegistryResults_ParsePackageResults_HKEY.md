# RegistryResults::ParsePackageResults(HKEY__ *)

- ea: `0x1800a8a40`
- end: `0x1800a8d0f`
- name: `?ParsePackageResults@RegistryResults@@AEAA?AV?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@PEAUHKEY__@@@Z`
- size: `719`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a8650`

## callees

- `0x18000377c`
- `0x180004d50`
- `0x18000523c`
- `0x180012ae8`
- `0x180015f70`
- `0x1800169b8`
- `0x18003a430`
- `0x18003b004`
- `0x1800a1be0`
- `0x1800a85e4`
- `0x1800a8608`
- `0x1800a8884`
- `0x1800a8a40`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a8bf5`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a8bf5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8b7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8b7e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a8b41`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a8b41`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a8ada`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a8ada`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall RegistryResults::ParsePackageResults(__int64 a1, _QWORD *a2, HKEY a3)
{
  HKEY v3; // r12
  _QWORD *v4; // rdi
  DWORD v5; // esi
  __int64 v6; // rcx
  int v7; // r8d
  int v8; // r9d
  const struct CommandResult *v9; // r13
  __int64 v10; // r15
  _QWORD *v11; // r14
  _QWORD *v12; // rcx
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-B4h] BYREF
  DWORD v16; // [rsp+68h] [rbp-B0h]
  HKEY phkResult; // [rsp+70h] [rbp-A8h] BYREF
  int v18; // [rsp+78h] [rbp-A0h]
  DWORD cSubKeys; // [rsp+7Ch] [rbp-9Ch] BYREF
  LPWSTR v20; // [rsp+80h] [rbp-98h] BYREF
  LPWSTR lpName[2]; // [rsp+88h] [rbp-90h] BYREF
  __int64 v22; // [rsp+98h] [rbp-80h]
  _QWORD *v23; // [rsp+A0h] [rbp-78h] BYREF
  _QWORD *v24; // [rsp+A8h] [rbp-70h]
  _QWORD *v25; // [rsp+B0h] [rbp-68h]
  HKEY v26; // [rsp+B8h] [rbp-60h]
  _BYTE v27[40]; // [rsp+C0h] [rbp-58h] BYREF

  v3 = a3;
  v4 = a2;
  v25 = a2;
  v26 = a3;
  std::list<CommandResult>::list<CommandResult>(a2);
  v18 = 1;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( !RegQueryInfoKeyW(v3, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    *(_OWORD *)lpName = 0;
    v22 = 0;
    cchName = cbMaxSubKeyLen + 1;
    std::vector<unsigned short>::reserve(lpName, cbMaxSubKeyLen + 1);
    v5 = 0;
    v16 = 0;
    while ( !RegEnumKeyExW(v3, v5, lpName[0], &cchName, 0, 0, 0, 0) )
    {
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      if ( RegOpenKeyExW(v3, lpName[0], 0, 0x20019u, &phkResult) )
      {
        if ( (unsigned int)dword_1800FA480 > 2 )
        {
          v20 = lpName[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v6,
            (unsigned int)&unk_1800EA1E0,
            v7,
            v8,
            (__int64)&v20);
        }
      }
      else
      {
        if ( (unsigned int)dword_1800FA480 > 4 )
        {
          v20 = lpName[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v6,
            (unsigned int)&word_1800E9FDE,
            v7,
            v8,
            (__int64)&v20);
        }
        try
        {
          v9 = (const struct CommandResult *)RegistryResults::ParseCommandResult(v6, v27, phkResult, lpName[0]);
          if ( v4[1] == 0x492492492492492LL )
            std::_Xlength_error("list too long");
          v10 = *v4;
          v23 = v4;
          v24 = 0;
          v11 = operator new(0x38u);
          v24 = v11;
          CommandResult::CommandResult((CommandResult *)(v11 + 2), v9);
          ++v4[1];
          v12 = *(_QWORD **)(v10 + 8);
          *v11 = v10;
          v11[1] = v12;
          v24 = 0;
          *(_QWORD *)(v10 + 8) = v11;
          *v12 = v11;
          std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>(&v23);
          std::wstring::_Tidy_deallocate(v27);
        }
        catch ( ... )
        {
          v5 = v16;
          v4 = v25;
          v3 = v26;
        }
      }
      cchName = cbMaxSubKeyLen + 1;
      v16 = ++v5;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    std::vector<unsigned short>::_Tidy(lpName);
  }
  return v4;
}

```

## disassembly

```asm
0x1800a8a40  mov     r11, rsp
0x1800a8a43  mov     [r11+8], rbx
0x1800a8a47  mov     [r11+20h], rsi
0x1800a8a4b  push    rdi
0x1800a8a4c  push    r12
0x1800a8a4e  push    r13
0x1800a8a50  push    r14
0x1800a8a52  push    r15
0x1800a8a54  sub     rsp, 0F0h
0x1800a8a5b  mov     rax, cs:__security_cookie
0x1800a8a62  xor     rax, rsp
0x1800a8a65  mov     [rsp+118h+var_30], rax
0x1800a8a6d  mov     r12, r8
0x1800a8a70  mov     rdi, rdx
0x1800a8a73  mov     [r11-68h], rdx
0x1800a8a77  mov     [rsp+118h+var_60], r8
0x1800a8a7f  xor     ebx, ebx
0x1800a8a81  mov     [rsp+118h+var_A0], ebx
0x1800a8a85  mov     rcx, rdx
0x1800a8a88  call    ??0?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@XZ; std::list<CommandResult>::list<CommandResult>(void)
0x1800a8a8d  mov     [rsp+118h+var_A0], 1
0x1800a8a95  mov     [rsp+118h+cSubKeys], ebx
0x1800a8a99  mov     [rsp+118h+cbMaxSubKeyLen], ebx
0x1800a8a9d  mov     [rsp+118h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1800a8aa2  mov     [rsp+118h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x1800a8aa7  mov     [rsp+118h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x1800a8aac  mov     [rsp+118h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x1800a8ab1  mov     [rsp+118h+lpcValues], rbx; lpcValues
0x1800a8ab6  mov     [rsp+118h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x1800a8abb  lea     rax, [rsp+118h+cbMaxSubKeyLen]
0x1800a8ac0  mov     [rsp+118h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800a8ac5  lea     rax, [rsp+118h+cSubKeys]
0x1800a8aca  mov     [rsp+118h+lpcSubKeys], rax; lpcSubKeys
0x1800a8acf  xor     r9d, r9d; lpReserved
0x1800a8ad2  xor     r8d, r8d; lpcchClass
0x1800a8ad5  xor     edx, edx; lpClass
0x1800a8ad7  mov     rcx, r12; hKey
0x1800a8ada  call    cs:__imp_RegQueryInfoKeyW
0x1800a8ae0  test    eax, eax
0x1800a8ae2  jnz     loc_1800A8CDE
0x1800a8ae8  xorps   xmm0, xmm0
0x1800a8aeb  movdqu  xmmword ptr [rsp+118h+lpName], xmm0
0x1800a8af4  mov     [rsp+118h+var_80], rbx
0x1800a8afc  mov     eax, [rsp+118h+cbMaxSubKeyLen]
0x1800a8b00  inc     eax
0x1800a8b02  mov     [rsp+118h+cchName], eax
0x1800a8b06  mov     edx, eax
0x1800a8b08  lea     rcx, [rsp+118h+lpName]
0x1800a8b10  call    ?reserve@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::reserve(unsigned __int64)
0x1800a8b15  mov     esi, ebx
0x1800a8b17  mov     [rsp+118h+var_B0], ebx
0x1800a8b1b  mov     [rsp+118h+lpcValues], rbx; lpftLastWriteTime
0x1800a8b20  mov     [rsp+118h+lpcbMaxClassLen], rbx; lpcchClass
0x1800a8b25  mov     [rsp+118h+lpcbMaxSubKeyLen], rbx; lpClass
0x1800a8b2a  mov     [rsp+118h+lpcSubKeys], rbx; lpReserved
0x1800a8b2f  lea     r9, [rsp+118h+cchName]; lpcchName
0x1800a8b34  mov     r8, [rsp+118h+lpName]; lpName
0x1800a8b3c  mov     edx, esi; dwIndex
0x1800a8b3e  mov     rcx, r12; hKey
0x1800a8b41  call    cs:__imp_RegEnumKeyExW
0x1800a8b47  test    eax, eax
0x1800a8b49  jnz     loc_1800A8CD1
0x1800a8b4f  mov     [rsp+118h+phkResult], rbx
0x1800a8b54  xor     edx, edx
0x1800a8b56  lea     rcx, [rsp+118h+phkResult]
0x1800a8b5b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a8b60  lea     rax, [rsp+118h+phkResult]
0x1800a8b65  mov     [rsp+118h+lpcSubKeys], rax; phkResult
0x1800a8b6a  mov     r9d, 20019h; samDesired
0x1800a8b70  xor     r8d, r8d; ulOptions
0x1800a8b73  mov     rdx, [rsp+118h+lpName]; lpSubKey
0x1800a8b7b  mov     rcx, r12; hKey
0x1800a8b7e  call    cs:__imp_RegOpenKeyExW
0x1800a8b84  test    eax, eax
0x1800a8b86  mov     eax, cs:dword_1800FA480
0x1800a8b8c  jnz     loc_1800A8C84
0x1800a8b92  cmp     eax, 4
0x1800a8b95  jbe     short loc_1800A8BC1
0x1800a8b97  mov     rax, [rsp+118h+lpName]
0x1800a8b9f  mov     [rsp+118h+var_98], rax
0x1800a8ba7  lea     rax, [rsp+118h+var_98]
0x1800a8baf  mov     [rsp+118h+lpcSubKeys], rax
0x1800a8bb4  lea     rdx, word_1800E9FDE
0x1800a8bbb  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800a8bc0  nop
0x1800a8bc1  mov     r9, [rsp+118h+lpName]
0x1800a8bc9  mov     r8, [rsp+118h+phkResult]
0x1800a8bce  lea     rdx, [rsp+118h+var_58]
0x1800a8bd6  call    ?ParseCommandResult@RegistryResults@@AEAA?AUCommandResult@@PEAUHKEY__@@PEBG@Z; RegistryResults::ParseCommandResult(HKEY__ *,ushort const *)
0x1800a8bdb  mov     r13, rax
0x1800a8bde  mov     rax, 492492492492492h
0x1800a8be8  cmp     [rdi+8], rax
0x1800a8bec  jnz     short loc_1800A8BFB
0x1800a8bee  lea     rcx, aListTooLong; "list too long"
0x1800a8bf5  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800a8bfb  mov     r15, [rdi]
0x1800a8bfe  mov     [rsp+118h+var_78], rdi
0x1800a8c06  mov     [rsp+118h+var_70], rbx
0x1800a8c0e  mov     ecx, 38h ; '8'; Size
0x1800a8c13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a8c18  mov     r14, rax
0x1800a8c1b  mov     [rsp+118h+var_70], rax
0x1800a8c23  lea     rcx, [rax+10h]; this
0x1800a8c27  mov     rdx, r13; struct CommandResult *
0x1800a8c2a  call    ??0CommandResult@@QEAA@AEBU0@@Z; CommandResult::CommandResult(CommandResult const &)
0x1800a8c2f  nop
0x1800a8c30  inc     qword ptr [rdi+8]
0x1800a8c34  mov     rcx, [r15+8]
0x1800a8c38  mov     [r14], r15
0x1800a8c3b  mov     [r14+8], rcx
0x1800a8c3f  mov     [rsp+118h+var_70], rbx
0x1800a8c47  mov     [r15+8], r14
0x1800a8c4b  mov     [rcx], r14
0x1800a8c4e  lea     rcx, [rsp+118h+var_78]
0x1800a8c56  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>(void)
0x1800a8c5b  nop
0x1800a8c5c  lea     rcx, [rsp+118h+var_58]
0x1800a8c64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8c69  nop
0x1800a8c6a  jmp     short loc_1800A8CB2
0x1800a8c6c  xor     ebx, ebx
0x1800a8c6e  mov     esi, [rsp+118h+var_B0]
0x1800a8c72  mov     rdi, [rsp+118h+var_68]
0x1800a8c7a  mov     r12, [rsp+118h+var_60]
0x1800a8c82  jmp     short loc_1800A8CB2
0x1800a8c84  cmp     eax, 2
0x1800a8c87  jbe     short loc_1800A8CB2
0x1800a8c89  mov     rax, [rsp+118h+lpName]
0x1800a8c91  mov     [rsp+118h+var_98], rax
0x1800a8c99  lea     rax, [rsp+118h+var_98]
0x1800a8ca1  mov     [rsp+118h+lpcSubKeys], rax
0x1800a8ca6  lea     rdx, unk_1800EA1E0
0x1800a8cad  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800a8cb2  mov     eax, [rsp+118h+cbMaxSubKeyLen]
0x1800a8cb6  inc     eax
0x1800a8cb8  mov     [rsp+118h+cchName], eax
0x1800a8cbc  inc     esi
0x1800a8cbe  mov     [rsp+118h+var_B0], esi
0x1800a8cc2  lea     rcx, [rsp+118h+phkResult]
0x1800a8cc7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a8ccc  jmp     loc_1800A8B1B
0x1800a8cd1  lea     rcx, [rsp+118h+lpName]
0x1800a8cd9  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a8cde  mov     rax, rdi
0x1800a8ce1  mov     rcx, [rsp+118h+var_30]
0x1800a8ce9  xor     rcx, rsp; StackCookie
0x1800a8cec  call    __security_check_cookie
0x1800a8cf1  lea     r11, [rsp+118h+var_28]
0x1800a8cf9  mov     rbx, [r11+30h]
0x1800a8cfd  mov     rsi, [r11+48h]
0x1800a8d01  mov     rsp, r11
0x1800a8d04  pop     r15
0x1800a8d06  pop     r14
0x1800a8d08  pop     r13
0x1800a8d0a  pop     r12
0x1800a8d0c  pop     rdi
0x1800a8d0d  retn
```
