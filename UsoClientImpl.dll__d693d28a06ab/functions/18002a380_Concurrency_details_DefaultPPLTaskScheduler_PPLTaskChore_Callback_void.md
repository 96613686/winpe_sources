# Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(void *)

- ea: `0x18002a380`
- end: `0x18002a3c3`
- name: `?_Callback@_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@CAXPEAX@Z`
- size: `67`
- prototype: `void __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x18002a380`
- `0x180056a08`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a3a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a3a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback(PTP_WORK *Block)
{
  ((void (__fastcall *)(PTP_WORK))Block[3])(Block[4]);
  if ( *Block )
  {
    CloseThreadpoolWork(*Block);
    *Block = 0;
  }
  operator delete(Block);
}

```

## disassembly

```asm
0x18002a380  push    rbx
0x18002a382  sub     rsp, 20h
0x18002a386  mov     rbx, rcx
0x18002a389  mov     [rsp+28h+arg_0], rcx
0x18002a38e  mov     rcx, [rcx+20h]
0x18002a392  mov     rax, [rbx+18h]
0x18002a396  call    _guard_dispatch_icall
0x18002a39b  nop
0x18002a39c  mov     rcx, [rbx]; pwk
0x18002a39f  test    rcx, rcx
0x18002a3a2  jz      short loc_18002A3B1
0x18002a3a4  call    cs:__imp_CloseThreadpoolWork
0x18002a3aa  mov     qword ptr [rbx], 0
0x18002a3b1  mov     edx, 28h ; '('
0x18002a3b6  mov     rcx, rbx; Block
0x18002a3b9  add     rsp, 20h
0x18002a3bd  pop     rbx
0x18002a3be  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
