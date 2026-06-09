# ReadExistingDllList(ushort const *,_DLL_LIST_ENTRY * *)

- ea: `0x18008c120`
- end: `0x18008c401`
- name: `?ReadExistingDllList@@YAHPEBGPEAPEAU_DLL_LIST_ENTRY@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _DLL_LIST_ENTRY **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180089f80`
- `0x18008a920`

## callees

- `0x180012920`
- `0x180089c5c`
- `0x18008c120`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `msvcrt!wcschr` at `0x18008c2dc`
- `msvcrt!wcschr` at `0x18008c2fa`
- `msvcrt!wcschr` at `0x18008c311`
- `msvcrt!wcschr` at `0x18008c2dc`
- `msvcrt!wcschr` at `0x18008c2fa`
- `msvcrt!wcschr` at `0x18008c311`
- `msvcrt!wcscpy_s` at `0x18008c33a`
- `msvcrt!wcscpy_s` at `0x18008c34b`
- `msvcrt!wcscpy_s` at `0x18008c33a`
- `msvcrt!wcscpy_s` at `0x18008c34b`
- `ntdll!RtlFreeHeap` at `0x18008c3b1`
- `ntdll!RtlFreeHeap` at `0x18008c3ce`
- `ntdll!RtlFreeHeap` at `0x18008c3b1`
- `ntdll!RtlFreeHeap` at `0x18008c3ce`
- `ntdll!RtlAllocateHeap` at `0x18008c1ca`
- `ntdll!RtlAllocateHeap` at `0x18008c274`
- `ntdll!RtlAllocateHeap` at `0x18008c1ca`
- `ntdll!RtlAllocateHeap` at `0x18008c274`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c394`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c394`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008c240`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008c2ab`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008c240`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008c2ab`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008c20c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008c20c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008c17e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008c17e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18008c19d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18008c19d`

## string_xrefs

- `0x18008c379`: `Failed to read file content`
- `0x18008c1e5`: `ReadExistingDllList`

## pseudocode

```c
__int64 __fastcall ReadExistingDllList(const unsigned __int16 *a1, struct _DLL_LIST_ENTRY **a2)
{
  HANDLE FileW; // rax
  void *v4; // r15
  WCHAR *v6; // rbp
  DWORD FileSize; // eax
  __int64 v8; // rbx
  unsigned int v9; // edi
  CHAR *Heap; // rax
  CHAR *v11; // rsi
  int v12; // eax
  int v13; // ebx
  WCHAR *v14; // rax
  const wchar_t *v15; // rbx
  wchar_t *v16; // rax
  wchar_t *v17; // rdi
  wchar_t *v18; // rax
  wchar_t *v19; // rax
  wchar_t *v20; // r14
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-4058h] BYREF
  wchar_t v22[4096]; // [rsp+50h] [rbp-4048h] BYREF
  wchar_t Destination[4096]; // [rsp+2050h] [rbp-2048h] BYREF

  NumberOfBytesRead = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 1;
  v6 = 0;
  FileSize = GetFileSize(FileW, 0);
  v8 = FileSize;
  if ( FileSize - 1 > 0xFFFFFFFD )
  {
    v11 = 0;
    v9 = 1;
  }
  else
  {
    v9 = 0;
    Heap = (CHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, FileSize + 1);
    v11 = Heap;
    if ( Heap )
    {
      if ( ReadFile(v4, Heap, v8, &NumberOfBytesRead, 0) && NumberOfBytesRead == (_DWORD)v8 )
      {
        v11[v8] = 0;
        v12 = MultiByteToWideChar(0xFDE9u, 0, v11, -1, 0, 0);
        v13 = v12;
        if ( v12 )
        {
          v14 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v12);
          v6 = v14;
          if ( v14 )
          {
            if ( MultiByteToWideChar(0xFDE9u, 0, v11, -1, v14, v13) )
            {
              v15 = v6;
              do
              {
                if ( !*v15 )
                  break;
                v16 = wcschr(v15, 0xAu);
                v17 = v16;
                if ( v16 )
                {
                  *v16 = 0;
                  v17 = v16 + 1;
                }
                v18 = wcschr(v15, 0xDu);
                if ( v18 )
                  *v18 = 0;
                v19 = wcschr(v15, 0x2Cu);
                v20 = v19;
                if ( v19 && v19 > v15 )
                {
                  *v19 = 0;
                  wcscpy_s(Destination, 0x1000u, v15);
                  wcscpy_s(v22, 0x1000u, v20 + 1);
                  AddDllToList(a2, Destination, v22);
                }
                v15 = v17;
              }
              while ( v17 );
              v9 = 1;
            }
            else
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"ReadExistingDllList",
                1128,
                (unsigned int)"Failed to convert to wide char");
            }
          }
          else
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"ReadExistingDllList",
              1122,
              (unsigned int)"Failed to allocate memory for wide content");
          }
        }
        else
        {
          AslLogCallPrintf(1, (unsigned int)"ReadExistingDllList", 1115, (unsigned int)"Failed to get wide char size");
        }
      }
      else
      {
        AslLogCallPrintf(1, (unsigned int)"ReadExistingDllList", 1105, (unsigned int)"Failed to read file content");
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"ReadExistingDllList",
        1099,
        (unsigned int)"Failed to allocate memory for file content");
    }
  }
  CloseHandle(v4);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return v9;
}

```

## disassembly

```asm
0x18008c120  mov     [rsp+arg_10], rbx
0x18008c125  push    rbp
0x18008c126  push    rsi
0x18008c127  push    rdi
0x18008c128  push    r12
0x18008c12a  push    r13
0x18008c12c  push    r14
0x18008c12e  push    r15
0x18008c130  mov     eax, 4060h
0x18008c135  call    _alloca_probe
0x18008c13a  sub     rsp, rax
0x18008c13d  mov     rax, cs:__security_cookie
0x18008c144  xor     rax, rsp
0x18008c147  mov     [rsp+4098h+var_48], rax
0x18008c14f  xor     r13d, r13d
0x18008c152  mov     r12, rdx
0x18008c155  mov     [rsp+4098h+hTemplateFile], r13; hTemplateFile
0x18008c15a  xor     r9d, r9d; lpSecurityAttributes
0x18008c15d  mov     [rsp+4098h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008c165  mov     edx, 80000000h; dwDesiredAccess
0x18008c16a  mov     [rsp+4098h+NumberOfBytesRead], r13d
0x18008c16f  lea     r14d, [r13+1]
0x18008c173  mov     [rsp+4098h+dwCreationDisposition], 3; dwCreationDisposition
0x18008c17b  mov     r8d, r14d; dwShareMode
0x18008c17e  call    cs:__imp_CreateFileW
0x18008c184  mov     r15, rax
0x18008c187  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008c18b  jnz     short loc_18008C195
0x18008c18d  mov     eax, r14d
0x18008c190  jmp     loc_18008C3D6
0x18008c195  xor     edx, edx; lpFileSizeHigh
0x18008c197  mov     rcx, r15; hFile
0x18008c19a  mov     rbp, r13
0x18008c19d  call    cs:__imp_GetFileSize
0x18008c1a3  mov     ebx, eax
0x18008c1a5  lea     ecx, [rbx-1]
0x18008c1a8  cmp     ecx, 0FFFFFFFDh
0x18008c1ab  ja      loc_18008C38B
0x18008c1b1  mov     rcx, gs:60h
0x18008c1ba  lea     r8d, [rbx+1]; Size
0x18008c1be  mov     edx, 8; Flags
0x18008c1c3  mov     edi, r13d
0x18008c1c6  mov     rcx, [rcx+30h]; HeapHandle
0x18008c1ca  call    cs:__imp_RtlAllocateHeap
0x18008c1d0  mov     rsi, rax
0x18008c1d3  test    rax, rax
0x18008c1d6  jnz     short loc_18008C1F9
0x18008c1d8  lea     r9, aFailedToAlloca; "Failed to allocate memory for file cont"...
0x18008c1df  mov     r8d, 44Bh
0x18008c1e5  lea     rdx, aReadexistingdl; "ReadExistingDllList"
0x18008c1ec  mov     ecx, r14d
0x18008c1ef  call    AslLogCallPrintf
0x18008c1f4  jmp     loc_18008C391
0x18008c1f9  lea     r9, [rsp+4098h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008c1fe  mov     qword ptr [rsp+4098h+dwCreationDisposition], r13; lpOverlapped
0x18008c203  mov     r8d, ebx; nNumberOfBytesToRead
0x18008c206  mov     rdx, rsi; lpBuffer
0x18008c209  mov     rcx, r15; hFile
0x18008c20c  call    cs:__imp_ReadFile
0x18008c212  test    eax, eax
0x18008c214  jz      loc_18008C379
0x18008c21a  cmp     [rsp+4098h+NumberOfBytesRead], ebx
0x18008c21e  jnz     loc_18008C379
0x18008c224  mov     [rsp+4098h+dwFlagsAndAttributes], r13d; cchWideChar
0x18008c229  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18008c22d  mov     r8, rsi; lpMultiByteStr
0x18008c230  mov     qword ptr [rsp+4098h+dwCreationDisposition], r13; lpWideCharStr
0x18008c235  xor     edx, edx; dwFlags
0x18008c237  mov     [rbx+rsi], r13b
0x18008c23b  mov     ecx, 0FDE9h; CodePage
0x18008c240  call    cs:__imp_MultiByteToWideChar
0x18008c246  movsxd  rbx, eax
0x18008c249  test    eax, eax
0x18008c24b  jnz     short loc_18008C25C
0x18008c24d  lea     r9, aFailedToGetWid; "Failed to get wide char size"
0x18008c254  mov     r8d, 45Bh
0x18008c25a  jmp     short loc_18008C1E5
0x18008c25c  mov     rcx, gs:60h
0x18008c265  mov     r8, rbx
0x18008c268  add     r8, r8; Size
0x18008c26b  mov     edx, 8; Flags
0x18008c270  mov     rcx, [rcx+30h]; HeapHandle
0x18008c274  call    cs:__imp_RtlAllocateHeap
0x18008c27a  mov     rbp, rax
0x18008c27d  test    rax, rax
0x18008c280  jnz     short loc_18008C294
0x18008c282  lea     r9, aFailedToAlloca_24; "Failed to allocate memory for wide cont"...
0x18008c289  mov     r8d, 462h
0x18008c28f  jmp     loc_18008C1E5
0x18008c294  mov     [rsp+4098h+dwFlagsAndAttributes], ebx; cchWideChar
0x18008c298  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18008c29c  mov     r8, rsi; lpMultiByteStr
0x18008c29f  mov     qword ptr [rsp+4098h+dwCreationDisposition], rbp; lpWideCharStr
0x18008c2a4  xor     edx, edx; dwFlags
0x18008c2a6  mov     ecx, 0FDE9h; CodePage
0x18008c2ab  call    cs:__imp_MultiByteToWideChar
0x18008c2b1  test    eax, eax
0x18008c2b3  jnz     short loc_18008C2C7
0x18008c2b5  lea     r9, aFailedToConver_21; "Failed to convert to wide char"
0x18008c2bc  mov     r8d, 468h
0x18008c2c2  jmp     loc_18008C1E5
0x18008c2c7  mov     rbx, rbp
0x18008c2ca  cmp     [rbx], r13w
0x18008c2ce  jz      loc_18008C372
0x18008c2d4  mov     edx, 0Ah; Ch
0x18008c2d9  mov     rcx, rbx; Str
0x18008c2dc  call    cs:__imp_wcschr
0x18008c2e2  mov     rdi, rax
0x18008c2e5  test    rax, rax
0x18008c2e8  jz      short loc_18008C2F2
0x18008c2ea  mov     [rax], r13w
0x18008c2ee  add     rdi, 2
0x18008c2f2  mov     edx, 0Dh; Ch
0x18008c2f7  mov     rcx, rbx; Str
0x18008c2fa  call    cs:__imp_wcschr
0x18008c300  test    rax, rax
0x18008c303  jz      short loc_18008C309
0x18008c305  mov     [rax], r13w
0x18008c309  mov     edx, 2Ch ; ','; Ch
0x18008c30e  mov     rcx, rbx; Str
0x18008c311  call    cs:__imp_wcschr
0x18008c317  mov     r14, rax
0x18008c31a  test    rax, rax
0x18008c31d  jz      short loc_18008C366
0x18008c31f  cmp     rax, rbx
0x18008c322  jbe     short loc_18008C366
0x18008c324  mov     r8, rbx; Source
0x18008c327  mov     [rax], r13w
0x18008c32b  mov     ebx, 1000h
0x18008c330  lea     rcx, [rsp+4098h+Destination]; Destination
0x18008c338  mov     edx, ebx; SizeInWords
0x18008c33a  call    cs:__imp_wcscpy_s
0x18008c340  lea     r8, [r14+2]; Source
0x18008c344  mov     edx, ebx; SizeInWords
0x18008c346  lea     rcx, [rsp+4098h+var_4048]; Destination
0x18008c34b  call    cs:__imp_wcscpy_s
0x18008c351  lea     r8, [rsp+4098h+var_4048]; unsigned __int16 *
0x18008c356  mov     rcx, r12; struct _DLL_LIST_ENTRY **
0x18008c359  lea     rdx, [rsp+4098h+Destination]; unsigned __int16 *
0x18008c361  call    ?AddDllToList@@YAHPEAPEAU_DLL_LIST_ENTRY@@PEBG1@Z; AddDllToList(_DLL_LIST_ENTRY * *,ushort const *,ushort const *)
0x18008c366  mov     rbx, rdi
0x18008c369  test    rdi, rdi
0x18008c36c  jnz     loc_18008C2CA
0x18008c372  mov     edi, 1
0x18008c377  jmp     short loc_18008C391
0x18008c379  lea     r9, aFailedToReadFi_0; "Failed to read file content"
0x18008c380  mov     r8d, 451h
0x18008c386  jmp     loc_18008C1E5
0x18008c38b  mov     rsi, r13
0x18008c38e  mov     edi, r14d
0x18008c391  mov     rcx, r15; hObject
0x18008c394  call    cs:__imp_CloseHandle
0x18008c39a  test    rsi, rsi
0x18008c39d  jz      short loc_18008C3B7
0x18008c39f  mov     rcx, gs:60h
0x18008c3a8  mov     r8, rsi; P
0x18008c3ab  xor     edx, edx; Flags
0x18008c3ad  mov     rcx, [rcx+30h]; HeapHandle
0x18008c3b1  call    cs:__imp_RtlFreeHeap
0x18008c3b7  test    rbp, rbp
0x18008c3ba  jz      short loc_18008C3D4
0x18008c3bc  mov     rcx, gs:60h
0x18008c3c5  mov     r8, rbp; P
0x18008c3c8  xor     edx, edx; Flags
0x18008c3ca  mov     rcx, [rcx+30h]; HeapHandle
0x18008c3ce  call    cs:__imp_RtlFreeHeap
0x18008c3d4  mov     eax, edi
0x18008c3d6  mov     rcx, [rsp+4098h+var_48]
0x18008c3de  xor     rcx, rsp; StackCookie
0x18008c3e1  call    __security_check_cookie
0x18008c3e6  mov     rbx, [rsp+4098h+arg_10]
0x18008c3ee  add     rsp, 4060h
0x18008c3f5  pop     r15
0x18008c3f7  pop     r14
0x18008c3f9  pop     r13
0x18008c3fb  pop     r12
0x18008c3fd  pop     rdi
0x18008c3fe  pop     rsi
0x18008c3ff  pop     rbp
0x18008c400  retn
```
