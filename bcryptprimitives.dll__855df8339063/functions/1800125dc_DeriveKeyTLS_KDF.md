# DeriveKeyTLS_KDF

- ea: `0x1800125dc`
- end: `0x180012881`
- name: `DeriveKeyTLS_KDF`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012060`

## callees

- `0x18000ee60`
- `0x1800125dc`
- `0x180012888`
- `0x180012a80`

## string_xrefs

- `0x18001277d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x1800127d6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeyTLS_KDF(__int64 a1, __int64 a2, __int64 a3, int a4, _DWORD *a5, int a6)
{
  __int64 v7; // r14
  __int64 v8; // r11
  unsigned int v10; // ebp
  __int64 v11; // rbx
  int ParameterList; // eax
  __int64 v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // r10
  int i; // ecx
  int v20; // edx
  int v21; // r8d
  char v23; // [rsp+30h] [rbp-58h]

  v7 = a3;
  v8 = a2;
  if ( a6 || !a2 )
  {
    v16 = -1073741811;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v16;
    v23 = -123;
LABEL_27:
    WPP_SF_sDsd(
      v17[2],
      a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
      v23);
    return v16;
  }
  v10 = *(_DWORD *)(a1 + 8);
  v11 = 0;
  if ( v10 != 393222 )
    goto LABEL_12;
  ParameterList = QueryParameterList(a2, 0, 0);
  if ( ParameterList < 0 )
  {
    v16 = -1073741811;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = -94;
      goto LABEL_27;
    }
    return v16;
  }
  _mm_lfence();
  a2 = *(_QWORD *)(v8 + 8);
  v13 = 2LL * ParameterList;
  v14 = *(_DWORD *)(a2 + 8 * v13);
  if ( v14 < 2 )
  {
LABEL_9:
    v16 = -1073741811;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v16;
    v23 = -101;
    goto LABEL_27;
  }
  v11 = *(_QWORD *)(a2 + 8 * v13 + 8);
  LODWORD(v15) = v14 >> 1;
  while ( 1 )
  {
    v15 = (unsigned int)(v15 - 1);
    if ( !*(_WORD *)(v11 + 2 * v15) )
      break;
    if ( !(_DWORD)v15 )
      goto LABEL_9;
  }
LABEL_12:
  LODWORD(a3) = *(_DWORD *)(v8 + 4);
  if ( (unsigned int)a3 <= 0x7FFFFFFF )
  {
    v18 = *(_QWORD *)(v8 + 8);
    LODWORD(a2) = 0;
    while ( (unsigned int)a2 < (unsigned int)a3 )
    {
      if ( *(_DWORD *)(v18 + 16LL * (unsigned int)a2 + 4) == 4 )
      {
        if ( (int)a2 < 0 )
          break;
        for ( i = 0; i < (unsigned int)a3; ++i )
        {
          if ( *(_DWORD *)(v18 + 16LL * (unsigned int)i + 4) == 5 )
          {
            if ( i >= 0 )
            {
              v16 = TLS_KDF(
                      v10,
                      v11,
                      *(_QWORD *)(a1 + 24),
                      *(unsigned int *)(a1 + 16),
                      *(_QWORD *)(v18 + 16LL * (int)a2 + 8),
                      *(_DWORD *)(v18 + 16LL * (int)a2),
                      *(_QWORD *)(v18 + 16LL * i + 8),
                      *(_DWORD *)(v18 + 16LL * i),
                      v7,
                      a4);
              if ( v16 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v20,
                    v21,
                    (unsigned int)"Status",
                    v16,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
                    221);
                }
              }
              else
              {
                *a5 = a4;
              }
              return v16;
            }
            break;
          }
        }
        v16 = -1073741811;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = -59;
          goto LABEL_27;
        }
        return v16;
      }
      LODWORD(a2) = a2 + 1;
    }
  }
  v16 = -1073741811;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v23 = -76;
    goto LABEL_27;
  }
  return v16;
}

```

## disassembly

```asm
0x1800125dc  push    rbx
0x1800125de  push    rbp
0x1800125df  push    rsi
0x1800125e0  push    rdi
0x1800125e1  push    r14
0x1800125e3  push    r15
0x1800125e5  sub     rsp, 58h
0x1800125e9  xor     r15d, r15d
0x1800125ec  mov     edi, r9d
0x1800125ef  mov     r14, r8
0x1800125f2  mov     r11, rdx
0x1800125f5  mov     rsi, rcx
0x1800125f8  cmp     [rsp+88h+arg_28], r15d
0x180012600  jnz     loc_180012757
0x180012606  test    rdx, rdx
0x180012609  jz      loc_180012757
0x18001260f  mov     ebp, [rcx+8]
0x180012612  mov     ebx, r15d
0x180012615  cmp     ebp, 60006h
0x18001261b  jnz     short loc_18001268D
0x18001261d  xor     r8d, r8d
0x180012620  xor     edx, edx
0x180012622  mov     rcx, r11
0x180012625  call    QueryParameterList
0x18001262a  test    eax, eax
0x18001262c  js      loc_18001284E
0x180012632  lfence
0x180012635  mov     rdx, [r11+8]
0x180012639  cdqe
0x18001263b  add     rax, rax
0x18001263e  mov     ecx, [rdx+rax*8]
0x180012641  cmp     ecx, 2
0x180012644  jb      short loc_18001265A
0x180012646  mov     rbx, [rdx+rax*8+8]
0x18001264b  shr     ecx, 1
0x18001264d  dec     ecx
0x18001264f  cmp     [rbx+rcx*2], r15w
0x180012654  jz      short loc_18001268D
0x180012656  test    ecx, ecx
0x180012658  jnz     short loc_18001264D
0x18001265a  mov     ebx, 0C000000Dh
0x18001265f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012666  lea     rax, WPP_GLOBAL_Control
0x18001266d  cmp     rcx, rax
0x180012670  jz      loc_180012747
0x180012676  test    byte ptr [rcx+1Ch], 1
0x18001267a  jz      loc_180012747
0x180012680  mov     dword ptr [rsp+88h+var_58], 69Bh
0x180012688  jmp     loc_18001277D
0x18001268d  mov     r8d, [r11+4]
0x180012691  cmp     r8d, 7FFFFFFFh
0x180012698  ja      loc_1800127E8
0x18001269e  mov     r10, [r11+8]
0x1800126a2  mov     edx, r15d
0x1800126a5  cmp     edx, r8d
0x1800126a8  jnb     loc_1800127E8
0x1800126ae  mov     eax, edx
0x1800126b0  add     rax, rax
0x1800126b3  cmp     dword ptr [r10+rax*8+4], 4
0x1800126b9  jnz     loc_1800127A3
0x1800126bf  test    edx, edx
0x1800126c1  js      loc_1800127E8
0x1800126c7  mov     ecx, r15d
0x1800126ca  cmp     ecx, r8d
0x1800126cd  jnb     loc_18001281B
0x1800126d3  mov     eax, ecx
0x1800126d5  add     rax, rax
0x1800126d8  cmp     dword ptr [r10+rax*8+4], 5
0x1800126de  jnz     loc_1800127AA
0x1800126e4  test    ecx, ecx
0x1800126e6  js      loc_18001281B
0x1800126ec  mov     [rsp+88h+var_40], edi
0x1800126f0  mov     [rsp+88h+var_48], r14
0x1800126f5  movsxd  r8, ecx
0x1800126f8  mov     ecx, ebp
0x1800126fa  add     r8, r8
0x1800126fd  movsxd  r9, edx
0x180012700  add     r9, r9
0x180012703  mov     rdx, rbx
0x180012706  mov     eax, [r10+r8*8]
0x18001270a  mov     [rsp+88h+var_50], eax
0x18001270e  mov     rax, [r10+r8*8+8]
0x180012713  mov     r8, [rsi+18h]
0x180012717  mov     [rsp+88h+var_58], rax
0x18001271c  mov     eax, [r10+r9*8]
0x180012720  mov     dword ptr [rsp+88h+var_60], eax
0x180012724  mov     rax, [r10+r9*8+8]
0x180012729  mov     r9d, [rsi+10h]
0x18001272d  mov     [rsp+88h+var_68], rax
0x180012732  call    _TLS_KDF
0x180012737  mov     ebx, eax
0x180012739  test    eax, eax
0x18001273b  jnz     short loc_1800127B1
0x18001273d  mov     rax, [rsp+88h+arg_20]
0x180012745  mov     [rax], edi
0x180012747  mov     eax, ebx
0x180012749  add     rsp, 58h
0x18001274d  pop     r15
0x18001274f  pop     r14
0x180012751  pop     rdi
0x180012752  pop     rsi
0x180012753  pop     rbp
0x180012754  pop     rbx
0x180012755  retn
0x180012757  mov     ebx, 0C000000Dh
0x18001275c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012763  lea     rax, WPP_GLOBAL_Control
0x18001276a  cmp     rcx, rax
0x18001276d  jz      short loc_180012747
0x18001276f  test    byte ptr [rcx+1Ch], 1
0x180012773  jz      short loc_180012747
0x180012775  mov     dword ptr [rsp+88h+var_58], 685h
0x18001277d  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012784  mov     [rsp+88h+var_60], rax
0x180012789  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180012791  mov     rcx, [rcx+10h]
0x180012795  lea     r9, aStatus; "Status"
0x18001279c  call    WPP_SF_sDsd
0x1800127a1  jmp     short loc_180012747
0x1800127a3  inc     edx
0x1800127a5  jmp     loc_1800126A5
0x1800127aa  inc     ecx
0x1800127ac  jmp     loc_1800126CA
0x1800127b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127b8  lea     rax, WPP_GLOBAL_Control
0x1800127bf  cmp     rcx, rax
0x1800127c2  jz      short loc_180012747
0x1800127c4  test    byte ptr [rcx+1Ch], 1
0x1800127c8  jz      loc_180012747
0x1800127ce  mov     dword ptr [rsp+88h+var_58], 6DDh
0x1800127d6  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800127dd  mov     [rsp+88h+var_60], rax
0x1800127e2  mov     dword ptr [rsp+88h+var_68], ebx
0x1800127e6  jmp     short loc_180012791
0x1800127e8  mov     ebx, 0C000000Dh
0x1800127ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127f4  lea     rax, WPP_GLOBAL_Control
0x1800127fb  cmp     rcx, rax
0x1800127fe  jz      loc_180012747
0x180012804  test    byte ptr [rcx+1Ch], 1
0x180012808  jz      loc_180012747
0x18001280e  mov     dword ptr [rsp+88h+var_58], 6B4h
0x180012816  jmp     loc_18001277D
0x18001281b  mov     ebx, 0C000000Dh
0x180012820  mov     rcx, cs:WPP_GLOBAL_Control
0x180012827  lea     rax, WPP_GLOBAL_Control
0x18001282e  cmp     rcx, rax
0x180012831  jz      loc_180012747
0x180012837  test    byte ptr [rcx+1Ch], 1
0x18001283b  jz      loc_180012747
0x180012841  mov     dword ptr [rsp+88h+var_58], 6C5h
0x180012849  jmp     loc_18001277D
0x18001284e  mov     ebx, 0C000000Dh
0x180012853  mov     rcx, cs:WPP_GLOBAL_Control
0x18001285a  lea     rax, WPP_GLOBAL_Control
0x180012861  cmp     rcx, rax
0x180012864  jz      loc_180012747
0x18001286a  test    byte ptr [rcx+1Ch], 1
0x18001286e  jz      loc_180012747
0x180012874  mov     dword ptr [rsp+88h+var_58], 6A2h
0x18001287c  jmp     loc_18001277D
```
