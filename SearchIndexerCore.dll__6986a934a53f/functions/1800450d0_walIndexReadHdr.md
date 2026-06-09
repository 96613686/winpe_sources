# walIndexReadHdr

- ea: `0x1800450d0`
- end: `0x18004542b`
- name: `walIndexReadHdr`
- size: `859`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180044d28`
- `0x18006b56c`

## callees

- `0x1800257e0`
- `0x1800333bc`
- `0x1800450d0`
- `0x180045440`
- `0x1800454c0`
- `0x180045750`
- `0x180045bb0`
- `0x180046058`
- `0x18004643c`
- `0x1800464a4`
- `0x180047294`
- `0x180047dd0`
- `0x180058a94`
- `0x1800789c0`
- `0x1800af614`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800453ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800453ad`

## string_xrefs

- `0x1800452e7`: `cannot open file`

## pseudocode

```c
__int64 __fastcall walIndexReadHdr(__int64 a1, _DWORD *a2)
{
  unsigned int v4; // esi
  bool v5; // zf
  __m128i **v6; // rax
  __m128i *v7; // rdi
  __m128i v8; // xmm6
  __m128i v9; // xmm0
  __m128i v10; // xmm1
  __m128i v11; // xmm1
  __m128i v12; // xmm0
  int v13; // edi
  __m128i v14; // xmm0
  __m128i v15; // xmm1
  __m128i v16; // xmm0
  __int64 result; // rax
  char v18; // r15
  int v19; // eax
  __int64 v20; // [rsp+30h] [rbp-59h] BYREF
  __int64 v21; // [rsp+38h] [rbp-51h] BYREF
  _OWORD Buf2[3]; // [rsp+40h] [rbp-49h] BYREF
  __m128i Buf1; // [rsp+70h] [rbp-19h] BYREF
  __m128i v24; // [rsp+80h] [rbp-9h]
  __m128i v25; // [rsp+90h] [rbp+7h]

  v20 = 0;
  if ( qword_1800D0A00 )
  {
    v19 = qword_1800D0A00(650);
    if ( v19 )
    {
      v24.m128i_i64[0] = v19;
      Buf1 = 0u;
      RaiseException(0xC0000006, 0, 3u, (const ULONG_PTR *)&Buf1);
    }
  }
  if ( *(int *)(a1 + 40) > 0 && (v20 = **(_QWORD **)(a1 + 48)) != 0 )
  {
    v4 = 0;
  }
  else
  {
    result = walIndexPageRealloc(a1, 0, &v20);
    v4 = result;
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result != 1288 )
        return result;
      *(_BYTE *)(a1 + 70) = 1;
      *(_BYTE *)(a1 + 63) = 2;
      *a2 = 1;
    }
  }
  if ( !v20 )
  {
    v13 = 1;
    goto LABEL_25;
  }
  sehInjectFault();
  v5 = *(_BYTE *)(a1 + 63) == 2;
  v6 = *(__m128i ***)(a1 + 48);
  v7 = *v6;
  v8 = **v6;
  v9 = (*v6)[1];
  v10 = (*v6)[2];
  Buf1 = v8;
  v24 = v9;
  v25 = v10;
  if ( !v5 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 120LL))(*(_QWORD *)(a1 + 8));
  v11 = v7[4];
  Buf2[0] = v7[3];
  v12 = v7[5];
  Buf2[1] = v11;
  Buf2[2] = v12;
  if ( !memcmp_0(&Buf1, Buf2, 0x30u)
    && (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v8, 12))
    && (walChecksumBytes(1, (unsigned int)&Buf1, 40, 0, (__int64)&v21), v21 == v25.m128i_i64[1]) )
  {
    if ( memcmp_0((const void *)(a1 + 72), &Buf1, 0x30u) )
    {
      v14 = Buf1;
      *a2 = 1;
      v15 = v24;
      *(__m128i *)(a1 + 72) = v14;
      v16 = v25;
      *(__m128i *)(a1 + 88) = v15;
      *(__m128i *)(a1 + 104) = v16;
      *(_DWORD *)(a1 + 56) = (*(_WORD *)(a1 + 86) & 0xFE00) + ((*(_WORD *)(a1 + 86) & 1) << 16);
    }
    v13 = 0;
  }
  else
  {
    v13 = 1;
  }
  if ( v13 )
  {
LABEL_25:
    if ( *(_BYTE *)(a1 + 70) || (*(_BYTE *)(a1 + 66) & 2) == 0 )
    {
      v18 = *(_BYTE *)(a1 + 64);
      if ( v18 || (v4 = walLockExclusive(a1, 0, 1)) == 0 )
      {
        *(_BYTE *)(a1 + 64) = 1;
        v4 = walIndexPage(a1, 0, &v20);
        if ( !v4 )
        {
          v13 = walIndexTryHdr(a1, a2);
          if ( v13 )
          {
            v4 = walIndexRecover(a1);
            *a2 = 1;
          }
        }
        if ( !v18 )
        {
          *(_BYTE *)(a1 + 64) = 0;
          walUnlockExclusive(a1, 0, 1);
        }
      }
    }
    else
    {
      v4 = walLockShared(a1, 0);
      if ( !v4 )
      {
        walUnlockShared(a1, 0);
        v4 = 264;
      }
    }
    if ( v13 )
      goto LABEL_18;
  }
  if ( *(_DWORD *)(a1 + 72) != 3007000 )
  {
    v4 = 14;
    sqlite3_log(
      14,
      "%s at line %d of [%.10s]",
      "cannot open file",
      67866,
      "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
  }
LABEL_18:
  if ( *(_BYTE *)(a1 + 70) )
  {
    if ( v4 )
    {
      walIndexClose(a1, 0);
      *(_BYTE *)(a1 + 70) = 0;
      if ( v4 == 522 )
        v4 = -1;
    }
    *(_BYTE *)(a1 + 63) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800450d0  push    rbp
0x1800450d2  push    rbx
0x1800450d3  push    r14
0x1800450d5  push    r15
0x1800450d7  lea     rbp, [rsp-3Fh]
0x1800450dc  sub     rsp, 0C8h
0x1800450e3  mov     rax, cs:__security_cookie
0x1800450ea  xor     rax, rsp
0x1800450ed  mov     [rbp+57h+var_40], rax
0x1800450f1  mov     rax, cs:qword_1800D0A00
0x1800450f8  xor     r15d, r15d
0x1800450fb  mov     [rbp+57h+var_B0], r15
0x1800450ff  mov     r14, rdx
0x180045102  mov     rbx, rcx
0x180045105  test    rax, rax
0x180045108  jnz     loc_18004537C
0x18004510e  mov     [rsp+0E0h+arg_10], rsi
0x180045116  cmp     [rbx+28h], r15d
0x18004511a  jle     loc_18004529B
0x180045120  mov     rax, [rbx+30h]
0x180045124  mov     rcx, [rax]
0x180045127  mov     [rbp+57h+var_B0], rcx
0x18004512b  test    rcx, rcx
0x18004512e  jz      loc_18004529B
0x180045134  mov     esi, r15d
0x180045137  mov     [rsp+0E0h+var_20], rdi
0x18004513f  cmp     [rbp+57h+var_B0], r15
0x180045143  jz      loc_1800452FF
0x180045149  movaps  [rsp+0E0h+var_30], xmm6
0x180045151  call    sehInjectFault
0x180045156  cmp     byte ptr [rbx+3Fh], 2
0x18004515a  mov     rax, [rbx+30h]
0x18004515e  mov     rdi, [rax]
0x180045161  movups  xmm6, xmmword ptr [rdi]
0x180045164  movups  xmm0, xmmword ptr [rdi+10h]
0x180045168  movups  xmm1, xmmword ptr [rdi+20h]
0x18004516c  movups  [rbp+57h+Buf1], xmm6
0x180045170  movups  [rbp+57h+var_60], xmm0
0x180045174  movups  [rbp+57h+var_50], xmm1
0x180045178  jz      short loc_18004518A
0x18004517a  mov     rcx, [rbx+8]
0x18004517e  mov     rax, [rcx]
0x180045181  mov     rax, [rax+78h]
0x180045185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004518a  movups  xmm0, xmmword ptr [rdi+30h]
0x18004518e  mov     r8d, 30h ; '0'; Size
0x180045194  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180045198  movups  xmm1, xmmword ptr [rdi+40h]
0x18004519c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800451a0  movups  [rbp+57h+Buf2], xmm0
0x1800451a4  movups  xmm0, xmmword ptr [rdi+50h]
0x1800451a8  movups  [rbp+57h+var_90], xmm1
0x1800451ac  movups  [rbp+57h+var_80], xmm0
0x1800451b0  call    memcmp_0
0x1800451b5  test    eax, eax
0x1800451b7  jnz     short loc_1800451EE
0x1800451b9  psrldq  xmm6, 0Ch
0x1800451be  movd    eax, xmm6
0x1800451c2  test    al, al
0x1800451c4  jz      short loc_1800451EE
0x1800451c6  lea     rax, [rbp+57h+var_A8]
0x1800451ca  xor     r9d, r9d
0x1800451cd  mov     r8d, 28h ; '('
0x1800451d3  mov     [rsp+0E0h+var_C0], rax
0x1800451d8  lea     rdx, [rbp+57h+Buf1]
0x1800451dc  mov     ecx, 1
0x1800451e1  call    walChecksumBytes
0x1800451e6  mov     eax, dword ptr [rbp+57h+var_50+8]
0x1800451e9  cmp     dword ptr [rbp+57h+var_A8], eax
0x1800451ec  jz      short loc_1800451F5
0x1800451ee  mov     edi, 1
0x1800451f3  jmp     short loc_18004524C
0x1800451f5  mov     eax, dword ptr [rbp+57h+var_50+0Ch]
0x1800451f8  cmp     dword ptr [rbp+57h+var_A8+4], eax
0x1800451fb  jnz     short loc_1800451EE
0x1800451fd  mov     r8d, 30h ; '0'; Size
0x180045203  lea     rdx, [rbp+57h+Buf1]; Buf2
0x180045207  lea     rcx, [rbx+48h]; Buf1
0x18004520b  call    memcmp_0
0x180045210  test    eax, eax
0x180045212  jz      short loc_180045249
0x180045214  movups  xmm0, [rbp+57h+Buf1]
0x180045218  mov     dword ptr [r14], 1
0x18004521f  movups  xmm1, [rbp+57h+var_60]
0x180045223  movups  xmmword ptr [rbx+48h], xmm0
0x180045227  movups  xmm0, [rbp+57h+var_50]
0x18004522b  movups  xmmword ptr [rbx+58h], xmm1
0x18004522f  movups  xmmword ptr [rbx+68h], xmm0
0x180045233  movzx   eax, word ptr [rbx+56h]
0x180045237  mov     ecx, eax
0x180045239  and     eax, 0FE00h
0x18004523e  and     ecx, 1
0x180045241  shl     ecx, 10h
0x180045244  add     ecx, eax
0x180045246  mov     [rbx+38h], ecx
0x180045249  mov     edi, r15d
0x18004524c  movaps  xmm6, [rsp+0E0h+var_30]
0x180045254  test    edi, edi
0x180045256  jnz     loc_180045304
0x18004525c  cmp     dword ptr [rbx+48h], 2DE218h
0x180045263  jnz     short loc_1800452CE
0x180045265  cmp     byte ptr [rbx+46h], 0
0x180045269  mov     rdi, [rsp+0E0h+var_20]
0x180045271  jnz     loc_180045402
0x180045277  mov     eax, esi
0x180045279  mov     rsi, [rsp+0E0h+arg_10]
0x180045281  mov     rcx, [rbp+57h+var_40]
0x180045285  xor     rcx, rsp; StackCookie
0x180045288  call    __security_check_cookie
0x18004528d  add     rsp, 0C8h
0x180045294  pop     r15
0x180045296  pop     r14
0x180045298  pop     rbx
0x180045299  pop     rbp
0x18004529a  retn
0x18004529b  lea     r8, [rbp+57h+var_B0]
0x18004529f  xor     edx, edx
0x1800452a1  mov     rcx, rbx
0x1800452a4  call    walIndexPageRealloc
0x1800452a9  mov     esi, eax
0x1800452ab  test    eax, eax
0x1800452ad  jz      loc_180045137
0x1800452b3  cmp     eax, 508h
0x1800452b8  jnz     short loc_180045279
0x1800452ba  mov     byte ptr [rbx+46h], 1
0x1800452be  mov     byte ptr [rbx+3Fh], 2
0x1800452c2  mov     dword ptr [r14], 1
0x1800452c9  jmp     loc_180045137
0x1800452ce  lea     rax, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x1800452d5  mov     esi, 0Eh
0x1800452da  mov     ecx, esi
0x1800452dc  mov     [rsp+0E0h+var_C0], rax
0x1800452e1  mov     r9d, 1091Ah
0x1800452e7  lea     r8, aCannotOpenFile; "cannot open file"
0x1800452ee  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x1800452f5  call    sqlite3_log
0x1800452fa  jmp     loc_180045265
0x1800452ff  mov     edi, 1
0x180045304  cmp     [rbx+46h], r15b
0x180045308  jz      loc_1800453D4
0x18004530e  movzx   r15d, byte ptr [rbx+40h]
0x180045313  test    r15b, r15b
0x180045316  jz      loc_1800453B8
0x18004531c  lea     r8, [rbp+57h+var_B0]
0x180045320  mov     byte ptr [rbx+40h], 1
0x180045324  xor     edx, edx
0x180045326  mov     rcx, rbx
0x180045329  call    walIndexPage
0x18004532e  mov     esi, eax
0x180045330  test    eax, eax
0x180045332  jnz     short loc_180045356
0x180045334  mov     rdx, r14
0x180045337  mov     rcx, rbx
0x18004533a  call    walIndexTryHdr
0x18004533f  mov     edi, eax
0x180045341  test    eax, eax
0x180045343  jz      short loc_180045356
0x180045345  mov     rcx, rbx
0x180045348  call    walIndexRecover
0x18004534d  mov     esi, eax
0x18004534f  mov     dword ptr [r14], 1
0x180045356  test    r15b, r15b
0x180045359  jnz     short loc_18004536F
0x18004535b  xor     edx, edx
0x18004535d  mov     [rbx+40h], r15b
0x180045361  mov     r8d, 1
0x180045367  mov     rcx, rbx
0x18004536a  call    walUnlockExclusive
0x18004536f  test    edi, edi
0x180045371  jnz     loc_180045265
0x180045377  jmp     loc_18004525C
0x18004537c  mov     ecx, 28Ah
0x180045381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045386  test    eax, eax
0x180045388  jz      loc_18004510E
0x18004538e  cdqe
0x180045390  lea     r9, [rbp+57h+Buf1]; lpArguments
0x180045394  xor     edx, edx; dwExceptionFlags
0x180045396  mov     qword ptr [rbp+57h+var_60], rax
0x18004539a  mov     ecx, 0C0000006h; dwExceptionCode
0x18004539f  mov     qword ptr [rbp+57h+Buf1], r15
0x1800453a3  mov     r8d, 3; nNumberOfArguments
0x1800453a9  mov     qword ptr [rbp+57h+Buf1+8], r15
0x1800453ad  call    cs:__imp_RaiseException
0x1800453b3  jmp     loc_18004510E
0x1800453b8  xor     edx, edx
0x1800453ba  mov     r8d, 1
0x1800453c0  mov     rcx, rbx
0x1800453c3  call    walLockExclusive
0x1800453c8  mov     esi, eax
0x1800453ca  test    eax, eax
0x1800453cc  jz      loc_18004531C
0x1800453d2  jmp     short loc_18004536F
0x1800453d4  test    byte ptr [rbx+42h], 2
0x1800453d8  jz      loc_18004530E
0x1800453de  xor     edx, edx
0x1800453e0  mov     rcx, rbx
0x1800453e3  call    walLockShared
0x1800453e8  mov     esi, eax
0x1800453ea  test    eax, eax
0x1800453ec  jnz     short loc_18004536F
0x1800453ee  xor     edx, edx
0x1800453f0  mov     rcx, rbx
0x1800453f3  call    walUnlockShared
0x1800453f8  mov     esi, 108h
0x1800453fd  jmp     loc_18004536F
0x180045402  test    esi, esi
0x180045404  jz      short loc_180045422
0x180045406  xor     edx, edx
0x180045408  mov     rcx, rbx
0x18004540b  call    walIndexClose
0x180045410  cmp     esi, 20Ah
0x180045416  mov     byte ptr [rbx+46h], 0
0x18004541a  mov     eax, 0FFFFFFFFh
0x18004541f  cmovz   esi, eax
0x180045422  mov     byte ptr [rbx+3Fh], 0
0x180045426  jmp     loc_180045277
```
