# CAudStreamSink::CreateAudioStreamInternal(IMFMediaType *,tWAVEFORMATEX const *,ulong,int,int,ILightWeightSampleConverter * *)

- ea: `0x1800b243c`
- end: `0x1800b2b8f`
- name: `?CreateAudioStreamInternal@CAudStreamSink@@IEAAJPEAUIMFMediaType@@PEBUtWAVEFORMATEX@@KHHPEAPEAVILightWeightSampleConverter@@@Z`
- size: `1875`
- prototype: `__int64 __usercall@<rax>(CAudStreamSink *__hidden this@<rcx>, struct IMFMediaType *@<rdx>, const struct tWAVEFORMATEX *@<r8>, unsigned int@<r9d>, int, int, struct ILightWeightSampleConverter **)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180176760`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004c4cc`
- `0x180050d6c`
- `0x18006b388`
- `0x1800717b4`
- `0x18007cb1c`
- `0x18007df8c`
- `0x1800b243c`
- `0x1800b2b98`
- `0x1800b403c`
- `0x1800b4238`
- `0x180122cdc`
- `0x180132f44`
- `0x1801525b8`
- `0x180163480`
- `0x180182ce8`
- `0x18018dc3c`
- `0x18018e69c`
- `0x1801a67fc`
- `0x18025839c`
- `0x1802583e8`
- `0x180258480`
- `0x1802debc4`
- `0x18031db08`
- `0x180322690`
- `0x180324758`
- `0x180344ce4`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b28db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2a4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2acb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b28db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2a4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2acb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2529`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2844`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b29a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b29ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2529`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2844`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b29a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b29ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b2b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b2b2b`

## string_xrefs

- `0x1800b2473`: `CAudStreamSink::CreateAudioStreamInternal`
- `0x1800b26d1`: `CAudStreamSink::CreateAudioStreamInternal: SAR input format`
- `0x1800b26e4`: `CAudStreamSink::CreateAudioStreamInternal: Format used by the SAR post-conversion`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::CreateAudioStreamInternal(
        CAudStreamSink *this,
        struct IMFMediaType *a2,
        const struct tWAVEFORMATEX *a3,
        int a4,
        int a5,
        int a6,
        struct ILightWeightSampleConverter **a7)
{
  int v11; // edx
  int v12; // ecx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v14; // ebx
  __int128 v15; // xmm0
  unsigned int v16; // edx
  int AudioStream; // edi
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  const struct tWAVEFORMATEX *v21; // r8
  unsigned int v22; // edx
  const struct tWAVEFORMATEX *v23; // rbx
  void *v24; // rcx
  unsigned int v25; // eax
  void *v26; // rax
  unsigned int v27; // eax
  void *v28; // r9
  struct tWAVEFORMATEX *v29; // rdx
  CSampleQueue *v30; // rcx
  int v31; // eax
  const char *v32; // r8
  const char *v33; // rcx
  int Instance; // eax
  __int64 v35; // rdx
  __int64 v36; // rbx
  __int64 v37; // rcx
  CAudTransform **v38; // rbx
  __int64 v39; // rcx
  float v40; // xmm1_4
  __int64 v41; // rbp
  __int64 v42; // rbx
  __int64 v43; // rcx
  int v44; // edx
  __int64 v45; // rdx
  int v46; // ecx
  int v48; // [rsp+30h] [rbp-98h]
  _BYTE v49[8]; // [rsp+50h] [rbp-78h] BYREF
  void *Src; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v51[16]; // [rsp+60h] [rbp-68h] BYREF

  Src = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v49,
    "CAudStreamSink::CreateAudioStreamInternal",
    5307);
  v12 = (int)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 825) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 825) + 296LL))(*((_QWORD *)this + 825));
    v15 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 825) + 280LL))(
                       *((_QWORD *)this + 825),
                       v51);
    *((_DWORD *)ThreadRelativeContext + 504) = v14;
    *((_OWORD *)ThreadRelativeContext + 125) = v15;
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
  {
    v48 = *((_DWORD *)this + 210);
    McTemplateU0pdttt_EventWriteTransfer(v12, v11, (_DWORD)this, a4, a5);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  AudioStream = CAudStreamSink::CreateAudioStream(
                  this,
                  a2,
                  a3,
                  *((_DWORD *)this + 174),
                  (struct CMfAudioStreamIF **)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 384),
                  a5,
                  v48,
                  (struct tWAVEFORMATEX **)&Src,
                  a7);
  if ( (unsigned __int8)byte_1803CECE9 >= 4u )
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      362,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      this,
      *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 384),
      AudioStream);
  if ( AudioStream < 0 && g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      363,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      this,
      AudioStream);
  v18 = *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 384);
  if ( v18 )
  {
    if ( AudioStream >= 0 )
    {
      v19 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v18 + 112LL))(v18, (char *)this + 792);
      AudioStream = v19;
      if ( v19 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            364,
            &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
            this,
            v19);
      }
    }
    v20 = *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 384);
    *((_DWORD *)this + 1293) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 120LL))(v20);
  }
  if ( AudioStream >= 0 )
  {
    if ( !Src )
      goto LABEL_25;
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 365, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
    v21 = a3 ? a3 : (const struct tWAVEFORMATEX *)*((_QWORD *)this + 100);
    LogWaveFormat(0x10005u, v16, v21, "CAudStreamSink::CreateAudioStreamInternal: SAR input format");
    LogWaveFormat(
      0x10005u,
      v22,
      (const struct tWAVEFORMATEX *)Src,
      "CAudStreamSink::CreateAudioStreamInternal: Format used by the SAR post-conversion");
    v23 = (const struct tWAVEFORMATEX *)Src;
    if ( !Src )
LABEL_25:
      v23 = a3;
    if ( a3 )
    {
      v24 = (void *)*((_QWORD *)this + 100);
      if ( v24 )
      {
        operator delete(v24);
        *((_QWORD *)this + 100) = 0;
      }
      else if ( *((_QWORD *)this + 812) )
      {
        CAudStreamSink::InitializeOTAWrapper(this, 1);
      }
      v25 = MFGetWfxSize(v23);
      v26 = operator new[](v25);
      *((_QWORD *)this + 100) = v26;
      if ( v26 )
      {
        v27 = MFGetWfxSize(v23);
        memcpy_0(v28, v23, v27);
        v29 = (struct tWAVEFORMATEX *)*((_QWORD *)this + 100);
        v30 = (CSampleQueue *)*((_QWORD *)this + 648);
        *((_DWORD *)this + 1339) = v23->nAvgBytesPerSec;
        AudioStream = CSampleQueue::Initialize(v30, v29);
      }
      else
      {
        AudioStream = -2147024882;
      }
      v31 = IsUncompressedWaveFormatEx(*((const struct tWAVEFORMATEX **)this + 100));
      *((_DWORD *)this + 1294) = v31 == 0;
      if ( (unsigned __int8)byte_1803CECE9 >= 2u )
      {
        v32 = "Yes";
        v33 = "Yes";
        if ( v31 )
          v33 = "No";
        if ( !*((_DWORD *)this + 1293) )
          v32 = "No";
        WPP_SF_qss(*((_QWORD *)WPP_GLOBAL_Control + 7), (__int64)v32, (__int64)v33);
      }
    }
  }
  if ( AudioStream >= 0 )
  {
    Instance = CAudStreamSink::SetStreamState(this, 0, 0);
    AudioStream = Instance;
    if ( Instance >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 392));
      AudioStream = CDevClock::Reset(
                      *((LPCRITICAL_SECTION *)this + 666),
                      0,
                      *(_DWORD *)(*((_QWORD *)this + 100) + 8LL),
                      0);
      CDevClock::SetStreamFormat(*((CDevClock **)this + 666), *((struct tWAVEFORMATEX **)this + 100));
      *(_DWORD *)(*((_QWORD *)this + 666) + 508LL) = *((_DWORD *)this + 1293);
      v36 = *((_QWORD *)this + 666);
      v37 = *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 384);
      *(_QWORD *)(v36 + 528) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 128LL))(v37);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 392));
      if ( AudioStream >= 0 )
      {
        v38 = (CAudTransform **)((char *)this + 5280);
        v39 = *((_QWORD *)this + 660);
        if ( v39 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
          *v38 = 0;
        }
        Instance = CAudTransform::CreateInstance(
                     *((const struct tWAVEFORMATEX **)this + 100),
                     (struct CAudTransform **)this + 660);
        AudioStream = Instance;
        if ( Instance >= 0 )
        {
          v40 = *((float *)this + 1335);
          if ( v40 == 0.0 )
            v40 = *((float *)this + 1336);
          Instance = CAudTransform::SetSpeedup(*v38, COERCE_FLOAT(LODWORD(v40) & _xmm));
          AudioStream = Instance;
          if ( Instance < 0 && g_wppLevels )
          {
            v35 = 369;
            goto LABEL_55;
          }
        }
        else if ( g_wppLevels )
        {
          v35 = 368;
          goto LABEL_55;
        }
      }
    }
    else if ( g_wppLevels )
    {
      v35 = 367;
LABEL_55:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v35,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        this,
        Instance);
    }
  }
  v41 = *(int *)(*((_QWORD *)this + 47) + 4LL);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + v41 + 392));
  if ( AudioStream < 0 && *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 384) )
  {
    CAudStreamSink::SetLastPolicyOnNewOTAs(this, 1);
    v42 = *(int *)(*((_QWORD *)this + 47) + 4LL);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + v42 + 432));
    v43 = *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 384);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 80LL))(v43);
    *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 384) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + v42 + 432));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + v41 + 392));
  if ( AudioStream < 0 )
  {
    if ( (_BYTE)byte_1803CECE9 )
    {
      v45 = 371;
      goto LABEL_64;
    }
  }
  else
  {
    *((_QWORD *)this + 655) = 0;
    *((_QWORD *)this + 654) = 0;
    *((_QWORD *)this + 656) = 0;
    *((_QWORD *)this + 657) = 0;
    CAudStreamSink::CTimestamps::Invalidate((CAudStreamSink *)((char *)this + 5264));
    CAudTransform::Reset(*((CAudTransform **)this + 660), v44);
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    {
      v45 = 370;
LABEL_64:
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), v45, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  if ( AudioStream == -2004287229 && !*((_DWORD *)this + 1655) )
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 372, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
    CAudioClientManager::MarkFormatAsFailed(*((CAudioClientManager **)this + 842), a2);
    *((_DWORD *)this + 64) = 1;
  }
  CoTaskMemFree(Src);
  Src = 0;
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pdt_EventWriteTransfer(
      v46,
      (unsigned int)&AudStreamSink_CreateAudioStreamInternal_Exit,
      (_DWORD)this,
      AudioStream,
      *((_DWORD *)this + 1293));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v49);
  return (unsigned int)AudioStream;
}

```

## disassembly

```asm
0x1800b243c  push    rbx
0x1800b243e  push    rbp
0x1800b243f  push    rsi
0x1800b2440  push    rdi
0x1800b2441  push    r12
0x1800b2443  push    r13
0x1800b2445  push    r14
0x1800b2447  push    r15
0x1800b2449  sub     rsp, 88h
0x1800b2450  mov     rax, cs:__security_cookie
0x1800b2457  xor     rax, rsp
0x1800b245a  mov     [rsp+0C8h+var_58], rax
0x1800b245f  mov     r15, [rsp+0C8h+arg_30]
0x1800b2467  mov     rbp, r8
0x1800b246a  mov     r12, rdx
0x1800b246d  mov     rsi, rcx
0x1800b2470  xor     r13d, r13d
0x1800b2473  lea     rdx, aCaudstreamsink_82; "CAudStreamSink::CreateAudioStreamIntern"...
0x1800b247a  mov     r8d, 14BBh; int
0x1800b2480  mov     [rsp+0C8h+Src], r13
0x1800b2485  lea     rcx, [rsp+0C8h+var_78]; this
0x1800b248a  mov     r14d, r9d
0x1800b248d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b2492  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b2499  cmp     [rcx+8], r13b
0x1800b249d  jz      short loc_1800B24F6
0x1800b249f  cmp     [rsi+19C8h], r13
0x1800b24a6  jz      short loc_1800B24F6
0x1800b24a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b24ad  mov     rcx, [rsi+19C8h]
0x1800b24b4  mov     rdi, rax
0x1800b24b7  mov     rdx, [rcx]
0x1800b24ba  mov     rax, [rdx+128h]
0x1800b24c1  call    cs:__guard_dispatch_icall_fptr
0x1800b24c7  mov     rcx, [rsi+19C8h]
0x1800b24ce  mov     ebx, eax
0x1800b24d0  mov     rdx, [rcx]
0x1800b24d3  mov     rax, [rdx+118h]
0x1800b24da  lea     rdx, [rsp+0C8h+var_68]
0x1800b24df  call    cs:__guard_dispatch_icall_fptr
0x1800b24e5  movups  xmm0, xmmword ptr [rax]
0x1800b24e8  mov     [rdi+7E0h], ebx
0x1800b24ee  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800b24f6  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x1800b24fd  mov     ebx, [rsp+0C8h+arg_20]
0x1800b2504  jz      short loc_1800B251F
0x1800b2506  mov     eax, [rsi+348h]
0x1800b250c  mov     r9d, r14d
0x1800b250f  mov     [rsp+0C8h+var_98], eax; int
0x1800b2513  mov     r8, rsi
0x1800b2516  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x1800b251a  call    McTemplateU0pdttt_EventWriteTransfer
0x1800b251f  lea     r14, [rsi+2C8h]
0x1800b2526  mov     rcx, r14; lpCriticalSection
0x1800b2529  call    cs:__imp_EnterCriticalSection
0x1800b2530  nop     dword ptr [rax+rax+00h]
0x1800b2535  mov     rax, [rsi+178h]
0x1800b253c  lea     rcx, [rsp+0C8h+Src]
0x1800b2541  mov     r9d, [rsi+2B8h]; unsigned int
0x1800b2548  mov     r8, rbp; struct tWAVEFORMATEX *
0x1800b254b  mov     [rsp+0C8h+var_88], r15; struct ILightWeightSampleConverter **
0x1800b2550  mov     rdx, r12; struct IMFMediaType *
0x1800b2553  mov     [rsp+0C8h+var_90], rcx; struct tWAVEFORMATEX **
0x1800b2558  mov     rcx, rsi; this
0x1800b255b  movsxd  rax, dword ptr [rax+4]
0x1800b255f  add     rax, 180h
0x1800b2565  mov     dword ptr [rsp+0C8h+var_A0], ebx; int
0x1800b2569  add     rax, rsi
0x1800b256c  mov     [rsp+0C8h+var_A8], rax; struct CMfAudioStreamIF **
0x1800b2571  call    ?CreateAudioStream@CAudStreamSink@@QEAAJPEAUIMFMediaType@@PEBUtWAVEFORMATEX@@KPEAPEAVCMfAudioStreamIF@@HHPEAPEAU3@PEAPEAVILightWeightSampleConverter@@@Z; CAudStreamSink::CreateAudioStream(IMFMediaType *,tWAVEFORMATEX const *,ulong,CMfAudioStreamIF * *,int,int,tWAVEFORMATEX * *,ILightWeightSampleConverter * *)
0x1800b2576  mov     edi, eax
0x1800b2578  cmp     cs:byte_1803CECE9, 4
0x1800b257f  jb      short loc_1800B25BC
0x1800b2581  mov     rax, [rsi+178h]
0x1800b2588  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1800b258f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2596  mov     edx, 16Ah
0x1800b259b  mov     dword ptr [rsp+0C8h+var_A0], edi
0x1800b259f  mov     r9, rsi
0x1800b25a2  movsxd  rax, dword ptr [rax+4]
0x1800b25a6  mov     rcx, [rcx+38h]
0x1800b25aa  mov     rax, [rax+rsi+180h]
0x1800b25b2  mov     [rsp+0C8h+var_A8], rax
0x1800b25b7  call    WPP_SF_qqD
0x1800b25bc  test    edi, edi
0x1800b25be  jns     short loc_1800B25F4
0x1800b25c0  mov     r15d, 1
0x1800b25c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800b25cd  jb      short loc_1800B25FA
0x1800b25cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b25d6  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1800b25dd  mov     edx, 16Bh
0x1800b25e2  mov     dword ptr [rsp+0C8h+var_A8], edi
0x1800b25e6  mov     r9, rsi
0x1800b25e9  mov     rcx, [rcx+10h]
0x1800b25ed  call    WPP_SF_qD
0x1800b25f2  jmp     short loc_1800B25FA
0x1800b25f4  mov     r15d, 1
0x1800b25fa  mov     rax, [rsi+178h]
0x1800b2601  movsxd  rcx, dword ptr [rax+4]
0x1800b2605  mov     rcx, [rcx+rsi+180h]
0x1800b260d  test    rcx, rcx
0x1800b2610  jz      short loc_1800B2682
0x1800b2612  test    edi, edi
0x1800b2614  js      short loc_1800B265C
0x1800b2616  mov     rax, [rcx]
0x1800b2619  lea     rdx, [rsi+318h]
0x1800b2620  mov     rax, [rax+70h]
0x1800b2624  call    cs:__guard_dispatch_icall_fptr
0x1800b262a  mov     edi, eax
0x1800b262c  test    eax, eax
0x1800b262e  jns     short loc_1800B265C
0x1800b2630  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800b2637  jb      short loc_1800B265C
0x1800b2639  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2640  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1800b2647  mov     edx, 16Ch
0x1800b264c  mov     dword ptr [rsp+0C8h+var_A8], eax
0x1800b2650  mov     r9, rsi
0x1800b2653  mov     rcx, [rcx+10h]
0x1800b2657  call    WPP_SF_qD
0x1800b265c  mov     rax, [rsi+178h]
0x1800b2663  movsxd  rcx, dword ptr [rax+4]
0x1800b2667  mov     rcx, [rcx+rsi+180h]
0x1800b266f  mov     rax, [rcx]
0x1800b2672  mov     rax, [rax+78h]
0x1800b2676  call    cs:__guard_dispatch_icall_fptr
0x1800b267c  mov     [rsi+1434h], eax
0x1800b2682  mov     eax, edi
0x1800b2684  test    eax, eax
0x1800b2686  js      loc_1800B27FD
0x1800b268c  cmp     [rsp+0C8h+Src], r13
0x1800b2691  jz      short loc_1800B26FC
0x1800b2693  cmp     cs:byte_1803CECE9, 10h
0x1800b269a  jb      short loc_1800B26BB
0x1800b269c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b26a3  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1800b26aa  mov     edx, 16Dh
0x1800b26af  mov     r9, rsi
0x1800b26b2  mov     rcx, [rcx+38h]
0x1800b26b6  call    WPP_SF_q
0x1800b26bb  test    rbp, rbp
0x1800b26be  jnz     short loc_1800B26C9
0x1800b26c0  mov     r8, [rsi+320h]
0x1800b26c7  jmp     short loc_1800B26CC
0x1800b26c9  mov     r8, rbp; struct tWAVEFORMATEX *
0x1800b26cc  mov     ebx, 10005h
0x1800b26d1  lea     r9, aCaudstreamsink_67; "CAudStreamSink::CreateAudioStreamIntern"...
0x1800b26d8  mov     ecx, ebx; unsigned int
0x1800b26da  call    ?LogWaveFormat@@YAXKKPEBUtWAVEFORMATEX@@PEBD@Z; LogWaveFormat(ulong,ulong,tWAVEFORMATEX const *,char const *)
0x1800b26df  mov     r8, [rsp+0C8h+Src]; struct tWAVEFORMATEX *
0x1800b26e4  lea     r9, aCaudstreamsink_95; "CAudStreamSink::CreateAudioStreamIntern"...
0x1800b26eb  mov     ecx, ebx; unsigned int
0x1800b26ed  call    ?LogWaveFormat@@YAXKKPEBUtWAVEFORMATEX@@PEBD@Z; LogWaveFormat(ulong,ulong,tWAVEFORMATEX const *,char const *)
0x1800b26f2  mov     rbx, [rsp+0C8h+Src]
0x1800b26f7  test    rbx, rbx
0x1800b26fa  jnz     short loc_1800B26FF
0x1800b26fc  mov     rbx, rbp
0x1800b26ff  test    rbp, rbp
0x1800b2702  jz      loc_1800B27FD
0x1800b2708  mov     rcx, [rsi+320h]; Block
0x1800b270f  test    rcx, rcx
0x1800b2712  jz      short loc_1800B2722
0x1800b2714  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b2719  mov     [rsi+320h], r13
0x1800b2720  jmp     short loc_1800B2736
0x1800b2722  cmp     [rsi+1960h], r13
0x1800b2729  jz      short loc_1800B2736
0x1800b272b  mov     edx, r15d; int
0x1800b272e  mov     rcx, rsi; this
0x1800b2731  call    ?InitializeOTAWrapper@CAudStreamSink@@IEAAJH@Z; CAudStreamSink::InitializeOTAWrapper(int)
0x1800b2736  mov     rcx, rbx; struct tWAVEFORMATEX *
0x1800b2739  call    ?MFGetWfxSize@@YAKPEBUtWAVEFORMATEX@@@Z; MFGetWfxSize(tWAVEFORMATEX const *)
0x1800b273e  mov     ecx, eax; unsigned __int64
0x1800b2740  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b2745  mov     [rsi+320h], rax
0x1800b274c  mov     r9, rax
0x1800b274f  test    rax, rax
0x1800b2752  jnz     short loc_1800B275B
0x1800b2754  mov     edi, 8007000Eh
0x1800b2759  jmp     short loc_1800B278F
0x1800b275b  mov     rcx, rbx; struct tWAVEFORMATEX *
0x1800b275e  call    ?MFGetWfxSize@@YAKPEBUtWAVEFORMATEX@@@Z; MFGetWfxSize(tWAVEFORMATEX const *)
0x1800b2763  mov     r8d, eax; Size
0x1800b2766  mov     rcx, r9; void *
0x1800b2769  mov     rdx, rbx; Src
0x1800b276c  call    memcpy_0
0x1800b2771  mov     eax, [rbx+8]
0x1800b2774  mov     rdx, [rsi+320h]; struct tWAVEFORMATEX *
0x1800b277b  mov     rcx, [rsi+1440h]; this
0x1800b2782  mov     [rsi+14ECh], eax
0x1800b2788  call    ?Initialize@CSampleQueue@@QEAAJPEAUtWAVEFORMATEX@@@Z; CSampleQueue::Initialize(tWAVEFORMATEX *)
0x1800b278d  mov     edi, eax
0x1800b278f  mov     rcx, [rsi+320h]; struct tWAVEFORMATEX *
0x1800b2796  call    ?IsUncompressedWaveFormatEx@@YAHPEBUtWAVEFORMATEX@@@Z; IsUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x1800b279b  mov     ecx, r13d
0x1800b279e  test    eax, eax
0x1800b27a0  setz    cl
0x1800b27a3  mov     [rsi+1438h], ecx
0x1800b27a9  cmp     cs:byte_1803CECE9, 2
0x1800b27b0  jb      short loc_1800B27FD
0x1800b27b2  lea     rdx, aNo; "No"
0x1800b27b9  test    eax, eax
0x1800b27bb  lea     r8, aYes_0; "Yes"
0x1800b27c2  mov     r9, rsi
0x1800b27c5  mov     rcx, r8
0x1800b27c8  cmovnz  rcx, rdx
0x1800b27cc  cmp     [rsi+1434h], r13d
0x1800b27d3  mov     [rsp+0C8h+var_A0], rcx; __int64
0x1800b27d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b27df  cmovz   r8, rdx
0x1800b27e3  mov     [rsp+0C8h+var_A8], r8; __int64
0x1800b27e8  mov     edx, 16Eh
0x1800b27ed  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1800b27f4  mov     rcx, [rcx+38h]; LoggerHandle
0x1800b27f8  call    WPP_SF_qss
0x1800b27fd  test    edi, edi
0x1800b27ff  js      loc_1800B298F
0x1800b2805  xor     r8d, r8d
0x1800b2808  xor     edx, edx
0x1800b280a  mov     rcx, rsi
0x1800b280d  call    ?SetStreamState@CAudStreamSink@@IEAAJ_JW4_MFAUDIO_STATE@@@Z; CAudStreamSink::SetStreamState(__int64,_MFAUDIO_STATE)
0x1800b2812  mov     edi, eax
0x1800b2814  test    eax, eax
0x1800b2816  jns     short loc_1800B282F
0x1800b2818  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800b281f  jb      loc_1800B298F
0x1800b2825  mov     edx, 16Fh
0x1800b282a  jmp     loc_1800B2971
0x1800b282f  mov     rax, [rsi+178h]
0x1800b2836  movsxd  rcx, dword ptr [rax+4]
0x1800b283a  add     rcx, 188h
0x1800b2841  add     rcx, rsi; lpCriticalSection
0x1800b2844  call    cs:__imp_EnterCriticalSection
0x1800b284b  nop     dword ptr [rax+rax+00h]
0x1800b2850  mov     r8, [rsi+320h]
0x1800b2857  xor     r9d, r9d; int
0x1800b285a  mov     rcx, [rsi+14D0h]; lpCriticalSection
0x1800b2861  xor     edx, edx; __int64
0x1800b2863  mov     r8d, [r8+8]; unsigned int
0x1800b2867  call    ?Reset@CDevClock@@QEAAJ_JKH@Z; CDevClock::Reset(__int64,ulong,int)
0x1800b286c  mov     rdx, [rsi+320h]; struct tWAVEFORMATEX *
0x1800b2873  mov     edi, eax
0x1800b2875  mov     rcx, [rsi+14D0h]; this
0x1800b287c  call    ?SetStreamFormat@CDevClock@@QEAAXPEAUtWAVEFORMATEX@@@Z; CDevClock::SetStreamFormat(tWAVEFORMATEX *)
0x1800b2881  mov     ecx, [rsi+1434h]
0x1800b2887  mov     r10, [rsi+14D0h]
0x1800b288e  mov     [r10+1FCh], ecx
0x1800b2895  mov     rcx, [rsi+178h]
0x1800b289c  mov     rbx, [rsi+14D0h]
0x1800b28a3  movsxd  rdx, dword ptr [rcx+4]
0x1800b28a7  mov     rcx, [rdx+rsi+180h]
0x1800b28af  mov     rdx, [rcx]
0x1800b28b2  mov     rax, [rdx+80h]
0x1800b28b9  call    cs:__guard_dispatch_icall_fptr
0x1800b28bf  mov     [rbx+210h], rax
0x1800b28c6  mov     rax, [rsi+178h]
0x1800b28cd  movsxd  rcx, dword ptr [rax+4]
0x1800b28d1  add     rcx, 188h
0x1800b28d8  add     rcx, rsi; lpCriticalSection
0x1800b28db  call    cs:__imp_LeaveCriticalSection
0x1800b28e2  nop     dword ptr [rax+rax+00h]
0x1800b28e7  test    edi, edi
0x1800b28e9  js      loc_1800B298F
0x1800b28ef  lea     rbx, [rsi+14A0h]
0x1800b28f6  mov     rcx, [rbx]
0x1800b28f9  test    rcx, rcx
0x1800b28fc  jz      short loc_1800B290E
0x1800b28fe  mov     rax, [rcx]
0x1800b2901  mov     rax, [rax+10h]
0x1800b2905  call    cs:__guard_dispatch_icall_fptr
0x1800b290b  mov     [rbx], r13
0x1800b290e  mov     rcx, [rsi+320h]; struct tWAVEFORMATEX *
0x1800b2915  mov     rdx, rbx; struct CAudTransform **
0x1800b2918  call    ?CreateInstance@CAudTransform@@SAJPEBUtWAVEFORMATEX@@PEAPEAV1@@Z; CAudTransform::CreateInstance(tWAVEFORMATEX const *,CAudTransform * *)
0x1800b291d  mov     edi, eax
0x1800b291f  test    eax, eax
0x1800b2921  jns     short loc_1800B2933
0x1800b2923  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800b292a  jb      short loc_1800B298F
0x1800b292c  mov     edx, 170h
0x1800b2931  jmp     short loc_1800B2971
0x1800b2933  movss   xmm1, dword ptr [rsi+14DCh]
0x1800b293b  ucomiss xmm1, cs:__real@00000000
0x1800b2942  jp      short loc_1800B294E
0x1800b2944  jnz     short loc_1800B294E
0x1800b2946  movss   xmm1, dword ptr [rsi+14E0h]
0x1800b294e  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff; float
0x1800b2955  mov     rcx, [rbx]; this
0x1800b2958  call    ?SetSpeedup@CAudTransform@@QEAAJM@Z; CAudTransform::SetSpeedup(float)
0x1800b295d  mov     edi, eax
0x1800b295f  test    eax, eax
0x1800b2961  jns     short loc_1800B298F
0x1800b2963  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800b296a  jb      short loc_1800B298F
0x1800b296c  mov     edx, 171h
0x1800b2971  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2978  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1800b297f  mov     r9, rsi
0x1800b2982  mov     dword ptr [rsp+0C8h+var_A8], eax
  ... truncated ...
```
