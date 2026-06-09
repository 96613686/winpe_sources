# StartAndWaitForService

- ea: `0x1800059a0`
- end: `0x1800059cd`
- name: `StartAndWaitForService`
- size: `45`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800059e0`

## pseudocode

```c
__int64 __fastcall StartAndWaitForService(__int64 a1, __int64 a2, unsigned int a3, int a4, __int64 a5, __int64 a6)
{
  return StartAndWaitForServiceForUser(a1, a2, 0, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x1800059a0  sub     rsp, 48h
0x1800059a4  mov     rax, [rsp+48h+arg_28]
0x1800059a9  mov     [rsp+48h+var_18], rax
0x1800059ae  mov     rax, [rsp+48h+arg_20]
0x1800059b3  mov     [rsp+48h+var_20], rax
0x1800059b8  mov     [rsp+48h+var_28], r9d
0x1800059bd  mov     r9d, r8d
0x1800059c0  xor     r8d, r8d
0x1800059c3  call    StartAndWaitForServiceForUser
0x1800059c8  add     rsp, 48h
0x1800059cc  retn
```
