# `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))

- ea: `0x140002228`
- end: `0x14000222d`
- name: `??_M@YAXPEAX_K1P6AX0@Z@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64, int, void (*)(void *))`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140009c08`
- `0x140009ecc`
- `0x14000ae7f`
- `0x14000aeaf`

## callees

- `0x140002234`

## pseudocode

```c
// attributes: thunk
void __fastcall `eh vector destructor iterator'(void *a1, unsigned __int64 a2, int a3, void (*a4)(void *))
{
  ??_M@YAXPEAX_KHP6AX0@Z@Z(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002228  jmp     ??_M@YAXPEAX_KHP6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,int,void (*)(void *))
```
