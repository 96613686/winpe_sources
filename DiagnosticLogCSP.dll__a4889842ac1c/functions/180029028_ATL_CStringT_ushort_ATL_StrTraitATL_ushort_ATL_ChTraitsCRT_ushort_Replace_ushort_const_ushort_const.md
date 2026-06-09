# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x180029028`
- end: `0x18002921b`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `499`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800274b4`

## callees

- `0x180002582`
- `0x180002d01`
- `0x180010db8`
- `0x180018bd8`
- `0x18002697c`
- `0x180029028`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800291ff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800291ff`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029079`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029105`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029188`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029079`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029105`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180029188`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        __int64 *a1)
{
  const wchar_t *v1; // rbx
  int v2; // r14d
  unsigned __int64 v3; // rdi
  wchar_t *v4; // rax
  __int64 v5; // rax
  __int64 v6; // r15
  int v7; // edi
  int v8; // edx
  __int64 v9; // r12
  const wchar_t *v10; // rbx
  unsigned __int64 v11; // r13
  const void *v12; // rdx
  wchar_t *v13; // rbp
  __int64 v14; // rcx
  int v15; // r13d
  size_t v16; // r8
  __int64 v17; // rax
  unsigned __int64 v19; // [rsp+20h] [rbp-38h]
  unsigned __int64 v21; // [rsp+70h] [rbp+18h]

  v1 = (const wchar_t *)*a1;
  v2 = 0;
  v3 = *a1 + 2LL * *(int *)(*a1 - 16);
  if ( *a1 < v3 )
  {
    do
    {
      while ( 1 )
      {
        v4 = wcsstr(v1, L"\\Framework64\\");
        if ( !v4 )
          break;
        ++v2;
        v1 = v4 + 13;
      }
      if ( v1 )
      {
        v5 = -1;
        do
          ++v5;
        while ( v1[v5] );
      }
      else
      {
        LODWORD(v5) = 0;
      }
      v1 += (int)v5 + 1;
    }
    while ( (unsigned __int64)v1 < v3 );
    if ( v2 > 0 )
    {
      v6 = *(int *)(*a1 - 16);
      v7 = *(_DWORD *)(*a1 - 16) - 2 * v2;
      v8 = v7;
      if ( v7 <= (int)v6 )
        v8 = *(_DWORD *)(*a1 - 16);
      if ( ((*(_DWORD *)(*a1 - 12) - v8) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v8);
      v9 = *a1;
      v10 = (const wchar_t *)*a1;
      v11 = *a1 + 2 * v6;
      v21 = v11;
      if ( *a1 < v11 )
      {
        do
        {
          v13 = wcsstr(v10, L"\\Framework64\\");
          if ( v13 )
          {
            do
            {
              v10 = v13 + 11;
              v14 = ((__int64)v13 - v9) >> 1;
              v15 = v6 - v14 - 13;
              v16 = 2LL * v15;
              if ( v16 )
              {
                if ( v13 == (wchar_t *)-22LL || (v12 = v13 + 13, v13 == (wchar_t *)-26LL) )
                {
                  *(_DWORD *)_o__errno(v14, v12, v16, 0) = 22;
                  invalid_parameter_noinfo();
                  goto LABEL_35;
                }
                memmove_0(v13 + 11, v12, v16);
              }
              ATL::Checked::memcpy_s(
                (ATL::Checked *)v13,
                (void *)0x16,
                (unsigned __int64)L"\\Framework\\",
                (const void *)0x16,
                v19);
              LODWORD(v6) = v6 - 2;
              v13[v15 + 11] = 0;
              v13 = wcsstr(v13 + 11, L"\\Framework64\\");
            }
            while ( v13 );
            v11 = v21;
          }
          if ( v10 )
          {
            v17 = -1;
            do
              ++v17;
            while ( v10[v17] );
          }
          else
          {
            LODWORD(v17) = 0;
          }
          v10 += (int)v17 + 1;
        }
        while ( (unsigned __int64)v10 < v11 );
      }
      if ( v7 < 0 || v7 > *(_DWORD *)(*a1 - 12) )
LABEL_35:
        ATL::AtlThrowImpl(-2147024809);
      *(_DWORD *)(*a1 - 16) = v7;
      *(_WORD *)(*a1 + 2LL * v7) = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180029028  mov     [rsp+arg_8], rbx
0x18002902d  mov     [rsp+arg_10], r8
0x180029032  mov     [rsp+arg_0], rcx
0x180029037  push    rbp
0x180029038  push    rsi
0x180029039  push    rdi
0x18002903a  push    r12
0x18002903c  push    r13
0x18002903e  push    r14
0x180029040  push    r15
0x180029042  sub     rsp, 20h
0x180029046  mov     rbx, [rcx]
0x180029049  xor     eax, eax
0x18002904b  mov     r14d, eax
0x18002904e  movsxd  rax, dword ptr [rbx-10h]
0x180029052  lea     rdi, [rbx+rax*2]
0x180029056  cmp     rbx, rdi
0x180029059  jnb     loc_1800291E7
0x18002905f  mov     ebp, 1
0x180029064  xor     esi, esi
0x180029066  jmp     short loc_18002906F
0x180029068  add     r14d, ebp
0x18002906b  lea     rbx, [rax+1Ah]
0x18002906f  lea     rdx, aFramework64; "\\Framework64\\"
0x180029076  mov     rcx, rbx; Str
0x180029079  call    cs:__imp_wcsstr
0x18002907f  test    rax, rax
0x180029082  jnz     short loc_180029068
0x180029084  test    rbx, rbx
0x180029087  jz      short loc_180029098
0x180029089  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002908d  inc     rax
0x180029090  cmp     [rbx+rax*2], si
0x180029094  jnz     short loc_18002908D
0x180029096  jmp     short loc_18002909A
0x180029098  mov     eax, esi
0x18002909a  inc     eax
0x18002909c  movsxd  rcx, eax
0x18002909f  lea     rbx, [rbx+rcx*2]
0x1800290a3  cmp     rbx, rdi
0x1800290a6  jb      short loc_18002906F
0x1800290a8  mov     rsi, [rsp+58h+arg_0]
0x1800290ad  test    r14d, r14d
0x1800290b0  jle     loc_1800291E7
0x1800290b6  mov     rcx, [rsi]
0x1800290b9  lea     eax, [r14+r14]
0x1800290bd  movsxd  r15, dword ptr [rcx-10h]
0x1800290c1  mov     edi, r15d
0x1800290c4  sub     edi, eax
0x1800290c6  mov     eax, [rcx-0Ch]
0x1800290c9  cmp     edi, r15d
0x1800290cc  mov     edx, edi
0x1800290ce  cmovle  edx, r15d
0x1800290d2  sub     ebp, [rcx-8]
0x1800290d5  sub     eax, edx
0x1800290d7  or      ebp, eax
0x1800290d9  jge     short loc_1800290E3
0x1800290db  mov     rcx, rsi
0x1800290de  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800290e3  mov     r12, [rsi]
0x1800290e6  mov     rbx, r12
0x1800290e9  lea     r13, [r12+r15*2]
0x1800290ed  mov     [rsp+58h+arg_10], r13
0x1800290f2  cmp     r12, r13
0x1800290f5  jnb     loc_1800291CA
0x1800290fb  lea     rdx, aFramework64; "\\Framework64\\"
0x180029102  mov     rcx, rbx; Str
0x180029105  call    cs:__imp_wcsstr
0x18002910b  xor     r9d, r9d
0x18002910e  mov     rbp, rax
0x180029111  test    rax, rax
0x180029114  jz      loc_18002919E
0x18002911a  mov     rcx, rbp
0x18002911d  lea     rbx, [rbp+16h]
0x180029121  sub     rcx, r12
0x180029124  mov     r13d, r15d
0x180029127  sar     rcx, 1
0x18002912a  sub     r13d, ecx
0x18002912d  add     r13d, 0FFFFFFF3h
0x180029131  movsxd  r8, r13d
0x180029134  add     r8, r8; Size
0x180029137  jz      short loc_180029157
0x180029139  test    rbx, rbx
0x18002913c  jz      loc_1800291FF
0x180029142  lea     rdx, [rbp+1Ah]; Src
0x180029146  test    rdx, rdx
0x180029149  jz      loc_1800291FF
0x18002914f  mov     rcx, rbx; void *
0x180029152  call    memmove_0
0x180029157  mov     eax, 16h
0x18002915c  lea     r8, aFramework; "\\Framework\\"
0x180029163  mov     r9d, eax; void *
0x180029166  mov     edx, eax; void *
0x180029168  mov     rcx, rbp; this
0x18002916b  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180029170  movsxd  rcx, r13d
0x180029173  lea     rdx, aFramework64; "\\Framework64\\"
0x18002917a  xor     eax, eax
0x18002917c  sub     r15d, 2
0x180029180  mov     [rbp+rcx*2+16h], ax
0x180029185  mov     rcx, rbx; Str
0x180029188  call    cs:__imp_wcsstr
0x18002918e  xor     r9d, r9d
0x180029191  mov     rbp, rax
0x180029194  test    rax, rax
0x180029197  jnz     short loc_18002911A
0x180029199  mov     r13, [rsp+58h+arg_10]
0x18002919e  test    rbx, rbx
0x1800291a1  jz      short loc_1800291B3
0x1800291a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800291a7  inc     rax
0x1800291aa  cmp     [rbx+rax*2], r9w
0x1800291af  jnz     short loc_1800291A7
0x1800291b1  jmp     short loc_1800291B6
0x1800291b3  mov     eax, r9d
0x1800291b6  inc     eax
0x1800291b8  movsxd  rcx, eax
0x1800291bb  lea     rbx, [rbx+rcx*2]
0x1800291bf  cmp     rbx, r13
0x1800291c2  jb      loc_1800290FB
0x1800291c8  jmp     short loc_1800291CD
0x1800291ca  xor     r9d, r9d
0x1800291cd  test    edi, edi
0x1800291cf  js      short loc_180029210
0x1800291d1  mov     rax, [rsi]
0x1800291d4  cmp     edi, [rax-0Ch]
0x1800291d7  jg      short loc_180029210
0x1800291d9  mov     [rax-10h], edi
0x1800291dc  mov     rcx, [rsi]
0x1800291df  movsxd  rdx, edi
0x1800291e2  mov     [rcx+rdx*2], r9w
0x1800291e7  mov     rbx, [rsp+58h+arg_8]
0x1800291ec  mov     eax, r14d
0x1800291ef  add     rsp, 20h
0x1800291f3  pop     r15
0x1800291f5  pop     r14
0x1800291f7  pop     r13
0x1800291f9  pop     r12
0x1800291fb  pop     rdi
0x1800291fc  pop     rsi
0x1800291fd  pop     rbp
0x1800291fe  retn
0x1800291ff  call    cs:__imp__o__errno
0x180029205  mov     dword ptr [rax], 16h
0x18002920b  call    _invalid_parameter_noinfo
0x180029210  mov     ecx, 80070057h; int
0x180029215  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
