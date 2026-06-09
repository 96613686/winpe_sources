# FSStream::~FSStream(void)

- ea: `0x1800a6f78`
- end: `0x1800a7131`
- name: `??1FSStream@@MEAA@XZ`
- size: `441`
- prototype: `void __fastcall(FSStream *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800a7140`

## callees

- `0x1800041f0`
- `0x180005d98`
- `0x180008cf0`
- `0x1800095c8`
- `0x18000a460`
- `0x18000a4a8`
- `0x18004fc24`
- `0x1800a6f78`
- `0x1800a79a8`
- `0x1800b0bc8`
- `0x1800b1d38`
- `0x1800b1db0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a7060`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a711e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a7060`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a711e`

## pseudocode

```c
void __fastcall FSStream::~FSStream(FSStream *this)
{
  const struct std::nothrow_t *v2; // rdx
  const struct std::nothrow_t *v3; // rdx

  *(_QWORD *)this = &FSStream::`vftable';
  FSStream::Shutdown(this);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::GetImpl'::`2'::impl) )
    FSStream::CloseFirstFrameTimer(this);
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, this);
  wistd::unique_ptr<FSSStreamTelemetryWatchdog,wistd::default_delete<FSSStreamTelemetryWatchdog>>::reset(
    (char *)this + 768,
    0);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 760);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 752);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 744);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 736);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 720);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 696);
  FSStatTracker::~FSStatTracker((FSStream *)((char *)this + 568));
  operator delete(*((void **)this + 68), v2);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 472);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 448);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 408));
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 384);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 376);
  CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>((char *)this + 352);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 344);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 336);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 328);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 320);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 304);
  operator delete(*((void **)this + 30), v3);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 192);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 176);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 152);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 112);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 96);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 80);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 72);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  _InterlockedDecrement(&g_lRefModule);
}

```

## disassembly

```asm
0x1800a6f78  push    rbx
0x1800a6f7a  sub     rsp, 20h
0x1800a6f7e  lea     rax, ??_7FSStream@@6B@; const FSStream::`vftable'
0x1800a6f85  mov     rbx, rcx
0x1800a6f88  mov     [rcx], rax
0x1800a6f8b  call    ?Shutdown@FSStream@@QEAAXXZ; FSStream::Shutdown(void)
0x1800a6f90  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent> `wil::Feature<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::GetImpl(void)'::`2'::impl
0x1800a6f97  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::__private_IsEnabled(void)
0x1800a6f9c  test    al, al
0x1800a6f9e  jz      short loc_1800A6FA8
0x1800a6fa0  mov     rcx, rbx; this
0x1800a6fa3  call    ?CloseFirstFrameTimer@FSStream@@IEAAXXZ; FSStream::CloseFirstFrameTimer(void)
0x1800a6fa8  cmp     cs:byte_18010EC4D, 10h
0x1800a6faf  jb      short loc_1800A6FD3
0x1800a6fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6fb8  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800a6fbf  mov     edx, 0Dh
0x1800a6fc4  mov     r9, rbx
0x1800a6fc7  mov     rcx, [rcx+0D8h]
0x1800a6fce  call    WPP_SF_q
0x1800a6fd3  lea     rcx, [rbx+300h]
0x1800a6fda  xor     edx, edx
0x1800a6fdc  call    ?reset@?$unique_ptr@VFSSStreamTelemetryWatchdog@@U?$default_delete@VFSSStreamTelemetryWatchdog@@@wistd@@@wistd@@QEAAXPEAVFSSStreamTelemetryWatchdog@@@Z; wistd::unique_ptr<FSSStreamTelemetryWatchdog,wistd::default_delete<FSSStreamTelemetryWatchdog>>::reset(FSSStreamTelemetryWatchdog *)
0x1800a6fe1  lea     rcx, [rbx+2F8h]; void *
0x1800a6fe8  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a6fed  lea     rcx, [rbx+2F0h]; void *
0x1800a6ff4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a6ff9  lea     rcx, [rbx+2E8h]; void *
0x1800a7000  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a7005  lea     rcx, [rbx+2E0h]; void *
0x1800a700c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a7011  lea     rcx, [rbx+2D0h]; void *
0x1800a7018  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a701d  lea     rcx, [rbx+2B8h]; void *
0x1800a7024  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a7029  lea     rcx, [rbx+238h]; this
0x1800a7030  call    ??1FSStatTracker@@UEAA@XZ; FSStatTracker::~FSStatTracker(void)
0x1800a7035  mov     rcx, [rbx+220h]; void *
0x1800a703c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a7041  lea     rcx, [rbx+1D8h]; void *
0x1800a7048  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800a704d  lea     rcx, [rbx+1C0h]; void *
0x1800a7054  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800a7059  lea     rcx, [rbx+198h]; lpCriticalSection
0x1800a7060  call    cs:__imp_DeleteCriticalSection
0x1800a7066  lea     rcx, [rbx+180h]; void *
0x1800a706d  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a7072  lea     rcx, [rbx+178h]; void *
0x1800a7079  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a707e  lea     rcx, [rbx+160h]
0x1800a7085  call    ??1?$CTUnkArray@UIFSProcessActivity@@@@QEAA@XZ; CTUnkArray<IFSProcessActivity>::~CTUnkArray<IFSProcessActivity>(void)
0x1800a708a  lea     rcx, [rbx+158h]; void *
0x1800a7091  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a7096  lea     rcx, [rbx+150h]; void *
0x1800a709d  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a70a2  lea     rcx, [rbx+148h]; void *
0x1800a70a9  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a70ae  lea     rcx, [rbx+140h]; void *
0x1800a70b5  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a70ba  lea     rcx, [rbx+130h]; void *
0x1800a70c1  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a70c6  mov     rcx, [rbx+0F0h]; void *
0x1800a70cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a70d2  lea     rcx, [rbx+0C0h]; void *
0x1800a70d9  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a70de  lea     rcx, [rbx+0B0h]
0x1800a70e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a70ea  lea     rcx, [rbx+98h]; void *
0x1800a70f1  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a70f6  lea     rcx, [rbx+70h]; void *
0x1800a70fa  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800a70ff  lea     rcx, [rbx+60h]; void *
0x1800a7103  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a7108  lea     rcx, [rbx+50h]; void *
0x1800a710c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a7111  lea     rcx, [rbx+48h]; void *
0x1800a7115  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a711a  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800a711e  call    cs:__imp_DeleteCriticalSection
0x1800a7124  lock dec cs:?g_lRefModule@@3JA; long g_lRefModule
0x1800a712b  add     rsp, 20h
0x1800a712f  pop     rbx
0x1800a7130  retn
```
