# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x140061bd4`
- end: `0x140061e88`
- name: `??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `692`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *, char **, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400639a4`

## callees

- `0x14006147c`
- `0x140061534`
- `0x1400616b4`
- `0x140061bd4`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,0>(
        __crt_cached_ptd_host *a1,
        char **a2,
        __int64 a3,
        __int64 a4)
{
  char *v4; // r12
  unsigned int v5; // ebp
  char **v6; // rbx
  char **v8; // rcx
  char v9; // si
  char *v10; // rcx
  unsigned int v11; // r14d
  int v12; // edi
  int v13; // eax
  char *v14; // r8
  int v15; // eax
  int v16; // eax
  char *v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rcx
  BOOL v21; // ecx
  bool v22; // cf
  bool v23; // zf
  char **v24; // rax
  int v26; // eax
  int v27; // ecx
  char **v28; // rdx
  char **v29; // rax

  v4 = *a2;
  v5 = a3;
  v6 = a2;
  if ( !*a2 )
  {
    *(_DWORD *)sub_1400616B4(a1, a2, a3, a4) = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( (_DWORD)a3 && (unsigned int)(a3 - 2) > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    sub_14006147C(0, 0, 0, 0, 0, a1);
LABEL_6:
    v8 = (char **)v6[1];
    if ( v8 )
      *v8 = *v6;
    return 0;
  }
  v9 = *v4;
  v10 = v4 + 1;
  v11 = 0;
  *a2 = v4 + 1;
  v12 = (unsigned __int8)a4 | 2;
  if ( v9 == 45 || (v12 = (unsigned __int8)a4, v9 == 43) )
  {
    v9 = *v10;
    v10 = v4 + 2;
    *a2 = v4 + 2;
  }
  if ( (a3 & 0xFFFFFFEF) == 0 )
  {
    if ( (unsigned __int8)(v9 - 48) > 9u )
    {
      if ( (unsigned __int8)(v9 - 97) > 0x19u )
      {
        if ( (unsigned __int8)(v9 - 65) > 0x19u )
          goto LABEL_26;
        v13 = v9 - 55;
      }
      else
      {
        v13 = v9 - 87;
      }
    }
    else
    {
      v13 = v9 - 48;
    }
    if ( !v13 )
    {
      LOBYTE(a2) = *v10;
      v14 = v10 + 1;
      *v6 = v10 + 1;
      if ( (((_BYTE)a2 - 88) & 0xDF) != 0 )
      {
        *v6 = v10;
        v15 = 8;
        if ( v5 )
          v15 = v5;
        v5 = v15;
        if ( (_BYTE)a2 && *v10 != (_BYTE)a2 )
        {
          *(_DWORD *)sub_1400616B4(v10, a2, v14, a4) = 22;
          invalid_parameter_noinfo();
        }
        goto LABEL_30;
      }
      v9 = *v14;
      *v6 = v10 + 2;
      v16 = 16;
      goto LABEL_27;
    }
LABEL_26:
    v16 = 10;
LABEL_27:
    if ( v5 )
      v16 = v5;
    v5 = v16;
  }
LABEL_30:
  v17 = *v6;
  v18 = 0xFFFFFFFF % v5;
  v19 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( (unsigned __int8)(v9 - 48) > 9u )
    {
      if ( (unsigned __int8)(v9 - 97) > 0x19u )
        v20 = (unsigned __int8)(v9 - 65) > 0x19u ? 0xFFFFFFFFLL : (unsigned int)(v9 - 55);
      else
        v20 = (unsigned int)(v9 - 87);
    }
    else
    {
      v20 = (unsigned int)(v9 - 48);
    }
    if ( (unsigned int)v20 >= v5 )
      break;
    v9 = *v17;
    v18 = v5 * v11 + (unsigned int)v20;
    v21 = (unsigned int)v18 < v5 * v11;
    v22 = v11 < (unsigned int)v19;
    v23 = v11 == (_DWORD)v19;
    v11 = v18;
    v12 |= (4 * (!v22 && !v23 || v21)) | 8;
    *v6 = ++v17;
  }
  *v6 = v17 - 1;
  if ( v9 && *(v17 - 1) != v9 )
  {
    *(_DWORD *)sub_1400616B4(v20, v18, v17, v19) = 22;
    invalid_parameter_noinfo();
  }
  if ( (v12 & 8) == 0 )
  {
    v24 = (char **)v6[1];
    *v6 = v4;
    if ( v24 )
      *v24 = v4;
    return 0;
  }
  if ( (v12 & 4) != 0 )
  {
    v26 = 1;
    v27 = v12;
    goto LABEL_55;
  }
  if ( (v12 & 1) == 0 )
  {
    if ( (v12 & 2) == 0 )
      goto LABEL_66;
    goto LABEL_65;
  }
  if ( (v12 & 2) == 0 )
  {
    if ( v11 <= 0x7FFFFFFF )
    {
LABEL_66:
      v29 = (char **)v6[1];
      if ( v29 )
        *v29 = *v6;
      return v11;
    }
    goto LABEL_54;
  }
  if ( v11 <= 0x80000000 )
  {
LABEL_65:
    v11 = -v11;
    goto LABEL_66;
  }
LABEL_54:
  v27 = 1;
  v26 = v12;
LABEL_55:
  *((_BYTE *)a1 + 48) = 1;
  *((_DWORD *)a1 + 11) = 34;
  if ( (v27 & v26) == 0 )
  {
    v11 = -1;
    goto LABEL_66;
  }
  v28 = (char **)v6[1];
  if ( (v12 & 2) != 0 )
  {
    if ( v28 )
      *v28 = *v6;
    return 0x80000000LL;
  }
  else
  {
    if ( v28 )
      *v28 = *v6;
    return 0x7FFFFFFF;
  }
}

```

## disassembly

```asm
0x140061bd4  mov     [rsp+arg_0], rbx
0x140061bd9  mov     [rsp+arg_8], rbp
0x140061bde  mov     [rsp+arg_10], rsi
0x140061be3  push    rdi
0x140061be4  push    r12
0x140061be6  push    r13
0x140061be8  push    r14
0x140061bea  push    r15
0x140061bec  sub     rsp, 30h
0x140061bf0  mov     r12, [rdx]
0x140061bf3  mov     ebp, r8d
0x140061bf6  mov     rbx, rdx
0x140061bf9  mov     r13, rcx
0x140061bfc  test    r12, r12
0x140061bff  jnz     short loc_140061C13
0x140061c01  call    sub_1400616B4
0x140061c06  mov     dword ptr [rax], 16h
0x140061c0c  call    _invalid_parameter_noinfo
0x140061c11  jmp     short loc_140061C45
0x140061c13  test    ebp, ebp
0x140061c15  jz      short loc_140061C5D
0x140061c17  lea     eax, [r8-2]
0x140061c1b  cmp     eax, 22h ; '"'
0x140061c1e  jbe     short loc_140061C5D
0x140061c20  mov     byte ptr [rcx+30h], 1
0x140061c24  xor     r9d, r9d; LineNo
0x140061c27  mov     dword ptr [rcx+2Ch], 16h
0x140061c2e  xor     r8d, r8d; FileName
0x140061c31  mov     [rsp+58h+var_30], r13; __crt_cached_ptd_host *
0x140061c36  xor     ecx, ecx; Expression
0x140061c38  and     [rsp+58h+var_38], 0
0x140061c3e  xor     edx, edx; FunctionName
0x140061c40  call    sub_14006147C
0x140061c45  mov     rcx, [rbx+8]
0x140061c49  test    rcx, rcx
0x140061c4c  jz      loc_140061DD0
0x140061c52  mov     rax, [rbx]
0x140061c55  mov     [rcx], rax
0x140061c58  jmp     loc_140061DD0
0x140061c5d  mov     sil, [r12]
0x140061c61  lea     rcx, [r12+1]
0x140061c66  xor     r14d, r14d
0x140061c69  movzx   eax, r9b
0x140061c6d  mov     edi, eax
0x140061c6f  mov     [rdx], rcx
0x140061c72  lea     r15d, [r14+2]
0x140061c76  or      edi, r15d
0x140061c79  cmp     sil, 2Dh ; '-'
0x140061c7d  cmovnz  edi, eax
0x140061c80  jz      short loc_140061C88
0x140061c82  cmp     sil, 2Bh ; '+'
0x140061c86  jnz     short loc_140061C91
0x140061c88  mov     sil, [rcx]
0x140061c8b  inc     rcx
0x140061c8e  mov     [rdx], rcx
0x140061c91  test    ebp, 0FFFFFFEFh
0x140061c97  jnz     loc_140061D25
0x140061c9d  lea     eax, [rsi-30h]
0x140061ca0  cmp     al, 9
0x140061ca2  ja      short loc_140061CAD
0x140061ca4  movsx   eax, sil
0x140061ca8  add     eax, 0FFFFFFD0h
0x140061cab  jmp     short loc_140061CCB
0x140061cad  lea     eax, [rsi-61h]
0x140061cb0  cmp     al, 19h
0x140061cb2  ja      short loc_140061CBD
0x140061cb4  movsx   eax, sil
0x140061cb8  add     eax, 0FFFFFFA9h
0x140061cbb  jmp     short loc_140061CCB
0x140061cbd  lea     eax, [rsi-41h]
0x140061cc0  cmp     al, 19h
0x140061cc2  ja      short loc_140061D19
0x140061cc4  movsx   eax, sil
0x140061cc8  add     eax, 0FFFFFFC9h
0x140061ccb  test    eax, eax
0x140061ccd  jnz     short loc_140061D19
0x140061ccf  mov     dl, [rcx]
0x140061cd1  lea     r8, [rcx+1]
0x140061cd5  mov     [rbx], r8
0x140061cd8  lea     eax, [rdx-58h]
0x140061cdb  test    al, 0DFh
0x140061cdd  jz      short loc_140061D08
0x140061cdf  test    ebp, ebp
0x140061ce1  mov     [rbx], rcx
0x140061ce4  mov     eax, 8
0x140061ce9  cmovnz  eax, ebp
0x140061cec  mov     ebp, eax
0x140061cee  test    dl, dl
0x140061cf0  jz      short loc_140061D25
0x140061cf2  cmp     [rcx], dl
0x140061cf4  jz      short loc_140061D25
0x140061cf6  call    sub_1400616B4
0x140061cfb  mov     dword ptr [rax], 16h
0x140061d01  call    _invalid_parameter_noinfo
0x140061d06  jmp     short loc_140061D25
0x140061d08  mov     sil, [r8]
0x140061d0b  lea     rax, [r8+1]
0x140061d0f  mov     [rbx], rax
0x140061d12  mov     eax, 10h
0x140061d17  jmp     short loc_140061D1E
0x140061d19  mov     eax, 0Ah
0x140061d1e  test    ebp, ebp
0x140061d20  cmovnz  eax, ebp
0x140061d23  mov     ebp, eax
0x140061d25  mov     r8, [rbx]
0x140061d28  xor     edx, edx
0x140061d2a  or      eax, 0FFFFFFFFh
0x140061d2d  div     ebp
0x140061d2f  mov     r9d, eax
0x140061d32  lea     ecx, [rsi-30h]
0x140061d35  cmp     cl, 9
0x140061d38  ja      short loc_140061D43
0x140061d3a  movsx   ecx, sil
0x140061d3e  add     ecx, 0FFFFFFD0h
0x140061d41  jmp     short loc_140061D66
0x140061d43  lea     eax, [rsi-61h]
0x140061d46  cmp     al, 19h
0x140061d48  ja      short loc_140061D53
0x140061d4a  movsx   ecx, sil
0x140061d4e  add     ecx, 0FFFFFFA9h
0x140061d51  jmp     short loc_140061D66
0x140061d53  lea     eax, [rsi-41h]
0x140061d56  cmp     al, 19h
0x140061d58  ja      short loc_140061D63
0x140061d5a  movsx   ecx, sil
0x140061d5e  add     ecx, 0FFFFFFC9h
0x140061d61  jmp     short loc_140061D66
0x140061d63  or      ecx, 0FFFFFFFFh
0x140061d66  cmp     ecx, ebp
0x140061d68  jnb     short loc_140061D9A
0x140061d6a  mov     sil, [r8]
0x140061d6d  mov     eax, r14d
0x140061d70  imul    eax, ebp
0x140061d73  lea     edx, [rax+rcx]
0x140061d76  xor     ecx, ecx
0x140061d78  cmp     edx, eax
0x140061d7a  setb    cl
0x140061d7d  xor     eax, eax
0x140061d7f  cmp     r14d, r9d
0x140061d82  mov     r14d, edx
0x140061d85  setnbe  al
0x140061d88  or      ecx, eax
0x140061d8a  shl     ecx, 2
0x140061d8d  or      ecx, 8
0x140061d90  or      edi, ecx
0x140061d92  inc     r8
0x140061d95  mov     [rbx], r8
0x140061d98  jmp     short loc_140061D32
0x140061d9a  lea     rax, [r8-1]
0x140061d9e  mov     [rbx], rax
0x140061da1  test    sil, sil
0x140061da4  jz      short loc_140061DBB
0x140061da6  cmp     [rax], sil
0x140061da9  jz      short loc_140061DBB
0x140061dab  call    sub_1400616B4
0x140061db0  mov     dword ptr [rax], 16h
0x140061db6  call    _invalid_parameter_noinfo
0x140061dbb  test    dil, 8
0x140061dbf  jnz     short loc_140061DD7
0x140061dc1  mov     rax, [rbx+8]
0x140061dc5  mov     [rbx], r12
0x140061dc8  test    rax, rax
0x140061dcb  jz      short loc_140061DD0
0x140061dcd  mov     [rax], r12
0x140061dd0  xor     eax, eax
0x140061dd2  jmp     loc_140061E6B
0x140061dd7  mov     r8d, 80000000h
0x140061ddd  lea     r9d, [r8-1]
0x140061de1  test    dil, 4
0x140061de5  jz      short loc_140061DF0
0x140061de7  mov     eax, 1
0x140061dec  mov     ecx, edi
0x140061dee  jmp     short loc_140061E0E
0x140061df0  test    dil, 1
0x140061df4  jz      short loc_140061E51
0x140061df6  test    r15b, dil
0x140061df9  jz      short loc_140061E02
0x140061dfb  cmp     r14d, r8d
0x140061dfe  jbe     short loc_140061E56
0x140061e00  jmp     short loc_140061E07
0x140061e02  cmp     r14d, r9d
0x140061e05  jbe     short loc_140061E59
0x140061e07  mov     ecx, 1
0x140061e0c  mov     eax, edi
0x140061e0e  and     r15d, edi
0x140061e11  mov     byte ptr [r13+30h], 1
0x140061e16  mov     dword ptr [r13+2Ch], 22h ; '"'
0x140061e1e  test    eax, ecx
0x140061e20  jnz     short loc_140061E28
0x140061e22  or      r14d, 0FFFFFFFFh
0x140061e26  jmp     short loc_140061E59
0x140061e28  mov     rdx, [rbx+8]
0x140061e2c  test    r15d, r15d
0x140061e2f  jz      short loc_140061E41
0x140061e31  test    rdx, rdx
0x140061e34  jz      short loc_140061E3C
0x140061e36  mov     rcx, [rbx]
0x140061e39  mov     [rdx], rcx
0x140061e3c  mov     eax, r8d
0x140061e3f  jmp     short loc_140061E6B
0x140061e41  test    rdx, rdx
0x140061e44  jz      short loc_140061E4C
0x140061e46  mov     rcx, [rbx]
0x140061e49  mov     [rdx], rcx
0x140061e4c  mov     eax, r9d
0x140061e4f  jmp     short loc_140061E6B
0x140061e51  test    r15b, dil
0x140061e54  jz      short loc_140061E59
0x140061e56  neg     r14d
0x140061e59  mov     rax, [rbx+8]
0x140061e5d  test    rax, rax
0x140061e60  jz      short loc_140061E68
0x140061e62  mov     rcx, [rbx]
0x140061e65  mov     [rax], rcx
0x140061e68  mov     eax, r14d
0x140061e6b  mov     rbx, [rsp+58h+arg_0]
0x140061e70  mov     rbp, [rsp+58h+arg_8]
0x140061e75  mov     rsi, [rsp+58h+arg_10]
0x140061e7a  add     rsp, 30h
0x140061e7e  pop     r15
0x140061e80  pop     r14
0x140061e82  pop     r13
0x140061e84  pop     r12
0x140061e86  pop     rdi
0x140061e87  retn
```
