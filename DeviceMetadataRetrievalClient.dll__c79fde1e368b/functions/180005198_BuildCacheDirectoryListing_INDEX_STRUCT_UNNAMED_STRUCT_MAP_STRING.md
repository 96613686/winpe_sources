# BuildCacheDirectoryListing(_INDEX_STRUCT *,UNNAMED_STRUCT_MAP_STRING *)

- ea: `0x180005198`
- end: `0x180005380`
- name: `?BuildCacheDirectoryListing@@YAKPEAU_INDEX_STRUCT@@PEAUUNNAMED_STRUCT_MAP_STRING@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(const unsigned __int16 **, struct UNNAMED_STRUCT_MAP_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000768c`

## callees

- `0x180004e2c`
- `0x180005198`
- `0x180005388`
- `0x18000ede8`
- `0x1800136c6`
- `0x180013700`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005261`
- `msvcrt!_wcsicmp` at `0x180005261`
- `KERNEL32!GetProcessHeap` at `0x1800052ab`
- `KERNEL32!GetProcessHeap` at `0x18000532a`
- `KERNEL32!GetProcessHeap` at `0x18000533e`
- `KERNEL32!GetProcessHeap` at `0x1800052ab`
- `KERNEL32!GetProcessHeap` at `0x18000532a`
- `KERNEL32!GetProcessHeap` at `0x18000533e`
- `KERNEL32!HeapFree` at `0x1800052b9`
- `KERNEL32!HeapFree` at `0x180005338`
- `KERNEL32!HeapFree` at `0x18000534c`
- `KERNEL32!HeapFree` at `0x1800052b9`
- `KERNEL32!HeapFree` at `0x180005338`
- `KERNEL32!HeapFree` at `0x18000534c`
- `KERNEL32!FindFirstFileW` at `0x180005208`
- `KERNEL32!FindFirstFileW` at `0x180005208`
- `KERNEL32!FindNextFileW` at `0x1800052ca`
- `KERNEL32!FindNextFileW` at `0x1800052ca`
- `KERNEL32!FindClose` at `0x18000531f`
- `KERNEL32!FindClose` at `0x18000531f`
- `KERNEL32!IsValidLocaleName` at `0x180005270`
- `KERNEL32!IsValidLocaleName` at `0x180005270`

## pseudocode

```c
__int64 __fastcall BuildCacheDirectoryListing(const unsigned __int16 **a1, struct UNNAMED_STRUCT_MAP_STRING *a2)
{
  unsigned int v4; // ebx
  const WCHAR *v5; // rax
  WCHAR *v6; // rbp
  HANDLE FirstFileW; // rsi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v11; // rax
  HANDLE v12; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-288h] BYREF

  v4 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = MemMallocAndCat(a1[2], L"\\*.*", 0);
  v6 = (WCHAR *)v5;
  if ( !v5 )
    return v4;
  FirstFileW = FindFirstFileW(v5, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    goto LABEL_22;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x12) != 0x10
      || FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_13;
    }
    if ( _wcsicmp(FindFileData.cFileName, L"MultiLoc") && !IsValidLocaleName(FindFileData.cFileName) )
      break;
    v8 = MemMallocAndCat(a1[2], L"\\", FindFileData.cFileName, 0);
    v9 = v8;
    if ( !v8 )
    {
      v4 = 8;
      goto LABEL_20;
    }
    v4 = BuildCacheLocaleDirectoryListing(v8, a2);
    if ( v4 )
      goto LABEL_20;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
LABEL_13:
    v9 = 0;
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
      FindFileData.cFileName);
  v4 = 13;
  v9 = 0;
LABEL_20:
  FindClose(FirstFileW);
  if ( v9 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v9);
  }
LABEL_22:
  v12 = GetProcessHeap();
  HeapFree(v12, 0, v6);
  return v4;
}

```

## disassembly

```asm
0x180005198  mov     [rsp+arg_10], rbx
0x18000519d  mov     [rsp+arg_18], rbp
0x1800051a2  push    rsi
0x1800051a3  push    rdi
0x1800051a4  push    r12
0x1800051a6  push    r14
0x1800051a8  push    r15
0x1800051aa  sub     rsp, 280h
0x1800051b1  mov     rax, cs:__security_cookie
0x1800051b8  xor     rax, rsp
0x1800051bb  mov     [rsp+2A8h+var_38], rax
0x1800051c3  mov     r15, rdx
0x1800051c6  mov     r14, rcx
0x1800051c9  xor     r12d, r12d
0x1800051cc  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x1800051d1  xor     edx, edx; Val
0x1800051d3  mov     r8d, 250h; Size
0x1800051d9  mov     ebx, r12d
0x1800051dc  call    memset_0
0x1800051e1  mov     rcx, [r14+10h]; unsigned __int16 *
0x1800051e5  lea     rdx, asc_180017548; "\\*.*"
0x1800051ec  xor     r8d, r8d
0x1800051ef  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x1800051f4  mov     rbp, rax
0x1800051f7  test    rax, rax
0x1800051fa  jz      loc_180005352
0x180005200  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x180005205  mov     rcx, rax; lpFileName
0x180005208  call    cs:__imp_FindFirstFileW
0x18000520e  mov     rsi, rax
0x180005211  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005215  jz      loc_18000533E
0x18000521b  mov     eax, [rsp+2A8h+FindFileData.dwFileAttributes]
0x18000521f  and     al, 12h
0x180005221  cmp     al, 10h
0x180005223  jnz     loc_1800052BF
0x180005229  cmp     [rsp+2A8h+FindFileData.cFileName], 2Eh ; '.'
0x18000522f  movzx   eax, [rsp+2A8h+FindFileData.cFileName+2]
0x180005234  jnz     short loc_180005255
0x180005236  test    ax, ax
0x180005239  jz      loc_1800052BF
0x18000523f  cmp     [rsp+2A8h+FindFileData.cFileName], 2Eh ; '.'
0x180005245  jnz     short loc_180005255
0x180005247  cmp     ax, 2Eh ; '.'
0x18000524b  jnz     short loc_180005255
0x18000524d  cmp     [rsp+2A8h+FindFileData.cFileName+4], r12w
0x180005253  jz      short loc_1800052BF
0x180005255  lea     rdx, aMultiloc; "MultiLoc"
0x18000525c  lea     rcx, [rsp+2A8h+FindFileData.cFileName]; String1
0x180005261  call    cs:__imp__wcsicmp
0x180005267  test    eax, eax
0x180005269  jz      short loc_18000527A
0x18000526b  lea     rcx, [rsp+2A8h+FindFileData.cFileName]; lpLocaleName
0x180005270  call    cs:__imp_IsValidLocaleName
0x180005276  test    eax, eax
0x180005278  jz      short loc_1800052DA
0x18000527a  mov     rcx, [r14+10h]; unsigned __int16 *
0x18000527e  lea     r8, [rsp+2A8h+FindFileData.cFileName]
0x180005283  xor     r9d, r9d
0x180005286  lea     rdx, asc_180016E08; "\\"
0x18000528d  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x180005292  mov     rdi, rax
0x180005295  test    rax, rax
0x180005298  jz      short loc_180005317
0x18000529a  mov     rdx, r15; struct UNNAMED_STRUCT_MAP_STRING *
0x18000529d  mov     rcx, rax; unsigned __int16 *
0x1800052a0  call    ?BuildCacheLocaleDirectoryListing@@YAKPEAGPEAUUNNAMED_STRUCT_MAP_STRING@@@Z; BuildCacheLocaleDirectoryListing(ushort *,UNNAMED_STRUCT_MAP_STRING *)
0x1800052a5  mov     ebx, eax
0x1800052a7  test    eax, eax
0x1800052a9  jnz     short loc_18000531C
0x1800052ab  call    cs:__imp_GetProcessHeap
0x1800052b1  mov     r8, rdi; lpMem
0x1800052b4  xor     edx, edx; dwFlags
0x1800052b6  mov     rcx, rax; hHeap
0x1800052b9  call    cs:__imp_HeapFree
0x1800052bf  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x1800052c4  mov     rcx, rsi; hFindFile
0x1800052c7  mov     rdi, r12
0x1800052ca  call    cs:__imp_FindNextFileW
0x1800052d0  test    eax, eax
0x1800052d2  jnz     loc_18000521B
0x1800052d8  jmp     short loc_18000531C
0x1800052da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052e1  lea     rax, WPP_GLOBAL_Control
0x1800052e8  cmp     rcx, rax
0x1800052eb  jz      short loc_18000530D
0x1800052ed  test    byte ptr [rcx+1Ch], 1
0x1800052f1  jz      short loc_18000530D
0x1800052f3  mov     rcx, [rcx+10h]
0x1800052f7  lea     r9, [rsp+2A8h+FindFileData.cFileName]
0x1800052fc  mov     edx, 1Ah
0x180005301  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180005308  call    WPP_SF_S
0x18000530d  mov     ebx, 0Dh
0x180005312  mov     rdi, r12
0x180005315  jmp     short loc_18000531C
0x180005317  mov     ebx, 8
0x18000531c  mov     rcx, rsi; hFindFile
0x18000531f  call    cs:__imp_FindClose
0x180005325  test    rdi, rdi
0x180005328  jz      short loc_18000533E
0x18000532a  call    cs:__imp_GetProcessHeap
0x180005330  mov     r8, rdi; lpMem
0x180005333  xor     edx, edx; dwFlags
0x180005335  mov     rcx, rax; hHeap
0x180005338  call    cs:__imp_HeapFree
0x18000533e  call    cs:__imp_GetProcessHeap
0x180005344  mov     r8, rbp; lpMem
0x180005347  xor     edx, edx; dwFlags
0x180005349  mov     rcx, rax; hHeap
0x18000534c  call    cs:__imp_HeapFree
0x180005352  mov     eax, ebx
0x180005354  mov     rcx, [rsp+2A8h+var_38]
0x18000535c  xor     rcx, rsp; StackCookie
0x18000535f  call    __security_check_cookie
0x180005364  lea     r11, [rsp+2A8h+var_28]
0x18000536c  mov     rbx, [r11+40h]
0x180005370  mov     rbp, [r11+48h]
0x180005374  mov     rsp, r11
0x180005377  pop     r15
0x180005379  pop     r14
0x18000537b  pop     r12
0x18000537d  pop     rdi
0x18000537e  pop     rsi
0x18000537f  retn
```
