# FSStream::InternalStart(IFSClientContextInfo *,ulong,unsigned __int64)

- ea: `0x1800abb70`
- end: `0x1800ac1fe`
- name: `?InternalStart@FSStream@@MEAAJPEAUIFSClientContextInfo@@K_K@Z`
- size: `1678`
- prototype: `__int64 __fastcall(FSStream *__hidden this, struct IFSClientContextInfo *, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800039f0`
- `0x180003e20`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180017ccc`
- `0x18001c674`
- `0x18003b884`
- `0x180060fb0`
- `0x180061080`
- `0x1800a7968`
- `0x1800abb70`
- `0x1800b1d38`
- `0x1800b1db0`
- `0x1800b203c`
- `0x1800b3918`
- `0x1800b3990`
- `0x1800b3be0`
- `0x1800b49a0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abd79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abd79`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800abd56`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800abd56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ac0f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ac0f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800abbbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800abbbd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ac1d4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800ac1d4`
- `MFPlat!MFGetSystemTime` at `0x1800abe74`
- `MFPlat!MFGetSystemTime` at `0x1800abe74`

## pseudocode

```c
__int64 __fastcall FSStream::InternalStart(
        FSStream *this,
        struct IFSClientContextInfo *a2,
        unsigned int a3,
        struct _FILETIME a4)
{
  __int64 v5; // r15
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  int v10; // ebx
  char v11; // r13
  __int64 v12; // rdx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  void *v15; // rax
  __int64 v16; // r8
  MFTIME v17; // rax
  _QWORD *v18; // r14
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 (__fastcall *v21)(FSStream *, struct IFSClientContextInfo *, _QWORD, struct _FILETIME, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdx
  struct _TP_TIMER *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  PROPVARIANT pvar[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h]
  __int128 v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  _QWORD v40[7]; // [rsp+B0h] [rbp-50h] BYREF
  int v41; // [rsp+E8h] [rbp-18h]
  FSStream *v42; // [rsp+7B0h] [rbp+6B0h]

  pftDueTime = a4;
  v37 = 0;
  *(_OWORD *)pvar = 0;
  v35 = 0;
  v5 = a3;
  *(_QWORD *)&v33 = GetCurrentThreadId() | 0xFFFFFFFF00000000uLL;
  v34 = 2;
  *((_QWORD *)&v33 + 1) = this;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qddd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      292,
      &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
      this,
      *((_DWORD *)this + 22),
      *((_DWORD *)this + 23),
      *((_DWORD *)this + 40));
  FSSourceWatchdog::FSSourceWatchdog(
    (FSSourceWatchdog *)v40,
    *((struct IFSSource **)this + 41),
    *((struct IMFVideoDeviceStateStats **)this + 92));
  v7 = (__int64 *)*((_QWORD *)this + 92);
  v40[0] = &FSStreamWatchdog::`vftable';
  v42 = this;
  v41 = 2;
  v8 = *v7;
  v38 = v33;
  v39 = v34;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v8 + 24))(v7, &v38);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 0;
    if ( !g_wppLevels )
      goto LABEL_58;
    v12 = 293;
    goto LABEL_6;
  }
  v11 = 1;
  FSStreamWatchdog::Start(v40, 2, (-(__int64)(*((_BYTE *)this + 732) != 0) & 0xFFFFFFFD40AA4A00uLL) - 200000000);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::GetImpl'::`2'::impl) )
  {
    FSStream::CancelFirstFrameTimer(this);
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 24LL))(*((_QWORD *)this + 42))
      || (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 24LL))(*((_QWORD *)this + 42)) == 4 )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 198);
      if ( !*((_QWORD *)this + 97) )
      {
        ThreadpoolTimer = CreateThreadpoolTimer(FSStream::FirstFrameTimerCallback, this, 0);
        *((_QWORD *)this + 97) = ThreadpoolTimer;
        if ( !ThreadpoolTimer )
        {
          if ( byte_18010EC4D )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              294,
              &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
              this,
              LastError);
          }
        }
      }
    }
  }
  else
  {
    wistd::unique_ptr<FSSStreamTelemetryWatchdog,wistd::default_delete<FSSStreamTelemetryWatchdog>>::reset(
      (char *)this + 768,
      0);
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 24LL))(*((_QWORD *)this + 42)) )
    {
      v15 = operator new(0x310u);
      if ( v15 )
        v15 = (void *)FSSStreamTelemetryWatchdog::FSSStreamTelemetryWatchdog(v15, *((_QWORD *)this + 41), v16, this);
      wistd::unique_ptr<FSSStreamTelemetryWatchdog,wistd::default_delete<FSSStreamTelemetryWatchdog>>::reset(
        (char *)this + 768,
        v15);
    }
  }
  v9 = (*(__int64 (__fastcall **)(FSStream *, struct IFSClientContextInfo *, _QWORD))(*(_QWORD *)this + 152LL))(
         this,
         a2,
         (unsigned int)v5);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 295;
LABEL_6:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, this, v9);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 280LL))(
         *((_QWORD *)this + 10),
         *((unsigned int *)this + 22));
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( !*((_DWORD *)this + 40) )
    {
      v17 = MFGetSystemTime();
      *((_QWORD *)this + 86) = v17;
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_qDDq(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          297,
          &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
          this,
          *((_DWORD *)this + 22),
          *((_DWORD *)this + 23),
          v17);
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, PROPVARIANT *))(**((_QWORD **)this + 9) + 72LL))(
           *((_QWORD *)this + 9),
           *((_QWORD *)this + 10),
           0,
           pvar);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( g_wppLevels )
      {
        v12 = 298;
        goto LABEL_6;
      }
      goto LABEL_58;
    }
    v18 = (_QWORD *)((char *)this + 384);
    if ( *((_QWORD *)this + 48) )
    {
      v9 = (*(__int64 (__fastcall **)(FSStream *))(*(_QWORD *)this + 232LL))(this);
      v10 = v9;
      if ( v9 < 0 )
      {
        if ( g_wppLevels )
        {
          v12 = 299;
          goto LABEL_6;
        }
        goto LABEL_58;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 56LL))(*v18);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 384);
    }
    v19 = *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v5);
    if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 352LL))(v19, 62)
      || ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 41) + 504LL))(*((_QWORD *)this + 41)) & 2) != 0 )
    {
      v20 = *(_QWORD *)this;
      v31 = 0;
      v21 = *(__int64 (__fastcall **)(FSStream *, struct IFSClientContextInfo *, _QWORD, struct _FILETIME, __int64 *))(v20 + 160);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v31);
      v22 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v21)(
              this,
              a2,
              *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v5),
              pftDueTime,
              &v31);
      v10 = v22;
      if ( v22 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_43:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v31);
          goto LABEL_58;
        }
        v23 = 300;
LABEL_42:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, this, v22);
        goto LABEL_43;
      }
      _InterlockedExchange64(
        (volatile __int64 *)this + 49,
        (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 24LL))(v31));
      wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=((char *)this + 384, &v31);
      v22 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 32LL))(*v18);
      v10 = v22;
      if ( v22 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_43;
        v23 = 301;
        goto LABEL_42;
      }
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v31);
    }
    if ( !*((_DWORD *)this + 40) )
      *((_DWORD *)this + 40) = 2;
    (*(void (__fastcall **)(FSStream *))(*(_QWORD *)this + 144LL))(this);
    v9 = (*(__int64 (__fastcall **)(FSStream *))(*(_QWORD *)this + 192LL))(this);
    v10 = v9;
    if ( v9 >= 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::GetImpl'::`2'::impl) )
      {
        v24 = (struct _TP_TIMER *)*((_QWORD *)this + 97);
        if ( v24 )
        {
          v25 = *((_QWORD *)this + 86) + 50000000LL;
          pftDueTime = (struct _FILETIME)-50000000LL;
          *((_QWORD *)this + 98) = v25;
          SetThreadpoolTimer(v24, &pftDueTime, 0, 0);
        }
      }
      else
      {
        v26 = *((_QWORD *)this + 96);
        if ( v26 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v26 + 48LL))(v26, 2, -50000000);
      }
    }
    else if ( g_wppLevels )
    {
      v12 = 302;
      goto LABEL_6;
    }
    goto LABEL_58;
  }
  if ( g_wppLevels )
  {
    v12 = 296;
    goto LABEL_6;
  }
LABEL_58:
  if ( AutoWatchdogTimer::IsStarted((AutoWatchdogTimer *)v40) )
    AutoWatchdogTimer::Stop((AutoWatchdogTimer *)v40);
  if ( v11 )
  {
    v28 = *((_QWORD *)this + 92);
    if ( v28 )
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v28 + 48LL))(v28, &v33);
  }
  if ( v10 >= 0 )
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v29 = 304;
      goto LABEL_68;
    }
  }
  else if ( byte_18010EC4D )
  {
    v29 = 303;
LABEL_68:
    WPP_SF_qDDDd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v29,
      v27,
      this,
      v10,
      *((_DWORD *)this + 22),
      *((_DWORD *)this + 23),
      *((_DWORD *)this + 40));
  }
  v40[0] = &FSStreamWatchdog::`vftable';
  FSSourceWatchdog::~FSSourceWatchdog((FSSourceWatchdog *)v40);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v35);
  PropVariantClear(pvar);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800abb70  push    rbp
0x1800abb72  push    rbx
0x1800abb73  push    rdi
0x1800abb74  push    r12
0x1800abb76  push    r13
0x1800abb78  push    r14
0x1800abb7a  push    r15
0x1800abb7c  lea     rbp, [rsp-6D0h]
0x1800abb84  sub     rsp, 7D0h
0x1800abb8b  mov     rax, cs:__security_cookie
0x1800abb92  xor     rax, rsp
0x1800abb95  mov     [rbp+700h+var_40], rax
0x1800abb9c  xor     eax, eax
0x1800abb9e  mov     qword ptr [rsp+800h+pftDueTime.dwLowDateTime], r9
0x1800abba3  xorps   xmm0, xmm0
0x1800abba6  mov     [rbp+700h+var_780], rax
0x1800abbaa  movups  xmmword ptr [rsp+800h+pvar], xmm0
0x1800abbaf  mov     [rsp+800h+var_798], rax
0x1800abbb4  mov     r12, rdx
0x1800abbb7  mov     r15d, r8d
0x1800abbba  mov     rdi, rcx
0x1800abbbd  call    cs:__imp_GetCurrentThreadId
0x1800abbc3  mov     ebx, 2
0x1800abbc8  mov     dword ptr [rsp+800h+var_7B0+4], 0FFFFFFFFh
0x1800abbd0  mov     dword ptr [rsp+800h+var_7B0], eax
0x1800abbd4  mov     [rsp+800h+var_7A0], rbx
0x1800abbd9  mov     qword ptr [rsp+800h+var_7B0+8], rdi
0x1800abbde  cmp     cs:byte_18010EC4D, 8
0x1800abbe5  lea     r14, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800abbec  jb      short loc_1800ABC24
0x1800abbee  mov     eax, [rdi+0A0h]
0x1800abbf4  mov     edx, 124h
0x1800abbf9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abc00  mov     r9, rdi
0x1800abc03  mov     dword ptr [rsp+800h+var_7D0], eax
0x1800abc07  mov     r8, r14
0x1800abc0a  mov     eax, [rdi+5Ch]
0x1800abc0d  mov     [rsp+800h+var_7D8], eax
0x1800abc11  mov     eax, [rdi+58h]
0x1800abc14  mov     rcx, [rcx+0D8h]
0x1800abc1b  mov     dword ptr [rsp+800h+var_7E0], eax
0x1800abc1f  call    WPP_SF_qddd
0x1800abc24  mov     r8, [rdi+2E0h]; struct IMFVideoDeviceStateStats *
0x1800abc2b  lea     rcx, [rbp+700h+var_750]; this
0x1800abc2f  mov     rdx, [rdi+148h]; struct IFSSource *
0x1800abc36  call    ??0FSSourceWatchdog@@QEAA@PEAUIFSSource@@PEAUIMFVideoDeviceStateStats@@@Z; FSSourceWatchdog::FSSourceWatchdog(IFSSource *,IMFVideoDeviceStateStats *)
0x1800abc3b  mov     rcx, [rdi+2E0h]
0x1800abc42  lea     rax, ??_7FSStreamWatchdog@@6B@; const FSStreamWatchdog::`vftable'
0x1800abc49  movups  xmm0, [rsp+800h+var_7B0]
0x1800abc4e  lea     rdx, [rbp+700h+var_770]
0x1800abc52  mov     [rbp+700h+var_750], rax
0x1800abc56  movsd   xmm1, [rsp+800h+var_7A0]
0x1800abc5c  mov     [rbp+700h+var_50], rdi
0x1800abc63  mov     [rbp+700h+var_718], ebx
0x1800abc66  mov     rax, [rcx]
0x1800abc69  movaps  [rbp+700h+var_770], xmm0
0x1800abc6d  movsd   [rbp+700h+var_760], xmm1
0x1800abc72  mov     rax, [rax+18h]
0x1800abc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abc7b  mov     ebx, eax
0x1800abc7d  test    eax, eax
0x1800abc7f  jns     short loc_1800ABCB5
0x1800abc81  xor     r13b, r13b
0x1800abc84  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800abc8b  jb      loc_1800AC125
0x1800abc91  mov     edx, 125h
0x1800abc96  mov     r8, r14
0x1800abc99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abca0  mov     r9, rdi
0x1800abca3  mov     dword ptr [rsp+800h+var_7E0], eax
0x1800abca7  mov     rcx, [rcx+10h]
0x1800abcab  call    WPP_SF_qD
0x1800abcb0  jmp     loc_1800AC125
0x1800abcb5  mov     al, [rdi+2DCh]
0x1800abcbb  lea     rcx, [rbp+700h+var_750]
0x1800abcbf  neg     al
0x1800abcc1  mov     edx, 2
0x1800abcc6  mov     rax, 0FFFFFFFD40AA4A00h
0x1800abcd0  mov     r13b, 1
0x1800abcd3  sbb     r8, r8
0x1800abcd6  and     r8, rax
0x1800abcd9  add     r8, 0FFFFFFFFF4143E00h
0x1800abce0  call    ?Start@FSStreamWatchdog@@UEAAXW4__MIDL___MIDL_itf_mfdeviceinternal_0000_0049_0002@@_J@Z; FSStreamWatchdog::Start(__MIDL___MIDL_itf_mfdeviceinternal_0000_0049_0002,__int64)
0x1800abce5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent> `wil::Feature<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::GetImpl(void)'::`2'::impl
0x1800abcec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraFirstFrameTelemetryEvent>::__private_IsEnabled(void)
0x1800abcf1  test    al, al
0x1800abcf3  jz      loc_1800ABDAF
0x1800abcf9  mov     rcx, rdi; this
0x1800abcfc  call    ?CancelFirstFrameTimer@FSStream@@IEAAXXZ; FSStream::CancelFirstFrameTimer(void)
0x1800abd01  mov     rcx, [rdi+150h]
0x1800abd08  mov     rax, [rcx]
0x1800abd0b  mov     rax, [rax+18h]
0x1800abd0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abd14  test    eax, eax
0x1800abd16  jz      short loc_1800ABD34
0x1800abd18  mov     rcx, [rdi+150h]
0x1800abd1f  mov     rax, [rcx]
0x1800abd22  mov     rax, [rax+18h]
0x1800abd26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abd2b  cmp     eax, 4
0x1800abd2e  jnz     loc_1800ABE03
0x1800abd34  lock inc dword ptr [rdi+318h]
0x1800abd3b  cmp     qword ptr [rdi+308h], 0
0x1800abd43  jnz     loc_1800ABE03
0x1800abd49  xor     r8d, r8d; pcbe
0x1800abd4c  lea     rcx, ?FirstFrameTimerCallback@FSStream@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800abd53  mov     rdx, rdi; pv
0x1800abd56  call    cs:__imp_CreateThreadpoolTimer
0x1800abd5c  mov     [rdi+308h], rax
0x1800abd63  test    rax, rax
0x1800abd66  jnz     loc_1800ABE03
0x1800abd6c  cmp     cs:byte_18010EC4D, r13b
0x1800abd73  jb      loc_1800ABE03
0x1800abd79  call    cs:__imp_GetLastError
0x1800abd7f  test    eax, eax
0x1800abd81  jle     short loc_1800ABD8B
0x1800abd83  movzx   eax, ax
0x1800abd86  or      eax, 80070000h
0x1800abd8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abd92  mov     edx, 126h
0x1800abd97  mov     r9, rdi
0x1800abd9a  mov     dword ptr [rsp+800h+var_7E0], eax
0x1800abd9e  mov     r8, r14
0x1800abda1  mov     rcx, [rcx+0D8h]
0x1800abda8  call    WPP_SF_qD
0x1800abdad  jmp     short loc_1800ABE03
0x1800abdaf  lea     rbx, [rdi+300h]
0x1800abdb6  xor     edx, edx
0x1800abdb8  mov     rcx, rbx
0x1800abdbb  call    ?reset@?$unique_ptr@VFSSStreamTelemetryWatchdog@@U?$default_delete@VFSSStreamTelemetryWatchdog@@@wistd@@@wistd@@QEAAXPEAVFSSStreamTelemetryWatchdog@@@Z; wistd::unique_ptr<FSSStreamTelemetryWatchdog,wistd::default_delete<FSSStreamTelemetryWatchdog>>::reset(FSSStreamTelemetryWatchdog *)
0x1800abdc0  mov     rcx, [rdi+150h]
0x1800abdc7  mov     rax, [rcx]
0x1800abdca  mov     rax, [rax+18h]
0x1800abdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abdd3  test    eax, eax
0x1800abdd5  jnz     short loc_1800ABE03
0x1800abdd7  mov     ecx, 310h; Size
0x1800abddc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800abde1  test    rax, rax
0x1800abde4  jz      short loc_1800ABDF8
0x1800abde6  mov     rdx, [rdi+148h]
0x1800abded  mov     r9, rdi
0x1800abdf0  mov     rcx, rax
0x1800abdf3  call    ??0FSSStreamTelemetryWatchdog@@QEAA@PEAUIFSSource@@PEAUIMFVideoDeviceStateStats@@PEAVFSStream@@W4FSTelemetryWatchdogType@@@Z; FSSStreamTelemetryWatchdog::FSSStreamTelemetryWatchdog(IFSSource *,IMFVideoDeviceStateStats *,FSStream *,FSTelemetryWatchdogType)
0x1800abdf8  mov     rdx, rax
0x1800abdfb  mov     rcx, rbx
0x1800abdfe  call    ?reset@?$unique_ptr@VFSSStreamTelemetryWatchdog@@U?$default_delete@VFSSStreamTelemetryWatchdog@@@wistd@@@wistd@@QEAAXPEAVFSSStreamTelemetryWatchdog@@@Z; wistd::unique_ptr<FSSStreamTelemetryWatchdog,wistd::default_delete<FSSStreamTelemetryWatchdog>>::reset(FSSStreamTelemetryWatchdog *)
0x1800abe03  mov     rax, [rdi]
0x1800abe06  mov     r8d, r15d
0x1800abe09  mov     rdx, r12
0x1800abe0c  mov     rcx, rdi
0x1800abe0f  mov     rax, [rax+98h]
0x1800abe16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe1b  mov     ebx, eax
0x1800abe1d  test    eax, eax
0x1800abe1f  jns     short loc_1800ABE38
0x1800abe21  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800abe28  jb      loc_1800AC125
0x1800abe2e  mov     edx, 127h
0x1800abe33  jmp     loc_1800ABC96
0x1800abe38  mov     rcx, [rdi+50h]
0x1800abe3c  mov     edx, [rdi+58h]
0x1800abe3f  mov     rax, [rcx]
0x1800abe42  mov     rax, [rax+118h]
0x1800abe49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe4e  mov     ebx, eax
0x1800abe50  test    eax, eax
0x1800abe52  jns     short loc_1800ABE6B
0x1800abe54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800abe5b  jb      loc_1800AC125
0x1800abe61  mov     edx, 128h
0x1800abe66  jmp     loc_1800ABC96
0x1800abe6b  cmp     dword ptr [rdi+0A0h], 0
0x1800abe72  jnz     short loc_1800ABEBB
0x1800abe74  call    cs:__imp_MFGetSystemTime
0x1800abe7a  mov     [rdi+2B0h], rax
0x1800abe81  cmp     cs:byte_18010EC4D, 8
0x1800abe88  jb      short loc_1800ABEBB
0x1800abe8a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abe91  mov     edx, 129h
0x1800abe96  mov     [rsp+800h+var_7D0], rax
0x1800abe9b  mov     r9, rdi
0x1800abe9e  mov     eax, [rdi+5Ch]
0x1800abea1  mov     r8, r14
0x1800abea4  mov     [rsp+800h+var_7D8], eax
0x1800abea8  mov     eax, [rdi+58h]
0x1800abeab  mov     rcx, [rcx+0D8h]
0x1800abeb2  mov     dword ptr [rsp+800h+var_7E0], eax
0x1800abeb6  call    WPP_SF_qDDq
0x1800abebb  mov     rcx, [rdi+48h]
0x1800abebf  lea     r9, [rsp+800h+pvar]
0x1800abec4  mov     rdx, [rdi+50h]
0x1800abec8  xor     r8d, r8d
0x1800abecb  mov     rax, [rcx]
0x1800abece  mov     rax, [rax+48h]
0x1800abed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abed7  mov     ebx, eax
0x1800abed9  test    eax, eax
0x1800abedb  jns     short loc_1800ABEF4
0x1800abedd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800abee4  jb      loc_1800AC125
0x1800abeea  mov     edx, 12Ah
0x1800abeef  jmp     loc_1800ABC96
0x1800abef4  lea     r14, [rdi+180h]
0x1800abefb  mov     rdx, [r14]
0x1800abefe  test    rdx, rdx
0x1800abf01  jz      short loc_1800ABF50
0x1800abf03  mov     rax, [rdi]
0x1800abf06  mov     rcx, rdi
0x1800abf09  mov     rax, [rax+0E8h]
0x1800abf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf15  mov     ebx, eax
0x1800abf17  test    eax, eax
0x1800abf19  jns     short loc_1800ABF39
0x1800abf1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800abf22  jb      loc_1800AC125
0x1800abf28  mov     edx, 12Bh
0x1800abf2d  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800abf34  jmp     loc_1800ABC99
0x1800abf39  mov     rcx, [r14]
0x1800abf3c  mov     rax, [rcx]
0x1800abf3f  mov     rax, [rax+38h]
0x1800abf43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf48  mov     rcx, r14
0x1800abf4b  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800abf50  mov     rax, [rdi+70h]
0x1800abf54  mov     edx, 3Eh ; '>'
0x1800abf59  mov     rcx, [rax+r15*8]
0x1800abf5d  mov     rax, [rcx]
0x1800abf60  mov     rax, [rax+160h]
0x1800abf67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf6c  test    eax, eax
0x1800abf6e  jnz     short loc_1800ABF8E
0x1800abf70  mov     rcx, [rdi+148h]
0x1800abf77  mov     rax, [rcx]
0x1800abf7a  mov     rax, [rax+1F8h]
0x1800abf81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf86  test    al, 2
0x1800abf88  jz      loc_1800AC065
0x1800abf8e  mov     rax, [rdi]
0x1800abf91  lea     rcx, [rsp+800h+var_7C0]
0x1800abf96  mov     [rsp+800h+var_7C0], 0
0x1800abf9f  mov     rbx, [rax+0A0h]
0x1800abfa6  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800abfab  mov     r8, [rdi+70h]
0x1800abfaf  lea     rax, [rsp+800h+var_7C0]
0x1800abfb4  mov     r9, qword ptr [rsp+800h+pftDueTime.dwLowDateTime]
0x1800abfb9  mov     rdx, r12
0x1800abfbc  mov     [rsp+800h+var_7E0], rax
0x1800abfc1  mov     rcx, rdi
0x1800abfc4  mov     rax, rbx
0x1800abfc7  mov     r8, [r8+r15*8]
0x1800abfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abfd0  mov     ebx, eax
0x1800abfd2  test    eax, eax
0x1800abfd4  jns     short loc_1800AC011
0x1800abfd6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800abfdd  jb      short loc_1800AC002
0x1800abfdf  mov     edx, 12Ch
0x1800abfe4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800abfeb  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800abff2  mov     r9, rdi
0x1800abff5  mov     dword ptr [rsp+800h+var_7E0], eax
0x1800abff9  mov     rcx, [rcx+10h]
0x1800abffd  call    WPP_SF_qD
0x1800ac002  lea     rcx, [rsp+800h+var_7C0]; void *
0x1800ac007  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800ac00c  jmp     loc_1800AC125
0x1800ac011  mov     rcx, [rsp+800h+var_7C0]
0x1800ac016  mov     rax, [rcx]
0x1800ac019  mov     rax, [rax+18h]
0x1800ac01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac022  xchg    rax, [rdi+188h]
0x1800ac029  lea     rdx, [rsp+800h+var_7C0]
0x1800ac02e  mov     rcx, r14
0x1800ac031  call    ??4?$com_ptr_t@UIFSControl@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IFSControl,wil::err_returncode_policy> const &)
0x1800ac036  mov     rcx, [r14]
0x1800ac039  mov     rax, [rcx]
0x1800ac03c  mov     rax, [rax+20h]
0x1800ac040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac045  mov     ebx, eax
0x1800ac047  test    eax, eax
0x1800ac049  jns     short loc_1800AC05B
0x1800ac04b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800ac052  jb      short loc_1800AC002
0x1800ac054  mov     edx, 12Dh
0x1800ac059  jmp     short loc_1800ABFE4
0x1800ac05b  lea     rcx, [rsp+800h+var_7C0]; void *
0x1800ac060  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800ac065  cmp     dword ptr [rdi+0A0h], 0
0x1800ac06c  jnz     short loc_1800AC078
0x1800ac06e  mov     dword ptr [rdi+0A0h], 2
0x1800ac078  mov     rax, [rdi]
0x1800ac07b  mov     rcx, rdi
0x1800ac07e  mov     rax, [rax+90h]
0x1800ac085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac08a  mov     rax, [rdi]
0x1800ac08d  mov     rcx, rdi
0x1800ac090  mov     rax, [rax+0C0h]
0x1800ac097  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
