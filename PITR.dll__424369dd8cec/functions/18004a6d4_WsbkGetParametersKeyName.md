# WsbkGetParametersKeyName

- ea: `0x18004a6d4`
- end: `0x18004a9ce`
- name: `WsbkGetParametersKeyName`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18004c180`

## callees

- `0x180009e04`
- `0x18003b7f4`
- `0x18003e128`
- `0x18004a6d4`
- `0x18004a9d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a987`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a9a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a987`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a9a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a995`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a9ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a995`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a9ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a915`
- `ntdll!RtlAllocateHeap` at `0x18004a7e4`
- `ntdll!RtlAllocateHeap` at `0x18004a7e4`
- `ntdll!RtlFreeHeap` at `0x18004a8aa`
- `ntdll!RtlFreeHeap` at `0x18004a8aa`
- `WDSCORE!CurrentIP` at `0x18004a71c`
- `WDSCORE!CurrentIP` at `0x18004a91d`
- `WDSCORE!CurrentIP` at `0x18004a71c`
- `WDSCORE!CurrentIP` at `0x18004a91d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a782`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a97c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a782`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a97c`

## string_xrefs

- `0x18004a926`: `WsbkGetParametersKeyName: Failed to build service key path; hr = 0x%x`

## pseudocode

```c
__int64 __fastcall WsbkGetParametersKeyName(__int64 a1, wchar_t **a2)
{
  int ServiceKeyName; // eax
  wchar_t *v4; // r14
  signed int v5; // esi
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  int v9; // esi
  __int64 v10; // rbx
  wchar_t *Heap; // rdi
  HRESULT v12; // eax
  unsigned __int16 v13; // bx
  HRESULT v14; // eax
  HRESULT v15; // eax
  signed int v16; // eax
  bool v17; // sf
  signed int v18; // eax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  HANDLE ProcessHeap; // rax
  DWORD v24; // [rsp+30h] [rbp-30h]
  DWORD v25; // [rsp+30h] [rbp-30h]
  STRSAFE_PCNZWCH pszSrc; // [rsp+A0h] [rbp+40h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+B0h] [rbp+50h] BYREF

  pszSrc = 0;
  ServiceKeyName = WsbkGetServiceKeyName(L"SYSTEM", (wchar_t **)&pszSrc);
  v4 = (wchar_t *)pszSrc;
  v5 = ServiceKeyName;
  if ( ServiceKeyName < 0 )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           0x2000000,
           "WsbkGetParametersKeyName: Failed to get current control set key name under hive key %s; hr = 0x%x",
           (const char *)L"SYSTEM",
           v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      3050,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkGetParametersKeyName",
      v7,
      LastError,
      0,
      0);
    goto LABEL_27;
  }
  pszDest = 0;
  pszSrc = 0;
  if ( v4 )
  {
    v9 = 0;
    v10 = -1;
    do
      ++v10;
    while ( v4[v10] );
    if ( (_DWORD)v10 && v4[(unsigned int)(v10 - 1)] != 92 )
      v9 = 1;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v10 + v9 + 11));
    if ( Heap )
    {
      v12 = StringCchCopyNExW(
              Heap,
              (unsigned int)(v10 + v9 + 11),
              v4,
              (unsigned int)v10,
              &pszDest,
              (size_t *)&pszSrc,
              v24);
      v13 = v12;
      if ( v12 >= 0 )
      {
        if ( !v9
          || (v14 = StringCchCopyNExW(pszDest, (size_t)pszSrc, L"\\", 1u, &pszDest, (size_t *)&pszSrc, v25),
              v13 = v14,
              v14 >= 0) )
        {
          v15 = StringCchCopyNW(pszDest, (size_t)pszSrc, L"Parameters", 0xAu);
          v13 = v15;
          if ( v15 >= 0 )
          {
            v5 = 0;
            NtCurrentTeb()->LastErrorValue = 0;
LABEL_24:
            *a2 = Heap;
            goto LABEL_27;
          }
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      NtCurrentTeb()->LastErrorValue = v13;
    }
    else
    {
      NtCurrentTeb()->LastErrorValue = 8;
    }
  }
  else
  {
    NtCurrentTeb()->LastErrorValue = 87;
  }
  Heap = 0;
  v16 = GetLastError();
  v17 = v16 < 0;
  if ( v16 > 0 )
    v17 = 1;
  if ( v17 )
  {
    v18 = GetLastError();
    v5 = v18;
    if ( v18 > 0 )
      v5 = (unsigned __int16)v18 | 0x80070000;
    if ( v5 >= 0 )
      goto LABEL_24;
  }
  else
  {
    v5 = -2147467259;
  }
  v19 = GetLastError();
  v20 = CurrentIP();
  v21 = ConstructPartialMsgW(0x2000000, "WsbkGetParametersKeyName: Failed to build service key path; hr = 0x%x", v5);
  WdsSetupLogMessageW(
    v21,
    0,
    L"D",
    0,
    3057,
    L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
    L"WsbkGetParametersKeyName",
    v20,
    v19,
    0,
    0);
LABEL_27:
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004a6d4  mov     [rsp-38h+arg_8], rbx
0x18004a6d9  mov     [rsp-38h+pszSrc], rcx
0x18004a6de  push    rbp
0x18004a6df  push    rsi
0x18004a6e0  push    rdi
0x18004a6e1  push    r12
0x18004a6e3  push    r13
0x18004a6e5  push    r14
0x18004a6e7  push    r15
0x18004a6e9  mov     rbp, rsp
0x18004a6ec  sub     rsp, 60h
0x18004a6f0  mov     r12, rdx
0x18004a6f3  lea     rcx, aSystem; "SYSTEM"
0x18004a6fa  xor     r13d, r13d
0x18004a6fd  lea     rdx, [rbp+pszSrc]
0x18004a701  mov     [rbp+pszSrc], r13
0x18004a705  call    WsbkGetServiceKeyName
0x18004a70a  mov     r14, [rbp+pszSrc]
0x18004a70e  mov     esi, eax
0x18004a710  test    eax, eax
0x18004a712  jns     short loc_18004A78D
0x18004a714  call    cs:__imp_GetLastError
0x18004a71a  mov     edi, eax
0x18004a71c  call    cs:__imp_CurrentIP
0x18004a722  mov     r9d, esi
0x18004a725  lea     r8, aSystem; "SYSTEM"
0x18004a72c  lea     rdx, aWsbkgetparamet; "WsbkGetParametersKeyName: Failed to get"...
0x18004a733  mov     ecx, 2000000h; unsigned int
0x18004a738  mov     rbx, rax
0x18004a73b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a740  mov     [rsp+60h+var_10], r13d
0x18004a745  lea     rcx, aWsbkgetparamet_1; "WsbkGetParametersKeyName"
0x18004a74c  mov     [rsp+60h+var_18], r13
0x18004a751  lea     r8, aD; "D"
0x18004a758  mov     [rsp+60h+var_20], edi
0x18004a75c  xor     r9d, r9d
0x18004a75f  mov     [rsp+60h+var_28], rbx
0x18004a764  xor     edx, edx
0x18004a766  mov     [rsp+60h+var_30], rcx
0x18004a76b  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004a772  mov     [rsp+60h+pcchRemaining], rcx
0x18004a777  mov     rcx, rax
0x18004a77a  mov     dword ptr [rsp+60h+ppszDestEnd], 0BEAh
0x18004a782  call    cs:__imp_WdsSetupLogMessageW
0x18004a788  jmp     loc_18004A99B
0x18004a78d  mov     [rbp+pszDest], r13
0x18004a791  mov     [rbp+pszSrc], r13
0x18004a795  test    r14, r14
0x18004a798  jz      loc_18004A8C1
0x18004a79e  mov     esi, r13d
0x18004a7a1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004a7a5  inc     rbx
0x18004a7a8  cmp     [r14+rbx*2], r13w
0x18004a7ad  jnz     short loc_18004A7A5
0x18004a7af  mov     edx, 1
0x18004a7b4  test    ebx, ebx
0x18004a7b6  jz      short loc_18004A7C6
0x18004a7b8  lea     ecx, [rbx-1]
0x18004a7bb  lea     eax, [rdx+5Bh]
0x18004a7be  cmp     ax, [r14+rcx*2]
0x18004a7c3  cmovnz  esi, edx
0x18004a7c6  mov     rcx, gs:60h
0x18004a7cf  lea     eax, [rsi+0Bh]
0x18004a7d2  add     eax, ebx
0x18004a7d4  mov     edx, 8; Flags
0x18004a7d9  mov     r15d, eax
0x18004a7dc  mov     rcx, [rcx+30h]; HeapHandle
0x18004a7e0  lea     r8, [rax+rax]; Size
0x18004a7e4  call    cs:__imp_RtlAllocateHeap
0x18004a7ea  mov     rdi, rax
0x18004a7ed  test    rax, rax
0x18004a7f0  jnz     short loc_18004A807
0x18004a7f2  mov     rax, gs:30h
0x18004a7fb  mov     dword ptr [rax+68h], 8
0x18004a802  jmp     loc_18004A8D1
0x18004a807  lea     rax, [rbp+pszSrc]
0x18004a80b  mov     r9d, ebx; cchToCopy
0x18004a80e  mov     [rsp+60h+pcchRemaining], rax; pcchRemaining
0x18004a813  mov     r8, r14; pszSrc
0x18004a816  lea     rax, [rbp+pszDest]
0x18004a81a  mov     rdx, r15; cchDest
0x18004a81d  mov     rcx, rdi; pszDest
0x18004a820  mov     [rsp+60h+ppszDestEnd], rax; ppszDestEnd
0x18004a825  call    StringCchCopyNExW
0x18004a82a  mov     ebx, eax
0x18004a82c  test    eax, eax
0x18004a82e  js      short loc_18004A898
0x18004a830  test    esi, esi
0x18004a832  jz      short loc_18004A866
0x18004a834  mov     rdx, [rbp+pszSrc]; cchDest
0x18004a838  lea     rax, [rbp+pszSrc]
0x18004a83c  mov     rcx, [rbp+pszDest]; pszDest
0x18004a840  lea     r8, pszSrc; "\\"
0x18004a847  mov     [rsp+60h+pcchRemaining], rax; pcchRemaining
0x18004a84c  mov     r9d, 1; cchToCopy
0x18004a852  lea     rax, [rbp+pszDest]
0x18004a856  mov     [rsp+60h+ppszDestEnd], rax; ppszDestEnd
0x18004a85b  call    StringCchCopyNExW
0x18004a860  mov     ebx, eax
0x18004a862  test    eax, eax
0x18004a864  js      short loc_18004A898
0x18004a866  mov     rdx, [rbp+pszSrc]; cchDest
0x18004a86a  lea     r8, aParameters; "Parameters"
0x18004a871  mov     rcx, [rbp+pszDest]; pszDest
0x18004a875  mov     r9d, 0Ah; cchToCopy
0x18004a87b  call    StringCchCopyNW
0x18004a880  mov     ebx, eax
0x18004a882  test    eax, eax
0x18004a884  js      short loc_18004A898
0x18004a886  mov     rax, gs:30h
0x18004a88f  mov     esi, r13d
0x18004a892  mov     [rax+68h], r13d
0x18004a896  jmp     short loc_18004A904
0x18004a898  mov     rcx, gs:60h
0x18004a8a1  mov     r8, rdi; P
0x18004a8a4  xor     edx, edx; Flags
0x18004a8a6  mov     rcx, [rcx+30h]; HeapHandle
0x18004a8aa  call    cs:__imp_RtlFreeHeap
0x18004a8b0  mov     rax, gs:30h
0x18004a8b9  movzx   ecx, bx
0x18004a8bc  mov     [rax+68h], ecx
0x18004a8bf  jmp     short loc_18004A8D1
0x18004a8c1  mov     rax, gs:30h
0x18004a8ca  mov     dword ptr [rax+68h], 57h ; 'W'
0x18004a8d1  mov     rdi, r13
0x18004a8d4  mov     r15, r13
0x18004a8d7  call    cs:__imp_GetLastError
0x18004a8dd  mov     ebx, 80070000h
0x18004a8e2  test    eax, eax
0x18004a8e4  jle     short loc_18004A8ED
0x18004a8e6  movzx   eax, ax
0x18004a8e9  or      eax, ebx
0x18004a8eb  test    eax, eax
0x18004a8ed  jns     short loc_18004A90D
0x18004a8ef  call    cs:__imp_GetLastError
0x18004a8f5  mov     esi, eax
0x18004a8f7  test    eax, eax
0x18004a8f9  jle     short loc_18004A900
0x18004a8fb  movzx   esi, ax
0x18004a8fe  or      esi, ebx
0x18004a900  test    esi, esi
0x18004a902  js      short loc_18004A912
0x18004a904  mov     [r12], rdi
0x18004a908  jmp     loc_18004A99B
0x18004a90d  mov     esi, 80004005h
0x18004a912  mov     r12d, esi
0x18004a915  call    cs:__imp_GetLastError
0x18004a91b  mov     edi, eax
0x18004a91d  call    cs:__imp_CurrentIP
0x18004a923  mov     r8d, esi
0x18004a926  lea     rdx, aWsbkgetparamet_0; "WsbkGetParametersKeyName: Failed to bui"...
0x18004a92d  mov     ecx, 2000000h; unsigned int
0x18004a932  mov     rbx, rax
0x18004a935  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a93a  mov     [rsp+60h+var_10], r13d
0x18004a93f  lea     rcx, aWsbkgetparamet_1; "WsbkGetParametersKeyName"
0x18004a946  mov     [rsp+60h+var_18], r13
0x18004a94b  lea     r8, aD; "D"
0x18004a952  mov     [rsp+60h+var_20], edi
0x18004a956  xor     r9d, r9d
0x18004a959  mov     [rsp+60h+var_28], rbx
0x18004a95e  xor     edx, edx
0x18004a960  mov     [rsp+60h+var_30], rcx
0x18004a965  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004a96c  mov     [rsp+60h+pcchRemaining], rcx
0x18004a971  mov     rcx, rax
0x18004a974  mov     dword ptr [rsp+60h+ppszDestEnd], 0BF1h
0x18004a97c  call    cs:__imp_WdsSetupLogMessageW
0x18004a982  test    r15, r15
0x18004a985  jz      short loc_18004A99B
0x18004a987  call    cs:__imp_GetProcessHeap
0x18004a98d  mov     r8, r15; lpMem
0x18004a990  xor     edx, edx; dwFlags
0x18004a992  mov     rcx, rax; hHeap
0x18004a995  call    cs:__imp_HeapFree
0x18004a99b  test    r14, r14
0x18004a99e  jz      short loc_18004A9B4
0x18004a9a0  call    cs:__imp_GetProcessHeap
0x18004a9a6  mov     r8, r14; lpMem
0x18004a9a9  xor     edx, edx; dwFlags
0x18004a9ab  mov     rcx, rax; hHeap
0x18004a9ae  call    cs:__imp_HeapFree
0x18004a9b4  mov     rbx, [rsp+60h+arg_8]
0x18004a9bc  mov     eax, esi
0x18004a9be  add     rsp, 60h
0x18004a9c2  pop     r15
0x18004a9c4  pop     r14
0x18004a9c6  pop     r13
0x18004a9c8  pop     r12
0x18004a9ca  pop     rdi
0x18004a9cb  pop     rsi
0x18004a9cc  pop     rbp
0x18004a9cd  retn
```
