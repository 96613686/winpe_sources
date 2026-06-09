# MonthNumOfMonthName

- ea: `0x180077444`
- end: `0x180077700`
- name: `MonthNumOfMonthName`
- size: `700`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, int cchCount2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180046790`

## callees

- `0x180077444`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180077497`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800774e5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007752c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180077576`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800775cc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180077608`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180077654`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007768a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800776d1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180077497`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800774e5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007752c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180077576`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800775cc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180077608`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180077654`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007768a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800776d1`

## pseudocode

```c
__int64 __fastcall MonthNumOfMonthName(PCNZWCH lpString1, int cchCount2, char a3, LCID *a4)
{
  int v4; // ebx
  __int64 result; // rax
  unsigned int v9; // r14d
  bool v10; // zf
  int i; // r14d
  unsigned int v12; // r14d
  LCID v13; // ecx
  __int64 (**v14)[2]; // rax

  v4 = 0;
  if ( (a3 & 8) != 0 )
  {
    while ( v4 < 12 )
    {
      if ( CompareStringW(0x401u, 1u, lpString1, cchCount2, (PCNZWCH)g_rgszHijriMonth2[v4], cchCount2) == 2 )
        return (unsigned int)(v4 + 1);
      ++v4;
    }
  }
  else
  {
    if ( a4[582] && cchCount2 > 3 )
    {
      LODWORD(result) = 0;
      while ( (int)result < 12 )
      {
        v9 = result + 1;
        v10 = CompareStringW(a4[4], 1u, lpString1, cchCount2, (PCNZWCH)off_1800A72F0[(int)result], cchCount2) == 2;
        result = v9;
        if ( v10 )
          return result;
      }
    }
    for ( i = 0; i < 12; ++i )
    {
      if ( CompareStringW(
             a4[4],
             1u,
             lpString1,
             cchCount2,
             *(PCNZWCH *)&a4[2 * i + 54],
             *((unsigned __int8 *)a4 + i + 312)) == 2
        || (a4[293] || a4[581] || a4[582])
        && CompareStringW(0x409u, 1u, lpString1, cchCount2, (PCNZWCH)&a4[2 * i + 486], -1) == 2 )
      {
        return (unsigned int)(i + 1);
      }
    }
    if ( cchCount2 >= 3 )
    {
      if ( a4[582] )
      {
        LODWORD(result) = 0;
        while ( (int)result < 12 )
        {
          v12 = result + 1;
          v10 = CompareStringW(a4[4], 1u, lpString1, cchCount2, (PCNZWCH)*(&off_1800A7280 + (int)result), cchCount2) == 2;
          result = v12;
          if ( v10 )
            return result;
        }
      }
      for ( i = 0; i < 12; ++i )
      {
        if ( CompareStringW(a4[4], 1u, lpString1, cchCount2, *(PCNZWCH *)&a4[2 * i + 30], cchCount2) == 2 )
          return (unsigned int)(i + 1);
        v13 = a4[4];
        if ( ((v13 - 1045) & 0xFFFFFFFB) == 0 )
        {
          v14 = (__int64 (**)[2])g_rgszPolishMonth2;
          if ( v13 != 1045 )
            v14 = g_rgszRussianMonth2;
          if ( CompareStringW(v13, 1u, lpString1, cchCount2, (PCNZWCH)v14[i], cchCount2) == 2 )
            return (unsigned int)(i + 1);
          if ( i == 1
            && a4[4] == 1049
            && CompareStringW(0x419u, 1u, lpString1, cchCount2, &word_1800B3F70, cchCount2) == 2 )
          {
            return 2;
          }
        }
        if ( (a4[293] || a4[581] || a4[582])
          && CompareStringW(0x409u, 1u, lpString1, cchCount2, (PCNZWCH)&a4[16 * (__int64)i + 294], cchCount2) == 2 )
        {
          return (unsigned int)(i + 1);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180077444  push    rbx
0x180077446  push    rbp
0x180077447  push    rsi
0x180077448  push    rdi
0x180077449  push    r12
0x18007744b  push    r13
0x18007744d  push    r14
0x18007744f  sub     rsp, 30h
0x180077453  xor     ebx, ebx
0x180077455  lea     r13, __ImageBase
0x18007745c  mov     rdi, r9
0x18007745f  mov     esi, edx
0x180077461  mov     r12, rcx
0x180077464  lea     ebp, [rbx+1]
0x180077467  test    r8b, 8
0x18007746b  jz      short loc_1800774AE
0x18007746d  cmp     ebx, 0Ch
0x180077470  jge     loc_1800776EF
0x180077476  movsxd  rax, ebx
0x180077479  mov     r9d, esi; cchCount1
0x18007747c  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180077480  mov     r8, r12; lpString1
0x180077483  mov     edx, ebp; dwCmpFlags
0x180077485  mov     ecx, 401h; Locale
0x18007748a  mov     rax, ds:rva g_rgszHijriMonth2[r13+rax*8]
0x180077492  mov     [rsp+68h+lpString2], rax; lpString2
0x180077497  call    cs:__imp_CompareStringW
0x18007749d  cmp     eax, 2
0x1800774a0  jz      short loc_1800774A6
0x1800774a2  inc     ebx
0x1800774a4  jmp     short loc_18007746D
0x1800774a6  lea     eax, [rbx+1]
0x1800774a9  jmp     loc_1800776F1
0x1800774ae  cmp     [r9+918h], ebx
0x1800774b5  jz      short loc_1800774F8
0x1800774b7  cmp     esi, 3
0x1800774ba  jle     short loc_1800774F8
0x1800774bc  mov     eax, ebx
0x1800774be  cmp     eax, 0Ch
0x1800774c1  jge     short loc_1800774F8
0x1800774c3  mov     ecx, [rdi+10h]; Locale
0x1800774c6  lea     r14d, [rax+1]
0x1800774ca  cdqe
0x1800774cc  mov     r9d, esi; cchCount1
0x1800774cf  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800774d3  mov     r8, r12; lpString1
0x1800774d6  mov     edx, ebp; dwCmpFlags
0x1800774d8  mov     rax, ds:rva off_1800A72F0[r13+rax*8]
0x1800774e0  mov     [rsp+68h+lpString2], rax; lpString2
0x1800774e5  call    cs:__imp_CompareStringW
0x1800774eb  cmp     eax, 2
0x1800774ee  mov     eax, r14d
0x1800774f1  jnz     short loc_1800774BE
0x1800774f3  jmp     loc_1800776F1
0x1800774f8  mov     r14d, ebx
0x1800774fb  cmp     r14d, 0Ch
0x1800774ff  jge     loc_180077592
0x180077505  movsxd  rcx, r14d
0x180077508  mov     r9d, esi; cchCount1
0x18007750b  mov     r8, r12; lpString1
0x18007750e  mov     edx, ebp; dwCmpFlags
0x180077510  movzx   eax, byte ptr [rcx+rdi+138h]
0x180077518  mov     [rsp+68h+cchCount2], eax; cchCount2
0x18007751c  mov     rax, [rdi+rcx*8+0D8h]
0x180077524  mov     ecx, [rdi+10h]; Locale
0x180077527  mov     [rsp+68h+lpString2], rax; lpString2
0x18007752c  call    cs:__imp_CompareStringW
0x180077532  cmp     eax, 2
0x180077535  jz      short loc_180077589
0x180077537  cmp     [rdi+494h], ebx
0x18007753d  jnz     short loc_18007754F
0x18007753f  cmp     [rdi+914h], ebx
0x180077545  jnz     short loc_18007754F
0x180077547  cmp     [rdi+918h], ebx
0x18007754d  jz      short loc_180077581
0x18007754f  movsxd  rax, r14d
0x180077552  mov     r9d, esi; cchCount1
0x180077555  add     rax, 0F3h
0x18007755b  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180077563  mov     r8, r12; lpString1
0x180077566  mov     edx, ebp; dwCmpFlags
0x180077568  mov     ecx, 409h; Locale
0x18007756d  lea     rax, [rdi+rax*8]
0x180077571  mov     [rsp+68h+lpString2], rax; lpString2
0x180077576  call    cs:__imp_CompareStringW
0x18007757c  cmp     eax, 2
0x18007757f  jz      short loc_180077589
0x180077581  add     r14d, ebp
0x180077584  jmp     loc_1800774FB
0x180077589  lea     eax, [r14+1]
0x18007758d  jmp     loc_1800776F1
0x180077592  cmp     esi, 3
0x180077595  jl      loc_1800776EF
0x18007759b  cmp     [rdi+918h], ebx
0x1800775a1  jz      short loc_1800775DF
0x1800775a3  mov     eax, ebx
0x1800775a5  cmp     eax, 0Ch
0x1800775a8  jge     short loc_1800775DF
0x1800775aa  mov     ecx, [rdi+10h]; Locale
0x1800775ad  lea     r14d, [rax+1]
0x1800775b1  cdqe
0x1800775b3  mov     r9d, esi; cchCount1
0x1800775b6  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800775ba  mov     r8, r12; lpString1
0x1800775bd  mov     edx, ebp; dwCmpFlags
0x1800775bf  mov     rax, ds:rva off_1800A7280[r13+rax*8]
0x1800775c7  mov     [rsp+68h+lpString2], rax; lpString2
0x1800775cc  call    cs:__imp_CompareStringW
0x1800775d2  cmp     eax, 2
0x1800775d5  mov     eax, r14d
0x1800775d8  jnz     short loc_1800775A5
0x1800775da  jmp     loc_1800776F1
0x1800775df  mov     r14d, ebx
0x1800775e2  cmp     r14d, 0Ch
0x1800775e6  jge     loc_1800776EF
0x1800775ec  mov     ecx, [rdi+10h]; Locale
0x1800775ef  mov     r9d, esi; cchCount1
0x1800775f2  movsxd  r13, r14d
0x1800775f5  mov     r8, r12; lpString1
0x1800775f8  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800775fc  mov     edx, ebp; dwCmpFlags
0x1800775fe  mov     rax, [rdi+r13*8+78h]
0x180077603  mov     [rsp+68h+lpString2], rax; lpString2
0x180077608  call    cs:__imp_CompareStringW
0x18007760e  cmp     eax, 2
0x180077611  jz      loc_180077589
0x180077617  mov     ecx, [rdi+10h]; Locale
0x18007761a  lea     eax, [rcx-415h]
0x180077620  test    eax, 0FFFFFFFBh
0x180077625  jnz     short loc_180077695
0x180077627  lea     rdx, g_rgszRussianMonth2
0x18007762e  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180077632  cmp     ecx, 415h
0x180077638  lea     rax, g_rgszPolishMonth2
0x18007763f  mov     r9d, esi; cchCount1
0x180077642  mov     r8, r12; lpString1
0x180077645  cmovnz  rax, rdx
0x180077649  mov     edx, ebp; dwCmpFlags
0x18007764b  mov     rax, [rax+r13*8]
0x18007764f  mov     [rsp+68h+lpString2], rax; lpString2
0x180077654  call    cs:__imp_CompareStringW
0x18007765a  cmp     eax, 2
0x18007765d  jz      loc_180077589
0x180077663  cmp     r14d, ebp
0x180077666  jnz     short loc_180077695
0x180077668  mov     ecx, 419h; Locale
0x18007766d  cmp     [rdi+10h], ecx
0x180077670  jnz     short loc_180077695
0x180077672  lea     rax, word_1800B3F70
0x180077679  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18007767d  mov     r9d, esi; cchCount1
0x180077680  mov     [rsp+68h+lpString2], rax; lpString2
0x180077685  mov     r8, r12; lpString1
0x180077688  mov     edx, ebp; dwCmpFlags
0x18007768a  call    cs:__imp_CompareStringW
0x180077690  cmp     eax, 2
0x180077693  jz      short loc_1800776E8
0x180077695  cmp     [rdi+494h], ebx
0x18007769b  jnz     short loc_1800776AD
0x18007769d  cmp     [rdi+914h], ebx
0x1800776a3  jnz     short loc_1800776AD
0x1800776a5  cmp     [rdi+918h], ebx
0x1800776ab  jz      short loc_1800776E0
0x1800776ad  shl     r13, 6
0x1800776b1  lea     rax, [rdi+498h]
0x1800776b8  add     rax, r13
0x1800776bb  mov     [rsp+68h+cchCount2], esi; cchCount2
0x1800776bf  mov     r9d, esi; cchCount1
0x1800776c2  mov     [rsp+68h+lpString2], rax; lpString2
0x1800776c7  mov     r8, r12; lpString1
0x1800776ca  mov     edx, ebp; dwCmpFlags
0x1800776cc  mov     ecx, 409h; Locale
0x1800776d1  call    cs:__imp_CompareStringW
0x1800776d7  cmp     eax, 2
0x1800776da  jz      loc_180077589
0x1800776e0  add     r14d, ebp
0x1800776e3  jmp     loc_1800775E2
0x1800776e8  mov     eax, 2
0x1800776ed  jmp     short loc_1800776F1
0x1800776ef  xor     eax, eax
0x1800776f1  add     rsp, 30h
0x1800776f5  pop     r14
0x1800776f7  pop     r13
0x1800776f9  pop     r12
0x1800776fb  pop     rdi
0x1800776fc  pop     rsi
0x1800776fd  pop     rbp
0x1800776fe  pop     rbx
0x1800776ff  retn
```
