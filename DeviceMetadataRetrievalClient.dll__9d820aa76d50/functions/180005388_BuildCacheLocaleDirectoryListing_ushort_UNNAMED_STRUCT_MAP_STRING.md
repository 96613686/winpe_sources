# BuildCacheLocaleDirectoryListing(ushort *,UNNAMED_STRUCT_MAP_STRING *)

- ea: `0x180005388`
- end: `0x1800054e8`
- name: `?BuildCacheLocaleDirectoryListing@@YAKPEAGPEAUUNNAMED_STRUCT_MAP_STRING@@@Z`
- size: `352`
- prototype: `unsigned int __fastcall(unsigned __int16 *, struct UNNAMED_STRUCT_MAP_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005198`

## callees

- `0x180002cb0`
- `0x180005388`
- `0x18000ede8`
- `0x1800136c6`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000546c`
- `KERNEL32!GetProcessHeap` at `0x1800054a6`
- `KERNEL32!GetProcessHeap` at `0x18000546c`
- `KERNEL32!GetProcessHeap` at `0x1800054a6`
- `KERNEL32!HeapFree` at `0x18000547a`
- `KERNEL32!HeapFree` at `0x1800054b4`
- `KERNEL32!HeapFree` at `0x18000547a`
- `KERNEL32!HeapFree` at `0x1800054b4`
- `KERNEL32!FindFirstFileW` at `0x1800053fb`
- `KERNEL32!FindFirstFileW` at `0x1800053fb`
- `KERNEL32!FindNextFileW` at `0x180005488`
- `KERNEL32!FindNextFileW` at `0x180005488`
- `KERNEL32!FindClose` at `0x1800054a0`
- `KERNEL32!FindClose` at `0x1800054a0`

## pseudocode

```c
__int64 __fastcall BuildCacheLocaleDirectoryListing(unsigned __int16 *a1, struct UNNAMED_STRUCT_MAP_STRING *a2)
{
  const WCHAR *v4; // rax
  WCHAR *v5; // rbp
  unsigned int v6; // ebx
  HANDLE FirstFileW; // rdi
  const unsigned __int16 *v8; // rax
  void *v9; // r8
  unsigned __int16 *v10; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v12; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-288h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = MemMallocAndCat(a1, L"\\*.*", 0);
  v5 = (WCHAR *)v4;
  if ( !v4 )
    return 8;
  v6 = 0;
  FirstFileW = FindFirstFileW(v4, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    goto LABEL_15;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x12) != 0x10
      || FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_11;
    }
    v8 = MemMallocAndCat(a1, L"\\", FindFileData.cFileName, 0);
    v10 = (unsigned __int16 *)v8;
    if ( !v8 )
      break;
    MapStringInsertV(a2, v8, v9);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
LABEL_11:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_14;
  }
  v6 = 8;
LABEL_14:
  FindClose(FirstFileW);
LABEL_15:
  v12 = GetProcessHeap();
  HeapFree(v12, 0, v5);
  return v6;
}

```

## disassembly

```asm
0x180005388  mov     [rsp+arg_10], rbx
0x18000538d  mov     [rsp+arg_18], rbp
0x180005392  push    rsi
0x180005393  push    rdi
0x180005394  push    r12
0x180005396  push    r14
0x180005398  push    r15
0x18000539a  sub     rsp, 280h
0x1800053a1  mov     rax, cs:__security_cookie
0x1800053a8  xor     rax, rsp
0x1800053ab  mov     [rsp+2A8h+var_38], rax
0x1800053b3  mov     r15, rdx
0x1800053b6  mov     r14, rcx
0x1800053b9  xor     edx, edx; Val
0x1800053bb  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x1800053c0  mov     r8d, 250h; Size
0x1800053c6  call    memset_0
0x1800053cb  xor     r8d, r8d
0x1800053ce  lea     rdx, asc_180017548; "\\*.*"
0x1800053d5  mov     rcx, r14; unsigned __int16 *
0x1800053d8  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x1800053dd  xor     r12d, r12d
0x1800053e0  mov     rbp, rax
0x1800053e3  test    rax, rax
0x1800053e6  jnz     short loc_1800053F0
0x1800053e8  lea     ebx, [rax+8]
0x1800053eb  jmp     loc_1800054BA
0x1800053f0  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x1800053f5  mov     rcx, rbp; lpFileName
0x1800053f8  mov     ebx, r12d
0x1800053fb  call    cs:__imp_FindFirstFileW
0x180005401  mov     rdi, rax
0x180005404  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005408  jz      loc_1800054A6
0x18000540e  mov     ecx, [rsp+2A8h+FindFileData.dwFileAttributes]
0x180005412  and     cl, 12h
0x180005415  cmp     cl, 10h
0x180005418  jnz     short loc_180005480
0x18000541a  cmp     [rsp+2A8h+FindFileData.cFileName], 2Eh ; '.'
0x180005420  movzx   eax, [rsp+2A8h+FindFileData.cFileName+2]
0x180005425  jnz     short loc_180005442
0x180005427  test    ax, ax
0x18000542a  jz      short loc_180005480
0x18000542c  cmp     [rsp+2A8h+FindFileData.cFileName], 2Eh ; '.'
0x180005432  jnz     short loc_180005442
0x180005434  cmp     ax, 2Eh ; '.'
0x180005438  jnz     short loc_180005442
0x18000543a  cmp     [rsp+2A8h+FindFileData.cFileName+4], r12w
0x180005440  jz      short loc_180005480
0x180005442  xor     r9d, r9d
0x180005445  lea     r8, [rsp+2A8h+FindFileData.cFileName]
0x18000544a  lea     rdx, asc_180016E08; "\\"
0x180005451  mov     rcx, r14; unsigned __int16 *
0x180005454  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x180005459  mov     rsi, rax
0x18000545c  test    rax, rax
0x18000545f  jz      short loc_180005498
0x180005461  mov     rdx, rax; unsigned __int16 *
0x180005464  mov     rcx, r15; struct UNNAMED_STRUCT_MAP_STRING *
0x180005467  call    ?MapStringInsertV@@YAHPEAUUNNAMED_STRUCT_MAP_STRING@@PEBGPEAX@Z; MapStringInsertV(UNNAMED_STRUCT_MAP_STRING *,ushort const *,void *)
0x18000546c  call    cs:__imp_GetProcessHeap
0x180005472  mov     r8, rsi; lpMem
0x180005475  xor     edx, edx; dwFlags
0x180005477  mov     rcx, rax; hHeap
0x18000547a  call    cs:__imp_HeapFree
0x180005480  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x180005485  mov     rcx, rdi; hFindFile
0x180005488  call    cs:__imp_FindNextFileW
0x18000548e  test    eax, eax
0x180005490  jnz     loc_18000540E
0x180005496  jmp     short loc_18000549D
0x180005498  mov     ebx, 8
0x18000549d  mov     rcx, rdi; hFindFile
0x1800054a0  call    cs:__imp_FindClose
0x1800054a6  call    cs:__imp_GetProcessHeap
0x1800054ac  mov     r8, rbp; lpMem
0x1800054af  xor     edx, edx; dwFlags
0x1800054b1  mov     rcx, rax; hHeap
0x1800054b4  call    cs:__imp_HeapFree
0x1800054ba  mov     eax, ebx
0x1800054bc  mov     rcx, [rsp+2A8h+var_38]
0x1800054c4  xor     rcx, rsp; StackCookie
0x1800054c7  call    __security_check_cookie
0x1800054cc  lea     r11, [rsp+2A8h+var_28]
0x1800054d4  mov     rbx, [r11+40h]
0x1800054d8  mov     rbp, [r11+48h]
0x1800054dc  mov     rsp, r11
0x1800054df  pop     r15
0x1800054e1  pop     r14
0x1800054e3  pop     r12
0x1800054e5  pop     rdi
0x1800054e6  pop     rsi
0x1800054e7  retn
```
