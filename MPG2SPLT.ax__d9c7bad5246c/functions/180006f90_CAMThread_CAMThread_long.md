# CAMThread::CAMThread(long *)

- ea: `0x180006f90`
- end: `0x180006fdc`
- name: `??0CAMThread@@QEAA@PEAJ@Z`
- size: `76`
- prototype: `CAMThread *__fastcall(CAMThread *__hidden this, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b784`
- `0x18001ac30`

## callees

- `0x180006f44`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006fbb`
- `KERNEL32!InitializeCriticalSection` at `0x180006fc5`
- `KERNEL32!InitializeCriticalSection` at `0x180006fbb`
- `KERNEL32!InitializeCriticalSection` at `0x180006fc5`

## pseudocode

```c
CAMThread *__fastcall CAMThread::CAMThread(CAMThread *this, int *a2)
{
  CAMThread *result; // rax

  CAMEvent::CAMEvent((CAMThread *)((char *)this + 8), 1, 0);
  CAMEvent::CAMEvent((CAMThread *)((char *)this + 16), 0, 0);
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 1);
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 2);
  result = this;
  *((_QWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180006f90  push    rbx
0x180006f92  sub     rsp, 20h
0x180006f96  xor     r8d, r8d; int *
0x180006f99  mov     rbx, rcx
0x180006f9c  add     rcx, 8; this
0x180006fa0  lea     edx, [r8+1]; int
0x180006fa4  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x180006fa9  lea     rcx, [rbx+10h]; this
0x180006fad  xor     r8d, r8d; int *
0x180006fb0  xor     edx, edx; int
0x180006fb2  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x180006fb7  lea     rcx, [rbx+28h]; lpCriticalSection
0x180006fbb  call    cs:__imp_InitializeCriticalSection
0x180006fc1  lea     rcx, [rbx+50h]; lpCriticalSection
0x180006fc5  call    cs:__imp_InitializeCriticalSection
0x180006fcb  mov     rax, rbx
0x180006fce  mov     qword ptr [rbx+20h], 0
0x180006fd6  add     rsp, 20h
0x180006fda  pop     rbx
0x180006fdb  retn
```
