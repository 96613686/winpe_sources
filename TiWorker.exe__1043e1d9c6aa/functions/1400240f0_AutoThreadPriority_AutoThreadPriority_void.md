# AutoThreadPriority::~AutoThreadPriority(void)

- ea: `0x1400240f0`
- end: `0x140024118`
- name: `??1AutoThreadPriority@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e550`
- `0x14001344c`

## callees

- `0x1400064e8`
- `0x140024cf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140024111`

## pseudocode

```c
void __fastcall AutoThreadPriority::~AutoThreadPriority(struct _RTL_CRITICAL_SECTION *this)
{
  AutoThreadPriority::SetPriority(this, 0);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&this[1].LockCount);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1400240f0  push    rbx
0x1400240f2  sub     rsp, 20h
0x1400240f6  xor     edx, edx
0x1400240f8  mov     rbx, rcx
0x1400240fb  call    ?SetPriority@AutoThreadPriority@@QEAAXW4PriorityType@1@@Z; AutoThreadPriority::SetPriority(AutoThreadPriority::PriorityType)
0x140024100  lea     rcx, [rbx+30h]
0x140024104  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140024109  mov     rcx, rbx
0x14002410c  add     rsp, 20h
0x140024110  pop     rbx
0x140024111  jmp     cs:__imp_DeleteCriticalSection
```
