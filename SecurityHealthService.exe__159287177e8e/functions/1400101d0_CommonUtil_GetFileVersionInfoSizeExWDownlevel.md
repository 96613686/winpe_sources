# CommonUtil::GetFileVersionInfoSizeExWDownlevel

- ea: `0x1400101d0`
- end: `0x1400101ec`
- name: `CommonUtil::GetFileVersionInfoSizeExWDownlevel`
- size: `28`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::GetFileVersionInfoSizeExWDownlevel(__int64 a1, __int64 a2, __int64 a3)
{
  return off_14001B010(a2, a3);
}

```

## disassembly

```asm
0x1400101d0  sub     rsp, 28h
0x1400101d4  mov     rcx, rdx
0x1400101d7  mov     rdx, r8
0x1400101da  mov     rax, cs:off_14001B010
0x1400101e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101e6  nop
0x1400101e7  add     rsp, 28h
0x1400101eb  retn
```
