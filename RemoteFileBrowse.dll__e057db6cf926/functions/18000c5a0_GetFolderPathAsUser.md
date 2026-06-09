# GetFolderPathAsUser

- ea: `0x18000c5a0`
- end: `0x18000c623`
- name: `GetFolderPathAsUser`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b640`
- `0x18000c5a0`

## pseudocode

```c
__int64 __fastcall GetFolderPathAsUser(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        int a10)
{
  bool v11; // [rsp+50h] [rbp-28h]

  if ( a6 && a7 && a8 )
    return ShowDialog(a1, a2, a3, 0, a4, a5, a6, a7, a8, 1u, v11, a9, a10);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x18000c5a0  push    rbx
0x18000c5a2  sub     rsp, 70h
0x18000c5a6  mov     rbx, [rsp+78h+arg_28]
0x18000c5ae  test    rbx, rbx
0x18000c5b1  jz      short loc_18000C618
0x18000c5b3  mov     r10, [rsp+78h+arg_30]
0x18000c5bb  test    r10, r10
0x18000c5be  jz      short loc_18000C618
0x18000c5c0  mov     r11, [rsp+78h+arg_38]
0x18000c5c8  test    r11, r11
0x18000c5cb  jz      short loc_18000C618
0x18000c5cd  mov     eax, [rsp+78h+arg_48]
0x18000c5d4  mov     [rsp+78h+var_18], eax; int
0x18000c5d8  mov     rax, [rsp+78h+arg_40]
0x18000c5e0  mov     [rsp+78h+var_20], rax; unsigned __int16 *
0x18000c5e5  mov     rax, [rsp+78h+arg_20]
0x18000c5ed  mov     [rsp+78h+var_30], 1; unsigned int
0x18000c5f5  mov     [rsp+78h+var_38], r11; unsigned __int16 *
0x18000c5fa  mov     [rsp+78h+var_40], r10; unsigned __int16 *
0x18000c5ff  mov     [rsp+78h+var_48], rbx; unsigned __int16 *
0x18000c604  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x18000c609  mov     [rsp+78h+var_58], r9; unsigned __int16 *
0x18000c60e  xor     r9d, r9d; unsigned __int16 *
0x18000c611  call    ?ShowDialog@@YAJPEAUHWND__@@PEBG1111111K_NPEAGH@Z; ShowDialog(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,bool,ushort *,int)
0x18000c616  jmp     short loc_18000C61D
0x18000c618  mov     eax, 80070057h
0x18000c61d  add     rsp, 70h
0x18000c621  pop     rbx
0x18000c622  retn
```
