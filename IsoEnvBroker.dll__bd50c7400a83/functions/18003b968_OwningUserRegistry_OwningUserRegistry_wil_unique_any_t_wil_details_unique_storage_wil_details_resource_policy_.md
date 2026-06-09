# OwningUserRegistry::OwningUserRegistry(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18003b968`
- end: `0x18003bd74`
- name: `??0OwningUserRegistry@@QEAA@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `1036`
- prototype: `__int64 __fastcall(__int64, HKEY *, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003ca08`
- `0x180060218`

## callees

- `0x180002520`
- `0x180002ee8`
- `0x1800075e4`
- `0x18000e4ec`
- `0x18001045c`
- `0x180011e18`
- `0x18001e820`
- `0x18001eb90`
- `0x18001f998`
- `0x18001fa68`
- `0x180021564`
- `0x18002193c`
- `0x18002ab4c`
- `0x180030214`
- `0x18003b4ec`
- `0x18003b968`
- `0x18003de88`
- `0x18003df4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bc8a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bc8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd1a`

## string_xrefs

- `0x18003bd4d`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18003bd62`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x18003bca5`: `Failed to delete reg key %s: %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OwningUserRegistry::OwningUserRegistry(__int64 a1, HKEY *a2, __int64 a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  HKEY v7; // rdx
  unsigned int child_key_count; // eax
  HKEY v9; // rdx
  unsigned int v10; // eax
  wil::reg *v11; // rcx
  int v12; // eax
  const char *v13; // r9
  int v14; // edi
  __int64 v15; // r15
  LPCWSTR *v16; // r8
  const WCHAR *v17; // r8
  const WCHAR *v18; // r8
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  const WCHAR *v21; // rdx
  unsigned int v22; // eax
  LPCWSTR *v23; // r8
  int v25; // [rsp+20h] [rbp-E0h]
  wil::reg *v26; // [rsp+30h] [rbp-D0h] BYREF
  __int128 Src; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  wil::reg *v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+98h] [rbp-68h]
  int v38; // [rsp+9Ch] [rbp-64h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  HKEY *v41; // [rsp+B0h] [rbp-50h]
  __int128 *p_Src; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v43[16]; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  int v47; // [rsp+100h] [rbp+0h]
  _BYTE v48[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  _BYTE v51[56]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v52[56]; // [rsp+188h] [rbp+88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v40 = a1;
  v41 = a2;
  *(_QWORD *)a1 = *a2;
  *a2 = 0;
  std::wstring::wstring(a1 + 8, a3);
  v26 = (wil::reg *)(a1 + 40);
  *(_DWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v5 = operator new(0x50u);
  *v5 = v5;
  v5[1] = v5;
  *(_QWORD *)(a1 + 48) = v5;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 7;
  *(_QWORD *)(a1 + 96) = 8;
  *(_DWORD *)(a1 + 40) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::_Assign_grow(
    a1 + 64,
    16,
    *(_QWORD *)(a1 + 48));
  v26 = (wil::reg *)(a1 + 104);
  *(_DWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  v6 = operator new(0x50u);
  *v6 = v6;
  v6[1] = v6;
  *(_QWORD *)(a1 + 112) = v6;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 7;
  *(_QWORD *)(a1 + 160) = 8;
  *(_DWORD *)(a1 + 104) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::_Assign_grow(
    a1 + 128,
    16,
    *(_QWORD *)(a1 + 112));
  child_key_count = wil::reg::get_child_key_count(*(wil::reg **)a1, v7);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::reserve(
    a1 + 40,
    child_key_count);
  v10 = wil::reg::get_child_key_count(*(wil::reg **)a1, v9);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::reserve(
    a1 + 104,
    v10);
  v26 = (wil::reg *)&v33;
  v38 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 7;
  LOWORD(v33) = 0;
  v36 = 0;
  v37 = -1;
  v39 = 0;
  p_Src = &Src;
  v11 = *(wil::reg **)a1;
  Src = 0;
  v28 = 0;
  v29 = 7;
  LOWORD(Src) = 0;
  v30 = v11;
  v31 = -1;
  v32 = 0;
  if ( v11 )
  {
    v31 = 0;
    v12 = wil::reg::key_iterator_data<std::wstring>::enumerate_current_index(&Src);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6EE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        (const char *)(unsigned int)v12,
        v25);
  }
  wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(v51, &Src, &v33);
  wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(
    lpSubKey,
    v51);
  wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(
    v48,
    v52);
  v14 = v50;
  v15 = v49;
  while ( v47 != -1 && v14 != -1 && v46 != v15 || v47 != v14 )
  {
    if ( v47 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6FF,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        v13);
    v16 = lpSubKey;
    if ( v45 > 7 )
      v16 = (LPCWSTR *)lpSubKey[0];
    Log(4u, L"Populating for existing key %s", v16);
    v17 = (const WCHAR *)lpSubKey;
    if ( v45 > 7 )
      v17 = lpSubKey[0];
    v26 = *(wil::reg **)a1;
    wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(
      (HKEY *)&v26,
      (__int64)&Src,
      v17,
      (const WCHAR *)&stru_18009E488,
      0x10000006u);
    v18 = (const WCHAR *)lpSubKey;
    if ( (_BYTE)v30 )
    {
      v19 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                        (float *)(a1 + 40),
                        (__int64)&p_Src,
                        lpSubKey);
      std::wstring::operator=(*v19 + 48LL, &Src);
    }
    else
    {
      if ( v45 > 7 )
        v18 = lpSubKey[0];
      v26 = *(wil::reg **)a1;
      wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(
        (HKEY *)&v26,
        (__int64)&v33,
        v18,
        (const WCHAR *)&stru_18009E498,
        0x10000006u);
      if ( (_BYTE)v36 )
      {
        v20 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                          (float *)(a1 + 104),
                          (__int64)v43,
                          lpSubKey);
        std::wstring::operator=(*v20 + 48LL, &v33);
      }
      else
      {
        Log(4u, L"  (no Marker or OwningApp value; cleaning it up)");
        v21 = (const WCHAR *)lpSubKey;
        if ( v45 > 7 )
          v21 = lpSubKey[0];
        v22 = RegDeleteTreeW(*(HKEY *)a1, v21);
        if ( v22 )
        {
          v23 = lpSubKey;
          if ( v45 > 7 )
            v23 = (LPCWSTR *)lpSubKey[0];
          Log(2u, L"Failed to delete reg key %s: %#x", v23, v22);
        }
      }
      if ( (_BYTE)v36 )
        std::wstring::~wstring(&v33);
    }
    if ( (_BYTE)v30 )
      std::wstring::~wstring(&Src);
    wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::operator++(lpSubKey);
  }
  std::wstring::~wstring(v48);
  std::wstring::~wstring(lpSubKey);
  std::wstring::~wstring(v52);
  std::wstring::~wstring(v51);
  if ( *a2 )
    RegCloseKey(*a2);
  return a1;
}

```

## disassembly

```asm
0x18003b968  mov     [rsp-8+arg_18], rbx
0x18003b96d  push    rbp
0x18003b96e  push    rsi
0x18003b96f  push    rdi
0x18003b970  push    r12
0x18003b972  push    r13
0x18003b974  push    r14
0x18003b976  push    r15
0x18003b978  lea     rbp, [rsp-0D0h]
0x18003b980  sub     rsp, 1D0h
0x18003b987  mov     rax, cs:__security_cookie
0x18003b98e  xor     rax, rsp
0x18003b991  mov     [rbp+100h+var_40], rax
0x18003b998  mov     r12, rdx
0x18003b99b  mov     rbx, rcx
0x18003b99e  mov     [rbp+100h+var_158], rcx
0x18003b9a2  mov     [rbp+100h+var_150], rdx
0x18003b9a6  xor     edi, edi
0x18003b9a8  mov     rax, [rdx]
0x18003b9ab  mov     [rcx], rax
0x18003b9ae  mov     [rdx], rdi
0x18003b9b1  add     rcx, 8
0x18003b9b5  mov     rdx, r8
0x18003b9b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003b9bd  nop
0x18003b9be  lea     rsi, [rbx+28h]
0x18003b9c2  mov     [rsp+200h+var_1D0], rsi
0x18003b9c7  mov     [rsi], edi
0x18003b9c9  mov     [rsi+8], rdi
0x18003b9cd  mov     [rsi+10h], rdi
0x18003b9d1  lea     ecx, [rdi+50h]; Size
0x18003b9d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b9d9  mov     [rax], rax
0x18003b9dc  mov     [rax+8], rax
0x18003b9e0  mov     [rsi+8], rax
0x18003b9e4  lea     rcx, [rsi+18h]
0x18003b9e8  mov     [rcx], rdi
0x18003b9eb  mov     [rcx+8], rdi
0x18003b9ef  mov     [rcx+10h], rdi
0x18003b9f3  mov     qword ptr [rsi+30h], 7
0x18003b9fb  lea     r13d, [rdi+8]
0x18003b9ff  mov     [rsi+38h], r13
0x18003ba03  mov     r15d, 3F800000h
0x18003ba09  mov     [rsi], r15d
0x18003ba0c  mov     r8, [rsi+8]
0x18003ba10  lea     edi, [r13+8]
0x18003ba14  mov     edx, edi
0x18003ba16  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>)
0x18003ba1b  nop
0x18003ba1c  lea     r14, [rbx+68h]
0x18003ba20  mov     [rsp+200h+var_1D0], r14
0x18003ba25  xor     eax, eax
0x18003ba27  mov     [r14], eax
0x18003ba2a  mov     [r14+8], rax
0x18003ba2e  mov     [r14+10h], rax
0x18003ba32  lea     ecx, [rdi+40h]; Size
0x18003ba35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ba3a  mov     [rax], rax
0x18003ba3d  mov     [rax+8], rax
0x18003ba41  mov     [r14+8], rax
0x18003ba45  lea     rcx, [r14+18h]
0x18003ba49  xor     eax, eax
0x18003ba4b  mov     [rcx], rax
0x18003ba4e  mov     [rcx+8], rax
0x18003ba52  mov     [rcx+10h], rax
0x18003ba56  mov     qword ptr [r14+30h], 7
0x18003ba5e  mov     [r14+38h], r13
0x18003ba62  mov     [r14], r15d
0x18003ba65  mov     r8, [r14+8]
0x18003ba69  mov     edx, edi
0x18003ba6b  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>>>)
0x18003ba70  nop
0x18003ba71  mov     rcx, [rbx]; this
0x18003ba74  call    ?get_child_key_count@reg@wil@@YAIPEAUHKEY__@@@Z; wil::reg::get_child_key_count(HKEY__ *)
0x18003ba79  mov     edx, eax
0x18003ba7b  mov     rcx, rsi
0x18003ba7e  call    ?reserve@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::reserve(unsigned __int64)
0x18003ba83  mov     rcx, [rbx]; this
0x18003ba86  call    ?get_child_key_count@reg@wil@@YAIPEAUHKEY__@@@Z; wil::reg::get_child_key_count(HKEY__ *)
0x18003ba8b  mov     edx, eax
0x18003ba8d  mov     rcx, r14
0x18003ba90  call    ?reserve@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::reserve(unsigned __int64)
0x18003ba95  lea     rax, [rsp+200h+var_190]
0x18003ba9a  mov     [rsp+200h+var_1D0], rax
0x18003ba9f  xor     r13d, r13d
0x18003baa2  mov     [rbp+100h+var_164], r13d
0x18003baa6  xorps   xmm0, xmm0
0x18003baa9  movups  [rsp+200h+var_190], xmm0
0x18003baae  mov     [rbp+100h+var_180], r13
0x18003bab2  lea     edx, [rdi-9]
0x18003bab5  mov     [rbp+100h+var_178], rdx
0x18003bab9  mov     word ptr [rsp+200h+var_190], r13w
0x18003babf  mov     [rbp+100h+var_170], r13
0x18003bac3  or      r8d, 0FFFFFFFFh
0x18003bac7  mov     [rbp+100h+var_168], r8d
0x18003bacb  mov     [rbp+100h+var_160], r13
0x18003bacf  lea     rax, [rsp+200h+Src]
0x18003bad4  mov     [rbp+100h+var_148], rax
0x18003bad8  mov     rcx, [rbx]
0x18003badb  movups  [rsp+200h+Src], xmm0
0x18003bae0  mov     [rsp+200h+var_1B8], r13
0x18003bae5  mov     [rsp+200h+var_1B0], rdx
0x18003baea  mov     word ptr [rsp+200h+Src], r13w
0x18003baf0  mov     [rsp+200h+var_1A8], rcx
0x18003baf5  mov     [rsp+200h+var_1A0], r8d
0x18003bafa  mov     [rsp+200h+var_198], r13
0x18003baff  test    rcx, rcx
0x18003bb02  jz      short loc_18003BB22
0x18003bb04  mov     [rsp+200h+var_1A0], r13d
0x18003bb09  lea     rcx, [rsp+200h+Src]; Src
0x18003bb0e  call    ?enumerate_current_index@?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@AEAAJXZ; wil::reg::key_iterator_data<std::wstring>::enumerate_current_index(void)
0x18003bb13  mov     rcx, [rbp+108h]; this
0x18003bb1a  test    eax, eax
0x18003bb1c  js      loc_18003BD5F
0x18003bb22  lea     r8, [rsp+200h+var_190]
0x18003bb27  lea     rdx, [rsp+200h+Src]
0x18003bb2c  lea     rcx, [rbp+100h+var_B0]
0x18003bb30  call    ??$make_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@@wil@@YA?AV?$pointer_range@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@@details@0@V?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@0@0@Z; wil::make_range<wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>,wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>)
0x18003bb35  nop
0x18003bb36  lea     rdx, [rbp+100h+var_B0]
0x18003bb3a  lea     rcx, [rbp+100h+lpSubKey]
0x18003bb3e  call    ??0?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>> const &)
0x18003bb43  nop
0x18003bb44  lea     rdx, [rbp+100h+var_78]
0x18003bb4b  lea     rcx, [rbp+100h+var_F0]
0x18003bb4f  call    ??0?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAA@AEBV012@@Z; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::iterator_t<wil::reg::key_iterator_data<std::wstring>>(wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>> const &)
0x18003bb54  nop
0x18003bb55  mov     rdi, [rbp+100h+var_C8]
0x18003bb59  mov     r15, [rbp+100h+var_D0]
0x18003bb5d  mov     eax, [rbp+100h+var_100]
0x18003bb60  or      ecx, 0FFFFFFFFh
0x18003bb63  cmp     eax, ecx
0x18003bb65  jz      short loc_18003BB71
0x18003bb67  cmp     edi, ecx
0x18003bb69  jz      short loc_18003BB71
0x18003bb6b  cmp     [rbp+100h+var_108], r15
0x18003bb6f  jnz     short loc_18003BB79
0x18003bb71  cmp     eax, edi
0x18003bb73  jz      loc_18003BCE7
0x18003bb79  cmp     eax, ecx
0x18003bb7b  setz    al
0x18003bb7e  mov     rcx, [rbp+108h]; this
0x18003bb85  test    al, al
0x18003bb87  jnz     loc_18003BD4D
0x18003bb8d  lea     r8, [rbp+100h+lpSubKey]
0x18003bb91  cmp     [rbp+100h+var_110], 7
0x18003bb96  cmova   r8, [rbp+100h+lpSubKey]
0x18003bb9b  lea     rdx, aPopulatingForE; "Populating for existing key %s"
0x18003bba2  mov     ecx, 4; unsigned __int8
0x18003bba7  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003bbac  lea     r8, [rbp+100h+lpSubKey]
0x18003bbb0  cmp     [rbp+100h+var_110], 7
0x18003bbb5  cmova   r8, [rbp+100h+lpSubKey]
0x18003bbba  mov     rax, [rbx]
0x18003bbbd  mov     [rsp+200h+var_1D0], rax
0x18003bbc2  mov     [rsp+200h+var_1E0], 10000006h
0x18003bbca  lea     r9, stru_18009E488
0x18003bbd1  lea     rdx, [rsp+200h+Src]
0x18003bbd6  lea     rcx, [rsp+200h+var_1D0]
0x18003bbdb  call    ??$try_get_value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEB_W0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(wchar_t const *,wchar_t const *,ulong)
0x18003bbe0  nop
0x18003bbe1  lea     r8, [rbp+100h+lpSubKey]
0x18003bbe5  cmp     byte ptr [rsp+200h+var_1A8], r13b
0x18003bbea  jz      short loc_18003BC0E
0x18003bbec  lea     rdx, [rbp+100h+var_148]
0x18003bbf0  mov     rcx, rsi
0x18003bbf3  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003bbf8  mov     rcx, [rax]
0x18003bbfb  add     rcx, 30h ; '0'
0x18003bbff  lea     rdx, [rsp+200h+Src]
0x18003bc04  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003bc09  jmp     loc_18003BCC8
0x18003bc0e  cmp     [rbp+100h+var_110], 7
0x18003bc13  cmova   r8, [rbp+100h+lpSubKey]
0x18003bc18  mov     rax, [rbx]
0x18003bc1b  mov     [rsp+200h+var_1D0], rax
0x18003bc20  mov     [rsp+200h+var_1E0], 10000006h
0x18003bc28  lea     r9, stru_18009E498
0x18003bc2f  lea     rdx, [rsp+200h+var_190]
0x18003bc34  lea     rcx, [rsp+200h+var_1D0]
0x18003bc39  call    ??$try_get_value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEB_W0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(wchar_t const *,wchar_t const *,ulong)
0x18003bc3e  nop
0x18003bc3f  cmp     byte ptr [rbp+100h+var_170], r13b
0x18003bc43  jz      short loc_18003BC68
0x18003bc45  lea     r8, [rbp+100h+lpSubKey]
0x18003bc49  lea     rdx, [rbp+100h+var_138]
0x18003bc4d  mov     rcx, r14
0x18003bc50  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003bc55  mov     rcx, [rax]
0x18003bc58  add     rcx, 30h ; '0'
0x18003bc5c  lea     rdx, [rsp+200h+var_190]
0x18003bc61  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003bc66  jmp     short loc_18003BCB7
0x18003bc68  lea     rdx, aNoMarkerOrOwni; "  (no Marker or OwningApp value; cleani"...
0x18003bc6f  mov     ecx, 4; unsigned __int8
0x18003bc74  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003bc79  lea     rdx, [rbp+100h+lpSubKey]
0x18003bc7d  cmp     [rbp+100h+var_110], 7
0x18003bc82  cmova   rdx, [rbp+100h+lpSubKey]; lpSubKey
0x18003bc87  mov     rcx, [rbx]; hKey
0x18003bc8a  call    cs:__imp_RegDeleteTreeW
0x18003bc90  test    eax, eax
0x18003bc92  jz      short loc_18003BCB7
0x18003bc94  lea     r8, [rbp+100h+lpSubKey]
0x18003bc98  cmp     [rbp+100h+var_110], 7
0x18003bc9d  cmova   r8, [rbp+100h+lpSubKey]
0x18003bca2  mov     r9d, eax
0x18003bca5  lea     rdx, aFailedToDelete_0; "Failed to delete reg key %s: %#x"
0x18003bcac  mov     ecx, 2; unsigned __int8
0x18003bcb1  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003bcb6  nop
0x18003bcb7  cmp     byte ptr [rbp+100h+var_170], r13b
0x18003bcbb  jz      short loc_18003BCC8
0x18003bcbd  lea     rcx, [rsp+200h+var_190]
0x18003bcc2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bcc7  nop
0x18003bcc8  cmp     byte ptr [rsp+200h+var_1A8], r13b
0x18003bccd  jz      short loc_18003BCD9
0x18003bccf  lea     rcx, [rsp+200h+Src]
0x18003bcd4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bcd9  lea     rcx, [rbp+100h+lpSubKey]; Src
0x18003bcdd  call    ??E?$iterator_t@V?$key_iterator_data@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@reg@wil@@@reg@wil@@QEAAAEAV012@XZ; wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::operator++(void)
0x18003bce2  jmp     loc_18003BB5D
0x18003bce7  lea     rcx, [rbp+100h+var_F0]
0x18003bceb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bcf0  nop
0x18003bcf1  lea     rcx, [rbp+100h+lpSubKey]
0x18003bcf5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bcfa  nop
0x18003bcfb  lea     rcx, [rbp+100h+var_78]
0x18003bd02  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bd07  lea     rcx, [rbp+100h+var_B0]
0x18003bd0b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bd10  nop
0x18003bd11  mov     rcx, [r12]; hKey
0x18003bd15  test    rcx, rcx
0x18003bd18  jz      short loc_18003BD20
0x18003bd1a  call    cs:__imp_RegCloseKey
0x18003bd20  mov     rax, rbx
0x18003bd23  mov     rcx, [rbp+100h+var_40]
0x18003bd2a  xor     rcx, rsp; StackCookie
0x18003bd2d  call    __security_check_cookie
0x18003bd32  mov     rbx, [rsp+200h+arg_18]
0x18003bd3a  add     rsp, 1D0h
0x18003bd41  pop     r15
0x18003bd43  pop     r14
0x18003bd45  pop     r13
0x18003bd47  pop     r12
0x18003bd49  pop     rdi
0x18003bd4a  pop     rsi
0x18003bd4b  pop     rbp
0x18003bd4c  retn
0x18003bd4d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003bd54  mov     edx, 6FFh; void *
0x18003bd59  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003bd5f  mov     r9d, eax; char *
0x18003bd62  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003bd69  mov     edx, 6EEh; void *
0x18003bd6e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
