# CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)

- ea: `0x180026598`
- end: `0x18002681b`
- name: `?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z`
- size: `643`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18002cebc`

## callees

- `0x180025124`
- `0x180026598`
- `0x180027008`
- `0x1800275b8`
- `0x1800293a4`
- `0x18002c6a0`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002660d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002660d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180026603`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180026603`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026798`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800267b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800267da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026798`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800267b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800267da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800267a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800267c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800267e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800267a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800267c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800267e9`

## string_xrefs

- `0x180026702`: `spp.dll`
- `0x180026726`: `spp.dll`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::AppendToSystemPath(__int64 a1, unsigned __int16 **a2)
{
  __int64 v3; // rbx
  unsigned __int16 *v4; // r15
  __int64 v5; // rsi
  signed int LastError; // eax
  unsigned int v7; // edi
  __int64 v8; // rdx
  wchar_t *v9; // rax
  __int64 v10; // rcx
  int Internal; // eax
  int StringCch; // eax
  int v13; // eax
  int v14; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h]
  wchar_t v22[266]; // [rsp+4Ch] [rbp-B4h] BYREF

  v21 = 1;
  v20 = 0;
  v18 = 0;
  v3 = 0;
  wcscpy(v22, L"\\");
  v19 = 0;
  v4 = 0;
  v5 = 0;
  if ( !GetSystemDirectoryW(&v22[2], 0x104u) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
LABEL_6:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_32;
  }
  v8 = 260;
  v9 = &v22[2];
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v7 = v8 == 0 ? 0x80070057 : 0;
  v10 = (260 - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
    goto LABEL_6;
  if ( v22[v10 + 1] == 92 || v22[v10 + 1] == 47 )
    --v10;
  if ( v10 == (unsigned int)v10 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v7 = 0;
  }
  else
  {
    v7 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) == 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(&v22[2]);
    v7 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v5 = v18;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_6;
  LODWORD(v18) = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"spp.dll", &v18);
  v7 = StringCch;
  if ( StringCch >= 0 )
  {
    v13 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"spp.dll");
    v7 = v13;
    if ( v13 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
    v3 = v19;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_6;
  v14 = STRAPI_MultiCat(&v20, 3u, v5, v22, v3);
  v7 = v14;
  if ( v14 >= 0 )
  {
    *a2 = v20;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
    v4 = v20;
  }
LABEL_32:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v3 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v7;
}

```

## disassembly

```asm
0x180026598  push    rbp
0x18002659a  push    rbx
0x18002659b  push    rsi
0x18002659c  push    rdi
0x18002659d  push    r12
0x18002659f  push    r13
0x1800265a1  push    r14
0x1800265a3  push    r15
0x1800265a5  lea     rbp, [rsp-178h]
0x1800265ad  sub     rsp, 278h
0x1800265b4  mov     rax, cs:__security_cookie
0x1800265bb  xor     rax, rsp
0x1800265be  mov     [rbp+1B0h+var_50], rax
0x1800265c5  mov     eax, dword ptr cs:pszSrc; "\\"
0x1800265cb  lea     rcx, [rsp+2B0h+var_264+4]; lpBuffer
0x1800265d0  xor     r13d, r13d
0x1800265d3  mov     [rsp+2B0h+var_268], 1
0x1800265db  mov     r12, rdx
0x1800265de  mov     [rsp+2B0h+var_270], r13
0x1800265e3  mov     r14d, 104h
0x1800265e9  mov     [rsp+2B0h+var_280], r13
0x1800265ee  mov     ebx, r13d
0x1800265f1  mov     dword ptr [rsp+2B0h+var_264], eax
0x1800265f5  mov     edx, r14d; uSize
0x1800265f8  mov     [rsp+2B0h+var_278], rbx
0x1800265fd  mov     r15d, r13d
0x180026600  mov     esi, r13d
0x180026603  call    cs:__imp_GetSystemDirectoryW
0x180026609  test    eax, eax
0x18002660b  jnz     short loc_180026637
0x18002660d  call    cs:__imp_GetLastError
0x180026613  mov     edi, eax
0x180026615  test    eax, eax
0x180026617  jnz     short loc_180026620
0x180026619  mov     edi, 80004005h
0x18002661e  jmp     short loc_18002662B
0x180026620  jle     short loc_18002662B
0x180026622  movzx   edi, ax
0x180026625  or      edi, 80070000h
0x18002662b  mov     ecx, edi
0x18002662d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180026632  jmp     loc_18002678C
0x180026637  mov     rdx, r14
0x18002663a  lea     rax, [rsp+2B0h+var_264+4]
0x18002663f  cmp     [rax], r13w
0x180026643  jz      short loc_18002664F
0x180026645  add     rax, 2
0x180026649  sub     rdx, 1
0x18002664d  jnz     short loc_18002663F
0x18002664f  mov     rax, rdx
0x180026652  neg     rax
0x180026655  mov     rax, rdx
0x180026658  sbb     edi, edi
0x18002665a  sub     r14, rdx
0x18002665d  not     edi
0x18002665f  and     edi, 80070057h
0x180026665  neg     rax
0x180026668  sbb     rcx, rcx
0x18002666b  and     rcx, r14
0x18002666e  test    rdx, rdx
0x180026671  jz      short loc_18002662B
0x180026673  mov     eax, 5Ch ; '\'
0x180026678  cmp     ax, [rsp+rcx*2+2B0h+var_264+2]
0x18002667d  jz      short loc_18002668B
0x18002667f  mov     eax, 2Fh ; '/'
0x180026684  cmp     ax, [rsp+rcx*2+2B0h+var_264+2]
0x180026689  jnz     short loc_18002668E
0x18002668b  dec     rcx
0x18002668e  mov     r14d, ecx
0x180026691  cmp     rcx, r14
0x180026694  jz      short loc_1800266A7
0x180026696  mov     edi, 80070216h
0x18002669b  mov     r14d, r13d
0x18002669e  mov     ecx, edi
0x1800266a0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800266a5  jmp     short loc_1800266B1
0x1800266a7  xor     ecx, ecx
0x1800266a9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800266ae  mov     edi, r13d
0x1800266b1  mov     ecx, edi
0x1800266b3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800266b8  test    edi, edi
0x1800266ba  jns     short loc_1800266C5
0x1800266bc  mov     ecx, edi
0x1800266be  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800266c3  jmp     short loc_1800266E9
0x1800266c5  lea     r8, [rsp+2B0h+var_280]
0x1800266ca  mov     edx, r14d
0x1800266cd  lea     rcx, [rsp+2B0h+var_264+4]; Src
0x1800266d2  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x1800266d7  mov     edi, eax
0x1800266d9  test    eax, eax
0x1800266db  jns     short loc_1800266E4
0x1800266dd  mov     ecx, eax
0x1800266df  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800266e4  mov     rsi, [rsp+2B0h+var_280]
0x1800266e9  mov     ecx, edi
0x1800266eb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800266f0  test    edi, edi
0x1800266f2  js      loc_18002662B
0x1800266f8  lea     rdx, [rsp+2B0h+var_280]
0x1800266fd  mov     dword ptr [rsp+2B0h+var_280], r13d
0x180026702  lea     rcx, aSppDll; "spp.dll"
0x180026709  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18002670e  mov     edi, eax
0x180026710  test    eax, eax
0x180026712  jns     short loc_18002671D
0x180026714  mov     ecx, eax
0x180026716  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002671b  jmp     short loc_180026744
0x18002671d  mov     edx, dword ptr [rsp+2B0h+var_280]
0x180026721  lea     r8, [rsp+2B0h+var_278]
0x180026726  lea     rcx, aSppDll; "spp.dll"
0x18002672d  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180026732  mov     edi, eax
0x180026734  test    eax, eax
0x180026736  jns     short loc_18002673F
0x180026738  mov     ecx, eax
0x18002673a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002673f  mov     rbx, [rsp+2B0h+var_278]
0x180026744  mov     ecx, edi
0x180026746  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002674b  test    edi, edi
0x18002674d  js      loc_18002662B
0x180026753  lea     r9, [rsp+2B0h+var_264]
0x180026758  mov     [rsp+2B0h+var_290], rbx
0x18002675d  mov     r8, rsi
0x180026760  lea     rcx, [rsp+2B0h+var_270]; unsigned __int16 **
0x180026765  mov     edx, 3; unsigned int
0x18002676a  call    ?STRAPI_MultiCat@@YAJPEAPEAGKZZ; STRAPI_MultiCat(ushort * *,ulong,...)
0x18002676f  mov     edi, eax
0x180026771  test    eax, eax
0x180026773  jns     short loc_180026783
0x180026775  mov     ecx, eax
0x180026777  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002677c  mov     r15, [rsp+2B0h+var_270]
0x180026781  jmp     short loc_18002678C
0x180026783  mov     rax, [rsp+2B0h+var_270]
0x180026788  mov     [r12], rax
0x18002678c  mov     ecx, edi
0x18002678e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180026793  test    rbx, rbx
0x180026796  jz      short loc_1800267B4
0x180026798  call    cs:__imp_GetProcessHeap
0x18002679e  lea     r8, [rbx-4]; lpMem
0x1800267a2  xor     edx, edx; dwFlags
0x1800267a4  mov     rcx, rax; hHeap
0x1800267a7  call    cs:__imp_HeapFree
0x1800267ad  xor     ecx, ecx
0x1800267af  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800267b4  test    rsi, rsi
0x1800267b7  jz      short loc_1800267D5
0x1800267b9  call    cs:__imp_GetProcessHeap
0x1800267bf  lea     r8, [rsi-4]; lpMem
0x1800267c3  xor     edx, edx; dwFlags
0x1800267c5  mov     rcx, rax; hHeap
0x1800267c8  call    cs:__imp_HeapFree
0x1800267ce  xor     ecx, ecx
0x1800267d0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800267d5  test    r15, r15
0x1800267d8  jz      short loc_1800267F6
0x1800267da  call    cs:__imp_GetProcessHeap
0x1800267e0  lea     r8, [r15-4]; lpMem
0x1800267e4  xor     edx, edx; dwFlags
0x1800267e6  mov     rcx, rax; hHeap
0x1800267e9  call    cs:__imp_HeapFree
0x1800267ef  xor     ecx, ecx
0x1800267f1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800267f6  mov     eax, edi
0x1800267f8  mov     rcx, [rbp+1B0h+var_50]
0x1800267ff  xor     rcx, rsp; StackCookie
0x180026802  call    __security_check_cookie
0x180026807  add     rsp, 278h
0x18002680e  pop     r15
0x180026810  pop     r14
0x180026812  pop     r13
0x180026814  pop     r12
0x180026816  pop     rdi
0x180026817  pop     rsi
0x180026818  pop     rbx
0x180026819  pop     rbp
0x18002681a  retn
```
