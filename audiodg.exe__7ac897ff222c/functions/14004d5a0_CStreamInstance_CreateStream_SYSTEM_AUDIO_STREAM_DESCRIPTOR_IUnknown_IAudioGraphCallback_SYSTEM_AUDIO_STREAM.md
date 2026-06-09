# CStreamInstance::CreateStream(SYSTEM_AUDIO_STREAM_DESCRIPTOR *,IUnknown *,IAudioGraphCallback *,SYSTEM_AUDIO_STREAM *)

- ea: `0x14004d5a0`
- end: `0x14004dbef`
- name: `?CreateStream@CStreamInstance@@UEAAJPEAUSYSTEM_AUDIO_STREAM_DESCRIPTOR@@PEAUIUnknown@@PEAUIAudioGraphCallback@@PEAUSYSTEM_AUDIO_STREAM@@@Z`
- size: `1615`
- prototype: `__int64 __fastcall(CStreamInstance *this, struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *, struct IUnknown *, struct _RTL_CRITICAL_SECTION *, struct SYSTEM_AUDIO_STREAM *)`
- caller_count: `0`
- callee_count: `23`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140008124`
- `0x14000a378`
- `0x14000ad48`
- `0x14000c33c`
- `0x14000e11c`
- `0x14000e280`
- `0x14000e404`
- `0x14001af2c`
- `0x14001c9ac`
- `0x14001c9d8`
- `0x14001d854`
- `0x14001f8b0`
- `0x14002be00`
- `0x1400332f8`
- `0x1400349d4`
- `0x14004d5a0`
- `0x14004dbf8`
- `0x14004dd7c`
- `0x14005d0e0`
- `0x14005e150`
- `0x14005e168`
- `0x140069c30`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004d679`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004d8d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004dba3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004d679`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004d8d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004dba3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004d61b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004d61b`
- `ntdll!EtwEventActivityIdControl` at `0x14004d6b3`
- `ntdll!EtwEventActivityIdControl` at `0x14004d720`
- `ntdll!EtwEventActivityIdControl` at `0x14004d8c9`
- `ntdll!EtwEventActivityIdControl` at `0x14004db95`
- `ntdll!EtwEventActivityIdControl` at `0x14004d6b3`
- `ntdll!EtwEventActivityIdControl` at `0x14004d720`
- `ntdll!EtwEventActivityIdControl` at `0x14004d8c9`
- `ntdll!EtwEventActivityIdControl` at `0x14004db95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004d6cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004d6cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d8b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004d8b7`

## string_xrefs

- `0x14004d5f6`: `SrvStreamInstance_Create`

## pseudocode

```c
__int64 __fastcall CStreamInstance::CreateStream(
        CStreamInstance *this,
        struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *a2,
        struct IUnknown *a3,
        struct _RTL_CRITICAL_SECTION *a4,
        struct SYSTEM_AUDIO_STREAM *a5)
{
  const struct _tlgProvider_t *v8; // rax
  struct tWAVEFORMATEX *v9; // r15
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  unsigned int v11; // edi
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // eax
  LPVOID v16; // rax
  int DeviceGraphObjectCache; // eax
  __int64 v18; // rdx
  struct IDeviceGraphObjectCache *v19; // rbx
  int v20; // eax
  unsigned int v21; // edx
  __int64 v22; // rbx
  int HistoryBufferManager; // eax
  __int64 v24; // rdx
  __int64 v25; // r9
  _OWORD *v26; // rbx
  _OWORD *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r9
  __int64 v30; // r9
  int v32; // [rsp+28h] [rbp-E0h]
  int v33; // [rsp+28h] [rbp-E0h]
  int v34; // [rsp+28h] [rbp-E0h]
  int v35; // [rsp+28h] [rbp-E0h]
  struct CPipeInstance **v36; // [rsp+30h] [rbp-D8h]
  struct CPipeInstance **v37; // [rsp+30h] [rbp-D8h]
  struct CPipeInstance **v38; // [rsp+30h] [rbp-D8h]
  void *v39; // [rsp+58h] [rbp-B0h] BYREF
  struct IDeviceGraphObjectCache *v40; // [rsp+60h] [rbp-A8h] BYREF
  struct ICrossProcessMemory *v41; // [rsp+68h] [rbp-A0h] BYREF
  struct ICrossProcessEvent *v42; // [rsp+70h] [rbp-98h] BYREF
  CPipeInstance *v43; // [rsp+78h] [rbp-90h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-88h] BYREF
  __int128 v45; // [rsp+88h] [rbp-80h]
  _BYTE v46[296]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v47; // [rsp+1C0h] [rbp+B8h]
  _QWORD v48[3]; // [rsp+1D0h] [rbp+C8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+1E8h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+340h] [rbp+238h]

  lpCriticalSection = a4;
  *(_QWORD *)&v45 = this;
  v8 = AudioDgTelemetryProvider::Provider();
  CPerfTracker::CPerfTracker(&PerformanceCount, v8, "SrvStreamInstance_Create", 0);
  v9 = 0;
  v43 = 0;
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  *((_DWORD *)a5 + 236) = 0;
  if ( *((_DWORD *)a2 + 68) )
  {
    v11 = -2147418113;
    v12 = 2147549183LL;
    v13 = 295;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
      (const char *)v12,
      v32);
    goto LABEL_6;
  }
  v14 = ValidateStreamDescriptor(a2);
  v11 = v14;
  if ( v14 < 0 )
  {
    v12 = (unsigned int)v14;
    v13 = 298;
    goto LABEL_5;
  }
  v47 = *((_OWORD *)a2 + 3);
  v48[0] = *((_QWORD *)a2 + 6);
  v48[1] = *((_QWORD *)a2 + 7);
  EtwEventActivityIdControl(4, v48);
  v39 = 0;
  v15 = *((_DWORD *)a2 + 70);
  if ( v15 )
  {
    v16 = CoTaskMemAlloc(v15);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v39,
      v16);
    v9 = (struct tWAVEFORMATEX *)v39;
    if ( !v39 )
    {
      v11 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x133,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
        (const char *)0x8007000ELL,
        v32);
LABEL_11:
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v39,
        0);
      EtwEventActivityIdControl(4, v48);
LABEL_6:
      if ( v10 )
        LeaveCriticalSection(v10);
LABEL_57:
      ATL::CAutoPtr<CPipeInstance>::Free(&v43);
      goto LABEL_58;
    }
    memcpy_0(v39, *((const void **)a2 + 36), *((unsigned int *)a2 + 70));
  }
  v40 = 0;
  DeviceGraphObjectCache = GetDeviceGraphObjectCache(
                             a3,
                             *((const unsigned __int16 **)a2 + 18),
                             *((_QWORD *)a2 + 4),
                             *((_DWORD *)a2 + 34) & 1,
                             v9,
                             &v40);
  v11 = DeviceGraphObjectCache;
  if ( DeviceGraphObjectCache < 0 )
  {
    v18 = 312;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
      (const char *)(unsigned int)DeviceGraphObjectCache,
      v33);
LABEL_16:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    goto LABEL_11;
  }
  v19 = v40;
  DeviceGraphObjectCache = CPipeInstance::CreateStreamPipeInstance(v40, a2, 0, v9, a5, &v43);
  v11 = DeviceGraphObjectCache;
  if ( DeviceGraphObjectCache < 0 )
  {
    v18 = 319;
    goto LABEL_15;
  }
  DeviceGraphObjectCache = CPipeInstance::Initialize(v43);
  v11 = DeviceGraphObjectCache;
  if ( DeviceGraphObjectCache < 0 )
  {
    v18 = 320;
    goto LABEL_15;
  }
  DeviceGraphObjectCache = CPipeInstance::ConnectAPOs(v43, (struct IAudioGraphCallback *)lpCriticalSection);
  v11 = DeviceGraphObjectCache;
  if ( DeviceGraphObjectCache < 0 )
  {
    v18 = 321;
    goto LABEL_15;
  }
  v42 = 0;
  v41 = 0;
  v20 = CPipeInstance::CreateStreamInstance(v43, a2, v19, &v41, &v42, a5);
  v11 = v20;
  if ( v20 >= 0 )
  {
    v22 = v45;
    v45 = *(_OWORD *)((char *)a2 + 156);
    v36 = (struct CPipeInstance **)*((_QWORD *)a2 + 31);
    v35 = (int)v43;
    HistoryBufferManager = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)(v22 - 8) + 144LL))(
                             v22 - 8,
                             *((unsigned int *)a2 + 3),
                             *(unsigned int *)a2);
    v11 = HistoryBufferManager;
    if ( HistoryBufferManager >= 0 )
    {
      v43 = 0;
      if ( *((_QWORD *)a2 + 31) )
      {
        lpCriticalSection = 0;
        HistoryBufferManager = GetHistoryBufferManager((struct CAudioHistoryBufferManager **)&lpCriticalSection);
        v11 = HistoryBufferManager;
        if ( HistoryBufferManager < 0 )
        {
          v24 = 344;
          goto LABEL_39;
        }
        HistoryBufferManager = CAudioHistoryBufferManager::Add(
                                 lpCriticalSection,
                                 *((_QWORD *)a2 + 31),
                                 *((_DWORD *)a2 + 78),
                                 v41);
        v11 = HistoryBufferManager;
        if ( HistoryBufferManager < 0 )
        {
          v24 = 346;
          goto LABEL_39;
        }
      }
      *((_QWORD *)a5 + 4) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v22 - 8) + 88LL))(v22 - 8);
      if ( *((_DWORD *)a2 + 74) == 1
        || (HistoryBufferManager = (*(__int64 (__fastcall **)(struct ICrossProcessMemory *, char *))(*(_QWORD *)v41 + 40LL))(
                                     v41,
                                     (char *)a5 + 944),
            v11 = HistoryBufferManager,
            HistoryBufferManager >= 0) )
      {
        if ( v42 )
        {
          HistoryBufferManager = (*(__int64 (__fastcall **)(struct ICrossProcessEvent *, char *))(*(_QWORD *)v42 + 32LL))(
                                   v42,
                                   (char *)a5 + 640);
          v11 = HistoryBufferManager;
          if ( HistoryBufferManager < 0 )
          {
            v24 = 365;
            goto LABEL_39;
          }
        }
        else
        {
          v26 = (_OWORD *)((char *)a5 + 640);
          memset_0(v46, 0, sizeof(v46));
          v27 = v46;
          v28 = 2;
          do
          {
            *v26 = *v27;
            v26[1] = v27[1];
            v26[2] = v27[2];
            v26[3] = v27[3];
            v26[4] = v27[4];
            v26[5] = v27[5];
            v26[6] = v27[6];
            v26[7] = v27[7];
            v26 += 8;
            v27 += 8;
            --v28;
          }
          while ( v28 );
          *v26 = *v27;
          v26[1] = v27[1];
          *((_QWORD *)v26 + 4) = *((_QWORD *)v27 + 4);
        }
        *(float *)&v36 = FLOAT_1_0;
        LOBYTE(v25) = 1;
        TrackSystemEffectBehavior(*((_QWORD *)a2 + 18), 1, 0, v25, &GUID_00000000_0000_0000_0000_000000000000, v36);
        *(float *)&v37 = FLOAT_1_0;
        LOBYTE(v29) = 1;
        TrackSystemEffectBehavior(*((_QWORD *)a2 + 18), 2, 0, v29, &GUID_00000000_0000_0000_0000_000000000000, v37);
        *(float *)&v38 = FLOAT_1_0;
        LOBYTE(v30) = 1;
        TrackSystemEffectBehavior(*((_QWORD *)a2 + 18), 3, 0, v30, &GUID_00000000_0000_0000_0000_000000000000, v38);
        PublishDeviceGraphWnfState();
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v39,
          0);
        EtwEventActivityIdControl(4, v48);
        if ( v10 )
          LeaveCriticalSection(v10);
        v11 = 0;
        goto LABEL_57;
      }
      v24 = 357;
    }
    else
    {
      v24 = 335;
    }
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
      (const char *)(unsigned int)HistoryBufferManager,
      v35);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x145,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\streaminstance.cpp",
    (const char *)(unsigned int)v20,
    v34);
  if ( v42 )
    (*(void (__fastcall **)(struct ICrossProcessEvent *))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v41 )
    (*(void (__fastcall **)(struct ICrossProcessMemory *))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v19 )
    (*(void (__fastcall **)(struct IDeviceGraphObjectCache *))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v9 )
    CoTaskMemFree(v9);
  EtwEventActivityIdControl(4, v48);
  if ( v10 )
    LeaveCriticalSection(v10);
  if ( v43 )
    CPipeInstance::`scalar deleting destructor'(v43, v21);
  v43 = 0;
LABEL_58:
  CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
  return v11;
}

```

## disassembly

```asm
0x14004d5a0  mov     rax, rsp
0x14004d5a3  push    rbp
0x14004d5a4  push    rbx
0x14004d5a5  push    rsi
0x14004d5a6  push    rdi
0x14004d5a7  push    r12
0x14004d5a9  push    r13
0x14004d5ab  push    r14
0x14004d5ad  push    r15
0x14004d5af  lea     rbp, [rax-238h]
0x14004d5b6  sub     rsp, 2F8h
0x14004d5bd  movaps  xmmword ptr [rax-58h], xmm6
0x14004d5c1  mov     rax, cs:__security_cookie
0x14004d5c8  xor     rax, rsp
0x14004d5cb  mov     [rbp+230h+var_60], rax
0x14004d5d2  mov     [rsp+330h+lpCriticalSection], r9
0x14004d5d7  mov     rbx, r8
0x14004d5da  mov     r14, rdx
0x14004d5dd  mov     rdi, rcx
0x14004d5e0  mov     qword ptr [rbp+230h+var_2B0], rcx
0x14004d5e4  mov     r13, [rbp+230h+arg_20]
0x14004d5eb  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x14004d5f0  mov     rdx, rax; struct _tlgProvider_t *
0x14004d5f3  xor     r9d, r9d; char *
0x14004d5f6  lea     r8, aSrvstreaminsta_4; "SrvStreamInstance_Create"
0x14004d5fd  lea     rcx, [rbp+230h+PerformanceCount]; lpPerformanceCount
0x14004d604  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBD1@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,char const * const)
0x14004d609  xor     r15d, r15d
0x14004d60c  mov     [rsp+330h+var_2C0], r15
0x14004d611  lea     rsi, [rdi+0D8h]
0x14004d618  mov     rcx, rsi; lpCriticalSection
0x14004d61b  call    cs:__imp_EnterCriticalSection
0x14004d621  lea     r12, [r13+3B0h]
0x14004d628  mov     [r12], r15d
0x14004d62c  cmp     [r14+110h], r15d
0x14004d633  jz      short loc_14004D644
0x14004d635  mov     edi, 8000FFFFh
0x14004d63a  mov     r9d, edi
0x14004d63d  mov     edx, 127h
0x14004d642  jmp     short loc_14004D65A
0x14004d644  mov     rcx, r14; struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *
0x14004d647  call    ?ValidateStreamDescriptor@@YAJPEAUSYSTEM_AUDIO_STREAM_DESCRIPTOR@@@Z; ValidateStreamDescriptor(SYSTEM_AUDIO_STREAM_DESCRIPTOR *)
0x14004d64c  mov     edi, eax
0x14004d64e  test    eax, eax
0x14004d650  jns     short loc_14004D684
0x14004d652  mov     r9d, eax; char *
0x14004d655  mov     edx, 12Ah; void *
0x14004d65a  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004d661  mov     rcx, [rbp+238h]; this
0x14004d668  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004d66d  test    rsi, rsi
0x14004d670  jz      loc_14004DBAC
0x14004d676  mov     rcx, rsi; lpCriticalSection
0x14004d679  call    cs:__imp_LeaveCriticalSection
0x14004d67f  jmp     loc_14004DBAC
0x14004d684  movups  xmm0, xmmword ptr [r14+30h]
0x14004d689  movdqu  [rbp+230h+var_178], xmm0
0x14004d691  mov     rax, [r14+30h]
0x14004d695  mov     [rbp+230h+var_168], rax
0x14004d69c  mov     rax, [r14+38h]
0x14004d6a0  mov     [rbp+230h+var_160], rax
0x14004d6a7  lea     rdx, [rbp+230h+var_168]
0x14004d6ae  mov     ecx, 4
0x14004d6b3  call    cs:__imp_EtwEventActivityIdControl
0x14004d6b9  mov     [rsp+330h+var_2E0], r15
0x14004d6be  mov     eax, [r14+118h]
0x14004d6c5  test    eax, eax
0x14004d6c7  jz      short loc_14004D742
0x14004d6c9  mov     ecx, eax; cb
0x14004d6cb  call    cs:__imp_CoTaskMemAlloc
0x14004d6d1  mov     rdx, rax
0x14004d6d4  lea     rcx, [rsp+330h+var_2E0]
0x14004d6d9  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14004d6de  mov     r15, [rsp+330h+var_2E0]
0x14004d6e3  test    r15, r15
0x14004d6e6  jnz     short loc_14004D72B
0x14004d6e8  mov     rcx, [rbp+238h]; this
0x14004d6ef  mov     edi, 8007000Eh
0x14004d6f4  mov     r9d, edi; char *
0x14004d6f7  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004d6fe  mov     edx, 133h; void *
0x14004d703  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004d708  xor     edx, edx
0x14004d70a  lea     rcx, [rsp+330h+var_2E0]
0x14004d70f  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14004d714  lea     rdx, [rbp+230h+var_168]
0x14004d71b  mov     ecx, 4
0x14004d720  call    cs:__imp_EtwEventActivityIdControl
0x14004d726  jmp     loc_14004D66D
0x14004d72b  mov     r8d, [r14+118h]; Size
0x14004d732  mov     rdx, [r14+120h]; Src
0x14004d739  mov     rcx, r15; void *
0x14004d73c  call    memcpy_0
0x14004d741  nop
0x14004d742  mov     [rsp+330h+var_2D8], 0
0x14004d74b  mov     r9d, [r14+88h]
0x14004d752  and     r9d, 1; int
0x14004d756  lea     rax, [rsp+330h+var_2D8]
0x14004d75b  mov     [rsp+330h+var_308], rax; struct IDeviceGraphObjectCache **
0x14004d760  mov     [rsp+330h+var_310], r15; int
0x14004d765  mov     r8, [r14+20h]; __int64
0x14004d769  mov     rdx, [r14+90h]; unsigned __int16 *
0x14004d770  mov     rcx, rbx; struct IUnknown *
0x14004d773  call    ?GetDeviceGraphObjectCache@@YAJPEAUIUnknown@@PEBG_JHPEAUtWAVEFORMATEX@@PEAPEAUIDeviceGraphObjectCache@@@Z; GetDeviceGraphObjectCache(IUnknown *,ushort const *,__int64,int,tWAVEFORMATEX *,IDeviceGraphObjectCache * *)
0x14004d778  mov     edi, eax
0x14004d77a  test    eax, eax
0x14004d77c  jns     short loc_14004D7A8
0x14004d77e  mov     edx, 138h; void *
0x14004d783  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004d78a  mov     r9d, eax; char *
0x14004d78d  mov     rcx, [rbp+238h]; this
0x14004d794  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004d799  lea     rcx, [rsp+330h+var_2D8]
0x14004d79e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004d7a3  jmp     loc_14004D708
0x14004d7a8  lea     rax, [rsp+330h+var_2C0]
0x14004d7ad  mov     [rsp+330h+var_308], rax; struct CPipeInstance **
0x14004d7b2  mov     [rsp+330h+var_310], r13; struct SYSTEM_AUDIO_STREAM *
0x14004d7b7  mov     r9, r15; struct tWAVEFORMATEX *
0x14004d7ba  xor     r8d, r8d; struct CPipeInstance *
0x14004d7bd  mov     rdx, r14; struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *
0x14004d7c0  mov     rbx, [rsp+330h+var_2D8]
0x14004d7c5  mov     rcx, rbx; struct IDeviceGraphObjectCache *
0x14004d7c8  call    ?CreateStreamPipeInstance@CPipeInstance@@SAJPEAUIDeviceGraphObjectCache@@PEAUSYSTEM_AUDIO_STREAM_DESCRIPTOR@@PEAV1@PEAUtWAVEFORMATEX@@PEAUSYSTEM_AUDIO_STREAM@@PEAPEAV1@@Z; CPipeInstance::CreateStreamPipeInstance(IDeviceGraphObjectCache *,SYSTEM_AUDIO_STREAM_DESCRIPTOR *,CPipeInstance *,tWAVEFORMATEX *,SYSTEM_AUDIO_STREAM *,CPipeInstance * *)
0x14004d7cd  mov     edi, eax
0x14004d7cf  test    eax, eax
0x14004d7d1  jns     short loc_14004D7DA
0x14004d7d3  mov     edx, 13Fh
0x14004d7d8  jmp     short loc_14004D783
0x14004d7da  mov     rcx, [rsp+330h+var_2C0]; this
0x14004d7df  call    ?Initialize@CPipeInstance@@QEAAJXZ; CPipeInstance::Initialize(void)
0x14004d7e4  mov     edi, eax
0x14004d7e6  test    eax, eax
0x14004d7e8  jns     short loc_14004D7F1
0x14004d7ea  mov     edx, 140h
0x14004d7ef  jmp     short loc_14004D783
0x14004d7f1  mov     rdx, [rsp+330h+lpCriticalSection]; struct IAudioGraphCallback *
0x14004d7f6  mov     rcx, [rsp+330h+var_2C0]; this
0x14004d7fb  call    ?ConnectAPOs@CPipeInstance@@QEAAJPEAUIAudioGraphCallback@@@Z; CPipeInstance::ConnectAPOs(IAudioGraphCallback *)
0x14004d800  mov     edi, eax
0x14004d802  test    eax, eax
0x14004d804  jns     short loc_14004D810
0x14004d806  mov     edx, 141h
0x14004d80b  jmp     loc_14004D783
0x14004d810  mov     [rsp+330h+var_2C8], 0
0x14004d819  mov     [rsp+330h+var_2D0], 0
0x14004d822  mov     [rsp+330h+var_308], r13; struct SYSTEM_AUDIO_STREAM *
0x14004d827  lea     rax, [rsp+330h+var_2C8]
0x14004d82c  mov     [rsp+330h+var_310], rax; int
0x14004d831  lea     r9, [rsp+330h+var_2D0]; struct ICrossProcessMemory **
0x14004d836  mov     r8, rbx; struct IDeviceGraphObjectCache *
0x14004d839  mov     rdx, r14; struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *
0x14004d83c  mov     rcx, [rsp+330h+var_2C0]; this
0x14004d841  call    ?CreateStreamInstance@CPipeInstance@@QEAAJPEAUSYSTEM_AUDIO_STREAM_DESCRIPTOR@@PEAUIDeviceGraphObjectCache@@PEAPEAUICrossProcessMemory@@PEAPEAUICrossProcessEvent@@PEAUSYSTEM_AUDIO_STREAM@@@Z; CPipeInstance::CreateStreamInstance(SYSTEM_AUDIO_STREAM_DESCRIPTOR *,IDeviceGraphObjectCache *,ICrossProcessMemory * *,ICrossProcessEvent * *,SYSTEM_AUDIO_STREAM *)
0x14004d846  mov     edi, eax
0x14004d848  test    eax, eax
0x14004d84a  jns     loc_14004D8FA
0x14004d850  mov     rcx, [rbp+238h]; this
0x14004d857  mov     r9d, eax; char *
0x14004d85a  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004d861  mov     edx, 145h; void *
0x14004d866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004d86b  nop
0x14004d86c  mov     rcx, [rsp+330h+var_2C8]
0x14004d871  test    rcx, rcx
0x14004d874  jz      short loc_14004D883
0x14004d876  mov     rax, [rcx]
0x14004d879  mov     rax, [rax+10h]
0x14004d87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d882  nop
0x14004d883  mov     rcx, [rsp+330h+var_2D0]
0x14004d888  test    rcx, rcx
0x14004d88b  jz      short loc_14004D89A
0x14004d88d  mov     rax, [rcx]
0x14004d890  mov     rax, [rax+10h]
0x14004d894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d899  nop
0x14004d89a  test    rbx, rbx
0x14004d89d  jz      short loc_14004D8AF
0x14004d89f  mov     rax, [rbx]
0x14004d8a2  mov     rcx, rbx
0x14004d8a5  mov     rax, [rax+10h]
0x14004d8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d8ae  nop
0x14004d8af  test    r15, r15
0x14004d8b2  jz      short loc_14004D8BD
0x14004d8b4  mov     rcx, r15; pv
0x14004d8b7  call    cs:__imp_CoTaskMemFree
0x14004d8bd  lea     rdx, [rbp+230h+var_168]
0x14004d8c4  mov     ecx, 4
0x14004d8c9  call    cs:__imp_EtwEventActivityIdControl
0x14004d8cf  test    rsi, rsi
0x14004d8d2  jz      short loc_14004D8DD
0x14004d8d4  mov     rcx, rsi; lpCriticalSection
0x14004d8d7  call    cs:__imp_LeaveCriticalSection
0x14004d8dd  mov     rcx, [rsp+330h+var_2C0]; this
0x14004d8e2  test    rcx, rcx
0x14004d8e5  jz      short loc_14004D8EC
0x14004d8e7  call    ??_GCPipeInstance@@QEAAPEAXI@Z; CPipeInstance::`scalar deleting destructor'(uint)
0x14004d8ec  mov     [rsp+330h+var_2C0], 0
0x14004d8f5  jmp     loc_14004DBB6
0x14004d8fa  mov     rbx, qword ptr [rbp+230h+var_2B0]
0x14004d8fe  mov     r9, [rsp+330h+var_2C0]
0x14004d903  movups  xmm0, xmmword ptr [r14+9Ch]
0x14004d90b  movdqu  [rbp+230h+var_2B0], xmm0
0x14004d910  mov     rax, [rbx-8]
0x14004d914  mov     rcx, [r14+70h]
0x14004d918  mov     [rsp+40h], rcx
0x14004d91d  lea     rcx, [rbp+230h+var_2B0]
0x14004d921  mov     [rsp+330h+var_2F8], rcx
0x14004d926  mov     rcx, [r14+20h]
0x14004d92a  mov     [rsp+330h+var_300], rcx
0x14004d92f  mov     rcx, [r14+0F8h]
0x14004d936  mov     [rsp+330h+var_308], rcx
0x14004d93b  mov     [rsp+330h+var_310], r9; int
0x14004d940  mov     r8d, [r14]
0x14004d943  mov     edx, [r14+0Ch]
0x14004d947  lea     rcx, [rbx-8]
0x14004d94b  mov     rax, [rax+90h]
0x14004d952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d957  mov     edi, eax
0x14004d959  xor     r15d, r15d
0x14004d95c  test    eax, eax
0x14004d95e  jns     short loc_14004D994
0x14004d960  mov     edx, 14Fh; void *
0x14004d965  mov     rcx, [rbp+238h]; this
0x14004d96c  mov     r9d, eax; char *
0x14004d96f  lea     r8, aAvcoreAudiocor_67; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004d976  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004d97b  lea     rcx, [rsp+330h+var_2C8]
0x14004d980  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004d985  lea     rcx, [rsp+330h+var_2D0]
0x14004d98a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004d98f  jmp     loc_14004D799
0x14004d994  mov     [rsp+330h+var_2C0], r15
0x14004d999  cmp     [r14+0F8h], r15
0x14004d9a0  jz      short loc_14004D9EB
0x14004d9a2  mov     [rsp+330h+lpCriticalSection], r15
0x14004d9a7  lea     rcx, [rsp+330h+lpCriticalSection]; struct CAudioHistoryBufferManager **
0x14004d9ac  call    ?GetHistoryBufferManager@@YAJPEAPEAVCAudioHistoryBufferManager@@@Z; GetHistoryBufferManager(CAudioHistoryBufferManager * *)
0x14004d9b1  mov     edi, eax
0x14004d9b3  test    eax, eax
0x14004d9b5  jns     short loc_14004D9BE
0x14004d9b7  mov     edx, 158h
0x14004d9bc  jmp     short loc_14004D965
0x14004d9be  mov     r9, [rsp+330h+var_2D0]; struct ICrossProcessMemory *
0x14004d9c3  mov     r8d, [r14+138h]; unsigned int
0x14004d9ca  mov     rdx, [r14+0F8h]; unsigned __int64
0x14004d9d1  mov     rcx, [rsp+330h+lpCriticalSection]; lpCriticalSection
0x14004d9d6  call    ?Add@CAudioHistoryBufferManager@@QEAAJ_KKPEAUICrossProcessMemory@@@Z; CAudioHistoryBufferManager::Add(unsigned __int64,ulong,ICrossProcessMemory *)
0x14004d9db  mov     edi, eax
0x14004d9dd  test    eax, eax
0x14004d9df  jns     short loc_14004D9EB
0x14004d9e1  mov     edx, 15Ah
0x14004d9e6  jmp     loc_14004D965
0x14004d9eb  mov     rax, [rbx-8]
0x14004d9ef  lea     rcx, [rbx-8]
0x14004d9f3  mov     rax, [rax+58h]
0x14004d9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d9fc  mov     [r13+20h], rax
0x14004da00  cmp     dword ptr [r14+128h], 1
0x14004da08  jz      short loc_14004DA2E
0x14004da0a  mov     rcx, [rsp+330h+var_2D0]
0x14004da0f  mov     rax, [rcx]
0x14004da12  mov     rdx, r12
0x14004da15  mov     rax, [rax+28h]
0x14004da19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004da1e  mov     edi, eax
0x14004da20  test    eax, eax
0x14004da22  jns     short loc_14004DA2E
0x14004da24  mov     edx, 165h
0x14004da29  jmp     loc_14004D965
0x14004da2e  mov     r12d, 2
0x14004da34  mov     rcx, [rsp+330h+var_2C8]
0x14004da39  test    rcx, rcx
0x14004da3c  jz      short loc_14004DA65
0x14004da3e  lea     rdx, [r13+280h]
0x14004da45  mov     rax, [rcx]
0x14004da48  mov     rax, [rax+20h]
0x14004da4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004da51  mov     edi, eax
0x14004da53  test    eax, eax
0x14004da55  jns     loc_14004DAE9
0x14004da5b  mov     edx, 16Dh
0x14004da60  jmp     loc_14004D965
0x14004da65  lea     rbx, [r13+280h]
0x14004da6c  xor     edx, edx; Val
0x14004da6e  mov     r8d, 128h; Size
0x14004da74  lea     rcx, [rbp+230h+var_2A0]; void *
0x14004da78  call    memset_0
0x14004da7d  lea     rax, [rbp+230h+var_2A0]
0x14004da81  mov     rcx, r12
0x14004da84  mov     edx, 80h
0x14004da89  movups  xmm0, xmmword ptr [rax]
0x14004da8c  movups  xmmword ptr [rbx], xmm0
0x14004da8f  movups  xmm1, xmmword ptr [rax+10h]
0x14004da93  movups  xmmword ptr [rbx+10h], xmm1
0x14004da97  movups  xmm0, xmmword ptr [rax+20h]
0x14004da9b  movups  xmmword ptr [rbx+20h], xmm0
0x14004da9f  movups  xmm1, xmmword ptr [rax+30h]
  ... truncated ...
```
