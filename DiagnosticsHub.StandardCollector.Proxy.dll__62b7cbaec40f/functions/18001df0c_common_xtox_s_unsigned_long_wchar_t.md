# common_xtox_s_unsigned_long_wchar_t_

- ea: `0x18001df0c`
- end: `0x18001df75`
- name: `common_xtox_s_unsigned_long_wchar_t_`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e17c`
- `0x18001e21c`
- `0x18001e308`

## callees

- `0x180007c00`
- `0x180007ee8`
- `0x18001dc2c`
- `0x18001df0c`

## pseudocode

```c
__int64 __fastcall common_xtox_s_unsigned_long_wchar_t_(
        unsigned int a1,
        __int16 *a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned __int8 a5)
{
  int *v5; // rax
  unsigned int v6; // ebx

  if ( !a2 || !a3 )
    goto LABEL_2;
  *a2 = 0;
  if ( a3 <= (unsigned __int64)a5 + 1 )
  {
    v5 = errno();
    v6 = 34;
    goto LABEL_3;
  }
  if ( a4 - 2 > 0x22 )
  {
LABEL_2:
    v5 = errno();
    v6 = 22;
LABEL_3:
    *v5 = v6;
    invalid_parameter_noinfo();
    return v6;
  }
  return common_xtox_unsigned_long_wchar_t_(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18001df0c  push    rbx
0x18001df0e  sub     rsp, 30h
0x18001df12  xor     eax, eax
0x18001df14  mov     r10d, ecx
0x18001df17  test    rdx, rdx
0x18001df1a  jnz     short loc_18001DF35
0x18001df1c  call    _errno
0x18001df21  mov     ebx, 16h
0x18001df26  mov     [rax], ebx
0x18001df28  call    _invalid_parameter_noinfo
0x18001df2d  mov     eax, ebx
0x18001df2f  add     rsp, 30h
0x18001df33  pop     rbx
0x18001df34  retn
0x18001df35  test    r8, r8
0x18001df38  jz      short loc_18001DF1C
0x18001df3a  movzx   ecx, [rsp+38h+arg_20]
0x18001df3f  mov     [rdx], ax
0x18001df42  lea     rax, [rcx+1]
0x18001df46  cmp     r8, rax
0x18001df49  ja      short loc_18001DF57
0x18001df4b  call    _errno
0x18001df50  mov     ebx, 22h ; '"'
0x18001df55  jmp     short loc_18001DF26
0x18001df57  lea     eax, [r9-2]
0x18001df5b  mov     ebx, 22h ; '"'
0x18001df60  cmp     eax, ebx
0x18001df62  ja      short loc_18001DF1C
0x18001df64  mov     [rsp+38h+arg_20], cl
0x18001df68  mov     ecx, r10d
0x18001df6b  add     rsp, 30h
0x18001df6f  pop     rbx
0x18001df70  jmp     common_xtox_unsigned_long_wchar_t_
```
