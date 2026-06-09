# __crt_strtox::parse_floating_point_write_result<float>(__crt_strtox::floating_point_parse_result,__crt_strtox::floating_point_string const &,float * const)

- ea: `0x14000625c`
- end: `0x1400063cb`
- name: `??$parse_floating_point_write_result@M@__crt_strtox@@YA?AW4SLD_STATUS@@W4floating_point_parse_result@0@AEBUfloating_point_string@0@QEAM@Z`
- size: `367`
- prototype: `__int64 __fastcall(int, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004a8c`

## callees

- `0x14000625c`
- `0x140007c98`
- `0x140009a94`

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
    return sub_140007C98(a2, &v11);
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
0x14000625c  sub     rsp, 38h
0x140006260  mov     r9, rdx
0x140006263  cmp     ecx, 5
0x140006266  jg      loc_140006352
0x14000626c  jz      loc_140006325
0x140006272  test    ecx, ecx
0x140006274  jz      loc_140006309
0x14000627a  sub     ecx, 1
0x14000627d  jz      short loc_1400062ED
0x14000627f  sub     ecx, 1
0x140006282  jz      short loc_1400062D8
0x140006284  sub     ecx, 1
0x140006287  jz      short loc_1400062B1
0x140006289  cmp     ecx, 1
0x14000628c  jnz     loc_1400063B6
0x140006292  mov     al, [rdx+308h]
0x140006298  neg     al
0x14000629a  mov     eax, 80000000h
0x14000629f  sbb     ecx, ecx
0x1400062a1  and     ecx, eax
0x1400062a3  add     ecx, 7FFFFFFFh
0x1400062a9  mov     [r8], ecx
0x1400062ac  jmp     loc_1400063C4
0x1400062b1  mov     al, [rdx+308h]
0x1400062b7  mov     edx, 7F800000h
0x1400062bc  neg     al
0x1400062be  mov     eax, 80000000h
0x1400062c3  sbb     ecx, ecx
0x1400062c5  and     ecx, eax
0x1400062c7  mov     eax, [r8]
0x1400062ca  and     eax, edx
0x1400062cc  add     ecx, edx
0x1400062ce  or      ecx, eax
0x1400062d0  and     ecx, 0FF800000h
0x1400062d6  jmp     short loc_1400062A9
0x1400062d8  mov     al, [rdx+308h]
0x1400062de  neg     al
0x1400062e0  mov     eax, 80000000h
0x1400062e5  sbb     ecx, ecx
0x1400062e7  and     ecx, eax
0x1400062e9  and     ecx, eax
0x1400062eb  jmp     short loc_1400062A9
0x1400062ed  lea     rdx, [rsp+38h+var_18]
0x1400062f2  mov     [rsp+38h+var_18], r8
0x1400062f7  mov     rcx, r9
0x1400062fa  mov     [rsp+38h+var_10], 0
0x1400062ff  call    ?convert_hexadecimal_string_to_floating_type_common@__crt_strtox@@YA?AW4SLD_STATUS@@AEBUfloating_point_string@1@AEBVfloating_point_value@1@@Z
0x140006304  jmp     loc_1400063C6
0x140006309  lea     rdx, [rsp+38h+var_18]
0x14000630e  mov     [rsp+38h+var_18], r8
0x140006313  mov     rcx, r9
0x140006316  mov     [rsp+38h+var_10], 0
0x14000631b  call    sub_140007C98
0x140006320  jmp     loc_1400063C6
0x140006325  mov     al, [rdx+308h]
0x14000632b  mov     edx, 7F800000h
0x140006330  neg     al
0x140006332  mov     eax, 80000000h
0x140006337  sbb     ecx, ecx
0x140006339  and     ecx, eax
0x14000633b  mov     eax, [r8]
0x14000633e  add     ecx, edx
0x140006340  and     eax, edx
0x140006342  or      ecx, eax
0x140006344  and     ecx, 0FF800001h
0x14000634a  or      ecx, 1
0x14000634d  jmp     loc_1400062A9
0x140006352  sub     ecx, 6
0x140006355  jz      short loc_1400063BD
0x140006357  sub     ecx, 1
0x14000635a  jz      short loc_1400063B2
0x14000635c  sub     ecx, 1
0x14000635f  jz      short loc_140006395
0x140006361  cmp     ecx, 1
0x140006364  jnz     short loc_1400063B6
0x140006366  mov     al, [rdx+308h]
0x14000636c  mov     edx, 7F800000h
0x140006371  neg     al
0x140006373  mov     eax, 80000000h
0x140006378  sbb     ecx, ecx
0x14000637a  and     ecx, eax
0x14000637c  mov     eax, [r8]
0x14000637f  and     eax, edx
0x140006381  add     ecx, edx
0x140006383  or      ecx, eax
0x140006385  mov     eax, 3
0x14000638a  and     ecx, 0FF800000h
0x140006390  mov     [r8], ecx
0x140006393  jmp     short loc_1400063C6
0x140006395  mov     al, [rdx+308h]
0x14000639b  neg     al
0x14000639d  mov     eax, 80000000h
0x1400063a2  sbb     ecx, ecx
0x1400063a4  and     ecx, eax
0x1400063a6  and     ecx, eax
0x1400063a8  mov     eax, 2
0x1400063ad  mov     [r8], ecx
0x1400063b0  jmp     short loc_1400063C6
0x1400063b2  and     dword ptr [r8], 0
0x1400063b6  mov     eax, 1
0x1400063bb  jmp     short loc_1400063C6
0x1400063bd  mov     dword ptr [r8], 0FFC00000h
0x1400063c4  xor     eax, eax
0x1400063c6  add     rsp, 38h
0x1400063ca  retn
```
