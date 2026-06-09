# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x18003871c`
- end: `0x1800389d0`
- name: `??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `692`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x180033408`
- `0x18004308c`
- `0x18004311c`
- `0x1800431ac`
- `0x18004323c`
- `0x1800432cc`
- `0x18004335c`
- `0x180052100`
- `0x18005226c`
- `0x180052708`
- `0x180052874`
- `0x180052f94`
- `0x1800530d8`

## callees

- `0x1800073e8`
- `0x1800074a0`
- `0x180007788`
- `0x18003871c`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,0>(
        __crt_cached_ptd_host *a1,
        __int64 a2,
        int a3,
        unsigned __int8 a4)
{
  char *v4; // r12
  unsigned int v5; // ebp
  _QWORD *v8; // rcx
  char v9; // si
  char *v10; // rcx
  unsigned int v11; // r14d
  int v12; // edi
  int v13; // eax
  char v14; // dl
  int v15; // eax
  int v16; // eax
  char *v17; // r8
  unsigned int v18; // r9d
  unsigned int v19; // ecx
  unsigned int v20; // edx
  BOOL v21; // ecx
  bool v22; // cf
  bool v23; // zf
  char **v24; // rax
  int v26; // eax
  int v27; // ecx
  _QWORD *v28; // rdx
  _QWORD *v29; // rax

  v4 = *(char **)a2;
  v5 = a3;
  if ( !*(_QWORD *)a2 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && (unsigned int)(a3 - 2) > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, a1);
LABEL_6:
    v8 = *(_QWORD **)(a2 + 8);
    if ( v8 )
      *v8 = *(_QWORD *)a2;
    return 0;
  }
  v9 = *v4;
  v10 = v4 + 1;
  v11 = 0;
  *(_QWORD *)a2 = v4 + 1;
  v12 = a4 | 2;
  if ( v9 == 45 || (v12 = a4, v9 == 43) )
  {
    v9 = *v10;
    v10 = v4 + 2;
    *(_QWORD *)a2 = v4 + 2;
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
      v14 = *v10;
      *(_QWORD *)a2 = v10 + 1;
      if ( ((v14 - 88) & 0xDF) != 0 )
      {
        *(_QWORD *)a2 = v10;
        v15 = 8;
        if ( a3 )
          v15 = a3;
        v5 = v15;
        if ( v14 && *v10 != v14 )
        {
          *errno() = 22;
          invalid_parameter_noinfo();
        }
        goto LABEL_30;
      }
      v9 = v10[1];
      *(_QWORD *)a2 = v10 + 2;
      v16 = 16;
      goto LABEL_27;
    }
LABEL_26:
    v16 = 10;
LABEL_27:
    if ( a3 )
      v16 = a3;
    v5 = v16;
  }
LABEL_30:
  v17 = *(char **)a2;
  v18 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( (unsigned __int8)(v9 - 48) > 9u )
    {
      if ( (unsigned __int8)(v9 - 97) > 0x19u )
        v19 = (unsigned __int8)(v9 - 65) > 0x19u ? -1 : v9 - 55;
      else
        v19 = v9 - 87;
    }
    else
    {
      v19 = v9 - 48;
    }
    if ( v19 >= v5 )
      break;
    v9 = *v17;
    v20 = v5 * v11 + v19;
    v21 = v20 < v5 * v11;
    v22 = v11 < v18;
    v23 = v11 == v18;
    v11 = v20;
    v12 |= (4 * (!v22 && !v23 || v21)) | 8;
    *(_QWORD *)a2 = ++v17;
  }
  *(_QWORD *)a2 = v17 - 1;
  if ( v9 && *(v17 - 1) != v9 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
  if ( (v12 & 8) == 0 )
  {
    v24 = *(char ***)(a2 + 8);
    *(_QWORD *)a2 = v4;
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
      v29 = *(_QWORD **)(a2 + 8);
      if ( v29 )
        *v29 = *(_QWORD *)a2;
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
  v28 = *(_QWORD **)(a2 + 8);
  if ( (v12 & 2) != 0 )
  {
    if ( v28 )
      *v28 = *(_QWORD *)a2;
    return 0x80000000LL;
  }
  else
  {
    if ( v28 )
      *v28 = *(_QWORD *)a2;
    return 0x7FFFFFFF;
  }
}

```

## disassembly

```asm
0x18003871c  mov     [rsp+arg_0], rbx
0x180038721  mov     [rsp+arg_8], rbp
0x180038726  mov     [rsp+arg_10], rsi
0x18003872b  push    rdi
0x18003872c  push    r12
0x18003872e  push    r13
0x180038730  push    r14
0x180038732  push    r15
0x180038734  sub     rsp, 30h
0x180038738  mov     r12, [rdx]
0x18003873b  mov     ebp, r8d
0x18003873e  mov     rbx, rdx
0x180038741  mov     r13, rcx
0x180038744  test    r12, r12
0x180038747  jnz     short loc_18003875B
0x180038749  call    _errno
0x18003874e  mov     dword ptr [rax], 16h
0x180038754  call    _invalid_parameter_noinfo
0x180038759  jmp     short loc_18003878D
0x18003875b  test    ebp, ebp
0x18003875d  jz      short loc_1800387A5
0x18003875f  lea     eax, [r8-2]
0x180038763  cmp     eax, 22h ; '"'
0x180038766  jbe     short loc_1800387A5
0x180038768  mov     byte ptr [rcx+30h], 1
0x18003876c  xor     r9d, r9d; LineNo
0x18003876f  mov     dword ptr [rcx+2Ch], 16h
0x180038776  xor     r8d, r8d; FileName
0x180038779  mov     [rsp+58h+var_30], r13; __crt_cached_ptd_host *
0x18003877e  xor     ecx, ecx; Expression
0x180038780  and     [rsp+58h+var_38], 0
0x180038786  xor     edx, edx; FunctionName
0x180038788  call    _invalid_parameter_internal
0x18003878d  mov     rcx, [rbx+8]
0x180038791  test    rcx, rcx
0x180038794  jz      loc_180038918
0x18003879a  mov     rax, [rbx]
0x18003879d  mov     [rcx], rax
0x1800387a0  jmp     loc_180038918
0x1800387a5  mov     sil, [r12]
0x1800387a9  lea     rcx, [r12+1]
0x1800387ae  xor     r14d, r14d
0x1800387b1  movzx   eax, r9b
0x1800387b5  mov     edi, eax
0x1800387b7  mov     [rdx], rcx
0x1800387ba  lea     r15d, [r14+2]
0x1800387be  or      edi, r15d
0x1800387c1  cmp     sil, 2Dh ; '-'
0x1800387c5  cmovnz  edi, eax
0x1800387c8  jz      short loc_1800387D0
0x1800387ca  cmp     sil, 2Bh ; '+'
0x1800387ce  jnz     short loc_1800387D9
0x1800387d0  mov     sil, [rcx]
0x1800387d3  inc     rcx
0x1800387d6  mov     [rdx], rcx
0x1800387d9  test    ebp, 0FFFFFFEFh
0x1800387df  jnz     loc_18003886D
0x1800387e5  lea     eax, [rsi-30h]
0x1800387e8  cmp     al, 9
0x1800387ea  ja      short loc_1800387F5
0x1800387ec  movsx   eax, sil
0x1800387f0  add     eax, 0FFFFFFD0h
0x1800387f3  jmp     short loc_180038813
0x1800387f5  lea     eax, [rsi-61h]
0x1800387f8  cmp     al, 19h
0x1800387fa  ja      short loc_180038805
0x1800387fc  movsx   eax, sil
0x180038800  add     eax, 0FFFFFFA9h
0x180038803  jmp     short loc_180038813
0x180038805  lea     eax, [rsi-41h]
0x180038808  cmp     al, 19h
0x18003880a  ja      short loc_180038861
0x18003880c  movsx   eax, sil
0x180038810  add     eax, 0FFFFFFC9h
0x180038813  test    eax, eax
0x180038815  jnz     short loc_180038861
0x180038817  mov     dl, [rcx]
0x180038819  lea     r8, [rcx+1]
0x18003881d  mov     [rbx], r8
0x180038820  lea     eax, [rdx-58h]
0x180038823  test    al, 0DFh
0x180038825  jz      short loc_180038850
0x180038827  test    ebp, ebp
0x180038829  mov     [rbx], rcx
0x18003882c  mov     eax, 8
0x180038831  cmovnz  eax, ebp
0x180038834  mov     ebp, eax
0x180038836  test    dl, dl
0x180038838  jz      short loc_18003886D
0x18003883a  cmp     [rcx], dl
0x18003883c  jz      short loc_18003886D
0x18003883e  call    _errno
0x180038843  mov     dword ptr [rax], 16h
0x180038849  call    _invalid_parameter_noinfo
0x18003884e  jmp     short loc_18003886D
0x180038850  mov     sil, [r8]
0x180038853  lea     rax, [r8+1]
0x180038857  mov     [rbx], rax
0x18003885a  mov     eax, 10h
0x18003885f  jmp     short loc_180038866
0x180038861  mov     eax, 0Ah
0x180038866  test    ebp, ebp
0x180038868  cmovnz  eax, ebp
0x18003886b  mov     ebp, eax
0x18003886d  mov     r8, [rbx]
0x180038870  xor     edx, edx
0x180038872  or      eax, 0FFFFFFFFh
0x180038875  div     ebp
0x180038877  mov     r9d, eax
0x18003887a  lea     ecx, [rsi-30h]
0x18003887d  cmp     cl, 9
0x180038880  ja      short loc_18003888B
0x180038882  movsx   ecx, sil
0x180038886  add     ecx, 0FFFFFFD0h
0x180038889  jmp     short loc_1800388AE
0x18003888b  lea     eax, [rsi-61h]
0x18003888e  cmp     al, 19h
0x180038890  ja      short loc_18003889B
0x180038892  movsx   ecx, sil
0x180038896  add     ecx, 0FFFFFFA9h
0x180038899  jmp     short loc_1800388AE
0x18003889b  lea     eax, [rsi-41h]
0x18003889e  cmp     al, 19h
0x1800388a0  ja      short loc_1800388AB
0x1800388a2  movsx   ecx, sil
0x1800388a6  add     ecx, 0FFFFFFC9h
0x1800388a9  jmp     short loc_1800388AE
0x1800388ab  or      ecx, 0FFFFFFFFh
0x1800388ae  cmp     ecx, ebp
0x1800388b0  jnb     short loc_1800388E2
0x1800388b2  mov     sil, [r8]
0x1800388b5  mov     eax, r14d
0x1800388b8  imul    eax, ebp
0x1800388bb  lea     edx, [rax+rcx]
0x1800388be  xor     ecx, ecx
0x1800388c0  cmp     edx, eax
0x1800388c2  setb    cl
0x1800388c5  xor     eax, eax
0x1800388c7  cmp     r14d, r9d
0x1800388ca  mov     r14d, edx
0x1800388cd  setnbe  al
0x1800388d0  or      ecx, eax
0x1800388d2  shl     ecx, 2
0x1800388d5  or      ecx, 8
0x1800388d8  or      edi, ecx
0x1800388da  inc     r8
0x1800388dd  mov     [rbx], r8
0x1800388e0  jmp     short loc_18003887A
0x1800388e2  lea     rax, [r8-1]
0x1800388e6  mov     [rbx], rax
0x1800388e9  test    sil, sil
0x1800388ec  jz      short loc_180038903
0x1800388ee  cmp     [rax], sil
0x1800388f1  jz      short loc_180038903
0x1800388f3  call    _errno
0x1800388f8  mov     dword ptr [rax], 16h
0x1800388fe  call    _invalid_parameter_noinfo
0x180038903  test    dil, 8
0x180038907  jnz     short loc_18003891F
0x180038909  mov     rax, [rbx+8]
0x18003890d  mov     [rbx], r12
0x180038910  test    rax, rax
0x180038913  jz      short loc_180038918
0x180038915  mov     [rax], r12
0x180038918  xor     eax, eax
0x18003891a  jmp     loc_1800389B3
0x18003891f  mov     r8d, 80000000h
0x180038925  lea     r9d, [r8-1]
0x180038929  test    dil, 4
0x18003892d  jz      short loc_180038938
0x18003892f  mov     eax, 1
0x180038934  mov     ecx, edi
0x180038936  jmp     short loc_180038956
0x180038938  test    dil, 1
0x18003893c  jz      short loc_180038999
0x18003893e  test    r15b, dil
0x180038941  jz      short loc_18003894A
0x180038943  cmp     r14d, r8d
0x180038946  jbe     short loc_18003899E
0x180038948  jmp     short loc_18003894F
0x18003894a  cmp     r14d, r9d
0x18003894d  jbe     short loc_1800389A1
0x18003894f  mov     ecx, 1
0x180038954  mov     eax, edi
0x180038956  and     r15d, edi
0x180038959  mov     byte ptr [r13+30h], 1
0x18003895e  mov     dword ptr [r13+2Ch], 22h ; '"'
0x180038966  test    eax, ecx
0x180038968  jnz     short loc_180038970
0x18003896a  or      r14d, 0FFFFFFFFh
0x18003896e  jmp     short loc_1800389A1
0x180038970  mov     rdx, [rbx+8]
0x180038974  test    r15d, r15d
0x180038977  jz      short loc_180038989
0x180038979  test    rdx, rdx
0x18003897c  jz      short loc_180038984
0x18003897e  mov     rcx, [rbx]
0x180038981  mov     [rdx], rcx
0x180038984  mov     eax, r8d
0x180038987  jmp     short loc_1800389B3
0x180038989  test    rdx, rdx
0x18003898c  jz      short loc_180038994
0x18003898e  mov     rcx, [rbx]
0x180038991  mov     [rdx], rcx
0x180038994  mov     eax, r9d
0x180038997  jmp     short loc_1800389B3
0x180038999  test    r15b, dil
0x18003899c  jz      short loc_1800389A1
0x18003899e  neg     r14d
0x1800389a1  mov     rax, [rbx+8]
0x1800389a5  test    rax, rax
0x1800389a8  jz      short loc_1800389B0
0x1800389aa  mov     rcx, [rbx]
0x1800389ad  mov     [rax], rcx
0x1800389b0  mov     eax, r14d
0x1800389b3  mov     rbx, [rsp+58h+arg_0]
0x1800389b8  mov     rbp, [rsp+58h+arg_8]
0x1800389bd  mov     rsi, [rsp+58h+arg_10]
0x1800389c2  add     rsp, 30h
0x1800389c6  pop     r15
0x1800389c8  pop     r14
0x1800389ca  pop     r13
0x1800389cc  pop     r12
0x1800389ce  pop     rdi
0x1800389cf  retn
```
