# `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))

- ea: `0x18000154c`
- end: `0x180001551`
- name: `??_M@YAXPEAX_K1P6AX0@Z@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64, unsigned __int64, void (*)(void *))`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002348`
- `0x1800024ac`
- `0x180007c5c`
- `0x180007f40`

## callees

- `0x180001558`

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
0x18000154c  jmp     ??_M@YAXPEAX_KHP6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,int,void (*)(void *))
```
