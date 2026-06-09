# OutputMmrLine

- ea: `0x18000a88c`
- end: `0x18000ac31`
- name: `OutputMmrLine`
- size: `933`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int8, unsigned __int16 *, unsigned __int16 *, unsigned int **, unsigned __int8 *, unsigned __int64, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180009c84`
- `0x18000ac38`
- `0x18000b604`

## callees

- `0x180004280`
- `0x180009a7c`
- `0x180009aa4`
- `0x18000a88c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000ab53`
- `KERNEL32!SetLastError` at `0x18000abaf`
- `KERNEL32!SetLastError` at `0x18000abf0`
- `KERNEL32!SetLastError` at `0x18000ab53`
- `KERNEL32!SetLastError` at `0x18000abaf`
- `KERNEL32!SetLastError` at `0x18000abf0`

## pseudocode

```c
__int64 __fastcall OutputMmrLine(
        unsigned int *a1,
        unsigned __int8 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int **a5,
        unsigned __int8 *a6,
        unsigned __int64 a7,
        int a8)
{
  int v8; // r11d
  int v9; // r14d
  unsigned int *v10; // rbx
  int v11; // edi
  int v12; // ecx
  unsigned __int16 *v13; // r12
  int v15; // r10d
  unsigned int v16; // r8d
  int v17; // eax
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  int v20; // r9d
  int v21; // r10d
  int v22; // ecx
  int v23; // r8d
  unsigned __int8 v24; // cl
  unsigned __int64 v25; // r8
  unsigned int v26; // eax
  char v27; // cl
  int v28; // r13d
  int v29; // eax
  unsigned __int8 v30; // dl
  int v31; // edx
  int v32; // eax
  unsigned int v33; // r12d
  unsigned int v34; // ebx
  __int64 v35; // rdx
  unsigned int v36; // r10d
  int v37; // eax
  __int64 v38; // rax
  __int64 result; // rax
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  unsigned int *v42; // [rsp+70h] [rbp+48h] BYREF
  unsigned __int8 v43; // [rsp+78h] [rbp+50h] BYREF
  int v44; // [rsp+80h] [rbp+58h]
  unsigned __int16 *v45; // [rsp+88h] [rbp+60h]

  v45 = a4;
  v42 = a1;
  v8 = a8;
  v9 = 0;
  v10 = a1;
  v44 = 0;
  v11 = 0;
  v12 = 0;
  v13 = a4;
  v15 = 0;
  do
  {
    v16 = a3[v12];
    if ( v16 >= v8 )
      break;
    if ( (_WORD)v16 == a3[v12 + 1] )
    {
      v17 = 2;
    }
    else
    {
      v18 = v15++;
      a3[v18] = v16;
      v17 = 1;
    }
    v12 += v17;
  }
  while ( v12 < 1730 );
  v19 = a7;
  v20 = 0;
  a3[v15] = v8;
  v21 = *a3;
  v22 = *v13;
  while ( 1 )
  {
    if ( (unsigned __int64)v10 >= v19 || (unsigned __int64)((__int64)(v19 - (_QWORD)v10) >> 2) < 4 )
    {
      SetLastError(0x7Au);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids,
          (unsigned int)((__int64)(v19 - (_QWORD)v10) >> 2));
      }
      return 0;
    }
    v23 = v22 < v8 ? v13[v11 + 1] : v8;
    if ( v23 >= v21 )
    {
      if ( (unsigned int)(v21 - v22 + 3) > 6 )
      {
        if ( v21 < v8 )
          v28 = a3[v9 + 1];
        else
          v28 = v8;
        v29 = 4 << a2;
        v30 = a2 + 3;
        *v10 += v29;
        v43 = v30;
        if ( v30 > 0x1Fu )
        {
          v43 = v30 - 32;
          v42 = v10 + 1;
          v10[1] = 4u >> (3 - (v30 - 32));
        }
        v31 = v9;
        if ( v9 >= 1731 )
        {
LABEL_28:
          v32 = v44;
        }
        else
        {
          while ( a3[v31] <= v20 )
          {
            if ( ++v31 >= 1731 )
              goto LABEL_28;
          }
          v9 = v31;
          v32 = v31 & 1;
          v44 = v32;
        }
        if ( v21 && v32 )
        {
          v33 = 0;
          v34 = v28 - v21;
          v35 = 255;
          v36 = v21 - v20;
        }
        else
        {
          v33 = 255;
          v34 = v28 - v21;
          v36 = v21 - v20;
          v35 = 0;
        }
        OutputRunFastReversed(v36, v35, &v42, &v43);
        OutputRunFastReversed(v34, v33, &v42, &v43);
        a2 = v43;
        v20 = v28;
        v8 = a8;
        v10 = v42;
        v13 = v45;
      }
      else
      {
        v25 = (unsigned int)v21 - (unsigned __int64)(unsigned int)v22;
        *v10 += asc_18001BCB0[2 * v25 + 7] << a2;
        a2 += LOBYTE(asc_18001BCB0[2 * v25 + 6]);
        if ( a2 > 0x1Fu )
        {
          ++v10;
          v26 = asc_18001BCB0[2 * v25 + 7];
          a2 -= 32;
          v27 = LOBYTE(asc_18001BCB0[2 * v25 + 6]) - a2;
          v42 = v10;
          *v10 = v26 >> v27;
        }
        v20 = v21;
      }
    }
    else
    {
      v24 = a2;
      a2 += 4;
      *v10 += 8 << v24;
      if ( a2 > 0x1Fu )
      {
        v42 = ++v10;
        a2 -= 32;
        *v10 = 8u >> (4 - a2);
      }
      v20 = v23;
    }
    if ( v20 >= v8 )
      break;
    while ( v9 < 1731 )
    {
      if ( a3[v9] > v20 )
        goto LABEL_41;
      ++v9;
    }
    if ( v9 == 1731 )
    {
      SetLastError(0x7Au);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = 32;
        goto LABEL_60;
      }
      return 0;
    }
LABEL_41:
    v37 = v11 - 1;
    if ( v11 <= 0 )
      v37 = v11;
    v11 = v37;
    if ( v37 >= 1731 )
    {
LABEL_46:
      if ( v11 != 1731 )
        goto LABEL_47;
      SetLastError(0x7Au);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = 33;
LABEL_60:
        WPP_SF_(v40[2], v41, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
        return 0;
      }
      return 0;
    }
    while ( v13[v11] <= v20 )
    {
      if ( ++v11 >= 1731 )
        goto LABEL_46;
    }
LABEL_47:
    v21 = a3[v9];
    v22 = v13[v11];
    if ( (((unsigned __int8)v9 ^ (unsigned __int8)v11) & 1) != 0 && v22 < v8 )
    {
      v38 = v11++;
      v22 = v13[v38 + 1];
    }
  }
  result = 1;
  *a5 = v10;
  *a6 = a2;
  return result;
}

```

## disassembly

```asm
0x18000a88c  mov     [rsp-40h+arg_18], r9
0x18000a891  mov     [rsp-40h+arg_0], rcx
0x18000a896  push    rbp
0x18000a897  push    rbx
0x18000a898  push    rsi
0x18000a899  push    rdi
0x18000a89a  push    r12
0x18000a89c  push    r13
0x18000a89e  push    r14
0x18000a8a0  push    r15
0x18000a8a2  mov     rbp, rsp
0x18000a8a5  sub     rsp, 28h
0x18000a8a9  mov     r11d, [rbp+arg_38]
0x18000a8b0  xor     r14d, r14d
0x18000a8b3  mov     rbx, rcx
0x18000a8b6  mov     [rbp+arg_10], 0
0x18000a8bd  xor     edi, edi
0x18000a8bf  xor     ecx, ecx
0x18000a8c1  mov     r12, r9
0x18000a8c4  mov     r15, r8
0x18000a8c7  lea     r13d, [r14+1]
0x18000a8cb  xor     r10d, r10d
0x18000a8ce  movsxd  rax, ecx
0x18000a8d1  movzx   r8d, word ptr [r15+rax*2]
0x18000a8d6  cmp     r8d, r11d
0x18000a8d9  jnb     short loc_18000A902
0x18000a8db  cmp     r8w, [r15+rax*2+2]
0x18000a8e1  jnz     short loc_18000A8EA
0x18000a8e3  mov     eax, 2
0x18000a8e8  jmp     short loc_18000A8F8
0x18000a8ea  movsxd  rax, r10d
0x18000a8ed  add     r10d, r13d
0x18000a8f0  mov     [r15+rax*2], r8w
0x18000a8f5  mov     eax, r13d
0x18000a8f8  add     ecx, eax
0x18000a8fa  cmp     ecx, 6C2h
0x18000a900  jl      short loc_18000A8CE
0x18000a902  mov     rsi, [rbp+arg_30]
0x18000a906  xor     r9d, r9d
0x18000a909  movsxd  rax, r10d
0x18000a90c  mov     [r15+rax*2], r11w
0x18000a911  movzx   r10d, word ptr [r15]
0x18000a915  movzx   ecx, word ptr [r12]
0x18000a91a  jmp     loc_18000AB45
0x18000a91f  mov     rax, rsi
0x18000a922  sub     rax, rbx
0x18000a925  sar     rax, 2
0x18000a929  cmp     rax, 4
0x18000a92d  jb      loc_18000AB4E
0x18000a933  cmp     ecx, r11d
0x18000a936  jl      short loc_18000A93D
0x18000a938  mov     r8d, r11d
0x18000a93b  jmp     short loc_18000A946
0x18000a93d  movsxd  rax, edi
0x18000a940  movzx   r8d, word ptr [r12+rax*2+2]
0x18000a946  cmp     r8d, r10d
0x18000a949  jge     short loc_18000A985
0x18000a94b  mov     cl, dl
0x18000a94d  mov     r9d, 8
0x18000a953  mov     eax, r9d
0x18000a956  add     dl, 4
0x18000a959  shl     eax, cl
0x18000a95b  add     [rbx], eax
0x18000a95d  cmp     dl, 1Fh
0x18000a960  jbe     short loc_18000A97D
0x18000a962  add     rbx, 4
0x18000a966  lea     ecx, [r9-4]
0x18000a96a  sub     dl, 20h ; ' '
0x18000a96d  mov     [rbp+arg_0], rbx
0x18000a971  movzx   edx, dl
0x18000a974  mov     eax, r9d
0x18000a977  sub     ecx, edx
0x18000a979  shr     eax, cl
0x18000a97b  mov     [rbx], eax
0x18000a97d  mov     r9d, r8d
0x18000a980  jmp     loc_18000AAC1
0x18000a985  mov     eax, r10d
0x18000a988  sub     eax, ecx
0x18000a98a  add     eax, 3
0x18000a98d  cmp     eax, 6
0x18000a990  ja      short loc_18000A9DB
0x18000a992  mov     eax, ecx
0x18000a994  lea     r9, asc_18001BCB0; "\a "
0x18000a99b  mov     cl, dl
0x18000a99d  mov     r8d, r10d
0x18000a9a0  sub     r8, rax
0x18000a9a3  movzx   eax, word ptr [r9+r8*4+0Eh]
0x18000a9a9  shl     eax, cl
0x18000a9ab  add     [rbx], eax
0x18000a9ad  add     dl, [r9+r8*4+0Ch]
0x18000a9b2  cmp     dl, 1Fh
0x18000a9b5  jbe     short loc_18000A9D3
0x18000a9b7  mov     cl, [r9+r8*4+0Ch]
0x18000a9bc  add     rbx, 4
0x18000a9c0  movzx   eax, word ptr [r9+r8*4+0Eh]
0x18000a9c6  sub     dl, 20h ; ' '
0x18000a9c9  sub     cl, dl
0x18000a9cb  mov     [rbp+arg_0], rbx
0x18000a9cf  shr     eax, cl
0x18000a9d1  mov     [rbx], eax
0x18000a9d3  mov     r9d, r10d
0x18000a9d6  jmp     loc_18000AAC1
0x18000a9db  cmp     r10d, r11d
0x18000a9de  jl      short loc_18000A9E5
0x18000a9e0  mov     r13d, r11d
0x18000a9e3  jmp     short loc_18000A9EE
0x18000a9e5  movsxd  rax, r14d
0x18000a9e8  movzx   r13d, word ptr [r15+rax*2+2]
0x18000a9ee  mov     cl, dl
0x18000a9f0  mov     eax, 4
0x18000a9f5  shl     eax, cl
0x18000a9f7  add     dl, 3
0x18000a9fa  add     [rbx], eax
0x18000a9fc  mov     [rbp+arg_8], dl
0x18000a9ff  cmp     dl, 1Fh
0x18000aa02  jbe     short loc_18000AA25
0x18000aa04  add     rbx, 4
0x18000aa08  sub     dl, 20h ; ' '
0x18000aa0b  movzx   eax, dl
0x18000aa0e  mov     ecx, 3
0x18000aa13  mov     [rbp+arg_8], al
0x18000aa16  sub     ecx, eax
0x18000aa18  mov     eax, 4
0x18000aa1d  mov     [rbp+arg_0], rbx
0x18000aa21  shr     eax, cl
0x18000aa23  mov     [rbx], eax
0x18000aa25  mov     r8d, 6C3h
0x18000aa2b  mov     edx, r14d
0x18000aa2e  cmp     r14d, r8d
0x18000aa31  jge     short loc_18000AA47
0x18000aa33  movsxd  rax, edx
0x18000aa36  movzx   ecx, word ptr [r15+rax*2]
0x18000aa3b  cmp     ecx, r9d
0x18000aa3e  jg      short loc_18000AA66
0x18000aa40  inc     edx
0x18000aa42  cmp     edx, r8d
0x18000aa45  jl      short loc_18000AA33
0x18000aa47  mov     eax, [rbp+arg_10]
0x18000aa4a  test    r10d, r10d
0x18000aa4d  jz      short loc_18000AA73
0x18000aa4f  test    eax, eax
0x18000aa51  jz      short loc_18000AA73
0x18000aa53  mov     ebx, r13d
0x18000aa56  xor     r12d, r12d
0x18000aa59  sub     ebx, r10d
0x18000aa5c  mov     edx, 0FFh
0x18000aa61  sub     r10d, r9d
0x18000aa64  jmp     short loc_18000AA84
0x18000aa66  mov     eax, edx
0x18000aa68  mov     r14d, edx
0x18000aa6b  and     eax, 1
0x18000aa6e  mov     [rbp+arg_10], eax
0x18000aa71  jmp     short loc_18000AA4A
0x18000aa73  mov     ebx, r13d
0x18000aa76  mov     r12d, 0FFh
0x18000aa7c  sub     ebx, r10d
0x18000aa7f  sub     r10d, r9d
0x18000aa82  xor     edx, edx
0x18000aa84  lea     r9, [rbp+arg_8]
0x18000aa88  mov     ecx, r10d
0x18000aa8b  lea     r8, [rbp+arg_0]
0x18000aa8f  call    OutputRunFastReversed
0x18000aa94  mov     edx, r12d
0x18000aa97  lea     r9, [rbp+arg_8]
0x18000aa9b  mov     ecx, ebx
0x18000aa9d  lea     r8, [rbp+arg_0]
0x18000aaa1  call    OutputRunFastReversed
0x18000aaa6  mov     dl, [rbp+arg_8]
0x18000aaa9  mov     r9d, r13d
0x18000aaac  mov     r11d, [rbp+arg_38]
0x18000aab3  mov     r13d, 1
0x18000aab9  mov     rbx, [rbp+arg_0]
0x18000aabd  mov     r12, [rbp+arg_18]
0x18000aac1  cmp     r9d, r11d
0x18000aac4  jge     loc_18000AC1C
0x18000aaca  mov     r10d, 6C3h
0x18000aad0  jmp     short loc_18000AAE2
0x18000aad2  movsxd  rax, r14d
0x18000aad5  movzx   ecx, word ptr [r15+rax*2]
0x18000aada  cmp     ecx, r9d
0x18000aadd  jg      short loc_18000AAED
0x18000aadf  add     r14d, r13d
0x18000aae2  cmp     r14d, r10d
0x18000aae5  jl      short loc_18000AAD2
0x18000aae7  jz      loc_18000ABEB
0x18000aaed  test    edi, edi
0x18000aaef  movsxd  r8, r14d
0x18000aaf2  lea     eax, [rdi-1]
0x18000aaf5  cmovle  eax, edi
0x18000aaf8  mov     edi, eax
0x18000aafa  cmp     eax, r10d
0x18000aafd  jge     short loc_18000AB14
0x18000aaff  movsxd  rax, edi
0x18000ab02  movzx   ecx, word ptr [r12+rax*2]
0x18000ab07  cmp     ecx, r9d
0x18000ab0a  jg      short loc_18000AB1D
0x18000ab0c  add     edi, r13d
0x18000ab0f  cmp     edi, r10d
0x18000ab12  jl      short loc_18000AAFF
0x18000ab14  cmp     edi, r10d
0x18000ab17  jz      loc_18000ABAA
0x18000ab1d  movzx   r10d, word ptr [r15+r8*2]
0x18000ab22  movsxd  rax, edi
0x18000ab25  movzx   ecx, word ptr [r12+rax*2]
0x18000ab2a  mov     eax, edi
0x18000ab2c  xor     eax, r14d
0x18000ab2f  test    r13b, al
0x18000ab32  jz      short loc_18000AB45
0x18000ab34  cmp     ecx, r11d
0x18000ab37  jge     short loc_18000AB45
0x18000ab39  movsxd  rax, edi
0x18000ab3c  add     edi, r13d
0x18000ab3f  movzx   ecx, word ptr [r12+rax*2+2]
0x18000ab45  cmp     rbx, rsi
0x18000ab48  jb      loc_18000A91F
0x18000ab4e  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000ab53  call    cs:__imp_SetLastError
0x18000ab59  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab60  lea     rax, WPP_GLOBAL_Control
0x18000ab67  cmp     rcx, rax
0x18000ab6a  jz      short loc_18000AB97
0x18000ab6c  test    byte ptr [rcx+1Ch], 2
0x18000ab70  jz      short loc_18000AB97
0x18000ab72  cmp     byte ptr [rcx+19h], 2
0x18000ab76  jb      short loc_18000AB97
0x18000ab78  mov     rcx, [rcx+10h]
0x18000ab7c  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000ab83  sub     rsi, rbx
0x18000ab86  mov     edx, 1Fh
0x18000ab8b  sar     rsi, 2
0x18000ab8f  mov     r9d, esi
0x18000ab92  call    WPP_SF_d
0x18000ab97  xor     eax, eax
0x18000ab99  add     rsp, 28h
0x18000ab9d  pop     r15
0x18000ab9f  pop     r14
0x18000aba1  pop     r13
0x18000aba3  pop     r12
0x18000aba5  pop     rdi
0x18000aba6  pop     rsi
0x18000aba7  pop     rbx
0x18000aba8  pop     rbp
0x18000aba9  retn
0x18000abaa  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000abaf  call    cs:__imp_SetLastError
0x18000abb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abbc  lea     rax, WPP_GLOBAL_Control
0x18000abc3  cmp     rcx, rax
0x18000abc6  jz      short loc_18000AB97
0x18000abc8  test    byte ptr [rcx+1Ch], 2
0x18000abcc  jz      short loc_18000AB97
0x18000abce  cmp     byte ptr [rcx+19h], 2
0x18000abd2  jb      short loc_18000AB97
0x18000abd4  mov     edx, 21h ; '!'
0x18000abd9  mov     rcx, [rcx+10h]
0x18000abdd  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000abe4  call    WPP_SF_
0x18000abe9  jmp     short loc_18000AB97
0x18000abeb  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000abf0  call    cs:__imp_SetLastError
0x18000abf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abfd  lea     rax, WPP_GLOBAL_Control
0x18000ac04  cmp     rcx, rax
0x18000ac07  jz      short loc_18000AB97
0x18000ac09  test    byte ptr [rcx+1Ch], 2
0x18000ac0d  jz      short loc_18000AB97
0x18000ac0f  cmp     byte ptr [rcx+19h], 2
0x18000ac13  jb      short loc_18000AB97
0x18000ac15  mov     edx, 20h ; ' '
0x18000ac1a  jmp     short loc_18000ABD9
0x18000ac1c  mov     rcx, [rbp+arg_20]
0x18000ac20  mov     eax, r13d
0x18000ac23  mov     [rcx], rbx
0x18000ac26  mov     rcx, [rbp+arg_28]
0x18000ac2a  mov     [rcx], dl
0x18000ac2c  jmp     loc_18000AB99
```
