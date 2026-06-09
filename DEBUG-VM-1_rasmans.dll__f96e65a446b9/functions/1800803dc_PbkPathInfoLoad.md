# PbkPathInfoLoad

- ea: `0x1800803dc`
- end: `0x18008069b`
- name: `PbkPathInfoLoad`
- size: `703`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18007a880`
- `0x18007bf90`
- `0x18007c56c`
- `0x18007f9ec`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18005cd78`
- `0x180069ab4`
- `0x1800803dc`
- `0x1800806a4`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800805fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800805fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080420`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080420`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080659`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180080659`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800804c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800804e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800804c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800804e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800804fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080513`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080528`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800804fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080513`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080528`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008046f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008047d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008048b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008046f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008047d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008048b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008043c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080453`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080608`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008061f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080635`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080650`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008043c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080453`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080608`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008061f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080635`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180080650`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800805bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800805bf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18008058a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800805a6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18008058a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800805a6`

## string_xrefs

- `0x1800804ba`: `api-ms-win-core-shlwapi-legacy-l1-1-0.dll`
- `0x1800804d8`: `shlwapi.dll`
- `0x180080508`: `PathRemoveFileSpecW`
- `0x1800804f4`: `PathCanonicalizeW`
- `0x18008051d`: `PathFindFileNameW`
- `0x1800805cd`: `\System32\Ras`

## pseudocode

```c
__int64 __fastcall PbkPathInfoLoad(LPCRITICAL_SECTION lpCriticalSection)
{
  DWORD LastError; // ebx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  void *v4; // rcx
  wchar_t *v5; // rax
  PRTL_CRITICAL_SECTION_DEBUG v6; // rcx
  wchar_t *v7; // rsi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  bool v14; // zf
  PRTL_CRITICAL_SECTION_DEBUG v15; // rbx
  PRTL_CRITICAL_SECTION_DEBUG v16; // rbx
  STRSAFE_LPWSTR *v17; // r9
  HRESULT v18; // eax
  void *v19; // rcx
  size_t *v21; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 82, WPP_38cda081c674317ed40163d707084d83_Traceguids);
  }
  EnterCriticalSection(lpCriticalSection);
  if ( !HIDWORD(lpCriticalSection[1].DebugInfo) )
  {
    DebugInfo = lpCriticalSection[2].DebugInfo;
    if ( DebugInfo )
    {
      GlobalFree(DebugInfo);
      lpCriticalSection[2].DebugInfo = 0;
    }
    v4 = *(void **)&lpCriticalSection[2].LockCount;
    if ( v4 )
    {
      GlobalFree(v4);
      *(_QWORD *)&lpCriticalSection[2].LockCount = 0;
    }
    lpCriticalSection[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)GlobalAlloc(0x40u, 0x20Au);
    *(_QWORD *)&lpCriticalSection[2].LockCount = GlobalAlloc(0x40u, 0x20Au);
    v5 = (wchar_t *)GlobalAlloc(0x40u, 0x20Au);
    v6 = lpCriticalSection[2].DebugInfo;
    v7 = v5;
    if ( v6 )
    {
      if ( *(_QWORD *)&lpCriticalSection[2].LockCount && v5 )
      {
        Library = LoadLibraryExW(L"api-ms-win-core-shlwapi-legacy-l1-1-0.dll", 0, 0x800u);
        *(_QWORD *)&lpCriticalSection[1].LockCount = Library;
        if ( !Library )
        {
          Library = LoadLibraryExW(L"shlwapi.dll", 0, 0x800u);
          *(_QWORD *)&lpCriticalSection[1].LockCount = Library;
          if ( !Library )
            goto LABEL_28;
        }
        ProcAddress = GetProcAddress(Library, "PathCanonicalizeW");
        v10 = *(HMODULE *)&lpCriticalSection[1].LockCount;
        lpCriticalSection[1].OwningThread = ProcAddress;
        v11 = GetProcAddress(v10, "PathRemoveFileSpecW");
        v12 = *(HMODULE *)&lpCriticalSection[1].LockCount;
        lpCriticalSection[1].LockSemaphore = v11;
        v13 = GetProcAddress(v12, "PathFindFileNameW");
        v14 = lpCriticalSection[1].OwningThread == 0;
        lpCriticalSection[1].SpinCount = (ULONG_PTR)v13;
        if ( v14 || !lpCriticalSection[1].LockSemaphore || !v13 )
          goto LABEL_28;
        if ( (unsigned int)GetPhonebookDirectory(0, v7)
          && ((unsigned int (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, wchar_t *))lpCriticalSection[1].OwningThread)(
               lpCriticalSection[2].DebugInfo,
               v7) )
        {
          v15 = lpCriticalSection[2].DebugInfo;
          if ( *((_WORD *)v15 + lstrlenW(&v15->Type) - 1) == 92 )
          {
            v16 = lpCriticalSection[2].DebugInfo;
            *((_WORD *)v16 + lstrlenW(&v16->Type) - 1) = 0;
          }
          if ( GetSystemWindowsDirectoryW(*(LPWSTR *)&lpCriticalSection[2].LockCount, 0xF6u) )
          {
            v18 = StringCchCatExW(
                    *(STRSAFE_LPWSTR *)&lpCriticalSection[2].LockCount,
                    0x105u,
                    L"\\System32\\Ras",
                    v17,
                    v21,
                    0x100u);
            if ( v18 >= 0 )
            {
              LastError = 0;
              HIDWORD(lpCriticalSection[1].DebugInfo) = 1;
              goto LABEL_38;
            }
            LastError = (unsigned __int16)v18;
            goto LABEL_29;
          }
LABEL_28:
          LastError = GetLastError();
LABEL_29:
          if ( !LastError )
            goto LABEL_38;
          goto LABEL_37;
        }
        LastError = 1003;
LABEL_37:
        PbkPathInfoReset(lpCriticalSection);
        if ( !v7 )
          goto LABEL_39;
LABEL_38:
        GlobalFree(v7);
        goto LABEL_39;
      }
      GlobalFree(v6);
    }
    v19 = *(void **)&lpCriticalSection[2].LockCount;
    lpCriticalSection[2].DebugInfo = 0;
    if ( v19 )
      GlobalFree(v19);
    *(_QWORD *)&lpCriticalSection[2].LockCount = 0;
    if ( v7 )
      GlobalFree(v7);
    v7 = 0;
    LastError = 8;
    goto LABEL_37;
  }
  LastError = 0;
LABEL_39:
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 83, WPP_38cda081c674317ed40163d707084d83_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800803dc  push    rbx
0x1800803de  push    rsi
0x1800803df  push    rdi
0x1800803e0  push    r15
0x1800803e2  sub     rsp, 38h
0x1800803e6  mov     rdi, rcx
0x1800803e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800803f0  lea     r15, WPP_GLOBAL_Control
0x1800803f7  cmp     rcx, r15
0x1800803fa  jz      short loc_18008041D
0x1800803fc  test    byte ptr [rcx+1Ch], 80h
0x180080400  jz      short loc_18008041D
0x180080402  cmp     byte ptr [rcx+19h], 6
0x180080406  jb      short loc_18008041D
0x180080408  mov     rcx, [rcx+10h]
0x18008040c  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x180080413  mov     edx, 52h ; 'R'
0x180080418  call    WPP_SF_
0x18008041d  mov     rcx, rdi; lpCriticalSection
0x180080420  call    cs:__imp_EnterCriticalSection
0x180080426  cmp     dword ptr [rdi+2Ch], 0
0x18008042a  jz      short loc_180080433
0x18008042c  xor     ebx, ebx
0x18008042e  jmp     loc_180080656
0x180080433  mov     rcx, [rdi+50h]; hMem
0x180080437  test    rcx, rcx
0x18008043a  jz      short loc_18008044A
0x18008043c  call    cs:__imp_GlobalFree
0x180080442  mov     qword ptr [rdi+50h], 0
0x18008044a  mov     rcx, [rdi+58h]; hMem
0x18008044e  test    rcx, rcx
0x180080451  jz      short loc_180080461
0x180080453  call    cs:__imp_GlobalFree
0x180080459  mov     qword ptr [rdi+58h], 0
0x180080461  mov     esi, 20Ah
0x180080466  mov     ebx, 40h ; '@'
0x18008046b  mov     edx, esi; dwBytes
0x18008046d  mov     ecx, ebx; uFlags
0x18008046f  call    cs:__imp_GlobalAlloc
0x180080475  mov     edx, esi; dwBytes
0x180080477  mov     ecx, ebx; uFlags
0x180080479  mov     [rdi+50h], rax
0x18008047d  call    cs:__imp_GlobalAlloc
0x180080483  mov     edx, esi; dwBytes
0x180080485  mov     ecx, ebx; uFlags
0x180080487  mov     [rdi+58h], rax
0x18008048b  call    cs:__imp_GlobalAlloc
0x180080491  mov     rcx, [rdi+50h]; hMem
0x180080495  mov     rsi, rax
0x180080498  test    rcx, rcx
0x18008049b  jz      loc_18008060E
0x1800804a1  cmp     qword ptr [rdi+58h], 0
0x1800804a6  jz      loc_180080608
0x1800804ac  test    rax, rax
0x1800804af  jz      loc_180080608
0x1800804b5  mov     ebx, 800h
0x1800804ba  lea     rcx, aApiMsWinCoreSh_0; "api-ms-win-core-shlwapi-legacy-l1-1-0.d"...
0x1800804c1  mov     r8d, ebx; dwFlags
0x1800804c4  xor     edx, edx; hFile
0x1800804c6  call    cs:__imp_LoadLibraryExW
0x1800804cc  mov     [rdi+30h], rax
0x1800804d0  test    rax, rax
0x1800804d3  jnz     short loc_1800804F4
0x1800804d5  mov     r8d, ebx; dwFlags
0x1800804d8  lea     rcx, aShlwapiDll; "shlwapi.dll"
0x1800804df  xor     edx, edx; hFile
0x1800804e1  call    cs:__imp_LoadLibraryExW
0x1800804e7  mov     [rdi+30h], rax
0x1800804eb  test    rax, rax
0x1800804ee  jz      loc_1800805FA
0x1800804f4  lea     rdx, aPathcanonicali; "PathCanonicalizeW"
0x1800804fb  mov     rcx, rax; hModule
0x1800804fe  call    cs:__imp_GetProcAddress
0x180080504  mov     rcx, [rdi+30h]; hModule
0x180080508  lea     rdx, aPathremovefile; "PathRemoveFileSpecW"
0x18008050f  mov     [rdi+38h], rax
0x180080513  call    cs:__imp_GetProcAddress
0x180080519  mov     rcx, [rdi+30h]; hModule
0x18008051d  lea     rdx, aPathfindfilena; "PathFindFileNameW"
0x180080524  mov     [rdi+40h], rax
0x180080528  call    cs:__imp_GetProcAddress
0x18008052e  cmp     qword ptr [rdi+38h], 0
0x180080533  mov     [rdi+48h], rax
0x180080537  jz      loc_1800805FA
0x18008053d  cmp     qword ptr [rdi+40h], 0
0x180080542  jz      loc_1800805FA
0x180080548  test    rax, rax
0x18008054b  jz      loc_1800805FA
0x180080551  mov     r8d, 105h
0x180080557  mov     rdx, rsi
0x18008055a  xor     ecx, ecx
0x18008055c  call    GetPhonebookDirectory
0x180080561  test    eax, eax
0x180080563  jnz     short loc_18008056F
0x180080565  mov     ebx, 3EBh
0x18008056a  jmp     loc_180080640
0x18008056f  mov     rcx, [rdi+50h]
0x180080573  mov     rdx, rsi
0x180080576  mov     rax, [rdi+38h]
0x18008057a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008057f  test    eax, eax
0x180080581  jz      short loc_180080565
0x180080583  mov     rbx, [rdi+50h]
0x180080587  mov     rcx, rbx; lpString
0x18008058a  call    cs:__imp_lstrlenW
0x180080590  movsxd  rcx, eax
0x180080593  mov     eax, 5Ch ; '\'
0x180080598  cmp     ax, [rbx+rcx*2-2]
0x18008059d  jnz     short loc_1800805B6
0x18008059f  mov     rbx, [rdi+50h]
0x1800805a3  mov     rcx, rbx; lpString
0x1800805a6  call    cs:__imp_lstrlenW
0x1800805ac  movsxd  rcx, eax
0x1800805af  xor     eax, eax
0x1800805b1  mov     [rbx+rcx*2-2], ax
0x1800805b6  mov     rcx, [rdi+58h]; lpBuffer
0x1800805ba  mov     edx, 0F6h; uSize
0x1800805bf  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800805c5  test    eax, eax
0x1800805c7  jz      short loc_1800805FA
0x1800805c9  mov     rcx, [rdi+58h]; pszDest
0x1800805cd  lea     r8, aSystem32Ras; "\\System32\\Ras"
0x1800805d4  mov     edx, 105h; cchDest
0x1800805d9  mov     [rsp+58h+dwFlags], 100h; dwFlags
0x1800805e1  call    StringCchCatExW
0x1800805e6  test    eax, eax
0x1800805e8  jns     short loc_1800805EF
0x1800805ea  movzx   ebx, ax
0x1800805ed  jmp     short loc_180080602
0x1800805ef  xor     ebx, ebx
0x1800805f1  mov     dword ptr [rdi+2Ch], 1
0x1800805f8  jmp     short loc_18008064D
0x1800805fa  call    cs:__imp_GetLastError
0x180080600  mov     ebx, eax
0x180080602  test    ebx, ebx
0x180080604  jz      short loc_18008064D
0x180080606  jmp     short loc_180080640
0x180080608  call    cs:__imp_GlobalFree
0x18008060e  mov     rcx, [rdi+58h]; hMem
0x180080612  mov     qword ptr [rdi+50h], 0
0x18008061a  test    rcx, rcx
0x18008061d  jz      short loc_180080625
0x18008061f  call    cs:__imp_GlobalFree
0x180080625  mov     qword ptr [rdi+58h], 0
0x18008062d  test    rsi, rsi
0x180080630  jz      short loc_18008063B
0x180080632  mov     rcx, rsi; hMem
0x180080635  call    cs:__imp_GlobalFree
0x18008063b  xor     esi, esi
0x18008063d  lea     ebx, [rsi+8]
0x180080640  mov     rcx, rdi
0x180080643  call    PbkPathInfoReset
0x180080648  test    rsi, rsi
0x18008064b  jz      short loc_180080656
0x18008064d  mov     rcx, rsi; hMem
0x180080650  call    cs:__imp_GlobalFree
0x180080656  mov     rcx, rdi; lpCriticalSection
0x180080659  call    cs:__imp_LeaveCriticalSection
0x18008065f  mov     rcx, cs:WPP_GLOBAL_Control
0x180080666  cmp     rcx, r15
0x180080669  jz      short loc_18008068F
0x18008066b  test    byte ptr [rcx+1Ch], 80h
0x18008066f  jz      short loc_18008068F
0x180080671  cmp     byte ptr [rcx+19h], 6
0x180080675  jb      short loc_18008068F
0x180080677  mov     rcx, [rcx+10h]
0x18008067b  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x180080682  mov     edx, 53h ; 'S'
0x180080687  mov     r9d, ebx
0x18008068a  call    WPP_SF_d
0x18008068f  mov     eax, ebx
0x180080691  add     rsp, 38h
0x180080695  pop     r15
0x180080697  pop     rdi
0x180080698  pop     rsi
0x180080699  pop     rbx
0x18008069a  retn
```
