# __crt_strtox::parse_integer<ulong,__crt_strtox::c_string_character_source<char>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x18001dc44`
- end: `0x18001df1d`
- name: `??$parse_integer@KV?$c_string_character_source@D@__crt_strtox@@$00@__crt_strtox@@YAKAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `729`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001f11c`
- `0x18001fad8`
- `0x18001fb94`
- `0x1800203a0`
- `0x180020450`

## callees

- `0x1800073e8`
- `0x1800074a0`
- `0x180007788`
- `0x1800149cc`
- `0x18001dc44`
- `0x18001fd70`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned long,__crt_strtox::c_string_character_source<char>,1>(
        __crt_cached_ptd_host *a1,
        unsigned __int8 **a2,
        unsigned int a3,
        char a4)
{
  unsigned __int8 *v4; // r12
  unsigned int v5; // esi
  unsigned __int8 *v9; // rcx
  int v10; // edi
  unsigned int v11; // r14d
  char v12; // bp
  int v13; // eax
  unsigned __int8 *v14; // rcx
  char v15; // dl
  unsigned __int8 *v16; // r8
  int v17; // eax
  int v18; // eax
  unsigned int v19; // r9d
  unsigned int v20; // ecx
  unsigned __int8 *v21; // r8
  unsigned int v22; // edx
  bool v23; // cl
  bool v24; // cf
  bool v25; // zf
  unsigned __int8 *v26; // rax
  __int64 result; // rax
  unsigned __int8 *v28; // rax
  unsigned __int8 *v29; // rdx

  v4 = *a2;
  v5 = a3;
  if ( !*a2 )
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_6;
  }
  if ( a3 && a3 - 2 > 0x22 )
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
  v12 = a4 | 2;
  if ( (_BYTE)v10 != 45 )
    v12 = a4;
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
  v19 = 0xFFFFFFFF / v5;
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
    v22 = v5 * v11 + v20;
    v23 = v22 < v5 * v11;
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
  result = 0x7FFFFFFF;
  if ( (v12 & 4) == 0 )
  {
    if ( (v12 & 1) == 0 )
    {
      if ( (v12 & 2) == 0 )
        goto LABEL_58;
      goto LABEL_64;
    }
    if ( (v12 & 2) != 0 )
    {
      if ( v11 > 0x80000000 )
        goto LABEL_56;
LABEL_64:
      v11 = -v11;
      goto LABEL_58;
    }
    if ( v11 <= 0x7FFFFFFF )
      goto LABEL_58;
  }
LABEL_56:
  *((_BYTE *)a1 + 48) = 1;
  *((_DWORD *)a1 + 11) = 34;
  if ( (v12 & 1) == 0 )
  {
    v11 = -1;
LABEL_58:
    v28 = a2[1];
    if ( v28 )
      *(_QWORD *)v28 = *a2;
    return v11;
  }
  v29 = a2[1];
  if ( (v12 & 2) != 0 )
  {
    if ( v29 )
      *(_QWORD *)v29 = *a2;
    return 0x80000000LL;
  }
  else if ( v29 )
  {
    *(_QWORD *)v29 = *a2;
  }
  return result;
}

```

## disassembly

```asm
0x18001dc44  mov     [rsp+arg_0], rbx
0x18001dc49  mov     [rsp+arg_8], rbp
0x18001dc4e  mov     [rsp+arg_10], rsi
0x18001dc53  push    rdi
0x18001dc54  push    r12
0x18001dc56  push    r13
0x18001dc58  push    r14
0x18001dc5a  push    r15
0x18001dc5c  sub     rsp, 30h
0x18001dc60  mov     r12, [rdx]
0x18001dc63  mov     esi, r8d
0x18001dc66  movzx   r13d, r9b
0x18001dc6a  mov     rbx, rdx
0x18001dc6d  mov     r15, rcx
0x18001dc70  test    r12, r12
0x18001dc73  jnz     short loc_18001DC87
0x18001dc75  call    _errno
0x18001dc7a  mov     dword ptr [rax], 16h
0x18001dc80  call    _invalid_parameter_noinfo
0x18001dc85  jmp     short loc_18001DCB9
0x18001dc87  test    esi, esi
0x18001dc89  jz      short loc_18001DCD1
0x18001dc8b  lea     eax, [r8-2]
0x18001dc8f  cmp     eax, 22h ; '"'
0x18001dc92  jbe     short loc_18001DCD1
0x18001dc94  mov     byte ptr [rcx+30h], 1
0x18001dc98  xor     r9d, r9d; LineNo
0x18001dc9b  mov     dword ptr [rcx+2Ch], 16h
0x18001dca2  xor     r8d, r8d; FileName
0x18001dca5  mov     [rsp+58h+var_30], r15; __crt_cached_ptd_host *
0x18001dcaa  xor     ecx, ecx; Expression
0x18001dcac  and     [rsp+58h+var_38], 0
0x18001dcb2  xor     edx, edx; FunctionName
0x18001dcb4  call    _invalid_parameter_internal
0x18001dcb9  mov     rcx, [rbx+8]; this
0x18001dcbd  test    rcx, rcx
0x18001dcc0  jz      loc_18001DE76
0x18001dcc6  mov     rax, [rbx]
0x18001dcc9  mov     [rcx], rax
0x18001dccc  jmp     loc_18001DE76
0x18001dcd1  movzx   edi, byte ptr [r12]
0x18001dcd6  lea     rax, [r12+1]
0x18001dcdb  xor     r14d, r14d
0x18001dcde  mov     [rdx], rax
0x18001dce1  cmp     [rcx+28h], r14b
0x18001dce5  jnz     short loc_18001DCFA
0x18001dce7  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001dcec  jmp     short loc_18001DCFA
0x18001dcee  mov     rax, [rbx]
0x18001dcf1  movzx   edi, byte ptr [rax]
0x18001dcf4  inc     rax
0x18001dcf7  mov     [rbx], rax
0x18001dcfa  lea     r8, [r15+18h]; Locale
0x18001dcfe  mov     edx, 8; Mask
0x18001dd03  mov     ecx, edi; C
0x18001dd05  call    _ischartype_l
0x18001dd0a  test    eax, eax
0x18001dd0c  jnz     short loc_18001DCEE
0x18001dd0e  mov     ebp, r13d
0x18001dd11  lea     eax, [rdi-2Bh]
0x18001dd14  or      ebp, 2
0x18001dd17  cmp     dil, 2Dh ; '-'
0x18001dd1b  cmovnz  ebp, r13d
0x18001dd1f  test    al, 0FDh
0x18001dd21  jnz     short loc_18001DD2F
0x18001dd23  mov     rax, [rbx]
0x18001dd26  mov     dil, [rax]
0x18001dd29  inc     rax
0x18001dd2c  mov     [rbx], rax
0x18001dd2f  test    esi, 0FFFFFFEFh
0x18001dd35  jnz     loc_18001DDC6
0x18001dd3b  lea     eax, [rdi-30h]
0x18001dd3e  cmp     al, 9
0x18001dd40  ja      short loc_18001DD4B
0x18001dd42  movsx   eax, dil
0x18001dd46  add     eax, 0FFFFFFD0h
0x18001dd49  jmp     short loc_18001DD69
0x18001dd4b  lea     eax, [rdi-61h]
0x18001dd4e  cmp     al, 19h
0x18001dd50  ja      short loc_18001DD5B
0x18001dd52  movsx   eax, dil
0x18001dd56  add     eax, 0FFFFFFA9h
0x18001dd59  jmp     short loc_18001DD69
0x18001dd5b  lea     eax, [rdi-41h]
0x18001dd5e  cmp     al, 19h
0x18001dd60  ja      short loc_18001DDBA
0x18001dd62  movsx   eax, dil
0x18001dd66  add     eax, 0FFFFFFC9h
0x18001dd69  test    eax, eax
0x18001dd6b  jnz     short loc_18001DDBA
0x18001dd6d  mov     rcx, [rbx]
0x18001dd70  mov     dl, [rcx]
0x18001dd72  lea     r8, [rcx+1]
0x18001dd76  mov     [rbx], r8
0x18001dd79  lea     eax, [rdx-58h]
0x18001dd7c  test    al, 0DFh
0x18001dd7e  jz      short loc_18001DDA9
0x18001dd80  test    esi, esi
0x18001dd82  mov     [rbx], rcx
0x18001dd85  mov     eax, 8
0x18001dd8a  cmovnz  eax, esi
0x18001dd8d  mov     esi, eax
0x18001dd8f  test    dl, dl
0x18001dd91  jz      short loc_18001DDC6
0x18001dd93  cmp     [rcx], dl
0x18001dd95  jz      short loc_18001DDC6
0x18001dd97  call    _errno
0x18001dd9c  mov     dword ptr [rax], 16h
0x18001dda2  call    _invalid_parameter_noinfo
0x18001dda7  jmp     short loc_18001DDC6
0x18001dda9  mov     dil, [r8]
0x18001ddac  lea     rax, [r8+1]
0x18001ddb0  mov     [rbx], rax
0x18001ddb3  mov     eax, 10h
0x18001ddb8  jmp     short loc_18001DDBF
0x18001ddba  mov     eax, 0Ah
0x18001ddbf  test    esi, esi
0x18001ddc1  cmovnz  eax, esi
0x18001ddc4  mov     esi, eax
0x18001ddc6  or      r13d, 0FFFFFFFFh
0x18001ddca  xor     edx, edx
0x18001ddcc  mov     eax, r13d
0x18001ddcf  div     esi
0x18001ddd1  mov     r9d, eax
0x18001ddd4  lea     ecx, [rdi-30h]
0x18001ddd7  cmp     cl, 9
0x18001ddda  ja      short loc_18001DDE5
0x18001dddc  movsx   ecx, dil
0x18001dde0  add     ecx, 0FFFFFFD0h
0x18001dde3  jmp     short loc_18001DE08
0x18001dde5  lea     eax, [rdi-61h]
0x18001dde8  cmp     al, 19h
0x18001ddea  ja      short loc_18001DDF5
0x18001ddec  movsx   ecx, dil
0x18001ddf0  add     ecx, 0FFFFFFA9h
0x18001ddf3  jmp     short loc_18001DE08
0x18001ddf5  lea     eax, [rdi-41h]
0x18001ddf8  cmp     al, 19h
0x18001ddfa  ja      short loc_18001DE05
0x18001ddfc  movsx   ecx, dil
0x18001de00  add     ecx, 0FFFFFFC9h
0x18001de03  jmp     short loc_18001DE08
0x18001de05  mov     ecx, r13d
0x18001de08  mov     r8, [rbx]
0x18001de0b  cmp     ecx, esi
0x18001de0d  jnb     short loc_18001DE40
0x18001de0f  mov     dil, [r8]
0x18001de12  mov     eax, r14d
0x18001de15  imul    eax, esi
0x18001de18  lea     edx, [rax+rcx]
0x18001de1b  xor     ecx, ecx
0x18001de1d  cmp     edx, eax
0x18001de1f  setb    cl
0x18001de22  xor     eax, eax
0x18001de24  cmp     r14d, r9d
0x18001de27  mov     r14d, edx
0x18001de2a  setnbe  al
0x18001de2d  or      ecx, eax
0x18001de2f  lea     rax, [r8+1]
0x18001de33  shl     ecx, 2
0x18001de36  or      ecx, 8
0x18001de39  mov     [rbx], rax
0x18001de3c  or      ebp, ecx
0x18001de3e  jmp     short loc_18001DDD4
0x18001de40  lea     rax, [r8-1]
0x18001de44  mov     [rbx], rax
0x18001de47  test    dil, dil
0x18001de4a  jz      short loc_18001DE61
0x18001de4c  cmp     [rax], dil
0x18001de4f  jz      short loc_18001DE61
0x18001de51  call    _errno
0x18001de56  mov     dword ptr [rax], 16h
0x18001de5c  call    _invalid_parameter_noinfo
0x18001de61  test    bpl, 8
0x18001de65  jnz     short loc_18001DE7D
0x18001de67  mov     rax, [rbx+8]
0x18001de6b  mov     [rbx], r12
0x18001de6e  test    rax, rax
0x18001de71  jz      short loc_18001DE76
0x18001de73  mov     [rax], r12
0x18001de76  xor     eax, eax
0x18001de78  jmp     loc_18001DF00
0x18001de7d  mov     eax, 7FFFFFFFh
0x18001de82  mov     r8d, 80000000h
0x18001de88  test    bpl, 4
0x18001de8c  jnz     short loc_18001DE9F
0x18001de8e  test    bpl, 1
0x18001de92  jz      short loc_18001DED0
0x18001de94  test    bpl, 2
0x18001de98  jz      short loc_18001DEC9
0x18001de9a  cmp     r14d, r8d
0x18001de9d  jbe     short loc_18001DED6
0x18001de9f  mov     byte ptr [r15+30h], 1
0x18001dea4  mov     dword ptr [r15+2Ch], 22h ; '"'
0x18001deac  test    bpl, 1
0x18001deb0  jnz     short loc_18001DEDB
0x18001deb2  mov     r14d, r13d
0x18001deb5  mov     rax, [rbx+8]
0x18001deb9  test    rax, rax
0x18001debc  jz      short loc_18001DEC4
0x18001debe  mov     rcx, [rbx]
0x18001dec1  mov     [rax], rcx
0x18001dec4  mov     eax, r14d
0x18001dec7  jmp     short loc_18001DF00
0x18001dec9  cmp     r14d, eax
0x18001decc  jbe     short loc_18001DEB5
0x18001dece  jmp     short loc_18001DE9F
0x18001ded0  test    bpl, 2
0x18001ded4  jz      short loc_18001DEB5
0x18001ded6  neg     r14d
0x18001ded9  jmp     short loc_18001DEB5
0x18001dedb  mov     rdx, [rbx+8]
0x18001dedf  test    bpl, 2
0x18001dee3  jz      short loc_18001DEF5
0x18001dee5  test    rdx, rdx
0x18001dee8  jz      short loc_18001DEF0
0x18001deea  mov     rcx, [rbx]
0x18001deed  mov     [rdx], rcx
0x18001def0  mov     eax, r8d
0x18001def3  jmp     short loc_18001DF00
0x18001def5  test    rdx, rdx
0x18001def8  jz      short loc_18001DF00
0x18001defa  mov     rcx, [rbx]
0x18001defd  mov     [rdx], rcx
0x18001df00  mov     rbx, [rsp+58h+arg_0]
0x18001df05  mov     rbp, [rsp+58h+arg_8]
0x18001df0a  mov     rsi, [rsp+58h+arg_10]
0x18001df0f  add     rsp, 30h
0x18001df13  pop     r15
0x18001df15  pop     r14
0x18001df17  pop     r13
0x18001df19  pop     r12
0x18001df1b  pop     rdi
0x18001df1c  retn
```
