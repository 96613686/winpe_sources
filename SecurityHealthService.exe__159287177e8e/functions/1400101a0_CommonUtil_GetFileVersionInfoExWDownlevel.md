# CommonUtil::GetFileVersionInfoExWDownlevel

- ea: `0x1400101a0`
- end: `0x1400101ca`
- name: `CommonUtil::GetFileVersionInfoExWDownlevel`
- size: `42`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::GetFileVersionInfoExWDownlevel(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  return off_14001B020(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1400101a0  sub     rsp, 38h
0x1400101a4  mov     eax, r9d
0x1400101a7  mov     r10d, r8d
0x1400101aa  mov     rcx, rdx
0x1400101ad  mov     r9, [rsp+38h+arg_20]
0x1400101b2  mov     r8d, eax
0x1400101b5  mov     edx, r10d
0x1400101b8  mov     rax, cs:off_14001B020
0x1400101bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101c4  nop
0x1400101c5  add     rsp, 38h
0x1400101c9  retn
```
