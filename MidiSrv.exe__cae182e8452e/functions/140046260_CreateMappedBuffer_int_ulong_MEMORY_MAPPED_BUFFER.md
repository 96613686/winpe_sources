# CreateMappedBuffer(int,ulong,MEMORY_MAPPED_BUFFER *)

- ea: `0x140046260`
- end: `0x140046426`
- name: `?CreateMappedBuffer@@YAJHKPEAUMEMORY_MAPPED_BUFFER@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(int, DWORD, HANDLE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x14004642c`
- `0x1400464d8`

## callees

- `0x14000a694`
- `0x14000a6b4`
- `0x140046260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400462c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140046379`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400463cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400462c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140046379`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400463cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400462b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400463b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400462b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400463b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400462be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400462be`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x140046311`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x140046311`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140046371`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400463c3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140046371`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400463c3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x140046354`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1400463a6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x140046354`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1400463a6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x140046332`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x140046332`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14004629d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14004629d`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
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
0x140046260  push    rbx
0x140046262  push    rbp
0x140046263  push    rsi
0x140046264  push    rdi
0x140046265  push    r14
0x140046267  push    r15
0x140046269  sub     rsp, 38h
0x14004626d  mov     rax, [r8]
0x140046270  mov     rdi, r8
0x140046273  inc     rax
0x140046276  mov     esi, edx
0x140046278  mov     r15d, ecx
0x14004627b  test    rax, 0FFFFFFFFFFFFFFFEh
0x140046281  jnz     short loc_1400462F6
0x140046283  xor     r9d, r9d; dwMaximumSizeHigh
0x140046286  mov     [rsp+68h+lpName], 0; lpName
0x14004628f  xor     edx, edx; lpFileMappingAttributes
0x140046291  mov     [rsp+68h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x140046295  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x140046299  lea     r8d, [r9+4]; flProtect
0x14004629d  call    cs:__imp_CreateFileMappingW
0x1400462a3  mov     r14, [rdi]
0x1400462a6  mov     rbp, rax
0x1400462a9  lea     rdx, [r14-1]
0x1400462ad  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400462b1  ja      short loc_1400462CC
0x1400462b3  call    cs:__imp_GetLastError
0x1400462b9  mov     rcx, r14; hObject
0x1400462bc  mov     ebx, eax
0x1400462be  call    cs:__imp_CloseHandle
0x1400462c4  mov     ecx, ebx; dwErrCode
0x1400462c6  call    cs:__imp_SetLastError
0x1400462cc  lea     rax, [rbp+1]
0x1400462d0  mov     [rdi], rbp
0x1400462d3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400462d9  jnz     short loc_1400462F6
0x1400462db  mov     rcx, [rsp+68h]; this
0x1400462e0  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x1400462e7  mov     edx, 79h ; 'y'; void *
0x1400462ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400462f1  jmp     loc_140046419
0x1400462f6  xor     ebp, ebp
0x1400462f8  test    r15d, r15d
0x1400462fb  jz      loc_14004638E
0x140046301  lea     rdx, [rsi+rsi]; dwSize
0x140046305  xor     ecx, ecx; lpAddress
0x140046307  lea     r9d, [rbp+4]; flProtect
0x14004630b  mov     r8d, 2000h; flAllocationType
0x140046311  call    cs:__imp_VirtualAlloc
0x140046317  mov     rbp, rax
0x14004631a  test    rax, rax
0x14004631d  jnz     short loc_140046327
0x14004631f  lea     edx, [rax+62h]
0x140046322  jmp     loc_1400463DD
0x140046327  xor     edx, edx; dwSize
0x140046329  mov     r8d, 8000h; dwFreeType
0x14004632f  mov     rcx, rbp; lpAddress
0x140046332  call    cs:__imp_VirtualFree
0x140046338  mov     rcx, [rdi]; hFileMappingObject
0x14004633b  lea     rax, [rsi+rbp]
0x14004633f  mov     [rsp+68h+lpName], rax; lpBaseAddress
0x140046344  xor     r9d, r9d; dwFileOffsetLow
0x140046347  xor     r8d, r8d; dwFileOffsetHigh
0x14004634a  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x14004634f  mov     edx, 0F001Fh; dwDesiredAccess
0x140046354  call    cs:__imp_MapViewOfFileEx
0x14004635a  mov     r15, [rdi+10h]
0x14004635e  mov     r14, rax
0x140046361  test    r15, r15
0x140046364  jz      short loc_14004637F
0x140046366  call    cs:__imp_GetLastError
0x14004636c  mov     rcx, r15; lpBaseAddress
0x14004636f  mov     ebx, eax
0x140046371  call    cs:__imp_UnmapViewOfFile
0x140046377  mov     ecx, ebx; dwErrCode
0x140046379  call    cs:__imp_SetLastError
0x14004637f  mov     [rdi+10h], r14
0x140046383  test    r14, r14
0x140046386  jnz     short loc_14004638E
0x140046388  lea     edx, [r14+67h]
0x14004638c  jmp     short loc_1400463DD
0x14004638e  mov     rcx, [rdi]; hFileMappingObject
0x140046391  xor     r9d, r9d; dwFileOffsetLow
0x140046394  mov     [rsp+68h+lpName], rbp; lpBaseAddress
0x140046399  xor     r8d, r8d; dwFileOffsetHigh
0x14004639c  mov     edx, 0F001Fh; dwDesiredAccess
0x1400463a1  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rsi; int
0x1400463a6  call    cs:__imp_MapViewOfFileEx
0x1400463ac  mov     rbp, [rdi+8]
0x1400463b0  mov     rsi, rax
0x1400463b3  test    rbp, rbp
0x1400463b6  jz      short loc_1400463D1
0x1400463b8  call    cs:__imp_GetLastError
0x1400463be  mov     rcx, rbp; lpBaseAddress
0x1400463c1  mov     ebx, eax
0x1400463c3  call    cs:__imp_UnmapViewOfFile
0x1400463c9  mov     ecx, ebx; dwErrCode
0x1400463cb  call    cs:__imp_SetLastError
0x1400463d1  mov     [rdi+8], rsi
0x1400463d5  test    rsi, rsi
0x1400463d8  jnz     short loc_140046417
0x1400463da  lea     edx, [rsi+6Bh]; void *
0x1400463dd  mov     rcx, [rsp+68h]; this
0x1400463e2  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x1400463e9  mov     r9d, 8007000Eh; char *
0x1400463ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400463f4  mov     rcx, [rsp+68h]; this
0x1400463f9  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x140046400  mov     r9d, 8007000Eh; char *
0x140046406  mov     edx, 7Bh ; '{'; void *
0x14004640b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140046410  mov     eax, 8007000Eh
0x140046415  jmp     short loc_140046419
0x140046417  xor     eax, eax
0x140046419  add     rsp, 38h
0x14004641d  pop     r15
0x14004641f  pop     r14
0x140046421  pop     rdi
0x140046422  pop     rsi
0x140046423  pop     rbp
0x140046424  pop     rbx
0x140046425  retn
```
