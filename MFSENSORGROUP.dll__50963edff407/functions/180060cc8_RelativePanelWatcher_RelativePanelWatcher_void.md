# RelativePanelWatcher::~RelativePanelWatcher(void)

- ea: `0x180060cc8`
- end: `0x180060d49`
- name: `??1RelativePanelWatcher@@EEAA@XZ`
- size: `129`
- prototype: `void __fastcall(RelativePanelWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180060ed0`

## callees

- `0x180008f9c`
- `0x180044b28`
- `0x180060cc8`
- `0x180062470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180060d36`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180060d36`

## pseudocode

```c
void __fastcall RelativePanelWatcher::~RelativePanelWatcher(RelativePanelWatcher *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &RelativePanelWatcher::`vftable'{for `IMFRelativePanelWatcher'};
  *((_QWORD *)this + 1) = &RelativePanelWatcher::`vftable'{for `IMFRelativePanelReport'};
  RelativePanelWatcher::Shutdown(this);
  v2 = (void *)*((_QWORD *)this + 10);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 10) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 9) = 0;
  }
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 14);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 13);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 12);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x180060cc8  push    rbx
0x180060cca  sub     rsp, 20h
0x180060cce  lea     rax, ??_7RelativePanelWatcher@@6BIMFRelativePanelWatcher@@@; const RelativePanelWatcher::`vftable'{for `IMFRelativePanelWatcher'}
0x180060cd5  mov     rbx, rcx
0x180060cd8  mov     [rcx], rax
0x180060cdb  lea     rax, ??_7RelativePanelWatcher@@6BIMFRelativePanelReport@@@; const RelativePanelWatcher::`vftable'{for `IMFRelativePanelReport'}
0x180060ce2  mov     [rcx+8], rax
0x180060ce6  call    ?Shutdown@RelativePanelWatcher@@UEAAJXZ; RelativePanelWatcher::Shutdown(void)
0x180060ceb  mov     rcx, [rbx+50h]; Block
0x180060cef  test    rcx, rcx
0x180060cf2  jz      short loc_180060D01
0x180060cf4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060cf9  mov     qword ptr [rbx+50h], 0
0x180060d01  mov     rcx, [rbx+48h]; Block
0x180060d05  test    rcx, rcx
0x180060d08  jz      short loc_180060D17
0x180060d0a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060d0f  mov     qword ptr [rbx+48h], 0
0x180060d17  lea     rcx, [rbx+70h]
0x180060d1b  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180060d20  lea     rcx, [rbx+68h]
0x180060d24  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180060d29  lea     rcx, [rbx+60h]
0x180060d2d  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180060d32  lea     rcx, [rbx+18h]; lpCriticalSection
0x180060d36  call    cs:__imp_DeleteCriticalSection
0x180060d3c  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x180060d43  add     rsp, 20h
0x180060d47  pop     rbx
0x180060d48  retn
```
