# Dns_GetBufferLengthForStringCopyU

- ea: `0x180013344`
- end: `0x18001352f`
- name: `Dns_GetBufferLengthForStringCopyU`
- size: `491`
- prototype: `__int64 __fastcall(const WCHAR *lpMultiByteStr, int cbMultiByte, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e470`
- `0x180013538`

## callees

- `0x180013344`
- `0x180013944`
- `0x18001399c`
- `0x180015f14`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013430`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013430`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800133cd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800133cd`

## pseudocode

```c
__int64 __fastcall Dns_GetBufferLengthForStringCopyU(const WCHAR *lpMultiByteStr, int cbMultiByte, int a3, int a4)
{
  __int64 v4; // rbx
  __int64 v6; // rdi
  UINT v8; // ecx
  int v9; // eax
  UINT v10; // ecx
  int v11; // eax
  __int128 v12; // [rsp+40h] [rbp-48h] BYREF

  LODWORD(v4) = cbMultiByte;
  if ( lpMultiByteStr )
  {
    v6 = -1;
    if ( a3 == 1 )
    {
      if ( !cbMultiByte )
      {
        v4 = -1;
        do
          ++v4;
        while ( lpMultiByteStr[v4] );
      }
      switch ( a4 )
      {
        case 1:
          return (unsigned int)(2 * v4 + 2);
        case 2:
          v8 = 65001;
LABEL_12:
          v9 = WideCharToMultiByte(v8, 0, lpMultiByteStr, v4, 0, 0, 0, 0);
          if ( v9 || !(_DWORD)v4 )
            return (unsigned int)(v9 + 1);
          break;
        case 3:
          v8 = 0;
          goto LABEL_12;
      }
LABEL_34:
      if ( SBYTE3(xmmword_18001F260) < 0 )
      {
        v12 = (unsigned __int64)lpMultiByteStr;
        if ( (_DWORD)v4 == -1 )
        {
          do
            ++v6;
          while ( *((_BYTE *)lpMultiByteStr + v6) );
        }
        else
        {
          LODWORD(v6) = v4;
        }
        if ( (_DWORD)v6 )
        {
          if ( (unsigned int)v6 <= 0xFFFF )
            WORD4(v12) = v6;
          else
            WORD4(v12) = -1;
        }
        else
        {
          WORD4(v12) = 1;
          *(_QWORD *)&v12 = &qword_18001AD20;
        }
        WPP_SF_q_COUNTEDSTRING_ddd(
          (_DWORD)lpMultiByteStr,
          10,
          (unsigned int)WPP_d97a7e548edc37ae44a2f94ff682ae66_Traceguids,
          (_DWORD)lpMultiByteStr,
          (__int64)&v12);
      }
      return 0;
    }
    if ( !cbMultiByte )
    {
      v4 = -1;
      do
        ++v4;
      while ( *((_BYTE *)lpMultiByteStr + v4) );
    }
    if ( a4 == a3 )
      return (unsigned int)(v4 + 1);
    if ( a4 != 1 )
    {
      if ( a3 == 2 )
      {
        if ( a4 == 3 )
          return Dns_Utf8ToOrFromAnsi_New(0, 2, 3);
      }
      else if ( a3 == 3 && a4 == 2 )
      {
        return Dns_AnsiToUtf8_New(lpMultiByteStr, (unsigned int)v4, 0, 0);
      }
      goto LABEL_34;
    }
    if ( a3 == 2 )
    {
      v10 = 65001;
    }
    else
    {
      if ( a3 != 3 )
        goto LABEL_34;
      v10 = 0;
    }
    v11 = MultiByteToWideChar(v10, 0, (LPCCH)lpMultiByteStr, v4, 0, 0);
    if ( v11 || !(_DWORD)v4 )
      return (unsigned int)(2 * v11 + 2);
    goto LABEL_34;
  }
  return 0;
}

```

## disassembly

```asm
0x180013344  push    rbx
0x180013346  push    rbp
0x180013347  push    rsi
0x180013348  push    rdi
0x180013349  push    r12
0x18001334b  push    r14
0x18001334d  push    r15
0x18001334f  sub     rsp, 50h
0x180013353  xor     r15d, r15d
0x180013356  mov     esi, r9d
0x180013359  mov     r14d, r8d
0x18001335c  mov     ebx, edx
0x18001335e  mov     rbp, rcx
0x180013361  test    rcx, rcx
0x180013364  jz      loc_18001351E
0x18001336a  lea     r12d, [r15+1]
0x18001336e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013372  cmp     r8d, r12d
0x180013375  jnz     short loc_1800133E6
0x180013377  test    edx, edx
0x180013379  jnz     short loc_180013388
0x18001337b  mov     rbx, rdi
0x18001337e  inc     rbx
0x180013381  cmp     [rcx+rbx*2], r15w
0x180013386  jnz     short loc_18001337E
0x180013388  cmp     esi, r12d
0x18001338b  jnz     short loc_180013399
0x18001338d  lea     eax, ds:2[rbx*2]
0x180013394  jmp     loc_180013520
0x180013399  cmp     esi, 2
0x18001339c  jnz     short loc_1800133A5
0x18001339e  mov     ecx, 0FDE9h
0x1800133a3  jmp     short loc_1800133B1
0x1800133a5  cmp     esi, 3
0x1800133a8  jnz     loc_18001348F
0x1800133ae  mov     ecx, r15d; CodePage
0x1800133b1  mov     [rsp+88h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800133b6  mov     r9d, ebx; cchWideChar
0x1800133b9  mov     [rsp+88h+lpDefaultChar], r15; lpDefaultChar
0x1800133be  mov     r8, rbp; lpWideCharStr
0x1800133c1  mov     [rsp+88h+cbMultiByte], r15d; cbMultiByte
0x1800133c6  xor     edx, edx; dwFlags
0x1800133c8  mov     [rsp+88h+lpMultiByteStr], r15; lpMultiByteStr
0x1800133cd  call    cs:__imp_WideCharToMultiByte
0x1800133d3  test    eax, eax
0x1800133d5  jnz     short loc_1800133DF
0x1800133d7  test    ebx, ebx
0x1800133d9  jnz     loc_18001348F
0x1800133df  inc     eax
0x1800133e1  jmp     loc_180013520
0x1800133e6  test    edx, edx
0x1800133e8  jnz     short loc_1800133F6
0x1800133ea  mov     rbx, rdi
0x1800133ed  inc     rbx
0x1800133f0  cmp     [rbx+rcx], r15b
0x1800133f4  jnz     short loc_1800133ED
0x1800133f6  cmp     esi, r14d
0x1800133f9  jnz     short loc_180013403
0x1800133fb  lea     eax, [rbx+1]
0x1800133fe  jmp     loc_180013520
0x180013403  cmp     esi, r12d
0x180013406  jnz     short loc_18001344A
0x180013408  cmp     r14d, 2
0x18001340c  jnz     short loc_180013415
0x18001340e  mov     ecx, 0FDE9h
0x180013413  jmp     short loc_18001341E
0x180013415  cmp     r14d, 3
0x180013419  jnz     short loc_18001348F
0x18001341b  mov     ecx, r15d; CodePage
0x18001341e  mov     [rsp+88h+cbMultiByte], r15d; cchWideChar
0x180013423  mov     r9d, ebx; cbMultiByte
0x180013426  mov     r8, rbp; lpMultiByteStr
0x180013429  mov     [rsp+88h+lpMultiByteStr], r15; lpWideCharStr
0x18001342e  xor     edx, edx; dwFlags
0x180013430  call    cs:__imp_MultiByteToWideChar
0x180013436  test    eax, eax
0x180013438  jnz     short loc_18001343E
0x18001343a  test    ebx, ebx
0x18001343c  jnz     short loc_18001348F
0x18001343e  lea     eax, ds:2[rax*2]
0x180013445  jmp     loc_180013520
0x18001344a  cmp     r14d, 2
0x18001344e  jnz     short loc_180013472
0x180013450  cmp     esi, 3
0x180013453  jnz     short loc_18001348F
0x180013455  mov     [rsp+88h+cbMultiByte], esi; int
0x180013459  mov     r9d, ebx
0x18001345c  mov     r8, rbp
0x18001345f  mov     dword ptr [rsp+88h+lpMultiByteStr], r14d; int
0x180013464  xor     edx, edx
0x180013466  xor     ecx, ecx; void *
0x180013468  call    Dns_Utf8ToOrFromAnsi_New
0x18001346d  jmp     loc_180013520
0x180013472  cmp     r14d, 3
0x180013476  jnz     short loc_18001348F
0x180013478  cmp     esi, 2
0x18001347b  jnz     short loc_18001348F
0x18001347d  xor     r9d, r9d
0x180013480  xor     r8d, r8d
0x180013483  mov     edx, ebx
0x180013485  call    Dns_AnsiToUtf8_New
0x18001348a  jmp     loc_180013520
0x18001348f  cmp     byte ptr cs:xmmword_18001F260+3, r15b
0x180013496  jge     loc_18001351E
0x18001349c  xorps   xmm0, xmm0
0x18001349f  movups  [rsp+88h+var_48], xmm0
0x1800134a4  mov     qword ptr [rsp+88h+var_48], rbp
0x1800134a9  cmp     ebx, 0FFFFFFFFh
0x1800134ac  jnz     short loc_1800134B9
0x1800134ae  inc     rdi
0x1800134b1  cmp     [rdi+rbp], r15b
0x1800134b5  jnz     short loc_1800134AE
0x1800134b7  jmp     short loc_1800134BB
0x1800134b9  mov     edi, ebx
0x1800134bb  test    edi, edi
0x1800134bd  jz      short loc_1800134D6
0x1800134bf  mov     eax, 0FFFFh
0x1800134c4  cmp     edi, eax
0x1800134c6  jbe     short loc_1800134CF
0x1800134c8  mov     word ptr [rsp+88h+var_48+8], ax
0x1800134cd  jmp     short loc_1800134E8
0x1800134cf  mov     word ptr [rsp+88h+var_48+8], di
0x1800134d4  jmp     short loc_1800134E8
0x1800134d6  lea     rax, qword_18001AD20
0x1800134dd  mov     word ptr [rsp+88h+var_48+8], r12w
0x1800134e3  mov     qword ptr [rsp+88h+var_48], rax
0x1800134e8  movaps  xmm0, [rsp+88h+var_48]
0x1800134ed  lea     rax, [rsp+88h+var_48]
0x1800134f2  mov     dword ptr [rsp+88h+lpUsedDefaultChar], esi
0x1800134f6  lea     r8, WPP_d97a7e548edc37ae44a2f94ff682ae66_Traceguids
0x1800134fd  mov     dword ptr [rsp+88h+lpDefaultChar], r14d
0x180013502  mov     edx, 0Ah
0x180013507  mov     [rsp+88h+cbMultiByte], ebx
0x18001350b  mov     r9, rbp
0x18001350e  mov     [rsp+88h+lpMultiByteStr], rax
0x180013513  movdqa  [rsp+88h+var_48], xmm0
0x180013519  call    WPP_SF_q_COUNTEDSTRING_ddd
0x18001351e  xor     eax, eax
0x180013520  add     rsp, 50h
0x180013524  pop     r15
0x180013526  pop     r14
0x180013528  pop     r12
0x18001352a  pop     rdi
0x18001352b  pop     rsi
0x18001352c  pop     rbp
0x18001352d  pop     rbx
0x18001352e  retn
```
