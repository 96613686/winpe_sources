# _CxxThrowException_0

- ea: `0x18000895c`
- end: `0x180008962`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `90`
- callee_count: `0`
- tags: ``

## callers

- `0x180001760`
- `0x180001afc`
- `0x180001b78`
- `0x180001c48`
- `0x180002220`
- `0x180002320`
- `0x18000266c`
- `0x180003490`
- `0x180003818`
- `0x180003894`
- `0x180003b90`
- `0x180003f40`
- `0x180004120`
- `0x180004260`
- `0x180004430`
- `0x180004a20`
- `0x180004b20`
- `0x180004d40`
- `0x180004dbc`
- `0x180004fc0`
- `0x18000515c`
- `0x180005328`
- `0x18000536c`
- `0x180005558`
- `0x180005b24`
- `0x180005c60`
- `0x180005ce4`
- `0x180005d60`
- `0x180005de4`
- `0x180005e60`
- `0x180005edc`
- `0x180005fbc`
- `0x180006068`
- `0x1800060f8`
- `0x18000617c`
- `0x180006208`
- `0x1800063f8`
- `0x180006474`
- `0x180006528`
- `0x180006688`
- `0x1800067e8`
- `0x180006af8`
- `0x1800079b4`
- `0x180008088`
- `0x180008130`
- `0x180008208`
- `0x180008230`
- `0x18000825c`
- `0x18000ab20`
- `0x18000af90`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000895c`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException_0(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x18000895c  jmp     cs:__imp__CxxThrowException
```
