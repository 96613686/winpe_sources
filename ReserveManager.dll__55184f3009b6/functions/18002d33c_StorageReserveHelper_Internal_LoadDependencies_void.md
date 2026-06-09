# StorageReserveHelper::Internal::LoadDependencies(void)

- ea: `0x18002d33c`
- end: `0x18002d48b`
- name: `?LoadDependencies@Internal@StorageReserveHelper@@YAJXZ`
- size: `335`
- prototype: `__int64 __fastcall(StorageReserveHelper::Internal *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800262e0`
- `0x180027414`
- `0x1800287e4`
- `0x18002d6a0`

## callees

- `0x180007930`
- `0x18000a0cc`
- `0x18002d33c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002d3ff`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002d424`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002d473`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002d3ff`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002d424`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002d473`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d397`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d3bd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d3e3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d453`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d397`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d3bd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d3e3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002d453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d419`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d42c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d42c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18002d35c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18002d410`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18002d35c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18002d410`

## string_xrefs

- `0x18002d409`: `ntdll.dll`
- `0x18002d355`: `kernelbase.dll`
- `0x18002d38d`: `PathCchCombineEx`
- `0x18002d3d9`: `PathAllocCanonicalize`
- `0x18002d3b3`: `PathAllocCombine`
- `0x18002d449`: `RtlIsNonEmptyDirectoryReparsePointAllowed`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::Internal::LoadDependencies(StorageReserveHelper::Internal *this)
{
  HMODULE LibraryW; // rax
  const char *v2; // r9
  HMODULE v3; // rbx
  __int64 v4; // rdx
  wil::details *v6; // rcx
  unsigned int v7; // edi
  HMODULE v8; // rsi
  DWORD LastError; // edi
  wil::details *v10; // rcx
  unsigned int LastErrorFailHr; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  LibraryW = LoadLibraryW(L"kernelbase.dll");
  v3 = LibraryW;
  if ( !LibraryW )
  {
    v4 = 25;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
             v2);
  }
  if ( (StorageReserveHelper::Internal::pfnPathCchCombineEx
     || (StorageReserveHelper::Internal::pfnPathCchCombineEx = (int (*)(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned int))GetProcAddress(LibraryW, "PathCchCombineEx")) != 0)
    && (StorageReserveHelper::Internal::pfnPathAllocCombine
     || (StorageReserveHelper::Internal::pfnPathAllocCombine = (int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **))GetProcAddress(v3, "PathAllocCombine")) != 0)
    && (StorageReserveHelper::Internal::pfnPathAllocCanonicalize
     || (StorageReserveHelper::Internal::pfnPathAllocCanonicalize = (int (*)(const unsigned __int16 *, unsigned int, unsigned __int16 **))GetProcAddress(v3, "PathAllocCanonicalize")) != 0) )
  {
    v8 = LoadLibraryW(L"ntdll.dll");
    LastError = GetLastError();
    FreeLibrary(v3);
    SetLastError(LastError);
    if ( !v8 )
    {
      v4 = 46;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v4,
               (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
               v2);
    }
    if ( StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed
      || (StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed = (unsigned __int8 (*)(unsigned int))GetProcAddress(v8, "RtlIsNonEmptyDirectoryReparsePointAllowed")) != 0 )
    {
      LastErrorFailHr = 0;
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
    }
    FreeLibrary(v8);
    return LastErrorFailHr;
  }
  else
  {
    v7 = wil::details::GetLastErrorFailHr(v6);
    FreeLibrary(v3);
    return v7;
  }
}

```

## disassembly

```asm
0x18002d33c  push    rdi
0x18002d33e  sub     rsp, 30h
0x18002d342  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002d34b  mov     [rsp+38h+arg_0], rbx
0x18002d350  mov     [rsp+38h+arg_8], rsi
0x18002d355  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002d35c  call    cs:__imp_LoadLibraryW
0x18002d362  mov     rbx, rax
0x18002d365  test    rax, rax
0x18002d368  jnz     short loc_18002D383
0x18002d36a  lea     edx, [rax+19h]; void *
0x18002d36d  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d374  mov     rcx, [rsp+38h]; this
0x18002d379  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d37e  jmp     loc_18002D47B
0x18002d383  cmp     cs:?pfnPathCchCombineEx@Internal@StorageReserveHelper@@3P6AJPEAG_KPEBG2K@ZEA, 0; long (*StorageReserveHelper::Internal::pfnPathCchCombineEx)(ushort *,unsigned __int64,ushort const *,ushort const *,ulong)
0x18002d38b  jnz     short loc_18002D3A9
0x18002d38d  lea     rdx, aPathcchcombine; "PathCchCombineEx"
0x18002d394  mov     rcx, rbx; hModule
0x18002d397  call    cs:__imp_GetProcAddress
0x18002d39d  mov     cs:?pfnPathCchCombineEx@Internal@StorageReserveHelper@@3P6AJPEAG_KPEBG2K@ZEA, rax; long (*StorageReserveHelper::Internal::pfnPathCchCombineEx)(ushort *,unsigned __int64,ushort const *,ushort const *,ulong)
0x18002d3a4  test    rax, rax
0x18002d3a7  jz      short loc_18002D3F5
0x18002d3a9  cmp     cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA, 0; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x18002d3b1  jnz     short loc_18002D3CF
0x18002d3b3  lea     rdx, aPathalloccombi; "PathAllocCombine"
0x18002d3ba  mov     rcx, rbx; hModule
0x18002d3bd  call    cs:__imp_GetProcAddress
0x18002d3c3  mov     cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA, rax; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x18002d3ca  test    rax, rax
0x18002d3cd  jz      short loc_18002D3F5
0x18002d3cf  cmp     cs:?pfnPathAllocCanonicalize@Internal@StorageReserveHelper@@3P6AJPEBGKPEAPEAG@ZEA, 0; long (*StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(ushort const *,ulong,ushort * *)
0x18002d3d7  jnz     short loc_18002D409
0x18002d3d9  lea     rdx, aPathalloccanon; "PathAllocCanonicalize"
0x18002d3e0  mov     rcx, rbx; hModule
0x18002d3e3  call    cs:__imp_GetProcAddress
0x18002d3e9  mov     cs:?pfnPathAllocCanonicalize@Internal@StorageReserveHelper@@3P6AJPEBGKPEAPEAG@ZEA, rax; long (*StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(ushort const *,ulong,ushort * *)
0x18002d3f0  test    rax, rax
0x18002d3f3  jnz     short loc_18002D409
0x18002d3f5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002d3fa  mov     edi, eax
0x18002d3fc  mov     rcx, rbx; hLibModule
0x18002d3ff  call    cs:__imp_FreeLibrary
0x18002d405  mov     eax, edi
0x18002d407  jmp     short loc_18002D47B
0x18002d409  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18002d410  call    cs:__imp_LoadLibraryW
0x18002d416  mov     rsi, rax
0x18002d419  call    cs:__imp_GetLastError
0x18002d41f  mov     edi, eax
0x18002d421  mov     rcx, rbx; hLibModule
0x18002d424  call    cs:__imp_FreeLibrary
0x18002d42a  mov     ecx, edi; dwErrCode
0x18002d42c  call    cs:__imp_SetLastError
0x18002d432  test    rsi, rsi
0x18002d435  jnz     short loc_18002D43F
0x18002d437  lea     edx, [rsi+2Eh]
0x18002d43a  jmp     loc_18002D36D
0x18002d43f  cmp     cs:?pfnRtlIsNonEmptyDirectoryReparsePointAllowed@Internal@StorageReserveHelper@@3P6AEK@ZEA, 0; uchar (*StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed)(ulong)
0x18002d447  jnz     short loc_18002D46E
0x18002d449  lea     rdx, aRtlisnonemptyd; "RtlIsNonEmptyDirectoryReparsePointAllow"...
0x18002d450  mov     rcx, rsi; hModule
0x18002d453  call    cs:__imp_GetProcAddress
0x18002d459  mov     cs:?pfnRtlIsNonEmptyDirectoryReparsePointAllowed@Internal@StorageReserveHelper@@3P6AEK@ZEA, rax; uchar (*StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed)(ulong)
0x18002d460  test    rax, rax
0x18002d463  jnz     short loc_18002D46E
0x18002d465  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002d46a  mov     ebx, eax
0x18002d46c  jmp     short loc_18002D470
0x18002d46e  xor     ebx, ebx
0x18002d470  mov     rcx, rsi; hLibModule
0x18002d473  call    cs:__imp_FreeLibrary
0x18002d479  mov     eax, ebx
0x18002d47b  mov     rbx, [rsp+38h+arg_0]
0x18002d480  mov     rsi, [rsp+38h+arg_8]
0x18002d485  add     rsp, 30h
0x18002d489  pop     rdi
0x18002d48a  retn
```
