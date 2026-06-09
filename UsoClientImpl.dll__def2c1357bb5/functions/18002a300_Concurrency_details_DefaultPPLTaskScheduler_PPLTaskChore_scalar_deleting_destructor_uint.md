# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::`scalar deleting destructor'(uint)

- ea: `0x18002a300`
- end: `0x18002a334`
- name: `??_G_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@QEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18002a3cc`

## callees

- `0x18002a300`
- `0x180056a08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a311`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a311`

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
0x18002a300  push    rbx
0x18002a302  sub     rsp, 20h
0x18002a306  mov     rbx, rcx
0x18002a309  mov     rcx, [rcx]; pwk
0x18002a30c  test    rcx, rcx
0x18002a30f  jz      short loc_18002A31E
0x18002a311  call    cs:__imp_CloseThreadpoolWork
0x18002a317  mov     qword ptr [rbx], 0
0x18002a31e  mov     edx, 28h ; '('
0x18002a323  mov     rcx, rbx; Block
0x18002a326  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002a32b  mov     rax, rbx
0x18002a32e  add     rsp, 20h
0x18002a332  pop     rbx
0x18002a333  retn
```
