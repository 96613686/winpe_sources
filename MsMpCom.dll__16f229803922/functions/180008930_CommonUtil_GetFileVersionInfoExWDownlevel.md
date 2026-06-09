# CommonUtil::GetFileVersionInfoExWDownlevel

- ea: `0x180008930`
- end: `0x18000895a`
- name: `CommonUtil::GetFileVersionInfoExWDownlevel`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CommonUtil::GetFileVersionInfoExWDownlevel(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  return ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64))off_180012068)(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180008930  sub     rsp, 38h
0x180008934  mov     eax, r9d
0x180008937  mov     r10d, r8d
0x18000893a  mov     rcx, rdx
0x18000893d  mov     r9, [rsp+38h+arg_20]
0x180008942  mov     r8d, eax
0x180008945  mov     edx, r10d
0x180008948  mov     rax, cs:off_180012068
0x18000894f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008954  nop
0x180008955  add     rsp, 38h
0x180008959  retn
```
