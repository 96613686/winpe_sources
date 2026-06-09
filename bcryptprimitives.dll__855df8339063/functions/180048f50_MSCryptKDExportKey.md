# MSCryptKDExportKey

- ea: `0x180048f50`
- end: `0x1800491d9`
- name: `MSCryptKDExportKey`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006c410`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180048f50`
- `0x180063170`
- `0x18007f765`

## string_xrefs

- `0x1800490ab`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180049131`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180049164`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18004918d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800491b6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDExportKey(
        __int64 a1,
        int a2,
        const wchar_t *a3,
        char *a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  unsigned int v7; // esi
  unsigned int *v10; // rdi
  int v11; // edx
  int v12; // r8d
  _DWORD *v13; // r15
  unsigned int v14; // r14d
  char *v16; // r9
  int v17; // ecx
  char *v18; // rax
  char *v19; // rdx
  char v20; // cl

  v7 = 0;
  if ( a7 )
  {
    v14 = -1073741811;
    DebugTraceError(
      3221225485LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      1807);
  }
  else
  {
    if ( a1 )
    {
      if ( *(_DWORD *)(a1 + 4) == 1297304409 )
      {
        v10 = a6;
        if ( !a6 )
        {
          v14 = -1073741811;
          DebugTraceError(
            3221225485LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            1830);
          return v14;
        }
        if ( a3 )
        {
          if ( !wcscmp_0(a3, L"KeyDataBlob") )
          {
            v13 = (_DWORD *)(a1 + 64);
            v7 = *(_DWORD *)(a1 + 16) + 12;
            if ( *(_QWORD *)(a1 + 72) )
              v7 = *v13 + *(_DWORD *)(a1 + 16) + 16;
            if ( a4 )
            {
              if ( a5 < v7 )
              {
                v14 = -1073741789;
              }
              else
              {
                *(_DWORD *)a4 = 1296188491;
                v16 = a4 + 12;
                *((_DWORD *)a4 + 1) = 1;
                v14 = 0;
                v17 = *(_DWORD *)(a1 + 16);
                *((_DWORD *)a4 + 2) = v17;
                if ( *(_QWORD *)(a1 + 72) )
                {
                  v18 = a4 + 15;
                  v19 = (char *)(a1 + 64);
                  *((_DWORD *)a4 + 2) = *v13 + v17 + 4;
                  if ( a4 + 15 >= a4 + 12 )
                  {
                    do
                    {
                      v20 = *v19++;
                      *v18-- = v20;
                    }
                    while ( v18 >= v16 );
                  }
                  memcpy_0(a4 + 16, *(const void **)(a1 + 56), (unsigned int)*v13);
                  v16 = &a4[*v13 + 16];
                }
                memcpy_0(v16, *(const void **)(a1 + 24), *(unsigned int *)(a1 + 16));
              }
            }
            else
            {
              v14 = 0;
            }
          }
          else
          {
            v14 = -1073741637;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v11,
                v12,
                (unsigned int)"Status",
                187,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
                96);
          }
        }
        else
        {
          v14 = -1073741811;
          DebugTraceError(
            3221225485LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            1837);
        }
        goto LABEL_15;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          84);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        75);
    }
    v14 = -1073741816;
  }
  v10 = a6;
  if ( a6 )
LABEL_15:
    *v10 = v7;
  return v14;
}

```

## disassembly

```asm
0x180048f50  push    rbx
0x180048f52  push    rbp
0x180048f53  push    rsi
0x180048f54  push    rdi
0x180048f55  push    r14
0x180048f57  push    r15
0x180048f59  sub     rsp, 48h
0x180048f5d  xor     esi, esi
0x180048f5f  mov     rbx, r9
0x180048f62  mov     rbp, rcx
0x180048f65  cmp     [rsp+78h+arg_30], esi
0x180048f6c  jnz     loc_18004915E
0x180048f72  test    rcx, rcx
0x180048f75  jz      loc_1800490DB
0x180048f7b  cmp     dword ptr [rcx+4], 4D534B59h
0x180048f82  jnz     short loc_180048FD6
0x180048f84  mov     rdi, [rsp+78h+arg_28]
0x180048f8c  test    rdi, rdi
0x180048f8f  jz      loc_180049187
0x180048f95  test    r8, r8
0x180048f98  jz      loc_1800491B0
0x180048f9e  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180048fa5  mov     rcx, r8; String1
0x180048fa8  call    wcscmp_0
0x180048fad  test    eax, eax
0x180048faf  jnz     loc_180049106
0x180048fb5  mov     esi, [rbp+10h]
0x180048fb8  lea     r15, [rbp+40h]
0x180048fbc  add     esi, 0Ch
0x180048fbf  cmp     qword ptr [rbp+48h], 0
0x180048fc4  jz      short loc_180048FCC
0x180048fc6  add     esi, 4
0x180048fc9  add     esi, [r15]
0x180048fcc  test    rbx, rbx
0x180048fcf  jnz     short loc_180049019
0x180048fd1  xor     r14d, r14d
0x180048fd4  jmp     short loc_180049006
0x180048fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180048fdd  lea     rax, WPP_GLOBAL_Control
0x180048fe4  cmp     rcx, rax
0x180048fe7  jz      short loc_180048FF3
0x180048fe9  test    byte ptr [rcx+1Ch], 1
0x180048fed  jnz     loc_18004909F
0x180048ff3  mov     r14d, 0C0000008h
0x180048ff9  mov     rdi, [rsp+78h+arg_28]
0x180049001  test    rdi, rdi
0x180049004  jz      short loc_180049008
0x180049006  mov     [rdi], esi
0x180049008  mov     eax, r14d
0x18004900b  add     rsp, 48h
0x18004900f  pop     r15
0x180049011  pop     r14
0x180049013  pop     rdi
0x180049014  pop     rsi
0x180049015  pop     rbp
0x180049016  pop     rbx
0x180049017  retn
0x180049019  cmp     [rsp+78h+arg_20], esi
0x180049020  jb      loc_1800490D0
0x180049026  mov     dword ptr [rbx], 4D42444Bh
0x18004902c  lea     r9, [rbx+0Ch]
0x180049030  mov     dword ptr [rbx+4], 1
0x180049037  xor     r14d, r14d
0x18004903a  mov     ecx, [rbp+10h]
0x18004903d  mov     [rbx+8], ecx
0x180049040  cmp     [rbp+48h], r14
0x180049044  jz      short loc_18004908A
0x180049046  add     ecx, 4
0x180049049  lea     rax, [r9+3]
0x18004904d  add     ecx, [r15]
0x180049050  mov     rdx, r15
0x180049053  mov     [rbx+8], ecx
0x180049056  cmp     rax, r9
0x180049059  jb      short loc_180049071
0x18004905b  nop     dword ptr [rax+rax+00h]
0x180049060  movzx   ecx, byte ptr [rdx]
0x180049063  lea     rdx, [rdx+1]
0x180049067  mov     [rax], cl
0x180049069  dec     rax
0x18004906c  cmp     rax, r9
0x18004906f  jnb     short loc_180049060
0x180049071  mov     r8d, [r15]; Size
0x180049074  lea     rbx, [r9+4]
0x180049078  mov     rdx, [rbp+38h]; Src
0x18004907c  mov     rcx, rbx; void *
0x18004907f  call    memcpy_0
0x180049084  mov     r9d, [r15]
0x180049087  add     r9, rbx
0x18004908a  mov     r8d, [rbp+10h]; Size
0x18004908e  mov     rcx, r9; void *
0x180049091  mov     rdx, [rbp+18h]; Src
0x180049095  call    memcpy_0
0x18004909a  jmp     loc_180049006
0x18004909f  mov     [rsp+78h+var_48], 154h
0x1800490a7  mov     rcx, [rcx+10h]
0x1800490ab  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800490b2  mov     [rsp+78h+var_50], rax
0x1800490b7  lea     r9, aStatus; "Status"
0x1800490be  mov     [rsp+78h+var_58], 0C0000008h
0x1800490c6  call    WPP_SF_sDsd
0x1800490cb  jmp     loc_180048FF3
0x1800490d0  mov     r14d, 0C0000023h
0x1800490d6  jmp     loc_180049006
0x1800490db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800490e2  lea     rax, WPP_GLOBAL_Control
0x1800490e9  cmp     rcx, rax
0x1800490ec  jz      loc_180048FF3
0x1800490f2  test    byte ptr [rcx+1Ch], 1
0x1800490f6  jz      loc_180048FF3
0x1800490fc  mov     [rsp+78h+var_48], 14Bh
0x180049104  jmp     short loc_1800490A7
0x180049106  mov     r14d, 0C00000BBh
0x18004910c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049113  lea     rax, WPP_GLOBAL_Control
0x18004911a  cmp     rcx, rax
0x18004911d  jz      loc_180049006
0x180049123  test    byte ptr [rcx+1Ch], 1
0x180049127  jz      loc_180049006
0x18004912d  mov     rcx, [rcx+10h]
0x180049131  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049138  mov     [rsp+78h+var_48], 760h
0x180049140  lea     r9, aStatus; "Status"
0x180049147  mov     [rsp+78h+var_50], rax
0x18004914c  mov     [rsp+78h+var_58], 0C00000BBh
0x180049154  call    WPP_SF_sDsd
0x180049159  jmp     loc_180049006
0x18004915e  mov     r9d, 70Fh
0x180049164  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004916b  lea     rdx, aStatus; "Status"
0x180049172  mov     ecx, 0C000000Dh
0x180049177  mov     r14d, 0C000000Dh
0x18004917d  call    DebugTraceError
0x180049182  jmp     loc_180048FF9
0x180049187  mov     r9d, 726h
0x18004918d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049194  lea     rdx, aStatus; "Status"
0x18004919b  mov     ecx, 0C000000Dh
0x1800491a0  mov     r14d, 0C000000Dh
0x1800491a6  call    DebugTraceError
0x1800491ab  jmp     loc_180049008
0x1800491b0  mov     r9d, 72Dh
0x1800491b6  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800491bd  lea     rdx, aStatus; "Status"
0x1800491c4  mov     ecx, 0C000000Dh
0x1800491c9  mov     r14d, 0C000000Dh
0x1800491cf  call    DebugTraceError
0x1800491d4  jmp     loc_180049006
```
