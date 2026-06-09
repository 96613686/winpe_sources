# llrintf

- ea: `0x180078df6`
- end: `0x180078dfc`
- name: `llrintf`
- size: `6`
- prototype: `__int64 __cdecl(float X)`
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x18006b9c0`
- `0x18006ba40`
- `0x18006bac0`
- `0x18006bb40`
- `0x18006bbc0`
- `0x18006bc40`
- `0x18006bcc0`
- `0x18006bd50`
- `0x18006bde0`
- `0x18006be70`
- `0x18006bf00`
- `0x18006bf90`
- `0x18006c020`
- `0x18006c0b0`
- `0x18006c140`
- `0x18006c1d0`
- `0x18006c260`
- `0x18006c2f0`
- `0x18006c380`
- `0x18006c410`
- `0x18006c690`
- `0x18006c7f0`
- `0x18006ef00`
- `0x18006f090`
- `0x18006f9f0`
- `0x18006fb70`
- `0x180074f40`
- `0x180075f90`
- `0x180077250`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!llrintf` at `0x180078df6`

## pseudocode

```c
// attributes: thunk
__int64 __cdecl llrintf(float X)
{
  return __imp_llrintf(X);
}

```

## disassembly

```asm
0x180078df6  jmp     cs:__imp_llrintf
```
