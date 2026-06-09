# `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))

- ea: `0x180001b60`
- end: `0x180001b65`
- name: `??_L@YAXPEAX_K1P6AX0@Z2@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64, unsigned __int64, void (*)(void *), void (*)(void *))`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c5c`
- `0x180007f40`

## callees

- `0x180001b6c`

## pseudocode

```c
// attributes: thunk
void __fastcall `eh vector constructor iterator'(
        void *a1,
        unsigned __int64 a2,
        int a3,
        void (*a4)(void *),
        void (*a5)(void *))
{
  ??_L@YAXPEAX_KHP6AX0@Z2@Z(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180001b60  jmp     ??_L@YAXPEAX_KHP6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,int,void (*)(void *),void (*)(void *))
```
