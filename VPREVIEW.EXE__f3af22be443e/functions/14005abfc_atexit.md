# atexit

- ea: `0x14005abfc`
- end: `0x14005ac13`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `54`
- callee_count: `1`
- tags: ``

## callers

- `0x140001120`
- `0x140001130`
- `0x1400011a0`
- `0x1400011c0`
- `0x1400011e0`
- `0x140001200`
- `0x140001220`
- `0x140001260`
- `0x1400012b0`
- `0x1400012d0`
- `0x1400012f0`
- `0x140001310`
- `0x140001320`
- `0x1400014c0`
- `0x140001530`
- `0x140001580`
- `0x140001590`
- `0x1400015a0`
- `0x1400015b0`
- `0x1400015c0`
- `0x1400015d0`
- `0x1400015e0`
- `0x140001670`
- `0x1400016a0`
- `0x1400016b0`
- `0x1400016e0`
- `0x1400016f0`
- `0x140001780`
- `0x140001790`
- `0x1400017a0`
- `0x140001850`
- `0x140001890`
- `0x1400018b0`
- `0x140001960`
- `0x1400019d0`
- `0x140001a00`
- `0x140001a10`
- `0x140001a20`
- `0x140001a30`
- `0x140001a40`
- `0x140001a50`
- `0x140001a60`
- `0x140001a70`
- `0x140001a80`
- `0x140001aa0`
- `0x140001ad0`
- `0x14000332c`
- `0x14001f6cc`
- `0x140021d88`
- `0x14002a93c`

## callees

- `0x14005abc0`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x14005abfc  sub     rsp, 28h
0x14005ac00  call    _onexit
0x14005ac05  neg     rax
0x14005ac08  sbb     eax, eax
0x14005ac0a  neg     eax
0x14005ac0c  dec     eax
0x14005ac0e  add     rsp, 28h
0x14005ac12  retn
```
