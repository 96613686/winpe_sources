# NetSetupSvcDeviceManager::~NetSetupSvcDeviceManager(void)

- ea: `0x18001d74c`
- end: `0x18001d778`
- name: `??1NetSetupSvcDeviceManager@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(struct _TP_WORK **this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800091c0`
- `0x18002ea08`

## callees

- `0x18001d74c`
- `0x18001d7e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001d75d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001d75d`

## pseudocode

```c
void __fastcall NetSetupSvcDeviceManager::~NetSetupSvcDeviceManager(struct _TP_WORK **this)
{
  struct _TP_WORK *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    CloseThreadpoolWork(v2);
    *this = 0;
  }
  details::WorkSynchronization::~WorkSynchronization((details::WorkSynchronization *)(this + 1));
}

```

## disassembly

```asm
0x18001d74c  push    rbx
0x18001d74e  sub     rsp, 20h
0x18001d752  mov     rbx, rcx
0x18001d755  mov     rcx, [rcx]; pwk
0x18001d758  test    rcx, rcx
0x18001d75b  jz      short loc_18001D76A
0x18001d75d  call    cs:__imp_CloseThreadpoolWork
0x18001d763  mov     qword ptr [rbx], 0
0x18001d76a  lea     rcx, [rbx+8]; this
0x18001d76e  add     rsp, 20h
0x18001d772  pop     rbx
0x18001d773  jmp     ??1WorkSynchronization@details@@QEAA@XZ; details::WorkSynchronization::~WorkSynchronization(void)
```
