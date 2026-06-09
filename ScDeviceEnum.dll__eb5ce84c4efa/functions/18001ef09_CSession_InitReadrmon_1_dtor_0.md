# _CSession::_InitReadrmon_::_1_::dtor$0

- ea: `0x18001ef09`
- end: `0x18001ef15`
- name: `_CSession::_InitReadrmon_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c8ac`

## pseudocode

```c
__int64 __fastcall CSession::_InitReadrmon_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WppTraceUnwinder__lambda_c31ae6585624ce606d045e361ca8fd8c____::_WppTraceUnwinder__lambda_c31ae6585624ce606d045e361ca8fd8c____(a2 + 64);
}

```

## disassembly

```asm
0x18001ef09  lea     rcx, [rdx+40h]
0x18001ef10  jmp     WppTraceUnwinder__lambda_c31ae6585624ce606d045e361ca8fd8c_______WppTraceUnwinder__lambda_c31ae6585624ce606d045e361ca8fd8c____
```
