# Uev::ParseTemplate<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Uev::TemplateData &)

- ea: `0x140053048`
- end: `0x140055191`
- name: `??$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@0@@Z`
- size: `8521`
- prototype: `__int64 __fastcall(BSTR **, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400586c0`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x14000423c`
- `0x140004ab4`
- `0x14000aa1c`
- `0x14000aa84`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000d7b4`
- `0x14000e30c`
- `0x140013dc4`
- `0x14001a310`
- `0x1400255d0`
- `0x1400322b8`
- `0x140038a64`
- `0x14004ba24`
- `0x14004c1bc`
- `0x14004caf8`
- `0x140053048`
- `0x14005b080`
- `0x14005b35c`
- `0x14005b654`
- `0x14005e3b8`
- `0x14005f1a8`
- `0x14005f408`
- `0x14005f830`
- `0x14006059c`
- `0x140061150`
- `0x140061704`
- `0x1400617c4`
- `0x140061918`
- `0x140061a48`
- `0x140061c00`
- `0x140061d9c`
- `0x1400663e4`
- `0x140066868`
- `0x140067124`
- `0x140087a7c`
- `0x14009b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14005440c`
- `OLEAUT32!__imp_SysAllocString` at `0x1400544c9`
- `OLEAUT32!__imp_SysAllocString` at `0x140054586`
- `OLEAUT32!__imp_SysAllocString` at `0x140054643`
- `OLEAUT32!__imp_SysAllocString` at `0x140054700`
- `OLEAUT32!__imp_SysAllocString` at `0x1400547bd`
- `OLEAUT32!__imp_SysAllocString` at `0x14005487a`
- `OLEAUT32!__imp_SysAllocString` at `0x140054937`
- `OLEAUT32!__imp_SysAllocString` at `0x1400549f4`
- `OLEAUT32!__imp_SysAllocString` at `0x140054ab1`
- `OLEAUT32!__imp_SysAllocString` at `0x140054b6e`
- `OLEAUT32!__imp_SysAllocString` at `0x140054c2b`
- `OLEAUT32!__imp_SysAllocString` at `0x140054ce8`
- `OLEAUT32!__imp_SysAllocString` at `0x140054da5`
- `OLEAUT32!__imp_SysAllocString` at `0x140054e62`
- `OLEAUT32!__imp_SysAllocString` at `0x140054f1f`
- `OLEAUT32!__imp_SysAllocString` at `0x140054fdc`
- `OLEAUT32!__imp_SysAllocString` at `0x140055097`
- `OLEAUT32!__imp_SysAllocString` at `0x14005440c`
- `OLEAUT32!__imp_SysAllocString` at `0x1400544c9`
- `OLEAUT32!__imp_SysAllocString` at `0x140054586`
- `OLEAUT32!__imp_SysAllocString` at `0x140054643`
- `OLEAUT32!__imp_SysAllocString` at `0x140054700`
- `OLEAUT32!__imp_SysAllocString` at `0x1400547bd`
- `OLEAUT32!__imp_SysAllocString` at `0x14005487a`
- `OLEAUT32!__imp_SysAllocString` at `0x140054937`
- `OLEAUT32!__imp_SysAllocString` at `0x1400549f4`
- `OLEAUT32!__imp_SysAllocString` at `0x140054ab1`
- `OLEAUT32!__imp_SysAllocString` at `0x140054b6e`
- `OLEAUT32!__imp_SysAllocString` at `0x140054c2b`
- `OLEAUT32!__imp_SysAllocString` at `0x140054ce8`
- `OLEAUT32!__imp_SysAllocString` at `0x140054da5`
- `OLEAUT32!__imp_SysAllocString` at `0x140054e62`
- `OLEAUT32!__imp_SysAllocString` at `0x140054f1f`
- `OLEAUT32!__imp_SysAllocString` at `0x140054fdc`
- `OLEAUT32!__imp_SysAllocString` at `0x140055097`

## string_xrefs

- `0x1400547b6`: `ReplacedTemplates`
- `0x140054fd5`: `SystemParameter`
- `0x140054e5b`: `Registry`

## pseudocode

```c
__int64 __fastcall Uev::ParseTemplate<2>(BSTR **a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r15
  char v6; // r14
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v9; // rbx
  __int64 result; // rax
  __int64 v11; // rbx
  BSTR *v12; // rcx
  __int64 NodeText; // rbx
  BSTR **v14; // rdi
  __int64 v15; // rbx
  BSTR *v16; // rcx
  BSTR ***Node; // rax
  BSTR **v18; // rcx
  BSTR *v19; // rax
  BSTR v20; // rax
  void *NodeName; // rax
  unsigned __int64 v22; // rbx
  __int64 v23; // r9
  __int64 v24; // rax
  const wchar_t *v25; // rdx
  unsigned __int64 v26; // rsi
  const wchar_t *v27; // rcx
  size_t v28; // r8
  __int64 v29; // rax
  __int64 v30; // rdx
  BSTR *v31; // rbx
  void (__fastcall *v32)(BSTR *, BSTR **); // rsi
  __int64 v33; // rbx
  BSTR *v34; // rcx
  __int64 v35; // rbx
  BSTR *v36; // rcx
  __int64 v37; // rsi
  _OWORD *v38; // rbx
  __int64 v39; // rsi
  BSTR *v40; // rcx
  __int64 v41; // r14
  _OWORD *v42; // rsi
  __int64 v43; // r14
  BSTR *v44; // rcx
  __int64 LocalizedValue; // r14
  __int64 v46; // rbx
  BSTR *v47; // rcx
  BSTR *v48; // rcx
  __int64 v49; // rbx
  __int64 v50; // rbx
  __int64 v51; // rbx
  BSTR *v52; // rcx
  __int64 v53; // rbx
  BSTR *v54; // rcx
  BSTR *v55; // rcx
  BSTR *v56; // rbx
  __int64 v57; // rdi
  BSTR *v58; // rcx
  BSTR *v59; // rcx
  BSTR v60; // rax
  BSTR v61; // rax
  BSTR *v62; // rdi
  void (__fastcall *v63)(BSTR *, BSTR **); // rsi
  BSTR *v64; // rbx
  __int64 v65; // rdi
  BSTR *v66; // rcx
  BSTR *v67; // rcx
  __int64 v68; // rdi
  __int64 v69; // r8
  __int64 v70; // rdi
  __int64 v71; // r9
  __int64 v72; // r8
  __int64 v73; // rdi
  __int64 v74; // r8
  unsigned int (__fastcall *v75)(BSTR *, __int64, BSTR **); // r9
  __int64 v76; // rdx
  BSTR v77; // rax
  __int64 v78; // r8
  __int64 v79; // r9
  _QWORD *v80; // rsi
  BSTR *v81; // rdi
  void (__fastcall *v82)(BSTR *, BSTR **); // rsi
  unsigned int (__fastcall *v83)(BSTR *, __int64, BSTR **); // r9
  __int64 v84; // rdx
  BSTR v85; // rax
  __int64 v86; // r8
  __int64 v87; // r9
  Uev::TemplateSetting *v88; // rdi
  BSTR *v89; // rdi
  void (__fastcall *v90)(BSTR *, BSTR **); // rsi
  unsigned int (__fastcall *v91)(BSTR *, __int64, __int64 **); // r9
  __int64 v92; // rdx
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rdx
  _QWORD *v96; // rsi
  __int64 *v97; // rdi
  void (__fastcall *v98)(__int64 *, BSTR **); // rsi
  __int64 (__fastcall *v99)(BSTR *, __int64, BSTR **); // r9
  __int64 v100; // rdx
  BSTR v101; // rax
  __int64 v102; // rax
  BSTR *v103; // rdi
  void (__fastcall *v104)(BSTR *, BSTR **); // rsi
  _bstr_t *v105; // rsi
  BSTR *v106; // rdi
  BSTR v107; // rax
  _bstr_t *v108; // rsi
  BSTR *v109; // rdi
  BSTR v110; // rax
  _bstr_t *v111; // rsi
  BSTR *v112; // rdi
  BSTR v113; // rax
  _bstr_t *v114; // rsi
  BSTR *v115; // rdi
  BSTR v116; // rax
  _bstr_t *v117; // rsi
  BSTR *v118; // rdi
  BSTR v119; // rax
  _bstr_t *v120; // rsi
  BSTR *v121; // rdi
  BSTR v122; // rax
  _bstr_t *v123; // rsi
  BSTR *v124; // rdi
  BSTR v125; // rax
  _bstr_t *v126; // rsi
  BSTR *v127; // rdi
  BSTR v128; // rax
  _bstr_t *v129; // rsi
  BSTR *v130; // rdi
  BSTR v131; // rax
  _bstr_t *v132; // rsi
  BSTR *v133; // rdi
  BSTR v134; // rax
  _bstr_t *v135; // rsi
  BSTR *v136; // rdi
  BSTR v137; // rax
  _bstr_t *v138; // rsi
  BSTR *v139; // rdi
  BSTR v140; // rax
  _bstr_t *v141; // rsi
  BSTR *v142; // rdi
  BSTR v143; // rax
  _bstr_t *v144; // rsi
  BSTR *v145; // rdi
  BSTR v146; // rax
  _bstr_t *v147; // rsi
  BSTR *v148; // rdi
  BSTR v149; // rax
  _bstr_t *v150; // rsi
  BSTR *v151; // rdi
  BSTR v152; // rax
  _bstr_t *v153; // rsi
  BSTR *v154; // rdi
  BSTR v155; // rax
  _bstr_t *v156; // rdi
  BSTR *v157; // rbx
  BSTR v158; // rax
  __int64 v159; // [rsp+20h] [rbp-E0h]
  __int64 v160; // [rsp+20h] [rbp-E0h]
  __int64 v161; // [rsp+20h] [rbp-E0h]
  __int64 v162; // [rsp+20h] [rbp-E0h]
  BSTR *v163; // [rsp+30h] [rbp-D0h] BYREF
  BSTR **v164; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-C0h] BYREF
  BSTR **v166; // [rsp+80h] [rbp-80h]
  BSTR *v167; // [rsp+88h] [rbp-78h] BYREF
  BSTR *v168; // [rsp+90h] [rbp-70h] BYREF
  BSTR *v169; // [rsp+98h] [rbp-68h] BYREF
  BSTR *v170; // [rsp+A0h] [rbp-60h] BYREF
  BSTR *v171; // [rsp+A8h] [rbp-58h] BYREF
  BSTR *v172; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v173; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v174[24]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v175; // [rsp+D8h] [rbp-28h]
  __int64 v176; // [rsp+E0h] [rbp-20h]
  _BYTE v177[24]; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v178[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v179; // [rsp+120h] [rbp+20h]
  _BYTE v180[24]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v181; // [rsp+140h] [rbp+40h] BYREF
  __int64 v182; // [rsp+150h] [rbp+50h]
  __int128 v183; // [rsp+160h] [rbp+60h] BYREF
  __int64 v184; // [rsp+170h] [rbp+70h]
  __int64 v185; // [rsp+178h] [rbp+78h]
  __int16 v186; // [rsp+180h] [rbp+80h]
  wchar_t *S1[2]; // [rsp+188h] [rbp+88h] BYREF
  __int128 v188; // [rsp+198h] [rbp+98h]

  v4 = a4;
  v6 = a2;
  LODWORD(v173) = a2;
  v166 = a1;
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v9 = *ThreadLocalStoragePointer;
  if ( __TSS0__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&__TSS0__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS0__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v105 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v106 = (BSTR *)operator new(0x18u);
      v169 = v106;
      v106[1] = 0;
      *((_DWORD *)v106 + 4) = 1;
      v107 = SysAllocString(L"Name");
      *v106 = v107;
      if ( !v107 )
        _com_issue_error(-2147024882);
      v163 = v106;
      _bstr_t::operator+(v105, &`Uev::ParseTemplate<2>'::`2'::nameString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__nameString__);
      Init_thread_footer(&__TSS0__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS1__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS1__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS1__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v108 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v109 = (BSTR *)operator new(0x18u);
      v169 = v109;
      v109[1] = 0;
      *((_DWORD *)v109 + 4) = 1;
      v110 = SysAllocString(L"Description");
      *v109 = v110;
      if ( !v110 )
        _com_issue_error(-2147024882);
      v163 = v109;
      _bstr_t::operator+(v108, &`Uev::ParseTemplate<2>'::`2'::descriptionString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__descriptionString__);
      Init_thread_footer(&__TSS1__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS2__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS2__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS2__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v111 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v112 = (BSTR *)operator new(0x18u);
      v169 = v112;
      v112[1] = 0;
      *((_DWORD *)v112 + 4) = 1;
      v113 = SysAllocString(L"LocalizedNames");
      *v112 = v113;
      if ( !v113 )
        _com_issue_error(-2147024882);
      v163 = v112;
      _bstr_t::operator+(v111, &`Uev::ParseTemplate<2>'::`2'::localizedNameString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__localizedNameString__);
      Init_thread_footer(&__TSS2__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS3__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS3__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS3__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v114 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v115 = (BSTR *)operator new(0x18u);
      v169 = v115;
      v115[1] = 0;
      *((_DWORD *)v115 + 4) = 1;
      v116 = SysAllocString(L"LocalizedDescriptions");
      *v115 = v116;
      if ( !v116 )
        _com_issue_error(-2147024882);
      v163 = v115;
      _bstr_t::operator+(v114, &`Uev::ParseTemplate<2>'::`2'::localizedDescriptionString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__localizedDescriptionString__);
      Init_thread_footer(&__TSS3__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS4__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS4__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS4__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v117 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v118 = (BSTR *)operator new(0x18u);
      v169 = v118;
      v118[1] = 0;
      *((_DWORD *)v118 + 4) = 1;
      v119 = SysAllocString(L"ID");
      *v118 = v119;
      if ( !v119 )
        _com_issue_error(-2147024882);
      v163 = v118;
      _bstr_t::operator+(v117, &`Uev::ParseTemplate<2>'::`2'::idString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__idString__);
      Init_thread_footer(&__TSS4__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS5__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS5__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS5__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v120 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v121 = (BSTR *)operator new(0x18u);
      v169 = v121;
      v121[1] = 0;
      *((_DWORD *)v121 + 4) = 1;
      v122 = SysAllocString(L"ReplacedTemplates");
      *v121 = v122;
      if ( !v122 )
        _com_issue_error(-2147024882);
      v163 = v121;
      _bstr_t::operator+(v120, &`Uev::ParseTemplate<2>'::`2'::replacedTemplatesString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__replacedTemplatesString__);
      Init_thread_footer(&__TSS5__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS6__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS6__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS6__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v123 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v124 = (BSTR *)operator new(0x18u);
      v169 = v124;
      v124[1] = 0;
      *((_DWORD *)v124 + 4) = 1;
      v125 = SysAllocString(L"Version");
      *v124 = v125;
      if ( !v125 )
        _com_issue_error(-2147024882);
      v163 = v124;
      _bstr_t::operator+(v123, &`Uev::ParseTemplate<2>'::`2'::versionString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__versionString__);
      Init_thread_footer(&__TSS6__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS7__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS7__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS7__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v126 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v127 = (BSTR *)operator new(0x18u);
      v169 = v127;
      v127[1] = 0;
      *((_DWORD *)v127 + 4) = 1;
      v128 = SysAllocString(L"DeferToMSAccount");
      *v127 = v128;
      if ( !v128 )
        _com_issue_error(-2147024882);
      v163 = v127;
      _bstr_t::operator+(v126, &`Uev::ParseTemplate<2>'::`2'::deferToMSAccountString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__deferToMSAccountString__);
      Init_thread_footer(&__TSS7__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS8__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS8__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS8__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v129 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v130 = (BSTR *)operator new(0x18u);
      v169 = v130;
      v130[1] = 0;
      *((_DWORD *)v130 + 4) = 1;
      v131 = SysAllocString(L"DeferToOffice365");
      *v130 = v131;
      if ( !v131 )
        _com_issue_error(-2147024882);
      v163 = v130;
      _bstr_t::operator+(v129, &`Uev::ParseTemplate<2>'::`2'::deferToOffice365String, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__deferToOffice365String__);
      Init_thread_footer(&__TSS8__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS9__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS9__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS9__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v132 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v133 = (BSTR *)operator new(0x18u);
      v169 = v133;
      v133[1] = 0;
      *((_DWORD *)v133 + 4) = 1;
      v134 = SysAllocString(L"Asynchronous");
      *v133 = v134;
      if ( !v134 )
        _com_issue_error(-2147024882);
      v163 = v133;
      _bstr_t::operator+(v132, &`Uev::ParseTemplate<2>'::`2'::asyncString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__asyncString__);
      Init_thread_footer(&__TSS9__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS10__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS10__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS10__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v135 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v136 = (BSTR *)operator new(0x18u);
      v169 = v136;
      v136[1] = 0;
      *((_DWORD *)v136 + 4) = 1;
      v137 = SysAllocString(L"PreventOverlappingSynchronization");
      *v136 = v137;
      if ( !v137 )
        _com_issue_error(-2147024882);
      v163 = v136;
      _bstr_t::operator+(v135, &`Uev::ParseTemplate<2>'::`2'::preventOverlappingSynchronizationString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__preventOverlappingSynchronizationString__);
      Init_thread_footer(&__TSS10__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS11__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS11__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS11__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v138 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v139 = (BSTR *)operator new(0x18u);
      v169 = v139;
      v139[1] = 0;
      *((_DWORD *)v139 + 4) = 1;
      v140 = SysAllocString(L"AlwaysApplySettings");
      *v139 = v140;
      if ( !v140 )
        _com_issue_error(-2147024882);
      v163 = v139;
      _bstr_t::operator+(v138, &`Uev::ParseTemplate<2>'::`2'::alwaysApplySettingsString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__alwaysApplySettingsString__);
      Init_thread_footer(&__TSS11__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS12__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS12__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS12__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v141 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v142 = (BSTR *)operator new(0x18u);
      v169 = v142;
      v142[1] = 0;
      *((_DWORD *)v142 + 4) = 1;
      v143 = SysAllocString(L"Processes");
      *v142 = v143;
      if ( !v143 )
        _com_issue_error(-2147024882);
      v163 = v142;
      _bstr_t::operator+(v141, &`Uev::ParseTemplate<2>'::`2'::processesString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__processesString__);
      Init_thread_footer(&__TSS12__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS13__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS13__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS13__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v144 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v145 = (BSTR *)operator new(0x18u);
      v169 = v145;
      v145[1] = 0;
      *((_DWORD *)v145 + 4) = 1;
      v146 = SysAllocString(L"Settings");
      *v145 = v146;
      if ( !v146 )
        _com_issue_error(-2147024882);
      v163 = v145;
      _bstr_t::operator+(v144, &`Uev::ParseTemplate<2>'::`2'::settingsString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__settingsString__);
      Init_thread_footer(&__TSS13__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS14__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS14__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS14__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v147 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v148 = (BSTR *)operator new(0x18u);
      v169 = v148;
      v148[1] = 0;
      *((_DWORD *)v148 + 4) = 1;
      v149 = SysAllocString(L"Registry");
      *v148 = v149;
      if ( !v149 )
        _com_issue_error(-2147024882);
      v163 = v148;
      _bstr_t::operator+(v147, &`Uev::ParseTemplate<2>'::`2'::registryString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__registryString__);
      Init_thread_footer(&__TSS14__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS15__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS15__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS15__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v150 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v151 = (BSTR *)operator new(0x18u);
      v169 = v151;
      v151[1] = 0;
      *((_DWORD *)v151 + 4) = 1;
      v152 = SysAllocString(L"File");
      *v151 = v152;
      if ( !v152 )
        _com_issue_error(-2147024882);
      v163 = v151;
      _bstr_t::operator+(v150, &`Uev::ParseTemplate<2>'::`2'::fileString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__fileString__);
      Init_thread_footer(&__TSS15__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS16__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS16__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS16__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v153 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v154 = (BSTR *)operator new(0x18u);
      v169 = v154;
      v154[1] = 0;
      *((_DWORD *)v154 + 4) = 1;
      v155 = SysAllocString(L"SystemParameter");
      *v154 = v155;
      if ( !v155 )
        _com_issue_error(-2147024882);
      v163 = v154;
      _bstr_t::operator+(v153, &`Uev::ParseTemplate<2>'::`2'::systemParameterString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__systemParameterString__);
      Init_thread_footer(&__TSS16__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  result = *(unsigned int *)(v9 + 4);
  if ( __TSS17__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > (int)result )
  {
    result = Init_thread_header(&__TSS17__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS17__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v156 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB300);
      v157 = (BSTR *)operator new(0x18u);
      v169 = v157;
      v157[1] = 0;
      *((_DWORD *)v157 + 4) = 1;
      v158 = SysAllocString(L"CustomAction");
      *v157 = v158;
      if ( !v158 )
        _com_issue_error(-2147024882);
      v163 = v157;
      _bstr_t::operator+(v156, &`Uev::ParseTemplate<2>'::`2'::customActionString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_2__::_2_::_dynamic_atexit_destructor_for__customActionString__);
      result = Init_thread_footer(&__TSS17__1____ParseTemplate__01_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( (v6 & 1) != 0 )
  {
    if ( `Uev::ParseTemplate<2>'::`2'::idString )
      v11 = *`Uev::ParseTemplate<2>'::`2'::idString;
    else
      v11 = 0;
    v12 = *a1;
    v163 = v12;
    if ( v12 )
      (*((void (__fastcall **)(BSTR *))*v12 + 1))(v12);
    LOBYTE(a4) = 1;
    NodeText = Uev::DomHelper::GetNodeText(S1, &v163, v11, a4);
    if ( v4 != NodeText )
    {
      std::wstring::_Tidy_deallocate(v4);
      *(_OWORD *)v4 = *(_OWORD *)NodeText;
      *(_OWORD *)(v4 + 16) = *(_OWORD *)(NodeText + 16);
      *(_QWORD *)(NodeText + 16) = 0;
      *(_QWORD *)(NodeText + 24) = 7;
      *(_WORD *)NodeText = 0;
    }
    std::wstring::_Tidy_deallocate(S1);
    v14 = 0;
    v164 = 0;
    if ( `Uev::ParseTemplate<2>'::`2'::replacedTemplatesString )
      v15 = *`Uev::ParseTemplate<2>'::`2'::replacedTemplatesString;
    else
      v15 = 0;
    v16 = *a1;
    v163 = v16;
    if ( v16 )
      (*((void (__fastcall **)(BSTR *))*v16 + 1))(v16);
    Node = (BSTR ***)Uev::DomHelper::GetNode(&v170, &v163, v15, 0, v159);
    v18 = *Node;
    if ( *Node )
    {
      v14 = *Node;
      v164 = *Node;
      ((void (__fastcall *)(BSTR **))(*v18)[1])(v18);
    }
    if ( v170 )
      (*((void (__fastcall **)(BSTR *))*v170 + 2))(v170);
    if ( v14 )
    {
      v171 = 0;
      v19 = *v14;
      v171 = 0;
      if ( !((unsigned int (__fastcall *)(BSTR **, BSTR **))v19[12])(v14, &v171) )
      {
        v168 = 0;
        if ( !v171 )
          _com_issue_error(-2147467261);
        v20 = *v171;
        v168 = 0;
        (*((void (__fastcall **)(BSTR *, BSTR **))v20 + 9))(v171, &v168);
        while ( v168 )
        {
          v163 = v168;
          (*((void (__fastcall **)(BSTR *))*v168 + 1))(v168);
          NodeName = (void *)Uev::DomHelper::GetNodeName(&v183, &v163);
          v22 = -1;
          v23 = -1;
          do
            ++v23;
          while ( off_1400CB300[v23] );
          v24 = std::wstring::_Insert<wchar_t>(NodeName);
          *(_OWORD *)S1 = *(_OWORD *)v24;
          v188 = *(_OWORD *)(v24 + 16);
          *(_QWORD *)(v24 + 16) = 0;
          *(_QWORD *)(v24 + 24) = 7;
          *(_WORD *)v24 = 0;
          std::wstring::_Tidy_deallocate(&v183);
          if ( `Uev::ParseTemplate<2>'::`2'::idString )
            v25 = (const wchar_t *)*`Uev::ParseTemplate<2>'::`2'::idString;
          else
            v25 = 0;
          do
            ++v22;
          while ( v25[v22] );
          v26 = v188;
          v27 = (const wchar_t *)S1;
          if ( *((_QWORD *)&v188 + 1) > 7u )
            v27 = S1[0];
          v28 = v188;
          if ( v22 < (unsigned __int64)v188 )
            v28 = v22;
          if ( wmemcmp(v27, v25, v28) || v26 < v22 || v26 > v22 )
          {
            Uev::InvalidXmlException::InvalidXmlException((Uev::InvalidXmlException *)pExceptionObject);
            throw (Uev::InvalidXmlException *)pExceptionObject;
          }
          v170 = v168;
          if ( v168 )
            (*((void (__fastcall **)(BSTR *))*v168 + 1))(v168);
          v29 = Uev::DomHelper::GetNodeText(pExceptionObject, &v170);
          v30 = *(_QWORD *)(v4 + 40);
          if ( v30 == *(_QWORD *)(v4 + 48) )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v4 + 32, v30, v29);
          }
          else
          {
            *(_OWORD *)v30 = 0;
            *(_QWORD *)(v30 + 16) = 0;
            *(_QWORD *)(v30 + 24) = 0;
            *(_OWORD *)v30 = *(_OWORD *)v29;
            *(_OWORD *)(v30 + 16) = *(_OWORD *)(v29 + 16);
            *(_QWORD *)(v29 + 16) = 0;
            *(_QWORD *)(v29 + 24) = 7;
            *(_WORD *)v29 = 0;
            *(_QWORD *)(v4 + 40) += 32LL;
          }
          std::wstring::_Tidy_deallocate(pExceptionObject);
          v31 = v171;
          if ( !v171 )
            _com_issue_error(-2147467261);
          v32 = (void (__fastcall *)(BSTR *, BSTR **))*((_QWORD *)*v171 + 9);
          if ( v168 )
            (*((void (__fastcall **)(BSTR *))*v168 + 2))(v168);
          v168 = 0;
          v32(v31, &v168);
          std::wstring::_Tidy_deallocate(S1);
        }
      }
      if ( v171 )
        (*((void (__fastcall **)(BSTR *))*v171 + 2))(v171);
    }
    if ( `Uev::ParseTemplate<2>'::`2'::versionString )
      v33 = *`Uev::ParseTemplate<2>'::`2'::versionString;
    else
      v33 = 0;
    v34 = *a1;
    v163 = v34;
    if ( v34 )
      (*((void (__fastcall **)(BSTR *))*v34 + 1))(v34);
    *(_DWORD *)(v4 + 120) = Uev::DomHelper::GetNodeNumber(&v163, v33);
    if ( `Uev::ParseTemplate<2>'::`2'::nameString )
      v35 = *`Uev::ParseTemplate<2>'::`2'::nameString;
    else
      v35 = 0;
    v36 = *a1;
    v163 = v36;
    if ( v36 )
      (*((void (__fastcall **)(BSTR *))*v36 + 1))(v36);
    v37 = Uev::DomHelper::GetNodeText(pExceptionObject, &v163, v35, 0);
    v38 = (_OWORD *)(v4 + 56);
    if ( v4 + 56 != v37 )
    {
      std::wstring::_Tidy_deallocate(v4 + 56);
      *v38 = *(_OWORD *)v37;
      *(_OWORD *)(v4 + 72) = *(_OWORD *)(v37 + 16);
      *(_QWORD *)(v37 + 16) = 0;
      *(_QWORD *)(v37 + 24) = 7;
      *(_WORD *)v37 = 0;
    }
    std::wstring::_Tidy_deallocate(pExceptionObject);
    if ( `Uev::ParseTemplate<2>'::`2'::descriptionString )
      v39 = *`Uev::ParseTemplate<2>'::`2'::descriptionString;
    else
      v39 = 0;
    v40 = *a1;
    v163 = v40;
    if ( v40 )
      (*((void (__fastcall **)(BSTR *))*v40 + 1))(v40);
    v41 = Uev::DomHelper::GetNodeText(pExceptionObject, &v163, v39, 0);
    v42 = (_OWORD *)(v4 + 88);
    if ( v4 + 88 != v41 )
    {
      std::wstring::_Tidy_deallocate(v4 + 88);
      *v42 = *(_OWORD *)v41;
      *(_OWORD *)(v4 + 104) = *(_OWORD *)(v41 + 16);
      *(_QWORD *)(v41 + 16) = 0;
      *(_QWORD *)(v41 + 24) = 7;
      *(_WORD *)v41 = 0;
    }
    std::wstring::_Tidy_deallocate(pExceptionObject);
    if ( *(_QWORD *)(a3 + 16) )
    {
      if ( `Uev::ParseTemplate<2>'::`2'::localizedNameString )
        v43 = *`Uev::ParseTemplate<2>'::`2'::localizedNameString;
      else
        v43 = 0;
      v44 = *a1;
      v163 = v44;
      if ( v44 )
        (*((void (__fastcall **)(BSTR *))*v44 + 1))(v44);
      Uev::DomHelper::GetNode(&v171, &v163, v43, 0, v160);
      LODWORD(v43) = 0;
      if ( v171 )
      {
        if ( `Uev::ParseTemplate<2>'::`2'::nameString )
          v43 = *`Uev::ParseTemplate<2>'::`2'::nameString;
        v170 = v171;
        (*((void (**)(void))*v171 + 1))();
        LocalizedValue = Uev::DomHelper::GetLocalizedValue(
                           (unsigned int)pExceptionObject,
                           (unsigned int)&v170,
                           v43,
                           a3,
                           v4 + 56);
        if ( v38 != (_OWORD *)LocalizedValue )
        {
          std::wstring::_Tidy_deallocate(v4 + 56);
          *v38 = *(_OWORD *)LocalizedValue;
          *(_OWORD *)(v4 + 72) = *(_OWORD *)(LocalizedValue + 16);
          *(_QWORD *)(LocalizedValue + 16) = 0;
          *(_QWORD *)(LocalizedValue + 24) = 7;
          *(_WORD *)LocalizedValue = 0;
        }
        std::wstring::_Tidy_deallocate(pExceptionObject);
      }
      if ( `Uev::ParseTemplate<2>'::`2'::localizedDescriptionString )
        v46 = *`Uev::ParseTemplate<2>'::`2'::localizedDescriptionString;
      else
        v46 = 0;
      v47 = *a1;
      v170 = v47;
      if ( v47 )
        (*((void (__fastcall **)(BSTR *))*v47 + 1))(v47);
      Uev::DomHelper::GetNode(&v172, &v170, v46, 0, v161);
      v48 = v172;
      if ( v172 )
      {
        if ( `Uev::ParseTemplate<2>'::`2'::descriptionString )
          v49 = *`Uev::ParseTemplate<2>'::`2'::descriptionString;
        else
          LODWORD(v49) = 0;
        v163 = v172;
        (*((void (**)(void))*v172 + 1))();
        v50 = Uev::DomHelper::GetLocalizedValue((unsigned int)pExceptionObject, (unsigned int)&v163, v49, a3, v4 + 88);
        if ( v42 != (_OWORD *)v50 )
        {
          std::wstring::_Tidy_deallocate(v4 + 88);
          *v42 = *(_OWORD *)v50;
          *(_OWORD *)(v4 + 104) = *(_OWORD *)(v50 + 16);
          *(_QWORD *)(v50 + 16) = 0;
          *(_QWORD *)(v50 + 24) = 7;
          *(_WORD *)v50 = 0;
        }
        std::wstring::_Tidy_deallocate(pExceptionObject);
        v48 = v172;
      }
      if ( v48 )
        (*((void (__fastcall **)(BSTR *))*v48 + 2))(v48);
      if ( v171 )
        (*((void (__fastcall **)(BSTR *))*v171 + 2))(v171);
    }
    if ( `Uev::ParseTemplate<2>'::`2'::deferToMSAccountString )
      v51 = *`Uev::ParseTemplate<2>'::`2'::deferToMSAccountString;
    else
      v51 = 0;
    v52 = *a1;
    v163 = v52;
    if ( v52 )
      (*((void (__fastcall **)(BSTR *))*v52 + 1))(v52);
    Uev::DomHelper::GetNode(&v167, &v163, v51, 0, v160);
    if ( v167 )
      *(_BYTE *)(v4 + 124) = 1;
    if ( `Uev::ParseTemplate<2>'::`2'::deferToOffice365String )
      v53 = *`Uev::ParseTemplate<2>'::`2'::deferToOffice365String;
    else
      v53 = 0;
    v54 = *a1;
    v170 = v54;
    if ( v54 )
      (*((void (__fastcall **)(BSTR *))*v54 + 1))(v54);
    result = Uev::DomHelper::GetNode(&v169, &v170, v53, 0, v162);
    v55 = v169;
    if ( v169 )
      *(_BYTE *)(v4 + 125) = 1;
    if ( v55 )
      result = (*((__int64 (__fastcall **)(BSTR *))*v55 + 2))(v55);
    if ( v167 )
      result = (*((__int64 (__fastcall **)(BSTR *))*v167 + 2))(v167);
    if ( v14 )
      result = ((__int64 (__fastcall *)(BSTR **))(*v14)[2])(v14);
    v6 = (char)v173;
  }
  if ( (v6 & 4) != 0 )
  {
    v56 = 0;
    v169 = 0;
    if ( `Uev::ParseTemplate<2>'::`2'::processesString )
      v57 = *`Uev::ParseTemplate<2>'::`2'::processesString;
    else
      v57 = 0;
    v58 = *a1;
    v167 = v58;
    if ( v58 )
      (*((void (__fastcall **)(BSTR *))*v58 + 1))(v58);
    LOBYTE(a4) = 1;
    result = Uev::DomHelper::GetNode(&v164, &v167, v57, a4, v159);
    v59 = *(BSTR **)result;
    if ( *(_QWORD *)result )
    {
      v56 = *(BSTR **)result;
      v169 = *(BSTR **)result;
      result = (*((__int64 (__fastcall **)(BSTR *))*v59 + 1))(v59);
    }
    if ( v164 )
      result = ((__int64 (__fastcall *)(BSTR **))(*v164)[2])(v164);
    if ( v56 )
    {
      v171 = 0;
      v60 = *v56;
      v171 = 0;
      result = (*((__int64 (__fastcall **)(BSTR *, BSTR **))v60 + 12))(v56, &v171);
      if ( !(_DWORD)result )
      {
        v168 = 0;
        if ( !v171 )
          _com_issue_error(-2147467261);
        v61 = *v171;
        v168 = 0;
        result = (*((__int64 (__fastcall **)(BSTR *, BSTR **))v61 + 9))(v171, &v168);
        while ( v168 )
        {
          memset(v174, 0, sizeof(v174));
          v175 = 7;
          *(_WORD *)v174 = 0;
          memset(v177, 0, sizeof(v177));
          *(_QWORD *)&v178[0] = 7;
          *(_WORD *)v177 = 0;
          memset((char *)v178 + 8, 0, 24);
          v179 = 7;
          WORD4(v178[0]) = 0;
          memset(v180, 0, sizeof(v180));
          v181 = 0;
          v182 = 0;
          v167 = v168;
          (*((void (__fastcall **)(BSTR *))*v168 + 1))(v168);
          Uev::TemplateProcess::Parse<2>((__int64)v174, &v167);
          std::vector<Uev::TemplateProcess>::push_back(v4 + 136, v174);
          v62 = v171;
          if ( !v171 )
            _com_issue_error(-2147467261);
          v63 = (void (__fastcall *)(BSTR *, BSTR **))*((_QWORD *)*v171 + 9);
          if ( v168 )
            (*((void (__fastcall **)(BSTR *))*v168 + 2))(v168);
          v168 = 0;
          v63(v62, &v168);
          std::vector<Uev::VersionElement>::~vector<Uev::VersionElement>(&v181);
          std::vector<Uev::VersionElement>::~vector<Uev::VersionElement>(v180);
          std::wstring::_Tidy_deallocate((char *)v178 + 8);
          std::wstring::_Tidy_deallocate(v177);
          result = std::wstring::_Tidy_deallocate(v174);
        }
      }
      if ( v171 )
        result = (*((__int64 (__fastcall **)(BSTR *))*v171 + 2))(v171);
    }
    if ( v56 )
      result = (*((__int64 (__fastcall **)(BSTR *))*v56 + 2))(v56);
  }
  if ( (v6 & 8) != 0 )
  {
    v64 = 0;
    v169 = 0;
    if ( `Uev::ParseTemplate<2>'::`2'::settingsString )
      v65 = *`Uev::ParseTemplate<2>'::`2'::settingsString;
    else
      v65 = 0;
    v66 = *a1;
    v167 = v66;
    if ( v66 )
      (*((void (__fastcall **)(BSTR *))*v66 + 1))(v66);
    LOBYTE(a4) = 1;
    result = Uev::DomHelper::GetNode(&v164, &v167, v65, a4, v159);
    v67 = *(BSTR **)result;
    if ( *(_QWORD *)result )
    {
      v64 = *(BSTR **)result;
      v169 = *(BSTR **)result;
      result = (*((__int64 (__fastcall **)(BSTR *))*v67 + 1))(v67);
    }
    if ( v164 )
      result = ((__int64 (__fastcall *)(BSTR **))(*v164)[2])(v164);
    if ( v64 )
    {
      if ( `Uev::ParseTemplate<2>'::`2'::asyncString )
        v68 = *`Uev::ParseTemplate<2>'::`2'::asyncString;
      else
        v68 = 0;
      v167 = v64;
      (*((void (__fastcall **)(BSTR *))*v64 + 1))(v64);
      *(_BYTE *)(v4 + 126) = Uev::DomHelper::GetNodeBoolean(&v167, v68, v69, 0);
      if ( `Uev::ParseTemplate<2>'::`2'::preventOverlappingSynchronizationString )
        v70 = *`Uev::ParseTemplate<2>'::`2'::preventOverlappingSynchronizationString;
      else
        v70 = 0;
      v167 = v64;
      (*((void (__fastcall **)(BSTR *))*v64 + 1))(v64);
      LOBYTE(v71) = 1;
      *(_BYTE *)(v4 + 127) = Uev::DomHelper::GetNodeBoolean(&v167, v70, v72, v71);
      if ( `Uev::ParseTemplate<2>'::`2'::alwaysApplySettingsString )
        v73 = *`Uev::ParseTemplate<2>'::`2'::alwaysApplySettingsString;
      else
        v73 = 0;
      v167 = v64;
      (*((void (__fastcall **)(BSTR *))*v64 + 1))(v64);
      *(_BYTE *)(v4 + 128) = Uev::DomHelper::GetNodeBoolean(&v167, v73, v74, 0);
      v170 = 0;
      v75 = (unsigned int (__fastcall *)(BSTR *, __int64, BSTR **))*((_QWORD *)*v64 + 36);
      v170 = 0;
      if ( `Uev::ParseTemplate<2>'::`2'::registryString )
        v76 = *`Uev::ParseTemplate<2>'::`2'::registryString;
      else
        v76 = 0;
      if ( !v75(v64, v76, &v170) )
      {
        v168 = 0;
        if ( !v170 )
          _com_issue_error(-2147467261);
        v77 = *v170;
        v168 = 0;
        (*((void (__fastcall **)(BSTR *, BSTR **))v77 + 9))(v170, &v168);
        while ( v168 )
        {
          *(_OWORD *)&v174[8] = 0;
          v175 = 0;
          v176 = 7;
          *(_WORD *)&v174[8] = 0;
          *(_WORD *)v177 = 0;
          *(_OWORD *)&v177[8] = 0;
          memset(v178, 0, sizeof(v178));
          *(_QWORD *)v174 = &Uev::RegistrySetting::`vftable';
          v167 = v168;
          (*((void (__fastcall **)(BSTR *))*v168 + 1))(v168);
          Uev::RegistrySetting::Parse<2>((__int64)v174, (OLECHAR **)&v167, v78, v79);
          v80 = *(_QWORD **)(v4 + 168);
          if ( v80 == *(_QWORD **)(v4 + 176) )
          {
            std::vector<Uev::RegistrySetting>::_Emplace_reallocate<Uev::RegistrySetting const &>(
              (const struct Uev::TemplateSetting **)(v4 + 160),
              *(const struct Uev::TemplateSetting **)(v4 + 168),
              (const struct Uev::TemplateSetting *)v174);
          }
          else
          {
            Uev::TemplateSetting::TemplateSetting(
              *(Uev::TemplateSetting **)(v4 + 168),
              (const struct Uev::TemplateSetting *)v174);
            *v80 = &Uev::RegistrySetting::`vftable';
            *(_QWORD *)(v4 + 168) += 96LL;
          }
          v81 = v170;
          if ( !v170 )
            _com_issue_error(-2147467261);
          v82 = (void (__fastcall *)(BSTR *, BSTR **))*((_QWORD *)*v170 + 9);
          if ( v168 )
            (*((void (__fastcall **)(BSTR *))*v168 + 2))(v168);
          v168 = 0;
          v82(v81, &v168);
          *(_QWORD *)v174 = &Uev::TemplateSetting::`vftable';
          std::vector<Uev::Exclude>::_Tidy((char *)v178 + 8);
          std::vector<std::wstring>::_Tidy(&v177[8]);
          std::wstring::_Tidy_deallocate(&v174[8]);
        }
      }
      v172 = 0;
      v83 = (unsigned int (__fastcall *)(BSTR *, __int64, BSTR **))*((_QWORD *)*v64 + 36);
      v172 = 0;
      if ( `Uev::ParseTemplate<2>'::`2'::fileString )
        v84 = *`Uev::ParseTemplate<2>'::`2'::fileString;
      else
        v84 = 0;
      if ( !v83(v64, v84, &v172) )
      {
        v168 = 0;
        if ( !v172 )
          _com_issue_error(-2147467261);
        v85 = *v172;
        v168 = 0;
        (*((void (__fastcall **)(BSTR *, BSTR **))v85 + 9))(v172, &v168);
        while ( v168 )
        {
          *(_OWORD *)&v174[8] = 0;
          v175 = 0;
          v176 = 7;
          *(_WORD *)&v174[8] = 0;
          *(_WORD *)v177 = 0;
          *(_OWORD *)&v177[8] = 0;
          memset(v178, 0, sizeof(v178));
          *(_QWORD *)v174 = &Uev::FileSetting::`vftable';
          memset(v180, 0, sizeof(v180));
          *(_QWORD *)&v181 = 7;
          *(_WORD *)v180 = 0;
          v167 = v168;
          (*((void (__fastcall **)(BSTR *))*v168 + 1))(v168);
          Uev::FileSetting::Parse<2>((__int64)v174, (OLECHAR **)&v167, v86, v87);
          v88 = *(Uev::TemplateSetting **)(v4 + 192);
          if ( v88 == *(Uev::TemplateSetting **)(v4 + 200) )
          {
            std::vector<Uev::FileSetting>::_Emplace_reallocate<Uev::FileSetting const &>(
              v4 + 184,
              *(_QWORD *)(v4 + 192),
              v174);
          }
          else
          {
            v164 = *(BSTR ***)(v4 + 192);
            Uev::TemplateSetting::TemplateSetting(v88, (const struct Uev::TemplateSetting *)v174);
            *(_QWORD *)v88 = &Uev::FileSetting::`vftable';
            *((_DWORD *)v88 + 24) = v179;
            std::wstring::wstring((char *)v88 + 104, v180);
            *(_QWORD *)(v4 + 192) += 136LL;
          }
          v89 = v172;
          if ( !v172 )
            _com_issue_error(-2147467261);
          v90 = (void (__fastcall *)(BSTR *, BSTR **))*((_QWORD *)*v172 + 9);
          if ( v168 )
            (*((void (__fastcall **)(BSTR *))*v168 + 2))(v168);
          v168 = 0;
          v90(v89, &v168);
          std::wstring::_Tidy_deallocate(v180);
          *(_QWORD *)v174 = &Uev::TemplateSetting::`vftable';
          std::vector<Uev::Exclude>::_Tidy((char *)v178 + 8);
          std::vector<std::wstring>::_Tidy(&v177[8]);
          std::wstring::_Tidy_deallocate(&v174[8]);
        }
      }
      v173 = 0;
      v91 = (unsigned int (__fastcall *)(BSTR *, __int64, __int64 **))*((_QWORD *)*v64 + 36);
      v173 = 0;
      if ( `Uev::ParseTemplate<2>'::`2'::systemParameterString )
        v92 = *`Uev::ParseTemplate<2>'::`2'::systemParameterString;
      else
        v92 = 0;
      if ( !v91(v64, v92, &v173) )
      {
        v168 = 0;
        if ( !v173 )
          _com_issue_error(-2147467261);
        v93 = *v173;
        v168 = 0;
        (*(void (__fastcall **)(__int64 *, BSTR **))(v93 + 72))(v173, &v168);
        while ( v168 )
        {
          *(_OWORD *)&v174[8] = 0;
          v175 = 0;
          v176 = 7;
          *(_WORD *)&v174[8] = 0;
          *(_WORD *)v177 = 0;
          *(_OWORD *)&v177[8] = 0;
          memset(v178, 0, sizeof(v178));
          *(_QWORD *)v174 = &Uev::SystemParameterSetting::`vftable';
          v163 = v168;
          (*((void (__fastcall **)(BSTR *))*v168 + 1))(v168);
          v164 = &v163;
          v167 = v163;
          if ( v163 )
            (*((void (__fastcall **)(BSTR *))*v163 + 1))(v163);
          v94 = Uev::DomHelper::GetNodeText(pExceptionObject, &v167);
          v95 = *(_QWORD *)&v177[16];
          if ( *(_QWORD *)&v177[16] == *(_QWORD *)&v178[0] )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v177[8], *(_QWORD *)&v177[16], v94);
          }
          else
          {
            **(_OWORD **)&v177[16] = 0;
            *(_QWORD *)(v95 + 16) = 0;
            *(_QWORD *)(v95 + 24) = 0;
            *(_OWORD *)v95 = *(_OWORD *)v94;
            *(_OWORD *)(v95 + 16) = *(_OWORD *)(v94 + 16);
            *(_QWORD *)(v94 + 16) = 0;
            *(_QWORD *)(v94 + 24) = 7;
            *(_WORD *)v94 = 0;
            *(_QWORD *)&v177[16] += 32LL;
          }
          std::wstring::_Tidy_deallocate(pExceptionObject);
          if ( v163 )
            (*((void (__fastcall **)(BSTR *))*v163 + 2))(v163);
          v96 = *(_QWORD **)(v4 + 216);
          if ( v96 == *(_QWORD **)(v4 + 224) )
          {
            std::vector<Uev::SystemParameterSetting>::_Emplace_reallocate<Uev::SystemParameterSetting const &>(
              (const struct Uev::TemplateSetting **)(v4 + 208),
              *(const struct Uev::TemplateSetting **)(v4 + 216),
              (const struct Uev::TemplateSetting *)v174);
          }
          else
          {
            Uev::TemplateSetting::TemplateSetting(
              *(Uev::TemplateSetting **)(v4 + 216),
              (const struct Uev::TemplateSetting *)v174);
            *v96 = &Uev::SystemParameterSetting::`vftable';
            *(_QWORD *)(v4 + 216) += 96LL;
          }
          v97 = v173;
          if ( !v173 )
            _com_issue_error(-2147467261);
          v98 = *(void (__fastcall **)(__int64 *, BSTR **))(*v173 + 72);
          if ( v168 )
            (*((void (__fastcall **)(BSTR *))*v168 + 2))(v168);
          v168 = 0;
          v98(v97, &v168);
          *(_QWORD *)v174 = &Uev::TemplateSetting::`vftable';
          std::vector<Uev::Exclude>::_Tidy((char *)v178 + 8);
          std::vector<std::wstring>::_Tidy(&v177[8]);
          std::wstring::_Tidy_deallocate(&v174[8]);
        }
      }
      v171 = 0;
      v99 = (__int64 (__fastcall *)(BSTR *, __int64, BSTR **))*((_QWORD *)*v64 + 36);
      v171 = 0;
      if ( `Uev::ParseTemplate<2>'::`2'::customActionString )
        v100 = *`Uev::ParseTemplate<2>'::`2'::customActionString;
      else
        v100 = 0;
      result = v99(v64, v100, &v171);
      if ( !(_DWORD)result )
      {
        v168 = 0;
        if ( !v171 )
          _com_issue_error(-2147467261);
        v101 = *v171;
        v168 = 0;
        result = (*((__int64 (__fastcall **)(BSTR *, BSTR **))v101 + 9))(v171, &v168);
        while ( v168 )
        {
          *(_OWORD *)&v174[8] = 0;
          v175 = 0;
          v176 = 7;
          *(_WORD *)&v174[8] = 0;
          *(_WORD *)v177 = 0;
          *(_OWORD *)&v177[8] = 0;
          memset(v178, 0, sizeof(v178));
          *(_QWORD *)v174 = &Uev::CustomActionSetting::`vftable';
          v163 = v168;
          (*((void (__fastcall **)(BSTR *))*v168 + 1))(v168);
          v164 = &v163;
          v183 = 0;
          v184 = 0;
          v185 = 7;
          LOWORD(v183) = 0;
          v186 = 0;
          v167 = v163;
          if ( v163 )
            (*((void (__fastcall **)(BSTR *))*v163 + 1))(v163);
          v102 = Uev::DomHelper::GetNodeText(pExceptionObject, &v167);
          std::wstring::operator=(&v183, v102);
          std::wstring::_Tidy_deallocate(pExceptionObject);
          std::wstring::operator=(&v174[8], &v183);
          *(_WORD *)v177 = v186;
          std::wstring::_Tidy_deallocate(&v183);
          if ( v163 )
            (*((void (__fastcall **)(BSTR *))*v163 + 2))(v163);
          std::deque<std::wstring>::_Emplace_back_internal<std::wstring const &>(v4 + 232, &v174[8]);
          v103 = v171;
          if ( !v171 )
            _com_issue_error(-2147467261);
          v104 = (void (__fastcall *)(BSTR *, BSTR **))*((_QWORD *)*v171 + 9);
          if ( v168 )
            (*((void (__fastcall **)(BSTR *))*v168 + 2))(v168);
          v168 = 0;
          v104(v103, &v168);
          *(_QWORD *)v174 = &Uev::TemplateSetting::`vftable';
          std::vector<Uev::Exclude>::_Tidy((char *)v178 + 8);
          std::vector<std::wstring>::_Tidy(&v177[8]);
          result = std::wstring::_Tidy_deallocate(&v174[8]);
        }
      }
      if ( v171 )
        result = (*((__int64 (__fastcall **)(BSTR *))*v171 + 2))(v171);
      if ( v173 )
        result = (*(__int64 (__fastcall **)(__int64 *))(*v173 + 16))(v173);
      if ( v172 )
        result = (*((__int64 (__fastcall **)(BSTR *))*v172 + 2))(v172);
      if ( v170 )
        result = (*((__int64 (__fastcall **)(BSTR *))*v170 + 2))(v170);
    }
    if ( v64 )
      result = (*((__int64 (__fastcall **)(BSTR *))*v64 + 2))(v64);
  }
  if ( *a1 )
    return (*((__int64 (__fastcall **)(BSTR *))**a1 + 2))(*a1);
  return result;
}

```

## disassembly

```asm
0x140053048  mov     [rsp-8+arg_8], rbx
0x14005304d  push    rbp
0x14005304e  push    rsi
0x14005304f  push    rdi
0x140053050  push    r12
0x140053052  push    r13
0x140053054  push    r14
0x140053056  push    r15
0x140053058  lea     rbp, [rsp-0B0h]
0x140053060  sub     rsp, 1B0h
0x140053067  mov     rax, cs:__security_cookie
0x14005306e  xor     rax, rsp
0x140053071  mov     [rbp+0E0h+var_38], rax
0x140053078  mov     r15, r9
0x14005307b  mov     r12, r8
0x14005307e  mov     r14d, edx
0x140053081  mov     dword ptr [rbp+0E0h+var_128], edx
0x140053084  mov     r13, rcx
0x140053087  mov     [rbp+0E0h+var_160], rcx
0x14005308b  mov     edi, 4
0x140053090  mov     rax, gs:58h
0x140053099  mov     rbx, [rax]
0x14005309c  mov     eax, [rdi+rbx]
0x14005309f  cmp     cs:?$TSS0@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x1400530a5  jg      loc_1400543B9
0x1400530ab  mov     eax, [rdi+rbx]
0x1400530ae  cmp     cs:?$TSS1@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x1400530b4  jg      loc_140054476
0x1400530ba  mov     eax, [rdi+rbx]
0x1400530bd  cmp     cs:?$TSS2@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x1400530c3  jg      loc_140054533
0x1400530c9  mov     eax, [rdi+rbx]
0x1400530cc  cmp     cs:?$TSS3@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x1400530d2  jg      loc_1400545F0
0x1400530d8  mov     eax, [rdi+rbx]
0x1400530db  cmp     cs:?$TSS4@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x1400530e1  jg      loc_1400546AD
0x1400530e7  mov     eax, [rdi+rbx]
0x1400530ea  cmp     cs:?$TSS5@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x1400530f0  jg      loc_14005476A
0x1400530f6  mov     eax, [rdi+rbx]
0x1400530f9  cmp     cs:?$TSS6@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x1400530ff  jg      loc_140054827
0x140053105  mov     eax, [rdi+rbx]
0x140053108  cmp     cs:?$TSS7@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x14005310e  jg      loc_1400548E4
0x140053114  mov     eax, [rdi+rbx]
0x140053117  cmp     cs:?$TSS8@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x14005311d  jg      loc_1400549A1
0x140053123  mov     eax, [rdi+rbx]
0x140053126  cmp     cs:?$TSS9@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x14005312c  jg      loc_140054A5E
0x140053132  mov     eax, [rdi+rbx]
0x140053135  cmp     cs:?$TSS10@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x14005313b  jg      loc_140054B1B
0x140053141  mov     eax, [rdi+rbx]
0x140053144  cmp     cs:?$TSS11@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x14005314a  jg      loc_140054BD8
0x140053150  mov     eax, [rdi+rbx]
0x140053153  cmp     cs:?$TSS12@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140053159  jg      loc_140054C95
0x14005315f  mov     eax, [rdi+rbx]
0x140053162  cmp     cs:?$TSS13@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140053168  jg      loc_140054D52
0x14005316e  mov     eax, [rdi+rbx]
0x140053171  cmp     cs:?$TSS14@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140053177  jg      loc_140054E0F
0x14005317d  mov     eax, [rdi+rbx]
0x140053180  cmp     cs:?$TSS15@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140053186  jg      loc_140054ECC
0x14005318c  mov     eax, [rdi+rbx]
0x14005318f  cmp     cs:?$TSS16@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140053195  jg      loc_140054F89
0x14005319b  mov     eax, [rdi+rbx]
0x14005319e  cmp     cs:?$TSS17@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x1400531a4  jg      loc_140055046
0x1400531aa  xor     esi, esi
0x1400531ac  test    r14b, 1
0x1400531b0  jz      loc_1400538D9
0x1400531b6  mov     rax, cs:?idString@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplate<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateData &)'::`2'::idString
0x1400531bd  test    rax, rax
0x1400531c0  jz      short loc_1400531C7
0x1400531c2  mov     rbx, [rax]
0x1400531c5  jmp     short loc_1400531CA
0x1400531c7  mov     rbx, rsi
0x1400531ca  mov     rcx, [r13+0]
0x1400531ce  mov     [rsp+1E0h+var_1B0], rcx
0x1400531d3  test    rcx, rcx
0x1400531d6  jz      short loc_1400531E5
0x1400531d8  mov     rax, [rcx]
0x1400531db  mov     rax, [rax+8]
0x1400531df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400531e4  nop
0x1400531e5  mov     r9b, 1
0x1400531e8  mov     r8, rbx
0x1400531eb  lea     rdx, [rsp+1E0h+var_1B0]
0x1400531f0  lea     rcx, [rbp+0E0h+S1]
0x1400531f7  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x1400531fc  mov     rbx, rax
0x1400531ff  cmp     r15, rax
0x140053202  jz      short loc_14005322B
0x140053204  mov     rcx, r15
0x140053207  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005320c  movups  xmm0, xmmword ptr [rbx]
0x14005320f  movups  xmmword ptr [r15], xmm0
0x140053213  movups  xmm1, xmmword ptr [rbx+10h]
0x140053217  movups  xmmword ptr [r15+10h], xmm1
0x14005321c  mov     [rbx+10h], rsi
0x140053220  mov     qword ptr [rbx+18h], 7
0x140053228  mov     [rbx], si
0x14005322b  lea     rcx, [rbp+0E0h+S1]
0x140053232  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140053237  mov     rdi, rsi
0x14005323a  mov     [rsp+1E0h+var_1A8], rsi
0x14005323f  mov     rax, cs:?replacedTemplatesString@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplate<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateData &)'::`2'::replacedTemplatesString
0x140053246  test    rax, rax
0x140053249  jz      short loc_140053250
0x14005324b  mov     rbx, [rax]
0x14005324e  jmp     short loc_140053253
0x140053250  mov     rbx, rsi
0x140053253  mov     rcx, [r13+0]
0x140053257  mov     [rsp+1E0h+var_1B0], rcx
0x14005325c  test    rcx, rcx
0x14005325f  jz      short loc_14005326E
0x140053261  mov     rax, [rcx]
0x140053264  mov     rax, [rax+8]
0x140053268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005326d  nop
0x14005326e  xor     r9d, r9d
0x140053271  mov     r8, rbx
0x140053274  lea     rdx, [rsp+1E0h+var_1B0]
0x140053279  lea     rcx, [rbp+0E0h+var_140]
0x14005327d  call    ?GetNode@DomHelper@Uev@@SA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V3@PEA_W_N@Z; Uev::DomHelper::GetNode(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140053282  mov     rcx, [rax]
0x140053285  test    rcx, rcx
0x140053288  jz      short loc_14005329F
0x14005328a  mov     rdi, rcx
0x14005328d  mov     [rsp+1E0h+var_1A8], rcx
0x140053292  mov     rax, [rcx]
0x140053295  mov     rax, [rax+8]
0x140053299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005329e  nop
0x14005329f  mov     rcx, [rbp+0E0h+var_140]
0x1400532a3  test    rcx, rcx
0x1400532a6  jz      short loc_1400532B5
0x1400532a8  mov     rax, [rcx]
0x1400532ab  mov     rax, [rax+10h]
0x1400532af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400532b4  nop
0x1400532b5  test    rdi, rdi
0x1400532b8  jz      loc_1400534D5
0x1400532be  mov     [rbp+0E0h+var_138], rsi
0x1400532c2  mov     rax, [rdi]
0x1400532c5  mov     [rbp+0E0h+var_138], rsi
0x1400532c9  lea     rdx, [rbp+0E0h+var_138]
0x1400532cd  mov     rcx, rdi
0x1400532d0  mov     rax, [rax+60h]
0x1400532d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400532d9  test    eax, eax
0x1400532db  jnz     loc_1400534BF
0x1400532e1  mov     [rbp+0E0h+var_150], rsi
0x1400532e5  mov     rcx, [rbp+0E0h+var_138]
0x1400532e9  test    rcx, rcx
0x1400532ec  jz      loc_1400550FC
0x1400532f2  mov     rax, [rcx]
0x1400532f5  mov     [rbp+0E0h+var_150], rsi
0x1400532f9  lea     rdx, [rbp+0E0h+var_150]
0x1400532fd  mov     rax, [rax+48h]
0x140053301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053306  mov     rcx, [rbp+0E0h+var_150]
0x14005330a  test    rcx, rcx
0x14005330d  jz      loc_1400534BF
0x140053313  mov     [rsp+1E0h+var_1B0], rcx
0x140053318  mov     rax, [rcx]
0x14005331b  mov     rax, [rax+8]
0x14005331f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053324  nop
0x140053325  lea     rdx, [rsp+1E0h+var_1B0]
0x14005332a  lea     rcx, [rbp+0E0h+var_80]
0x14005332e  call    ?GetNodeName@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; Uev::DomHelper::GetNodeName(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)
0x140053333  nop
0x140053334  mov     r8, cs:off_1400CB300; "r3:"
0x14005333b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14005333f  mov     r9, rbx
0x140053342  inc     r9
0x140053345  cmp     [r8+r9*2], si
0x14005334a  jnz     short loc_140053342
0x14005334c  xor     edx, edx
0x14005334e  mov     rcx, rax; Src
0x140053351  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x140053356  movups  xmm0, xmmword ptr [rax]
0x140053359  movups  xmmword ptr [rbp+0E0h+S1], xmm0
0x140053360  movups  xmm1, xmmword ptr [rax+10h]
0x140053364  movups  [rbp+0E0h+var_48], xmm1
0x14005336b  mov     [rax+10h], rsi
0x14005336f  mov     qword ptr [rax+18h], 7
0x140053377  mov     [rax], si
0x14005337a  lea     rcx, [rbp+0E0h+var_80]
0x14005337e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140053383  mov     rax, cs:?idString@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplate<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateData &)'::`2'::idString
0x14005338a  test    rax, rax
0x14005338d  jz      short loc_140053394
0x14005338f  mov     rdx, [rax]
0x140053392  jmp     short loc_140053397
0x140053394  mov     rdx, rsi; S2
0x140053397  inc     rbx
0x14005339a  cmp     [rdx+rbx*2], si
0x14005339e  jnz     short loc_140053397
0x1400533a0  mov     rsi, qword ptr [rbp+0E0h+var_48]
0x1400533a7  lea     rcx, [rbp+0E0h+S1]
0x1400533ae  cmp     qword ptr [rbp+0E0h+var_48+8], 7
0x1400533b6  cmova   rcx, [rbp+0E0h+S1]; S1
0x1400533be  mov     r8, rsi
0x1400533c1  cmp     rbx, rsi
0x1400533c4  cmovb   r8, rbx; N
0x1400533c8  call    wmemcmp
0x1400533cd  xor     r14d, r14d
0x1400533d0  test    eax, eax
0x1400533d2  jnz     loc_140055112
0x1400533d8  cmp     rsi, rbx
0x1400533db  jb      loc_140055112
0x1400533e1  ja      loc_140055112
0x1400533e7  mov     eax, r14d
0x1400533ea  test    eax, eax
0x1400533ec  jnz     loc_140055112
0x1400533f2  mov     rcx, [rbp+0E0h+var_150]
0x1400533f6  mov     [rbp+0E0h+var_140], rcx
0x1400533fa  test    rcx, rcx
0x1400533fd  jz      short loc_14005340C
0x1400533ff  mov     rax, [rcx]
0x140053402  mov     rax, [rax+8]
0x140053406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005340b  nop
0x14005340c  lea     rdx, [rbp+0E0h+var_140]
0x140053410  lea     rcx, [rsp+1E0h+pExceptionObject]
0x140053415  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,bool)
0x14005341a  mov     r8, rax
0x14005341d  mov     rdx, [r15+28h]
0x140053421  cmp     rdx, [r15+30h]
0x140053425  jz      short loc_14005345A
0x140053427  xorps   xmm0, xmm0
0x14005342a  movups  xmmword ptr [rdx], xmm0
0x14005342d  mov     [rdx+10h], r14
0x140053431  mov     [rdx+18h], r14
0x140053435  movups  xmm0, xmmword ptr [rax]
0x140053438  movups  xmmword ptr [rdx], xmm0
0x14005343b  movups  xmm1, xmmword ptr [rax+10h]
0x14005343f  movups  xmmword ptr [rdx+10h], xmm1
0x140053443  mov     [rax+10h], r14
0x140053447  mov     qword ptr [rax+18h], 7
0x14005344f  mov     [rax], r14w
0x140053453  add     qword ptr [r15+28h], 20h ; ' '
0x140053458  jmp     short loc_140053464
0x14005345a  lea     rcx, [r15+20h]
0x14005345e  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x140053463  nop
0x140053464  lea     rcx, [rsp+1E0h+pExceptionObject]
0x140053469  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005346e  mov     rbx, [rbp+0E0h+var_138]
0x140053472  test    rbx, rbx
0x140053475  jz      loc_140055107
0x14005347b  mov     rax, [rbx]
0x14005347e  mov     rsi, [rax+48h]
0x140053482  mov     rcx, [rbp+0E0h+var_150]
0x140053486  test    rcx, rcx
0x140053489  jz      short loc_140053498
0x14005348b  mov     rdx, [rcx]
0x14005348e  mov     rax, [rdx+10h]
0x140053492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053497  nop
0x140053498  mov     [rbp+0E0h+var_150], r14
0x14005349c  lea     rdx, [rbp+0E0h+var_150]
0x1400534a0  mov     rcx, rbx
0x1400534a3  mov     rax, rsi
0x1400534a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400534ab  nop
0x1400534ac  lea     rcx, [rbp+0E0h+S1]
0x1400534b3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400534b8  xor     esi, esi
0x1400534ba  jmp     loc_140053306
0x1400534bf  mov     rcx, [rbp+0E0h+var_138]
0x1400534c3  test    rcx, rcx
0x1400534c6  jz      short loc_1400534D5
0x1400534c8  mov     rax, [rcx]
0x1400534cb  mov     rax, [rax+10h]
0x1400534cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400534d4  nop
0x1400534d5  mov     rax, cs:?versionString@?1???$ParseTemplate@$01@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplate<2>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateData &)'::`2'::versionString
0x1400534dc  test    rax, rax
0x1400534df  jz      short loc_1400534E6
0x1400534e1  mov     rbx, [rax]
0x1400534e4  jmp     short loc_1400534E9
0x1400534e6  mov     rbx, rsi
0x1400534e9  mov     rcx, [r13+0]
0x1400534ed  mov     [rsp+1E0h+var_1B0], rcx
0x1400534f2  test    rcx, rcx
0x1400534f5  jz      short loc_140053504
0x1400534f7  mov     rax, [rcx]
0x1400534fa  mov     rax, [rax+8]
0x1400534fe  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
