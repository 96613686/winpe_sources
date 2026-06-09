# D3D12CoreCreateDevice(IUnknown *,D3D_FEATURE_LEVEL,DeviceConfiguration *,bool,DebugPrintF &,D3D12_LAYER_REGISTRATION const *,unsigned __int64,_GUID const &,void * *)

- ea: `0x18007703c`
- end: `0x1800785d4`
- name: `?D3D12CoreCreateDevice@@YAJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@PEAVDeviceConfiguration@@_NAEAVDebugPrintF@@PEBUD3D12_LAYER_REGISTRATION@@_KAEBU_GUID@@PEAPEAX@Z`
- size: `5528`
- prototype: `__int64 __usercall@<rax>(struct IUnknown *@<rcx>, enum D3D_FEATURE_LEVEL@<edx>, struct DeviceConfiguration *@<r8>, bool@<r9b>, struct DebugPrintF *, const struct D3D12_LAYER_REGISTRATION *, unsigned __int64, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `43`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180029bb4`

## callees

- `0x180003bdc`
- `0x180003c84`
- `0x180004df0`
- `0x1800056d0`
- `0x180006b40`
- `0x180009354`
- `0x18000ab50`
- `0x18000ac4c`
- `0x18000b010`
- `0x18000bb58`
- `0x180017d60`
- `0x1800299a4`
- `0x180029b30`
- `0x18002a750`
- `0x18002a900`
- `0x180035e80`
- `0x18004be7c`
- `0x18004c080`
- `0x18004c164`
- `0x18004c610`
- `0x1800567c8`
- `0x180058b24`
- `0x180059cf0`
- `0x18005a444`
- `0x18005cfa8`
- `0x18005f27c`
- `0x18005fd58`
- `0x180060f60`
- `0x180061400`
- `0x180064b60`
- `0x18007703c`
- `0x1800785dc`
- `0x18007eb04`
- `0x18007f054`
- `0x1800a443c`
- `0x1800a6754`
- `0x1800ba8a0`
- `0x1800bb480`
- `0x1800bc094`
- `0x1800c5b60`
- `0x1800c665c`
- `0x1801032e4`
- `0x180262020`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800774af`
- `msvcp_win!_Mtx_unlock` at `0x1800775b4`
- `msvcp_win!_Mtx_unlock` at `0x18007777f`
- `msvcp_win!_Mtx_unlock` at `0x18007782f`
- `msvcp_win!_Mtx_unlock` at `0x180077a67`
- `msvcp_win!_Mtx_unlock` at `0x1800785a9`
- `msvcp_win!_Mtx_unlock` at `0x1800774af`
- `msvcp_win!_Mtx_unlock` at `0x1800775b4`
- `msvcp_win!_Mtx_unlock` at `0x18007777f`
- `msvcp_win!_Mtx_unlock` at `0x18007782f`
- `msvcp_win!_Mtx_unlock` at `0x180077a67`
- `msvcp_win!_Mtx_unlock` at `0x1800785a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077d21`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077d43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077d65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077d21`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077d43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077d65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180077142`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180077142`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180077138`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180077138`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180077153`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180077153`

## string_xrefs

- `0x180077d39`: `D3D12TranslateCreateDevice`
- `0x1800773ec`: `ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, a singleton device exists, and the factory was configured to disallow returning an existing device.`
- `0x18007795c`: `ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, a singleton device exists, and the factory was configured to disallow returning an existing device.`
- `0x1800774f1`: `ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, a singleton device exists, but the singleton's device configuration is incompatible with the factory's requested configuration.`
- `0x180077984`: `ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, a singleton device exists, but the singleton's device configuration is incompatible with the factory's requested configuration.`
- `0x1800775fb`: `Existing singleton device already removed.`
- `0x180077a81`: `ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, and the factory was configured to disallow creation of a new singleton device.`
- `0x180077abc`: `ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, but the globally-configured D3D12Core cannot be changed, as there are outstanding references to non-device global interfaces like ID3D12DebugController.`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall D3D12CoreCreateDevice(
        struct IUnknown *a1,
        enum D3D_FEATURE_LEVEL a2,
        int **a3,
        char a4,
        struct DebugPrintF *a5,
        const struct D3D12_LAYER_REGISTRATION *a6,
        unsigned __int64 a7,
        const struct _GUID *a8,
        void **a9)
{
  HANDLE CurrentProcess; // rax
  int v13; // edi
  __int64 (__fastcall ***v14)(_QWORD, const struct _GUID *, void **); // rcx
  char v15; // r15
  int (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rcx
  char v17; // di
  std::_Ref_count_base *v18; // rcx
  std::_Ref_count_base *v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // r9
  unsigned int v26; // ebx
  std::_Ref_count_base *v27; // rcx
  std::_Ref_count_base *v28; // rcx
  __int64 v29; // r9
  char v30; // al
  std::_Ref_count_base *v31; // rcx
  int v32; // ecx
  __int64 v33; // rcx
  int v34; // r12d
  HMODULE v35; // rax
  HMODULE v36; // rbx
  __int64 v37; // rax
  __int64 (*ProcAddress)(void); // r12
  FARPROC v39; // r15
  FARPROC v40; // rax
  int v41; // eax
  unsigned __int64 v42; // rbx
  char *v43; // rdi
  unsigned __int64 v44; // rax
  size_t v45; // rbx
  unsigned __int64 v46; // rcx
  unsigned __int64 v47; // rcx
  char *v48; // rax
  size_t v49; // rbx
  void *v50; // rbx
  __int64 v51; // rax
  std::_Ref_count_base *i; // rsi
  _DWORD *v53; // rax
  unsigned __int64 v54; // r15
  unsigned __int64 j; // r12
  unsigned int v56; // r13d
  __int64 v57; // rbx
  unsigned __int64 v58; // rcx
  __int64 v59; // r8
  unsigned __int64 v60; // rdi
  char *v61; // rsi
  unsigned __int64 v62; // rax
  size_t v63; // rdi
  unsigned __int64 v64; // rcx
  char *v65; // rdi
  unsigned __int64 v66; // rcx
  char *v67; // rax
  size_t v68; // rbx
  void *v69; // rbx
  __int64 v70; // rax
  __int64 v71; // r9
  unsigned int *v72; // rbx
  void *v73; // r10
  char *v74; // rsi
  unsigned int *v75; // r11
  unsigned int v76; // edi
  char *v77; // rax
  unsigned int *k; // rdi
  unsigned int v79; // r12d
  char *v80; // rax
  char *v81; // rdi
  unsigned __int64 v82; // rcx
  size_t v83; // rbx
  __int64 v84; // r8
  _DWORD *v85; // rcx
  _DWORD *v86; // r9
  _DWORD *v87; // rdx
  void **v88; // rbx
  int v89; // eax
  void (__fastcall ***v90)(_QWORD, GUID *, HMODULE *); // rcx
  __int64 v91; // rbx
  int v92; // edi
  int v93; // esi
  int v94; // eax
  unsigned int v95; // ebx
  std::_Ref_count_base *v96; // rcx
  int LayeredDevice; // [rsp+60h] [rbp-1F8h] BYREF
  int v98; // [rsp+64h] [rbp-1F4h]
  void *v99[2]; // [rsp+68h] [rbp-1F0h] BYREF
  __int64 v100; // [rsp+78h] [rbp-1E0h]
  __int64 (__fastcall ***v101)(_QWORD, const struct _GUID *, void **); // [rsp+80h] [rbp-1D8h] BYREF
  __int64 v102[2]; // [rsp+88h] [rbp-1D0h] BYREF
  HMODULE hModule; // [rsp+98h] [rbp-1C0h] BYREF
  void *Src[2]; // [rsp+A0h] [rbp-1B8h] BYREF
  __int64 v105; // [rsp+B0h] [rbp-1A8h]
  enum D3D_FEATURE_LEVEL v106; // [rsp+B8h] [rbp-1A0h] BYREF
  __int128 v107; // [rsp+C0h] [rbp-198h] BYREF
  __int64 v108; // [rsp+D0h] [rbp-188h]
  void **v109; // [rsp+D8h] [rbp-180h]
  __int64 v110; // [rsp+E0h] [rbp-178h] BYREF
  const struct D3D12_LAYER_REGISTRATION *v111; // [rsp+E8h] [rbp-170h] BYREF
  __int64 v112; // [rsp+F0h] [rbp-168h] BYREF
  const struct _GUID *v113; // [rsp+F8h] [rbp-160h]
  __int64 v114; // [rsp+100h] [rbp-158h] BYREF
  _QWORD v115[5]; // [rsp+108h] [rbp-150h] BYREF
  _Mtx_t v116; // [rsp+130h] [rbp-128h]
  _QWORD v117[2]; // [rsp+140h] [rbp-118h] BYREF
  __int128 v118; // [rsp+150h] [rbp-108h]
  __int128 v119; // [rsp+160h] [rbp-F8h]
  __int64 v120; // [rsp+170h] [rbp-E8h]
  int v121; // [rsp+178h] [rbp-E0h]
  __int128 v122; // [rsp+180h] [rbp-D8h]
  int v123; // [rsp+190h] [rbp-C8h]
  __int64 v124; // [rsp+198h] [rbp-C0h]
  __int128 v125; // [rsp+1A0h] [rbp-B8h]
  int v126; // [rsp+1B0h] [rbp-A8h]
  _QWORD v127[5]; // [rsp+1C0h] [rbp-98h] BYREF
  int v128; // [rsp+1E8h] [rbp-70h]
  int v129; // [rsp+1ECh] [rbp-6Ch]
  std::_Ref_count_base *v130[2]; // [rsp+1F8h] [rbp-60h] BYREF

  v106 = a2;
  v111 = a6;
  v113 = a8;
  v109 = a9;
  v115[4] = a9;
  if ( a9 )
    *a9 = 0;
  LayeredDevice = 0;
  v116 = (_Mtx_t)&g_Module;
  std::_Mutex_base::lock((std::_Mutex_base *)&g_Module);
  *(_OWORD *)v130 = 0;
  std::shared_ptr<NDXGI::CUMDAdapter>::operator=(&g_TransientState, v130);
  if ( v130[1] )
    std::_Ref_count_base::_Decref(v130[1]);
  if ( qword_180339C58 != qword_180339C60 )
    qword_180339C60 = qword_180339C58;
  qword_180339C50 = (DeviceConfiguration *)a3;
  v114 = 0;
  byte_180339830 = IsApiSetImplemented("ext-ms-win-ntuser-uicontext-ext-l1-1-0")
                && (CurrentProcess = GetCurrentProcess(),
                    (unsigned int)GetProcessUIContextInformation(CurrentProcess, &v114))
                && (_DWORD)v114 == 1;
  dword_180339C3C = v106;
  v110 = qword_180339958;
  v115[0] = &LayeredDevice;
  v115[1] = &v110;
  v115[2] = a9;
  v115[3] = a3;
  v117[0] = 0;
  v117[1] = 0;
  v118 = 0;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  v123 = 1;
  v124 = 0;
  v125 = 0;
  v126 = 0;
  v112 = 0;
  v107 = 0;
  v108 = 0;
  v130[0] = (std::_Ref_count_base *)83;
  std::vector<SupportedVersion>::_Reallocate<0>(&v107, v130);
  LayeredDevice = CCreateDeviceCache::SelectAdapter((CCreateDeviceCache *)v117, a1);
  v13 = *a3[26];
  v98 = v13;
  DeviceConfiguration::UpdateFromBehaviorValues((DeviceConfiguration *)a3);
  v130[0] = (std::_Ref_count_base *)v117[0];
  std::_Tree<std::_Tmap_traits<_LUID,ID3D12Device *,std::less<_LUID>,std::allocator<std::pair<_LUID const,ID3D12Device *>>,0>>::find(
    &qword_180339958,
    &hModule,
    v130);
  if ( hModule == (HMODULE)qword_180339958 )
    v14 = 0;
  else
    v14 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)hModule + 5);
  v101 = v14;
  if ( v14 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v14)[1])(v14);
  if ( LayeredDevice < 0 )
    goto LABEL_215;
  v15 = 0;
  if ( a4 )
  {
    CCreateDeviceCache::SelectSingleAdapterHybridMode((CCreateDeviceCache *)v117, a1);
    v16 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))v101;
    if ( v101
      || qword_180339B48
      && ((*(void (__fastcall **)(__int64, _QWORD, GUID *, __int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **)))(*(_QWORD *)qword_180339B48 + 40LL))(
            qword_180339B48,
            v117[0],
            &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
            &v101),
          (v16 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))v101) != 0) )
    {
      v17 = 0;
      v102[0] = 0;
      if ( (**v16)(v16, &GUID_78dbf87b_f766_422b_a61c_c8c446bdb9ad, v102) >= 0 )
      {
        (*(void (__fastcall **)(__int64, std::_Ref_count_base **))(*(_QWORD *)v102[0] + 24LL))(v102[0], v130);
        if ( ((__int64)v130[0] & 0x40000000) != 0 || *((_BYTE *)a3 + 234) && *((_BYTE *)a3 + 233) )
        {
          v17 = 1;
          v15 = 1;
        }
        else
        {
          if ( (DeviceConfiguration::GetFlags((DeviceConfiguration *)(a3 + 1)) & 1) == 0 )
          {
            DebugPrintF::operator()(
              a5,
              0,
              "ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, a singleton device exists,"
              " and the factory was configured to disallow returning an existing device.");
            ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(v102);
            ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v101);
            if ( (_QWORD)v107 )
            {
              std::_Deallocate<16>(v107, (v108 - v107) & 0xFFFFFFFFFFFFFFF8uLL);
              v107 = 0;
              v108 = 0;
            }
            CCreateDeviceCache::~CCreateDeviceCache((CCreateDeviceCache *)v117);
            lambda_d50afd8fc60b66131f1acc6658d54be0_::operator()(v115);
            g_TransientState = 0;
            v18 = qword_180339C48;
            qword_180339C48 = 0;
            if ( v18 )
              std::_Ref_count_base::_Decref(v18);
            if ( qword_180339C58 != qword_180339C60 )
              qword_180339C60 = qword_180339C58;
LABEL_33:
            qword_180339C50 = 0;
            _Mtx_unlock((_Mtx_t)&g_Module);
            return 2289696822LL;
          }
          v17 = 0;
          v15 = 1;
          if ( (DeviceConfiguration::GetFlags((DeviceConfiguration *)(a3 + 1)) & 2) == 0
            && !SingletonConfigCompatible((__int64)a5, (__int64)a3, v102[0]) )
          {
            DebugPrintF::operator()(
              a5,
              0,
              "ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, a singleton device exists,"
              " but the singleton's device configuration is incompatible with the factory's requested configuration.");
            ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(v102);
            ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v101);
            if ( (_QWORD)v107 )
            {
              std::_Deallocate<16>(v107, (v108 - v107) & 0xFFFFFFFFFFFFFFF8uLL);
              v107 = 0;
              v108 = 0;
            }
            CCreateDeviceCache::~CCreateDeviceCache((CCreateDeviceCache *)v117);
            lambda_d50afd8fc60b66131f1acc6658d54be0_::operator()(v115);
            g_TransientState = 0;
            v20 = qword_180339C48;
            qword_180339C48 = 0;
            if ( v20 )
              std::_Ref_count_base::_Decref(v20);
            if ( qword_180339C58 != qword_180339C60 )
              qword_180339C60 = qword_180339C58;
            goto LABEL_33;
          }
        }
      }
      ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(v102);
      v21 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v101)[37])(v101);
      LayeredDevice = v21;
      if ( v21 < 0 )
      {
        CJournal::RecordJournal(v22, v21, (__int64)"Existing singleton device already removed.", v23, 0);
        if ( LayeredDevice < 0 )
          goto LABEL_215;
      }
      Src[0] = (void *)1;
      v105 = 0;
      Src[1] = &v106;
      if ( (int)(*v101)[13](v101, (const struct _GUID *)2, Src) < 0 )
      {
        CJournal::RecordJournal(v24, -2005270524, (__int64)"Existing singleton device feature level too low", v25, 0);
        LayeredDevice = -2005270524;
      }
      if ( LayeredDevice < 0 )
      {
LABEL_215:
        v88 = v109;
        goto LABEL_216;
      }
      if ( a3 == (int **)&qword_180339978 || v15 && !v17 )
      {
        if ( !v109 )
        {
          ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v101);
          if ( (_QWORD)v107 )
          {
            std::_Deallocate<16>(v107, (v108 - v107) & 0xFFFFFFFFFFFFFFF8uLL);
            v107 = 0;
            v108 = 0;
          }
          CCreateDeviceCache::~CCreateDeviceCache((CCreateDeviceCache *)v117);
          lambda_d50afd8fc60b66131f1acc6658d54be0_::operator()(v115);
          g_TransientState = 0;
          v28 = qword_180339C48;
          qword_180339C48 = 0;
          if ( v28 )
            std::_Ref_count_base::_Decref(v28);
          if ( qword_180339C58 != qword_180339C60 )
            qword_180339C60 = qword_180339C58;
          qword_180339C50 = 0;
          _Mtx_unlock((_Mtx_t)&g_Module);
          return 1;
        }
        v26 = (**v101)(v101, v113, v109);
        ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v101);
        if ( (_QWORD)v107 )
        {
          std::_Deallocate<16>(v107, (v108 - v107) & 0xFFFFFFFFFFFFFFF8uLL);
          v107 = 0;
          v108 = 0;
        }
        CCreateDeviceCache::~CCreateDeviceCache((CCreateDeviceCache *)v117);
        lambda_d50afd8fc60b66131f1acc6658d54be0_::operator()(v115);
        g_TransientState = 0;
        v27 = qword_180339C48;
        qword_180339C48 = 0;
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
        if ( qword_180339C58 != qword_180339C60 )
          qword_180339C60 = qword_180339C58;
LABEL_60:
        qword_180339C50 = 0;
        _Mtx_unlock((_Mtx_t)&g_Module);
        return v26;
      }
      v13 = v98;
    }
    else if ( v110 == qword_180339958
           && v109
           && (DeviceConfiguration::GetFlags((DeviceConfiguration *)(a3 + 1)) & 4) == 0 )
    {
      v130[0] = 0;
      hModule = (HMODULE)v117[0];
      std::_Tree<std::_Tmap_traits<_LUID,ID3D12Device *,std::less<_LUID>,std::allocator<std::pair<_LUID const,ID3D12Device *>>,0>>::_Emplace<_LUID,std::nullptr_t>(
        &qword_180339958,
        v102,
        &hModule,
        v130);
      v110 = v102[0];
    }
  }
  if ( LayeredDevice < 0 )
    goto LABEL_215;
  LayeredDevice = CCreateDeviceCache::ResolveUMDAndVersion((CCreateDeviceCache *)v117, (__int64)&v112);
  if ( LayeredDevice == -2005270523 )
    ThrowFailure(-2005270523);
  if ( v15 )
    goto LABEL_99;
  v30 = (unsigned __int64)v112 >= 0xC005000620000LL;
  if ( *((_BYTE *)a3 + 234) )
    v30 = *((_BYTE *)a3 + 233);
  if ( v30 )
  {
LABEL_99:
    if ( a3 != (int **)&qword_180339978 && v110 != qword_180339958 )
    {
      std::_Tree<std::_Tmap_traits<_LUID,ID3D12Device *,std::less<_LUID>,std::allocator<std::pair<_LUID const,ID3D12Device *>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_LUID const,ID3D12Device *>>>>,0>(
        &qword_180339958,
        v130);
      v110 = qword_180339958;
    }
  }
  else
  {
    if ( !v101 )
    {
      if ( (DeviceConfiguration::GetFlags((DeviceConfiguration *)(a3 + 1)) & 4) != 0 )
      {
        DebugPrintF::operator()(
          a5,
          0,
          "ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, and the factory was configured"
          " to disallow creation of a new singleton device.");
        v32 = -2005270524;
      }
      else
      {
        if ( !qword_180339B48
          || !(*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)qword_180339B48 + 56LL))(
                qword_180339B48,
                &qword_180339B30) )
        {
          goto LABEL_101;
        }
        DebugPrintF::operator()(
          a5,
          0,
          "ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, but the globally-configured D3"
          "D12Core cannot be changed, as there are outstanding references to non-device global interfaces like ID3D12DebugController.");
        v32 = -2005008381;
      }
      ThrowFailure(v32);
      goto LABEL_101;
    }
    if ( a4 )
    {
      if ( (DeviceConfiguration::GetFlags((DeviceConfiguration *)(a3 + 1)) & 1) == 0 )
      {
        DebugPrintF::operator()(
          a5,
          0,
          "ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, a singleton device exists, and"
          " the factory was configured to disallow returning an existing device.");
        ThrowFailure(-2005270474);
      }
      if ( (DeviceConfiguration::GetFlags((DeviceConfiguration *)(a3 + 1)) & 2) == 0 )
      {
        DebugPrintF::operator()(
          a5,
          0,
          "ID3D12DeviceFactory::CreateDevice: Driver does not support independent devices, a singleton device exists, but"
          " the singleton's device configuration is incompatible with the factory's requested configuration.");
        ThrowFailure(-2005270474);
      }
      v26 = (**v101)(v101, v113, v109);
      ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v101);
      if ( (_QWORD)v107 )
      {
        std::_Deallocate<16>(v107, (v108 - v107) & 0xFFFFFFFFFFFFFFF8uLL);
        v107 = 0;
        v108 = 0;
      }
      CCreateDeviceCache::~CCreateDeviceCache((CCreateDeviceCache *)v117);
      lambda_d50afd8fc60b66131f1acc6658d54be0_::operator()(v115);
      g_TransientState = 0;
      v31 = qword_180339C48;
      qword_180339C48 = 0;
      if ( v31 )
        std::_Ref_count_base::_Decref(v31);
      if ( qword_180339C58 != qword_180339C60 )
        qword_180339C60 = qword_180339C58;
      goto LABEL_60;
    }
  }
LABEL_101:
  if ( LayeredDevice < 0 )
    goto LABEL_215;
  v33 = (unsigned int)(v123 - 1);
  if ( v123 == 1 )
  {
    v34 = 256;
  }
  else
  {
    v33 = (unsigned int)(v123 - 2);
    if ( v123 == 2 )
    {
      v34 = 4096;
    }
    else
    {
      v33 = (unsigned int)(v123 - 10);
      if ( v123 == 10 )
      {
LABEL_109:
        v34 = 45056;
        goto LABEL_116;
      }
      v33 = (unsigned int)(v123 - 11);
      if ( v123 == 11 )
      {
        v34 = 45312;
      }
      else
      {
        v33 = (unsigned int)(v123 - 12);
        if ( v123 == 12 )
        {
          v34 = 49152;
        }
        else
        {
          v33 = (unsigned int)(v123 - 13);
          if ( v123 == 13 )
          {
            v34 = 49408;
          }
          else
          {
            if ( v123 != 14 )
              goto LABEL_109;
            v34 = 49664;
          }
        }
      }
    }
  }
LABEL_116:
  v98 = v34;
  if ( v34 < v106 )
  {
    LayeredDevice = -2005270524;
    CJournal::RecordJournal(v33, -2005270524, (__int64)"Hardware feature level not high enough", v29, 0);
  }
  if ( LayeredDevice < 0 )
    goto LABEL_215;
  *(_OWORD *)v99 = 0;
  v100 = 0;
  *(_OWORD *)Src = 0;
  v105 = 0;
  std::vector<unsigned int>::reserve(v99, 10);
  std::vector<unsigned int>::reserve(Src, 10);
  LayeredDevice = D3D12CoreRegisterLayers(v111, a7);
  ThrowFailure(LayeredDevice);
  LayeredDevice = D3D12CoreRegisterLayers(&qword_180271540, 2);
  ThrowFailure(LayeredDevice);
  LODWORD(v102[0]) = -1;
  std::vector<unsigned int>::push_back(Src, v102);
  hModule = 0;
  v102[0] = 0;
  if ( (!(unsigned int)GetBehaviorValue("RequireSDKLayers", v102) || !v102[0]) && !v13 )
    goto LABEL_155;
  v35 = CModule::SDKLoadLibrary((__int64)&g_Module, 0);
  D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)&hModule, v35);
  v36 = hModule;
  if ( !hModule )
  {
    if ( v13 )
      ThrowFailure(-2005270483);
    if ( *((_BYTE *)a3 + 24) )
    {
      v37 = *(_QWORD *)qword_180339958;
      v102[0] = *(_QWORD *)qword_180339958;
      while ( !*(_BYTE *)(v37 + 25) )
      {
        NDXGI::CDevice::RemoveDevice(*(NDXGI::CDevice **)(*(_QWORD *)(v37 + 40) + 760LL), -2005270521);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_LUID const,ID3D12Device *>>>,std::_Iterator_base0>::operator++(v102);
        v37 = v102[0];
      }
    }
    *((_DWORD *)a3 + 40) = 0;
    goto LABEL_155;
  }
  ProcAddress = GetProcAddress(hModule, "D3D12RegisterLayers");
  if ( !ProcAddress )
    ThrowFailure(-2147467259);
  v39 = GetProcAddress(v36, "D3D12TranslateCreateDevice");
  if ( !v39 )
    ThrowFailure(-2147467259);
  v40 = GetProcAddress(v36, "SetD3DDebugLayerStartupOptions");
  if ( v40 )
  {
    v41 = ((__int64 (__fastcall *)(int **, __int64))v40)(a3 + 20, 48);
    ThrowFailure(v41);
  }
  v42 = (signed __int64)(v100 - (unsigned __int64)v99[0]) >> 2;
  v43 = (char *)v99[1];
  v44 = ((char *)v99[1] - (char *)v99[0]) >> 2;
  if ( v42 >= v44 )
  {
    if ( v42 <= v44 )
      goto LABEL_141;
LABEL_139:
    v45 = 4 * (v42 - v44);
    memset_0(v43, 0, v45);
    v43 += v45;
  }
  else
  {
    v43 = (char *)v99[0] + 4 * v42;
  }
LABEL_140:
  v99[1] = v43;
LABEL_141:
  while ( 1 )
  {
    v102[0] = (v43 - (char *)v99[0]) >> 2;
    LayeredDevice = ((__int64 (__fastcall *)(_QWORD, __int64 *))v39)((unsigned int)*a3[26], v102);
    v43 = (char *)v99[1];
    if ( LayeredDevice != -2147024774 )
      break;
    v46 = (signed __int64)(v100 - (unsigned __int64)v99[0]) >> 2;
    v42 = 2 * v46;
    v44 = ((char *)v99[1] - (char *)v99[0]) >> 2;
    if ( 2 * v46 < v44 )
    {
      v43 = (char *)v99[0] + 8 * v46;
      goto LABEL_140;
    }
    if ( 2 * v46 > v44 )
    {
      if ( v42 <= v46 )
        goto LABEL_139;
      std::vector<enum DXGI_FORMAT>::_Resize_reallocate<std::_Value_init_tag>(v99, 2 * v46);
      v43 = (char *)v99[1];
    }
  }
  v47 = ((char *)v99[1] - (char *)v99[0]) >> 2;
  if ( v102[0] < v47 )
  {
    v48 = (char *)v99[0] + 4 * v102[0];
LABEL_153:
    v99[1] = v48;
    goto LABEL_154;
  }
  if ( v102[0] > v47 )
  {
    if ( v102[0] <= (unsigned __int64)((signed __int64)(v100 - (unsigned __int64)v99[0]) >> 2) )
    {
      v49 = 4 * (v102[0] - v47);
      memset_0(v99[1], 0, v49);
      v48 = &v43[v49];
      goto LABEL_153;
    }
    std::vector<enum DXGI_FORMAT>::_Resize_reallocate<std::_Value_init_tag>(v99, v102[0]);
  }
LABEL_154:
  ThrowFailure(LayeredDevice);
  std::vector<unsigned int>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>,0>(
    (unsigned int)Src,
    (unsigned int)&v111,
    Src[1],
    v99[0],
    (__int64)v99[1]);
  LayeredDevice = ProcAddress();
  ThrowFailure(LayeredDevice);
LABEL_155:
  std::_Sort_unchecked<unsigned int *,std::less<void>>(Src[0]);
  v50 = Src[1];
  v51 = _std_unique_4(Src[0], Src[1]);
  std::vector<unsigned int>::erase(Src, &v111, v51, v50);
  for ( i = 0; ; i = (std::_Ref_count_base *)v54 )
  {
    v130[0] = i;
    v53 = Src[0];
    v54 = ((char *)Src[1] - (char *)Src[0]) >> 2;
    if ( i == (std::_Ref_count_base *)v54 )
      break;
    for ( j = (unsigned __int64)i; j < v54; ++j )
    {
      v56 = v53[j];
      v57 = qword_180339C58;
      v58 = (qword_180339C60 - qword_180339C58) >> 5;
      while ( (__int64)v58 > 0 )
      {
        v59 = 32 * (v58 >> 1);
        if ( *(_DWORD *)(v59 + v57) >= v56 )
        {
          v58 >>= 1;
        }
        else
        {
          v57 += v59 + 32;
          v58 += -1LL - (v58 >> 1);
        }
      }
      if ( v57 == qword_180339C60 || *(_DWORD *)v57 != v56 )
        ThrowFailure(-2147024809);
      v60 = (signed __int64)(v100 - (unsigned __int64)v99[0]) >> 2;
      v61 = (char *)v99[1];
      v62 = ((char *)v99[1] - (char *)v99[0]) >> 2;
      if ( v60 >= v62 )
      {
        if ( v60 <= v62 )
          goto LABEL_172;
LABEL_170:
        v63 = 4 * (v60 - v62);
        memset_0(v61, 0, v63);
        v61 += v63;
      }
      else
      {
        v61 = (char *)v99[0] + 4 * v60;
      }
LABEL_171:
      v99[1] = v61;
LABEL_172:
      while ( 1 )
      {
        v102[0] = (v61 - (char *)v99[0]) >> 2;
        LayeredDevice = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v57 + 8))(v56, v102);
        if ( LayeredDevice != -2147024774 )
          break;
        v64 = (signed __int64)(v100 - (unsigned __int64)v99[0]) >> 2;
        v60 = 2 * v64;
        v61 = (char *)v99[1];
        v62 = ((char *)v99[1] - (char *)v99[0]) >> 2;
        if ( 2 * v64 < v62 )
        {
          v61 = (char *)v99[0] + 8 * v64;
          goto LABEL_171;
        }
        if ( 2 * v64 > v62 )
        {
          if ( v60 <= v64 )
            goto LABEL_170;
          std::vector<enum DXGI_FORMAT>::_Resize_reallocate<std::_Value_init_tag>(v99, v60);
          v61 = (char *)v99[1];
        }
      }
      v65 = (char *)v99[1];
      v66 = ((char *)v99[1] - (char *)v99[0]) >> 2;
      if ( v102[0] >= v66 )
      {
        if ( v102[0] <= v66 )
          goto LABEL_185;
        if ( v102[0] > (unsigned __int64)((signed __int64)(v100 - (unsigned __int64)v99[0]) >> 2) )
        {
          std::vector<enum DXGI_FORMAT>::_Resize_reallocate<std::_Value_init_tag>(v99, v102[0]);
          goto LABEL_185;
        }
        v68 = 4 * (v102[0] - v66);
        memset_0(v99[1], 0, v68);
        v67 = &v65[v68];
      }
      else
      {
        v67 = (char *)v99[0] + 4 * v102[0];
      }
      v99[1] = v67;
LABEL_185:
      ThrowFailure(LayeredDevice);
      std::vector<unsigned int>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>,0>(
        (unsigned int)Src,
        (unsigned int)&v111,
        Src[1],
        v99[0],
        (__int64)v99[1]);
      v53 = Src[0];
    }
    std::_Sort_unchecked<unsigned int *,std::less<void>>(&v53[v54]);
    v69 = Src[1];
    v70 = _std_unique_4((char *)Src[0] + 4 * v54, Src[1]);
    std::vector<unsigned int>::erase(Src, v102, v70, v69);
    LOBYTE(v71) = 0;
    std::inplace_merge<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>,std::less<void>>(
      Src[0],
      (char *)Src[0] + 4 * (__int64)v130[0],
      (char *)Src[0] + 4 * v54,
      v71);
    v72 = (unsigned int *)Src[1];
    v73 = Src[0];
    v74 = (char *)Src[0] + 4 * v54;
    v75 = (unsigned int *)v74;
    if ( v74 != Src[1] )
    {
      do
      {
        v76 = *v75;
        LODWORD(v102[0]) = *v75;
        v77 = (char *)std::lower_bound<unsigned int *,unsigned int,std::less<void>>(v73, v74, v102);
        if ( v77 != v74 && v76 >= *(_DWORD *)v77 )
          break;
        ++v75;
      }
      while ( v75 != v72 );
    }
    if ( v75 != v72 )
    {
      for ( k = v75 + 1; k != v72; ++k )
      {
        v79 = *k;
        LODWORD(v102[0]) = *k;
        v80 = (char *)std::lower_bound<unsigned int *,unsigned int,std::less<void>>(v73, v74, v102);
        if ( v80 == v74 || v79 < *(_DWORD *)v80 )
          *v75++ = v79;
      }
    }
    std::vector<unsigned int>::erase(Src, v130, v75, v72);
  }
  v81 = (char *)v99[1];
  v82 = ((char *)v99[1] - (char *)v99[0]) >> 2;
  if ( v54 >= v82 )
  {
    if ( v54 > v82 )
    {
      if ( v54 <= (signed __int64)(v100 - (unsigned __int64)v99[0]) >> 2 )
      {
        v83 = 4 * (v54 - v82);
        memset_0(v99[1], 0, v83);
        v99[1] = &v81[v83];
      }
      else
      {
        std::vector<enum DXGI_FORMAT>::_Resize_reallocate<std::_Value_init_tag>(
          v99,
          ((char *)Src[1] - (char *)Src[0]) >> 2);
      }
      v53 = Src[0];
    }
  }
  else
  {
    v99[1] = (char *)v99[0] + 4 * v54;
  }
  v84 = qword_180339C58;
  v85 = (_DWORD *)qword_180339C58;
  v86 = Src[1];
  v87 = v99[0];
  while ( v53 != v86 )
  {
    while ( *v85 != *v53 )
      v85 += 8;
    *v87 = ((__int64)v85 - v84) >> 5;
    v85 += 8;
    ++v53;
    ++v87;
  }
  v88 = v109;
  if ( v109 )
  {
    v129 = 0;
    v127[0] = 0;
    v127[1] = 0;
    v127[2] = Src[0];
    v127[3] = v99[0];
    v127[4] = v112;
    v128 = v98;
    LayeredDevice = D3D12CoreCreateLayeredDevice((unsigned int)v127, 48, 0, (_DWORD)v113, (__int64)v109);
    ThrowFailure(LayeredDevice);
    hModule = 0;
    v89 = 0;
  }
  else
  {
    v89 = 1;
  }
  LayeredDevice = v89;
  D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)&hModule, 0);
  std::vector<enum DXGI_FORMAT>::_Tidy(Src);
  std::vector<enum DXGI_FORMAT>::_Tidy(v99);
LABEL_216:
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v101);
  if ( (_QWORD)v107 )
    std::_Deallocate<16>(v107, (v108 - v107) & 0xFFFFFFFFFFFFFFF8uLL);
  if ( LayeredDevice >= 0 )
  {
    if ( v88 )
    {
      v90 = (void (__fastcall ***)(_QWORD, GUID *, HMODULE *))*v88;
      if ( *v88 )
      {
        hModule = 0;
        (**v90)(v90, &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae, &hModule);
        v91 = *(_QWORD *)(*((_QWORD *)hModule + 95) + 40LL);
        v92 = *((_DWORD *)hModule + 140);
        v93 = *(_DWORD *)(v91 + 592);
        v94 = (*(__int64 (__fastcall **)(void *))(qword_180339B30 + 56LL))(&qword_180339B30);
        CD3D12TelemetryHelper::LogCreateDeviceEvent(
          *((_QWORD *)hModule + 95),
          hModule,
          hModule + 718,
          (unsigned int)v106,
          *((_DWORD *)hModule + 362),
          *((_QWORD *)hModule + 843),
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)hModule + 95) + 40LL) + 560LL),
          hModule + 718,
          v94,
          v93,
          v92,
          v91);
        ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(&hModule);
      }
    }
  }
  v95 = LayeredDevice;
  CCreateDeviceCache::~CCreateDeviceCache((CCreateDeviceCache *)v117);
  lambda_d50afd8fc60b66131f1acc6658d54be0_::operator()(v115);
  g_TransientState = 0;
  v96 = qword_180339C48;
  qword_180339C48 = 0;
  if ( v96 )
    std::_Ref_count_base::_Decref(v96);
  if ( qword_180339C58 != qword_180339C60 )
    qword_180339C60 = qword_180339C58;
  qword_180339C50 = 0;
  _Mtx_unlock(v116);
  return v95;
}

```

## disassembly

```asm
0x18007703c  push    rbx
0x18007703e  push    rsi
0x18007703f  push    rdi
0x180077040  push    r12
0x180077042  push    r13
0x180077044  push    r14
0x180077046  push    r15
0x180077048  sub     rsp, 220h
0x18007704f  mov     rax, cs:__security_cookie
0x180077056  xor     rax, rsp
0x180077059  mov     [rsp+258h+var_48], rax
0x180077061  mov     r13b, r9b
0x180077064  mov     rsi, r8
0x180077067  mov     rbx, rcx
0x18007706a  mov     [rsp+258h+var_1A0], edx
0x180077071  mov     r12, [rsp+258h+arg_20]
0x180077079  mov     rax, [rsp+258h+arg_28]
0x180077081  mov     [rsp+258h+var_170], rax
0x180077089  mov     rax, [rsp+258h+arg_38]
0x180077091  mov     [rsp+258h+var_160], rax
0x180077099  mov     rdi, [rsp+258h+arg_40]
0x1800770a1  mov     [rsp+258h+var_180], rdi
0x1800770a9  mov     [rsp+258h+var_130], rdi
0x1800770b1  xor     r14d, r14d
0x1800770b4  test    rdi, rdi
0x1800770b7  jz      short loc_1800770BC
0x1800770b9  mov     [rdi], r14
0x1800770bc  mov     [rsp+258h+var_1F8], r14d
0x1800770c1  lea     rax, ?g_Module@@3VCModule@@A; CModule g_Module
0x1800770c8  mov     [rsp+258h+var_128], rax
0x1800770d0  mov     rcx, rax; this
0x1800770d3  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800770d8  nop
0x1800770d9  xorps   xmm0, xmm0
0x1800770dc  movdqu  xmmword ptr [rsp+258h+var_60], xmm0
0x1800770e5  lea     rdx, [rsp+258h+var_60]
0x1800770ed  lea     rcx, ?g_TransientState@@3UGlobalTransientState@@A; GlobalTransientState g_TransientState
0x1800770f4  call    ??4?$shared_ptr@VCUMDAdapter@NDXGI@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<NDXGI::CUMDAdapter>::operator=(std::shared_ptr<NDXGI::CUMDAdapter> &&)
0x1800770f9  mov     rcx, [rsp+258h+var_60+8]; this
0x180077101  test    rcx, rcx
0x180077104  jz      short loc_18007710B
0x180077106  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007710b  mov     rax, cs:qword_180339C58
0x180077112  cmp     rax, cs:qword_180339C60
0x180077119  jz      short loc_180077122
0x18007711b  mov     cs:qword_180339C60, rax
0x180077122  mov     cs:qword_180339C50, rsi
0x180077129  mov     [rsp+258h+var_158], r14
0x180077131  lea     rcx, Contract; "ext-ms-win-ntuser-uicontext-ext-l1-1-0"
0x180077138  call    cs:__imp_IsApiSetImplemented
0x18007713e  test    eax, eax
0x180077140  jz      short loc_180077173
0x180077142  call    cs:__imp_GetCurrentProcess
0x180077148  mov     rcx, rax
0x18007714b  lea     rdx, [rsp+258h+var_158]
0x180077153  call    cs:__imp_GetProcessUIContextInformation
0x180077159  test    eax, eax
0x18007715b  jz      short loc_180077173
0x18007715d  mov     ecx, 1
0x180077162  cmp     dword ptr [rsp+258h+var_158], ecx
0x180077169  jnz     short loc_180077178
0x18007716b  mov     cs:byte_180339830, cl
0x180077171  jmp     short loc_18007717F
0x180077173  mov     ecx, 1
0x180077178  mov     cs:byte_180339830, r14b
0x18007717f  mov     eax, [rsp+258h+var_1A0]
0x180077186  mov     cs:dword_180339C3C, eax
0x18007718c  mov     rax, cs:qword_180339958
0x180077193  mov     [rsp+258h+var_178], rax
0x18007719b  lea     rax, [rsp+258h+var_1F8]
0x1800771a0  mov     [rsp+258h+var_150], rax
0x1800771a8  lea     rax, [rsp+258h+var_178]
0x1800771b0  mov     [rsp+258h+var_148], rax
0x1800771b8  mov     [rsp+258h+var_140], rdi
0x1800771c0  mov     [rsp+258h+var_138], rsi
0x1800771c8  xor     eax, eax
0x1800771ca  mov     [rsp+258h+var_118], rax
0x1800771d2  mov     [rsp+258h+var_110], r14
0x1800771da  xorps   xmm0, xmm0
0x1800771dd  movdqa  [rsp+258h+var_108], xmm0
0x1800771e6  xorps   xmm1, xmm1
0x1800771e9  movdqa  [rsp+258h+var_F8], xmm1
0x1800771f2  mov     [rsp+258h+var_E8], r14
0x1800771fa  mov     [rsp+258h+var_E0], r14d
0x180077202  movdqa  [rsp+258h+var_D8], xmm0
0x18007720b  mov     [rsp+258h+var_C8], ecx
0x180077212  mov     [rsp+258h+var_C0], r14
0x18007721a  movdqa  [rsp+258h+var_B8], xmm0
0x180077223  mov     [rsp+258h+var_A8], r14d
0x18007722b  mov     [rsp+258h+var_168], r14
0x180077233  movdqu  [rsp+258h+var_198], xmm0
0x18007723c  mov     [rsp+258h+var_188], r14
0x180077244  mov     [rsp+258h+var_60], 53h ; 'S'
0x180077250  lea     rdx, [rsp+258h+var_60]
0x180077258  lea     rcx, [rsp+258h+var_198]
0x180077260  call    ??$_Reallocate@$0A@@?$vector@USupportedVersion@@V?$allocator@USupportedVersion@@@std@@@std@@AEAAXAEA_K@Z; std::vector<SupportedVersion>::_Reallocate<0>(unsigned __int64 &)
0x180077265  mov     rdx, rbx; struct IUnknown *
0x180077268  lea     rcx, [rsp+258h+var_118]; this
0x180077270  call    ?SelectAdapter@CCreateDeviceCache@@QEAAJPEAUIUnknown@@@Z; CCreateDeviceCache::SelectAdapter(IUnknown *)
0x180077275  mov     [rsp+258h+var_1F8], eax
0x180077279  mov     rax, [rsi+0D0h]
0x180077280  mov     edi, [rax]
0x180077282  mov     [rsp+258h+var_1F4], edi
0x180077286  mov     rcx, rsi; this
0x180077289  call    ?UpdateFromBehaviorValues@DeviceConfiguration@@QEAAXXZ; DeviceConfiguration::UpdateFromBehaviorValues(void)
0x18007728e  mov     rax, [rsp+258h+var_118]
0x180077296  mov     [rsp+258h+var_60], rax
0x18007729e  lea     r8, [rsp+258h+var_60]
0x1800772a6  lea     rdx, [rsp+258h+hModule]
0x1800772ae  lea     rcx, qword_180339958
0x1800772b5  call    ?find@?$_Tree@V?$_Tmap_traits@U_LUID@@PEAUID3D12Device@@U?$less@U_LUID@@@std@@V?$allocator@U?$pair@$$CBU_LUID@@PEAUID3D12Device@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_LUID@@PEAUID3D12Device@@@std@@@std@@@std@@@2@AEBU_LUID@@@Z; std::_Tree<std::_Tmap_traits<_LUID,ID3D12Device *,std::less<_LUID>,std::allocator<std::pair<_LUID const,ID3D12Device *>>,0>>::find(_LUID const &)
0x1800772ba  mov     rdx, [rsp+258h+hModule]
0x1800772c2  cmp     rdx, cs:qword_180339958
0x1800772c9  jz      short loc_1800772D1
0x1800772cb  mov     rcx, [rdx+28h]
0x1800772cf  jmp     short loc_1800772D4
0x1800772d1  mov     rcx, r14
0x1800772d4  mov     [rsp+258h+var_1D8], rcx
0x1800772dc  test    rcx, rcx
0x1800772df  jz      short loc_1800772EE
0x1800772e1  mov     rax, [rcx]
0x1800772e4  mov     rax, [rax+8]
0x1800772e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772ed  nop
0x1800772ee  cmp     [rsp+258h+var_1F8], r14d
0x1800772f3  jl      loc_18007840E
0x1800772f9  mov     r15b, r14b
0x1800772fc  test    r13b, r13b
0x1800772ff  jz      loc_1800778B3
0x180077305  mov     rdx, rbx; struct IUnknown *
0x180077308  lea     rcx, [rsp+258h+var_118]; this
0x180077310  call    ?SelectSingleAdapterHybridMode@CCreateDeviceCache@@QEAAXPEAUIUnknown@@@Z; CCreateDeviceCache::SelectSingleAdapterHybridMode(IUnknown *)
0x180077315  mov     rcx, [rsp+258h+var_1D8]
0x18007731d  test    rcx, rcx
0x180077320  jnz     short loc_180077366
0x180077322  mov     rcx, cs:qword_180339B48
0x180077329  test    rcx, rcx
0x18007732c  jz      loc_18007783F
0x180077332  mov     rax, [rcx]
0x180077335  lea     r9, [rsp+258h+var_1D8]
0x18007733d  lea     r8, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x180077344  mov     rdx, [rsp+258h+var_118]
0x18007734c  mov     rax, [rax+28h]
0x180077350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077355  mov     rcx, [rsp+258h+var_1D8]
0x18007735d  test    rcx, rcx
0x180077360  jz      loc_18007783F
0x180077366  mov     dil, r14b
0x180077369  mov     [rsp+258h+var_1D0], r14
0x180077371  mov     rax, [rcx]
0x180077374  lea     r8, [rsp+258h+var_1D0]
0x18007737c  lea     rdx, _GUID_78dbf87b_f766_422b_a61c_c8c446bdb9ad
0x180077383  mov     rax, [rax]
0x180077386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007738b  test    eax, eax
0x18007738d  js      loc_1800775CA
0x180077393  mov     rcx, [rsp+258h+var_1D0]
0x18007739b  mov     rax, [rcx]
0x18007739e  lea     rdx, [rsp+258h+var_60]
0x1800773a6  mov     rax, [rax+18h]
0x1800773aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800773af  test    dword ptr [rsp+258h+var_60], 40000000h
0x1800773ba  jnz     loc_1800775C4
0x1800773c0  cmp     [rsi+0EAh], r14b
0x1800773c7  jz      short loc_1800773D6
0x1800773c9  cmp     [rsi+0E9h], r14b
0x1800773d0  jnz     loc_1800775C4
0x1800773d6  lea     rcx, [rsi+8]; this
0x1800773da  call    ?GetFlags@DeviceConfiguration@@UEAA?AW4D3D12_DEVICE_FACTORY_FLAGS@@XZ; DeviceConfiguration::GetFlags(void)
0x1800773df  mov     ecx, 1
0x1800773e4  test    cl, al
0x1800773e6  jnz     loc_1800774BF
0x1800773ec  lea     r8, aId3d12devicefa_5; "ID3D12DeviceFactory::CreateDevice: Driv"...
0x1800773f3  xor     edx, edx
0x1800773f5  mov     rcx, r12
0x1800773f8  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x1800773fd  nop
0x1800773fe  lea     rcx, [rsp+258h+var_1D0]
0x180077406  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x18007740b  nop
0x18007740c  lea     rcx, [rsp+258h+var_1D8]
0x180077414  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180077419  nop
0x18007741a  mov     rcx, qword ptr [rsp+258h+var_198]
0x180077422  test    rcx, rcx
0x180077425  jz      short loc_18007744F
0x180077427  mov     rdx, [rsp+258h+var_188]
0x18007742f  sub     rdx, rcx
0x180077432  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180077436  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007743b  xorps   xmm0, xmm0
0x18007743e  movdqu  [rsp+258h+var_198], xmm0
0x180077447  mov     [rsp+258h+var_188], r14
0x18007744f  lea     rcx, [rsp+258h+var_118]; this
0x180077457  call    ??1CCreateDeviceCache@@QEAA@XZ; CCreateDeviceCache::~CCreateDeviceCache(void)
0x18007745c  nop
0x18007745d  lea     rcx, [rsp+258h+var_150]
0x180077465  call    _lambda_d50afd8fc60b66131f1acc6658d54be0___operator__
0x18007746a  nop
0x18007746b  mov     cs:?g_TransientState@@3UGlobalTransientState@@A, r14; GlobalTransientState g_TransientState
0x180077472  mov     rcx, cs:qword_180339C48; this
0x180077479  mov     cs:qword_180339C48, r14
0x180077480  test    rcx, rcx
0x180077483  jz      short loc_18007748A
0x180077485  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007748a  mov     rax, cs:qword_180339C58
0x180077491  cmp     rax, cs:qword_180339C60
0x180077498  jz      short loc_1800774A1
0x18007749a  mov     cs:qword_180339C60, rax
0x1800774a1  mov     cs:qword_180339C50, r14
0x1800774a8  lea     rcx, ?g_Module@@3VCModule@@A; _Mtx_t
0x1800774af  call    cs:__imp__Mtx_unlock
0x1800774b5  mov     eax, 887A0036h
0x1800774ba  jmp     loc_1800785B1
0x1800774bf  mov     dil, r14b
0x1800774c2  mov     r15b, cl
0x1800774c5  lea     rcx, [rsi+8]; this
0x1800774c9  call    ?GetFlags@DeviceConfiguration@@UEAA?AW4D3D12_DEVICE_FACTORY_FLAGS@@XZ; DeviceConfiguration::GetFlags(void)
0x1800774ce  test    al, 2
0x1800774d0  jnz     loc_1800775CA
0x1800774d6  mov     r8, [rsp+258h+var_1D0]
0x1800774de  mov     rdx, rsi
0x1800774e1  mov     rcx, r12
0x1800774e4  call    SingletonConfigCompatible
0x1800774e9  test    al, al
0x1800774eb  jnz     loc_1800775CA
0x1800774f1  lea     r8, aId3d12devicefa_2; "ID3D12DeviceFactory::CreateDevice: Driv"...
0x1800774f8  xor     edx, edx
0x1800774fa  mov     rcx, r12
0x1800774fd  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x180077502  nop
0x180077503  lea     rcx, [rsp+258h+var_1D0]
0x18007750b  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180077510  nop
0x180077511  lea     rcx, [rsp+258h+var_1D8]
0x180077519  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x18007751e  nop
0x18007751f  mov     rcx, qword ptr [rsp+258h+var_198]
0x180077527  test    rcx, rcx
0x18007752a  jz      short loc_180077554
0x18007752c  mov     rdx, [rsp+258h+var_188]
0x180077534  sub     rdx, rcx
0x180077537  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18007753b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180077540  xorps   xmm0, xmm0
0x180077543  movdqu  [rsp+258h+var_198], xmm0
0x18007754c  mov     [rsp+258h+var_188], r14
0x180077554  lea     rcx, [rsp+258h+var_118]; this
0x18007755c  call    ??1CCreateDeviceCache@@QEAA@XZ; CCreateDeviceCache::~CCreateDeviceCache(void)
0x180077561  nop
0x180077562  lea     rcx, [rsp+258h+var_150]
0x18007756a  call    _lambda_d50afd8fc60b66131f1acc6658d54be0___operator__
0x18007756f  nop
0x180077570  mov     cs:?g_TransientState@@3UGlobalTransientState@@A, r14; GlobalTransientState g_TransientState
0x180077577  mov     rcx, cs:qword_180339C48; this
0x18007757e  mov     cs:qword_180339C48, r14
0x180077585  test    rcx, rcx
0x180077588  jz      short loc_18007758F
0x18007758a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007758f  mov     rax, cs:qword_180339C58
0x180077596  cmp     rax, cs:qword_180339C60
0x18007759d  jz      short loc_1800775A6
0x18007759f  mov     cs:qword_180339C60, rax
0x1800775a6  mov     cs:qword_180339C50, r14
0x1800775ad  lea     rcx, ?g_Module@@3VCModule@@A; _Mtx_t
0x1800775b4  call    cs:__imp__Mtx_unlock
0x1800775ba  mov     eax, 887A0036h
0x1800775bf  jmp     loc_1800785B1
0x1800775c4  mov     dil, 1
0x1800775c7  mov     r15b, dil
0x1800775ca  lea     rcx, [rsp+258h+var_1D0]
0x1800775d2  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x1800775d7  mov     rcx, [rsp+258h+var_1D8]
0x1800775df  mov     rax, [rcx]
0x1800775e2  mov     rax, [rax+128h]
0x1800775e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775ee  mov     [rsp+258h+var_1F8], eax
0x1800775f2  test    eax, eax
0x1800775f4  jns     short loc_180077615
0x1800775f6  mov     dword ptr [rsp+258h+var_238], r14d
0x1800775fb  lea     r8, aExistingSingle_0; "Existing singleton device already remov"...
0x180077602  mov     edx, eax
0x180077604  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x180077609  mov     eax, [rsp+258h+var_1F8]
0x18007760d  test    eax, eax
0x18007760f  js      loc_18007840E
0x180077615  mov     [rsp+258h+Src], 1
0x180077621  mov     [rsp+258h+var_1A8], r14
0x180077629  lea     rax, [rsp+258h+var_1A0]
0x180077631  mov     [rsp+258h+Src+8], rax
0x180077639  mov     rcx, [rsp+258h+var_1D8]
0x180077641  mov     rax, [rcx]
0x180077644  mov     r9d, 18h
0x18007764a  lea     r8, [rsp+258h+Src]
0x180077652  lea     edx, [r9-16h]
0x180077656  mov     rax, [rax+68h]
0x18007765a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007765f  test    eax, eax
0x180077661  jns     short loc_180077681
0x180077663  mov     dword ptr [rsp+258h+var_238], r14d
  ... truncated ...
```
