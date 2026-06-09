# __GSHandlerCheck

- ea: `0x140001ce0`
- end: `0x140001cfd`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001d04`

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
0x140001ce0  sub     rsp, 28h
0x140001ce4  mov     r8, [r9+38h]
0x140001ce8  mov     rcx, rdx
0x140001ceb  mov     rdx, r9
0x140001cee  call    __GSHandlerCheckCommon
0x140001cf3  mov     eax, 1
0x140001cf8  add     rsp, 28h
0x140001cfc  retn
```
