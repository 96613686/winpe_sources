# Dns_GetBufferLengthForStringCopy

- ea: `0x18000e470`
- end: `0x18000e677`
- name: `Dns_GetBufferLengthForStringCopy`
- size: `519`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e680`
- `0x18000ea2c`
- `0x180012dac`

## callees

- `0x18000e470`
- `0x180012cf0`
- `0x180012d64`
- `0x180013344`
- `0x180015f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e660`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e660`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e578`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e578`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e515`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e515`

## pseudocode

```c
__int64 __fastcall Dns_GetBufferLengthForStringCopy(LPCCH lpMultiByteStr, int cbMultiByte, int a3, int a4)
{
  __int64 v4; // rbx
  DWORD v7; // ecx
  __int64 v8; // rdi
  __int64 v9; // rax
  UINT v10; // ecx
  int v11; // eax
  UINT v12; // ecx
  int v13; // eax
  __int128 v14; // [rsp+40h] [rbp-48h] BYREF

  LODWORD(v4) = cbMultiByte;
  if ( g_fVelocityDnsKernelApi )
    return Dns_GetBufferLengthForStringCopyU(lpMultiByteStr, cbMultiByte);
  if ( lpMultiByteStr )
  {
    v8 = -1;
    if ( a3 == 1 )
    {
      if ( !cbMultiByte )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)&lpMultiByteStr[2 * v9] );
        LODWORD(v4) = (unsigned __int16)v9;
      }
      switch ( a4 )
      {
        case 1:
          return (unsigned int)(2 * v4 + 2);
        case 2:
          v10 = 65001;
LABEL_16:
          v11 = WideCharToMultiByte(v10, 0, (LPCWCH)lpMultiByteStr, v4, 0, 0, 0, 0);
          if ( v11 || !(_DWORD)v4 )
            return (unsigned int)(v11 + 1);
          break;
        case 3:
          v10 = 0;
          goto LABEL_16;
      }
LABEL_38:
      if ( SBYTE3(xmmword_18001F260) < 0 )
      {
        v14 = (unsigned __int64)lpMultiByteStr;
        if ( (_DWORD)v4 == -1 )
        {
          do
            ++v8;
          while ( lpMultiByteStr[v8] );
        }
        else
        {
          LODWORD(v8) = v4;
        }
        if ( (_DWORD)v8 )
        {
          if ( (unsigned int)v8 <= 0xFFFF )
            WORD4(v14) = v8;
          else
            WORD4(v14) = -1;
        }
        else
        {
          WORD4(v14) = 1;
          *(_QWORD *)&v14 = &qword_18001AD20;
        }
        WPP_SF_q_COUNTEDSTRING_ddd(
          (_DWORD)lpMultiByteStr,
          11,
          (unsigned int)WPP_0858b138ff673a747303b7a775217598_Traceguids,
          (_DWORD)lpMultiByteStr,
          (__int64)&v14);
      }
      v7 = 13;
      goto LABEL_50;
    }
    if ( !cbMultiByte )
    {
      v4 = -1;
      do
        ++v4;
      while ( lpMultiByteStr[v4] );
    }
    if ( a4 == a3 )
      return (unsigned int)(v4 + 1);
    if ( a4 != 1 )
    {
      if ( a3 == 2 )
      {
        if ( a4 == 3 )
          return Dns_Utf8ToAnsi(lpMultiByteStr, (unsigned int)v4, 0, 0);
      }
      else if ( a3 == 3 && a4 == 2 )
      {
        return Dns_AnsiToUtf8(lpMultiByteStr, (unsigned int)v4, 0, 0);
      }
      goto LABEL_38;
    }
    if ( a3 == 2 )
    {
      v12 = 65001;
    }
    else
    {
      if ( a3 != 3 )
        goto LABEL_38;
      v12 = 0;
    }
    v13 = MultiByteToWideChar(v12, 0, lpMultiByteStr, v4, 0, 0);
    if ( v13 || !(_DWORD)v4 )
      return (unsigned int)(2 * v13 + 2);
    goto LABEL_38;
  }
  v7 = 87;
LABEL_50:
  SetLastError(v7);
  return 0;
}

```

## disassembly

```asm
0x18000e470  push    rbx
0x18000e472  push    rbp
0x18000e473  push    rsi
0x18000e474  push    rdi
0x18000e475  push    r12
0x18000e477  push    r14
0x18000e479  push    r15
0x18000e47b  sub     rsp, 50h
0x18000e47f  xor     r15d, r15d
0x18000e482  mov     ebp, r9d
0x18000e485  cmp     cs:g_fVelocityDnsKernelApi, r15d
0x18000e48c  mov     r14d, r8d
0x18000e48f  mov     ebx, edx
0x18000e491  mov     rsi, rcx
0x18000e494  jz      short loc_18000E4A0
0x18000e496  call    Dns_GetBufferLengthForStringCopyU
0x18000e49b  jmp     loc_18000E668
0x18000e4a0  test    rsi, rsi
0x18000e4a3  jnz     short loc_18000E4AD
0x18000e4a5  lea     ecx, [rsi+57h]
0x18000e4a8  jmp     loc_18000E660
0x18000e4ad  mov     r12d, 1
0x18000e4b3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e4b7  cmp     r14d, r12d
0x18000e4ba  jnz     short loc_18000E52E
0x18000e4bc  test    edx, edx
0x18000e4be  jnz     short loc_18000E4D0
0x18000e4c0  mov     rax, rdi
0x18000e4c3  inc     rax
0x18000e4c6  cmp     [rcx+rax*2], r15w
0x18000e4cb  jnz     short loc_18000E4C3
0x18000e4cd  movzx   ebx, ax
0x18000e4d0  cmp     ebp, r12d
0x18000e4d3  jnz     short loc_18000E4E1
0x18000e4d5  lea     eax, ds:2[rbx*2]
0x18000e4dc  jmp     loc_18000E668
0x18000e4e1  cmp     ebp, 2
0x18000e4e4  jnz     short loc_18000E4ED
0x18000e4e6  mov     ecx, 0FDE9h
0x18000e4eb  jmp     short loc_18000E4F9
0x18000e4ed  cmp     ebp, 3
0x18000e4f0  jnz     loc_18000E5CC
0x18000e4f6  mov     ecx, r15d; CodePage
0x18000e4f9  mov     [rsp+88h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18000e4fe  mov     r9d, ebx; cchWideChar
0x18000e501  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x18000e506  mov     r8, rsi; lpWideCharStr
0x18000e509  mov     [rsp+88h+cbMultiByte], r15d; cbMultiByte
0x18000e50e  xor     edx, edx; dwFlags
0x18000e510  mov     [rsp+88h+lpMultiByteStr], r15; lpMultiByteStr
0x18000e515  call    cs:__imp_WideCharToMultiByte
0x18000e51b  test    eax, eax
0x18000e51d  jnz     short loc_18000E527
0x18000e51f  test    ebx, ebx
0x18000e521  jnz     loc_18000E5CC
0x18000e527  inc     eax
0x18000e529  jmp     loc_18000E668
0x18000e52e  test    edx, edx
0x18000e530  jnz     short loc_18000E53E
0x18000e532  mov     rbx, rdi
0x18000e535  inc     rbx
0x18000e538  cmp     [rcx+rbx], r15b
0x18000e53c  jnz     short loc_18000E535
0x18000e53e  cmp     ebp, r14d
0x18000e541  jnz     short loc_18000E54B
0x18000e543  lea     eax, [rbx+1]
0x18000e546  jmp     loc_18000E668
0x18000e54b  cmp     ebp, r12d
0x18000e54e  jnz     short loc_18000E592
0x18000e550  cmp     r14d, 2
0x18000e554  jnz     short loc_18000E55D
0x18000e556  mov     ecx, 0FDE9h
0x18000e55b  jmp     short loc_18000E566
0x18000e55d  cmp     r14d, 3
0x18000e561  jnz     short loc_18000E5CC
0x18000e563  mov     ecx, r15d; CodePage
0x18000e566  mov     [rsp+88h+cbMultiByte], r15d; cchWideChar
0x18000e56b  mov     r9d, ebx; cbMultiByte
0x18000e56e  mov     r8, rsi; lpMultiByteStr
0x18000e571  mov     [rsp+88h+lpMultiByteStr], r15; lpWideCharStr
0x18000e576  xor     edx, edx; dwFlags
0x18000e578  call    cs:__imp_MultiByteToWideChar
0x18000e57e  test    eax, eax
0x18000e580  jnz     short loc_18000E586
0x18000e582  test    ebx, ebx
0x18000e584  jnz     short loc_18000E5CC
0x18000e586  lea     eax, ds:2[rax*2]
0x18000e58d  jmp     loc_18000E668
0x18000e592  cmp     r14d, 2
0x18000e596  jnz     short loc_18000E5AF
0x18000e598  cmp     ebp, 3
0x18000e59b  jnz     short loc_18000E5CC
0x18000e59d  xor     r9d, r9d
0x18000e5a0  xor     r8d, r8d
0x18000e5a3  mov     edx, ebx
0x18000e5a5  call    Dns_Utf8ToAnsi
0x18000e5aa  jmp     loc_18000E668
0x18000e5af  cmp     r14d, 3
0x18000e5b3  jnz     short loc_18000E5CC
0x18000e5b5  cmp     ebp, 2
0x18000e5b8  jnz     short loc_18000E5CC
0x18000e5ba  xor     r9d, r9d
0x18000e5bd  xor     r8d, r8d
0x18000e5c0  mov     edx, ebx
0x18000e5c2  call    Dns_AnsiToUtf8
0x18000e5c7  jmp     loc_18000E668
0x18000e5cc  cmp     byte ptr cs:xmmword_18001F260+3, r15b
0x18000e5d3  jge     loc_18000E65B
0x18000e5d9  xorps   xmm0, xmm0
0x18000e5dc  movups  [rsp+88h+var_48], xmm0
0x18000e5e1  mov     qword ptr [rsp+88h+var_48], rsi
0x18000e5e6  cmp     ebx, 0FFFFFFFFh
0x18000e5e9  jnz     short loc_18000E5F6
0x18000e5eb  inc     rdi
0x18000e5ee  cmp     [rsi+rdi], r15b
0x18000e5f2  jnz     short loc_18000E5EB
0x18000e5f4  jmp     short loc_18000E5F8
0x18000e5f6  mov     edi, ebx
0x18000e5f8  test    edi, edi
0x18000e5fa  jz      short loc_18000E613
0x18000e5fc  mov     eax, 0FFFFh
0x18000e601  cmp     edi, eax
0x18000e603  jbe     short loc_18000E60C
0x18000e605  mov     word ptr [rsp+88h+var_48+8], ax
0x18000e60a  jmp     short loc_18000E625
0x18000e60c  mov     word ptr [rsp+88h+var_48+8], di
0x18000e611  jmp     short loc_18000E625
0x18000e613  lea     rax, qword_18001AD20
0x18000e61a  mov     word ptr [rsp+88h+var_48+8], r12w
0x18000e620  mov     qword ptr [rsp+88h+var_48], rax
0x18000e625  movaps  xmm0, [rsp+88h+var_48]
0x18000e62a  lea     rax, [rsp+88h+var_48]
0x18000e62f  mov     dword ptr [rsp+88h+lpUsedDefaultChar], ebp
0x18000e633  lea     r8, WPP_0858b138ff673a747303b7a775217598_Traceguids
0x18000e63a  mov     dword ptr [rsp+88h+lpDefaultChar], r14d
0x18000e63f  mov     edx, 0Bh
0x18000e644  mov     [rsp+88h+cbMultiByte], ebx
0x18000e648  mov     r9, rsi
0x18000e64b  mov     [rsp+88h+lpMultiByteStr], rax
0x18000e650  movdqa  [rsp+88h+var_48], xmm0
0x18000e656  call    WPP_SF_q_COUNTEDSTRING_ddd
0x18000e65b  mov     ecx, 0Dh; dwErrCode
0x18000e660  call    cs:__imp_SetLastError
0x18000e666  xor     eax, eax
0x18000e668  add     rsp, 50h
0x18000e66c  pop     r15
0x18000e66e  pop     r14
0x18000e670  pop     r12
0x18000e672  pop     rdi
0x18000e673  pop     rsi
0x18000e674  pop     rbp
0x18000e675  pop     rbx
0x18000e676  retn
```
