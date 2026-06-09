# I_CryptXmlObjectAddReference

- ea: `0x1800160e4`
- end: `0x1800162a2`
- name: `I_CryptXmlObjectAddReference`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003650`

## callees

- `0x180006da0`
- `0x1800070d0`
- `0x180009478`
- `0x180012b24`
- `0x180014ce0`
- `0x1800160e4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800161a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800161a9`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800161f7`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800161f7`

## string_xrefs

- `0x180016129`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x180016167`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x1800161c3`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x180016211`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlObjectAddReference(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // edi
  __int64 DocCtxt; // rsi
  const WCHAR *v7; // rdx
  const char *v8; // rax
  int v9; // r9d
  int v10; // edx
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rsi
  unsigned int v14; // r9d
  void *v15; // rcx
  LPVOID v16; // rcx
  int v17; // r10d
  __int64 v18; // rdx
  int v19; // eax
  void (__fastcall *v20)(__int64); // rax

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
        v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
        v9 = 262;
LABEL_5:
        v10 = v5;
LABEL_6:
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v10, v8, v9);
        goto LABEL_20;
      }
    }
  }
  v11 = *(_QWORD *)(a1 + 136);
  v12 = *(_DWORD *)(v11 + 40);
  if ( (unsigned int)(v12 + 1) >= 0x7FF8 )
  {
    v5 = -2146885375;
    v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
    v9 = 277;
    goto LABEL_5;
  }
  v13 = *(_QWORD *)(a2 + 8);
  v14 = (v12 & 0xFFFFFF00) + 256;
  if ( !v12 )
  {
    v15 = *(void **)(a1 + 48);
    *(_QWORD *)(a1 + 88) = v13;
    v16 = HeapAlloc(v15, 8u, 8LL * v14);
    if ( !v16 )
    {
      v5 = -2147024882;
      v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
      v9 = 300;
LABEL_15:
      v10 = v17;
      goto LABEL_6;
    }
LABEL_16:
    *(_QWORD *)(*(_QWORD *)(a1 + 136) + 48LL) = v16;
    goto LABEL_17;
  }
  if ( v12 + 1 >= v14 )
  {
    v16 = HeapReAlloc(*(HANDLE *)(a1 + 48), 8u, *(LPVOID *)(v11 + 48), 8LL * ((v12 & 0xFFFFFF00) + 512));
    if ( !v16 )
    {
      v5 = -2147024882;
      v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
      v9 = 320;
      goto LABEL_15;
    }
    goto LABEL_16;
  }
LABEL_17:
  *(_QWORD *)(v13 + 80) = a1;
  _InterlockedIncrement((volatile signed __int32 *)(v13 + 56));
  v18 = *(_QWORD *)(a1 + 136);
  v19 = *(_DWORD *)(v18 + 40);
  if ( v19 )
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v18 + 48) + 8LL * (unsigned int)(v19 - 1)) + 8LL) + 96LL) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 48LL)
            + 8LL * (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 136) + 40LL))++) = a2;
LABEL_20:
  v20 = *(void (__fastcall **)(__int64))(a1 + 128);
  if ( v20 )
    v20(a1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800160e4  push    rbx
0x1800160e6  push    rbp
0x1800160e7  push    rsi
0x1800160e8  push    rdi
0x1800160e9  sub     rsp, 28h
0x1800160ed  mov     rbp, rdx
0x1800160f0  mov     rbx, rcx
0x1800160f3  xor     edi, edi
0x1800160f5  call    I_CryptXmlGetDocCtxt
0x1800160fa  mov     rcx, rbx
0x1800160fd  mov     rsi, rax
0x180016100  call    I_CryptXmlLock
0x180016105  cmp     [rsi+48h], edi
0x180016108  jge     short loc_180016151
0x18001610a  mov     rdx, [rbp+10h]
0x18001610e  test    rdx, rdx
0x180016111  jz      short loc_180016151
0x180016113  lea     r9d, [rdi+1]
0x180016117  or      r8d, 0FFFFFFFFh
0x18001611b  mov     rcx, rsi
0x18001611e  call    I_CryptXmlCheckUniqueId
0x180016123  mov     edi, eax
0x180016125  test    eax, eax
0x180016127  jns     short loc_180016151
0x180016129  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016130  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016135  mov     r9d, 106h
0x18001613b  mov     edx, edi
0x18001613d  mov     r8, rax
0x180016140  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180016147  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001614c  jmp     loc_180016282
0x180016151  mov     r8, [rbx+88h]
0x180016158  mov     eax, [r8+28h]
0x18001615c  lea     edx, [rax+1]
0x18001615f  cmp     edx, 7FF8h
0x180016165  jb      short loc_180016180
0x180016167  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001616e  mov     edi, 80092101h
0x180016173  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016178  mov     r9d, 115h
0x18001617e  jmp     short loc_18001613B
0x180016180  mov     rsi, [rbp+8]
0x180016184  mov     ecx, eax
0x180016186  and     ecx, 0FFFFFF00h
0x18001618c  lea     r9d, [rcx+100h]
0x180016193  test    eax, eax
0x180016195  jnz     short loc_1800161DA
0x180016197  mov     rcx, [rbx+30h]; hHeap
0x18001619b  lea     edx, [rax+8]; dwFlags
0x18001619e  mov     r8d, r9d
0x1800161a1  shl     r8, 3; dwBytes
0x1800161a5  mov     [rbx+58h], rsi
0x1800161a9  call    cs:__imp_HeapAlloc
0x1800161b0  nop     dword ptr [rax+rax+00h]
0x1800161b5  mov     rcx, rax
0x1800161b8  test    rax, rax
0x1800161bb  jnz     short loc_18001622E
0x1800161bd  mov     r10d, 8007000Eh
0x1800161c3  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800161ca  mov     edi, r10d
0x1800161cd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800161d2  mov     r9d, 12Ch
0x1800161d8  jmp     short loc_180016226
0x1800161da  cmp     edx, r9d
0x1800161dd  jb      short loc_180016239
0x1800161df  mov     r8, [r8+30h]; lpMem
0x1800161e3  lea     r9d, [rcx+200h]
0x1800161ea  mov     rcx, [rbx+30h]; hHeap
0x1800161ee  mov     edx, 8; dwFlags
0x1800161f3  shl     r9, 3; dwBytes
0x1800161f7  call    cs:__imp_HeapReAlloc
0x1800161fe  nop     dword ptr [rax+rax+00h]
0x180016203  mov     rcx, rax
0x180016206  test    rax, rax
0x180016209  jnz     short loc_18001622E
0x18001620b  mov     r10d, 8007000Eh
0x180016211  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016218  mov     edi, r10d
0x18001621b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016220  mov     r9d, 140h
0x180016226  mov     edx, r10d
0x180016229  jmp     loc_18001613D
0x18001622e  mov     rax, [rbx+88h]
0x180016235  mov     [rax+30h], rcx
0x180016239  mov     [rsi+50h], rbx
0x18001623d  lock inc dword ptr [rsi+38h]
0x180016241  mov     rdx, [rbx+88h]
0x180016248  mov     eax, [rdx+28h]
0x18001624b  test    eax, eax
0x18001624d  jz      short loc_180016266
0x18001624f  lea     ecx, [rax-1]
0x180016252  mov     rax, [rdx+30h]
0x180016256  mov     rcx, [rax+rcx*8]
0x18001625a  mov     rax, [rbp+8]
0x18001625e  mov     rdx, [rcx+8]
0x180016262  mov     [rdx+60h], rax
0x180016266  mov     rax, [rbx+88h]
0x18001626d  mov     ecx, [rax+28h]
0x180016270  mov     rax, [rax+30h]
0x180016274  mov     [rax+rcx*8], rbp
0x180016278  mov     rax, [rbx+88h]
0x18001627f  inc     dword ptr [rax+28h]
0x180016282  mov     rax, [rbx+80h]
0x180016289  test    rax, rax
0x18001628c  jz      short loc_180016296
0x18001628e  mov     rcx, rbx
0x180016291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016296  mov     eax, edi
0x180016298  add     rsp, 28h
0x18001629c  pop     rdi
0x18001629d  pop     rsi
0x18001629e  pop     rbp
0x18001629f  pop     rbx
0x1800162a0  retn
```
