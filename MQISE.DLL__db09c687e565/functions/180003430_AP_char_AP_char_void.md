# AP<char>::~AP<char>(void)

- ea: `0x180003430`
- end: `0x180003443`
- name: `??1?$AP@D@@QEAA@XZ`
- size: `19`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fac0`
- `0x18000fad2`
- `0x18000fae4`
- `0x18000fb44`

## import_xrefs

- `msvcrt!free` at `0x180003437`
- `msvcrt!free` at `0x180003437`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AP<char>::~AP<char>(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180003430  sub     rsp, 28h
0x180003434  mov     rcx, [rcx]; Block
0x180003437  call    cs:__imp_free
0x18000343d  nop
0x18000343e  add     rsp, 28h
0x180003442  retn
```
