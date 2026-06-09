# Microsoft::Resources::BaseFile::LoadFileData(ushort const *,unsigned __int64 *,void * *)

- ea: `0x1800795e4`
- end: `0x1800797b7`
- name: `?LoadFileData@BaseFile@Resources@Microsoft@@SAJPEBGPEA_KPEAPEAX@Z`
- size: `467`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64 *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024788`

## callees

- `0x1800238c4`
- `0x18002c8d0`
- `0x180030c6c`
- `0x180072238`
- `0x1800795e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079673`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079673`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079662`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800796a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800796a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007975c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007975c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007969b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007969b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180079637`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180079637`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::BaseFile::LoadFileData(
        const unsigned __int16 *a1,
        unsigned __int64 *a2,
        Microsoft::Resources **a3,
        __int64 a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  char *v8; // rdi
  signed int LastError; // eax
  unsigned __int64 LowPart; // r14
  HANDLE ProcessHeap; // rax
  Microsoft::Resources *v12; // rax
  Microsoft::Resources *v13; // rsi
  signed int v14; // eax
  void *v15; // rdx
  bool v16; // cc
  HANDLE v18; // rcx
  void *v19; // rdx
  int lpOverlapped; // [rsp+20h] [rbp-20h]
  int lpOverlappeda; // [rsp+20h] [rbp-20h]
  int lpOverlappedb; // [rsp+20h] [rbp-20h]
  int v23; // [rsp+28h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp+48h] BYREF
  HANDLE hFile; // [rsp+90h] [rbp+50h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+58h] BYREF

  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  *a2 = 0;
  *a3 = 0;
  hFile = 0;
  v6 = DefCreateFile(a1, (__int64)a2, (__int64)a3, a4, lpOverlapped, v23, &hFile);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\basefile.cpp",
      (const char *)(unsigned int)v6,
      lpOverlappeda);
    v18 = hFile;
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return v7;
LABEL_18:
    CloseHandle(v18);
    return v7;
  }
  v8 = (char *)hFile;
  if ( !GetFileSizeEx(hFile, &FileSize) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (v7 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\basefile.cpp",
        (const char *)v7,
        lpOverlappeda);
      goto LABEL_23;
    }
  }
  LowPart = FileSize.LowPart;
  ProcessHeap = GetProcessHeap();
  v12 = (Microsoft::Resources *)HeapAlloc(ProcessHeap, 8u, (unsigned int)LowPart);
  v13 = v12;
  if ( v12 )
  {
    if ( !ReadFile(v8, v12, LowPart, &NumberOfBytesRead, 0) )
    {
      v14 = GetLastError();
      v7 = v14;
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      if ( (v7 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\basefile.cpp",
          (const char *)v7,
          lpOverlappedb);
        Microsoft::Resources::DefFreeMemory(v13, v15);
        v16 = (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
        goto LABEL_12;
      }
    }
    if ( NumberOfBytesRead == (_DWORD)LowPart )
    {
      *a2 = LowPart;
      v7 = 0;
      *a3 = v13;
    }
    else
    {
      v7 = -2147009770;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\basefile.cpp",
        (const char *)0x80073B16LL,
        lpOverlappedb);
      Microsoft::Resources::DefFreeMemory(v13, v19);
    }
LABEL_23:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hFile);
    return v7;
  }
  v7 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6F,
    (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\basefile.cpp",
    (const char *)0x8007000ELL,
    lpOverlappeda);
  v16 = (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_12:
  if ( v16 )
  {
    v18 = v8;
    goto LABEL_18;
  }
  return v7;
}

```

## disassembly

```asm
0x1800795e4  mov     [rsp-38h+arg_0], rbx
0x1800795e9  push    rbp
0x1800795ea  push    rsi
0x1800795eb  push    rdi
0x1800795ec  push    r12
0x1800795ee  push    r13
0x1800795f0  push    r14
0x1800795f2  push    r15
0x1800795f4  mov     rbp, rsp
0x1800795f7  sub     rsp, 40h
0x1800795fb  xor     esi, esi
0x1800795fd  lea     rax, [rbp+hFile]
0x180079601  mov     [rbp+NumberOfBytesRead], esi
0x180079604  mov     r12, r8
0x180079607  mov     qword ptr [rbp+FileSize], rsi
0x18007960b  mov     r13, rdx
0x18007960e  mov     [rdx], rsi
0x180079611  mov     [r8], rsi
0x180079614  mov     [rbp+hFile], rsi
0x180079618  mov     [rsp+40h+var_10], rax
0x18007961d  call    _DefCreateFile
0x180079622  mov     ebx, eax
0x180079624  test    eax, eax
0x180079626  js      loc_180079731
0x18007962c  mov     rdi, [rbp+hFile]
0x180079630  lea     rdx, [rbp+FileSize]; lpFileSize
0x180079634  mov     rcx, rdi; hFile
0x180079637  call    cs:__imp_GetFileSizeEx
0x18007963d  test    eax, eax
0x18007963f  jnz     short loc_18007965E
0x180079641  call    cs:__imp_GetLastError
0x180079647  mov     ebx, eax
0x180079649  test    eax, eax
0x18007964b  jle     short loc_180079656
0x18007964d  movzx   ebx, ax
0x180079650  or      ebx, 80070000h
0x180079656  test    ebx, ebx
0x180079658  js      loc_180079764
0x18007965e  mov     r14d, dword ptr [rbp+FileSize]
0x180079662  call    cs:__imp_GetProcessHeap
0x180079668  mov     r8d, r14d; dwBytes
0x18007966b  mov     edx, 8; dwFlags
0x180079670  mov     rcx, rax; hHeap
0x180079673  call    cs:__imp_HeapAlloc
0x180079679  mov     rsi, rax
0x18007967c  test    rax, rax
0x18007967f  jz      loc_18007970A
0x180079685  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180079689  mov     [rsp+40h+lpOverlapped], 0; int
0x180079692  mov     r8d, r14d; nNumberOfBytesToRead
0x180079695  mov     rdx, rax; lpBuffer
0x180079698  mov     rcx, rdi; hFile
0x18007969b  call    cs:__imp_ReadFile
0x1800796a1  test    eax, eax
0x1800796a3  jnz     loc_180079782
0x1800796a9  call    cs:__imp_GetLastError
0x1800796af  mov     ebx, eax
0x1800796b1  test    eax, eax
0x1800796b3  jle     short loc_1800796BE
0x1800796b5  movzx   ebx, ax
0x1800796b8  or      ebx, 80070000h
0x1800796be  test    ebx, ebx
0x1800796c0  jns     loc_180079782
0x1800796c6  mov     rcx, [rbp+38h]; this
0x1800796ca  lea     r8, aMinkernelMrtMr_43; "minkernel\\mrt\\mrm\\mrmmin\\basefile.c"...
0x1800796d1  mov     r9d, ebx; char *
0x1800796d4  mov     edx, 71h ; 'q'; void *
0x1800796d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800796de  mov     rcx, rsi; this
0x1800796e1  call    ?DefFreeMemory@Resources@Microsoft@@YAXPEAX@Z; Microsoft::Resources::DefFreeMemory(void *)
0x1800796e6  lea     rcx, [rdi-1]
0x1800796ea  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800796ee  jbe     short loc_180079759
0x1800796f0  mov     eax, ebx
0x1800796f2  mov     rbx, [rsp+40h+arg_0]
0x1800796fa  add     rsp, 40h
0x1800796fe  pop     r15
0x180079700  pop     r14
0x180079702  pop     r13
0x180079704  pop     r12
0x180079706  pop     rdi
0x180079707  pop     rsi
0x180079708  pop     rbp
0x180079709  retn
0x18007970a  mov     rcx, [rbp+38h]; this
0x18007970e  lea     r8, aMinkernelMrtMr_43; "minkernel\\mrt\\mrm\\mrmmin\\basefile.c"...
0x180079715  mov     ebx, 8007000Eh
0x18007971a  mov     edx, 6Fh ; 'o'; void *
0x18007971f  mov     r9d, ebx; char *
0x180079722  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079727  lea     rdx, [rdi-1]
0x18007972b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007972f  jmp     short loc_1800796EE
0x180079731  mov     rcx, [rbp+38h]; this
0x180079735  lea     r8, aMinkernelMrtMr_43; "minkernel\\mrt\\mrm\\mrmmin\\basefile.c"...
0x18007973c  mov     r9d, ebx; char *
0x18007973f  mov     edx, 69h ; 'i'; void *
0x180079744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079749  mov     rcx, [rbp+hFile]
0x18007974d  lea     rdx, [rcx-1]
0x180079751  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180079755  ja      short loc_1800796F0
0x180079757  jmp     short loc_18007975C
0x180079759  mov     rcx, rdi; hObject
0x18007975c  call    cs:__imp_CloseHandle
0x180079762  jmp     short loc_1800796F0
0x180079764  mov     rcx, [rbp+38h]; this
0x180079768  lea     r8, aMinkernelMrtMr_43; "minkernel\\mrt\\mrm\\mrmmin\\basefile.c"...
0x18007976f  mov     r9d, ebx; char *
0x180079772  mov     edx, 6Bh ; 'k'; void *
0x180079777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007977c  nop
0x18007977d  jmp     loc_1800C4CD0
0x180079782  cmp     [rbp+NumberOfBytesRead], r14d
0x180079786  jz      loc_1800C4CC6
0x18007978c  mov     rcx, [rbp+38h]; this
0x180079790  lea     r8, aMinkernelMrtMr_43; "minkernel\\mrt\\mrm\\mrmmin\\basefile.c"...
0x180079797  mov     ebx, 80073B16h
0x18007979c  mov     edx, 73h ; 's'; void *
0x1800797a1  mov     r9d, ebx; char *
0x1800797a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800797a9  mov     rcx, rsi; this
0x1800797ac  call    ?DefFreeMemory@Resources@Microsoft@@YAXPEAX@Z; Microsoft::Resources::DefFreeMemory(void *)
0x1800797b1  nop
0x1800797b2  jmp     loc_1800C4CD0
0x1800c4cc6  mov     [r13+0], r14
0x1800c4cca  xor     ebx, ebx
0x1800c4ccc  mov     [r12], rsi
0x1800c4cd0  lea     rcx, [rbp+hFile]
0x1800c4cd4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@Z$1?_DefCloseHandle@@YAX0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&_DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&_DefCloseHandle(void *)>>(void)
0x1800c4cd9  nop
0x1800c4cda  jmp     loc_1800796F0
```
