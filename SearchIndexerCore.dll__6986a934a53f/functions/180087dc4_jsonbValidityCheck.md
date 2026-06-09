# jsonbValidityCheck

- ea: `0x180087dc4`
- end: `0x1800882d4`
- name: `jsonbValidityCheck`
- size: `1296`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180083a60`
- `0x180087a80`
- `0x180087dc4`

## callees

- `0x18008455c`
- `0x18008785c`
- `0x180087c68`
- `0x180087dc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180088221`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180088221`

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
  unsigned int v16; // edx
  __int64 v17; // r8
  __int64 v18; // rcx
  unsigned int v19; // edx
  __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  unsigned int v22; // r10d
  char v23; // r8
  char v24; // cl
  __int64 v25; // rax
  __int64 v26; // r8
  char v27; // si
  unsigned int v28; // r12d
  int v29; // eax
  unsigned int v30; // r15d
  unsigned int v31; // esi
  int v32; // eax
  unsigned int v33; // edi
  unsigned int v34; // r15d
  __int64 v35; // rcx
  __int64 v36; // rsi
  int v37; // eax
  __int64 v38; // rcx
  unsigned int v39; // edx
  __int64 v40; // r8
  _DWORD v41[6]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v42; // [rsp+98h] [rbp+60h] BYREF

  v4 = a2;
  if ( a4 > 0x3E8 )
    return (unsigned int)(v4 + 1);
  v42 = 0;
  v8 = jsonbPayloadSize(a1, a2, &v42);
  if ( !v8 )
    return (unsigned int)(v4 + 1);
  v9 = v42;
  v10 = v42 + v8;
  v11 = v42 + v8 + v4;
  if ( v11 != a3 )
    return (unsigned int)(v4 + 1);
  v12 = *a1;
  LOBYTE(v42) = *(_BYTE *)(v4 + *a1) & 0xF;
  v13 = v42;
  if ( (unsigned __int8)v42 > 6u )
  {
    if ( (unsigned __int8)v42 == 7 )
    {
      v38 = (unsigned int)(v8 + v4);
      v39 = v38 + v9;
      if ( (unsigned int)v38 >= (unsigned int)v38 + v9 )
        return 0;
      while ( 1 )
      {
        v40 = *(unsigned __int8 *)(v38 + v12);
        if ( !*((_BYTE *)qword_1800C11D0 + v40) && (_BYTE)v40 != 39 )
          break;
        v38 = (unsigned int)(v38 + 1);
        if ( (unsigned int)v38 >= v39 )
          return 0;
      }
      return (unsigned int)(v38 + 1);
    }
    if ( (unsigned __int8)v42 != 8 && (unsigned __int8)v42 != 9 )
    {
      if ( (unsigned __int8)v42 != 10 )
      {
        if ( (unsigned __int8)v42 == 11 )
        {
          LODWORD(v4) = v8 + v4;
          v31 = v4 + v9;
          if ( (unsigned int)v4 < (unsigned int)v4 + v9 )
          {
            while ( 1 )
            {
              v42 = 0;
              v32 = jsonbPayloadSize(a1, v4, &v42);
              if ( !v32 )
                break;
              v33 = v32 + v4 + v42;
              if ( v33 > v31 )
                break;
              result = jsonbValidityCheck(a1, (unsigned int)v4, v33, a4 + 1);
              if ( (_DWORD)result )
                return result;
              LODWORD(v4) = v33;
              if ( v33 >= v31 )
                return 0;
            }
            return (unsigned int)(v4 + 1);
          }
        }
        else
        {
          if ( (unsigned __int8)v42 != 12 )
            return (unsigned int)(v4 + 1);
          LODWORD(v4) = v8 + v4;
          v27 = 0;
          v28 = v4 + v9;
          if ( (unsigned int)v4 < (unsigned int)v4 + v9 )
          {
            while ( 1 )
            {
              v42 = 0;
              v29 = jsonbPayloadSize(a1, v4, &v42);
              if ( !v29 )
                break;
              v30 = v29 + v4 + v42;
              if ( v30 > v28 || (v27 & 1) == 0 && (unsigned __int8)((*(_BYTE *)((unsigned int)v4 + v12) & 0xF) - 7) > 3u )
                break;
              result = jsonbValidityCheck(a1, (unsigned int)v4, v30, a4 + 1);
              if ( (_DWORD)result )
                return result;
              ++v27;
              LODWORD(v4) = v30;
              if ( v30 >= v28 )
              {
                if ( (v27 & 1) == 0 )
                  return 0;
                return v30 + 1;
              }
            }
            return (unsigned int)(v4 + 1);
          }
        }
      }
      return 0;
    }
    v4 = (unsigned int)(v8 + v4);
    v34 = v4 + v9;
    if ( (unsigned int)v4 >= (unsigned int)v4 + v9 )
      return 0;
    while ( 1 )
    {
      v35 = *(unsigned __int8 *)(v4 + v12);
      if ( *((_BYTE *)qword_1800C11D0 + v35) || (_BYTE)v35 == 39 )
        goto LABEL_112;
      if ( (_BYTE)v35 == 34 || (unsigned __int8)v35 <= 0x1Fu )
      {
        if ( v13 == 8 )
          return (unsigned int)(v4 + 1);
        goto LABEL_112;
      }
      if ( (_BYTE)v35 != 92 )
        return (unsigned int)(v4 + 1);
      v36 = (unsigned int)(v4 + 1);
      if ( (unsigned int)v36 >= v34 )
        return (unsigned int)(v4 + 1);
      if ( !strchr("\"\\/bfnrt", *(unsigned __int8 *)(v36 + v12)) )
      {
        if ( *(_BYTE *)(v36 + v12) != 117 )
        {
          if ( (_BYTE)v42 != 9 )
            return (unsigned int)v36;
          v41[0] = 0;
          v37 = jsonUnescapeOneChar(v12 + (unsigned int)v4, v34 - (unsigned int)v4, v41);
          if ( v41[0] == 629145 )
            return (unsigned int)v36;
          LODWORD(v4) = v37 + v4 - 1;
          goto LABEL_111;
        }
        if ( (int)v4 + 5 >= v34 || !(unsigned int)jsonIs4Hex(v12 + (unsigned int)(v4 + 2)) )
          return (unsigned int)v36;
      }
      LODWORD(v4) = v4 + 1;
LABEL_111:
      v13 = v42;
LABEL_112:
      v4 = (unsigned int)(v4 + 1);
      if ( (unsigned int)v4 >= v34 )
        return 0;
    }
  }
  if ( (unsigned __int8)v42 == 6 )
  {
LABEL_38:
    if ( v9 < 2 )
      return (unsigned int)(v4 + 1);
    v20 = (unsigned int)(v8 + v4);
    if ( *(_BYTE *)(v20 + v12) == 45 )
    {
      if ( v9 < 3 )
        return (unsigned int)(v4 + 1);
      v21 = (unsigned int)(v20 + 1);
    }
    else
    {
      v21 = (unsigned int)v20;
    }
    v22 = v20 + v9;
    v23 = *(_BYTE *)((unsigned int)v21 + v12);
    if ( v23 == 46 )
    {
      v17 = (unsigned int)(v21 + 1);
      if ( (_BYTE)v42 != 5 && (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(v17 + v12)) & 4) != 0 )
      {
        LODWORD(v21) = v21 + 2;
        v24 = 1;
        goto LABEL_67;
      }
    }
    else
    {
      v24 = 0;
      if ( v23 != 48 || (_BYTE)v42 != 5 )
      {
LABEL_67:
        while ( (unsigned int)v21 < v22 )
        {
          v26 = *(unsigned __int8 *)((unsigned int)v21 + v12);
          if ( (*((_BYTE *)&qword_1800B4FF0 + v26) & 4) == 0 )
          {
            if ( (_BYTE)v26 == 46 )
            {
              if ( v24
                || (_BYTE)v42 == 5
                && ((_DWORD)v21 == v22 - 1
                 || (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)((unsigned int)(v21 + 1) + v12)) & 4) == 0) )
              {
                return (unsigned int)(v21 + 1);
              }
              v24 = 1;
            }
            else
            {
              if ( (((_BYTE)v26 - 69) & 0xDF) != 0 )
                return (unsigned int)(v21 + 1);
              v17 = (unsigned int)(v21 + 1);
              if ( v24 == 2 || (_DWORD)v21 == v22 - 1 )
                return (unsigned int)v17;
              if ( ((*(_BYTE *)(v17 + v12) - 43) & 0xFD) == 0 )
              {
                LODWORD(v21) = v21 + 1;
                if ( (_DWORD)v17 == v22 - 1 )
                  return (unsigned int)(v17 + 1);
              }
              v24 = 2;
            }
          }
          LODWORD(v21) = v21 + 1;
        }
        if ( v24 )
          return 0;
        return (unsigned int)(v4 + 1);
      }
      v17 = (unsigned int)(v21 + 1);
      if ( (int)v21 + 3 <= v22 )
      {
        LOBYTE(v21) = *(_BYTE *)(v17 + v12) - 46;
        if ( (unsigned __int8)v21 <= 0x37u )
        {
          v25 = 0x80000000800001LL;
          if ( _bittest64(&v25, v21) )
          {
            LODWORD(v21) = v17;
            goto LABEL_67;
          }
        }
      }
    }
    return (unsigned int)v17;
  }
  if ( !(_BYTE)v42 || (unsigned __int8)v42 == 1 || (unsigned __int8)v42 == 2 )
  {
    result = 0;
    if ( v10 != 1 )
      return (unsigned int)(v4 + 1);
  }
  else
  {
    if ( (unsigned __int8)v42 != 3 )
    {
      if ( (unsigned __int8)v42 != 4 )
      {
        if ( (unsigned __int8)v42 != 5 )
          return (unsigned int)(v4 + 1);
        goto LABEL_38;
      }
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
      v16 = v15 + 2;
      if ( v16 < v11 )
      {
        while ( 1 )
        {
          LODWORD(v17) = v16 + 1;
          if ( (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(v16 + v12)) & 8) == 0 )
            break;
          ++v16;
          if ( (unsigned int)v17 >= v11 )
            return 0;
        }
        return (unsigned int)v17;
      }
      return 0;
    }
    if ( !v9 )
      return (unsigned int)(v4 + 1);
    v18 = (unsigned int)(v8 + v4);
    if ( *(_BYTE *)(v18 + v12) == 45 )
    {
      if ( v9 < 2 )
        return (unsigned int)(v4 + 1);
      LODWORD(v18) = v18 + 1;
    }
    if ( (unsigned int)v18 >= v11 )
      return 0;
    while ( 1 )
    {
      v19 = v18 + 1;
      if ( (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)((unsigned int)v18 + v12)) & 4) == 0 )
        break;
      LODWORD(v18) = v18 + 1;
      if ( v19 >= v11 )
        return 0;
    }
    return v19;
  }
  return result;
}

```

## disassembly

```asm
0x180087dc4  push    rbp
0x180087dc6  push    rbx
0x180087dc7  push    rsi
0x180087dc8  push    rdi
0x180087dc9  push    r12
0x180087dcb  push    r13
0x180087dcd  push    r14
0x180087dcf  push    r15
0x180087dd1  mov     rbp, rsp
0x180087dd4  sub     rsp, 38h
0x180087dd8  mov     ebx, edx
0x180087dda  mov     r13d, r9d
0x180087ddd  mov     edi, r8d
0x180087de0  mov     r14, rcx
0x180087de3  cmp     r9d, 3E8h
0x180087dea  ja      short loc_180087E69
0x180087dec  lea     r8, [rbp+arg_18]
0x180087df0  mov     [rbp+arg_18], 0
0x180087df7  mov     edx, ebx
0x180087df9  call    jsonbPayloadSize
0x180087dfe  mov     edx, eax
0x180087e00  test    eax, eax
0x180087e02  jz      short loc_180087E69
0x180087e04  mov     r8d, [rbp+arg_18]
0x180087e08  lea     r10d, [r8+rax]
0x180087e0c  lea     r9d, [r10+rbx]
0x180087e10  cmp     r9d, edi
0x180087e13  jnz     short loc_180087E69
0x180087e15  mov     rdi, [r14]
0x180087e18  mov     r11b, [rbx+rdi]
0x180087e1c  and     r11b, 0Fh
0x180087e20  movzx   ecx, r11b
0x180087e24  mov     byte ptr [rbp+arg_18], r11b
0x180087e28  cmp     ecx, 6
0x180087e2b  ja      loc_180088091
0x180087e31  jz      loc_180087F3B
0x180087e37  test    r11b, r11b
0x180087e3a  jz      loc_180087F2A
0x180087e40  sub     ecx, 1
0x180087e43  jz      loc_180087F2A
0x180087e49  sub     ecx, 1
0x180087e4c  jz      loc_180087F2A
0x180087e52  sub     ecx, 1
0x180087e55  jz      loc_180087EDF
0x180087e5b  sub     ecx, 1
0x180087e5e  jz      short loc_180087E7D
0x180087e60  cmp     ecx, 1
0x180087e63  jz      loc_180087F3B
0x180087e69  lea     eax, [rbx+1]
0x180087e6c  add     rsp, 38h
0x180087e70  pop     r15
0x180087e72  pop     r14
0x180087e74  pop     r13
0x180087e76  pop     r12
0x180087e78  pop     rdi
0x180087e79  pop     rsi
0x180087e7a  pop     rbx
0x180087e7b  pop     rbp
0x180087e7c  retn
0x180087e7d  cmp     r8d, 3
0x180087e81  jb      short loc_180087E69
0x180087e83  add     edx, ebx
0x180087e85  cmp     byte ptr [rdx+rdi], 2Dh ; '-'
0x180087e89  jnz     short loc_180087E93
0x180087e8b  cmp     r8d, 4
0x180087e8f  jb      short loc_180087E69
0x180087e91  inc     edx
0x180087e93  cmp     byte ptr [rdx+rdi], 30h ; '0'
0x180087e97  jnz     short loc_180087E69
0x180087e99  lea     eax, [rdx+1]
0x180087e9c  mov     al, [rax+rdi]
0x180087e9f  sub     al, 58h ; 'X'
0x180087ea1  test    al, 0DFh
0x180087ea3  jz      short loc_180087EAA
0x180087ea5  lea     eax, [rdx+2]
0x180087ea8  jmp     short loc_180087E6C
0x180087eaa  add     edx, 2
0x180087ead  cmp     edx, r9d
0x180087eb0  jnb     short loc_180087ED6
0x180087eb2  lea     r14, __ImageBase
0x180087eb9  mov     eax, edx
0x180087ebb  lea     r8d, [rdx+1]
0x180087ebf  movzx   ecx, byte ptr [rax+rdi]
0x180087ec3  test    byte ptr [rcx+r14+0B4FF0h], 8
0x180087ecc  jz      short loc_180087EDA
0x180087ece  mov     edx, r8d
0x180087ed1  cmp     r8d, r9d
0x180087ed4  jb      short loc_180087EB9
0x180087ed6  xor     eax, eax
0x180087ed8  jmp     short loc_180087E6C
0x180087eda  mov     eax, r8d
0x180087edd  jmp     short loc_180087E6C
0x180087edf  cmp     r8d, 1
0x180087ee3  jb      short loc_180087E69
0x180087ee5  lea     ecx, [rax+rbx]
0x180087ee8  cmp     byte ptr [rcx+rdi], 2Dh ; '-'
0x180087eec  jnz     short loc_180087EFA
0x180087eee  cmp     r8d, 2
0x180087ef2  jb      loc_180087E69
0x180087ef8  inc     ecx
0x180087efa  cmp     ecx, r9d
0x180087efd  jnb     short loc_180087ED6
0x180087eff  lea     r14, __ImageBase
0x180087f06  mov     eax, ecx
0x180087f08  lea     edx, [rcx+1]
0x180087f0b  movzx   ecx, byte ptr [rax+rdi]
0x180087f0f  test    byte ptr [rcx+r14+0B4FF0h], 4
0x180087f18  jz      short loc_180087F23
0x180087f1a  mov     ecx, edx
0x180087f1c  cmp     edx, r9d
0x180087f1f  jb      short loc_180087F06
0x180087f21  jmp     short loc_180087ED6
0x180087f23  mov     eax, edx
0x180087f25  jmp     loc_180087E6C
0x180087f2a  xor     eax, eax
0x180087f2c  lea     ecx, [rbx+1]
0x180087f2f  cmp     r10d, 1
0x180087f33  cmovnz  eax, ecx
0x180087f36  jmp     loc_180087E6C
0x180087f3b  cmp     r8d, 2
0x180087f3f  jb      loc_180087E69
0x180087f45  lea     ecx, [rax+rbx]
0x180087f48  cmp     byte ptr [rcx+rdi], 2Dh ; '-'
0x180087f4c  jnz     short loc_180087F5D
0x180087f4e  cmp     r8d, 3
0x180087f52  jb      loc_180087E69
0x180087f58  lea     edx, [rcx+1]
0x180087f5b  jmp     short loc_180087F5F
0x180087f5d  mov     edx, ecx
0x180087f5f  mov     eax, edx
0x180087f61  lea     r10d, [rcx+r8]
0x180087f65  mov     r15b, 2Eh ; '.'
0x180087f68  lea     r14, __ImageBase
0x180087f6f  mov     sil, 5
0x180087f72  mov     r8b, [rax+rdi]
0x180087f76  cmp     r8b, r15b
0x180087f79  jnz     short loc_180087FA6
0x180087f7b  lea     r8d, [rdx+1]
0x180087f7f  cmp     r11b, sil
0x180087f82  jz      loc_180087EDA
0x180087f88  movzx   ecx, byte ptr [r8+rdi]
0x180087f8d  test    byte ptr [rcx+r14+0B4FF0h], 4
0x180087f96  jz      loc_180087EDA
0x180087f9c  add     edx, 2
0x180087f9f  mov     cl, 1
0x180087fa1  jmp     loc_18008806E
0x180087fa6  xor     cl, cl
0x180087fa8  cmp     r8b, 30h ; '0'
0x180087fac  jnz     loc_18008806E
0x180087fb2  cmp     r11b, sil
0x180087fb5  jnz     loc_18008806E
0x180087fbb  lea     eax, [rdx+3]
0x180087fbe  lea     r8d, [rdx+1]
0x180087fc2  cmp     eax, r10d
0x180087fc5  ja      loc_180087EDA
0x180087fcb  mov     dl, [r8+rdi]
0x180087fcf  sub     dl, r15b
0x180087fd2  cmp     dl, 37h ; '7'
0x180087fd5  ja      loc_180087EDA
0x180087fdb  mov     rax, 80000000800001h
0x180087fe5  bt      rax, rdx
0x180087fe9  jnb     loc_180087EDA
0x180087fef  mov     edx, r8d
0x180087ff2  jmp     short loc_18008806E
0x180087ff4  mov     eax, edx
0x180087ff6  movzx   r8d, byte ptr [rax+rdi]
0x180087ffb  test    byte ptr [r8+r14+0B4FF0h], 4
0x180088004  jnz     short loc_18008806C
0x180088006  cmp     r8b, r15b
0x180088009  jnz     short loc_180088032
0x18008800b  test    cl, cl
0x18008800d  jnz     short loc_180088089
0x18008800f  cmp     r11b, sil
0x180088012  jnz     short loc_18008802E
0x180088014  lea     eax, [r10-1]
0x180088018  cmp     edx, eax
0x18008801a  jz      short loc_180088089
0x18008801c  lea     eax, [rdx+1]
0x18008801f  movzx   eax, byte ptr [rax+rdi]
0x180088023  test    byte ptr [rax+r14+0B4FF0h], 4
0x18008802c  jz      short loc_180088089
0x18008802e  mov     cl, 1
0x180088030  jmp     short loc_18008806C
0x180088032  sub     r8b, 45h ; 'E'
0x180088036  test    r8b, 0DFh
0x18008803a  jnz     short loc_180088089
0x18008803c  lea     r8d, [rdx+1]
0x180088040  cmp     cl, 2
0x180088043  jz      loc_180087EDA
0x180088049  lea     r9d, [r10-1]
0x18008804d  cmp     edx, r9d
0x180088050  jz      loc_180087EDA
0x180088056  mov     cl, [r8+rdi]
0x18008805a  sub     cl, 2Bh ; '+'
0x18008805d  test    cl, 0FDh
0x180088060  jnz     short loc_18008806A
0x180088062  mov     edx, r8d
0x180088065  cmp     r8d, r9d
0x180088068  jz      short loc_180088080
0x18008806a  mov     cl, 2
0x18008806c  inc     edx
0x18008806e  cmp     edx, r10d
0x180088071  jb      short loc_180087FF4
0x180088073  test    cl, cl
0x180088075  jnz     loc_180087ED6
0x18008807b  jmp     loc_180087E69
0x180088080  lea     eax, [r8+1]
0x180088084  jmp     loc_180087E6C
0x180088089  lea     eax, [rdx+1]
0x18008808c  jmp     loc_180087E6C
0x180088091  sub     ecx, 7
0x180088094  jz      loc_180088295
0x18008809a  sub     ecx, 1
0x18008809d  jz      loc_1800881B6
0x1800880a3  sub     ecx, 1
0x1800880a6  jz      loc_1800881B6
0x1800880ac  sub     ecx, 1
0x1800880af  jz      loc_180087ED6
0x1800880b5  sub     ecx, 1
0x1800880b8  jz      loc_180088158
0x1800880be  cmp     ecx, 1
0x1800880c1  jnz     loc_180087E69
0x1800880c7  add     ebx, edx
0x1800880c9  xor     esi, esi
0x1800880cb  lea     r12d, [rbx+r8]
0x1800880cf  cmp     ebx, r12d
0x1800880d2  jnb     loc_180087ED6
0x1800880d8  lea     r8, [rbp+arg_18]
0x1800880dc  mov     [rbp+arg_18], 0
0x1800880e3  mov     edx, ebx
0x1800880e5  mov     rcx, r14
0x1800880e8  call    jsonbPayloadSize
0x1800880ed  test    eax, eax
0x1800880ef  jz      loc_180087E69
0x1800880f5  mov     r15d, [rbp+arg_18]
0x1800880f9  add     r15d, ebx
0x1800880fc  add     r15d, eax
0x1800880ff  cmp     r15d, r12d
0x180088102  ja      loc_180087E69
0x180088108  test    sil, 1
0x18008810c  jnz     short loc_180088122
0x18008810e  mov     eax, ebx
0x180088110  mov     cl, [rax+rdi]
0x180088113  and     cl, 0Fh
0x180088116  sub     cl, 7
0x180088119  cmp     cl, 3
0x18008811c  ja      loc_180087E69
0x180088122  lea     r9d, [r13+1]
0x180088126  mov     r8d, r15d
0x180088129  mov     edx, ebx
0x18008812b  mov     rcx, r14
0x18008812e  call    jsonbValidityCheck
0x180088133  test    eax, eax
0x180088135  jnz     loc_180087E6C
0x18008813b  inc     esi
0x18008813d  mov     ebx, r15d
0x180088140  cmp     r15d, r12d
0x180088143  jb      short loc_1800880D8
0x180088145  test    sil, 1
0x180088149  jz      loc_180087ED6
0x18008814f  lea     eax, [r15+1]
0x180088153  jmp     loc_180087E6C
0x180088158  add     ebx, edx
0x18008815a  lea     esi, [rbx+r8]
0x18008815e  cmp     ebx, esi
0x180088160  jnb     loc_180087ED6
0x180088166  lea     r8, [rbp+arg_18]
0x18008816a  mov     [rbp+arg_18], 0
0x180088171  mov     edx, ebx
0x180088173  mov     rcx, r14
0x180088176  call    jsonbPayloadSize
0x18008817b  test    eax, eax
0x18008817d  jz      loc_180087E69
0x180088183  mov     edi, [rbp+arg_18]
0x180088186  add     edi, ebx
0x180088188  add     edi, eax
0x18008818a  cmp     edi, esi
0x18008818c  ja      loc_180087E69
0x180088192  lea     r9d, [r13+1]
0x180088196  mov     r8d, edi
0x180088199  mov     edx, ebx
0x18008819b  mov     rcx, r14
0x18008819e  call    jsonbValidityCheck
0x1800881a3  test    eax, eax
0x1800881a5  jnz     loc_180087E6C
0x1800881ab  mov     ebx, edi
0x1800881ad  cmp     edi, esi
0x1800881af  jb      short loc_180088166
0x1800881b1  jmp     loc_180087ED6
0x1800881b6  add     ebx, edx
0x1800881b8  lea     r15d, [rbx+r8]
0x1800881bc  cmp     ebx, r15d
0x1800881bf  jnb     loc_180087ED6
0x1800881c5  lea     r14, __ImageBase
0x1800881cc  movzx   ecx, byte ptr [rbx+rdi]
0x1800881d0  cmp     byte ptr [rcx+r14+0C11D0h], 0
0x1800881d9  jnz     loc_180088285
0x1800881df  cmp     cl, 27h ; '''
0x1800881e2  jz      loc_180088285
0x1800881e8  cmp     cl, 22h ; '"'
  ... truncated ...
```
