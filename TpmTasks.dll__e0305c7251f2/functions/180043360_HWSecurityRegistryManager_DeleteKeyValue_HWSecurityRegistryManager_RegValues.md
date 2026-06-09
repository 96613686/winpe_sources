# HWSecurityRegistryManager::DeleteKeyValue(HWSecurityRegistryManager::RegValues)

- ea: `0x180043360`
- end: `0x1800434ae`
- name: `?DeleteKeyValue@HWSecurityRegistryManager@@SAJW4RegValues@1@@Z`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d0d4`
- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x18001a42c`
- `0x180023634`
- `0x18002386c`
- `0x180042a6c`
- `0x180043360`
- `0x1800436ec`
- `0x180043d34`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180043473`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180043481`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180043473`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180043481`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180043411`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180043411`

## string_xrefs

- `0x180043453`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HWSecurityRegistryManager::DeleteKeyValue(__int64 a1)
{
  unsigned int v1; // ebx
  __int64 ValueName; // rax
  const WCHAR *v3; // rdi
  __int64 v4; // rcx
  __int64 KeyPath; // rax
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-78h] BYREF
  _QWORD v11[2]; // [rsp+28h] [rbp-70h] BYREF
  __int64 v12; // [rsp+38h] [rbp-60h]
  _BYTE v13[32]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v14[32]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v1 = a1;
  v10 = a1;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    a1,
    v11,
    &v10);
  if ( *(_BYTE *)(v12 + 25) || v1 < *(_DWORD *)(v12 + 32) )
    goto LABEL_12;
  ValueName = HWSecurityRegistryManager::RegistryValueEntry::GetValueName(v12 + 40, v14);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ValueName);
  v10 = v1;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v4,
    v11,
    &v10);
  if ( *(_BYTE *)(v12 + 25) || v1 < *(_DWORD *)(v12 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
LABEL_12:
    std::_Xout_of_range("invalid map<K, T> key");
    return (unsigned int)v10;
  }
  KeyPath = HWSecurityRegistryManager::RegistryValueEntry::GetKeyPath(v12 + 40, v13);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
  v7 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, v6, v3);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  std::wstring::_Tidy_deallocate(v13);
  std::wstring::_Tidy_deallocate(v14);
  if ( (v8 & 0x80000000) == 0 )
    return 0;
  result = 2147942402LL;
  if ( v8 != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
      (const char *)v8,
      v10);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180043360  mov     [rsp+arg_0], rbx
0x180043365  push    rdi
0x180043366  sub     rsp, 90h
0x18004336d  mov     rax, cs:__security_cookie
0x180043374  xor     rax, rsp
0x180043377  mov     [rsp+98h+var_18], rax
0x18004337f  mov     ebx, ecx
0x180043381  mov     [rsp+98h+var_78], ecx
0x180043385  lea     r8, [rsp+98h+var_78]
0x18004338a  lea     rdx, [rsp+98h+var_70]
0x18004338f  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180043394  mov     rcx, [rsp+98h+var_60]
0x180043399  cmp     byte ptr [rcx+19h], 0
0x18004339d  jnz     loc_18004347A
0x1800433a3  cmp     ebx, [rcx+20h]
0x1800433a6  jb      loc_18004347A
0x1800433ac  add     rcx, 28h ; '('
0x1800433b0  lea     rdx, [rsp+98h+var_38]
0x1800433b5  call    ?GetValueName@RegistryValueEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryValueEntry::GetValueName(void)
0x1800433ba  nop
0x1800433bb  mov     rcx, rax
0x1800433be  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800433c3  mov     rdi, rax
0x1800433c6  mov     [rsp+98h+var_78], ebx; int
0x1800433ca  lea     r8, [rsp+98h+var_78]
0x1800433cf  lea     rdx, [rsp+98h+var_70]
0x1800433d4  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x1800433d9  mov     rcx, [rsp+98h+var_60]
0x1800433de  cmp     byte ptr [rcx+19h], 0
0x1800433e2  jnz     loc_18004346C
0x1800433e8  cmp     ebx, [rcx+20h]
0x1800433eb  jb      short loc_18004346C
0x1800433ed  add     rcx, 28h ; '('
0x1800433f1  lea     rdx, [rsp+98h+var_58]
0x1800433f6  call    ?GetKeyPath@RegistryValueEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryValueEntry::GetKeyPath(void)
0x1800433fb  nop
0x1800433fc  mov     rcx, rax
0x1800433ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043404  mov     r8, rdi; lpValueName
0x180043407  mov     rdx, rax; lpSubKey
0x18004340a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043411  call    cs:__imp_RegDeleteKeyValueW
0x180043417  mov     ebx, eax
0x180043419  test    eax, eax
0x18004341b  jle     short loc_180043426
0x18004341d  movzx   ebx, ax
0x180043420  or      ebx, 80070000h
0x180043426  lea     rcx, [rsp+98h+var_58]
0x18004342b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043430  nop
0x180043431  lea     rcx, [rsp+98h+var_38]
0x180043436  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004343b  test    ebx, ebx
0x18004343d  jns     short loc_180043468
0x18004343f  mov     eax, 80070002h
0x180043444  cmp     ebx, eax
0x180043446  jz      short loc_18004348C
0x180043448  mov     rcx, [rsp+98h]; this
0x180043450  mov     r9d, ebx; char *
0x180043453  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x18004345a  mov     edx, 1D1h; void *
0x18004345f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043464  mov     eax, ebx
0x180043466  jmp     short loc_18004348C
0x180043468  xor     eax, eax
0x18004346a  jmp     short loc_18004348C
0x18004346c  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180043473  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180043479  nop
0x18004347a  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180043481  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180043487  nop
0x180043488  mov     eax, [rsp+98h+var_78]
0x18004348c  mov     rcx, [rsp+98h+var_18]
0x180043494  xor     rcx, rsp; StackCookie
0x180043497  call    __security_check_cookie
0x18004349c  mov     rbx, [rsp+98h+arg_0]
0x1800434a4  add     rsp, 90h
0x1800434ab  pop     rdi
0x1800434ac  retn
```
