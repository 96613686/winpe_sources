# CUploadQueueManager::_ScheduleRetryTimer(void)

- ea: `0x1801c2d04`
- end: `0x1801c3170`
- name: `?_ScheduleRetryTimer@CUploadQueueManager@@AEAAJXZ`
- size: `1132`
- prototype: `__int64 __fastcall(CUploadQueueManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801c2ba8`

## callees

- `0x180025710`
- `0x18002fc18`
- `0x18006a010`
- `0x180076bec`
- `0x180093bd8`
- `0x180142e10`
- `0x180142e34`
- `0x180143a7c`
- `0x1801c1c38`
- `0x1801c2d04`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801c2d43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801c2d43`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1801c2fd0`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1801c2fd0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801c2d7d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801c2d7d`
- `TimeBrokerClient!TbCreateEvent` at `0x1801c2e9c`
- `TimeBrokerClient!TbCreateEvent` at `0x1801c2e9c`
- `TimeBrokerClient!TbDeleteEvent` at `0x1801c313a`
- `TimeBrokerClient!TbDeleteEvent` at `0x1801c313a`
- `SystemEventsBrokerClient!SebCreateDisplayOnEvent` at `0x1801c2f07`
- `SystemEventsBrokerClient!SebCreateDisplayOnEvent` at `0x1801c2f07`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1801c30f2`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1801c3116`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1801c30f2`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1801c3116`
- `SystemEventsBrokerClient!SebRegisterWellKnownEvent` at `0x1801c2ecd`
- `SystemEventsBrokerClient!SebRegisterWellKnownEvent` at `0x1801c2ecd`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItem` at `0x1801c30d2`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItem` at `0x1801c30d2`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x1801c2f76`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x1801c2f76`

## pseudocode

```c
__int64 __fastcall CUploadQueueManager::_ScheduleRetryTimer(CUploadQueueManager *this)
{
  __int64 v2; // rax
  int Error; // ebx
  int v4; // eax
  int v5; // eax
  __int64 v6; // rdx
  char v7; // si
  char *v8; // rax
  char *v9; // rbx
  __int128 v10; // xmm0
  __int128 v11; // xmm2
  __int128 v12; // xmm1
  __int64 v13; // r8
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int128 *v18; // [rsp+60h] [rbp-A0h] BYREF
  char v19; // [rsp+68h] [rbp-98h]
  __int128 *v20; // [rsp+70h] [rbp-90h]
  char v21; // [rsp+78h] [rbp-88h]
  __m256i v22; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int128 v24; // [rsp+B0h] [rbp-50h]
  __int128 v25; // [rsp+C0h] [rbp-40h]
  __int128 v26; // [rsp+D0h] [rbp-30h]
  __int128 v27; // [rsp+E0h] [rbp-20h]
  __int128 v28; // [rsp+F0h] [rbp-10h]
  __int128 v29; // [rsp+100h] [rbp+0h]
  __int128 v30; // [rsp+110h] [rbp+10h]
  __int128 v31; // [rsp+120h] [rbp+20h]
  __int128 v32; // [rsp+130h] [rbp+30h]
  __int128 v33; // [rsp+140h] [rbp+40h]
  __int128 v34; // [rsp+150h] [rbp+50h]
  __int128 v35; // [rsp+160h] [rbp+60h]
  __int64 v36; // [rsp+170h] [rbp+70h]
  __m256i v37; // [rsp+180h] [rbp+80h] BYREF
  __int128 v38; // [rsp+1A0h] [rbp+A0h]
  __int128 v39; // [rsp+1B0h] [rbp+B0h]
  __int128 v40; // [rsp+1C0h] [rbp+C0h]
  __int128 v41; // [rsp+1D0h] [rbp+D0h]
  __int128 v42; // [rsp+1E0h] [rbp+E0h]
  __int128 v43; // [rsp+1F0h] [rbp+F0h]
  __int128 v44; // [rsp+200h] [rbp+100h]
  __int128 v45; // [rsp+210h] [rbp+110h]
  __int128 v46; // [rsp+220h] [rbp+120h]
  __int128 v47; // [rsp+230h] [rbp+130h]
  __int128 v48; // [rsp+240h] [rbp+140h]
  __int128 v49; // [rsp+250h] [rbp+150h]
  __int128 v50; // [rsp+260h] [rbp+160h]
  __int64 v51; // [rsp+270h] [rbp+170h]
  __int128 v52; // [rsp+280h] [rbp+180h] BYREF
  __int64 v53; // [rsp+290h] [rbp+190h] BYREF
  __int128 v54; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v55; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v56; // [rsp+2C0h] [rbp+1C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v58[16]; // [rsp+2E0h] [rbp+1E0h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = *((_QWORD *)this + 28) + *(_QWORD *)&SystemTimeAsFileTime;
  SystemTimeAsFileTime.dwLowDateTime += *((_DWORD *)this + 56);
  SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v2);
  SystemTime = 0;
  if ( FileTimeToSystemTime(&SystemTimeAsFileTime, &SystemTime) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    memset_0(&v22, 0, 0xF8u);
    v22.m256i_i64[3] = 0x100000000LL;
    *(struct _SYSTEMTIME *)&v22.m256i_u64[1] = SystemTime;
    v56 = 0;
    LODWORD(v23) = 1440;
    v37 = v22;
    BYTE5(v24) = 0;
    v51 = v36;
    v38 = v23;
    v39 = v24;
    v40 = v25;
    v41 = v26;
    v42 = v27;
    v43 = v28;
    v44 = v29;
    v45 = v30;
    v46 = v31;
    v47 = v32;
    v48 = v33;
    v49 = v34;
    v50 = v35;
    Error = TbCreateEvent(0, &v37, &v56);
    if ( Error >= 0 )
    {
      v55 = 0;
      Error = SebRegisterWellKnownEvent(4, &v55, 0);
      if ( Error < 0 )
      {
LABEL_20:
        v52 = v56;
        TbDeleteEvent(0, &v52);
        return (unsigned int)Error;
      }
      v19 = 1;
      v18 = &v55;
      v54 = 0;
      Error = SebCreateDisplayOnEvent(&v54, 0);
      if ( Error < 0 )
      {
LABEL_19:
        v52 = v55;
        SebDeleteEvent(&v52, 0);
        goto LABEL_20;
      }
      v20 = &v54;
      v21 = 1;
      v53 = 0;
      v52 = 0;
      v4 = BiPtAssociateActivationProxy(&v52, &v53, &v56, &v18, 2, 0, 0);
      Error = ResultFromWin32FromStatus(v4);
      if ( Error < 0 )
      {
LABEL_18:
        v17 = v54;
        SebDeleteEvent(&v17, 0);
        goto LABEL_19;
      }
      v16 = 0;
      v5 = RtlSubscribeWnfStateChangeNotification(&v16, v53, 0, CUploadQueueManager::_TimerWnfCallback, this, 0, 0, 1);
      Error = ResultFromWin32FromStatus(v5);
      if ( Error < 0 )
        goto LABEL_17;
      v7 = 1;
      wil::AcquireSRWLockExclusive(&v17, (char *)this + 192);
      if ( !*((_BYTE *)this + 200) )
      {
        v8 = (char *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
        v9 = v8;
        if ( v8 )
        {
          v10 = v56;
          v11 = v55;
          v12 = v54;
          *(_QWORD *)v8 = v16;
          *(_OWORD *)(v8 + 8) = v10;
          *(_OWORD *)(v8 + 24) = v12;
          *(_OWORD *)(v8 + 40) = v11;
          *(_OWORD *)(v8 + 56) = v52;
        }
        else
        {
          v9 = 0;
        }
        CTSmartObj<CRetryTimerRegistration *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release((char *)this + 208);
        *((_QWORD *)this + 26) = v9;
        if ( v9 )
        {
          *((_BYTE *)this + 200) = 1;
          Error = 0;
          v7 = 0;
          if ( (Microsoft_Windows_Immersive_ShellEnableBits & 0x100000) != 0 )
            McGenEventWrite_EventWriteTransfer(
              &MICROSOFT_TWINUI_PUBLISHER_Context,
              ConnectedSearch_RetryTimerScheduled,
              v13,
              1,
              v58);
        }
        else
        {
          Error = -2147024882;
        }
      }
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v17);
      if ( v7 )
      {
LABEL_17:
        LOBYTE(v6) = 1;
        BiPtDisassociateWorkItem(&v52, v6);
        goto LABEL_18;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1801c2d04  mov     [rsp-8+arg_8], rbx
0x1801c2d09  mov     [rsp-8+arg_10], rsi
0x1801c2d0e  push    rbp
0x1801c2d0f  push    rdi
0x1801c2d10  push    r14
0x1801c2d12  lea     rbp, [rsp-200h]
0x1801c2d1a  sub     rsp, 300h
0x1801c2d21  mov     rax, cs:__security_cookie
0x1801c2d28  xor     rax, rsp
0x1801c2d2b  mov     [rbp+210h+var_20], rax
0x1801c2d32  mov     rdi, rcx
0x1801c2d35  mov     qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1801c2d3e  lea     rcx, [rsp+310h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801c2d43  call    cs:__imp_GetSystemTimeAsFileTime
0x1801c2d4a  nop     dword ptr [rax+rax+00h]
0x1801c2d4f  mov     rax, qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime]
0x1801c2d54  lea     rdx, [rbp+210h+SystemTime]; lpSystemTime
0x1801c2d5b  add     rax, [rdi+0E0h]
0x1801c2d62  lea     rcx, [rsp+310h+SystemTimeAsFileTime]; lpFileTime
0x1801c2d67  mov     [rsp+310h+SystemTimeAsFileTime.dwLowDateTime], eax
0x1801c2d6b  xorps   xmm0, xmm0
0x1801c2d6e  shr     rax, 20h
0x1801c2d72  mov     [rsp+310h+SystemTimeAsFileTime.dwHighDateTime], eax
0x1801c2d76  movups  xmmword ptr [rbp+210h+SystemTime.wYear], xmm0
0x1801c2d7d  call    cs:__imp_FileTimeToSystemTime
0x1801c2d84  nop     dword ptr [rax+rax+00h]
0x1801c2d89  test    eax, eax
0x1801c2d8b  jnz     short loc_1801C2D9C
0x1801c2d8d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801c2d92  mov     ebx, eax
0x1801c2d94  test    eax, eax
0x1801c2d96  js      loc_1801C3146
0x1801c2d9c  xor     edx, edx; Val
0x1801c2d9e  lea     rcx, [rbp+210h+var_290]; void *
0x1801c2da2  mov     r8d, 0F8h; Size
0x1801c2da8  call    memset_0
0x1801c2dad  movups  xmm0, xmmword ptr [rbp+210h+SystemTime.wYear]
0x1801c2db4  mov     rax, [rbp+210h+var_1A0]
0x1801c2db8  lea     r8, [rbp+210h+var_50]
0x1801c2dbf  mov     [rbp+210h+var_278], 0
0x1801c2dc6  lea     rdx, [rbp+210h+var_190]
0x1801c2dcd  movdqu  [rbp+210h+var_290+8], xmm0
0x1801c2dd2  mov     [rbp+210h+var_274], 1
0x1801c2dd9  xor     ecx, ecx
0x1801c2ddb  movaps  xmm1, [rbp+210h+var_290]
0x1801c2ddf  xorps   xmm0, xmm0
0x1801c2de2  movups  [rbp+210h+var_50], xmm0
0x1801c2de9  mov     dword ptr [rbp+210h+var_270], 5A0h
0x1801c2df0  movaps  xmm0, xmmword ptr [rbp-70h]
0x1801c2df4  movups  [rbp+210h+var_190], xmm1
0x1801c2dfb  mov     [rbp+210h+var_25B], 0
0x1801c2dff  movaps  xmm1, [rbp+210h+var_270]
0x1801c2e03  movups  [rbp+210h+var_180], xmm0
0x1801c2e0a  mov     [rbp+210h+var_A0], rax
0x1801c2e11  movaps  xmm0, xmmword ptr [rbp-50h]
0x1801c2e15  movups  [rbp+210h+var_170], xmm1
0x1801c2e1c  movaps  xmm1, [rbp+210h+var_250]
0x1801c2e20  movups  [rbp+210h+var_160], xmm0
0x1801c2e27  movaps  xmm0, [rbp+210h+var_240]
0x1801c2e2b  movups  [rbp+210h+var_150], xmm1
0x1801c2e32  movaps  xmm1, [rbp+210h+var_230]
0x1801c2e36  movups  [rbp+210h+var_140], xmm0
0x1801c2e3d  movaps  xmm0, [rbp+210h+var_220]
0x1801c2e41  movups  [rbp+210h+var_130], xmm1
0x1801c2e48  movaps  xmm1, [rbp+210h+var_210]
0x1801c2e4c  movups  [rbp+210h+var_120], xmm0
0x1801c2e53  movaps  xmm0, [rbp+210h+var_200]
0x1801c2e57  movups  [rbp+210h+var_110], xmm1
0x1801c2e5e  movaps  xmm1, [rbp+210h+var_1F0]
0x1801c2e62  movups  [rbp+210h+var_100], xmm0
0x1801c2e69  movaps  xmm0, [rbp+210h+var_1E0]
0x1801c2e6d  movups  [rbp+210h+var_F0], xmm1
0x1801c2e74  movaps  xmm1, [rbp+210h+var_1D0]
0x1801c2e78  movups  [rbp+210h+var_E0], xmm0
0x1801c2e7f  movaps  xmm0, [rbp+210h+var_1C0]
0x1801c2e83  movups  [rbp+210h+var_D0], xmm1
0x1801c2e8a  movaps  xmm1, [rbp+210h+var_1B0]
0x1801c2e8e  movups  [rbp+210h+var_C0], xmm0
0x1801c2e95  movups  [rbp+210h+var_B0], xmm1
0x1801c2e9c  call    cs:__imp_TbCreateEvent
0x1801c2ea3  nop     dword ptr [rax+rax+00h]
0x1801c2ea8  mov     ebx, eax
0x1801c2eaa  test    eax, eax
0x1801c2eac  js      loc_1801C3146
0x1801c2eb2  xor     r9d, r9d
0x1801c2eb5  lea     rdx, [rbp+210h+var_60]
0x1801c2ebc  xorps   xmm0, xmm0
0x1801c2ebf  xor     r8d, r8d
0x1801c2ec2  movups  [rbp+210h+var_60], xmm0
0x1801c2ec9  lea     ecx, [r9+4]
0x1801c2ecd  call    cs:__imp_SebRegisterWellKnownEvent
0x1801c2ed4  nop     dword ptr [rax+rax+00h]
0x1801c2ed9  mov     ebx, eax
0x1801c2edb  test    eax, eax
0x1801c2edd  js      loc_1801C3122
0x1801c2ee3  lea     rax, [rbp+210h+var_60]
0x1801c2eea  mov     [rsp+310h+var_2A8], 1
0x1801c2eef  xorps   xmm0, xmm0
0x1801c2ef2  mov     [rsp+310h+var_2B0], rax
0x1801c2ef7  xor     edx, edx
0x1801c2ef9  lea     rcx, [rbp+210h+var_70]
0x1801c2f00  movups  [rbp+210h+var_70], xmm0
0x1801c2f07  call    cs:__imp_SebCreateDisplayOnEvent
0x1801c2f0e  nop     dword ptr [rax+rax+00h]
0x1801c2f13  mov     ebx, eax
0x1801c2f15  test    eax, eax
0x1801c2f17  js      loc_1801C30FE
0x1801c2f1d  lea     rax, [rbp+210h+var_70]
0x1801c2f24  mov     [rsp+310h+var_2E0], 0
0x1801c2f2d  xorps   xmm0, xmm0
0x1801c2f30  mov     dword ptr [rsp+310h+var_2E8], 0
0x1801c2f38  lea     r9, [rsp+310h+var_2B0]
0x1801c2f3d  mov     [rsp+310h+var_2A0], rax
0x1801c2f42  lea     r8, [rbp+210h+var_50]
0x1801c2f49  mov     dword ptr [rsp+310h+var_2F0], 2
0x1801c2f51  lea     rdx, [rbp+210h+var_80]
0x1801c2f58  mov     [rsp+310h+var_298], 1
0x1801c2f5d  lea     rcx, [rbp+210h+var_90]
0x1801c2f64  mov     [rbp+210h+var_80], 0
0x1801c2f6f  movups  [rbp+210h+var_90], xmm0
0x1801c2f76  call    cs:__imp_BiPtAssociateActivationProxy
0x1801c2f7d  nop     dword ptr [rax+rax+00h]
0x1801c2f82  mov     ecx, eax; int
0x1801c2f84  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1801c2f89  mov     ebx, eax
0x1801c2f8b  test    eax, eax
0x1801c2f8d  js      loc_1801C30DE
0x1801c2f93  mov     rdx, [rbp+210h+var_80]
0x1801c2f9a  lea     r9, ?_TimerWnfCallback@CUploadQueueManager@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CUploadQueueManager::_TimerWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1801c2fa1  mov     [rsp+310h+var_2D8], 1
0x1801c2fa9  lea     rcx, [rsp+310h+var_2C8]
0x1801c2fae  mov     dword ptr [rsp+310h+var_2E0], 0
0x1801c2fb6  xor     r8d, r8d
0x1801c2fb9  mov     [rsp+310h+var_2E8], 0
0x1801c2fc2  mov     [rsp+310h+var_2F0], rdi
0x1801c2fc7  mov     [rsp+310h+var_2C8], 0
0x1801c2fd0  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1801c2fd7  nop     dword ptr [rax+rax+00h]
0x1801c2fdc  mov     ecx, eax; int
0x1801c2fde  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1801c2fe3  mov     ebx, eax
0x1801c2fe5  test    eax, eax
0x1801c2fe7  js      loc_1801C30C9
0x1801c2fed  lea     rdx, [rdi+0C0h]
0x1801c2ff4  mov     sil, 1
0x1801c2ff7  lea     rcx, [rsp+310h+var_2C0]
0x1801c2ffc  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801c3001  mov     al, [rdi+0C8h]
0x1801c3007  test    al, al
0x1801c3009  jnz     loc_1801C30BA
0x1801c300f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801c3016  mov     ecx, 50h ; 'P'; unsigned __int64
0x1801c301b  lea     r14, [rdi+0D0h]
0x1801c3022  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801c3027  mov     rbx, rax
0x1801c302a  test    rax, rax
0x1801c302d  jz      short loc_1801C3069
0x1801c302f  movaps  xmm0, [rbp+210h+var_50]
0x1801c3036  movaps  xmm2, [rbp+210h+var_60]
0x1801c303d  movaps  xmm1, [rbp+210h+var_70]
0x1801c3044  mov     rcx, [rsp+310h+var_2C8]
0x1801c3049  mov     [rax], rcx
0x1801c304c  movdqu  xmmword ptr [rax+8], xmm0
0x1801c3051  movdqu  xmmword ptr [rax+18h], xmm1
0x1801c3056  movdqu  xmmword ptr [rax+28h], xmm2
0x1801c305b  movups  xmm0, [rbp+210h+var_90]
0x1801c3062  movdqu  xmmword ptr [rax+38h], xmm0
0x1801c3067  jmp     short loc_1801C306B
0x1801c3069  xor     ebx, ebx
0x1801c306b  mov     rcx, r14
0x1801c306e  call    ?Release@?$CTSmartObj@PEAVCRetryTimerRegistration@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<CRetryTimerRegistration *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
0x1801c3073  mov     [r14], rbx
0x1801c3076  test    rbx, rbx
0x1801c3079  jz      short loc_1801C30B5
0x1801c307b  mov     [rdi+0C8h], sil
0x1801c3082  xor     ebx, ebx
0x1801c3084  xor     sil, sil
0x1801c3087  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits+2, 10h
0x1801c308e  jz      short loc_1801C30BA
0x1801c3090  lea     rax, [rbp+210h+var_30]
0x1801c3097  lea     r9d, [rbx+1]
0x1801c309b  mov     [rsp+310h+var_2F0], rax
0x1801c30a0  lea     rdx, ConnectedSearch_RetryTimerScheduled
0x1801c30a7  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x1801c30ae  call    McGenEventWrite_EventWriteTransfer
0x1801c30b3  jmp     short loc_1801C30BA
0x1801c30b5  mov     ebx, 8007000Eh
0x1801c30ba  lea     rcx, [rsp+310h+var_2C0]; this
0x1801c30bf  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801c30c4  test    sil, sil
0x1801c30c7  jz      short loc_1801C3146
0x1801c30c9  mov     dl, 1
0x1801c30cb  lea     rcx, [rbp+210h+var_90]
0x1801c30d2  call    cs:__imp_BiPtDisassociateWorkItem
0x1801c30d9  nop     dword ptr [rax+rax+00h]
0x1801c30de  movaps  xmm0, [rbp+210h+var_70]
0x1801c30e5  lea     rcx, [rsp+310h+var_2C0]
0x1801c30ea  xor     edx, edx
0x1801c30ec  movdqa  [rsp+310h+var_2C0], xmm0
0x1801c30f2  call    cs:__imp_SebDeleteEvent
0x1801c30f9  nop     dword ptr [rax+rax+00h]
0x1801c30fe  movaps  xmm0, [rbp+210h+var_60]
0x1801c3105  lea     rcx, [rbp+210h+var_90]
0x1801c310c  xor     edx, edx
0x1801c310e  movdqa  [rbp+210h+var_90], xmm0
0x1801c3116  call    cs:__imp_SebDeleteEvent
0x1801c311d  nop     dword ptr [rax+rax+00h]
0x1801c3122  movaps  xmm0, [rbp+210h+var_50]
0x1801c3129  lea     rdx, [rbp+210h+var_90]
0x1801c3130  xor     ecx, ecx
0x1801c3132  movdqa  [rbp+210h+var_90], xmm0
0x1801c313a  call    cs:__imp_TbDeleteEvent
0x1801c3141  nop     dword ptr [rax+rax+00h]
0x1801c3146  mov     eax, ebx
0x1801c3148  mov     rcx, [rbp+210h+var_20]
0x1801c314f  xor     rcx, rsp; StackCookie
0x1801c3152  call    __security_check_cookie
0x1801c3157  lea     r11, [rsp+310h+var_10]
0x1801c315f  mov     rbx, [r11+28h]
0x1801c3163  mov     rsi, [r11+30h]
0x1801c3167  mov     rsp, r11
0x1801c316a  pop     r14
0x1801c316c  pop     rdi
0x1801c316d  pop     rbp
0x1801c316e  retn
```
