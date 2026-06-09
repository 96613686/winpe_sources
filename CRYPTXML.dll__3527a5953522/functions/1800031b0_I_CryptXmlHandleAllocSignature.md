# I_CryptXmlHandleAllocSignature

- ea: `0x1800031b0`
- end: `0x180003649`
- name: `I_CryptXmlHandleAllocSignature`
- size: `1177`
- prototype: `__int64 __fastcall(HANDLE hHeap, int, int, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800029b0`
- `0x180003fb0`

## callees

- `0x1800031b0`
- `0x180004f60`
- `0x1800070d0`
- `0x180014ce0`
- `0x18001860d`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003275`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000353d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800035d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003275`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000353d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800035d1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003311`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003311`

## string_xrefs

- `0x180003290`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000356d`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x1800035fb`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlHandleAllocSignature(HANDLE hHeap, int a2, int a3, __int64 a4, _QWORD *a5)
{
  __int64 v8; // r8
  __int64 v9; // rcx
  char *v11; // rax
  char *v12; // rbx
  const char *v13; // r8
  char v14; // al
  const char *v15; // rdx
  bool v16; // zf
  __int64 (__fastcall *v18)(); // rax
  __int64 (__fastcall *v19)(); // rcx
  _QWORD *v20; // rax
  _QWORD *v21; // r14
  char *v22; // rsi
  __int64 v23; // rax
  char *v24; // r14
  char *v25; // rsi
  char *v26; // rsi
  char *v27; // rcx
  int v28; // ecx
  unsigned int v29; // edi
  const char *v30; // r8
  char v31; // al
  const char *v32; // rdx
  bool v33; // zf
  int v34; // ecx
  const char *v35; // rax

  v8 = *(unsigned int *)(a4 + 52) + 7LL;
  v9 = 2LL * (unsigned int)(*(_DWORD *)(a4 + 8) + 1) + 7;
  *a5 = 0;
  v11 = (char *)HeapAlloc(
                  hHeap,
                  8u,
                  ((*(unsigned int *)(a4 + 84) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((*(unsigned int *)(a4 + 112) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((*(unsigned int *)(a4 + 124) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((2LL * (unsigned int)(*(_DWORD *)(a4 + 40) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((2LL * (unsigned int)(*(_DWORD *)(a4 + 72) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((2LL * (unsigned int)(*(_DWORD *)(a4 + 24) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
                + (v9 & 0xFFFFFFFFFFFFFFF8uLL)
                + (v8 & 0xFFFFFFFFFFFFFFF8uLL)
                + 2416);
  v12 = v11;
  if ( v11 )
  {
    *((_DWORD *)v11 + 14) = 1;
    *(_DWORD *)v11 = 1145324610;
    *((_QWORD *)v11 + 6) = hHeap;
    *((_DWORD *)v11 + 15) = a3;
    *((_QWORD *)v11 + 14) = I_CRYPT_XML_HANDLE_FREE_SIGNATURE;
    *((_QWORD *)v11 + 8) = 12;
    *((_DWORD *)v11 + 18) = 0;
    *((_QWORD *)v11 + 10) = 0;
    *((_QWORD *)v11 + 11) = 0;
    *((_QWORD *)v11 + 12) = 0;
    if ( a3 < 0 )
    {
      v18 = 0;
      v19 = 0;
    }
    else
    {
      InitializeCriticalSection((LPCRITICAL_SECTION)(v11 + 8));
      v18 = CRYPT_XML_HANDLE_UNLOCK;
      v19 = CRYPT_XML_HANDLE_LOCK;
    }
    *((_QWORD *)v12 + 15) = v19;
    *((_QWORD *)v12 + 16) = v18;
    if ( a2 )
      *((_DWORD *)v12 + 18) |= 0x80000000;
    if ( (a3 & 0x4000000) != 0 )
      *((_DWORD *)v12 + 34) |= 0x4000000u;
    *((_QWORD *)v12 + 18) = v12 + 2240;
    *((_DWORD *)v12 + 560) = 176;
    *((_QWORD *)v12 + 281) = v12;
    v20 = (_QWORD *)*((_QWORD *)v12 + 18);
    v21 = v20 + 22;
    if ( *(_DWORD *)(a4 + 8) )
    {
      v20[2] = v21;
      memcpy_0(v20 + 22, *(const void **)a4, 2LL * *(unsigned int *)(a4 + 8));
      v20 = (_QWORD *)*((_QWORD *)v12 + 18);
      v22 = (char *)v21 + ((2LL * (unsigned int)(*(_DWORD *)(a4 + 8) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    else
    {
      v22 = (char *)(v20 + 22);
    }
    if ( *(_DWORD *)(a4 + 24) )
    {
      v20[4] = v22;
      memcpy_0(v22, *(const void **)(a4 + 16), 2LL * *(unsigned int *)(a4 + 24));
      v22 += (2LL * (unsigned int)(*(_DWORD *)(a4 + 24) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    }
    *(_QWORD *)(*((_QWORD *)v12 + 18) + 48LL) = v22;
    memcpy_0(v22, *(const void **)(a4 + 32), 2LL * *(unsigned int *)(a4 + 40));
    v23 = (unsigned int)(*(_DWORD *)(a4 + 40) + 1);
    v24 = &v22[(2 * v23 + 7) & 0xFFFFFFFFFFFFFFF8uLL];
    if ( *(_DWORD *)(a4 + 52) )
    {
      *(_QWORD *)(*((_QWORD *)v12 + 18) + 64LL) = v24;
      *(_DWORD *)(*((_QWORD *)v12 + 18) + 60LL) = *(_DWORD *)(a4 + 52);
      *(_DWORD *)(*((_QWORD *)v12 + 18) + 56LL) = *(_DWORD *)(a4 + 48);
      memcpy_0(v24, *(const void **)(a4 + 56), *(unsigned int *)(a4 + 52));
      v25 = &v24[(*(unsigned int *)(a4 + 52) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
    }
    else
    {
      v25 = &v22[(2 * v23 + 7) & 0xFFFFFFFFFFFFFFF8uLL];
    }
    *(_QWORD *)(*((_QWORD *)v12 + 18) + 80LL) = v25;
    memcpy_0(v25, *(const void **)(a4 + 64), 2LL * *(unsigned int *)(a4 + 72));
    v26 = &v25[(2LL * (unsigned int)(*(_DWORD *)(a4 + 72) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL];
    if ( *(_DWORD *)(a4 + 84) )
    {
      *(_QWORD *)(*((_QWORD *)v12 + 18) + 96LL) = v26;
      *(_DWORD *)(*((_QWORD *)v12 + 18) + 92LL) = *(_DWORD *)(a4 + 84);
      *(_DWORD *)(*((_QWORD *)v12 + 18) + 88LL) = *(_DWORD *)(a4 + 80);
      memcpy_0(v26, *(const void **)(a4 + 88), *(unsigned int *)(a4 + 84));
      v27 = &v26[(*(unsigned int *)(a4 + 84) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
    }
    else
    {
      v27 = v26;
    }
    *(_QWORD *)(*((_QWORD *)v12 + 18) + 144LL) = v27;
    *(_DWORD *)(*((_QWORD *)v12 + 18) + 136LL) = *(_DWORD *)(a4 + 112);
    memcpy_0(v27, *(const void **)(a4 + 104), *(unsigned int *)(a4 + 112));
    v28 = *(_DWORD *)(a4 + 96);
    if ( !v28
      || (*(_DWORD *)(*((_QWORD *)v12 + 18) + 104LL) = v28,
          (*(_QWORD *)(*((_QWORD *)v12 + 18) + 112LL) = HeapAlloc(hHeap, 8u, 8LL * *(unsigned int *)(a4 + 96))) != 0) )
    {
      v34 = *(_DWORD *)(a4 + 136);
      if ( !v34
        || (*(_DWORD *)(*((_QWORD *)v12 + 18) + 160LL) = v34,
            (*(_QWORD *)(*((_QWORD *)v12 + 18) + 168LL) = HeapAlloc(hHeap, 8u, 8LL * *(unsigned int *)(a4 + 136))) != 0) )
      {
        *a5 = v12;
        _InterlockedIncrement((volatile signed __int32 *)v12 + 14);
        v29 = 0;
      }
      else
      {
        v29 = -2147024882;
        v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v35, 202);
      }
    }
    else
    {
      v29 = -2147024882;
      v30 = "";
      while ( 1 )
      {
        v31 = *(v30 - 1);
        v32 = v30--;
        v33 = v31 == 92;
        if ( v31 == 92 )
          break;
        if ( v30 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
        {
          v33 = v31 == 92;
          break;
        }
      }
      if ( v33 )
        v30 = v32;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v30, 182);
    }
    I_CryptXmlRelease(v12);
    return v29;
  }
  else
  {
    v13 = "";
    while ( 1 )
    {
      v14 = *(v13 - 1);
      v15 = v13--;
      v16 = v14 == 92;
      if ( v14 == 92 )
        break;
      if ( v13 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
      {
        v16 = v14 == 92;
        break;
      }
    }
    if ( v16 )
      v13 = v15;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v13, 77);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800031b0  push    rbx
0x1800031b2  push    rbp
0x1800031b3  push    rsi
0x1800031b4  push    rdi
0x1800031b5  push    r12
0x1800031b7  push    r14
0x1800031b9  push    r15
0x1800031bb  sub     rsp, 20h
0x1800031bf  mov     eax, [r9+8]
0x1800031c3  mov     rbp, rcx
0x1800031c6  mov     r15, [rsp+58h+arg_20]
0x1800031ce  inc     eax
0x1800031d0  mov     esi, r8d
0x1800031d3  mov     r14d, edx
0x1800031d6  mov     r8d, [r9+34h]
0x1800031da  xor     r12d, r12d
0x1800031dd  add     r8, 7
0x1800031e1  mov     edx, 8; dwFlags
0x1800031e6  lea     rcx, ds:7[rax*2]
0x1800031ee  mov     [r15], r12
0x1800031f1  mov     eax, [r9+18h]
0x1800031f5  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800031f9  inc     eax
0x1800031fb  and     r8, 0FFFFFFFFFFFFFFF8h
0x1800031ff  add     r8, 970h
0x180003206  mov     rdi, r9
0x180003209  lea     rax, ds:7[rax*2]
0x180003211  and     rax, 0FFFFFFFFFFFFFFF8h
0x180003215  add     rcx, rax
0x180003218  mov     eax, [r9+48h]
0x18000321c  inc     eax
0x18000321e  lea     rax, ds:7[rax*2]
0x180003226  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000322a  add     rcx, rax
0x18000322d  mov     eax, [r9+28h]
0x180003231  inc     eax
0x180003233  lea     rax, ds:7[rax*2]
0x18000323b  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000323f  add     rcx, rax
0x180003242  mov     eax, [r9+7Ch]
0x180003246  add     rax, 7
0x18000324a  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000324e  add     rcx, rax
0x180003251  mov     eax, [r9+70h]
0x180003255  add     rax, 7
0x180003259  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000325d  add     rcx, rax
0x180003260  mov     eax, [r9+54h]
0x180003264  add     rax, 7
0x180003268  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000326c  add     rcx, rax
0x18000326f  add     r8, rcx; dwBytes
0x180003272  mov     rcx, rbp; hHeap
0x180003275  call    cs:__imp_HeapAlloc
0x18000327c  nop     dword ptr [rax+rax+00h]
0x180003281  mov     rbx, rax
0x180003284  test    rax, rax
0x180003287  jnz     short loc_1800032D2
0x180003289  lea     r8, aOnecoreDsSecur_11+33h; ""
0x180003290  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180003297  movzx   eax, byte ptr [r8-1]
0x18000329c  mov     rdx, r8
0x18000329f  dec     r8
0x1800032a2  cmp     al, 5Ch ; '\'
0x1800032a4  jz      short loc_1800032AD
0x1800032a6  cmp     r8, rcx
0x1800032a9  ja      short loc_180003297
0x1800032ab  cmp     al, 5Ch ; '\'
0x1800032ad  cmovz   r8, rdx
0x1800032b1  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800032b8  mov     edx, 8007000Eh
0x1800032bd  mov     r9d, 4Dh ; 'M'
0x1800032c3  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800032c8  mov     eax, 8007000Eh
0x1800032cd  jmp     loc_180003639
0x1800032d2  mov     dword ptr [rax+38h], 1
0x1800032d9  mov     dword ptr [rax], 44444442h
0x1800032df  mov     [rax+30h], rbp
0x1800032e3  mov     [rax+3Ch], esi
0x1800032e6  lea     rax, ?I_CRYPT_XML_HANDLE_FREE_SIGNATURE@@YAJPEAU_HXML_HANDLE@@@Z; I_CRYPT_XML_HANDLE_FREE_SIGNATURE(_HXML_HANDLE *)
0x1800032ed  mov     [rbx+70h], rax
0x1800032f1  mov     qword ptr [rbx+40h], 0Ch
0x1800032f9  mov     [rbx+48h], r12d
0x1800032fd  mov     [rbx+50h], r12
0x180003301  mov     [rbx+58h], r12
0x180003305  mov     [rbx+60h], r12
0x180003309  test    esi, esi
0x18000330b  js      short loc_18000332D
0x18000330d  lea     rcx, [rbx+8]; lpCriticalSection
0x180003311  call    cs:__imp_InitializeCriticalSection
0x180003318  nop     dword ptr [rax+rax+00h]
0x18000331d  lea     rax, _CRYPT_XML_HANDLE_UNLOCK
0x180003324  lea     rcx, _CRYPT_XML_HANDLE_LOCK
0x18000332b  jmp     short loc_180003333
0x18000332d  mov     rax, r12
0x180003330  mov     rcx, r12
0x180003333  mov     [rbx+78h], rcx
0x180003337  mov     [rbx+80h], rax
0x18000333e  test    r14d, r14d
0x180003341  jz      short loc_18000334A
0x180003343  or      dword ptr [rbx+48h], 80000000h
0x18000334a  bt      esi, 1Ah
0x18000334e  jnb     short loc_18000335A
0x180003350  or      dword ptr [rbx+88h], 4000000h
0x18000335a  lea     rax, [rbx+8C0h]
0x180003361  mov     [rbx+90h], rax
0x180003368  mov     dword ptr [rax], 0B0h
0x18000336e  mov     [rax+8], rbx
0x180003372  mov     rax, [rbx+90h]
0x180003379  lea     r14, [rax+0B0h]
0x180003380  cmp     [rdi+8], r12d
0x180003384  jbe     short loc_1800033B9
0x180003386  mov     [rax+10h], r14
0x18000338a  mov     rcx, r14; void *
0x18000338d  mov     r8d, [rdi+8]
0x180003391  mov     rdx, [rdi]; Src
0x180003394  add     r8, r8; Size
0x180003397  call    memcpy_0
0x18000339c  mov     eax, [rdi+8]
0x18000339f  inc     eax
0x1800033a1  lea     rsi, ds:7[rax*2]
0x1800033a9  mov     rax, [rbx+90h]
0x1800033b0  and     rsi, 0FFFFFFFFFFFFFFF8h
0x1800033b4  add     rsi, r14
0x1800033b7  jmp     short loc_1800033BC
0x1800033b9  mov     rsi, r14
0x1800033bc  cmp     [rdi+18h], r12d
0x1800033c0  jbe     short loc_1800033ED
0x1800033c2  mov     [rax+20h], rsi
0x1800033c6  mov     rcx, rsi; void *
0x1800033c9  mov     r8d, [rdi+18h]
0x1800033cd  mov     rdx, [rdi+10h]; Src
0x1800033d1  add     r8, r8; Size
0x1800033d4  call    memcpy_0
0x1800033d9  mov     eax, [rdi+18h]
0x1800033dc  inc     eax
0x1800033de  lea     rax, ds:7[rax*2]
0x1800033e6  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800033ea  add     rsi, rax
0x1800033ed  mov     rax, [rbx+90h]
0x1800033f4  mov     rcx, rsi; void *
0x1800033f7  mov     [rax+30h], rsi
0x1800033fb  mov     r8d, [rdi+28h]
0x1800033ff  mov     rdx, [rdi+20h]; Src
0x180003403  add     r8, r8; Size
0x180003406  call    memcpy_0
0x18000340b  mov     eax, [rdi+28h]
0x18000340e  inc     eax
0x180003410  lea     r14, ds:7[rax*2]
0x180003418  and     r14, 0FFFFFFFFFFFFFFF8h
0x18000341c  add     r14, rsi
0x18000341f  cmp     [rdi+34h], r12d
0x180003423  jbe     short loc_18000346A
0x180003425  mov     rax, [rbx+90h]
0x18000342c  mov     [rax+40h], r14
0x180003430  mov     rcx, [rbx+90h]
0x180003437  mov     eax, [rdi+34h]
0x18000343a  mov     [rcx+3Ch], eax
0x18000343d  mov     rcx, [rbx+90h]
0x180003444  mov     eax, [rdi+30h]
0x180003447  mov     [rcx+38h], eax
0x18000344a  mov     rcx, r14; void *
0x18000344d  mov     r8d, [rdi+34h]; Size
0x180003451  mov     rdx, [rdi+38h]; Src
0x180003455  call    memcpy_0
0x18000345a  mov     esi, [rdi+34h]
0x18000345d  add     rsi, 7
0x180003461  and     rsi, 0FFFFFFFFFFFFFFF8h
0x180003465  add     rsi, r14
0x180003468  jmp     short loc_18000346D
0x18000346a  mov     rsi, r14
0x18000346d  mov     rax, [rbx+90h]
0x180003474  mov     rcx, rsi; void *
0x180003477  mov     [rax+50h], rsi
0x18000347b  mov     r8d, [rdi+48h]
0x18000347f  mov     rdx, [rdi+40h]; Src
0x180003483  add     r8, r8; Size
0x180003486  call    memcpy_0
0x18000348b  mov     eax, [rdi+48h]
0x18000348e  inc     eax
0x180003490  lea     rax, ds:7[rax*2]
0x180003498  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000349c  add     rsi, rax
0x18000349f  cmp     [rdi+54h], r12d
0x1800034a3  jbe     short loc_1800034EA
0x1800034a5  mov     rax, [rbx+90h]
0x1800034ac  mov     [rax+60h], rsi
0x1800034b0  mov     rcx, [rbx+90h]
0x1800034b7  mov     eax, [rdi+54h]
0x1800034ba  mov     [rcx+5Ch], eax
0x1800034bd  mov     rcx, [rbx+90h]
0x1800034c4  mov     eax, [rdi+50h]
0x1800034c7  mov     [rcx+58h], eax
0x1800034ca  mov     rcx, rsi; void *
0x1800034cd  mov     r8d, [rdi+54h]; Size
0x1800034d1  mov     rdx, [rdi+58h]; Src
0x1800034d5  call    memcpy_0
0x1800034da  mov     ecx, [rdi+54h]
0x1800034dd  add     rcx, 7
0x1800034e1  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800034e5  add     rcx, rsi
0x1800034e8  jmp     short loc_1800034ED
0x1800034ea  mov     rcx, rsi; void *
0x1800034ed  mov     rax, [rbx+90h]
0x1800034f4  mov     [rax+90h], rcx
0x1800034fb  mov     rdx, [rbx+90h]
0x180003502  mov     eax, [rdi+70h]
0x180003505  mov     [rdx+88h], eax
0x18000350b  mov     r8d, [rdi+70h]; Size
0x18000350f  mov     rdx, [rdi+68h]; Src
0x180003513  call    memcpy_0
0x180003518  mov     ecx, [rdi+60h]
0x18000351b  test    ecx, ecx
0x18000351d  jz      loc_1800035A7
0x180003523  mov     rax, [rbx+90h]
0x18000352a  mov     edx, 8; dwFlags
0x18000352f  mov     [rax+68h], ecx
0x180003532  mov     rcx, rbp; hHeap
0x180003535  mov     r8d, [rdi+60h]
0x180003539  shl     r8, 3; dwBytes
0x18000353d  call    cs:__imp_HeapAlloc
0x180003544  nop     dword ptr [rax+rax+00h]
0x180003549  mov     rcx, [rbx+90h]
0x180003550  mov     [rcx+70h], rax
0x180003554  mov     rax, [rbx+90h]
0x18000355b  cmp     [rax+70h], r12
0x18000355f  jnz     short loc_1800035A7
0x180003561  mov     edi, 8007000Eh
0x180003566  lea     r8, aOnecoreDsSecur_11+33h; ""
0x18000356d  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180003574  movzx   eax, byte ptr [r8-1]
0x180003579  mov     rdx, r8
0x18000357c  dec     r8
0x18000357f  cmp     al, 5Ch ; '\'
0x180003581  jz      short loc_18000358A
0x180003583  cmp     r8, rcx
0x180003586  ja      short loc_180003574
0x180003588  cmp     al, 5Ch ; '\'
0x18000358a  cmovz   r8, rdx
0x18000358e  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180003595  mov     edx, edi
0x180003597  mov     r9d, 0B6h
0x18000359d  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800035a2  jmp     loc_18000362F
0x1800035a7  mov     ecx, [rdi+88h]
0x1800035ad  test    ecx, ecx
0x1800035af  jz      short loc_180003625
0x1800035b1  mov     rax, [rbx+90h]
0x1800035b8  mov     edx, 8; dwFlags
0x1800035bd  mov     [rax+0A0h], ecx
0x1800035c3  mov     rcx, rbp; hHeap
0x1800035c6  mov     r8d, [rdi+88h]
0x1800035cd  shl     r8, 3; dwBytes
0x1800035d1  call    cs:__imp_HeapAlloc
0x1800035d8  nop     dword ptr [rax+rax+00h]
0x1800035dd  mov     rcx, [rbx+90h]
0x1800035e4  mov     [rcx+0A8h], rax
0x1800035eb  mov     rax, [rbx+90h]
0x1800035f2  cmp     [rax+0A8h], r12
0x1800035f9  jnz     short loc_180003625
0x1800035fb  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180003602  mov     edi, 8007000Eh
0x180003607  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000360c  mov     r8, rax
0x18000360f  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180003616  mov     edx, edi
0x180003618  mov     r9d, 0CAh
0x18000361e  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180003623  jmp     short loc_18000362F
0x180003625  mov     [r15], rbx
0x180003628  lock inc dword ptr [rbx+38h]
0x18000362c  mov     edi, r12d
0x18000362f  mov     rcx, rbx
0x180003632  call    I_CryptXmlRelease
0x180003637  mov     eax, edi
0x180003639  add     rsp, 20h
0x18000363d  pop     r15
0x18000363f  pop     r14
0x180003641  pop     r12
0x180003643  pop     rdi
0x180003644  pop     rsi
0x180003645  pop     rbp
0x180003646  pop     rbx
0x180003647  retn
```
