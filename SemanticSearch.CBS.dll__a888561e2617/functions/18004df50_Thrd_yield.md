# _Thrd_yield

- ea: `0x18004df50`
- end: `0x18004df57`
- name: `_Thrd_yield`
- size: `7`
- prototype: `void __cdecl()`
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x18001efe0`
- `0x180054750`
- `0x180054b70`
- `0x180055d70`
- `0x180056180`
- `0x180056590`
- `0x180056980`
- `0x180056d90`
- `0x180057180`
- `0x180057590`
- `0x1800579e0`
- `0x180057e10`
- `0x180059df0`
- `0x18005a410`
- `0x18005a820`
- `0x18005ac10`
- `0x18005b020`
- `0x18005b450`
- `0x18005b870`
- `0x18005c630`
- `0x18005ca50`
- `0x18005ce70`
- `0x18005d2c0`
- `0x18005d600`
- `0x18005d940`
- `0x18005dd60`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x18004df50`

## pseudocode

```c
// attributes: thunk
void __cdecl Thrd_yield()
{
  SwitchToThread();
}

```

## disassembly

```asm
0x18004df50  jmp     cs:__imp_SwitchToThread
```
