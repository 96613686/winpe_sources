# Concurrency::details::_Task_impl_base::_Cancel(bool)

- ea: `0x18001c110`
- end: `0x18001c134`
- name: `?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z`
- size: `36`
- prototype: `__int64 __fastcall(Concurrency::details::_Task_impl_base *this, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001d090`
- `0x18001d84c`
- `0x18001d904`
- `0x18001e780`
- `0x18001e800`
- `0x18002425f`
- `0x1800242e2`

## callees

- `0x180025010`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl_base::_Cancel(
        Concurrency::details::_Task_impl_base *this,
        __int64 a2)
{
  return (*(__int64 (__fastcall **)(Concurrency::details::_Task_impl_base *, __int64, _QWORD, _QWORD, char *))(*(_QWORD *)this + 8LL))(
           this,
           a2,
           0,
           0,
           (char *)this + 16);
}

```

## disassembly

```asm
0x18001c110  sub     rsp, 38h
0x18001c114  mov     rax, [rcx]
0x18001c117  lea     r8, [rcx+10h]
0x18001c11b  mov     [rsp+38h+var_18], r8
0x18001c120  xor     r9d, r9d
0x18001c123  xor     r8d, r8d
0x18001c126  mov     rax, [rax+8]
0x18001c12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c12f  add     rsp, 38h
0x18001c133  retn
```
