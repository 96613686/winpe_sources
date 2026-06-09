# I_CryptXmlCheckUniqueId

- ea: `0x180006da0`
- end: `0x1800070c7`
- name: `I_CryptXmlCheckUniqueId`
- size: `807`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int, int)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003650`
- `0x180003fb0`
- `0x180006150`
- `0x18000b3b0`
- `0x1800160e4`
- `0x180016820`
- `0x180017224`

## callees

- `0x180006da0`
- `0x1800070d0`
- `0x180014ce0`
- `0x1800170a0`
- `0x18001860d`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006e59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006e59`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180006f24`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180006f24`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007015`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007015`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000702d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180007049`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000702d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180007049`

## string_xrefs

- `0x180006f3c`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180006f75`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180006fbb`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180007084`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlCheckUniqueId(__int64 a1, const WCHAR *a2, unsigned int a3, int a4)
{
  unsigned int cchCount2; // edi
  void (__fastcall *v8)(__int64); // rax
  const WCHAR *v9; // rsi
  unsigned int v10; // ebp
  char *v11; // r10
  DWORD v12; // edx
  char *v13; // rax
  _DWORD *v14; // rsi
  void (__fastcall *v15)(__int64); // rax
  int v17; // ecx
  unsigned __int64 v18; // r9
  char *v19; // rax
  const char *v20; // rax
  const char *v21; // r8
  char v22; // al
  const char *v23; // rdx
  bool v24; // zf
  const char *v25; // r8
  char v26; // al
  const char *v27; // rdx
  bool v28; // zf
  const char *v29; // rax

  cchCount2 = a3;
  if ( a3 == -1 )
    cchCount2 = lstrlenW(a2);
  v8 = *(void (__fastcall **)(__int64))(a1 + 120);
  if ( v8 )
    v8(a1);
  if ( cchCount2 > 0x100 )
  {
    v10 = -2146885375;
    v21 = "";
    while ( 1 )
    {
      v22 = *(v21 - 1);
      v23 = v21--;
      v24 = v22 == 92;
      if ( v22 == 92 )
        break;
      if ( v21 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
      {
        v24 = v22 == 92;
        break;
      }
    }
    if ( v24 )
      v21 = v23;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885375, v21, 876);
  }
  else
  {
    if ( ((*(_DWORD *)(a1 + 60) & 0x20000000) != 0 || (*(_DWORD *)(a1 + 60) & 0x8000000) != 0)
      && !(unsigned int)IsValidNameFormat(a2, cchCount2, (*(_DWORD *)(a1 + 60) & 0x20000000) != 0) )
    {
      v10 = -2146885360;
      v29 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885360, v29, 888);
      goto LABEL_14;
    }
    v9 = *(const WCHAR **)(a1 + 184);
    if ( v9 )
    {
      while ( *v9 )
      {
        if ( CompareStringW(0, 0, v9, -1, a2, cchCount2) == 2 )
        {
          v10 = -2146885358;
          goto LABEL_14;
        }
        v9 += lstrlenW(v9) + 1;
      }
    }
    v10 = 0;
    if ( a4 )
    {
      v11 = *(char **)(a1 + 184);
      v12 = ((*(int *)(a1 + 60) >> 31) & 1) + 8;
      if ( v11 )
      {
        v14 = (_DWORD *)(a1 + 192);
        v17 = *(_DWORD *)(a1 + 192);
        v18 = cchCount2 + v17 + 2;
        if ( (v17 & 0xFFFFFC00) + 1024 < v18 )
        {
          v19 = (char *)HeapReAlloc(*(HANDLE *)(a1 + 48), v12, *(LPVOID *)(a1 + 184), ((v18 >> 10) + 1) << 11);
          v11 = v19;
          if ( !v19 )
          {
            v10 = -2147024882;
            v20 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v20, 957);
            goto LABEL_14;
          }
          *(_QWORD *)(a1 + 184) = v19;
        }
LABEL_13:
        memcpy_0(&v11[2 * *v14], a2, 2LL * cchCount2);
        *v14 += cchCount2;
        *(_WORD *)(*(_QWORD *)(a1 + 184) + 2LL * (unsigned int)(*v14)++) = 0;
        *(_WORD *)(*(_QWORD *)(a1 + 184) + 2LL * (unsigned int)*v14) = 0;
        goto LABEL_14;
      }
      v13 = (char *)HeapAlloc(*(HANDLE *)(a1 + 48), v12, 2LL * (((cchCount2 + 2) & 0xFFFFFC00) + 1024));
      *(_QWORD *)(a1 + 184) = v13;
      v11 = v13;
      if ( v13 )
      {
        v14 = (_DWORD *)(a1 + 192);
        goto LABEL_13;
      }
      v10 = -2147024882;
      v25 = "";
      while ( 1 )
      {
        v26 = *(v25 - 1);
        v27 = v25--;
        v28 = v26 == 92;
        if ( v26 == 92 )
          break;
        if ( v25 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
        {
          v28 = v26 == 92;
          break;
        }
      }
      if ( v28 )
        v25 = v27;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v25, 935);
    }
  }
LABEL_14:
  v15 = *(void (__fastcall **)(__int64))(a1 + 128);
  if ( v15 )
    v15(a1);
  return v10;
}

```

## disassembly

```asm
0x180006da0  push    rbx
0x180006da2  sub     rsp, 40h
0x180006da6  mov     [rsp+48h+arg_10], rdi
0x180006dab  mov     edi, r8d
0x180006dae  mov     [rsp+48h+var_10], r14
0x180006db3  mov     r14d, r9d
0x180006db6  mov     [rsp+48h+var_18], r15
0x180006dbb  mov     r15, rdx
0x180006dbe  mov     rbx, rcx
0x180006dc1  cmp     r8d, 0FFFFFFFFh
0x180006dc5  jz      loc_180007046
0x180006dcb  mov     rax, [rbx+78h]
0x180006dcf  test    rax, rax
0x180006dd2  jnz     loc_18000705C
0x180006dd8  mov     [rsp+48h+arg_0], rbp
0x180006ddd  cmp     edi, 100h
0x180006de3  ja      loc_180006F69
0x180006de9  mov     eax, [rbx+3Ch]
0x180006dec  mov     ecx, eax
0x180006dee  and     ecx, 20000000h
0x180006df4  jnz     loc_180007069
0x180006dfa  bt      eax, 1Bh
0x180006dfe  jb      loc_180007069
0x180006e04  mov     [rsp+48h+arg_8], rsi
0x180006e09  mov     rsi, [rbx+0B8h]
0x180006e10  test    rsi, rsi
0x180006e13  jnz     loc_180006FF5
0x180006e19  xor     ebp, ebp
0x180006e1b  test    r14d, r14d
0x180006e1e  jz      loc_180006EB7
0x180006e24  mov     edx, [rbx+3Ch]
0x180006e27  mov     r10, [rbx+0B8h]
0x180006e2e  sar     edx, 1Fh
0x180006e31  and     edx, 1
0x180006e34  add     edx, 8; dwFlags
0x180006e37  test    r10, r10
0x180006e3a  jnz     loc_180006EED
0x180006e40  mov     rcx, [rbx+30h]; hHeap
0x180006e44  lea     r8d, [rdi+2]
0x180006e48  and     r8d, 0FFFFFC00h
0x180006e4f  add     r8d, 400h
0x180006e56  add     r8, r8; dwBytes
0x180006e59  call    cs:__imp_HeapAlloc
0x180006e60  nop     dword ptr [rax+rax+00h]
0x180006e65  mov     [rbx+0B8h], rax
0x180006e6c  mov     r10, rax
0x180006e6f  test    rax, rax
0x180006e72  jz      loc_180006FAF
0x180006e78  lea     rsi, [rbx+0C0h]
0x180006e7f  mov     eax, [rsi]
0x180006e81  mov     rdx, r15; Src
0x180006e84  mov     r8d, edi
0x180006e87  add     r8, r8; Size
0x180006e8a  lea     rcx, [r10+rax*2]; void *
0x180006e8e  call    memcpy_0
0x180006e93  add     [rsi], edi
0x180006e95  xor     eax, eax
0x180006e97  mov     edx, [rsi]
0x180006e99  mov     rcx, [rbx+0B8h]
0x180006ea0  mov     [rcx+rdx*2], ax
0x180006ea4  inc     dword ptr [rsi]
0x180006ea6  mov     r8d, [rsi]
0x180006ea9  xor     ecx, ecx
0x180006eab  mov     rdx, [rbx+0B8h]
0x180006eb2  mov     [rdx+r8*2], cx
0x180006eb7  mov     rsi, [rsp+48h+arg_8]
0x180006ebc  mov     rax, [rbx+80h]
0x180006ec3  mov     r15, [rsp+48h+var_18]
0x180006ec8  mov     r14, [rsp+48h+var_10]
0x180006ecd  mov     rdi, [rsp+48h+arg_10]
0x180006ed2  test    rax, rax
0x180006ed5  jz      short loc_180006EDF
0x180006ed7  mov     rcx, rbx
0x180006eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006edf  mov     eax, ebp
0x180006ee1  mov     rbp, [rsp+48h+arg_0]
0x180006ee6  add     rsp, 40h
0x180006eea  pop     rbx
0x180006eeb  retn
0x180006eed  lea     rsi, [rbx+0C0h]
0x180006ef4  mov     ecx, [rsi]
0x180006ef6  lea     r9d, [rcx+2]
0x180006efa  and     ecx, 0FFFFFC00h
0x180006f00  add     r9d, edi
0x180006f03  lea     eax, [rcx+400h]
0x180006f09  cmp     rax, r9
0x180006f0c  jnb     loc_180006E7F
0x180006f12  mov     rcx, [rbx+30h]; hHeap
0x180006f16  mov     r8, r10; lpMem
0x180006f19  shr     r9, 0Ah
0x180006f1d  inc     r9
0x180006f20  shl     r9, 0Bh; dwBytes
0x180006f24  call    cs:__imp_HeapReAlloc
0x180006f2b  nop     dword ptr [rax+rax+00h]
0x180006f30  mov     r10, rax
0x180006f33  test    rax, rax
0x180006f36  jnz     loc_1800070BB
0x180006f3c  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180006f43  mov     ebp, 8007000Eh
0x180006f48  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180006f4d  mov     r8, rax
0x180006f50  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180006f57  mov     edx, ebp
0x180006f59  mov     r9d, 3BDh
0x180006f5f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180006f64  jmp     loc_180006EB7
0x180006f69  mov     ebp, 80092101h
0x180006f6e  lea     r8, aOnecoreDsSecur_12+2Eh; ""
0x180006f75  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180006f7c  movzx   eax, byte ptr [r8-1]
0x180006f81  mov     rdx, r8
0x180006f84  dec     r8
0x180006f87  cmp     al, 5Ch ; '\'
0x180006f89  jz      short loc_180006F92
0x180006f8b  cmp     r8, rcx
0x180006f8e  ja      short loc_180006F7C
0x180006f90  cmp     al, 5Ch ; '\'
0x180006f92  cmovz   r8, rdx
0x180006f96  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180006f9d  mov     edx, ebp
0x180006f9f  mov     r9d, 36Ch
0x180006fa5  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180006faa  jmp     loc_180006EBC
0x180006faf  mov     ebp, 8007000Eh
0x180006fb4  lea     r8, aOnecoreDsSecur_12+2Eh; ""
0x180006fbb  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180006fc2  movzx   eax, byte ptr [r8-1]
0x180006fc7  mov     rdx, r8
0x180006fca  dec     r8
0x180006fcd  cmp     al, 5Ch ; '\'
0x180006fcf  jz      short loc_180006FD8
0x180006fd1  cmp     r8, rcx
0x180006fd4  ja      short loc_180006FC2
0x180006fd6  cmp     al, 5Ch ; '\'
0x180006fd8  cmovz   r8, rdx
0x180006fdc  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180006fe3  mov     edx, ebp
0x180006fe5  mov     r9d, 3A7h
0x180006feb  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180006ff0  jmp     loc_180006EB7
0x180006ff5  cmp     word ptr [rsi], 0
0x180006ff9  jz      loc_180006E19
0x180006fff  mov     [rsp+48h+cchCount2], edi; cchCount2
0x180007003  mov     r9d, 0FFFFFFFFh; cchCount1
0x180007009  mov     r8, rsi; lpString1
0x18000700c  mov     [rsp+48h+lpString2], r15; lpString2
0x180007011  xor     edx, edx; dwCmpFlags
0x180007013  xor     ecx, ecx; Locale
0x180007015  call    cs:__imp_CompareStringW
0x18000701c  nop     dword ptr [rax+rax+00h]
0x180007021  cmp     eax, 2
0x180007024  jz      loc_1800070B1
0x18000702a  mov     rcx, rsi; lpString
0x18000702d  call    cs:__imp_lstrlenW
0x180007034  nop     dword ptr [rax+rax+00h]
0x180007039  movsxd  rcx, eax
0x18000703c  lea     rsi, [rsi+rcx*2]
0x180007040  add     rsi, 2
0x180007044  jmp     short loc_180006FF5
0x180007046  mov     rcx, r15; lpString
0x180007049  call    cs:__imp_lstrlenW
0x180007050  nop     dword ptr [rax+rax+00h]
0x180007055  mov     edi, eax
0x180007057  jmp     loc_180006DCB
0x18000705c  mov     rcx, rbx
0x18000705f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007064  jmp     loc_180006DD8
0x180007069  xor     r8d, r8d
0x18000706c  mov     edx, edi
0x18000706e  test    ecx, ecx
0x180007070  mov     rcx, r15
0x180007073  setnz   r8b
0x180007077  call    _IsValidNameFormat
0x18000707c  test    eax, eax
0x18000707e  jnz     loc_180006E04
0x180007084  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000708b  mov     ebp, 80092110h
0x180007090  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007095  mov     r8, rax
0x180007098  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000709f  mov     edx, ebp
0x1800070a1  mov     r9d, 378h
0x1800070a7  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800070ac  jmp     loc_180006EBC
0x1800070b1  mov     ebp, 80092112h
0x1800070b6  jmp     loc_180006EB7
0x1800070bb  mov     [rbx+0B8h], rax
0x1800070c2  jmp     loc_180006E7F
```
