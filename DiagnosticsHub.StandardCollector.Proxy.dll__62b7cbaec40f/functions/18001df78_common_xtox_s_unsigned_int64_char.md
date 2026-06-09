# common_xtox_s_unsigned___int64_char_

- ea: `0x18001df78`
- end: `0x18001dfdf`
- name: `common_xtox_s_unsigned___int64_char_`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e080`
- `0x18001e260`

## callees

- `0x180007c00`
- `0x180007ee8`
- `0x18001dd00`
- `0x18001df78`

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
0x18001df78  push    rbx
0x18001df7a  sub     rsp, 30h
0x18001df7e  mov     r10, rcx
0x18001df81  test    rdx, rdx
0x18001df84  jnz     short loc_18001DF9F
0x18001df86  call    _errno
0x18001df8b  mov     ebx, 16h
0x18001df90  mov     [rax], ebx
0x18001df92  call    _invalid_parameter_noinfo
0x18001df97  mov     eax, ebx
0x18001df99  add     rsp, 30h
0x18001df9d  pop     rbx
0x18001df9e  retn
0x18001df9f  test    r8, r8
0x18001dfa2  jz      short loc_18001DF86
0x18001dfa4  movzx   ecx, [rsp+38h+arg_20]
0x18001dfa9  mov     byte ptr [rdx], 0
0x18001dfac  lea     rax, [rcx+1]
0x18001dfb0  cmp     r8, rax
0x18001dfb3  ja      short loc_18001DFC1
0x18001dfb5  call    _errno
0x18001dfba  mov     ebx, 22h ; '"'
0x18001dfbf  jmp     short loc_18001DF90
0x18001dfc1  lea     eax, [r9-2]
0x18001dfc5  mov     ebx, 22h ; '"'
0x18001dfca  cmp     eax, ebx
0x18001dfcc  ja      short loc_18001DF86
0x18001dfce  mov     [rsp+38h+arg_20], cl
0x18001dfd2  mov     rcx, r10
0x18001dfd5  add     rsp, 30h
0x18001dfd9  pop     rbx
0x18001dfda  jmp     common_xtox_unsigned___int64_char_
```
