# GetKeySubkeyNames(HKEY__ * const &)

- ea: `0x180022560`
- end: `0x1800226db`
- name: `?GetKeySubkeyNames@@YA?AV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBQEAUHKEY__@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d480`
- `0x180020cf8`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000ccf4`
- `0x18000cd50`
- `0x1800151fc`
- `0x1800198f4`
- `0x18001bbe4`
- `0x1800221cc`
- `0x180022560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800225e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800225e8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180022654`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180022654`

## string_xrefs

- `0x1800225f9`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`
- `0x1800226c9`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
WCHAR *__fastcall GetKeySubkeyNames(WCHAR *a1, HKEY *a2)
{
  unsigned int v4; // eax
  DWORD i; // ebx
  unsigned int v6; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-69h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-69h]
  DWORD cSubKeys; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbMaxSubKeyLen[2]; // [rsp+64h] [rbp-25h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-1Dh] BYREF
  LPWSTR lpName[4]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v14[16]; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v15[32]; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  lpName[3] = a1;
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(a1);
  cbMaxSubKeyLen[1] = 1;
  cSubKeys = 0;
  cbMaxSubKeyLen[0] = 0;
  v4 = RegQueryInfoKeyW(*a2, 0, 0, 0, &cSubKeys, cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x6E,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
      (const char *)v4,
      lpcSubKeys);
  for ( i = 0; i < cSubKeys; ++i )
  {
    std::vector<unsigned short>::vector<unsigned short>(lpName, cbMaxSubKeyLen[0] + 1);
    cchName = lpName[1] - lpName[0];
    v6 = RegEnumKeyExW(*a2, i, lpName[0], &cchName, 0, 0, 0, 0);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x75,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
        (const char *)v6,
        lpcSubKeysa);
    std::wstring::wstring((__int64)v15, (__int64)lpName[0]);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      (float *)a1,
      (__int64)v14,
      (__int64)v15);
    std::wstring::_Tidy_deallocate((__int64)v15);
    std::vector<unsigned short>::_Tidy(lpName);
  }
  return a1;
}

```

## disassembly

```asm
0x180022560  mov     [rsp-8+arg_10], rbx
0x180022565  mov     [rsp-8+arg_18], rsi
0x18002256a  push    rbp
0x18002256b  push    rdi
0x18002256c  push    r14
0x18002256e  lea     rbp, [rsp-47h]
0x180022573  sub     rsp, 0D0h
0x18002257a  mov     rax, cs:__security_cookie
0x180022581  xor     rax, rsp
0x180022584  mov     [rbp+57h+var_20], rax
0x180022588  mov     rsi, rdx
0x18002258b  mov     rdi, rcx
0x18002258e  mov     [rbp+57h+var_58], rcx
0x180022592  xor     r14d, r14d
0x180022595  mov     [rbp+57h+var_78], r14d
0x180022599  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18002259e  mov     [rbp+57h+var_78], 1
0x1800225a5  mov     [rbp+57h+cSubKeys], r14d
0x1800225a9  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x1800225ad  mov     [rsp+0E0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800225b2  mov     [rsp+0E0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800225b7  mov     [rsp+0E0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800225bc  mov     [rsp+0E0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800225c1  mov     [rsp+0E0h+lpcValues], r14; lpcValues
0x1800225c6  mov     [rsp+0E0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800225cb  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800225cf  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800225d4  lea     rax, [rbp+57h+cSubKeys]
0x1800225d8  mov     [rsp+0E0h+lpcSubKeys], rax; unsigned int
0x1800225dd  xor     r9d, r9d; lpReserved
0x1800225e0  xor     r8d, r8d; lpcchClass
0x1800225e3  xor     edx, edx; lpClass
0x1800225e5  mov     rcx, [rsi]; hKey
0x1800225e8  call    cs:__imp_RegQueryInfoKeyW
0x1800225ee  mov     rcx, [rbp+5Fh]; this
0x1800225f2  test    eax, eax
0x1800225f4  jz      short loc_18002260A
0x1800225f6  mov     r9d, eax; char *
0x1800225f9  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x180022600  lea     edx, [r14+6Eh]; void *
0x180022604  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002260a  mov     ebx, r14d
0x18002260d  cmp     [rbp+57h+cSubKeys], r14d
0x180022611  jbe     loc_18002269F
0x180022617  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x18002261a  inc     edx
0x18002261c  lea     rcx, [rbp+57h+lpName]
0x180022620  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180022625  nop
0x180022626  mov     r8, [rbp+57h+lpName]; lpName
0x18002262a  mov     rax, [rbp+57h+var_68]
0x18002262e  sub     rax, r8
0x180022631  sar     rax, 1
0x180022634  mov     [rbp+57h+cchName], eax
0x180022637  mov     [rsp+0E0h+lpcValues], r14; lpftLastWriteTime
0x18002263c  mov     [rsp+0E0h+lpcbMaxClassLen], r14; lpcchClass
0x180022641  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r14; lpClass
0x180022646  mov     [rsp+0E0h+lpcSubKeys], r14; unsigned int
0x18002264b  lea     r9, [rbp+57h+cchName]; lpcchName
0x18002264f  mov     edx, ebx; dwIndex
0x180022651  mov     rcx, [rsi]; hKey
0x180022654  call    cs:__imp_RegEnumKeyExW
0x18002265a  mov     rcx, [rbp+5Fh]; this
0x18002265e  test    eax, eax
0x180022660  jnz     short loc_1800226C6
0x180022662  mov     rdx, [rbp+57h+lpName]
0x180022666  lea     rcx, [rbp+57h+var_40]
0x18002266a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002266f  nop
0x180022670  lea     r8, [rbp+57h+var_40]
0x180022674  lea     rdx, [rbp+57h+var_50]
0x180022678  mov     rcx, rdi
0x18002267b  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x180022680  nop
0x180022681  lea     rcx, [rbp+57h+var_40]
0x180022685  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002268a  nop
0x18002268b  lea     rcx, [rbp+57h+lpName]
0x18002268f  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180022694  inc     ebx
0x180022696  cmp     ebx, [rbp+57h+cSubKeys]
0x180022699  jb      loc_180022617
0x18002269f  mov     rax, rdi
0x1800226a2  mov     rcx, [rbp+57h+var_20]
0x1800226a6  xor     rcx, rsp; StackCookie
0x1800226a9  call    __security_check_cookie
0x1800226ae  lea     r11, [rsp+0E0h+var_10]
0x1800226b6  mov     rbx, [r11+30h]
0x1800226ba  mov     rsi, [r11+38h]
0x1800226be  mov     rsp, r11
0x1800226c1  pop     r14
0x1800226c3  pop     rdi
0x1800226c4  pop     rbp
0x1800226c5  retn
0x1800226c6  mov     r9d, eax; char *
0x1800226c9  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800226d0  mov     edx, 75h ; 'u'; void *
0x1800226d5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
