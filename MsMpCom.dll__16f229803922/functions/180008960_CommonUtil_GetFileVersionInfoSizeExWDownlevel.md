# CommonUtil::GetFileVersionInfoSizeExWDownlevel

- ea: `0x180008960`
- end: `0x18000897c`
- name: `CommonUtil::GetFileVersionInfoSizeExWDownlevel`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CommonUtil::GetFileVersionInfoSizeExWDownlevel(__int64 a1, __int64 a2, __int64 a3)
{
  return ((__int64 (__fastcall *)(__int64, __int64))off_180012058[0])(a2, a3);
}

```

## disassembly

```asm
0x180008960  sub     rsp, 28h
0x180008964  mov     rcx, rdx
0x180008967  mov     rdx, r8
0x18000896a  mov     rax, cs:off_180012058
0x180008971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008976  nop
0x180008977  add     rsp, 28h
0x18000897b  retn
```
