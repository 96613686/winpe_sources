# __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<char>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x18001ee1c`
- end: `0x18001f0f7`
- name: `??$parse_integer@_KV?$c_string_character_source@D@__crt_strtox@@$00@__crt_strtox@@YA_KAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `731`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001f9f4`
- `0x1800200c8`
- `0x18002017c`
- `0x1800203b0`
- `0x180020c60`

## callees

- `0x180007b48`
- `0x180007c00`
- `0x180007ee8`
- `0x18001512c`
- `0x18001e344`
- `0x18001ee1c`
- `0x1800204d0`

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
0x18001ee1c  mov     [rsp+arg_0], rbx
0x18001ee21  mov     [rsp+arg_8], rbp
0x18001ee26  mov     [rsp+arg_10], rsi
0x18001ee2b  push    rdi
0x18001ee2c  push    r12
0x18001ee2e  push    r13
0x18001ee30  push    r14
0x18001ee32  push    r15
0x18001ee34  sub     rsp, 30h
0x18001ee38  mov     r12, [rdx]
0x18001ee3b  mov     esi, r8d
0x18001ee3e  movzx   r13d, r9b
0x18001ee42  mov     rbx, rdx
0x18001ee45  mov     r15, rcx
0x18001ee48  test    r12, r12
0x18001ee4b  jnz     short loc_18001EE5F
0x18001ee4d  call    _errno
0x18001ee52  mov     dword ptr [rax], 16h
0x18001ee58  call    _invalid_parameter_noinfo
0x18001ee5d  jmp     short loc_18001EE91
0x18001ee5f  test    esi, esi
0x18001ee61  jz      short loc_18001EEA9
0x18001ee63  lea     eax, [r8-2]
0x18001ee67  cmp     eax, 22h ; '"'
0x18001ee6a  jbe     short loc_18001EEA9
0x18001ee6c  mov     byte ptr [rcx+30h], 1
0x18001ee70  xor     r9d, r9d; LineNo
0x18001ee73  mov     dword ptr [rcx+2Ch], 16h
0x18001ee7a  xor     r8d, r8d; FileName
0x18001ee7d  mov     [rsp+58h+var_30], r15; __crt_cached_ptd_host *
0x18001ee82  xor     ecx, ecx; Expression
0x18001ee84  and     [rsp+58h+var_38], 0
0x18001ee8a  xor     edx, edx; FunctionName
0x18001ee8c  call    _invalid_parameter_internal
0x18001ee91  mov     rcx, [rbx+8]; this
0x18001ee95  test    rcx, rcx
0x18001ee98  jz      loc_18001F05B
0x18001ee9e  mov     rax, [rbx]
0x18001eea1  mov     [rcx], rax
0x18001eea4  jmp     loc_18001F05B
0x18001eea9  movzx   edi, byte ptr [r12]
0x18001eeae  lea     rax, [r12+1]
0x18001eeb3  xor     ebp, ebp
0x18001eeb5  mov     [rdx], rax
0x18001eeb8  cmp     [rcx+28h], bpl
0x18001eebc  jnz     short loc_18001EED1
0x18001eebe  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001eec3  jmp     short loc_18001EED1
0x18001eec5  mov     rax, [rbx]
0x18001eec8  movzx   edi, byte ptr [rax]
0x18001eecb  inc     rax
0x18001eece  mov     [rbx], rax
0x18001eed1  lea     r8, [r15+18h]; Locale
0x18001eed5  mov     edx, 8; Mask
0x18001eeda  mov     ecx, edi; C
0x18001eedc  call    _ischartype_l
0x18001eee1  test    eax, eax
0x18001eee3  jnz     short loc_18001EEC5
0x18001eee5  mov     r14d, r13d
0x18001eee8  lea     eax, [rdi-2Bh]
0x18001eeeb  or      r14d, 2
0x18001eeef  cmp     dil, 2Dh ; '-'
0x18001eef3  cmovnz  r14d, r13d
0x18001eef7  test    al, 0FDh
0x18001eef9  jnz     short loc_18001EF07
0x18001eefb  mov     rax, [rbx]
0x18001eefe  mov     dil, [rax]
0x18001ef01  inc     rax
0x18001ef04  mov     [rbx], rax
0x18001ef07  mov     r13b, 19h
0x18001ef0a  test    esi, 0FFFFFFEFh
0x18001ef10  jnz     loc_18001EFA3
0x18001ef16  lea     eax, [rdi-30h]
0x18001ef19  cmp     al, 9
0x18001ef1b  ja      short loc_18001EF26
0x18001ef1d  movsx   eax, dil
0x18001ef21  add     eax, 0FFFFFFD0h
0x18001ef24  jmp     short loc_18001EF46
0x18001ef26  lea     eax, [rdi-61h]
0x18001ef29  cmp     al, r13b
0x18001ef2c  ja      short loc_18001EF37
0x18001ef2e  movsx   eax, dil
0x18001ef32  add     eax, 0FFFFFFA9h
0x18001ef35  jmp     short loc_18001EF46
0x18001ef37  lea     eax, [rdi-41h]
0x18001ef3a  cmp     al, r13b
0x18001ef3d  ja      short loc_18001EF97
0x18001ef3f  movsx   eax, dil
0x18001ef43  add     eax, 0FFFFFFC9h
0x18001ef46  test    eax, eax
0x18001ef48  jnz     short loc_18001EF97
0x18001ef4a  mov     rcx, [rbx]
0x18001ef4d  mov     dl, [rcx]
0x18001ef4f  lea     r8, [rcx+1]
0x18001ef53  mov     [rbx], r8
0x18001ef56  lea     eax, [rdx-58h]
0x18001ef59  test    al, 0DFh
0x18001ef5b  jz      short loc_18001EF86
0x18001ef5d  test    esi, esi
0x18001ef5f  mov     [rbx], rcx
0x18001ef62  mov     eax, 8
0x18001ef67  cmovnz  eax, esi
0x18001ef6a  mov     esi, eax
0x18001ef6c  test    dl, dl
0x18001ef6e  jz      short loc_18001EFA3
0x18001ef70  cmp     [rcx], dl
0x18001ef72  jz      short loc_18001EFA3
0x18001ef74  call    _errno
0x18001ef79  mov     dword ptr [rax], 16h
0x18001ef7f  call    _invalid_parameter_noinfo
0x18001ef84  jmp     short loc_18001EFA3
0x18001ef86  mov     dil, [r8]
0x18001ef89  lea     rax, [r8+1]
0x18001ef8d  mov     [rbx], rax
0x18001ef90  mov     eax, 10h
0x18001ef95  jmp     short loc_18001EF9C
0x18001ef97  mov     eax, 0Ah
0x18001ef9c  test    esi, esi
0x18001ef9e  cmovnz  eax, esi
0x18001efa1  mov     esi, eax
0x18001efa3  movsxd  r9, esi
0x18001efa6  xor     edx, edx
0x18001efa8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001efac  div     r9
0x18001efaf  mov     r10, rax
0x18001efb2  lea     ecx, [rdi-30h]
0x18001efb5  cmp     cl, 9
0x18001efb8  ja      short loc_18001EFC3
0x18001efba  movsx   ecx, dil
0x18001efbe  add     ecx, 0FFFFFFD0h
0x18001efc1  jmp     short loc_18001EFE8
0x18001efc3  lea     eax, [rdi-61h]
0x18001efc6  cmp     al, r13b
0x18001efc9  ja      short loc_18001EFD4
0x18001efcb  movsx   ecx, dil
0x18001efcf  add     ecx, 0FFFFFFA9h
0x18001efd2  jmp     short loc_18001EFE8
0x18001efd4  lea     eax, [rdi-41h]
0x18001efd7  cmp     al, r13b
0x18001efda  ja      short loc_18001EFE5
0x18001efdc  movsx   ecx, dil
0x18001efe0  add     ecx, 0FFFFFFC9h
0x18001efe3  jmp     short loc_18001EFE8
0x18001efe5  or      ecx, 0FFFFFFFFh
0x18001efe8  mov     r8, [rbx]
0x18001efeb  cmp     ecx, esi
0x18001efed  jnb     short loc_18001F025
0x18001efef  mov     dil, [r8]
0x18001eff2  mov     rax, r9
0x18001eff5  imul    rax, rbp
0x18001eff9  mov     edx, ecx
0x18001effb  xor     ecx, ecx
0x18001effd  add     rdx, rax
0x18001f000  cmp     rdx, rax
0x18001f003  setb    cl
0x18001f006  xor     eax, eax
0x18001f008  cmp     rbp, r10
0x18001f00b  mov     rbp, rdx
0x18001f00e  setnbe  al
0x18001f011  or      ecx, eax
0x18001f013  lea     rax, [r8+1]
0x18001f017  shl     ecx, 2
0x18001f01a  or      ecx, 8
0x18001f01d  mov     [rbx], rax
0x18001f020  or      r14d, ecx
0x18001f023  jmp     short loc_18001EFB2
0x18001f025  lea     rax, [r8-1]
0x18001f029  mov     [rbx], rax
0x18001f02c  test    dil, dil
0x18001f02f  jz      short loc_18001F046
0x18001f031  cmp     [rax], dil
0x18001f034  jz      short loc_18001F046
0x18001f036  call    _errno
0x18001f03b  mov     dword ptr [rax], 16h
0x18001f041  call    _invalid_parameter_noinfo
0x18001f046  test    r14b, 8
0x18001f04a  jnz     short loc_18001F05F
0x18001f04c  mov     rax, [rbx+8]
0x18001f050  mov     [rbx], r12
0x18001f053  test    rax, rax
0x18001f056  jz      short loc_18001F05B
0x18001f058  mov     [rax], r12
0x18001f05b  xor     eax, eax
0x18001f05d  jmp     short loc_18001F0DA
0x18001f05f  mov     rdx, rbp
0x18001f062  mov     ecx, r14d
0x18001f065  call    ??$is_overflow_condition@_K@__crt_strtox@@YA_NI_K@Z; __crt_strtox::is_overflow_condition<unsigned __int64>(uint,unsigned __int64)
0x18001f06a  test    al, al
0x18001f06c  jz      short loc_18001F0BF
0x18001f06e  mov     byte ptr [r15+30h], 1
0x18001f073  mov     dword ptr [r15+2Ch], 22h ; '"'
0x18001f07b  test    r14b, 1
0x18001f07f  jnz     short loc_18001F087
0x18001f081  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001f085  jmp     short loc_18001F0C8
0x18001f087  mov     rcx, [rbx+8]
0x18001f08b  test    r14b, 2
0x18001f08f  jz      short loc_18001F0A8
0x18001f091  test    rcx, rcx
0x18001f094  jz      short loc_18001F09C
0x18001f096  mov     rax, [rbx]
0x18001f099  mov     [rcx], rax
0x18001f09c  mov     rax, 8000000000000000h
0x18001f0a6  jmp     short loc_18001F0DA
0x18001f0a8  test    rcx, rcx
0x18001f0ab  jz      short loc_18001F0B3
0x18001f0ad  mov     rax, [rbx]
0x18001f0b0  mov     [rcx], rax
0x18001f0b3  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001f0bd  jmp     short loc_18001F0DA
0x18001f0bf  test    r14b, 2
0x18001f0c3  jz      short loc_18001F0C8
0x18001f0c5  neg     rbp
0x18001f0c8  mov     rax, [rbx+8]
0x18001f0cc  test    rax, rax
0x18001f0cf  jz      short loc_18001F0D7
0x18001f0d1  mov     rcx, [rbx]
0x18001f0d4  mov     [rax], rcx
0x18001f0d7  mov     rax, rbp
0x18001f0da  mov     rbx, [rsp+58h+arg_0]
0x18001f0df  mov     rbp, [rsp+58h+arg_8]
0x18001f0e4  mov     rsi, [rsp+58h+arg_10]
0x18001f0e9  add     rsp, 30h
0x18001f0ed  pop     r15
0x18001f0ef  pop     r14
0x18001f0f1  pop     r13
0x18001f0f3  pop     r12
0x18001f0f5  pop     rdi
0x18001f0f6  retn
```
