# CreateMappedBuffer(int,ulong,MEMORY_MAPPED_BUFFER *)

- ea: `0x18000d504`
- end: `0x18000d6ca`
- name: `?CreateMappedBuffer@@YAJHKPEAUMEMORY_MAPPED_BUFFER@@@Z`
- size: `454`
- prototype: `int(int, unsigned int, struct MEMORY_MAPPED_BUFFER *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000d6d0`
- `0x18000d748`

## callees

- `0x180007e04`
- `0x180007e24`
- `0x18000d504`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d56a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d61d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d66f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d56a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d61d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d66f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d60a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d65c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d60a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d562`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d562`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000d5b5`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000d5b5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000d5f8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000d64a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000d5f8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000d64a`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000d5d6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000d5d6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d615`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d667`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d615`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d667`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000d541`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000d541`

## pseudocode

```c
__int64 __fastcall CreateMappedBuffer(int a1, DWORD a2, HANDLE *a3)
{
  SIZE_T v4; // rsi
  HANDLE FileMappingW; // rax
  const char *v7; // r9
  HANDLE v8; // r14
  HANDLE v9; // rbp
  DWORD LastError; // ebx
  char *v12; // rbp
  char *v13; // rax
  __int64 v14; // rdx
  LPVOID v15; // rax
  HANDLE v16; // r15
  void *v17; // r14
  DWORD v18; // ebx
  LPVOID v19; // rax
  HANDLE v20; // rbp
  void *v21; // rsi
  DWORD v22; // ebx
  int dwMaximumSizeLow; // [rsp+20h] [rbp-48h]
  int dwMaximumSizeLowa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = a2;
  if ( (((unsigned __int64)*a3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, a2, 0);
    v8 = *a3;
    v9 = FileMappingW;
    if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v8);
      SetLastError(LastError);
    }
    *a3 = v9;
    if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x79,
               (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
               v7);
  }
  v12 = 0;
  if ( a1 )
  {
    v13 = (char *)VirtualAlloc(0, 2 * v4, 0x2000u, 4u);
    v12 = v13;
    if ( !v13 )
    {
      v14 = 98;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
        (const char *)0x8007000ELL,
        dwMaximumSizeLow);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
        (const char *)0x8007000ELL,
        dwMaximumSizeLowa);
      return 2147942414LL;
    }
    VirtualFree(v13, 0, 0x8000u);
    v15 = MapViewOfFileEx(*a3, 0xF001Fu, 0, 0, v4, &v12[v4]);
    v16 = a3[2];
    v17 = v15;
    if ( v16 )
    {
      v18 = GetLastError();
      UnmapViewOfFile(v16);
      SetLastError(v18);
    }
    a3[2] = v17;
    if ( !v17 )
    {
      v14 = 103;
      goto LABEL_17;
    }
  }
  v19 = MapViewOfFileEx(*a3, 0xF001Fu, 0, 0, v4, v12);
  v20 = a3[1];
  v21 = v19;
  if ( v20 )
  {
    v22 = GetLastError();
    UnmapViewOfFile(v20);
    SetLastError(v22);
  }
  a3[1] = v21;
  if ( !v21 )
  {
    v14 = 107;
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d504  push    rbx
0x18000d506  push    rbp
0x18000d507  push    rsi
0x18000d508  push    rdi
0x18000d509  push    r14
0x18000d50b  push    r15
0x18000d50d  sub     rsp, 38h
0x18000d511  mov     rax, [r8]
0x18000d514  mov     rdi, r8
0x18000d517  inc     rax
0x18000d51a  mov     esi, edx
0x18000d51c  mov     r15d, ecx
0x18000d51f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000d525  jnz     short loc_18000D59A
0x18000d527  xor     r9d, r9d; dwMaximumSizeHigh
0x18000d52a  mov     [rsp+68h+lpName], 0; lpName
0x18000d533  xor     edx, edx; lpFileMappingAttributes
0x18000d535  mov     [rsp+68h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x18000d539  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000d53d  lea     r8d, [r9+4]; flProtect
0x18000d541  call    cs:__imp_CreateFileMappingW
0x18000d547  mov     r14, [rdi]
0x18000d54a  mov     rbp, rax
0x18000d54d  lea     rdx, [r14-1]
0x18000d551  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000d555  ja      short loc_18000D570
0x18000d557  call    cs:__imp_GetLastError
0x18000d55d  mov     rcx, r14; hObject
0x18000d560  mov     ebx, eax
0x18000d562  call    cs:__imp_CloseHandle
0x18000d568  mov     ecx, ebx; dwErrCode
0x18000d56a  call    cs:__imp_SetLastError
0x18000d570  lea     rax, [rbp+1]
0x18000d574  mov     [rdi], rbp
0x18000d577  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000d57d  jnz     short loc_18000D59A
0x18000d57f  mov     rcx, [rsp+68h]; this
0x18000d584  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18000d58b  mov     edx, 79h ; 'y'; void *
0x18000d590  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d595  jmp     loc_18000D6BD
0x18000d59a  xor     ebp, ebp
0x18000d59c  test    r15d, r15d
0x18000d59f  jz      loc_18000D632
0x18000d5a5  lea     rdx, [rsi+rsi]; dwSize
0x18000d5a9  xor     ecx, ecx; lpAddress
0x18000d5ab  lea     r9d, [rbp+4]; flProtect
0x18000d5af  mov     r8d, 2000h; flAllocationType
0x18000d5b5  call    cs:__imp_VirtualAlloc
0x18000d5bb  mov     rbp, rax
0x18000d5be  test    rax, rax
0x18000d5c1  jnz     short loc_18000D5CB
0x18000d5c3  lea     edx, [rax+62h]
0x18000d5c6  jmp     loc_18000D681
0x18000d5cb  xor     edx, edx; dwSize
0x18000d5cd  mov     r8d, 8000h; dwFreeType
0x18000d5d3  mov     rcx, rbp; lpAddress
0x18000d5d6  call    cs:__imp_VirtualFree
0x18000d5dc  mov     rcx, [rdi]; hFileMappingObject
0x18000d5df  lea     rax, [rsi+rbp]
0x18000d5e3  mov     [rsp+68h+lpName], rax; lpBaseAddress
0x18000d5e8  xor     r9d, r9d; dwFileOffsetLow
0x18000d5eb  xor     r8d, r8d; dwFileOffsetHigh
0x18000d5ee  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x18000d5f3  mov     edx, 0F001Fh; dwDesiredAccess
0x18000d5f8  call    cs:__imp_MapViewOfFileEx
0x18000d5fe  mov     r15, [rdi+10h]
0x18000d602  mov     r14, rax
0x18000d605  test    r15, r15
0x18000d608  jz      short loc_18000D623
0x18000d60a  call    cs:__imp_GetLastError
0x18000d610  mov     rcx, r15; lpBaseAddress
0x18000d613  mov     ebx, eax
0x18000d615  call    cs:__imp_UnmapViewOfFile
0x18000d61b  mov     ecx, ebx; dwErrCode
0x18000d61d  call    cs:__imp_SetLastError
0x18000d623  mov     [rdi+10h], r14
0x18000d627  test    r14, r14
0x18000d62a  jnz     short loc_18000D632
0x18000d62c  lea     edx, [r14+67h]
0x18000d630  jmp     short loc_18000D681
0x18000d632  mov     rcx, [rdi]; hFileMappingObject
0x18000d635  xor     r9d, r9d; dwFileOffsetLow
0x18000d638  mov     [rsp+68h+lpName], rbp; lpBaseAddress
0x18000d63d  xor     r8d, r8d; dwFileOffsetHigh
0x18000d640  mov     edx, 0F001Fh; dwDesiredAccess
0x18000d645  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rsi; int
0x18000d64a  call    cs:__imp_MapViewOfFileEx
0x18000d650  mov     rbp, [rdi+8]
0x18000d654  mov     rsi, rax
0x18000d657  test    rbp, rbp
0x18000d65a  jz      short loc_18000D675
0x18000d65c  call    cs:__imp_GetLastError
0x18000d662  mov     rcx, rbp; lpBaseAddress
0x18000d665  mov     ebx, eax
0x18000d667  call    cs:__imp_UnmapViewOfFile
0x18000d66d  mov     ecx, ebx; dwErrCode
0x18000d66f  call    cs:__imp_SetLastError
0x18000d675  mov     [rdi+8], rsi
0x18000d679  test    rsi, rsi
0x18000d67c  jnz     short loc_18000D6BB
0x18000d67e  lea     edx, [rsi+6Bh]; void *
0x18000d681  mov     rcx, [rsp+68h]; this
0x18000d686  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18000d68d  mov     r9d, 8007000Eh; char *
0x18000d693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d698  mov     rcx, [rsp+68h]; this
0x18000d69d  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18000d6a4  mov     r9d, 8007000Eh; char *
0x18000d6aa  mov     edx, 7Bh ; '{'; void *
0x18000d6af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d6b4  mov     eax, 8007000Eh
0x18000d6b9  jmp     short loc_18000D6BD
0x18000d6bb  xor     eax, eax
0x18000d6bd  add     rsp, 38h
0x18000d6c1  pop     r15
0x18000d6c3  pop     r14
0x18000d6c5  pop     rdi
0x18000d6c6  pop     rsi
0x18000d6c7  pop     rbp
0x18000d6c8  pop     rbx
0x18000d6c9  retn
```
