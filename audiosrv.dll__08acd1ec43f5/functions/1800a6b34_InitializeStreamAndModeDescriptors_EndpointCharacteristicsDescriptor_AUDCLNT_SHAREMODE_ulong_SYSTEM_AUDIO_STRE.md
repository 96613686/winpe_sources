# InitializeStreamAndModeDescriptors(EndpointCharacteristicsDescriptor *,_AUDCLNT_SHAREMODE,ulong,SYSTEM_AUDIO_STREAM_TYPE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,_GUID,_GUID,ulong,tWAVEFORMATEX const *,tWAVEFORMATEX const *,__int64,__int64,__int64,ushort const *,_GUID const *,_GUID const *,_GUID const *,SPATIAL_STREAM_PROPERTIES const *,__int64,bool,bool,__int64,__int64,_BridgeStreamProperties,__int64,ulong,SYSTEM_AUDIO_STREAM_DESCRIPTOR * *,std::unique_ptr<MODE_PARAMS,std::default_delete<MODE_PARAMS>> &)

- ea: `0x1800a6b34`
- end: `0x1800a7d24`
- name: `?InitializeStreamAndModeDescriptors@@YAJPEAUEndpointCharacteristicsDescriptor@@W4_AUDCLNT_SHAREMODE@@KW4SYSTEM_AUDIO_STREAM_TYPE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@44KPEBUtWAVEFORMATEX@@5_J66PEBGPEBU5@88PEBUSPATIAL_STREAM_PROPERTIES@@6_N_N66W4_BridgeStreamProperties@@6KPEAPEAUSYSTEM_AUDIO_STREAM_DESCRIPTOR@@AEAV?$unique_ptr@UMODE_PARAMS@@U?$default_delete@UMODE_PARAMS@@@std@@@std@@@Z`
- size: `4592`
- prototype: `__int64 __usercall@<rax>(AudioModeEffectsWatcherFactory *this@<rcx>, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, void *Buf1, __int64, __int64, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, char, char, __int64, __int64, int, __int64, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180073490`
- `0x1800c0154`

## callees

- `0x180008a2c`
- `0x18000ae1c`
- `0x18000cc30`
- `0x18001280c`
- `0x18001e9a0`
- `0x180020d2c`
- `0x180020eb8`
- `0x1800210c4`
- `0x18002115c`
- `0x180029eec`
- `0x18002c4c0`
- `0x18003e610`
- `0x180055740`
- `0x18006686c`
- `0x180068068`
- `0x1800696ec`
- `0x18007204c`
- `0x1800a6b34`
- `0x1800afbc4`
- `0x1800b3c3c`
- `0x1800b46f0`
- `0x1800cddac`
- `0x1800ce750`
- `0x1800ce774`
- `0x1800d0e38`
- `0x1800e1c54`
- `0x1800e512c`
- `0x18016c010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800a7010`
- `RPCRT4!RpcImpersonateClient` at `0x1800a7010`
- `RPCRT4!RpcRevertToSelf` at `0x1800a7028`
- `RPCRT4!RpcRevertToSelf` at `0x1800a7028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6bb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6f2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a71d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a72b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6bb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a6f2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a71d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a72b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a74a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a74a9`
- `ext-ms-win-audiocore-spatial-l1-1-0!IsVirtualSurroundAllowedForProcess` at `0x1800a7020`
- `ext-ms-win-audiocore-spatial-l1-1-0!IsVirtualSurroundAllowedForProcess` at `0x1800a7020`

## string_xrefs

- `0x1800a6bdb`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a6cb3`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a6f5b`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a716b`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a72e2`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a748f`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a75dd`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a7745`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a7851`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a78aa`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a792c`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a7ad9`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a7be0`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a7c39`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800a7cb8`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall InitializeStreamAndModeDescriptors(
        EffectPack **this,
        int a2,
        unsigned int a3,
        int a4,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a5,
        void *Buf1,
        IID *a7,
        _OWORD *a8,
        unsigned int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        IID *a16,
        _QWORD *a17,
        GUID *a18,
        __int64 a19,
        __int64 a20,
        char a21,
        char a22,
        __int64 a23,
        __int64 a24,
        int a25,
        __int64 a26,
        int a27,
        _QWORD *a28,
        __int64 a29)
{
  int v29; // ebx
  unsigned int v33; // r13d
  char *v34; // rsi
  EffectPack *v35; // rcx
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v36; // r14d
  unsigned int v37; // edi
  __int64 v38; // rdx
  char *v39; // rax
  unsigned __int64 v40; // r9
  unsigned int v41; // edx
  int v42; // eax
  EffectPack *v43; // rcx
  int StreamEffect; // eax
  __int64 v45; // rdx
  __int64 *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rdx
  LPVOID v49; // rax
  unsigned int v50; // ebx
  int v51; // eax
  __int64 v52; // rdi
  LPVOID v53; // rax
  unsigned int i; // edx
  unsigned int v55; // ecx
  GUID v56; // xmm0
  __int64 v57; // rdi
  LPVOID v58; // rax
  __int64 v59; // rax
  int v60; // ebx
  unsigned int v61; // ecx
  __int64 *v62; // rcx
  int v63; // eax
  __int64 v64; // r9
  __int64 v65; // rdx
  __int64 v66; // rax
  unsigned int v67; // edi
  __int64 v68; // rbx
  LPVOID v69; // rax
  unsigned int j; // edx
  unsigned int v71; // ecx
  LPVOID v72; // rax
  IID *v73; // r13
  __int64 v74; // rax
  GUID *v75; // rax
  __int128 v76; // xmm0
  __int128 v77; // xmm2
  __int64 v78; // xmm3_8
  int v79; // ecx
  __int64 v80; // rdx
  IID *v81; // rbx
  __int64 v82; // rax
  int v83; // eax
  __int64 v84; // r9
  __int64 v85; // rdx
  __int64 v86; // rax
  int ContainerProperty; // eax
  __int64 v88; // rax
  int ModeEffect; // eax
  __int64 v90; // r9
  __int64 v91; // rdx
  __int64 v92; // rax
  char IsEnabled; // al
  unsigned int v94; // r14d
  __int64 v95; // rdi
  char *v96; // rax
  char *v97; // rbx
  __int64 v98; // rdx
  void **v99; // rcx
  unsigned int v100; // edx
  unsigned int v101; // ecx
  BOOL v102; // eax
  int v103; // eax
  __int64 v104; // rdx
  __int64 v105; // rax
  struct _GUID *v106; // rax
  struct IAudioModeEffectsWatcher **v107; // r9
  struct _GUID *v108; // rbx
  int Watcher; // eax
  void **v110; // rcx
  unsigned int v112; // r14d
  __int64 v113; // rdi
  char *v114; // rax
  char *v115; // rbx
  __int64 v116; // rdx
  unsigned int v117; // edx
  unsigned int v118; // ecx
  BOOL v119; // eax
  int v120; // eax
  __int64 v121; // rdx
  __int64 v122; // rax
  struct _GUID *v123; // rax
  struct IAudioModeEffectsWatcher **v124; // r9
  struct _GUID *v125; // rbx
  int v126; // eax
  struct IAudioSystemEffects2 **v127; // [rsp+28h] [rbp-D9h]
  int v128; // [rsp+28h] [rbp-D9h]
  struct IAudioProcessingObject *v129; // [rsp+48h] [rbp-B9h] BYREF
  __int64 v130; // [rsp+50h] [rbp-B1h] BYREF
  struct ICompositeSystemEffect *v131; // [rsp+58h] [rbp-A9h] BYREF
  __int64 v132; // [rsp+60h] [rbp-A1h] BYREF
  __int64 v133; // [rsp+68h] [rbp-99h] BYREF
  void *v134; // [rsp+70h] [rbp-91h] BYREF
  char *v135; // [rsp+78h] [rbp-89h] BYREF
  char *v136; // [rsp+80h] [rbp-81h] BYREF
  IID rclsid; // [rsp+88h] [rbp-79h] BYREF
  char v138; // [rsp+98h] [rbp-69h]
  unsigned int v139; // [rsp+A8h] [rbp-59h] BYREF
  __int64 v140; // [rsp+B0h] [rbp-51h] BYREF
  unsigned int v141; // [rsp+B8h] [rbp-49h] BYREF
  __int64 v142; // [rsp+C0h] [rbp-41h] BYREF
  __int64 v143; // [rsp+C8h] [rbp-39h] BYREF
  __int64 v144; // [rsp+D0h] [rbp-31h] BYREF
  __int64 v145; // [rsp+D8h] [rbp-29h] BYREF
  struct _GUID *v146; // [rsp+E0h] [rbp-21h] BYREF
  _QWORD v147[2]; // [rsp+E8h] [rbp-19h] BYREF
  _OWORD v148[4]; // [rsp+F8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+3Fh]
  struct ICompositeSystemEffect *v150; // [rsp+148h] [rbp+47h] BYREF
  int v151; // [rsp+150h] [rbp+4Fh]
  int v152; // [rsp+160h] [rbp+5Fh]

  v152 = a4;
  v151 = a2;
  v29 = a4;
  v33 = 0;
  v34 = 0;
  v134 = 0;
  v146 = 0;
  v35 = *this;
  v147[0] = 0;
  wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>((char *)v35 + 40, v147);
  v36 = a5;
  if ( !a28 )
  {
    v73 = a7;
    goto LABEL_118;
  }
  if ( (a3 & 0x800000) == 0 )
  {
    if ( !a2 && (a5 == eHostProcessConnector || (unsigned int)(a5 - 2) <= 2) )
    {
      v133 = 0;
      v41 = 0;
      v139 = 0;
      if ( ((a5 - 2) & 0xFFFFFFFD) != 0 )
      {
        v150 = 0;
        v42 = EffectPack::EndpointConnectorSupportsProcessingModes(this[1], a5);
        v43 = this[1];
        if ( v42 )
        {
          v150 = 0;
          rclsid = *a7;
          StreamEffect = EffectPack::GetStreamEffect(v43, &rclsid, 0, v36, &v150, 0, 0);
          v37 = StreamEffect;
          if ( StreamEffect < 0 )
          {
            v45 = 307;
LABEL_17:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v45,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
              (const char *)(unsigned int)StreamEffect,
              (int)v127);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v150);
LABEL_18:
            v46 = &v133;
LABEL_19:
            wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
              v46,
              0);
            goto LABEL_167;
          }
        }
        else
        {
          v150 = 0;
          StreamEffect = EffectPack::GetLfx(v43, v36, &v150, 0, v127);
          v37 = StreamEffect;
          if ( StreamEffect < 0 )
          {
            v45 = 312;
            goto LABEL_17;
          }
        }
        if ( v150 )
        {
          v47 = *(_QWORD *)v150;
          *(_QWORD *)&rclsid.Data1 = &v133;
          *(_QWORD *)rclsid.Data4 = 0;
          v138 = 1;
          (*(void (__fastcall **)(struct ICompositeSystemEffect *, unsigned int *, unsigned __int8 *))(v47 + 32))(
            v150,
            &v139,
            rclsid.Data4);
          wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&rclsid);
        }
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v150);
        v41 = v139;
      }
      if ( v29 )
      {
        if ( v29 != 1 )
        {
          if ( (unsigned int)(v29 - 2) >= 2 )
          {
            v37 = -2147024809;
            v48 = 432;
LABEL_47:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v48,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
              (const char *)v37,
              (int)v127);
            goto LABEL_18;
          }
          v49 = CoTaskMemAlloc(0x17Cu);
          wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            &v134,
            v49);
          v34 = (char *)v134;
          if ( !v134 )
          {
            v48 = 416;
LABEL_46:
            v37 = -2147024882;
            goto LABEL_47;
          }
          v50 = 3;
          memset_0(v134, 0, 0x17Cu);
          v51 = 1;
          if ( ((v36 - 2) & 0xFFFFFFFD) != 0 )
            v51 = v152;
          *(_DWORD *)v34 = v51;
          *((_DWORD *)v34 + 34) = a3;
          *((_DWORD *)v34 + 82) = 3;
          *(GUID *)(v34 + 332) = GUID_07252659_bb6b_4b79_b78b_623f6699a579;
          *(GUID *)(v34 + 348) = GUID_3dc09436_7d83_4ba0_addc_cd47f996c5ba;
          *(GUID *)(v34 + 364) = GUID_06587e71_f043_403a_bf49_cb591ba6e103;
          *((_DWORD *)v34 + 38) = 0;
          goto LABEL_64;
        }
        v50 = v41 + 2;
        v52 = 16LL * (v41 + 2);
        v53 = CoTaskMemAlloc(v52 + 332);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v134,
          v53);
        v34 = (char *)v134;
        if ( !v134 )
        {
          v48 = 381;
          goto LABEL_46;
        }
        memset_0(v134, 0, v52 + 332);
        *(_DWORD *)v34 = 1;
        *((_DWORD *)v34 + 34) = a3;
        *((_DWORD *)v34 + 38) = 0;
        *((_DWORD *)v34 + 82) = 0;
        *((_QWORD *)v34 + 32) = a23;
        *((_QWORD *)v34 + 33) = a24;
        if ( a22 )
          *((_QWORD *)v34 + 31) = a20;
        for ( i = 0; i < v139; ++i )
        {
          v55 = *((_DWORD *)v34 + 82);
          if ( v55 > 0x1F )
          {
            v37 = -2147418113;
            v48 = 396;
            goto LABEL_47;
          }
          *((_DWORD *)v34 + 38) |= 1 << v55;
          *(_OWORD *)&v34[16 * (*((_DWORD *)v34 + 82))++ + 332] = *(_OWORD *)(v133 + 16LL * i);
        }
        *(GUID *)&v34[16 * *((unsigned int *)v34 + 82) + 332] = GUID_3dc09436_7d83_4ba0_addc_cd47f996c5ba;
        v56 = GUID_06587e71_f043_403a_bf49_cb591ba6e103;
      }
      else
      {
        v50 = v41 + 4;
        LODWORD(v150) = v41 + 4;
        v57 = 16LL * (v41 + 4);
        v58 = CoTaskMemAlloc(v57 + 332);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v134,
          v58);
        v34 = (char *)v134;
        if ( !v134 )
        {
          v48 = 326;
          goto LABEL_46;
        }
        memset_0(v134, 0, v57 + 332);
        *(_DWORD *)v34 = 0;
        *((_DWORD *)v34 + 34) = a3;
        *((_DWORD *)v34 + 82) = 0;
        *((_DWORD *)v34 + 38) = 0;
        if ( a21 )
        {
          *((_DWORD *)v34 + 38) = 1;
          *(GUID *)&v34[16 * (*((_DWORD *)v34 + 82))++ + 332] = GUID_7bf2a436_2a30_4797_90ee_0f66b8426d75;
        }
        else
        {
          while ( v33 < v139 )
          {
            v59 = *(_QWORD *)(v133 + 16LL * v33) - *(_QWORD *)&GUID_4be8a061_c73b_4f23_8114_317aae3e8698.Data1;
            if ( !v59 )
              v59 = *(_QWORD *)(v133 + 16LL * v33 + 8) - *(_QWORD *)GUID_4be8a061_c73b_4f23_8114_317aae3e8698.Data4;
            if ( v59
              || !(unsigned __int8)IsGetDefaultSpatialRenderingModePresent()
              || RpcImpersonateClient(0) < 0
              || (v60 = IsVirtualSurroundAllowedForProcess(a9), RpcRevertToSelf(), v60) )
            {
              v61 = *((_DWORD *)v34 + 82);
              if ( v61 > 0x1F )
              {
                v37 = -2147418113;
                v48 = 360;
                goto LABEL_47;
              }
              *((_DWORD *)v34 + 38) |= 1 << v61;
              *(_OWORD *)&v34[16 * (*((_DWORD *)v34 + 82))++ + 332] = *(_OWORD *)(v133 + 16LL * v33);
            }
            ++v33;
          }
          v50 = (unsigned int)v150;
        }
        *(GUID *)&v34[16 * (*((_DWORD *)v34 + 82))++ + 332] = GUID_3dc09436_7d83_4ba0_addc_cd47f996c5ba;
        *(GUID *)&v34[16 * *((unsigned int *)v34 + 82) + 332] = GUID_06587e71_f043_403a_bf49_cb591ba6e103;
        v56 = GUID_07252659_bb6b_4b79_b78b_623f6699a579;
      }
      *(GUID *)&v34[16 * ++*((_DWORD *)v34 + 82) + 332] = v56;
      ++*((_DWORD *)v34 + 82);
LABEL_64:
      *((_DWORD *)v34 + 1) = a3 >> 31;
      if ( *((_DWORD *)v34 + 82) > v50 )
      {
        v37 = -2147418113;
        v48 = 436;
        goto LABEL_47;
      }
      v62 = &v133;
LABEL_89:
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        v62,
        0);
      goto LABEL_90;
    }
    v140 = 0;
    v141 = 0;
    if ( a5 != eOffloadConnector || a2 )
    {
      v72 = CoTaskMemAlloc(0x160u);
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v134,
        v72);
      v34 = (char *)v134;
      if ( !v134 )
      {
        v37 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DE,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)0x8007000ELL,
          (int)v127);
        goto LABEL_72;
      }
      memset_0(v134, 0, 0x160u);
      *(_DWORD *)v34 = v29;
      *((_DWORD *)v34 + 34) = a3;
      *((_DWORD *)v34 + 82) = 0;
      *((_DWORD *)v34 + 1) = 0;
    }
    else
    {
      v150 = 0;
      rclsid = *a7;
      v63 = EffectPack::GetStreamEffect(this[1], &rclsid, 0, a5, &v150, 0, 0);
      v37 = v63;
      if ( v63 < 0 )
      {
        v64 = (unsigned int)v63;
        v65 = 445;
LABEL_71:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v65,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)v64,
          (int)v127);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v150);
LABEL_72:
        v46 = &v140;
        goto LABEL_19;
      }
      if ( v150 )
      {
        v66 = *(_QWORD *)v150;
        *(_QWORD *)&rclsid.Data1 = &v140;
        *(_QWORD *)rclsid.Data4 = 0;
        v138 = 1;
        (*(void (__fastcall **)(struct ICompositeSystemEffect *, unsigned int *, unsigned __int8 *))(v66 + 32))(
          v150,
          &v141,
          rclsid.Data4);
        wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&rclsid);
      }
      v67 = v141;
      v68 = 16LL * v141;
      v69 = CoTaskMemAlloc(v68 + 332);
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v134,
        v69);
      v34 = (char *)v134;
      if ( !v134 )
      {
        v37 = -2147024882;
        v64 = 2147942414LL;
        v65 = 452;
        goto LABEL_71;
      }
      memset_0(v134, 0, v68 + 332);
      *(_DWORD *)v34 = 0;
      *((_DWORD *)v34 + 34) = a3;
      *((_DWORD *)v34 + 82) = 0;
      *((_DWORD *)v34 + 38) = 0;
      for ( j = 0; j < v141; ++j )
      {
        v71 = *((_DWORD *)v34 + 82);
        if ( v71 > 0x1F )
        {
          v37 = -2147418113;
          v64 = 2147549183LL;
          v65 = 462;
          goto LABEL_71;
        }
        *((_DWORD *)v34 + 38) |= 1 << v71;
        *(_OWORD *)&v34[16 * (*((_DWORD *)v34 + 82))++ + 332] = *(_OWORD *)(v140 + 16LL * j);
      }
      *((_DWORD *)v34 + 1) = 0;
      if ( *((_DWORD *)v34 + 82) > v67 )
      {
        v37 = -2147418113;
        v64 = 2147549183LL;
        v65 = 470;
        goto LABEL_71;
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v150);
    }
    v62 = &v140;
    goto LABEL_89;
  }
  if ( a2 )
  {
    v37 = -2147418113;
    v38 = 270;
LABEL_7:
    v40 = v37;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)v40,
      (int)v127);
LABEL_167:
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v146);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v134,
      0);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v147);
    return v37;
  }
  v39 = (char *)CoTaskMemAlloc(0x15Cu);
  v34 = v39;
  v134 = v39;
  if ( !v39 )
  {
    v37 = -2147024882;
    v38 = 275;
    goto LABEL_7;
  }
  memset_0(v39, 0, 0x15Cu);
  *((_DWORD *)v34 + 34) = a3;
  *((_DWORD *)v34 + 38) = 1;
  *(GUID *)(v34 + 332) = GUID_fed4acc3_87c9_45e9_a026_5b59a855e687;
  *((_DWORD *)v34 + 82) = 1;
  *((_DWORD *)v34 + 1) = 1;
LABEL_90:
  v73 = a7;
  *(IID *)(v34 + 156) = *a7;
  *(_OWORD *)(v34 + 172) = *a8;
  *((_DWORD *)v34 + 2) = v36;
  v74 = a10;
  *((_QWORD *)v34 + 16) = a10;
  *((_DWORD *)v34 + 30) = *(unsigned __int16 *)(v74 + 16) + 18;
  *((_QWORD *)v34 + 3) = a12;
  *((_QWORD *)v34 + 4) = a13;
  *((_DWORD *)v34 + 3) = a9;
  *((_QWORD *)v34 + 2) = a15;
  v75 = &GUID_00000000_0000_0000_0000_000000000000;
  if ( a18 )
    v75 = a18;
  *((GUID *)v34 + 3) = *v75;
  v76 = *(_OWORD *)(a19 + 16);
  v77 = *(_OWORD *)(a19 + 32);
  v78 = *(_QWORD *)(a19 + 48);
  *((_OWORD *)v34 + 12) = *(_OWORD *)a19;
  *((_OWORD *)v34 + 13) = v76;
  *((_OWORD *)v34 + 14) = v77;
  *((_QWORD *)v34 + 30) = v78;
  *((_QWORD *)v34 + 14) = a20;
  v79 = a25;
  *((_DWORD *)v34 + 74) = a25;
  v80 = a26;
  if ( v79 != 2 )
    v80 = 0;
  *((_QWORD *)v34 + 38) = v80;
  *((_DWORD *)v34 + 78) = a27;
  *((_DWORD *)v34 + 68) = v151 == 1;
  *((_QWORD *)v34 + 40) = a14;
  *((GUID *)v34 + 4) = GUID_00000000_0000_0000_0000_000000000000;
  v81 = a16;
  if ( !a16 )
    goto LABEL_104;
  v82 = *(_QWORD *)&a16->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( *(_QWORD *)&a16->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
    v82 = *(_QWORD *)a16->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( !v82
    || (rclsid = *a16,
        v83 = GetContainerProperty(&rclsid, &PKEY_Audio_CPMemoryManager, (struct _GUID *)v34 + 4),
        v37 = v83,
        v83 >= 0) )
  {
LABEL_104:
    *((GUID *)v34 + 5) = GUID_00000000_0000_0000_0000_000000000000;
    v84 = *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
    v85 = *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
    if ( v81 )
    {
      v86 = *(_QWORD *)&v81->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
      if ( *(_QWORD *)&v81->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
        v86 = *(_QWORD *)v81->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
      if ( v86 )
      {
        rclsid = *v81;
        ContainerProperty = GetContainerProperty(&rclsid, &PKEY_Audio_CPEventManager, (struct _GUID *)v34 + 5);
        v37 = ContainerProperty;
        if ( ContainerProperty < 0 )
        {
          v40 = (unsigned int)ContainerProperty;
          v38 = 516;
          goto LABEL_8;
        }
        v85 = *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
        v84 = *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
      }
    }
    if ( a17 )
    {
      v88 = *a17 - v84;
      if ( *a17 == v84 )
        v88 = a17[1] - v85;
      v29 = v152;
      if ( v88 )
        *((_OWORD *)v34 + 6) = *(_OWORD *)a17;
    }
    else
    {
      v29 = v152;
    }
LABEL_118:
    v130 = 0;
    LODWORD(v132) = 0;
    v129 = 0;
    v131 = 0;
    rclsid = *v73;
    ModeEffect = EffectPack::GetModeEffect(this[1], &rclsid, 0, v36, &v131, &v129, 0);
    v37 = ModeEffect;
    if ( ModeEffect < 0 )
    {
      v90 = (unsigned int)ModeEffect;
      v91 = 530;
LABEL_120:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v91,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)v90,
        v128);
LABEL_121:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v129);
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v130,
        0);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v131);
      goto LABEL_167;
    }
    v37 = 0;
    if ( v131 )
    {
      v92 = *(_QWORD *)v131;
      *(_QWORD *)&rclsid.Data1 = &v130;
      *(_QWORD *)rclsid.Data4 = 0;
      v138 = 1;
      (*(void (__fastcall **)(struct ICompositeSystemEffect *, __int64 *, unsigned __int8 *))(v92 + 32))(
        v131,
        &v132,
        rclsid.Data4);
      wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&rclsid);
    }
    if ( (a3 & 0x800000) != 0 )
    {
      if ( v151 )
      {
        v37 = -2147418113;
        v90 = 2147549183LL;
        v91 = 540;
        goto LABEL_120;
      }
LABEL_164:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v129);
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v130,
        0);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v131);
      if ( a28 )
      {
        v134 = 0;
        *a28 = v34;
      }
      std::unique_ptr<MODE_PARAMS>::operator=<std::default_delete<MODE_PARAMS>,0>(a29, &v146);
      goto LABEL_167;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DisableModePipeForOffloadPins>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_DisableModePipeForOffloadPins>::GetImpl'::`2'::impl);
    if ( v151 )
      goto LABEL_164;
    if ( IsEnabled )
    {
      if ( v36 && v36 != eKeywordDetectorConnector )
        goto LABEL_164;
      if ( (unsigned int)(v29 - 2) <= 1 )
        goto LABEL_164;
      rclsid = *v73;
      LOBYTE(v150) = EffectPack::CanProcessingModeBeParameterized(this[1], &rclsid, v36);
      if ( !(_BYTE)v150
        && (memcmp_0(Buf1, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u)
         || !(unsigned int)EffectPack::CanBuildProcessingModesOnRawConnector(this[1], (unsigned int)v36, 0)) )
      {
        goto LABEL_164;
      }
      v94 = 1;
      if ( (unsigned int)v132 > 1 )
        v94 = v132;
      v95 = 16LL * v94;
      v96 = (char *)operator new[](v95 + 68, (const struct std::nothrow_t *)&std::nothrow);
      v97 = v96;
      v136 = v96;
      if ( !v96 )
      {
        v37 = -2147024882;
        v98 = 570;
LABEL_139:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v98,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)v37,
          v128);
        goto LABEL_140;
      }
      memset_0(v96, 0, v95 + 68);
      *(_DWORD *)v97 = v152;
      v37 = 0;
      *((_DWORD *)v97 + 1) = 0;
      *((_DWORD *)v97 + 16) = 0;
      v100 = 0;
      v101 = 0;
      while ( v100 < (unsigned int)v132 )
      {
        if ( v101 > 0x1F )
        {
          v37 = -2147418113;
          v98 = 578;
          goto LABEL_139;
        }
        *((_DWORD *)v97 + 8) |= 1 << v101;
        *(_OWORD *)&v97[16 * (*((_DWORD *)v97 + 16))++ + 68] = *(_OWORD *)(v130 + 16LL * v100);
        v101 = *((_DWORD *)v97 + 16);
        ++v100;
      }
      *(IID *)(v97 + 36) = *v73;
      wil::com_ptr_t<IAudioProcessingObject,wil::err_returncode_policy>::try_copy<IApoAuxiliaryInputConfiguration>(
        &v129,
        &v143);
      *((_DWORD *)v97 + 13) = v143 != 0;
      wil::com_ptr_t<IAudioProcessingObject,wil::err_returncode_policy>::try_copy<IApoAcousticEchoCancellation>(
        &v129,
        &v142);
      v102 = v142 != 0;
      *((_DWORD *)v97 + 14) = v102;
      if ( v102 )
      {
        wil::com_ptr_t<IAudioProcessingObject,wil::err_returncode_policy>::try_copy<IApoAcousticEchoCancellation2>(
          &v129,
          v148);
        if ( *(_QWORD *)&v148[0] )
        {
          LODWORD(v135) = 0;
          v103 = (*(__int64 (__fastcall **)(_QWORD, char **))(**(_QWORD **)&v148[0] + 24LL))(*(_QWORD *)&v148[0], &v135);
          v37 = v103;
          if ( v103 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x258,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
              (const char *)(unsigned int)v103,
              v128);
            wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(v148);
LABEL_151:
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v142);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v143);
LABEL_140:
            v99 = (void **)&v136;
LABEL_141:
            std::unique_ptr<AUDIO_DEVICE_MODE_DESCRIPTOR>::~unique_ptr<AUDIO_DEVICE_MODE_DESCRIPTOR>(v99);
            goto LABEL_121;
          }
          *((_DWORD *)v97 + 15) = (unsigned __int8)v135 & 1;
          v37 = 0;
        }
        wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(v148);
      }
      if ( *((_DWORD *)v97 + 16) > v94 )
      {
        v37 = -2147418113;
        v104 = 609;
LABEL_156:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v104,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)v37,
          v128);
        goto LABEL_151;
      }
      v105 = a11;
      *((_QWORD *)v97 + 2) = a11;
      *((_DWORD *)v97 + 2) = *(unsigned __int16 *)(v105 + 16) + 18;
      v106 = (struct _GUID *)operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v108 = v106;
      if ( !v106 )
      {
        v146 = 0;
        v37 = -2147024882;
        v104 = 614;
        goto LABEL_156;
      }
      v146 = v106;
      *v106 = 0;
      if ( (_BYTE)v150 )
      {
        v150 = 0;
        rclsid = *v73;
        Watcher = AudioModeEffectsWatcherFactory::GetWatcher(
                    (AudioModeEffectsWatcherFactory *)this,
                    (struct EndpointCharacteristicsDescriptor *)&rclsid,
                    v106,
                    v107);
        v37 = Watcher;
        if ( Watcher < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26C,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)Watcher,
            v128);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v150);
          goto LABEL_151;
        }
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v150);
        v37 = 0;
      }
      std::unique_ptr<AUDIO_DEVICE_MODE_DESCRIPTOR>::operator=<std::default_delete<AUDIO_DEVICE_MODE_DESCRIPTOR>,0>(
        v108->Data4,
        &v136);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v142);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v143);
      v110 = (void **)&v136;
LABEL_163:
      std::unique_ptr<AUDIO_DEVICE_MODE_DESCRIPTOR>::~unique_ptr<AUDIO_DEVICE_MODE_DESCRIPTOR>(v110);
      goto LABEL_164;
    }
    if ( (v36 & 0xFFFFFFFC) != 0 )
      goto LABEL_164;
    if ( v36 == eLoopbackConnector )
      goto LABEL_164;
    if ( (unsigned int)(v29 - 2) <= 1 )
      goto LABEL_164;
    rclsid = *v73;
    LOBYTE(v150) = EffectPack::CanProcessingModeBeParameterized(this[1], &rclsid, v36);
    if ( !(_BYTE)v150
      && (memcmp_0(Buf1, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u)
       || !(unsigned int)EffectPack::CanBuildProcessingModesOnRawConnector(this[1], (unsigned int)v36, 0)) )
    {
      goto LABEL_164;
    }
    v112 = 1;
    if ( (unsigned int)v132 > 1 )
      v112 = v132;
    v113 = 16LL * v112;
    v114 = (char *)operator new[](v113 + 68, (const struct std::nothrow_t *)&std::nothrow);
    v115 = v114;
    v135 = v114;
    if ( !v114 )
    {
      v37 = -2147024882;
      v116 = 652;
LABEL_180:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v116,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)v37,
        v128);
      goto LABEL_181;
    }
    memset_0(v114, 0, v113 + 68);
    *(_DWORD *)v115 = v152;
    v37 = 0;
    *((_DWORD *)v115 + 1) = 0;
    *((_DWORD *)v115 + 16) = 0;
    v117 = 0;
    v118 = 0;
    while ( v117 < (unsigned int)v132 )
    {
      if ( v118 > 0x1F )
      {
        v37 = -2147418113;
        v116 = 660;
        goto LABEL_180;
      }
      *((_DWORD *)v115 + 8) |= 1 << v118;
      *(_OWORD *)&v115[16 * (*((_DWORD *)v115 + 16))++ + 68] = *(_OWORD *)(v130 + 16LL * v117);
      v118 = *((_DWORD *)v115 + 16);
      ++v117;
    }
    *(IID *)(v115 + 36) = *v73;
    wil::com_ptr_t<IAudioProcessingObject,wil::err_returncode_policy>::try_copy<IApoAuxiliaryInputConfiguration>(
      &v129,
      &v145);
    *((_DWORD *)v115 + 13) = v145 != 0;
    wil::com_ptr_t<IAudioProcessingObject,wil::err_returncode_policy>::try_copy<IApoAcousticEchoCancellation>(
      &v129,
      &v144);
    v119 = v144 != 0;
    *((_DWORD *)v115 + 14) = v119;
    if ( v119 )
    {
      wil::com_ptr_t<IAudioProcessingObject,wil::err_returncode_policy>::try_copy<IApoAcousticEchoCancellation2>(
        &v129,
        &rclsid);
      if ( *(_QWORD *)&rclsid.Data1 )
      {
        LODWORD(v136) = 0;
        v120 = (*(__int64 (__fastcall **)(_QWORD, char **))(**(_QWORD **)&rclsid.Data1 + 24LL))(
                 *(_QWORD *)&rclsid.Data1,
                 &v136);
        v37 = v120;
        if ( v120 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2AA,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)v120,
            v128);
          wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&rclsid);
          goto LABEL_191;
        }
        *((_DWORD *)v115 + 15) = (unsigned __int8)v136 & 1;
        v37 = 0;
      }
      wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&rclsid);
    }
    if ( *((_DWORD *)v115 + 16) <= v112 )
    {
      v122 = a11;
      *((_QWORD *)v115 + 2) = a11;
      *((_DWORD *)v115 + 2) = *(unsigned __int16 *)(v122 + 16) + 18;
      v123 = (struct _GUID *)operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v125 = v123;
      if ( v123 )
      {
        v146 = v123;
        *v123 = 0;
        if ( (_BYTE)v150 )
        {
          v150 = 0;
          v148[0] = *v73;
          v126 = AudioModeEffectsWatcherFactory::GetWatcher(
                   (AudioModeEffectsWatcherFactory *)this,
                   (struct EndpointCharacteristicsDescriptor *)v148,
                   v123,
                   v124);
          v37 = v126;
          if ( v126 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2BE,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
              (const char *)(unsigned int)v126,
              v128);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v150);
            goto LABEL_191;
          }
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v150);
          v37 = 0;
        }
        std::unique_ptr<AUDIO_DEVICE_MODE_DESCRIPTOR>::operator=<std::default_delete<AUDIO_DEVICE_MODE_DESCRIPTOR>,0>(
          v125->Data4,
          &v135);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v144);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v145);
        v110 = (void **)&v135;
        goto LABEL_163;
      }
      v146 = 0;
      v37 = -2147024882;
      v121 = 696;
    }
    else
    {
      v37 = -2147418113;
      v121 = 691;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v121,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)v37,
      v128);
LABEL_191:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v144);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v145);
LABEL_181:
    v99 = (void **)&v135;
    goto LABEL_141;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1FD,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
    (const char *)(unsigned int)v83,
    (int)v127);
  if ( v34 )
    CoTaskMemFree(v34);
  if ( v147[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v147[0] + 16LL))(v147[0]);
  return v37;
}

```

## disassembly

```asm
0x1800a6b34  mov     rax, rsp
0x1800a6b37  mov     [rax+18h], rbx
0x1800a6b3b  mov     [rax+20h], r9d
0x1800a6b3f  mov     [rax+10h], edx
0x1800a6b42  push    rbp
0x1800a6b43  push    rsi
0x1800a6b44  push    rdi
0x1800a6b45  push    r12
0x1800a6b47  push    r13
0x1800a6b49  push    r14
0x1800a6b4b  push    r15
0x1800a6b4d  lea     rbp, [rax-3Fh]
0x1800a6b51  sub     rsp, 100h
0x1800a6b58  mov     ebx, r9d
0x1800a6b5b  mov     r15d, r8d
0x1800a6b5e  mov     edi, edx
0x1800a6b60  mov     r12, rcx
0x1800a6b63  xor     r13d, r13d
0x1800a6b66  mov     esi, r13d
0x1800a6b69  mov     [rsp+130h+var_C8], r13
0x1800a6b6e  mov     [rbp+37h+var_58], r13
0x1800a6b72  mov     rcx, [rcx]
0x1800a6b75  mov     [rbp+37h+var_50], r13
0x1800a6b79  add     rcx, 28h ; '('
0x1800a6b7d  lea     rdx, [rbp+37h+var_50]
0x1800a6b81  call    ??$copy_to@VCAudioSession@@@?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAVCAudioSession@@@Z; wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(CAudioSession * *)
0x1800a6b86  mov     r14d, [rbp+37h+arg_20]
0x1800a6b8a  cmp     [rbp+37h+arg_D8], r13
0x1800a6b91  jz      loc_1800A7568
0x1800a6b97  bt      r15d, 17h
0x1800a6b9c  jnb     loc_1800A6C28
0x1800a6ba2  test    edi, edi
0x1800a6ba4  jz      short loc_1800A6BB2
0x1800a6ba6  mov     edi, 8000FFFFh
0x1800a6bab  mov     edx, 10Eh
0x1800a6bb0  jmp     short loc_1800A6BD4
0x1800a6bb2  mov     ebx, 15Ch
0x1800a6bb7  mov     ecx, ebx; cb
0x1800a6bb9  call    cs:__imp_CoTaskMemAlloc
0x1800a6bbf  mov     rsi, rax
0x1800a6bc2  mov     [rsp+130h+var_C8], rax
0x1800a6bc7  test    rax, rax
0x1800a6bca  jnz     short loc_1800A6BEC
0x1800a6bcc  mov     edi, 8007000Eh
0x1800a6bd1  lea     edx, [rbx-49h]; void *
0x1800a6bd4  mov     r9d, edi; char *
0x1800a6bd7  mov     rcx, [rbp+3Fh]; this
0x1800a6bdb  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a6be2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6be7  jmp     loc_1800A79CC
0x1800a6bec  mov     r8, rbx; Size
0x1800a6bef  xor     edx, edx; Val
0x1800a6bf1  mov     rcx, rsi; void *
0x1800a6bf4  call    memset_0
0x1800a6bf9  mov     [rsi+88h], r15d
0x1800a6c00  mov     eax, 1
0x1800a6c05  mov     [rsi+98h], eax
0x1800a6c0b  movups  xmm0, xmmword ptr cs:_GUID_fed4acc3_87c9_45e9_a026_5b59a855e687.Data1
0x1800a6c12  movdqu  xmmword ptr [rsi+14Ch], xmm0
0x1800a6c1a  mov     [rsi+148h], eax
0x1800a6c20  mov     [rsi+4], eax
0x1800a6c23  jmp     loc_1800A7324
0x1800a6c28  test    edi, edi
0x1800a6c2a  jnz     loc_1800A710C
0x1800a6c30  test    r14d, r14d
0x1800a6c33  jz      short loc_1800A6C42
0x1800a6c35  lea     eax, [r14-2]
0x1800a6c39  cmp     eax, 2
0x1800a6c3c  ja      loc_1800A710C
0x1800a6c42  mov     [rsp+130h+var_D0], r13
0x1800a6c47  mov     edx, r13d
0x1800a6c4a  mov     [rbp+37h+var_90], edx
0x1800a6c4d  lea     eax, [r14-2]
0x1800a6c51  test    eax, 0FFFFFFFDh
0x1800a6c56  jz      loc_1800A6D47
0x1800a6c5c  mov     [rbp+37h+arg_0], r13
0x1800a6c60  mov     edx, r14d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800a6c63  mov     rcx, [r12+8]; this
0x1800a6c68  call    ?EndpointConnectorSupportsProcessingModes@EffectPack@@QEAAHW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::EndpointConnectorSupportsProcessingModes(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x1800a6c6d  mov     rcx, [r12+8]; this
0x1800a6c72  test    eax, eax
0x1800a6c74  jz      short loc_1800A6CE2
0x1800a6c76  mov     [rbp+37h+arg_0], r13
0x1800a6c7a  mov     rax, [rbp+37h+arg_30]
0x1800a6c7e  movaps  xmm0, xmmword ptr [rax]
0x1800a6c81  movdqa  xmmword ptr [rbp+37h+rclsid.Data1], xmm0
0x1800a6c86  mov     [rsp+30h], r13; struct IAudioSystemEffects2 **
0x1800a6c8b  mov     [rsp+130h+var_108], r13; struct IAudioProcessingObject **
0x1800a6c90  lea     rax, [rbp+37h+arg_0]
0x1800a6c94  mov     [rsp+130h+var_110], rax; int
0x1800a6c99  mov     r9d, r14d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800a6c9c  xor     r8d, r8d; int
0x1800a6c9f  lea     rdx, [rbp+37h+rclsid]; struct _GUID *
0x1800a6ca3  call    ?GetStreamEffect@EffectPack@@QEAAJU_GUID@@HW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetStreamEffect(_GUID,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x1800a6ca8  mov     edi, eax
0x1800a6caa  test    eax, eax
0x1800a6cac  jns     short loc_1800A6D02
0x1800a6cae  mov     edx, 133h; void *
0x1800a6cb3  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a6cba  mov     r9d, eax; char *
0x1800a6cbd  mov     rcx, [rbp+3Fh]; this
0x1800a6cc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6cc6  nop
0x1800a6cc7  lea     rcx, [rbp+37h+arg_0]
0x1800a6ccb  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800a6cd0  nop
0x1800a6cd1  lea     rcx, [rsp+130h+var_D0]
0x1800a6cd6  xor     edx, edx
0x1800a6cd8  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x1800a6cdd  jmp     loc_1800A79CC
0x1800a6ce2  mov     [rbp+37h+arg_0], r13
0x1800a6ce6  xor     r9d, r9d; struct IAudioProcessingObject **
0x1800a6ce9  lea     r8, [rbp+37h+arg_0]; struct ICompositeSystemEffect **
0x1800a6ced  mov     edx, r14d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800a6cf0  call    ?GetLfx@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUICompositeSystemEffect@@PEAPEAUIAudioProcessingObject@@PEAPEAUIAudioSystemEffects2@@@Z; EffectPack::GetLfx(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,ICompositeSystemEffect * *,IAudioProcessingObject * *,IAudioSystemEffects2 * *)
0x1800a6cf5  mov     edi, eax
0x1800a6cf7  test    eax, eax
0x1800a6cf9  jns     short loc_1800A6D02
0x1800a6cfb  mov     edx, 138h
0x1800a6d00  jmp     short loc_1800A6CB3
0x1800a6d02  mov     rcx, [rbp+37h+arg_0]
0x1800a6d06  test    rcx, rcx
0x1800a6d09  jz      short loc_1800A6D3B
0x1800a6d0b  mov     rax, [rcx]
0x1800a6d0e  lea     rdx, [rsp+130h+var_D0]
0x1800a6d13  mov     qword ptr [rbp+37h+rclsid.Data1], rdx
0x1800a6d17  mov     qword ptr [rbp+37h+rclsid.Data4], r13
0x1800a6d1b  mov     [rbp+37h+var_A0], 1
0x1800a6d1f  lea     r8, [rbp+37h+rclsid.Data4]
0x1800a6d23  lea     rdx, [rbp+37h+var_90]
0x1800a6d27  mov     rax, [rax+20h]
0x1800a6d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6d30  nop
0x1800a6d31  lea     rcx, [rbp+37h+rclsid]
0x1800a6d35  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800a6d3a  nop
0x1800a6d3b  lea     rcx, [rbp+37h+arg_0]
0x1800a6d3f  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800a6d44  mov     edx, [rbp+37h+var_90]
0x1800a6d47  mov     ecx, ebx
0x1800a6d49  test    ebx, ebx
0x1800a6d4b  jz      loc_1800A6F1A
0x1800a6d51  sub     ecx, 1
0x1800a6d54  jz      loc_1800A6E09
0x1800a6d5a  sub     ecx, 1
0x1800a6d5d  jz      short loc_1800A6D73
0x1800a6d5f  cmp     ecx, 1
0x1800a6d62  jz      short loc_1800A6D73
0x1800a6d64  mov     edi, 80070057h
0x1800a6d69  mov     edx, 1B0h
0x1800a6d6e  jmp     loc_1800A6F54
0x1800a6d73  mov     edi, 17Ch
0x1800a6d78  mov     ecx, edi; cb
0x1800a6d7a  call    cs:__imp_CoTaskMemAlloc
0x1800a6d80  mov     rdx, rax
0x1800a6d83  lea     rcx, [rsp+130h+var_C8]
0x1800a6d88  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x1800a6d8d  mov     rsi, [rsp+130h+var_C8]
0x1800a6d92  test    rsi, rsi
0x1800a6d95  jnz     short loc_1800A6D9F
0x1800a6d97  lea     edx, [rdi+24h]
0x1800a6d9a  jmp     loc_1800A6F4F
0x1800a6d9f  mov     ebx, 3
0x1800a6da4  mov     r8, rdi; Size
0x1800a6da7  xor     edx, edx; Val
0x1800a6da9  mov     rcx, rsi; void *
0x1800a6dac  call    memset_0
0x1800a6db1  lea     eax, [r14-2]
0x1800a6db5  test    eax, 0FFFFFFFDh
0x1800a6dba  lea     eax, [rbx-2]
0x1800a6dbd  cmovnz  eax, [rbp+37h+arg_18]
0x1800a6dc1  mov     [rsi], eax
0x1800a6dc3  mov     [rsi+88h], r15d
0x1800a6dca  mov     [rsi+148h], ebx
0x1800a6dd0  movups  xmm0, xmmword ptr cs:_GUID_07252659_bb6b_4b79_b78b_623f6699a579.Data1
0x1800a6dd7  movdqu  xmmword ptr [rsi+14Ch], xmm0
0x1800a6ddf  movups  xmm1, xmmword ptr cs:_GUID_3dc09436_7d83_4ba0_addc_cd47f996c5ba.Data1
0x1800a6de6  movdqu  xmmword ptr [rsi+15Ch], xmm1
0x1800a6dee  movups  xmm0, xmmword ptr cs:_GUID_06587e71_f043_403a_bf49_cb591ba6e103.Data1
0x1800a6df5  movdqu  xmmword ptr [rsi+16Ch], xmm0
0x1800a6dfd  mov     [rsi+98h], r13d
0x1800a6e04  jmp     loc_1800A70E2
0x1800a6e09  lea     ebx, [rdx+2]
0x1800a6e0c  mov     edi, ebx
0x1800a6e0e  shl     rdi, 4
0x1800a6e12  lea     rcx, [rdi+14Ch]; cb
0x1800a6e19  call    cs:__imp_CoTaskMemAlloc
0x1800a6e1f  mov     rdx, rax
0x1800a6e22  lea     rcx, [rsp+130h+var_C8]
0x1800a6e27  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x1800a6e2c  mov     rsi, [rsp+130h+var_C8]
0x1800a6e31  test    rsi, rsi
0x1800a6e34  jnz     short loc_1800A6E40
0x1800a6e36  mov     edx, 17Dh
0x1800a6e3b  jmp     loc_1800A6F4F
0x1800a6e40  lea     r8, [rdi+14Ch]; Size
0x1800a6e47  xor     edx, edx; Val
0x1800a6e49  mov     rcx, rsi; void *
0x1800a6e4c  call    memset_0
0x1800a6e51  mov     dword ptr [rsi], 1
0x1800a6e57  mov     [rsi+88h], r15d
0x1800a6e5e  mov     [rsi+98h], r13d
0x1800a6e65  mov     [rsi+148h], r13d
0x1800a6e6c  mov     rax, [rbp+37h+arg_B0]
0x1800a6e73  mov     [rsi+100h], rax
0x1800a6e7a  mov     rax, [rbp+37h+arg_B8]
0x1800a6e81  mov     [rsi+108h], rax
0x1800a6e88  cmp     [rbp+37h+arg_A8], r13b
0x1800a6e8f  jz      short loc_1800A6E9F
0x1800a6e91  mov     rax, [rbp+37h+arg_98]
0x1800a6e98  mov     [rsi+0F8h], rax
0x1800a6e9f  mov     edx, r13d
0x1800a6ea2  cmp     edx, [rbp+37h+var_90]
0x1800a6ea5  jnb     short loc_1800A6EF5
0x1800a6ea7  mov     ecx, [rsi+148h]
0x1800a6ead  cmp     ecx, 1Fh
0x1800a6eb0  ja      short loc_1800A6EE9
0x1800a6eb2  mov     eax, 1
0x1800a6eb7  shl     eax, cl
0x1800a6eb9  or      [rsi+98h], eax
0x1800a6ebf  mov     ecx, edx
0x1800a6ec1  add     rcx, rcx
0x1800a6ec4  mov     rax, [rsp+130h+var_D0]
0x1800a6ec9  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800a6ecd  mov     eax, [rsi+148h]
0x1800a6ed3  add     rax, rax
0x1800a6ed6  movdqu  xmmword ptr [rsi+rax*8+14Ch], xmm0
0x1800a6edf  inc     dword ptr [rsi+148h]
0x1800a6ee5  inc     edx
0x1800a6ee7  jmp     short loc_1800A6EA2
0x1800a6ee9  mov     edi, 8000FFFFh
0x1800a6eee  mov     edx, 18Ch
0x1800a6ef3  jmp     short loc_1800A6F54
0x1800a6ef5  mov     eax, [rsi+148h]
0x1800a6efb  add     rax, rax
0x1800a6efe  movups  xmm0, xmmword ptr cs:_GUID_3dc09436_7d83_4ba0_addc_cd47f996c5ba.Data1
0x1800a6f05  movdqu  xmmword ptr [rsi+rax*8+14Ch], xmm0
0x1800a6f0e  movups  xmm0, xmmword ptr cs:_GUID_06587e71_f043_403a_bf49_cb591ba6e103.Data1
0x1800a6f15  jmp     loc_1800A70C4
0x1800a6f1a  lea     ebx, [rdx+4]
0x1800a6f1d  mov     dword ptr [rbp+37h+arg_0], ebx
0x1800a6f20  mov     edi, ebx
0x1800a6f22  shl     rdi, 4
0x1800a6f26  lea     rcx, [rdi+14Ch]; cb
0x1800a6f2d  call    cs:__imp_CoTaskMemAlloc
0x1800a6f33  mov     rdx, rax
0x1800a6f36  lea     rcx, [rsp+130h+var_C8]
0x1800a6f3b  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x1800a6f40  mov     rsi, [rsp+130h+var_C8]
0x1800a6f45  test    rsi, rsi
0x1800a6f48  jnz     short loc_1800A6F6C
0x1800a6f4a  mov     edx, 146h; void *
0x1800a6f4f  mov     edi, 8007000Eh
0x1800a6f54  mov     rcx, [rbp+3Fh]; this
0x1800a6f58  mov     r9d, edi; char *
0x1800a6f5b  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800a6f62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6f67  jmp     loc_1800A6CD1
0x1800a6f6c  lea     r8, [rdi+14Ch]; Size
0x1800a6f73  xor     edx, edx; Val
0x1800a6f75  mov     rcx, rsi; void *
0x1800a6f78  call    memset_0
0x1800a6f7d  mov     [rsi], r13d
0x1800a6f80  mov     [rsi+88h], r15d
0x1800a6f87  mov     [rsi+148h], r13d
0x1800a6f8e  mov     [rsi+98h], r13d
0x1800a6f95  cmp     [rbp+37h+arg_A0], r13b
0x1800a6f9c  jz      short loc_1800A6FD2
0x1800a6f9e  mov     ecx, r13d
0x1800a6fa1  mov     eax, 1
0x1800a6fa6  shl     eax, cl
0x1800a6fa8  mov     [rsi+98h], eax
0x1800a6fae  mov     eax, [rsi+148h]
0x1800a6fb4  add     rax, rax
0x1800a6fb7  movups  xmm0, xmmword ptr cs:_GUID_7bf2a436_2a30_4797_90ee_0f66b8426d75.Data1
0x1800a6fbe  movdqu  xmmword ptr [rsi+rax*8+14Ch], xmm0
0x1800a6fc7  inc     dword ptr [rsi+148h]
0x1800a6fcd  jmp     loc_1800A7085
0x1800a6fd2  cmp     r13d, [rbp+37h+var_90]
0x1800a6fd6  jnb     loc_1800A7082
0x1800a6fdc  mov     edi, r13d
0x1800a6fdf  add     rdi, rdi
0x1800a6fe2  mov     rcx, [rsp+130h+var_D0]
0x1800a6fe7  mov     rax, [rcx+rdi*8]
0x1800a6feb  sub     rax, qword ptr cs:_GUID_4be8a061_c73b_4f23_8114_317aae3e8698.Data1
0x1800a6ff2  jnz     short loc_1800A7000
0x1800a6ff4  mov     rax, [rcx+rdi*8+8]
0x1800a6ff9  sub     rax, qword ptr cs:_GUID_4be8a061_c73b_4f23_8114_317aae3e8698.Data4
0x1800a7000  test    rax, rax
0x1800a7003  jnz     short loc_1800A7032
0x1800a7005  call    IsGetDefaultSpatialRenderingModePresent
0x1800a700a  test    al, al
0x1800a700c  jz      short loc_1800A7032
0x1800a700e  xor     ecx, ecx; BindingHandle
0x1800a7010  call    cs:__imp_RpcImpersonateClient
0x1800a7016  test    eax, eax
0x1800a7018  js      short loc_1800A7032
0x1800a701a  mov     ecx, [rbp+37h+arg_40]
0x1800a7020  call    cs:__imp_IsVirtualSurroundAllowedForProcess
0x1800a7026  mov     ebx, eax
  ... truncated ...
```
