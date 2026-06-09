# EnsureHtmlDocumentInitializedForOneCore(void)

- ea: `0x180007660`
- end: `0x180007812`
- name: `?EnsureHtmlDocumentInitializedForOneCore@@YAJXZ`
- size: `434`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800078b0`
- `0x1800079d0`

## callees

- `0x180007660`
- `0x18000a00c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800076d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000773d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800076d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000773d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077fb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800076b1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800076b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000776a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000776a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007797`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007797`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000768e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000768e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800076ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800076ca`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1800077bc`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1800077bc`

## string_xrefs

- `0x180007750`: `mshtml.dll`
- `0x18000775a`: `edgehtml.dll`

## pseudocode

```c
__int64 EnsureHtmlDocumentInitializedForOneCore(void)
{
  char *v0; // rdi
  unsigned __int64 CurrentProcessWebPlatformVersionUncached; // rax
  bool v2; // bp
  signed int v3; // ebx
  const WCHAR *v4; // rcx
  HMODULE v5; // rcx
  FARPROC ProcAddress; // rax
  __int64 v7; // rdx
  signed int LastError; // eax
  WINBOOL v10; // [rsp+40h] [rbp+8h] BYREF
  char *v11; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  v11 = 0;
  InitOnceBeginInitialize(&g_trident, 0, &v10, (LPVOID *)&v11);
  v0 = v11;
  if ( !v11 )
  {
    byte_180011A50 = 0;
    InitializeCriticalSectionEx(&stru_180011A58, 0, 0);
    v0 = &byte_180011A50;
    InitOnceComplete(&g_trident, 0, &byte_180011A50);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v0 + 8));
  if ( *v0 )
    goto LABEL_22;
  if ( dword_180011948 )
  {
    CurrentProcessWebPlatformVersionUncached = qword_180011940;
  }
  else
  {
    CurrentProcessWebPlatformVersionUncached = GetCurrentProcessWebPlatformVersionUncached();
    qword_180011940 = CurrentProcessWebPlatformVersionUncached;
    dword_180011948 = 1;
  }
  v2 = CurrentProcessWebPlatformVersionUncached >= 0x6000400000000LL;
  _InterlockedIncrement(&dword_180011934);
  if ( hLibModule )
    goto LABEL_21;
  v3 = 0;
  EnterCriticalSection(&g_critSecLock);
  if ( !hLibModule )
  {
    v4 = L"edgehtml.dll";
    if ( !v2 )
      v4 = L"mshtml.dll";
    hLibModule = LoadLibraryExW(v4, 0, 0);
    v5 = hLibModule;
    if ( hLibModule )
    {
      ProcAddress = (FARPROC)qword_180011960;
      if ( qword_180011960
        || (v3 = -2147467263,
            ProcAddress = GetProcAddress(hLibModule, "InitializeLocalHtmlEngine"),
            (qword_180011960 = (__int64)ProcAddress) != 0) )
      {
        v3 = ((__int64 (__fastcall *)(HMODULE))ProcAddress)(v5);
      }
      if ( v3 >= 0 )
      {
        LOBYTE(v7) = v2;
        IEConfiguration_SetBool(536870927, v7);
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  LeaveCriticalSection(&g_critSecLock);
  if ( v3 >= 0 )
  {
LABEL_21:
    *v0 = 1;
LABEL_22:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v0 + 8));
    return 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v0 + 8));
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007660  mov     rax, rsp
0x180007663  mov     [rax+18h], rbx
0x180007667  push    rbp
0x180007668  push    rsi
0x180007669  push    rdi
0x18000766a  sub     rsp, 20h
0x18000766e  lea     r9, [rax+10h]; lpContext
0x180007672  mov     dword ptr [rax+8], 0
0x180007679  lea     r8, [rax+8]; fPending
0x18000767d  mov     qword ptr [rax+10h], 0
0x180007685  xor     edx, edx; dwFlags
0x180007687  lea     rcx, ?g_trident@@3V?$static_lazy@VTridentHtmlManager@@$0A@V?$lazy_construct@VTridentHtmlManager@@@tlx@@@tlx@@A; lpInitOnce
0x18000768e  call    cs:__imp_InitOnceBeginInitialize
0x180007694  mov     rdi, [rsp+38h+arg_8]
0x180007699  test    rdi, rdi
0x18000769c  jnz     short loc_1800076D0
0x18000769e  xor     r8d, r8d; Flags
0x1800076a1  mov     cs:byte_180011A50, dil
0x1800076a8  xor     edx, edx; dwSpinCount
0x1800076aa  lea     rcx, stru_180011A58; lpCriticalSection
0x1800076b1  call    cs:__imp_InitializeCriticalSectionEx
0x1800076b7  lea     rdi, byte_180011A50
0x1800076be  xor     edx, edx; dwFlags
0x1800076c0  mov     r8, rdi; lpContext
0x1800076c3  lea     rcx, ?g_trident@@3V?$static_lazy@VTridentHtmlManager@@$0A@V?$lazy_construct@VTridentHtmlManager@@@tlx@@@tlx@@A; lpInitOnce
0x1800076ca  call    cs:__imp_InitOnceComplete
0x1800076d0  lea     rsi, [rdi+8]
0x1800076d4  mov     rcx, rsi; lpCriticalSection
0x1800076d7  call    cs:__imp_EnterCriticalSection
0x1800076dd  cmp     byte ptr [rdi], 0
0x1800076e0  jnz     loc_1800077F8
0x1800076e6  cmp     cs:dword_180011948, 0
0x1800076ed  jnz     short loc_180007707
0x1800076ef  call    GetCurrentProcessWebPlatformVersionUncached
0x1800076f4  mov     cs:qword_180011940, rax
0x1800076fb  mov     cs:dword_180011948, 1
0x180007705  jmp     short loc_18000770E
0x180007707  mov     rax, cs:qword_180011940
0x18000770e  mov     rcx, 6000400000000h
0x180007718  cmp     rax, rcx
0x18000771b  setnb   bpl
0x18000771f  lock inc cs:dword_180011934
0x180007726  cmp     cs:hLibModule, 0
0x18000772e  jnz     loc_1800077F5
0x180007734  lea     rcx, ?g_critSecLock@@3VTridentVersionHelper_StaticLock@@A; lpCriticalSection
0x18000773b  xor     ebx, ebx
0x18000773d  call    cs:__imp_EnterCriticalSection
0x180007743  cmp     cs:hLibModule, rbx
0x18000774a  jnz     loc_1800077D9
0x180007750  lea     rax, LibFileName; "mshtml.dll"
0x180007757  test    bpl, bpl
0x18000775a  lea     rcx, aEdgehtmlDll; "edgehtml.dll"
0x180007761  cmovz   rcx, rax; lpLibFileName
0x180007765  xor     r8d, r8d; dwFlags
0x180007768  xor     edx, edx; hFile
0x18000776a  call    cs:__imp_LoadLibraryExW
0x180007770  mov     cs:hLibModule, rax
0x180007777  mov     rcx, rax; hModule
0x18000777a  test    rax, rax
0x18000777d  jz      short loc_1800077C4
0x18000777f  mov     rax, cs:qword_180011960
0x180007786  test    rax, rax
0x180007789  jnz     short loc_1800077A9
0x18000778b  lea     rdx, aInitializeloca; "InitializeLocalHtmlEngine"
0x180007792  mov     ebx, 80004001h
0x180007797  call    cs:__imp_GetProcAddress
0x18000779d  mov     cs:qword_180011960, rax
0x1800077a4  test    rax, rax
0x1800077a7  jz      short loc_1800077B0
0x1800077a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ae  mov     ebx, eax
0x1800077b0  test    ebx, ebx
0x1800077b2  js      short loc_1800077D9
0x1800077b4  mov     dl, bpl
0x1800077b7  mov     ecx, 2000000Fh
0x1800077bc  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1800077c2  jmp     short loc_1800077D9
0x1800077c4  call    cs:__imp_GetLastError
0x1800077ca  mov     ebx, eax
0x1800077cc  test    eax, eax
0x1800077ce  jle     short loc_1800077D9
0x1800077d0  movzx   ebx, ax
0x1800077d3  or      ebx, 80070000h
0x1800077d9  lea     rcx, ?g_critSecLock@@3VTridentVersionHelper_StaticLock@@A; lpCriticalSection
0x1800077e0  call    cs:__imp_LeaveCriticalSection
0x1800077e6  test    ebx, ebx
0x1800077e8  jns     short loc_1800077F5
0x1800077ea  mov     rcx, rsi; lpCriticalSection
0x1800077ed  call    cs:__imp_LeaveCriticalSection
0x1800077f3  jmp     short loc_180007803
0x1800077f5  mov     byte ptr [rdi], 1
0x1800077f8  mov     rcx, rsi; lpCriticalSection
0x1800077fb  call    cs:__imp_LeaveCriticalSection
0x180007801  xor     ebx, ebx
0x180007803  mov     eax, ebx
0x180007805  mov     rbx, [rsp+38h+arg_10]
0x18000780a  add     rsp, 20h
0x18000780e  pop     rdi
0x18000780f  pop     rsi
0x180007810  pop     rbp
0x180007811  retn
```
