# CDfsShell::ReplacePage(uint,int (*)(_PSP *,__int64),__int64)

- ea: `0x180006330`
- end: `0x180006336`
- name: `?ReplacePage@CDfsShell@@UEAAJIP6AHPEAU_PSP@@_J@Z1@Z`
- size: `6`
- prototype: `__int64 __fastcall(CDfsShell *__hidden this, unsigned int, int (*)(struct _PSP *, __int64), __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CDfsShell::ReplacePage(CDfsShell *this, __int64 a2, int (*a3)(struct _PSP *, __int64))
{
  return 2147500037LL;
}

```

## disassembly

```asm
0x180006330  mov     eax, 80004005h
0x180006335  retn
```
