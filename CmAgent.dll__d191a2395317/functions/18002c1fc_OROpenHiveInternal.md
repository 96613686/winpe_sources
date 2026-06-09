# OROpenHiveInternal

- ea: `0x18002c1fc`
- end: `0x18002c3fd`
- name: `OROpenHiveInternal`
- size: `513`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ba38`

## callees

- `0x180002b28`
- `0x180002b34`
- `0x18002c164`
- `0x18002c1fc`
- `0x18002f124`
- `0x18002f9c4`
- `0x180030b90`
- `0x180030bd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c35b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c35b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c38a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c36c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c36c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002c287`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002c287`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c306`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c306`

## string_xrefs

- `0x18002c34f`: `ntdll.dll`
- `0x18002c380`: `RtlValidRelativeSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall OROpenHiveInternal(HANDLE hFile, __int64 a2, __int64 a3, __int64 a4)
{
  void *v4; // rsi
  char v5; // r14
  HANDLE v7; // rdi
  DWORD LastError; // ebx
  __int64 v9; // r8
  DWORD LowPart; // ebx
  void *v11; // rax
  __int64 v12; // r8
  HMODULE ModuleHandleW; // rax
  void *Block; // [rsp+60h] [rbp+30h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+68h] [rbp+38h] BYREF
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+40h] BYREF

  Block = hFile;
  v4 = 0;
  NumberOfBytesRead = 0;
  v5 = 0;
  FileSize.QuadPart = 0;
  *(_QWORD *)a4 = 0;
  v7 = hFile;
  if ( !hFile )
  {
    LastError = 87;
    goto LABEL_26;
  }
  LastError = ORStart();
  if ( !LastError )
  {
    if ( !v7 )
    {
      LastError = ORCreateFile(0, LastError + 1, v9, 1, &Block);
      if ( LastError )
      {
        v7 = Block;
        goto LABEL_26;
      }
      v5 = 1;
      v7 = Block;
    }
    if ( GetFileSizeEx(v7, &FileSize) || (LastError = GetLastError()) == 0 )
    {
      LowPart = FileSize.LowPart;
      if ( FileSize.LowPart <= 0x1000 || FileSize.HighPart )
      {
        LastError = 1009;
        goto LABEL_26;
      }
      v11 = o__aligned_malloc_0(FileSize.LowPart, 0x10u);
      Block = v11;
      v4 = v11;
      if ( !v11 )
      {
        LastError = 8;
        goto LABEL_26;
      }
      if ( ReadFile(v7, v11, LowPart, &NumberOfBytesRead, 0) || (LastError = GetLastError()) == 0 )
      {
        LastError = ValidateHiveAndRecoverFromLog(&Block, &FileSize, v12, v7);
        if ( !LastError )
        {
          if ( v5 )
            ORCloseFile(v7);
          v7 = 0;
          v5 = 0;
          ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
          if ( ModuleHandleW )
          {
            ORValidRelativeSecurityDescriptor = (__int64)GetProcAddress(
                                                           ModuleHandleW,
                                                           "RtlValidRelativeSecurityDescriptor");
            if ( ORValidRelativeSecurityDescriptor )
            {
              v4 = 0;
              LastError = OROpenHiveFromMemoryInternal(Block);
              if ( !LastError )
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a4 + 16LL) + 128LL) = 0;
              goto LABEL_26;
            }
          }
          LastError = GetLastError();
        }
        v4 = Block;
      }
    }
  }
LABEL_26:
  if ( v4 )
    aligned_free(v4);
  if ( v5 )
    ORCloseFile(v7);
  return LastError;
}

```

## disassembly

```asm
0x18002c1fc  mov     rax, rsp
0x18002c1ff  mov     [rax+20h], rbx
0x18002c203  mov     [rax+18h], r8d
0x18002c207  mov     [rax+10h], rdx
0x18002c20b  mov     [rax+8], rcx
0x18002c20f  push    rbp
0x18002c210  push    rsi
0x18002c211  push    rdi
0x18002c212  push    r14
0x18002c214  push    r15
0x18002c216  mov     rbp, rsp
0x18002c219  sub     rsp, 30h
0x18002c21d  xor     esi, esi
0x18002c21f  mov     [rbp+NumberOfBytesRead], 0
0x18002c226  xor     r14b, r14b
0x18002c229  mov     qword ptr [rbp+FileSize], 0
0x18002c231  mov     [r9], rsi
0x18002c234  mov     r15, r9
0x18002c237  mov     rdi, rcx
0x18002c23a  test    rcx, rcx
0x18002c23d  jnz     short loc_18002C247
0x18002c23f  lea     ebx, [rcx+57h]
0x18002c242  jmp     loc_18002C3CF
0x18002c247  call    ORStart
0x18002c24c  mov     ebx, eax
0x18002c24e  test    eax, eax
0x18002c250  jnz     loc_18002C3CF
0x18002c256  test    rdi, rdi
0x18002c259  jnz     short loc_18002C280
0x18002c25b  lea     edi, [rbx+1]
0x18002c25e  xor     ecx, ecx
0x18002c260  lea     rax, [rbp+Block]
0x18002c264  mov     r9d, edi
0x18002c267  mov     edx, edi
0x18002c269  mov     [rsp+30h+lpOverlapped], rax
0x18002c26e  call    ORCreateFile
0x18002c273  mov     ebx, eax
0x18002c275  test    eax, eax
0x18002c277  jnz     short loc_18002C2E7
0x18002c279  mov     r14b, dil
0x18002c27c  mov     rdi, [rbp+Block]
0x18002c280  lea     rdx, [rbp+FileSize]; lpFileSize
0x18002c284  mov     rcx, rdi; hFile
0x18002c287  call    cs:__imp_GetFileSizeEx
0x18002c28e  nop     dword ptr [rax+rax+00h]
0x18002c293  test    eax, eax
0x18002c295  jnz     short loc_18002C2AD
0x18002c297  call    cs:__imp_GetLastError
0x18002c29e  nop     dword ptr [rax+rax+00h]
0x18002c2a3  mov     ebx, eax
0x18002c2a5  test    eax, eax
0x18002c2a7  jnz     loc_18002C3CF
0x18002c2ad  mov     rbx, qword ptr [rbp+FileSize]
0x18002c2b1  cmp     ebx, 1000h
0x18002c2b7  jbe     loc_18002C3CA
0x18002c2bd  cmp     dword ptr [rbp+FileSize+4], esi
0x18002c2c0  jnz     loc_18002C3CA
0x18002c2c6  mov     edx, 10h; Alignment
0x18002c2cb  mov     rcx, rbx; Size
0x18002c2ce  call    _o__aligned_malloc_0
0x18002c2d3  mov     [rbp+Block], rax
0x18002c2d7  mov     rsi, rax
0x18002c2da  test    rax, rax
0x18002c2dd  jnz     short loc_18002C2F0
0x18002c2df  lea     ebx, [rax+8]
0x18002c2e2  jmp     loc_18002C3CF
0x18002c2e7  mov     rdi, [rbp+Block]
0x18002c2eb  jmp     loc_18002C3CF
0x18002c2f0  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002c2f4  mov     [rsp+30h+lpOverlapped], 0; lpOverlapped
0x18002c2fd  mov     r8d, ebx; nNumberOfBytesToRead
0x18002c300  mov     rdx, rax; lpBuffer
0x18002c303  mov     rcx, rdi; hFile
0x18002c306  call    cs:__imp_ReadFile
0x18002c30d  nop     dword ptr [rax+rax+00h]
0x18002c312  test    eax, eax
0x18002c314  jnz     short loc_18002C32C
0x18002c316  call    cs:__imp_GetLastError
0x18002c31d  nop     dword ptr [rax+rax+00h]
0x18002c322  mov     ebx, eax
0x18002c324  test    eax, eax
0x18002c326  jnz     loc_18002C3CF
0x18002c32c  mov     r9, rdi
0x18002c32f  lea     rdx, [rbp+FileSize]
0x18002c333  lea     rcx, [rbp+Block]
0x18002c337  call    ValidateHiveAndRecoverFromLog
0x18002c33c  mov     ebx, eax
0x18002c33e  test    eax, eax
0x18002c340  jnz     short loc_18002C37A
0x18002c342  test    r14b, r14b
0x18002c345  jz      short loc_18002C34F
0x18002c347  mov     rcx, rdi
0x18002c34a  call    ORCloseFile
0x18002c34f  lea     rcx, ModuleName; "ntdll.dll"
0x18002c356  xor     edi, edi
0x18002c358  xor     r14b, r14b
0x18002c35b  call    cs:__imp_GetModuleHandleW
0x18002c362  nop     dword ptr [rax+rax+00h]
0x18002c367  test    rax, rax
0x18002c36a  jnz     short loc_18002C380
0x18002c36c  call    cs:__imp_GetLastError
0x18002c373  nop     dword ptr [rax+rax+00h]
0x18002c378  mov     ebx, eax
0x18002c37a  mov     rsi, [rbp+Block]
0x18002c37e  jmp     short loc_18002C3CF
0x18002c380  lea     rdx, aRtlvalidrelati; "RtlValidRelativeSecurityDescriptor"
0x18002c387  mov     rcx, rax; hModule
0x18002c38a  call    cs:__imp_GetProcAddress
0x18002c391  nop     dword ptr [rax+rax+00h]
0x18002c396  mov     cs:ORValidRelativeSecurityDescriptor, rax
0x18002c39d  test    rax, rax
0x18002c3a0  jz      short loc_18002C36C
0x18002c3a2  mov     rdx, qword ptr [rbp+FileSize]
0x18002c3a6  mov     r9, r15
0x18002c3a9  mov     rcx, [rbp+Block]; Block
0x18002c3ad  call    OROpenHiveFromMemoryInternal
0x18002c3b2  xor     esi, esi
0x18002c3b4  mov     ebx, eax
0x18002c3b6  test    eax, eax
0x18002c3b8  jnz     short loc_18002C3CF
0x18002c3ba  mov     rax, [r15]
0x18002c3bd  mov     rcx, [rax+10h]
0x18002c3c1  mov     [rcx+80h], rsi
0x18002c3c8  jmp     short loc_18002C3CF
0x18002c3ca  mov     ebx, 3F1h
0x18002c3cf  test    rsi, rsi
0x18002c3d2  jz      short loc_18002C3DC
0x18002c3d4  mov     rcx, rsi; Block
0x18002c3d7  call    _aligned_free
0x18002c3dc  test    r14b, r14b
0x18002c3df  jz      short loc_18002C3E9
0x18002c3e1  mov     rcx, rdi
0x18002c3e4  call    ORCloseFile
0x18002c3e9  mov     eax, ebx
0x18002c3eb  mov     rbx, [rsp+30h+arg_18]
0x18002c3f0  add     rsp, 30h
0x18002c3f4  pop     r15
0x18002c3f6  pop     r14
0x18002c3f8  pop     rdi
0x18002c3f9  pop     rsi
0x18002c3fa  pop     rbp
0x18002c3fb  retn
```
