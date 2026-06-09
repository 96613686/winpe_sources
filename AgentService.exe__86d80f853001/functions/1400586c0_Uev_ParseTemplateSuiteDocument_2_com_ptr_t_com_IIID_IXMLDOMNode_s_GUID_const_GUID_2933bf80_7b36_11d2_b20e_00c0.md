# Uev::ParseTemplateSuiteDocument<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Uev::TemplateSuiteData &)

- ea: `0x1400586c0`
- end: `0x140059a90`
- name: `??$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@0@@Z`
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
- `0x14004c818`
- `0x140053048`
- `0x1400586c0`
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

- `OLEAUT32!__imp_SysAllocString` at `0x14005929e`
- `OLEAUT32!__imp_SysAllocString` at `0x140059359`
- `OLEAUT32!__imp_SysAllocString` at `0x140059414`
- `OLEAUT32!__imp_SysAllocString` at `0x1400594cf`
- `OLEAUT32!__imp_SysAllocString` at `0x14005958a`
- `OLEAUT32!__imp_SysAllocString` at `0x140059645`
- `OLEAUT32!__imp_SysAllocString` at `0x140059700`
- `OLEAUT32!__imp_SysAllocString` at `0x1400597bb`
- `OLEAUT32!__imp_SysAllocString` at `0x140059876`
- `OLEAUT32!__imp_SysAllocString` at `0x140059931`
- `OLEAUT32!__imp_SysAllocString` at `0x1400599ec`
- `OLEAUT32!__imp_SysAllocString` at `0x14005929e`
- `OLEAUT32!__imp_SysAllocString` at `0x140059359`
- `OLEAUT32!__imp_SysAllocString` at `0x140059414`
- `OLEAUT32!__imp_SysAllocString` at `0x1400594cf`
- `OLEAUT32!__imp_SysAllocString` at `0x14005958a`
- `OLEAUT32!__imp_SysAllocString` at `0x140059645`
- `OLEAUT32!__imp_SysAllocString` at `0x140059700`
- `OLEAUT32!__imp_SysAllocString` at `0x1400597bb`
- `OLEAUT32!__imp_SysAllocString` at `0x140059876`
- `OLEAUT32!__imp_SysAllocString` at `0x140059931`
- `OLEAUT32!__imp_SysAllocString` at `0x1400599ec`

## string_xrefs

- `0x14005986f`: `Common`
- `0x140059a5f`: `Application template section has the same ID as another section.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Uev::ParseTemplateSuiteDocument<2>(BSTR **a1, int a2, __int64 a3, __int64 a4)
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
  if ( __TSS0__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&__TSS0__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS0__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v71 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v72 = (BSTR *)operator new(0x18u);
      v72[1] = 0;
      *((_DWORD *)v72 + 4) = 1;
      v73 = SysAllocString(L"Name");
      *v72 = v73;
      if ( !v73 )
        _com_issue_error(-2147024882);
      v109 = v72;
      _bstr_t::operator+(v71, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::nameString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__nameString__);
      Init_thread_footer(&__TSS0__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS1__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS1__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS1__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v74 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v75 = (BSTR *)operator new(0x18u);
      v75[1] = 0;
      *((_DWORD *)v75 + 4) = 1;
      v76 = SysAllocString(L"Description");
      *v75 = v76;
      if ( !v76 )
        _com_issue_error(-2147024882);
      v109 = v75;
      _bstr_t::operator+(v74, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::descriptionString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__descriptionString__);
      Init_thread_footer(&__TSS1__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS2__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS2__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS2__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v77 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v78 = (BSTR *)operator new(0x18u);
      v78[1] = 0;
      *((_DWORD *)v78 + 4) = 1;
      v79 = SysAllocString(L"LocalizedNames");
      *v78 = v79;
      if ( !v79 )
        _com_issue_error(-2147024882);
      v109 = v78;
      _bstr_t::operator+(v77, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::localizedNameString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__localizedNameString__);
      Init_thread_footer(&__TSS2__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS3__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS3__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS3__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v80 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v81 = (BSTR *)operator new(0x18u);
      v81[1] = 0;
      *((_DWORD *)v81 + 4) = 1;
      v82 = SysAllocString(L"LocalizedDescriptions");
      *v81 = v82;
      if ( !v82 )
        _com_issue_error(-2147024882);
      v109 = v81;
      _bstr_t::operator+(v80, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::localizedDescriptionString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__localizedDescriptionString__);
      Init_thread_footer(&__TSS3__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS4__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS4__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS4__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v83 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v84 = (BSTR *)operator new(0x18u);
      v84[1] = 0;
      *((_DWORD *)v84 + 4) = 1;
      v85 = SysAllocString(L"ID");
      *v84 = v85;
      if ( !v85 )
        _com_issue_error(-2147024882);
      v109 = v84;
      _bstr_t::operator+(v83, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::idString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__idString__);
      Init_thread_footer(&__TSS4__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS5__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS5__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS5__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v86 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v87 = (BSTR *)operator new(0x18u);
      v87[1] = 0;
      *((_DWORD *)v87 + 4) = 1;
      v88 = SysAllocString(L"Author");
      *v87 = v88;
      if ( !v88 )
        _com_issue_error(-2147024882);
      v109 = v87;
      _bstr_t::operator+(v86, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::authorString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__authorString__);
      Init_thread_footer(&__TSS5__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS6__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS6__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS6__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v89 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v90 = (BSTR *)operator new(0x18u);
      v90[1] = 0;
      *((_DWORD *)v90 + 4) = 1;
      v91 = SysAllocString(L"FixedProfile");
      *v90 = v91;
      if ( !v91 )
        _com_issue_error(-2147024882);
      v109 = v90;
      _bstr_t::operator+(v89, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::fixedProfileString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__fixedProfileString__);
      Init_thread_footer(&__TSS6__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS7__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS7__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS7__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v92 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v93 = (BSTR *)operator new(0x18u);
      v93[1] = 0;
      *((_DWORD *)v93 + 4) = 1;
      v94 = SysAllocString(L"ManageSuiteOnly");
      *v93 = v94;
      if ( !v94 )
        _com_issue_error(-2147024882);
      v109 = v93;
      _bstr_t::operator+(v92, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::manageSuiteOnlyString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__manageSuiteOnlyString__);
      Init_thread_footer(&__TSS7__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS8__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS8__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS8__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v95 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v96 = (BSTR *)operator new(0x18u);
      v96[1] = 0;
      *((_DWORD *)v96 + 4) = 1;
      v97 = SysAllocString(L"Common");
      *v96 = v97;
      if ( !v97 )
        _com_issue_error(-2147024882);
      v109 = v96;
      _bstr_t::operator+(v95, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::commonString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__commonString__);
      Init_thread_footer(&__TSS8__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS9__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS9__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS9__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v98 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v99 = (BSTR *)operator new(0x18u);
      v99[1] = 0;
      *((_DWORD *)v99 + 4) = 1;
      v100 = SysAllocString(L"Application");
      *v99 = v100;
      if ( !v100 )
        _com_issue_error(-2147024882);
      v109 = v99;
      _bstr_t::operator+(v98, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::applicationString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__applicationString__);
      Init_thread_footer(&__TSS9__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( __TSS10__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS10__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    if ( __TSS10__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA == -1 )
    {
      v101 = _bstr_t::_bstr_t((_bstr_t *)&v110, off_1400CB300);
      v102 = (BSTR *)operator new(0x18u);
      v102[1] = 0;
      *((_DWORD *)v102 + 4) = 1;
      v103 = SysAllocString(L"CustomAction");
      *v102 = v103;
      if ( !v103 )
        _com_issue_error(-2147024882);
      v109 = v102;
      _bstr_t::operator+(v101, &`Uev::ParseTemplateSuiteDocument<2>'::`2'::customActionString, &v109);
      _bstr_t::_Free((_bstr_t *)&v109);
      _bstr_t::_Free((_bstr_t *)&v110);
      atexit(Uev::ParseTemplateSuiteDocument_2__::_2_::_dynamic_atexit_destructor_for__customActionString__);
      Init_thread_footer(&__TSS10__1____ParseTemplateSuiteDocument__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateSuiteData_1__Z_4HA);
    }
  }
  if ( (a2 & 1) != 0 )
  {
    if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::idString )
      v10 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::idString;
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
    if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::fixedProfileString )
      v14 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::fixedProfileString;
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
      if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::manageSuiteOnlyString )
        v21 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::manageSuiteOnlyString;
      else
        v21 = 0;
      v22 = *a1;
      v109 = v22;
      if ( v22 )
        (*((void (__fastcall **)(BSTR *))*v22 + 1))(v22);
      NodeBoolean = Uev::DomHelper::GetNodeBoolean(&v109, v21, v17, 0);
    }
    *(_BYTE *)(v4 + 1) = NodeBoolean;
    if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::nameString )
      v23 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::nameString;
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
    if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::descriptionString )
      v27 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::descriptionString;
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
      if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::localizedNameString )
        v31 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::localizedNameString;
      else
        v31 = 0;
      v32 = *a1;
      v109 = v32;
      if ( v32 )
        (*((void (__fastcall **)(BSTR *))*v32 + 1))(v32);
      Uev::DomHelper::GetNode(&v110, &v109, v31, 0, v104);
      if ( v110 )
      {
        if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::nameString )
          v33 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::nameString;
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
      if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::localizedDescriptionString )
        v35 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::localizedDescriptionString;
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
        if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::descriptionString )
          v38 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::descriptionString;
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
    if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::authorString )
      v41 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::authorString;
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
      Uev::TemplateAuthor::Parse<2>(&v113, &v110, v44, v45);
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
    if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::commonString )
      v47 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::commonString;
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
      Uev::ParseTemplate<2>(&v110, a2, v5, (__int64)v120);
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
    Uev::ParseTemplate<2>(&v110, a2, a3, v4 + 232);
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
      if ( `Uev::ParseTemplateSuiteDocument<2>'::`2'::applicationString )
        v60 = *`Uev::ParseTemplateSuiteDocument<2>'::`2'::applicationString;
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
          Uev::ParseTemplate<2>(&v110, a2, a3, (__int64)v119);
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
0x1400586c0  push    rbp
0x1400586c2  push    rbx
0x1400586c3  push    rsi
0x1400586c4  push    rdi
0x1400586c5  push    r12
0x1400586c7  push    r13
0x1400586c9  push    r14
0x1400586cb  push    r15
0x1400586cd  lea     rbp, [rsp-238h]
0x1400586d5  sub     rsp, 338h
0x1400586dc  mov     rax, cs:__security_cookie
0x1400586e3  xor     rax, rsp
0x1400586e6  mov     [rbp+270h+var_50], rax
0x1400586ed  mov     r13, r9
0x1400586f0  mov     r14, r8
0x1400586f3  mov     [rsp+370h+var_328], r8
0x1400586f8  mov     r12d, edx
0x1400586fb  mov     r15, rcx
0x1400586fe  mov     [rbp+270h+var_2E0], rcx
0x140058702  mov     edi, 4
0x140058707  mov     rax, gs:58h
0x140058710  mov     rbx, [rax]
0x140058713  mov     eax, [rdi+rbx]
0x140058716  cmp     cs:?$TSS0@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x14005871c  jg      loc_14005924A
0x140058722  mov     eax, [rdi+rbx]
0x140058725  cmp     cs:?$TSS1@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x14005872b  jg      loc_140059305
0x140058731  mov     eax, [rdi+rbx]
0x140058734  cmp     cs:?$TSS2@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x14005873a  jg      loc_1400593C0
0x140058740  mov     eax, [rdi+rbx]
0x140058743  cmp     cs:?$TSS3@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140058749  jg      loc_14005947B
0x14005874f  mov     eax, [rdi+rbx]
0x140058752  cmp     cs:?$TSS4@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140058758  jg      loc_140059536
0x14005875e  mov     eax, [rdi+rbx]
0x140058761  cmp     cs:?$TSS5@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140058767  jg      loc_1400595F1
0x14005876d  mov     eax, [rdi+rbx]
0x140058770  cmp     cs:?$TSS6@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140058776  jg      loc_1400596AC
0x14005877c  mov     eax, [rdi+rbx]
0x14005877f  cmp     cs:?$TSS7@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140058785  jg      loc_140059767
0x14005878b  mov     eax, [rdi+rbx]
0x14005878e  cmp     cs:?$TSS8@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x140058794  jg      loc_140059822
0x14005879a  mov     eax, [rdi+rbx]
0x14005879d  cmp     cs:?$TSS9@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x1400587a3  jg      loc_1400598DD
0x1400587a9  mov     eax, [rdi+rbx]
0x1400587ac  cmp     cs:?$TSS10@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4HA, eax
0x1400587b2  jg      loc_140059998
0x1400587b8  mov     esi, 7
0x1400587bd  test    r12b, 1
0x1400587c1  jz      loc_140058C93
0x1400587c7  mov     rax, cs:?idString@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::idString
0x1400587ce  test    rax, rax
0x1400587d1  jz      short loc_1400587D8
0x1400587d3  mov     rbx, [rax]
0x1400587d6  jmp     short loc_1400587DA
0x1400587d8  xor     ebx, ebx
0x1400587da  mov     rcx, [r15]
0x1400587dd  mov     [rbp+270h+var_2D8], rcx
0x1400587e1  test    rcx, rcx
0x1400587e4  jz      short loc_1400587F3
0x1400587e6  mov     rax, [rcx]
0x1400587e9  mov     rax, [rax+8]
0x1400587ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400587f2  nop
0x1400587f3  mov     r9b, 1
0x1400587f6  mov     r8, rbx
0x1400587f9  lea     rdx, [rbp+270h+var_2D8]
0x1400587fd  lea     rcx, [rsp+370h+pExceptionObject]
0x140058802  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140058807  mov     rbx, rax
0x14005880a  lea     rdi, [r13+28h]
0x14005880e  cmp     rdi, rax
0x140058811  jz      short loc_14005883A
0x140058813  mov     rcx, rdi
0x140058816  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005881b  movups  xmm0, xmmword ptr [rbx]
0x14005881e  movups  xmmword ptr [rdi], xmm0
0x140058821  movups  xmm1, xmmword ptr [rbx+10h]
0x140058825  movups  xmmword ptr [rdi+10h], xmm1
0x140058829  mov     qword ptr [rbx+10h], 0
0x140058831  mov     [rbx+18h], rsi
0x140058835  xor     eax, eax
0x140058837  mov     [rbx], ax
0x14005883a  lea     rcx, [rsp+370h+pExceptionObject]
0x14005883f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140058844  xor     ebx, ebx
0x140058846  mov     [rsp+370h+var_330], rbx
0x14005884b  mov     rax, cs:?fixedProfileString@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::fixedProfileString
0x140058852  test    rax, rax
0x140058855  jz      short loc_14005885C
0x140058857  mov     rdi, [rax]
0x14005885a  jmp     short loc_14005885E
0x14005885c  xor     edi, edi
0x14005885e  mov     rcx, [r15]
0x140058861  mov     [rbp+270h+var_2D8], rcx
0x140058865  test    rcx, rcx
0x140058868  jz      short loc_140058877
0x14005886a  mov     rax, [rcx]
0x14005886d  mov     rax, [rax+8]
0x140058871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058876  nop
0x140058877  xor     r9d, r9d
0x14005887a  mov     r8, rdi
0x14005887d  lea     rdx, [rbp+270h+var_2D8]
0x140058881  lea     rcx, [rbp+270h+var_2D0]
0x140058885  call    ?GetNode@DomHelper@Uev@@SA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V3@PEA_W_N@Z; Uev::DomHelper::GetNode(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x14005888a  mov     rcx, [rax]
0x14005888d  test    rcx, rcx
0x140058890  jz      short loc_1400588A7
0x140058892  mov     rbx, rcx
0x140058895  mov     [rsp+370h+var_330], rcx
0x14005889a  mov     rax, [rcx]
0x14005889d  mov     rax, [rax+8]
0x1400588a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400588a6  nop
0x1400588a7  mov     rcx, [rbp+270h+var_2D0]
0x1400588ab  test    rcx, rcx
0x1400588ae  jz      short loc_1400588BD
0x1400588b0  mov     rax, [rcx]
0x1400588b3  mov     rax, [rax+10h]
0x1400588b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400588bc  nop
0x1400588bd  test    rbx, rbx
0x1400588c0  jnz     short loc_1400588E6
0x1400588c2  lea     rax, [r13+0C8h]
0x1400588c9  cmp     [rax+18h], rsi
0x1400588cd  jbe     short loc_1400588D4
0x1400588cf  mov     rcx, [rax]
0x1400588d2  jmp     short loc_1400588D7
0x1400588d4  mov     rcx, rax
0x1400588d7  mov     qword ptr [rax+10h], 0
0x1400588df  xor     eax, eax
0x1400588e1  mov     [rcx], ax
0x1400588e4  jmp     short loc_14005894C
0x1400588e6  mov     [rbp+270h+var_2D8], rbx
0x1400588ea  mov     rax, [rbx]
0x1400588ed  mov     rcx, rbx
0x1400588f0  mov     rax, [rax+8]
0x1400588f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400588f9  nop
0x1400588fa  lea     rdx, [rbp+270h+var_2D8]
0x1400588fe  lea     rcx, [rsp+370h+pExceptionObject]
0x140058903  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,bool)
0x140058908  mov     rdi, rax
0x14005890b  lea     rsi, [r13+0C8h]
0x140058912  cmp     rsi, rax
0x140058915  jz      short loc_140058942
0x140058917  mov     rcx, rsi
0x14005891a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005891f  movups  xmm0, xmmword ptr [rdi]
0x140058922  movups  xmmword ptr [rsi], xmm0
0x140058925  movups  xmm1, xmmword ptr [rdi+10h]
0x140058929  movups  xmmword ptr [rsi+10h], xmm1
0x14005892d  mov     qword ptr [rdi+10h], 0
0x140058935  mov     qword ptr [rdi+18h], 7
0x14005893d  xor     eax, eax
0x14005893f  mov     [rdi], ax
0x140058942  lea     rcx, [rsp+370h+pExceptionObject]
0x140058947  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005894c  bt      r12d, 0Ah
0x140058951  jnb     short loc_140058957
0x140058953  xor     eax, eax
0x140058955  jmp     short loc_140058992
0x140058957  mov     rax, cs:?manageSuiteOnlyString@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::manageSuiteOnlyString
0x14005895e  test    rax, rax
0x140058961  jz      short loc_140058968
0x140058963  mov     rdi, [rax]
0x140058966  jmp     short loc_14005896A
0x140058968  xor     edi, edi
0x14005896a  mov     rcx, [r15]
0x14005896d  mov     [rbp+270h+var_2D8], rcx
0x140058971  test    rcx, rcx
0x140058974  jz      short loc_140058983
0x140058976  mov     rax, [rcx]
0x140058979  mov     rax, [rax+8]
0x14005897d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058982  nop
0x140058983  xor     r9d, r9d
0x140058986  mov     rdx, rdi
0x140058989  lea     rcx, [rbp+270h+var_2D8]
0x14005898d  call    ?GetNodeBoolean@DomHelper@Uev@@SA_NV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N2@Z; Uev::DomHelper::GetNodeBoolean(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool,bool)
0x140058992  mov     [r13+1], al
0x140058996  mov     rax, cs:?nameString@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::nameString
0x14005899d  test    rax, rax
0x1400589a0  jz      short loc_1400589A7
0x1400589a2  mov     rdi, [rax]
0x1400589a5  jmp     short loc_1400589A9
0x1400589a7  xor     edi, edi
0x1400589a9  mov     rcx, [r15]
0x1400589ac  mov     [rbp+270h+var_2D8], rcx
0x1400589b0  test    rcx, rcx
0x1400589b3  jz      short loc_1400589C2
0x1400589b5  mov     rax, [rcx]
0x1400589b8  mov     rax, [rax+8]
0x1400589bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400589c1  nop
0x1400589c2  xor     r9d, r9d
0x1400589c5  mov     r8, rdi
0x1400589c8  lea     rdx, [rbp+270h+var_2D8]
0x1400589cc  lea     rcx, [rsp+370h+pExceptionObject]
0x1400589d1  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x1400589d6  mov     rsi, rax
0x1400589d9  lea     rdi, [r13+48h]
0x1400589dd  cmp     rdi, rax
0x1400589e0  jz      short loc_140058A0D
0x1400589e2  mov     rcx, rdi
0x1400589e5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400589ea  movups  xmm0, xmmword ptr [rsi]
0x1400589ed  movups  xmmword ptr [rdi], xmm0
0x1400589f0  movups  xmm1, xmmword ptr [rsi+10h]
0x1400589f4  movups  xmmword ptr [rdi+10h], xmm1
0x1400589f8  mov     qword ptr [rsi+10h], 0
0x140058a00  mov     qword ptr [rsi+18h], 7
0x140058a08  xor     eax, eax
0x140058a0a  mov     [rsi], ax
0x140058a0d  lea     rcx, [rsp+370h+pExceptionObject]
0x140058a12  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140058a17  mov     rax, cs:?descriptionString@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::descriptionString
0x140058a1e  test    rax, rax
0x140058a21  jz      short loc_140058A28
0x140058a23  mov     rsi, [rax]
0x140058a26  jmp     short loc_140058A2A
0x140058a28  xor     esi, esi
0x140058a2a  mov     rcx, [r15]
0x140058a2d  mov     [rbp+270h+var_2D8], rcx
0x140058a31  test    rcx, rcx
0x140058a34  jz      short loc_140058A43
0x140058a36  mov     rax, [rcx]
0x140058a39  mov     rax, [rax+8]
0x140058a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058a42  nop
0x140058a43  xor     r9d, r9d
0x140058a46  mov     r8, rsi
0x140058a49  lea     rdx, [rbp+270h+var_2D8]
0x140058a4d  lea     rcx, [rsp+370h+pExceptionObject]
0x140058a52  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140058a57  mov     rsi, rax
0x140058a5a  lea     r14, [r13+68h]
0x140058a5e  cmp     r14, rax
0x140058a61  jz      short loc_140058A90
0x140058a63  mov     rcx, r14
0x140058a66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140058a6b  movups  xmm0, xmmword ptr [rsi]
0x140058a6e  movups  xmmword ptr [r14], xmm0
0x140058a72  movups  xmm1, xmmword ptr [rsi+10h]
0x140058a76  movups  xmmword ptr [r14+10h], xmm1
0x140058a7b  mov     qword ptr [rsi+10h], 0
0x140058a83  mov     qword ptr [rsi+18h], 7
0x140058a8b  xor     eax, eax
0x140058a8d  mov     [rsi], ax
0x140058a90  lea     rcx, [rsp+370h+pExceptionObject]
0x140058a95  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140058a9a  mov     rax, [rsp+370h+var_328]
0x140058a9f  cmp     qword ptr [rax+10h], 0
0x140058aa4  jbe     loc_140058C74
0x140058aaa  mov     rax, cs:?localizedNameString@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::localizedNameString
0x140058ab1  test    rax, rax
0x140058ab4  jz      short loc_140058ABB
0x140058ab6  mov     rsi, [rax]
0x140058ab9  jmp     short loc_140058ABD
0x140058abb  xor     esi, esi
0x140058abd  mov     rcx, [r15]
0x140058ac0  mov     [rbp+270h+var_2D8], rcx
0x140058ac4  test    rcx, rcx
0x140058ac7  jz      short loc_140058AD6
0x140058ac9  mov     rax, [rcx]
0x140058acc  mov     rax, [rax+8]
0x140058ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058ad5  nop
0x140058ad6  xor     r9d, r9d
0x140058ad9  mov     r8, rsi
0x140058adc  lea     rdx, [rbp+270h+var_2D8]
0x140058ae0  lea     rcx, [rbp+270h+var_2D0]
0x140058ae4  call    ?GetNode@DomHelper@Uev@@SA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V3@PEA_W_N@Z; Uev::DomHelper::GetNode(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140058ae9  nop
0x140058aea  mov     rcx, [rbp+270h+var_2D0]
0x140058aee  test    rcx, rcx
0x140058af1  jz      loc_140058B78
0x140058af7  mov     rax, cs:?nameString@?1???$ParseTemplateSuiteDocument@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplateSuiteDocument<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateSuiteData &)'::`2'::nameString
0x140058afe  test    rax, rax
0x140058b01  jz      short loc_140058B08
0x140058b03  mov     rsi, [rax]
0x140058b06  jmp     short loc_140058B0A
0x140058b08  xor     esi, esi
0x140058b0a  mov     [rbp+270h+var_2C8], rcx
0x140058b0e  test    rcx, rcx
0x140058b11  jz      short loc_140058B20
0x140058b13  mov     rax, [rcx]
0x140058b16  mov     rax, [rax+8]
0x140058b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058b1f  nop
0x140058b20  mov     [rsp+370h+var_350], rdi
  ... truncated ...
```
