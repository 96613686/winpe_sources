# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,0>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x1400101b0`
- end: `0x140010464`
- name: `??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$0A@@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `692`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *, char **, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140011fe8`

## callees

- `0x1400101b0`
- `0x140015fe4`
- `0x14001609c`
- `0x140016ea0`

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
    *(_DWORD *)sub_140016EA0(a1, a2, a3, a4) = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( (_DWORD)a3 && (unsigned int)(a3 - 2) > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    sub_140015FE4(0, 0, 0, 0, 0, a1);
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
          *(_DWORD *)sub_140016EA0(v10, a2, v14, a4) = 22;
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
    *(_DWORD *)sub_140016EA0(v20, v18, v17, v19) = 22;
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
0x1400101b0  mov     [rsp+arg_0], rbx
0x1400101b5  mov     [rsp+arg_8], rbp
0x1400101ba  mov     [rsp+arg_10], rsi
0x1400101bf  push    rdi
0x1400101c0  push    r12
0x1400101c2  push    r13
0x1400101c4  push    r14
0x1400101c6  push    r15
0x1400101c8  sub     rsp, 30h
0x1400101cc  mov     r12, [rdx]
0x1400101cf  mov     ebp, r8d
0x1400101d2  mov     rbx, rdx
0x1400101d5  mov     r13, rcx
0x1400101d8  test    r12, r12
0x1400101db  jnz     short loc_1400101EF
0x1400101dd  call    sub_140016EA0
0x1400101e2  mov     dword ptr [rax], 16h
0x1400101e8  call    _invalid_parameter_noinfo
0x1400101ed  jmp     short loc_140010221
0x1400101ef  test    ebp, ebp
0x1400101f1  jz      short loc_140010239
0x1400101f3  lea     eax, [r8-2]
0x1400101f7  cmp     eax, 22h ; '"'
0x1400101fa  jbe     short loc_140010239
0x1400101fc  mov     byte ptr [rcx+30h], 1
0x140010200  xor     r9d, r9d; LineNo
0x140010203  mov     dword ptr [rcx+2Ch], 16h
0x14001020a  xor     r8d, r8d; FileName
0x14001020d  mov     [rsp+58h+var_30], r13; __crt_cached_ptd_host *
0x140010212  xor     ecx, ecx; Expression
0x140010214  and     [rsp+58h+var_38], 0
0x14001021a  xor     edx, edx; FunctionName
0x14001021c  call    sub_140015FE4
0x140010221  mov     rcx, [rbx+8]
0x140010225  test    rcx, rcx
0x140010228  jz      loc_1400103AC
0x14001022e  mov     rax, [rbx]
0x140010231  mov     [rcx], rax
0x140010234  jmp     loc_1400103AC
0x140010239  mov     sil, [r12]
0x14001023d  lea     rcx, [r12+1]
0x140010242  xor     r14d, r14d
0x140010245  movzx   eax, r9b
0x140010249  mov     edi, eax
0x14001024b  mov     [rdx], rcx
0x14001024e  lea     r15d, [r14+2]
0x140010252  or      edi, r15d
0x140010255  cmp     sil, 2Dh ; '-'
0x140010259  cmovnz  edi, eax
0x14001025c  jz      short loc_140010264
0x14001025e  cmp     sil, 2Bh ; '+'
0x140010262  jnz     short loc_14001026D
0x140010264  mov     sil, [rcx]
0x140010267  inc     rcx
0x14001026a  mov     [rdx], rcx
0x14001026d  test    ebp, 0FFFFFFEFh
0x140010273  jnz     loc_140010301
0x140010279  lea     eax, [rsi-30h]
0x14001027c  cmp     al, 9
0x14001027e  ja      short loc_140010289
0x140010280  movsx   eax, sil
0x140010284  add     eax, 0FFFFFFD0h
0x140010287  jmp     short loc_1400102A7
0x140010289  lea     eax, [rsi-61h]
0x14001028c  cmp     al, 19h
0x14001028e  ja      short loc_140010299
0x140010290  movsx   eax, sil
0x140010294  add     eax, 0FFFFFFA9h
0x140010297  jmp     short loc_1400102A7
0x140010299  lea     eax, [rsi-41h]
0x14001029c  cmp     al, 19h
0x14001029e  ja      short loc_1400102F5
0x1400102a0  movsx   eax, sil
0x1400102a4  add     eax, 0FFFFFFC9h
0x1400102a7  test    eax, eax
0x1400102a9  jnz     short loc_1400102F5
0x1400102ab  mov     dl, [rcx]
0x1400102ad  lea     r8, [rcx+1]
0x1400102b1  mov     [rbx], r8
0x1400102b4  lea     eax, [rdx-58h]
0x1400102b7  test    al, 0DFh
0x1400102b9  jz      short loc_1400102E4
0x1400102bb  test    ebp, ebp
0x1400102bd  mov     [rbx], rcx
0x1400102c0  mov     eax, 8
0x1400102c5  cmovnz  eax, ebp
0x1400102c8  mov     ebp, eax
0x1400102ca  test    dl, dl
0x1400102cc  jz      short loc_140010301
0x1400102ce  cmp     [rcx], dl
0x1400102d0  jz      short loc_140010301
0x1400102d2  call    sub_140016EA0
0x1400102d7  mov     dword ptr [rax], 16h
0x1400102dd  call    _invalid_parameter_noinfo
0x1400102e2  jmp     short loc_140010301
0x1400102e4  mov     sil, [r8]
0x1400102e7  lea     rax, [r8+1]
0x1400102eb  mov     [rbx], rax
0x1400102ee  mov     eax, 10h
0x1400102f3  jmp     short loc_1400102FA
0x1400102f5  mov     eax, 0Ah
0x1400102fa  test    ebp, ebp
0x1400102fc  cmovnz  eax, ebp
0x1400102ff  mov     ebp, eax
0x140010301  mov     r8, [rbx]
0x140010304  xor     edx, edx
0x140010306  or      eax, 0FFFFFFFFh
0x140010309  div     ebp
0x14001030b  mov     r9d, eax
0x14001030e  lea     ecx, [rsi-30h]
0x140010311  cmp     cl, 9
0x140010314  ja      short loc_14001031F
0x140010316  movsx   ecx, sil
0x14001031a  add     ecx, 0FFFFFFD0h
0x14001031d  jmp     short loc_140010342
0x14001031f  lea     eax, [rsi-61h]
0x140010322  cmp     al, 19h
0x140010324  ja      short loc_14001032F
0x140010326  movsx   ecx, sil
0x14001032a  add     ecx, 0FFFFFFA9h
0x14001032d  jmp     short loc_140010342
0x14001032f  lea     eax, [rsi-41h]
0x140010332  cmp     al, 19h
0x140010334  ja      short loc_14001033F
0x140010336  movsx   ecx, sil
0x14001033a  add     ecx, 0FFFFFFC9h
0x14001033d  jmp     short loc_140010342
0x14001033f  or      ecx, 0FFFFFFFFh
0x140010342  cmp     ecx, ebp
0x140010344  jnb     short loc_140010376
0x140010346  mov     sil, [r8]
0x140010349  mov     eax, r14d
0x14001034c  imul    eax, ebp
0x14001034f  lea     edx, [rax+rcx]
0x140010352  xor     ecx, ecx
0x140010354  cmp     edx, eax
0x140010356  setb    cl
0x140010359  xor     eax, eax
0x14001035b  cmp     r14d, r9d
0x14001035e  mov     r14d, edx
0x140010361  setnbe  al
0x140010364  or      ecx, eax
0x140010366  shl     ecx, 2
0x140010369  or      ecx, 8
0x14001036c  or      edi, ecx
0x14001036e  inc     r8
0x140010371  mov     [rbx], r8
0x140010374  jmp     short loc_14001030E
0x140010376  lea     rax, [r8-1]
0x14001037a  mov     [rbx], rax
0x14001037d  test    sil, sil
0x140010380  jz      short loc_140010397
0x140010382  cmp     [rax], sil
0x140010385  jz      short loc_140010397
0x140010387  call    sub_140016EA0
0x14001038c  mov     dword ptr [rax], 16h
0x140010392  call    _invalid_parameter_noinfo
0x140010397  test    dil, 8
0x14001039b  jnz     short loc_1400103B3
0x14001039d  mov     rax, [rbx+8]
0x1400103a1  mov     [rbx], r12
0x1400103a4  test    rax, rax
0x1400103a7  jz      short loc_1400103AC
0x1400103a9  mov     [rax], r12
0x1400103ac  xor     eax, eax
0x1400103ae  jmp     loc_140010447
0x1400103b3  mov     r8d, 80000000h
0x1400103b9  lea     r9d, [r8-1]
0x1400103bd  test    dil, 4
0x1400103c1  jz      short loc_1400103CC
0x1400103c3  mov     eax, 1
0x1400103c8  mov     ecx, edi
0x1400103ca  jmp     short loc_1400103EA
0x1400103cc  test    dil, 1
0x1400103d0  jz      short loc_14001042D
0x1400103d2  test    r15b, dil
0x1400103d5  jz      short loc_1400103DE
0x1400103d7  cmp     r14d, r8d
0x1400103da  jbe     short loc_140010432
0x1400103dc  jmp     short loc_1400103E3
0x1400103de  cmp     r14d, r9d
0x1400103e1  jbe     short loc_140010435
0x1400103e3  mov     ecx, 1
0x1400103e8  mov     eax, edi
0x1400103ea  and     r15d, edi
0x1400103ed  mov     byte ptr [r13+30h], 1
0x1400103f2  mov     dword ptr [r13+2Ch], 22h ; '"'
0x1400103fa  test    eax, ecx
0x1400103fc  jnz     short loc_140010404
0x1400103fe  or      r14d, 0FFFFFFFFh
0x140010402  jmp     short loc_140010435
0x140010404  mov     rdx, [rbx+8]
0x140010408  test    r15d, r15d
0x14001040b  jz      short loc_14001041D
0x14001040d  test    rdx, rdx
0x140010410  jz      short loc_140010418
0x140010412  mov     rcx, [rbx]
0x140010415  mov     [rdx], rcx
0x140010418  mov     eax, r8d
0x14001041b  jmp     short loc_140010447
0x14001041d  test    rdx, rdx
0x140010420  jz      short loc_140010428
0x140010422  mov     rcx, [rbx]
0x140010425  mov     [rdx], rcx
0x140010428  mov     eax, r9d
0x14001042b  jmp     short loc_140010447
0x14001042d  test    r15b, dil
0x140010430  jz      short loc_140010435
0x140010432  neg     r14d
0x140010435  mov     rax, [rbx+8]
0x140010439  test    rax, rax
0x14001043c  jz      short loc_140010444
0x14001043e  mov     rcx, [rbx]
0x140010441  mov     [rax], rcx
0x140010444  mov     eax, r14d
0x140010447  mov     rbx, [rsp+58h+arg_0]
0x14001044c  mov     rbp, [rsp+58h+arg_8]
0x140010451  mov     rsi, [rsp+58h+arg_10]
0x140010456  add     rsp, 30h
0x14001045a  pop     r15
0x14001045c  pop     r14
0x14001045e  pop     r13
0x140010460  pop     r12
0x140010462  pop     rdi
0x140010463  retn
```
