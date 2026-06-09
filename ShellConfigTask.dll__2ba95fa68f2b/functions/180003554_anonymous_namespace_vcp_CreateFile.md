# _anonymous_namespace_::__vcp_CreateFile

- ea: `0x180003554`
- end: `0x1800035b1`
- name: `_anonymous_namespace_::__vcp_CreateFile`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180003a38`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800035a6`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800035a6`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::__vcp_CreateFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7)
{
  _DWORD v8[4]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]
  __int64 v10; // [rsp+48h] [rbp-10h]

  v8[1] = (unsigned __int16)a6;
  v8[3] = 0;
  v8[0] = 32;
  v10 = a7;
  v9 = a4;
  v8[2] = a6 & 0xFFFF0000;
  return CreateFile2(a1, a2, a3, a5, v8);
}

```

## disassembly

```asm
0x180003554  mov     r11, rsp
0x180003557  sub     rsp, 58h
0x18000355b  mov     r10d, [rsp+58h+arg_28]
0x180003563  movzx   eax, r10w
0x180003567  and     r10d, 0FFFF0000h
0x18000356e  mov     [rsp+58h+var_24], eax
0x180003572  mov     rax, [rsp+58h+arg_30]
0x18000357a  mov     [rsp+58h+var_1C], 0
0x180003582  mov     [rsp+58h+var_28], 20h ; ' '
0x18000358a  mov     [r11-10h], rax
0x18000358e  lea     rax, [r11-28h]
0x180003592  mov     [r11-18h], r9
0x180003596  mov     r9d, [rsp+58h+arg_20]
0x18000359e  mov     [r11-38h], rax
0x1800035a2  mov     [r11-20h], r10d
0x1800035a6  call    cs:__imp_CreateFile2
0x1800035ac  add     rsp, 58h
0x1800035b0  retn
```
