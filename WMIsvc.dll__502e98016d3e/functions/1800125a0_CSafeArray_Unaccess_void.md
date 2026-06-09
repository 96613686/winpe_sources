# CSafeArray::Unaccess(void)

- ea: `0x1800125a0`
- end: `0x1800125ab`
- name: `?Unaccess@CSafeArray@@QEAAJXZ`
- size: `11`
- prototype: `__int64 __fastcall(CSafeArray *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800125a4`

## pseudocode

```c
HRESULT __fastcall CSafeArray::Unaccess(SAFEARRAY **this)
{
  return SafeArrayUnaccessData(this[4]);
}

```

## disassembly

```asm
0x1800125a0  mov     rcx, [rcx+20h]
0x1800125a4  jmp     cs:__imp_SafeArrayUnaccessData
```
