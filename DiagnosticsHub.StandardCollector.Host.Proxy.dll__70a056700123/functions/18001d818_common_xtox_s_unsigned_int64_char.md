# common_xtox_s_unsigned___int64_char_

- ea: `0x18001d818`
- end: `0x18001d87f`
- name: `common_xtox_s_unsigned___int64_char_`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d920`
- `0x18001db00`

## callees

- `0x1800074a0`
- `0x180007788`
- `0x18001d5a0`
- `0x18001d818`

## pseudocode

```c
__int64 __fastcall common_xtox_s_unsigned___int64_char_(
        unsigned __int64 a1,
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
  return common_xtox_unsigned___int64_char_(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18001d818  push    rbx
0x18001d81a  sub     rsp, 30h
0x18001d81e  mov     r10, rcx
0x18001d821  test    rdx, rdx
0x18001d824  jnz     short loc_18001D83F
0x18001d826  call    _errno
0x18001d82b  mov     ebx, 16h
0x18001d830  mov     [rax], ebx
0x18001d832  call    _invalid_parameter_noinfo
0x18001d837  mov     eax, ebx
0x18001d839  add     rsp, 30h
0x18001d83d  pop     rbx
0x18001d83e  retn
0x18001d83f  test    r8, r8
0x18001d842  jz      short loc_18001D826
0x18001d844  movzx   ecx, [rsp+38h+arg_20]
0x18001d849  mov     byte ptr [rdx], 0
0x18001d84c  lea     rax, [rcx+1]
0x18001d850  cmp     r8, rax
0x18001d853  ja      short loc_18001D861
0x18001d855  call    _errno
0x18001d85a  mov     ebx, 22h ; '"'
0x18001d85f  jmp     short loc_18001D830
0x18001d861  lea     eax, [r9-2]
0x18001d865  mov     ebx, 22h ; '"'
0x18001d86a  cmp     eax, ebx
0x18001d86c  ja      short loc_18001D826
0x18001d86e  mov     [rsp+38h+arg_20], cl
0x18001d872  mov     rcx, r10
0x18001d875  add     rsp, 30h
0x18001d879  pop     rbx
0x18001d87a  jmp     common_xtox_unsigned___int64_char_
```
