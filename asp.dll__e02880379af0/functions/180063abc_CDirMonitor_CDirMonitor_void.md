# CDirMonitor::~CDirMonitor(void)

- ea: `0x180063abc`
- end: `0x180063ae4`
- name: `??1CDirMonitor@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(CDirMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18003cf2c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180063ac9`
- `KERNEL32!DeleteCriticalSection` at `0x180063ac9`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180063add`
- `W3TP!ThreadPoolTerminate` at `0x180063acf`
- `W3TP!ThreadPoolTerminate` at `0x180063acf`

## pseudocode

```c
void __fastcall CDirMonitor::~CDirMonitor(CDirMonitor *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  ThreadPoolTerminate();
  CLKRHashTable::~CLKRHashTable(this);
}

```

## disassembly

```asm
0x180063abc  push    rbx
0x180063abe  sub     rsp, 20h
0x180063ac2  mov     rbx, rcx
0x180063ac5  add     rcx, 48h ; 'H'; lpCriticalSection
0x180063ac9  call    cs:__imp_DeleteCriticalSection
0x180063acf  call    cs:__imp_?ThreadPoolTerminate@@YAJXZ; ThreadPoolTerminate(void)
0x180063ad5  mov     rcx, rbx
0x180063ad8  add     rsp, 20h
0x180063adc  pop     rbx
0x180063add  jmp     cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
```
