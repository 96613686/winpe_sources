# MSCryptOpenSymmetricProvider

- ea: `0x180010630`
- end: `0x1800109b8`
- name: `MSCryptOpenSymmetricProvider`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067358`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010630`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180010841`
- `ntdll!RtlAllocateHeap` at `0x180010841`

## string_xrefs

- `0x1800108c6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18001092b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18001096f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180010996`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptOpenSymmetricProvider(_QWORD *a1, char *a2, int a3)
{
  char *v4; // r9
  char *v6; // rax
  char *v7; // r8
  int v8; // ecx
  int v9; // edx
  __int64 v10; // rax
  unsigned __int16 *v11; // rax
  int v12; // ecx
  int v13; // edx
  unsigned __int16 *v14; // rax
  int v15; // ecx
  int v16; // edx
  unsigned __int16 *v17; // rax
  int v18; // ecx
  int v19; // edx
  unsigned __int16 *v20; // rax
  int v21; // ecx
  int v22; // edx
  unsigned __int16 *v23; // rax
  int v24; // ecx
  int v25; // edx
  unsigned __int16 *v26; // rax
  int v27; // ecx
  int v28; // edx
  unsigned __int16 *v29; // rax
  char *v30; // r8
  int v31; // ecx
  int v32; // edx
  char *v33; // rdx
  int v34; // eax
  int v35; // ecx
  __int64 *v36; // rbx
  _OWORD *Heap; // rax
  int v38; // edx
  int v39; // r8d
  bool v40; // zf
  unsigned int v41; // ebx
  __int64 v43; // r9

  v4 = a2;
  if ( !a1 )
  {
    v41 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        74);
      return v41;
    }
    return v41;
  }
  if ( !a2 )
  {
    v43 = 337;
LABEL_57:
    v41 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v43);
    return v41;
  }
  v6 = a2;
  v7 = (char *)((char *)L"RC4" - a2);
  do
  {
    v8 = *(unsigned __int16 *)&v7[(_QWORD)v6];
    v9 = *(unsigned __int16 *)v6 - v8;
    if ( v9 )
      break;
    v6 += 2;
  }
  while ( v8 );
  v10 = 0;
  if ( v9 )
  {
    v11 = (unsigned __int16 *)v4;
    do
    {
      v12 = *(unsigned __int16 *)((char *)v11 + (char *)L"AES" - v4);
      v13 = *v11 - v12;
      if ( v13 )
        break;
      ++v11;
    }
    while ( v12 );
    v10 = 1;
    if ( v13 )
    {
      v14 = (unsigned __int16 *)v4;
      do
      {
        v15 = *(unsigned __int16 *)((char *)v14 + (char *)L"DES" - v4);
        v16 = *v14 - v15;
        if ( v16 )
          break;
        ++v14;
      }
      while ( v15 );
      v10 = 2;
      if ( v16 )
      {
        v17 = (unsigned __int16 *)v4;
        do
        {
          v18 = *(unsigned __int16 *)((char *)v17 + (char *)L"DESX" - v4);
          v19 = *v17 - v18;
          if ( v19 )
            break;
          ++v17;
        }
        while ( v18 );
        v10 = 3;
        if ( v19 )
        {
          v20 = (unsigned __int16 *)v4;
          do
          {
            v21 = *(unsigned __int16 *)((char *)v20 + (char *)L"3DES" - v4);
            v22 = *v20 - v21;
            if ( v22 )
              break;
            ++v20;
          }
          while ( v21 );
          v10 = 4;
          if ( v22 )
          {
            v23 = (unsigned __int16 *)v4;
            do
            {
              v24 = *(unsigned __int16 *)((char *)v23 + (char *)L"3DES_112" - v4);
              v25 = *v23 - v24;
              if ( v25 )
                break;
              ++v23;
            }
            while ( v24 );
            v10 = 5;
            if ( v25 )
            {
              v26 = (unsigned __int16 *)v4;
              do
              {
                v27 = *(unsigned __int16 *)((char *)v26 + (char *)L"RC2" - v4);
                v28 = *v26 - v27;
                if ( v28 )
                  break;
                ++v26;
              }
              while ( v27 );
              v10 = 6;
              if ( v28 )
              {
                v29 = (unsigned __int16 *)v4;
                v30 = (char *)((char *)L"XTS-AES" - v4);
                do
                {
                  v31 = *(unsigned __int16 *)&v30[(_QWORD)v29];
                  v32 = *v29 - v31;
                  if ( v32 )
                    break;
                  ++v29;
                }
                while ( v31 );
                v10 = 7;
                if ( v32 )
                {
                  v33 = (char *)((char *)L"CHACHA20_POLY1305" - v4);
                  do
                  {
                    v34 = *(unsigned __int16 *)&v33[(_QWORD)v4];
                    v35 = *(unsigned __int16 *)v4 - v34;
                    if ( v35 )
                      break;
                    v4 += 2;
                  }
                  while ( v34 );
                  v10 = 8;
                  if ( v35 )
                  {
                    v41 = -1073741637;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        (_DWORD)v33,
                        (_DWORD)v30,
                        (unsigned int)"Status",
                        187,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                        94);
                      return v41;
                    }
                    return v41;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( (a3 & 0xFFFFFFB6) != 0 )
  {
    v43 = 359;
    goto LABEL_57;
  }
  _mm_lfence();
  v36 = &rgSymmAlgorithmDefaults[14 * v10];
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)v36);
  if ( Heap )
  {
    *Heap = *(_OWORD *)v36;
    Heap[1] = *((_OWORD *)v36 + 1);
    *((_QWORD *)Heap + 4) = v36[4];
    *((_DWORD *)Heap + 9) = a3;
    v40 = *((_DWORD *)Heap + 2) == 65543;
    *((_DWORD *)Heap + 8) = a3 & 1;
    if ( v40 )
      *((_DWORD *)Heap + 9) = 128;
    *a1 = Heap;
    return 0;
  }
  v41 = -1073741801;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v41;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v38,
    v39,
    (unsigned int)"Status",
    23,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
    116);
  return v41;
}

```

## disassembly

```asm
0x180010630  mov     [rsp+arg_0], rbx
0x180010635  mov     [rsp+arg_8], rsi
0x18001063a  push    rdi
0x18001063b  sub     rsp, 40h
0x18001063f  mov     edi, r8d
0x180010642  mov     r9, rdx
0x180010645  mov     rsi, rcx
0x180010648  test    rcx, rcx
0x18001064b  jz      loc_1800108FD
0x180010651  test    rdx, rdx
0x180010654  jz      loc_180010988
0x18001065a  mov     r8, cs:off_180084118; "RC4"
0x180010661  mov     rax, rdx
0x180010664  sub     r8, rdx
0x180010667  nop     word ptr [rax+rax+00000000h]
0x180010670  movzx   edx, word ptr [rax]
0x180010673  movzx   ecx, word ptr [rax+r8]
0x180010678  sub     edx, ecx
0x18001067a  jnz     short loc_180010684
0x18001067c  add     rax, 2
0x180010680  test    ecx, ecx
0x180010682  jnz     short loc_180010670
0x180010684  xor     eax, eax
0x180010686  test    edx, edx
0x180010688  jz      loc_180010812
0x18001068e  mov     r8, cs:off_180084188; "AES"
0x180010695  mov     rax, r9
0x180010698  sub     r8, r9
0x18001069b  nop     dword ptr [rax+rax+00h]
0x1800106a0  movzx   edx, word ptr [rax]
0x1800106a3  movzx   ecx, word ptr [rax+r8]
0x1800106a8  sub     edx, ecx
0x1800106aa  jnz     short loc_1800106B4
0x1800106ac  add     rax, 2
0x1800106b0  test    ecx, ecx
0x1800106b2  jnz     short loc_1800106A0
0x1800106b4  mov     eax, 1
0x1800106b9  test    edx, edx
0x1800106bb  jz      loc_180010812
0x1800106c1  mov     r8, cs:off_1800841F8; "DES"
0x1800106c8  mov     rax, r9
0x1800106cb  sub     r8, r9
0x1800106ce  xchg    ax, ax
0x1800106d0  movzx   edx, word ptr [rax]
0x1800106d3  movzx   ecx, word ptr [rax+r8]
0x1800106d8  sub     edx, ecx
0x1800106da  jnz     short loc_1800106E4
0x1800106dc  add     rax, 2
0x1800106e0  test    ecx, ecx
0x1800106e2  jnz     short loc_1800106D0
0x1800106e4  mov     eax, 2
0x1800106e9  test    edx, edx
0x1800106eb  jz      loc_180010812
0x1800106f1  mov     r8, cs:off_180084268; "DESX"
0x1800106f8  mov     rax, r9
0x1800106fb  sub     r8, r9
0x1800106fe  xchg    ax, ax
0x180010700  movzx   edx, word ptr [rax]
0x180010703  movzx   ecx, word ptr [rax+r8]
0x180010708  sub     edx, ecx
0x18001070a  jnz     short loc_180010714
0x18001070c  add     rax, 2
0x180010710  test    ecx, ecx
0x180010712  jnz     short loc_180010700
0x180010714  mov     eax, 3
0x180010719  test    edx, edx
0x18001071b  jz      loc_180010812
0x180010721  mov     r8, cs:off_1800842D8; "3DES"
0x180010728  mov     rax, r9
0x18001072b  sub     r8, r9
0x18001072e  xchg    ax, ax
0x180010730  movzx   edx, word ptr [rax]
0x180010733  movzx   ecx, word ptr [rax+r8]
0x180010738  sub     edx, ecx
0x18001073a  jnz     short loc_180010744
0x18001073c  add     rax, 2
0x180010740  test    ecx, ecx
0x180010742  jnz     short loc_180010730
0x180010744  mov     eax, 4
0x180010749  test    edx, edx
0x18001074b  jz      loc_180010812
0x180010751  mov     r8, cs:off_180084348; "3DES_112"
0x180010758  mov     rax, r9
0x18001075b  sub     r8, r9
0x18001075e  xchg    ax, ax
0x180010760  movzx   edx, word ptr [rax]
0x180010763  movzx   ecx, word ptr [rax+r8]
0x180010768  sub     edx, ecx
0x18001076a  jnz     short loc_180010774
0x18001076c  add     rax, 2
0x180010770  test    ecx, ecx
0x180010772  jnz     short loc_180010760
0x180010774  mov     eax, 5
0x180010779  test    edx, edx
0x18001077b  jz      loc_180010812
0x180010781  mov     r8, cs:off_1800843B8; "RC2"
0x180010788  mov     rax, r9
0x18001078b  sub     r8, r9
0x18001078e  xchg    ax, ax
0x180010790  movzx   edx, word ptr [rax]
0x180010793  movzx   ecx, word ptr [rax+r8]
0x180010798  sub     edx, ecx
0x18001079a  jnz     short loc_1800107A4
0x18001079c  add     rax, 2
0x1800107a0  test    ecx, ecx
0x1800107a2  jnz     short loc_180010790
0x1800107a4  mov     eax, 6
0x1800107a9  test    edx, edx
0x1800107ab  jz      short loc_180010812
0x1800107ad  mov     r8, cs:off_180084428; "XTS-AES"
0x1800107b4  mov     rax, r9
0x1800107b7  sub     r8, r9
0x1800107ba  nop     word ptr [rax+rax+00h]
0x1800107c0  movzx   edx, word ptr [rax]
0x1800107c3  movzx   ecx, word ptr [rax+r8]
0x1800107c8  sub     edx, ecx
0x1800107ca  jnz     short loc_1800107D4
0x1800107cc  add     rax, 2
0x1800107d0  test    ecx, ecx
0x1800107d2  jnz     short loc_1800107C0
0x1800107d4  mov     eax, 7
0x1800107d9  test    edx, edx
0x1800107db  jz      short loc_180010812
0x1800107dd  mov     rdx, cs:off_180084498; "CHACHA20_POLY1305"
0x1800107e4  sub     rdx, r9
0x1800107e7  nop     word ptr [rax+rax+00000000h]
0x1800107f0  movzx   ecx, word ptr [r9]
0x1800107f4  movzx   eax, word ptr [r9+rdx]
0x1800107f9  sub     ecx, eax
0x1800107fb  jnz     short loc_180010805
0x1800107fd  add     r9, 2
0x180010801  test    eax, eax
0x180010803  jnz     short loc_1800107F0
0x180010805  mov     eax, 8
0x18001080a  test    ecx, ecx
0x18001080c  jnz     loc_180010941
0x180010812  test    edi, 0FFFFFFB6h
0x180010818  jnz     loc_180010990
0x18001081e  lfence
0x180010821  imul    rbx, rax, 70h ; 'p'
0x180010825  lea     rcx, rgSymmAlgorithmDefaults
0x18001082c  xor     edx, edx; Flags
0x18001082e  add     rbx, rcx
0x180010831  mov     rcx, gs:60h
0x18001083a  mov     rcx, [rcx+30h]; HeapHandle
0x18001083e  mov     r8d, [rbx]; Size
0x180010841  call    cs:__imp_RtlAllocateHeap
0x180010848  nop     dword ptr [rax+rax+00h]
0x18001084d  mov     rcx, rax
0x180010850  test    rax, rax
0x180010853  jz      short loc_1800108A0
0x180010855  movups  xmm0, xmmword ptr [rbx]
0x180010858  movups  xmmword ptr [rax], xmm0
0x18001085b  movups  xmm1, xmmword ptr [rbx+10h]
0x18001085f  movups  xmmword ptr [rax+10h], xmm1
0x180010863  movsd   xmm0, qword ptr [rbx+20h]
0x180010868  movsd   qword ptr [rax+20h], xmm0
0x18001086d  mov     eax, edi
0x18001086f  and     eax, 1
0x180010872  mov     [rcx+24h], edi
0x180010875  cmp     dword ptr [rcx+8], 10007h
0x18001087c  mov     [rcx+20h], eax
0x18001087f  jnz     short loc_180010888
0x180010881  mov     dword ptr [rcx+24h], 80h
0x180010888  mov     [rsi], rcx
0x18001088b  xor     ebx, ebx
0x18001088d  mov     eax, ebx
0x18001088f  mov     rbx, [rsp+48h+arg_0]
0x180010894  mov     rsi, [rsp+48h+arg_8]
0x180010899  add     rsp, 40h
0x18001089d  pop     rdi
0x18001089e  retn
0x1800108a0  mov     ebx, 0C0000017h
0x1800108a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108ac  lea     rax, WPP_GLOBAL_Control
0x1800108b3  cmp     rcx, rax
0x1800108b6  jz      short loc_18001088D
0x1800108b8  test    byte ptr [rcx+1Ch], 1
0x1800108bc  jz      short loc_18001088D
0x1800108be  mov     [rsp+48h+var_18], 174h
0x1800108c6  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800108cd  mov     [rsp+48h+var_20], rax
0x1800108d2  mov     [rsp+48h+var_28], 0C0000017h
0x1800108da  mov     rcx, [rcx+10h]
0x1800108de  lea     r9, aStatus; "Status"
0x1800108e5  call    WPP_SF_sDsd
0x1800108ea  mov     rsi, [rsp+48h+arg_8]
0x1800108ef  mov     eax, ebx
0x1800108f1  mov     rbx, [rsp+48h+arg_0]
0x1800108f6  add     rsp, 40h
0x1800108fa  pop     rdi
0x1800108fb  retn
0x1800108fd  mov     ebx, 0C000000Dh
0x180010902  mov     rcx, cs:WPP_GLOBAL_Control
0x180010909  lea     rax, WPP_GLOBAL_Control
0x180010910  cmp     rcx, rax
0x180010913  jz      loc_18001088D
0x180010919  test    byte ptr [rcx+1Ch], 1
0x18001091d  jz      loc_18001088D
0x180010923  mov     [rsp+48h+var_18], 14Ah
0x18001092b  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010932  mov     [rsp+48h+var_20], rax
0x180010937  mov     [rsp+48h+var_28], 0C000000Dh
0x18001093f  jmp     short loc_1800108DA
0x180010941  mov     ebx, 0C00000BBh
0x180010946  mov     rcx, cs:WPP_GLOBAL_Control
0x18001094d  lea     rax, WPP_GLOBAL_Control
0x180010954  cmp     rcx, rax
0x180010957  jz      loc_18001088D
0x18001095d  test    byte ptr [rcx+1Ch], 1
0x180010961  jz      loc_18001088D
0x180010967  mov     [rsp+48h+var_18], 15Eh
0x18001096f  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010976  mov     [rsp+48h+var_20], rax
0x18001097b  mov     [rsp+48h+var_28], 0C00000BBh
0x180010983  jmp     loc_1800108DA
0x180010988  mov     r9d, 151h
0x18001098e  jmp     short loc_180010996
0x180010990  mov     r9d, 167h
0x180010996  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001099d  mov     ecx, 0C000000Dh
0x1800109a2  lea     rdx, aStatus; "Status"
0x1800109a9  mov     ebx, 0C000000Dh
0x1800109ae  call    DebugTraceError
0x1800109b3  jmp     loc_18001088D
```
