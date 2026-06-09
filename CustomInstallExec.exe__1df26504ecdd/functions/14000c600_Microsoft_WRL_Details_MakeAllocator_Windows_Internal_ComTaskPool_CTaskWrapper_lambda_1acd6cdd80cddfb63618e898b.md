# Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____

- ea: `0x14000c600`
- end: `0x14000c616`
- name: `Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000becc`

## callees

- `0x140003708`
- `0x14000c600`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_1acd6cdd80cddfb63618e898b2901780_____(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x14000c600  sub     rsp, 28h
0x14000c604  mov     rcx, [rcx]; Block
0x14000c607  test    rcx, rcx
0x14000c60a  jz      short loc_14000C611
0x14000c60c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c611  add     rsp, 28h
0x14000c615  retn
```
