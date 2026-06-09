# SdbGrabMatchingInfoEx

- ea: `0x18004ecc0`
- end: `0x18004f05a`
- name: `SdbGrabMatchingInfoEx`
- size: `922`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18004ec90`

## callees

- `0x1800055e0`
- `0x180005660`
- `0x18000f114`
- `0x180018f20`
- `0x180039a72`
- `0x18004ecc0`
- `0x18004f060`
- `0x18004f094`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004edd0`
- `ntdll!RtlAllocateHeap` at `0x18004edd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f019`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f019`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ef83`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004efbc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ef83`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004efbc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004efa7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004efa7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004ee20`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004ee20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004ee00`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004ee00`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18004eed1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18004eed1`

## string_xrefs

- `0x18004ed4c`: `szFile does not contain a storage file path`
- `0x18004edde`: `Unable to allocate memory for lpRootDirectory`
- `0x18004ef42`: `GRABMI_FILTER_THISFILEONLY specified but passed in a directory: %ws`
- `0x18004ee33`: `GetFileAttributes failed or %ws is not a valid path`
- `0x18004efcb`: `Unable to open the storage file`

## pseudocode

```c
__int64 __fastcall SdbGrabMatchingInfoEx(LPCWSTR lpFileName, int a2, const WCHAR *a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // r13d
  const char *v10; // r9
  __int64 v11; // r8
  WCHAR *Heap; // rax
  wchar_t *v13; // rbx
  char v14; // r10
  __int64 v15; // rax
  wchar_t *v16; // rax
  __int64 v17; // rax
  _WORD *v18; // r10
  __int64 v19; // r14
  HANDLE FileW; // rsi
  _QWORD v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+5Ch] [rbp-A4h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int16 v27; // [rsp+70h] [rbp-90h] BYREF
  __int128 v28; // [rsp+72h] [rbp-8Eh]
  __int128 v29; // [rsp+82h] [rbp-7Eh]
  wchar_t v30; // [rsp+92h] [rbp-6Eh]
  _BYTE v31[492]; // [rsp+94h] [rbp-6Ch] BYREF

  v27 = 69;
  v30 = aExeNotSpecifie[17];
  v28 = *(_OWORD *)L"xe Not Specified";
  v29 = *(_OWORD *)L"pecified";
  memset_0(v31, 0, 0x1E4u);
  v9 = 0;
  if ( a3 )
  {
    if ( (unsigned __int16)a2 >= 6u )
    {
      v10 = "dwFilter is not a recognized filter";
      v11 = 861;
      goto LABEL_3;
    }
    v23[0] = a5;
    v26 = 1;
    v23[1] = a4;
    v25 = 0;
    v24 = (a2 & 0x40000000) != 0 ? 0x19 : 0;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2000u);
    v13 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "SdbGrabMatchingInfoEx", 875, "Unable to allocate memory for lpRootDirectory");
      return v9;
    }
    if ( (unsigned __int16)a2 == 4 )
    {
      if ( GetSystemDirectoryW(Heap, 0x104u) - 1 > 0x103 )
        goto LABEL_39;
      goto LABEL_23;
    }
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      AslLogCallPrintf(
        1,
        "SdbGrabMatchingInfoEx",
        894,
        "GetFileAttributes failed or %ws is not a valid path",
        lpFileName);
      goto LABEL_39;
    }
    if ( (int)RtlStringCchCopyW(v13, 4096, lpFileName) < 0 )
      goto LABEL_39;
    v15 = -1;
    do
      ++v15;
    while ( v13[v15] );
    if ( (v14 & 0x10) != 0 )
    {
      if ( (int)v15 > 0 && v13[(int)v15 - 1] != 92 )
      {
LABEL_23:
        if ( (int)RtlStringCchCatW(v13, 4096, L"\\") >= 0 )
          goto LABEL_27;
LABEL_39:
        AslFree(NtCurrentPeb()->ProcessHeap, v13);
        return v9;
      }
    }
    else
    {
      v16 = wcsrchr_0(v13, 0x5Cu);
      if ( !v16 )
      {
        if ( (int)RtlStringCchCopyW(&v27, 260, v13) < 0 )
          goto LABEL_39;
        GetCurrentDirectoryW(0x1040u, v13);
        goto LABEL_23;
      }
      v17 = SdbpCharNext(v16);
      if ( (int)RtlStringCchCopyW(&v27, 260, v17) < 0 )
        goto LABEL_39;
      *v18 = 0;
    }
LABEL_27:
    v19 = -1;
    do
      ++v19;
    while ( v13[v19] );
    if ( (unsigned __int16)a2 != 5 || v27 )
    {
      if ( (a2 & 0x20000000) != 0 )
      {
        FileW = CreateFileW(a3, 0x40000000u, 0, 0, 4u, 0x80u, 0);
        if ( GetLastError() == 183 )
        {
          SetFilePointer(FileW, 0, 0, 2u);
          LODWORD(v26) = 0;
        }
      }
      else
      {
        FileW = CreateFileW(a3, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      }
      if ( FileW == (HANDLE)-1LL )
      {
        AslLogCallPrintf(1, "SdbGrabMatchingInfoEx", 982, "Unable to open the storage file");
      }
      else
      {
        v9 = SdbpGrabMatchingInfoDir(
               (_DWORD)FileW,
               (unsigned int)v23,
               a2,
               (_DWORD)v13,
               (__int64)&v27,
               (__int64)&v13[v19],
               0);
        CloseHandle(FileW);
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        "SdbGrabMatchingInfoEx",
        949,
        "GRABMI_FILTER_THISFILEONLY specified but passed in a directory: %ws",
        v13);
    }
    goto LABEL_39;
  }
  v10 = "szFile does not contain a storage file path";
  v11 = 845;
LABEL_3:
  AslLogCallPrintf(1, "SdbGrabMatchingInfoEx", v11, v10);
  return v9;
}

```

## disassembly

```asm
0x18004ecc0  push    rbp
0x18004ecc2  push    rbx
0x18004ecc3  push    rsi
0x18004ecc4  push    rdi
0x18004ecc5  push    r12
0x18004ecc7  push    r13
0x18004ecc9  push    r14
0x18004eccb  push    r15
0x18004eccd  lea     rbp, [rsp-198h]
0x18004ecd5  sub     rsp, 298h
0x18004ecdc  mov     rax, cs:__security_cookie
0x18004ece3  xor     rax, rsp
0x18004ece6  mov     [rbp+1D0h+var_50], rax
0x18004eced  movups  xmm0, xmmword ptr cs:aExeNotSpecifie+2; "xe Not Specified"
0x18004ecf4  mov     rdi, [rbp+1D0h+arg_20]
0x18004ecfb  mov     eax, 45h ; 'E'
0x18004ed00  movups  xmm1, xmmword ptr cs:aExeNotSpecifie+12h; "pecified"
0x18004ed07  mov     [rsp+2D0h+var_260], ax
0x18004ed0c  mov     r14, r8
0x18004ed0f  movzx   eax, word ptr cs:aExeNotSpecifie+22h; ""
0x18004ed16  mov     r12d, edx
0x18004ed19  mov     [rsp+2D0h+lpFileName], r8
0x18004ed1e  mov     rsi, rcx
0x18004ed21  xor     edx, edx; Val
0x18004ed23  mov     [rbp+1D0h+var_23E], ax
0x18004ed27  mov     r8d, 1E4h; Size
0x18004ed2d  lea     rcx, [rbp+1D0h+var_23C]; void *
0x18004ed31  mov     rbx, r9
0x18004ed34  movups  [rsp+2D0h+var_25E], xmm0
0x18004ed39  movups  [rbp+1D0h+var_24E], xmm1
0x18004ed3d  call    memset_0
0x18004ed42  xor     eax, eax
0x18004ed44  mov     r13d, eax
0x18004ed47  test    r14, r14
0x18004ed4a  jnz     short loc_18004ED6F
0x18004ed4c  lea     r9, aSzfileDoesNotC; "szFile does not contain a storage file "...
0x18004ed53  mov     r8d, 34Dh
0x18004ed59  mov     ecx, 1
0x18004ed5e  lea     rdx, aSdbgrabmatchin_1; "SdbGrabMatchingInfoEx"
0x18004ed65  call    AslLogCallPrintf
0x18004ed6a  jmp     loc_18004F034
0x18004ed6f  movzx   r15d, r12w
0x18004ed73  cmp     r15d, 6
0x18004ed77  jb      short loc_18004ED88
0x18004ed79  lea     r9, aDwfilterIsNotA; "dwFilter is not a recognized filter"
0x18004ed80  mov     r8d, 35Dh
0x18004ed86  jmp     short loc_18004ED59
0x18004ed88  mov     [rsp+2D0h+var_288], rdi
0x18004ed8d  xor     r14d, r14d
0x18004ed90  mov     [rsp+2D0h+var_270], 1
0x18004ed99  mov     eax, r12d
0x18004ed9c  and     eax, 40000000h
0x18004eda1  mov     [rsp+2D0h+var_280], rbx
0x18004eda6  neg     eax
0x18004eda8  mov     [rsp+2D0h+var_274], r14d
0x18004edad  lea     edi, [r14+1]
0x18004edb1  mov     r8d, 2000h; Size
0x18004edb7  sbb     eax, eax
0x18004edb9  lea     edx, [rdi+7]; Flags
0x18004edbc  and     eax, 19h
0x18004edbf  mov     [rsp+2D0h+var_278], eax
0x18004edc3  mov     rcx, gs:60h
0x18004edcc  mov     rcx, [rcx+30h]; HeapHandle
0x18004edd0  call    cs:__imp_RtlAllocateHeap
0x18004edd6  mov     rbx, rax
0x18004edd9  test    rax, rax
0x18004eddc  jnz     short loc_18004EDF2
0x18004edde  lea     r9, aUnableToAlloca; "Unable to allocate memory for lpRootDir"...
0x18004ede5  mov     r8d, 36Bh
0x18004edeb  mov     ecx, edi
0x18004eded  jmp     loc_18004ED5E
0x18004edf2  cmp     r15d, 4
0x18004edf6  jnz     short loc_18004EE1D
0x18004edf8  mov     edx, 104h; uSize
0x18004edfd  mov     rcx, rbx; lpBuffer
0x18004ee00  call    cs:__imp_GetSystemDirectoryW
0x18004ee06  dec     eax
0x18004ee08  cmp     eax, 103h
0x18004ee0d  ja      loc_18004F01F
0x18004ee13  mov     edx, 1000h
0x18004ee18  jmp     loc_18004EEDA
0x18004ee1d  mov     rcx, rsi; lpFileName
0x18004ee20  call    cs:__imp_GetFileAttributesW
0x18004ee26  mov     r10d, eax
0x18004ee29  cmp     eax, 0FFFFFFFFh
0x18004ee2c  jnz     short loc_18004EE53
0x18004ee2e  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rsi
0x18004ee33  lea     r9, aGetfileattribu; "GetFileAttributes failed or %ws is not "...
0x18004ee3a  mov     r8d, 37Eh
0x18004ee40  lea     rdx, aSdbgrabmatchin_1; "SdbGrabMatchingInfoEx"
0x18004ee47  mov     ecx, edi
0x18004ee49  call    AslLogCallPrintf
0x18004ee4e  jmp     loc_18004F01F
0x18004ee53  mov     r8, rsi
0x18004ee56  mov     rcx, rbx
0x18004ee59  mov     esi, 1000h
0x18004ee5e  mov     edx, esi
0x18004ee60  call    RtlStringCchCopyW
0x18004ee65  test    eax, eax
0x18004ee67  js      loc_18004F01F
0x18004ee6d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ee71  inc     rax
0x18004ee74  cmp     [rbx+rax*2], r14w
0x18004ee79  jnz     short loc_18004EE71
0x18004ee7b  test    r10b, 10h
0x18004ee7f  jz      short loc_18004EE9D
0x18004ee81  test    eax, eax
0x18004ee83  jle     loc_18004EF1C
0x18004ee89  cdqe
0x18004ee8b  mov     edx, 5Ch ; '\'
0x18004ee90  cmp     [rbx+rax*2-2], dx
0x18004ee95  jz      loc_18004EF1C
0x18004ee9b  jmp     short loc_18004EED7
0x18004ee9d  mov     edx, 5Ch ; '\'; Ch
0x18004eea2  mov     rcx, rbx; Str
0x18004eea5  call    wcsrchr_0
0x18004eeaa  test    rax, rax
0x18004eead  jnz     short loc_18004EEF3
0x18004eeaf  mov     r8, rbx
0x18004eeb2  lea     rcx, [rsp+2D0h+var_260]
0x18004eeb7  mov     edx, 104h
0x18004eebc  call    RtlStringCchCopyW
0x18004eec1  test    eax, eax
0x18004eec3  js      loc_18004F01F
0x18004eec9  mov     rdx, rbx; lpBuffer
0x18004eecc  mov     ecx, 1040h; nBufferLength
0x18004eed1  call    cs:__imp_GetCurrentDirectoryW
0x18004eed7  mov     rdx, rsi
0x18004eeda  lea     r8, pszSrc; "\\"
0x18004eee1  mov     rcx, rbx
0x18004eee4  call    RtlStringCchCatW
0x18004eee9  test    eax, eax
0x18004eeeb  js      loc_18004F01F
0x18004eef1  jmp     short loc_18004EF1C
0x18004eef3  mov     rcx, rax
0x18004eef6  call    SdbpCharNext
0x18004eefb  mov     r8, rax
0x18004eefe  lea     rcx, [rsp+2D0h+var_260]
0x18004ef03  mov     edx, 104h
0x18004ef08  mov     r10, rax
0x18004ef0b  call    RtlStringCchCopyW
0x18004ef10  test    eax, eax
0x18004ef12  js      loc_18004F01F
0x18004ef18  mov     [r10], r14w
0x18004ef1c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004ef20  xor     eax, eax
0x18004ef22  inc     r14
0x18004ef25  cmp     [rbx+r14*2], ax
0x18004ef2a  jnz     short loc_18004EF22
0x18004ef2c  cmp     r15d, 5
0x18004ef30  jnz     short loc_18004EF54
0x18004ef32  xor     r15d, r15d
0x18004ef35  cmp     [rsp+2D0h+var_260], r15w
0x18004ef3b  jnz     short loc_18004EF57
0x18004ef3d  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rbx
0x18004ef42  lea     r9, aGrabmiFilterTh; "GRABMI_FILTER_THISFILEONLY specified bu"...
0x18004ef49  mov     r8d, 3B5h
0x18004ef4f  jmp     loc_18004EE40
0x18004ef54  xor     r15d, r15d
0x18004ef57  mov     rcx, [rsp+2D0h+lpFileName]; lpFileName
0x18004ef5c  xor     r9d, r9d; lpSecurityAttributes
0x18004ef5f  xor     r8d, r8d; dwShareMode
0x18004ef62  mov     [rsp+2D0h+hTemplateFile], r15; hTemplateFile
0x18004ef67  mov     [rsp+2D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004ef6f  mov     edx, 40000000h; dwDesiredAccess
0x18004ef74  bt      r12d, 1Dh
0x18004ef79  jnb     short loc_18004EFB4
0x18004ef7b  mov     [rsp+2D0h+dwCreationDisposition], 4; dwCreationDisposition
0x18004ef83  call    cs:__imp_CreateFileW
0x18004ef89  mov     rsi, rax
0x18004ef8c  call    cs:__imp_GetLastError
0x18004ef92  cmp     eax, 0B7h
0x18004ef97  jnz     short loc_18004EFC5
0x18004ef99  mov     r9d, 2; dwMoveMethod
0x18004ef9f  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004efa2  xor     edx, edx; lDistanceToMove
0x18004efa4  mov     rcx, rsi; hFile
0x18004efa7  call    cs:__imp_SetFilePointer
0x18004efad  mov     dword ptr [rsp+2D0h+var_270], r15d
0x18004efb2  jmp     short loc_18004EFC5
0x18004efb4  mov     [rsp+2D0h+dwCreationDisposition], 2; dwCreationDisposition
0x18004efbc  call    cs:__imp_CreateFileW
0x18004efc2  mov     rsi, rax
0x18004efc5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004efc9  jnz     short loc_18004EFE8
0x18004efcb  lea     r9, aUnableToOpenTh; "Unable to open the storage file"
0x18004efd2  mov     r8d, 3D6h
0x18004efd8  lea     rdx, aSdbgrabmatchin_1; "SdbGrabMatchingInfoEx"
0x18004efdf  mov     ecx, edi
0x18004efe1  call    AslLogCallPrintf
0x18004efe6  jmp     short loc_18004F01F
0x18004efe8  lea     rax, [rbx+r14*2]
0x18004efec  mov     dword ptr [rsp+2D0h+hTemplateFile], r15d
0x18004eff1  mov     qword ptr [rsp+2D0h+dwFlagsAndAttributes], rax
0x18004eff6  lea     rdx, [rsp+2D0h+var_288]
0x18004effb  lea     rax, [rsp+2D0h+var_260]
0x18004f000  mov     r9, rbx
0x18004f003  mov     r8d, r12d
0x18004f006  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rax
0x18004f00b  mov     rcx, rsi
0x18004f00e  call    SdbpGrabMatchingInfoDir
0x18004f013  mov     r13d, eax
0x18004f016  mov     rcx, rsi; hObject
0x18004f019  call    cs:__imp_CloseHandle
0x18004f01f  mov     rcx, gs:60h
0x18004f028  mov     rdx, rbx
0x18004f02b  mov     rcx, [rcx+30h]
0x18004f02f  call    AslFree
0x18004f034  mov     eax, r13d
0x18004f037  mov     rcx, [rbp+1D0h+var_50]
0x18004f03e  xor     rcx, rsp; StackCookie
0x18004f041  call    __security_check_cookie
0x18004f046  add     rsp, 298h
0x18004f04d  pop     r15
0x18004f04f  pop     r14
0x18004f051  pop     r13
0x18004f053  pop     r12
0x18004f055  pop     rdi
0x18004f056  pop     rsi
0x18004f057  pop     rbx
0x18004f058  pop     rbp
0x18004f059  retn
```
