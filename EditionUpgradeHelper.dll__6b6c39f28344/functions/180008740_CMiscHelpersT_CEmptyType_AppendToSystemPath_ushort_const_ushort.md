# CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)

- ea: `0x180008740`
- end: `0x180008a37`
- name: `?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z`
- size: `759`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000a390`

## callees

- `0x1800018e0`
- `0x180008740`
- `0x180008c60`
- `0x180008dbc`
- `0x180009978`
- `0x18000a340`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800087a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800087a9`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::AppendToSystemPath(__int64 a1, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // r15
  signed int LastError; // eax
  unsigned int v5; // edi
  __int64 v6; // rdx
  WCHAR *v7; // rax
  __int64 v8; // rcx
  int Internal; // eax
  const wchar_t *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v18 = 1;
  v17 = 0;
  v3 = 0;
  v19 = *(_DWORD *)L"\\";
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
LABEL_6:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_39;
  }
  v6 = 260;
  v7 = Buffer;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v5 = v6 == 0 ? 0x80070057 : 0;
  v8 = (260 - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
    goto LABEL_6;
  if ( Buffer[v8 - 1] == 92 || Buffer[v8 - 1] == 47 )
    --v8;
  if ( v8 == (unsigned int)v8 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v5 = 0;
  }
  else
  {
    v5 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) == 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer);
    v5 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_6;
  v10 = L"ChangePk.exe";
  v11 = 0x7FFFFFFF;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v5 = v11 == 0 ? 0x80070057 : 0;
  if ( !v11 )
    goto LABEL_26;
  v12 = (0x7FFFFFFF - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64);
  if ( v12 == (unsigned int)v12 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v5 = 0;
  }
  else
  {
    v5 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
LABEL_26:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) == 0 )
  {
    v13 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"ChangePk.exe");
    v5 = v13;
    if ( v13 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_6;
  v14 = STRAPI_MultiCat(&v17, 3u, 0, &v19, 0);
  v5 = v14;
  if ( v14 >= 0 )
  {
    v3 = 0;
    *a2 = v17;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
    v3 = v17;
  }
LABEL_39:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v5;
}

```

## disassembly

```asm
0x180008740  push    rbp
0x180008742  push    rbx
0x180008743  push    rsi
0x180008744  push    rdi
0x180008745  push    r12
0x180008747  push    r13
0x180008749  push    r14
0x18000874b  push    r15
0x18000874d  lea     rbp, [rsp-178h]
0x180008755  sub     rsp, 278h
0x18000875c  mov     rax, cs:__security_cookie
0x180008763  xor     rax, rsp
0x180008766  mov     [rbp+1B0h+var_50], rax
0x18000876d  mov     eax, dword ptr cs:asc_180028EC0; "\\"
0x180008773  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x180008778  xor     r12d, r12d
0x18000877b  mov     [rsp+2B0h+var_268], 1
0x180008783  mov     r13, rdx
0x180008786  mov     [rsp+2B0h+var_270], r12
0x18000878b  mov     ebx, 104h
0x180008790  mov     [rsp+2B0h+var_280], r12
0x180008795  mov     edx, ebx; uSize
0x180008797  mov     [rsp+2B0h+var_278], r12
0x18000879c  mov     r15d, r12d
0x18000879f  mov     [rsp+2B0h+var_264], eax
0x1800087a3  mov     r14d, r12d
0x1800087a6  mov     esi, r12d
0x1800087a9  call    cs:__imp_GetSystemDirectoryW
0x1800087af  test    eax, eax
0x1800087b1  jnz     short loc_1800087DD
0x1800087b3  call    cs:__imp_GetLastError
0x1800087b9  mov     edi, eax
0x1800087bb  test    eax, eax
0x1800087bd  jnz     short loc_1800087C6
0x1800087bf  mov     edi, 80004005h
0x1800087c4  jmp     short loc_1800087D1
0x1800087c6  jle     short loc_1800087D1
0x1800087c8  movzx   edi, ax
0x1800087cb  or      edi, 80070000h
0x1800087d1  mov     ecx, edi
0x1800087d3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800087d8  jmp     loc_1800089A8
0x1800087dd  mov     rdx, rbx
0x1800087e0  lea     rax, [rsp+2B0h+Buffer]
0x1800087e5  cmp     [rax], r12w
0x1800087e9  jz      short loc_1800087F5
0x1800087eb  add     rax, 2
0x1800087ef  sub     rdx, 1
0x1800087f3  jnz     short loc_1800087E5
0x1800087f5  mov     rax, rdx
0x1800087f8  neg     rax
0x1800087fb  mov     rax, rdx
0x1800087fe  sbb     edi, edi
0x180008800  sub     rbx, rdx
0x180008803  not     edi
0x180008805  and     edi, 80070057h
0x18000880b  neg     rax
0x18000880e  sbb     rcx, rcx
0x180008811  and     rcx, rbx
0x180008814  test    rdx, rdx
0x180008817  jz      short loc_1800087D1
0x180008819  mov     eax, 5Ch ; '\'
0x18000881e  cmp     ax, word ptr [rsp+rcx*2+2B0h+var_264+2]
0x180008823  jz      short loc_180008831
0x180008825  mov     eax, 2Fh ; '/'
0x18000882a  cmp     ax, word ptr [rsp+rcx*2+2B0h+var_264+2]
0x18000882f  jnz     short loc_180008834
0x180008831  dec     rcx
0x180008834  mov     ebx, ecx
0x180008836  mov     eax, 80070216h
0x18000883b  cmp     rcx, rbx
0x18000883e  jz      short loc_18000884E
0x180008840  mov     ecx, eax
0x180008842  mov     ebx, r12d
0x180008845  mov     edi, eax
0x180008847  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000884c  jmp     short loc_180008858
0x18000884e  xor     ecx, ecx
0x180008850  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008855  mov     edi, r12d
0x180008858  mov     ecx, edi
0x18000885a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000885f  test    edi, edi
0x180008861  jns     short loc_18000886C
0x180008863  mov     ecx, edi
0x180008865  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000886a  jmp     short loc_18000888F
0x18000886c  lea     r8, [rsp+2B0h+var_280]
0x180008871  mov     edx, ebx
0x180008873  lea     rcx, [rsp+2B0h+Buffer]; Src
0x180008878  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18000887d  mov     edi, eax
0x18000887f  test    eax, eax
0x180008881  jns     short loc_18000888A
0x180008883  mov     ecx, eax
0x180008885  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000888a  mov     r14, [rsp+2B0h+var_280]
0x18000888f  mov     ecx, edi
0x180008891  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008896  test    edi, edi
0x180008898  js      loc_1800087D1
0x18000889e  mov     r8d, 7FFFFFFFh
0x1800088a4  lea     rax, aChangepkExe; "ChangePk.exe"
0x1800088ab  mov     ecx, r8d
0x1800088ae  xor     r9d, r9d
0x1800088b1  cmp     [rax], r9w
0x1800088b5  jz      short loc_1800088C1
0x1800088b7  add     rax, 2
0x1800088bb  sub     rcx, 1
0x1800088bf  jnz     short loc_1800088B1
0x1800088c1  mov     rax, rcx
0x1800088c4  neg     rax
0x1800088c7  mov     rax, rcx
0x1800088ca  sbb     edi, edi
0x1800088cc  sub     r8, rcx
0x1800088cf  not     edi
0x1800088d1  and     edi, 80070057h
0x1800088d7  neg     rax
0x1800088da  sbb     rdx, rdx
0x1800088dd  and     rdx, r8
0x1800088e0  test    rcx, rcx
0x1800088e3  jnz     short loc_1800088EE
0x1800088e5  mov     ecx, edi
0x1800088e7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800088ec  jmp     short loc_18000891D
0x1800088ee  mov     ebx, edx
0x1800088f0  cmp     rdx, rbx
0x1800088f3  jz      short loc_180008906
0x1800088f5  mov     ecx, 80070216h
0x1800088fa  mov     ebx, r9d
0x1800088fd  mov     edi, ecx
0x1800088ff  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008904  jmp     short loc_18000890F
0x180008906  xor     ecx, ecx
0x180008908  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000890d  xor     edi, edi
0x18000890f  mov     ecx, edi
0x180008911  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008916  test    edi, edi
0x180008918  js      short loc_1800088E5
0x18000891a  mov     r12d, ebx
0x18000891d  mov     ecx, edi
0x18000891f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008924  test    edi, edi
0x180008926  jns     short loc_180008934
0x180008928  mov     ecx, edi
0x18000892a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000892f  xor     r12d, r12d
0x180008932  jmp     short loc_18000895D
0x180008934  lea     r8, [rsp+2B0h+var_278]
0x180008939  mov     edx, r12d
0x18000893c  lea     rcx, aChangepkExe; "ChangePk.exe"
0x180008943  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180008948  xor     r12d, r12d
0x18000894b  mov     edi, eax
0x18000894d  test    eax, eax
0x18000894f  jns     short loc_180008958
0x180008951  mov     ecx, eax
0x180008953  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008958  mov     rsi, [rsp+2B0h+var_278]
0x18000895d  mov     ecx, edi
0x18000895f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008964  test    edi, edi
0x180008966  js      loc_1800087D1
0x18000896c  lea     r9, [rsp+2B0h+var_264]
0x180008971  mov     [rsp+2B0h+var_290], rsi
0x180008976  mov     r8, r14
0x180008979  lea     rcx, [rsp+2B0h+var_270]; unsigned __int16 **
0x18000897e  mov     edx, 3; unsigned int
0x180008983  call    ?STRAPI_MultiCat@@YAJPEAPEAGKZZ; STRAPI_MultiCat(ushort * *,ulong,...)
0x180008988  mov     edi, eax
0x18000898a  test    eax, eax
0x18000898c  jns     short loc_18000899C
0x18000898e  mov     ecx, eax
0x180008990  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180008995  mov     r15, [rsp+2B0h+var_270]
0x18000899a  jmp     short loc_1800089A8
0x18000899c  mov     rax, [rsp+2B0h+var_270]
0x1800089a1  mov     r15, r12
0x1800089a4  mov     [r13+0], rax
0x1800089a8  mov     ecx, edi
0x1800089aa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800089af  test    rsi, rsi
0x1800089b2  jz      short loc_1800089D0
0x1800089b4  call    cs:__imp_GetProcessHeap
0x1800089ba  lea     r8, [rsi-4]; lpMem
0x1800089be  xor     edx, edx; dwFlags
0x1800089c0  mov     rcx, rax; hHeap
0x1800089c3  call    cs:__imp_HeapFree
0x1800089c9  xor     ecx, ecx
0x1800089cb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800089d0  test    r14, r14
0x1800089d3  jz      short loc_1800089F1
0x1800089d5  call    cs:__imp_GetProcessHeap
0x1800089db  lea     r8, [r14-4]; lpMem
0x1800089df  xor     edx, edx; dwFlags
0x1800089e1  mov     rcx, rax; hHeap
0x1800089e4  call    cs:__imp_HeapFree
0x1800089ea  xor     ecx, ecx
0x1800089ec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800089f1  test    r15, r15
0x1800089f4  jz      short loc_180008A12
0x1800089f6  call    cs:__imp_GetProcessHeap
0x1800089fc  lea     r8, [r15-4]; lpMem
0x180008a00  xor     edx, edx; dwFlags
0x180008a02  mov     rcx, rax; hHeap
0x180008a05  call    cs:__imp_HeapFree
0x180008a0b  xor     ecx, ecx
0x180008a0d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180008a12  mov     eax, edi
0x180008a14  mov     rcx, [rbp+1B0h+var_50]
0x180008a1b  xor     rcx, rsp; StackCookie
0x180008a1e  call    __security_check_cookie
0x180008a23  add     rsp, 278h
0x180008a2a  pop     r15
0x180008a2c  pop     r14
0x180008a2e  pop     r13
0x180008a30  pop     r12
0x180008a32  pop     rdi
0x180008a33  pop     rsi
0x180008a34  pop     rbx
0x180008a35  pop     rbp
0x180008a36  retn
```
