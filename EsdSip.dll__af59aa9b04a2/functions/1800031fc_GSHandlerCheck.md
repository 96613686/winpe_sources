# __GSHandlerCheck

- ea: `0x1800031fc`
- end: `0x180003219`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003220`

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
0x1800031fc  sub     rsp, 28h
0x180003200  mov     r8, [r9+38h]
0x180003204  mov     rcx, rdx
0x180003207  mov     rdx, r9
0x18000320a  call    __GSHandlerCheckCommon
0x18000320f  mov     eax, 1
0x180003214  add     rsp, 28h
0x180003218  retn
```
