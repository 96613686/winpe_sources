# _CSession::_HandleReaderAction_::_1_::dtor$0

- ea: `0x18001ee26`
- end: `0x18001ee32`
- name: `_CSession::_HandleReaderAction_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c7b0`

## pseudocode

```c
__int64 __fastcall CSession::_HandleReaderAction_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WppTraceUnwinder__lambda_1684c019d9c653e113c18e280f091e04____::_WppTraceUnwinder__lambda_1684c019d9c653e113c18e280f091e04____(a2 + 56);
}

```

## disassembly

```asm
0x18001ee26  lea     rcx, [rdx+38h]
0x18001ee2d  jmp     WppTraceUnwinder__lambda_1684c019d9c653e113c18e280f091e04_______WppTraceUnwinder__lambda_1684c019d9c653e113c18e280f091e04____
```
