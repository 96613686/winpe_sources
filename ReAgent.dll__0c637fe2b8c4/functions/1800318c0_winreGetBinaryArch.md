# winreGetBinaryArch

- ea: `0x1800318c0`
- end: `0x1800319f8`
- name: `winreGetBinaryArch`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x180030770`
- `0x180031a7c`

## callees

- `0x1800318c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003190b`
- `KERNEL32!GetLastError` at `0x180031943`
- `KERNEL32!GetLastError` at `0x180031971`
- `KERNEL32!GetLastError` at `0x18003198c`
- `KERNEL32!GetLastError` at `0x18003190b`
- `KERNEL32!GetLastError` at `0x180031943`
- `KERNEL32!GetLastError` at `0x180031971`
- `KERNEL32!GetLastError` at `0x18003198c`
- `KERNEL32!SetLastError` at `0x1800319da`
- `KERNEL32!SetLastError` at `0x1800319da`
- `KERNEL32!CreateFileW` at `0x1800318fc`
- `KERNEL32!CreateFileW` at `0x1800318fc`
- `KERNEL32!CloseHandle` at `0x1800319c0`
- `KERNEL32!CloseHandle` at `0x1800319ce`
- `KERNEL32!CloseHandle` at `0x1800319c0`
- `KERNEL32!CloseHandle` at `0x1800319ce`
- `KERNEL32!CreateFileMappingW` at `0x180031935`
- `KERNEL32!CreateFileMappingW` at `0x180031935`
- `KERNEL32!MapViewOfFile` at `0x180031963`
- `KERNEL32!MapViewOfFile` at `0x180031963`
- `KERNEL32!UnmapViewOfFile` at `0x1800319b1`
- `KERNEL32!UnmapViewOfFile` at `0x1800319b1`
- `imagehlp!ImageNtHeader` at `0x18003197e`
- `imagehlp!ImageNtHeader` at `0x18003197e`

## pseudocode

```c
__int64 __fastcall winreGetBinaryArch(const WCHAR *a1, _DWORD *a2, _DWORD *a3, _DWORD *a4)
{
  HANDLE FileW; // rax
  void *v8; // rsi
  DWORD LastError; // ebx
  HANDLE FileMappingW; // rax
  void *v11; // rdi
  void *v12; // rax
  const void *v13; // rbp
  PIMAGE_NT_HEADERS v14; // rax

  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    v11 = FileMappingW;
    if ( FileMappingW )
    {
      v12 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v13 = v12;
      if ( v12 )
      {
        v14 = ImageNtHeader(v12);
        if ( v14 )
        {
          LastError = 0;
          *a2 = v14->FileHeader.Machine;
          *a3 = v14->OptionalHeader.MajorImageVersion;
          *a4 = v14->OptionalHeader.MinorImageVersion;
        }
        else
        {
          LastError = GetLastError();
        }
        UnmapViewOfFile(v13);
      }
      else
      {
        LastError = GetLastError();
      }
      if ( v11 != (void *)-1LL )
        CloseHandle(v11);
    }
    else
    {
      LastError = GetLastError();
    }
    if ( v8 )
      CloseHandle(v8);
  }
  if ( !LastError )
    return 1;
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x1800318c0  push    rbx
0x1800318c2  push    rbp
0x1800318c3  push    rsi
0x1800318c4  push    rdi
0x1800318c5  push    r12
0x1800318c7  push    r14
0x1800318c9  push    r15
0x1800318cb  sub     rsp, 40h
0x1800318cf  mov     r15, r8
0x1800318d2  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800318db  mov     r8d, 3; dwShareMode
0x1800318e1  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800318e9  mov     r14, r9
0x1800318ec  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800318f1  mov     r12, rdx
0x1800318f4  xor     r9d, r9d; lpSecurityAttributes
0x1800318f7  mov     edx, 80000000h; dwDesiredAccess
0x1800318fc  call    cs:__imp_CreateFileW
0x180031902  mov     rsi, rax
0x180031905  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031909  jnz     short loc_180031918
0x18003190b  call    cs:__imp_GetLastError
0x180031911  mov     ebx, eax
0x180031913  jmp     loc_1800319D4
0x180031918  xor     r9d, r9d; dwMaximumSizeHigh
0x18003191b  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpName
0x180031924  xor     edx, edx; lpFileMappingAttributes
0x180031926  mov     [rsp+78h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18003192e  mov     rcx, rsi; hFile
0x180031931  lea     r8d, [r9+2]; flProtect
0x180031935  call    cs:__imp_CreateFileMappingW
0x18003193b  mov     rdi, rax
0x18003193e  test    rax, rax
0x180031941  jnz     short loc_18003194D
0x180031943  call    cs:__imp_GetLastError
0x180031949  mov     ebx, eax
0x18003194b  jmp     short loc_1800319C6
0x18003194d  xor     r9d, r9d; dwFileOffsetLow
0x180031950  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180031959  xor     r8d, r8d; dwFileOffsetHigh
0x18003195c  mov     rcx, rdi; hFileMappingObject
0x18003195f  lea     edx, [r9+4]; dwDesiredAccess
0x180031963  call    cs:__imp_MapViewOfFile
0x180031969  mov     rbp, rax
0x18003196c  test    rax, rax
0x18003196f  jnz     short loc_18003197B
0x180031971  call    cs:__imp_GetLastError
0x180031977  mov     ebx, eax
0x180031979  jmp     short loc_1800319B7
0x18003197b  mov     rcx, rbp; Base
0x18003197e  call    cs:__imp_ImageNtHeader
0x180031984  mov     rcx, rax
0x180031987  test    rax, rax
0x18003198a  jnz     short loc_180031996
0x18003198c  call    cs:__imp_GetLastError
0x180031992  mov     ebx, eax
0x180031994  jmp     short loc_1800319AE
0x180031996  movzx   eax, word ptr [rax+4]
0x18003199a  xor     ebx, ebx
0x18003199c  mov     [r12], eax
0x1800319a0  movzx   eax, word ptr [rcx+44h]
0x1800319a4  mov     [r15], eax
0x1800319a7  movzx   eax, word ptr [rcx+46h]
0x1800319ab  mov     [r14], eax
0x1800319ae  mov     rcx, rbp; lpBaseAddress
0x1800319b1  call    cs:__imp_UnmapViewOfFile
0x1800319b7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800319bb  jz      short loc_1800319C6
0x1800319bd  mov     rcx, rdi; hObject
0x1800319c0  call    cs:__imp_CloseHandle
0x1800319c6  test    rsi, rsi
0x1800319c9  jz      short loc_1800319D4
0x1800319cb  mov     rcx, rsi; hObject
0x1800319ce  call    cs:__imp_CloseHandle
0x1800319d4  test    ebx, ebx
0x1800319d6  jz      short loc_1800319E4
0x1800319d8  mov     ecx, ebx; dwErrCode
0x1800319da  call    cs:__imp_SetLastError
0x1800319e0  xor     eax, eax
0x1800319e2  jmp     short loc_1800319E9
0x1800319e4  mov     eax, 1
0x1800319e9  add     rsp, 40h
0x1800319ed  pop     r15
0x1800319ef  pop     r14
0x1800319f1  pop     r12
0x1800319f3  pop     rdi
0x1800319f4  pop     rsi
0x1800319f5  pop     rbp
0x1800319f6  pop     rbx
0x1800319f7  retn
```
