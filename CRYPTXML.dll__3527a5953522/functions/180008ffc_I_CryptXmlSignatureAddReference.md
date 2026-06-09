# I_CryptXmlSignatureAddReference

- ea: `0x180008ffc`
- end: `0x180009178`
- name: `I_CryptXmlSignatureAddReference`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003650`

## callees

- `0x1800070d0`
- `0x180008ffc`
- `0x180009478`
- `0x180014ce0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000907d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000907d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800090cb`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800090cb`

## string_xrefs

- `0x180009028`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x180009097`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x1800090e5`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlSignatureAddReference(__int64 a1, __int64 a2)
{
  __int64 v4; // r10
  int v5; // eax
  unsigned int v6; // edi
  const char *v7; // rax
  int v8; // edx
  int v9; // r9d
  __int64 v10; // rsi
  unsigned int v11; // edx
  void *v12; // rcx
  LPVOID v13; // rcx
  int v14; // r10d
  __int64 v15; // rdx
  int v16; // eax
  void (__fastcall *v17)(__int64); // rax

  I_CryptXmlLock(a1);
  v4 = *(_QWORD *)(a1 + 144);
  v5 = *(_DWORD *)(v4 + 104);
  if ( (unsigned int)(v5 + 1) >= 0x7FF8 )
  {
    v6 = -2146885375;
    v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
    v8 = -2146885375;
    v9 = 363;
LABEL_3:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v8, v7, v9);
    goto LABEL_15;
  }
  v10 = *(_QWORD *)(a2 + 8);
  v11 = (v5 & 0xFFFFFF00) + 256;
  if ( !v5 )
  {
    v12 = *(void **)(a1 + 48);
    *(_QWORD *)(a1 + 88) = v10;
    v13 = HeapAlloc(v12, 8u, 8LL * v11);
    if ( !v13 )
    {
      v6 = -2147024882;
      v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v9 = 386;
LABEL_10:
      v8 = v14;
      goto LABEL_3;
    }
LABEL_11:
    *(_QWORD *)(*(_QWORD *)(a1 + 144) + 112LL) = v13;
    goto LABEL_12;
  }
  if ( v5 + 1 >= v11 )
  {
    v13 = HeapReAlloc(*(HANDLE *)(a1 + 48), 8u, *(LPVOID *)(v4 + 112), 8LL * ((v5 & 0xFFFFFF00) + 512));
    if ( !v13 )
    {
      v6 = -2147024882;
      v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v9 = 407;
      goto LABEL_10;
    }
    goto LABEL_11;
  }
LABEL_12:
  v6 = 0;
  *(_QWORD *)(v10 + 80) = a1;
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 56));
  v15 = *(_QWORD *)(a1 + 144);
  v16 = *(_DWORD *)(v15 + 104);
  if ( v16 )
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 112) + 8LL * (unsigned int)(v16 - 1)) + 8LL) + 96LL) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 112LL)
            + 8LL * (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 144) + 104LL))++) = a2;
LABEL_15:
  v17 = *(void (__fastcall **)(__int64))(a1 + 128);
  if ( v17 )
    v17(a1);
  return v6;
}

```

## disassembly

```asm
0x180008ffc  push    rbx
0x180008ffe  push    rbp
0x180008fff  push    rsi
0x180009000  push    rdi
0x180009001  sub     rsp, 28h
0x180009005  mov     rbp, rdx
0x180009008  mov     rbx, rcx
0x18000900b  call    I_CryptXmlLock
0x180009010  mov     r10, [rbx+90h]
0x180009017  mov     eax, [r10+68h]
0x18000901b  lea     r8d, [rax+1]
0x18000901f  cmp     r8d, 7FF8h
0x180009026  jb      short loc_180009055
0x180009028  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000902f  mov     edi, 80092101h
0x180009034  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009039  mov     edx, edi
0x18000903b  mov     r9d, 16Bh
0x180009041  mov     r8, rax
0x180009044  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000904b  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009050  jmp     loc_180009158
0x180009055  mov     rsi, [rbp+8]
0x180009059  mov     ecx, eax
0x18000905b  and     ecx, 0FFFFFF00h
0x180009061  lea     edx, [rcx+100h]
0x180009067  test    eax, eax
0x180009069  jnz     short loc_1800090AE
0x18000906b  mov     rcx, [rbx+30h]; hHeap
0x18000906f  mov     r8d, edx
0x180009072  lea     edx, [rax+8]; dwFlags
0x180009075  shl     r8, 3; dwBytes
0x180009079  mov     [rbx+58h], rsi
0x18000907d  call    cs:__imp_HeapAlloc
0x180009084  nop     dword ptr [rax+rax+00h]
0x180009089  mov     rcx, rax
0x18000908c  test    rax, rax
0x18000908f  jnz     short loc_180009102
0x180009091  mov     r10d, 8007000Eh
0x180009097  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000909e  mov     edi, r10d
0x1800090a1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800090a6  mov     r9d, 182h
0x1800090ac  jmp     short loc_1800090FA
0x1800090ae  cmp     r8d, edx
0x1800090b1  jb      short loc_18000910D
0x1800090b3  mov     r8, [r10+70h]; lpMem
0x1800090b7  lea     r9d, [rcx+200h]
0x1800090be  mov     rcx, [rbx+30h]; hHeap
0x1800090c2  mov     edx, 8; dwFlags
0x1800090c7  shl     r9, 3; dwBytes
0x1800090cb  call    cs:__imp_HeapReAlloc
0x1800090d2  nop     dword ptr [rax+rax+00h]
0x1800090d7  mov     rcx, rax
0x1800090da  test    rax, rax
0x1800090dd  jnz     short loc_180009102
0x1800090df  mov     r10d, 8007000Eh
0x1800090e5  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800090ec  mov     edi, r10d
0x1800090ef  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800090f4  mov     r9d, 197h
0x1800090fa  mov     edx, r10d
0x1800090fd  jmp     loc_180009041
0x180009102  mov     rax, [rbx+90h]
0x180009109  mov     [rax+70h], rcx
0x18000910d  xor     edi, edi
0x18000910f  mov     [rsi+50h], rbx
0x180009113  lock inc dword ptr [rsi+38h]
0x180009117  mov     rdx, [rbx+90h]
0x18000911e  mov     eax, [rdx+68h]
0x180009121  test    eax, eax
0x180009123  jz      short loc_18000913C
0x180009125  lea     ecx, [rax-1]
0x180009128  mov     rax, [rdx+70h]
0x18000912c  mov     rcx, [rax+rcx*8]
0x180009130  mov     rax, [rbp+8]
0x180009134  mov     rdx, [rcx+8]
0x180009138  mov     [rdx+60h], rax
0x18000913c  mov     rax, [rbx+90h]
0x180009143  mov     ecx, [rax+68h]
0x180009146  mov     rax, [rax+70h]
0x18000914a  mov     [rax+rcx*8], rbp
0x18000914e  mov     rcx, [rbx+90h]
0x180009155  inc     dword ptr [rcx+68h]
0x180009158  mov     rax, [rbx+80h]
0x18000915f  test    rax, rax
0x180009162  jz      short loc_18000916C
0x180009164  mov     rcx, rbx
0x180009167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000916c  mov     eax, edi
0x18000916e  add     rsp, 28h
0x180009172  pop     rdi
0x180009173  pop     rsi
0x180009174  pop     rbp
0x180009175  pop     rbx
0x180009176  retn
```
