# jsonbValidityCheck

- ea: `0x180078bb4`
- end: `0x1800790c4`
- name: `jsonbValidityCheck`
- size: `1296`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180074810`
- `0x180078870`
- `0x180078bb4`

## callees

- `0x18007531c`
- `0x18007864c`
- `0x180078a58`
- `0x180078bb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180079011`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180079011`

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
  __int64 v37; // rdx
  int v38; // eax
  __int64 v39; // rcx
  unsigned int v40; // edx
  __int64 v41; // r8
  _DWORD v42[6]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v43; // [rsp+98h] [rbp+60h] BYREF

  v4 = a2;
  if ( a4 > 0x3E8 )
    return (unsigned int)(v4 + 1);
  v43 = 0;
  v8 = jsonbPayloadSize(a1, a2, &v43);
  if ( !v8 )
    return (unsigned int)(v4 + 1);
  v9 = v43;
  v10 = v43 + v8;
  v11 = v43 + v8 + v4;
  if ( v11 != a3 )
    return (unsigned int)(v4 + 1);
  v12 = *a1;
  LOBYTE(v43) = *(_BYTE *)(v4 + *a1) & 0xF;
  v13 = v43;
  if ( (unsigned __int8)v43 > 6u )
  {
    if ( (unsigned __int8)v43 == 7 )
    {
      v39 = (unsigned int)(v8 + v4);
      v40 = v39 + v9;
      if ( (unsigned int)v39 >= (unsigned int)v39 + v9 )
        return 0;
      while ( 1 )
      {
        v41 = *(unsigned __int8 *)(v39 + v12);
        if ( !byte_1800AA810[v41] && (_BYTE)v41 != 39 )
          break;
        v39 = (unsigned int)(v39 + 1);
        if ( (unsigned int)v39 >= v40 )
          return 0;
      }
      return (unsigned int)(v39 + 1);
    }
    if ( (unsigned __int8)v43 != 8 && (unsigned __int8)v43 != 9 )
    {
      if ( (unsigned __int8)v43 != 10 )
      {
        if ( (unsigned __int8)v43 == 11 )
        {
          LODWORD(v4) = v8 + v4;
          v31 = v4 + v9;
          if ( (unsigned int)v4 < (unsigned int)v4 + v9 )
          {
            while ( 1 )
            {
              v43 = 0;
              v32 = jsonbPayloadSize(a1, v4, &v43);
              if ( !v32 )
                break;
              v33 = v32 + v4 + v43;
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
          if ( (unsigned __int8)v43 != 12 )
            return (unsigned int)(v4 + 1);
          LODWORD(v4) = v8 + v4;
          v27 = 0;
          v28 = v4 + v9;
          if ( (unsigned int)v4 < (unsigned int)v4 + v9 )
          {
            while ( 1 )
            {
              v43 = 0;
              v29 = jsonbPayloadSize(a1, v4, &v43);
              if ( !v29 )
                break;
              v30 = v29 + v4 + v43;
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
      if ( byte_1800AA810[v35] || (_BYTE)v35 == 39 )
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
          if ( (_BYTE)v43 != 9 )
            return (unsigned int)v36;
          v42[0] = 0;
          v38 = jsonUnescapeOneChar(v12 + (unsigned int)v4, v34 - (unsigned int)v4, v42);
          if ( v42[0] == 629145 )
            return (unsigned int)v36;
          LODWORD(v4) = v38 + v4 - 1;
          goto LABEL_111;
        }
        if ( (int)v4 + 5 >= v34 || !(unsigned int)jsonIs4Hex(v12 + (unsigned int)(v4 + 2), v37) )
          return (unsigned int)v36;
      }
      LODWORD(v4) = v4 + 1;
LABEL_111:
      v13 = v43;
LABEL_112:
      v4 = (unsigned int)(v4 + 1);
      if ( (unsigned int)v4 >= v34 )
        return 0;
    }
  }
  if ( (unsigned __int8)v43 == 6 )
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
      if ( (_BYTE)v43 != 5 && (byte_18009E630[*(unsigned __int8 *)(v17 + v12)] & 4) != 0 )
      {
        LODWORD(v21) = v21 + 2;
        v24 = 1;
        goto LABEL_67;
      }
    }
    else
    {
      v24 = 0;
      if ( v23 != 48 || (_BYTE)v43 != 5 )
      {
LABEL_67:
        while ( (unsigned int)v21 < v22 )
        {
          v26 = *(unsigned __int8 *)((unsigned int)v21 + v12);
          if ( (byte_18009E630[v26] & 4) == 0 )
          {
            if ( (_BYTE)v26 == 46 )
            {
              if ( v24
                || (_BYTE)v43 == 5
                && ((_DWORD)v21 == v22 - 1
                 || (byte_18009E630[*(unsigned __int8 *)((unsigned int)(v21 + 1) + v12)] & 4) == 0) )
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
  if ( !(_BYTE)v43 || (unsigned __int8)v43 == 1 || (unsigned __int8)v43 == 2 )
  {
    result = 0;
    if ( v10 != 1 )
      return (unsigned int)(v4 + 1);
  }
  else
  {
    if ( (unsigned __int8)v43 != 3 )
    {
      if ( (unsigned __int8)v43 != 4 )
      {
        if ( (unsigned __int8)v43 != 5 )
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
          if ( (byte_18009E630[*(unsigned __int8 *)(v16 + v12)] & 8) == 0 )
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
      if ( (byte_18009E630[*(unsigned __int8 *)((unsigned int)v18 + v12)] & 4) == 0 )
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
0x180078bb4  push    rbp
0x180078bb6  push    rbx
0x180078bb7  push    rsi
0x180078bb8  push    rdi
0x180078bb9  push    r12
0x180078bbb  push    r13
0x180078bbd  push    r14
0x180078bbf  push    r15
0x180078bc1  mov     rbp, rsp
0x180078bc4  sub     rsp, 38h
0x180078bc8  mov     ebx, edx
0x180078bca  mov     r13d, r9d
0x180078bcd  mov     edi, r8d
0x180078bd0  mov     r14, rcx
0x180078bd3  cmp     r9d, 3E8h
0x180078bda  ja      short loc_180078C59
0x180078bdc  lea     r8, [rbp+arg_18]
0x180078be0  mov     [rbp+arg_18], 0
0x180078be7  mov     edx, ebx
0x180078be9  call    jsonbPayloadSize
0x180078bee  mov     edx, eax
0x180078bf0  test    eax, eax
0x180078bf2  jz      short loc_180078C59
0x180078bf4  mov     r8d, [rbp+arg_18]
0x180078bf8  lea     r10d, [r8+rax]
0x180078bfc  lea     r9d, [r10+rbx]
0x180078c00  cmp     r9d, edi
0x180078c03  jnz     short loc_180078C59
0x180078c05  mov     rdi, [r14]
0x180078c08  mov     r11b, [rbx+rdi]
0x180078c0c  and     r11b, 0Fh
0x180078c10  movzx   ecx, r11b
0x180078c14  mov     byte ptr [rbp+arg_18], r11b
0x180078c18  cmp     ecx, 6
0x180078c1b  ja      loc_180078E81
0x180078c21  jz      loc_180078D2B
0x180078c27  test    r11b, r11b
0x180078c2a  jz      loc_180078D1A
0x180078c30  sub     ecx, 1
0x180078c33  jz      loc_180078D1A
0x180078c39  sub     ecx, 1
0x180078c3c  jz      loc_180078D1A
0x180078c42  sub     ecx, 1
0x180078c45  jz      loc_180078CCF
0x180078c4b  sub     ecx, 1
0x180078c4e  jz      short loc_180078C6D
0x180078c50  cmp     ecx, 1
0x180078c53  jz      loc_180078D2B
0x180078c59  lea     eax, [rbx+1]
0x180078c5c  add     rsp, 38h
0x180078c60  pop     r15
0x180078c62  pop     r14
0x180078c64  pop     r13
0x180078c66  pop     r12
0x180078c68  pop     rdi
0x180078c69  pop     rsi
0x180078c6a  pop     rbx
0x180078c6b  pop     rbp
0x180078c6c  retn
0x180078c6d  cmp     r8d, 3
0x180078c71  jb      short loc_180078C59
0x180078c73  add     edx, ebx
0x180078c75  cmp     byte ptr [rdx+rdi], 2Dh ; '-'
0x180078c79  jnz     short loc_180078C83
0x180078c7b  cmp     r8d, 4
0x180078c7f  jb      short loc_180078C59
0x180078c81  inc     edx
0x180078c83  cmp     byte ptr [rdx+rdi], 30h ; '0'
0x180078c87  jnz     short loc_180078C59
0x180078c89  lea     eax, [rdx+1]
0x180078c8c  mov     al, [rax+rdi]
0x180078c8f  sub     al, 58h ; 'X'
0x180078c91  test    al, 0DFh
0x180078c93  jz      short loc_180078C9A
0x180078c95  lea     eax, [rdx+2]
0x180078c98  jmp     short loc_180078C5C
0x180078c9a  add     edx, 2
0x180078c9d  cmp     edx, r9d
0x180078ca0  jnb     short loc_180078CC6
0x180078ca2  lea     r14, cs:180000000h
0x180078ca9  mov     eax, edx
0x180078cab  lea     r8d, [rdx+1]
0x180078caf  movzx   ecx, byte ptr [rax+rdi]
0x180078cb3  test    byte ptr [rcx+r14+9E630h], 8
0x180078cbc  jz      short loc_180078CCA
0x180078cbe  mov     edx, r8d
0x180078cc1  cmp     r8d, r9d
0x180078cc4  jb      short loc_180078CA9
0x180078cc6  xor     eax, eax
0x180078cc8  jmp     short loc_180078C5C
0x180078cca  mov     eax, r8d
0x180078ccd  jmp     short loc_180078C5C
0x180078ccf  cmp     r8d, 1
0x180078cd3  jb      short loc_180078C59
0x180078cd5  lea     ecx, [rax+rbx]
0x180078cd8  cmp     byte ptr [rcx+rdi], 2Dh ; '-'
0x180078cdc  jnz     short loc_180078CEA
0x180078cde  cmp     r8d, 2
0x180078ce2  jb      loc_180078C59
0x180078ce8  inc     ecx
0x180078cea  cmp     ecx, r9d
0x180078ced  jnb     short loc_180078CC6
0x180078cef  lea     r14, cs:180000000h
0x180078cf6  mov     eax, ecx
0x180078cf8  lea     edx, [rcx+1]
0x180078cfb  movzx   ecx, byte ptr [rax+rdi]
0x180078cff  test    byte ptr [rcx+r14+9E630h], 4
0x180078d08  jz      short loc_180078D13
0x180078d0a  mov     ecx, edx
0x180078d0c  cmp     edx, r9d
0x180078d0f  jb      short loc_180078CF6
0x180078d11  jmp     short loc_180078CC6
0x180078d13  mov     eax, edx
0x180078d15  jmp     loc_180078C5C
0x180078d1a  xor     eax, eax
0x180078d1c  lea     ecx, [rbx+1]
0x180078d1f  cmp     r10d, 1
0x180078d23  cmovnz  eax, ecx
0x180078d26  jmp     loc_180078C5C
0x180078d2b  cmp     r8d, 2
0x180078d2f  jb      loc_180078C59
0x180078d35  lea     ecx, [rax+rbx]
0x180078d38  cmp     byte ptr [rcx+rdi], 2Dh ; '-'
0x180078d3c  jnz     short loc_180078D4D
0x180078d3e  cmp     r8d, 3
0x180078d42  jb      loc_180078C59
0x180078d48  lea     edx, [rcx+1]
0x180078d4b  jmp     short loc_180078D4F
0x180078d4d  mov     edx, ecx
0x180078d4f  mov     eax, edx
0x180078d51  lea     r10d, [rcx+r8]
0x180078d55  mov     r15b, 2Eh ; '.'
0x180078d58  lea     r14, cs:180000000h
0x180078d5f  mov     sil, 5
0x180078d62  mov     r8b, [rax+rdi]
0x180078d66  cmp     r8b, r15b
0x180078d69  jnz     short loc_180078D96
0x180078d6b  lea     r8d, [rdx+1]
0x180078d6f  cmp     r11b, sil
0x180078d72  jz      loc_180078CCA
0x180078d78  movzx   ecx, byte ptr [r8+rdi]
0x180078d7d  test    byte ptr [rcx+r14+9E630h], 4
0x180078d86  jz      loc_180078CCA
0x180078d8c  add     edx, 2
0x180078d8f  mov     cl, 1
0x180078d91  jmp     loc_180078E5E
0x180078d96  xor     cl, cl
0x180078d98  cmp     r8b, 30h ; '0'
0x180078d9c  jnz     loc_180078E5E
0x180078da2  cmp     r11b, sil
0x180078da5  jnz     loc_180078E5E
0x180078dab  lea     eax, [rdx+3]
0x180078dae  lea     r8d, [rdx+1]
0x180078db2  cmp     eax, r10d
0x180078db5  ja      loc_180078CCA
0x180078dbb  mov     dl, [r8+rdi]
0x180078dbf  sub     dl, r15b
0x180078dc2  cmp     dl, 37h ; '7'
0x180078dc5  ja      loc_180078CCA
0x180078dcb  mov     rax, 80000000800001h
0x180078dd5  bt      rax, rdx
0x180078dd9  jnb     loc_180078CCA
0x180078ddf  mov     edx, r8d
0x180078de2  jmp     short loc_180078E5E
0x180078de4  mov     eax, edx
0x180078de6  movzx   r8d, byte ptr [rax+rdi]
0x180078deb  test    byte ptr [r8+r14+9E630h], 4
0x180078df4  jnz     short loc_180078E5C
0x180078df6  cmp     r8b, r15b
0x180078df9  jnz     short loc_180078E22
0x180078dfb  test    cl, cl
0x180078dfd  jnz     short loc_180078E79
0x180078dff  cmp     r11b, sil
0x180078e02  jnz     short loc_180078E1E
0x180078e04  lea     eax, [r10-1]
0x180078e08  cmp     edx, eax
0x180078e0a  jz      short loc_180078E79
0x180078e0c  lea     eax, [rdx+1]
0x180078e0f  movzx   eax, byte ptr [rax+rdi]
0x180078e13  test    byte ptr [rax+r14+9E630h], 4
0x180078e1c  jz      short loc_180078E79
0x180078e1e  mov     cl, 1
0x180078e20  jmp     short loc_180078E5C
0x180078e22  sub     r8b, 45h ; 'E'
0x180078e26  test    r8b, 0DFh
0x180078e2a  jnz     short loc_180078E79
0x180078e2c  lea     r8d, [rdx+1]
0x180078e30  cmp     cl, 2
0x180078e33  jz      loc_180078CCA
0x180078e39  lea     r9d, [r10-1]
0x180078e3d  cmp     edx, r9d
0x180078e40  jz      loc_180078CCA
0x180078e46  mov     cl, [r8+rdi]
0x180078e4a  sub     cl, 2Bh ; '+'
0x180078e4d  test    cl, 0FDh
0x180078e50  jnz     short loc_180078E5A
0x180078e52  mov     edx, r8d
0x180078e55  cmp     r8d, r9d
0x180078e58  jz      short loc_180078E70
0x180078e5a  mov     cl, 2
0x180078e5c  inc     edx
0x180078e5e  cmp     edx, r10d
0x180078e61  jb      short loc_180078DE4
0x180078e63  test    cl, cl
0x180078e65  jnz     loc_180078CC6
0x180078e6b  jmp     loc_180078C59
0x180078e70  lea     eax, [r8+1]
0x180078e74  jmp     loc_180078C5C
0x180078e79  lea     eax, [rdx+1]
0x180078e7c  jmp     loc_180078C5C
0x180078e81  sub     ecx, 7
0x180078e84  jz      loc_180079085
0x180078e8a  sub     ecx, 1
0x180078e8d  jz      loc_180078FA6
0x180078e93  sub     ecx, 1
0x180078e96  jz      loc_180078FA6
0x180078e9c  sub     ecx, 1
0x180078e9f  jz      loc_180078CC6
0x180078ea5  sub     ecx, 1
0x180078ea8  jz      loc_180078F48
0x180078eae  cmp     ecx, 1
0x180078eb1  jnz     loc_180078C59
0x180078eb7  add     ebx, edx
0x180078eb9  xor     esi, esi
0x180078ebb  lea     r12d, [rbx+r8]
0x180078ebf  cmp     ebx, r12d
0x180078ec2  jnb     loc_180078CC6
0x180078ec8  lea     r8, [rbp+arg_18]
0x180078ecc  mov     [rbp+arg_18], 0
0x180078ed3  mov     edx, ebx
0x180078ed5  mov     rcx, r14
0x180078ed8  call    jsonbPayloadSize
0x180078edd  test    eax, eax
0x180078edf  jz      loc_180078C59
0x180078ee5  mov     r15d, [rbp+arg_18]
0x180078ee9  add     r15d, ebx
0x180078eec  add     r15d, eax
0x180078eef  cmp     r15d, r12d
0x180078ef2  ja      loc_180078C59
0x180078ef8  test    sil, 1
0x180078efc  jnz     short loc_180078F12
0x180078efe  mov     eax, ebx
0x180078f00  mov     cl, [rax+rdi]
0x180078f03  and     cl, 0Fh
0x180078f06  sub     cl, 7
0x180078f09  cmp     cl, 3
0x180078f0c  ja      loc_180078C59
0x180078f12  lea     r9d, [r13+1]
0x180078f16  mov     r8d, r15d
0x180078f19  mov     edx, ebx
0x180078f1b  mov     rcx, r14
0x180078f1e  call    jsonbValidityCheck
0x180078f23  test    eax, eax
0x180078f25  jnz     loc_180078C5C
0x180078f2b  inc     esi
0x180078f2d  mov     ebx, r15d
0x180078f30  cmp     r15d, r12d
0x180078f33  jb      short loc_180078EC8
0x180078f35  test    sil, 1
0x180078f39  jz      loc_180078CC6
0x180078f3f  lea     eax, [r15+1]
0x180078f43  jmp     loc_180078C5C
0x180078f48  add     ebx, edx
0x180078f4a  lea     esi, [rbx+r8]
0x180078f4e  cmp     ebx, esi
0x180078f50  jnb     loc_180078CC6
0x180078f56  lea     r8, [rbp+arg_18]
0x180078f5a  mov     [rbp+arg_18], 0
0x180078f61  mov     edx, ebx
0x180078f63  mov     rcx, r14
0x180078f66  call    jsonbPayloadSize
0x180078f6b  test    eax, eax
0x180078f6d  jz      loc_180078C59
0x180078f73  mov     edi, [rbp+arg_18]
0x180078f76  add     edi, ebx
0x180078f78  add     edi, eax
0x180078f7a  cmp     edi, esi
0x180078f7c  ja      loc_180078C59
0x180078f82  lea     r9d, [r13+1]
0x180078f86  mov     r8d, edi
0x180078f89  mov     edx, ebx
0x180078f8b  mov     rcx, r14
0x180078f8e  call    jsonbValidityCheck
0x180078f93  test    eax, eax
0x180078f95  jnz     loc_180078C5C
0x180078f9b  mov     ebx, edi
0x180078f9d  cmp     edi, esi
0x180078f9f  jb      short loc_180078F56
0x180078fa1  jmp     loc_180078CC6
0x180078fa6  add     ebx, edx
0x180078fa8  lea     r15d, [rbx+r8]
0x180078fac  cmp     ebx, r15d
0x180078faf  jnb     loc_180078CC6
0x180078fb5  lea     r14, cs:180000000h
0x180078fbc  movzx   ecx, byte ptr [rbx+rdi]
0x180078fc0  cmp     byte ptr [rcx+r14+0AA810h], 0
0x180078fc9  jnz     loc_180079075
0x180078fcf  cmp     cl, 27h ; '''
0x180078fd2  jz      loc_180079075
0x180078fd8  cmp     cl, 22h ; '"'
  ... truncated ...
```
