# FindCallerExeInFolder(ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ushort *,ulong)

- ea: `0x180024f80`
- end: `0x180025166`
- name: `?FindCallerExeInFolder@@YAXPEAGV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0K@Z`
- size: `486`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180024f80`
- `0x1800298e4`

## callees

- `0x180023a78`
- `0x180024f80`
- `0x18002636c`
- `0x180027d04`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180025154`
- `msvcrt!wcscpy_s` at `0x180025154`
- `msvcrt!_wcsicmp` at `0x180025035`
- `msvcrt!_wcsicmp` at `0x18002504f`
- `msvcrt!_wcsicmp` at `0x1800250c5`
- `msvcrt!_wcsicmp` at `0x180025035`
- `msvcrt!_wcsicmp` at `0x18002504f`
- `msvcrt!_wcsicmp` at `0x1800250c5`
- `SHLWAPI!PathCombineW` at `0x180024ffb`
- `SHLWAPI!PathCombineW` at `0x18002506c`
- `SHLWAPI!PathCombineW` at `0x180024ffb`
- `SHLWAPI!PathCombineW` at `0x18002506c`
- `SHLWAPI!PathFindExtensionW` at `0x1800250aa`
- `SHLWAPI!PathFindExtensionW` at `0x1800250aa`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800250f7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800250f7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002510d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002510d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180025016`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180025016`

## pseudocode

```c
void __fastcall FindCallerExeInFolder(wchar_t *a1, LPCWSTR *a2, wchar_t *a3)
{
  HANDLE FirstFileW; // rdi
  __int64 v7; // rax
  const wchar_t *ExtensionW; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v10[8]; // [rsp+28h] [rbp-D8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszDest[264]; // [rsp+490h] [rbp+390h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !dword_180078CF4 )
  {
    if ( a1 )
    {
      if ( *a1 )
      {
        if ( PathCombineW(pszDest, *a2, L"*") )
        {
          FirstFileW = FindFirstFileW(pszDest, &FindFileData);
          if ( FirstFileW != (HANDLE)-1LL )
          {
            do
            {
              if ( _wcsicmp(FindFileData.cFileName, L"..")
                && _wcsicmp(FindFileData.cFileName, L".")
                && PathCombineW(pszPath, *a2, FindFileData.cFileName) )
              {
                if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
                  v7 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                         v9,
                         pszPath);
                  FindCallerExeInFolder(a1, v7, a3);
                }
                ExtensionW = PathFindExtensionW(pszPath);
                if ( ExtensionW )
                {
                  if ( *ExtensionW )
                  {
                    if ( !_wcsicmp(ExtensionW, L".lnk") )
                    {
                      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                        v10,
                        pszPath);
                      if ( (unsigned int)IsCallerExeMatchingTargetShortcut(a1) )
                      {
                        wcscpy_s(a3, 0x104u, pszPath);
                        dword_180078CF4 = 1;
                        goto LABEL_18;
                      }
                    }
                  }
                }
              }
            }
            while ( FindNextFileW(FirstFileW, &FindFileData) );
            if ( FirstFileW )
              FindClose(FirstFileW);
          }
        }
      }
    }
  }
LABEL_18:
  ATL::CStringData::Release((ATL::CStringData *)(*a2 - 12));
}

```

## disassembly

```asm
0x180024f80  mov     [rsp-8+arg_18], rbx
0x180024f85  push    rbp
0x180024f86  push    rsi
0x180024f87  push    rdi
0x180024f88  push    r14
0x180024f8a  push    r15
0x180024f8c  lea     rbp, [rsp-5B0h]
0x180024f94  sub     rsp, 6B0h
0x180024f9b  mov     rax, cs:__security_cookie
0x180024fa2  xor     rax, rsp
0x180024fa5  mov     [rbp+5D0h+var_30], rax
0x180024fac  mov     r14, r8
0x180024faf  mov     rbx, rdx
0x180024fb2  mov     rsi, rcx
0x180024fb5  xor     edx, edx; Val
0x180024fb7  mov     r8d, 250h; Size
0x180024fbd  lea     rcx, [rsp+6D0h+FindFileData]; void *
0x180024fc2  call    memset_0
0x180024fc7  xor     r15d, r15d
0x180024fca  cmp     cs:dword_180078CF4, r15d
0x180024fd1  jnz     loc_180025113
0x180024fd7  test    rsi, rsi
0x180024fda  jz      loc_180025113
0x180024fe0  cmp     [rsi], r15w
0x180024fe4  jz      loc_180025113
0x180024fea  mov     rdx, [rbx]; pszDir
0x180024fed  lea     r8, pszFile; "*"
0x180024ff4  lea     rcx, [rbp+5D0h+pszDest]; pszDest
0x180024ffb  call    cs:__imp_PathCombineW
0x180025001  test    rax, rax
0x180025004  jz      loc_180025113
0x18002500a  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x18002500f  lea     rcx, [rbp+5D0h+pszDest]; lpFileName
0x180025016  call    cs:__imp_FindFirstFileW
0x18002501c  mov     rdi, rax
0x18002501f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025023  jz      loc_180025113
0x180025029  lea     rdx, asc_1800653A4; ".."
0x180025030  lea     rcx, [rsp+6D0h+FindFileData.cFileName]; String1
0x180025035  call    cs:__imp__wcsicmp
0x18002503b  test    eax, eax
0x18002503d  jz      loc_1800250EF
0x180025043  lea     rdx, asc_1800653AC; "."
0x18002504a  lea     rcx, [rsp+6D0h+FindFileData.cFileName]; String1
0x18002504f  call    cs:__imp__wcsicmp
0x180025055  test    eax, eax
0x180025057  jz      loc_1800250EF
0x18002505d  mov     rdx, [rbx]; pszDir
0x180025060  lea     r8, [rsp+6D0h+FindFileData.cFileName]; pszFile
0x180025065  lea     rcx, [rbp+5D0h+pszPath]; pszDest
0x18002506c  call    cs:__imp_PathCombineW
0x180025072  test    rax, rax
0x180025075  jz      short loc_1800250EF
0x180025077  test    byte ptr [rsp+6D0h+FindFileData.dwFileAttributes], 10h
0x18002507c  jz      short loc_1800250A3
0x18002507e  lea     rdx, [rbp+5D0h+pszPath]
0x180025085  lea     rcx, [rsp+6D0h+var_6B0]
0x18002508a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002508f  mov     rdx, rax
0x180025092  mov     r9d, 104h
0x180025098  mov     r8, r14
0x18002509b  mov     rcx, rsi
0x18002509e  call    ?FindCallerExeInFolder@@YAXPEAGV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0K@Z; FindCallerExeInFolder(ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ushort *,ulong)
0x1800250a3  lea     rcx, [rbp+5D0h+pszPath]; pszPath
0x1800250aa  call    cs:__imp_PathFindExtensionW
0x1800250b0  test    rax, rax
0x1800250b3  jz      short loc_1800250EF
0x1800250b5  cmp     r15w, [rax]
0x1800250b9  jz      short loc_1800250EF
0x1800250bb  lea     rdx, aLnk; ".lnk"
0x1800250c2  mov     rcx, rax; String1
0x1800250c5  call    cs:__imp__wcsicmp
0x1800250cb  test    eax, eax
0x1800250cd  jnz     short loc_1800250EF
0x1800250cf  lea     rdx, [rbp+5D0h+pszPath]
0x1800250d6  lea     rcx, [rsp+6D0h+var_6A8]
0x1800250db  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800250e0  mov     rdx, rax
0x1800250e3  mov     rcx, rsi; SubStr
0x1800250e6  call    ?IsCallerExeMatchingTargetShortcut@@YAHPEAGV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IsCallerExeMatchingTargetShortcut(ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x1800250eb  test    eax, eax
0x1800250ed  jnz     short loc_180025145
0x1800250ef  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x1800250f4  mov     rcx, rdi; hFindFile
0x1800250f7  call    cs:__imp_FindNextFileW
0x1800250fd  test    eax, eax
0x1800250ff  jnz     loc_180025029
0x180025105  test    rdi, rdi
0x180025108  jz      short loc_180025113
0x18002510a  mov     rcx, rdi; hFindFile
0x18002510d  call    cs:__imp_FindClose
0x180025113  mov     rcx, [rbx]
0x180025116  sub     rcx, 18h; this
0x18002511a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002511f  mov     rcx, [rbp+5D0h+var_30]
0x180025126  xor     rcx, rsp; StackCookie
0x180025129  call    __security_check_cookie
0x18002512e  mov     rbx, [rsp+6D0h+arg_18]
0x180025136  add     rsp, 6B0h
0x18002513d  pop     r15
0x18002513f  pop     r14
0x180025141  pop     rdi
0x180025142  pop     rsi
0x180025143  pop     rbp
0x180025144  retn
0x180025145  lea     r8, [rbp+5D0h+pszPath]; Source
0x18002514c  mov     edx, 104h; SizeInWords
0x180025151  mov     rcx, r14; Destination
0x180025154  call    cs:__imp_wcscpy_s
0x18002515a  mov     cs:dword_180078CF4, 1
0x180025164  jmp     short loc_180025113
```
