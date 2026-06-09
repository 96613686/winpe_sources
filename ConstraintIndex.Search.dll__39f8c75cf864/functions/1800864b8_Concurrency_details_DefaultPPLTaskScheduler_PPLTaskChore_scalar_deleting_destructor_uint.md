# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x1800864b8`
- end: `0x1800864e7`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180082770`
- `0x180093884`

## callees

- `0x1800864b8`
- `0x1800d9660`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800864c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800864c9`

## pseudocode

```c
Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(
        struct _TP_WORK **this)
{
  struct _TP_WORK *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    CloseThreadpoolWork(v2);
    *this = 0;
  }
  operator delete(this);
  return (Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *)this;
}

```

## disassembly

```asm
0x1800864b8  push    rbx
0x1800864ba  sub     rsp, 20h
0x1800864be  mov     rbx, rcx
0x1800864c1  mov     rcx, [rcx]; pwk
0x1800864c4  test    rcx, rcx
0x1800864c7  jz      short loc_1800864D6
0x1800864c9  call    cs:__imp_CloseThreadpoolWork
0x1800864cf  mov     qword ptr [rbx], 0
0x1800864d6  mov     rcx, rbx; Block
0x1800864d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800864de  mov     rax, rbx
0x1800864e1  add     rsp, 20h
0x1800864e5  pop     rbx
0x1800864e6  retn
```
