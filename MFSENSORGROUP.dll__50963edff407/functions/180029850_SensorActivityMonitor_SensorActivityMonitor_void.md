# SensorActivityMonitor::~SensorActivityMonitor(void)

- ea: `0x180029850`
- end: `0x1800298b7`
- name: `??1SensorActivityMonitor@@MEAA@XZ`
- size: `103`
- prototype: `void __fastcall(SensorActivityMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a7a0`

## callees

- `0x180008f9c`
- `0x1800298c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800298a4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800298a4`

## pseudocode

```c
void __fastcall SensorActivityMonitor::~SensorActivityMonitor(SensorActivityMonitor *this)
{
  SensorActivityMonitor *v2; // rcx

  *(_QWORD *)this = &SensorActivityMonitor::`vftable'{for `IMFSensorActivityMonitorInternal'};
  v2 = (SensorActivityMonitor *)((char *)this + 8);
  *(_QWORD *)v2 = &SensorActivityMonitor::`vftable'{for `IMFShutdown'};
  SensorActivityMonitor::Shutdown(v2);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 17);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 16);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 11);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 10);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x180029850  push    rbx
0x180029852  sub     rsp, 20h
0x180029856  lea     rax, ??_7SensorActivityMonitor@@6BIMFSensorActivityMonitorInternal@@@; const SensorActivityMonitor::`vftable'{for `IMFSensorActivityMonitorInternal'}
0x18002985d  mov     rbx, rcx
0x180029860  mov     [rcx], rax
0x180029863  add     rcx, 8; this
0x180029867  lea     rax, ??_7SensorActivityMonitor@@6BIMFShutdown@@@; const SensorActivityMonitor::`vftable'{for `IMFShutdown'}
0x18002986e  mov     [rcx], rax
0x180029871  call    ?Shutdown@SensorActivityMonitor@@UEAAJXZ; SensorActivityMonitor::Shutdown(void)
0x180029876  lea     rcx, [rbx+88h]
0x18002987d  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180029882  lea     rcx, [rbx+80h]
0x180029889  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18002988e  lea     rcx, [rbx+58h]
0x180029892  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180029897  lea     rcx, [rbx+50h]
0x18002989b  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800298a0  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800298a4  call    cs:__imp_DeleteCriticalSection
0x1800298aa  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x1800298b1  add     rsp, 20h
0x1800298b5  pop     rbx
0x1800298b6  retn
```
