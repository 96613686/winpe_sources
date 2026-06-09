# SeQuirkManagerExecute

- ea: `0x1800274f4`
- end: `0x180027734`
- name: `SeQuirkManagerExecute`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180002520`

## callees

- `0x180009e94`
- `0x18000f114`
- `0x1800274f4`
- `0x18005a010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800276ac`
- `ntdll!_wcsicmp` at `0x1800276ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027521`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027521`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002753a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002753a`

## string_xrefs

- `0x180027514`: `api-ms-win-core-quirks-l1-1-0.dll`
- `0x180027720`: `Failed to copy quirk command line`

## pseudocode

```c
__int64 __fastcall SeQuirkManagerExecute(unsigned __int64 *a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const char *v4; // r9
  __int64 v5; // r8
  unsigned int v6; // ebx
  __int64 v8; // r14
  unsigned __int64 i; // rbp
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rbx
  unsigned __int16 v13; // r12
  const wchar_t *v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned __int16 j; // r13
  __int64 v18; // [rsp+70h] [rbp+8h]
  __int64 v19; // [rsp+78h] [rbp+10h]
  const wchar_t *v20; // [rsp+80h] [rbp+18h]

  if ( !a1[2] )
    return 0;
  Library = LoadLibraryExW(L"api-ms-win-core-quirks-l1-1-0.dll", 0, 0x800u);
  if ( !Library )
  {
    v4 = "Quirks not available";
    v5 = 318;
    goto LABEL_6;
  }
  ProcAddress = GetProcAddress(Library, "QuirkIsEnabled");
  if ( !ProcAddress )
  {
    v4 = "Quirks API not found";
    v5 = 325;
    goto LABEL_6;
  }
  ((void (__fastcall *)(_QWORD))ProcAddress)(0);
  if ( NtCurrentPeb()->pShimData )
  {
    v8 = *((_QWORD *)NtCurrentPeb()->pShimData + 560);
    if ( !v8 )
    {
      v4 = "Quirk table not initialized";
      v5 = 344;
      goto LABEL_6;
    }
    for ( i = 0; i < a1[2]; ++i )
    {
      v10 = a1[1] * i;
      if ( !is_mul_ok(a1[1], i) || (v11 = a1[5], v12 = v11 + v10, v11 + v10 < v11) )
        v12 = 0;
      v13 = 0;
      v14 = 0;
      if ( *(_WORD *)(v8 + 2) )
      {
        while ( !v14 )
        {
          v15 = 16LL * v13;
          v18 = v15;
          v16 = v8 + *(_QWORD *)(v15 + v8 + 16);
          v19 = v16;
          for ( j = 0; j < *(_WORD *)(v15 + v8 + 8); ++j )
          {
            v20 = (const wchar_t *)(v16 + 556LL * j);
            if ( !_wcsicmp(v20, (const wchar_t *)v12) )
            {
              v14 = v20;
              break;
            }
            v15 = v18;
            v16 = v19;
          }
          if ( ++v13 >= *(_WORD *)(v8 + 2) )
          {
            if ( !v14 )
              goto LABEL_16;
            break;
          }
        }
        *((_DWORD *)v14 + 138) |= 2 - (*(_DWORD *)(v12 + 516) != 0);
        if ( *(_DWORD *)(v12 + 512)
          && StringCchCopyW((STRSAFE_LPWSTR)v14 + 148, 0x80u, (STRSAFE_LPCWSTR)(v12 + 256)) < 0 )
        {
          v4 = "Failed to copy quirk command line";
          v5 = 399;
          goto LABEL_6;
        }
      }
      else
      {
LABEL_16:
        AslLogCallPrintf(1, "SeQuirkManagerExecute", 382, "Failed to find quirk %S", (const wchar_t *)v12);
      }
    }
    return 0;
  }
  v4 = "Shim peb data not initialized";
  v5 = 337;
LABEL_6:
  v6 = -1073741595;
  AslLogCallPrintf(1, "SeQuirkManagerExecute", v5, v4);
  return v6;
}

```

## disassembly

```asm
0x1800274f4  mov     [rsp+arg_18], rbx
0x1800274f9  push    rbp
0x1800274fa  push    rsi
0x1800274fb  push    rdi
0x1800274fc  push    r12
0x1800274fe  push    r13
0x180027500  push    r14
0x180027502  push    r15
0x180027504  sub     rsp, 30h
0x180027508  cmp     qword ptr [rcx+10h], 0
0x18002750d  mov     r15, rcx
0x180027510  jz      short loc_180027588
0x180027512  xor     edx, edx; hFile
0x180027514  lea     rcx, aApiMsWinCoreQu; "api-ms-win-core-quirks-l1-1-0.dll"
0x18002751b  mov     r8d, 800h; dwFlags
0x180027521  call    cs:__imp_LoadLibraryExW
0x180027527  test    rax, rax
0x18002752a  jz      loc_1800276DC
0x180027530  lea     rdx, aQuirkisenabled; "QuirkIsEnabled"
0x180027537  mov     rcx, rax; hModule
0x18002753a  call    cs:__imp_GetProcAddress
0x180027540  test    rax, rax
0x180027543  jz      loc_1800276EE
0x180027549  xor     ecx, ecx
0x18002754b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027550  mov     rax, gs:60h
0x180027559  cmp     qword ptr [rax+2D8h], 0
0x180027561  jnz     short loc_1800275A4
0x180027563  lea     r9, aShimPebDataNot; "Shim peb data not initialized"
0x18002756a  mov     r8d, 151h
0x180027570  mov     ecx, 1
0x180027575  lea     rdx, aSequirkmanager; "SeQuirkManagerExecute"
0x18002757c  mov     ebx, 0C00000E5h
0x180027581  call    AslLogCallPrintf
0x180027586  jmp     short loc_18002758A
0x180027588  xor     ebx, ebx
0x18002758a  mov     eax, ebx
0x18002758c  mov     rbx, [rsp+68h+arg_18]
0x180027594  add     rsp, 30h
0x180027598  pop     r15
0x18002759a  pop     r14
0x18002759c  pop     r13
0x18002759e  pop     r12
0x1800275a0  pop     rdi
0x1800275a1  pop     rsi
0x1800275a2  pop     rbp
0x1800275a3  retn
0x1800275a4  mov     rax, gs:60h
0x1800275ad  mov     rcx, [rax+2D8h]
0x1800275b4  mov     r14, [rcx+1180h]
0x1800275bb  test    r14, r14
0x1800275be  jz      loc_1800276CA
0x1800275c4  xor     ebp, ebp
0x1800275c6  lea     edi, [rbp+1]
0x1800275c9  cmp     rbp, [r15+10h]
0x1800275cd  jnb     short loc_180027588
0x1800275cf  mov     rax, rbp
0x1800275d2  mov     [rsp+68h+arg_0], 0
0x1800275db  mul     qword ptr [r15+8]
0x1800275df  mov     rcx, rax
0x1800275e2  test    rdx, rdx
0x1800275e5  jnz     short loc_1800275F4
0x1800275e7  mov     rax, [r15+28h]
0x1800275eb  lea     rbx, [rax+rcx]
0x1800275ef  cmp     rbx, rax
0x1800275f2  jnb     short loc_1800275F6
0x1800275f4  xor     ebx, ebx
0x1800275f6  xor     r12d, r12d
0x1800275f9  xor     esi, esi
0x1800275fb  xor     eax, eax
0x1800275fd  cmp     ax, [r14+2]
0x180027602  jb      short loc_180027666
0x180027604  lea     r9, aFailedToFindQu; "Failed to find quirk %S"
0x18002760b  mov     [rsp+68h+var_48], rbx
0x180027610  mov     r8d, 17Eh
0x180027616  lea     rdx, aSequirkmanager; "SeQuirkManagerExecute"
0x18002761d  mov     ecx, edi
0x18002761f  call    AslLogCallPrintf
0x180027624  jmp     short loc_18002765E
0x180027626  mov     rsi, [rsp+68h+arg_10]
0x18002762e  add     r12w, di
0x180027632  cmp     r12w, [r14+2]
0x180027637  jb      short loc_180027666
0x180027639  test    rsi, rsi
0x18002763c  jz      short loc_180027604
0x18002763e  mov     eax, [rbx+204h]
0x180027644  neg     eax
0x180027646  sbb     ecx, ecx
0x180027648  add     ecx, 2
0x18002764b  or      [rsi+228h], ecx
0x180027651  cmp     dword ptr [rbx+200h], 0
0x180027658  jnz     loc_180027700
0x18002765e  add     rbp, rdi
0x180027661  jmp     loc_1800275C9
0x180027666  test    rsi, rsi
0x180027669  jnz     short loc_18002763E
0x18002766b  movzx   ecx, r12w
0x18002766f  shl     rcx, 4
0x180027673  mov     [rsp+68h+arg_0], rcx
0x180027678  mov     rdx, [rcx+r14+10h]
0x18002767d  add     rdx, r14
0x180027680  mov     [rsp+68h+arg_8], rdx
0x180027685  xor     r13d, r13d
0x180027688  cmp     r13w, [rcx+r14+8]
0x18002768e  jnb     short loc_18002762E
0x180027690  movzx   eax, r13w
0x180027694  imul    rax, 22Ch
0x18002769b  add     rax, rdx
0x18002769e  mov     rdx, rbx; String2
0x1800276a1  mov     rcx, rax; String1
0x1800276a4  mov     [rsp+68h+arg_10], rax
0x1800276ac  call    cs:__imp__wcsicmp
0x1800276b2  test    eax, eax
0x1800276b4  jz      loc_180027626
0x1800276ba  mov     rcx, [rsp+68h+arg_0]
0x1800276bf  add     r13w, di
0x1800276c3  mov     rdx, [rsp+68h+arg_8]
0x1800276c8  jmp     short loc_180027688
0x1800276ca  lea     r9, aQuirkTableNotI; "Quirk table not initialized"
0x1800276d1  mov     r8d, 158h
0x1800276d7  jmp     loc_180027570
0x1800276dc  lea     r9, aQuirksNotAvail; "Quirks not available"
0x1800276e3  mov     r8d, 13Eh
0x1800276e9  jmp     loc_180027570
0x1800276ee  lea     r9, aQuirksApiNotFo; "Quirks API not found"
0x1800276f5  mov     r8d, 145h
0x1800276fb  jmp     loc_180027570
0x180027700  lea     r8, [rbx+100h]; pszSrc
0x180027707  mov     edx, 80h; cchDest
0x18002770c  lea     rcx, [rsi+128h]; pszDest
0x180027713  call    StringCchCopyW
0x180027718  test    eax, eax
0x18002771a  jns     loc_18002765E
0x180027720  lea     r9, aFailedToCopyQu; "Failed to copy quirk command line"
0x180027727  mov     r8d, 18Fh
0x18002772d  mov     ecx, edi
0x18002772f  jmp     loc_180027575
```
