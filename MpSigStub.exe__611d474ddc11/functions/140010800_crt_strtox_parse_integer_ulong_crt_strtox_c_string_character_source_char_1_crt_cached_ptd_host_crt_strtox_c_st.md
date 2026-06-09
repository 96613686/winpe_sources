# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x140010800`
- end: `0x140010aed`
- name: `??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$00@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `749`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *, unsigned __int8 **, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140011274`

## callees

- `0x140004614`
- `0x1400046cc`
- `0x14000ad70`
- `0x14000b020`
- `0x14000fa6c`
- `0x140010800`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,1>(
        __crt_cached_ptd_host *a1,
        unsigned __int8 **a2,
        unsigned int a3,
        unsigned __int8 a4)
{
  unsigned __int8 *v4; // r12
  unsigned int v5; // ebp
  int v6; // r15d
  unsigned __int8 *v9; // rcx
  int v10; // esi
  unsigned int v11; // r14d
  __int64 v12; // rdx
  int v13; // edi
  int v14; // eax
  unsigned __int8 *v15; // rcx
  unsigned __int8 *v16; // r8
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // r9d
  __int64 v21; // rcx
  unsigned __int8 *v22; // r8
  BOOL v23; // ecx
  bool v24; // cf
  bool v25; // zf
  unsigned __int8 *v26; // rax
  int v28; // eax
  int v29; // ecx
  int v30; // edi
  unsigned __int8 *v31; // rdx
  unsigned __int8 *v32; // rax

  v4 = *a2;
  v5 = a3;
  v6 = a4;
  if ( !*a2 )
  {
    *(_DWORD *)sub_14000FA6C(a1, a2) = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && a3 - 2 > 0x22 )
  {
    *((_BYTE *)a1 + 48) = 1;
    *((_DWORD *)a1 + 11) = 22;
    sub_140004614(0, 0, 0, 0, 0, a1);
LABEL_6:
    v9 = a2[1];
    if ( v9 )
      *(_QWORD *)v9 = *a2;
    return 0;
  }
  v10 = *v4;
  v11 = 0;
  *a2 = v4 + 1;
  if ( !*((_BYTE *)a1 + 40) )
    __crt_cached_ptd_host::update_locale_slow(a1);
  while ( ischartype_l(v10, 8, (const _locale_t)((char *)a1 + 24)) )
    v10 = *(*a2)++;
  v13 = v6 | 2;
  if ( (_BYTE)v10 != 45 )
    v13 = v6;
  if ( (((_BYTE)v10 - 43) & 0xFD) == 0 )
    LOBYTE(v10) = *(*a2)++;
  if ( (v5 & 0xFFFFFFEF) == 0 )
  {
    if ( (unsigned __int8)(v10 - 48) > 9u )
    {
      if ( (unsigned __int8)(v10 - 97) > 0x19u )
      {
        if ( (unsigned __int8)(v10 - 65) > 0x19u )
          goto LABEL_31;
        v14 = (char)v10 - 55;
      }
      else
      {
        v14 = (char)v10 - 87;
      }
    }
    else
    {
      v14 = (char)v10 - 48;
    }
    if ( !v14 )
    {
      v15 = *a2;
      LOBYTE(v12) = **a2;
      v16 = *a2 + 1;
      *a2 = v16;
      if ( (((_BYTE)v12 - 88) & 0xDF) != 0 )
      {
        *a2 = v15;
        v17 = 8;
        if ( v5 )
          v17 = v5;
        v5 = v17;
        if ( (_BYTE)v12 && *v15 != (_BYTE)v12 )
        {
          *(_DWORD *)sub_14000FA6C(v15, v12) = 22;
          invalid_parameter_noinfo();
        }
        goto LABEL_35;
      }
      LOBYTE(v10) = *v16;
      *a2 = v16 + 1;
      v18 = 16;
      goto LABEL_32;
    }
LABEL_31:
    v18 = 10;
LABEL_32:
    if ( v5 )
      v18 = v5;
    v5 = v18;
  }
LABEL_35:
  v19 = 0xFFFFFFFF % v5;
  v20 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( (unsigned __int8)(v10 - 48) > 9u )
    {
      if ( (unsigned __int8)(v10 - 97) > 0x19u )
        v21 = (unsigned __int8)(v10 - 65) > 0x19u ? 0xFFFFFFFFLL : (unsigned int)((char)v10 - 55);
      else
        v21 = (unsigned int)((char)v10 - 87);
    }
    else
    {
      v21 = (unsigned int)((char)v10 - 48);
    }
    v22 = *a2;
    if ( (unsigned int)v21 >= v5 )
      break;
    LOBYTE(v10) = *v22;
    v19 = v5 * v11 + (unsigned int)v21;
    v23 = (unsigned int)v19 < v5 * v11;
    v24 = v11 < v20;
    v25 = v11 == v20;
    v11 = v19;
    *a2 = v22 + 1;
    v13 |= (4 * (!v24 && !v25 || v23)) | 8;
  }
  *a2 = v22 - 1;
  if ( (_BYTE)v10 && *(v22 - 1) != (_BYTE)v10 )
  {
    *(_DWORD *)sub_14000FA6C(v21, v19) = 22;
    invalid_parameter_noinfo();
  }
  if ( (v13 & 8) == 0 )
  {
    v26 = a2[1];
    *a2 = v4;
    if ( v26 )
      *(_QWORD *)v26 = v4;
    return 0;
  }
  if ( (v13 & 4) != 0 )
  {
    v28 = 1;
    v29 = v13;
    goto LABEL_60;
  }
  if ( (v13 & 1) == 0 )
  {
    if ( (v13 & 2) == 0 )
      goto LABEL_71;
    goto LABEL_70;
  }
  if ( (v13 & 2) == 0 )
  {
    if ( v11 <= 0x7FFFFFFF )
    {
LABEL_71:
      v32 = a2[1];
      if ( v32 )
        *(_QWORD *)v32 = *a2;
      return v11;
    }
    goto LABEL_59;
  }
  if ( v11 <= 0x80000000 )
  {
LABEL_70:
    v11 = -v11;
    goto LABEL_71;
  }
LABEL_59:
  v29 = 1;
  v28 = v13;
LABEL_60:
  v30 = v13 & 2;
  *((_BYTE *)a1 + 48) = 1;
  *((_DWORD *)a1 + 11) = 34;
  if ( (v29 & v28) == 0 )
  {
    v11 = -1;
    goto LABEL_71;
  }
  v31 = a2[1];
  if ( v30 )
  {
    if ( v31 )
      *(_QWORD *)v31 = *a2;
    return 0x80000000LL;
  }
  else
  {
    if ( v31 )
      *(_QWORD *)v31 = *a2;
    return 0x7FFFFFFF;
  }
}

```

## disassembly

```asm
0x140010800  mov     [rsp+arg_0], rbx
0x140010805  mov     [rsp+arg_8], rbp
0x14001080a  mov     [rsp+arg_10], rsi
0x14001080f  push    rdi
0x140010810  push    r12
0x140010812  push    r13
0x140010814  push    r14
0x140010816  push    r15
0x140010818  sub     rsp, 30h
0x14001081c  mov     r12, [rdx]
0x14001081f  mov     ebp, r8d
0x140010822  movzx   r15d, r9b
0x140010826  mov     rbx, rdx
0x140010829  mov     r13, rcx
0x14001082c  test    r12, r12
0x14001082f  jnz     short loc_140010843
0x140010831  call    sub_14000FA6C
0x140010836  mov     dword ptr [rax], 16h
0x14001083c  call    _invalid_parameter_noinfo
0x140010841  jmp     short loc_140010875
0x140010843  test    ebp, ebp
0x140010845  jz      short loc_14001088D
0x140010847  lea     eax, [r8-2]
0x14001084b  cmp     eax, 22h ; '"'
0x14001084e  jbe     short loc_14001088D
0x140010850  mov     byte ptr [rcx+30h], 1
0x140010854  xor     r9d, r9d; LineNo
0x140010857  mov     dword ptr [rcx+2Ch], 16h
0x14001085e  xor     r8d, r8d; FileName
0x140010861  mov     [rsp+58h+var_30], r13; __crt_cached_ptd_host *
0x140010866  xor     ecx, ecx; Expression
0x140010868  and     [rsp+58h+var_38], 0
0x14001086e  xor     edx, edx; FunctionName
0x140010870  call    sub_140004614
0x140010875  mov     rcx, [rbx+8]; this
0x140010879  test    rcx, rcx
0x14001087c  jz      loc_140010A36
0x140010882  mov     rax, [rbx]
0x140010885  mov     [rcx], rax
0x140010888  jmp     loc_140010A36
0x14001088d  movzx   esi, byte ptr [r12]
0x140010892  lea     rax, [r12+1]
0x140010897  xor     r14d, r14d
0x14001089a  mov     [rdx], rax
0x14001089d  cmp     [rcx+28h], r14b
0x1400108a1  jnz     short loc_1400108B6
0x1400108a3  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x1400108a8  jmp     short loc_1400108B6
0x1400108aa  mov     rax, [rbx]
0x1400108ad  movzx   esi, byte ptr [rax]
0x1400108b0  inc     rax
0x1400108b3  mov     [rbx], rax
0x1400108b6  lea     r8, [r13+18h]; Locale
0x1400108ba  mov     edx, 8; Mask
0x1400108bf  mov     ecx, esi; C
0x1400108c1  call    _ischartype_l
0x1400108c6  test    eax, eax
0x1400108c8  jnz     short loc_1400108AA
0x1400108ca  mov     eax, r15d
0x1400108cd  mov     edi, r15d
0x1400108d0  mov     r15d, 2
0x1400108d6  or      edi, r15d
0x1400108d9  cmp     sil, 2Dh ; '-'
0x1400108dd  cmovnz  edi, eax
0x1400108e0  lea     eax, [rsi-2Bh]
0x1400108e3  test    al, 0FDh
0x1400108e5  jnz     short loc_1400108F3
0x1400108e7  mov     rax, [rbx]
0x1400108ea  mov     sil, [rax]
0x1400108ed  inc     rax
0x1400108f0  mov     [rbx], rax
0x1400108f3  test    ebp, 0FFFFFFEFh
0x1400108f9  jnz     loc_14001098A
0x1400108ff  lea     eax, [rsi-30h]
0x140010902  cmp     al, 9
0x140010904  ja      short loc_14001090F
0x140010906  movsx   eax, sil
0x14001090a  add     eax, 0FFFFFFD0h
0x14001090d  jmp     short loc_14001092D
0x14001090f  lea     eax, [rsi-61h]
0x140010912  cmp     al, 19h
0x140010914  ja      short loc_14001091F
0x140010916  movsx   eax, sil
0x14001091a  add     eax, 0FFFFFFA9h
0x14001091d  jmp     short loc_14001092D
0x14001091f  lea     eax, [rsi-41h]
0x140010922  cmp     al, 19h
0x140010924  ja      short loc_14001097E
0x140010926  movsx   eax, sil
0x14001092a  add     eax, 0FFFFFFC9h
0x14001092d  test    eax, eax
0x14001092f  jnz     short loc_14001097E
0x140010931  mov     rcx, [rbx]
0x140010934  mov     dl, [rcx]
0x140010936  lea     r8, [rcx+1]
0x14001093a  mov     [rbx], r8
0x14001093d  lea     eax, [rdx-58h]
0x140010940  test    al, 0DFh
0x140010942  jz      short loc_14001096D
0x140010944  test    ebp, ebp
0x140010946  mov     [rbx], rcx
0x140010949  mov     eax, 8
0x14001094e  cmovnz  eax, ebp
0x140010951  mov     ebp, eax
0x140010953  test    dl, dl
0x140010955  jz      short loc_14001098A
0x140010957  cmp     [rcx], dl
0x140010959  jz      short loc_14001098A
0x14001095b  call    sub_14000FA6C
0x140010960  mov     dword ptr [rax], 16h
0x140010966  call    _invalid_parameter_noinfo
0x14001096b  jmp     short loc_14001098A
0x14001096d  mov     sil, [r8]
0x140010970  lea     rax, [r8+1]
0x140010974  mov     [rbx], rax
0x140010977  mov     eax, 10h
0x14001097c  jmp     short loc_140010983
0x14001097e  mov     eax, 0Ah
0x140010983  test    ebp, ebp
0x140010985  cmovnz  eax, ebp
0x140010988  mov     ebp, eax
0x14001098a  xor     edx, edx
0x14001098c  or      eax, 0FFFFFFFFh
0x14001098f  div     ebp
0x140010991  mov     r9d, eax
0x140010994  lea     ecx, [rsi-30h]
0x140010997  cmp     cl, 9
0x14001099a  ja      short loc_1400109A5
0x14001099c  movsx   ecx, sil
0x1400109a0  add     ecx, 0FFFFFFD0h
0x1400109a3  jmp     short loc_1400109C8
0x1400109a5  lea     eax, [rsi-61h]
0x1400109a8  cmp     al, 19h
0x1400109aa  ja      short loc_1400109B5
0x1400109ac  movsx   ecx, sil
0x1400109b0  add     ecx, 0FFFFFFA9h
0x1400109b3  jmp     short loc_1400109C8
0x1400109b5  lea     eax, [rsi-41h]
0x1400109b8  cmp     al, 19h
0x1400109ba  ja      short loc_1400109C5
0x1400109bc  movsx   ecx, sil
0x1400109c0  add     ecx, 0FFFFFFC9h
0x1400109c3  jmp     short loc_1400109C8
0x1400109c5  or      ecx, 0FFFFFFFFh
0x1400109c8  mov     r8, [rbx]
0x1400109cb  cmp     ecx, ebp
0x1400109cd  jnb     short loc_140010A00
0x1400109cf  mov     sil, [r8]
0x1400109d2  mov     eax, r14d
0x1400109d5  imul    eax, ebp
0x1400109d8  lea     edx, [rax+rcx]
0x1400109db  xor     ecx, ecx
0x1400109dd  cmp     edx, eax
0x1400109df  setb    cl
0x1400109e2  xor     eax, eax
0x1400109e4  cmp     r14d, r9d
0x1400109e7  mov     r14d, edx
0x1400109ea  setnbe  al
0x1400109ed  or      ecx, eax
0x1400109ef  lea     rax, [r8+1]
0x1400109f3  shl     ecx, 2
0x1400109f6  or      ecx, 8
0x1400109f9  mov     [rbx], rax
0x1400109fc  or      edi, ecx
0x1400109fe  jmp     short loc_140010994
0x140010a00  lea     rax, [r8-1]
0x140010a04  mov     [rbx], rax
0x140010a07  test    sil, sil
0x140010a0a  jz      short loc_140010A21
0x140010a0c  cmp     [rax], sil
0x140010a0f  jz      short loc_140010A21
0x140010a11  call    sub_14000FA6C
0x140010a16  mov     dword ptr [rax], 16h
0x140010a1c  call    _invalid_parameter_noinfo
0x140010a21  test    dil, 8
0x140010a25  jnz     short loc_140010A3D
0x140010a27  mov     rax, [rbx+8]
0x140010a2b  mov     [rbx], r12
0x140010a2e  test    rax, rax
0x140010a31  jz      short loc_140010A36
0x140010a33  mov     [rax], r12
0x140010a36  xor     eax, eax
0x140010a38  jmp     loc_140010AD0
0x140010a3d  mov     r8d, 80000000h
0x140010a43  lea     r9d, [r8-1]
0x140010a47  test    dil, 4
0x140010a4b  jz      short loc_140010A56
0x140010a4d  mov     eax, 1
0x140010a52  mov     ecx, edi
0x140010a54  jmp     short loc_140010A74
0x140010a56  test    dil, 1
0x140010a5a  jz      short loc_140010AB6
0x140010a5c  test    r15b, dil
0x140010a5f  jz      short loc_140010A68
0x140010a61  cmp     r14d, r8d
0x140010a64  jbe     short loc_140010ABB
0x140010a66  jmp     short loc_140010A6D
0x140010a68  cmp     r14d, r9d
0x140010a6b  jbe     short loc_140010ABE
0x140010a6d  mov     ecx, 1
0x140010a72  mov     eax, edi
0x140010a74  and     edi, r15d
0x140010a77  mov     byte ptr [r13+30h], 1
0x140010a7c  mov     dword ptr [r13+2Ch], 22h ; '"'
0x140010a84  test    eax, ecx
0x140010a86  jnz     short loc_140010A8E
0x140010a88  or      r14d, 0FFFFFFFFh
0x140010a8c  jmp     short loc_140010ABE
0x140010a8e  mov     rdx, [rbx+8]
0x140010a92  test    edi, edi
0x140010a94  jz      short loc_140010AA6
0x140010a96  test    rdx, rdx
0x140010a99  jz      short loc_140010AA1
0x140010a9b  mov     rcx, [rbx]
0x140010a9e  mov     [rdx], rcx
0x140010aa1  mov     eax, r8d
0x140010aa4  jmp     short loc_140010AD0
0x140010aa6  test    rdx, rdx
0x140010aa9  jz      short loc_140010AB1
0x140010aab  mov     rcx, [rbx]
0x140010aae  mov     [rdx], rcx
0x140010ab1  mov     eax, r9d
0x140010ab4  jmp     short loc_140010AD0
0x140010ab6  test    r15b, dil
0x140010ab9  jz      short loc_140010ABE
0x140010abb  neg     r14d
0x140010abe  mov     rax, [rbx+8]
0x140010ac2  test    rax, rax
0x140010ac5  jz      short loc_140010ACD
0x140010ac7  mov     rcx, [rbx]
0x140010aca  mov     [rax], rcx
0x140010acd  mov     eax, r14d
0x140010ad0  mov     rbx, [rsp+58h+arg_0]
0x140010ad5  mov     rbp, [rsp+58h+arg_8]
0x140010ada  mov     rsi, [rsp+58h+arg_10]
0x140010adf  add     rsp, 30h
0x140010ae3  pop     r15
0x140010ae5  pop     r14
0x140010ae7  pop     r13
0x140010ae9  pop     r12
0x140010aeb  pop     rdi
0x140010aec  retn
```
