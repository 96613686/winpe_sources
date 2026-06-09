# FSRemoveDirPath

- ea: `0x180003514`
- end: `0x1800038c2`
- name: `FSRemoveDirPath`
- size: `942`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800033c0`
- `0x180003514`
- `0x180004b04`
- `0x180006904`
- `0x180007380`
- `0x18000b244`
- `0x18000dabc`

## callees

- `0x180002dc8`
- `0x180003514`
- `0x1800039d0`
- `0x18000eed0`
- `0x1800136c6`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800035e1`
- `KERNEL32!GetProcessHeap` at `0x1800036c3`
- `KERNEL32!GetProcessHeap` at `0x180003884`
- `KERNEL32!GetProcessHeap` at `0x1800035e1`
- `KERNEL32!GetProcessHeap` at `0x1800036c3`
- `KERNEL32!GetProcessHeap` at `0x180003884`
- `KERNEL32!HeapFree` at `0x1800035ef`
- `KERNEL32!HeapFree` at `0x1800036d1`
- `KERNEL32!HeapFree` at `0x180003892`
- `KERNEL32!HeapFree` at `0x1800035ef`
- `KERNEL32!HeapFree` at `0x1800036d1`
- `KERNEL32!HeapFree` at `0x180003892`
- `KERNEL32!GetFileAttributesW` at `0x180003559`
- `KERNEL32!GetFileAttributesW` at `0x18000385c`
- `KERNEL32!GetFileAttributesW` at `0x180003559`
- `KERNEL32!GetFileAttributesW` at `0x18000385c`
- `KERNEL32!FindFirstFileW` at `0x1800036f0`
- `KERNEL32!FindFirstFileW` at `0x1800036f0`
- `KERNEL32!lstrcmpW` at `0x180003788`
- `KERNEL32!lstrcmpW` at `0x1800037a2`
- `KERNEL32!lstrcmpW` at `0x180003788`
- `KERNEL32!lstrcmpW` at `0x1800037a2`
- `KERNEL32!SetFileAttributesW` at `0x1800037ce`
- `KERNEL32!SetFileAttributesW` at `0x1800037ce`
- `KERNEL32!DeleteFileW` at `0x1800037db`
- `KERNEL32!DeleteFileW` at `0x1800037db`
- `KERNEL32!GetTempFileNameW` at `0x1800035b1`
- `KERNEL32!GetTempFileNameW` at `0x1800037f9`
- `KERNEL32!GetTempFileNameW` at `0x1800035b1`
- `KERNEL32!GetTempFileNameW` at `0x1800037f9`
- `KERNEL32!MoveFileExW` at `0x1800035c8`
- `KERNEL32!MoveFileExW` at `0x180003659`
- `KERNEL32!MoveFileExW` at `0x180003814`
- `KERNEL32!MoveFileExW` at `0x180003831`
- `KERNEL32!MoveFileExW` at `0x18000387b`
- `KERNEL32!MoveFileExW` at `0x1800035c8`
- `KERNEL32!MoveFileExW` at `0x180003659`
- `KERNEL32!MoveFileExW` at `0x180003814`
- `KERNEL32!MoveFileExW` at `0x180003831`
- `KERNEL32!MoveFileExW` at `0x18000387b`
- `KERNEL32!FindNextFileW` at `0x180003842`
- `KERNEL32!FindNextFileW` at `0x180003842`
- `KERNEL32!FindClose` at `0x180003853`
- `KERNEL32!FindClose` at `0x180003853`
- `KERNEL32!CreateFileW` at `0x180003639`
- `KERNEL32!CreateFileW` at `0x180003639`
- `KERNEL32!CloseHandle` at `0x180003648`
- `KERNEL32!CloseHandle` at `0x180003648`
- `KERNEL32!RemoveDirectoryW` at `0x180003869`
- `KERNEL32!RemoveDirectoryW` at `0x180003869`

## pseudocode

```c
__int64 __fastcall FSRemoveDirPath(const WCHAR *a1)
{
  DWORD FileAttributesW; // eax
  __int16 v3; // r14
  WCHAR *v4; // r15
  __int64 v5; // rax
  unsigned int v6; // edi
  WCHAR *v7; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE FileW; // rax
  __int64 v10; // rcx
  WCHAR *v11; // rax
  WCHAR *v12; // r8
  __int64 v13; // rdx
  WCHAR *v14; // rcx
  HANDLE v15; // rax
  unsigned int v17; // r14d
  BOOL NextFileW; // r15d
  HANDLE FirstFileW; // r12
  __int64 v20; // rcx
  WCHAR *v21; // r8
  WCHAR *v22; // r9
  __int64 v23; // rdx
  WCHAR *v24; // rcx
  BOOL v25; // eax
  WCHAR *v26; // rcx
  HANDLE v27; // rax
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR TempFileName[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR v31[264]; // [rsp+6B0h] [rbp+5B0h] BYREF
  WCHAR NewFileName[264]; // [rsp+8C0h] [rbp+7C0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileAttributesW = GetFileAttributesW(a1);
  v3 = FileAttributesW;
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    return 0;
  v4 = MemMallocAndCopy(a1);
  v5 = FSSplitFileName(v4);
  v6 = 1;
  if ( v4 )
  {
    v7 = 0;
    if ( v5 && GetTempFileNameW(v4, L"DEL", 0, TempFileName) && MoveFileExW(a1, TempFileName, 1u) )
      v7 = MemMallocAndCopy(TempFileName);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    if ( v7 )
      goto LABEL_10;
  }
  v7 = MemMallocAndCopy(a1);
  if ( !v7 )
    return 0;
LABEL_10:
  if ( (v3 & 0x400) != 0 )
  {
    FileW = CreateFileW(v7, 0x10000u, 7u, 0, 3u, 0x6200000u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      CloseHandle(FileW);
LABEL_23:
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v7);
      return v6;
    }
    MoveFileExW(v7, 0, 4u);
LABEL_22:
    v6 = 0;
    goto LABEL_23;
  }
  v10 = 2147483646;
  v11 = v31;
  v12 = v7;
  v13 = 260;
  do
  {
    if ( !v10 )
      break;
    if ( !*v12 )
      break;
    *v11++ = *v12++;
    --v10;
    --v13;
  }
  while ( v13 );
  v14 = v11 - 1;
  if ( v13 )
    v14 = v11;
  *v14 = 0;
  if ( !v13 || !(unsigned int)ConcatenatePaths(v31, L"*.*", v12) )
    goto LABEL_22;
  v17 = 1;
  NextFileW = 1;
  FirstFileW = FindFirstFileW(v31, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    while ( NextFileW )
    {
      v20 = 2147483646;
      v21 = FileName;
      v22 = v7;
      v23 = 260;
      do
      {
        if ( !v20 )
          break;
        if ( !*v22 )
          break;
        *v21++ = *v22++;
        --v20;
        --v23;
      }
      while ( v23 );
      v24 = v21 - 1;
      if ( v23 )
        v24 = v21;
      *v24 = 0;
      if ( v23 && (unsigned int)ConcatenatePaths(FileName, FindFileData.cFileName, v21) )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          SetFileAttributesW(FileName, 0x80u);
          if ( DeleteFileW(FileName) )
            goto LABEL_45;
          if ( !GetTempFileNameW(v7, L"DEL", 0, NewFileName)
            || (v25 = MoveFileExW(FileName, NewFileName, 1u), v26 = NewFileName, !v25) )
          {
            v26 = FileName;
          }
          MoveFileExW(v26, 0, 4u);
LABEL_44:
          v17 = 0;
          goto LABEL_45;
        }
        if ( lstrcmpW(FindFileData.cFileName, L".")
          && lstrcmpW(FindFileData.cFileName, L"..")
          && !(unsigned int)FSRemoveDirPath(FileName) )
        {
          goto LABEL_44;
        }
      }
LABEL_45:
      NextFileW = FindNextFileW(FirstFileW, &FindFileData);
    }
  }
  FindClose(FirstFileW);
  if ( (GetFileAttributesW(v7) & 0x10) != 0 && !RemoveDirectoryW(v7) )
  {
    MoveFileExW(v7, 0, 4u);
    v17 = 0;
  }
  v27 = GetProcessHeap();
  HeapFree(v27, 0, v7);
  return v17;
}

```

## disassembly

```asm
0x180003514  push    rbp
0x180003516  push    rbx
0x180003517  push    rsi
0x180003518  push    rdi
0x180003519  push    r12
0x18000351b  push    r13
0x18000351d  push    r14
0x18000351f  push    r15
0x180003521  lea     rbp, [rsp-9E8h]
0x180003529  sub     rsp, 0AE8h
0x180003530  mov     rax, cs:__security_cookie
0x180003537  xor     rax, rsp
0x18000353a  mov     [rbp+0A20h+var_50], rax
0x180003541  mov     rsi, rcx
0x180003544  xor     edx, edx; Val
0x180003546  lea     rcx, [rsp+0B20h+FindFileData]; void *
0x18000354b  mov     r8d, 250h; Size
0x180003551  call    memset_0
0x180003556  mov     rcx, rsi; lpFileName
0x180003559  call    cs:__imp_GetFileAttributesW
0x18000355f  mov     r14d, eax
0x180003562  cmp     eax, 0FFFFFFFFh
0x180003565  jz      loc_18000389D
0x18000356b  test    r14b, 10h
0x18000356f  jz      loc_18000389D
0x180003575  mov     rcx, rsi; unsigned __int16 *
0x180003578  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000357d  mov     rcx, rax
0x180003580  mov     r15, rax
0x180003583  call    FSSplitFileName
0x180003588  xor     r13d, r13d
0x18000358b  mov     edi, 1
0x180003590  test    r15, r15
0x180003593  jz      short loc_1800035FA
0x180003595  mov     ebx, r13d
0x180003598  test    rax, rax
0x18000359b  jz      short loc_1800035E1
0x18000359d  lea     r9, [rbp+0A20h+TempFileName]; lpTempFileName
0x1800035a4  xor     r8d, r8d; uUnique
0x1800035a7  lea     rdx, PrefixString; "DEL"
0x1800035ae  mov     rcx, r15; lpPathName
0x1800035b1  call    cs:__imp_GetTempFileNameW
0x1800035b7  test    eax, eax
0x1800035b9  jz      short loc_1800035E1
0x1800035bb  mov     r8d, edi; dwFlags
0x1800035be  lea     rdx, [rbp+0A20h+TempFileName]; lpNewFileName
0x1800035c5  mov     rcx, rsi; lpExistingFileName
0x1800035c8  call    cs:__imp_MoveFileExW
0x1800035ce  test    eax, eax
0x1800035d0  jz      short loc_1800035E1
0x1800035d2  lea     rcx, [rbp+0A20h+TempFileName]; unsigned __int16 *
0x1800035d9  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x1800035de  mov     rbx, rax
0x1800035e1  call    cs:__imp_GetProcessHeap
0x1800035e7  mov     r8, r15; lpMem
0x1800035ea  xor     edx, edx; dwFlags
0x1800035ec  mov     rcx, rax; hHeap
0x1800035ef  call    cs:__imp_HeapFree
0x1800035f5  test    rbx, rbx
0x1800035f8  jnz     short loc_18000360E
0x1800035fa  mov     rcx, rsi; unsigned __int16 *
0x1800035fd  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x180003602  mov     rbx, rax
0x180003605  test    rax, rax
0x180003608  jz      loc_18000389D
0x18000360e  bt      r14d, 0Ah
0x180003613  jnb     short loc_180003661
0x180003615  xor     r9d, r9d; lpSecurityAttributes
0x180003618  mov     [rsp+0B20h+hTemplateFile], r13; hTemplateFile
0x18000361d  mov     [rsp+0B20h+dwFlagsAndAttributes], 6200000h; dwFlagsAndAttributes
0x180003625  mov     edx, 10000h; dwDesiredAccess
0x18000362a  mov     rcx, rbx; lpFileName
0x18000362d  mov     [rsp+0B20h+dwCreationDisposition], 3; dwCreationDisposition
0x180003635  lea     r8d, [r9+7]; dwShareMode
0x180003639  call    cs:__imp_CreateFileW
0x18000363f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003643  jz      short loc_180003650
0x180003645  mov     rcx, rax; hObject
0x180003648  call    cs:__imp_CloseHandle
0x18000364e  jmp     short loc_1800036C3
0x180003650  xor     edx, edx; lpNewFileName
0x180003652  mov     rcx, rbx; lpExistingFileName
0x180003655  lea     r8d, [rdx+4]; dwFlags
0x180003659  call    cs:__imp_MoveFileExW
0x18000365f  jmp     short loc_1800036C0
0x180003661  mov     ecx, 7FFFFFFEh
0x180003666  lea     rax, [rbp+0A20h+var_470]
0x18000366d  mov     r8, rbx
0x180003670  mov     edx, 104h
0x180003675  test    rcx, rcx
0x180003678  jz      short loc_180003698
0x18000367a  movzx   r9d, word ptr [r8]
0x18000367e  test    r9w, r9w
0x180003682  jz      short loc_180003698
0x180003684  mov     [rax], r9w
0x180003688  add     r8, 2
0x18000368c  add     rax, 2
0x180003690  sub     rcx, rdi
0x180003693  sub     rdx, rdi
0x180003696  jnz     short loc_180003675
0x180003698  test    rdx, rdx
0x18000369b  lea     rcx, [rax-2]
0x18000369f  cmovnz  rcx, rax
0x1800036a3  mov     [rcx], r13w
0x1800036a7  jz      short loc_1800036C0
0x1800036a9  lea     rdx, asc_180017038; "*.*"
0x1800036b0  lea     rcx, [rbp+0A20h+var_470]
0x1800036b7  call    ConcatenatePaths
0x1800036bc  test    eax, eax
0x1800036be  jnz     short loc_1800036DE
0x1800036c0  mov     edi, r13d
0x1800036c3  call    cs:__imp_GetProcessHeap
0x1800036c9  mov     r8, rbx; lpMem
0x1800036cc  xor     edx, edx; dwFlags
0x1800036ce  mov     rcx, rax; hHeap
0x1800036d1  call    cs:__imp_HeapFree
0x1800036d7  mov     eax, edi
0x1800036d9  jmp     loc_18000389F
0x1800036de  lea     rdx, [rsp+0B20h+FindFileData]; lpFindFileData
0x1800036e3  mov     r14d, edi
0x1800036e6  lea     rcx, [rbp+0A20h+var_470]; lpFileName
0x1800036ed  mov     r15d, edi
0x1800036f0  call    cs:__imp_FindFirstFileW
0x1800036f6  mov     r12, rax
0x1800036f9  mov     esi, 4
0x1800036fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003702  jz      loc_180003850
0x180003708  cmp     r15d, edi
0x18000370b  jnz     loc_180003850
0x180003711  mov     ecx, 7FFFFFFEh
0x180003716  lea     r8, [rbp+0A20h+FileName]
0x18000371d  mov     r9, rbx
0x180003720  mov     edx, 104h
0x180003725  test    rcx, rcx
0x180003728  jz      short loc_180003747
0x18000372a  movzx   eax, word ptr [r9]
0x18000372e  test    ax, ax
0x180003731  jz      short loc_180003747
0x180003733  mov     [r8], ax
0x180003737  add     r9, 2
0x18000373b  add     r8, 2
0x18000373f  sub     rcx, rdi
0x180003742  sub     rdx, rdi
0x180003745  jnz     short loc_180003725
0x180003747  test    rdx, rdx
0x18000374a  lea     rcx, [r8-2]
0x18000374e  cmovnz  rcx, r8
0x180003752  mov     [rcx], r13w
0x180003756  jz      loc_18000383A
0x18000375c  lea     rdx, [rsp+0B20h+FindFileData.cFileName]
0x180003761  lea     rcx, [rbp+0A20h+FileName]
0x180003768  call    ConcatenatePaths
0x18000376d  test    eax, eax
0x18000376f  jz      loc_18000383A
0x180003775  test    byte ptr [rsp+0B20h+FindFileData.dwFileAttributes], 10h
0x18000377a  jz      short loc_1800037C2
0x18000377c  lea     rdx, String2; "."
0x180003783  lea     rcx, [rsp+0B20h+FindFileData.cFileName]; lpString1
0x180003788  call    cs:__imp_lstrcmpW
0x18000378e  test    eax, eax
0x180003790  jz      loc_18000383A
0x180003796  lea     rdx, asc_180017044; ".."
0x18000379d  lea     rcx, [rsp+0B20h+FindFileData.cFileName]; lpString1
0x1800037a2  call    cs:__imp_lstrcmpW
0x1800037a8  test    eax, eax
0x1800037aa  jz      loc_18000383A
0x1800037b0  lea     rcx, [rbp+0A20h+FileName]
0x1800037b7  call    FSRemoveDirPath
0x1800037bc  test    eax, eax
0x1800037be  jnz     short loc_18000383A
0x1800037c0  jmp     short loc_180003837
0x1800037c2  mov     edx, 80h; dwFileAttributes
0x1800037c7  lea     rcx, [rbp+0A20h+FileName]; lpFileName
0x1800037ce  call    cs:__imp_SetFileAttributesW
0x1800037d4  lea     rcx, [rbp+0A20h+FileName]; lpFileName
0x1800037db  call    cs:__imp_DeleteFileW
0x1800037e1  test    eax, eax
0x1800037e3  jnz     short loc_18000383A
0x1800037e5  lea     r9, [rbp+0A20h+NewFileName]; lpTempFileName
0x1800037ec  xor     r8d, r8d; uUnique
0x1800037ef  lea     rdx, PrefixString; "DEL"
0x1800037f6  mov     rcx, rbx; lpPathName
0x1800037f9  call    cs:__imp_GetTempFileNameW
0x1800037ff  test    eax, eax
0x180003801  jz      short loc_180003825
0x180003803  mov     r8d, edi; dwFlags
0x180003806  lea     rdx, [rbp+0A20h+NewFileName]; lpNewFileName
0x18000380d  lea     rcx, [rbp+0A20h+FileName]; lpExistingFileName
0x180003814  call    cs:__imp_MoveFileExW
0x18000381a  lea     rcx, [rbp+0A20h+NewFileName]
0x180003821  test    eax, eax
0x180003823  jnz     short loc_18000382C
0x180003825  lea     rcx, [rbp+0A20h+FileName]; lpExistingFileName
0x18000382c  mov     r8d, esi; dwFlags
0x18000382f  xor     edx, edx; lpNewFileName
0x180003831  call    cs:__imp_MoveFileExW
0x180003837  mov     r14d, r13d
0x18000383a  lea     rdx, [rsp+0B20h+FindFileData]; lpFindFileData
0x18000383f  mov     rcx, r12; hFindFile
0x180003842  call    cs:__imp_FindNextFileW
0x180003848  mov     r15d, eax
0x18000384b  jmp     loc_180003708
0x180003850  mov     rcx, r12; hFindFile
0x180003853  call    cs:__imp_FindClose
0x180003859  mov     rcx, rbx; lpFileName
0x18000385c  call    cs:__imp_GetFileAttributesW
0x180003862  test    al, 10h
0x180003864  jz      short loc_180003884
0x180003866  mov     rcx, rbx; lpPathName
0x180003869  call    cs:__imp_RemoveDirectoryW
0x18000386f  test    eax, eax
0x180003871  jnz     short loc_180003884
0x180003873  mov     r8d, esi; dwFlags
0x180003876  xor     edx, edx; lpNewFileName
0x180003878  mov     rcx, rbx; lpExistingFileName
0x18000387b  call    cs:__imp_MoveFileExW
0x180003881  mov     r14d, r13d
0x180003884  call    cs:__imp_GetProcessHeap
0x18000388a  mov     r8, rbx; lpMem
0x18000388d  xor     edx, edx; dwFlags
0x18000388f  mov     rcx, rax; hHeap
0x180003892  call    cs:__imp_HeapFree
0x180003898  mov     eax, r14d
0x18000389b  jmp     short loc_18000389F
0x18000389d  xor     eax, eax
0x18000389f  mov     rcx, [rbp+0A20h+var_50]
0x1800038a6  xor     rcx, rsp; StackCookie
0x1800038a9  call    __security_check_cookie
0x1800038ae  add     rsp, 0AE8h
0x1800038b5  pop     r15
0x1800038b7  pop     r14
0x1800038b9  pop     r13
0x1800038bb  pop     r12
0x1800038bd  pop     rdi
0x1800038be  pop     rsi
0x1800038bf  pop     rbx
0x1800038c0  pop     rbp
0x1800038c1  retn
```
