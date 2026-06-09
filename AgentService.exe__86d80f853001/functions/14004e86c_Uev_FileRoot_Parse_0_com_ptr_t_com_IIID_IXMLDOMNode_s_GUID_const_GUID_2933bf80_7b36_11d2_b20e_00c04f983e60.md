# Uev::FileRoot::Parse<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)

- ea: `0x14004e86c`
- end: `0x14004ecce`
- name: `??$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `1122`
- prototype: `void __fastcall(__int64, BSTR **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004ecd4`

## callees

- `0x140003e74`
- `0x14000423c`
- `0x140004ab4`
- `0x14000aa1c`
- `0x14000aa84`
- `0x14000ba60`
- `0x140011cf8`
- `0x1400260ec`
- `0x14004e86c`
- `0x14005f408`
- `0x140060494`
- `0x14006059c`
- `0x140061c00`
- `0x1400663e4`
- `0x140087a7c`
- `0x14009b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14004e8fd`
- `OLEAUT32!__imp_SysAllocString` at `0x14004e9a6`
- `OLEAUT32!__imp_SysAllocString` at `0x14004ea52`
- `OLEAUT32!__imp_SysAllocString` at `0x14004e8fd`
- `OLEAUT32!__imp_SysAllocString` at `0x14004e9a6`
- `OLEAUT32!__imp_SysAllocString` at `0x14004ea52`

## string_xrefs

- `0x14004e99f`: `RegistryEntry`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Uev::FileRoot::Parse<0>(__int64 a1, BSTR **a2)
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
  if ( __TSS0__1____Parse__0A__FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&__TSS0__1____Parse__0A__FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    if ( __TSS0__1____Parse__0A__FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA == -1 )
    {
      `Uev::FileRoot::Parse<0>'::`2'::rootStringTypes = 0;
      qword_1400D2438 = 0;
      v31 = operator new(0x30u);
      *v31 = v31;
      v31[1] = v31;
      v31[2] = v31;
      *((_WORD *)v31 + 12) = 257;
      `Uev::FileRoot::Parse<0>'::`2'::rootStringTypes = (__int64)v31;
      atexit(`Uev::FileRoot::Parse<0>'::`2'::`dynamic atexit destructor for 'rootStringTypes'');
      Init_thread_footer(&__TSS0__1____Parse__0A__FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    }
  }
  if ( !qword_1400D2438 )
  {
    v4 = _bstr_t::_bstr_t((_bstr_t *)v34, namespacePrefixes);
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
                      &`Uev::FileRoot::Parse<0>'::`2'::rootStringTypes,
                      &v33);
    v9 = v8;
    if ( *(_QWORD *)v7 )
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)v7 + 16LL), 1u);
    _bstr_t::_Free(v8);
    *(_QWORD *)v9 = *(_QWORD *)v7;
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v32);
    _bstr_t::_Free((_bstr_t *)v34);
    v10 = _bstr_t::_bstr_t((_bstr_t *)&v35, namespacePrefixes);
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
                       &`Uev::FileRoot::Parse<0>'::`2'::rootStringTypes,
                       &v33);
    v15 = v14;
    if ( *(_QWORD *)v13 )
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)v13 + 16LL), 1u);
    _bstr_t::_Free(v14);
    *(_QWORD *)v15 = *(_QWORD *)v13;
    _bstr_t::_Free((_bstr_t *)v34);
    _bstr_t::_Free((_bstr_t *)&v32);
    _bstr_t::_Free((_bstr_t *)&v35);
    v16 = _bstr_t::_bstr_t((_bstr_t *)&v35, namespacePrefixes);
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
                       &`Uev::FileRoot::Parse<0>'::`2'::rootStringTypes,
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
  v22 = *(__int64 **)`Uev::FileRoot::Parse<0>'::`2'::rootStringTypes;
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
0x14004e86c  mov     [rsp-8+arg_10], rbx
0x14004e871  push    rbp
0x14004e872  push    rsi
0x14004e873  push    rdi
0x14004e874  push    r12
0x14004e876  push    r13
0x14004e878  push    r14
0x14004e87a  push    r15
0x14004e87c  lea     rbp, [rsp-27h]
0x14004e881  sub     rsp, 0B0h
0x14004e888  mov     r13, rdx
0x14004e88b  mov     rdi, rcx
0x14004e88e  mov     [rbp+57h+var_98], rdx
0x14004e892  mov     ecx, 4
0x14004e897  mov     rax, gs:58h
0x14004e8a0  mov     rax, [rax]
0x14004e8a3  xor     r15d, r15d
0x14004e8a6  lea     r12d, [r15+1]
0x14004e8aa  mov     eax, [rcx+rax]
0x14004e8ad  cmp     cs:?$TSS0@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, eax
0x14004e8b3  jg      loc_14004EC46
0x14004e8b9  mov     r14d, 18h
0x14004e8bf  cmp     cs:qword_1400D2438, r15
0x14004e8c6  jnz     loc_14004EACA
0x14004e8cc  mov     rdx, cs:?namespacePrefixes@@3PAPEB_WA; wchar_t *
0x14004e8d3  lea     rcx, [rbp+57h+var_B0]; this
0x14004e8d7  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14004e8dc  mov     rsi, rax
0x14004e8df  mov     ecx, r14d; Size
0x14004e8e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004e8e7  mov     rbx, rax
0x14004e8ea  mov     [rbp+57h+var_C0], rax
0x14004e8ee  mov     [rax+8], r15
0x14004e8f2  mov     [rax+10h], r12d
0x14004e8f6  lea     rcx, aKnownfolder; "KnownFolder"
0x14004e8fd  call    cs:__imp_SysAllocString
0x14004e903  mov     [rbx], rax
0x14004e906  test    rax, rax
0x14004e909  jz      loc_14004ECAD
0x14004e90f  mov     [rbp+57h+var_C0], rbx
0x14004e913  lea     r8, [rbp+57h+var_C0]
0x14004e917  lea     rdx, [rbp+57h+var_A8]
0x14004e91b  mov     rcx, rsi
0x14004e91e  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x14004e923  mov     rbx, rax
0x14004e926  mov     [rbp+57h+var_B8], r12d
0x14004e92a  lea     rdx, [rbp+57h+var_B8]
0x14004e92e  lea     rcx, ?rootStringTypes@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004e935  call    ??A?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@QEAAAEAV_bstr_t@@$$QEAW4NormalizationRootType@Uev@@@Z; std::map<Uev::NormalizationRootType,_bstr_t>::operator[](Uev::NormalizationRootType &&)
0x14004e93a  mov     rsi, rax
0x14004e93d  mov     rcx, [rbx]
0x14004e940  test    rcx, rcx
0x14004e943  jz      short loc_14004E94A
0x14004e945  lock add [rcx+10h], r12d
0x14004e94a  mov     rcx, rsi; this
0x14004e94d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004e952  mov     rcx, [rbx]
0x14004e955  mov     [rsi], rcx
0x14004e958  lea     rcx, [rbp+57h+var_A8]; this
0x14004e95c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004e961  nop
0x14004e962  lea     rcx, [rbp+57h+var_C0]; this
0x14004e966  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004e96b  nop
0x14004e96c  lea     rcx, [rbp+57h+var_B0]; this
0x14004e970  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004e975  mov     rdx, cs:?namespacePrefixes@@3PAPEB_WA; wchar_t *
0x14004e97c  lea     rcx, [rbp+57h+var_A8]; this
0x14004e980  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14004e985  mov     rsi, rax
0x14004e988  mov     rcx, r14; Size
0x14004e98b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004e990  mov     rbx, rax
0x14004e993  mov     [rbp+57h+var_C0], rax
0x14004e997  mov     [rax+8], r15
0x14004e99b  mov     [rax+10h], r12d
0x14004e99f  lea     rcx, aRegistryentry; "RegistryEntry"
0x14004e9a6  call    cs:__imp_SysAllocString
0x14004e9ac  mov     [rbx], rax
0x14004e9af  test    rax, rax
0x14004e9b2  jz      loc_14004ECB8
0x14004e9b8  mov     [rbp+57h+var_C0], rbx
0x14004e9bc  lea     r8, [rbp+57h+var_C0]
0x14004e9c0  lea     rdx, [rbp+57h+var_B0]
0x14004e9c4  mov     rcx, rsi
0x14004e9c7  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x14004e9cc  mov     rbx, rax
0x14004e9cf  mov     [rbp+57h+var_B8], 2
0x14004e9d6  lea     rdx, [rbp+57h+var_B8]
0x14004e9da  lea     rcx, ?rootStringTypes@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004e9e1  call    ??A?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@QEAAAEAV_bstr_t@@$$QEAW4NormalizationRootType@Uev@@@Z; std::map<Uev::NormalizationRootType,_bstr_t>::operator[](Uev::NormalizationRootType &&)
0x14004e9e6  mov     rsi, rax
0x14004e9e9  mov     rcx, [rbx]
0x14004e9ec  test    rcx, rcx
0x14004e9ef  jz      short loc_14004E9F6
0x14004e9f1  lock add [rcx+10h], r12d
0x14004e9f6  mov     rcx, rsi; this
0x14004e9f9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004e9fe  mov     rcx, [rbx]
0x14004ea01  mov     [rsi], rcx
0x14004ea04  lea     rcx, [rbp+57h+var_B0]; this
0x14004ea08  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004ea0d  nop
0x14004ea0e  lea     rcx, [rbp+57h+var_C0]; this
0x14004ea12  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004ea17  nop
0x14004ea18  lea     rcx, [rbp+57h+var_A8]; this
0x14004ea1c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004ea21  mov     rdx, cs:?namespacePrefixes@@3PAPEB_WA; wchar_t *
0x14004ea28  lea     rcx, [rbp+57h+var_A8]; this
0x14004ea2c  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14004ea31  mov     rsi, rax
0x14004ea34  mov     rcx, r14; Size
0x14004ea37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004ea3c  mov     rbx, rax
0x14004ea3f  mov     [rbp+57h+var_C0], rax
0x14004ea43  mov     [rax+8], r15
0x14004ea47  mov     [rax+10h], r12d
0x14004ea4b  lea     rcx, aEnvironmentvar; "EnvironmentVariable"
0x14004ea52  call    cs:__imp_SysAllocString
0x14004ea58  mov     [rbx], rax
0x14004ea5b  test    rax, rax
0x14004ea5e  jz      loc_14004ECC3
0x14004ea64  mov     [rbp+57h+var_C0], rbx
0x14004ea68  lea     r8, [rbp+57h+var_C0]
0x14004ea6c  lea     rdx, [rbp+57h+var_B0]
0x14004ea70  mov     rcx, rsi
0x14004ea73  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x14004ea78  mov     rsi, rax
0x14004ea7b  mov     [rbp+57h+var_B8], r15d
0x14004ea7f  lea     rdx, [rbp+57h+var_B8]
0x14004ea83  lea     rcx, ?rootStringTypes@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004ea8a  call    ??A?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@QEAAAEAV_bstr_t@@$$QEAW4NormalizationRootType@Uev@@@Z; std::map<Uev::NormalizationRootType,_bstr_t>::operator[](Uev::NormalizationRootType &&)
0x14004ea8f  mov     rbx, rax
0x14004ea92  mov     rcx, [rsi]
0x14004ea95  test    rcx, rcx
0x14004ea98  jz      short loc_14004EA9F
0x14004ea9a  lock add [rcx+10h], r12d
0x14004ea9f  mov     rcx, rbx; this
0x14004eaa2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004eaa7  mov     rcx, [rsi]
0x14004eaaa  mov     [rbx], rcx
0x14004eaad  lea     rcx, [rbp+57h+var_B0]; this
0x14004eab1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004eab6  nop
0x14004eab7  lea     rcx, [rbp+57h+var_C0]; this
0x14004eabb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004eac0  nop
0x14004eac1  lea     rcx, [rbp+57h+var_A8]; this
0x14004eac5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004eaca  mov     rbx, cs:?rootStringTypes@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004ead1  mov     rbx, [rbx]
0x14004ead4  cmp     [rbx+19h], r15b
0x14004ead8  jnz     loc_14004EBE0
0x14004eade  mov     r12d, [rbx+20h]
0x14004eae2  mov     [rbp+57h+var_A8], r12d
0x14004eae6  mov     rax, [rbx+28h]
0x14004eaea  mov     [rbp+57h+var_A0], rax
0x14004eaee  test    rax, rax
0x14004eaf1  jz      short loc_14004EAF7
0x14004eaf3  lock inc dword ptr [rax+10h]
0x14004eaf7  test    rax, rax
0x14004eafa  jz      short loc_14004EB01
0x14004eafc  mov     rsi, [rax]
0x14004eaff  jmp     short loc_14004EB04
0x14004eb01  mov     rsi, r15
0x14004eb04  mov     rcx, [r13+0]
0x14004eb08  mov     [rbp+57h+var_C0], rcx
0x14004eb0c  test    rcx, rcx
0x14004eb0f  jz      short loc_14004EB1E
0x14004eb11  mov     rax, [rcx]
0x14004eb14  mov     rax, [rax+8]
0x14004eb18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eb1d  nop
0x14004eb1e  xor     r9d, r9d
0x14004eb21  mov     r8, rsi
0x14004eb24  lea     rdx, [rbp+57h+var_C0]
0x14004eb28  lea     rcx, [rbp+57h+var_90]
0x14004eb2c  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x14004eb31  mov     rsi, rax
0x14004eb34  lea     r15, [rdi+8]
0x14004eb38  cmp     r15, rax
0x14004eb3b  jz      short loc_14004EB6A
0x14004eb3d  mov     rcx, r15
0x14004eb40  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004eb45  movups  xmm0, xmmword ptr [rsi]
0x14004eb48  movups  xmmword ptr [r15], xmm0
0x14004eb4c  movups  xmm1, xmmword ptr [rsi+10h]
0x14004eb50  movups  xmmword ptr [r15+10h], xmm1
0x14004eb55  xor     r15d, r15d
0x14004eb58  mov     [rsi+10h], r15
0x14004eb5c  mov     qword ptr [rsi+18h], 7
0x14004eb64  mov     [rsi], r15w
0x14004eb68  jmp     short loc_14004EB6D
0x14004eb6a  xor     r15d, r15d
0x14004eb6d  lea     rcx, [rbp+57h+var_90]
0x14004eb71  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004eb76  cmp     [rdi+18h], r15
0x14004eb7a  jnz     short loc_14004EBD4
0x14004eb7c  lea     rcx, [rbp+57h+var_A0]; this
0x14004eb80  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004eb85  mov     rcx, [rbx+10h]
0x14004eb89  cmp     [rcx+19h], r15b
0x14004eb8d  jz      short loc_14004EBB0
0x14004eb8f  mov     rax, [rbx+8]
0x14004eb93  jmp     short loc_14004EBA2
0x14004eb95  cmp     rbx, [rax+10h]
0x14004eb99  jnz     short loc_14004EBA8
0x14004eb9b  mov     rbx, rax
0x14004eb9e  mov     rax, [rax+8]
0x14004eba2  cmp     [rax+19h], r15b
0x14004eba6  jz      short loc_14004EB95
0x14004eba8  mov     rbx, rax
0x14004ebab  jmp     loc_14004EAD4
0x14004ebb0  mov     rbx, rcx
0x14004ebb3  mov     rcx, [rcx]
0x14004ebb6  cmp     [rcx+19h], r15b
0x14004ebba  jnz     loc_14004EAD4
0x14004ebc0  mov     rbx, rcx
0x14004ebc3  mov     rax, [rcx]
0x14004ebc6  mov     rcx, rax
0x14004ebc9  cmp     [rax+19h], r15b
0x14004ebcd  jz      short loc_14004EBC0
0x14004ebcf  jmp     loc_14004EAD4
0x14004ebd4  mov     [rdi], r12d
0x14004ebd7  lea     rcx, [rbp+57h+var_A0]; this
0x14004ebdb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004ebe0  cmp     [r14+rdi], r15
0x14004ebe4  jz      short loc_14004EC17
0x14004ebe6  mov     rcx, [r13+0]
0x14004ebea  test    rcx, rcx
0x14004ebed  jz      short loc_14004EBFC
0x14004ebef  mov     rax, [rcx]
0x14004ebf2  mov     rax, [rax+10h]
0x14004ebf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ebfb  nop
0x14004ebfc  mov     rbx, [rsp+0E0h+arg_10]
0x14004ec04  add     rsp, 0B0h
0x14004ec0b  pop     r15
0x14004ec0d  pop     r14
0x14004ec0f  pop     r13
0x14004ec11  pop     r12
0x14004ec13  pop     rdi
0x14004ec14  pop     rsi
0x14004ec15  pop     rbp
0x14004ec16  retn
0x14004ec17  lea     rdx, aUnknownFileRoo; "Unknown file root type."
0x14004ec1e  lea     rcx, [rbp+57h+var_90]
0x14004ec22  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004ec27  nop
0x14004ec28  lea     rdx, [rbp+57h+var_90]
0x14004ec2c  lea     rcx, [rbp+57h+pExceptionObject]
0x14004ec30  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Uev::UevException::UevException(std::string const &)
0x14004ec35  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x14004ec3c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14004ec40  call    _CxxThrowException_0
0x14004ec46  lea     rcx, ?$TSS0@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x14004ec4d  call    _Init_thread_header
0x14004ec52  cmp     cs:?$TSS0@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, 0FFFFFFFFh
0x14004ec59  jnz     loc_14004E8B9
0x14004ec5f  mov     cs:?rootStringTypes@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A, r15; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004ec66  mov     cs:qword_1400D2438, r15
0x14004ec6d  mov     ecx, 30h ; '0'; Size
0x14004ec72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004ec77  mov     [rax], rax
0x14004ec7a  mov     [rax+8], rax
0x14004ec7e  mov     [rax+10h], rax
0x14004ec82  mov     word ptr [rax+18h], 101h
0x14004ec88  mov     cs:?rootStringTypes@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A, rax; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004ec8f  lea     rcx, ??__FrootStringTypes@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@YAXXZ; void (__cdecl *)()
0x14004ec96  call    atexit
0x14004ec9b  nop
0x14004ec9c  lea     rcx, ?$TSS0@?1???$Parse@$0A@@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x14004eca3  call    _Init_thread_footer
0x14004eca8  jmp     loc_14004E8B9
0x14004ecad  mov     ecx, 8007000Eh; int
0x14004ecb2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14004ecb8  mov     ecx, 8007000Eh; int
0x14004ecbd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14004ecc3  mov     ecx, 8007000Eh; int
0x14004ecc8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
