# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x14000c9e4`
- end: `0x14000cc98`
- name: `??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `692`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000e7b4`

## callees

- `0x14000bea4`
- `0x14000bf5c`
- `0x14000c9e4`
- `0x1400120dc`

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
0x14000c9e4  mov     [rsp+arg_0], rbx
0x14000c9e9  mov     [rsp+arg_8], rbp
0x14000c9ee  mov     [rsp+arg_10], rsi
0x14000c9f3  push    rdi
0x14000c9f4  push    r12
0x14000c9f6  push    r13
0x14000c9f8  push    r14
0x14000c9fa  push    r15
0x14000c9fc  sub     rsp, 30h
0x14000ca00  mov     r12, [rdx]
0x14000ca03  mov     ebp, r8d
0x14000ca06  mov     rbx, rdx
0x14000ca09  mov     r13, rcx
0x14000ca0c  test    r12, r12
0x14000ca0f  jnz     short loc_14000CA23
0x14000ca11  call    _errno
0x14000ca16  mov     dword ptr [rax], 16h
0x14000ca1c  call    _invalid_parameter_noinfo
0x14000ca21  jmp     short loc_14000CA55
0x14000ca23  test    ebp, ebp
0x14000ca25  jz      short loc_14000CA6D
0x14000ca27  lea     eax, [r8-2]
0x14000ca2b  cmp     eax, 22h ; '"'
0x14000ca2e  jbe     short loc_14000CA6D
0x14000ca30  mov     byte ptr [rcx+30h], 1
0x14000ca34  xor     r9d, r9d; LineNo
0x14000ca37  mov     dword ptr [rcx+2Ch], 16h
0x14000ca3e  xor     r8d, r8d; FileName
0x14000ca41  mov     [rsp+58h+var_30], r13; __crt_cached_ptd_host *
0x14000ca46  xor     ecx, ecx; Expression
0x14000ca48  and     [rsp+58h+var_38], 0
0x14000ca4e  xor     edx, edx; FunctionName
0x14000ca50  call    _invalid_parameter_internal
0x14000ca55  mov     rcx, [rbx+8]
0x14000ca59  test    rcx, rcx
0x14000ca5c  jz      loc_14000CBE0
0x14000ca62  mov     rax, [rbx]
0x14000ca65  mov     [rcx], rax
0x14000ca68  jmp     loc_14000CBE0
0x14000ca6d  mov     sil, [r12]
0x14000ca71  lea     rcx, [r12+1]
0x14000ca76  xor     r14d, r14d
0x14000ca79  movzx   eax, r9b
0x14000ca7d  mov     edi, eax
0x14000ca7f  mov     [rdx], rcx
0x14000ca82  lea     r15d, [r14+2]
0x14000ca86  or      edi, r15d
0x14000ca89  cmp     sil, 2Dh ; '-'
0x14000ca8d  cmovnz  edi, eax
0x14000ca90  jz      short loc_14000CA98
0x14000ca92  cmp     sil, 2Bh ; '+'
0x14000ca96  jnz     short loc_14000CAA1
0x14000ca98  mov     sil, [rcx]
0x14000ca9b  inc     rcx
0x14000ca9e  mov     [rdx], rcx
0x14000caa1  test    ebp, 0FFFFFFEFh
0x14000caa7  jnz     loc_14000CB35
0x14000caad  lea     eax, [rsi-30h]
0x14000cab0  cmp     al, 9
0x14000cab2  ja      short loc_14000CABD
0x14000cab4  movsx   eax, sil
0x14000cab8  add     eax, 0FFFFFFD0h
0x14000cabb  jmp     short loc_14000CADB
0x14000cabd  lea     eax, [rsi-61h]
0x14000cac0  cmp     al, 19h
0x14000cac2  ja      short loc_14000CACD
0x14000cac4  movsx   eax, sil
0x14000cac8  add     eax, 0FFFFFFA9h
0x14000cacb  jmp     short loc_14000CADB
0x14000cacd  lea     eax, [rsi-41h]
0x14000cad0  cmp     al, 19h
0x14000cad2  ja      short loc_14000CB29
0x14000cad4  movsx   eax, sil
0x14000cad8  add     eax, 0FFFFFFC9h
0x14000cadb  test    eax, eax
0x14000cadd  jnz     short loc_14000CB29
0x14000cadf  mov     dl, [rcx]
0x14000cae1  lea     r8, [rcx+1]
0x14000cae5  mov     [rbx], r8
0x14000cae8  lea     eax, [rdx-58h]
0x14000caeb  test    al, 0DFh
0x14000caed  jz      short loc_14000CB18
0x14000caef  test    ebp, ebp
0x14000caf1  mov     [rbx], rcx
0x14000caf4  mov     eax, 8
0x14000caf9  cmovnz  eax, ebp
0x14000cafc  mov     ebp, eax
0x14000cafe  test    dl, dl
0x14000cb00  jz      short loc_14000CB35
0x14000cb02  cmp     [rcx], dl
0x14000cb04  jz      short loc_14000CB35
0x14000cb06  call    _errno
0x14000cb0b  mov     dword ptr [rax], 16h
0x14000cb11  call    _invalid_parameter_noinfo
0x14000cb16  jmp     short loc_14000CB35
0x14000cb18  mov     sil, [r8]
0x14000cb1b  lea     rax, [r8+1]
0x14000cb1f  mov     [rbx], rax
0x14000cb22  mov     eax, 10h
0x14000cb27  jmp     short loc_14000CB2E
0x14000cb29  mov     eax, 0Ah
0x14000cb2e  test    ebp, ebp
0x14000cb30  cmovnz  eax, ebp
0x14000cb33  mov     ebp, eax
0x14000cb35  mov     r8, [rbx]
0x14000cb38  xor     edx, edx
0x14000cb3a  or      eax, 0FFFFFFFFh
0x14000cb3d  div     ebp
0x14000cb3f  mov     r9d, eax
0x14000cb42  lea     ecx, [rsi-30h]
0x14000cb45  cmp     cl, 9
0x14000cb48  ja      short loc_14000CB53
0x14000cb4a  movsx   ecx, sil
0x14000cb4e  add     ecx, 0FFFFFFD0h
0x14000cb51  jmp     short loc_14000CB76
0x14000cb53  lea     eax, [rsi-61h]
0x14000cb56  cmp     al, 19h
0x14000cb58  ja      short loc_14000CB63
0x14000cb5a  movsx   ecx, sil
0x14000cb5e  add     ecx, 0FFFFFFA9h
0x14000cb61  jmp     short loc_14000CB76
0x14000cb63  lea     eax, [rsi-41h]
0x14000cb66  cmp     al, 19h
0x14000cb68  ja      short loc_14000CB73
0x14000cb6a  movsx   ecx, sil
0x14000cb6e  add     ecx, 0FFFFFFC9h
0x14000cb71  jmp     short loc_14000CB76
0x14000cb73  or      ecx, 0FFFFFFFFh
0x14000cb76  cmp     ecx, ebp
0x14000cb78  jnb     short loc_14000CBAA
0x14000cb7a  mov     sil, [r8]
0x14000cb7d  mov     eax, r14d
0x14000cb80  imul    eax, ebp
0x14000cb83  lea     edx, [rax+rcx]
0x14000cb86  xor     ecx, ecx
0x14000cb88  cmp     edx, eax
0x14000cb8a  setb    cl
0x14000cb8d  xor     eax, eax
0x14000cb8f  cmp     r14d, r9d
0x14000cb92  mov     r14d, edx
0x14000cb95  setnbe  al
0x14000cb98  or      ecx, eax
0x14000cb9a  shl     ecx, 2
0x14000cb9d  or      ecx, 8
0x14000cba0  or      edi, ecx
0x14000cba2  inc     r8
0x14000cba5  mov     [rbx], r8
0x14000cba8  jmp     short loc_14000CB42
0x14000cbaa  lea     rax, [r8-1]
0x14000cbae  mov     [rbx], rax
0x14000cbb1  test    sil, sil
0x14000cbb4  jz      short loc_14000CBCB
0x14000cbb6  cmp     [rax], sil
0x14000cbb9  jz      short loc_14000CBCB
0x14000cbbb  call    _errno
0x14000cbc0  mov     dword ptr [rax], 16h
0x14000cbc6  call    _invalid_parameter_noinfo
0x14000cbcb  test    dil, 8
0x14000cbcf  jnz     short loc_14000CBE7
0x14000cbd1  mov     rax, [rbx+8]
0x14000cbd5  mov     [rbx], r12
0x14000cbd8  test    rax, rax
0x14000cbdb  jz      short loc_14000CBE0
0x14000cbdd  mov     [rax], r12
0x14000cbe0  xor     eax, eax
0x14000cbe2  jmp     loc_14000CC7B
0x14000cbe7  mov     r8d, 80000000h
0x14000cbed  lea     r9d, [r8-1]
0x14000cbf1  test    dil, 4
0x14000cbf5  jz      short loc_14000CC00
0x14000cbf7  mov     eax, 1
0x14000cbfc  mov     ecx, edi
0x14000cbfe  jmp     short loc_14000CC1E
0x14000cc00  test    dil, 1
0x14000cc04  jz      short loc_14000CC61
0x14000cc06  test    r15b, dil
0x14000cc09  jz      short loc_14000CC12
0x14000cc0b  cmp     r14d, r8d
0x14000cc0e  jbe     short loc_14000CC66
0x14000cc10  jmp     short loc_14000CC17
0x14000cc12  cmp     r14d, r9d
0x14000cc15  jbe     short loc_14000CC69
0x14000cc17  mov     ecx, 1
0x14000cc1c  mov     eax, edi
0x14000cc1e  and     r15d, edi
0x14000cc21  mov     byte ptr [r13+30h], 1
0x14000cc26  mov     dword ptr [r13+2Ch], 22h ; '"'
0x14000cc2e  test    eax, ecx
0x14000cc30  jnz     short loc_14000CC38
0x14000cc32  or      r14d, 0FFFFFFFFh
0x14000cc36  jmp     short loc_14000CC69
0x14000cc38  mov     rdx, [rbx+8]
0x14000cc3c  test    r15d, r15d
0x14000cc3f  jz      short loc_14000CC51
0x14000cc41  test    rdx, rdx
0x14000cc44  jz      short loc_14000CC4C
0x14000cc46  mov     rcx, [rbx]
0x14000cc49  mov     [rdx], rcx
0x14000cc4c  mov     eax, r8d
0x14000cc4f  jmp     short loc_14000CC7B
0x14000cc51  test    rdx, rdx
0x14000cc54  jz      short loc_14000CC5C
0x14000cc56  mov     rcx, [rbx]
0x14000cc59  mov     [rdx], rcx
0x14000cc5c  mov     eax, r9d
0x14000cc5f  jmp     short loc_14000CC7B
0x14000cc61  test    r15b, dil
0x14000cc64  jz      short loc_14000CC69
0x14000cc66  neg     r14d
0x14000cc69  mov     rax, [rbx+8]
0x14000cc6d  test    rax, rax
0x14000cc70  jz      short loc_14000CC78
0x14000cc72  mov     rcx, [rbx]
0x14000cc75  mov     [rax], rcx
0x14000cc78  mov     eax, r14d
0x14000cc7b  mov     rbx, [rsp+58h+arg_0]
0x14000cc80  mov     rbp, [rsp+58h+arg_8]
0x14000cc85  mov     rsi, [rsp+58h+arg_10]
0x14000cc8a  add     rsp, 30h
0x14000cc8e  pop     r15
0x14000cc90  pop     r14
0x14000cc92  pop     r13
0x14000cc94  pop     r12
0x14000cc96  pop     rdi
0x14000cc97  retn
```
