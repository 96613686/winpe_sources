# WriteDllListToFile(ushort const *,_DLL_LIST_ENTRY *)

- ea: `0x18008c4fc`
- end: `0x18008c789`
- name: `?WriteDllListToFile@@YAHPEBGPEAU_DLL_LIST_ENTRY@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _DLL_LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18008a920`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x18008c4fc`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18008c69e`
- `ntdll!RtlFreeHeap` at `0x18008c6d5`
- `ntdll!RtlFreeHeap` at `0x18008c69e`
- `ntdll!RtlFreeHeap` at `0x18008c6d5`
- `ntdll!RtlAllocateHeap` at `0x18008c619`
- `ntdll!RtlAllocateHeap` at `0x18008c619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c56c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c56c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c6b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c6b8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008c5f3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008c64e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008c5f3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008c64e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008c55d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008c55d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008c67c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008c67c`

## string_xrefs

- `0x18008c576`: `Failed to create file %ws with error [%d]`
- `0x18008c588`: `WriteDllListToFile`
- `0x18008c72f`: `WriteDllListToFile`
- `0x18008c750`: `WriteDllListToFile`
- `0x18008c775`: `WriteDllListToFile`
- `0x18008c704`: `Failed to write to file`

## pseudocode

```c
__int64 __fastcall WriteDllListToFile(const unsigned __int16 *a1, struct _DLL_LIST_ENTRY *a2)
{
  HANDLE FileW; // r14
  unsigned int v6; // ebp
  int v7; // eax
  int v8; // eax
  int v9; // edi
  CHAR *Heap; // rax
  CHAR *v11; // rbx
  __int64 v12; // rdi
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-4068h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-4060h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-4048h] BYREF
  WCHAR WideCharStr[8192]; // [rsp+50h] [rbp-4038h] BYREF

  NumberOfBytesWritten = 0;
  FileW = CreateFileW(a1, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LODWORD(dwFlagsAndAttributes) = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"WriteDllListToFile",
      1216,
      (unsigned int)"Failed to create file %ws with error [%d]",
      a1,
      dwFlagsAndAttributes);
    return 0;
  }
  v6 = 0;
  while ( 1 )
  {
    if ( !a2 )
    {
      v6 = 1;
LABEL_15:
      v11 = 0;
      goto LABEL_16;
    }
    v7 = StringCchPrintfW(WideCharStr, 0x2000u, L"%s,%s\r\n", *((_QWORD *)a2 + 1), *((_QWORD *)a2 + 2));
    if ( v7 < 0 )
    {
      dwCreationDisposition[0] = v7;
      AslLogCallPrintf(
        1,
        (unsigned int)"WriteDllListToFile",
        1226,
        (unsigned int)"StringCchPrintfW failed with error [%d]",
        *(_QWORD *)dwCreationDisposition);
      goto LABEL_15;
    }
    v8 = WideCharToMultiByte(0xFDE9u, 0, WideCharStr, -1, 0, 0, 0, 0);
    v9 = v8;
    if ( !v8 )
    {
      AslLogCallPrintf(1, (unsigned int)"WriteDllListToFile", 1234, (unsigned int)"Failed to get UTF-8 size");
      goto LABEL_15;
    }
    Heap = (CHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v8);
    v11 = Heap;
    if ( !Heap )
      break;
    if ( !WideCharToMultiByte(0xFDE9u, 0, WideCharStr, -1, Heap, v9, 0, 0) )
    {
      AslLogCallPrintf(1, (unsigned int)"WriteDllListToFile", 1247, (unsigned int)"Failed to convert to UTF-8");
      goto LABEL_16;
    }
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    if ( !WriteFile(FileW, v11, v12, &NumberOfBytesWritten, 0) || (_DWORD)v12 != NumberOfBytesWritten )
    {
      AslLogCallPrintf(1, (unsigned int)"WriteDllListToFile", 1254, (unsigned int)"Failed to write to file");
      goto LABEL_16;
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    a2 = *(struct _DLL_LIST_ENTRY **)a2;
  }
  AslLogCallPrintf(
    1,
    (unsigned int)"WriteDllListToFile",
    1241,
    (unsigned int)"Failed to allocate memory for UTF-8 line");
LABEL_16:
  CloseHandle(FileW);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  return v6;
}

```

## disassembly

```asm
0x18008c4fc  mov     [rsp+arg_10], rbx
0x18008c501  push    rbp
0x18008c502  push    rsi
0x18008c503  push    rdi
0x18008c504  push    r12
0x18008c506  push    r14
0x18008c508  mov     eax, 4060h
0x18008c50d  call    _alloca_probe
0x18008c512  sub     rsp, rax
0x18008c515  mov     rax, cs:__security_cookie
0x18008c51c  xor     rax, rsp
0x18008c51f  mov     [rsp+4088h+var_38], rax
0x18008c527  xor     r9d, r9d; lpSecurityAttributes
0x18008c52a  mov     [rsp+4088h+hTemplateFile], 0; hTemplateFile
0x18008c533  mov     rsi, rdx
0x18008c536  mov     dword ptr [rsp+4088h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008c53e  mov     edx, 40000000h; dwDesiredAccess
0x18008c543  mov     [rsp+4088h+NumberOfBytesWritten], 0
0x18008c54b  mov     rbx, rcx
0x18008c54e  mov     [rsp+4088h+dwCreationDisposition], 2; dwCreationDisposition
0x18008c556  lea     r12d, [r9+1]
0x18008c55a  mov     r8d, r12d; dwShareMode
0x18008c55d  call    cs:__imp_CreateFileW
0x18008c563  mov     r14, rax
0x18008c566  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008c56a  jnz     short loc_18008C59E
0x18008c56c  call    cs:__imp_GetLastError
0x18008c572  mov     dword ptr [rsp+4088h+dwFlagsAndAttributes], eax
0x18008c576  lea     r9, aFailedToCreate_53; "Failed to create file %ws with error [%"...
0x18008c57d  mov     r8d, 4C0h
0x18008c583  mov     qword ptr [rsp+4088h+dwCreationDisposition], rbx
0x18008c588  lea     rdx, aWritedlllistto; "WriteDllListToFile"
0x18008c58f  mov     ecx, r12d
0x18008c592  call    AslLogCallPrintf
0x18008c597  xor     eax, eax
0x18008c599  jmp     loc_18008C6DD
0x18008c59e  xor     ebp, ebp
0x18008c5a0  jmp     loc_18008C6A7
0x18008c5a5  mov     rax, [rsi+10h]
0x18008c5a9  lea     r8, aSS_4; "%s,%s\r\n"
0x18008c5b0  mov     r9, [rsi+8]
0x18008c5b4  lea     rcx, [rsp+4088h+WideCharStr]; unsigned __int16 *
0x18008c5b9  mov     edx, 2000h; unsigned __int64
0x18008c5be  mov     qword ptr [rsp+4088h+dwCreationDisposition], rax
0x18008c5c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008c5c8  test    eax, eax
0x18008c5ca  js      loc_18008C764
0x18008c5d0  mov     [rsp+4088h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x18008c5d5  lea     r8, [rsp+4088h+WideCharStr]; lpWideCharStr
0x18008c5da  mov     [rsp+4088h+hTemplateFile], rbp; lpDefaultChar
0x18008c5df  or      r9d, 0FFFFFFFFh; cchWideChar
0x18008c5e3  mov     dword ptr [rsp+4088h+dwFlagsAndAttributes], ebp; cbMultiByte
0x18008c5e7  xor     edx, edx; dwFlags
0x18008c5e9  mov     ecx, 0FDE9h; CodePage
0x18008c5ee  mov     qword ptr [rsp+4088h+dwCreationDisposition], rbp; lpMultiByteStr
0x18008c5f3  call    cs:__imp_WideCharToMultiByte
0x18008c5f9  movsxd  rdi, eax
0x18008c5fc  test    eax, eax
0x18008c5fe  jz      loc_18008C743
0x18008c604  mov     rcx, gs:60h
0x18008c60d  mov     r8, rdi; Size
0x18008c610  mov     edx, 8; Flags
0x18008c615  mov     rcx, [rcx+30h]; HeapHandle
0x18008c619  call    cs:__imp_RtlAllocateHeap
0x18008c61f  mov     rbx, rax
0x18008c622  test    rax, rax
0x18008c625  jz      loc_18008C722
0x18008c62b  mov     [rsp+4088h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x18008c630  lea     r8, [rsp+4088h+WideCharStr]; lpWideCharStr
0x18008c635  mov     [rsp+4088h+hTemplateFile], rbp; lpDefaultChar
0x18008c63a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18008c63e  mov     dword ptr [rsp+4088h+dwFlagsAndAttributes], edi; cbMultiByte
0x18008c642  xor     edx, edx; dwFlags
0x18008c644  mov     ecx, 0FDE9h; CodePage
0x18008c649  mov     qword ptr [rsp+4088h+dwCreationDisposition], rax; lpMultiByteStr
0x18008c64e  call    cs:__imp_WideCharToMultiByte
0x18008c654  test    eax, eax
0x18008c656  jz      loc_18008C713
0x18008c65c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008c660  inc     rdi
0x18008c663  cmp     [rbx+rdi], bpl
0x18008c667  jnz     short loc_18008C660
0x18008c669  lea     r9, [rsp+4088h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008c66e  mov     qword ptr [rsp+4088h+dwCreationDisposition], rbp; lpOverlapped
0x18008c673  mov     r8d, edi; nNumberOfBytesToWrite
0x18008c676  mov     rdx, rbx; lpBuffer
0x18008c679  mov     rcx, r14; hFile
0x18008c67c  call    cs:__imp_WriteFile
0x18008c682  test    eax, eax
0x18008c684  jz      short loc_18008C704
0x18008c686  cmp     edi, [rsp+4088h+NumberOfBytesWritten]
0x18008c68a  jnz     short loc_18008C704
0x18008c68c  mov     rcx, gs:60h
0x18008c695  mov     r8, rbx; P
0x18008c698  xor     edx, edx; Flags
0x18008c69a  mov     rcx, [rcx+30h]; HeapHandle
0x18008c69e  call    cs:__imp_RtlFreeHeap
0x18008c6a4  mov     rsi, [rsi]
0x18008c6a7  test    rsi, rsi
0x18008c6aa  jnz     loc_18008C5A5
0x18008c6b0  mov     ebp, r12d
0x18008c6b3  xor     ebx, ebx
0x18008c6b5  mov     rcx, r14; hObject
0x18008c6b8  call    cs:__imp_CloseHandle
0x18008c6be  test    rbx, rbx
0x18008c6c1  jz      short loc_18008C6DB
0x18008c6c3  mov     rcx, gs:60h
0x18008c6cc  mov     r8, rbx; P
0x18008c6cf  xor     edx, edx; Flags
0x18008c6d1  mov     rcx, [rcx+30h]; HeapHandle
0x18008c6d5  call    cs:__imp_RtlFreeHeap
0x18008c6db  mov     eax, ebp
0x18008c6dd  mov     rcx, [rsp+4088h+var_38]
0x18008c6e5  xor     rcx, rsp; StackCookie
0x18008c6e8  call    __security_check_cookie
0x18008c6ed  mov     rbx, [rsp+4088h+arg_10]
0x18008c6f5  add     rsp, 4060h
0x18008c6fc  pop     r14
0x18008c6fe  pop     r12
0x18008c700  pop     rdi
0x18008c701  pop     rsi
0x18008c702  pop     rbp
0x18008c703  retn
0x18008c704  lea     r9, aFailedToWriteT_4; "Failed to write to file"
0x18008c70b  mov     r8d, 4E6h
0x18008c711  jmp     short loc_18008C72F
0x18008c713  lea     r9, aFailedToConver_17; "Failed to convert to UTF-8"
0x18008c71a  mov     r8d, 4DFh
0x18008c720  jmp     short loc_18008C72F
0x18008c722  lea     r9, aFailedToAlloca_31; "Failed to allocate memory for UTF-8 lin"...
0x18008c729  mov     r8d, 4D9h
0x18008c72f  lea     rdx, aWritedlllistto; "WriteDllListToFile"
0x18008c736  mov     ecx, r12d
0x18008c739  call    AslLogCallPrintf
0x18008c73e  jmp     loc_18008C6B5
0x18008c743  lea     r9, aFailedToGetUtf; "Failed to get UTF-8 size"
0x18008c74a  mov     r8d, 4D2h
0x18008c750  lea     rdx, aWritedlllistto; "WriteDllListToFile"
0x18008c757  mov     ecx, r12d
0x18008c75a  call    AslLogCallPrintf
0x18008c75f  jmp     loc_18008C6B3
0x18008c764  lea     r9, aStringcchprint_4; "StringCchPrintfW failed with error [%d]"
0x18008c76b  mov     [rsp+4088h+dwCreationDisposition], eax
0x18008c76f  mov     r8d, 4CAh
0x18008c775  lea     rdx, aWritedlllistto; "WriteDllListToFile"
0x18008c77c  mov     ecx, r12d
0x18008c77f  call    AslLogCallPrintf
0x18008c784  jmp     loc_18008C6B3
```
