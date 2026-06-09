# Reg::OpenKey

- ea: `0x1800143b0`
- end: `0x1800145d0`
- name: `Reg::OpenKey`
- size: `544`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012b84`
- `0x180013b70`
- `0x180014080`
- `0x1800145d8`

## callees

- `0x180010c8c`
- `0x180014360`
- `0x1800143b0`
- `0x18001475c`
- `0x180015a18`
- `0x18001b004`
- `0x1800798e8`
- `0x1800d7f50`
- `0x1800d8084`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014564`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014564`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180014403`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800144b1`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180014403`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800144b1`

## string_xrefs

- `0x180014428`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`
- `0x1800144c2`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`
- `0x180014575`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HKEY __fastcall Reg::OpenKey(__int64 a1, __int64 a2, REGSAM a3)
{
  int PersistedRegistryLocationW; // eax
  __int64 v6; // r8
  unsigned __int64 v7; // r9
  unsigned __int64 v8; // rbx
  char *v9; // rsi
  unsigned __int64 v10; // rcx
  WCHAR *v11; // rax
  size_t v12; // rbx
  unsigned int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned __int64 v16; // rbx
  char *v17; // rdi
  unsigned __int64 v18; // rcx
  WCHAR *v19; // rax
  size_t v20; // rbx
  unsigned int v21; // eax
  HKEY v22; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-20h] BYREF
  void *v26; // [rsp+38h] [rbp-18h]
  __int64 v27; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY v29; // [rsp+70h] [rbp+20h] BYREF
  __int64 v30; // [rsp+78h] [rbp+28h] BYREF

  v30 = a2;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(&lpSubKey);
  if ( !a1 )
  {
    std::vector<unsigned short>::_Assign_counted_range<unsigned short const *>(
      &lpSubKey,
      L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\WebSignIn\\Navigation",
      67);
    goto LABEL_24;
  }
  LODWORD(v30) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 a1,
                                 L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\WebSignIn\\Navigation",
                                 0,
                                 0);
  if ( PersistedRegistryLocationW > 0 )
    v7 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  else
    v7 = (unsigned int)PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW != 234 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
      (const char *)v7,
      (int)&v30);
  v8 = (unsigned __int64)(unsigned int)v30 >> 1;
  v9 = (char *)v26;
  v10 = ((_BYTE *)v26 - (_BYTE *)lpSubKey) >> 1;
  if ( v8 < v10 )
  {
    v11 = (WCHAR *)&lpSubKey[v8];
LABEL_13:
    v26 = v11;
    goto LABEL_14;
  }
  if ( v8 > v10 )
  {
    if ( v8 <= (v27 - (__int64)lpSubKey) >> 1 )
    {
      v12 = 2 * (v8 - v10);
      memset_0(v26, 0, v12);
      v11 = (WCHAR *)&v9[v12];
      goto LABEL_13;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(
      &lpSubKey,
      (unsigned __int64)(unsigned int)v30 >> 1,
      v6,
      v7);
  }
LABEL_14:
  v13 = GetPersistedRegistryLocationW(
          a1,
          L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\WebSignIn\\Navigation",
          lpSubKey,
          (unsigned int)v30);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
      (const char *)v13,
      (unsigned int)&v30);
  v16 = (unsigned __int64)(unsigned int)v30 >> 1;
  v17 = (char *)v26;
  v18 = ((_BYTE *)v26 - (_BYTE *)lpSubKey) >> 1;
  if ( v16 >= v18 )
  {
    if ( v16 <= v18 )
      goto LABEL_24;
    if ( v16 > (v27 - (__int64)lpSubKey) >> 1 )
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(
        &lpSubKey,
        (unsigned __int64)(unsigned int)v30 >> 1,
        v14,
        v15);
      goto LABEL_24;
    }
    v20 = 2 * (v16 - v18);
    memset_0(v26, 0, v20);
    v19 = (WCHAR *)&v17[v20];
  }
  else
  {
    v19 = (WCHAR *)&lpSubKey[v16];
  }
  v26 = v19;
LABEL_24:
  v29 = 0;
  v21 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, a3, &v29);
  if ( v21 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
      (const char *)v21,
      phkResult);
  v22 = v29;
  v29 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
  if ( lpSubKey )
    std::_Deallocate<16>((void *)lpSubKey, (struct std::nothrow_t *)(2 * ((v27 - (__int64)lpSubKey) >> 1)));
  return v22;
}

```

## disassembly

```asm
0x1800143b0  mov     [rsp-18h+arg_10], rbx
0x1800143b5  mov     [rsp-18h+arg_18], rsi
0x1800143ba  mov     [rsp-18h+arg_8], rdx
0x1800143bf  push    rbp
0x1800143c0  push    rdi
0x1800143c1  push    r14
0x1800143c3  mov     rbp, rsp
0x1800143c6  sub     rsp, 50h
0x1800143ca  mov     r14d, r8d
0x1800143cd  mov     rdi, rcx
0x1800143d0  lea     rcx, [rbp+lpSubKey]
0x1800143d4  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x1800143d9  nop
0x1800143da  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x1800143e1  test    rdi, rdi
0x1800143e4  jz      loc_180014532
0x1800143ea  mov     dword ptr [rbp+arg_8], 0
0x1800143f1  lea     rax, [rbp+arg_8]
0x1800143f5  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800143fa  xor     r9d, r9d
0x1800143fd  xor     r8d, r8d
0x180014400  mov     rcx, rdi
0x180014403  call    cs:__imp_GetPersistedRegistryLocationW
0x180014409  test    eax, eax
0x18001440b  jg      short loc_180014412
0x18001440d  mov     r9d, eax
0x180014410  jmp     short loc_18001441D
0x180014412  movzx   r9d, ax
0x180014416  or      r9d, 80070000h; char *
0x18001441d  mov     rcx, [rbp+18h]; this
0x180014421  cmp     eax, 0EAh
0x180014426  jz      short loc_18001443A
0x180014428  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x18001442f  mov     edx, 11h; void *
0x180014434  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001443a  mov     ebx, dword ptr [rbp+arg_8]
0x18001443d  shr     rbx, 1
0x180014440  mov     rdx, [rbp+lpSubKey]
0x180014444  mov     rsi, [rbp+var_18]
0x180014448  mov     rcx, rsi
0x18001444b  sub     rcx, rdx
0x18001444e  sar     rcx, 1
0x180014451  cmp     rbx, rcx
0x180014454  jnb     short loc_18001445C
0x180014456  lea     rax, [rdx+rbx*2]
0x18001445a  jmp     short loc_180014492
0x18001445c  jbe     short loc_180014496
0x18001445e  mov     rax, [rbp+var_10]
0x180014462  sub     rax, rdx
0x180014465  sar     rax, 1
0x180014468  cmp     rbx, rax
0x18001446b  jbe     short loc_18001447B
0x18001446d  mov     rdx, rbx
0x180014470  lea     rcx, [rbp+lpSubKey]
0x180014474  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180014479  jmp     short loc_180014496
0x18001447b  sub     rbx, rcx
0x18001447e  add     rbx, rbx
0x180014481  mov     r8, rbx; Size
0x180014484  xor     edx, edx; Val
0x180014486  mov     rcx, rsi; void *
0x180014489  call    memset_0
0x18001448e  lea     rax, [rbx+rsi]
0x180014492  mov     [rbp+var_18], rax
0x180014496  lea     rax, [rbp+arg_8]
0x18001449a  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x18001449f  mov     r9d, dword ptr [rbp+arg_8]
0x1800144a3  mov     r8, [rbp+lpSubKey]
0x1800144a7  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x1800144ae  mov     rcx, rdi
0x1800144b1  call    cs:__imp_GetPersistedRegistryLocationW
0x1800144b7  mov     rcx, [rbp+18h]; this
0x1800144bb  test    eax, eax
0x1800144bd  jz      short loc_1800144D4
0x1800144bf  mov     r9d, eax; char *
0x1800144c2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800144c9  mov     edx, 15h; void *
0x1800144ce  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800144d4  mov     ebx, dword ptr [rbp+arg_8]
0x1800144d7  shr     rbx, 1
0x1800144da  mov     rdx, [rbp+lpSubKey]
0x1800144de  mov     rdi, [rbp+var_18]
0x1800144e2  mov     rcx, rdi
0x1800144e5  sub     rcx, rdx
0x1800144e8  sar     rcx, 1
0x1800144eb  cmp     rbx, rcx
0x1800144ee  jnb     short loc_1800144F6
0x1800144f0  lea     rax, [rdx+rbx*2]
0x1800144f4  jmp     short loc_18001452C
0x1800144f6  jbe     short loc_180014542
0x1800144f8  mov     rax, [rbp+var_10]
0x1800144fc  sub     rax, rdx
0x1800144ff  sar     rax, 1
0x180014502  cmp     rbx, rax
0x180014505  jbe     short loc_180014515
0x180014507  mov     rdx, rbx
0x18001450a  lea     rcx, [rbp+lpSubKey]
0x18001450e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180014513  jmp     short loc_180014542
0x180014515  sub     rbx, rcx
0x180014518  add     rbx, rbx
0x18001451b  mov     r8, rbx; Size
0x18001451e  xor     edx, edx; Val
0x180014520  mov     rcx, rdi; void *
0x180014523  call    memset_0
0x180014528  lea     rax, [rbx+rdi]
0x18001452c  mov     [rbp+var_18], rax
0x180014530  jmp     short loc_180014542
0x180014532  mov     r8d, 43h ; 'C'
0x180014538  lea     rcx, [rbp+lpSubKey]
0x18001453c  call    ??$_Assign_counted_range@PEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAXPEBG_K@Z; std::vector<ushort>::_Assign_counted_range<ushort const *>(ushort const *,unsigned __int64)
0x180014541  nop
0x180014542  mov     [rbp+arg_0], 0
0x18001454a  lea     rax, [rbp+arg_0]
0x18001454e  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x180014553  mov     r9d, r14d; samDesired
0x180014556  xor     r8d, r8d; ulOptions
0x180014559  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001455d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014564  call    cs:__imp_RegOpenKeyExW
0x18001456a  mov     rcx, [rbp+18h]; this
0x18001456e  test    eax, eax
0x180014570  jz      short loc_180014587
0x180014572  mov     r9d, eax; char *
0x180014575  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x18001457c  mov     edx, 1Eh; void *
0x180014581  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180014587  mov     rbx, [rbp+arg_0]
0x18001458b  mov     [rbp+arg_0], 0
0x180014593  lea     rcx, [rbp+arg_0]
0x180014597  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001459c  nop
0x18001459d  mov     rcx, [rbp+lpSubKey]
0x1800145a1  test    rcx, rcx
0x1800145a4  jz      short loc_1800145B8
0x1800145a6  mov     rdx, [rbp+var_10]
0x1800145aa  sub     rdx, rcx
0x1800145ad  sar     rdx, 1
0x1800145b0  add     rdx, rdx
0x1800145b3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800145b8  mov     rax, rbx
0x1800145bb  lea     r11, [rsp+50h+var_s0]
0x1800145c0  mov     rbx, [r11+30h]
0x1800145c4  mov     rsi, [r11+38h]
0x1800145c8  mov     rsp, r11
0x1800145cb  pop     r14
0x1800145cd  pop     rdi
0x1800145ce  pop     rbp
0x1800145cf  retn
```
