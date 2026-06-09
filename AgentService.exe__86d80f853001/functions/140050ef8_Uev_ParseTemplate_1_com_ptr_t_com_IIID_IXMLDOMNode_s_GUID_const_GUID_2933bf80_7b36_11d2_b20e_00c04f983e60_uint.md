# Uev::ParseTemplate<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Uev::TemplateData &)

- ea: `0x140050ef8`
- end: `0x140053041`
- name: `??$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@0@@Z`
- size: `8521`
- prototype: `__int64 __fastcall(BSTR **, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400572e8`

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
- `0x140049398`
- `0x140049b30`
- `0x14004a46c`
- `0x140050ef8`
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

- `OLEAUT32!__imp_SysAllocString` at `0x1400522bc`
- `OLEAUT32!__imp_SysAllocString` at `0x140052379`
- `OLEAUT32!__imp_SysAllocString` at `0x140052436`
- `OLEAUT32!__imp_SysAllocString` at `0x1400524f3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400525b0`
- `OLEAUT32!__imp_SysAllocString` at `0x14005266d`
- `OLEAUT32!__imp_SysAllocString` at `0x14005272a`
- `OLEAUT32!__imp_SysAllocString` at `0x1400527e7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400528a4`
- `OLEAUT32!__imp_SysAllocString` at `0x140052961`
- `OLEAUT32!__imp_SysAllocString` at `0x140052a1e`
- `OLEAUT32!__imp_SysAllocString` at `0x140052adb`
- `OLEAUT32!__imp_SysAllocString` at `0x140052b98`
- `OLEAUT32!__imp_SysAllocString` at `0x140052c55`
- `OLEAUT32!__imp_SysAllocString` at `0x140052d12`
- `OLEAUT32!__imp_SysAllocString` at `0x140052dcf`
- `OLEAUT32!__imp_SysAllocString` at `0x140052e8c`
- `OLEAUT32!__imp_SysAllocString` at `0x140052f47`
- `OLEAUT32!__imp_SysAllocString` at `0x1400522bc`
- `OLEAUT32!__imp_SysAllocString` at `0x140052379`
- `OLEAUT32!__imp_SysAllocString` at `0x140052436`
- `OLEAUT32!__imp_SysAllocString` at `0x1400524f3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400525b0`
- `OLEAUT32!__imp_SysAllocString` at `0x14005266d`
- `OLEAUT32!__imp_SysAllocString` at `0x14005272a`
- `OLEAUT32!__imp_SysAllocString` at `0x1400527e7`
- `OLEAUT32!__imp_SysAllocString` at `0x1400528a4`
- `OLEAUT32!__imp_SysAllocString` at `0x140052961`
- `OLEAUT32!__imp_SysAllocString` at `0x140052a1e`
- `OLEAUT32!__imp_SysAllocString` at `0x140052adb`
- `OLEAUT32!__imp_SysAllocString` at `0x140052b98`
- `OLEAUT32!__imp_SysAllocString` at `0x140052c55`
- `OLEAUT32!__imp_SysAllocString` at `0x140052d12`
- `OLEAUT32!__imp_SysAllocString` at `0x140052dcf`
- `OLEAUT32!__imp_SysAllocString` at `0x140052e8c`
- `OLEAUT32!__imp_SysAllocString` at `0x140052f47`

## string_xrefs

- `0x140052666`: `ReplacedTemplates`
- `0x140052e85`: `SystemParameter`
- `0x140052d0b`: `Registry`

## pseudocode

```c
__int64 __fastcall Uev::ParseTemplate<1>(BSTR **a1, int a2, __int64 a3, __int64 a4)
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
  if ( __TSS0__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&__TSS0__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS0__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v105 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v106 = (BSTR *)operator new(0x18u);
      v169 = v106;
      v106[1] = 0;
      *((_DWORD *)v106 + 4) = 1;
      v107 = SysAllocString(L"Name");
      *v106 = v107;
      if ( !v107 )
        _com_issue_error(-2147024882);
      v163 = v106;
      _bstr_t::operator+(v105, &`Uev::ParseTemplate<1>'::`2'::nameString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__nameString__);
      Init_thread_footer(&__TSS0__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS1__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS1__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS1__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v108 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v109 = (BSTR *)operator new(0x18u);
      v169 = v109;
      v109[1] = 0;
      *((_DWORD *)v109 + 4) = 1;
      v110 = SysAllocString(L"Description");
      *v109 = v110;
      if ( !v110 )
        _com_issue_error(-2147024882);
      v163 = v109;
      _bstr_t::operator+(v108, &`Uev::ParseTemplate<1>'::`2'::descriptionString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__descriptionString__);
      Init_thread_footer(&__TSS1__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS2__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS2__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS2__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v111 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v112 = (BSTR *)operator new(0x18u);
      v169 = v112;
      v112[1] = 0;
      *((_DWORD *)v112 + 4) = 1;
      v113 = SysAllocString(L"LocalizedNames");
      *v112 = v113;
      if ( !v113 )
        _com_issue_error(-2147024882);
      v163 = v112;
      _bstr_t::operator+(v111, &`Uev::ParseTemplate<1>'::`2'::localizedNameString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__localizedNameString__);
      Init_thread_footer(&__TSS2__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS3__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS3__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS3__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v114 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v115 = (BSTR *)operator new(0x18u);
      v169 = v115;
      v115[1] = 0;
      *((_DWORD *)v115 + 4) = 1;
      v116 = SysAllocString(L"LocalizedDescriptions");
      *v115 = v116;
      if ( !v116 )
        _com_issue_error(-2147024882);
      v163 = v115;
      _bstr_t::operator+(v114, &`Uev::ParseTemplate<1>'::`2'::localizedDescriptionString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__localizedDescriptionString__);
      Init_thread_footer(&__TSS3__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS4__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS4__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS4__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v117 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v118 = (BSTR *)operator new(0x18u);
      v169 = v118;
      v118[1] = 0;
      *((_DWORD *)v118 + 4) = 1;
      v119 = SysAllocString(L"ID");
      *v118 = v119;
      if ( !v119 )
        _com_issue_error(-2147024882);
      v163 = v118;
      _bstr_t::operator+(v117, &`Uev::ParseTemplate<1>'::`2'::idString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__idString__);
      Init_thread_footer(&__TSS4__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS5__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS5__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS5__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v120 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v121 = (BSTR *)operator new(0x18u);
      v169 = v121;
      v121[1] = 0;
      *((_DWORD *)v121 + 4) = 1;
      v122 = SysAllocString(L"ReplacedTemplates");
      *v121 = v122;
      if ( !v122 )
        _com_issue_error(-2147024882);
      v163 = v121;
      _bstr_t::operator+(v120, &`Uev::ParseTemplate<1>'::`2'::replacedTemplatesString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__replacedTemplatesString__);
      Init_thread_footer(&__TSS5__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS6__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS6__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS6__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v123 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v124 = (BSTR *)operator new(0x18u);
      v169 = v124;
      v124[1] = 0;
      *((_DWORD *)v124 + 4) = 1;
      v125 = SysAllocString(L"Version");
      *v124 = v125;
      if ( !v125 )
        _com_issue_error(-2147024882);
      v163 = v124;
      _bstr_t::operator+(v123, &`Uev::ParseTemplate<1>'::`2'::versionString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__versionString__);
      Init_thread_footer(&__TSS6__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS7__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS7__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS7__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v126 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v127 = (BSTR *)operator new(0x18u);
      v169 = v127;
      v127[1] = 0;
      *((_DWORD *)v127 + 4) = 1;
      v128 = SysAllocString(L"DeferToMSAccount");
      *v127 = v128;
      if ( !v128 )
        _com_issue_error(-2147024882);
      v163 = v127;
      _bstr_t::operator+(v126, &`Uev::ParseTemplate<1>'::`2'::deferToMSAccountString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__deferToMSAccountString__);
      Init_thread_footer(&__TSS7__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS8__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS8__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS8__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v129 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v130 = (BSTR *)operator new(0x18u);
      v169 = v130;
      v130[1] = 0;
      *((_DWORD *)v130 + 4) = 1;
      v131 = SysAllocString(L"DeferToOffice365");
      *v130 = v131;
      if ( !v131 )
        _com_issue_error(-2147024882);
      v163 = v130;
      _bstr_t::operator+(v129, &`Uev::ParseTemplate<1>'::`2'::deferToOffice365String, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__deferToOffice365String__);
      Init_thread_footer(&__TSS8__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS9__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS9__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS9__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v132 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v133 = (BSTR *)operator new(0x18u);
      v169 = v133;
      v133[1] = 0;
      *((_DWORD *)v133 + 4) = 1;
      v134 = SysAllocString(L"Asynchronous");
      *v133 = v134;
      if ( !v134 )
        _com_issue_error(-2147024882);
      v163 = v133;
      _bstr_t::operator+(v132, &`Uev::ParseTemplate<1>'::`2'::asyncString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__asyncString__);
      Init_thread_footer(&__TSS9__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS10__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS10__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS10__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v135 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v136 = (BSTR *)operator new(0x18u);
      v169 = v136;
      v136[1] = 0;
      *((_DWORD *)v136 + 4) = 1;
      v137 = SysAllocString(L"PreventOverlappingSynchronization");
      *v136 = v137;
      if ( !v137 )
        _com_issue_error(-2147024882);
      v163 = v136;
      _bstr_t::operator+(v135, &`Uev::ParseTemplate<1>'::`2'::preventOverlappingSynchronizationString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__preventOverlappingSynchronizationString__);
      Init_thread_footer(&__TSS10__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS11__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS11__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS11__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v138 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v139 = (BSTR *)operator new(0x18u);
      v169 = v139;
      v139[1] = 0;
      *((_DWORD *)v139 + 4) = 1;
      v140 = SysAllocString(L"AlwaysApplySettings");
      *v139 = v140;
      if ( !v140 )
        _com_issue_error(-2147024882);
      v163 = v139;
      _bstr_t::operator+(v138, &`Uev::ParseTemplate<1>'::`2'::alwaysApplySettingsString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__alwaysApplySettingsString__);
      Init_thread_footer(&__TSS11__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS12__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS12__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS12__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v141 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v142 = (BSTR *)operator new(0x18u);
      v169 = v142;
      v142[1] = 0;
      *((_DWORD *)v142 + 4) = 1;
      v143 = SysAllocString(L"Processes");
      *v142 = v143;
      if ( !v143 )
        _com_issue_error(-2147024882);
      v163 = v142;
      _bstr_t::operator+(v141, &`Uev::ParseTemplate<1>'::`2'::processesString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__processesString__);
      Init_thread_footer(&__TSS12__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS13__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS13__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS13__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v144 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v145 = (BSTR *)operator new(0x18u);
      v169 = v145;
      v145[1] = 0;
      *((_DWORD *)v145 + 4) = 1;
      v146 = SysAllocString(L"Settings");
      *v145 = v146;
      if ( !v146 )
        _com_issue_error(-2147024882);
      v163 = v145;
      _bstr_t::operator+(v144, &`Uev::ParseTemplate<1>'::`2'::settingsString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__settingsString__);
      Init_thread_footer(&__TSS13__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS14__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS14__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS14__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v147 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v148 = (BSTR *)operator new(0x18u);
      v169 = v148;
      v148[1] = 0;
      *((_DWORD *)v148 + 4) = 1;
      v149 = SysAllocString(L"Registry");
      *v148 = v149;
      if ( !v149 )
        _com_issue_error(-2147024882);
      v163 = v148;
      _bstr_t::operator+(v147, &`Uev::ParseTemplate<1>'::`2'::registryString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__registryString__);
      Init_thread_footer(&__TSS14__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS15__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS15__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS15__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v150 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v151 = (BSTR *)operator new(0x18u);
      v169 = v151;
      v151[1] = 0;
      *((_DWORD *)v151 + 4) = 1;
      v152 = SysAllocString(L"File");
      *v151 = v152;
      if ( !v152 )
        _com_issue_error(-2147024882);
      v163 = v151;
      _bstr_t::operator+(v150, &`Uev::ParseTemplate<1>'::`2'::fileString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__fileString__);
      Init_thread_footer(&__TSS15__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( __TSS16__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > *(_DWORD *)(v9 + 4) )
  {
    Init_thread_header(&__TSS16__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS16__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v153 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v154 = (BSTR *)operator new(0x18u);
      v169 = v154;
      v154[1] = 0;
      *((_DWORD *)v154 + 4) = 1;
      v155 = SysAllocString(L"SystemParameter");
      *v154 = v155;
      if ( !v155 )
        _com_issue_error(-2147024882);
      v163 = v154;
      _bstr_t::operator+(v153, &`Uev::ParseTemplate<1>'::`2'::systemParameterString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__systemParameterString__);
      Init_thread_footer(&__TSS16__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  result = *(unsigned int *)(v9 + 4);
  if ( __TSS17__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA > (int)result )
  {
    result = Init_thread_header(&__TSS17__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    if ( __TSS17__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA == -1 )
    {
      v156 = _bstr_t::_bstr_t((_bstr_t *)&v167, off_1400CB2F8);
      v157 = (BSTR *)operator new(0x18u);
      v169 = v157;
      v157[1] = 0;
      *((_DWORD *)v157 + 4) = 1;
      v158 = SysAllocString(L"CustomAction");
      *v157 = v158;
      if ( !v158 )
        _com_issue_error(-2147024882);
      v163 = v157;
      _bstr_t::operator+(v156, &`Uev::ParseTemplate<1>'::`2'::customActionString, &v163);
      _bstr_t::_Free((_bstr_t *)&v163);
      _bstr_t::_Free((_bstr_t *)&v167);
      atexit(Uev::ParseTemplate_1__::_2_::_dynamic_atexit_destructor_for__customActionString__);
      result = Init_thread_footer(&__TSS17__1____ParseTemplate__00_Uev__YAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B____IAEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAVTemplateData_1__Z_4HA);
    }
  }
  if ( (v6 & 1) != 0 )
  {
    if ( `Uev::ParseTemplate<1>'::`2'::idString )
      v11 = *`Uev::ParseTemplate<1>'::`2'::idString;
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
    if ( `Uev::ParseTemplate<1>'::`2'::replacedTemplatesString )
      v15 = *`Uev::ParseTemplate<1>'::`2'::replacedTemplatesString;
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
          while ( off_1400CB2F8[v23] );
          v24 = std::wstring::_Insert<wchar_t>(NodeName);
          *(_OWORD *)S1 = *(_OWORD *)v24;
          v188 = *(_OWORD *)(v24 + 16);
          *(_QWORD *)(v24 + 16) = 0;
          *(_QWORD *)(v24 + 24) = 7;
          *(_WORD *)v24 = 0;
          std::wstring::_Tidy_deallocate(&v183);
          if ( `Uev::ParseTemplate<1>'::`2'::idString )
            v25 = (const wchar_t *)*`Uev::ParseTemplate<1>'::`2'::idString;
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
    if ( `Uev::ParseTemplate<1>'::`2'::versionString )
      v33 = *`Uev::ParseTemplate<1>'::`2'::versionString;
    else
      v33 = 0;
    v34 = *a1;
    v163 = v34;
    if ( v34 )
      (*((void (__fastcall **)(BSTR *))*v34 + 1))(v34);
    *(_DWORD *)(v4 + 120) = Uev::DomHelper::GetNodeNumber(&v163, v33);
    if ( `Uev::ParseTemplate<1>'::`2'::nameString )
      v35 = *`Uev::ParseTemplate<1>'::`2'::nameString;
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
    if ( `Uev::ParseTemplate<1>'::`2'::descriptionString )
      v39 = *`Uev::ParseTemplate<1>'::`2'::descriptionString;
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
      if ( `Uev::ParseTemplate<1>'::`2'::localizedNameString )
        v43 = *`Uev::ParseTemplate<1>'::`2'::localizedNameString;
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
        if ( `Uev::ParseTemplate<1>'::`2'::nameString )
          v43 = *`Uev::ParseTemplate<1>'::`2'::nameString;
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
      if ( `Uev::ParseTemplate<1>'::`2'::localizedDescriptionString )
        v46 = *`Uev::ParseTemplate<1>'::`2'::localizedDescriptionString;
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
        if ( `Uev::ParseTemplate<1>'::`2'::descriptionString )
          v49 = *`Uev::ParseTemplate<1>'::`2'::descriptionString;
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
    if ( `Uev::ParseTemplate<1>'::`2'::deferToMSAccountString )
      v51 = *`Uev::ParseTemplate<1>'::`2'::deferToMSAccountString;
    else
      v51 = 0;
    v52 = *a1;
    v163 = v52;
    if ( v52 )
      (*((void (__fastcall **)(BSTR *))*v52 + 1))(v52);
    Uev::DomHelper::GetNode(&v167, &v163, v51, 0, v160);
    if ( v167 )
      *(_BYTE *)(v4 + 124) = 1;
    if ( `Uev::ParseTemplate<1>'::`2'::deferToOffice365String )
      v53 = *`Uev::ParseTemplate<1>'::`2'::deferToOffice365String;
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
    if ( `Uev::ParseTemplate<1>'::`2'::processesString )
      v57 = *`Uev::ParseTemplate<1>'::`2'::processesString;
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
          Uev::TemplateProcess::Parse<1>((__int64)v174, &v167);
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
    if ( `Uev::ParseTemplate<1>'::`2'::settingsString )
      v65 = *`Uev::ParseTemplate<1>'::`2'::settingsString;
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
      if ( `Uev::ParseTemplate<1>'::`2'::asyncString )
        v68 = *`Uev::ParseTemplate<1>'::`2'::asyncString;
      else
        v68 = 0;
      v167 = v64;
      (*((void (__fastcall **)(BSTR *))*v64 + 1))(v64);
      *(_BYTE *)(v4 + 126) = Uev::DomHelper::GetNodeBoolean(&v167, v68, v69, 0);
      if ( `Uev::ParseTemplate<1>'::`2'::preventOverlappingSynchronizationString )
        v70 = *`Uev::ParseTemplate<1>'::`2'::preventOverlappingSynchronizationString;
      else
        v70 = 0;
      v167 = v64;
      (*((void (__fastcall **)(BSTR *))*v64 + 1))(v64);
      LOBYTE(v71) = 1;
      *(_BYTE *)(v4 + 127) = Uev::DomHelper::GetNodeBoolean(&v167, v70, v72, v71);
      if ( `Uev::ParseTemplate<1>'::`2'::alwaysApplySettingsString )
        v73 = *`Uev::ParseTemplate<1>'::`2'::alwaysApplySettingsString;
      else
        v73 = 0;
      v167 = v64;
      (*((void (__fastcall **)(BSTR *))*v64 + 1))(v64);
      *(_BYTE *)(v4 + 128) = Uev::DomHelper::GetNodeBoolean(&v167, v73, v74, 0);
      v170 = 0;
      v75 = (unsigned int (__fastcall *)(BSTR *, __int64, BSTR **))*((_QWORD *)*v64 + 36);
      v170 = 0;
      if ( `Uev::ParseTemplate<1>'::`2'::registryString )
        v76 = *`Uev::ParseTemplate<1>'::`2'::registryString;
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
          Uev::RegistrySetting::Parse<1>((__int64)v174, (OLECHAR **)&v167, v78, v79);
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
      if ( `Uev::ParseTemplate<1>'::`2'::fileString )
        v84 = *`Uev::ParseTemplate<1>'::`2'::fileString;
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
          Uev::FileSetting::Parse<1>((__int64)v174, (OLECHAR **)&v167, v86, v87);
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
      if ( `Uev::ParseTemplate<1>'::`2'::systemParameterString )
        v92 = *`Uev::ParseTemplate<1>'::`2'::systemParameterString;
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
      if ( `Uev::ParseTemplate<1>'::`2'::customActionString )
        v100 = *`Uev::ParseTemplate<1>'::`2'::customActionString;
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
0x140050ef8  mov     [rsp-8+arg_8], rbx
0x140050efd  push    rbp
0x140050efe  push    rsi
0x140050eff  push    rdi
0x140050f00  push    r12
0x140050f02  push    r13
0x140050f04  push    r14
0x140050f06  push    r15
0x140050f08  lea     rbp, [rsp-0B0h]
0x140050f10  sub     rsp, 1B0h
0x140050f17  mov     rax, cs:__security_cookie
0x140050f1e  xor     rax, rsp
0x140050f21  mov     [rbp+0E0h+var_38], rax
0x140050f28  mov     r15, r9
0x140050f2b  mov     r12, r8
0x140050f2e  mov     r14d, edx
0x140050f31  mov     dword ptr [rbp+0E0h+var_128], edx
0x140050f34  mov     r13, rcx
0x140050f37  mov     [rbp+0E0h+var_160], rcx
0x140050f3b  mov     edi, 4
0x140050f40  mov     rax, gs:58h
0x140050f49  mov     rbx, [rax]
0x140050f4c  mov     eax, [rdi+rbx]
0x140050f4f  cmp     cs:?$TSS0@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050f55  jg      loc_140052269
0x140050f5b  mov     eax, [rdi+rbx]
0x140050f5e  cmp     cs:?$TSS1@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050f64  jg      loc_140052326
0x140050f6a  mov     eax, [rdi+rbx]
0x140050f6d  cmp     cs:?$TSS2@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050f73  jg      loc_1400523E3
0x140050f79  mov     eax, [rdi+rbx]
0x140050f7c  cmp     cs:?$TSS3@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050f82  jg      loc_1400524A0
0x140050f88  mov     eax, [rdi+rbx]
0x140050f8b  cmp     cs:?$TSS4@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050f91  jg      loc_14005255D
0x140050f97  mov     eax, [rdi+rbx]
0x140050f9a  cmp     cs:?$TSS5@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050fa0  jg      loc_14005261A
0x140050fa6  mov     eax, [rdi+rbx]
0x140050fa9  cmp     cs:?$TSS6@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050faf  jg      loc_1400526D7
0x140050fb5  mov     eax, [rdi+rbx]
0x140050fb8  cmp     cs:?$TSS7@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050fbe  jg      loc_140052794
0x140050fc4  mov     eax, [rdi+rbx]
0x140050fc7  cmp     cs:?$TSS8@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050fcd  jg      loc_140052851
0x140050fd3  mov     eax, [rdi+rbx]
0x140050fd6  cmp     cs:?$TSS9@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050fdc  jg      loc_14005290E
0x140050fe2  mov     eax, [rdi+rbx]
0x140050fe5  cmp     cs:?$TSS10@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050feb  jg      loc_1400529CB
0x140050ff1  mov     eax, [rdi+rbx]
0x140050ff4  cmp     cs:?$TSS11@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140050ffa  jg      loc_140052A88
0x140051000  mov     eax, [rdi+rbx]
0x140051003  cmp     cs:?$TSS12@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140051009  jg      loc_140052B45
0x14005100f  mov     eax, [rdi+rbx]
0x140051012  cmp     cs:?$TSS13@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140051018  jg      loc_140052C02
0x14005101e  mov     eax, [rdi+rbx]
0x140051021  cmp     cs:?$TSS14@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140051027  jg      loc_140052CBF
0x14005102d  mov     eax, [rdi+rbx]
0x140051030  cmp     cs:?$TSS15@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140051036  jg      loc_140052D7C
0x14005103c  mov     eax, [rdi+rbx]
0x14005103f  cmp     cs:?$TSS16@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140051045  jg      loc_140052E39
0x14005104b  mov     eax, [rdi+rbx]
0x14005104e  cmp     cs:?$TSS17@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4HA, eax
0x140051054  jg      loc_140052EF6
0x14005105a  xor     esi, esi
0x14005105c  test    r14b, 1
0x140051060  jz      loc_140051789
0x140051066  mov     rax, cs:?idString@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplate<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateData &)'::`2'::idString
0x14005106d  test    rax, rax
0x140051070  jz      short loc_140051077
0x140051072  mov     rbx, [rax]
0x140051075  jmp     short loc_14005107A
0x140051077  mov     rbx, rsi
0x14005107a  mov     rcx, [r13+0]
0x14005107e  mov     [rsp+1E0h+var_1B0], rcx
0x140051083  test    rcx, rcx
0x140051086  jz      short loc_140051095
0x140051088  mov     rax, [rcx]
0x14005108b  mov     rax, [rax+8]
0x14005108f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051094  nop
0x140051095  mov     r9b, 1
0x140051098  mov     r8, rbx
0x14005109b  lea     rdx, [rsp+1E0h+var_1B0]
0x1400510a0  lea     rcx, [rbp+0E0h+S1]
0x1400510a7  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x1400510ac  mov     rbx, rax
0x1400510af  cmp     r15, rax
0x1400510b2  jz      short loc_1400510DB
0x1400510b4  mov     rcx, r15
0x1400510b7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400510bc  movups  xmm0, xmmword ptr [rbx]
0x1400510bf  movups  xmmword ptr [r15], xmm0
0x1400510c3  movups  xmm1, xmmword ptr [rbx+10h]
0x1400510c7  movups  xmmword ptr [r15+10h], xmm1
0x1400510cc  mov     [rbx+10h], rsi
0x1400510d0  mov     qword ptr [rbx+18h], 7
0x1400510d8  mov     [rbx], si
0x1400510db  lea     rcx, [rbp+0E0h+S1]
0x1400510e2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400510e7  mov     rdi, rsi
0x1400510ea  mov     [rsp+1E0h+var_1A8], rsi
0x1400510ef  mov     rax, cs:?replacedTemplatesString@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplate<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateData &)'::`2'::replacedTemplatesString
0x1400510f6  test    rax, rax
0x1400510f9  jz      short loc_140051100
0x1400510fb  mov     rbx, [rax]
0x1400510fe  jmp     short loc_140051103
0x140051100  mov     rbx, rsi
0x140051103  mov     rcx, [r13+0]
0x140051107  mov     [rsp+1E0h+var_1B0], rcx
0x14005110c  test    rcx, rcx
0x14005110f  jz      short loc_14005111E
0x140051111  mov     rax, [rcx]
0x140051114  mov     rax, [rax+8]
0x140051118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005111d  nop
0x14005111e  xor     r9d, r9d
0x140051121  mov     r8, rbx
0x140051124  lea     rdx, [rsp+1E0h+var_1B0]
0x140051129  lea     rcx, [rbp+0E0h+var_140]
0x14005112d  call    ?GetNode@DomHelper@Uev@@SA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V3@PEA_W_N@Z; Uev::DomHelper::GetNode(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x140051132  mov     rcx, [rax]
0x140051135  test    rcx, rcx
0x140051138  jz      short loc_14005114F
0x14005113a  mov     rdi, rcx
0x14005113d  mov     [rsp+1E0h+var_1A8], rcx
0x140051142  mov     rax, [rcx]
0x140051145  mov     rax, [rax+8]
0x140051149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005114e  nop
0x14005114f  mov     rcx, [rbp+0E0h+var_140]
0x140051153  test    rcx, rcx
0x140051156  jz      short loc_140051165
0x140051158  mov     rax, [rcx]
0x14005115b  mov     rax, [rax+10h]
0x14005115f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051164  nop
0x140051165  test    rdi, rdi
0x140051168  jz      loc_140051385
0x14005116e  mov     [rbp+0E0h+var_138], rsi
0x140051172  mov     rax, [rdi]
0x140051175  mov     [rbp+0E0h+var_138], rsi
0x140051179  lea     rdx, [rbp+0E0h+var_138]
0x14005117d  mov     rcx, rdi
0x140051180  mov     rax, [rax+60h]
0x140051184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051189  test    eax, eax
0x14005118b  jnz     loc_14005136F
0x140051191  mov     [rbp+0E0h+var_150], rsi
0x140051195  mov     rcx, [rbp+0E0h+var_138]
0x140051199  test    rcx, rcx
0x14005119c  jz      loc_140052FAC
0x1400511a2  mov     rax, [rcx]
0x1400511a5  mov     [rbp+0E0h+var_150], rsi
0x1400511a9  lea     rdx, [rbp+0E0h+var_150]
0x1400511ad  mov     rax, [rax+48h]
0x1400511b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400511b6  mov     rcx, [rbp+0E0h+var_150]
0x1400511ba  test    rcx, rcx
0x1400511bd  jz      loc_14005136F
0x1400511c3  mov     [rsp+1E0h+var_1B0], rcx
0x1400511c8  mov     rax, [rcx]
0x1400511cb  mov     rax, [rax+8]
0x1400511cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400511d4  nop
0x1400511d5  lea     rdx, [rsp+1E0h+var_1B0]
0x1400511da  lea     rcx, [rbp+0E0h+var_80]
0x1400511de  call    ?GetNodeName@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; Uev::DomHelper::GetNodeName(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)
0x1400511e3  nop
0x1400511e4  mov     r8, cs:off_1400CB2F8; "r2:"
0x1400511eb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400511ef  mov     r9, rbx
0x1400511f2  inc     r9
0x1400511f5  cmp     [r8+r9*2], si
0x1400511fa  jnz     short loc_1400511F2
0x1400511fc  xor     edx, edx
0x1400511fe  mov     rcx, rax; Src
0x140051201  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x140051206  movups  xmm0, xmmword ptr [rax]
0x140051209  movups  xmmword ptr [rbp+0E0h+S1], xmm0
0x140051210  movups  xmm1, xmmword ptr [rax+10h]
0x140051214  movups  [rbp+0E0h+var_48], xmm1
0x14005121b  mov     [rax+10h], rsi
0x14005121f  mov     qword ptr [rax+18h], 7
0x140051227  mov     [rax], si
0x14005122a  lea     rcx, [rbp+0E0h+var_80]
0x14005122e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140051233  mov     rax, cs:?idString@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplate<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateData &)'::`2'::idString
0x14005123a  test    rax, rax
0x14005123d  jz      short loc_140051244
0x14005123f  mov     rdx, [rax]
0x140051242  jmp     short loc_140051247
0x140051244  mov     rdx, rsi; S2
0x140051247  inc     rbx
0x14005124a  cmp     [rdx+rbx*2], si
0x14005124e  jnz     short loc_140051247
0x140051250  mov     rsi, qword ptr [rbp+0E0h+var_48]
0x140051257  lea     rcx, [rbp+0E0h+S1]
0x14005125e  cmp     qword ptr [rbp+0E0h+var_48+8], 7
0x140051266  cmova   rcx, [rbp+0E0h+S1]; S1
0x14005126e  mov     r8, rsi
0x140051271  cmp     rbx, rsi
0x140051274  cmovb   r8, rbx; N
0x140051278  call    wmemcmp
0x14005127d  xor     r14d, r14d
0x140051280  test    eax, eax
0x140051282  jnz     loc_140052FC2
0x140051288  cmp     rsi, rbx
0x14005128b  jb      loc_140052FC2
0x140051291  ja      loc_140052FC2
0x140051297  mov     eax, r14d
0x14005129a  test    eax, eax
0x14005129c  jnz     loc_140052FC2
0x1400512a2  mov     rcx, [rbp+0E0h+var_150]
0x1400512a6  mov     [rbp+0E0h+var_140], rcx
0x1400512aa  test    rcx, rcx
0x1400512ad  jz      short loc_1400512BC
0x1400512af  mov     rax, [rcx]
0x1400512b2  mov     rax, [rax+8]
0x1400512b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400512bb  nop
0x1400512bc  lea     rdx, [rbp+0E0h+var_140]
0x1400512c0  lea     rcx, [rsp+1E0h+pExceptionObject]
0x1400512c5  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,bool)
0x1400512ca  mov     r8, rax
0x1400512cd  mov     rdx, [r15+28h]
0x1400512d1  cmp     rdx, [r15+30h]
0x1400512d5  jz      short loc_14005130A
0x1400512d7  xorps   xmm0, xmm0
0x1400512da  movups  xmmword ptr [rdx], xmm0
0x1400512dd  mov     [rdx+10h], r14
0x1400512e1  mov     [rdx+18h], r14
0x1400512e5  movups  xmm0, xmmword ptr [rax]
0x1400512e8  movups  xmmword ptr [rdx], xmm0
0x1400512eb  movups  xmm1, xmmword ptr [rax+10h]
0x1400512ef  movups  xmmword ptr [rdx+10h], xmm1
0x1400512f3  mov     [rax+10h], r14
0x1400512f7  mov     qword ptr [rax+18h], 7
0x1400512ff  mov     [rax], r14w
0x140051303  add     qword ptr [r15+28h], 20h ; ' '
0x140051308  jmp     short loc_140051314
0x14005130a  lea     rcx, [r15+20h]
0x14005130e  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x140051313  nop
0x140051314  lea     rcx, [rsp+1E0h+pExceptionObject]
0x140051319  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005131e  mov     rbx, [rbp+0E0h+var_138]
0x140051322  test    rbx, rbx
0x140051325  jz      loc_140052FB7
0x14005132b  mov     rax, [rbx]
0x14005132e  mov     rsi, [rax+48h]
0x140051332  mov     rcx, [rbp+0E0h+var_150]
0x140051336  test    rcx, rcx
0x140051339  jz      short loc_140051348
0x14005133b  mov     rdx, [rcx]
0x14005133e  mov     rax, [rdx+10h]
0x140051342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051347  nop
0x140051348  mov     [rbp+0E0h+var_150], r14
0x14005134c  lea     rdx, [rbp+0E0h+var_150]
0x140051350  mov     rcx, rbx
0x140051353  mov     rax, rsi
0x140051356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005135b  nop
0x14005135c  lea     rcx, [rbp+0E0h+S1]
0x140051363  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140051368  xor     esi, esi
0x14005136a  jmp     loc_1400511B6
0x14005136f  mov     rcx, [rbp+0E0h+var_138]
0x140051373  test    rcx, rcx
0x140051376  jz      short loc_140051385
0x140051378  mov     rax, [rcx]
0x14005137b  mov     rax, [rax+10h]
0x14005137f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051384  nop
0x140051385  mov     rax, cs:?versionString@?1???$ParseTemplate@$00@Uev@@YAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateData@1@@Z@4V_bstr_t@@B; _bstr_t const `Uev::ParseTemplate<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,uint,std::wstring const &,Uev::TemplateData &)'::`2'::versionString
0x14005138c  test    rax, rax
0x14005138f  jz      short loc_140051396
0x140051391  mov     rbx, [rax]
0x140051394  jmp     short loc_140051399
0x140051396  mov     rbx, rsi
0x140051399  mov     rcx, [r13+0]
0x14005139d  mov     [rsp+1E0h+var_1B0], rcx
0x1400513a2  test    rcx, rcx
0x1400513a5  jz      short loc_1400513B4
0x1400513a7  mov     rax, [rcx]
0x1400513aa  mov     rax, [rax+8]
0x1400513ae  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
