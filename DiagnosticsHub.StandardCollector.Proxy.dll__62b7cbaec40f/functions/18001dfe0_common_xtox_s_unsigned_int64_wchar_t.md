# common_xtox_s_unsigned___int64_wchar_t_

- ea: `0x18001dfe0`
- end: `0x18001e049`
- name: `common_xtox_s_unsigned___int64_wchar_t_`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e0d8`
- `0x18001e298`

## callees

- `0x180007c00`
- `0x180007ee8`
- `0x18001ddcc`
- `0x18001dfe0`

## pseudocode

```c
__int64 __fastcall common_xtox_s_unsigned___int64_wchar_t_(
        unsigned __int64 a1,
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
  return common_xtox_unsigned___int64_wchar_t_(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18001dfe0  push    rbx
0x18001dfe2  sub     rsp, 30h
0x18001dfe6  xor     eax, eax
0x18001dfe8  mov     r10, rcx
0x18001dfeb  test    rdx, rdx
0x18001dfee  jnz     short loc_18001E009
0x18001dff0  call    _errno
0x18001dff5  mov     ebx, 16h
0x18001dffa  mov     [rax], ebx
0x18001dffc  call    _invalid_parameter_noinfo
0x18001e001  mov     eax, ebx
0x18001e003  add     rsp, 30h
0x18001e007  pop     rbx
0x18001e008  retn
0x18001e009  test    r8, r8
0x18001e00c  jz      short loc_18001DFF0
0x18001e00e  movzx   ecx, [rsp+38h+arg_20]
0x18001e013  mov     [rdx], ax
0x18001e016  lea     rax, [rcx+1]
0x18001e01a  cmp     r8, rax
0x18001e01d  ja      short loc_18001E02B
0x18001e01f  call    _errno
0x18001e024  mov     ebx, 22h ; '"'
0x18001e029  jmp     short loc_18001DFFA
0x18001e02b  lea     eax, [r9-2]
0x18001e02f  mov     ebx, 22h ; '"'
0x18001e034  cmp     eax, ebx
0x18001e036  ja      short loc_18001DFF0
0x18001e038  mov     [rsp+38h+arg_20], cl
0x18001e03c  mov     rcx, r10
0x18001e03f  add     rsp, 30h
0x18001e043  pop     rbx
0x18001e044  jmp     common_xtox_unsigned___int64_wchar_t_
```
