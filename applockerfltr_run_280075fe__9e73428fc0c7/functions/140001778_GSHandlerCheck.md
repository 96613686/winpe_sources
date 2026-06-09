# __GSHandlerCheck

- ea: `0x140001778`
- end: `0x140001796`
- name: `__GSHandlerCheck`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000179c`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _GSHandlerCheckCommon(a2, a4);
  return 1;
}

```

## disassembly

```asm
0x140001778  sub     rsp, 28h
0x14000177c  mov     r8, [r9+38h]
0x140001780  mov     rcx, rdx
0x140001783  mov     rdx, r9
0x140001786  call    __GSHandlerCheckCommon
0x14000178b  mov     eax, 1
0x140001790  add     rsp, 28h
0x140001794  retn
```
