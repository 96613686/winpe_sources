# jsonbValidityCheck

- ea: `0x18006ad94`
- end: `0x18006b268`
- name: `jsonbValidityCheck`
- size: `1236`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800669f0`
- `0x18006aa50`
- `0x18006ad94`

## callees

- `0x1800674ec`
- `0x18006a7dc`
- `0x18006ac38`
- `0x18006ad94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18006b1c6`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18006b1c6`

## pseudocode

```c
__int64 __fastcall jsonbValidityCheck(__int64 *a1, unsigned int a2, int a3, unsigned int a4)
{
  __int64 v4; // rbx
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // r10d
  unsigned int v11; // r9d
  __int64 v12; // rdi
  char v13; // r11
  __int64 result; // rax
  __int64 v15; // rdx
  unsigned __int64 i; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned int v19; // r10d
  char v20; // r8
  __int64 v21; // r8
  char v22; // cl
  __int64 v23; // rax
  __int64 v24; // r8
  char v25; // si
  unsigned int v26; // r12d
  int v27; // eax
  unsigned int v28; // r15d
  unsigned int v29; // esi
  int v30; // eax
  unsigned int v31; // edi
  unsigned int v32; // r15d
  __int64 v33; // rcx
  __int64 v34; // rsi
  __int64 v35; // rdx
  int v36; // eax
  __int64 v37; // rcx
  unsigned int v38; // r9d
  __int64 v39; // rdx
  _DWORD v40[6]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v41; // [rsp+98h] [rbp+60h] BYREF

  v4 = a2;
  if ( a4 > 0x3E8 )
    return (unsigned int)(v4 + 1);
  v41 = 0;
  v8 = jsonbPayloadSize(a1, a2, &v41);
  if ( !v8 )
    return (unsigned int)(v4 + 1);
  v9 = v41;
  v10 = v41 + v8;
  v11 = v41 + v8 + v4;
  if ( v11 != a3 )
    return (unsigned int)(v4 + 1);
  v12 = *a1;
  LOBYTE(v41) = *(_BYTE *)(v4 + *a1) & 0xF;
  v13 = v41;
  if ( (unsigned __int8)v41 > 6u )
  {
    if ( (unsigned __int8)v41 == 7 )
    {
      v37 = (unsigned int)(v8 + v4);
      v38 = v37 + v9;
      while ( (unsigned int)v37 < v38 )
      {
        v39 = *(unsigned __int8 *)(v37 + v12);
        if ( !*((_BYTE *)qword_1800BA610 + v39) && (_BYTE)v39 != 39 )
          return (unsigned int)(v37 + 1);
        v37 = (unsigned int)(v37 + 1);
      }
      return 0;
    }
    if ( (unsigned __int8)v41 != 8 && (unsigned __int8)v41 != 9 )
    {
      if ( (unsigned __int8)v41 != 10 )
      {
        if ( (unsigned __int8)v41 == 11 )
        {
          LODWORD(v4) = v8 + v4;
          v29 = v4 + v9;
          while ( (unsigned int)v4 < v29 )
          {
            v41 = 0;
            v30 = jsonbPayloadSize(a1, v4, &v41);
            if ( !v30 )
              return (unsigned int)(v4 + 1);
            v31 = v30 + v4 + v41;
            if ( v31 > v29 )
              return (unsigned int)(v4 + 1);
            result = jsonbValidityCheck(a1, (unsigned int)v4, v31, a4 + 1);
            if ( (_DWORD)result )
              return result;
            LODWORD(v4) = v31;
          }
        }
        else
        {
          if ( (unsigned __int8)v41 != 12 )
            return (unsigned int)(v4 + 1);
          v25 = 0;
          LODWORD(v4) = v8 + v4;
          v26 = v4 + v9;
          while ( (unsigned int)v4 < v26 )
          {
            v41 = 0;
            v27 = jsonbPayloadSize(a1, v4, &v41);
            if ( !v27 )
              return (unsigned int)(v4 + 1);
            v28 = v27 + v4 + v41;
            if ( v28 > v26 || (v25 & 1) == 0 && (unsigned __int8)((*(_BYTE *)((unsigned int)v4 + v12) & 0xF) - 7) > 3u )
              return (unsigned int)(v4 + 1);
            result = jsonbValidityCheck(a1, (unsigned int)v4, v28, a4 + 1);
            if ( (_DWORD)result )
              return result;
            ++v25;
            LODWORD(v4) = v28;
          }
          if ( (v25 & 1) != 0 )
            return (unsigned int)(v4 + 1);
        }
      }
      return 0;
    }
    v4 = (unsigned int)(v8 + v4);
    v32 = v4 + v9;
    while ( 1 )
    {
      if ( (unsigned int)v4 >= v32 )
        return 0;
      v33 = *(unsigned __int8 *)(v4 + v12);
      if ( !*((_BYTE *)qword_1800BA610 + v33) && (_BYTE)v33 != 39 )
      {
        if ( (_BYTE)v33 != 34 && (unsigned __int8)v33 > 0x1Fu )
        {
          if ( (_BYTE)v33 != 92 )
            return (unsigned int)(v4 + 1);
          v34 = (unsigned int)(v4 + 1);
          if ( (unsigned int)v34 >= v32 )
            return (unsigned int)(v4 + 1);
          if ( strchr("\"\\/bfnrt", *(unsigned __int8 *)(v34 + v12)) )
            goto LABEL_104;
          if ( *(_BYTE *)(v34 + v12) == 117 )
          {
            if ( (int)v4 + 5 >= v32 || !(unsigned int)jsonIs4Hex(v12 + (unsigned int)(v4 + 2), v35) )
              return (unsigned int)v34;
LABEL_104:
            LODWORD(v4) = v4 + 1;
          }
          else
          {
            if ( (_BYTE)v41 != 9 )
              return (unsigned int)v34;
            v40[0] = 0;
            v36 = jsonUnescapeOneChar(v12 + (unsigned int)v4, v32 - (unsigned int)v4, v40);
            if ( v40[0] == 629145 )
              return (unsigned int)v34;
            LODWORD(v4) = v36 + v4 - 1;
          }
          v13 = v41;
          goto LABEL_113;
        }
        if ( v13 == 8 )
          return (unsigned int)(v4 + 1);
      }
LABEL_113:
      v4 = (unsigned int)(v4 + 1);
    }
  }
  if ( (unsigned __int8)v41 == 6 )
    goto LABEL_37;
  if ( (_BYTE)v41 && (unsigned __int8)v41 != 1 && (unsigned __int8)v41 != 2 )
  {
    if ( (unsigned __int8)v41 == 3 )
    {
      if ( !v9 )
        return (unsigned int)(v4 + 1);
      v17 = (unsigned int)(v8 + v4);
      if ( *(_BYTE *)(v17 + v12) != 45 )
        goto LABEL_30;
      if ( v9 < 2 )
        return (unsigned int)(v4 + 1);
      LODWORD(v17) = v17 + 1;
LABEL_30:
      while ( (unsigned int)v17 < v11 )
      {
        if ( (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)((unsigned int)v17 + v12)) & 4) == 0 )
          return (unsigned int)(v17 + 1);
        LODWORD(v17) = v17 + 1;
      }
      return 0;
    }
    if ( (unsigned __int8)v41 == 4 )
    {
      if ( v9 < 3 )
        return (unsigned int)(v4 + 1);
      v15 = (unsigned int)(v4 + v8);
      if ( *(_BYTE *)(v15 + v12) == 45 )
      {
        if ( v9 < 4 )
          return (unsigned int)(v4 + 1);
        v15 = (unsigned int)(v15 + 1);
      }
      if ( *(_BYTE *)(v15 + v12) != 48 )
        return (unsigned int)(v4 + 1);
      if ( ((*(_BYTE *)((unsigned int)(v15 + 1) + v12) - 88) & 0xDF) != 0 )
        return (unsigned int)(v15 + 2);
      for ( i = (unsigned int)(v15 + 2); (unsigned int)i < v11; i = (unsigned int)(i + 1) )
      {
        if ( (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(i + v12)) & 8) == 0 )
          return (unsigned int)(i + 1);
      }
      return 0;
    }
    if ( (unsigned __int8)v41 != 5 )
      return (unsigned int)(v4 + 1);
LABEL_37:
    if ( v9 < 2 )
      return (unsigned int)(v4 + 1);
    v18 = (unsigned int)(v8 + v4);
    if ( *(_BYTE *)(v18 + v12) == 45 )
    {
      if ( v9 < 3 )
        return (unsigned int)(v4 + 1);
      i = (unsigned int)(v18 + 1);
    }
    else
    {
      i = (unsigned int)v18;
    }
    v19 = v18 + v9;
    v20 = *(_BYTE *)((unsigned int)i + v12);
    if ( v20 == 46 )
    {
      v21 = (unsigned int)(i + 1);
      if ( (_BYTE)v41 != 5 && (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(v21 + v12)) & 4) != 0 )
      {
        LODWORD(i) = i + 2;
        v22 = 1;
        goto LABEL_53;
      }
      return (unsigned int)v21;
    }
    v22 = 0;
    if ( v20 == 48 && (_BYTE)v41 == 5 )
    {
      v21 = (unsigned int)(i + 1);
      if ( (int)i + 3 <= v19 )
      {
        LOBYTE(i) = *(_BYTE *)(v21 + v12) - 46;
        if ( (unsigned __int8)i <= 0x37u )
        {
          v23 = 0x80000000800001LL;
          if ( _bittest64(&v23, i) )
          {
            LODWORD(i) = v21;
            goto LABEL_53;
          }
        }
      }
      return (unsigned int)v21;
    }
LABEL_53:
    while ( (unsigned int)i < v19 )
    {
      v24 = *(unsigned __int8 *)((unsigned int)i + v12);
      if ( (*((_BYTE *)&qword_1800ADE90 + v24) & 4) == 0 )
      {
        if ( (_BYTE)v24 == 46 )
        {
          if ( v22
            || (_BYTE)v41 == 5
            && ((_DWORD)i == v19 - 1
             || (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)((unsigned int)(i + 1) + v12)) & 4) == 0) )
          {
            return (unsigned int)(i + 1);
          }
          v22 = 1;
        }
        else
        {
          if ( (((_BYTE)v24 - 69) & 0xDF) != 0 )
            return (unsigned int)(i + 1);
          v21 = (unsigned int)(i + 1);
          if ( v22 == 2 || (_DWORD)i == v19 - 1 )
            return (unsigned int)v21;
          if ( ((*(_BYTE *)(v21 + v12) - 43) & 0xFD) == 0 )
          {
            LODWORD(i) = i + 1;
            if ( (_DWORD)v21 == v19 - 1 )
              return (unsigned int)(v21 + 1);
          }
          v22 = 2;
        }
      }
      LODWORD(i) = i + 1;
    }
    if ( !v22 )
      return (unsigned int)(v4 + 1);
    return 0;
  }
  result = 0;
  if ( v10 != 1 )
    return (unsigned int)(v4 + 1);
  return result;
}

```

## disassembly

```asm
0x18006ad94  push    rbp
0x18006ad96  push    rbx
0x18006ad97  push    rsi
0x18006ad98  push    rdi
0x18006ad99  push    r12
0x18006ad9b  push    r13
0x18006ad9d  push    r14
0x18006ad9f  push    r15
0x18006ada1  mov     rbp, rsp
0x18006ada4  sub     rsp, 38h
0x18006ada8  mov     ebx, edx
0x18006adaa  mov     r13d, r9d
0x18006adad  mov     edi, r8d
0x18006adb0  mov     r14, rcx
0x18006adb3  cmp     r9d, 3E8h
0x18006adba  ja      short loc_18006AE35
0x18006adbc  lea     r8, [rbp+arg_18]
0x18006adc0  mov     [rbp+arg_18], 0
0x18006adc7  mov     edx, ebx
0x18006adc9  call    jsonbPayloadSize
0x18006adce  mov     edx, eax
0x18006add0  test    eax, eax
0x18006add2  jz      short loc_18006AE35
0x18006add4  mov     r8d, [rbp+arg_18]
0x18006add8  lea     r10d, [r8+rax]
0x18006addc  lea     r9d, [r10+rbx]
0x18006ade0  cmp     r9d, edi
0x18006ade3  jnz     short loc_18006AE35
0x18006ade5  mov     rdi, [r14]
0x18006ade8  mov     r11b, [rbx+rdi]
0x18006adec  and     r11b, 0Fh
0x18006adf0  movzx   ecx, r11b
0x18006adf4  mov     byte ptr [rbp+arg_18], r11b
0x18006adf8  cmp     ecx, 6
0x18006adfb  ja      loc_18006B04C
0x18006ae01  jz      loc_18006AEFC
0x18006ae07  test    r11b, r11b
0x18006ae0a  jz      loc_18006AEEB
0x18006ae10  sub     ecx, 1
0x18006ae13  jz      loc_18006AEEB
0x18006ae19  sub     ecx, 1
0x18006ae1c  jz      loc_18006AEEB
0x18006ae22  sub     ecx, 1
0x18006ae25  jz      short loc_18006AEA1
0x18006ae27  sub     ecx, 1
0x18006ae2a  jz      short loc_18006AE49
0x18006ae2c  cmp     ecx, 1
0x18006ae2f  jz      loc_18006AEFC
0x18006ae35  lea     eax, [rbx+1]
0x18006ae38  add     rsp, 38h
0x18006ae3c  pop     r15
0x18006ae3e  pop     r14
0x18006ae40  pop     r13
0x18006ae42  pop     r12
0x18006ae44  pop     rdi
0x18006ae45  pop     rsi
0x18006ae46  pop     rbx
0x18006ae47  pop     rbp
0x18006ae48  retn
0x18006ae49  cmp     r8d, 3
0x18006ae4d  jb      short loc_18006AE35
0x18006ae4f  add     edx, ebx
0x18006ae51  cmp     byte ptr [rdx+rdi], 2Dh ; '-'
0x18006ae55  jnz     short loc_18006AE5F
0x18006ae57  cmp     r8d, 4
0x18006ae5b  jb      short loc_18006AE35
0x18006ae5d  inc     edx
0x18006ae5f  cmp     byte ptr [rdx+rdi], 30h ; '0'
0x18006ae63  jnz     short loc_18006AE35
0x18006ae65  lea     eax, [rdx+1]
0x18006ae68  mov     al, [rax+rdi]
0x18006ae6b  sub     al, 58h ; 'X'
0x18006ae6d  test    al, 0DFh
0x18006ae6f  jz      short loc_18006AE76
0x18006ae71  lea     eax, [rdx+2]
0x18006ae74  jmp     short loc_18006AE38
0x18006ae76  add     edx, 2
0x18006ae79  lea     r14, __ImageBase
0x18006ae80  cmp     edx, r9d
0x18006ae83  jnb     loc_18006B045
0x18006ae89  movzx   ecx, byte ptr [rdx+rdi]
0x18006ae8d  test    byte ptr [rcx+r14+0ADE90h], 8
0x18006ae96  jz      short loc_18006AE9C
0x18006ae98  inc     edx
0x18006ae9a  jmp     short loc_18006AE80
0x18006ae9c  lea     eax, [rdx+1]
0x18006ae9f  jmp     short loc_18006AE38
0x18006aea1  cmp     r8d, 1
0x18006aea5  jb      short loc_18006AE35
0x18006aea7  lea     ecx, [rax+rbx]
0x18006aeaa  cmp     byte ptr [rcx+rdi], 2Dh ; '-'
0x18006aeae  jnz     short loc_18006AEBC
0x18006aeb0  cmp     r8d, 2
0x18006aeb4  jb      loc_18006AE35
0x18006aeba  inc     ecx
0x18006aebc  lea     r14, __ImageBase
0x18006aec3  cmp     ecx, r9d
0x18006aec6  jnb     loc_18006B045
0x18006aecc  mov     eax, ecx
0x18006aece  lea     edx, [rcx+1]
0x18006aed1  movzx   ecx, byte ptr [rax+rdi]
0x18006aed5  test    byte ptr [rcx+r14+0ADE90h], 4
0x18006aede  jz      short loc_18006AEE4
0x18006aee0  mov     ecx, edx
0x18006aee2  jmp     short loc_18006AEC3
0x18006aee4  mov     eax, edx
0x18006aee6  jmp     loc_18006AE38
0x18006aeeb  xor     eax, eax
0x18006aeed  lea     ecx, [rbx+1]
0x18006aef0  cmp     r10d, 1
0x18006aef4  cmovnz  eax, ecx
0x18006aef7  jmp     loc_18006AE38
0x18006aefc  cmp     r8d, 2
0x18006af00  jb      loc_18006AE35
0x18006af06  lea     ecx, [rax+rbx]
0x18006af09  cmp     byte ptr [rcx+rdi], 2Dh ; '-'
0x18006af0d  jnz     short loc_18006AF1E
0x18006af0f  cmp     r8d, 3
0x18006af13  jb      loc_18006AE35
0x18006af19  lea     edx, [rcx+1]
0x18006af1c  jmp     short loc_18006AF20
0x18006af1e  mov     edx, ecx
0x18006af20  mov     eax, edx
0x18006af22  lea     r10d, [rcx+r8]
0x18006af26  mov     r15b, 2Eh ; '.'
0x18006af29  lea     r14, __ImageBase
0x18006af30  mov     sil, 5
0x18006af33  mov     r8b, [rax+rdi]
0x18006af37  cmp     r8b, r15b
0x18006af3a  jnz     short loc_18006AF64
0x18006af3c  lea     r8d, [rdx+1]
0x18006af40  cmp     r11b, sil
0x18006af43  jz      short loc_18006AF5C
0x18006af45  movzx   ecx, byte ptr [r8+rdi]
0x18006af4a  test    byte ptr [rcx+r14+0ADE90h], 4
0x18006af53  jz      short loc_18006AF5C
0x18006af55  add     edx, 2
0x18006af58  mov     cl, 1
0x18006af5a  jmp     short loc_18006AF9C
0x18006af5c  mov     eax, r8d
0x18006af5f  jmp     loc_18006AE38
0x18006af64  xor     cl, cl
0x18006af66  cmp     r8b, 30h ; '0'
0x18006af6a  jnz     short loc_18006AF9C
0x18006af6c  cmp     r11b, sil
0x18006af6f  jnz     short loc_18006AF9C
0x18006af71  lea     eax, [rdx+3]
0x18006af74  lea     r8d, [rdx+1]
0x18006af78  cmp     eax, r10d
0x18006af7b  ja      short loc_18006AF5C
0x18006af7d  mov     dl, [r8+rdi]
0x18006af81  sub     dl, r15b
0x18006af84  cmp     dl, 37h ; '7'
0x18006af87  ja      short loc_18006AF5C
0x18006af89  mov     rax, 80000000800001h
0x18006af93  bt      rax, rdx
0x18006af97  jnb     short loc_18006AF5C
0x18006af99  mov     edx, r8d
0x18006af9c  cmp     edx, r10d
0x18006af9f  jnb     loc_18006B03D
0x18006afa5  mov     eax, edx
0x18006afa7  movzx   r8d, byte ptr [rax+rdi]
0x18006afac  test    byte ptr [r8+r14+0ADE90h], 4
0x18006afb5  jnz     short loc_18006B02D
0x18006afb7  cmp     r8b, r15b
0x18006afba  jnz     short loc_18006AFEF
0x18006afbc  test    cl, cl
0x18006afbe  jnz     loc_18006AE9C
0x18006afc4  cmp     r11b, sil
0x18006afc7  jnz     short loc_18006AFEB
0x18006afc9  lea     eax, [r10-1]
0x18006afcd  cmp     edx, eax
0x18006afcf  jz      loc_18006AE9C
0x18006afd5  lea     eax, [rdx+1]
0x18006afd8  movzx   eax, byte ptr [rax+rdi]
0x18006afdc  test    byte ptr [rax+r14+0ADE90h], 4
0x18006afe5  jz      loc_18006AE9C
0x18006afeb  mov     cl, 1
0x18006afed  jmp     short loc_18006B02D
0x18006afef  sub     r8b, 45h ; 'E'
0x18006aff3  test    r8b, 0DFh
0x18006aff7  jnz     loc_18006AE9C
0x18006affd  lea     r8d, [rdx+1]
0x18006b001  cmp     cl, 2
0x18006b004  jz      loc_18006AF5C
0x18006b00a  lea     r9d, [r10-1]
0x18006b00e  cmp     edx, r9d
0x18006b011  jz      loc_18006AF5C
0x18006b017  mov     cl, [r8+rdi]
0x18006b01b  sub     cl, 2Bh ; '+'
0x18006b01e  test    cl, 0FDh
0x18006b021  jnz     short loc_18006B02B
0x18006b023  mov     edx, r8d
0x18006b026  cmp     r8d, r9d
0x18006b029  jz      short loc_18006B034
0x18006b02b  mov     cl, 2
0x18006b02d  inc     edx
0x18006b02f  jmp     loc_18006AF9C
0x18006b034  lea     eax, [r8+1]
0x18006b038  jmp     loc_18006AE38
0x18006b03d  test    cl, cl
0x18006b03f  jz      loc_18006AE35
0x18006b045  xor     eax, eax
0x18006b047  jmp     loc_18006AE38
0x18006b04c  sub     ecx, 7
0x18006b04f  jz      loc_18006B231
0x18006b055  sub     ecx, 1
0x18006b058  jz      loc_18006B15B
0x18006b05e  sub     ecx, 1
0x18006b061  jz      loc_18006B15B
0x18006b067  sub     ecx, 1
0x18006b06a  jz      short loc_18006B045
0x18006b06c  sub     ecx, 1
0x18006b06f  jz      loc_18006B104
0x18006b075  cmp     ecx, 1
0x18006b078  jnz     loc_18006AE35
0x18006b07e  xor     esi, esi
0x18006b080  add     ebx, edx
0x18006b082  lea     r12d, [rbx+r8]
0x18006b086  cmp     ebx, r12d
0x18006b089  jnb     short loc_18006B0F5
0x18006b08b  lea     r8, [rbp+arg_18]
0x18006b08f  mov     [rbp+arg_18], 0
0x18006b096  mov     edx, ebx
0x18006b098  mov     rcx, r14
0x18006b09b  call    jsonbPayloadSize
0x18006b0a0  test    eax, eax
0x18006b0a2  jz      loc_18006AE35
0x18006b0a8  mov     r15d, [rbp+arg_18]
0x18006b0ac  add     r15d, ebx
0x18006b0af  add     r15d, eax
0x18006b0b2  cmp     r15d, r12d
0x18006b0b5  ja      loc_18006AE35
0x18006b0bb  test    sil, 1
0x18006b0bf  jnz     short loc_18006B0D5
0x18006b0c1  mov     eax, ebx
0x18006b0c3  mov     cl, [rax+rdi]
0x18006b0c6  and     cl, 0Fh
0x18006b0c9  sub     cl, 7
0x18006b0cc  cmp     cl, 3
0x18006b0cf  ja      loc_18006AE35
0x18006b0d5  lea     r9d, [r13+1]
0x18006b0d9  mov     r8d, r15d
0x18006b0dc  mov     edx, ebx
0x18006b0de  mov     rcx, r14
0x18006b0e1  call    jsonbValidityCheck
0x18006b0e6  test    eax, eax
0x18006b0e8  jnz     loc_18006AE38
0x18006b0ee  inc     esi
0x18006b0f0  mov     ebx, r15d
0x18006b0f3  jmp     short loc_18006B086
0x18006b0f5  test    sil, 1
0x18006b0f9  jz      loc_18006B045
0x18006b0ff  jmp     loc_18006AE35
0x18006b104  add     ebx, edx
0x18006b106  lea     esi, [rbx+r8]
0x18006b10a  cmp     ebx, esi
0x18006b10c  jnb     loc_18006B045
0x18006b112  lea     r8, [rbp+arg_18]
0x18006b116  mov     [rbp+arg_18], 0
0x18006b11d  mov     edx, ebx
0x18006b11f  mov     rcx, r14
0x18006b122  call    jsonbPayloadSize
0x18006b127  test    eax, eax
0x18006b129  jz      loc_18006AE35
0x18006b12f  mov     edi, [rbp+arg_18]
0x18006b132  add     edi, ebx
0x18006b134  add     edi, eax
0x18006b136  cmp     edi, esi
0x18006b138  ja      loc_18006AE35
0x18006b13e  lea     r9d, [r13+1]
0x18006b142  mov     r8d, edi
0x18006b145  mov     edx, ebx
0x18006b147  mov     rcx, r14
0x18006b14a  call    jsonbValidityCheck
0x18006b14f  test    eax, eax
0x18006b151  jnz     loc_18006AE38
0x18006b157  mov     ebx, edi
0x18006b159  jmp     short loc_18006B10A
0x18006b15b  add     ebx, edx
0x18006b15d  lea     r14, __ImageBase
0x18006b164  lea     r15d, [rbx+r8]
0x18006b168  cmp     ebx, r15d
0x18006b16b  jnb     loc_18006B045
0x18006b171  movzx   ecx, byte ptr [rbx+rdi]
0x18006b175  cmp     byte ptr [rcx+r14+0BA610h], 0
0x18006b17e  jnz     loc_18006B22A
0x18006b184  cmp     cl, 27h ; '''
0x18006b187  jz      loc_18006B22A
0x18006b18d  cmp     cl, 22h ; '"'
0x18006b190  jz      short loc_18006B197
0x18006b192  cmp     cl, 1Fh
0x18006b195  ja      short loc_18006B1A6
0x18006b197  cmp     r11b, 8
0x18006b19b  jz      loc_18006AE35
0x18006b1a1  jmp     loc_18006B22A
0x18006b1a6  cmp     cl, 5Ch ; '\'
0x18006b1a9  jnz     loc_18006AE35
0x18006b1af  lea     esi, [rbx+1]
0x18006b1b2  cmp     esi, r15d
  ... truncated ...
```
