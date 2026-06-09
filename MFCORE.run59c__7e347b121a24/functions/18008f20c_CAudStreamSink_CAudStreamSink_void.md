# CAudStreamSink::~CAudStreamSink(void)

- ea: `0x18008f20c`
- end: `0x18008f803`
- name: `??1CAudStreamSink@@UEAA@XZ`
- size: `1527`
- prototype: `void __fastcall(CAudStreamSink *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180317c20`

## callees

- `0x18000f278`
- `0x18002fee0`
- `0x180033eb8`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x18006b388`
- `0x18007cae0`
- `0x18008eea0`
- `0x18008f20c`
- `0x18008fd14`
- `0x1800f78c0`
- `0x180151650`
- `0x18015beb4`
- `0x1801760fc`
- `0x18017f040`
- `0x180185104`
- `0x18018a578`
- `0x1801c83a4`
- `0x180258390`
- `0x18025839c`
- `0x180258480`
- `0x180323654`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f633`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f6c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f6e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f70a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f71d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f730`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f743`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f756`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f79d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f7b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f633`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f6c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f6e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f70a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f71d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f730`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f743`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f756`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f79d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008f7b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f598`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f5b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f598`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008f5b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f783`
- `MFPlat!MFUnlockWorkQueue` at `0x18008f5d4`
- `MFPlat!MFUnlockWorkQueue` at `0x18008f5d4`

## string_xrefs

- `0x18008f362`: `CAudStreamSink::~CAudStreamSink`

## pseudocode

```c
void __fastcall CAudStreamSink::~CAudStreamSink(CAudStreamSink *this)
{
  CAudStreamVolume *v2; // r14
  CMFSampleProtectionBase *v3; // r15
  char *v4; // rbp
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  __int128 v7; // xmm0
  void *v8; // rbx
  void *v9; // rcx
  void *v10; // rcx
  CSampleQueue *v11; // rbx
  int v12; // eax
  CBaseUnknown *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  DWORD v18; // ecx
  __int64 v19; // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  __int64 v21; // rbx
  _BYTE v22[8]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v23[16]; // [rsp+38h] [rbp-40h] BYREF

  v2 = (CAudStreamSink *)((char *)this + 360);
  v3 = (CAudStreamSink *)((char *)this + 464);
  v4 = (char *)this + 544;
  *(_QWORD *)this = &CAudStreamSink::`vftable'{for `CBaseUnknown'};
  *((_QWORD *)this + 2) = &CAudStreamSink::`vftable'{for `IMFStreamSink'};
  *((_QWORD *)this + 3) = &CAudStreamSink::`vftable'{for `IMFClockStateSink'};
  *((_QWORD *)this + 4) = &CAudStreamSink::`vftable'{for `CMFMediaTypeHandlerBase'};
  *((_QWORD *)this + 13) = &CAudStreamSink::`vftable'{for `CBaseStreamSinkEventGenerator'};
  *((_QWORD *)this + 45) = &CAudStreamSink::`vftable'{for `IMFSimpleAudioVolume'};
  *((_QWORD *)this + 46) = &CAudStreamSink::`vftable'{for `IMFAudioStreamVolume'};
  *((_QWORD *)this + 58) = &CAudStreamSink::`vftable'{for `CMFSampleProtectionBase'};
  *((_QWORD *)this + 68) = &CAudStreamSink::`vftable'{for `CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>'};
  *((_QWORD *)this + 77) = &CAudStreamSink::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 78) = &CAudStreamSink::`vftable'{for `IMFTrustedOutput'};
  *((_QWORD *)this + 79) = &CAudStreamSink::`vftable'{for `IMFRealTimeClient'};
  *((_QWORD *)this + 80) = &CAudStreamSink::`vftable'{for `IMFRealTimeClientEx'};
  *((_QWORD *)this + 81) = &CAudStreamSink::`vftable'{for `IMFClockRateMatch'};
  *((_QWORD *)this + 82) = &CAudStreamSink::`vftable'{for `IAudStreamSinkCallback'};
  *((_QWORD *)this + 83) = &CAudStreamSink::`vftable'{for `IAudStreamSinkDataCallback'};
  *((_QWORD *)this + 84) = &CAudStreamSink::`vftable'{for `IMFTelemetryComponent'};
  *((_QWORD *)this + 85) = &CAudStreamSink::`vftable'{for `ISimpleAudioRendererPrivate'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 376) = &CAudStreamSink::`vftable'{for `CAudSinkSynchronization'};
  *(_DWORD *)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 372) = *(_DWORD *)(*((_QWORD *)this + 47) + 4LL)
                                                                           - 6968;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v22, "CAudStreamSink::~CAudStreamSink", 427);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 825) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 825) + 296LL))(*((_QWORD *)this + 825));
    v7 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 825) + 280LL))(
                      *((_QWORD *)this + 825),
                      v23);
    *((_DWORD *)ThreadRelativeContext + 504) = v6;
    *((_OWORD *)ThreadRelativeContext + 125) = v7;
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0p_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudStreamSink_DelAudStreamSink_Enter,
      this);
  CAudStreamSink::RemoveFromSink(this);
  CAudStreamSink::InternalFlush(this, 0);
  v8 = (void *)*((_QWORD *)this + 666);
  if ( v8 )
  {
    CDevClock::~CDevClock(*((LPCRITICAL_SECTION *)this + 666));
    operator delete(v8);
  }
  v9 = (void *)*((_QWORD *)this + 904);
  *((_QWORD *)this + 666) = 0;
  operator delete(v9);
  v10 = (void *)*((_QWORD *)this + 916);
  *((_QWORD *)this + 904) = 0;
  operator delete(v10);
  v11 = (CSampleQueue *)*((_QWORD *)this + 648);
  *((_QWORD *)this + 916) = 0;
  if ( v11 )
  {
    CSampleQueue::~CSampleQueue(v11);
    operator delete(v11);
  }
  *((_QWORD *)this + 648) = 0;
  if ( *((_QWORD *)this + 831) )
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 43, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 830) + 56LL))(
            *((_QWORD *)this + 830),
            (*((_QWORD *)this + 831) + 136LL) & -(__int64)(*((_QWORD *)this + 831) != 0));
    if ( v12 < 0 && g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this, v12);
    CMMNotificationClient::Shutdown(*((CMMNotificationClient **)this + 831));
    v13 = (CBaseUnknown *)*((_QWORD *)this + 831);
    if ( v13 )
    {
      CBaseUnknown::Release(v13);
      *((_QWORD *)this + 831) = 0;
    }
  }
  operator delete(*((void **)this + 100));
  v14 = *((_QWORD *)this + 101);
  *((_QWORD *)this + 100) = 0;
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 101) = 0;
  }
  v15 = *((_QWORD *)this + 660);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    *((_QWORD *)this + 660) = 0;
  }
  v16 = (void *)*((_QWORD *)this + 671);
  if ( v16 )
  {
    CloseHandle(v16);
    *((_QWORD *)this + 671) = 0;
  }
  v17 = (void *)*((_QWORD *)this + 804);
  if ( v17 )
  {
    CloseHandle(v17);
    *((_QWORD *)this + 804) = 0;
  }
  v18 = *((_DWORD *)this + 174);
  if ( v18 )
    MFUnlockWorkQueue(v18);
  v19 = *((_QWORD *)this + 816);
  if ( v19 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 16LL))(v19, 1);
  v20 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 842);
  *((_QWORD *)this + 816) = 0;
  if ( v20 )
    (**v20)(v20, 1);
  v21 = *((_QWORD *)this + 900);
  *((_QWORD *)this + 842) = 0;
  if ( v21 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v21 + 16));
    operator delete((void *)v21);
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0p_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudStreamSink_DelAudStreamSink_Exit,
      this);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v22);
  CVPtrList::RemoveAll((CAudStreamSink *)((char *)this + 6744));
  CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Cleanup();
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 6640);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 6632);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((char *)this + 6600);
  *((_QWORD *)this + 817) = &CAggregateTelemetryLazyUpdate<CAggregateSARTlmEvents,enum SARTelemetryType,SARTelemetryData *,0,0>::`vftable';
  CAggregateTelemetry<CAggregateSARTlmEvents,enum SARTelemetryType,SARTelemetryData *,0,0>::~CAggregateTelemetry<CAggregateSARTlmEvents,enum SARTelemetryType,SARTelemetryData *,0,0>();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 6456));
  CVPtrList::RemoveAll((CAudStreamSink *)((char *)this + 5984));
  CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Cleanup();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 5944));
  CVPtrList::RemoveAll((CAudStreamSink *)((char *)this + 5496));
  CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Cleanup();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 5432));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 5376));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 5288));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 5192));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 5088));
  CoTaskMemFree(*((LPVOID *)this + 104));
  *((_QWORD *)this + 104) = 0;
  CoTaskMemFree(*((LPVOID *)this + 103));
  *((_QWORD *)this + 103) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 752));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::~CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(v4);
  CMFSampleProtectionBase::~CMFSampleProtectionBase(v3);
  CAudStreamVolume::~CAudStreamVolume(v2);
  CBaseStreamSink::~CBaseStreamSink(this);
}

```

## disassembly

```asm
0x18008f20c  mov     [rsp+arg_8], rbx
0x18008f211  mov     [rsp+arg_10], rbp
0x18008f216  push    rsi
0x18008f217  push    rdi
0x18008f218  push    r12
0x18008f21a  push    r14
0x18008f21c  push    r15
0x18008f21e  sub     rsp, 50h
0x18008f222  mov     rax, cs:__security_cookie
0x18008f229  xor     rax, rsp
0x18008f22c  mov     [rsp+78h+var_30], rax
0x18008f231  mov     rsi, rcx
0x18008f234  lea     r14, [rcx+168h]
0x18008f23b  lea     r15, [rcx+1D0h]
0x18008f242  mov     r8d, 1ABh; int
0x18008f248  lea     rbp, [rcx+220h]
0x18008f24f  lea     rax, ??_7CAudStreamSink@@6BCBaseUnknown@@@; const CAudStreamSink::`vftable'{for `CBaseUnknown'}
0x18008f256  mov     [rcx], rax
0x18008f259  lea     rax, ??_7CAudStreamSink@@6BIMFStreamSink@@@; const CAudStreamSink::`vftable'{for `IMFStreamSink'}
0x18008f260  mov     [rcx+10h], rax
0x18008f264  lea     rax, ??_7CAudStreamSink@@6BIMFClockStateSink@@@; const CAudStreamSink::`vftable'{for `IMFClockStateSink'}
0x18008f26b  mov     [rcx+18h], rax
0x18008f26f  lea     rax, ??_7CAudStreamSink@@6BCMFMediaTypeHandlerBase@@@; const CAudStreamSink::`vftable'{for `CMFMediaTypeHandlerBase'}
0x18008f276  mov     [rcx+20h], rax
0x18008f27a  lea     rax, ??_7CAudStreamSink@@6BCBaseStreamSinkEventGenerator@@@; const CAudStreamSink::`vftable'{for `CBaseStreamSinkEventGenerator'}
0x18008f281  mov     [rcx+68h], rax
0x18008f285  lea     rax, ??_7CAudStreamSink@@6BIMFSimpleAudioVolume@@@; const CAudStreamSink::`vftable'{for `IMFSimpleAudioVolume'}
0x18008f28c  mov     [r14], rax
0x18008f28f  lea     rax, ??_7CAudStreamSink@@6BIMFAudioStreamVolume@@@; const CAudStreamSink::`vftable'{for `IMFAudioStreamVolume'}
0x18008f296  mov     [rcx+170h], rax
0x18008f29d  lea     rax, ??_7CAudStreamSink@@6BCMFSampleProtectionBase@@@; const CAudStreamSink::`vftable'{for `CMFSampleProtectionBase'}
0x18008f2a4  mov     [r15], rax
0x18008f2a7  lea     rax, ??_7CAudStreamSink@@6B?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@@; const CAudStreamSink::`vftable'{for `CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>'}
0x18008f2ae  mov     [rbp+0], rax
0x18008f2b2  lea     rax, ??_7CAudStreamSink@@6BIMFGetService@@@; const CAudStreamSink::`vftable'{for `IMFGetService'}
0x18008f2b9  mov     [rcx+268h], rax
0x18008f2c0  lea     rax, ??_7CAudStreamSink@@6BIMFTrustedOutput@@@; const CAudStreamSink::`vftable'{for `IMFTrustedOutput'}
0x18008f2c7  mov     [rcx+270h], rax
0x18008f2ce  lea     rax, ??_7CAudStreamSink@@6BIMFRealTimeClient@@@; const CAudStreamSink::`vftable'{for `IMFRealTimeClient'}
0x18008f2d5  mov     [rcx+278h], rax
0x18008f2dc  lea     rax, ??_7CAudStreamSink@@6BIMFRealTimeClientEx@@@; const CAudStreamSink::`vftable'{for `IMFRealTimeClientEx'}
0x18008f2e3  mov     [rcx+280h], rax
0x18008f2ea  lea     rax, ??_7CAudStreamSink@@6BIMFClockRateMatch@@@; const CAudStreamSink::`vftable'{for `IMFClockRateMatch'}
0x18008f2f1  mov     [rcx+288h], rax
0x18008f2f8  lea     rax, ??_7CAudStreamSink@@6BIAudStreamSinkCallback@@@; const CAudStreamSink::`vftable'{for `IAudStreamSinkCallback'}
0x18008f2ff  mov     [rcx+290h], rax
0x18008f306  lea     rax, ??_7CAudStreamSink@@6BIAudStreamSinkDataCallback@@@; const CAudStreamSink::`vftable'{for `IAudStreamSinkDataCallback'}
0x18008f30d  mov     [rcx+298h], rax
0x18008f314  lea     rax, ??_7CAudStreamSink@@6BIMFTelemetryComponent@@@; const CAudStreamSink::`vftable'{for `IMFTelemetryComponent'}
0x18008f31b  mov     [rcx+2A0h], rax
0x18008f322  lea     rax, ??_7CAudStreamSink@@6BISimpleAudioRendererPrivate@@@; const CAudStreamSink::`vftable'{for `ISimpleAudioRendererPrivate'}
0x18008f329  mov     [rcx+2A8h], rax
0x18008f330  mov     rax, [rcx+178h]
0x18008f337  movsxd  rcx, dword ptr [rax+4]
0x18008f33b  lea     rax, ??_7CAudStreamSink@@6BCAudSinkSynchronization@@@; const CAudStreamSink::`vftable'{for `CAudSinkSynchronization'}
0x18008f342  mov     [rcx+rsi+178h], rax
0x18008f34a  mov     rax, [rsi+178h]
0x18008f351  movsxd  rcx, dword ptr [rax+4]
0x18008f355  lea     edx, [rcx-1B38h]
0x18008f35b  mov     [rcx+rsi+174h], edx
0x18008f362  lea     rdx, aCaudstreamsink_2; "CAudStreamSink::~CAudStreamSink"
0x18008f369  lea     rcx, [rsp+78h+var_48]; this
0x18008f36e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008f373  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18008f37a  xor     r12d, r12d
0x18008f37d  cmp     [rcx+8], r12b
0x18008f381  jz      short loc_18008F3E0
0x18008f383  cmp     [rsi+19C8h], r12
0x18008f38a  jz      short loc_18008F3E0
0x18008f38c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008f391  mov     rdx, [rsi+19C8h]
0x18008f398  mov     rdi, rax
0x18008f39b  mov     rcx, [rdx]
0x18008f39e  mov     rax, [rcx+128h]
0x18008f3a5  mov     rcx, rdx
0x18008f3a8  call    cs:__guard_dispatch_icall_fptr
0x18008f3ae  mov     r8, [rsi+19C8h]
0x18008f3b5  lea     rdx, [rsp+78h+var_40]
0x18008f3ba  mov     ebx, eax
0x18008f3bc  mov     rcx, [r8]
0x18008f3bf  mov     rax, [rcx+118h]
0x18008f3c6  mov     rcx, r8
0x18008f3c9  call    cs:__guard_dispatch_icall_fptr
0x18008f3cf  movups  xmm0, xmmword ptr [rax]
0x18008f3d2  mov     [rdi+7E0h], ebx
0x18008f3d8  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18008f3e0  mov     edi, 1
0x18008f3e5  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, dil
0x18008f3ec  jz      short loc_18008F404
0x18008f3ee  mov     r8, rsi
0x18008f3f1  lea     rdx, AudStreamSink_DelAudStreamSink_Enter
0x18008f3f8  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Core_Context
0x18008f3ff  call    McTemplateU0p_EventWriteTransfer
0x18008f404  mov     rcx, rsi; this
0x18008f407  call    ?RemoveFromSink@CAudStreamSink@@UEAAJXZ; CAudStreamSink::RemoveFromSink(void)
0x18008f40c  xor     edx, edx; int
0x18008f40e  mov     rcx, rsi; this
0x18008f411  call    ?InternalFlush@CAudStreamSink@@IEAAJH@Z; CAudStreamSink::InternalFlush(int)
0x18008f416  mov     rbx, [rsi+14D0h]
0x18008f41d  test    rbx, rbx
0x18008f420  jz      short loc_18008F432
0x18008f422  mov     rcx, rbx; lpCriticalSection
0x18008f425  call    ??1CDevClock@@QEAA@XZ; CDevClock::~CDevClock(void)
0x18008f42a  mov     rcx, rbx; Block
0x18008f42d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008f432  mov     rcx, [rsi+1C40h]; Block
0x18008f439  mov     [rsi+14D0h], r12
0x18008f440  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008f445  mov     rcx, [rsi+1CA0h]; Block
0x18008f44c  mov     [rsi+1C40h], r12
0x18008f453  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008f458  mov     rbx, [rsi+1440h]
0x18008f45f  mov     [rsi+1CA0h], r12
0x18008f466  test    rbx, rbx
0x18008f469  jz      short loc_18008F47B
0x18008f46b  mov     rcx, rbx; this
0x18008f46e  call    ??1CSampleQueue@@QEAA@XZ; CSampleQueue::~CSampleQueue(void)
0x18008f473  mov     rcx, rbx; Block
0x18008f476  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008f47b  mov     [rsi+1440h], r12
0x18008f482  cmp     [rsi+19F8h], r12
0x18008f489  jz      loc_18008F539
0x18008f48f  cmp     cs:byte_1803CECE9, 20h ; ' '
0x18008f496  jb      short loc_18008F4B7
0x18008f498  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f49f  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x18008f4a6  mov     edx, 2Bh ; '+'
0x18008f4ab  mov     r9, rsi
0x18008f4ae  mov     rcx, [rcx+38h]
0x18008f4b2  call    WPP_SF_q
0x18008f4b7  mov     rcx, [rsi+19F8h]
0x18008f4be  mov     r10, [rsi+19F0h]
0x18008f4c5  lea     rax, [rcx+88h]
0x18008f4cc  neg     rcx
0x18008f4cf  mov     r9, [r10]
0x18008f4d2  mov     rcx, r10
0x18008f4d5  sbb     rdx, rdx
0x18008f4d8  and     rdx, rax
0x18008f4db  mov     rax, [r9+38h]
0x18008f4df  call    cs:__guard_dispatch_icall_fptr
0x18008f4e5  test    eax, eax
0x18008f4e7  jns     short loc_18008F515
0x18008f4e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18008f4f0  jb      short loc_18008F515
0x18008f4f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f4f9  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x18008f500  mov     edx, 2Ch ; ','
0x18008f505  mov     [rsp+78h+var_58], eax
0x18008f509  mov     r9, rsi
0x18008f50c  mov     rcx, [rcx+10h]
0x18008f510  call    WPP_SF_qD
0x18008f515  mov     rcx, [rsi+19F8h]; this
0x18008f51c  call    ?Shutdown@CMMNotificationClient@@QEAAXXZ; CMMNotificationClient::Shutdown(void)
0x18008f521  mov     rcx, [rsi+19F8h]; this
0x18008f528  test    rcx, rcx
0x18008f52b  jz      short loc_18008F539
0x18008f52d  call    ?Release@CBaseUnknown@@UEAAKXZ; CBaseUnknown::Release(void)
0x18008f532  mov     [rsi+19F8h], r12
0x18008f539  mov     rcx, [rsi+320h]; Block
0x18008f540  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008f545  mov     rcx, [rsi+328h]
0x18008f54c  mov     [rsi+320h], r12
0x18008f553  test    rcx, rcx
0x18008f556  jz      short loc_18008F56C
0x18008f558  mov     rax, [rcx]
0x18008f55b  mov     rax, [rax+10h]
0x18008f55f  call    cs:__guard_dispatch_icall_fptr
0x18008f565  mov     [rsi+328h], r12
0x18008f56c  mov     rcx, [rsi+14A0h]
0x18008f573  test    rcx, rcx
0x18008f576  jz      short loc_18008F58C
0x18008f578  mov     rax, [rcx]
0x18008f57b  mov     rax, [rax+10h]
0x18008f57f  call    cs:__guard_dispatch_icall_fptr
0x18008f585  mov     [rsi+14A0h], r12
0x18008f58c  mov     rcx, [rsi+14F8h]; hObject
0x18008f593  test    rcx, rcx
0x18008f596  jz      short loc_18008F5AB
0x18008f598  call    cs:__imp_CloseHandle
0x18008f59f  nop     dword ptr [rax+rax+00h]
0x18008f5a4  mov     [rsi+14F8h], r12
0x18008f5ab  mov     rcx, [rsi+1920h]; hObject
0x18008f5b2  test    rcx, rcx
0x18008f5b5  jz      short loc_18008F5CA
0x18008f5b7  call    cs:__imp_CloseHandle
0x18008f5be  nop     dword ptr [rax+rax+00h]
0x18008f5c3  mov     [rsi+1920h], r12
0x18008f5ca  mov     ecx, [rsi+2B8h]; dwWorkQueue
0x18008f5d0  test    ecx, ecx
0x18008f5d2  jz      short loc_18008F5E0
0x18008f5d4  call    cs:__imp_MFUnlockWorkQueue
0x18008f5db  nop     dword ptr [rax+rax+00h]
0x18008f5e0  mov     rcx, [rsi+1980h]
0x18008f5e7  test    rcx, rcx
0x18008f5ea  jz      short loc_18008F5FB
0x18008f5ec  mov     rax, [rcx]
0x18008f5ef  mov     edx, edi
0x18008f5f1  mov     rax, [rax+10h]
0x18008f5f5  call    cs:__guard_dispatch_icall_fptr
0x18008f5fb  mov     rcx, [rsi+1A50h]
0x18008f602  mov     [rsi+1980h], r12
0x18008f609  test    rcx, rcx
0x18008f60c  jz      short loc_18008F61C
0x18008f60e  mov     rax, [rcx]
0x18008f611  mov     edx, edi
0x18008f613  mov     rax, [rax]
0x18008f616  call    cs:__guard_dispatch_icall_fptr
0x18008f61c  mov     rbx, [rsi+1C20h]
0x18008f623  mov     [rsi+1A50h], r12
0x18008f62a  test    rbx, rbx
0x18008f62d  jz      short loc_18008F647
0x18008f62f  lea     rcx, [rbx+10h]; lpCriticalSection
0x18008f633  call    cs:__imp_DeleteCriticalSection
0x18008f63a  nop     dword ptr [rax+rax+00h]
0x18008f63f  mov     rcx, rbx; Block
0x18008f642  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008f647  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, dil
0x18008f64e  jz      short loc_18008F666
0x18008f650  mov     r8, rsi
0x18008f653  lea     rdx, AudStreamSink_DelAudStreamSink_Exit
0x18008f65a  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Core_Context
0x18008f661  call    McTemplateU0p_EventWriteTransfer
0x18008f666  lea     rcx, [rsp+78h+var_48]; this
0x18008f66b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18008f670  lea     rcx, [rsi+1A58h]; this
0x18008f677  call    ?RemoveAll@CVPtrList@@QEAAXXZ; CVPtrList::RemoveAll(void)
0x18008f67c  call    ?Cleanup@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXXZ; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Cleanup(void)
0x18008f681  lea     rcx, [rsi+19F0h]
0x18008f688  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18008f68d  lea     rcx, [rsi+19E8h]
0x18008f694  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18008f699  lea     rcx, [rsi+19C8h]
0x18008f6a0  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18008f6a5  lea     rcx, [rsi+1988h]
0x18008f6ac  lea     rax, ??_7?$CAggregateTelemetryLazyUpdate@VCAggregateSARTlmEvents@@W4SARTelemetryType@@PEAUSARTelemetryData@@$0A@$0A@@@6B@; const CAggregateTelemetryLazyUpdate<CAggregateSARTlmEvents,SARTelemetryType,SARTelemetryData *,0,0>::`vftable'
0x18008f6b3  mov     [rcx], rax
0x18008f6b6  call    ??1?$CAggregateTelemetry@VCAggregateSARTlmEvents@@W4SARTelemetryType@@PEAUSARTelemetryData@@$0A@$0A@@@UEAA@XZ; CAggregateTelemetry<CAggregateSARTlmEvents,SARTelemetryType,SARTelemetryData *,0,0>::~CAggregateTelemetry<CAggregateSARTlmEvents,SARTelemetryType,SARTelemetryData *,0,0>(void)
0x18008f6bb  lea     rcx, [rsi+1938h]; lpCriticalSection
0x18008f6c2  call    cs:__imp_DeleteCriticalSection
0x18008f6c9  nop     dword ptr [rax+rax+00h]
0x18008f6ce  lea     rcx, [rsi+1760h]; this
0x18008f6d5  call    ?RemoveAll@CVPtrList@@QEAAXXZ; CVPtrList::RemoveAll(void)
0x18008f6da  call    ?Cleanup@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXXZ; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Cleanup(void)
0x18008f6df  lea     rcx, [rsi+1738h]; lpCriticalSection
0x18008f6e6  call    cs:__imp_DeleteCriticalSection
0x18008f6ed  nop     dword ptr [rax+rax+00h]
0x18008f6f2  lea     rcx, [rsi+1578h]; this
0x18008f6f9  call    ?RemoveAll@CVPtrList@@QEAAXXZ; CVPtrList::RemoveAll(void)
0x18008f6fe  call    ?Cleanup@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXXZ; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Cleanup(void)
0x18008f703  lea     rcx, [rsi+1538h]; lpCriticalSection
0x18008f70a  call    cs:__imp_DeleteCriticalSection
0x18008f711  nop     dword ptr [rax+rax+00h]
0x18008f716  lea     rcx, [rsi+1500h]; lpCriticalSection
0x18008f71d  call    cs:__imp_DeleteCriticalSection
0x18008f724  nop     dword ptr [rax+rax+00h]
0x18008f729  lea     rcx, [rsi+14A8h]; lpCriticalSection
0x18008f730  call    cs:__imp_DeleteCriticalSection
0x18008f737  nop     dword ptr [rax+rax+00h]
0x18008f73c  lea     rcx, [rsi+1448h]; lpCriticalSection
0x18008f743  call    cs:__imp_DeleteCriticalSection
0x18008f74a  nop     dword ptr [rax+rax+00h]
0x18008f74f  lea     rcx, [rsi+13E0h]; lpCriticalSection
0x18008f756  call    cs:__imp_DeleteCriticalSection
0x18008f75d  nop     dword ptr [rax+rax+00h]
0x18008f762  mov     rcx, [rsi+340h]; pv
0x18008f769  call    cs:__imp_CoTaskMemFree
0x18008f770  nop     dword ptr [rax+rax+00h]
0x18008f775  mov     [rsi+340h], r12
0x18008f77c  mov     rcx, [rsi+338h]; pv
0x18008f783  call    cs:__imp_CoTaskMemFree
0x18008f78a  nop     dword ptr [rax+rax+00h]
0x18008f78f  lea     rcx, [rsi+2F0h]; lpCriticalSection
0x18008f796  mov     [rsi+338h], r12
0x18008f79d  call    cs:__imp_DeleteCriticalSection
0x18008f7a4  nop     dword ptr [rax+rax+00h]
0x18008f7a9  lea     rcx, [rsi+2C8h]; lpCriticalSection
0x18008f7b0  call    cs:__imp_DeleteCriticalSection
0x18008f7b7  nop     dword ptr [rax+rax+00h]
0x18008f7bc  mov     rcx, rbp
0x18008f7bf  call    ??1?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAA@XZ; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::~CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(void)
0x18008f7c4  mov     rcx, r15; this
0x18008f7c7  call    ??1CMFSampleProtectionBase@@UEAA@XZ; CMFSampleProtectionBase::~CMFSampleProtectionBase(void)
0x18008f7cc  mov     rcx, r14; this
0x18008f7cf  call    ??1CAudStreamVolume@@IEAA@XZ; CAudStreamVolume::~CAudStreamVolume(void)
0x18008f7d4  mov     rcx, rsi; this
0x18008f7d7  call    ??1CBaseStreamSink@@UEAA@XZ; CBaseStreamSink::~CBaseStreamSink(void)
0x18008f7dc  mov     rcx, [rsp+78h+var_30]
0x18008f7e1  xor     rcx, rsp; StackCookie
0x18008f7e4  call    __security_check_cookie
0x18008f7e9  lea     r11, [rsp+78h+var_28]
0x18008f7ee  mov     rbx, [r11+38h]
0x18008f7f2  mov     rbp, [r11+40h]
0x18008f7f6  mov     rsp, r11
0x18008f7f9  pop     r15
0x18008f7fb  pop     r14
0x18008f7fd  pop     r12
0x18008f7ff  pop     rdi
0x18008f800  pop     rsi
0x18008f801  retn
```
