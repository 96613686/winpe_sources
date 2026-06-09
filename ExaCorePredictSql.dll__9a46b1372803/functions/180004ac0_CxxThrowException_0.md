# _CxxThrowException_0

- ea: `0x180004ac0`
- end: `0x180004ac6`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b10`
- `0x180002030`
- `0x1800024e0`
- `0x1800026b0`
- `0x180002a00`
- `0x180004b72`
- `0x180004ddf`

## import_xrefs

- `VCRUNTIME140!_CxxThrowException` at `0x180004ac0`

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
0x180004ac0  jmp     cs:__imp__CxxThrowException
```
