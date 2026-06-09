# sub_18001DCCA

- ea: `0x18001dcca`
- end: `0x18001dd44`
- name: `sub_18001DCCA`
- size: `122`
- prototype: ``
- caller_count: `66`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001ccc1`
- `0x18001cccd`
- `0x18001ccd9`
- `0x18001cde8`
- `0x18001cdf4`
- `0x18002a189`
- `0x18002a1b9`
- `0x18002a1c5`
- `0x18002a1d1`
- `0x18002a1dd`
- `0x18002a1e9`
- `0x18002a1f5`
- `0x18002a201`
- `0x18002a20d`
- `0x18002a219`
- `0x18002a225`
- `0x18002a231`
- `0x18002a23d`
- `0x18002bc4c`
- `0x18002d203`
- `0x1800350c9`
- `0x18003a2fb`
- `0x18003a8c8`
- `0x18003c966`
- `0x18004ea2a`
- `0x18004ea36`
- `0x18004ea42`
- `0x18004ea4e`
- `0x18004ea5a`
- `0x18004ea66`
- `0x18004ea72`
- `0x18004ea7e`
- `0x18004ea8a`
- `0x18004ea96`
- `0x18004eaa2`
- `0x18004eaae`
- `0x18004eaba`
- `0x18004eac6`
- `0x18004ead2`
- `0x18004eade`
- `0x18004eaea`
- `0x18004eaf6`
- `0x18004eb02`
- `0x18004eb0e`
- `0x18004eb1a`
- `0x18004eb26`
- `0x18004eb32`
- `0x18004eb3e`
- `0x18004eb4a`
- `0x18004eb56`

## callees

- `0x18001d530`
- `0x18001dcca`

## pseudocode

```c
__int64 __fastcall sub_18001DCCA(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _BYTE *v4; // rax
  FARPROC v5; // rax

  v5 = sub_18001D530(&GDI32_dll_import_table, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))v5)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001dcca  mov     [rsp+arg_0], rcx
0x18001dccf  mov     [rsp+arg_8], rdx
0x18001dcd4  mov     [rsp+arg_10], r8
0x18001dcd9  mov     [rsp+arg_18], r9
0x18001dcde  sub     rsp, 68h
0x18001dce2  movdqa  [rsp+68h+var_48], xmm0
0x18001dce8  movdqa  [rsp+68h+var_38], xmm1
0x18001dcee  movdqa  [rsp+68h+var_28], xmm2
0x18001dcf4  movdqa  [rsp+68h+var_18], xmm3
0x18001dcfa  mov     rdx, rax
0x18001dcfd  lea     rcx, GDI32_dll_import_table
0x18001dd04  call    sub_18001D530
0x18001dd09  movdqa  xmm0, [rsp+68h+var_48]
0x18001dd0f  movdqa  xmm1, [rsp+68h+var_38]
0x18001dd15  movdqa  xmm2, [rsp+68h+var_28]
0x18001dd1b  movdqa  xmm3, [rsp+68h+var_18]
0x18001dd21  mov     rcx, [rsp+68h+arg_0]
0x18001dd26  mov     rdx, [rsp+68h+arg_8]
0x18001dd2b  mov     r8, [rsp+68h+arg_10]
0x18001dd33  mov     r9, [rsp+68h+arg_18]
0x18001dd3b  add     rsp, 68h
0x18001dd3f  jmp     short loc_18001DD42
0x18001dd42  jmp     rax
```
