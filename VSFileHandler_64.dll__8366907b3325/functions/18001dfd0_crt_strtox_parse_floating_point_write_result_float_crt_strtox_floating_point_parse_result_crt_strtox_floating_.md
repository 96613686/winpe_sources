# __crt_strtox::parse_floating_point_write_result<float>(__crt_strtox::floating_point_parse_result,__crt_strtox::floating_point_string const &,float * const)

- ea: `0x18001dfd0`
- end: `0x18001e13f`
- name: `??$parse_floating_point_write_result@M@__crt_strtox@@YA?AW4SLD_STATUS@@W4floating_point_parse_result@0@AEBUfloating_point_string@0@QEAM@Z`
- size: `367`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b548`
- `0x18001b698`

## callees

- `0x18001dfd0`
- `0x180020290`
- `0x1800220e0`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_floating_point_write_result<float>(int a1, __int64 a2, unsigned int *a3)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  unsigned int v6; // ecx
  __int64 result; // rax
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  unsigned int *v11; // [rsp+20h] [rbp-18h] BYREF
  char v12; // [rsp+28h] [rbp-10h]

  if ( a1 > 5 )
  {
    v8 = a1 - 6;
    if ( !v8 )
    {
      *a3 = -4194304;
      return 0;
    }
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( !v10 )
      {
        result = 2;
        *a3 = *(_BYTE *)(a2 + 776) != 0 ? 0x80000000 : 0;
        return result;
      }
      if ( v10 == 1 )
      {
        result = 3;
        *a3 = *a3 & 0x7F800000 | (*(_BYTE *)(a2 + 776) != 0 ? -8388608 : 2139095040) & 0xFF800000;
        return result;
      }
    }
    else
    {
      *a3 = 0;
    }
    return 1;
  }
  if ( a1 == 5 )
  {
    v6 = *a3 & 0x7F800000 | (*(_BYTE *)(a2 + 776) != 0 ? -8388608 : 2139095040) & 0xFF800001 | 1;
    goto LABEL_9;
  }
  if ( !a1 )
  {
    v11 = a3;
    v12 = 0;
    return __crt_strtox::convert_decimal_string_to_floating_type_common(a2, (__crt_strtox::floating_point_value *)&v11);
  }
  v3 = a1 - 1;
  if ( !v3 )
  {
    v11 = a3;
    v12 = 0;
    return __crt_strtox::convert_hexadecimal_string_to_floating_type_common(a2, &v11);
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v6 = *(_BYTE *)(a2 + 776) != 0 ? 0x80000000 : 0;
    goto LABEL_9;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v6 = *a3 & 0x7F800000 | (*(_BYTE *)(a2 + 776) != 0 ? -8388608 : 2139095040) & 0xFF800000;
    goto LABEL_9;
  }
  if ( v5 != 1 )
    return 1;
  v6 = *(_BYTE *)(a2 + 776) != 0 ? -1 : 0x7FFFFFFF;
LABEL_9:
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x18001dfd0  sub     rsp, 38h
0x18001dfd4  mov     r9, rdx
0x18001dfd7  cmp     ecx, 5
0x18001dfda  jg      loc_18001E0C6
0x18001dfe0  jz      loc_18001E099
0x18001dfe6  test    ecx, ecx
0x18001dfe8  jz      loc_18001E07D
0x18001dfee  sub     ecx, 1
0x18001dff1  jz      short loc_18001E061
0x18001dff3  sub     ecx, 1
0x18001dff6  jz      short loc_18001E04C
0x18001dff8  sub     ecx, 1
0x18001dffb  jz      short loc_18001E025
0x18001dffd  cmp     ecx, 1
0x18001e000  jnz     loc_18001E12A
0x18001e006  mov     al, [rdx+308h]
0x18001e00c  neg     al
0x18001e00e  mov     eax, 80000000h
0x18001e013  sbb     ecx, ecx
0x18001e015  and     ecx, eax
0x18001e017  add     ecx, 7FFFFFFFh
0x18001e01d  mov     [r8], ecx
0x18001e020  jmp     loc_18001E138
0x18001e025  mov     al, [rdx+308h]
0x18001e02b  mov     edx, 7F800000h
0x18001e030  neg     al
0x18001e032  mov     eax, 80000000h
0x18001e037  sbb     ecx, ecx
0x18001e039  and     ecx, eax
0x18001e03b  mov     eax, [r8]
0x18001e03e  and     eax, edx
0x18001e040  add     ecx, edx
0x18001e042  or      ecx, eax
0x18001e044  and     ecx, 0FF800000h
0x18001e04a  jmp     short loc_18001E01D
0x18001e04c  mov     al, [rdx+308h]
0x18001e052  neg     al
0x18001e054  mov     eax, 80000000h
0x18001e059  sbb     ecx, ecx
0x18001e05b  and     ecx, eax
0x18001e05d  and     ecx, eax
0x18001e05f  jmp     short loc_18001E01D
0x18001e061  lea     rdx, [rsp+38h+var_18]
0x18001e066  mov     [rsp+38h+var_18], r8
0x18001e06b  mov     rcx, r9
0x18001e06e  mov     [rsp+38h+var_10], 0
0x18001e073  call    ?convert_hexadecimal_string_to_floating_type_common@__crt_strtox@@YA?AW4SLD_STATUS@@AEBUfloating_point_string@1@AEBVfloating_point_value@1@@Z; __crt_strtox::convert_hexadecimal_string_to_floating_type_common(__crt_strtox::floating_point_string const &,__crt_strtox::floating_point_value const &)
0x18001e078  jmp     loc_18001E13A
0x18001e07d  lea     rdx, [rsp+38h+var_18]
0x18001e082  mov     [rsp+38h+var_18], r8
0x18001e087  mov     rcx, r9
0x18001e08a  mov     [rsp+38h+var_10], 0
0x18001e08f  call    ?convert_decimal_string_to_floating_type_common@__crt_strtox@@YA?AW4SLD_STATUS@@AEBUfloating_point_string@1@AEBVfloating_point_value@1@@Z; __crt_strtox::convert_decimal_string_to_floating_type_common(__crt_strtox::floating_point_string const &,__crt_strtox::floating_point_value const &)
0x18001e094  jmp     loc_18001E13A
0x18001e099  mov     al, [rdx+308h]
0x18001e09f  mov     edx, 7F800000h
0x18001e0a4  neg     al
0x18001e0a6  mov     eax, 80000000h
0x18001e0ab  sbb     ecx, ecx
0x18001e0ad  and     ecx, eax
0x18001e0af  mov     eax, [r8]
0x18001e0b2  add     ecx, edx
0x18001e0b4  and     eax, edx
0x18001e0b6  or      ecx, eax
0x18001e0b8  and     ecx, 0FF800001h
0x18001e0be  or      ecx, 1
0x18001e0c1  jmp     loc_18001E01D
0x18001e0c6  sub     ecx, 6
0x18001e0c9  jz      short loc_18001E131
0x18001e0cb  sub     ecx, 1
0x18001e0ce  jz      short loc_18001E126
0x18001e0d0  sub     ecx, 1
0x18001e0d3  jz      short loc_18001E109
0x18001e0d5  cmp     ecx, 1
0x18001e0d8  jnz     short loc_18001E12A
0x18001e0da  mov     al, [rdx+308h]
0x18001e0e0  mov     edx, 7F800000h
0x18001e0e5  neg     al
0x18001e0e7  mov     eax, 80000000h
0x18001e0ec  sbb     ecx, ecx
0x18001e0ee  and     ecx, eax
0x18001e0f0  mov     eax, [r8]
0x18001e0f3  and     eax, edx
0x18001e0f5  add     ecx, edx
0x18001e0f7  or      ecx, eax
0x18001e0f9  mov     eax, 3
0x18001e0fe  and     ecx, 0FF800000h
0x18001e104  mov     [r8], ecx
0x18001e107  jmp     short loc_18001E13A
0x18001e109  mov     al, [rdx+308h]
0x18001e10f  neg     al
0x18001e111  mov     eax, 80000000h
0x18001e116  sbb     ecx, ecx
0x18001e118  and     ecx, eax
0x18001e11a  and     ecx, eax
0x18001e11c  mov     eax, 2
0x18001e121  mov     [r8], ecx
0x18001e124  jmp     short loc_18001E13A
0x18001e126  and     dword ptr [r8], 0
0x18001e12a  mov     eax, 1
0x18001e12f  jmp     short loc_18001E13A
0x18001e131  mov     dword ptr [r8], 0FFC00000h
0x18001e138  xor     eax, eax
0x18001e13a  add     rsp, 38h
0x18001e13e  retn
```
