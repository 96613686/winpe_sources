# I_CryptXmlSignatureAddObject

- ea: `0x180017224`
- end: `0x1800173ed`
- name: `I_CryptXmlSignatureAddObject`
- size: `457`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003650`
- `0x180016a0c`

## callees

- `0x180006da0`
- `0x1800070d0`
- `0x180009478`
- `0x180012b24`
- `0x180014ce0`
- `0x180017224`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800172e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800172e2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180017330`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180017330`

## string_xrefs

- `0x180017269`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x1800172aa`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x1800172fc`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18001734a`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlSignatureAddObject(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // edi
  __int64 DocCtxt; // rbp
  const WCHAR *v7; // rdx
  const char *v8; // rax
  int v9; // r9d
  int v10; // edx
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rbp
  unsigned int v14; // r9d
  LPVOID v15; // rcx
  int v16; // r10d
  __int64 v17; // rdx
  int v18; // eax
  void (__fastcall *v19)(__int64); // rax

  v5 = 0;
  DocCtxt = I_CryptXmlGetDocCtxt(a1, a2, a3);
  I_CryptXmlLock(a1);
  if ( *(int *)(DocCtxt + 72) < 0 )
  {
    v7 = *(const WCHAR **)(a2 + 16);
    if ( v7 )
    {
      v5 = I_CryptXmlCheckUniqueId(DocCtxt, v7, 0xFFFFFFFF, 1);
      if ( v5 < 0 )
      {
        v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        v9 = 472;
LABEL_5:
        v10 = v5;
LABEL_6:
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v10, v8, v9);
        goto LABEL_20;
      }
    }
  }
  v11 = *(_QWORD *)(a1 + 144);
  v12 = *(_DWORD *)(v11 + 160);
  if ( (unsigned int)(v12 + 1) >= 0x100 )
  {
    v5 = -2146885375;
    v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
    v9 = 487;
    goto LABEL_5;
  }
  v13 = *(_QWORD *)(a2 + 8);
  v14 = (v12 & 0xFFFFFFE0) + 32;
  if ( !v12 )
  {
    v15 = HeapAlloc(*(HANDLE *)(a1 + 48), 8u, 8LL * v14);
    if ( !v15 )
    {
      v5 = -2147024882;
      v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v9 = 507;
LABEL_15:
      v10 = v16;
      goto LABEL_6;
    }
LABEL_16:
    *(_QWORD *)(*(_QWORD *)(a1 + 144) + 168LL) = v15;
    goto LABEL_17;
  }
  if ( v12 + 1 >= v14 )
  {
    v15 = HeapReAlloc(*(HANDLE *)(a1 + 48), 8u, *(LPVOID *)(v11 + 168), 8LL * ((v12 & 0xFFFFFFE0) + 64));
    if ( !v15 )
    {
      v5 = -2147024882;
      v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v9 = 528;
      goto LABEL_15;
    }
    goto LABEL_16;
  }
LABEL_17:
  *(_QWORD *)(v13 + 80) = a1;
  _InterlockedIncrement((volatile signed __int32 *)(v13 + 56));
  v17 = *(_QWORD *)(a1 + 144);
  v18 = *(_DWORD *)(v17 + 160);
  if ( v18 )
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v17 + 168) + 8LL * (unsigned int)(v18 - 1)) + 8LL) + 96LL) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 168LL)
            + 8LL * (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 144) + 160LL))++) = a2;
LABEL_20:
  v19 = *(void (__fastcall **)(__int64))(a1 + 128);
  if ( v19 )
    v19(a1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017224  push    rbx
0x180017226  push    rbp
0x180017227  push    rsi
0x180017228  push    rdi
0x180017229  sub     rsp, 28h
0x18001722d  mov     rsi, rdx
0x180017230  mov     rbx, rcx
0x180017233  xor     edi, edi
0x180017235  call    I_CryptXmlGetDocCtxt
0x18001723a  mov     rcx, rbx
0x18001723d  mov     rbp, rax
0x180017240  call    I_CryptXmlLock
0x180017245  cmp     [rbp+48h], edi
0x180017248  jge     short loc_180017291
0x18001724a  mov     rdx, [rsi+10h]
0x18001724e  test    rdx, rdx
0x180017251  jz      short loc_180017291
0x180017253  lea     r9d, [rdi+1]
0x180017257  or      r8d, 0FFFFFFFFh
0x18001725b  mov     rcx, rbp
0x18001725e  call    I_CryptXmlCheckUniqueId
0x180017263  mov     edi, eax
0x180017265  test    eax, eax
0x180017267  jns     short loc_180017291
0x180017269  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017270  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017275  mov     r9d, 1D8h
0x18001727b  mov     edx, edi
0x18001727d  mov     r8, rax
0x180017280  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180017287  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001728c  jmp     loc_1800173CD
0x180017291  mov     r8, [rbx+90h]
0x180017298  mov     eax, [r8+0A0h]
0x18001729f  lea     edx, [rax+1]
0x1800172a2  cmp     edx, 100h
0x1800172a8  jb      short loc_1800172C3
0x1800172aa  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800172b1  mov     edi, 80092101h
0x1800172b6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800172bb  mov     r9d, 1E7h
0x1800172c1  jmp     short loc_18001727B
0x1800172c3  mov     rbp, [rsi+8]
0x1800172c7  mov     ecx, eax
0x1800172c9  and     ecx, 0FFFFFFE0h
0x1800172cc  lea     r9d, [rcx+20h]
0x1800172d0  test    eax, eax
0x1800172d2  jnz     short loc_180017313
0x1800172d4  mov     rcx, [rbx+30h]; hHeap
0x1800172d8  lea     edx, [rax+8]; dwFlags
0x1800172db  mov     r8d, r9d
0x1800172de  shl     r8, 3; dwBytes
0x1800172e2  call    cs:__imp_HeapAlloc
0x1800172e9  nop     dword ptr [rax+rax+00h]
0x1800172ee  mov     rcx, rax
0x1800172f1  test    rax, rax
0x1800172f4  jnz     short loc_180017367
0x1800172f6  mov     r10d, 8007000Eh
0x1800172fc  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017303  mov     edi, r10d
0x180017306  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001730b  mov     r9d, 1FBh
0x180017311  jmp     short loc_18001735F
0x180017313  cmp     edx, r9d
0x180017316  jb      short loc_180017375
0x180017318  mov     r8, [r8+0A8h]; lpMem
0x18001731f  lea     r9d, [rcx+40h]
0x180017323  mov     rcx, [rbx+30h]; hHeap
0x180017327  mov     edx, 8; dwFlags
0x18001732c  shl     r9, 3; dwBytes
0x180017330  call    cs:__imp_HeapReAlloc
0x180017337  nop     dword ptr [rax+rax+00h]
0x18001733c  mov     rcx, rax
0x18001733f  test    rax, rax
0x180017342  jnz     short loc_180017367
0x180017344  mov     r10d, 8007000Eh
0x18001734a  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017351  mov     edi, r10d
0x180017354  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017359  mov     r9d, 210h
0x18001735f  mov     edx, r10d
0x180017362  jmp     loc_18001727D
0x180017367  mov     rax, [rbx+90h]
0x18001736e  mov     [rax+0A8h], rcx
0x180017375  mov     [rbp+50h], rbx
0x180017379  lock inc dword ptr [rbp+38h]
0x18001737d  mov     rdx, [rbx+90h]
0x180017384  mov     eax, [rdx+0A0h]
0x18001738a  test    eax, eax
0x18001738c  jz      short loc_1800173A8
0x18001738e  lea     ecx, [rax-1]
0x180017391  mov     rax, [rdx+0A8h]
0x180017398  mov     rcx, [rax+rcx*8]
0x18001739c  mov     rax, [rsi+8]
0x1800173a0  mov     rdx, [rcx+8]
0x1800173a4  mov     [rdx+60h], rax
0x1800173a8  mov     rax, [rbx+90h]
0x1800173af  mov     ecx, [rax+0A0h]
0x1800173b5  mov     rax, [rax+0A8h]
0x1800173bc  mov     [rax+rcx*8], rsi
0x1800173c0  mov     rax, [rbx+90h]
0x1800173c7  inc     dword ptr [rax+0A0h]
0x1800173cd  mov     rax, [rbx+80h]
0x1800173d4  test    rax, rax
0x1800173d7  jz      short loc_1800173E1
0x1800173d9  mov     rcx, rbx
0x1800173dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173e1  mov     eax, edi
0x1800173e3  add     rsp, 28h
0x1800173e7  pop     rdi
0x1800173e8  pop     rsi
0x1800173e9  pop     rbp
0x1800173ea  pop     rbx
0x1800173eb  retn
```
