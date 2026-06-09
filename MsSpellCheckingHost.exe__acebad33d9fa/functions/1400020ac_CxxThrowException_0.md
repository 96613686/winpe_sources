# _CxxThrowException_0

- ea: `0x1400020ac`
- end: `0x1400020b2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x140001758`
- `0x140001780`
- `0x1400017a8`
- `0x1400017d4`
- `0x140003b88`
- `0x14000d270`
- `0x14000e080`
- `0x1400120b8`
- `0x14001216e`
- `0x140012194`
- `0x1400121be`
- `0x1400121e7`
- `0x14001230a`
- `0x140012330`
- `0x1400124dc`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1400020ac`

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
0x1400020ac  jmp     cs:__imp__CxxThrowException
```
