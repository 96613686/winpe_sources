# __GSHandlerCheck

- ea: `0x140002cac`
- end: `0x140002cc9`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002cd0`

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
0x140002cac  sub     rsp, 28h
0x140002cb0  mov     r8, [r9+38h]
0x140002cb4  mov     rcx, rdx
0x140002cb7  mov     rdx, r9
0x140002cba  call    __GSHandlerCheckCommon
0x140002cbf  mov     eax, 1
0x140002cc4  add     rsp, 28h
0x140002cc8  retn
```
