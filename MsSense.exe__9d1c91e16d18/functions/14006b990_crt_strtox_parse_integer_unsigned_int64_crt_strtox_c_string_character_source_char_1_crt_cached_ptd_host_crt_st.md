# __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<char>,1>(__crt_cached_ptd_host &,__crt_strtox::c_string_character_source<char>,int,bool)

- ea: `0x14006b990`
- end: `0x14006bc69`
- name: `??$parse_integer@_KV?$c_string_character_source@D@__crt_strtox@@$00@__crt_strtox@@YA_KAEAV__crt_cached_ptd_host@@V?$c_string_character_source@D@0@H_N@Z`
- size: `729`
- prototype: `__int64 __fastcall(__crt_cached_ptd_host *, unsigned __int8 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140071bc0`

## callees

- `0x14004d500`
- `0x14006147c`
- `0x140061534`
- `0x1400616b4`
- `0x140065e50`
- `0x14006b990`

## pseudocode

```c
__int64 __fastcall __crt_strtox::parse_integer<unsigned __int64,__crt_strtox::c_string_character_source<char>,1>(
        __crt_cached_ptd_host *a1,
        unsigned __int8 **a2,
        __int64 a3,
        __int64 a4)
{
  unsigned __int8 *v4; // r12
  unsigned int v5; // esi
  char v6; // r13
  unsigned __int8 *v9; // rcx
  unsigned int v10; // edi
  unsigned int v11; // r14d
  __int64 v12; // rdx
  __int64 v13; // r9
  char v14; // bp
  int v15; // eax
  unsigned __int8 *v16; // rcx
  unsigned __int8 *v17; // r8
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // rcx
  unsigned __int8 *v23; // r8
  bool v24; // cl
  bool v25; // cf
  bool v26; // zf
  unsigned __int8 *v27; // rax
  __int64 result; // rax
  unsigned __int8 *v29; // rax
  unsigned __int8 *v30; // rdx

  v4 = *a2;
  v5 = a3;
  v6 = a4;
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
  while ( (unsigned int)sub_14004D500(v10, 8, (char *)a1 + 24) )
    v10 = *(*a2)++;
  v14 = v6 | 2;
  if ( (_BYTE)v10 != 45 )
    v14 = v6;
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
        v15 = (char)v10 - 55;
      }
      else
      {
        v15 = (char)v10 - 87;
      }
    }
    else
    {
      v15 = (char)v10 - 48;
    }
    if ( !v15 )
    {
      v16 = *a2;
      LOBYTE(v12) = **a2;
      v17 = *a2 + 1;
      *a2 = v17;
      if ( (((_BYTE)v12 - 88) & 0xDF) != 0 )
      {
        *a2 = v16;
        v18 = 8;
        if ( v5 )
          v18 = v5;
        v5 = v18;
        if ( (_BYTE)v12 && *v16 != (_BYTE)v12 )
        {
          *(_DWORD *)sub_1400616B4(v16, v12, v17, v13) = 22;
          invalid_parameter_noinfo();
        }
        goto LABEL_35;
      }
      LOBYTE(v10) = *v17;
      *a2 = v17 + 1;
      v19 = 16;
      goto LABEL_32;
    }
LABEL_31:
    v19 = 10;
LABEL_32:
    if ( v5 )
      v19 = v5;
    v5 = v19;
  }
LABEL_35:
  v20 = 0xFFFFFFFF % v5;
  v21 = 0xFFFFFFFF / v5;
  while ( 1 )
  {
    if ( (unsigned __int8)(v10 - 48) > 9u )
    {
      if ( (unsigned __int8)(v10 - 97) > 0x19u )
        v22 = (unsigned __int8)(v10 - 65) > 0x19u ? 0xFFFFFFFFLL : (unsigned int)((char)v10 - 55);
      else
        v22 = (unsigned int)((char)v10 - 87);
    }
    else
    {
      v22 = (unsigned int)((char)v10 - 48);
    }
    v23 = *a2;
    if ( (unsigned int)v22 >= v5 )
      break;
    LOBYTE(v10) = *v23;
    v20 = v5 * v11 + (unsigned int)v22;
    v24 = (unsigned int)v20 < v5 * v11;
    v25 = v11 < (unsigned int)v21;
    v26 = v11 == (_DWORD)v21;
    v11 = v20;
    *a2 = v23 + 1;
    v14 |= (4 * (!v25 && !v26 || v24)) | 8;
  }
  *a2 = v23 - 1;
  if ( (_BYTE)v10 && *(v23 - 1) != (_BYTE)v10 )
  {
    *(_DWORD *)sub_1400616B4(v22, v20, v23, v21) = 22;
    invalid_parameter_noinfo();
  }
  if ( (v14 & 8) == 0 )
  {
    v27 = a2[1];
    *a2 = v4;
    if ( v27 )
      *(_QWORD *)v27 = v4;
    return 0;
  }
  result = 0x7FFFFFFF;
  if ( (v14 & 4) == 0 )
  {
    if ( (v14 & 1) == 0 )
    {
      if ( (v14 & 2) == 0 )
        goto LABEL_58;
      goto LABEL_64;
    }
    if ( (v14 & 2) != 0 )
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
  if ( (v14 & 1) == 0 )
  {
    v11 = -1;
LABEL_58:
    v29 = a2[1];
    if ( v29 )
      *(_QWORD *)v29 = *a2;
    return v11;
  }
  v30 = a2[1];
  if ( (v14 & 2) != 0 )
  {
    if ( v30 )
      *(_QWORD *)v30 = *a2;
    return 0x80000000LL;
  }
  else if ( v30 )
  {
    *(_QWORD *)v30 = *a2;
  }
  return result;
}

```

## disassembly

```asm
0x14006b990  mov     [rsp+arg_0], rbx
0x14006b995  mov     [rsp+arg_8], rbp
0x14006b99a  mov     [rsp+arg_10], rsi
0x14006b99f  push    rdi
0x14006b9a0  push    r12
0x14006b9a2  push    r13
0x14006b9a4  push    r14
0x14006b9a6  push    r15
0x14006b9a8  sub     rsp, 30h
0x14006b9ac  mov     r12, [rdx]
0x14006b9af  mov     esi, r8d
0x14006b9b2  movzx   r13d, r9b
0x14006b9b6  mov     rbx, rdx
0x14006b9b9  mov     r15, rcx
0x14006b9bc  test    r12, r12
0x14006b9bf  jnz     short loc_14006B9D3
0x14006b9c1  call    sub_1400616B4
0x14006b9c6  mov     dword ptr [rax], 16h
0x14006b9cc  call    _invalid_parameter_noinfo
0x14006b9d1  jmp     short loc_14006BA05
0x14006b9d3  test    esi, esi
0x14006b9d5  jz      short loc_14006BA1D
0x14006b9d7  lea     eax, [r8-2]
0x14006b9db  cmp     eax, 22h ; '"'
0x14006b9de  jbe     short loc_14006BA1D
0x14006b9e0  mov     byte ptr [rcx+30h], 1
0x14006b9e4  xor     r9d, r9d; LineNo
0x14006b9e7  mov     dword ptr [rcx+2Ch], 16h
0x14006b9ee  xor     r8d, r8d; FileName
0x14006b9f1  mov     [rsp+58h+var_30], r15; __crt_cached_ptd_host *
0x14006b9f6  xor     ecx, ecx; Expression
0x14006b9f8  and     [rsp+58h+var_38], 0
0x14006b9fe  xor     edx, edx; FunctionName
0x14006ba00  call    sub_14006147C
0x14006ba05  mov     rcx, [rbx+8]; this
0x14006ba09  test    rcx, rcx
0x14006ba0c  jz      loc_14006BBC2
0x14006ba12  mov     rax, [rbx]
0x14006ba15  mov     [rcx], rax
0x14006ba18  jmp     loc_14006BBC2
0x14006ba1d  movzx   edi, byte ptr [r12]
0x14006ba22  lea     rax, [r12+1]
0x14006ba27  xor     r14d, r14d
0x14006ba2a  mov     [rdx], rax
0x14006ba2d  cmp     [rcx+28h], r14b
0x14006ba31  jnz     short loc_14006BA46
0x14006ba33  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14006ba38  jmp     short loc_14006BA46
0x14006ba3a  mov     rax, [rbx]
0x14006ba3d  movzx   edi, byte ptr [rax]
0x14006ba40  inc     rax
0x14006ba43  mov     [rbx], rax
0x14006ba46  lea     r8, [r15+18h]
0x14006ba4a  mov     edx, 8
0x14006ba4f  mov     ecx, edi
0x14006ba51  call    sub_14004D500
0x14006ba56  test    eax, eax
0x14006ba58  jnz     short loc_14006BA3A
0x14006ba5a  mov     ebp, r13d
0x14006ba5d  lea     eax, [rdi-2Bh]
0x14006ba60  or      ebp, 2
0x14006ba63  cmp     dil, 2Dh ; '-'
0x14006ba67  cmovnz  ebp, r13d
0x14006ba6b  test    al, 0FDh
0x14006ba6d  jnz     short loc_14006BA7B
0x14006ba6f  mov     rax, [rbx]
0x14006ba72  mov     dil, [rax]
0x14006ba75  inc     rax
0x14006ba78  mov     [rbx], rax
0x14006ba7b  test    esi, 0FFFFFFEFh
0x14006ba81  jnz     loc_14006BB12
0x14006ba87  lea     eax, [rdi-30h]
0x14006ba8a  cmp     al, 9
0x14006ba8c  ja      short loc_14006BA97
0x14006ba8e  movsx   eax, dil
0x14006ba92  add     eax, 0FFFFFFD0h
0x14006ba95  jmp     short loc_14006BAB5
0x14006ba97  lea     eax, [rdi-61h]
0x14006ba9a  cmp     al, 19h
0x14006ba9c  ja      short loc_14006BAA7
0x14006ba9e  movsx   eax, dil
0x14006baa2  add     eax, 0FFFFFFA9h
0x14006baa5  jmp     short loc_14006BAB5
0x14006baa7  lea     eax, [rdi-41h]
0x14006baaa  cmp     al, 19h
0x14006baac  ja      short loc_14006BB06
0x14006baae  movsx   eax, dil
0x14006bab2  add     eax, 0FFFFFFC9h
0x14006bab5  test    eax, eax
0x14006bab7  jnz     short loc_14006BB06
0x14006bab9  mov     rcx, [rbx]
0x14006babc  mov     dl, [rcx]
0x14006babe  lea     r8, [rcx+1]
0x14006bac2  mov     [rbx], r8
0x14006bac5  lea     eax, [rdx-58h]
0x14006bac8  test    al, 0DFh
0x14006baca  jz      short loc_14006BAF5
0x14006bacc  test    esi, esi
0x14006bace  mov     [rbx], rcx
0x14006bad1  mov     eax, 8
0x14006bad6  cmovnz  eax, esi
0x14006bad9  mov     esi, eax
0x14006badb  test    dl, dl
0x14006badd  jz      short loc_14006BB12
0x14006badf  cmp     [rcx], dl
0x14006bae1  jz      short loc_14006BB12
0x14006bae3  call    sub_1400616B4
0x14006bae8  mov     dword ptr [rax], 16h
0x14006baee  call    _invalid_parameter_noinfo
0x14006baf3  jmp     short loc_14006BB12
0x14006baf5  mov     dil, [r8]
0x14006baf8  lea     rax, [r8+1]
0x14006bafc  mov     [rbx], rax
0x14006baff  mov     eax, 10h
0x14006bb04  jmp     short loc_14006BB0B
0x14006bb06  mov     eax, 0Ah
0x14006bb0b  test    esi, esi
0x14006bb0d  cmovnz  eax, esi
0x14006bb10  mov     esi, eax
0x14006bb12  or      r13d, 0FFFFFFFFh
0x14006bb16  xor     edx, edx
0x14006bb18  mov     eax, r13d
0x14006bb1b  div     esi
0x14006bb1d  mov     r9d, eax
0x14006bb20  lea     ecx, [rdi-30h]
0x14006bb23  cmp     cl, 9
0x14006bb26  ja      short loc_14006BB31
0x14006bb28  movsx   ecx, dil
0x14006bb2c  add     ecx, 0FFFFFFD0h
0x14006bb2f  jmp     short loc_14006BB54
0x14006bb31  lea     eax, [rdi-61h]
0x14006bb34  cmp     al, 19h
0x14006bb36  ja      short loc_14006BB41
0x14006bb38  movsx   ecx, dil
0x14006bb3c  add     ecx, 0FFFFFFA9h
0x14006bb3f  jmp     short loc_14006BB54
0x14006bb41  lea     eax, [rdi-41h]
0x14006bb44  cmp     al, 19h
0x14006bb46  ja      short loc_14006BB51
0x14006bb48  movsx   ecx, dil
0x14006bb4c  add     ecx, 0FFFFFFC9h
0x14006bb4f  jmp     short loc_14006BB54
0x14006bb51  mov     ecx, r13d
0x14006bb54  mov     r8, [rbx]
0x14006bb57  cmp     ecx, esi
0x14006bb59  jnb     short loc_14006BB8C
0x14006bb5b  mov     dil, [r8]
0x14006bb5e  mov     eax, r14d
0x14006bb61  imul    eax, esi
0x14006bb64  lea     edx, [rax+rcx]
0x14006bb67  xor     ecx, ecx
0x14006bb69  cmp     edx, eax
0x14006bb6b  setb    cl
0x14006bb6e  xor     eax, eax
0x14006bb70  cmp     r14d, r9d
0x14006bb73  mov     r14d, edx
0x14006bb76  setnbe  al
0x14006bb79  or      ecx, eax
0x14006bb7b  lea     rax, [r8+1]
0x14006bb7f  shl     ecx, 2
0x14006bb82  or      ecx, 8
0x14006bb85  mov     [rbx], rax
0x14006bb88  or      ebp, ecx
0x14006bb8a  jmp     short loc_14006BB20
0x14006bb8c  lea     rax, [r8-1]
0x14006bb90  mov     [rbx], rax
0x14006bb93  test    dil, dil
0x14006bb96  jz      short loc_14006BBAD
0x14006bb98  cmp     [rax], dil
0x14006bb9b  jz      short loc_14006BBAD
0x14006bb9d  call    sub_1400616B4
0x14006bba2  mov     dword ptr [rax], 16h
0x14006bba8  call    _invalid_parameter_noinfo
0x14006bbad  test    bpl, 8
0x14006bbb1  jnz     short loc_14006BBC9
0x14006bbb3  mov     rax, [rbx+8]
0x14006bbb7  mov     [rbx], r12
0x14006bbba  test    rax, rax
0x14006bbbd  jz      short loc_14006BBC2
0x14006bbbf  mov     [rax], r12
0x14006bbc2  xor     eax, eax
0x14006bbc4  jmp     loc_14006BC4C
0x14006bbc9  mov     eax, 7FFFFFFFh
0x14006bbce  mov     r8d, 80000000h
0x14006bbd4  test    bpl, 4
0x14006bbd8  jnz     short loc_14006BBEB
0x14006bbda  test    bpl, 1
0x14006bbde  jz      short loc_14006BC1C
0x14006bbe0  test    bpl, 2
0x14006bbe4  jz      short loc_14006BC15
0x14006bbe6  cmp     r14d, r8d
0x14006bbe9  jbe     short loc_14006BC22
0x14006bbeb  mov     byte ptr [r15+30h], 1
0x14006bbf0  mov     dword ptr [r15+2Ch], 22h ; '"'
0x14006bbf8  test    bpl, 1
0x14006bbfc  jnz     short loc_14006BC27
0x14006bbfe  mov     r14d, r13d
0x14006bc01  mov     rax, [rbx+8]
0x14006bc05  test    rax, rax
0x14006bc08  jz      short loc_14006BC10
0x14006bc0a  mov     rcx, [rbx]
0x14006bc0d  mov     [rax], rcx
0x14006bc10  mov     eax, r14d
0x14006bc13  jmp     short loc_14006BC4C
0x14006bc15  cmp     r14d, eax
0x14006bc18  jbe     short loc_14006BC01
0x14006bc1a  jmp     short loc_14006BBEB
0x14006bc1c  test    bpl, 2
0x14006bc20  jz      short loc_14006BC01
0x14006bc22  neg     r14d
0x14006bc25  jmp     short loc_14006BC01
0x14006bc27  mov     rdx, [rbx+8]
0x14006bc2b  test    bpl, 2
0x14006bc2f  jz      short loc_14006BC41
0x14006bc31  test    rdx, rdx
0x14006bc34  jz      short loc_14006BC3C
0x14006bc36  mov     rcx, [rbx]
0x14006bc39  mov     [rdx], rcx
0x14006bc3c  mov     eax, r8d
0x14006bc3f  jmp     short loc_14006BC4C
0x14006bc41  test    rdx, rdx
0x14006bc44  jz      short loc_14006BC4C
0x14006bc46  mov     rcx, [rbx]
0x14006bc49  mov     [rdx], rcx
0x14006bc4c  mov     rbx, [rsp+58h+arg_0]
0x14006bc51  mov     rbp, [rsp+58h+arg_8]
0x14006bc56  mov     rsi, [rsp+58h+arg_10]
0x14006bc5b  add     rsp, 30h
0x14006bc5f  pop     r15
0x14006bc61  pop     r14
0x14006bc63  pop     r13
0x14006bc65  pop     r12
0x14006bc67  pop     rdi
0x14006bc68  retn
```
