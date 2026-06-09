# Dns_StringCopyU

- ea: `0x1800135ec`
- end: `0x18001393e`
- name: `Dns_StringCopyU`
- size: `850`
- prototype: `__int64 __fastcall(_WORD *, unsigned int *, const CHAR *, int, int, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e680`
- `0x180013544`
- `0x18001399c`

## callees

- `0x180013538`
- `0x1800135ec`
- `0x180013944`
- `0x18001399c`
- `0x180013f19`
- `0x180015d00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001378c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001378c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180013705`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180013705`

## pseudocode

```c
__int64 __fastcall Dns_StringCopyU(_WORD *a1, unsigned int *a2, const CHAR *a3, int a4, int a5, int a6)
{
  __int64 v7; // rbx
  __int64 v9; // r14
  unsigned int BufferLengthForStringCopy_New; // r13d
  unsigned int *v11; // r8
  unsigned int v12; // eax
  size_t v13; // r8
  unsigned int v14; // esi
  __int64 result; // rax
  UINT v16; // ecx
  unsigned int v17; // eax
  __int64 v18; // rcx
  UINT v19; // ecx
  unsigned int v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // r9d
  __int64 v23; // rcx
  int v24; // edx
  __int128 v25; // [rsp+70h] [rbp-19h] BYREF
  __int128 v26[5]; // [rsp+80h] [rbp-9h] BYREF

  LODWORD(v7) = a4;
  if ( !a3 )
    return 0;
  v9 = -1;
  if ( !a4 )
  {
    v7 = -1;
    if ( a5 == 1 )
    {
      do
        ++v7;
      while ( *(_WORD *)&a3[2 * v7] );
    }
    else
    {
      do
        ++v7;
      while ( a3[v7] );
    }
  }
  if ( !a2 )
    return 0;
  BufferLengthForStringCopy_New = Dns_GetBufferLengthForStringCopy_New(a3, v7);
  if ( BufferLengthForStringCopy_New )
  {
    v11 = a2;
    v12 = *a2;
    *a2 = BufferLengthForStringCopy_New;
    if ( BufferLengthForStringCopy_New > v12 )
      return 0;
    if ( a5 == 1 )
    {
      switch ( a6 )
      {
        case 1:
          v13 = (unsigned int)(2 * v7);
          v14 = v13 + 2;
          if ( BufferLengthForStringCopy_New < (int)v13 + 2 )
            return 0;
          a1[(unsigned int)v7] = 0;
          memcpy_0(a1, a3, v13);
          return v14;
        case 2:
          v16 = 65001;
          break;
        case 3:
          v16 = 0;
          break;
        default:
          goto LABEL_39;
      }
      v17 = WideCharToMultiByte(v16, 0, (LPCWCH)a3, v7, (LPSTR)a1, BufferLengthForStringCopy_New - 1, 0, 0);
      if ( v17 || !(_DWORD)v7 )
      {
        v18 = v17;
        result = v17 + 1;
        *((_BYTE *)a1 + v18) = 0;
        return result;
      }
    }
    else
    {
      if ( a6 == a5 )
      {
        v14 = v7 + 1;
        if ( (int)v7 + 1 > BufferLengthForStringCopy_New )
          return 0;
        memcpy_0(a1, a3, (unsigned int)v7);
        *((_BYTE *)a1 + (unsigned int)v7) = 0;
        return v14;
      }
      if ( a6 == 1 )
      {
        if ( a5 == 2 )
        {
          v19 = 65001;
        }
        else
        {
          if ( a5 != 3 )
            goto LABEL_39;
          v19 = 0;
        }
        v20 = MultiByteToWideChar(v19, 8u, a3, v7, a1, (BufferLengthForStringCopy_New >> 1) - 1);
        if ( v20 || !(_DWORD)v7 )
        {
          v21 = v20;
          result = 2 * v20 + 2;
          a1[v21] = 0;
          return result;
        }
      }
      else
      {
        if ( a5 == 2 )
        {
          if ( a6 != 3 )
            goto LABEL_39;
          result = Dns_Utf8ToOrFromAnsi_New(a1, 2, 3);
        }
        else
        {
          if ( a5 != 3 || a6 != 2 )
          {
LABEL_39:
            if ( SBYTE3(xmmword_18001F260) < 0 )
            {
              v22 = *v11;
              LODWORD(v23) = v7;
              v24 = 0;
              if ( a5 != 1 )
              {
                LODWORD(v23) = 0;
                v24 = v7;
              }
              v25 = (unsigned __int64)a3;
              if ( (_DWORD)v23 == -1 )
              {
                v23 = -1;
                do
                  ++v23;
                while ( *(_WORD *)&a3[2 * v23] );
              }
              if ( (_DWORD)v23 )
              {
                if ( 2 * (unsigned __int64)(unsigned int)v23 <= 0xFFFE )
                {
                  LOWORD(v23) = 2 * v23;
                  WORD4(v25) = v23;
                }
                else
                {
                  WORD4(v25) = -2;
                }
              }
              else
              {
                WORD4(v25) = 1;
                *(_QWORD *)&v25 = &Format;
              }
              v26[0] = v25;
              v25 = (unsigned __int64)a3;
              if ( v24 == -1 )
              {
                do
                  ++v9;
                while ( a3[v9] );
              }
              else
              {
                LODWORD(v9) = v24;
              }
              if ( (_DWORD)v9 )
              {
                if ( (unsigned int)v9 <= 0xFFFF )
                  WORD4(v25) = v9;
                else
                  WORD4(v25) = -1;
              }
              else
              {
                WORD4(v25) = 1;
                *(_QWORD *)&v25 = &qword_18001AD20;
              }
              WPP_SF_Dqqddq_COUNTEDSTRING__COUNTEDSTRINGW_ddd(
                v23,
                11,
                (unsigned int)WPP_d97a7e548edc37ae44a2f94ff682ae66_Traceguids,
                87,
                (__int64)a1,
                (__int64)v11,
                v22,
                BufferLengthForStringCopy_New,
                (__int64)a3,
                (__int64)&v25,
                (__int64)v26,
                v7,
                a5,
                a6);
            }
            return 0;
          }
          result = Dns_AnsiToUtf8_New(a3, (unsigned int)v7, a1, BufferLengthForStringCopy_New);
        }
        if ( (_DWORD)result )
          return result;
      }
    }
    v11 = a2;
    goto LABEL_39;
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800135ec  mov     [rsp-8+arg_8], rdx
0x1800135f1  push    rbp
0x1800135f2  push    rbx
0x1800135f3  push    rsi
0x1800135f4  push    rdi
0x1800135f5  push    r12
0x1800135f7  push    r13
0x1800135f9  push    r14
0x1800135fb  push    r15
0x1800135fd  lea     rbp, [rsp-0Fh]
0x180013602  sub     rsp, 98h
0x180013609  mov     r15, rcx
0x18001360c  mov     ebx, r9d
0x18001360f  xor     ecx, ecx
0x180013611  mov     rdi, r8
0x180013614  mov     rax, rdx
0x180013617  test    r8, r8
0x18001361a  jz      loc_180013928
0x180013620  mov     esi, [rbp+47h+arg_20]
0x180013623  or      r14, 0FFFFFFFFFFFFFFFFh
0x180013627  test    ebx, ebx
0x180013629  jnz     short loc_180013648
0x18001362b  mov     rbx, r14
0x18001362e  cmp     esi, 1
0x180013631  jnz     short loc_18001363F
0x180013633  inc     rbx
0x180013636  cmp     [r8+rbx*2], cx
0x18001363b  jnz     short loc_180013633
0x18001363d  jmp     short loc_180013648
0x18001363f  inc     rbx
0x180013642  cmp     [r8+rbx], cl
0x180013646  jnz     short loc_18001363F
0x180013648  test    rax, rax
0x18001364b  jz      loc_180013928
0x180013651  mov     r12d, [rbp+47h+arg_28]
0x180013655  mov     r8d, esi
0x180013658  mov     r9d, r12d
0x18001365b  mov     edx, ebx
0x18001365d  mov     rcx, rdi
0x180013660  call    Dns_GetBufferLengthForStringCopy_New
0x180013665  xor     r10d, r10d
0x180013668  mov     r13d, eax
0x18001366b  test    eax, eax
0x18001366d  jnz     short loc_18001367B
0x18001366f  mov     rax, [rbp+47h+arg_8]
0x180013673  mov     [rax], r10d
0x180013676  jmp     loc_180013928
0x18001367b  mov     r8, [rbp+47h+arg_8]
0x18001367f  mov     eax, [r8]
0x180013682  mov     [r8], r13d
0x180013685  cmp     r13d, eax
0x180013688  ja      loc_180013928
0x18001368e  mov     r11d, 1
0x180013694  cmp     esi, r11d
0x180013697  jnz     loc_180013727
0x18001369d  cmp     r12d, r11d
0x1800136a0  jnz     short loc_1800136CC
0x1800136a2  lea     r8d, [rbx+rbx]; Size
0x1800136a6  lea     esi, [r8+2]
0x1800136aa  cmp     r13d, esi
0x1800136ad  jb      loc_180013928
0x1800136b3  mov     edx, ebx
0x1800136b5  mov     rcx, r15; void *
0x1800136b8  mov     [r15+rdx*2], r10w
0x1800136bd  mov     rdx, rdi; Src
0x1800136c0  call    memcpy_0
0x1800136c5  mov     eax, esi
0x1800136c7  jmp     loc_18001392A
0x1800136cc  cmp     r12d, 2
0x1800136d0  jnz     short loc_1800136D9
0x1800136d2  mov     ecx, 0FDE9h
0x1800136d7  jmp     short loc_1800136E6
0x1800136d9  cmp     r12d, 3
0x1800136dd  jnz     loc_1800137EE
0x1800136e3  mov     ecx, r10d; CodePage
0x1800136e6  mov     [rsp+0D0h+lpUsedDefaultChar], r10; lpUsedDefaultChar
0x1800136eb  lea     eax, [r13-1]
0x1800136ef  mov     [rsp+0D0h+lpDefaultChar], r10; lpDefaultChar
0x1800136f4  mov     r9d, ebx; cchWideChar
0x1800136f7  mov     [rsp+0D0h+cbMultiByte], eax; cbMultiByte
0x1800136fb  mov     r8, rdi; lpWideCharStr
0x1800136fe  xor     edx, edx; dwFlags
0x180013700  mov     [rsp+0D0h+lpMultiByteStr], r15; lpMultiByteStr
0x180013705  call    cs:__imp_WideCharToMultiByte
0x18001370b  xor     r10d, r10d
0x18001370e  test    eax, eax
0x180013710  jnz     short loc_18001371A
0x180013712  test    ebx, ebx
0x180013714  jnz     loc_1800137E4
0x18001371a  mov     ecx, eax
0x18001371c  inc     eax
0x18001371e  mov     [rcx+r15], r10b
0x180013722  jmp     loc_18001392A
0x180013727  cmp     r12d, esi
0x18001372a  jnz     short loc_180013753
0x18001372c  lea     esi, [rbx+1]
0x18001372f  cmp     esi, r13d
0x180013732  ja      loc_180013928
0x180013738  mov     ebx, ebx
0x18001373a  mov     rdx, rdi; Src
0x18001373d  mov     r8d, ebx; Size
0x180013740  mov     rcx, r15; void *
0x180013743  call    memcpy_0
0x180013748  xor     ecx, ecx
0x18001374a  mov     [rbx+r15], cl
0x18001374e  jmp     loc_1800136C5
0x180013753  cmp     r12d, r11d
0x180013756  jnz     short loc_1800137B0
0x180013758  cmp     esi, 2
0x18001375b  jnz     short loc_180013764
0x18001375d  mov     ecx, 0FDE9h
0x180013762  jmp     short loc_180013770
0x180013764  cmp     esi, 3
0x180013767  jnz     loc_1800137EE
0x18001376d  mov     ecx, r10d; CodePage
0x180013770  mov     eax, r13d
0x180013773  mov     r9d, ebx; cbMultiByte
0x180013776  shr     eax, 1
0x180013778  mov     r8, rdi; lpMultiByteStr
0x18001377b  sub     eax, r11d
0x18001377e  mov     edx, 8; dwFlags
0x180013783  mov     [rsp+0D0h+cbMultiByte], eax; cchWideChar
0x180013787  mov     [rsp+0D0h+lpMultiByteStr], r15; lpWideCharStr
0x18001378c  call    cs:__imp_MultiByteToWideChar
0x180013792  xor     r10d, r10d
0x180013795  test    eax, eax
0x180013797  jnz     short loc_18001379D
0x180013799  test    ebx, ebx
0x18001379b  jnz     short loc_1800137E4
0x18001379d  mov     edx, eax
0x18001379f  lea     eax, ds:2[rax*2]
0x1800137a6  mov     [r15+rdx*2], r10w
0x1800137ab  jmp     loc_18001392A
0x1800137b0  cmp     esi, 2
0x1800137b3  jnz     loc_180013846
0x1800137b9  cmp     r12d, 3
0x1800137bd  jnz     short loc_1800137EE
0x1800137bf  mov     [rsp+0D0h+cbMultiByte], r12d; int
0x1800137c4  mov     r9d, ebx
0x1800137c7  mov     r8, rdi
0x1800137ca  mov     dword ptr [rsp+0D0h+lpMultiByteStr], esi; int
0x1800137ce  mov     edx, r13d
0x1800137d1  mov     rcx, r15; void *
0x1800137d4  call    Dns_Utf8ToOrFromAnsi_New
0x1800137d9  xor     r10d, r10d
0x1800137dc  test    eax, eax
0x1800137de  jnz     loc_18001392A
0x1800137e4  mov     r8, [rbp+47h+arg_8]
0x1800137e8  mov     r11d, 1
0x1800137ee  cmp     byte ptr cs:xmmword_18001F260+3, r10b
0x1800137f5  jge     loc_180013928
0x1800137fb  mov     r9d, [r8]
0x1800137fe  cmp     esi, r11d
0x180013801  mov     ecx, ebx
0x180013803  mov     edx, r10d
0x180013806  cmovnz  ecx, r10d
0x18001380a  xorps   xmm0, xmm0
0x18001380d  cmovnz  edx, ebx
0x180013810  movups  [rbp+47h+var_60], xmm0
0x180013814  mov     qword ptr [rbp+47h+var_60], rdi
0x180013818  cmp     ecx, 0FFFFFFFFh
0x18001381b  jnz     short loc_18001382A
0x18001381d  mov     rcx, r14
0x180013820  inc     rcx
0x180013823  cmp     [rdi+rcx*2], r10w
0x180013828  jnz     short loc_180013820
0x18001382a  test    ecx, ecx
0x18001382c  jz      short loc_18001386F
0x18001382e  mov     eax, ecx
0x180013830  add     rax, rax
0x180013833  cmp     rax, 0FFFEh
0x180013839  jbe     short loc_180013866
0x18001383b  mov     eax, 0FFFEh
0x180013840  mov     word ptr [rbp+47h+var_60+8], ax
0x180013844  jmp     short loc_18001387F
0x180013846  cmp     esi, 3
0x180013849  jnz     short loc_1800137EE
0x18001384b  cmp     r12d, 2
0x18001384f  jnz     short loc_1800137EE
0x180013851  mov     r9d, r13d
0x180013854  mov     r8, r15
0x180013857  mov     edx, ebx
0x180013859  mov     rcx, rdi
0x18001385c  call    Dns_AnsiToUtf8_New
0x180013861  jmp     loc_1800137D9
0x180013866  add     cx, cx
0x180013869  mov     word ptr [rbp+47h+var_60+8], cx
0x18001386d  jmp     short loc_18001387F
0x18001386f  lea     rax, Format
0x180013876  mov     word ptr [rbp+47h+var_60+8], r11w
0x18001387b  mov     qword ptr [rbp+47h+var_60], rax
0x18001387f  movaps  xmm0, [rbp+47h+var_60]
0x180013883  xorps   xmm1, xmm1
0x180013886  movdqa  [rbp+47h+var_50], xmm0
0x18001388b  movups  [rbp+47h+var_60], xmm1
0x18001388f  mov     qword ptr [rbp+47h+var_60], rdi
0x180013893  cmp     edx, 0FFFFFFFFh
0x180013896  jnz     short loc_1800138A3
0x180013898  inc     r14
0x18001389b  cmp     [rdi+r14], r10b
0x18001389f  jnz     short loc_180013898
0x1800138a1  jmp     short loc_1800138A6
0x1800138a3  mov     r14d, edx
0x1800138a6  test    r14d, r14d
0x1800138a9  jz      short loc_1800138C2
0x1800138ab  mov     eax, 0FFFFh
0x1800138b0  cmp     r14d, eax
0x1800138b3  jbe     short loc_1800138BB
0x1800138b5  mov     word ptr [rbp+47h+var_60+8], ax
0x1800138b9  jmp     short loc_1800138D2
0x1800138bb  mov     word ptr [rbp+47h+var_60+8], r14w
0x1800138c0  jmp     short loc_1800138D2
0x1800138c2  lea     rax, qword_18001AD20
0x1800138c9  mov     word ptr [rbp+47h+var_60+8], r11w
0x1800138ce  mov     qword ptr [rbp+47h+var_60], rax
0x1800138d2  movaps  xmm0, [rbp+47h+var_60]
0x1800138d6  lea     rax, [rbp+47h+var_50]
0x1800138da  mov     [rsp+0D0h+var_68], r12d
0x1800138df  mov     edx, 0Bh
0x1800138e4  mov     [rsp+0D0h+var_70], esi
0x1800138e8  mov     [rsp+0D0h+var_78], ebx
0x1800138ec  mov     [rsp+0D0h+var_80], rax
0x1800138f1  lea     rax, [rbp+47h+var_60]
0x1800138f5  mov     [rsp+0D0h+var_88], rax
0x1800138fa  mov     [rsp+0D0h+var_90], rdi
0x1800138ff  mov     dword ptr [rsp+0D0h+lpUsedDefaultChar], r13d
0x180013904  mov     dword ptr [rsp+0D0h+lpDefaultChar], r9d
0x180013909  lea     r9d, [rdx+4Ch]
0x18001390d  mov     qword ptr [rsp+0D0h+cbMultiByte], r8
0x180013912  lea     r8, WPP_d97a7e548edc37ae44a2f94ff682ae66_Traceguids
0x180013919  movdqa  [rbp+47h+var_60], xmm0
0x18001391e  mov     [rsp+0D0h+lpMultiByteStr], r15
0x180013923  call    WPP_SF_Dqqddq_COUNTEDSTRING__COUNTEDSTRINGW_ddd
0x180013928  xor     eax, eax
0x18001392a  add     rsp, 98h
0x180013931  pop     r15
0x180013933  pop     r14
0x180013935  pop     r13
0x180013937  pop     r12
0x180013939  pop     rdi
0x18001393a  pop     rsi
0x18001393b  pop     rbx
0x18001393c  pop     rbp
0x18001393d  retn
```
