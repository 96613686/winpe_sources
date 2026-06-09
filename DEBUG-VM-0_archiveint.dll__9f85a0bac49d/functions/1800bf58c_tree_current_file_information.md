# tree_current_file_information

- ea: `0x1800bf58c`
- end: `0x1800bf647`
- name: `tree_current_file_information`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800be6bc`
- `0x1800bf6bc`

## callees

- `0x1800149c0`
- `0x1800bf58c`
- `0x1800bf690`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf60c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf60c`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bf624`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bf624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf5ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf5ff`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800bf5f0`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800bf5f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf62f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf62f`

## pseudocode

```c
__int64 __fastcall tree_current_file_information(__int64 a1, struct _BY_HANDLE_FILE_INFORMATION *a2, __int64 a3)
{
  int v5; // r9d
  __int64 v6; // rcx
  void *File2; // rax
  void *v8; // rdi
  DWORD LastError; // eax
  int v10; // ecx
  __int64 result; // rax
  unsigned int FileInformationByHandle; // ebx
  _DWORD v13[10]; // [rsp+30h] [rbp-28h] BYREF

  v5 = 0x2000000;
  memset(v13, 0, 32);
  if ( (_DWORD)a3 && (unsigned int)tree_current_is_physical_link(a1, a2, a3, 0x2000000) )
    v5 = 35651584;
  v6 = *(_QWORD *)(a1 + 640);
  v13[2] = v5;
  v13[0] = 32;
  File2 = (void *)CreateFile2(v6, 0, 7, 3, v13);
  v8 = File2;
  if ( File2 == (void *)-1LL )
  {
    LastError = GetLastError();
    _la_dosmaperr(LastError);
    v10 = *(_DWORD *)_o__errno();
    result = 0;
    *(_DWORD *)(a1 + 632) = v10;
  }
  else
  {
    FileInformationByHandle = GetFileInformationByHandle(File2, a2);
    CloseHandle(v8);
    return FileInformationByHandle;
  }
  return result;
}

```

## disassembly

```asm
0x1800bf58c  mov     rax, rsp
0x1800bf58f  mov     [rax+8], rbx
0x1800bf593  mov     [rax+10h], rsi
0x1800bf597  push    rdi
0x1800bf598  sub     rsp, 50h
0x1800bf59c  xorps   xmm0, xmm0
0x1800bf59f  mov     rsi, rdx
0x1800bf5a2  mov     rbx, rcx
0x1800bf5a5  mov     r9d, 2000000h
0x1800bf5ab  movups  xmmword ptr [rax-28h], xmm0
0x1800bf5af  movups  xmmword ptr [rax-18h], xmm0
0x1800bf5b3  test    r8d, r8d
0x1800bf5b6  jz      short loc_1800BF5C8
0x1800bf5b8  call    tree_current_is_physical_link
0x1800bf5bd  test    eax, eax
0x1800bf5bf  mov     ecx, 2200000h
0x1800bf5c4  cmovnz  r9d, ecx
0x1800bf5c8  mov     rcx, [rbx+280h]
0x1800bf5cf  lea     rax, [rsp+58h+var_28]
0x1800bf5d4  xor     edx, edx
0x1800bf5d6  mov     [rsp+58h+var_20], r9d
0x1800bf5db  mov     [rsp+58h+var_28], 20h ; ' '
0x1800bf5e3  mov     [rsp+58h+var_38], rax
0x1800bf5e8  lea     r9d, [rdx+3]
0x1800bf5ec  lea     r8d, [rdx+7]
0x1800bf5f0  call    cs:__imp_CreateFile2
0x1800bf5f6  mov     rdi, rax
0x1800bf5f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bf5fd  jnz     short loc_1800BF61E
0x1800bf5ff  call    cs:__imp_GetLastError
0x1800bf605  mov     ecx, eax
0x1800bf607  call    __la_dosmaperr
0x1800bf60c  call    cs:__imp__o__errno
0x1800bf612  mov     ecx, [rax]
0x1800bf614  xor     eax, eax
0x1800bf616  mov     [rbx+278h], ecx
0x1800bf61c  jmp     short loc_1800BF637
0x1800bf61e  mov     rdx, rsi; lpFileInformation
0x1800bf621  mov     rcx, rdi; hFile
0x1800bf624  call    cs:__imp_GetFileInformationByHandle
0x1800bf62a  mov     rcx, rdi; hObject
0x1800bf62d  mov     ebx, eax
0x1800bf62f  call    cs:__imp_CloseHandle
0x1800bf635  mov     eax, ebx
0x1800bf637  mov     rbx, [rsp+58h+arg_0]
0x1800bf63c  mov     rsi, [rsp+58h+arg_8]
0x1800bf641  add     rsp, 50h
0x1800bf645  pop     rdi
0x1800bf646  retn
```
