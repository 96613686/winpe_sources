# CAudioCaptureClient::GetBuffer(uchar * *,uint *,ulong *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800186b0`
- end: `0x180018bca`
- name: `?GetBuffer@CAudioCaptureClient@@UEAAJPEAPEAEPEAIPEAKPEA_K3@Z`
- size: `1306`
- prototype: `int(CAudioCaptureClient *__hidden this, unsigned __int8 **, unsigned int *, unsigned int *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800186b0`
- `0x180018bd0`
- `0x1800190d0`
- `0x180019348`
- `0x1800193e0`
- `0x180087e80`
- `0x18008ac99`
- `0x18008f6dc`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018969`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018b93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018969`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018b93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018bb0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180018bb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018773`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018842`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018773`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018842`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800188dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001894c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800188dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001894c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018b6f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018b6f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018749`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018830`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800188eb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001895b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018749`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018830`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800188eb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001895b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018ad8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018af1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018af1`

## pseudocode

```c
__int64 __fastcall CAudioCaptureClient::GetBuffer(
        CAudioCaptureClient *this,
        unsigned __int8 **a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6)
{
  RTL_SRWLOCK *v6; // rbx
  __int64 v9; // rax
  char *v10; // r15
  GUID *v11; // rcx
  int v12; // edi
  unsigned int *v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // edx
  const char *v16; // rcx
  int v17; // edi
  __int64 v18; // rax
  unsigned int v19; // edx
  const char *v20; // rcx
  __int64 v22; // rcx
  int v23; // edx
  unsigned int *v24; // rdi
  void *v25; // rcx
  SIZE_T v26; // rax
  unsigned __int64 *v27; // rcx
  int v28; // edx
  unsigned int v29; // ecx
  __int64 v30; // r9
  unsigned int v31; // eax
  __int128 v32; // xmm0
  const struct tWAVEFORMATEX *v33; // rdx
  __int128 v34; // xmm1
  CAudioClientTraceLogger *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r9
  LPVOID v38; // rax
  void *v39; // rcx
  RTL_SRWLOCK *v40; // rbx
  unsigned int v41; // [rsp+50h] [rbp-B0h] BYREF
  RTL_SRWLOCK *v42; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v43; // [rsp+60h] [rbp-A0h]
  unsigned int *v44; // [rsp+68h] [rbp-98h]
  PSRWLOCK SRWLock; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 *v46; // [rsp+78h] [rbp-88h]
  unsigned __int64 *v47; // [rsp+80h] [rbp-80h]
  void *Src[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v49; // [rsp+98h] [rbp-68h]
  __int128 v50; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+C0h] [rbp-40h]
  AE_CURRENT_POSITION v53; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v54; // [rsp+100h] [rbp+0h]
  GUID ActivityId; // [rsp+110h] [rbp+10h] BYREF

  v47 = a5;
  v6 = 0;
  v46 = a6;
  v9 = *((_QWORD *)this + 14);
  v43 = a4;
  v44 = a3;
  v42 = 0;
  if ( *(_DWORD *)(v9 + 836) == 2 )
  {
    v40 = (RTL_SRWLOCK *)(v9 + 864);
    AcquireSRWLockShared((PSRWLOCK)(v9 + 864));
    SRWLock = v40;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
      &v42,
      &SRWLock);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    v10 = (char *)this + 112;
    WaitForSingleObjectEx(*(HANDLE *)(*((_QWORD *)this + 14) + 872LL), 0xFFFFFFFF, 0);
    v6 = v42;
  }
  else
  {
    v10 = (char *)this + 112;
  }
  v11 = *(GUID **)v10;
  v54 = *(_OWORD *)(*(_QWORD *)v10 + 528LL);
  ActivityId = v11[33];
  EventActivityIdControl(4u, &ActivityId);
  v41 = 0;
  v52 = 0;
  v50 = 0;
  v49 = 0;
  v51 = 0;
  *(_OWORD *)Src = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( a2 )
    *a2 = 0;
  LODWORD(v49) = 1094930515;
  HIDWORD(Src[1]) = 0;
  Src[0] = 0;
  if ( g_ProcessIsTerminating )
  {
    v12 = -2004287484;
    goto LABEL_25;
  }
  v12 = *(_DWORD *)(*(_QWORD *)v10 + 328LL);
  if ( v12 < 0 )
  {
LABEL_25:
    CAudioClientTraceLogger::LogCaptureGetBufferFailure((CAudioClientTraceLogger *)(*(_QWORD *)v10 + 512LL), v12);
    goto LABEL_19;
  }
  if ( !a2 || (v13 = v44) == 0 || !v43 )
  {
    v12 = -2147467261;
    goto LABEL_25;
  }
  if ( *((_QWORD *)this + 15) )
  {
    v12 = -2004287481;
    goto LABEL_25;
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v10 + 332LL)) == 2 )
  {
    v12 = -2004287477;
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v10 + 332LL));
    goto LABEL_25;
  }
  *v13 = 0;
  *((_DWORD *)this + 34) = 0;
  v14 = *((_QWORD *)this + 14);
  *(_OWORD *)&v53.u64DevicePosition = *(_OWORD *)(v14 + 528);
  v53.u64PaddingFrames = *(_QWORD *)(v14 + 528);
  v53.hnsQPCPosition = *(_QWORD *)(v14 + 536);
  EventActivityIdControl(4u, (LPGUID)&v53.u64PaddingFrames);
  v42 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( g_ProcessIsTerminating )
  {
    v17 = -2004287484;
  }
  else
  {
    v17 = *(_DWORD *)(*((_QWORD *)this + 14) + 328LL);
    if ( v17 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, RTL_SRWLOCK **, _QWORD))(**((_QWORD **)this + 13) + 24LL))(
        *((_QWORD *)this + 13),
        &v42,
        0);
      v18 = *((_QWORD *)this + 16);
      v15 = *(_DWORD *)(v18 + 8) % (unsigned int)*(unsigned __int16 *)(v18 + 12);
      v16 = (const char *)(*(_DWORD *)(v18 + 8) / (unsigned int)*(unsigned __int16 *)(v18 + 12));
      v41 = (int)((double)(int)v16 * (double)(int)v42 / 10000000.0 + 0.5);
    }
  }
  TraceWASAPI_IAudioCaptureClient_GetNextPacketSize(v16, v15, (char *)this - 16, v17, &v41);
  if ( this != (CAudioCaptureClient *)-56LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  EventActivityIdControl(4u, (LPGUID)&v53.u64PaddingFrames);
  if ( !v41 )
  {
    v12 = 143196161;
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v10 + 332LL));
    goto LABEL_19;
  }
  v22 = *((_QWORD *)this + 12);
  LODWORD(Src[1]) = v41;
  (*(void (__fastcall **)(__int64, void **, __int128 *))(*(_QWORD *)v22 + 24LL))(v22, Src, &v50);
  v23 = (int)Src[1];
  v24 = v44;
  *v44 = (unsigned int)Src[1];
  v25 = (void *)*((_QWORD *)this + 19);
  v26 = v23 * (unsigned int)*(unsigned __int16 *)(*((_QWORD *)this + 16) + 12LL);
  v42 = (RTL_SRWLOCK *)v26;
  if ( !v25 || *((_QWORD *)this + 20) < v26 )
  {
    v38 = CoTaskMemAlloc(v26);
    v39 = (void *)*((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = v38;
    if ( v39 )
      CoTaskMemFree(v39);
    v25 = (void *)*((_QWORD *)this + 19);
    if ( v25 )
    {
      v26 = (SIZE_T)v42;
      *((_QWORD *)this + 20) = v42;
      goto LABEL_28;
    }
    v12 = -2147024882;
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v10 + 332LL));
    goto LABEL_25;
  }
LABEL_28:
  memcpy_0(v25, Src[0], v26);
  v27 = v47;
  *a2 = (unsigned __int8 *)*((_QWORD *)this + 19);
  if ( v27 )
    *v27 = *((_QWORD *)&v50 + 1);
  if ( v46 )
    *v46 = *((_QWORD *)&v51 + 1);
  v28 = BYTE4(v52) & 1;
  if ( (v52 & 0x400000000LL) != 0 )
    v28 = BYTE4(v52) & 1 | 4;
  v29 = v28 | 2;
  if ( (BYTE4(Src[1]) & 2) == 0 )
    v29 = v28;
  *v43 = v29;
  v30 = *(_QWORD *)v10;
  if ( *(_DWORD *)(*(_QWORD *)v10 + 480LL) == 1 && !Src[0] )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v30 + 332));
    v12 = -2004287464;
    goto LABEL_25;
  }
  v31 = *v24;
  v32 = v50;
  v33 = (const struct tWAVEFORMATEX *)*((_QWORD *)this + 16);
  v12 = 0;
  v34 = v51;
  *((void **)this + 15) = Src[0];
  v35 = (CAudioClientTraceLogger *)(v30 + 512);
  *((_DWORD *)this + 34) = v31;
  v36 = *(_QWORD *)(v30 + 816);
  v37 = *(_QWORD *)(v30 + 824);
  *(_OWORD *)&v53.u64DevicePosition = v32;
  *(_QWORD *)&v53.f32FramesPerSecond = v52;
  *(_OWORD *)&v53.u64PaddingFrames = v34;
  CAudioClientTraceLogger::LogCaptureLatency(v35, v33, &v53, v37, v36);
LABEL_19:
  TraceWASAPI_IAudioCaptureClient_GetBuffer(v20, v19, (char *)this - 16, v12, a2, v44, v43, v47, v46);
  if ( this != (CAudioCaptureClient *)-56LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  EventActivityIdControl(4u, &ActivityId);
  if ( v6 )
    ReleaseSRWLockShared(v6);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800186b0  push    rbp
0x1800186b2  push    rbx
0x1800186b3  push    rsi
0x1800186b4  push    rdi
0x1800186b5  push    r12
0x1800186b7  push    r13
0x1800186b9  push    r14
0x1800186bb  push    r15
0x1800186bd  lea     rbp, [rsp-38h]
0x1800186c2  sub     rsp, 138h
0x1800186c9  mov     rax, cs:__security_cookie
0x1800186d0  xor     rax, rsp
0x1800186d3  mov     [rbp+70h+var_50], rax
0x1800186d7  mov     rax, [rbp+70h+arg_20]
0x1800186de  xor     edi, edi
0x1800186e0  mov     [rbp+70h+var_F0], rax
0x1800186e4  mov     ebx, edi
0x1800186e6  mov     rax, [rbp+70h+arg_28]
0x1800186ed  mov     r14, rdx
0x1800186f0  mov     [rsp+170h+var_F8], rax
0x1800186f5  mov     rsi, rcx
0x1800186f8  mov     rax, [rcx+70h]
0x1800186fc  mov     [rsp+170h+var_110], r9
0x180018701  mov     [rsp+170h+var_108], r8
0x180018706  mov     [rsp+170h+var_118], rbx
0x18001870b  cmp     dword ptr [rax+344h], 2
0x180018712  jz      loc_180018B65
0x180018718  lea     r15, [rcx+70h]
0x18001871c  mov     rcx, [r15]
0x18001871f  lea     rdx, [rbp+70h+ActivityId]; ActivityId
0x180018723  movups  xmm0, xmmword ptr [rcx+210h]
0x18001872a  movups  [rbp+70h+var_70], xmm0
0x18001872e  mov     rax, [rcx+210h]
0x180018735  mov     qword ptr [rbp+70h+ActivityId.Data1], rax
0x180018739  mov     rax, [rcx+218h]
0x180018740  mov     ecx, 4; ControlCode
0x180018745  mov     qword ptr [rbp+70h+ActivityId.Data4], rax
0x180018749  call    cs:__imp_EventActivityIdControl
0x18001874f  xorps   xmm0, xmm0
0x180018752  mov     [rsp+170h+var_120], edi
0x180018756  xor     eax, eax
0x180018758  lea     r12, [rsi+38h]
0x18001875c  mov     rcx, r12; lpCriticalSection
0x18001875f  mov     [rbp+70h+var_B0], rax
0x180018763  movups  [rbp+70h+var_D0], xmm0
0x180018767  mov     [rbp+70h+var_D8], rax
0x18001876b  movups  [rbp+70h+var_C0], xmm0
0x18001876f  movups  xmmword ptr [rbp+70h+Src], xmm0
0x180018773  call    cs:__imp_EnterCriticalSection
0x180018779  test    r14, r14
0x18001877c  jz      short loc_180018781
0x18001877e  mov     [r14], rdi
0x180018781  cmp     cs:?g_ProcessIsTerminating@@3HA, edi; int g_ProcessIsTerminating
0x180018787  mov     dword ptr [rbp+70h+var_D8], 41435053h
0x18001878e  mov     dword ptr [rbp+70h+Src+0Ch], edi
0x180018791  mov     [rbp+70h+Src], rdi
0x180018795  jnz     loc_180018B2C
0x18001879b  mov     rcx, [r15]
0x18001879e  mov     edi, [rcx+148h]
0x1800187a4  test    edi, edi
0x1800187a6  js      loc_1800189A0
0x1800187ac  test    r14, r14
0x1800187af  jz      loc_180018BC0
0x1800187b5  mov     rdx, [rsp+170h+var_108]
0x1800187ba  test    rdx, rdx
0x1800187bd  jz      loc_180018BC0
0x1800187c3  cmp     [rsp+170h+var_110], 0
0x1800187c9  jz      loc_180018BC0
0x1800187cf  cmp     qword ptr [rsi+78h], 0
0x1800187d4  jnz     loc_180018B5B
0x1800187da  mov     eax, 1
0x1800187df  lock xadd [rcx+14Ch], eax
0x1800187e7  inc     eax
0x1800187e9  cmp     eax, 2
0x1800187ec  jz      loc_180018B18
0x1800187f2  mov     dword ptr [rdx], 0
0x1800187f8  lea     rdx, [rbp+70h+var_A0.u64PaddingFrames]; ActivityId
0x1800187fc  mov     dword ptr [rsi+88h], 0
0x180018806  mov     rcx, [rsi+70h]
0x18001880a  movups  xmm0, xmmword ptr [rcx+210h]
0x180018811  movups  xmmword ptr [rbp+70h+var_A0.u64DevicePosition], xmm0
0x180018815  mov     rax, [rcx+210h]
0x18001881c  mov     [rbp+70h+var_A0.u64PaddingFrames], rax
0x180018820  mov     rax, [rcx+218h]
0x180018827  mov     ecx, 4; ControlCode
0x18001882c  mov     [rbp+70h+var_A0.hnsQPCPosition], rax
0x180018830  call    cs:__imp_EventActivityIdControl
0x180018836  mov     rcx, r12; lpCriticalSection
0x180018839  mov     [rsp+170h+var_118], 0
0x180018842  call    cs:__imp_EnterCriticalSection
0x180018848  cmp     cs:?g_ProcessIsTerminating@@3HA, 0; int g_ProcessIsTerminating
0x18001884f  jnz     loc_180018B36
0x180018855  mov     rax, [rsi+70h]
0x180018859  mov     edi, [rax+148h]
0x18001885f  test    edi, edi
0x180018861  js      short loc_1800188BE
0x180018863  mov     rcx, [rsi+68h]
0x180018867  lea     rdx, [rsp+170h+var_118]
0x18001886c  xor     r8d, r8d
0x18001886f  mov     rax, [rcx]
0x180018872  mov     rax, [rax+18h]
0x180018876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001887b  mov     rax, [rsi+80h]
0x180018882  xorps   xmm1, xmm1
0x180018885  xor     edx, edx; unsigned int
0x180018887  xorps   xmm0, xmm0
0x18001888a  cvtsi2sd xmm0, [rsp+170h+var_118]
0x180018891  movzx   ecx, word ptr [rax+0Ch]
0x180018895  mov     eax, [rax+8]
0x180018898  div     ecx
0x18001889a  mov     ecx, eax; char *
0x18001889c  cvtsi2sd xmm1, rcx
0x1800188a1  mulsd   xmm1, xmm0
0x1800188a5  divsd   xmm1, cs:__real@416312d000000000
0x1800188ad  addsd   xmm1, cs:__real@3fe0000000000000
0x1800188b5  cvttsd2si rax, xmm1
0x1800188ba  mov     [rsp+170h+var_120], eax
0x1800188be  lea     rax, [rsp+170h+var_120]
0x1800188c3  mov     r9d, edi; int
0x1800188c6  lea     r8, [rsi-10h]; void *
0x1800188ca  mov     [rsp+170h+var_150], rax; unsigned int *
0x1800188cf  call    ?TraceWASAPI_IAudioCaptureClient_GetNextPacketSize@@YAXPEBDIPEAXJPEAI@Z; TraceWASAPI_IAudioCaptureClient_GetNextPacketSize(char const *,uint,void *,long,uint *)
0x1800188d4  test    r12, r12
0x1800188d7  jz      short loc_1800188E2
0x1800188d9  mov     rcx, r12; lpCriticalSection
0x1800188dc  call    cs:__imp_LeaveCriticalSection
0x1800188e2  lea     rdx, [rbp+70h+var_A0.u64PaddingFrames]; ActivityId
0x1800188e6  mov     ecx, 4; ControlCode
0x1800188eb  call    cs:__imp_EventActivityIdControl
0x1800188f1  mov     eax, [rsp+170h+var_120]
0x1800188f5  test    eax, eax
0x1800188f7  jnz     loc_1800189B6
0x1800188fd  mov     rax, [r15]
0x180018900  mov     edi, 8890001h
0x180018905  lock dec dword ptr [rax+14Ch]
0x18001890c  mov     rax, [rsp+170h+var_F8]
0x180018911  lea     r8, [rsi-10h]; void *
0x180018915  mov     [rsp+170h+var_130], rax; unsigned __int64 *
0x18001891a  mov     r9d, edi; int
0x18001891d  mov     rax, [rbp+70h+var_F0]
0x180018921  mov     [rsp+170h+var_138], rax; unsigned __int64 *
0x180018926  mov     rax, [rsp+170h+var_110]
0x18001892b  mov     [rsp+170h+var_140], rax; unsigned int *
0x180018930  mov     rax, [rsp+170h+var_108]
0x180018935  mov     [rsp+170h+var_148], rax; unsigned int *
0x18001893a  mov     [rsp+170h+var_150], r14; unsigned __int8 **
0x18001893f  call    ?TraceWASAPI_IAudioCaptureClient_GetBuffer@@YAXPEBDIPEAXJPEAPEAEPEAIPEAKPEA_K5@Z; TraceWASAPI_IAudioCaptureClient_GetBuffer(char const *,uint,void *,long,uchar * *,uint *,ulong *,unsigned __int64 *,unsigned __int64 *)
0x180018944  test    r12, r12
0x180018947  jz      short loc_180018952
0x180018949  mov     rcx, r12; lpCriticalSection
0x18001894c  call    cs:__imp_LeaveCriticalSection
0x180018952  lea     rdx, [rbp+70h+ActivityId]; ActivityId
0x180018956  mov     ecx, 4; ControlCode
0x18001895b  call    cs:__imp_EventActivityIdControl
0x180018961  test    rbx, rbx
0x180018964  jz      short loc_18001896F
0x180018966  mov     rcx, rbx; SRWLock
0x180018969  call    cs:__imp_ReleaseSRWLockShared
0x18001896f  mov     eax, edi
0x180018971  mov     rcx, [rbp+70h+var_50]
0x180018975  xor     rcx, rsp; StackCookie
0x180018978  call    __security_check_cookie
0x18001897d  add     rsp, 138h
0x180018984  pop     r15
0x180018986  pop     r14
0x180018988  pop     r13
0x18001898a  pop     r12
0x18001898c  pop     rdi
0x18001898d  pop     rsi
0x18001898e  pop     rbx
0x18001898f  pop     rbp
0x180018990  retn
0x180018991  mov     rax, [r15]
0x180018994  mov     edi, 8007000Eh
0x180018999  lock dec dword ptr [rax+14Ch]
0x1800189a0  mov     rcx, [r15]
0x1800189a3  mov     edx, edi; int
0x1800189a5  add     rcx, 200h; this
0x1800189ac  call    ?LogCaptureGetBufferFailure@CAudioClientTraceLogger@@QEAAXJ@Z; CAudioClientTraceLogger::LogCaptureGetBufferFailure(long)
0x1800189b1  jmp     loc_18001890C
0x1800189b6  mov     rcx, [rsi+60h]
0x1800189ba  lea     r8, [rbp+70h+var_D0]
0x1800189be  mov     dword ptr [rbp+70h+Src+8], eax
0x1800189c1  lea     rdx, [rbp+70h+Src]
0x1800189c5  mov     rax, [rcx]
0x1800189c8  mov     rax, [rax+18h]
0x1800189cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189d1  mov     edx, dword ptr [rbp+70h+Src+8]
0x1800189d4  mov     rdi, [rsp+170h+var_108]
0x1800189d9  mov     [rdi], edx
0x1800189db  mov     rax, [rsi+80h]
0x1800189e2  mov     rcx, [rsi+98h]; void *
0x1800189e9  movzx   eax, word ptr [rax+0Ch]
0x1800189ed  imul    eax, edx
0x1800189f0  mov     [rsp+170h+var_118], rax
0x1800189f5  test    rcx, rcx
0x1800189f8  jz      loc_180018AD5
0x1800189fe  cmp     [rsi+0A0h], rax
0x180018a05  jb      loc_180018AD5
0x180018a0b  mov     rdx, [rbp+70h+Src]; Src
0x180018a0f  mov     r8, rax; Size
0x180018a12  call    memcpy_0
0x180018a17  mov     rcx, [rbp+70h+var_F0]
0x180018a1b  mov     rax, [rsi+98h]
0x180018a22  mov     [r14], rax
0x180018a25  test    rcx, rcx
0x180018a28  jz      short loc_180018A31
0x180018a2a  mov     rax, qword ptr [rbp+70h+var_D0+8]
0x180018a2e  mov     [rcx], rax
0x180018a31  mov     rcx, [rsp+170h+var_F8]
0x180018a36  test    rcx, rcx
0x180018a39  jz      short loc_180018A42
0x180018a3b  mov     rax, qword ptr [rbp+70h+var_C0+8]
0x180018a3f  mov     [rcx], rax
0x180018a42  mov     ecx, dword ptr [rbp+70h+var_B0+4]
0x180018a45  mov     edx, ecx
0x180018a47  and     edx, 1
0x180018a4a  mov     eax, edx
0x180018a4c  or      eax, 4
0x180018a4f  test    cl, 4
0x180018a52  cmovnz  edx, eax
0x180018a55  mov     eax, dword ptr [rbp+70h+Src+0Ch]
0x180018a58  mov     ecx, edx
0x180018a5a  or      ecx, 2
0x180018a5d  test    al, 2
0x180018a5f  mov     rax, [rsp+170h+var_110]
0x180018a64  cmovz   ecx, edx
0x180018a67  mov     [rax], ecx
0x180018a69  mov     r9, [r15]
0x180018a6c  mov     rcx, [rbp+70h+Src]
0x180018a70  cmp     dword ptr [r9+1E0h], 1
0x180018a78  jz      loc_180018B40
0x180018a7e  mov     eax, [rdi]
0x180018a80  lea     r8, [rbp+70h+var_A0]; struct AE_CURRENT_POSITION *
0x180018a84  movups  xmm0, [rbp+70h+var_D0]
0x180018a88  mov     rdx, [rsi+80h]; struct tWAVEFORMATEX *
0x180018a8f  xor     edi, edi
0x180018a91  movups  xmm1, [rbp+70h+var_C0]
0x180018a95  mov     [rsi+78h], rcx
0x180018a99  lea     rcx, [r9+200h]; this
0x180018aa0  mov     [rsi+88h], eax
0x180018aa6  mov     rax, [r9+330h]
0x180018aad  mov     r9, [r9+338h]; __int64
0x180018ab4  movaps  xmmword ptr [rbp+70h+var_A0.u64DevicePosition], xmm0
0x180018ab8  movsd   xmm0, [rbp+70h+var_B0]
0x180018abd  movsd   qword ptr [rbp+70h+var_A0.f32FramesPerSecond], xmm0
0x180018ac2  movaps  xmmword ptr [rbp+70h+var_A0.u64PaddingFrames], xmm1
0x180018ac6  mov     [rsp+170h+var_150], rax; __int64
0x180018acb  call    ?LogCaptureLatency@CAudioClientTraceLogger@@QEAAXPEBUtWAVEFORMATEX@@UAE_CURRENT_POSITION@@_J2@Z; CAudioClientTraceLogger::LogCaptureLatency(tWAVEFORMATEX const *,AE_CURRENT_POSITION,__int64,__int64)
0x180018ad0  jmp     loc_18001890C
0x180018ad5  mov     rcx, rax; cb
0x180018ad8  call    cs:__imp_CoTaskMemAlloc
0x180018ade  mov     rcx, [rsi+98h]; pv
0x180018ae5  mov     [rsi+98h], rax
0x180018aec  test    rcx, rcx
0x180018aef  jz      short loc_180018AF7
0x180018af1  call    cs:__imp_CoTaskMemFree
0x180018af7  mov     rcx, [rsi+98h]
0x180018afe  test    rcx, rcx
0x180018b01  jz      loc_180018991
0x180018b07  mov     rax, [rsp+170h+var_118]
0x180018b0c  mov     [rsi+0A0h], rax
0x180018b13  jmp     loc_180018A0B
0x180018b18  mov     rax, [r15]
0x180018b1b  mov     edi, 8889000Bh
0x180018b20  lock dec dword ptr [rax+14Ch]
0x180018b27  jmp     loc_1800189A0
0x180018b2c  mov     edi, 88890004h
0x180018b31  jmp     loc_1800189A0
0x180018b36  mov     edi, 88890004h
0x180018b3b  jmp     loc_1800188BE
0x180018b40  test    rcx, rcx
0x180018b43  jnz     loc_180018A7E
0x180018b49  lock dec dword ptr [r9+14Ch]
0x180018b51  mov     edi, 88890018h
0x180018b56  jmp     loc_1800189A0
0x180018b5b  mov     edi, 88890007h
0x180018b60  jmp     loc_1800189A0
0x180018b65  lea     rbx, [rax+360h]
0x180018b6c  mov     rcx, rbx; SRWLock
0x180018b6f  call    cs:__imp_AcquireSRWLockShared
0x180018b75  lea     rdx, [rsp+170h+SRWLock]
0x180018b7a  mov     [rsp+170h+SRWLock], rbx
0x180018b7f  lea     rcx, [rsp+170h+var_118]
0x180018b84  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x180018b89  mov     rcx, [rsp+170h+SRWLock]; SRWLock
0x180018b8e  test    rcx, rcx
0x180018b91  jz      short loc_180018B99
0x180018b93  call    cs:__imp_ReleaseSRWLockShared
0x180018b99  mov     rcx, [rsi+70h]
0x180018b9d  lea     r15, [rsi+70h]
0x180018ba1  xor     r8d, r8d; bAlertable
0x180018ba4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180018ba9  mov     rcx, [rcx+368h]; hHandle
0x180018bb0  call    cs:__imp_WaitForSingleObjectEx
0x180018bb6  mov     rbx, [rsp+170h+var_118]
0x180018bbb  jmp     loc_18001871C
0x180018bc0  mov     edi, 80004003h
0x180018bc5  jmp     loc_1800189A0
```
