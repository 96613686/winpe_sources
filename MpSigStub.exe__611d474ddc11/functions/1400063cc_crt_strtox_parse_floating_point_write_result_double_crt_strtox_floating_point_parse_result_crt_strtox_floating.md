# __crt_strtox::parse_floating_point_write_result<double>(__crt_strtox::floating_point_parse_result,__crt_strtox::floating_point_string const &,double * const)

- ea: `0x1400063cc`
- end: `0x1400065aa`
- name: `??$parse_floating_point_write_result@N@__crt_strtox@@YA?AW4SLD_STATUS@@W4floating_point_parse_result@0@AEBUfloating_point_string@0@QEAN@Z`
- size: `478`
- prototype: `__int64 __fastcall(int, __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004b48`

## callees

- `0x1400063cc`
- `0x140007c98`
- `0x140009a94`

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
    return sub_140007C98(a2, &v11);
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
0x1400063cc  sub     rsp, 38h
0x1400063d0  mov     r9, rdx
0x1400063d3  cmp     ecx, 5
0x1400063d6  jg      loc_140006509
0x1400063dc  jz      loc_1400064C5
0x1400063e2  test    ecx, ecx
0x1400063e4  jz      loc_1400064A9
0x1400063ea  sub     ecx, 1
0x1400063ed  jz      loc_14000648D
0x1400063f3  sub     ecx, 1
0x1400063f6  jz      short loc_140006470
0x1400063f8  sub     ecx, 1
0x1400063fb  jz      short loc_140006433
0x1400063fd  cmp     ecx, 1
0x140006400  jnz     loc_14000658F
0x140006406  mov     al, [rdx+308h]
0x14000640c  neg     al
0x14000640e  mov     rax, 8000000000000000h
0x140006418  sbb     rcx, rcx
0x14000641b  and     rcx, rax
0x14000641e  mov     rax, 7FFFFFFFFFFFFFFFh
0x140006428  add     rcx, rax
0x14000642b  mov     [r8], rcx
0x14000642e  jmp     loc_1400065A3
0x140006433  mov     al, [rdx+308h]
0x140006439  mov     rdx, 7FF0000000000000h
0x140006443  neg     al
0x140006445  mov     rax, 8000000000000000h
0x14000644f  sbb     rcx, rcx
0x140006452  and     rcx, rax
0x140006455  mov     rax, 0FFF0000000000000h
0x14000645f  add     rcx, rdx
0x140006462  and     rcx, rax
0x140006465  mov     rax, [r8]
0x140006468  and     rax, rdx
0x14000646b  or      rcx, rax
0x14000646e  jmp     short loc_14000642B
0x140006470  mov     al, [rdx+308h]
0x140006476  neg     al
0x140006478  mov     rax, 8000000000000000h
0x140006482  sbb     rcx, rcx
0x140006485  and     rcx, rax
0x140006488  and     rcx, rax
0x14000648b  jmp     short loc_14000642B
0x14000648d  lea     rdx, [rsp+38h+var_18]
0x140006492  mov     [rsp+38h+var_18], r8
0x140006497  mov     rcx, r9
0x14000649a  mov     [rsp+38h+var_10], 1
0x14000649f  call    ?convert_hexadecimal_string_to_floating_type_common@__crt_strtox@@YA?AW4SLD_STATUS@@AEBUfloating_point_string@1@AEBVfloating_point_value@1@@Z
0x1400064a4  jmp     loc_1400065A5
0x1400064a9  lea     rdx, [rsp+38h+var_18]
0x1400064ae  mov     [rsp+38h+var_18], r8
0x1400064b3  mov     rcx, r9
0x1400064b6  mov     [rsp+38h+var_10], 1
0x1400064bb  call    sub_140007C98
0x1400064c0  jmp     loc_1400065A5
0x1400064c5  mov     al, [rdx+308h]
0x1400064cb  mov     rdx, 7FF0000000000000h
0x1400064d5  neg     al
0x1400064d7  mov     rax, 8000000000000000h
0x1400064e1  sbb     rcx, rcx
0x1400064e4  and     rcx, rax
0x1400064e7  mov     rax, 0FFF0000000000001h
0x1400064f1  add     rcx, rdx
0x1400064f4  and     rcx, rax
0x1400064f7  mov     rax, [r8]
0x1400064fa  and     rax, rdx
0x1400064fd  or      rcx, rax
0x140006500  or      rcx, 1
0x140006504  jmp     loc_14000642B
0x140006509  sub     ecx, 6
0x14000650c  jz      loc_140006596
0x140006512  sub     ecx, 1
0x140006515  jz      short loc_14000658B
0x140006517  sub     ecx, 1
0x14000651a  jz      short loc_140006566
0x14000651c  cmp     ecx, 1
0x14000651f  jnz     short loc_14000658F
0x140006521  mov     al, [rdx+308h]
0x140006527  mov     rdx, 7FF0000000000000h
0x140006531  neg     al
0x140006533  mov     rax, 8000000000000000h
0x14000653d  sbb     rcx, rcx
0x140006540  and     rcx, rax
0x140006543  mov     rax, 0FFF0000000000000h
0x14000654d  add     rcx, rdx
0x140006550  and     rcx, rax
0x140006553  mov     rax, [r8]
0x140006556  and     rax, rdx
0x140006559  or      rcx, rax
0x14000655c  mov     eax, 3
0x140006561  mov     [r8], rcx
0x140006564  jmp     short loc_1400065A5
0x140006566  mov     al, [rdx+308h]
0x14000656c  neg     al
0x14000656e  mov     rax, 8000000000000000h
0x140006578  sbb     rcx, rcx
0x14000657b  and     rcx, rax
0x14000657e  and     rcx, rax
0x140006581  mov     eax, 2
0x140006586  mov     [r8], rcx
0x140006589  jmp     short loc_1400065A5
0x14000658b  and     qword ptr [r8], 0
0x14000658f  mov     eax, 1
0x140006594  jmp     short loc_1400065A5
0x140006596  mov     rax, 0FFF8000000000000h
0x1400065a0  mov     [r8], rax
0x1400065a3  xor     eax, eax
0x1400065a5  add     rsp, 38h
0x1400065a9  retn
```
