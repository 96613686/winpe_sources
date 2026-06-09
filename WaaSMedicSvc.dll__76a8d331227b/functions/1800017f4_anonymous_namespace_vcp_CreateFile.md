# _anonymous_namespace_::__vcp_CreateFile

- ea: `0x1800017f4`
- end: `0x180001851`
- name: `_anonymous_namespace_::__vcp_CreateFile`
- size: `93`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, int, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001cd8`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180001846`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180001846`

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
0x1800017f4  mov     r11, rsp
0x1800017f7  sub     rsp, 58h
0x1800017fb  mov     r10d, [rsp+58h+arg_28]
0x180001803  movzx   eax, r10w
0x180001807  and     r10d, 0FFFF0000h
0x18000180e  mov     [rsp+58h+var_24], eax
0x180001812  mov     rax, [rsp+58h+arg_30]
0x18000181a  mov     [rsp+58h+var_1C], 0
0x180001822  mov     [rsp+58h+var_28], 20h ; ' '
0x18000182a  mov     [r11-10h], rax
0x18000182e  lea     rax, [r11-28h]
0x180001832  mov     [r11-18h], r9
0x180001836  mov     r9d, [rsp+58h+arg_20]
0x18000183e  mov     [r11-38h], rax
0x180001842  mov     [r11-20h], r10d
0x180001846  call    cs:__imp_CreateFile2
0x18000184c  add     rsp, 58h
0x180001850  retn
```
