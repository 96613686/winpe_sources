# WindowsPerformanceRecorder::CETWProperties::AddSystemCollectors(std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>> &,ushort const *,WindowsPerformanceRecorder::CControlManager *,std::vector<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *,std::less<WindowsPerformanceRecorder::CBaseProfileElement const *>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>,std::allocator<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *,std::less<WindowsPerformanceRecorder::CBaseProfileElement const *>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>>>> const &)

- ea: `0x18003d11c`
- end: `0x18003de4e`
- name: `?AddSystemCollectors@CETWProperties@WindowsPerformanceRecorder@@AEAAJAEAV?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@std@@PEBGPEAVCControlManager@2@AEBV?$vector@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@V?$allocator@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@@2@@4@@Z`
- size: `3378`
- prototype: `__int64 __usercall@<rax>(WindowsPerformanceRecorder::CETWProperties *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a92c`

## callees

- `0x180001cc4`
- `0x180001d74`
- `0x180001ffc`
- `0x180002478`
- `0x1800024d0`
- `0x180002568`
- `0x1800026e4`
- `0x180006210`
- `0x18000b540`
- `0x180015e2c`
- `0x18001656c`
- `0x180017d70`
- `0x180018b9c`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001f170`
- `0x180033b98`
- `0x180033c54`
- `0x180035084`
- `0x180035734`
- `0x180036a7c`
- `0x180036aac`
- `0x180037f64`
- `0x180039d24`
- `0x18003d11c`
- `0x1800453b8`
- `0x180045cb4`
- `0x1800464b8`
- `0x18004742c`
- `0x180048a14`
- `0x18004f904`
- `0x1800581cc`
- `0x1800638b0`
- `0x1800644dc`
- `0x180064648`
- `0x18008c010`

## string_xrefs

- `0x18003d226`: `COMGUARD`
- `0x18003d5d0`: `COMGUARD`
- `0x18003d6a4`: `COMGUARD`
- `0x18003db66`: `COMGUARD`
- `0x18003dc27`: `COMGUARD`
- `0x18003dcea`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::AddSystemCollectors(
        WindowsPerformanceRecorder::CETWProperties *this,
        __int64 a2,
        __int64 a3,
        struct WindowsPerformanceRecorder::CControlManager *a4,
        __int64 **a5)
{
  struct WindowsPerformanceRecorder::CControlManager *v5; // r12
  __int64 v6; // rsi
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v8; // rdi
  __int64 v9; // r15
  unsigned __int64 v10; // rbx
  signed int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // edx
  __int64 result; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v15; // rdx
  unsigned __int64 v16; // r14
  int v17; // esi
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v18; // r8
  unsigned int v19; // edx
  int v20; // edx
  unsigned int v21; // r12d
  unsigned int Buffers; // r14d
  unsigned int v23; // ecx
  signed int v24; // eax
  unsigned int v25; // ebx
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v26; // rax
  __int64 v27; // rbx
  signed int v28; // eax
  unsigned int v29; // ebx
  int v30; // r8d
  __int64 *v31; // rcx
  __int64 *v32; // rax
  __int64 **v33; // r10
  __int64 **v34; // rbx
  unsigned int v35; // edx
  unsigned int *v36; // rcx
  struct _TRACE_ENABLE_FLAG_EXT_HEADER *v37; // r14
  char *v38; // r15
  const unsigned __int16 *SessionName; // rax
  const struct _GUID *v40; // r8
  const char *v41; // rax
  _DWORD *v42; // r8
  _DWORD *v43; // r8
  _DWORD *v44; // r8
  _DWORD *v45; // r8
  char *v46; // rsi
  _QWORD *v47; // rbx
  void *v48; // rcx
  __int64 v49; // rcx
  signed int v50; // eax
  unsigned int v51; // ebx
  const unsigned __int16 *v52; // rax
  signed int v53; // eax
  unsigned int v54; // ebx
  const unsigned __int16 *v55; // r8
  signed int v56; // eax
  unsigned int v57; // ebx
  __int64 i; // rsi
  struct IControlErrorInfo *v59; // [rsp+28h] [rbp-120h]
  struct IControlErrorInfo *v60; // [rsp+28h] [rbp-120h]
  struct IControlErrorInfo *v61; // [rsp+28h] [rbp-120h]
  struct IControlErrorInfo *v62; // [rsp+28h] [rbp-120h]
  int v63; // [rsp+40h] [rbp-108h] BYREF
  void *v64; // [rsp+48h] [rbp-100h] BYREF
  __int64 v65; // [rsp+50h] [rbp-F8h]
  char v66[8]; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v67; // [rsp+60h] [rbp-E8h]
  unsigned int v68; // [rsp+68h] [rbp-E0h]
  void *v69[2]; // [rsp+70h] [rbp-D8h] BYREF
  void *v70[2]; // [rsp+80h] [rbp-C8h] BYREF
  void *v71[2]; // [rsp+90h] [rbp-B8h] BYREF
  void *v72[2]; // [rsp+A0h] [rbp-A8h] BYREF
  void *v73[2]; // [rsp+B0h] [rbp-98h] BYREF
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v74; // [rsp+C0h] [rbp-88h] BYREF
  __int64 *v75; // [rsp+C8h] [rbp-80h] BYREF
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v76; // [rsp+D0h] [rbp-78h] BYREF
  _QWORD v77[2]; // [rsp+D8h] [rbp-70h] BYREF
  char v78[8]; // [rsp+E8h] [rbp-60h] BYREF
  void *v79[3]; // [rsp+F0h] [rbp-58h] BYREF
  ATL::CAtlException *v80; // [rsp+108h] [rbp-40h] BYREF

  v79[2] = (void *)-2LL;
  v5 = a4;
  v6 = a3;
  v8 = 0;
  try
  {
    std::map<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::map<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>(&v64);
    std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>(v73);
    std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>(v72);
    std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>(v71);
    std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>(v70);
    std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
    std::set<unsigned long>::set<unsigned long>(v69);
    v68 = 0;
    v30 = 0;
    v31 = *a5;
    v32 = a5[1];
    v77[0] = v32;
    while ( 1 )
    {
      v75 = v31;
      v63 = v30;
      if ( v31 == v32 )
        break;
      v9 = *v31;
      v10 = *(_QWORD *)(*v31 + 32);
      if ( !v8 )
      {
        v76 = 0;
        v11 = WindowsPerformanceRecorder::CETWProperties::CreateSystemSession(
                this,
                v10,
                v6,
                *((unsigned int *)this + 64),
                &v76);
        v12 = v11;
        if ( v11 < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"AddSystemCollectors",
            (const char *)0x270,
            v11,
            "COMGUARD",
            (const char *)v59);
          if ( v76 )
            WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(v76, v13);
          std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
          std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
          std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
          return v12;
        }
        v8 = v76;
        v76 = 0;
        v74 = v8;
        v15 = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)this + 2);
        if ( v15 == *((WindowsPerformanceRecorder::CETWProperties::CEventSession ***)this + 3) )
        {
          std::vector<WindowsPerformanceRecorder::CETWProperties::CEventSession *>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventSession * const &>(
            (char *)this + 8,
            v15,
            &v74);
          v8 = v74;
        }
        else
        {
          *v15 = v8;
          *((_QWORD *)this + 2) += 8LL;
        }
        *(_DWORD *)v8 = 1;
      }
      *((_QWORD *)v8 + 23) = *(_QWORD *)(v10 + 52);
      if ( *(_BYTE *)(v10 + 32) )
      {
        if ( *((_DWORD *)this + 64) == 1 )
        {
          std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
          std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
          std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
          return 2147549183LL;
        }
        *(_DWORD *)(*((_QWORD *)v8 + 1) + 64LL) |= 0x100u;
      }
      v16 = v10 + 16;
      WindowsPerformanceRecorder::CETWProperties::AddQPCDeltaTracking(
        this,
        (const struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *)((v10 + 16)
                                                                                       & ((unsigned __int128)-(__int128)v10 >> 64)),
        v8,
        v5);
      v17 = WindowsPerformanceRecorder::CETWProperties::AddMaxFileSize(
              this,
              (const struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *)((v10 + 16)
                                                                                             & ((unsigned __int128)-(__int128)v10 >> 64)),
              v8);
      if ( v17 < 0 )
      {
LABEL_17:
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
        std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
        std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
        return (unsigned int)v17;
      }
      v19 = *(_DWORD *)((v16 & -(__int64)(v10 != 0)) + 0x34);
      if ( *((_DWORD *)v8 + 50) >= v19 )
        v19 = *((_DWORD *)v8 + 50);
      *((_DWORD *)v8 + 50) = v19;
      v20 = *(_DWORD *)((v16 & -(__int64)(v10 != 0)) + 0x38);
      if ( v20 && *(_DWORD *)((v16 & -(__int64)(v10 != 0)) + 0x3C) )
      {
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
        std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
        std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
        return 3310880301LL;
      }
      *(_DWORD *)(*((_QWORD *)v8 + 1) + 68LL) = v20;
      v17 = WindowsPerformanceRecorder::CETWProperties::AddFlushThreshold(
              (WindowsPerformanceRecorder::CETWProperties *)(v16 & -(__int64)(v10 != 0)),
              (const struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *)(v16
                                                                                             & ((unsigned __int128)-(__int128)v10 >> 64)),
              v18);
      if ( v17 < 0 )
        goto LABEL_17;
      v21 = *(_DWORD *)(v10 + 36);
      Buffers = WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement::get_Buffers((WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *)(v10 + 16));
      v23 = v21;
      if ( v68 >= v21 )
        v23 = v68;
      v68 = v23;
      if ( *((_DWORD *)this + 64) == 1 )
        *((_WORD *)v8 + 102) = *(_WORD *)(v10 + 48);
      *(_DWORD *)(*((_QWORD *)v8 + 1) + 64LL) |= 0x80u;
      if ( Performance::COSVersionInfo::IsWin8AndUp() )
        *(_DWORD *)(*((_QWORD *)v8 + 1) + 64LL) |= 0x2000000u;
      v24 = WindowsPerformanceRecorder::CETWProperties::ConfigEventProviders(this, a4, v8, (_QWORD **)(v9 + 40), 0);
      v25 = v24;
      if ( v24 < 0 )
      {
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          (unsigned __int8)"AddSystemCollectors",
          (const char *)0x2A1,
          v24,
          "COMGUARD",
          (const char *)v59);
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
        std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
        std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
        return v25;
      }
      v26 = **(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v9 + 40);
      v74 = v26;
      while ( !*((_BYTE *)v26 + 25) )
      {
        v27 = *((_QWORD *)v26 + 4);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27) == 56 )
        {
          v28 = WindowsPerformanceRecorder::CETWProperties::AddHardwareCounters(
                  this,
                  (const struct WindowsPerformanceRecorder::CHardwareCounterElement *)v27,
                  a4);
          v29 = v28;
          if ( v28 < 0 )
          {
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)2,
              (unsigned __int8)"AddSystemCollectors",
              (const char *)0x2A8,
              v28,
              "COMGUARD",
              (const char *)v59);
            std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
            std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
            std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
            std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
            std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
            std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
            std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
            return v29;
          }
        }
        else if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27) == 7 )
        {
          if ( !*(_BYTE *)(v27 + 176) )
            *((_BYTE *)v8 + 207) = 0;
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::insert<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>>(
            (__int64 *)v73,
            *(_QWORD *)(v27 + 24),
            *(_QWORD *)(v27 + 32));
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::insert<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>>(
            (__int64 *)v72,
            *(_QWORD *)(v27 + 48),
            *(_QWORD *)(v27 + 56));
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::insert<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>>(
            (__int64 *)v71,
            *(_QWORD *)(v27 + 72),
            *(_QWORD *)(v27 + 80));
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::insert<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>>(
            (__int64 *)v70,
            *(_QWORD *)(v27 + 96),
            *(_QWORD *)(v27 + 104));
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>>>(
            v66,
            **(_QWORD **)(v27 + 120),
            *(_QWORD *)(v27 + 120));
          std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned long>>>>(
            v69,
            **(_QWORD **)(v27 + 136),
            *(_QWORD *)(v27 + 136));
        }
        else if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27) == 8 )
        {
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,0>>::insert<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>>>(
            v66,
            **(_QWORD **)(v27 + 192),
            *(_QWORD *)(v27 + 192));
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v74);
        v26 = v74;
      }
      v30 = v21 * Buffers + v63;
      v31 = v75 + 1;
      v5 = a4;
      v32 = (__int64 *)v77[0];
      v6 = a3;
    }
    v33 = *(__int64 ***)v66;
    v34 = **(__int64 ****)v66;
    v75 = **(__int64 ***)v66;
    while ( v34 != v33 )
    {
      for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
      {
        if ( *((_DWORD *)qword_18009C4B8 + i) == *((unsigned __int16 *)v34 + 20) )
          std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CBaseProfileElement::CStack,std::less<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement::CStack>,0>>::insert<0,0>(
            a2,
            v77);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>,std::_Iterator_base0>::operator++(&v75);
      v34 = (__int64 **)v75;
    }
    v35 = v68;
    *(_DWORD *)(*((_QWORD *)v8 + 1) + 48LL) = v68;
    if ( v35 > 0x400 )
      *((_BYTE *)this + 416) = 1;
    *(_DWORD *)(*((_QWORD *)v8 + 1) + 56LL) = (int)o_ceil_0();
    *(_DWORD *)(*((_QWORD *)v8 + 1) + 52LL) = *(_DWORD *)(*((_QWORD *)v8 + 1) + 56LL);
    v36 = (unsigned int *)*((_QWORD *)v8 + 1);
    v37 = (struct _TRACE_ENABLE_FLAG_EXT_HEADER *)((char *)v36 + *((unsigned __int16 *)v36 + 36));
    v38 = (char *)v36 + *v36;
    if ( v73[1] )
    {
      v63 = 0;
      v42 = (_DWORD *)std::make_pair<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx> &>(
                        (__int64)v78,
                        &v63,
                        v73);
      std::map<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::insert<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>,0>(
        (__int64 *)&v64,
        (__int64)v77,
        v42);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v79);
      if ( v72[1] )
      {
        v63 = 1;
        v43 = (_DWORD *)std::make_pair<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx> &>(
                          (__int64)v78,
                          &v63,
                          v72);
        std::map<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::insert<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>,0>(
          (__int64 *)&v64,
          (__int64)v77,
          v43);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v79);
      }
      if ( v71[1] )
      {
        v63 = 2;
        v44 = (_DWORD *)std::make_pair<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx> &>(
                          (__int64)v78,
                          &v63,
                          v71);
        std::map<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::insert<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>,0>(
          (__int64 *)&v64,
          (__int64)v77,
          v44);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v79);
      }
      if ( v70[1] )
      {
        v63 = 3;
        v45 = (_DWORD *)std::make_pair<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx> &>(
                          (__int64)v78,
                          &v63,
                          v70);
        std::map<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::insert<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>,0>(
          (__int64 *)&v64,
          (__int64)v77,
          v45);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v79);
      }
      v46 = (char *)v8 + 96;
      if ( (void **)((char *)v8 + 96) != &v64 )
      {
        v47 = *(_QWORD **)v46;
        std::_Tree_val<std::_Tree_simple_types<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>,void *>>>(
          (__int64)v8 + 96,
          (__int64)v8 + 96,
          *(_QWORD *)(*(_QWORD *)v46 + 8LL));
        v47[1] = v47;
        *v47 = v47;
        v47[2] = v47;
        *((_QWORD *)v8 + 13) = 0;
        v48 = *(void **)v46;
        *(_QWORD *)v46 = v64;
        v64 = v48;
        v49 = *((_QWORD *)v8 + 13);
        *((_QWORD *)v8 + 13) = v65;
        v65 = v49;
      }
      v50 = WindowsPerformanceRecorder::CETWProperties::AddSystemKeywords(
              (const unsigned __int16 **)this,
              v5,
              v8,
              v37,
              v38,
              (bool *)v8 + 206);
      v51 = v50;
      if ( v50 < 0 )
      {
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          (unsigned __int8)"AddSystemCollectors",
          (const char *)0x2F4,
          v50,
          "COMGUARD",
          (const char *)v60);
        std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
        std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
        std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
        std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
        return v51;
      }
    }
    else if ( v5 )
    {
      SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v8);
      WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(
        v5,
        -984087023,
        v40,
        SessionName,
        *((const unsigned __int16 **)this + 40),
        0);
      v41 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v8);
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)3,
        (unsigned __int8)"AddSystemCollectors",
        (const char *)0x2FC,
        0xC5580611,
        "%ws: %ws",
        v41,
        *((_QWORD *)this + 40));
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
      std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
      std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
      return 3310880273LL;
    }
    if ( v67
      && (v52 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v8),
          v53 = WindowsPerformanceRecorder::CETWProperties::AddSystemStacks(
                  (__int64)this,
                  v5,
                  v52,
                  v37,
                  v38,
                  (__int64 **)v66),
          v54 = v53,
          v53 < 0) )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"AddSystemCollectors",
        (const char *)0x303,
        v53,
        "COMGUARD",
        (const char *)v61);
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
      std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
      std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
      result = v54;
    }
    else if ( v69[1]
           && (v55 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v8),
               v56 = WindowsPerformanceRecorder::CETWProperties::AddSystemPoolTags(
                       (__int64)this,
                       v5,
                       v55,
                       v37,
                       v38,
                       (void ***)v69),
               v57 = v56,
               v56 < 0) )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"AddSystemCollectors",
        (const char *)0x309,
        v56,
        "COMGUARD",
        (const char *)v62);
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
      std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
      std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
      result = v57;
    }
    else
    {
      if ( !*((_WORD *)v37 + 1) )
        *(_DWORD *)(*((_QWORD *)v8 + 1) + 72LL) = 0;
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::~_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>(v69);
      std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(v66);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v70);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v71);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v72);
      std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(v73);
      std::_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<enum WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<enum WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<enum WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(&v64);
      result = 0;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( std::length_error )
  {
    return 2147942414LL;
  }
  catch ( ATL::CAtlException *v80 )
  {
    return *(unsigned int *)v80;
  }
  return result;
}

```

## disassembly

```asm
0x18003d11c  mov     rax, rsp
0x18003d11f  mov     [rax+20h], r9
0x18003d123  mov     [rax+18h], r8
0x18003d127  mov     [rax+10h], rdx
0x18003d12b  push    rbx
0x18003d12c  push    rsi
0x18003d12d  push    rdi
0x18003d12e  push    r12
0x18003d130  push    r13
0x18003d132  push    r14
0x18003d134  push    r15
0x18003d136  sub     rsp, 110h
0x18003d13d  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18003d145  mov     r12, r9
0x18003d148  mov     rsi, r8
0x18003d14b  mov     r13, rcx
0x18003d14e  xor     r14d, r14d
0x18003d151  mov     edi, r14d
0x18003d154  lea     rcx, [rsp+148h+var_100]
0x18003d159  call    ??0?$map@W4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@U?$less@W4SystemKeywordType@WindowsPerformanceRecorder@@@4@V?$allocator@U?$pair@$$CBW4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@@std@@@4@@std@@QEAA@XZ; std::map<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>::map<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>(void)
0x18003d15e  nop
0x18003d15f  lea     rcx, [rsp+148h+var_98]
0x18003d167  call    ??0?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>(void)
0x18003d16c  nop
0x18003d16d  lea     rcx, [rsp+148h+var_A8]
0x18003d175  call    ??0?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>(void)
0x18003d17a  nop
0x18003d17b  lea     rcx, [rsp+148h+var_B8]
0x18003d183  call    ??0?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>(void)
0x18003d188  nop
0x18003d189  lea     rcx, [rsp+148h+var_C8]
0x18003d191  call    ??0?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>(void)
0x18003d196  nop
0x18003d197  lea     rcx, [rsp+148h+var_F0]
0x18003d19c  call    ??0?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(void)
0x18003d1a1  nop
0x18003d1a2  lea     rcx, [rsp+148h+var_D8]
0x18003d1a7  call    ??0?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@QEAA@XZ; std::set<ulong>::set<ulong>(void)
0x18003d1ac  nop
0x18003d1ad  mov     [rsp+148h+var_E0], r14d
0x18003d1b2  mov     r8d, r14d
0x18003d1b5  mov     rax, [rsp+148h+arg_20]
0x18003d1bd  mov     rcx, [rax]
0x18003d1c0  mov     rax, [rax+8]
0x18003d1c4  mov     [rsp+148h+var_70], rax
0x18003d1cc  mov     [rsp+148h+var_80], rcx
0x18003d1d4  mov     [rsp+148h+var_108], r8d
0x18003d1d9  cmp     rcx, rax
0x18003d1dc  jz      loc_18003D850
0x18003d1e2  mov     r15, [rcx]
0x18003d1e5  mov     rbx, [r15+20h]
0x18003d1e9  test    rdi, rdi
0x18003d1ec  jnz     loc_18003D30A
0x18003d1f2  mov     [rsp+148h+var_78], r14
0x18003d1fa  lea     rax, [rsp+148h+var_78]
0x18003d202  mov     [rsp+148h+Format], rax
0x18003d207  mov     r9d, [r13+100h]
0x18003d20e  mov     r8, rsi
0x18003d211  mov     rdx, rbx
0x18003d214  mov     rcx, r13
0x18003d217  call    ?CreateSystemSession@CETWProperties@WindowsPerformanceRecorder@@AEBAJPEBVCSystemCollectorElement@2@PEBGW4__MIDL_IProfile_0001@@PEAPEAUCEventSession@12@@Z; WindowsPerformanceRecorder::CETWProperties::CreateSystemSession(WindowsPerformanceRecorder::CSystemCollectorElement const *,ushort const *,__MIDL_IProfile_0001,WindowsPerformanceRecorder::CETWProperties::CEventSession * *)
0x18003d21c  mov     edi, eax
0x18003d21e  test    eax, eax
0x18003d220  jns     loc_18003D2BF
0x18003d226  lea     rcx, aComguard; "COMGUARD"
0x18003d22d  mov     [rsp+148h+Format], rcx; Format
0x18003d232  mov     r9d, eax; unsigned int
0x18003d235  mov     r8d, 270h; char *
0x18003d23b  lea     rdx, aAddsystemcolle; "AddSystemCollectors"
0x18003d242  mov     ecx, 2; this
0x18003d247  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003d24c  nop
0x18003d24d  mov     rcx, [rsp+148h+var_78]; this
0x18003d255  test    rcx, rcx
0x18003d258  jz      short loc_18003D260
0x18003d25a  call    ??_GCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAAPEAXI@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(uint)
0x18003d25f  nop
0x18003d260  lea     rcx, [rsp+148h+var_D8]
0x18003d265  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x18003d26a  nop
0x18003d26b  lea     rcx, [rsp+148h+var_F0]
0x18003d270  call    ??1?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(void)
0x18003d275  nop
0x18003d276  lea     rcx, [rsp+148h+var_C8]
0x18003d27e  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d283  nop
0x18003d284  lea     rcx, [rsp+148h+var_B8]
0x18003d28c  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d291  nop
0x18003d292  lea     rcx, [rsp+148h+var_A8]
0x18003d29a  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d29f  nop
0x18003d2a0  lea     rcx, [rsp+148h+var_98]
0x18003d2a8  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d2ad  nop
0x18003d2ae  lea     rcx, [rsp+148h+var_100]
0x18003d2b3  call    ??1?$_Tree@V?$_Tmap_traits@W4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@U?$less@W4SystemKeywordType@WindowsPerformanceRecorder@@@4@V?$allocator@U?$pair@$$CBW4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(void)
0x18003d2b8  mov     eax, edi
0x18003d2ba  jmp     loc_18003DE3A
0x18003d2bf  mov     rdi, [rsp+148h+var_78]
0x18003d2c7  mov     [rsp+148h+var_78], r14
0x18003d2cf  mov     [rsp+148h+var_88], rdi
0x18003d2d7  lea     rcx, [r13+8]
0x18003d2db  mov     rdx, [rcx+8]
0x18003d2df  cmp     rdx, [rcx+10h]
0x18003d2e3  jz      short loc_18003D2EF
0x18003d2e5  mov     [rdx], rdi
0x18003d2e8  add     qword ptr [rcx+8], 8
0x18003d2ed  jmp     short loc_18003D304
0x18003d2ef  lea     r8, [rsp+148h+var_88]
0x18003d2f7  call    ??$_Emplace_reallocate@AEBQEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@@?$vector@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@AEAAPEAPEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAPEAU234@AEBQEAU234@@Z; std::vector<WindowsPerformanceRecorder::CETWProperties::CEventSession *>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventSession * const &>(WindowsPerformanceRecorder::CETWProperties::CEventSession * * const,WindowsPerformanceRecorder::CETWProperties::CEventSession * const &)
0x18003d2fc  mov     rdi, [rsp+148h+var_88]
0x18003d304  mov     dword ptr [rdi], 1
0x18003d30a  mov     rax, [rbx+34h]
0x18003d30e  mov     [rdi+0B8h], eax
0x18003d314  shr     rax, 20h
0x18003d318  mov     [rdi+0BCh], eax
0x18003d31e  cmp     [rbx+20h], r14b
0x18003d322  jz      short loc_18003D399
0x18003d324  cmp     dword ptr [r13+100h], 1
0x18003d32c  jnz     short loc_18003D390
0x18003d32e  lea     rcx, [rsp+148h+var_D8]
0x18003d333  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x18003d338  nop
0x18003d339  lea     rcx, [rsp+148h+var_F0]
0x18003d33e  call    ??1?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(void)
0x18003d343  nop
0x18003d344  lea     rcx, [rsp+148h+var_C8]
0x18003d34c  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d351  nop
0x18003d352  lea     rcx, [rsp+148h+var_B8]
0x18003d35a  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d35f  nop
0x18003d360  lea     rcx, [rsp+148h+var_A8]
0x18003d368  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d36d  nop
0x18003d36e  lea     rcx, [rsp+148h+var_98]
0x18003d376  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d37b  nop
0x18003d37c  lea     rcx, [rsp+148h+var_100]
0x18003d381  call    ??1?$_Tree@V?$_Tmap_traits@W4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@U?$less@W4SystemKeywordType@WindowsPerformanceRecorder@@@4@V?$allocator@U?$pair@$$CBW4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(void)
0x18003d386  mov     eax, 8000FFFFh
0x18003d38b  jmp     loc_18003DE3A
0x18003d390  mov     rax, [rdi+8]
0x18003d394  bts     dword ptr [rax+40h], 8
0x18003d399  lea     r14, [rbx+10h]
0x18003d39d  mov     rax, rbx
0x18003d3a0  lea     rcx, [rbx+10h]
0x18003d3a4  neg     rax
0x18003d3a7  sbb     rdx, rdx
0x18003d3aa  and     rdx, rcx; struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *
0x18003d3ad  mov     r9, r12; struct WindowsPerformanceRecorder::CControlManager *
0x18003d3b0  mov     r8, rdi; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18003d3b3  mov     rcx, r13; this
0x18003d3b6  call    ?AddQPCDeltaTracking@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEBVCBaseSystemAndEventCollectorElement@2@PEAUCEventSession@12@PEAVCControlManager@2@@Z; WindowsPerformanceRecorder::CETWProperties::AddQPCDeltaTracking(WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement const *,WindowsPerformanceRecorder::CETWProperties::CEventSession *,WindowsPerformanceRecorder::CControlManager *)
0x18003d3bb  mov     rax, rbx
0x18003d3be  neg     rax
0x18003d3c1  sbb     rdx, rdx
0x18003d3c4  and     rdx, r14; struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *
0x18003d3c7  mov     r8, rdi; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18003d3ca  mov     rcx, r13; this
0x18003d3cd  call    ?AddMaxFileSize@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEBVCBaseSystemAndEventCollectorElement@2@PEAUCEventSession@12@@Z; WindowsPerformanceRecorder::CETWProperties::AddMaxFileSize(WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement const *,WindowsPerformanceRecorder::CETWProperties::CEventSession *)
0x18003d3d2  mov     esi, eax
0x18003d3d4  xor     r12d, r12d
0x18003d3d7  test    eax, eax
0x18003d3d9  jns     short loc_18003D43A
0x18003d3db  lea     rcx, [rsp+148h+var_D8]
0x18003d3e0  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x18003d3e5  nop
0x18003d3e6  lea     rcx, [rsp+148h+var_F0]
0x18003d3eb  call    ??1?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(void)
0x18003d3f0  nop
0x18003d3f1  lea     rcx, [rsp+148h+var_C8]
0x18003d3f9  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d3fe  nop
0x18003d3ff  lea     rcx, [rsp+148h+var_B8]
0x18003d407  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d40c  nop
0x18003d40d  lea     rcx, [rsp+148h+var_A8]
0x18003d415  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d41a  nop
0x18003d41b  lea     rcx, [rsp+148h+var_98]
0x18003d423  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d428  nop
0x18003d429  lea     rcx, [rsp+148h+var_100]
0x18003d42e  call    ??1?$_Tree@V?$_Tmap_traits@W4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@U?$less@W4SystemKeywordType@WindowsPerformanceRecorder@@@4@V?$allocator@U?$pair@$$CBW4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(void)
0x18003d433  mov     eax, esi
0x18003d435  jmp     loc_18003DE3A
0x18003d43a  mov     rax, rbx
0x18003d43d  neg     rax
0x18003d440  sbb     rcx, rcx
0x18003d443  and     rcx, r14
0x18003d446  mov     edx, [rcx+34h]
0x18003d449  mov     eax, [rdi+0C8h]
0x18003d44f  cmp     eax, edx
0x18003d451  cmovnb  edx, eax
0x18003d454  mov     [rdi+0C8h], edx
0x18003d45a  mov     rax, rbx
0x18003d45d  neg     rax
0x18003d460  sbb     rcx, rcx
0x18003d463  and     rcx, r14; this
0x18003d466  mov     edx, [rcx+38h]
0x18003d469  test    edx, edx
0x18003d46b  jz      short loc_18003D4D5
0x18003d46d  cmp     [rcx+3Ch], r12d
0x18003d471  jz      short loc_18003D4D5
0x18003d473  lea     rcx, [rsp+148h+var_D8]
0x18003d478  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x18003d47d  nop
0x18003d47e  lea     rcx, [rsp+148h+var_F0]
0x18003d483  call    ??1?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(void)
0x18003d488  nop
0x18003d489  lea     rcx, [rsp+148h+var_C8]
0x18003d491  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d496  nop
0x18003d497  lea     rcx, [rsp+148h+var_B8]
0x18003d49f  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d4a4  nop
0x18003d4a5  lea     rcx, [rsp+148h+var_A8]
0x18003d4ad  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d4b2  nop
0x18003d4b3  lea     rcx, [rsp+148h+var_98]
0x18003d4bb  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d4c0  nop
0x18003d4c1  lea     rcx, [rsp+148h+var_100]
0x18003d4c6  call    ??1?$_Tree@V?$_Tmap_traits@W4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@U?$less@W4SystemKeywordType@WindowsPerformanceRecorder@@@4@V?$allocator@U?$pair@$$CBW4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(void)
0x18003d4cb  mov     eax, 0C558062Dh
0x18003d4d0  jmp     loc_18003DE3A
0x18003d4d5  mov     rax, [rdi+8]
0x18003d4d9  mov     [rax+44h], edx
0x18003d4dc  mov     rax, rbx
0x18003d4df  neg     rax
0x18003d4e2  sbb     rdx, rdx
0x18003d4e5  and     rdx, r14; struct WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement *
0x18003d4e8  call    ?AddFlushThreshold@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEBVCBaseSystemAndEventCollectorElement@2@PEAUCEventSession@12@@Z; WindowsPerformanceRecorder::CETWProperties::AddFlushThreshold(WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement const *,WindowsPerformanceRecorder::CETWProperties::CEventSession *)
0x18003d4ed  mov     esi, eax
0x18003d4ef  test    eax, eax
0x18003d4f1  jns     short loc_18003D552
0x18003d4f3  lea     rcx, [rsp+148h+var_D8]
0x18003d4f8  call    ??1?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::~_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>(void)
0x18003d4fd  nop
0x18003d4fe  lea     rcx, [rsp+148h+var_F0]
0x18003d503  call    ??1?$set@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@U?$less@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@5@@std@@QEAA@XZ; std::set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>::~set<WindowsPerformanceRecorder::CBaseProfileElement::CStack>(void)
0x18003d508  nop
0x18003d509  lea     rcx, [rsp+148h+var_C8]
0x18003d511  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d516  nop
0x18003d517  lea     rcx, [rsp+148h+var_B8]
0x18003d51f  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d524  nop
0x18003d525  lea     rcx, [rsp+148h+var_A8]
0x18003d52d  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d532  nop
0x18003d533  lea     rcx, [rsp+148h+var_98]
0x18003d53b  call    ??1?$_Tree@V?$_Tset_traits@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>::~_Tree<std::_Tset_traits<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx,std::less<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::allocator<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,0>>(void)
0x18003d540  nop
0x18003d541  lea     rcx, [rsp+148h+var_100]
0x18003d546  call    ??1?$_Tree@V?$_Tmap_traits@W4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@U?$less@W4SystemKeywordType@WindowsPerformanceRecorder@@@4@V?$allocator@U?$pair@$$CBW4SystemKeywordType@WindowsPerformanceRecorder@@V?$set@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@U?$less@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@std@@V?$allocator@UCKeywordEx@CSystemProviderElement@WindowsPerformanceRecorder@@@5@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>::~_Tree<std::_Tmap_traits<WindowsPerformanceRecorder::SystemKeywordType,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>,std::less<WindowsPerformanceRecorder::SystemKeywordType>,std::allocator<std::pair<WindowsPerformanceRecorder::SystemKeywordType const,std::set<WindowsPerformanceRecorder::CSystemProviderElement::CKeywordEx>>>,0>>(void)
0x18003d54b  mov     eax, esi
0x18003d54d  jmp     loc_18003DE3A
0x18003d552  mov     r12d, [rbx+24h]
0x18003d556  mov     rcx, r14; this
0x18003d559  call    ?get_Buffers@CBaseSystemAndEventCollectorElement@WindowsPerformanceRecorder@@QEBAKXZ; WindowsPerformanceRecorder::CBaseSystemAndEventCollectorElement::get_Buffers(void)
0x18003d55e  mov     r14d, eax
0x18003d561  mov     ecx, r12d
0x18003d564  cmp     [rsp+148h+var_E0], r12d
0x18003d569  cmovnb  ecx, [rsp+148h+var_E0]
0x18003d56e  mov     [rsp+148h+var_E0], ecx
0x18003d572  cmp     dword ptr [r13+100h], 1
0x18003d57a  jnz     short loc_18003D587
0x18003d57c  movzx   ecx, word ptr [rbx+30h]
0x18003d580  mov     [rdi+0CCh], cx
0x18003d587  mov     rcx, [rdi+8]
0x18003d58b  bts     dword ptr [rcx+40h], 7
0x18003d590  call    ?IsWin8AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin8AndUp(void)
0x18003d595  xor     ecx, ecx
0x18003d597  test    al, al
0x18003d599  jz      short loc_18003D5A4
0x18003d59b  mov     rax, [rdi+8]
0x18003d59f  bts     dword ptr [rax+40h], 19h
0x18003d5a4  lea     rsi, [r15+28h]
0x18003d5a8  mov     [rsp+148h+Format], rcx; __int64
0x18003d5ad  mov     r9, rsi
0x18003d5b0  mov     r8, rdi; WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18003d5b3  mov     r15, [rsp+148h+arg_18]
0x18003d5bb  mov     rdx, r15; struct WindowsPerformanceRecorder::CControlManager *
0x18003d5be  mov     rcx, r13; this
0x18003d5c1  call    ?ConfigEventProviders@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEAVCControlManager@2@PEAUCEventSession@12@AEBV?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@PEBVCEventCollectorElement@2@@Z; WindowsPerformanceRecorder::CETWProperties::ConfigEventProviders(WindowsPerformanceRecorder::CControlManager *,WindowsPerformanceRecorder::CETWProperties::CEventSession *,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *> const &,WindowsPerformanceRecorder::CEventCollectorElement const *)
0x18003d5c6  mov     ebx, eax
0x18003d5c8  test    eax, eax
0x18003d5ca  jns     loc_18003D656
0x18003d5d0  lea     rcx, aComguard; "COMGUARD"
0x18003d5d7  mov     [rsp+148h+Format], rcx; Format
0x18003d5dc  mov     r9d, eax; unsigned int
0x18003d5df  mov     r8d, 2A1h; char *
0x18003d5e5  lea     rdx, aAddsystemcolle; "AddSystemCollectors"
0x18003d5ec  mov     ecx, 2; this
0x18003d5f1  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003d5f6  nop
0x18003d5f7  lea     rcx, [rsp+148h+var_D8]
  ... truncated ...
```
