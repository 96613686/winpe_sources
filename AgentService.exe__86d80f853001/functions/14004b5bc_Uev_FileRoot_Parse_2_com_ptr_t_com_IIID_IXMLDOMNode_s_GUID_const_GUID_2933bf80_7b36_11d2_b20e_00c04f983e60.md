# Uev::FileRoot::Parse<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)

- ea: `0x14004b5bc`
- end: `0x14004ba1e`
- name: `??$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `1122`
- prototype: `void __fastcall(__int64, BSTR **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004ba24`

## callees

- `0x140003e74`
- `0x14000423c`
- `0x140004ab4`
- `0x14000aa1c`
- `0x14000aa84`
- `0x14000ba60`
- `0x140011cf8`
- `0x1400260ec`
- `0x14004b5bc`
- `0x14005f408`
- `0x140060494`
- `0x14006059c`
- `0x140061c00`
- `0x1400663e4`
- `0x140087a7c`
- `0x14009b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14004b64d`
- `OLEAUT32!__imp_SysAllocString` at `0x14004b6f6`
- `OLEAUT32!__imp_SysAllocString` at `0x14004b7a2`
- `OLEAUT32!__imp_SysAllocString` at `0x14004b64d`
- `OLEAUT32!__imp_SysAllocString` at `0x14004b6f6`
- `OLEAUT32!__imp_SysAllocString` at `0x14004b7a2`

## string_xrefs

- `0x14004b6ef`: `RegistryEntry`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Uev::FileRoot::Parse<2>(__int64 a1, BSTR **a2)
{
  _bstr_t *v4; // rsi
  BSTR *v5; // rbx
  BSTR v6; // rax
  __int64 v7; // rbx
  _bstr_t *v8; // rax
  _bstr_t *v9; // rsi
  _bstr_t *v10; // rsi
  BSTR *v11; // rbx
  BSTR v12; // rax
  __int64 v13; // rbx
  _bstr_t *v14; // rax
  _bstr_t *v15; // rsi
  _bstr_t *v16; // rsi
  BSTR *v17; // rbx
  BSTR v18; // rax
  __int64 v19; // rsi
  _bstr_t *v20; // rax
  _bstr_t *v21; // rbx
  __int64 *v22; // rbx
  int v23; // r12d
  volatile signed __int32 *v24; // rax
  __int64 v25; // rsi
  BSTR *v26; // rcx
  __int64 v27; // rsi
  __int64 **v28; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *v31; // rax
  BSTR *v32; // [rsp+20h] [rbp-69h] BYREF
  int v33; // [rsp+28h] [rbp-61h] BYREF
  char v34[8]; // [rsp+30h] [rbp-59h] BYREF
  int v35; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v36[2]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v37[32]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-19h] BYREF

  v36[1] = a2;
  if ( __TSS0__1____Parse__01_FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&__TSS0__1____Parse__01_FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    if ( __TSS0__1____Parse__01_FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA == -1 )
    {
      `Uev::FileRoot::Parse<2>'::`2'::rootStringTypes = 0;
      qword_1400D1F50 = 0;
      v31 = operator new(0x30u);
      *v31 = v31;
      v31[1] = v31;
      v31[2] = v31;
      *((_WORD *)v31 + 12) = 257;
      `Uev::FileRoot::Parse<2>'::`2'::rootStringTypes = (__int64)v31;
      atexit(`Uev::FileRoot::Parse<2>'::`2'::`dynamic atexit destructor for 'rootStringTypes'');
      Init_thread_footer(&__TSS0__1____Parse__01_FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    }
  }
  if ( !qword_1400D1F50 )
  {
    v4 = _bstr_t::_bstr_t((_bstr_t *)v34, off_1400CB300);
    v5 = (BSTR *)operator new(0x18u);
    v32 = v5;
    v5[1] = 0;
    *((_DWORD *)v5 + 4) = 1;
    v6 = SysAllocString(L"KnownFolder");
    *v5 = v6;
    if ( !v6 )
      _com_issue_error(-2147024882);
    v32 = v5;
    v7 = _bstr_t::operator+(v4, &v35, &v32);
    v33 = 1;
    v8 = (_bstr_t *)std::map<enum Uev::NormalizationRootType,_bstr_t>::operator[](
                      &`Uev::FileRoot::Parse<2>'::`2'::rootStringTypes,
                      &v33);
    v9 = v8;
    if ( *(_QWORD *)v7 )
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)v7 + 16LL), 1u);
    _bstr_t::_Free(v8);
    *(_QWORD *)v9 = *(_QWORD *)v7;
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v32);
    _bstr_t::_Free((_bstr_t *)v34);
    v10 = _bstr_t::_bstr_t((_bstr_t *)&v35, off_1400CB300);
    v11 = (BSTR *)operator new(0x18u);
    v32 = v11;
    v11[1] = 0;
    *((_DWORD *)v11 + 4) = 1;
    v12 = SysAllocString(L"RegistryEntry");
    *v11 = v12;
    if ( !v12 )
      _com_issue_error(-2147024882);
    v32 = v11;
    v13 = _bstr_t::operator+(v10, v34, &v32);
    v33 = 2;
    v14 = (_bstr_t *)std::map<enum Uev::NormalizationRootType,_bstr_t>::operator[](
                       &`Uev::FileRoot::Parse<2>'::`2'::rootStringTypes,
                       &v33);
    v15 = v14;
    if ( *(_QWORD *)v13 )
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)v13 + 16LL), 1u);
    _bstr_t::_Free(v14);
    *(_QWORD *)v15 = *(_QWORD *)v13;
    _bstr_t::_Free((_bstr_t *)v34);
    _bstr_t::_Free((_bstr_t *)&v32);
    _bstr_t::_Free((_bstr_t *)&v35);
    v16 = _bstr_t::_bstr_t((_bstr_t *)&v35, off_1400CB300);
    v17 = (BSTR *)operator new(0x18u);
    v32 = v17;
    v17[1] = 0;
    *((_DWORD *)v17 + 4) = 1;
    v18 = SysAllocString(L"EnvironmentVariable");
    *v17 = v18;
    if ( !v18 )
      _com_issue_error(-2147024882);
    v32 = v17;
    v19 = _bstr_t::operator+(v16, v34, &v32);
    v33 = 0;
    v20 = (_bstr_t *)std::map<enum Uev::NormalizationRootType,_bstr_t>::operator[](
                       &`Uev::FileRoot::Parse<2>'::`2'::rootStringTypes,
                       &v33);
    v21 = v20;
    if ( *(_QWORD *)v19 )
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)v19 + 16LL), 1u);
    _bstr_t::_Free(v20);
    *(_QWORD *)v21 = *(_QWORD *)v19;
    _bstr_t::_Free((_bstr_t *)v34);
    _bstr_t::_Free((_bstr_t *)&v32);
    _bstr_t::_Free((_bstr_t *)&v35);
  }
  v22 = *(__int64 **)`Uev::FileRoot::Parse<2>'::`2'::rootStringTypes;
  while ( !*((_BYTE *)v22 + 25) )
  {
    v23 = *((_DWORD *)v22 + 8);
    v35 = v23;
    v24 = (volatile signed __int32 *)v22[5];
    v36[0] = v24;
    if ( v24 )
    {
      _InterlockedIncrement(v24 + 4);
      v25 = *(_QWORD *)v24;
    }
    else
    {
      v25 = 0;
    }
    v26 = *a2;
    v32 = v26;
    if ( v26 )
      (*((void (__fastcall **)(BSTR *))*v26 + 1))(v26);
    v27 = ((__int64 (__fastcall *)(_BYTE *, BSTR **, __int64, _QWORD))Uev::DomHelper::GetNodeText)(v37, &v32, v25, 0);
    if ( a1 + 8 != v27 )
    {
      std::wstring::_Tidy_deallocate(a1 + 8);
      *(_OWORD *)(a1 + 8) = *(_OWORD *)v27;
      *(_OWORD *)(a1 + 24) = *(_OWORD *)(v27 + 16);
      *(_QWORD *)(v27 + 16) = 0;
      *(_QWORD *)(v27 + 24) = 7;
      *(_WORD *)v27 = 0;
    }
    std::wstring::_Tidy_deallocate(v37);
    if ( *(_QWORD *)(a1 + 24) )
    {
      *(_DWORD *)a1 = v23;
      _bstr_t::_Free((_bstr_t *)v36);
      break;
    }
    _bstr_t::_Free((_bstr_t *)v36);
    v28 = (__int64 **)v22[2];
    if ( *((_BYTE *)v28 + 25) )
    {
      for ( i = (__int64 *)v22[1]; !*((_BYTE *)i + 25) && v22 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v22 = i;
      v22 = i;
    }
    else
    {
      v22 = (__int64 *)v22[2];
      for ( j = *v28; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v22 = j;
    }
  }
  if ( !*(_QWORD *)(a1 + 24) )
  {
    std::string::string(v37, "Unknown file root type.");
    Uev::UevException::UevException(pExceptionObject, v37);
    throw (Uev::UevException *)pExceptionObject;
  }
  if ( *a2 )
    (*((void (__fastcall **)(BSTR *))**a2 + 2))(*a2);
}

```

## disassembly

```asm
0x14004b5bc  mov     [rsp-8+arg_10], rbx
0x14004b5c1  push    rbp
0x14004b5c2  push    rsi
0x14004b5c3  push    rdi
0x14004b5c4  push    r12
0x14004b5c6  push    r13
0x14004b5c8  push    r14
0x14004b5ca  push    r15
0x14004b5cc  lea     rbp, [rsp-27h]
0x14004b5d1  sub     rsp, 0B0h
0x14004b5d8  mov     r13, rdx
0x14004b5db  mov     rdi, rcx
0x14004b5de  mov     [rbp+57h+var_98], rdx
0x14004b5e2  mov     ecx, 4
0x14004b5e7  mov     rax, gs:58h
0x14004b5f0  mov     rax, [rax]
0x14004b5f3  xor     r15d, r15d
0x14004b5f6  lea     r12d, [r15+1]
0x14004b5fa  mov     eax, [rcx+rax]
0x14004b5fd  cmp     cs:?$TSS0@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, eax
0x14004b603  jg      loc_14004B996
0x14004b609  mov     r14d, 18h
0x14004b60f  cmp     cs:qword_1400D1F50, r15
0x14004b616  jnz     loc_14004B81A
0x14004b61c  mov     rdx, cs:off_1400CB300; wchar_t *
0x14004b623  lea     rcx, [rbp+57h+var_B0]; this
0x14004b627  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14004b62c  mov     rsi, rax
0x14004b62f  mov     ecx, r14d; Size
0x14004b632  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004b637  mov     rbx, rax
0x14004b63a  mov     [rbp+57h+var_C0], rax
0x14004b63e  mov     [rax+8], r15
0x14004b642  mov     [rax+10h], r12d
0x14004b646  lea     rcx, aKnownfolder; "KnownFolder"
0x14004b64d  call    cs:__imp_SysAllocString
0x14004b653  mov     [rbx], rax
0x14004b656  test    rax, rax
0x14004b659  jz      loc_14004B9FD
0x14004b65f  mov     [rbp+57h+var_C0], rbx
0x14004b663  lea     r8, [rbp+57h+var_C0]
0x14004b667  lea     rdx, [rbp+57h+var_A8]
0x14004b66b  mov     rcx, rsi
0x14004b66e  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x14004b673  mov     rbx, rax
0x14004b676  mov     [rbp+57h+var_B8], r12d
0x14004b67a  lea     rdx, [rbp+57h+var_B8]
0x14004b67e  lea     rcx, ?rootStringTypes@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004b685  call    ??A?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@QEAAAEAV_bstr_t@@$$QEAW4NormalizationRootType@Uev@@@Z; std::map<Uev::NormalizationRootType,_bstr_t>::operator[](Uev::NormalizationRootType &&)
0x14004b68a  mov     rsi, rax
0x14004b68d  mov     rcx, [rbx]
0x14004b690  test    rcx, rcx
0x14004b693  jz      short loc_14004B69A
0x14004b695  lock add [rcx+10h], r12d
0x14004b69a  mov     rcx, rsi; this
0x14004b69d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b6a2  mov     rcx, [rbx]
0x14004b6a5  mov     [rsi], rcx
0x14004b6a8  lea     rcx, [rbp+57h+var_A8]; this
0x14004b6ac  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b6b1  nop
0x14004b6b2  lea     rcx, [rbp+57h+var_C0]; this
0x14004b6b6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b6bb  nop
0x14004b6bc  lea     rcx, [rbp+57h+var_B0]; this
0x14004b6c0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b6c5  mov     rdx, cs:off_1400CB300; wchar_t *
0x14004b6cc  lea     rcx, [rbp+57h+var_A8]; this
0x14004b6d0  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14004b6d5  mov     rsi, rax
0x14004b6d8  mov     rcx, r14; Size
0x14004b6db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004b6e0  mov     rbx, rax
0x14004b6e3  mov     [rbp+57h+var_C0], rax
0x14004b6e7  mov     [rax+8], r15
0x14004b6eb  mov     [rax+10h], r12d
0x14004b6ef  lea     rcx, aRegistryentry; "RegistryEntry"
0x14004b6f6  call    cs:__imp_SysAllocString
0x14004b6fc  mov     [rbx], rax
0x14004b6ff  test    rax, rax
0x14004b702  jz      loc_14004BA08
0x14004b708  mov     [rbp+57h+var_C0], rbx
0x14004b70c  lea     r8, [rbp+57h+var_C0]
0x14004b710  lea     rdx, [rbp+57h+var_B0]
0x14004b714  mov     rcx, rsi
0x14004b717  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x14004b71c  mov     rbx, rax
0x14004b71f  mov     [rbp+57h+var_B8], 2
0x14004b726  lea     rdx, [rbp+57h+var_B8]
0x14004b72a  lea     rcx, ?rootStringTypes@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004b731  call    ??A?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@QEAAAEAV_bstr_t@@$$QEAW4NormalizationRootType@Uev@@@Z; std::map<Uev::NormalizationRootType,_bstr_t>::operator[](Uev::NormalizationRootType &&)
0x14004b736  mov     rsi, rax
0x14004b739  mov     rcx, [rbx]
0x14004b73c  test    rcx, rcx
0x14004b73f  jz      short loc_14004B746
0x14004b741  lock add [rcx+10h], r12d
0x14004b746  mov     rcx, rsi; this
0x14004b749  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b74e  mov     rcx, [rbx]
0x14004b751  mov     [rsi], rcx
0x14004b754  lea     rcx, [rbp+57h+var_B0]; this
0x14004b758  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b75d  nop
0x14004b75e  lea     rcx, [rbp+57h+var_C0]; this
0x14004b762  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b767  nop
0x14004b768  lea     rcx, [rbp+57h+var_A8]; this
0x14004b76c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b771  mov     rdx, cs:off_1400CB300; wchar_t *
0x14004b778  lea     rcx, [rbp+57h+var_A8]; this
0x14004b77c  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14004b781  mov     rsi, rax
0x14004b784  mov     rcx, r14; Size
0x14004b787  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004b78c  mov     rbx, rax
0x14004b78f  mov     [rbp+57h+var_C0], rax
0x14004b793  mov     [rax+8], r15
0x14004b797  mov     [rax+10h], r12d
0x14004b79b  lea     rcx, aEnvironmentvar; "EnvironmentVariable"
0x14004b7a2  call    cs:__imp_SysAllocString
0x14004b7a8  mov     [rbx], rax
0x14004b7ab  test    rax, rax
0x14004b7ae  jz      loc_14004BA13
0x14004b7b4  mov     [rbp+57h+var_C0], rbx
0x14004b7b8  lea     r8, [rbp+57h+var_C0]
0x14004b7bc  lea     rdx, [rbp+57h+var_B0]
0x14004b7c0  mov     rcx, rsi
0x14004b7c3  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x14004b7c8  mov     rsi, rax
0x14004b7cb  mov     [rbp+57h+var_B8], r15d
0x14004b7cf  lea     rdx, [rbp+57h+var_B8]
0x14004b7d3  lea     rcx, ?rootStringTypes@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004b7da  call    ??A?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@QEAAAEAV_bstr_t@@$$QEAW4NormalizationRootType@Uev@@@Z; std::map<Uev::NormalizationRootType,_bstr_t>::operator[](Uev::NormalizationRootType &&)
0x14004b7df  mov     rbx, rax
0x14004b7e2  mov     rcx, [rsi]
0x14004b7e5  test    rcx, rcx
0x14004b7e8  jz      short loc_14004B7EF
0x14004b7ea  lock add [rcx+10h], r12d
0x14004b7ef  mov     rcx, rbx; this
0x14004b7f2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b7f7  mov     rcx, [rsi]
0x14004b7fa  mov     [rbx], rcx
0x14004b7fd  lea     rcx, [rbp+57h+var_B0]; this
0x14004b801  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b806  nop
0x14004b807  lea     rcx, [rbp+57h+var_C0]; this
0x14004b80b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b810  nop
0x14004b811  lea     rcx, [rbp+57h+var_A8]; this
0x14004b815  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b81a  mov     rbx, cs:?rootStringTypes@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004b821  mov     rbx, [rbx]
0x14004b824  cmp     [rbx+19h], r15b
0x14004b828  jnz     loc_14004B930
0x14004b82e  mov     r12d, [rbx+20h]
0x14004b832  mov     [rbp+57h+var_A8], r12d
0x14004b836  mov     rax, [rbx+28h]
0x14004b83a  mov     [rbp+57h+var_A0], rax
0x14004b83e  test    rax, rax
0x14004b841  jz      short loc_14004B847
0x14004b843  lock inc dword ptr [rax+10h]
0x14004b847  test    rax, rax
0x14004b84a  jz      short loc_14004B851
0x14004b84c  mov     rsi, [rax]
0x14004b84f  jmp     short loc_14004B854
0x14004b851  mov     rsi, r15
0x14004b854  mov     rcx, [r13+0]
0x14004b858  mov     [rbp+57h+var_C0], rcx
0x14004b85c  test    rcx, rcx
0x14004b85f  jz      short loc_14004B86E
0x14004b861  mov     rax, [rcx]
0x14004b864  mov     rax, [rax+8]
0x14004b868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b86d  nop
0x14004b86e  xor     r9d, r9d
0x14004b871  mov     r8, rsi
0x14004b874  lea     rdx, [rbp+57h+var_C0]
0x14004b878  lea     rcx, [rbp+57h+var_90]
0x14004b87c  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x14004b881  mov     rsi, rax
0x14004b884  lea     r15, [rdi+8]
0x14004b888  cmp     r15, rax
0x14004b88b  jz      short loc_14004B8BA
0x14004b88d  mov     rcx, r15
0x14004b890  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004b895  movups  xmm0, xmmword ptr [rsi]
0x14004b898  movups  xmmword ptr [r15], xmm0
0x14004b89c  movups  xmm1, xmmword ptr [rsi+10h]
0x14004b8a0  movups  xmmword ptr [r15+10h], xmm1
0x14004b8a5  xor     r15d, r15d
0x14004b8a8  mov     [rsi+10h], r15
0x14004b8ac  mov     qword ptr [rsi+18h], 7
0x14004b8b4  mov     [rsi], r15w
0x14004b8b8  jmp     short loc_14004B8BD
0x14004b8ba  xor     r15d, r15d
0x14004b8bd  lea     rcx, [rbp+57h+var_90]
0x14004b8c1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004b8c6  cmp     [rdi+18h], r15
0x14004b8ca  jnz     short loc_14004B924
0x14004b8cc  lea     rcx, [rbp+57h+var_A0]; this
0x14004b8d0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b8d5  mov     rcx, [rbx+10h]
0x14004b8d9  cmp     [rcx+19h], r15b
0x14004b8dd  jz      short loc_14004B900
0x14004b8df  mov     rax, [rbx+8]
0x14004b8e3  jmp     short loc_14004B8F2
0x14004b8e5  cmp     rbx, [rax+10h]
0x14004b8e9  jnz     short loc_14004B8F8
0x14004b8eb  mov     rbx, rax
0x14004b8ee  mov     rax, [rax+8]
0x14004b8f2  cmp     [rax+19h], r15b
0x14004b8f6  jz      short loc_14004B8E5
0x14004b8f8  mov     rbx, rax
0x14004b8fb  jmp     loc_14004B824
0x14004b900  mov     rbx, rcx
0x14004b903  mov     rcx, [rcx]
0x14004b906  cmp     [rcx+19h], r15b
0x14004b90a  jnz     loc_14004B824
0x14004b910  mov     rbx, rcx
0x14004b913  mov     rax, [rcx]
0x14004b916  mov     rcx, rax
0x14004b919  cmp     [rax+19h], r15b
0x14004b91d  jz      short loc_14004B910
0x14004b91f  jmp     loc_14004B824
0x14004b924  mov     [rdi], r12d
0x14004b927  lea     rcx, [rbp+57h+var_A0]; this
0x14004b92b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004b930  cmp     [r14+rdi], r15
0x14004b934  jz      short loc_14004B967
0x14004b936  mov     rcx, [r13+0]
0x14004b93a  test    rcx, rcx
0x14004b93d  jz      short loc_14004B94C
0x14004b93f  mov     rax, [rcx]
0x14004b942  mov     rax, [rax+10h]
0x14004b946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b94b  nop
0x14004b94c  mov     rbx, [rsp+0E0h+arg_10]
0x14004b954  add     rsp, 0B0h
0x14004b95b  pop     r15
0x14004b95d  pop     r14
0x14004b95f  pop     r13
0x14004b961  pop     r12
0x14004b963  pop     rdi
0x14004b964  pop     rsi
0x14004b965  pop     rbp
0x14004b966  retn
0x14004b967  lea     rdx, aUnknownFileRoo; "Unknown file root type."
0x14004b96e  lea     rcx, [rbp+57h+var_90]
0x14004b972  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004b977  nop
0x14004b978  lea     rdx, [rbp+57h+var_90]
0x14004b97c  lea     rcx, [rbp+57h+pExceptionObject]
0x14004b980  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Uev::UevException::UevException(std::string const &)
0x14004b985  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x14004b98c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14004b990  call    _CxxThrowException_0
0x14004b996  lea     rcx, ?$TSS0@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x14004b99d  call    _Init_thread_header
0x14004b9a2  cmp     cs:?$TSS0@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, 0FFFFFFFFh
0x14004b9a9  jnz     loc_14004B609
0x14004b9af  mov     cs:?rootStringTypes@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A, r15; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004b9b6  mov     cs:qword_1400D1F50, r15
0x14004b9bd  mov     ecx, 30h ; '0'; Size
0x14004b9c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004b9c7  mov     [rax], rax
0x14004b9ca  mov     [rax+8], rax
0x14004b9ce  mov     [rax+10h], rax
0x14004b9d2  mov     word ptr [rax+18h], 101h
0x14004b9d8  mov     cs:?rootStringTypes@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A, rax; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004b9df  lea     rcx, ??__FrootStringTypes@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@YAXXZ; void (__cdecl *)()
0x14004b9e6  call    atexit
0x14004b9eb  nop
0x14004b9ec  lea     rcx, ?$TSS0@?1???$Parse@$01@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x14004b9f3  call    _Init_thread_footer
0x14004b9f8  jmp     loc_14004B609
0x14004b9fd  mov     ecx, 8007000Eh; int
0x14004ba02  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14004ba08  mov     ecx, 8007000Eh; int
0x14004ba0d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14004ba13  mov     ecx, 8007000Eh; int
0x14004ba18  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
