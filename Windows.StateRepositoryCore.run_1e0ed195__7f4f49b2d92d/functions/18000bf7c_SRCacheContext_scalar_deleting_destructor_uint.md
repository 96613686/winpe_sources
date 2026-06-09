# SRCacheContext::`scalar deleting destructor'(uint)

- ea: `0x18000bf7c`
- end: `0x18000bfa3`
- name: `??_GSRCacheContext@@QEAAPEAXI@Z`
- size: `39`
- prototype: `void *__fastcall(SRCacheContext *__hidden this, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c05c`
- `0x18000c430`
- `0x18000c950`
- `0x18000ca80`
- `0x18000caa0`
- `0x18000cb60`
- `0x18000d090`
- `0x18000d170`

## callees

- `0x1800022a0`
- `0x18000be00`

## pseudocode

```c
HKEY *__fastcall SRCacheContext::`scalar deleting destructor'(HKEY *this)
{
  Common::AutoHandleCloseHKEY<HKEY__ *>(*this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000bf7c  push    rbx
0x18000bf7e  sub     rsp, 20h
0x18000bf82  mov     rbx, rcx
0x18000bf85  mov     rcx, [rcx]
0x18000bf88  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000bf8d  mov     edx, 8; unsigned __int64
0x18000bf92  mov     rcx, rbx; void *
0x18000bf95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bf9a  mov     rax, rbx
0x18000bf9d  add     rsp, 20h
0x18000bfa1  pop     rbx
0x18000bfa2  retn
```
