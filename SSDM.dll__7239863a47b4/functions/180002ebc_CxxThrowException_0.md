# _CxxThrowException_0

- ea: `0x180002ebc`
- end: `0x180002ec2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180002bc8`
- `0x180002bf0`
- `0x180002c18`
- `0x180002c44`
- `0x180008cb8`
- `0x180008ea0`
- `0x180008ff0`
- `0x180009840`
- `0x18000bba4`
- `0x18000ee26`
- `0x18000ee5c`
- `0x18000ee79`
- `0x18000f1cc`
- `0x18000f250`
- `0x18000f276`
- `0x18000f2d3`
- `0x18000f2f9`
- `0x18000f711`
- `0x18000f83d`
- `0x18000f866`
- `0x18000f88c`
- `0x18000f994`
- `0x18000f9ba`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180002ebc`

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
0x180002ebc  jmp     cs:__imp__CxxThrowException
```
