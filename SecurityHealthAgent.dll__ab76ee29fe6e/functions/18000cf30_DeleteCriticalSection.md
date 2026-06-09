# DeleteCriticalSection

- ea: `0x18000cf30`
- end: `0x18000cf37`
- name: `DeleteCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x180019150`
- `0x18001ca00`
- `0x18001cac0`
- `0x18002b580`
- `0x18002bbe0`
- `0x18002bf40`
- `0x18008fc10`
- `0x18008fc60`
- `0x1800901e8`
- `0x1800903e4`
- `0x1800ad720`
- `0x1800ad8c0`
- `0x1800af390`
- `0x1800af7d0`
- `0x1800b3016`
- `0x1800b36ba`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000cf30`

## pseudocode

```c
// attributes: thunk
void __stdcall DeleteCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  __imp_DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000cf30  jmp     cs:__imp_DeleteCriticalSection
```
