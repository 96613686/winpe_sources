# MSCryptGetDHProperty

- ea: `0x1800685a0`
- end: `0x1800686d9`
- name: `MSCryptGetDHProperty`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18005229c`
- `0x180068378`
- `0x1800685a0`
- `0x18007f765`

## string_xrefs

- `0x1800686b8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetDHProperty(_DWORD *a1, const wchar_t *a2, __int64 a3, unsigned int a4, _DWORD *a5, int a6)
{
  unsigned int v10; // ebx
  int DHAlgProperty; // eax
  __int64 v12; // r9
  __int64 v13; // rcx

  if ( !a1 || !a2 || !a5 || a6 )
  {
    v12 = 601;
    goto LABEL_19;
  }
  if ( wcscmp_0(a2, L"AlgorithmName") )
  {
    if ( a1[1] == 1297301836 )
    {
      DHAlgProperty = MSCryptGetDHAlgProperty(a1, a2, (_DWORD *)a3, a4, a5, 0);
      v10 = DHAlgProperty;
      if ( DHAlgProperty >= 0 )
        return v10;
      v12 = 643;
      goto LABEL_13;
    }
    if ( a1[1] == 1297304409 )
    {
      DHAlgProperty = MSCryptGetDHKeyPairProperty((__int64)a1, a2, (_DWORD *)a3, a4, a5, 0);
      v10 = DHAlgProperty;
      if ( DHAlgProperty >= 0 )
        return v10;
      v12 = 657;
LABEL_13:
      v13 = (unsigned int)DHAlgProperty;
LABEL_20:
      DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v12);
      return v10;
    }
    v12 = 664;
LABEL_19:
    v13 = 3221225485LL;
    v10 = -1073741811;
    goto LABEL_20;
  }
  v10 = 0;
  *a5 = 6;
  if ( a3 )
  {
    if ( a4 >= 6 )
    {
      *(_DWORD *)a3 = *(_DWORD *)L"DH";
      *(_WORD *)(a3 + 4) = aDh[2];
    }
    else
    {
      return (unsigned int)-1073741789;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800685a0  push    rbx
0x1800685a2  push    rbp
0x1800685a3  push    rsi
0x1800685a4  push    rdi
0x1800685a5  push    r14
0x1800685a7  sub     rsp, 30h
0x1800685ab  mov     r14d, r9d
0x1800685ae  mov     rdi, r8
0x1800685b1  mov     rbx, rdx
0x1800685b4  mov     rbp, rcx
0x1800685b7  test    rcx, rcx
0x1800685ba  jz      loc_1800686A8
0x1800685c0  test    rdx, rdx
0x1800685c3  jz      loc_1800686A8
0x1800685c9  mov     rsi, [rsp+58h+arg_20]
0x1800685d1  test    rsi, rsi
0x1800685d4  jz      loc_1800686A8
0x1800685da  cmp     [rsp+58h+arg_28], 0
0x1800685e2  jnz     loc_1800686A8
0x1800685e8  lea     rdx, aAlgorithmname; "AlgorithmName"
0x1800685ef  mov     rcx, rbx; String1
0x1800685f2  call    wcscmp_0
0x1800685f7  test    eax, eax
0x1800685f9  jnz     short loc_180068634
0x1800685fb  xor     ebx, ebx
0x1800685fd  mov     dword ptr [rsi], 6
0x180068603  test    rdi, rdi
0x180068606  jz      loc_1800686CB
0x18006860c  cmp     r14d, 6
0x180068610  jnb     short loc_18006861C
0x180068612  mov     ebx, 0C0000023h
0x180068617  jmp     loc_1800686CB
0x18006861c  mov     eax, dword ptr cs:aDh; "DH"
0x180068622  mov     [rdi], eax
0x180068624  movzx   eax, word ptr cs:aDh+4; ""
0x18006862b  mov     [rdi+4], ax
0x18006862f  jmp     loc_1800686CB
0x180068634  cmp     dword ptr [rbp+4], 4D53414Ch
0x18006863b  jnz     short loc_18006866B
0x18006863d  mov     [rsp+58h+var_30], 0
0x180068645  mov     r9d, r14d
0x180068648  mov     r8, rdi
0x18006864b  mov     [rsp+58h+var_38], rsi
0x180068650  mov     rdx, rbx
0x180068653  mov     rcx, rbp
0x180068656  call    MSCryptGetDHAlgProperty
0x18006865b  mov     ebx, eax
0x18006865d  test    eax, eax
0x18006865f  jns     short loc_1800686CB
0x180068661  mov     r9d, 283h
0x180068667  mov     ecx, eax
0x180068669  jmp     short loc_1800686B8
0x18006866b  cmp     dword ptr [rbp+4], 4D534B59h
0x180068672  jnz     short loc_1800686A0
0x180068674  mov     [rsp+58h+var_30], 0
0x18006867c  mov     r9d, r14d
0x18006867f  mov     r8, rdi
0x180068682  mov     [rsp+58h+var_38], rsi
0x180068687  mov     rdx, rbx
0x18006868a  mov     rcx, rbp
0x18006868d  call    MSCryptGetDHKeyPairProperty
0x180068692  mov     ebx, eax
0x180068694  test    eax, eax
0x180068696  jns     short loc_1800686CB
0x180068698  mov     r9d, 291h
0x18006869e  jmp     short loc_180068667
0x1800686a0  mov     r9d, 298h
0x1800686a6  jmp     short loc_1800686AE
0x1800686a8  mov     r9d, 259h
0x1800686ae  mov     ecx, 0C000000Dh
0x1800686b3  mov     ebx, 0C000000Dh
0x1800686b8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800686bf  lea     rdx, aStatus; "Status"
0x1800686c6  call    DebugTraceError
0x1800686cb  mov     eax, ebx
0x1800686cd  add     rsp, 30h
0x1800686d1  pop     r14
0x1800686d3  pop     rdi
0x1800686d4  pop     rsi
0x1800686d5  pop     rbp
0x1800686d6  pop     rbx
0x1800686d7  retn
```
