# common_xtox_s_unsigned_long_char_

- ea: `0x18001d744`
- end: `0x18001d7ab`
- name: `common_xtox_s_unsigned_long_char_`
- size: `103`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d9cc`
- `0x18001da6c`
- `0x18001db70`

## callees

- `0x1800074a0`
- `0x180007788`
- `0x18001d404`
- `0x18001d744`

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
0x18001d744  push    rbx
0x18001d746  sub     rsp, 30h
0x18001d74a  mov     r10d, ecx
0x18001d74d  test    rdx, rdx
0x18001d750  jnz     short loc_18001D76B
0x18001d752  call    _errno
0x18001d757  mov     ebx, 16h
0x18001d75c  mov     [rax], ebx
0x18001d75e  call    _invalid_parameter_noinfo
0x18001d763  mov     eax, ebx
0x18001d765  add     rsp, 30h
0x18001d769  pop     rbx
0x18001d76a  retn
0x18001d76b  test    r8, r8
0x18001d76e  jz      short loc_18001D752
0x18001d770  movzx   ecx, [rsp+38h+arg_20]
0x18001d775  mov     byte ptr [rdx], 0
0x18001d778  lea     rax, [rcx+1]
0x18001d77c  cmp     r8, rax
0x18001d77f  ja      short loc_18001D78D
0x18001d781  call    _errno
0x18001d786  mov     ebx, 22h ; '"'
0x18001d78b  jmp     short loc_18001D75C
0x18001d78d  lea     eax, [r9-2]
0x18001d791  mov     ebx, 22h ; '"'
0x18001d796  cmp     eax, ebx
0x18001d798  ja      short loc_18001D752
0x18001d79a  mov     [rsp+38h+arg_20], cl
0x18001d79e  mov     ecx, r10d
0x18001d7a1  add     rsp, 30h
0x18001d7a5  pop     rbx
0x18001d7a6  jmp     common_xtox_unsigned_long_char_
```
