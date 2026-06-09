# CameraControlMonitorSubscription::~CameraControlMonitorSubscription(void)

- ea: `0x18003f8dc`
- end: `0x18003f8f6`
- name: `??1CameraControlMonitorSubscription@@AEAA@XZ`
- size: `26`
- prototype: `void __fastcall(CameraControlMonitorSubscription *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180036b10`
- `0x1800653b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f8e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f8e4`

## pseudocode

```c
void __fastcall CameraControlMonitorSubscription::~CameraControlMonitorSubscription(
        CameraControlMonitorSubscription *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x18003f8dc  sub     rsp, 28h
0x18003f8e0  add     rcx, 10h; lpCriticalSection
0x18003f8e4  call    cs:__imp_DeleteCriticalSection
0x18003f8ea  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x18003f8f1  add     rsp, 28h
0x18003f8f5  retn
```
