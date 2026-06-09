# WaasMedic::CServiceHealthPlugin::RunDetectionHelper(ushort const *,long (WaasMedic::CServiceHealthPlugin::*)(ushort const *,bool &),bool &)

- ea: `0x18004c7ec`
- end: `0x18004c9eb`
- name: `?RunDetectionHelper@CServiceHealthPlugin@WaasMedic@@AEAAJPEBGP812@EAAJ0AEA_N@Z1@Z`
- size: `511`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004c9f4`
- `0x18004d1b0`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x1800250e0`
- `0x18002543c`
- `0x180026920`
- `0x18004c7ec`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c8f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c9c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c8f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c9c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c8ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c9b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c8ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c9b4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004c992`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004c992`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004c97c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004c97c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004c8a4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004c8a4`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004c862`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004c920`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004c862`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004c920`

## string_xrefs

- `0x18004c8d2`: `onecore\enduser\waasmedic\lib\plugins\servicehealthplugin.cpp`
- `0x18004c8cb`: `FindFirstFile Failed for search path [%ws]`
- `0x18004c887`: `Looking for xml files in folder %ws`
- `0x18004c99d`: `Failed to form the path to the folder containing registry files ErrorCode = 0x%08x`
- `0x18004c963`: `Failed to append the file name [%ws] to search path [%ws] ErrorCode = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CServiceHealthPlugin::RunDetectionHelper(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        _BYTE *a4)
{
  HRESULT v7; // esi
  WCHAR *v8; // rbx
  WCHAR *FirstFileW; // rdi
  unsigned int LastErrorMsg; // edi
  HANDLE ProcessHeap; // rax
  HRESULT v13; // eax
  HANDLE v14; // rax
  char *v15; // [rsp+20h] [rbp-E0h]
  _BYTE v16[8]; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszPathIn[3]; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR v20[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+708h] [rbp+608h]

  *a4 = 0;
  pszPathIn[0] = 0;
  v7 = WaasMedic::SafeExpandEnvironmentString(a2, (const unsigned __int16 *)pszPathIn, (unsigned __int16 **)a3);
  v8 = (WCHAR *)pszPathIn[0];
  if ( v7 < 0 || (v7 = PathCchCombine(pszPathOut, 0x104u, pszPathIn[0], L"*"), v7 < 0) )
  {
    LogLevelW(
      2u,
      L"Failed to form the path to the folder containing registry files ErrorCode = 0x%08x",
      (unsigned int)v7);
  }
  else
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    LogLevelW(4u, L"Looking for xml files in folder %ws", v8);
    FirstFileW = (WCHAR *)FindFirstFileW(pszPathOut, &FindFileData);
    pszPathIn[1] = FirstFileW;
    if ( FirstFileW == (WCHAR *)-1LL )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0xE1,
                       (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicehealthplugin.cpp",
                       "FindFirstFile Failed for search path [%ws]",
                       (const char *)pszPathOut);
      if ( v8 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
      }
      return LastErrorMsg;
    }
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v13 = PathCchCombine(v20, 0x104u, v8, FindFileData.cFileName);
        v7 = v13;
        if ( v13 < 0 )
        {
          LODWORD(v15) = v13;
          LogLevelW(
            3u,
            L"Failed to append the file name [%ws] to search path [%ws] ErrorCode = 0x%08x",
            FindFileData.cFileName,
            v8,
            v15);
        }
        else
        {
          v16[0] = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, WCHAR *, _BYTE *))a3)(a1 + *(int *)(a3 + 8), v20, v16);
          *a4 |= v16[0];
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( FirstFileW )
      FindClose(FirstFileW);
  }
  if ( v8 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004c7ec  push    rbp
0x18004c7ee  push    rbx
0x18004c7ef  push    rsi
0x18004c7f0  push    rdi
0x18004c7f1  push    r12
0x18004c7f3  push    r14
0x18004c7f5  push    r15
0x18004c7f7  lea     rbp, [rsp-5D0h]
0x18004c7ff  sub     rsp, 6D0h
0x18004c806  mov     rax, cs:__security_cookie
0x18004c80d  xor     rax, rsp
0x18004c810  mov     [rbp+600h+var_40], rax
0x18004c817  mov     r14, r9
0x18004c81a  mov     r15, r8
0x18004c81d  mov     rax, rdx
0x18004c820  mov     r12, rcx
0x18004c823  mov     byte ptr [r9], 0
0x18004c827  mov     [rsp+700h+pszPathIn], 0
0x18004c830  lea     rdx, [rsp+700h+pszPathIn]; unsigned __int16 *
0x18004c835  mov     rcx, rax; lpSrc
0x18004c838  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x18004c83d  mov     esi, eax
0x18004c83f  mov     rbx, [rsp+700h+pszPathIn]
0x18004c844  test    eax, eax
0x18004c846  js      loc_18004C99A
0x18004c84c  lea     r9, pszMore; "*"
0x18004c853  mov     r8, rbx; pszPathIn
0x18004c856  mov     edx, 104h; cchPathOut
0x18004c85b  lea     rcx, [rbp+600h+pszPathOut]; pszPathOut
0x18004c862  call    cs:__imp_PathCchCombine
0x18004c868  mov     esi, eax
0x18004c86a  test    eax, eax
0x18004c86c  js      loc_18004C99A
0x18004c872  xor     edx, edx; Val
0x18004c874  mov     r8d, 250h; Size
0x18004c87a  lea     rcx, [rsp+700h+FindFileData]; void *
0x18004c87f  call    memset_0
0x18004c884  mov     r8, rbx
0x18004c887  lea     rdx, aLookingForXmlF; "Looking for xml files in folder %ws"
0x18004c88e  mov     ecx, 4; unsigned __int8
0x18004c893  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c898  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x18004c89d  lea     rcx, [rbp+600h+pszPathOut]; lpFileName
0x18004c8a4  call    cs:__imp_FindFirstFileW
0x18004c8aa  mov     rdi, rax
0x18004c8ad  mov     [rsp+700h+var_6C0], rax
0x18004c8b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004c8b6  jnz     short loc_18004C905
0x18004c8b8  mov     rcx, [rbp+608h]; this
0x18004c8bf  lea     rax, [rbp+600h+pszPathOut]
0x18004c8c6  mov     [rsp+700h+var_6E0], rax; char *
0x18004c8cb  lea     r9, aFindfirstfileF; "FindFirstFile Failed for search path [%"...
0x18004c8d2  lea     r8, aOnecoreEnduser_40; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004c8d9  mov     edx, 0E1h; void *
0x18004c8de  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18004c8e3  mov     edi, eax
0x18004c8e5  test    rbx, rbx
0x18004c8e8  jz      short loc_18004C8FE
0x18004c8ea  call    cs:__imp_GetProcessHeap
0x18004c8f0  mov     rcx, rax; hHeap
0x18004c8f3  mov     r8, rbx; lpMem
0x18004c8f6  xor     edx, edx; dwFlags
0x18004c8f8  call    cs:__imp_HeapFree
0x18004c8fe  mov     eax, edi
0x18004c900  jmp     loc_18004C9CA
0x18004c905  test    byte ptr [rsp+700h+FindFileData.dwFileAttributes], 10h
0x18004c90a  jnz     short loc_18004C974
0x18004c90c  lea     r9, [rsp+700h+FindFileData.cFileName]; pszMore
0x18004c911  mov     r8, rbx; pszPathIn
0x18004c914  mov     edx, 104h; cchPathOut
0x18004c919  lea     rcx, [rbp+600h+var_250]; pszPathOut
0x18004c920  call    cs:__imp_PathCchCombine
0x18004c926  mov     esi, eax
0x18004c928  test    eax, eax
0x18004c92a  js      short loc_18004C957
0x18004c92c  mov     [rsp+700h+var_6D0], 0
0x18004c931  movsxd  rcx, dword ptr [r15+8]
0x18004c935  add     rcx, r12
0x18004c938  lea     r8, [rsp+700h+var_6D0]
0x18004c93d  lea     rdx, [rbp+600h+var_250]
0x18004c944  mov     rax, [r15]
0x18004c947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c94c  mov     esi, eax
0x18004c94e  mov     al, [rsp+700h+var_6D0]
0x18004c952  or      [r14], al
0x18004c955  jmp     short loc_18004C974
0x18004c957  mov     dword ptr [rsp+700h+var_6E0], eax
0x18004c95b  mov     r9, rbx
0x18004c95e  lea     r8, [rsp+700h+FindFileData.cFileName]
0x18004c963  lea     rdx, aFailedToAppend_0; "Failed to append the file name [%ws] to"...
0x18004c96a  mov     ecx, 3; unsigned __int8
0x18004c96f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c974  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x18004c979  mov     rcx, rdi; hFindFile
0x18004c97c  call    cs:__imp_FindNextFileW
0x18004c982  test    eax, eax
0x18004c984  jnz     loc_18004C905
0x18004c98a  test    rdi, rdi
0x18004c98d  jz      short loc_18004C9AF
0x18004c98f  mov     rcx, rdi; hFindFile
0x18004c992  call    cs:__imp_FindClose
0x18004c998  jmp     short loc_18004C9AF
0x18004c99a  mov     r8d, esi
0x18004c99d  lea     rdx, aFailedToFormTh; "Failed to form the path to the folder c"...
0x18004c9a4  mov     ecx, 2; unsigned __int8
0x18004c9a9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c9ae  nop
0x18004c9af  test    rbx, rbx
0x18004c9b2  jz      short loc_18004C9C8
0x18004c9b4  call    cs:__imp_GetProcessHeap
0x18004c9ba  mov     rcx, rax; hHeap
0x18004c9bd  mov     r8, rbx; lpMem
0x18004c9c0  xor     edx, edx; dwFlags
0x18004c9c2  call    cs:__imp_HeapFree
0x18004c9c8  mov     eax, esi
0x18004c9ca  mov     rcx, [rbp+600h+var_40]
0x18004c9d1  xor     rcx, rsp; StackCookie
0x18004c9d4  call    __security_check_cookie
0x18004c9d9  add     rsp, 6D0h
0x18004c9e0  pop     r15
0x18004c9e2  pop     r14
0x18004c9e4  pop     r12
0x18004c9e6  pop     rdi
0x18004c9e7  pop     rsi
0x18004c9e8  pop     rbx
0x18004c9e9  pop     rbp
0x18004c9ea  retn
```
