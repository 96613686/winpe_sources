# _CxxThrowException_0

- ea: `0x140001dbc`
- end: `0x140001dc2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140001658`
- `0x140001680`
- `0x1400016ac`
- `0x14000596c`
- `0x140006080`
- `0x140006210`
- `0x1400068d0`
- `0x140009558`
- `0x140009856`
- `0x140009c07`
- `0x140009c6c`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x140001dbc`

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
0x140001dbc  jmp     cs:__imp__CxxThrowException
```
