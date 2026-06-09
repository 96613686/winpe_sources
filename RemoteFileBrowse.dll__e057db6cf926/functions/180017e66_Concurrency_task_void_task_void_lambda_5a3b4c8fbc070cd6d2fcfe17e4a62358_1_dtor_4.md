# _Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$4

- ea: `0x180017e66`
- end: `0x180017e92`
- name: `_Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$4`
- size: `44`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000ffdc`
- `0x180017e66`

## pseudocode

```c
void __fastcall Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 208) & 2) != 0 )
  {
    *(_DWORD *)(a2 + 208) &= ~2u;
    Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack((char **)(a2 + 88));
  }
}

```

## disassembly

```asm
0x180017e66  push    rbp
0x180017e68  sub     rsp, 20h
0x180017e6c  mov     rbp, rdx
0x180017e6f  mov     eax, [rbp+0D0h]
0x180017e75  and     eax, 2
0x180017e78  test    eax, eax
0x180017e7a  jz      short loc_180017E8C
0x180017e7c  and     dword ptr [rbp+0D0h], 0FFFFFFFDh
0x180017e83  lea     rcx, [rbp+58h]; this
0x180017e87  call    ??1_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack(void)
0x180017e8c  add     rsp, 20h
0x180017e90  pop     rbp
0x180017e91  retn
```
