# Dns_StringCopy

- ea: `0x18000e680`
- end: `0x18000ea26`
- name: `Dns_StringCopy`
- size: `934`
- prototype: `__int64 __fastcall(void *, unsigned int *, const CHAR *, int, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ea2c`
- `0x180012dac`

## callees

- `0x18000e470`
- `0x18000e680`
- `0x180012cf0`
- `0x180012d64`
- `0x1800135ec`
- `0x180013f19`
- `0x180015d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e72a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e748`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e72a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e748`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea0a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e860`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000e860`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e7da`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e7da`

## pseudocode

```c
__int64 __fastcall Dns_StringCopy(void *a1, unsigned int *a2, const CHAR *a3, int a4, int a5, int a6)
{
  __int64 v7; // rbx
  __int64 result; // rax
  __int64 v10; // r13
  __int64 v11; // rax
  unsigned int BufferLengthForStringCopy; // esi
  size_t v13; // r8
  unsigned int v14; // r15d
  UINT v15; // ecx
  unsigned int v16; // eax
  __int64 v17; // rcx
  DWORD v18; // ecx
  UINT v19; // ecx
  unsigned int v20; // eax
  __int64 v21; // rdx
  DWORD LastError; // r9d
  int v23; // edx
  int v24; // r8d
  __int64 v25; // rax
  unsigned int v26; // r10d
  __int64 v27; // rcx
  __int128 v28; // [rsp+70h] [rbp-19h] BYREF
  __int128 v29[5]; // [rsp+80h] [rbp-9h] BYREF

  LODWORD(v7) = a4;
  if ( g_fVelocityDnsKernelApi )
    return Dns_StringCopyU(a1, a5, a6);
  if ( !a3 )
    goto LABEL_72;
  v10 = -1;
  if ( !a4 )
  {
    if ( a5 == 1 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&a3[2 * v11] );
      LODWORD(v7) = (unsigned __int16)v11;
    }
    else
    {
      v7 = -1;
      do
        ++v7;
      while ( a3[v7] );
    }
  }
  if ( !a2 )
  {
LABEL_72:
    v18 = 87;
    goto LABEL_73;
  }
  BufferLengthForStringCopy = Dns_GetBufferLengthForStringCopy(a3, v7, a5, a6);
  if ( BufferLengthForStringCopy )
  {
    if ( BufferLengthForStringCopy > *a2 )
    {
      SetLastError(0xEAu);
      *a2 = BufferLengthForStringCopy;
      return 0;
    }
    *a2 = BufferLengthForStringCopy;
    if ( a5 == 1 )
    {
      switch ( a6 )
      {
        case 1:
          v13 = (unsigned int)(2 * v7);
          v14 = v13 + 2;
          if ( BufferLengthForStringCopy >= (int)v13 + 2 )
          {
            *((_WORD *)a1 + (unsigned int)v7) = 0;
            memcpy_0(a1, a3, v13);
            return v14;
          }
LABEL_30:
          v18 = 234;
LABEL_73:
          SetLastError(v18);
          return 0;
        case 2:
          v15 = 65001;
LABEL_25:
          v16 = WideCharToMultiByte(v15, 0, (LPCWCH)a3, v7, (LPSTR)a1, BufferLengthForStringCopy - 1, 0, 0);
          if ( v16 || !(_DWORD)v7 )
          {
            v17 = v16;
            result = v16 + 1;
            *((_BYTE *)a1 + v17) = 0;
            return result;
          }
          break;
        case 3:
          v15 = 0;
          goto LABEL_25;
      }
LABEL_44:
      LastError = GetLastError();
      if ( SBYTE3(xmmword_18001F260) < 0 )
      {
        v23 = v7;
        v24 = 0;
        v25 = (__int64)a2;
        if ( a5 != 1 )
        {
          v23 = 0;
          v24 = v7;
        }
        v28 = (unsigned __int64)a3;
        v26 = *a2;
        if ( v23 == -1 )
        {
          v27 = -1;
          do
            ++v27;
          while ( *(_WORD *)&a3[2 * v27] );
        }
        else
        {
          LODWORD(v27) = v23;
        }
        if ( (_DWORD)v27 )
        {
          v25 = (__int64)a2;
          if ( 2 * (unsigned __int64)(unsigned int)v27 <= 0xFFFE )
            WORD4(v28) = 2 * v27;
          else
            WORD4(v28) = -2;
        }
        else
        {
          WORD4(v28) = 1;
          *(_QWORD *)&v28 = &Format;
        }
        v29[0] = v28;
        v28 = (unsigned __int64)a3;
        if ( v24 == -1 )
        {
          do
            ++v10;
          while ( a3[v10] );
        }
        else
        {
          LODWORD(v10) = v24;
        }
        if ( (_DWORD)v10 )
        {
          if ( (unsigned int)v10 <= 0xFFFF )
            WORD4(v28) = v10;
          else
            WORD4(v28) = -1;
        }
        else
        {
          WORD4(v28) = 1;
          *(_QWORD *)&v28 = &qword_18001AD20;
        }
        WPP_SF_Dqqddq_COUNTEDSTRING__COUNTEDSTRINGW_ddd(
          (unsigned int)&v28,
          14,
          (unsigned int)WPP_0858b138ff673a747303b7a775217598_Traceguids,
          LastError,
          (__int64)a1,
          v25,
          v26,
          BufferLengthForStringCopy,
          (__int64)a3,
          (__int64)&v28,
          (__int64)v29,
          v7,
          a5,
          a6);
      }
      v18 = 13;
      goto LABEL_73;
    }
    if ( a6 == a5 )
    {
      v14 = v7 + 1;
      if ( (int)v7 + 1 <= BufferLengthForStringCopy )
      {
        memcpy_0(a1, a3, (unsigned int)v7);
        *((_BYTE *)a1 + (unsigned int)v7) = 0;
        return v14;
      }
      goto LABEL_30;
    }
    if ( a6 != 1 )
    {
      if ( a5 == 2 )
      {
        if ( a6 != 3 )
          goto LABEL_44;
        result = Dns_Utf8ToAnsi(a3, (unsigned int)v7, a1, BufferLengthForStringCopy);
      }
      else
      {
        if ( a5 != 3 || a6 != 2 )
          goto LABEL_44;
        result = Dns_AnsiToUtf8(a3, (unsigned int)v7, a1, BufferLengthForStringCopy);
      }
      if ( (_DWORD)result )
        return result;
      goto LABEL_44;
    }
    if ( a5 == 2 )
    {
      v19 = 65001;
    }
    else
    {
      if ( a5 != 3 )
        goto LABEL_44;
      v19 = 0;
    }
    v20 = MultiByteToWideChar(v19, 8u, a3, v7, (LPWSTR)a1, (BufferLengthForStringCopy >> 1) - 1);
    if ( v20 || !(_DWORD)v7 )
    {
      v21 = v20;
      result = 2 * v20 + 2;
      *((_WORD *)a1 + v21) = 0;
      return result;
    }
    goto LABEL_44;
  }
  SetLastError(0xDu);
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000e680  mov     [rsp-8+arg_8], rdx
0x18000e685  push    rbp
0x18000e686  push    rbx
0x18000e687  push    rsi
0x18000e688  push    rdi
0x18000e689  push    r12
0x18000e68b  push    r13
0x18000e68d  push    r14
0x18000e68f  push    r15
0x18000e691  lea     rbp, [rsp-0Fh]
0x18000e696  sub     rsp, 98h
0x18000e69d  mov     r14, rcx
0x18000e6a0  mov     ebx, r9d
0x18000e6a3  xor     ecx, ecx
0x18000e6a5  mov     rdi, r8
0x18000e6a8  cmp     cs:g_fVelocityDnsKernelApi, ecx
0x18000e6ae  jz      short loc_18000E6CB
0x18000e6b0  mov     eax, [rbp+47h+arg_28]
0x18000e6b3  mov     rcx, r14; void *
0x18000e6b6  mov     [rsp+0D0h+cbMultiByte], eax; int
0x18000e6ba  mov     eax, [rbp+47h+arg_20]
0x18000e6bd  mov     dword ptr [rsp+0D0h+lpMultiByteStr], eax; int
0x18000e6c1  call    Dns_StringCopyU
0x18000e6c6  jmp     loc_18000EA12
0x18000e6cb  test    rdi, rdi
0x18000e6ce  jz      loc_18000EA05
0x18000e6d4  mov     r15d, [rbp+47h+arg_20]
0x18000e6d8  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000e6dc  test    ebx, ebx
0x18000e6de  jnz     short loc_18000E704
0x18000e6e0  cmp     r15d, 1
0x18000e6e4  jnz     short loc_18000E6F8
0x18000e6e6  mov     rax, r13
0x18000e6e9  inc     rax
0x18000e6ec  cmp     [r8+rax*2], cx
0x18000e6f1  jnz     short loc_18000E6E9
0x18000e6f3  movzx   ebx, ax
0x18000e6f6  jmp     short loc_18000E704
0x18000e6f8  mov     rbx, r13
0x18000e6fb  inc     rbx
0x18000e6fe  cmp     [r8+rbx], cl
0x18000e702  jnz     short loc_18000E6FB
0x18000e704  test    rdx, rdx
0x18000e707  jz      loc_18000EA05
0x18000e70d  mov     r12d, [rbp+47h+arg_28]
0x18000e711  mov     r8d, r15d
0x18000e714  mov     r9d, r12d
0x18000e717  mov     edx, ebx; cbMultiByte
0x18000e719  mov     rcx, rdi; lpMultiByteStr
0x18000e71c  call    Dns_GetBufferLengthForStringCopy
0x18000e721  mov     esi, eax
0x18000e723  test    eax, eax
0x18000e725  jnz     short loc_18000E73B
0x18000e727  lea     ecx, [rax+0Dh]; dwErrCode
0x18000e72a  call    cs:__imp_SetLastError
0x18000e730  mov     rax, [rbp+47h+arg_8]
0x18000e734  mov     [rax], esi
0x18000e736  jmp     loc_18000EA10
0x18000e73b  mov     rax, [rbp+47h+arg_8]
0x18000e73f  cmp     esi, [rax]
0x18000e741  jbe     short loc_18000E759
0x18000e743  mov     ecx, 0EAh; dwErrCode
0x18000e748  call    cs:__imp_SetLastError
0x18000e74e  mov     rax, [rbp+47h+arg_8]
0x18000e752  mov     [rax], esi
0x18000e754  jmp     loc_18000EA10
0x18000e759  mov     edx, 1
0x18000e75e  mov     [rax], esi
0x18000e760  cmp     r15d, edx
0x18000e763  jnz     loc_18000E7FA
0x18000e769  cmp     r12d, edx
0x18000e76c  jnz     short loc_18000E79B
0x18000e76e  lea     r8d, [rbx+rbx]; Size
0x18000e772  lea     r15d, [r8+2]
0x18000e776  cmp     esi, r15d
0x18000e779  jb      loc_18000E808
0x18000e77f  xor     ecx, ecx
0x18000e781  mov     edx, ebx
0x18000e783  mov     [r14+rdx*2], cx
0x18000e788  mov     rdx, rdi; Src
0x18000e78b  mov     rcx, r14; void *
0x18000e78e  call    memcpy_0
0x18000e793  mov     eax, r15d
0x18000e796  jmp     loc_18000EA12
0x18000e79b  cmp     r12d, 2
0x18000e79f  jnz     short loc_18000E7A8
0x18000e7a1  mov     ecx, 0FDE9h
0x18000e7a6  jmp     short loc_18000E7B4
0x18000e7a8  cmp     r12d, 3
0x18000e7ac  jnz     loc_18000E8A7
0x18000e7b2  xor     ecx, ecx; CodePage
0x18000e7b4  mov     [rsp+0D0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000e7bd  lea     eax, [rsi-1]
0x18000e7c0  mov     [rsp+0D0h+lpDefaultChar], 0; lpDefaultChar
0x18000e7c9  mov     r9d, ebx; cchWideChar
0x18000e7cc  mov     [rsp+0D0h+cbMultiByte], eax; cbMultiByte
0x18000e7d0  mov     r8, rdi; lpWideCharStr
0x18000e7d3  xor     edx, edx; dwFlags
0x18000e7d5  mov     [rsp+0D0h+lpMultiByteStr], r14; lpMultiByteStr
0x18000e7da  call    cs:__imp_WideCharToMultiByte
0x18000e7e0  test    eax, eax
0x18000e7e2  jnz     short loc_18000E7EC
0x18000e7e4  test    ebx, ebx
0x18000e7e6  jnz     loc_18000E8A7
0x18000e7ec  mov     ecx, eax
0x18000e7ee  inc     eax
0x18000e7f0  mov     byte ptr [rcx+r14], 0
0x18000e7f5  jmp     loc_18000EA12
0x18000e7fa  cmp     r12d, r15d
0x18000e7fd  jnz     short loc_18000E82C
0x18000e7ff  lea     r15d, [rbx+1]
0x18000e803  cmp     r15d, esi
0x18000e806  jbe     short loc_18000E812
0x18000e808  mov     ecx, 0EAh
0x18000e80d  jmp     loc_18000EA0A
0x18000e812  mov     ebx, ebx
0x18000e814  mov     rdx, rdi; Src
0x18000e817  mov     r8d, ebx; Size
0x18000e81a  mov     rcx, r14; void *
0x18000e81d  call    memcpy_0
0x18000e822  mov     byte ptr [rbx+r14], 0
0x18000e827  jmp     loc_18000E793
0x18000e82c  cmp     r12d, edx
0x18000e82f  jnz     short loc_18000E883
0x18000e831  cmp     r15d, 2
0x18000e835  jnz     short loc_18000E83E
0x18000e837  mov     ecx, 0FDE9h
0x18000e83c  jmp     short loc_18000E846
0x18000e83e  cmp     r15d, 3
0x18000e842  jnz     short loc_18000E8A7
0x18000e844  xor     ecx, ecx; CodePage
0x18000e846  mov     eax, esi
0x18000e848  mov     r9d, ebx; cbMultiByte
0x18000e84b  shr     eax, 1
0x18000e84d  mov     r8, rdi; lpMultiByteStr
0x18000e850  sub     eax, edx
0x18000e852  mov     edx, 8; dwFlags
0x18000e857  mov     [rsp+0D0h+cbMultiByte], eax; cchWideChar
0x18000e85b  mov     [rsp+0D0h+lpMultiByteStr], r14; lpWideCharStr
0x18000e860  call    cs:__imp_MultiByteToWideChar
0x18000e866  test    eax, eax
0x18000e868  jnz     short loc_18000E86E
0x18000e86a  test    ebx, ebx
0x18000e86c  jnz     short loc_18000E8A7
0x18000e86e  mov     edx, eax
0x18000e870  xor     ecx, ecx
0x18000e872  lea     eax, ds:2[rax*2]
0x18000e879  mov     [r14+rdx*2], cx
0x18000e87e  jmp     loc_18000EA12
0x18000e883  cmp     r15d, 2
0x18000e887  jnz     short loc_18000E8FA
0x18000e889  cmp     r12d, 3
0x18000e88d  jnz     short loc_18000E8A7
0x18000e88f  mov     r9d, esi
0x18000e892  mov     r8, r14
0x18000e895  mov     edx, ebx
0x18000e897  mov     rcx, rdi
0x18000e89a  call    Dns_Utf8ToAnsi
0x18000e89f  test    eax, eax
0x18000e8a1  jnz     loc_18000EA12
0x18000e8a7  call    cs:__imp_GetLastError
0x18000e8ad  mov     r9d, eax
0x18000e8b0  xor     r11d, r11d
0x18000e8b3  cmp     byte ptr cs:xmmword_18001F260+3, r11b
0x18000e8ba  jge     loc_18000E9FE
0x18000e8c0  lea     eax, [r11+1]
0x18000e8c4  mov     edx, ebx
0x18000e8c6  cmp     r15d, eax
0x18000e8c9  mov     r8d, r11d
0x18000e8cc  mov     rax, [rbp+47h+arg_8]
0x18000e8d0  xorps   xmm0, xmm0
0x18000e8d3  cmovnz  edx, r11d
0x18000e8d7  cmovnz  r8d, ebx
0x18000e8db  movups  [rbp+47h+var_60], xmm0
0x18000e8df  mov     qword ptr [rbp+47h+var_60], rdi
0x18000e8e3  mov     r10d, [rax]
0x18000e8e6  cmp     edx, 0FFFFFFFFh
0x18000e8e9  jnz     short loc_18000E918
0x18000e8eb  mov     rcx, r13
0x18000e8ee  inc     rcx
0x18000e8f1  cmp     [rdi+rcx*2], r11w
0x18000e8f6  jnz     short loc_18000E8EE
0x18000e8f8  jmp     short loc_18000E91A
0x18000e8fa  cmp     r15d, 3
0x18000e8fe  jnz     short loc_18000E8A7
0x18000e900  cmp     r12d, 2
0x18000e904  jnz     short loc_18000E8A7
0x18000e906  mov     r9d, esi
0x18000e909  mov     r8, r14
0x18000e90c  mov     edx, ebx
0x18000e90e  mov     rcx, rdi
0x18000e911  call    Dns_AnsiToUtf8
0x18000e916  jmp     short loc_18000E89F
0x18000e918  mov     ecx, edx
0x18000e91a  test    ecx, ecx
0x18000e91c  jz      short loc_18000E945
0x18000e91e  mov     eax, ecx
0x18000e920  mov     edx, 0FFFEh
0x18000e925  add     rax, rax
0x18000e928  cmp     rax, rdx
0x18000e92b  mov     rax, [rbp+47h+arg_8]
0x18000e92f  jbe     short loc_18000E93C
0x18000e931  mov     word ptr [rbp+47h+var_60+8], dx
0x18000e935  mov     edx, 1
0x18000e93a  jmp     short loc_18000E959
0x18000e93c  add     cx, cx
0x18000e93f  mov     word ptr [rbp+47h+var_60+8], cx
0x18000e943  jmp     short loc_18000E935
0x18000e945  mov     edx, 1
0x18000e94a  lea     rcx, Format
0x18000e951  mov     word ptr [rbp+47h+var_60+8], dx
0x18000e955  mov     qword ptr [rbp+47h+var_60], rcx
0x18000e959  movaps  xmm0, [rbp+47h+var_60]
0x18000e95d  xorps   xmm1, xmm1
0x18000e960  movdqa  [rbp+47h+var_50], xmm0
0x18000e965  movups  [rbp+47h+var_60], xmm1
0x18000e969  mov     qword ptr [rbp+47h+var_60], rdi
0x18000e96d  cmp     r8d, 0FFFFFFFFh
0x18000e971  jnz     short loc_18000E97E
0x18000e973  inc     r13
0x18000e976  cmp     [rdi+r13], r11b
0x18000e97a  jnz     short loc_18000E973
0x18000e97c  jmp     short loc_18000E981
0x18000e97e  mov     r13d, r8d
0x18000e981  test    r13d, r13d
0x18000e984  jz      short loc_18000E99D
0x18000e986  mov     ecx, 0FFFFh
0x18000e98b  cmp     r13d, ecx
0x18000e98e  jbe     short loc_18000E996
0x18000e990  mov     word ptr [rbp+47h+var_60+8], cx
0x18000e994  jmp     short loc_18000E9AC
0x18000e996  mov     word ptr [rbp+47h+var_60+8], r13w
0x18000e99b  jmp     short loc_18000E9AC
0x18000e99d  lea     rcx, qword_18001AD20
0x18000e9a4  mov     word ptr [rbp+47h+var_60+8], dx
0x18000e9a8  mov     qword ptr [rbp+47h+var_60], rcx
0x18000e9ac  movaps  xmm0, [rbp+47h+var_60]
0x18000e9b0  lea     rcx, [rbp+47h+var_50]
0x18000e9b4  mov     [rsp+0D0h+var_68], r12d
0x18000e9b9  lea     r8, WPP_0858b138ff673a747303b7a775217598_Traceguids
0x18000e9c0  mov     [rsp+0D0h+var_70], r15d
0x18000e9c5  mov     edx, 0Eh
0x18000e9ca  mov     [rsp+0D0h+var_78], ebx
0x18000e9ce  mov     [rsp+0D0h+var_80], rcx
0x18000e9d3  lea     rcx, [rbp+47h+var_60]
0x18000e9d7  mov     [rsp+0D0h+var_88], rcx
0x18000e9dc  mov     [rsp+0D0h+var_90], rdi
0x18000e9e1  mov     dword ptr [rsp+0D0h+lpUsedDefaultChar], esi
0x18000e9e5  mov     dword ptr [rsp+0D0h+lpDefaultChar], r10d
0x18000e9ea  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x18000e9ef  mov     [rsp+0D0h+lpMultiByteStr], r14
0x18000e9f4  movdqa  [rbp+47h+var_60], xmm0
0x18000e9f9  call    WPP_SF_Dqqddq_COUNTEDSTRING__COUNTEDSTRINGW_ddd
0x18000e9fe  mov     ecx, 0Dh
0x18000ea03  jmp     short loc_18000EA0A
0x18000ea05  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ea0a  call    cs:__imp_SetLastError
0x18000ea10  xor     eax, eax
0x18000ea12  add     rsp, 98h
0x18000ea19  pop     r15
0x18000ea1b  pop     r14
0x18000ea1d  pop     r13
0x18000ea1f  pop     r12
0x18000ea21  pop     rdi
0x18000ea22  pop     rsi
0x18000ea23  pop     rbx
0x18000ea24  pop     rbp
0x18000ea25  retn
```
