# common_xtox_s_unsigned_long_char_

- ea: `0x18001dea4`
- end: `0x18001df0b`
- name: `common_xtox_s_unsigned_long_char_`
- size: `103`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e12c`
- `0x18001e1cc`
- `0x18001e2d0`

## callees

- `0x180007c00`
- `0x180007ee8`
- `0x18001db64`
- `0x18001dea4`

## pseudocode

```c
__int64 __fastcall common_xtox_s_unsigned_long_char_(
        unsigned int a1,
        char *a2,
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
  return common_xtox_unsigned_long_char_(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18001dea4  push    rbx
0x18001dea6  sub     rsp, 30h
0x18001deaa  mov     r10d, ecx
0x18001dead  test    rdx, rdx
0x18001deb0  jnz     short loc_18001DECB
0x18001deb2  call    _errno
0x18001deb7  mov     ebx, 16h
0x18001debc  mov     [rax], ebx
0x18001debe  call    _invalid_parameter_noinfo
0x18001dec3  mov     eax, ebx
0x18001dec5  add     rsp, 30h
0x18001dec9  pop     rbx
0x18001deca  retn
0x18001decb  test    r8, r8
0x18001dece  jz      short loc_18001DEB2
0x18001ded0  movzx   ecx, [rsp+38h+arg_20]
0x18001ded5  mov     byte ptr [rdx], 0
0x18001ded8  lea     rax, [rcx+1]
0x18001dedc  cmp     r8, rax
0x18001dedf  ja      short loc_18001DEED
0x18001dee1  call    _errno
0x18001dee6  mov     ebx, 22h ; '"'
0x18001deeb  jmp     short loc_18001DEBC
0x18001deed  lea     eax, [r9-2]
0x18001def1  mov     ebx, 22h ; '"'
0x18001def6  cmp     eax, ebx
0x18001def8  ja      short loc_18001DEB2
0x18001defa  mov     [rsp+38h+arg_20], cl
0x18001defe  mov     ecx, r10d
0x18001df01  add     rsp, 30h
0x18001df05  pop     rbx
0x18001df06  jmp     common_xtox_unsigned_long_char_
```
