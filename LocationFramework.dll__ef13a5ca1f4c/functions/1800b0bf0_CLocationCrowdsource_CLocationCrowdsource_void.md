# CLocationCrowdsource::~CLocationCrowdsource(void)

- ea: `0x1800b0bf0`
- end: `0x1800b0c82`
- name: `??1CLocationCrowdsource@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(CLocationCrowdsource *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800af2b0`
- `0x1800afe80`

## callees

- `0x180012398`
- `0x180015cfc`
- `0x180085444`
- `0x180085500`
- `0x18009d35c`
- `0x1800aeb7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c6e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c6e`

## pseudocode

```c
void __fastcall CLocationCrowdsource::~CLocationCrowdsource(CLocationCrowdsource *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
  ResettableTimer::~ResettableTimer((CLocationCrowdsource *)((char *)this + 424));
  CLocationCrowdsource::_unnamed_type_m_crowdsourceLockedData_::__unnamed_type_m_crowdsourceLockedData_((char *)this + 392);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  std::unique_ptr<CLocationOrionTelemetry>::~unique_ptr<CLocationOrionTelemetry>((char *)this + 336);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 328);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 320);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 312);
  LocationWnfWaitOnCallbacks::~LocationWnfWaitOnCallbacks((CLocationCrowdsource *)((char *)this + 232));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 48);
}

```

## disassembly

```asm
0x1800b0bf0  push    rbx
0x1800b0bf2  sub     rsp, 20h
0x1800b0bf6  mov     rbx, rcx
0x1800b0bf9  add     rcx, 240h; lpCriticalSection
0x1800b0c00  call    cs:__imp_DeleteCriticalSection
0x1800b0c06  lea     rcx, [rbx+1A8h]; this
0x1800b0c0d  call    ??1ResettableTimer@@UEAA@XZ; ResettableTimer::~ResettableTimer(void)
0x1800b0c12  lea     rcx, [rbx+188h]
0x1800b0c19  call    CLocationCrowdsource___unnamed_type_m_crowdsourceLockedData_____unnamed_type_m_crowdsourceLockedData_
0x1800b0c1e  lea     rcx, [rbx+160h]; lpCriticalSection
0x1800b0c25  call    cs:__imp_DeleteCriticalSection
0x1800b0c2b  lea     rcx, [rbx+150h]
0x1800b0c32  call    ??1?$unique_ptr@VCLocationOrionTelemetry@@U?$default_delete@VCLocationOrionTelemetry@@@std@@@std@@QEAA@XZ; std::unique_ptr<CLocationOrionTelemetry>::~unique_ptr<CLocationOrionTelemetry>(void)
0x1800b0c37  lea     rcx, [rbx+148h]
0x1800b0c3e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b0c43  lea     rcx, [rbx+140h]
0x1800b0c4a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b0c4f  lea     rcx, [rbx+138h]
0x1800b0c56  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b0c5b  lea     rcx, [rbx+0E8h]; this
0x1800b0c62  call    ??1LocationWnfWaitOnCallbacks@@UEAA@XZ; LocationWnfWaitOnCallbacks::~LocationWnfWaitOnCallbacks(void)
0x1800b0c67  lea     rcx, [rbx+90h]; lpCriticalSection
0x1800b0c6e  call    cs:__imp_DeleteCriticalSection
0x1800b0c74  lea     rcx, [rbx+30h]
0x1800b0c78  add     rsp, 20h
0x1800b0c7c  pop     rbx
0x1800b0c7d  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
