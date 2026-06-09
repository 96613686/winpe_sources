# __crt_strtox::parse_floating_point_write_result<double>(__crt_strtox::floating_point_parse_result,__crt_strtox::floating_point_string const &,double * const)

- ea: `0x18001e140`
- end: `0x18001e31e`
- name: `??$parse_floating_point_write_result@N@__crt_strtox@@YA?AW4SLD_STATUS@@W4floating_point_parse_result@0@AEBUfloating_point_string@0@QEAN@Z`
- size: `478`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b5f0`
- `0x18001b740`

## callees

- `0x18001e140`
- `0x180020290`
- `0x1800220e0`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_floating_point_write_result<double>(int a1, __int64 a2, unsigned __int64 *a3)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  unsigned __int64 v6; // rcx
  __int64 result; // rax
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  unsigned __int64 *v11; // [rsp+20h] [rbp-18h] BYREF
  char v12; // [rsp+28h] [rbp-10h]

  if ( a1 > 5 )
  {
    v8 = a1 - 6;
    if ( !v8 )
    {
      *a3 = 0xFFF8000000000000uLL;
      return 0;
    }
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( !v10 )
      {
        result = 2;
        *a3 = -(__int64)(*(_BYTE *)(a2 + 776) != 0) & 0x8000000000000000uLL;
        return result;
      }
      if ( v10 == 1 )
      {
        result = 3;
        *a3 = *a3 & 0x7FF0000000000000LL
            | ((-(__int64)(*(_BYTE *)(a2 + 776) != 0) & 0x8000000000000000uLL) + 0x7FF0000000000000LL)
            & 0xFFF0000000000000uLL;
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
    v6 = *a3 & 0x7FF0000000000000LL
       | ((-(__int64)(*(_BYTE *)(a2 + 776) != 0) & 0x8000000000000000uLL) + 0x7FF0000000000000LL)
       & 0xFFF0000000000001uLL
       | 1;
    goto LABEL_9;
  }
  if ( !a1 )
  {
    v11 = a3;
    v12 = 1;
    return __crt_strtox::convert_decimal_string_to_floating_type_common(a2, (__crt_strtox::floating_point_value *)&v11);
  }
  v3 = a1 - 1;
  if ( !v3 )
  {
    v11 = a3;
    v12 = 1;
    return __crt_strtox::convert_hexadecimal_string_to_floating_type_common(a2, &v11);
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v6 = -(__int64)(*(_BYTE *)(a2 + 776) != 0) & 0x8000000000000000uLL;
    goto LABEL_9;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v6 = *a3 & 0x7FF0000000000000LL
       | ((-(__int64)(*(_BYTE *)(a2 + 776) != 0) & 0x8000000000000000uLL) + 0x7FF0000000000000LL)
       & 0xFFF0000000000000uLL;
    goto LABEL_9;
  }
  if ( v5 != 1 )
    return 1;
  v6 = (-(__int64)(*(_BYTE *)(a2 + 776) != 0) & 0x8000000000000000uLL) + 0x7FFFFFFFFFFFFFFFLL;
LABEL_9:
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x18001e140  sub     rsp, 38h
0x18001e144  mov     r9, rdx
0x18001e147  cmp     ecx, 5
0x18001e14a  jg      loc_18001E27D
0x18001e150  jz      loc_18001E239
0x18001e156  test    ecx, ecx
0x18001e158  jz      loc_18001E21D
0x18001e15e  sub     ecx, 1
0x18001e161  jz      loc_18001E201
0x18001e167  sub     ecx, 1
0x18001e16a  jz      short loc_18001E1E4
0x18001e16c  sub     ecx, 1
0x18001e16f  jz      short loc_18001E1A7
0x18001e171  cmp     ecx, 1
0x18001e174  jnz     loc_18001E303
0x18001e17a  mov     al, [rdx+308h]
0x18001e180  neg     al
0x18001e182  mov     rax, 8000000000000000h
0x18001e18c  sbb     rcx, rcx
0x18001e18f  and     rcx, rax
0x18001e192  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001e19c  add     rcx, rax
0x18001e19f  mov     [r8], rcx
0x18001e1a2  jmp     loc_18001E317
0x18001e1a7  mov     al, [rdx+308h]
0x18001e1ad  mov     rdx, 7FF0000000000000h
0x18001e1b7  neg     al
0x18001e1b9  mov     rax, 8000000000000000h
0x18001e1c3  sbb     rcx, rcx
0x18001e1c6  and     rcx, rax
0x18001e1c9  mov     rax, 0FFF0000000000000h
0x18001e1d3  add     rcx, rdx
0x18001e1d6  and     rcx, rax
0x18001e1d9  mov     rax, [r8]
0x18001e1dc  and     rax, rdx
0x18001e1df  or      rcx, rax
0x18001e1e2  jmp     short loc_18001E19F
0x18001e1e4  mov     al, [rdx+308h]
0x18001e1ea  neg     al
0x18001e1ec  mov     rax, 8000000000000000h
0x18001e1f6  sbb     rcx, rcx
0x18001e1f9  and     rcx, rax
0x18001e1fc  and     rcx, rax
0x18001e1ff  jmp     short loc_18001E19F
0x18001e201  lea     rdx, [rsp+38h+var_18]
0x18001e206  mov     [rsp+38h+var_18], r8
0x18001e20b  mov     rcx, r9
0x18001e20e  mov     [rsp+38h+var_10], 1
0x18001e213  call    ?convert_hexadecimal_string_to_floating_type_common@__crt_strtox@@YA?AW4SLD_STATUS@@AEBUfloating_point_string@1@AEBVfloating_point_value@1@@Z; __crt_strtox::convert_hexadecimal_string_to_floating_type_common(__crt_strtox::floating_point_string const &,__crt_strtox::floating_point_value const &)
0x18001e218  jmp     loc_18001E319
0x18001e21d  lea     rdx, [rsp+38h+var_18]
0x18001e222  mov     [rsp+38h+var_18], r8
0x18001e227  mov     rcx, r9
0x18001e22a  mov     [rsp+38h+var_10], 1
0x18001e22f  call    ?convert_decimal_string_to_floating_type_common@__crt_strtox@@YA?AW4SLD_STATUS@@AEBUfloating_point_string@1@AEBVfloating_point_value@1@@Z; __crt_strtox::convert_decimal_string_to_floating_type_common(__crt_strtox::floating_point_string const &,__crt_strtox::floating_point_value const &)
0x18001e234  jmp     loc_18001E319
0x18001e239  mov     al, [rdx+308h]
0x18001e23f  mov     rdx, 7FF0000000000000h
0x18001e249  neg     al
0x18001e24b  mov     rax, 8000000000000000h
0x18001e255  sbb     rcx, rcx
0x18001e258  and     rcx, rax
0x18001e25b  mov     rax, 0FFF0000000000001h
0x18001e265  add     rcx, rdx
0x18001e268  and     rcx, rax
0x18001e26b  mov     rax, [r8]
0x18001e26e  and     rax, rdx
0x18001e271  or      rcx, rax
0x18001e274  or      rcx, 1
0x18001e278  jmp     loc_18001E19F
0x18001e27d  sub     ecx, 6
0x18001e280  jz      loc_18001E30A
0x18001e286  sub     ecx, 1
0x18001e289  jz      short loc_18001E2FF
0x18001e28b  sub     ecx, 1
0x18001e28e  jz      short loc_18001E2DA
0x18001e290  cmp     ecx, 1
0x18001e293  jnz     short loc_18001E303
0x18001e295  mov     al, [rdx+308h]
0x18001e29b  mov     rdx, 7FF0000000000000h
0x18001e2a5  neg     al
0x18001e2a7  mov     rax, 8000000000000000h
0x18001e2b1  sbb     rcx, rcx
0x18001e2b4  and     rcx, rax
0x18001e2b7  mov     rax, 0FFF0000000000000h
0x18001e2c1  add     rcx, rdx
0x18001e2c4  and     rcx, rax
0x18001e2c7  mov     rax, [r8]
0x18001e2ca  and     rax, rdx
0x18001e2cd  or      rcx, rax
0x18001e2d0  mov     eax, 3
0x18001e2d5  mov     [r8], rcx
0x18001e2d8  jmp     short loc_18001E319
0x18001e2da  mov     al, [rdx+308h]
0x18001e2e0  neg     al
0x18001e2e2  mov     rax, 8000000000000000h
0x18001e2ec  sbb     rcx, rcx
0x18001e2ef  and     rcx, rax
0x18001e2f2  and     rcx, rax
0x18001e2f5  mov     eax, 2
0x18001e2fa  mov     [r8], rcx
0x18001e2fd  jmp     short loc_18001E319
0x18001e2ff  and     qword ptr [r8], 0
0x18001e303  mov     eax, 1
0x18001e308  jmp     short loc_18001E319
0x18001e30a  mov     rax, 0FFF8000000000000h
0x18001e314  mov     [r8], rax
0x18001e317  xor     eax, eax
0x18001e319  add     rsp, 38h
0x18001e31d  retn
```
