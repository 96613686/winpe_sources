# CDeleteMe<ushort>::~CDeleteMe<ushort>(void)

- ea: `0x18000ca20`
- end: `0x18000ca33`
- name: `??1?$CDeleteMe@G@@QEAA@XZ`
- size: `19`
- prototype: ``
- caller_count: `22`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003b94`
- `0x1800150ec`
- `0x180015560`
- `0x180015a00`
- `0x180015d9c`
- `0x180015ff0`
- `0x1800186bc`
- `0x180018850`
- `0x18001d81a`
- `0x18001e117`
- `0x18001e862`
- `0x18001e874`
- `0x18001e886`
- `0x18001e8aa`
- `0x18001e8bc`
- `0x18001e9e5`
- `0x18001eadb`
- `0x18001eaff`
- `0x18001eb11`
- `0x18001eb35`
- `0x18001ec18`
- `0x18001ed47`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ca27`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ca27`

## pseudocode

```c
int __fastcall CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>(void **a1)
{
  return CWin32DefaultArena::WbemMemFree(*a1);
}

```

## disassembly

```asm
0x18000ca20  sub     rsp, 28h
0x18000ca24  mov     rcx, [rcx]
0x18000ca27  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000ca2d  nop
0x18000ca2e  add     rsp, 28h
0x18000ca32  retn
```
