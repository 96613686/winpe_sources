# WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)

- ea: `0x18001a92c`
- end: `0x18001b742`
- name: `?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z`
- size: `3606`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CETWProperties *__hidden this, struct IProfileCollection *, struct WindowsPerformanceRecorder::CControlManager *, bool)`
- caller_count: `17`
- callee_count: `35`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001c8bc`
- `0x180031374`
- `0x180032adc`
- `0x18003a1f0`
- `0x180049630`
- `0x180049970`
- `0x180049ca0`
- `0x18004ac00`
- `0x180058800`
- `0x180059060`
- `0x18005a1f0`
- `0x18005d1bc`
- `0x18005deb0`
- `0x18005f068`
- `0x180060940`
- `0x180061780`
- `0x18006eda0`

## callees

- `0x180004d78`
- `0x180006914`
- `0x180008330`
- `0x18000a9e0`
- `0x18000b540`
- `0x18000c550`
- `0x18000c720`
- `0x18000c880`
- `0x18000eeb0`
- `0x18000fe14`
- `0x1800102d8`
- `0x1800131a0`
- `0x1800195b0`
- `0x18001a490`
- `0x18001a59c`
- `0x18001a92c`
- `0x18001b748`
- `0x18001c458`
- `0x18001e6e0`
- `0x180036d08`
- `0x18003d11c`
- `0x180040a04`
- `0x180041e30`
- `0x180044230`
- `0x180046a40`
- `0x180046a70`
- `0x180046d2c`
- `0x1800480fc`
- `0x1800489e0`
- `0x180048a60`
- `0x18004f1d0`
- `0x1800639d4`
- `0x180063aec`
- `0x180064024`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001ab4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ac4c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001accc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ab4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ac4c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001accc`

## string_xrefs

- `0x18001a9b1`: `COMGUARD`
- `0x18001af0a`: `COMGUARD`
- `0x18001b0a2`: `COMGUARD`
- `0x18001b14a`: `COMGUARD`
- `0x18001b1fc`: `COMGUARD`
- `0x18001b2f7`: `COMGUARD`
- `0x18001b609`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::Initialize(
        WindowsPerformanceRecorder::CETWProperties *this,
        struct IProfileCollection *a2,
        struct WindowsPerformanceRecorder::CControlManager *a3,
        char a4)
{
  struct WindowsPerformanceRecorder::CControlManager *v5; // r15
  int v8; // ebx
  signed int v9; // eax
  __int64 v10; // rcx
  int v12; // ebx
  __int64 v13; // rbx
  BSTR v14; // rdx
  __int64 *v15; // rbx
  BSTR v16; // rdi
  __int64 *v17; // rbx
  __int64 v18; // rcx
  signed int v19; // eax
  unsigned int v20; // r14d
  __int64 **v21; // rcx
  __int64 *n; // rax
  __int64 *ii; // rcx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  signed int v28; // eax
  unsigned int v29; // r14d
  signed int v30; // eax
  unsigned int v31; // r14d
  signed int v32; // eax
  unsigned int v33; // r14d
  __int64 **v34; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  signed int v37; // eax
  unsigned int v38; // edi
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // r8
  __int64 v42; // r8
  char *v43; // r15
  void *v44; // r14
  _QWORD *v45; // rax
  int v46; // edi
  _BYTE *v47; // r11
  _QWORD *v48; // r12
  char *v49; // rcx
  signed __int64 v50; // r10
  int v51; // edx
  int v52; // r9d
  unsigned __int16 *v53; // rax
  int v54; // ecx
  int v55; // edx
  _QWORD *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r14
  __int64 i; // rcx
  __int64 v61; // rcx
  __int64 j; // rax
  signed int v63; // eax
  unsigned int v64; // edi
  BSTR v65; // rax
  __int64 v66; // rcx
  const char *v67; // [rsp+28h] [rbp-F0h]
  __int64 v68; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v69; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v70; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v71; // [rsp+48h] [rbp-D0h] BYREF
  BSTR v72; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v73; // [rsp+58h] [rbp-C0h] BYREF
  void *v74; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v75; // [rsp+68h] [rbp-B0h]
  __int128 v76; // [rsp+70h] [rbp-A8h] BYREF
  void *Block[2]; // [rsp+80h] [rbp-98h] BYREF
  __int64 **v78; // [rsp+90h] [rbp-88h] BYREF
  __int64 v79; // [rsp+98h] [rbp-80h] BYREF
  _QWORD *v80; // [rsp+A0h] [rbp-78h] BYREF
  int v81; // [rsp+A8h] [rbp-70h]
  int v82; // [rsp+ACh] [rbp-6Ch]
  void **v83; // [rsp+B0h] [rbp-68h]
  __int64 v84; // [rsp+B8h] [rbp-60h]
  __int64 v85; // [rsp+C0h] [rbp-58h]
  _QWORD *v86; // [rsp+D0h] [rbp-48h]
  BSTR bstrString; // [rsp+128h] [rbp+10h] BYREF
  struct WindowsPerformanceRecorder::CControlManager *v88; // [rsp+130h] [rbp+18h]

  v88 = a3;
  v85 = -2;
  v5 = a3;
  v71 = 0;
  v8 = (**(__int64 (__fastcall ***)(struct IProfileCollection *, GUID *, __int64 *))a2)(
         a2,
         &GUID_cf882c39_ba69_4b60_81d1_8cfa576e7f44,
         &v71);
  if ( v8 < 0 )
    goto LABEL_12;
  v78 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 ***))(*(_QWORD *)v71 + 24LL))(v71, &v78);
  v8 = v9;
  if ( v9 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"Initialize",
      (const char *)0x81,
      v9,
      "COMGUARD",
      v67);
LABEL_12:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
    return (unsigned int)v8;
  }
  v68 = 0;
  (**(void (__fastcall ***)(struct IProfileCollection *, GUID *, __int64 *))a2)(
    a2,
    &GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4,
    &v68);
  if ( !v68 )
  {
    ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
    v8 = -2147467262;
    goto LABEL_12;
  }
  v69 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 96LL))(v68, &v69);
  if ( v8 < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
    ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
    goto LABEL_12;
  }
  v10 = 0;
  v70 = 0;
  if ( v69 )
  {
    (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v69)(v69, &GUID_3aaab089_6481_4c2b_8491_0053d8fd27c7, &v70);
    v10 = v70;
  }
  if ( !v10 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
    ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
    v8 = -2147418113;
    goto LABEL_12;
  }
  v79 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 24LL))(v10, &v79);
  WindowsPerformanceRecorder::CTraceMergePropertyElement::operator=((char *)this + 352, v79);
  if ( v5 )
  {
    bstrString = 0;
    (*(void (__fastcall **)(__int64, BSTR *))(*((_QWORD *)v5 + 23) + 144LL))((__int64)v5 + 184, &bstrString);
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 336, bstrString);
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 344, *((_QWORD *)v5 + 67));
    *((_BYTE *)this + 418) = a4;
    SysFreeString(bstrString);
  }
  v76 = 0;
  std::_Tree<std::_Tmap_traits<unsigned short const *,std::vector<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>,std::less<unsigned short const *>,std::allocator<std::pair<unsigned short const * const,std::vector<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>>>,0>>::_Alloc_sentinel_and_proxy(&v76);
  v74 = 0;
  v75 = 0;
  std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::_Alloc_sentinel_and_proxy(&v74);
  bstrString = (BSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v73 = 0;
  (**(void (__fastcall ***)(struct IProfileCollection *, GUID *, __int64 *))a2)(
    a2,
    &GUID_00383df6_90fc_49c0_b65e_0b585bdfddda,
    &v73);
  if ( v73 )
  {
    v72 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v73 + 40LL))(v73, &v72);
    if ( v12 >= 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&bstrString, v72);
      SysFreeString(v72);
      if ( v73 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      v13 = **v78;
      while ( (__int64 *)v13 != *v78 )
      {
        v73 = 0;
        v37 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v13 + 32) + 24LL))(
                *(_QWORD *)(v13 + 32),
                &v73);
        v38 = v37;
        if ( v37 < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"Initialize",
            (const char *)0xC3,
            v37,
            "COMGUARD",
            v67);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
          std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
          __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
          ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
          return v38;
        }
        v39 = v73;
        if ( !*(_QWORD *)(v73 + 120) )
        {
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
          std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
          __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
          ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
          return 2147549183LL;
        }
        if ( *(_DWORD *)(*((_QWORD *)this + 40) - 16LL) )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append((char *)this + 320, L", ");
          v39 = v73;
        }
        v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        if ( v40 )
        {
          v41 = -1;
          do
            ++v41;
          while ( *(_WORD *)(v40 + 2 * v41) );
        }
        else
        {
          v41 = 0;
        }
        ATL::CSimpleStringT<unsigned short,0>::Append((char *)this + 320, v40, v41);
        v42 = v73;
        v43 = *(char **)(v73 + 40);
        v44 = v74;
        v45 = (_QWORD *)*((_QWORD *)v74 + 1);
        v46 = 0;
        v72 = 0;
        v47 = v74;
        if ( *((_BYTE *)v45 + 25) )
        {
          v48 = v45;
        }
        else
        {
          do
          {
            v48 = v45;
            v86 = v45;
            v49 = (char *)v45[4];
            v50 = v43 - v49;
            do
            {
              v51 = *(unsigned __int16 *)&v49[v50];
              v52 = *(unsigned __int16 *)v49 - v51;
              if ( v52 )
                break;
              v49 += 2;
            }
            while ( v51 );
            if ( v52 >= 0 )
            {
              v46 = 1;
              v47 = v45;
            }
            else
            {
              v46 = 0;
              v45 += 2;
            }
            v45 = (_QWORD *)*v45;
          }
          while ( !*((_BYTE *)v45 + 25) );
        }
        if ( v47[25] )
          goto LABEL_96;
        v53 = (unsigned __int16 *)v43;
        do
        {
          v54 = *(unsigned __int16 *)((char *)v53 + *((_QWORD *)v47 + 4) - (_QWORD)v43);
          v55 = *v53 - v54;
          if ( v55 )
            break;
          ++v53;
        }
        while ( v54 );
        if ( v55 < 0 )
        {
LABEL_96:
          if ( v75 == 0x666666666666666LL )
            std::_Xlength_error("map/set too long");
          v83 = &v74;
          v84 = 0;
          v56 = std::_Allocate<16,std::_Default_allocate_traits>(0x28u);
          v56[4] = v43;
          *v56 = v44;
          v56[1] = v44;
          v56[2] = v44;
          *((_WORD *)v56 + 12) = 0;
          v84 = 0;
          v80 = v48;
          v81 = v46;
          v82 = (int)v72;
          std::_Tree_val<std::_Tree_simple_types<unsigned short>>::_Insert_node(&v74, &v80, v56);
          v42 = v73;
        }
        *((_QWORD *)this + 34) = *(_QWORD *)(v42 + 64);
        *((_DWORD *)this + 64) = *(_DWORD *)(v42 + 28);
        *((_QWORD *)this + 33) = *(_QWORD *)(v42 + 32);
        *((_DWORD *)this + 70) = **(_DWORD **)(v42 + 120);
        std::_Tree<std::_Tset_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,0>>::_Insert_range_unchecked<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,std::_Iterator_base0>>(
          (char *)this + 288,
          **(_QWORD **)(v42 + 80),
          *(_QWORD *)(v42 + 80));
        v59 = v73;
        i = **(_QWORD **)(v73 + 96);
        while ( 1 )
        {
          v72 = (BSTR)i;
          if ( i == *(_QWORD *)(v59 + 96) )
            break;
          v63 = WindowsPerformanceRecorder::CETWProperties::AddCollectorByName(i, &v76, &v72);
          v64 = v63;
          if ( v63 < 0 )
          {
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)2,
              (unsigned __int8)"Initialize",
              (const char *)0xDC,
              v63,
              "COMGUARD",
              v67);
            WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
            std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
            __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
            ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
            return v64;
          }
          v65 = v72;
          v66 = *((_QWORD *)v72 + 2);
          if ( *(_BYTE *)(v66 + 25) )
          {
            for ( i = *((_QWORD *)v72 + 1); !*(_BYTE *)(i + 25) && v65 == *(BSTR *)(i + 16); i = *(_QWORD *)(i + 8) )
              v65 = (BSTR)i;
          }
          else
          {
            i = std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::IProfileElement *>>::_Min(
                  v66,
                  v57,
                  v58);
          }
        }
        v61 = *(_QWORD *)(v13 + 16);
        if ( *(_BYTE *)(v61 + 25) )
        {
          for ( j = *(_QWORD *)(v13 + 8); !*(_BYTE *)(j + 25) && v13 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
            v13 = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::IProfileElement *>>::_Min(
                v61,
                v57,
                v58);
        }
        v13 = j;
        v5 = v88;
      }
      v14 = *(BSTR *)v74;
      v72 = *(BSTR *)v74;
      while ( !*((_BYTE *)v14 + 25) )
      {
        ATL::CSimpleStringT<unsigned short,0>::Append((char *)this + 328, *((_QWORD *)v14 + 4));
        std::_Tree_unchecked_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>::operator++(&v72);
        v14 = v72;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 312,
        L"%ws.%ws.%ws",
        *((_QWORD *)this + 41),
        *((_QWORD *)this + 34),
        *((_QWORD *)this + 33));
      *(_OWORD *)Block = 0;
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,0>>::_Alloc_sentinel_and_proxy(Block);
      v15 = *(__int64 **)v76;
      v16 = bstrString;
      while ( v15 != (__int64 *)v76 )
      {
        v24 = *(_QWORD *)(*(_QWORD *)v15[5] + 32LL);
        v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24) - 3;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( v26 )
          {
            v27 = v26 - 1;
            if ( v27 )
            {
              if ( v27 != 1 )
              {
                std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(Block);
                WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
                std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
                __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
                ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
                return 2147549183LL;
              }
              v28 = WindowsPerformanceRecorder::CETWProperties::AddHypervisorEventCollectors(this);
              v29 = v28;
              if ( v28 < 0 )
              {
                WindowsPerformanceRecorder::TraceHR(
                  (WindowsPerformanceRecorder *)2,
                  (unsigned __int8)"Initialize",
                  (const char *)0x103,
                  v28,
                  "COMGUARD",
                  v67);
                std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(Block);
                WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
                std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
                __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
                ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
                return v29;
              }
            }
          }
          else
          {
            v30 = WindowsPerformanceRecorder::CETWProperties::AddEventCollectors(this, v16, v5, v15 + 5);
            v31 = v30;
            if ( v30 < 0 )
            {
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)2,
                (unsigned __int8)"Initialize",
                (const char *)0xF9,
                v30,
                "COMGUARD",
                v67);
              std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(Block);
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
              std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
              __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
              ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
              return v31;
            }
          }
        }
        else
        {
          v32 = WindowsPerformanceRecorder::CETWProperties::AddSystemCollectors(this, (__int64)(v15 + 5));
          v33 = v32;
          if ( v32 < 0 )
          {
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)2,
              (unsigned __int8)"Initialize",
              (const char *)0xF3,
              v32,
              "COMGUARD",
              v67);
            std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(Block);
            WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
            std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
            __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
            ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
            return v33;
          }
        }
        v34 = (__int64 **)v15[2];
        if ( *((_BYTE *)v34 + 25) )
        {
          for ( k = (__int64 *)v15[1]; !*((_BYTE *)k + 25) && v15 == (__int64 *)k[2]; k = (__int64 *)k[1] )
            v15 = k;
          v15 = k;
        }
        else
        {
          v15 = (__int64 *)v15[2];
          for ( m = *v34; !*((_BYTE *)m + 25); m = (__int64 *)*m )
            v15 = m;
        }
      }
      v17 = *(__int64 **)v76;
      while ( v17 != (__int64 *)v76 )
      {
        v18 = *(_QWORD *)(*(_QWORD *)v17[5] + 32LL);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18) == 5 )
        {
          v19 = WindowsPerformanceRecorder::CETWProperties::AddHeapEventCollectors((int)this, (__int64)Block);
          v20 = v19;
          if ( v19 < 0 )
          {
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)2,
              (unsigned __int8)"Initialize",
              (const char *)0x114,
              v19,
              "COMGUARD",
              v67);
            std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(Block);
            WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
            std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
            __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
            ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
            return v20;
          }
        }
        v21 = (__int64 **)v17[2];
        if ( *((_BYTE *)v21 + 25) )
        {
          for ( n = (__int64 *)v17[1]; !*((_BYTE *)n + 25) && v17 == (__int64 *)n[2]; n = (__int64 *)n[1] )
            v17 = n;
          v17 = n;
        }
        else
        {
          v17 = (__int64 *)v17[2];
          for ( ii = *v21; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
            v17 = ii;
        }
      }
      std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(
        Block,
        Block,
        *((_QWORD *)Block[0] + 1));
      operator delete(Block[0]);
      ATL::CStringData::Release((ATL::CStringData *)(v16 - 12));
      std::_Tree_val<std::_Tree_simple_types<unsigned short const *>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned short const *,void *>>>(
        &v74,
        &v74,
        *((_QWORD *)v74 + 1));
      operator delete(v74);
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,std::vector<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,std::vector<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>>,void *>>>(
        &v76,
        &v76,
        *(_QWORD *)(v76 + 8));
      std::_Deallocate<16>((void *)v76, 0x40u);
      std::_Sort_unchecked<WindowsPerformanceRecorder::CETWProperties::CEventSession * *,bool (*)(WindowsPerformanceRecorder::CETWProperties::CEventSession *,WindowsPerformanceRecorder::CETWProperties::CEventSession *)>(
        *((_QWORD *)this + 1),
        *((_QWORD *)this + 2),
        (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 3,
        WindowsPerformanceRecorder::lessEventSession);
      if ( v70 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      if ( v69 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
      if ( v68 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
      if ( v71 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      return 0;
    }
    else
    {
      SysFreeString(v72);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
      std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
      __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
      ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
      return (unsigned int)v12;
    }
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&bstrString);
    std::_Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___::__Tree_std::_Tset_traits_unsigned_short_const____WindowsPerformanceRecorder::CETWProperties::Initialize_::_24_::lessLPCWSTR_std::allocator_unsigned_short_const____0___(&v74);
    __1___Tree_V___Tmap_traits_PEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std__U__less_PEBG_2_V__allocator_U__pair_QEBGV__vector_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std__V__allocator_V___Tree_const_iterator_V___Tree_val_U___Tree_simple_types_U__pair_QEBVCBaseProfileElement_WindowsPerformanceRecorder__V__set_PEBVCBaseProfileElement_WindowsPerformanceRecorder__U__less_PEBVCBaseProfileElement_WindowsPerformanceRecorder___std__V__allocator_PEBVCBaseProfileElement_WindowsPerformanceRecorder___4__std___std___std___std___std___2__std___std___2__0A__std___std__QEAA_XZ(&v76);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
    ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v68);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18001a92c  mov     rax, rsp
0x18001a92f  mov     [rax+18h], r8
0x18001a933  mov     [rax+8], rcx
0x18001a937  push    rsi
0x18001a938  push    rdi
0x18001a939  push    r12
0x18001a93b  push    r14
0x18001a93d  push    r15
0x18001a93f  sub     rsp, 0F0h
0x18001a946  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x18001a94e  mov     [rax+20h], rbx
0x18001a952  mov     r14b, r9b
0x18001a955  mov     r15, r8
0x18001a958  mov     rdi, rdx
0x18001a95b  mov     rsi, rcx
0x18001a95e  xor     r12d, r12d
0x18001a961  mov     [rsp+118h+var_D0], r12
0x18001a966  mov     rax, [rdx]
0x18001a969  lea     r8, [rsp+118h+var_D0]
0x18001a96e  lea     rdx, _GUID_cf882c39_ba69_4b60_81d1_8cfa576e7f44
0x18001a975  mov     rcx, rdi
0x18001a978  mov     rax, [rax]
0x18001a97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a980  mov     ebx, eax
0x18001a982  test    eax, eax
0x18001a984  js      loc_18001AAA8
0x18001a98a  mov     [rsp+118h+var_88], r12
0x18001a992  mov     rcx, [rsp+118h+var_D0]
0x18001a997  mov     rax, [rcx]
0x18001a99a  lea     rdx, [rsp+118h+var_88]
0x18001a9a2  mov     rax, [rax+18h]
0x18001a9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9ab  mov     ebx, eax
0x18001a9ad  test    eax, eax
0x18001a9af  jns     short loc_18001A9DC
0x18001a9b1  lea     rcx, aComguard; "COMGUARD"
0x18001a9b8  mov     [rsp+118h+Format], rcx; Format
0x18001a9bd  mov     r9d, eax; unsigned int
0x18001a9c0  mov     r8d, 81h; char *
0x18001a9c6  lea     rdx, aInitialize; "Initialize"
0x18001a9cd  lea     ecx, [r12+2]; this
0x18001a9d2  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001a9d7  jmp     loc_18001AAA8
0x18001a9dc  mov     [rsp+118h+var_E8], r12
0x18001a9e1  mov     rax, [rdi]
0x18001a9e4  lea     r8, [rsp+118h+var_E8]
0x18001a9e9  lea     rdx, _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4
0x18001a9f0  mov     rcx, rdi
0x18001a9f3  mov     rax, [rax]
0x18001a9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9fb  nop
0x18001a9fc  mov     rcx, [rsp+118h+var_E8]
0x18001aa01  test    rcx, rcx
0x18001aa04  jnz     short loc_18001AA1A
0x18001aa06  lea     rcx, [rsp+118h+var_E8]
0x18001aa0b  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x18001aa10  mov     ebx, 80004002h
0x18001aa15  jmp     loc_18001AAA8
0x18001aa1a  mov     [rsp+118h+var_E0], r12
0x18001aa1f  mov     rax, [rcx]
0x18001aa22  lea     rdx, [rsp+118h+var_E0]
0x18001aa27  mov     rax, [rax+60h]
0x18001aa2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa30  mov     ebx, eax
0x18001aa32  test    eax, eax
0x18001aa34  jns     short loc_18001AA4D
0x18001aa36  lea     rcx, [rsp+118h+var_E0]
0x18001aa3b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001aa40  nop
0x18001aa41  lea     rcx, [rsp+118h+var_E8]
0x18001aa46  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x18001aa4b  jmp     short loc_18001AAA8
0x18001aa4d  mov     r9, [rsp+118h+var_E0]
0x18001aa52  mov     rcx, r12
0x18001aa55  mov     [rsp+118h+var_D8], rcx
0x18001aa5a  test    r9, r9
0x18001aa5d  jz      short loc_18001AA7E
0x18001aa5f  mov     rax, [r9]
0x18001aa62  lea     r8, [rsp+118h+var_D8]
0x18001aa67  lea     rdx, _GUID_3aaab089_6481_4c2b_8491_0053d8fd27c7
0x18001aa6e  mov     rcx, r9
0x18001aa71  mov     rax, [rax]
0x18001aa74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa79  mov     rcx, [rsp+118h+var_D8]
0x18001aa7e  test    rcx, rcx
0x18001aa81  jnz     short loc_18001AAB9
0x18001aa83  lea     rcx, [rsp+118h+var_D8]
0x18001aa88  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001aa8d  nop
0x18001aa8e  lea     rcx, [rsp+118h+var_E0]
0x18001aa93  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001aa98  nop
0x18001aa99  lea     rcx, [rsp+118h+var_E8]
0x18001aa9e  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x18001aaa3  mov     ebx, 8000FFFFh
0x18001aaa8  lea     rcx, [rsp+118h+var_D0]
0x18001aaad  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001aab2  mov     eax, ebx
0x18001aab4  jmp     loc_18001B72A
0x18001aab9  mov     [rsp+118h+var_80], r12
0x18001aac1  mov     rax, [rcx]
0x18001aac4  lea     rdx, [rsp+118h+var_80]
0x18001aacc  mov     rax, [rax+18h]
0x18001aad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aad5  lea     rcx, [rsi+160h]
0x18001aadc  mov     rdx, [rsp+118h+var_80]
0x18001aae4  call    ??4CTraceMergePropertyElement@WindowsPerformanceRecorder@@QEAAAEAV01@AEBV01@@Z; WindowsPerformanceRecorder::CTraceMergePropertyElement::operator=(WindowsPerformanceRecorder::CTraceMergePropertyElement const &)
0x18001aae9  test    r15, r15
0x18001aaec  jz      short loc_18001AB51
0x18001aaee  mov     [rsp+118h+bstrString], r12
0x18001aaf6  lea     rcx, [r15+0B8h]
0x18001aafd  mov     rax, [rcx]
0x18001ab00  lea     rdx, [rsp+118h+bstrString]
0x18001ab08  mov     rax, [rax+90h]
0x18001ab0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab14  lea     rcx, [rsi+150h]
0x18001ab1b  mov     rdx, [rsp+118h+bstrString]
0x18001ab23  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001ab28  lea     rcx, [rsi+158h]
0x18001ab2f  mov     rdx, [r15+218h]
0x18001ab36  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001ab3b  mov     [rsi+1A2h], r14b
0x18001ab42  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18001ab4a  call    cs:__imp_SysFreeString
0x18001ab50  nop
0x18001ab51  xorps   xmm0, xmm0
0x18001ab54  movdqu  [rsp+118h+var_A8], xmm0
0x18001ab5a  lea     rcx, [rsp+118h+var_A8]
0x18001ab5f  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@U?$less@PEBG@2@V?$allocator@U?$pair@QEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,std::vector<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>,std::less<ushort const *>,std::allocator<std::pair<ushort const * const,std::vector<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001ab64  nop
0x18001ab65  mov     [rsp+118h+var_B8], r12
0x18001ab6a  mov     [rsp+118h+var_B0], r12
0x18001ab6f  lea     rcx, [rsp+118h+var_B8]
0x18001ab74  call    std___Tree_std___Tset_traits_unsigned_short_const____WindowsPerformanceRecorder__CETWProperties__Initialize____24___lessLPCWSTR_std__allocator_unsigned_short_const____0______Alloc_sentinel_and_proxy
0x18001ab79  nop
0x18001ab7a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001ab81  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001ab88  mov     rax, [rax+18h]
0x18001ab8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab91  add     rax, 18h
0x18001ab95  mov     [rsp+118h+bstrString], rax
0x18001ab9d  mov     [rsp+118h+var_C0], r12
0x18001aba2  mov     rax, [rdi]
0x18001aba5  lea     r8, [rsp+118h+var_C0]
0x18001abaa  lea     rdx, _GUID_00383df6_90fc_49c0_b65e_0b585bdfddda
0x18001abb1  mov     rcx, rdi
0x18001abb4  mov     rax, [rax]
0x18001abb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abbc  nop
0x18001abbd  mov     rcx, [rsp+118h+var_C0]
0x18001abc2  test    rcx, rcx
0x18001abc5  jnz     short loc_18001AC2B
0x18001abc7  lea     rcx, [rsp+118h+var_C0]
0x18001abcc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001abd1  nop
0x18001abd2  lea     rcx, [rsp+118h+bstrString]; this
0x18001abda  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001abdf  nop
0x18001abe0  lea     rcx, [rsp+118h+var_B8]
0x18001abe5  call    std___Tree_std___Tset_traits_unsigned_short_const____WindowsPerformanceRecorder__CETWProperties__Initialize____24___lessLPCWSTR_std__allocator_unsigned_short_const____0_______Tree_std___Tset_traits_unsigned_short_const____WindowsPerformanceRecorder__CETWProperties__Initialize____24___lessLPCWSTR_std__allocator_unsigned_short_const____0___
0x18001abea  nop
0x18001abeb  lea     rcx, [rsp+118h+var_A8]
0x18001abf0  call    ??1?$_Tree@V?$_Tmap_traits@PEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@U?$less@PEBG@2@V?$allocator@U?$pair@QEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x18001abf5  nop
0x18001abf6  lea     rcx, [rsp+118h+var_D8]
0x18001abfb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ac00  nop
0x18001ac01  lea     rcx, [rsp+118h+var_E0]
0x18001ac06  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ac0b  nop
0x18001ac0c  lea     rcx, [rsp+118h+var_E8]
0x18001ac11  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x18001ac16  nop
0x18001ac17  lea     rcx, [rsp+118h+var_D0]
0x18001ac1c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ac21  mov     eax, 8000FFFFh
0x18001ac26  jmp     loc_18001B72A
0x18001ac2b  mov     [rsp+118h+var_C8], r12
0x18001ac30  mov     rax, [rcx]
0x18001ac33  lea     rdx, [rsp+118h+var_C8]
0x18001ac38  mov     rax, [rax+28h]
0x18001ac3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac41  mov     ebx, eax
0x18001ac43  test    eax, eax
0x18001ac45  jns     short loc_18001ACB4
0x18001ac47  mov     rcx, [rsp+118h+var_C8]; bstrString
0x18001ac4c  call    cs:__imp_SysFreeString
0x18001ac52  nop
0x18001ac53  lea     rcx, [rsp+118h+var_C0]
0x18001ac58  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ac5d  nop
0x18001ac5e  lea     rcx, [rsp+118h+bstrString]; this
0x18001ac66  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001ac6b  nop
0x18001ac6c  lea     rcx, [rsp+118h+var_B8]
0x18001ac71  call    std___Tree_std___Tset_traits_unsigned_short_const____WindowsPerformanceRecorder__CETWProperties__Initialize____24___lessLPCWSTR_std__allocator_unsigned_short_const____0_______Tree_std___Tset_traits_unsigned_short_const____WindowsPerformanceRecorder__CETWProperties__Initialize____24___lessLPCWSTR_std__allocator_unsigned_short_const____0___
0x18001ac76  nop
0x18001ac77  lea     rcx, [rsp+118h+var_A8]
0x18001ac7c  call    ??1?$_Tree@V?$_Tmap_traits@PEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@U?$less@PEBG@2@V?$allocator@U?$pair@QEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x18001ac81  nop
0x18001ac82  lea     rcx, [rsp+118h+var_D8]
0x18001ac87  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ac8c  nop
0x18001ac8d  lea     rcx, [rsp+118h+var_E0]
0x18001ac92  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ac97  nop
0x18001ac98  lea     rcx, [rsp+118h+var_E8]
0x18001ac9d  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x18001aca2  nop
0x18001aca3  lea     rcx, [rsp+118h+var_D0]
0x18001aca8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001acad  mov     eax, ebx
0x18001acaf  jmp     loc_18001B72A
0x18001acb4  mov     rdx, [rsp+118h+var_C8]
0x18001acb9  lea     rcx, [rsp+118h+bstrString]
0x18001acc1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001acc6  nop
0x18001acc7  mov     rcx, [rsp+118h+var_C8]; bstrString
0x18001accc  call    cs:__imp_SysFreeString
0x18001acd2  nop
0x18001acd3  mov     rcx, [rsp+118h+var_C0]
0x18001acd8  test    rcx, rcx
0x18001acdb  jz      short loc_18001ACEA
0x18001acdd  mov     rax, [rcx]
0x18001ace0  mov     rax, [rax+10h]
0x18001ace4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ace9  nop
0x18001acea  mov     rax, [rsp+118h+var_88]
0x18001acf2  mov     rbx, [rax]
0x18001acf5  mov     rbx, [rbx]
0x18001acf8  mov     rax, [rsp+118h+var_88]
0x18001ad00  cmp     rbx, [rax]
0x18001ad03  jnz     loc_18001B2D7
0x18001ad09  mov     rdx, [rsp+118h+var_B8]
0x18001ad0e  mov     rdx, [rdx]
0x18001ad11  mov     [rsp+118h+var_C8], rdx
0x18001ad16  cmp     [rdx+19h], r12b
0x18001ad1a  jnz     short loc_18001AD3D
0x18001ad1c  lea     rcx, [rsi+148h]
0x18001ad23  mov     rdx, [rdx+20h]
0x18001ad27  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001ad2c  lea     rcx, [rsp+118h+var_C8]
0x18001ad31  call    ??E?$_Tree_unchecked_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>::operator++(void)
0x18001ad36  mov     rdx, [rsp+118h+var_C8]
0x18001ad3b  jmp     short loc_18001AD16
0x18001ad3d  lea     rcx, [rsi+138h]
0x18001ad44  mov     rax, [rsi+108h]
0x18001ad4b  mov     [rsp+118h+Format], rax
0x18001ad50  mov     r9, [rsi+110h]
0x18001ad57  mov     r8, [rsi+148h]
0x18001ad5e  lea     rdx, aWsWsWs_0; "%ws.%ws.%ws"
0x18001ad65  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001ad6a  xorps   xmm0, xmm0
0x18001ad6d  movdqu  xmmword ptr [rsp+118h+Block], xmm0
0x18001ad76  lea     rcx, [rsp+118h+Block]
0x18001ad7e  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001ad83  nop
0x18001ad84  mov     rbx, qword ptr [rsp+118h+var_A8]
0x18001ad89  mov     rbx, [rbx]
0x18001ad8c  mov     rdi, [rsp+118h+bstrString]
0x18001ad94  mov     rax, qword ptr [rsp+118h+var_A8]
0x18001ad99  cmp     rbx, rax
0x18001ad9c  jnz     loc_18001AFE5
0x18001ada2  mov     rbx, [rax]
0x18001ada5  cmp     rbx, qword ptr [rsp+118h+var_A8]
0x18001adaa  jnz     loc_18001AEC0
0x18001adb0  mov     r8, [rsp+118h+Block]
0x18001adb8  mov     r8, [r8+8]
0x18001adbc  lea     rdx, [rsp+118h+Block]
0x18001adc4  lea     rcx, [rsp+118h+Block]
0x18001adcc  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@PEAX@std@@@1@PEAU?$_Tree_node@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>::_Erase_tree<std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>>>(std::allocator<std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *>> &,std::_Tree_node<WindowsPerformanceRecorder::CBaseProfileElement::CStack,void *> *)
0x18001add1  mov     edx, 38h ; '8'
0x18001add6  mov     rcx, [rsp+118h+Block]; Block
0x18001adde  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ade3  nop
0x18001ade4  lea     rcx, [rdi-18h]; this
0x18001ade8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001aded  nop
0x18001adee  mov     r8, [rsp+118h+var_B8]
0x18001adf3  mov     r8, [r8+8]
0x18001adf7  lea     rdx, [rsp+118h+var_B8]
0x18001adfc  lea     rcx, [rsp+118h+var_B8]
0x18001ae01  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEBGPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEBGPEAX@std@@@1@PEAU?$_Tree_node@PEBGPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ushort const *>>::_Erase_tree<std::allocator<std::_Tree_node<ushort const *,void *>>>(std::allocator<std::_Tree_node<ushort const *,void *>> &,std::_Tree_node<ushort const *,void *> *)
0x18001ae06  mov     edx, 28h ; '('
0x18001ae0b  mov     rcx, [rsp+118h+var_B8]; Block
0x18001ae10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ae15  nop
0x18001ae16  mov     r8, qword ptr [rsp+118h+var_A8]
0x18001ae1b  mov     r8, [r8+8]
0x18001ae1f  lea     rdx, [rsp+118h+var_A8]
0x18001ae24  lea     rcx, [rsp+118h+var_A8]
0x18001ae29  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@std@@@std@@PEAX@1@@Z
0x18001ae2e  mov     edx, 40h ; '@'
0x18001ae33  mov     rcx, qword ptr [rsp+118h+var_A8]
0x18001ae38  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ae3d  nop
0x18001ae3e  mov     rdx, [rsi+10h]
0x18001ae42  mov     rcx, [rsi+8]
0x18001ae46  mov     r8, rdx
0x18001ae49  sub     r8, rcx
  ... truncated ...
```
