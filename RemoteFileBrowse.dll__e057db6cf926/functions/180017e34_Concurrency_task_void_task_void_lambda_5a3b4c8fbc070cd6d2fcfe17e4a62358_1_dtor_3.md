# _Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$3

- ea: `0x180017e34`
- end: `0x180017e60`
- name: `_Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$3`
- size: `44`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000ffdc`
- `0x180017e34`

## pseudocode

```c
void __fastcall Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 208) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 208) &= ~1u;
    Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack((char **)(a2 + 56));
  }
}

```

## disassembly

```asm
0x180017e34  push    rbp
0x180017e36  sub     rsp, 20h
0x180017e3a  mov     rbp, rdx
0x180017e3d  mov     eax, [rbp+0D0h]
0x180017e43  and     eax, 1
0x180017e46  test    eax, eax
0x180017e48  jz      short loc_180017E5A
0x180017e4a  and     dword ptr [rbp+0D0h], 0FFFFFFFEh
0x180017e51  lea     rcx, [rbp+38h]; this
0x180017e55  call    ??1_TaskCreationCallstack@details@Concurrency@@QEAA@XZ; Concurrency::details::_TaskCreationCallstack::~_TaskCreationCallstack(void)
0x180017e5a  add     rsp, 20h
0x180017e5e  pop     rbp
0x180017e5f  retn
```
