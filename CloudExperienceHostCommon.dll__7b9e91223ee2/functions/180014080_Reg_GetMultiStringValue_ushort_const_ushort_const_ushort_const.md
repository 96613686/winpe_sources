# Reg::GetMultiStringValue(ushort const *,ushort const *,ushort const *)

- ea: `0x180014080`
- end: `0x180014341`
- name: `?GetMultiStringValue@Reg@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG00@Z`
- size: `705`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d3ba0`
- `0x1800d7ca0`

## callees

- `0x1800052ac`
- `0x180010c8c`
- `0x180013a74`
- `0x180014080`
- `0x180014348`
- `0x180014360`
- `0x180014378`
- `0x1800143b0`
- `0x18001475c`
- `0x180015a18`
- `0x18001a540`
- `0x18001b004`
- `0x1800798e8`
- `0x1800d8084`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800140f9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800141f1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800140f9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800141f1`

## string_xrefs

- `0x180014123`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`
- `0x18001415b`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`
- `0x180014202`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`
- `0x1800142ef`: `onecore\ds\security\cfl\policy\lib\registryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Reg::GetMultiStringValue(__int64 a1, __int64 a2, __int64 a3, const WCHAR *a4)
{
  __int64 v6; // rdx
  HKEY v7; // rbx
  LSTATUS ValueW; // eax
  __int64 v9; // r8
  unsigned __int64 v10; // r9
  char v11; // cl
  unsigned __int64 v12; // rdi
  char *v13; // rsi
  unsigned __int64 v14; // rcx
  char *v15; // rax
  size_t v16; // rdi
  unsigned int v17; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned __int64 v20; // rbx
  char *v21; // rdi
  unsigned __int64 v22; // rcx
  char *v23; // rax
  size_t v24; // rbx
  wchar_t *v25; // rbx
  unsigned __int64 v26; // rdi
  unsigned __int64 v27; // rsi
  __int64 v28; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-59h]
  DWORD pcbData; // [rsp+40h] [rbp-39h] BYREF
  PVOID pvData; // [rsp+48h] [rbp-31h] BYREF
  void *v33; // [rsp+50h] [rbp-29h]
  __int64 v34; // [rsp+58h] [rbp-21h]
  int v35; // [rsp+60h] [rbp-19h]
  _QWORD v36[2]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v37[32]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v36[1] = a1;
  v35 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(&pvData);
  v7 = Reg::OpenKey(v6, v6, 0x20019u);
  v36[0] = v7;
  pcbData = 0;
  ValueW = RegGetValueW(v7, 0, a4, 0x20u, 0, 0, &pcbData);
  if ( ValueW > 0 )
    v10 = (unsigned __int16)ValueW | 0x80070000;
  else
    v10 = (unsigned int)ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
      (const char *)v10,
      pdwType);
  if ( ValueW )
    goto LABEL_28;
  if ( !pcbData || (v11 = 0, (pcbData & 1) != 0) )
    v11 = 1;
  if ( v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
      (const char *)0x80070018LL,
      pdwType);
  v12 = (unsigned __int64)pcbData >> 1;
  v13 = (char *)v33;
  v14 = ((_BYTE *)v33 - (_BYTE *)pvData) >> 1;
  if ( v12 < v14 )
  {
    v15 = (char *)pvData + 2 * v12;
LABEL_18:
    v33 = v15;
    goto LABEL_19;
  }
  if ( (unsigned __int64)pcbData >> 1 > v14 )
  {
    if ( v12 <= (v34 - (__int64)pvData) >> 1 )
    {
      v16 = 2 * (v12 - v14);
      memset_0(v33, 0, v16);
      v15 = &v13[v16];
      goto LABEL_18;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&pvData, v12, v9, v10);
  }
LABEL_19:
  v17 = RegGetValueW(v7, 0, a4, 0x20u, 0, pvData, &pcbData);
  if ( v17 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
      (const char *)v17,
      pdwType);
  v20 = (unsigned __int64)pcbData >> 1;
  v21 = (char *)v33;
  v22 = ((_BYTE *)v33 - (_BYTE *)pvData) >> 1;
  if ( v20 >= v22 )
  {
    if ( v20 <= v22 )
      goto LABEL_28;
    if ( v20 > (v34 - (__int64)pvData) >> 1 )
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(
        &pvData,
        (unsigned __int64)pcbData >> 1,
        v18,
        v19);
      goto LABEL_28;
    }
    v24 = 2 * (v20 - v22);
    memset_0(v33, 0, v24);
    v23 = &v21[v24];
  }
  else
  {
    v23 = (char *)pvData + 2 * v20;
  }
  v33 = v23;
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v36);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(a1);
  v35 = 1;
  v25 = (wchar_t *)pvData;
  v26 = ((_BYTE *)v33 - (_BYTE *)pvData) >> 1;
  if ( v26 )
  {
    v27 = 0;
    while ( v25[v27] )
    {
      v28 = std::wstring::wstring(v37, &v25[v27]);
      std::vector<std::wstring>::push_back(a1, v28);
      std::wstring::_Tidy_deallocate(v37);
      v27 += wcsnlen_s(&v25[v27], v26 - v27) + 1;
      if ( v26 <= v27 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x61,
          (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\registryhelper.cpp",
          (const char *)0x80070057LL,
          pdwType);
    }
    v25 = (wchar_t *)pvData;
  }
  if ( v25 )
    std::_Deallocate<16>(v25, (struct std::nothrow_t *)(2 * ((v34 - (__int64)v25) >> 1)));
  return a1;
}

```

## disassembly

```asm
0x180014080  push    rbp
0x180014082  push    rbx
0x180014083  push    rsi
0x180014084  push    rdi
0x180014085  push    r12
0x180014087  push    r14
0x180014089  push    r15
0x18001408b  lea     rbp, [rsp-27h]
0x180014090  sub     rsp, 0A0h
0x180014097  mov     rax, cs:__security_cookie
0x18001409e  xor     rax, rsp
0x1800140a1  mov     [rbp+57h+var_38], rax
0x1800140a5  mov     r14, r9
0x1800140a8  mov     r15, rcx
0x1800140ab  mov     [rbp+57h+var_60], rcx
0x1800140af  xor     r12d, r12d
0x1800140b2  mov     [rbp+57h+var_70], r12d
0x1800140b6  lea     rcx, [rbp+57h+var_88]
0x1800140ba  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x1800140bf  nop
0x1800140c0  mov     r8d, 20019h
0x1800140c6  mov     rcx, rdx
0x1800140c9  call    Reg__OpenKey
0x1800140ce  mov     rbx, rax
0x1800140d1  mov     [rbp+57h+var_68], rax
0x1800140d5  mov     [rbp+57h+var_90], r12d
0x1800140d9  lea     rax, [rbp+57h+var_90]
0x1800140dd  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1800140e2  mov     [rsp+0D0h+pvData], r12; pvData
0x1800140e7  mov     [rsp+0D0h+pdwType], r12; int
0x1800140ec  lea     r9d, [r12+20h]; dwFlags
0x1800140f1  mov     r8, r14; lpValue
0x1800140f4  xor     edx, edx; lpSubKey
0x1800140f6  mov     rcx, rbx; hkey
0x1800140f9  call    cs:__imp_RegGetValueW
0x1800140ff  test    eax, 0FFFFFFFDh
0x180014104  setnz   dl
0x180014107  test    eax, eax
0x180014109  jg      short loc_180014110
0x18001410b  mov     r9d, eax
0x18001410e  jmp     short loc_18001411B
0x180014110  movzx   r9d, ax
0x180014114  or      r9d, 80070000h; char *
0x18001411b  mov     rcx, [rbp+5Fh]; this
0x18001411f  test    dl, dl
0x180014121  jz      short loc_180014135
0x180014123  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x18001412a  mov     edx, 48h ; 'H'; void *
0x18001412f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014135  test    eax, eax
0x180014137  jnz     loc_180014270
0x18001413d  mov     eax, [rbp+57h+var_90]
0x180014140  test    eax, eax
0x180014142  jz      short loc_18001414B
0x180014144  test    al, 1
0x180014146  mov     cl, r12b
0x180014149  jz      short loc_18001414D
0x18001414b  mov     cl, 1
0x18001414d  mov     r10, [rbp+5Fh]
0x180014151  test    cl, cl
0x180014153  jz      short loc_180014170
0x180014155  mov     r9d, 80070018h; char *
0x18001415b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x180014162  mov     edx, 4Bh ; 'K'; void *
0x180014167  mov     rcx, r10; this
0x18001416a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014170  mov     rdi, rax
0x180014173  shr     rdi, 1
0x180014176  mov     rdx, [rbp+57h+var_88]
0x18001417a  mov     rsi, [rbp+57h+var_80]
0x18001417e  mov     rcx, rsi
0x180014181  sub     rcx, rdx
0x180014184  sar     rcx, 1
0x180014187  cmp     rdi, rcx
0x18001418a  jnb     short loc_180014192
0x18001418c  lea     rax, [rdx+rdi*2]
0x180014190  jmp     short loc_1800141C8
0x180014192  jbe     short loc_1800141CC
0x180014194  mov     rax, [rbp+57h+var_78]
0x180014198  sub     rax, rdx
0x18001419b  sar     rax, 1
0x18001419e  cmp     rdi, rax
0x1800141a1  jbe     short loc_1800141B1
0x1800141a3  mov     rdx, rdi
0x1800141a6  lea     rcx, [rbp+57h+var_88]
0x1800141aa  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800141af  jmp     short loc_1800141CC
0x1800141b1  sub     rdi, rcx
0x1800141b4  add     rdi, rdi
0x1800141b7  mov     r8, rdi; Size
0x1800141ba  xor     edx, edx; Val
0x1800141bc  mov     rcx, rsi; void *
0x1800141bf  call    memset_0
0x1800141c4  lea     rax, [rdi+rsi]
0x1800141c8  mov     [rbp+57h+var_80], rax
0x1800141cc  mov     rax, [rbp+57h+var_88]
0x1800141d0  lea     rcx, [rbp+57h+var_90]
0x1800141d4  mov     [rsp+0D0h+pcbData], rcx; pcbData
0x1800141d9  mov     [rsp+0D0h+pvData], rax; pvData
0x1800141de  mov     [rsp+0D0h+pdwType], r12; int
0x1800141e3  mov     r9d, 20h ; ' '; dwFlags
0x1800141e9  mov     r8, r14; lpValue
0x1800141ec  xor     edx, edx; lpSubKey
0x1800141ee  mov     rcx, rbx; hkey
0x1800141f1  call    cs:__imp_RegGetValueW
0x1800141f7  mov     rcx, [rbp+5Fh]; this
0x1800141fb  test    eax, eax
0x1800141fd  jz      short loc_180014214
0x1800141ff  mov     r9d, eax; char *
0x180014202  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x180014209  mov     edx, 4Eh ; 'N'; void *
0x18001420e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180014214  mov     ebx, [rbp+57h+var_90]
0x180014217  shr     rbx, 1
0x18001421a  mov     rdx, [rbp+57h+var_88]
0x18001421e  mov     rdi, [rbp+57h+var_80]
0x180014222  mov     rcx, rdi
0x180014225  sub     rcx, rdx
0x180014228  sar     rcx, 1
0x18001422b  cmp     rbx, rcx
0x18001422e  jnb     short loc_180014236
0x180014230  lea     rax, [rdx+rbx*2]
0x180014234  jmp     short loc_18001426C
0x180014236  jbe     short loc_180014270
0x180014238  mov     rax, [rbp+57h+var_78]
0x18001423c  sub     rax, rdx
0x18001423f  sar     rax, 1
0x180014242  cmp     rbx, rax
0x180014245  jbe     short loc_180014255
0x180014247  mov     rdx, rbx
0x18001424a  lea     rcx, [rbp+57h+var_88]
0x18001424e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180014253  jmp     short loc_180014270
0x180014255  sub     rbx, rcx
0x180014258  add     rbx, rbx
0x18001425b  mov     r8, rbx; Size
0x18001425e  xor     edx, edx; Val
0x180014260  mov     rcx, rdi; void *
0x180014263  call    memset_0
0x180014268  lea     rax, [rbx+rdi]
0x18001426c  mov     [rbp+57h+var_80], rax
0x180014270  lea     rcx, [rbp+57h+var_68]
0x180014274  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014279  mov     rcx, r15
0x18001427c  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>(std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x180014281  mov     [rbp+57h+var_70], 1
0x180014288  mov     rbx, [rbp+57h+var_88]
0x18001428c  mov     rdi, [rbp+57h+var_80]
0x180014290  sub     rdi, rbx
0x180014293  sar     rdi, 1
0x180014296  jz      short loc_180014305
0x180014298  mov     rsi, r12
0x18001429b  test    rdi, rdi
0x18001429e  jz      short loc_180014305
0x1800142a0  lea     r14, [rbx+rsi*2]
0x1800142a4  cmp     [r14], r12w
0x1800142a8  jz      short loc_180014301
0x1800142aa  mov     rdx, r14
0x1800142ad  lea     rcx, [rbp+57h+var_58]
0x1800142b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800142b6  nop
0x1800142b7  mov     rdx, rax
0x1800142ba  mov     rcx, r15
0x1800142bd  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800142c2  nop
0x1800142c3  lea     rcx, [rbp+57h+var_58]
0x1800142c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800142cc  mov     rdx, rdi
0x1800142cf  sub     rdx, rsi; MaxCount
0x1800142d2  mov     rcx, r14; Source
0x1800142d5  call    wcsnlen_s
0x1800142da  inc     rsi
0x1800142dd  add     rsi, rax
0x1800142e0  mov     rcx, [rbp+5Fh]; this
0x1800142e4  cmp     rdi, rsi
0x1800142e7  ja      short loc_1800142A0
0x1800142e9  mov     r9d, 80070057h; char *
0x1800142ef  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800142f6  mov     edx, 61h ; 'a'; void *
0x1800142fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014301  mov     rbx, [rbp+57h+var_88]
0x180014305  test    rbx, rbx
0x180014308  jz      short loc_18001431F
0x18001430a  mov     rdx, [rbp+57h+var_78]
0x18001430e  sub     rdx, rbx
0x180014311  sar     rdx, 1
0x180014314  add     rdx, rdx
0x180014317  mov     rcx, rbx
0x18001431a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001431f  mov     rax, r15
0x180014322  mov     rcx, [rbp+57h+var_38]
0x180014326  xor     rcx, rsp; StackCookie
0x180014329  call    __security_check_cookie
0x18001432e  add     rsp, 0A0h
0x180014335  pop     r15
0x180014337  pop     r14
0x180014339  pop     r12
0x18001433b  pop     rdi
0x18001433c  pop     rsi
0x18001433d  pop     rbx
0x18001433e  pop     rbp
0x18001433f  retn
```
