# _CxxThrowException_0

- ea: `0x1400029d3`
- end: `0x1400029d9`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x140002754`
- `0x1400027b0`
- `0x14000cec0`
- `0x14000f2ec`
- `0x14000f460`
- `0x14000f490`
- `0x14000f4d0`
- `0x14000f510`
- `0x14000f6b4`
- `0x14000fe40`
- `0x1400136c3`
- `0x1400136e9`
- `0x14001370f`
- `0x140013774`
- `0x1400137a2`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1400029d3`

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
0x1400029d3  jmp     cs:__imp__CxxThrowException
```
