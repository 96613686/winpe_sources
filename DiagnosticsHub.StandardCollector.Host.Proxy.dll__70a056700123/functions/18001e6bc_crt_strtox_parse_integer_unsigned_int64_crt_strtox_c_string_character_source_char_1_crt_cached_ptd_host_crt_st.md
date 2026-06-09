# __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<char>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x18001e6bc`
- end: `0x18001e997`
- name: `??$parse_integer@_KV?$c_string_character_source@D@__crt_strtox@@$00@__crt_strtox@@YA_KAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `731`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001f294`
- `0x18001f968`
- `0x18001fa1c`
- `0x18001fc50`
- `0x180020500`

## callees

- `0x1800073e8`
- `0x1800074a0`
- `0x180007788`
- `0x1800149cc`
- `0x18001dbe4`
- `0x18001e6bc`
- `0x18001fd70`

## pseudocode

```c
unsigned __int64 __fastcall __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<char>,1>(
        __crt_cached_ptd_host *a1,
        unsigned __int8 **a2,
        signed int a3,
        unsigned __int8 a4)
{
  unsigned __int8 *v4; // r12
  signed int v5; // esi
  unsigned int v6; // r13d
  unsigned __int8 *v9; // rcx
  int v10; // edi
  unsigned __int64 v11; // rbp
  unsigned int v12; // r14d
  int v13; // eax
  unsigned __int8 *v14; // rcx
  char v15; // dl
  unsigned __int8 *v16; // r8
  int v17; // eax
  int v18; // eax
  unsigned __int64 v19; // r10
  unsigned int v20; // ecx
  unsigned __int8 *v21; // r8
  unsigned __int64 v22; // rdx
  BOOL v23; // ecx
  bool v24; // cf
  bool v25; // zf
  unsigned __int8 *v26; // rax
  unsigned __int8 *v28; // rcx
  unsigned __int8 *v29; // rax

  v4 = *a2;
  v5 = a3;
  v6 = a4;
  if ( !*a2 )
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
  v12 = v6 | 2;
  if ( (_BYTE)v10 != 45 )
    v12 = v6;
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
        v13 = (char)v10 - 55;
      }
      else
      {
        v13 = (char)v10 - 87;
      }
    }
    else
    {
      v13 = (char)v10 - 48;
    }
    if ( !v13 )
    {
      v14 = *a2;
      v15 = **a2;
      v16 = *a2 + 1;
      *a2 = v16;
      if ( ((v15 - 88) & 0xDF) != 0 )
      {
        *a2 = v14;
        v17 = 8;
        if ( v5 )
          v17 = v5;
        v5 = v17;
        if ( v15 && *v14 != v15 )
        {
          *errno() = 22;
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
  v19 = 0xFFFFFFFFFFFFFFFFuLL / v5;
  while ( 1 )
  {
    if ( (unsigned __int8)(v10 - 48) > 9u )
    {
      if ( (unsigned __int8)(v10 - 97) > 0x19u )
        v20 = (unsigned __int8)(v10 - 65) > 0x19u ? -1 : (char)v10 - 55;
      else
        v20 = (char)v10 - 87;
    }
    else
    {
      v20 = (char)v10 - 48;
    }
    v21 = *a2;
    if ( v20 >= v5 )
      break;
    LOBYTE(v10) = *v21;
    v22 = v11 * v5 + v20;
    v23 = v22 < v11 * v5;
    v24 = v11 < v19;
    v25 = v11 == v19;
    v11 = v22;
    *a2 = v21 + 1;
    v12 |= (4 * (!v24 && !v25 || v23)) | 8;
  }
  *a2 = v21 - 1;
  if ( (_BYTE)v10 && *(v21 - 1) != (_BYTE)v10 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
  if ( (v12 & 8) == 0 )
  {
    v26 = a2[1];
    *a2 = v4;
    if ( v26 )
      *(_QWORD *)v26 = v4;
    return 0;
  }
  if ( !(unsigned __int8)__crt_strtox::is_overflow_condition<unsigned __int64>(v12, v11) )
  {
    if ( (v12 & 2) != 0 )
      v11 = -(__int64)v11;
    goto LABEL_64;
  }
  *((_BYTE *)a1 + 48) = 1;
  *((_DWORD *)a1 + 11) = 34;
  if ( (v12 & 1) == 0 )
  {
    v11 = -1;
LABEL_64:
    v29 = a2[1];
    if ( v29 )
      *(_QWORD *)v29 = *a2;
    return v11;
  }
  v28 = a2[1];
  if ( (v12 & 2) != 0 )
  {
    if ( v28 )
      *(_QWORD *)v28 = *a2;
    return 0x8000000000000000uLL;
  }
  else
  {
    if ( v28 )
      *(_QWORD *)v28 = *a2;
    return 0x7FFFFFFFFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x18001e6bc  mov     [rsp+arg_0], rbx
0x18001e6c1  mov     [rsp+arg_8], rbp
0x18001e6c6  mov     [rsp+arg_10], rsi
0x18001e6cb  push    rdi
0x18001e6cc  push    r12
0x18001e6ce  push    r13
0x18001e6d0  push    r14
0x18001e6d2  push    r15
0x18001e6d4  sub     rsp, 30h
0x18001e6d8  mov     r12, [rdx]
0x18001e6db  mov     esi, r8d
0x18001e6de  movzx   r13d, r9b
0x18001e6e2  mov     rbx, rdx
0x18001e6e5  mov     r15, rcx
0x18001e6e8  test    r12, r12
0x18001e6eb  jnz     short loc_18001E6FF
0x18001e6ed  call    _errno
0x18001e6f2  mov     dword ptr [rax], 16h
0x18001e6f8  call    _invalid_parameter_noinfo
0x18001e6fd  jmp     short loc_18001E731
0x18001e6ff  test    esi, esi
0x18001e701  jz      short loc_18001E749
0x18001e703  lea     eax, [r8-2]
0x18001e707  cmp     eax, 22h ; '"'
0x18001e70a  jbe     short loc_18001E749
0x18001e70c  mov     byte ptr [rcx+30h], 1
0x18001e710  xor     r9d, r9d; LineNo
0x18001e713  mov     dword ptr [rcx+2Ch], 16h
0x18001e71a  xor     r8d, r8d; FileName
0x18001e71d  mov     [rsp+58h+var_30], r15; __crt_cached_ptd_host *
0x18001e722  xor     ecx, ecx; Expression
0x18001e724  and     [rsp+58h+var_38], 0
0x18001e72a  xor     edx, edx; FunctionName
0x18001e72c  call    _invalid_parameter_internal
0x18001e731  mov     rcx, [rbx+8]; this
0x18001e735  test    rcx, rcx
0x18001e738  jz      loc_18001E8FB
0x18001e73e  mov     rax, [rbx]
0x18001e741  mov     [rcx], rax
0x18001e744  jmp     loc_18001E8FB
0x18001e749  movzx   edi, byte ptr [r12]
0x18001e74e  lea     rax, [r12+1]
0x18001e753  xor     ebp, ebp
0x18001e755  mov     [rdx], rax
0x18001e758  cmp     [rcx+28h], bpl
0x18001e75c  jnz     short loc_18001E771
0x18001e75e  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001e763  jmp     short loc_18001E771
0x18001e765  mov     rax, [rbx]
0x18001e768  movzx   edi, byte ptr [rax]
0x18001e76b  inc     rax
0x18001e76e  mov     [rbx], rax
0x18001e771  lea     r8, [r15+18h]; Locale
0x18001e775  mov     edx, 8; Mask
0x18001e77a  mov     ecx, edi; C
0x18001e77c  call    _ischartype_l
0x18001e781  test    eax, eax
0x18001e783  jnz     short loc_18001E765
0x18001e785  mov     r14d, r13d
0x18001e788  lea     eax, [rdi-2Bh]
0x18001e78b  or      r14d, 2
0x18001e78f  cmp     dil, 2Dh ; '-'
0x18001e793  cmovnz  r14d, r13d
0x18001e797  test    al, 0FDh
0x18001e799  jnz     short loc_18001E7A7
0x18001e79b  mov     rax, [rbx]
0x18001e79e  mov     dil, [rax]
0x18001e7a1  inc     rax
0x18001e7a4  mov     [rbx], rax
0x18001e7a7  mov     r13b, 19h
0x18001e7aa  test    esi, 0FFFFFFEFh
0x18001e7b0  jnz     loc_18001E843
0x18001e7b6  lea     eax, [rdi-30h]
0x18001e7b9  cmp     al, 9
0x18001e7bb  ja      short loc_18001E7C6
0x18001e7bd  movsx   eax, dil
0x18001e7c1  add     eax, 0FFFFFFD0h
0x18001e7c4  jmp     short loc_18001E7E6
0x18001e7c6  lea     eax, [rdi-61h]
0x18001e7c9  cmp     al, r13b
0x18001e7cc  ja      short loc_18001E7D7
0x18001e7ce  movsx   eax, dil
0x18001e7d2  add     eax, 0FFFFFFA9h
0x18001e7d5  jmp     short loc_18001E7E6
0x18001e7d7  lea     eax, [rdi-41h]
0x18001e7da  cmp     al, r13b
0x18001e7dd  ja      short loc_18001E837
0x18001e7df  movsx   eax, dil
0x18001e7e3  add     eax, 0FFFFFFC9h
0x18001e7e6  test    eax, eax
0x18001e7e8  jnz     short loc_18001E837
0x18001e7ea  mov     rcx, [rbx]
0x18001e7ed  mov     dl, [rcx]
0x18001e7ef  lea     r8, [rcx+1]
0x18001e7f3  mov     [rbx], r8
0x18001e7f6  lea     eax, [rdx-58h]
0x18001e7f9  test    al, 0DFh
0x18001e7fb  jz      short loc_18001E826
0x18001e7fd  test    esi, esi
0x18001e7ff  mov     [rbx], rcx
0x18001e802  mov     eax, 8
0x18001e807  cmovnz  eax, esi
0x18001e80a  mov     esi, eax
0x18001e80c  test    dl, dl
0x18001e80e  jz      short loc_18001E843
0x18001e810  cmp     [rcx], dl
0x18001e812  jz      short loc_18001E843
0x18001e814  call    _errno
0x18001e819  mov     dword ptr [rax], 16h
0x18001e81f  call    _invalid_parameter_noinfo
0x18001e824  jmp     short loc_18001E843
0x18001e826  mov     dil, [r8]
0x18001e829  lea     rax, [r8+1]
0x18001e82d  mov     [rbx], rax
0x18001e830  mov     eax, 10h
0x18001e835  jmp     short loc_18001E83C
0x18001e837  mov     eax, 0Ah
0x18001e83c  test    esi, esi
0x18001e83e  cmovnz  eax, esi
0x18001e841  mov     esi, eax
0x18001e843  movsxd  r9, esi
0x18001e846  xor     edx, edx
0x18001e848  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e84c  div     r9
0x18001e84f  mov     r10, rax
0x18001e852  lea     ecx, [rdi-30h]
0x18001e855  cmp     cl, 9
0x18001e858  ja      short loc_18001E863
0x18001e85a  movsx   ecx, dil
0x18001e85e  add     ecx, 0FFFFFFD0h
0x18001e861  jmp     short loc_18001E888
0x18001e863  lea     eax, [rdi-61h]
0x18001e866  cmp     al, r13b
0x18001e869  ja      short loc_18001E874
0x18001e86b  movsx   ecx, dil
0x18001e86f  add     ecx, 0FFFFFFA9h
0x18001e872  jmp     short loc_18001E888
0x18001e874  lea     eax, [rdi-41h]
0x18001e877  cmp     al, r13b
0x18001e87a  ja      short loc_18001E885
0x18001e87c  movsx   ecx, dil
0x18001e880  add     ecx, 0FFFFFFC9h
0x18001e883  jmp     short loc_18001E888
0x18001e885  or      ecx, 0FFFFFFFFh
0x18001e888  mov     r8, [rbx]
0x18001e88b  cmp     ecx, esi
0x18001e88d  jnb     short loc_18001E8C5
0x18001e88f  mov     dil, [r8]
0x18001e892  mov     rax, r9
0x18001e895  imul    rax, rbp
0x18001e899  mov     edx, ecx
0x18001e89b  xor     ecx, ecx
0x18001e89d  add     rdx, rax
0x18001e8a0  cmp     rdx, rax
0x18001e8a3  setb    cl
0x18001e8a6  xor     eax, eax
0x18001e8a8  cmp     rbp, r10
0x18001e8ab  mov     rbp, rdx
0x18001e8ae  setnbe  al
0x18001e8b1  or      ecx, eax
0x18001e8b3  lea     rax, [r8+1]
0x18001e8b7  shl     ecx, 2
0x18001e8ba  or      ecx, 8
0x18001e8bd  mov     [rbx], rax
0x18001e8c0  or      r14d, ecx
0x18001e8c3  jmp     short loc_18001E852
0x18001e8c5  lea     rax, [r8-1]
0x18001e8c9  mov     [rbx], rax
0x18001e8cc  test    dil, dil
0x18001e8cf  jz      short loc_18001E8E6
0x18001e8d1  cmp     [rax], dil
0x18001e8d4  jz      short loc_18001E8E6
0x18001e8d6  call    _errno
0x18001e8db  mov     dword ptr [rax], 16h
0x18001e8e1  call    _invalid_parameter_noinfo
0x18001e8e6  test    r14b, 8
0x18001e8ea  jnz     short loc_18001E8FF
0x18001e8ec  mov     rax, [rbx+8]
0x18001e8f0  mov     [rbx], r12
0x18001e8f3  test    rax, rax
0x18001e8f6  jz      short loc_18001E8FB
0x18001e8f8  mov     [rax], r12
0x18001e8fb  xor     eax, eax
0x18001e8fd  jmp     short loc_18001E97A
0x18001e8ff  mov     rdx, rbp
0x18001e902  mov     ecx, r14d
0x18001e905  call    ??$is_overflow_condition@_K@__crt_strtox@@YA_NI_K@Z; __crt_strtox::is_overflow_condition<unsigned __int64>(uint,unsigned __int64)
0x18001e90a  test    al, al
0x18001e90c  jz      short loc_18001E95F
0x18001e90e  mov     byte ptr [r15+30h], 1
0x18001e913  mov     dword ptr [r15+2Ch], 22h ; '"'
0x18001e91b  test    r14b, 1
0x18001e91f  jnz     short loc_18001E927
0x18001e921  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001e925  jmp     short loc_18001E968
0x18001e927  mov     rcx, [rbx+8]
0x18001e92b  test    r14b, 2
0x18001e92f  jz      short loc_18001E948
0x18001e931  test    rcx, rcx
0x18001e934  jz      short loc_18001E93C
0x18001e936  mov     rax, [rbx]
0x18001e939  mov     [rcx], rax
0x18001e93c  mov     rax, 8000000000000000h
0x18001e946  jmp     short loc_18001E97A
0x18001e948  test    rcx, rcx
0x18001e94b  jz      short loc_18001E953
0x18001e94d  mov     rax, [rbx]
0x18001e950  mov     [rcx], rax
0x18001e953  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001e95d  jmp     short loc_18001E97A
0x18001e95f  test    r14b, 2
0x18001e963  jz      short loc_18001E968
0x18001e965  neg     rbp
0x18001e968  mov     rax, [rbx+8]
0x18001e96c  test    rax, rax
0x18001e96f  jz      short loc_18001E977
0x18001e971  mov     rcx, [rbx]
0x18001e974  mov     [rax], rcx
0x18001e977  mov     rax, rbp
0x18001e97a  mov     rbx, [rsp+58h+arg_0]
0x18001e97f  mov     rbp, [rsp+58h+arg_8]
0x18001e984  mov     rsi, [rsp+58h+arg_10]
0x18001e989  add     rsp, 30h
0x18001e98d  pop     r15
0x18001e98f  pop     r14
0x18001e991  pop     r13
0x18001e993  pop     r12
0x18001e995  pop     rdi
0x18001e996  retn
```
