# Reg::SetMultiStringValue(ushort const *,ushort const *,ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x180012b84`
- end: `0x180012d26`
- name: `?SetMultiStringValue@Reg@@YAXPEBG00AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d7ca0`

## callees

- `0x180010c8c`
- `0x180012b84`
- `0x180012d2c`
- `0x1800135ec`
- `0x180014360`
- `0x1800143b0`
- `0x18001475c`
- `0x180015a18`
- `0x18001b004`
- `0x1800798e8`
- `0x1800d8084`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012ccb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012ccb`

## string_xrefs

- `0x180012c73`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`
- `0x180012cdc`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Reg::SetMultiStringValue(__int64 a1, __int64 a2, HKEY a3, __int64 *a4)
{
  __int64 v5; // r8
  __int64 *v6; // r9
  unsigned int v7; // edi
  __int64 i; // rcx
  char *v9; // r14
  unsigned __int64 v10; // rcx
  BYTE *v11; // rax
  size_t v12; // rbx
  unsigned __int16 *v13; // rbx
  unsigned int v14; // r14d
  __int64 v15; // r11
  __int64 v16; // rsi
  const unsigned __int16 *v17; // rax
  int v18; // eax
  __int64 v19; // r11
  __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  int lpData; // [rsp+20h] [rbp-30h]
  unsigned int lpDataa; // [rsp+20h] [rbp-30h]
  BYTE *v25; // [rsp+30h] [rbp-20h] BYREF
  void *v26; // [rsp+38h] [rbp-18h]
  __int64 v27; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY v29; // [rsp+80h] [rbp+30h] BYREF

  v29 = a3;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(&v25);
  v7 = 1;
  for ( i = *v6; i != v6[1]; i += 32 )
    v7 += *(_DWORD *)(i + 16) + 1;
  v9 = (char *)v26;
  v10 = ((_BYTE *)v26 - v25) >> 1;
  if ( v7 >= v10 )
  {
    if ( v7 <= v10 )
      goto LABEL_11;
    if ( v7 > (unsigned __int64)((v27 - (__int64)v25) >> 1) )
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v25, v7, v5, v6);
      goto LABEL_11;
    }
    v12 = 2 * (v7 - v10);
    memset_0(v26, 0, v12);
    v11 = (BYTE *)&v9[v12];
  }
  else
  {
    v11 = &v25[2 * v7];
  }
  v26 = v11;
LABEL_11:
  v13 = (unsigned __int16 *)v25;
  v14 = v7;
  v15 = *a4;
  v16 = a4[1];
  if ( v15 != v16 )
  {
    while ( 1 )
    {
      v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
      v18 = StringCchCopyW(v13, v14, v17);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
          (const char *)(unsigned int)v18,
          lpData);
      v20 = v19;
      v15 = v19 + 32;
      if ( v15 == v16 )
        break;
      v13 += *(_QWORD *)(v20 + 16) + 1;
      v14 += -1 - *(_DWORD *)(v20 + 16);
    }
  }
  v21 = v7 - 1;
  *(_WORD *)&v25[2 * v21] = 0;
  v29 = Reg::OpenKey((__int64)L"WebSignInNav", v21, 0x20006u);
  v22 = RegSetValueExW(v29, L"O365Allowlist", 0, 7u, v25, 2 * v7);
  if ( v22 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
      (const char *)v22,
      lpDataa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
  if ( v25 )
    std::_Deallocate<16>(v25, (struct std::nothrow_t *)(2 * ((v27 - (__int64)v25) >> 1)));
}

```

## disassembly

```asm
0x180012b84  mov     [rsp-18h+arg_0], rbx
0x180012b89  mov     [rsp-18h+arg_8], rsi
0x180012b8e  mov     [rsp-18h+arg_10], r8
0x180012b93  push    rbp
0x180012b94  push    rdi
0x180012b95  push    r14
0x180012b97  mov     rbp, rsp
0x180012b9a  sub     rsp, 50h
0x180012b9e  mov     rsi, r9
0x180012ba1  lea     rcx, [rbp+var_20]
0x180012ba5  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x180012baa  nop
0x180012bab  mov     edi, 1
0x180012bb0  mov     rcx, [r9]
0x180012bb3  jmp     short loc_180012BBE
0x180012bb5  inc     edi
0x180012bb7  add     edi, [rcx+10h]
0x180012bba  add     rcx, 20h ; ' '
0x180012bbe  cmp     rcx, [r9+8]
0x180012bc2  jnz     short loc_180012BB5
0x180012bc4  mov     rdx, [rbp+var_20]
0x180012bc8  mov     r14, [rbp+var_18]
0x180012bcc  mov     rcx, r14
0x180012bcf  sub     rcx, rdx
0x180012bd2  sar     rcx, 1
0x180012bd5  mov     ebx, edi
0x180012bd7  cmp     rbx, rcx
0x180012bda  jnb     short loc_180012BE2
0x180012bdc  lea     rax, [rdx+rbx*2]
0x180012be0  jmp     short loc_180012C18
0x180012be2  jbe     short loc_180012C1C
0x180012be4  mov     rax, [rbp+var_10]
0x180012be8  sub     rax, rdx
0x180012beb  sar     rax, 1
0x180012bee  cmp     rbx, rax
0x180012bf1  jbe     short loc_180012C01
0x180012bf3  mov     rdx, rbx
0x180012bf6  lea     rcx, [rbp+var_20]
0x180012bfa  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180012bff  jmp     short loc_180012C1C
0x180012c01  sub     rbx, rcx
0x180012c04  add     rbx, rbx
0x180012c07  mov     r8, rbx; Size
0x180012c0a  xor     edx, edx; Val
0x180012c0c  mov     rcx, r14; void *
0x180012c0f  call    memset_0
0x180012c14  lea     rax, [rbx+r14]
0x180012c18  mov     [rbp+var_18], rax
0x180012c1c  mov     rbx, [rbp+var_20]
0x180012c20  mov     r14d, edi
0x180012c23  mov     r11, [rsi]
0x180012c26  mov     rsi, [rsi+8]
0x180012c2a  cmp     r11, rsi
0x180012c2d  jz      short loc_180012C85
0x180012c2f  mov     rcx, r11
0x180012c32  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012c37  mov     edx, r14d; unsigned __int64
0x180012c3a  mov     r8, rax; unsigned __int16 *
0x180012c3d  mov     rcx, rbx; unsigned __int16 *
0x180012c40  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012c45  mov     rcx, [rbp+18h]; this
0x180012c49  test    eax, eax
0x180012c4b  js      short loc_180012C70
0x180012c4d  mov     rcx, r11
0x180012c50  add     r11, 20h ; ' '
0x180012c54  cmp     r11, rsi
0x180012c57  jz      short loc_180012C85
0x180012c59  mov     rax, [rcx+10h]
0x180012c5d  lea     rbx, [rbx+rax*2]
0x180012c61  add     rbx, 2
0x180012c65  or      eax, 0FFFFFFFFh
0x180012c68  sub     eax, [rcx+10h]
0x180012c6b  add     r14d, eax
0x180012c6e  jmp     short loc_180012C2F
0x180012c70  mov     r9d, eax; char *
0x180012c73  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x180012c7a  mov     edx, 78h ; 'x'; void *
0x180012c7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012c85  lea     edx, [rdi-1]
0x180012c88  xor     ecx, ecx
0x180012c8a  mov     rax, [rbp+var_20]
0x180012c8e  mov     [rax+rdx*2], cx
0x180012c92  mov     r8d, 20006h
0x180012c98  lea     rcx, aWebsigninnav; "WebSignInNav"
0x180012c9f  call    Reg__OpenKey
0x180012ca4  mov     [rbp+arg_10], rax
0x180012ca8  mov     rdx, [rbp+var_20]
0x180012cac  lea     ecx, [rdi+rdi]
0x180012caf  mov     [rsp+50h+cbData], ecx; cbData
0x180012cb3  mov     [rsp+50h+lpData], rdx; unsigned int
0x180012cb8  mov     r9d, 7; dwType
0x180012cbe  xor     r8d, r8d; Reserved
0x180012cc1  lea     rdx, aO365allowlist; "O365Allowlist"
0x180012cc8  mov     rcx, rax; hKey
0x180012ccb  call    cs:__imp_RegSetValueExW
0x180012cd1  mov     rcx, [rbp+18h]; this
0x180012cd5  test    eax, eax
0x180012cd7  jz      short loc_180012CEE
0x180012cd9  mov     r9d, eax; char *
0x180012cdc  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x180012ce3  mov     edx, 84h; void *
0x180012ce8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180012cee  lea     rcx, [rbp+arg_10]
0x180012cf2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012cf7  nop
0x180012cf8  mov     rcx, [rbp+var_20]
0x180012cfc  test    rcx, rcx
0x180012cff  jz      short loc_180012D13
0x180012d01  mov     rdx, [rbp+var_10]
0x180012d05  sub     rdx, rcx
0x180012d08  sar     rdx, 1
0x180012d0b  add     rdx, rdx
0x180012d0e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012d13  mov     rbx, [rsp+50h+arg_0]
0x180012d18  mov     rsi, [rsp+50h+arg_8]
0x180012d1d  add     rsp, 50h
0x180012d21  pop     r14
0x180012d23  pop     rdi
0x180012d24  pop     rbp
0x180012d25  retn
```
