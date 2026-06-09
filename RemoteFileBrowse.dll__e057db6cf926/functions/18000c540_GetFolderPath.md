# GetFolderPath

- ea: `0x18000c540`
- end: `0x18000c591`
- name: `GetFolderPath`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b640`

## pseudocode

```c
__int64 __fastcall GetFolderPath(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        int a7)
{
  bool v8; // [rsp+50h] [rbp-28h]

  return ShowDialog(a1, a2, a3, 0, a4, a5, 0, 0, 0, 1u, v8, a6, a7);
}

```

## disassembly

```asm
0x18000c540  mov     r11, rsp
0x18000c543  sub     rsp, 78h
0x18000c547  mov     eax, [rsp+78h+arg_30]
0x18000c54e  mov     [rsp+78h+var_18], eax; int
0x18000c552  mov     rax, [rsp+78h+arg_28]
0x18000c55a  mov     [r11-20h], rax
0x18000c55e  xor     eax, eax
0x18000c560  mov     [rsp+78h+var_30], 1; unsigned int
0x18000c568  mov     [r11-38h], rax
0x18000c56c  mov     [r11-40h], rax
0x18000c570  mov     [r11-48h], rax
0x18000c574  mov     rax, [rsp+78h+arg_20]
0x18000c57c  mov     [r11-50h], rax
0x18000c580  mov     [r11-58h], r9
0x18000c584  xor     r9d, r9d; unsigned __int16 *
0x18000c587  call    ?ShowDialog@@YAJPEAUHWND__@@PEBG1111111K_NPEAGH@Z; ShowDialog(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,bool,ushort *,int)
0x18000c58c  add     rsp, 78h
0x18000c590  retn
```
