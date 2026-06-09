# Uev::ParseTemplateSuiteDocument<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Uev::TemplateSuiteData &)

- ea: `0x1400572e8`
- end: `0x1400586b8`
- name: `??$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@0@@Z`
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
- `0x14004a18c`
- `0x140050ef8`
- `0x1400572e8`
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

- `OLEAUT32!__imp_SysAllocString` at `0x140057ec6`
- `OLEAUT32!__imp_SysAllocString` at `0x140057f81`
- `OLEAUT32!__imp_SysAllocString` at `0x14005803c`
- `OLEAUT32!__imp_SysAllocString` at `0x1400580f7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400581b2`
- `OLEAUT32!__imp_SysAllocString` at `0x14005826d`
- `OLEAUT32!__imp_SysAllocString` at `0x140058328`
- `OLEAUT32!__imp_SysAllocString` at `0x1400583e3`
- `OLEAUT32!__imp_SysAllocString` at `0x14005849e`
- `OLEAUT32!__imp_SysAllocString` at `0x140058559`
- `OLEAUT32!__imp_SysAllocString` at `0x140058614`
- `OLEAUT32!__imp_SysAllocString` at `0x140057ec6`
- `OLEAUT32!__imp_SysAllocString` at `0x140057f81`
- `OLEAUT32!__imp_SysAllocString` at `0x14005803c`
- `OLEAUT32!__imp_SysAllocString` at `0x1400580f7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400581b2`
- `OLEAUT32!__imp_SysAllocString` at `0x14005826d`
- `OLEAUT32!__imp_SysAllocString` at `0x140058328`
- `OLEAUT32!__imp_SysAllocString` at `0x1400583e3`
- `OLEAUT32!__imp_SysAllocString` at `0x14005849e`
- `OLEAUT32!__imp_SysAllocString` at `0x140058559`
- `OLEAUT32!__imp_SysAllocString` at `0x140058614`

## string_xrefs

- `0x140058497`: `Common`
- `0x140058687`: `Application template section has the same ID as another section.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Uev::ParseTemplateSuiteDocument<1>(BSTR **a1, int a2, __int64 a3, __int64 a4)
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
  if ( __TSS0__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&__TSS0__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS0__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v71 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v72 = (BSTR *)operator new(0x18u);
      v72[1] = 0;
      *((_DWORD *)v72 + 4) = 1;
      v73 = SysAllocString(L"Name");
      *v72 = v73;
      if ( !v73 )
        _com_issue_error(-2147024882);
      v109 = v72;
      _bstr_t::operator+(v71, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::nameString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__nameString__);
      Init_thread_footer(&__TSS0__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS1__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS1__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS1__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v74 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v75 = (BSTR *)operator new(0x18u);
      v75[1] = 0;
      *((_DWORD *)v75 + 4) = 1;
      v76 = SysAllocString(L"Description");
      *v75 = v76;
      if ( !v76 )
        _com_issue_error(-2147024882);
      v109 = v75;
      _bstr_t::operator+(v74, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::descriptionString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__descriptionString__);
      Init_thread_footer(&__TSS1__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS2__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS2__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS2__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v77 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v78 = (BSTR *)operator new(0x18u);
      v78[1] = 0;
      *((_DWORD *)v78 + 4) = 1;
      v79 = SysAllocString(L"LocalizedNames");
      *v78 = v79;
      if ( !v79 )
        _com_issue_error(-2147024882);
      v109 = v78;
      _bstr_t::operator+(v77, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::localizedNameString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__localizedNameString__);
      Init_thread_footer(&__TSS2__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS3__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS3__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS3__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v80 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v81 = (BSTR *)operator new(0x18u);
      v81[1] = 0;
      *((_DWORD *)v81 + 4) = 1;
      v82 = SysAllocString(L"LocalizedDescriptions");
      *v81 = v82;
      if ( !v82 )
        _com_issue_error(-2147024882);
      v109 = v81;
      _bstr_t::operator+(v80, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::localizedDescriptionString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__localizedDescriptionString__);
      Init_thread_footer(&__TSS3__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS4__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS4__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS4__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v83 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v84 = (BSTR *)operator new(0x18u);
      v84[1] = 0;
      *((_DWORD *)v84 + 4) = 1;
      v85 = SysAllocString(L"ID");
      *v84 = v85;
      if ( !v85 )
        _com_issue_error(-2147024882);
      v109 = v84;
      _bstr_t::operator+(v83, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::idString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__idString__);
      Init_thread_footer(&__TSS4__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS5__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS5__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS5__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v86 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v87 = (BSTR *)operator new(0x18u);
      v87[1] = 0;
      *((_DWORD *)v87 + 4) = 1;
      v88 = SysAllocString(L"Author");
      *v87 = v88;
      if ( !v88 )
        _com_issue_error(-2147024882);
      v109 = v87;
      _bstr_t::operator+(v86, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::authorString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__authorString__);
      Init_thread_footer(&__TSS5__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS6__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS6__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS6__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v89 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v90 = (BSTR *)operator new(0x18u);
      v90[1] = 0;
      *((_DWORD *)v90 + 4) = 1;
      v91 = SysAllocString(L"FixedProfile");
      *v90 = v91;
      if ( !v91 )
        _com_issue_error(-2147024882);
      v109 = v90;
      _bstr_t::operator+(v89, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::fixedProfileString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__fixedProfileString__);
      Init_thread_footer(&__TSS6__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS7__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS7__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS7__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v92 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v93 = (BSTR *)operator new(0x18u);
      v93[1] = 0;
      *((_DWORD *)v93 + 4) = 1;
      v94 = SysAllocString(L"ManageSuiteOnly");
      *v93 = v94;
      if ( !v94 )
        _com_issue_error(-2147024882);
      v109 = v93;
      _bstr_t::operator+(v92, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::manageSuiteOnlyString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__manageSuiteOnlyString__);
      Init_thread_footer(&__TSS7__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS8__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS8__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS8__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v95 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v96 = (BSTR *)operator new(0x18u);
      v96[1] = 0;
      *((_DWORD *)v96 + 4) = 1;
      v97 = SysAllocString(L"Common");
      *v96 = v97;
      if ( !v97 )
        _com_issue_error(-2147024882);
      v109 = v96;
      _bstr_t::operator+(v95, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::commonString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__commonString__);
      Init_thread_footer(&__TSS8__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS9__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS9__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS9__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v98 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v99 = (BSTR *)operator new(0x18u);
      v99[1] = 0;
      *((_DWORD *)v99 + 4) = 1;
      v100 = SysAllocString(L"Application");
      *v99 = v100;
      if ( !v100 )
        _com_issue_error(-2147024882);
      v109 = v99;
      _bstr_t::operator+(v98, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::applicationString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__applicationString__);
      Init_thread_footer(&__TSS9__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS10__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS10__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS10__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v101 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB2F8);
      v102 = (BSTR *)operator new(0x18u);
      v102[1] = 0;
      *((_DWORD *)v102 + 4) = 1;
      v103 = SysAllocString(L"CustomAction");
      *v102 = v103;
      if ( !v103 )
        _com_issue_error(-2147024882);
      v109 = v102;
      _bstr_t::operator+(v101, &`Uev::ParseTemplateSuiteDocument<1>'::`2'::customActionString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_1__::_2_::_dynamic_atexit_destructor_for__customActionString__);
      Init_thread_footer(&__TSS10__1____ParseTemplateSuiteDocument__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( (a2 & 1) != 0 )
  {
    if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::idString )
      v10 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::idString;
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
    if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::fixedProfileString )
      v14 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::fixedProfileString;
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
      if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::manageSuiteOnlyString )
        v21 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::manageSuiteOnlyString;
      else
        v21 = 0;
      v22 = *a1;
      v109 = v22;
      if ( v22 )
        (*((void (__fastcall **)(BSTR *))*v22 + 1))(v22);
      NodeBoolean = Uev::DomHelper::GetNodeBoolean(&v109, v21, v17, 0);
    }
    *(_BYTE *)(v4 + 1) = NodeBoolean;
    if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::nameString )
      v23 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::nameString;
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
    if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::descriptionString )
      v27 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::descriptionString;
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
      if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::localizedNameString )
        v31 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::localizedNameString;
      else
        v31 = 0;
      v32 = *a1;
      v109 = v32;
      if ( v32 )
        (*((void (__fastcall **)(BSTR *))*v32 + 1))(v32);
      Uev::DomHelper::GetNode(&v110, &v109, v31, 0, v104);
      if ( v110 )
      {
        if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::nameString )
          v33 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::nameString;
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
      if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::localizedDescriptionString )
        v35 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::localizedDescriptionString;
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
        if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::descriptionString )
          v38 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::descriptionString;
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
    if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::authorString )
      v41 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::authorString;
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
      Uev::TemplateAuthor::Parse<1>(&v113, &v110, v44, v45);
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
    if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::commonString )
      v47 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::commonString;
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
      Uev::ParseTemplate<1>(&v110, a2, v5, (__int64)v120);
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
    Uev::ParseTemplate<1>(&v110, a2, a3, v4 + 232);
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
      if ( `Uev::ParseTemplateSuiteDocument<1>'::`2'::applicationString )
        v60 = *`Uev::ParseTemplateSuiteDocument<1>'::`2'::applicationString;
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
          Uev::ParseTemplate<1>(&v110, a2, a3, (__int64)v119);
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
0x1400572e8  push    rbp
0x1400572ea  push    rbx
0x1400572eb  push    rsi
0x1400572ec  push    rdi
0x1400572ed  push    r12
0x1400572ef  push    r13
0x1400572f1  push    r14
0x1400572f3  push    r15
0x1400572f5  lea     rbp, [rsp-238h]
0x1400572fd  sub     rsp, 338h
0x140057304  mov     rax, cs:__security_cookie
0x14005730b  xor     rax, rsp
0x14005730e  mov     [rbp+270h+var_50], rax
0x140057315  mov     r13, r9
0x140057318  mov     r14, r8
0x14005731b  mov     [rsp+370h+var_328], r8
0x140057320  mov     r12d, edx
0x140057323  mov     r15, rcx
0x140057326  mov     [rbp+270h+var_2E0], rcx
0x14005732a  mov     edi, 4
0x14005732f  mov     rax, gs:58h
0x140057338  mov     rbx, [rax]
0x14005733b  mov     eax, [rdi+rbx]
0x14005733e  cmp     cs:?$TSS0@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140057344  jg      loc_140057E72
0x14005734a  mov     eax, [rdi+rbx]
0x14005734d  cmp     cs:?$TSS1@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140057353  jg      loc_140057F2D
0x140057359  mov     eax, [rdi+rbx]
0x14005735c  cmp     cs:?$TSS2@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140057362  jg      loc_140057FE8
0x140057368  mov     eax, [rdi+rbx]
0x14005736b  cmp     cs:?$TSS3@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140057371  jg      loc_1400580A3
0x140057377  mov     eax, [rdi+rbx]
0x14005737a  cmp     cs:?$TSS4@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140057380  jg      loc_14005815E
0x140057386  mov     eax, [rdi+rbx]
0x140057389  cmp     cs:?$TSS5@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x14005738f  jg      loc_140058219
0x140057395  mov     eax, [rdi+rbx]
0x140057398  cmp     cs:?$TSS6@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x14005739e  jg      loc_1400582D4
0x1400573a4  mov     eax, [rdi+rbx]
0x1400573a7  cmp     cs:?$TSS7@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x1400573ad  jg      loc_14005838F
0x1400573b3  mov     eax, [rdi+rbx]
0x1400573b6  cmp     cs:?$TSS8@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x1400573bc  jg      loc_14005844A
0x1400573c2  mov     eax, [rdi+rbx]
0x1400573c5  cmp     cs:?$TSS9@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x1400573cb  jg      loc_140058505
0x1400573d1  mov     eax, [rdi+rbx]
0x1400573d4  cmp     cs:?$TSS10@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x1400573da  jg      loc_1400585C0
0x1400573e0  mov     esi, 7
0x1400573e5  test    r12b, 1
0x1400573e9  jz      loc_1400578BB
0x1400573ef  mov     rax, cs:?idString@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::idString
0x1400573f6  test    rax, rax
0x1400573f9  jz      short loc_140057400
0x1400573fb  mov     rbx, [rax]
0x1400573fe  jmp     short loc_140057402
0x140057400  xor     ebx, ebx
0x140057402  mov     rcx, [r15]
0x140057405  mov     [rbp+270h+var_2D8], rcx
0x140057409  test    rcx, rcx
0x14005740c  jz      short loc_14005741B
0x14005740e  mov     rax, [rcx]
0x140057411  mov     rax, [rax+8]
0x140057415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005741a  nop
0x14005741b  mov     r9b, 1
0x14005741e  mov     r8, rbx
0x140057421  lea     rdx, [rbp+270h+var_2D8]
0x140057425  lea     rcx, [rsp+370h+pExceptionObject]
0x14005742a  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x14005742f  mov     rbx, rax
0x140057432  lea     rdi, [r13+28h]
0x140057436  cmp     rdi, rax
0x140057439  jz      short loc_140057462
0x14005743b  mov     rcx, rdi
0x14005743e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140057443  movups  xmm0, xmmword ptr [rbx]
0x140057446  movups  xmmword ptr [rdi], xmm0
0x140057449  movups  xmm1, xmmword ptr [rbx+10h]
0x14005744d  movups  xmmword ptr [rdi+10h], xmm1
0x140057451  mov     qword ptr [rbx+10h], 0
0x140057459  mov     [rbx+18h], rsi
0x14005745d  xor     eax, eax
0x14005745f  mov     [rbx], ax
0x140057462  lea     rcx, [rsp+370h+pExceptionObject]
0x140057467  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005746c  xor     ebx, ebx
0x14005746e  mov     [rsp+370h+var_330], rbx
0x140057473  mov     rax, cs:?fixedProfileString@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::fixedProfileString
0x14005747a  test    rax, rax
0x14005747d  jz      short loc_140057484
0x14005747f  mov     rdi, [rax]
0x140057482  jmp     short loc_140057486
0x140057484  xor     edi, edi
0x140057486  mov     rcx, [r15]
0x140057489  mov     [rbp+270h+var_2D8], rcx
0x14005748d  test    rcx, rcx
0x140057490  jz      short loc_14005749F
0x140057492  mov     rax, [rcx]
0x140057495  mov     rax, [rax+8]
0x140057499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005749e  nop
0x14005749f  xor     r9d, r9d
0x1400574a2  mov     r8, rdi
0x1400574a5  lea     rdx, [rbp+270h+var_2D8]
0x1400574a9  lea     rcx, [rbp+270h+var_2D0]
0x1400574ad  call    ?GetNode@DomHelper@Uev@@SA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V3@PEA_W_N@Z; Uev::DomHelper::GetNode(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x1400574b2  mov     rcx, [rax]
0x1400574b5  test    rcx, rcx
0x1400574b8  jz      short loc_1400574CF
0x1400574ba  mov     rbx, rcx
0x1400574bd  mov     [rsp+370h+var_330], rcx
0x1400574c2  mov     rax, [rcx]
0x1400574c5  mov     rax, [rax+8]
0x1400574c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400574ce  nop
0x1400574cf  mov     rcx, [rbp+270h+var_2D0]
0x1400574d3  test    rcx, rcx
0x1400574d6  jz      short loc_1400574E5
0x1400574d8  mov     rax, [rcx]
0x1400574db  mov     rax, [rax+10h]
0x1400574df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400574e4  nop
0x1400574e5  test    rbx, rbx
0x1400574e8  jnz     short loc_14005750E
0x1400574ea  lea     rax, [r13+0C8h]
0x1400574f1  cmp     [rax+18h], rsi
0x1400574f5  jbe     short loc_1400574FC
0x1400574f7  mov     rcx, [rax]
0x1400574fa  jmp     short loc_1400574FF
0x1400574fc  mov     rcx, rax
0x1400574ff  mov     qword ptr [rax+10h], 0
0x140057507  xor     eax, eax
0x140057509  mov     [rcx], ax
0x14005750c  jmp     short loc_140057574
0x14005750e  mov     [rbp+270h+var_2D8], rbx
0x140057512  mov     rax, [rbx]
0x140057515  mov     rcx, rbx
0x140057518  mov     rax, [rax+8]
0x14005751c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057521  nop
0x140057522  lea     rdx, [rbp+270h+var_2D8]
0x140057526  lea     rcx, [rsp+370h+pExceptionObject]
0x14005752b  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,bool)
0x140057530  mov     rdi, rax
0x140057533  lea     rsi, [r13+0C8h]
0x14005753a  cmp     rsi, rax
0x14005753d  jz      short loc_14005756A
0x14005753f  mov     rcx, rsi
0x140057542  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140057547  movups  xmm0, xmmword ptr [rdi]
0x14005754a  movups  xmmword ptr [rsi], xmm0
0x14005754d  movups  xmm1, xmmword ptr [rdi+10h]
0x140057551  movups  xmmword ptr [rsi+10h], xmm1
0x140057555  mov     qword ptr [rdi+10h], 0
0x14005755d  mov     qword ptr [rdi+18h], 7
0x140057565  xor     eax, eax
0x140057567  mov     [rdi], ax
0x14005756a  lea     rcx, [rsp+370h+pExceptionObject]
0x14005756f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140057574  bt      r12d, 0Ah
0x140057579  jnb     short loc_14005757F
0x14005757b  xor     eax, eax
0x14005757d  jmp     short loc_1400575BA
0x14005757f  mov     rax, cs:?manageSuiteOnlyString@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::manageSuiteOnlyString
0x140057586  test    rax, rax
0x140057589  jz      short loc_140057590
0x14005758b  mov     rdi, [rax]
0x14005758e  jmp     short loc_140057592
0x140057590  xor     edi, edi
0x140057592  mov     rcx, [r15]
0x140057595  mov     [rbp+270h+var_2D8], rcx
0x140057599  test    rcx, rcx
0x14005759c  jz      short loc_1400575AB
0x14005759e  mov     rax, [rcx]
0x1400575a1  mov     rax, [rax+8]
0x1400575a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400575aa  nop
0x1400575ab  xor     r9d, r9d
0x1400575ae  mov     rdx, rdi
0x1400575b1  lea     rcx, [rbp+270h+var_2D8]
0x1400575b5  call    ?GetNodeBoolean@DomHelper@Uev@@SA_NV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N2@Z; Uev::DomHelper::GetNodeBoolean(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool,bool)
0x1400575ba  mov     [r13+1], al
0x1400575be  mov     rax, cs:?nameString@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::nameString
0x1400575c5  test    rax, rax
0x1400575c8  jz      short loc_1400575CF
0x1400575ca  mov     rdi, [rax]
0x1400575cd  jmp     short loc_1400575D1
0x1400575cf  xor     edi, edi
0x1400575d1  mov     rcx, [r15]
0x1400575d4  mov     [rbp+270h+var_2D8], rcx
0x1400575d8  test    rcx, rcx
0x1400575db  jz      short loc_1400575EA
0x1400575dd  mov     rax, [rcx]
0x1400575e0  mov     rax, [rax+8]
0x1400575e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400575e9  nop
0x1400575ea  xor     r9d, r9d
0x1400575ed  mov     r8, rdi
0x1400575f0  lea     rdx, [rbp+270h+var_2D8]
0x1400575f4  lea     rcx, [rsp+370h+pExceptionObject]
0x1400575f9  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x1400575fe  mov     rsi, rax
0x140057601  lea     rdi, [r13+48h]
0x140057605  cmp     rdi, rax
0x140057608  jz      short loc_140057635
0x14005760a  mov     rcx, rdi
0x14005760d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140057612  movups  xmm0, xmmword ptr [rsi]
0x140057615  movups  xmmword ptr [rdi], xmm0
0x140057618  movups  xmm1, xmmword ptr [rsi+10h]
0x14005761c  movups  xmmword ptr [rdi+10h], xmm1
0x140057620  mov     qword ptr [rsi+10h], 0
0x140057628  mov     qword ptr [rsi+18h], 7
0x140057630  xor     eax, eax
0x140057632  mov     [rsi], ax
0x140057635  lea     rcx, [rsp+370h+pExceptionObject]
0x14005763a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005763f  mov     rax, cs:?descriptionString@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::descriptionString
0x140057646  test    rax, rax
0x140057649  jz      short loc_140057650
0x14005764b  mov     rsi, [rax]
0x14005764e  jmp     short loc_140057652
0x140057650  xor     esi, esi
0x140057652  mov     rcx, [r15]
0x140057655  mov     [rbp+270h+var_2D8], rcx
0x140057659  test    rcx, rcx
0x14005765c  jz      short loc_14005766B
0x14005765e  mov     rax, [rcx]
0x140057661  mov     rax, [rax+8]
0x140057665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005766a  nop
0x14005766b  xor     r9d, r9d
0x14005766e  mov     r8, rsi
0x140057671  lea     rdx, [rbp+270h+var_2D8]
0x140057675  lea     rcx, [rsp+370h+pExceptionObject]
0x14005767a  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x14005767f  mov     rsi, rax
0x140057682  lea     r14, [r13+68h]
0x140057686  cmp     r14, rax
0x140057689  jz      short loc_1400576B8
0x14005768b  mov     rcx, r14
0x14005768e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140057693  movups  xmm0, xmmword ptr [rsi]
0x140057696  movups  xmmword ptr [r14], xmm0
0x14005769a  movups  xmm1, xmmword ptr [rsi+10h]
0x14005769e  movups  xmmword ptr [r14+10h], xmm1
0x1400576a3  mov     qword ptr [rsi+10h], 0
0x1400576ab  mov     qword ptr [rsi+18h], 7
0x1400576b3  xor     eax, eax
0x1400576b5  mov     [rsi], ax
0x1400576b8  lea     rcx, [rsp+370h+pExceptionObject]
0x1400576bd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400576c2  mov     rax, [rsp+370h+var_328]
0x1400576c7  cmp     qword ptr [rax+10h], 0
0x1400576cc  jbe     loc_14005789C
0x1400576d2  mov     rax, cs:?localizedNameString@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::localizedNameString
0x1400576d9  test    rax, rax
0x1400576dc  jz      short loc_1400576E3
0x1400576de  mov     rsi, [rax]
0x1400576e1  jmp     short loc_1400576E5
0x1400576e3  xor     esi, esi
0x1400576e5  mov     rcx, [r15]
0x1400576e8  mov     [rbp+270h+var_2D8], rcx
0x1400576ec  test    rcx, rcx
0x1400576ef  jz      short loc_1400576FE
0x1400576f1  mov     rax, [rcx]
0x1400576f4  mov     rax, [rax+8]
0x1400576f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400576fd  nop
0x1400576fe  xor     r9d, r9d
0x140057701  mov     r8, rsi
0x140057704  lea     rdx, [rbp+270h+var_2D8]
0x140057708  lea     rcx, [rbp+270h+var_2D0]
0x14005770c  call    ?GetNode@DomHelper@Uev@@SA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V3@PEA_W_N@Z; Uev::DomHelper::GetNode(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140057711  nop
0x140057712  mov     rcx, [rbp+270h+var_2D0]
0x140057716  test    rcx, rcx
0x140057719  jz      loc_1400577A0
0x14005771f  mov     rax, cs:?nameString@?1???$ParseTemplateSuiteDocument@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::nameString
0x140057726  test    rax, rax
0x140057729  jz      short loc_140057730
0x14005772b  mov     rsi, [rax]
0x14005772e  jmp     short loc_140057732
0x140057730  xor     esi, esi
0x140057732  mov     [rbp+270h+var_2C8], rcx
0x140057736  test    rcx, rcx
0x140057739  jz      short loc_140057748
0x14005773b  mov     rax, [rcx]
0x14005773e  mov     rax, [rax+8]
0x140057742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057747  nop
0x140057748  mov     [rsp+370h+var_350], rdi
  ... truncated ...
```
