# _CxxThrowException_0

- ea: `0x180001dcc`
- end: `0x180001dd2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180001658`
- `0x180001680`
- `0x1800016ac`
- `0x180008c50`
- `0x180009b80`
- `0x180010bd6`
- `0x180010cde`
- `0x180010d56`
- `0x180010dda`
- `0x180010e00`
- `0x180010e26`
- `0x180010e8b`
- `0x180010eb1`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001dcc`

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
0x180001dcc  jmp     cs:__imp__CxxThrowException
```
