# CStreamInstance::~CStreamInstance(void)

- ea: `0x140012e14`
- end: `0x140012e78`
- name: `??1CStreamInstance@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(CStreamInstance *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012dbc`
- `0x14005ff7c`

## callees

- `0x140008124`
- `0x14000e590`
- `0x1400127bc`
- `0x14001c9ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140012e24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140012e31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140012e24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140012e31`

## pseudocode

```c
void __fastcall CStreamInstance::~CStreamInstance(CStreamInstance *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 136);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 128);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 120);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 104);
  ATL::CAutoPtr<CPipeInstance>::Free((char *)this + 80);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CStreamInstance *)((char *)this + 32));
}

```

## disassembly

```asm
0x140012e14  push    rbx
0x140012e16  sub     rsp, 20h
0x140012e1a  mov     rbx, rcx
0x140012e1d  add     rcx, 0E0h; lpCriticalSection
0x140012e24  call    cs:__imp_DeleteCriticalSection
0x140012e2a  lea     rcx, [rbx+90h]; lpCriticalSection
0x140012e31  call    cs:__imp_DeleteCriticalSection
0x140012e37  lea     rcx, [rbx+88h]
0x140012e3e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140012e43  lea     rcx, [rbx+80h]
0x140012e4a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140012e4f  lea     rcx, [rbx+78h]
0x140012e53  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140012e58  lea     rcx, [rbx+68h]
0x140012e5c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140012e61  lea     rcx, [rbx+50h]
0x140012e65  call    ?Free@?$CAutoPtr@VCPipeInstance@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CPipeInstance>::Free(void)
0x140012e6a  lea     rcx, [rbx+20h]; this
0x140012e6e  add     rsp, 20h
0x140012e72  pop     rbx
0x140012e73  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
