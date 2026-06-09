# __GSHandlerCheck

- ea: `0x180002588`
- end: `0x1800025a5`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800025ac`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _GSHandlerCheckCommon(a2, a4, *(_QWORD *)(a4 + 56));
  return 1;
}

```

## disassembly

```asm
0x180002588  sub     rsp, 28h
0x18000258c  mov     r8, [r9+38h]
0x180002590  mov     rcx, rdx
0x180002593  mov     rdx, r9
0x180002596  call    __GSHandlerCheckCommon
0x18000259b  mov     eax, 1
0x1800025a0  add     rsp, 28h
0x1800025a4  retn
```
