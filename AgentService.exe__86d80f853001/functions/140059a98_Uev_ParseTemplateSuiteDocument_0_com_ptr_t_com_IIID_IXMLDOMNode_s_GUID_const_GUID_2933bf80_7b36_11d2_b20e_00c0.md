# Uev::ParseTemplateSuiteDocument<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Uev::TemplateSuiteData &)

- ea: `0x140059a98`
- end: `0x14005ae68`
- name: `??$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@0@@Z`
- size: `5072`
- prototype: `void __fastcall(BSTR **, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140063f54`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x14000423c`
- `0x140004ab4`
- `0x14000aa1c`
- `0x14000aa84`
- `0x14000ba60`
- `0x14000bacc`
- `0x14000d7b4`
- `0x140011cf8`
- `0x1400231f8`
- `0x140025560`
- `0x14004fac8`
- `0x140055198`
- `0x140059a98`
- `0x14005b94c`
- `0x14005e2f0`
- `0x14005eaac`
- `0x14005ef28`
- `0x14005f408`
- `0x14005f9bc`
- `0x14006059c`
- `0x140061010`
- `0x140061150`
- `0x140061704`
- `0x1400617c4`
- `0x140061c00`
- `0x140061d9c`
- `0x1400663e4`
- `0x140087a7c`
- `0x14009b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14005a676`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a731`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a7ec`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a8a7`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a962`
- `OLEAUT32!__imp_SysAllocString` at `0x14005aa1d`
- `OLEAUT32!__imp_SysAllocString` at `0x14005aad8`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ab93`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ac4e`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ad09`
- `OLEAUT32!__imp_SysAllocString` at `0x14005adc4`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a676`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a731`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a7ec`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a8a7`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a962`
- `OLEAUT32!__imp_SysAllocString` at `0x14005aa1d`
- `OLEAUT32!__imp_SysAllocString` at `0x14005aad8`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ab93`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ac4e`
- `OLEAUT32!__imp_SysAllocString` at `0x14005ad09`
- `OLEAUT32!__imp_SysAllocString` at `0x14005adc4`

## string_xrefs

- `0x14005ac47`: `Common`
- `0x14005ae37`: `Application template section has the same ID as another section.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Uev::ParseTemplateSuiteDocument<0>(BSTR **a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r13
  __int64 v5; // r14
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v9; // rbx
  __int64 v10; // rbx
  BSTR *v11; // rcx
  __int64 NodeText; // rbx
  BSTR *v13; // rbx
  __int64 v14; // rdi
  BSTR *v15; // rcx
  BSTR **Node; // rax
  __int64 v17; // r8
  _WORD *v18; // rcx
  __int64 v19; // rdi
  char NodeBoolean; // al
  __int64 v21; // rdi
  BSTR *v22; // rcx
  __int64 v23; // rdi
  BSTR *v24; // rcx
  __int64 v25; // rsi
  _OWORD *v26; // rdi
  __int64 v27; // rsi
  BSTR *v28; // rcx
  __int64 v29; // rsi
  _OWORD *v30; // r14
  __int64 v31; // rsi
  BSTR *v32; // rcx
  __int64 v33; // rsi
  __int64 LocalizedValue; // rsi
  __int64 v35; // rdi
  BSTR *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rdi
  __int64 v39; // rdi
  BSTR *v40; // rbx
  __int64 v41; // rdi
  BSTR *v42; // rcx
  BSTR **v43; // rax
  __int64 v44; // r8
  __int64 v45; // r9
  BSTR *v46; // rbx
  __int64 v47; // rdi
  BSTR *v48; // rcx
  BSTR **v49; // rax
  BSTR *v50; // rcx
  _OWORD *v51; // r14
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 *v54; // rsi
  __int64 v55; // rcx
  __int64 v56; // r9
  __int64 v57; // rdi
  BSTR *v58; // rcx
  unsigned int (__fastcall *v59)(BSTR *, __int64, BSTR **); // r9
  __int64 v60; // rdx
  BSTR *v61; // rdi
  void (__fastcall *v62)(BSTR *, BSTR **); // r14
  BSTR *v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rcx
  __int64 v67; // r9
  __int64 v68; // rdi
  BSTR *v69; // rdi
  void (__fastcall *v70)(BSTR *, BSTR **); // r14
  _bstr_t *v71; // rsi
  BSTR *v72; // rdi
  BSTR v73; // rax
  _bstr_t *v74; // rsi
  BSTR *v75; // rdi
  BSTR v76; // rax
  _bstr_t *v77; // rsi
  BSTR *v78; // rdi
  BSTR v79; // rax
  _bstr_t *v80; // rsi
  BSTR *v81; // rdi
  BSTR v82; // rax
  _bstr_t *v83; // rsi
  BSTR *v84; // rdi
  BSTR v85; // rax
  _bstr_t *v86; // rsi
  BSTR *v87; // rdi
  BSTR v88; // rax
  _bstr_t *v89; // rsi
  BSTR *v90; // rdi
  BSTR v91; // rax
  _bstr_t *v92; // rsi
  BSTR *v93; // rdi
  BSTR v94; // rax
  _bstr_t *v95; // rsi
  BSTR *v96; // rdi
  BSTR v97; // rax
  _bstr_t *v98; // rsi
  BSTR *v99; // rdi
  BSTR v100; // rax
  _bstr_t *v101; // rdi
  BSTR *v102; // rbx
  BSTR v103; // rax
  __int64 v104; // [rsp+20h] [rbp-E0h]
  __int64 v105; // [rsp+20h] [rbp-E0h]
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-B0h] BYREF
  BSTR **v108; // [rsp+90h] [rbp-70h]
  BSTR *v109; // [rsp+98h] [rbp-68h] BYREF
  BSTR *v110; // [rsp+A0h] [rbp-60h] BYREF
  BSTR *v111; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v112[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v113; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v114; // [rsp+D0h] [rbp-30h]
  __int64 v115; // [rsp+D8h] [rbp-28h]
  __int128 v116; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v117; // [rsp+F0h] [rbp-10h]
  __int64 v118; // [rsp+F8h] [rbp-8h]
  _OWORD v119[17]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v120[272]; // [rsp+210h] [rbp+110h] BYREF

  v4 = a4;
  v5 = a3;
  v108 = a1;
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v9 = *ThreadLocalStoragePointer;
  if ( __TSS0__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&__TSS0__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS0__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v71 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v72 = (BSTR *)operator new(0x18u);
      v72[1] = 0;
      *((_DWORD *)v72 + 4) = 1;
      v73 = SysAllocString(L"Name");
      *v72 = v73;
      if ( !v73 )
        _com_issue_error(-2147024882);
      v109 = v72;
      _bstr_t::operator+(v71, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::nameString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__nameString__);
      Init_thread_footer(&__TSS0__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS1__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS1__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS1__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v74 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v75 = (BSTR *)operator new(0x18u);
      v75[1] = 0;
      *((_DWORD *)v75 + 4) = 1;
      v76 = SysAllocString(L"Description");
      *v75 = v76;
      if ( !v76 )
        _com_issue_error(-2147024882);
      v109 = v75;
      _bstr_t::operator+(v74, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::descriptionString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__descriptionString__);
      Init_thread_footer(&__TSS1__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS2__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS2__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS2__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v77 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v78 = (BSTR *)operator new(0x18u);
      v78[1] = 0;
      *((_DWORD *)v78 + 4) = 1;
      v79 = SysAllocString(L"LocalizedNames");
      *v78 = v79;
      if ( !v79 )
        _com_issue_error(-2147024882);
      v109 = v78;
      _bstr_t::operator+(v77, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::localizedNameString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__localizedNameString__);
      Init_thread_footer(&__TSS2__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS3__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS3__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS3__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v80 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v81 = (BSTR *)operator new(0x18u);
      v81[1] = 0;
      *((_DWORD *)v81 + 4) = 1;
      v82 = SysAllocString(L"LocalizedDescriptions");
      *v81 = v82;
      if ( !v82 )
        _com_issue_error(-2147024882);
      v109 = v81;
      _bstr_t::operator+(v80, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::localizedDescriptionString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__localizedDescriptionString__);
      Init_thread_footer(&__TSS3__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS4__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS4__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS4__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v83 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v84 = (BSTR *)operator new(0x18u);
      v84[1] = 0;
      *((_DWORD *)v84 + 4) = 1;
      v85 = SysAllocString(L"ID");
      *v84 = v85;
      if ( !v85 )
        _com_issue_error(-2147024882);
      v109 = v84;
      _bstr_t::operator+(v83, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::idString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__idString__);
      Init_thread_footer(&__TSS4__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS5__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS5__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS5__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v86 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v87 = (BSTR *)operator new(0x18u);
      v87[1] = 0;
      *((_DWORD *)v87 + 4) = 1;
      v88 = SysAllocString(L"Author");
      *v87 = v88;
      if ( !v88 )
        _com_issue_error(-2147024882);
      v109 = v87;
      _bstr_t::operator+(v86, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::authorString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__authorString__);
      Init_thread_footer(&__TSS5__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS6__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS6__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS6__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v89 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v90 = (BSTR *)operator new(0x18u);
      v90[1] = 0;
      *((_DWORD *)v90 + 4) = 1;
      v91 = SysAllocString(L"FixedProfile");
      *v90 = v91;
      if ( !v91 )
        _com_issue_error(-2147024882);
      v109 = v90;
      _bstr_t::operator+(v89, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::fixedProfileString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__fixedProfileString__);
      Init_thread_footer(&__TSS6__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS7__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS7__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS7__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v92 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v93 = (BSTR *)operator new(0x18u);
      v93[1] = 0;
      *((_DWORD *)v93 + 4) = 1;
      v94 = SysAllocString(L"ManageSuiteOnly");
      *v93 = v94;
      if ( !v94 )
        _com_issue_error(-2147024882);
      v109 = v93;
      _bstr_t::operator+(v92, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::manageSuiteOnlyString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__manageSuiteOnlyString__);
      Init_thread_footer(&__TSS7__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS8__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS8__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS8__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v95 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v96 = (BSTR *)operator new(0x18u);
      v96[1] = 0;
      *((_DWORD *)v96 + 4) = 1;
      v97 = SysAllocString(L"Common");
      *v96 = v97;
      if ( !v97 )
        _com_issue_error(-2147024882);
      v109 = v96;
      _bstr_t::operator+(v95, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::commonString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__commonString__);
      Init_thread_footer(&__TSS8__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS9__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS9__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS9__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v98 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v99 = (BSTR *)operator new(0x18u);
      v99[1] = 0;
      *((_DWORD *)v99 + 4) = 1;
      v100 = SysAllocString(L"Application");
      *v99 = v100;
      if ( !v100 )
        _com_issue_error(-2147024882);
      v109 = v99;
      _bstr_t::operator+(v98, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::applicationString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__applicationString__);
      Init_thread_footer(&__TSS9__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS10__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS10__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS10__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v101 = _bstr_t::_bstr_t((_bstr_t *)&v110, namespacePrefixes);
      v102 = (BSTR *)operator new(0x18u);
      v102[1] = 0;
      *((_DWORD *)v102 + 4) = 1;
      v103 = SysAllocString(L"CustomAction");
      *v102 = v103;
      if ( !v103 )
        _com_issue_error(-2147024882);
      v109 = v102;
      _bstr_t::operator+(v101, &`Uev::ParseTemplateSuiteDocument<0>'::`2'::customActionString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_0__::_2_::_dynamic_atexit_destructor_for__customActionString__);
      Init_thread_footer(&__TSS10__1____ParseTemplateSuiteDocument__0A__Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( (a2 & 1) != 0 )
  {
    if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::idString )
      v10 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::idString;
    else
      v10 = 0;
    v11 = *a1;
    v109 = v11;
    if ( v11 )
      (*((void (__fastcall **)(BSTR *))*v11 + 1))(v11);
    LOBYTE(a4) = 1;
    NodeText = Uev::DomHelper::GetNodeText(pExceptionObject, &v109, v10, a4);
    if ( v4 + 40 != NodeText )
    {
      std::wstring::_Tidy_deallocate(v4 + 40);
      *(_OWORD *)(v4 + 40) = *(_OWORD *)NodeText;
      *(_OWORD *)(v4 + 56) = *(_OWORD *)(NodeText + 16);
      *(_QWORD *)(NodeText + 16) = 0;
      *(_QWORD *)(NodeText + 24) = 7;
      *(_WORD *)NodeText = 0;
    }
    std::wstring::_Tidy_deallocate(pExceptionObject);
    v13 = 0;
    if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::fixedProfileString )
      v14 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::fixedProfileString;
    else
      v14 = 0;
    v15 = *a1;
    v109 = v15;
    if ( v15 )
      (*((void (__fastcall **)(BSTR *))*v15 + 1))(v15);
    Node = (BSTR **)Uev::DomHelper::GetNode(&v110, &v109, v14, 0, v104);
    if ( *Node )
    {
      v13 = *Node;
      (*((void (__fastcall **)(BSTR *))**Node + 1))(*Node);
    }
    if ( v110 )
      (*((void (__fastcall **)(BSTR *))*v110 + 2))(v110);
    if ( v13 )
    {
      v109 = v13;
      (*((void (__fastcall **)(BSTR *))*v13 + 1))(v13);
      v19 = Uev::DomHelper::GetNodeText(pExceptionObject, &v109);
      if ( v4 + 200 != v19 )
      {
        std::wstring::_Tidy_deallocate(v4 + 200);
        *(_OWORD *)(v4 + 200) = *(_OWORD *)v19;
        *(_OWORD *)(v4 + 216) = *(_OWORD *)(v19 + 16);
        *(_QWORD *)(v19 + 16) = 0;
        *(_QWORD *)(v19 + 24) = 7;
        *(_WORD *)v19 = 0;
      }
      std::wstring::_Tidy_deallocate(pExceptionObject);
    }
    else
    {
      if ( *(_QWORD *)(v4 + 224) <= 7u )
        v18 = (_WORD *)(v4 + 200);
      else
        v18 = *(_WORD **)(v4 + 200);
      *(_QWORD *)(v4 + 216) = 0;
      *v18 = 0;
    }
    if ( (a2 & 0x400) != 0 )
    {
      NodeBoolean = 0;
    }
    else
    {
      if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::manageSuiteOnlyString )
        v21 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::manageSuiteOnlyString;
      else
        v21 = 0;
      v22 = *a1;
      v109 = v22;
      if ( v22 )
        (*((void (__fastcall **)(BSTR *))*v22 + 1))(v22);
      NodeBoolean = Uev::DomHelper::GetNodeBoolean(&v109, v21, v17, 0);
    }
    *(_BYTE *)(v4 + 1) = NodeBoolean;
    if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::nameString )
      v23 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::nameString;
    else
      v23 = 0;
    v24 = *a1;
    v109 = v24;
    if ( v24 )
      (*((void (__fastcall **)(BSTR *))*v24 + 1))(v24);
    v25 = Uev::DomHelper::GetNodeText(pExceptionObject, &v109, v23, 0);
    v26 = (_OWORD *)(v4 + 72);
    if ( v4 + 72 != v25 )
    {
      std::wstring::_Tidy_deallocate(v4 + 72);
      *v26 = *(_OWORD *)v25;
      *(_OWORD *)(v4 + 88) = *(_OWORD *)(v25 + 16);
      *(_QWORD *)(v25 + 16) = 0;
      *(_QWORD *)(v25 + 24) = 7;
      *(_WORD *)v25 = 0;
    }
    std::wstring::_Tidy_deallocate(pExceptionObject);
    if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::descriptionString )
      v27 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::descriptionString;
    else
      v27 = 0;
    v28 = *a1;
    v109 = v28;
    if ( v28 )
      (*((void (__fastcall **)(BSTR *))*v28 + 1))(v28);
    v29 = Uev::DomHelper::GetNodeText(pExceptionObject, &v109, v27, 0);
    v30 = (_OWORD *)(v4 + 104);
    if ( v4 + 104 != v29 )
    {
      std::wstring::_Tidy_deallocate(v4 + 104);
      *v30 = *(_OWORD *)v29;
      *(_OWORD *)(v4 + 120) = *(_OWORD *)(v29 + 16);
      *(_QWORD *)(v29 + 16) = 0;
      *(_QWORD *)(v29 + 24) = 7;
      *(_WORD *)v29 = 0;
    }
    std::wstring::_Tidy_deallocate(pExceptionObject);
    if ( *(_QWORD *)(a3 + 16) )
    {
      if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::localizedNameString )
        v31 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::localizedNameString;
      else
        v31 = 0;
      v32 = *a1;
      v109 = v32;
      if ( v32 )
        (*((void (__fastcall **)(BSTR *))*v32 + 1))(v32);
      Uev::DomHelper::GetNode(&v110, &v109, v31, 0, v104);
      if ( v110 )
      {
        if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::nameString )
          v33 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::nameString;
        else
          LODWORD(v33) = 0;
        v111 = v110;
        (*((void (**)(void))*v110 + 1))();
        LocalizedValue = Uev::DomHelper::GetLocalizedValue(
                           (unsigned int)pExceptionObject,
                           (unsigned int)&v111,
                           v33,
                           a3,
                           v4 + 72);
        if ( v26 != (_OWORD *)LocalizedValue )
        {
          std::wstring::_Tidy_deallocate(v4 + 72);
          *v26 = *(_OWORD *)LocalizedValue;
          *(_OWORD *)(v4 + 88) = *(_OWORD *)(LocalizedValue + 16);
          *(_QWORD *)(LocalizedValue + 16) = 0;
          *(_QWORD *)(LocalizedValue + 24) = 7;
          *(_WORD *)LocalizedValue = 0;
        }
        std::wstring::_Tidy_deallocate(pExceptionObject);
      }
      if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::localizedDescriptionString )
        v35 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::localizedDescriptionString;
      else
        v35 = 0;
      v36 = *a1;
      v111 = v36;
      if ( v36 )
        (*((void (__fastcall **)(BSTR *))*v36 + 1))(v36);
      Uev::DomHelper::GetNode(v112, &v111, v35, 0, v105);
      v37 = v112[0];
      if ( v112[0] )
      {
        if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::descriptionString )
          v38 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::descriptionString;
        else
          LODWORD(v38) = 0;
        v109 = (BSTR *)v112[0];
        (*(void (**)(void))(*(_QWORD *)v112[0] + 8LL))();
        v39 = Uev::DomHelper::GetLocalizedValue((unsigned int)pExceptionObject, (unsigned int)&v109, v38, a3, v4 + 104);
        if ( v30 != (_OWORD *)v39 )
        {
          std::wstring::_Tidy_deallocate(v4 + 104);
          *v30 = *(_OWORD *)v39;
          *(_OWORD *)(v4 + 120) = *(_OWORD *)(v39 + 16);
          *(_QWORD *)(v39 + 16) = 0;
          *(_QWORD *)(v39 + 24) = 7;
          *(_WORD *)v39 = 0;
        }
        std::wstring::_Tidy_deallocate(pExceptionObject);
        v37 = v112[0];
      }
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      if ( v110 )
        (*((void (__fastcall **)(BSTR *))*v110 + 2))(v110);
    }
    if ( v13 )
      (*((void (__fastcall **)(BSTR *))*v13 + 2))(v13);
    v5 = a3;
  }
  if ( (a2 & 2) != 0 )
  {
    v40 = 0;
    if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::authorString )
      v41 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::authorString;
    else
      v41 = 0;
    v42 = *a1;
    v110 = v42;
    if ( v42 )
      (*((void (__fastcall **)(BSTR *))*v42 + 1))(v42);
    v43 = (BSTR **)Uev::DomHelper::GetNode(v112, &v110, v41, 0, v104);
    if ( *v43 )
    {
      v40 = *v43;
      (*((void (__fastcall **)(BSTR *))**v43 + 1))(*v43);
    }
    if ( v112[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v112[0] + 16LL))(v112[0]);
    if ( v40 )
    {
      v113 = 0;
      v114 = 0;
      v115 = 7;
      LOWORD(v113) = 0;
      v116 = 0;
      v117 = 0;
      v118 = 7;
      LOWORD(v116) = 0;
      v110 = v40;
      (*((void (__fastcall **)(BSTR *))*v40 + 1))(v40);
      Uev::TemplateAuthor::Parse<0>(&v113, &v110, v44, v45);
      std::wstring::operator=(v4 + 136, &v113);
      std::wstring::operator=(v4 + 168, &v116);
      std::wstring::_Tidy_deallocate(&v116);
      std::wstring::_Tidy_deallocate(&v113);
      (*((void (__fastcall **)(BSTR *))*v40 + 2))(v40);
    }
  }
  if ( (a2 & 0x1D) != 0 )
  {
    v46 = 0;
    if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::commonString )
      v47 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::commonString;
    else
      v47 = 0;
    v48 = *a1;
    v110 = v48;
    if ( v48 )
      (*((void (__fastcall **)(BSTR *))*v48 + 1))(v48);
    v49 = (BSTR **)Uev::DomHelper::GetNode(v112, &v110, v47, 0, v104);
    if ( *v49 )
    {
      v46 = *v49;
      (*((void (__fastcall **)(BSTR *))**v49 + 1))(*v49);
    }
    if ( v112[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v112[0] + 16LL))(v112[0]);
    Uev::TemplateData::TemplateData((Uev::TemplateData *)v120);
    if ( !v46 )
    {
      v50 = *a1;
      v110 = v50;
      if ( v50 )
        (*((void (__fastcall **)(BSTR *))*v50 + 1))(v50);
      Uev::ParseTemplate<0>(&v110, a2, v5, (__int64)v120);
      if ( *(_QWORD *)(v4 + 512) == *(_QWORD *)(v4 + 520) )
      {
        std::vector<Uev::TemplateData>::_Emplace_reallocate<Uev::TemplateData const &>(
          (const struct Uev::TemplateData **)(v4 + 504),
          *(const struct Uev::TemplateData **)(v4 + 512),
          (const struct Uev::TemplateData *)v120);
      }
      else
      {
        Uev::TemplateData::TemplateData(*(Uev::TemplateData **)(v4 + 512), (const struct Uev::TemplateData *)v120);
        *(_QWORD *)(v4 + 512) += 272LL;
      }
LABEL_156:
      Uev::TemplateData::~TemplateData((Uev::TemplateData *)v120);
      if ( v46 )
        (*((void (__fastcall **)(BSTR *))*v46 + 2))(v46);
      goto LABEL_158;
    }
    v110 = v46;
    (*((void (__fastcall **)(BSTR *))*v46 + 1))(v46);
    v51 = (_OWORD *)(v4 + 232);
    Uev::ParseTemplate<0>(&v110, a2, a3, v4 + 232);
    v54 = (__int64 *)(v4 + 40);
    v55 = *(_QWORD *)(v4 + 56);
    if ( v55 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( *(_QWORD *)(v4 + 64) <= 7u )
      v56 = v4 + 40;
    else
      v56 = *v54;
    std::wstring::wstring(pExceptionObject, v52, v53, v56, v55, L".", 1);
    v57 = std::operator+<wchar_t>((__int64)&v113, pExceptionObject);
    if ( v51 != (_OWORD *)v57 )
    {
      std::wstring::_Tidy_deallocate(v4 + 232);
      *v51 = *(_OWORD *)v57;
      *(_OWORD *)(v4 + 248) = *(_OWORD *)(v57 + 16);
      *(_QWORD *)(v57 + 16) = 0;
      *(_QWORD *)(v57 + 24) = 7;
      *(_WORD *)v57 = 0;
    }
    std::wstring::_Tidy_deallocate(&v113);
    std::wstring::_Tidy_deallocate(pExceptionObject);
    v109 = 0;
    v111 = 0;
    v58 = *a1;
    if ( *a1 )
    {
      v59 = (unsigned int (__fastcall *)(BSTR *, __int64, BSTR **))*((_QWORD *)*v58 + 36);
      v109 = 0;
      if ( `Uev::ParseTemplateSuiteDocument<0>'::`2'::applicationString )
        v60 = *`Uev::ParseTemplateSuiteDocument<0>'::`2'::applicationString;
      else
        v60 = 0;
      if ( v59(v58, v60, &v109) )
      {
        v63 = v111;
LABEL_152:
        if ( v63 )
          (*((void (__fastcall **)(BSTR *))*v63 + 2))(v63);
        if ( v109 )
          (*((void (__fastcall **)(BSTR *))*v109 + 2))(v109);
        goto LABEL_156;
      }
      v61 = v109;
      if ( v109 )
      {
        v62 = (void (__fastcall *)(BSTR *, BSTR **))*((_QWORD *)*v109 + 9);
        if ( v111 )
          (*((void (__fastcall **)(BSTR *))*v111 + 2))(v111);
        v111 = 0;
        v62(v61, &v111);
        while ( 1 )
        {
          v63 = v111;
          if ( !v111 )
            break;
          Uev::TemplateData::TemplateData((Uev::TemplateData *)v119);
          v110 = v111;
          if ( v111 )
            (*((void (__fastcall **)(BSTR *))*v111 + 1))(v111);
          Uev::ParseTemplate<0>(&v110, a2, a3, (__int64)v119);
          v66 = *(_QWORD *)(v4 + 56);
          if ( v66 == 0x7FFFFFFFFFFFFFFELL )
            std::_Xlen_string();
          if ( *(_QWORD *)(v4 + 64) <= 7u )
            v67 = v4 + 40;
          else
            v67 = *v54;
          std::wstring::wstring(pExceptionObject, v64, v65, v67, v66, L".", 1);
          v68 = std::operator+<wchar_t>((__int64)&v113, pExceptionObject);
          if ( v119 != (_OWORD *)v68 )
          {
            std::wstring::_Tidy_deallocate(v119);
            v119[0] = *(_OWORD *)v68;
            v119[1] = *(_OWORD *)(v68 + 16);
            *(_QWORD *)(v68 + 16) = 0;
            *(_QWORD *)(v68 + 24) = 7;
            *(_WORD *)v68 = 0;
          }
          std::wstring::_Tidy_deallocate(&v113);
          std::wstring::_Tidy_deallocate(pExceptionObject);
          if ( (unsigned __int8)Uev::TemplateSuiteData::FindId(v4, v119) )
          {
            std::string::string(&v113, "Application template section has the same ID as another section.");
            Uev::InvalidTemplateException::InvalidTemplateException(pExceptionObject, &v113);
            throw (Uev::InvalidTemplateException *)pExceptionObject;
          }
          if ( *(_QWORD *)(v4 + 512) == *(_QWORD *)(v4 + 520) )
          {
            std::vector<Uev::TemplateData>::_Emplace_reallocate<Uev::TemplateData const &>(
              (const struct Uev::TemplateData **)(v4 + 504),
              *(const struct Uev::TemplateData **)(v4 + 512),
              (const struct Uev::TemplateData *)v119);
          }
          else
          {
            Uev::TemplateData::TemplateData(*(Uev::TemplateData **)(v4 + 512), (const struct Uev::TemplateData *)v119);
            *(_QWORD *)(v4 + 512) += 272LL;
          }
          v69 = v109;
          if ( !v109 )
            _com_issue_error(-2147467261);
          v70 = (void (__fastcall *)(BSTR *, BSTR **))*((_QWORD *)*v109 + 9);
          if ( v111 )
            (*((void (__fastcall **)(BSTR *))*v111 + 2))(v111);
          v111 = 0;
          v70(v69, &v111);
          Uev::TemplateData::~TemplateData((Uev::TemplateData *)v119);
        }
        goto LABEL_152;
      }
    }
    _com_issue_error(-2147467261);
  }
LABEL_158:
  if ( *a1 )
    (*((void (__fastcall **)(BSTR *))**a1 + 2))(*a1);
}

```

## disassembly

```asm
0x140059a98  push    rbp
0x140059a9a  push    rbx
0x140059a9b  push    rsi
0x140059a9c  push    rdi
0x140059a9d  push    r12
0x140059a9f  push    r13
0x140059aa1  push    r14
0x140059aa3  push    r15
0x140059aa5  lea     rbp, [rsp-238h]
0x140059aad  sub     rsp, 338h
0x140059ab4  mov     rax, cs:__security_cookie
0x140059abb  xor     rax, rsp
0x140059abe  mov     [rbp+270h+var_50], rax
0x140059ac5  mov     r13, r9
0x140059ac8  mov     r14, r8
0x140059acb  mov     [rsp+370h+var_328], r8
0x140059ad0  mov     r12d, edx
0x140059ad3  mov     r15, rcx
0x140059ad6  mov     [rbp+270h+var_2E0], rcx
0x140059ada  mov     edi, 4
0x140059adf  mov     rax, gs:58h
0x140059ae8  mov     rbx, [rax]
0x140059aeb  mov     eax, [rdi+rbx]
0x140059aee  cmp     cs:?$TSS0@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059af4  jg      loc_14005A622
0x140059afa  mov     eax, [rdi+rbx]
0x140059afd  cmp     cs:?$TSS1@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b03  jg      loc_14005A6DD
0x140059b09  mov     eax, [rdi+rbx]
0x140059b0c  cmp     cs:?$TSS2@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b12  jg      loc_14005A798
0x140059b18  mov     eax, [rdi+rbx]
0x140059b1b  cmp     cs:?$TSS3@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b21  jg      loc_14005A853
0x140059b27  mov     eax, [rdi+rbx]
0x140059b2a  cmp     cs:?$TSS4@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b30  jg      loc_14005A90E
0x140059b36  mov     eax, [rdi+rbx]
0x140059b39  cmp     cs:?$TSS5@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b3f  jg      loc_14005A9C9
0x140059b45  mov     eax, [rdi+rbx]
0x140059b48  cmp     cs:?$TSS6@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b4e  jg      loc_14005AA84
0x140059b54  mov     eax, [rdi+rbx]
0x140059b57  cmp     cs:?$TSS7@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b5d  jg      loc_14005AB3F
0x140059b63  mov     eax, [rdi+rbx]
0x140059b66  cmp     cs:?$TSS8@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b6c  jg      loc_14005ABFA
0x140059b72  mov     eax, [rdi+rbx]
0x140059b75  cmp     cs:?$TSS9@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b7b  jg      loc_14005ACB5
0x140059b81  mov     eax, [rdi+rbx]
0x140059b84  cmp     cs:?$TSS10@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140059b8a  jg      loc_14005AD70
0x140059b90  mov     esi, 7
0x140059b95  test    r12b, 1
0x140059b99  jz      loc_14005A06B
0x140059b9f  mov     rax, cs:?idString@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::idString
0x140059ba6  test    rax, rax
0x140059ba9  jz      short loc_140059BB0
0x140059bab  mov     rbx, [rax]
0x140059bae  jmp     short loc_140059BB2
0x140059bb0  xor     ebx, ebx
0x140059bb2  mov     rcx, [r15]
0x140059bb5  mov     [rbp+270h+var_2D8], rcx
0x140059bb9  test    rcx, rcx
0x140059bbc  jz      short loc_140059BCB
0x140059bbe  mov     rax, [rcx]
0x140059bc1  mov     rax, [rax+8]
0x140059bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059bca  nop
0x140059bcb  mov     r9b, 1
0x140059bce  mov     r8, rbx
0x140059bd1  lea     rdx, [rbp+270h+var_2D8]
0x140059bd5  lea     rcx, [rsp+370h+pExceptionObject]
0x140059bda  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140059bdf  mov     rbx, rax
0x140059be2  lea     rdi, [r13+28h]
0x140059be6  cmp     rdi, rax
0x140059be9  jz      short loc_140059C12
0x140059beb  mov     rcx, rdi
0x140059bee  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140059bf3  movups  xmm0, xmmword ptr [rbx]
0x140059bf6  movups  xmmword ptr [rdi], xmm0
0x140059bf9  movups  xmm1, xmmword ptr [rbx+10h]
0x140059bfd  movups  xmmword ptr [rdi+10h], xmm1
0x140059c01  mov     qword ptr [rbx+10h], 0
0x140059c09  mov     [rbx+18h], rsi
0x140059c0d  xor     eax, eax
0x140059c0f  mov     [rbx], ax
0x140059c12  lea     rcx, [rsp+370h+pExceptionObject]
0x140059c17  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140059c1c  xor     ebx, ebx
0x140059c1e  mov     [rsp+370h+var_330], rbx
0x140059c23  mov     rax, cs:?fixedProfileString@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::fixedProfileString
0x140059c2a  test    rax, rax
0x140059c2d  jz      short loc_140059C34
0x140059c2f  mov     rdi, [rax]
0x140059c32  jmp     short loc_140059C36
0x140059c34  xor     edi, edi
0x140059c36  mov     rcx, [r15]
0x140059c39  mov     [rbp+270h+var_2D8], rcx
0x140059c3d  test    rcx, rcx
0x140059c40  jz      short loc_140059C4F
0x140059c42  mov     rax, [rcx]
0x140059c45  mov     rax, [rax+8]
0x140059c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059c4e  nop
0x140059c4f  xor     r9d, r9d
0x140059c52  mov     r8, rdi
0x140059c55  lea     rdx, [rbp+270h+var_2D8]
0x140059c59  lea     rcx, [rbp+270h+var_2D0]
0x140059c5d  call    ?GetNode@DomHelper@Uev@@SA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V3@PEA_W_N@Z; Uev::DomHelper::GetNode(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140059c62  mov     rcx, [rax]
0x140059c65  test    rcx, rcx
0x140059c68  jz      short loc_140059C7F
0x140059c6a  mov     rbx, rcx
0x140059c6d  mov     [rsp+370h+var_330], rcx
0x140059c72  mov     rax, [rcx]
0x140059c75  mov     rax, [rax+8]
0x140059c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059c7e  nop
0x140059c7f  mov     rcx, [rbp+270h+var_2D0]
0x140059c83  test    rcx, rcx
0x140059c86  jz      short loc_140059C95
0x140059c88  mov     rax, [rcx]
0x140059c8b  mov     rax, [rax+10h]
0x140059c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059c94  nop
0x140059c95  test    rbx, rbx
0x140059c98  jnz     short loc_140059CBE
0x140059c9a  lea     rax, [r13+0C8h]
0x140059ca1  cmp     [rax+18h], rsi
0x140059ca5  jbe     short loc_140059CAC
0x140059ca7  mov     rcx, [rax]
0x140059caa  jmp     short loc_140059CAF
0x140059cac  mov     rcx, rax
0x140059caf  mov     qword ptr [rax+10h], 0
0x140059cb7  xor     eax, eax
0x140059cb9  mov     [rcx], ax
0x140059cbc  jmp     short loc_140059D24
0x140059cbe  mov     [rbp+270h+var_2D8], rbx
0x140059cc2  mov     rax, [rbx]
0x140059cc5  mov     rcx, rbx
0x140059cc8  mov     rax, [rax+8]
0x140059ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059cd1  nop
0x140059cd2  lea     rdx, [rbp+270h+var_2D8]
0x140059cd6  lea     rcx, [rsp+370h+pExceptionObject]
0x140059cdb  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,bool)
0x140059ce0  mov     rdi, rax
0x140059ce3  lea     rsi, [r13+0C8h]
0x140059cea  cmp     rsi, rax
0x140059ced  jz      short loc_140059D1A
0x140059cef  mov     rcx, rsi
0x140059cf2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140059cf7  movups  xmm0, xmmword ptr [rdi]
0x140059cfa  movups  xmmword ptr [rsi], xmm0
0x140059cfd  movups  xmm1, xmmword ptr [rdi+10h]
0x140059d01  movups  xmmword ptr [rsi+10h], xmm1
0x140059d05  mov     qword ptr [rdi+10h], 0
0x140059d0d  mov     qword ptr [rdi+18h], 7
0x140059d15  xor     eax, eax
0x140059d17  mov     [rdi], ax
0x140059d1a  lea     rcx, [rsp+370h+pExceptionObject]
0x140059d1f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140059d24  bt      r12d, 0Ah
0x140059d29  jnb     short loc_140059D2F
0x140059d2b  xor     eax, eax
0x140059d2d  jmp     short loc_140059D6A
0x140059d2f  mov     rax, cs:?manageSuiteOnlyString@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::manageSuiteOnlyString
0x140059d36  test    rax, rax
0x140059d39  jz      short loc_140059D40
0x140059d3b  mov     rdi, [rax]
0x140059d3e  jmp     short loc_140059D42
0x140059d40  xor     edi, edi
0x140059d42  mov     rcx, [r15]
0x140059d45  mov     [rbp+270h+var_2D8], rcx
0x140059d49  test    rcx, rcx
0x140059d4c  jz      short loc_140059D5B
0x140059d4e  mov     rax, [rcx]
0x140059d51  mov     rax, [rax+8]
0x140059d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059d5a  nop
0x140059d5b  xor     r9d, r9d
0x140059d5e  mov     rdx, rdi
0x140059d61  lea     rcx, [rbp+270h+var_2D8]
0x140059d65  call    ?GetNodeBoolean@DomHelper@Uev@@SA_NV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N2@Z; Uev::DomHelper::GetNodeBoolean(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool,bool)
0x140059d6a  mov     [r13+1], al
0x140059d6e  mov     rax, cs:?nameString@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::nameString
0x140059d75  test    rax, rax
0x140059d78  jz      short loc_140059D7F
0x140059d7a  mov     rdi, [rax]
0x140059d7d  jmp     short loc_140059D81
0x140059d7f  xor     edi, edi
0x140059d81  mov     rcx, [r15]
0x140059d84  mov     [rbp+270h+var_2D8], rcx
0x140059d88  test    rcx, rcx
0x140059d8b  jz      short loc_140059D9A
0x140059d8d  mov     rax, [rcx]
0x140059d90  mov     rax, [rax+8]
0x140059d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059d99  nop
0x140059d9a  xor     r9d, r9d
0x140059d9d  mov     r8, rdi
0x140059da0  lea     rdx, [rbp+270h+var_2D8]
0x140059da4  lea     rcx, [rsp+370h+pExceptionObject]
0x140059da9  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140059dae  mov     rsi, rax
0x140059db1  lea     rdi, [r13+48h]
0x140059db5  cmp     rdi, rax
0x140059db8  jz      short loc_140059DE5
0x140059dba  mov     rcx, rdi
0x140059dbd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140059dc2  movups  xmm0, xmmword ptr [rsi]
0x140059dc5  movups  xmmword ptr [rdi], xmm0
0x140059dc8  movups  xmm1, xmmword ptr [rsi+10h]
0x140059dcc  movups  xmmword ptr [rdi+10h], xmm1
0x140059dd0  mov     qword ptr [rsi+10h], 0
0x140059dd8  mov     qword ptr [rsi+18h], 7
0x140059de0  xor     eax, eax
0x140059de2  mov     [rsi], ax
0x140059de5  lea     rcx, [rsp+370h+pExceptionObject]
0x140059dea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140059def  mov     rax, cs:?descriptionString@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::descriptionString
0x140059df6  test    rax, rax
0x140059df9  jz      short loc_140059E00
0x140059dfb  mov     rsi, [rax]
0x140059dfe  jmp     short loc_140059E02
0x140059e00  xor     esi, esi
0x140059e02  mov     rcx, [r15]
0x140059e05  mov     [rbp+270h+var_2D8], rcx
0x140059e09  test    rcx, rcx
0x140059e0c  jz      short loc_140059E1B
0x140059e0e  mov     rax, [rcx]
0x140059e11  mov     rax, [rax+8]
0x140059e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059e1a  nop
0x140059e1b  xor     r9d, r9d
0x140059e1e  mov     r8, rsi
0x140059e21  lea     rdx, [rbp+270h+var_2D8]
0x140059e25  lea     rcx, [rsp+370h+pExceptionObject]
0x140059e2a  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140059e2f  mov     rsi, rax
0x140059e32  lea     r14, [r13+68h]
0x140059e36  cmp     r14, rax
0x140059e39  jz      short loc_140059E68
0x140059e3b  mov     rcx, r14
0x140059e3e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140059e43  movups  xmm0, xmmword ptr [rsi]
0x140059e46  movups  xmmword ptr [r14], xmm0
0x140059e4a  movups  xmm1, xmmword ptr [rsi+10h]
0x140059e4e  movups  xmmword ptr [r14+10h], xmm1
0x140059e53  mov     qword ptr [rsi+10h], 0
0x140059e5b  mov     qword ptr [rsi+18h], 7
0x140059e63  xor     eax, eax
0x140059e65  mov     [rsi], ax
0x140059e68  lea     rcx, [rsp+370h+pExceptionObject]
0x140059e6d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140059e72  mov     rax, [rsp+370h+var_328]
0x140059e77  cmp     qword ptr [rax+10h], 0
0x140059e7c  jbe     loc_14005A04C
0x140059e82  mov     rax, cs:?localizedNameString@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::localizedNameString
0x140059e89  test    rax, rax
0x140059e8c  jz      short loc_140059E93
0x140059e8e  mov     rsi, [rax]
0x140059e91  jmp     short loc_140059E95
0x140059e93  xor     esi, esi
0x140059e95  mov     rcx, [r15]
0x140059e98  mov     [rbp+270h+var_2D8], rcx
0x140059e9c  test    rcx, rcx
0x140059e9f  jz      short loc_140059EAE
0x140059ea1  mov     rax, [rcx]
0x140059ea4  mov     rax, [rax+8]
0x140059ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059ead  nop
0x140059eae  xor     r9d, r9d
0x140059eb1  mov     r8, rsi
0x140059eb4  lea     rdx, [rbp+270h+var_2D8]
0x140059eb8  lea     rcx, [rbp+270h+var_2D0]
0x140059ebc  call    ?GetNode@DomHelper@Uev@@SA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V3@PEA_W_N@Z; Uev::DomHelper::GetNode(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140059ec1  nop
0x140059ec2  mov     rcx, [rbp+270h+var_2D0]
0x140059ec6  test    rcx, rcx
0x140059ec9  jz      loc_140059F50
0x140059ecf  mov     rax, cs:?nameString@?1???$ParseTemplateSuiteDocument@$0A@@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<0>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::nameString
0x140059ed6  test    rax, rax
0x140059ed9  jz      short loc_140059EE0
0x140059edb  mov     rsi, [rax]
0x140059ede  jmp     short loc_140059EE2
0x140059ee0  xor     esi, esi
0x140059ee2  mov     [rbp+270h+var_2C8], rcx
0x140059ee6  test    rcx, rcx
0x140059ee9  jz      short loc_140059EF8
0x140059eeb  mov     rax, [rcx]
0x140059eee  mov     rax, [rax+8]
0x140059ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059ef7  nop
0x140059ef8  mov     [rsp+370h+var_350], rdi
  ... truncated ...
```
