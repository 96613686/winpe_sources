# FSSource::Shutdown(void)

- ea: `0x1800a2670`
- end: `0x1800a2afa`
- name: `?Shutdown@FSSource@@UEAAJXZ`
- size: `1162`
- prototype: `__int64 __fastcall(FSSource *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180091fd4`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180014f08`
- `0x180018998`
- `0x18004d714`
- `0x18004d748`
- `0x18004f37c`
- `0x180061080`
- `0x18009e0e0`
- `0x1800a0600`
- `0x1800a2584`
- `0x1800a2670`
- `0x1800b0bc8`
- `0x1800b3990`
- `0x1800b3be0`
- `0x1800b4860`
- `0x1800b5c08`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a27da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a287c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2a0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2ad3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a27da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a287c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2a0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2ad3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a26a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a278e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a27ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a29ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a26a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a278e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a27ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a29ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a273a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a273a`
- `MFPlat!MFUnlockWorkQueue` at `0x1800a2a9f`
- `MFPlat!MFUnlockWorkQueue` at `0x1800a2a9f`

## pseudocode

```c
__int64 __fastcall FSSource::Shutdown(FSSource *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  char v3; // si
  CFSEventPayload *v4; // rbx
  FSString *v5; // rax
  const char *String; // rax
  DWORD CurrentThreadId; // eax
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 i; // rbx
  void (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rsi
  void (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rbx
  __int64 j; // rbx
  __int64 v19; // rcx
  __int64 k; // rbx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  DWORD v24; // ecx
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  CFSEventPayload *v27; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int128 v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h]
  _DWORD v32[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+88h] [rbp-78h] BYREF
  int v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+94h] [rbp-6Ch]
  _BYTE v36[1792]; // [rsp+290h] [rbp+190h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v4 = 0;
  v26 = 0;
  v27 = 0;
  if ( !*((_BYTE *)this + 1024) )
  {
    FSSourceWatchdog::FSSourceWatchdog((FSSourceWatchdog *)v36, this, *((struct IMFVideoDeviceStateStats **)this + 125));
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v5 = ClientContextInfoTrace::ClientContextInfoTrace(
             (ClientContextInfoTrace *)&v30,
             *((struct IFSClientContextInfo **)this + 17));
      String = FSString::GetString(v5);
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        224,
        (unsigned int)&WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
        (_DWORD)this,
        (__int64)String);
      v3 = 1;
    }
    if ( (v3 & 1) != 0 )
      FSString::~FSString((FSString *)&v30);
    CurrentThreadId = GetCurrentThreadId();
    v8 = (__int64 *)*((_QWORD *)this + 125);
    *(_QWORD *)&v28 = CurrentThreadId | 0xFFFFFFFF00000000uLL;
    *((_QWORD *)&v28 + 1) = this;
    v29 = 0;
    v9 = *v8;
    v30 = v28;
    v31 = 0;
    (*(void (__fastcall **)(__int64 *, __int128 *))(v9 + 24))(v8, &v30);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
    if ( FSSource::ShouldNotifySensorActivity(this) )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 71) + 40LL))(
        *((_QWORD *)this + 71),
        *((_QWORD *)this + 72),
        1);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 576);
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 568);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
    if ( *((_QWORD *)this + 64) )
    {
      memset_0(&v33, 0, 0x208u);
      v10 = *(_QWORD *)this;
      v32[1] = 528;
      v32[0] = 9;
      v11 = (*(__int64 (__fastcall **)(FSSource *))(v10 + 536))(this);
      v12 = *((_QWORD *)this + 64);
      v33 = v11;
      v34 = 6;
      v35 = -1072873851;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 128LL))(v12);
      FSSource::QueueFSNotification(this, v32, v13, 2, &v27);
      v4 = v27;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
    if ( v4 )
      CFSEventPayload::WaitForCompletion(v4, v14);
    FSSourceWatchdog::Start(v36, 4, -200000000);
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 74); i = (unsigned int)(i + 1) )
      FSStream::Shutdown(*(FSStream **)(*((_QWORD *)this + 36) + 8 * i));
    v16 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 33);
    if ( v16 )
    {
      v17 = **v16;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v26);
      v17(v16, &GUID_28f54685_06fd_11d2_b27a_00a0c9223196, &v26);
      for ( j = 0; (unsigned int)j < *((_DWORD *)this + 50); j = (unsigned int)(j + 1) )
      {
        v19 = *(_QWORD *)(*((_QWORD *)this + 24) + 8 * j);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 72LL))(v19, v26);
      }
      CTUnkArray<IFSMemStream>::RemoveAll((char *)this + 192);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 33) + 96LL))(*((_QWORD *)this + 33));
    }
    AutoWatchdogTimer::Stop((AutoWatchdogTimer *)v36);
    (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 125) + 48LL))(*((_QWORD *)this + 125), &v28);
    for ( k = 0; (unsigned int)k < *((_DWORD *)this + 56); k = (unsigned int)(k + 1) )
    {
      v21 = *(_QWORD *)(*((_QWORD *)this + 27) + 8 * k);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 72LL))(v21, v26);
    }
    CTUnkArray<IFSMemStream>::RemoveAll((char *)this + 216);
    v22 = *((_QWORD *)this + 32);
    if ( v22 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 336LL))(v22, 0);
    FSSource::SetAsyncStatus(this, -1072873851);
    *((_BYTE *)this + 1024) = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
    CTUnkArray<IFSMemStream>::RemoveAll((char *)this + 392);
    CTUnkArray<IFSMemStream>::RemoveAll((char *)this + 416);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
    v23 = *((_QWORD *)this + 123);
    if ( v23 && *((_BYTE *)this + 992) )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 32LL))(v23, *((_QWORD *)this + 32));
      *((_BYTE *)this + 992) = 0;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 320);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 312);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 1056);
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 225, &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids, this);
    v24 = *((_DWORD *)this + 71);
    if ( v24 )
    {
      MFUnlockWorkQueue(v24);
      *((_DWORD *)this + 71) = 0;
    }
    FSSourceWatchdog::~FSSourceWatchdog((FSSourceWatchdog *)v36);
  }
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v27);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v26);
  LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x1800a2670  push    rbp
0x1800a2672  push    rbx
0x1800a2673  push    rsi
0x1800a2674  push    rdi
0x1800a2675  push    r14
0x1800a2677  push    r15
0x1800a2679  lea     rbp, [rsp-8A8h]
0x1800a2681  sub     rsp, 9A8h
0x1800a2688  mov     rax, cs:__security_cookie
0x1800a268f  xor     rax, rsp
0x1800a2692  mov     [rbp+8D0h+var_40], rax
0x1800a2699  lea     rdi, [rcx+60h]
0x1800a269d  mov     r14, rcx
0x1800a26a0  xor     esi, esi
0x1800a26a2  mov     rcx, rdi; lpCriticalSection
0x1800a26a5  mov     dword ptr [rsp+9D0h+var_9A0], esi
0x1800a26a9  call    cs:__imp_EnterCriticalSection
0x1800a26af  xor     ebx, ebx
0x1800a26b1  mov     [rsp+9D0h+var_9A0], rsi
0x1800a26b6  mov     [rsp+9D0h+var_998], rbx
0x1800a26bb  cmp     [r14+400h], bl
0x1800a26c2  jnz     loc_1800A2ABC
0x1800a26c8  mov     r8, [r14+3E8h]; struct IMFVideoDeviceStateStats *
0x1800a26cf  lea     rcx, [rbp+8D0h+var_740]; this
0x1800a26d6  mov     rdx, r14; struct IFSSource *
0x1800a26d9  call    ??0FSSourceWatchdog@@QEAA@PEAUIFSSource@@PEAUIMFVideoDeviceStateStats@@@Z; FSSourceWatchdog::FSSourceWatchdog(IFSSource *,IMFVideoDeviceStateStats *)
0x1800a26de  cmp     cs:byte_18010EC4D, 8
0x1800a26e5  jb      short loc_1800A272A
0x1800a26e7  mov     rdx, [r14+88h]; struct IFSClientContextInfo *
0x1800a26ee  lea     rcx, [rsp+9D0h+var_970]; this
0x1800a26f3  call    ??0ClientContextInfoTrace@@QEAA@PEAUIFSClientContextInfo@@@Z; ClientContextInfoTrace::ClientContextInfoTrace(IFSClientContextInfo *)
0x1800a26f8  mov     rcx, rax; this
0x1800a26fb  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800a2700  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2707  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x1800a270e  mov     edx, 0E0h
0x1800a2713  mov     [rsp+9D0h+var_9B0], rax
0x1800a2718  mov     r9, r14
0x1800a271b  mov     rcx, [rcx+0D8h]
0x1800a2722  call    WPP_SF_qs
0x1800a2727  lea     esi, [rbx+1]
0x1800a272a  test    sil, 1
0x1800a272e  jz      short loc_1800A273A
0x1800a2730  lea     rcx, [rsp+9D0h+var_970]; this
0x1800a2735  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800a273a  call    cs:__imp_GetCurrentThreadId
0x1800a2740  mov     rcx, [r14+3E8h]
0x1800a2747  lea     rdx, [rsp+9D0h+var_970]
0x1800a274c  mov     dword ptr [rsp+9D0h+var_990], eax
0x1800a2750  mov     dword ptr [rsp+9D0h+var_990+4], 0FFFFFFFFh
0x1800a2758  mov     qword ptr [rsp+9D0h+var_990+8], r14
0x1800a275d  movups  xmm0, [rsp+9D0h+var_990]
0x1800a2762  mov     [rsp+9D0h+var_980], rbx
0x1800a2767  mov     rax, [rcx]
0x1800a276a  movsd   xmm1, [rsp+9D0h+var_980]
0x1800a2770  movaps  [rsp+9D0h+var_970], xmm0
0x1800a2775  movsd   [rsp+9D0h+var_960], xmm1
0x1800a277b  mov     rax, [rax+18h]
0x1800a277f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2784  lea     r15, [r14+210h]
0x1800a278b  mov     rcx, r15; lpCriticalSection
0x1800a278e  call    cs:__imp_EnterCriticalSection
0x1800a2794  mov     rcx, r14; this
0x1800a2797  call    ?ShouldNotifySensorActivity@FSSource@@IEBA_NXZ; FSSource::ShouldNotifySensorActivity(void)
0x1800a279c  test    al, al
0x1800a279e  jz      short loc_1800A27CB
0x1800a27a0  mov     rcx, [r14+238h]
0x1800a27a7  lea     rsi, [r14+240h]
0x1800a27ae  mov     rdx, [rsi]
0x1800a27b1  mov     r8d, 1
0x1800a27b7  mov     rax, [rcx]
0x1800a27ba  mov     rax, [rax+28h]
0x1800a27be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a27c3  mov     rcx, rsi
0x1800a27c6  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a27cb  lea     rcx, [r14+238h]
0x1800a27d2  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a27d7  mov     rcx, r15; lpCriticalSection
0x1800a27da  call    cs:__imp_LeaveCriticalSection
0x1800a27e0  lea     rsi, [r14+1C0h]
0x1800a27e7  mov     rcx, rsi; lpCriticalSection
0x1800a27ea  call    cs:__imp_EnterCriticalSection
0x1800a27f0  mov     r15d, 0C00D3E85h
0x1800a27f6  cmp     [r14+200h], rbx
0x1800a27fd  jz      short loc_1800A2879
0x1800a27ff  xor     edx, edx; Val
0x1800a2801  lea     rcx, [rbp+8D0h+var_948]; void *
0x1800a2805  mov     r8d, 208h; Size
0x1800a280b  call    memset_0
0x1800a2810  mov     rax, [r14]
0x1800a2813  mov     rcx, r14
0x1800a2816  mov     [rbp+8D0h+var_94C], 210h
0x1800a281d  mov     [rbp+8D0h+var_950], 9
0x1800a2824  mov     rax, [rax+218h]
0x1800a282b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2830  mov     rcx, [r14+200h]
0x1800a2837  mov     [rbp+8D0h+var_948], rax
0x1800a283b  mov     [rbp+8D0h+var_940], 6
0x1800a2842  mov     [rbp+8D0h+var_93C], r15d
0x1800a2846  mov     rax, [rcx]
0x1800a2849  mov     rax, [rax+80h]
0x1800a2850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2855  lea     rcx, [rsp+9D0h+var_998]
0x1800a285a  mov     r9d, 2
0x1800a2860  mov     [rsp+9D0h+var_9B0], rcx
0x1800a2865  lea     rdx, [rbp+8D0h+var_950]
0x1800a2869  mov     rcx, r14
0x1800a286c  mov     r8, rax
0x1800a286f  call    ?QueueFSNotification@FSSource@@IEAAJAEBU__MIDL___MIDL_itf_fsclienttypes_0000_0000_0015@@_KW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0004@@PEAPEAVCFSEventPayload@@@Z; FSSource::QueueFSNotification(__MIDL___MIDL_itf_fsclienttypes_0000_0000_0015 const &,unsigned __int64,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0004,CFSEventPayload * *)
0x1800a2874  mov     rbx, [rsp+9D0h+var_998]
0x1800a2879  mov     rcx, rsi; lpCriticalSection
0x1800a287c  call    cs:__imp_LeaveCriticalSection
0x1800a2882  test    rbx, rbx
0x1800a2885  jz      short loc_1800A288F
0x1800a2887  mov     rcx, rbx; this
0x1800a288a  call    ?WaitForCompletion@CFSEventPayload@@QEAAJ_J@Z; CFSEventPayload::WaitForCompletion(__int64)
0x1800a288f  mov     edx, 4
0x1800a2894  lea     rcx, [rbp+8D0h+var_740]
0x1800a289b  mov     r8, 0FFFFFFFFF4143E00h
0x1800a28a2  call    ?Start@FSSourceWatchdog@@UEAAXW4__MIDL___MIDL_itf_mfdeviceinternal_0000_0049_0002@@_J@Z; FSSourceWatchdog::Start(__MIDL___MIDL_itf_mfdeviceinternal_0000_0049_0002,__int64)
0x1800a28a7  xor     ebx, ebx
0x1800a28a9  cmp     [r14+128h], ebx
0x1800a28b0  jbe     short loc_1800A28CD
0x1800a28b2  mov     rcx, [r14+120h]
0x1800a28b9  mov     rcx, [rcx+rbx*8]; this
0x1800a28bd  call    ?Shutdown@FSStream@@QEAAXXZ; FSStream::Shutdown(void)
0x1800a28c2  inc     ebx
0x1800a28c4  cmp     ebx, [r14+128h]
0x1800a28cb  jb      short loc_1800A28B2
0x1800a28cd  mov     rsi, [r14+108h]
0x1800a28d4  test    rsi, rsi
0x1800a28d7  jz      short loc_1800A2951
0x1800a28d9  mov     rax, [rsi]
0x1800a28dc  lea     rcx, [rsp+9D0h+var_9A0]
0x1800a28e1  mov     rbx, [rax]
0x1800a28e4  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a28e9  lea     r8, [rsp+9D0h+var_9A0]
0x1800a28ee  mov     rcx, rsi
0x1800a28f1  lea     rdx, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x1800a28f8  mov     rax, rbx
0x1800a28fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2900  xor     ebx, ebx
0x1800a2902  cmp     [r14+0C8h], ebx
0x1800a2909  jbe     short loc_1800A2932
0x1800a290b  mov     rax, [r14+0C0h]
0x1800a2912  mov     rdx, [rsp+9D0h+var_9A0]
0x1800a2917  mov     rcx, [rax+rbx*8]
0x1800a291b  mov     rax, [rcx]
0x1800a291e  mov     rax, [rax+48h]
0x1800a2922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2927  inc     ebx
0x1800a2929  cmp     ebx, [r14+0C8h]
0x1800a2930  jb      short loc_1800A290B
0x1800a2932  lea     rcx, [r14+0C0h]
0x1800a2939  call    ?RemoveAll@?$CTUnkArray@UIFSMemStream@@@@QEAAXXZ; CTUnkArray<IFSMemStream>::RemoveAll(void)
0x1800a293e  mov     rcx, [r14+108h]
0x1800a2945  mov     rax, [rcx]
0x1800a2948  mov     rax, [rax+60h]
0x1800a294c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2951  lea     rcx, [rbp+8D0h+var_740]; this
0x1800a2958  call    ?Stop@AutoWatchdogTimer@@UEAAXXZ; AutoWatchdogTimer::Stop(void)
0x1800a295d  mov     rcx, [r14+3E8h]
0x1800a2964  lea     rdx, [rsp+9D0h+var_990]
0x1800a2969  mov     rax, [rcx]
0x1800a296c  mov     rax, [rax+30h]
0x1800a2970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2975  xor     ebx, ebx
0x1800a2977  cmp     [r14+0E0h], ebx
0x1800a297e  jbe     short loc_1800A29A7
0x1800a2980  mov     rax, [r14+0D8h]
0x1800a2987  mov     rdx, [rsp+9D0h+var_9A0]
0x1800a298c  mov     rcx, [rax+rbx*8]
0x1800a2990  mov     rax, [rcx]
0x1800a2993  mov     rax, [rax+48h]
0x1800a2997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a299c  inc     ebx
0x1800a299e  cmp     ebx, [r14+0E0h]
0x1800a29a5  jb      short loc_1800A2980
0x1800a29a7  lea     rcx, [r14+0D8h]
0x1800a29ae  call    ?RemoveAll@?$CTUnkArray@UIFSMemStream@@@@QEAAXXZ; CTUnkArray<IFSMemStream>::RemoveAll(void)
0x1800a29b3  mov     rcx, [r14+100h]
0x1800a29ba  test    rcx, rcx
0x1800a29bd  jz      short loc_1800A29D0
0x1800a29bf  mov     rax, [rcx]
0x1800a29c2  xor     edx, edx
0x1800a29c4  mov     rax, [rax+150h]
0x1800a29cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a29d0  mov     edx, r15d; int
0x1800a29d3  mov     rcx, r14; this
0x1800a29d6  call    ?SetAsyncStatus@FSSource@@IEAAXJ@Z; FSSource::SetAsyncStatus(long)
0x1800a29db  lea     rbx, [r14+160h]
0x1800a29e2  mov     byte ptr [r14+400h], 1
0x1800a29ea  mov     rcx, rbx; lpCriticalSection
0x1800a29ed  call    cs:__imp_EnterCriticalSection
0x1800a29f3  lea     rcx, [r14+188h]
0x1800a29fa  call    ?RemoveAll@?$CTUnkArray@UIFSMemStream@@@@QEAAXXZ; CTUnkArray<IFSMemStream>::RemoveAll(void)
0x1800a29ff  lea     rcx, [r14+1A0h]
0x1800a2a06  call    ?RemoveAll@?$CTUnkArray@UIFSMemStream@@@@QEAAXXZ; CTUnkArray<IFSMemStream>::RemoveAll(void)
0x1800a2a0b  mov     rcx, rbx; lpCriticalSection
0x1800a2a0e  call    cs:__imp_LeaveCriticalSection
0x1800a2a14  mov     rcx, [r14+3D8h]
0x1800a2a1b  test    rcx, rcx
0x1800a2a1e  jz      short loc_1800A2A45
0x1800a2a20  cmp     byte ptr [r14+3E0h], 0
0x1800a2a28  jz      short loc_1800A2A45
0x1800a2a2a  mov     rax, [rcx]
0x1800a2a2d  mov     rdx, [r14+100h]
0x1800a2a34  mov     rax, [rax+20h]
0x1800a2a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2a3d  mov     byte ptr [r14+3E0h], 0
0x1800a2a45  lea     rcx, [r14+140h]
0x1800a2a4c  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a2a51  lea     rcx, [r14+138h]
0x1800a2a58  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a2a5d  lea     rcx, [r14+420h]
0x1800a2a64  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a2a69  cmp     cs:byte_18010EC4D, 8
0x1800a2a70  jb      short loc_1800A2A94
0x1800a2a72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2a79  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x1800a2a80  mov     edx, 0E1h
0x1800a2a85  mov     r9, r14
0x1800a2a88  mov     rcx, [rcx+0D8h]
0x1800a2a8f  call    WPP_SF_q
0x1800a2a94  mov     ecx, [r14+11Ch]; dwWorkQueue
0x1800a2a9b  test    ecx, ecx
0x1800a2a9d  jz      short loc_1800A2AB0
0x1800a2a9f  call    cs:__imp_MFUnlockWorkQueue
0x1800a2aa5  mov     dword ptr [r14+11Ch], 0
0x1800a2ab0  lea     rcx, [rbp+8D0h+var_740]; this
0x1800a2ab7  call    ??1FSSourceWatchdog@@UEAA@XZ; FSSourceWatchdog::~FSSourceWatchdog(void)
0x1800a2abc  lea     rcx, [rsp+9D0h+var_998]; void *
0x1800a2ac1  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a2ac6  lea     rcx, [rsp+9D0h+var_9A0]; void *
0x1800a2acb  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a2ad0  mov     rcx, rdi; lpCriticalSection
0x1800a2ad3  call    cs:__imp_LeaveCriticalSection
0x1800a2ad9  xor     eax, eax
0x1800a2adb  mov     rcx, [rbp+8D0h+var_40]
0x1800a2ae2  xor     rcx, rsp; StackCookie
0x1800a2ae5  call    __security_check_cookie
0x1800a2aea  add     rsp, 9A8h
0x1800a2af1  pop     r15
0x1800a2af3  pop     r14
0x1800a2af5  pop     rdi
0x1800a2af6  pop     rsi
0x1800a2af7  pop     rbx
0x1800a2af8  pop     rbp
0x1800a2af9  retn
```
