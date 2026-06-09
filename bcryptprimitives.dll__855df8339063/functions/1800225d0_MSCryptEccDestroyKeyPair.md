# MSCryptEccDestroyKeyPair

- ea: `0x1800225d0`
- end: `0x18002286c`
- name: `MSCryptEccDestroyKeyPair`
- size: `668`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021a40`
- `0x180047560`
- `0x180047620`
- `0x1800476d0`
- `0x180047c50`
- `0x180048430`
- `0x18004fb80`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800215e4`
- `0x1800225d0`
- `0x180022874`
- `0x180023ce0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800226df`
- `ntdll!RtlFreeHeap` at `0x1800226df`

## string_xrefs

- `0x180022852`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`
- `0x1800225da`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccDestroyKeyPair(_DWORD *P, int a2, int a3)
{
  wchar_t **v4; // rsi
  unsigned int i; // ecx
  __int64 v6; // rcx
  unsigned int v7; // r8d
  _BYTE *v8; // rax
  int v9; // r9d
  __int64 v10; // rcx
  wchar_t *v11; // r10
  unsigned int j; // edx
  __int64 k; // rcx
  int v14; // eax
  __int64 result; // rax
  _QWORD *v16; // rcx
  void *v17; // rcx
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // edi

  if ( !P )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        51);
LABEL_27:
      v16 = WPP_GLOBAL_Control;
LABEL_28:
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          v16[2],
          a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          137);
    }
    return 3221225485LL;
  }
  if ( P[1] != 1297304409 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        60);
      goto LABEL_27;
    }
    return 3221225485LL;
  }
  v4 = &off_180084710;
  if ( !a2 )
    v4 = &off_1800847D0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return 3221225485LL;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          116);
        goto LABEL_27;
      }
      goto LABEL_28;
    }
    if ( P[2] == LODWORD(v4[6 * i + 1]) )
      break;
  }
  v6 = *((_QWORD *)P + 3);
  if ( v6 )
  {
    SymCryptEckeyFree(v6);
    *((_QWORD *)P + 3) = 0;
  }
  if ( (P[8] & 1) == 0 )
  {
    v17 = (void *)*((_QWORD *)P + 2);
    if ( v17 )
    {
      result = FreeGenericEccKeyParameters(v17);
      v20 = result;
      if ( (int)result < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v18,
            v19,
            (unsigned int)"Status",
            result,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            154);
          return v20;
        }
        return result;
      }
      *((_QWORD *)P + 2) = 0;
    }
  }
  v7 = *P;
  v8 = P;
  v9 = P[2];
  v10 = (unsigned int)*P;
  if ( *P )
  {
    do
    {
      *v8++ = 0;
      --v10;
    }
    while ( v10 );
  }
  v11 = 0;
  for ( j = 0; j < 4; ++j )
  {
    if ( v9 == LODWORD(v4[6 * j + 1]) )
    {
      v11 = v4[6 * j];
      break;
    }
  }
  for ( k = 0; (unsigned int)k < v7; k = (unsigned int)(k + 1) )
  {
    if ( *((_BYTE *)P + (unsigned int)k) )
    {
      v14 = MSCryptAuditPrimitiveFailure(k, v11, 2438, 0);
      if ( v14 < 0 )
        DebugTraceError((unsigned int)v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c", 491);
      break;
    }
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return 0;
}

```

## disassembly

```asm
0x1800225d0  push    rbx
0x1800225d2  push    rbp
0x1800225d3  push    rsi
0x1800225d4  push    r14
0x1800225d6  sub     rsp, 48h
0x1800225da  lea     rbp, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800225e1  mov     rbx, rcx
0x1800225e4  test    rcx, rcx
0x1800225e7  jz      loc_18002275D
0x1800225ed  cmp     dword ptr [rcx+4], 4D534B59h
0x1800225f4  jnz     loc_1800227A2
0x1800225fa  test    edx, edx
0x1800225fc  lea     rax, off_1800847D0; "ECDH_P256"
0x180022603  lea     rsi, off_180084710; "ECDSA_P256"
0x18002260a  cmovz   rsi, rax
0x18002260e  xor     r14d, r14d
0x180022611  mov     ecx, r14d
0x180022614  cmp     ecx, 4
0x180022617  jnb     loc_18002281E
0x18002261d  mov     eax, ecx
0x18002261f  lea     rax, [rax+rax*2]
0x180022623  add     rax, rax
0x180022626  mov     eax, [rsi+rax*8+8]
0x18002262a  cmp     [rbx+8], eax
0x18002262d  jz      short loc_180022633
0x18002262f  inc     ecx
0x180022631  jmp     short loc_180022614
0x180022633  mov     rcx, [rbx+18h]
0x180022637  test    rcx, rcx
0x18002263a  jz      short loc_180022645
0x18002263c  call    SymCryptEckeyFree
0x180022641  mov     [rbx+18h], r14
0x180022645  test    byte ptr [rbx+20h], 1
0x180022649  mov     [rsp+68h+arg_0], rdi
0x18002264e  jz      loc_18002273C
0x180022654  mov     r8d, [rbx]
0x180022657  mov     rax, rbx
0x18002265a  mov     r9d, [rbx+8]
0x18002265e  mov     ecx, r8d
0x180022661  test    r8, r8
0x180022664  jz      short loc_18002267D
0x180022666  nop     word ptr [rax+rax+00000000h]
0x180022670  mov     [rax], r14b
0x180022673  lea     rax, [rax+1]
0x180022677  sub     rcx, 1
0x18002267b  jnz     short loc_180022670
0x18002267d  mov     r10, r14
0x180022680  mov     edx, r14d
0x180022683  cmp     edx, 4
0x180022686  jnb     short loc_1800226A0
0x180022688  mov     eax, edx
0x18002268a  lea     rax, [rax+rax*2]
0x18002268e  add     rax, rax
0x180022691  cmp     r9d, [rsi+rax*8+8]
0x180022696  jz      short loc_18002269C
0x180022698  inc     edx
0x18002269a  jmp     short loc_180022683
0x18002269c  mov     r10, [rsi+rax*8]
0x1800226a0  mov     ecx, r14d
0x1800226a3  cmp     ecx, r8d
0x1800226a6  jnb     short loc_1800226CD
0x1800226a8  mov     eax, ecx
0x1800226aa  cmp     [rax+rbx], r14b
0x1800226ae  jnz     short loc_1800226B4
0x1800226b0  inc     ecx
0x1800226b2  jmp     short loc_1800226A3
0x1800226b4  xor     r9d, r9d
0x1800226b7  mov     r8d, 986h
0x1800226bd  mov     rdx, r10
0x1800226c0  call    MSCryptAuditPrimitiveFailure
0x1800226c5  test    eax, eax
0x1800226c7  js      loc_18002284C
0x1800226cd  mov     rcx, gs:60h
0x1800226d6  mov     r8, rbx; P
0x1800226d9  xor     edx, edx; Flags
0x1800226db  mov     rcx, [rcx+30h]; HeapHandle
0x1800226df  call    cs:__imp_RtlFreeHeap
0x1800226e6  nop     dword ptr [rax+rax+00h]
0x1800226eb  mov     eax, r14d
0x1800226ee  mov     rdi, [rsp+68h+arg_0]
0x1800226f3  jmp     short loc_180022731
0x1800226f5  mov     [rsp+68h+var_38], 233h
0x1800226fd  mov     rcx, [rcx+10h]
0x180022701  lea     r9, aStatus; "Status"
0x180022708  mov     [rsp+68h+var_40], rbp
0x18002270d  mov     [rsp+68h+var_48], 0C000000Dh
0x180022715  call    WPP_SF_sDsd
0x18002271a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022721  cmp     rcx, rbx
0x180022724  jz      short loc_18002272C
0x180022726  test    byte ptr [rcx+1Ch], 1
0x18002272a  jnz     short loc_18002277B
0x18002272c  mov     eax, 0C000000Dh
0x180022731  add     rsp, 48h
0x180022735  pop     r14
0x180022737  pop     rsi
0x180022738  pop     rbp
0x180022739  pop     rbx
0x18002273a  retn
0x18002273c  mov     rcx, [rbx+10h]; P
0x180022740  test    rcx, rcx
0x180022743  jz      loc_180022654
0x180022749  call    FreeGenericEccKeyParameters
0x18002274e  mov     edi, eax
0x180022750  test    eax, eax
0x180022752  js      short loc_1800227D0
0x180022754  mov     [rbx+10h], r14
0x180022758  jmp     loc_180022654
0x18002275d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022764  lea     rbx, WPP_GLOBAL_Control
0x18002276b  cmp     rcx, rbx
0x18002276e  jz      short loc_18002272C
0x180022770  test    byte ptr [rcx+1Ch], 1
0x180022774  jz      short loc_180022721
0x180022776  jmp     loc_1800226F5
0x18002277b  mov     rcx, [rcx+10h]
0x18002277f  lea     r9, aStatus; "Status"
0x180022786  mov     [rsp+68h+var_38], 0C89h
0x18002278e  mov     [rsp+68h+var_40], rbp
0x180022793  mov     [rsp+68h+var_48], 0C000000Dh
0x18002279b  call    WPP_SF_sDsd
0x1800227a0  jmp     short loc_18002272C
0x1800227a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227a9  lea     rbx, WPP_GLOBAL_Control
0x1800227b0  cmp     rcx, rbx
0x1800227b3  jz      loc_18002272C
0x1800227b9  test    byte ptr [rcx+1Ch], 1
0x1800227bd  jz      loc_180022721
0x1800227c3  mov     [rsp+68h+var_38], 23Ch
0x1800227cb  jmp     loc_1800226FD
0x1800227d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227d7  lea     rbx, WPP_GLOBAL_Control
0x1800227de  cmp     rcx, rbx
0x1800227e1  jz      loc_1800226EE
0x1800227e7  test    byte ptr [rcx+1Ch], 1
0x1800227eb  jz      loc_1800226EE
0x1800227f1  mov     rcx, [rcx+10h]
0x1800227f5  lea     r9, aStatus; "Status"
0x1800227fc  mov     [rsp+68h+var_38], 0C9Ah
0x180022804  mov     [rsp+68h+var_40], rbp
0x180022809  mov     [rsp+68h+var_48], edi
0x18002280d  call    WPP_SF_sDsd
0x180022812  mov     eax, edi
0x180022814  mov     rdi, [rsp+68h+arg_0]
0x180022819  jmp     loc_180022731
0x18002281e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022825  lea     rbx, WPP_GLOBAL_Control
0x18002282c  cmp     rcx, rbx
0x18002282f  jz      loc_18002272C
0x180022835  test    byte ptr [rcx+1Ch], 1
0x180022839  jz      loc_180022721
0x18002283f  mov     [rsp+68h+var_38], 274h
0x180022847  jmp     loc_1800226FD
0x18002284c  mov     r9d, 1EBh
0x180022852  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022859  lea     rdx, aStatus; "Status"
0x180022860  mov     ecx, eax
0x180022862  call    DebugTraceError
0x180022867  jmp     loc_1800226CD
```
