# I_CRYPT_XML_C14N_DATA_PROVIDER_READ

- ea: `0x180008110`
- end: `0x18000849b`
- name: `I_CRYPT_XML_C14N_DATA_PROVIDER_READ`
- size: `907`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180008110`
- `0x180014ce0`
- `0x18001860d`
- `0x180018619`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008182`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008182`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008156`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800081a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800081f1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000820b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008156`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800081a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800081f1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000820b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800081d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000826e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800081d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000826e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800081bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008256`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800081bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000828a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000838a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000828a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000838a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083fa`

## string_xrefs

- `0x1800082a1`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x180008311`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x18000835f`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x1800083a1`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x1800083d9`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`
- `0x18000840d`: `onecore\ds\security\cryptoapi\xml\lib\c14n.cpp`

## pseudocode

```c
__int64 __fastcall I_CRYPT_XML_C14N_DATA_PROVIDER_READ(__int64 a1, char *a2, unsigned int a3, _DWORD *a4)
{
  int v8; // r15d
  unsigned int v9; // eax
  __int64 v10; // rdi
  void *v11; // rcx
  signed int v12; // eax
  unsigned int v13; // r10d
  const char *v14; // r8
  signed int v15; // r10d
  signed int v16; // edx
  int v17; // r9d
  signed int LastError; // eax
  char v20; // dl
  const char *v21; // r9
  bool v22; // zf
  char v23; // dl
  const char *v24; // r9
  bool v25; // zf
  signed int v26; // eax
  unsigned int v27; // r10d
  signed int v28; // r10d
  signed int v29; // eax
  unsigned int v30; // r10d
  signed int v31; // r10d
  signed int v32; // eax
  unsigned int v33; // r10d
  signed int v34; // r10d
  HANDLE Handles[9]; // [rsp+30h] [rbp-48h] BYREF

  Handles[0] = *(HANDLE *)(a1 + 56);
  Handles[1] = *(HANDLE *)(a1 + 40);
  *a4 = 0;
  v8 = 0;
  while ( WaitForSingleObject(*(HANDLE *)(a1 + 72), 0) )
  {
    if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) > 1 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *(_DWORD *)(a1 + 96) = LastError;
      v14 = "";
      while ( 1 )
      {
        v20 = *(v14 - 1);
        v21 = v14--;
        v22 = v20 == 92;
        if ( v20 == 92 )
          break;
        if ( v14 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp" )
        {
          v22 = v20 == 92;
          break;
        }
      }
      if ( v22 )
        v14 = v21;
      v17 = 375;
      goto LABEL_36;
    }
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 48), 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *(_DWORD *)(a1 + 96) = LastError;
      v14 = "";
      while ( 1 )
      {
        v23 = *(v14 - 1);
        v24 = v14--;
        v25 = v23 == 92;
        if ( v23 == 92 )
          break;
        if ( v14 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp" )
        {
          v25 = v23 == 92;
          break;
        }
      }
      if ( v25 )
        v14 = v24;
      v17 = 393;
LABEL_36:
      v16 = LastError;
LABEL_23:
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v16, v14, v17);
      return *(unsigned int *)(a1 + 96);
    }
    v9 = *(_DWORD *)(a1 + 84);
    if ( v9 )
    {
      if ( v9 >= a3 )
        v9 = a3;
      v10 = v9;
      memcpy_0(a2, *(const void **)(a1 + 88), v9);
      *a4 += v10;
      v22 = *(_DWORD *)(a1 + 84) == (_DWORD)v10;
      *(_DWORD *)(a1 + 84) -= v10;
      if ( !v22 )
        memmove_0(*(void **)(a1 + 88), (const void *)(*(_QWORD *)(a1 + 88) + v10), *(unsigned int *)(a1 + 84));
      v11 = *(void **)(a1 + 64);
      *(_DWORD *)(a1 + 96) = 0;
      if ( !SetEvent(v11) )
      {
        v26 = GetLastError();
        v27 = v26;
        if ( v26 > 0 )
          v27 = (unsigned __int16)v26 | 0x80070000;
        *(_DWORD *)(a1 + 96) = v27;
        v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
        v16 = v28;
        v17 = 442;
        goto LABEL_23;
      }
      if ( !ReleaseMutex(*(HANDLE *)(a1 + 48)) )
      {
        v12 = GetLastError();
        v13 = v12;
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        *(_DWORD *)(a1 + 96) = v13;
        v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
        v16 = v15;
        v17 = 450;
        goto LABEL_23;
      }
      a3 -= v10;
      if ( !a3 )
        return *(unsigned int *)(a1 + 96);
      a2 += v10;
    }
    else
    {
      if ( !SetEvent(*(HANDLE *)(a1 + 64)) )
      {
        v32 = GetLastError();
        v33 = v32;
        if ( v32 > 0 )
          v33 = (unsigned __int16)v32 | 0x80070000;
        *(_DWORD *)(a1 + 96) = v33;
        v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
        v16 = v34;
        v17 = 473;
        goto LABEL_23;
      }
      if ( !ReleaseMutex(*(HANDLE *)(a1 + 48)) )
      {
        v29 = GetLastError();
        v30 = v29;
        if ( v29 > 0 )
          v30 = (unsigned __int16)v29 | 0x80070000;
        *(_DWORD *)(a1 + 96) = v30;
        v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\c14n.cpp");
        v16 = v31;
        v17 = 481;
        goto LABEL_23;
      }
      if ( !WaitForSingleObject(*(HANDLE *)(a1 + 72), 0) )
        return *(unsigned int *)(a1 + 96);
      if ( !WaitForSingleObject(*(HANDLE *)(a1 + 40), 0) )
      {
        if ( v8 )
          return *(unsigned int *)(a1 + 96);
        v8 = 1;
      }
      if ( !a3 )
        return *(unsigned int *)(a1 + 96);
    }
  }
  return *(unsigned int *)(a1 + 96);
}

```

## disassembly

```asm
0x180008110  push    rbx
0x180008112  push    rbp
0x180008113  push    rsi
0x180008114  push    r12
0x180008116  push    r14
0x180008118  push    r15
0x18000811a  sub     rsp, 48h
0x18000811e  mov     rax, [rcx+38h]
0x180008122  xor     r12d, r12d
0x180008125  mov     [rsp+78h+Handles], rax
0x18000812a  mov     r14, r9
0x18000812d  mov     rax, [rcx+28h]
0x180008131  mov     esi, r8d
0x180008134  mov     [rsp+78h+var_40], rax
0x180008139  mov     rbp, rdx
0x18000813c  mov     rbx, rcx
0x18000813f  mov     [r9], r12d
0x180008142  mov     r15d, r12d
0x180008145  mov     [rsp+78h+arg_0], rdi
0x18000814d  nop     dword ptr [rax]
0x180008150  mov     rcx, [rbx+48h]; hHandle
0x180008154  xor     edx, edx; dwMilliseconds
0x180008156  call    cs:__imp_WaitForSingleObject
0x18000815d  nop     dword ptr [rax+rax+00h]
0x180008162  test    eax, eax
0x180008164  jz      loc_1800082C9
0x18000816a  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180008170  mov     [rsp+78h+bAlertable], r12d; bAlertable
0x180008175  xor     r8d, r8d; bWaitAll
0x180008178  lea     rdx, [rsp+78h+Handles]; lpHandles
0x18000817d  mov     ecx, 2; nCount
0x180008182  call    cs:__imp_WaitForMultipleObjectsEx
0x180008189  nop     dword ptr [rax+rax+00h]
0x18000818e  cmp     eax, 1
0x180008191  ja      loc_1800082F3
0x180008197  mov     rcx, [rbx+30h]; hHandle
0x18000819b  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800081a0  call    cs:__imp_WaitForSingleObject
0x1800081a7  nop     dword ptr [rax+rax+00h]
0x1800081ac  test    eax, eax
0x1800081ae  jnz     loc_180008341
0x1800081b4  mov     eax, [rbx+54h]
0x1800081b7  test    eax, eax
0x1800081b9  jnz     short loc_18000822C
0x1800081bb  mov     rcx, [rbx+40h]; hEvent
0x1800081bf  call    cs:__imp_SetEvent
0x1800081c6  nop     dword ptr [rax+rax+00h]
0x1800081cb  test    eax, eax
0x1800081cd  jz      loc_1800083FA
0x1800081d3  mov     rcx, [rbx+30h]; hMutex
0x1800081d7  call    cs:__imp_ReleaseMutex
0x1800081de  nop     dword ptr [rax+rax+00h]
0x1800081e3  test    eax, eax
0x1800081e5  jz      loc_1800083C2
0x1800081eb  mov     rcx, [rbx+48h]; hHandle
0x1800081ef  xor     edx, edx; dwMilliseconds
0x1800081f1  call    cs:__imp_WaitForSingleObject
0x1800081f8  nop     dword ptr [rax+rax+00h]
0x1800081fd  test    eax, eax
0x1800081ff  jz      loc_1800082C9
0x180008205  mov     rcx, [rbx+28h]; hHandle
0x180008209  xor     edx, edx; dwMilliseconds
0x18000820b  call    cs:__imp_WaitForSingleObject
0x180008212  nop     dword ptr [rax+rax+00h]
0x180008217  test    eax, eax
0x180008219  jz      loc_1800082E3
0x18000821f  test    esi, esi
0x180008221  jnz     loc_180008150
0x180008227  jmp     loc_1800082C9
0x18000822c  mov     rdx, [rbx+58h]; Src
0x180008230  cmp     eax, esi
0x180008232  mov     rcx, rbp; void *
0x180008235  cmovnb  eax, esi
0x180008238  mov     r8d, eax; Size
0x18000823b  mov     edi, eax
0x18000823d  call    memcpy_0
0x180008242  add     [r14], edi
0x180008245  sub     [rbx+54h], edi
0x180008248  jnz     loc_18000842E
0x18000824e  mov     rcx, [rbx+40h]; hEvent
0x180008252  mov     [rbx+60h], r12d
0x180008256  call    cs:__imp_SetEvent
0x18000825d  nop     dword ptr [rax+rax+00h]
0x180008262  test    eax, eax
0x180008264  jz      loc_18000838A
0x18000826a  mov     rcx, [rbx+30h]; hMutex
0x18000826e  call    cs:__imp_ReleaseMutex
0x180008275  nop     dword ptr [rax+rax+00h]
0x18000827a  test    eax, eax
0x18000827c  jz      short loc_18000828A
0x18000827e  sub     esi, edi
0x180008280  jz      short loc_1800082C9
0x180008282  add     rbp, rdi
0x180008285  jmp     loc_180008150
0x18000828a  call    cs:__imp_GetLastError
0x180008291  nop     dword ptr [rax+rax+00h]
0x180008296  mov     r10d, eax
0x180008299  test    eax, eax
0x18000829b  jg      loc_180008444
0x1800082a1  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800082a8  mov     [rbx+60h], r10d
0x1800082ac  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800082b1  mov     r8, rax
0x1800082b4  mov     edx, r10d
0x1800082b7  mov     r9d, 1C2h
0x1800082bd  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800082c4  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800082c9  mov     eax, [rbx+60h]
0x1800082cc  mov     rdi, [rsp+78h+arg_0]
0x1800082d4  add     rsp, 48h
0x1800082d8  pop     r15
0x1800082da  pop     r14
0x1800082dc  pop     r12
0x1800082de  pop     rsi
0x1800082df  pop     rbp
0x1800082e0  pop     rbx
0x1800082e1  retn
0x1800082e3  test    r15d, r15d
0x1800082e6  jnz     short loc_1800082C9
0x1800082e8  mov     r15d, 1
0x1800082ee  jmp     loc_18000821F
0x1800082f3  call    cs:__imp_GetLastError
0x1800082fa  nop     dword ptr [rax+rax+00h]
0x1800082ff  test    eax, eax
0x180008301  jg      loc_18000848E
0x180008307  mov     [rbx+60h], eax
0x18000830a  lea     r8, aOnecoreDsSecur_13+2Eh; ""
0x180008311  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008318  movzx   edx, byte ptr [r8-1]
0x18000831d  mov     r9, r8
0x180008320  dec     r8
0x180008323  cmp     dl, 5Ch ; '\'
0x180008326  jz      short loc_180008330
0x180008328  cmp     r8, rcx
0x18000832b  ja      short loc_180008318
0x18000832d  cmp     dl, 5Ch ; '\'
0x180008330  cmovz   r8, r9
0x180008334  mov     r9d, 177h
0x18000833a  mov     edx, eax
0x18000833c  jmp     loc_1800082BD
0x180008341  call    cs:__imp_GetLastError
0x180008348  nop     dword ptr [rax+rax+00h]
0x18000834d  test    eax, eax
0x18000834f  jg      loc_180008481
0x180008355  mov     [rbx+60h], eax
0x180008358  lea     r8, aOnecoreDsSecur_13+2Eh; ""
0x18000835f  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008366  movzx   edx, byte ptr [r8-1]
0x18000836b  mov     r9, r8
0x18000836e  dec     r8
0x180008371  cmp     dl, 5Ch ; '\'
0x180008374  jz      short loc_18000837E
0x180008376  cmp     r8, rcx
0x180008379  ja      short loc_180008366
0x18000837b  cmp     dl, 5Ch ; '\'
0x18000837e  cmovz   r8, r9
0x180008382  mov     r9d, 189h
0x180008388  jmp     short loc_18000833A
0x18000838a  call    cs:__imp_GetLastError
0x180008391  nop     dword ptr [rax+rax+00h]
0x180008396  mov     r10d, eax
0x180008399  test    eax, eax
0x18000839b  jg      loc_180008454
0x1800083a1  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800083a8  mov     [rbx+60h], r10d
0x1800083ac  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800083b1  mov     r8, rax
0x1800083b4  mov     edx, r10d
0x1800083b7  mov     r9d, 1BAh
0x1800083bd  jmp     loc_1800082BD
0x1800083c2  call    cs:__imp_GetLastError
0x1800083c9  nop     dword ptr [rax+rax+00h]
0x1800083ce  mov     r10d, eax
0x1800083d1  test    eax, eax
0x1800083d3  jg      loc_180008464
0x1800083d9  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800083e0  mov     [rbx+60h], r10d
0x1800083e4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800083e9  mov     r8, rax
0x1800083ec  mov     edx, r10d
0x1800083ef  mov     r9d, 1E1h
0x1800083f5  jmp     loc_1800082BD
0x1800083fa  call    cs:__imp_GetLastError
0x180008401  nop     dword ptr [rax+rax+00h]
0x180008406  mov     r10d, eax
0x180008409  test    eax, eax
0x18000840b  jg      short loc_180008474
0x18000840d  lea     rcx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180008414  mov     [rbx+60h], r10d
0x180008418  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000841d  mov     r8, rax
0x180008420  mov     edx, r10d
0x180008423  mov     r9d, 1D9h
0x180008429  jmp     loc_1800082BD
0x18000842e  mov     rcx, [rbx+58h]; void *
0x180008432  mov     r8d, [rbx+54h]; Size
0x180008436  lea     rdx, [rcx+rdi]; Src
0x18000843a  call    memmove_0
0x18000843f  jmp     loc_18000824E
0x180008444  movzx   r10d, ax
0x180008448  or      r10d, 80070000h
0x18000844f  jmp     loc_1800082A1
0x180008454  movzx   r10d, ax
0x180008458  or      r10d, 80070000h
0x18000845f  jmp     loc_1800083A1
0x180008464  movzx   r10d, ax
0x180008468  or      r10d, 80070000h
0x18000846f  jmp     loc_1800083D9
0x180008474  movzx   r10d, ax
0x180008478  or      r10d, 80070000h
0x18000847f  jmp     short loc_18000840D
0x180008481  movzx   eax, ax
0x180008484  or      eax, 80070000h
0x180008489  jmp     loc_180008355
0x18000848e  movzx   eax, ax
0x180008491  or      eax, 80070000h
0x180008496  jmp     loc_180008307
```
