# DeleteDirectory_0

- ea: `0x180225074`
- end: `0x1802252c8`
- name: `DeleteDirectory_0`
- size: `596`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180225074`
- `0x1802266e4`

## callees

- `0x1800059d0`
- `0x180006934`
- `0x180006a18`
- `0x180222764`
- `0x180224598`
- `0x180225074`
- `0x180226bf0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1802251a5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1802251a5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1802251dd`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1802251dd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1802250e9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1802250e9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1802251c3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1802251c3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1802251f4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1802251f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225142`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225270`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225142`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180225270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225156`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225284`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225156`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180225284`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180225292`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180225292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022520a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022521a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022520a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022521a`

## string_xrefs

- `0x180225229`: `DeleteDirectory: Unable to delete file/directory [%s] GLE = 0x%x, `
- `0x180225253`: `DeleteDirectory: Unable to delete directory [%s] GLE = 0x%x, `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeleteDirectory_0(__int64 a1)
{
  int v2; // eax
  WCHAR *v3; // rbx
  char *FirstFileW; // rsi
  HANDLE ProcessHeap; // rax
  char dwFileAttributes; // al
  unsigned int v7; // eax
  unsigned int v8; // edi
  DWORD v9; // esi
  HANDLE v10; // rax
  __int64 v12; // [rsp+20h] [rbp-E0h]
  DWORD LastError; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  lpFileName[0] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v2 = StrAllocatingPrintf(lpFileName, L"%s\\*", a1);
  v3 = (WCHAR *)lpFileName[0];
  if ( v2 < 0 )
  {
LABEL_22:
    v8 = 0;
    v9 = (unsigned __int16)v2;
  }
  else
  {
    FirstFileW = (char *)FindFirstFileW(lpFileName[0], &FindFileData);
    if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
LABEL_19:
      v8 = WdsRemoveDirectory(a1);
    }
    else
    {
      while ( 1 )
      {
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
        {
          FindClose(FirstFileW);
          goto LABEL_19;
        }
        if ( wcsicmp(FindFileData.cFileName, L".") && wcsicmp(FindFileData.cFileName, L"..") )
        {
          if ( v3 )
          {
            ProcessHeap = GetProcessHeap();
            if ( HeapFree(ProcessHeap, 0, v3) )
              v3 = 0;
            lpFileName[0] = v3;
          }
          v2 = StrAllocatingPrintf(lpFileName, L"%s\\%s", a1, FindFileData.cFileName);
          v3 = (WCHAR *)lpFileName[0];
          if ( v2 < 0 )
            goto LABEL_22;
          dwFileAttributes = FindFileData.dwFileAttributes;
          if ( (FindFileData.dwFileAttributes & 1) != 0 )
          {
            SetFileAttributesW(lpFileName[0], 0x80u);
            dwFileAttributes = FindFileData.dwFileAttributes;
          }
          v7 = (dwFileAttributes & 0x10) != 0 ? DeleteDirectory_0(v3) : DeleteFileW(v3);
          v8 = v7;
          if ( !v7 )
            break;
        }
      }
      LastError = GetLastError();
      LibLog(
        &g_WdsLibLog,
        0x2000000,
        L"DeleteDirectory: Unable to delete file/directory [%s] GLE = 0x%x, ",
        v3,
        LastError);
    }
    v9 = GetLastError();
  }
  LODWORD(v12) = v9;
  LibLog(&g_WdsLibLog, 0x2000000, L"DeleteDirectory: Unable to delete directory [%s] GLE = 0x%x, ", a1, v12);
  if ( v3 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v3);
  }
  SetLastError(v9);
  return v8;
}

```

## disassembly

```asm
0x180225074  mov     [rsp-8+arg_8], rbx
0x180225079  mov     [rsp-8+arg_10], rsi
0x18022507e  push    rbp
0x18022507f  push    rdi
0x180225080  push    r14
0x180225082  lea     rbp, [rsp-1A0h]
0x18022508a  sub     rsp, 2A0h
0x180225091  mov     rax, cs:__security_cookie
0x180225098  xor     rax, rsp
0x18022509b  mov     [rbp+1B0h+var_20], rax
0x1802250a2  mov     r14, rcx
0x1802250a5  mov     [rsp+2B0h+lpFileName], 0
0x1802250ae  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x1802250b3  xor     edx, edx; Val
0x1802250b5  mov     r8d, 250h; Size
0x1802250bb  call    memset_0
0x1802250c0  mov     r8, r14
0x1802250c3  lea     rdx, aS_2; "%s\\*"
0x1802250ca  lea     rcx, [rsp+2B0h+lpFileName]
0x1802250cf  call    StrAllocatingPrintf
0x1802250d4  mov     rbx, [rsp+2B0h+lpFileName]
0x1802250d9  test    eax, eax
0x1802250db  js      loc_180225247
0x1802250e1  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1802250e6  mov     rcx, rbx; lpFileName
0x1802250e9  call    cs:__imp_FindFirstFileW
0x1802250f0  nop     dword ptr [rax+rax+00h]
0x1802250f5  mov     rsi, rax
0x1802250f8  lea     rcx, [rax-1]
0x1802250fc  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180225100  ja      loc_180225200
0x180225106  jmp     loc_1802251D5
0x18022510b  lea     rdx, S; "."
0x180225112  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; String1
0x180225117  call    _wcsicmp
0x18022511c  test    eax, eax
0x18022511e  jz      loc_1802251D5
0x180225124  lea     rdx, asc_1802D0F48; ".."
0x18022512b  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; String1
0x180225130  call    _wcsicmp
0x180225135  test    eax, eax
0x180225137  jz      loc_1802251D5
0x18022513d  test    rbx, rbx
0x180225140  jz      short loc_18022516F
0x180225142  call    cs:__imp_GetProcessHeap
0x180225149  nop     dword ptr [rax+rax+00h]
0x18022514e  mov     r8, rbx; lpMem
0x180225151  xor     edx, edx; dwFlags
0x180225153  mov     rcx, rax; hHeap
0x180225156  call    cs:__imp_HeapFree
0x18022515d  nop     dword ptr [rax+rax+00h]
0x180225162  xor     ecx, ecx
0x180225164  test    eax, eax
0x180225166  cmovnz  rbx, rcx
0x18022516a  mov     [rsp+2B0h+lpFileName], rbx
0x18022516f  lea     r9, [rsp+2B0h+FindFileData.cFileName]
0x180225174  mov     r8, r14
0x180225177  lea     rdx, aSS_1; "%s\\%s"
0x18022517e  lea     rcx, [rsp+2B0h+lpFileName]
0x180225183  call    StrAllocatingPrintf
0x180225188  mov     rbx, [rsp+2B0h+lpFileName]
0x18022518d  test    eax, eax
0x18022518f  js      loc_180225247
0x180225195  mov     eax, [rsp+2B0h+FindFileData.dwFileAttributes]
0x180225199  test    al, 1
0x18022519b  jz      short loc_1802251B5
0x18022519d  mov     edx, 80h; dwFileAttributes
0x1802251a2  mov     rcx, rbx; lpFileName
0x1802251a5  call    cs:__imp_SetFileAttributesW
0x1802251ac  nop     dword ptr [rax+rax+00h]
0x1802251b1  mov     eax, [rsp+2B0h+FindFileData.dwFileAttributes]
0x1802251b5  mov     rcx, rbx; lpFileName
0x1802251b8  test    al, 10h
0x1802251ba  jz      short loc_1802251C3
0x1802251bc  call    DeleteDirectory_0
0x1802251c1  jmp     short loc_1802251CF
0x1802251c3  call    cs:__imp_DeleteFileW
0x1802251ca  nop     dword ptr [rax+rax+00h]
0x1802251cf  mov     edi, eax
0x1802251d1  test    eax, eax
0x1802251d3  jz      short loc_18022521A
0x1802251d5  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1802251da  mov     rcx, rsi; hFindFile
0x1802251dd  call    cs:__imp_FindNextFileW
0x1802251e4  nop     dword ptr [rax+rax+00h]
0x1802251e9  test    eax, eax
0x1802251eb  jnz     loc_18022510B
0x1802251f1  mov     rcx, rsi; hFindFile
0x1802251f4  call    cs:__imp_FindClose
0x1802251fb  nop     dword ptr [rax+rax+00h]
0x180225200  mov     rcx, r14
0x180225203  call    WdsRemoveDirectory
0x180225208  mov     edi, eax
0x18022520a  call    cs:__imp_GetLastError
0x180225211  nop     dword ptr [rax+rax+00h]
0x180225216  mov     esi, eax
0x180225218  jmp     short loc_18022524C
0x18022521a  call    cs:__imp_GetLastError
0x180225221  nop     dword ptr [rax+rax+00h]
0x180225226  mov     r9, rbx
0x180225229  lea     r8, aDeletedirector; "DeleteDirectory: Unable to delete file/"...
0x180225230  lea     rcx, g_WdsLibLog
0x180225237  mov     [rsp+2B0h+var_290], eax
0x18022523b  mov     edx, 2000000h
0x180225240  call    LibLog
0x180225245  jmp     short loc_18022520A
0x180225247  xor     edi, edi
0x180225249  movzx   esi, ax
0x18022524c  mov     r9, r14
0x18022524f  mov     [rsp+2B0h+var_290], esi
0x180225253  lea     r8, aDeletedirector_0; "DeleteDirectory: Unable to delete direc"...
0x18022525a  mov     edx, 2000000h
0x18022525f  lea     rcx, g_WdsLibLog
0x180225266  call    LibLog
0x18022526b  test    rbx, rbx
0x18022526e  jz      short loc_180225290
0x180225270  call    cs:__imp_GetProcessHeap
0x180225277  nop     dword ptr [rax+rax+00h]
0x18022527c  mov     r8, rbx; lpMem
0x18022527f  xor     edx, edx; dwFlags
0x180225281  mov     rcx, rax; hHeap
0x180225284  call    cs:__imp_HeapFree
0x18022528b  nop     dword ptr [rax+rax+00h]
0x180225290  mov     ecx, esi; dwErrCode
0x180225292  call    cs:__imp_SetLastError
0x180225299  nop     dword ptr [rax+rax+00h]
0x18022529e  mov     eax, edi
0x1802252a0  mov     rcx, [rbp+1B0h+var_20]
0x1802252a7  xor     rcx, rsp; StackCookie
0x1802252aa  call    __security_check_cookie
0x1802252af  lea     r11, [rsp+2B0h+var_10]
0x1802252b7  mov     rbx, [r11+28h]
0x1802252bb  mov     rsi, [r11+30h]
0x1802252bf  mov     rsp, r11
0x1802252c2  pop     r14
0x1802252c4  pop     rdi
0x1802252c5  pop     rbp
0x1802252c6  retn
```
