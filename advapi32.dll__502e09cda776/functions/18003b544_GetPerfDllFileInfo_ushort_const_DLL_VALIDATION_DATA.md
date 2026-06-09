# GetPerfDllFileInfo(ushort const *,DLL_VALIDATION_DATA *)

- ea: `0x18003b544`
- end: `0x18003b65b`
- name: `?GetPerfDllFileInfo@@YAJPEBGPEAUDLL_VALIDATION_DATA@@@Z`
- size: `279`
- prototype: `int(const unsigned __int16 *, struct DLL_VALIDATION_DATA *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18003d248`

## callees

- `0x18003b544`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003b620`
- `KERNEL32!GetLastError` at `0x18003b63f`
- `KERNEL32!GetLastError` at `0x18003b620`
- `KERNEL32!GetLastError` at `0x18003b63f`
- `KERNEL32!CloseHandle` at `0x18003b631`
- `KERNEL32!CloseHandle` at `0x18003b631`
- `KERNEL32!CreateFileW` at `0x18003b57d`
- `KERNEL32!CreateFileW` at `0x18003b57d`
- `KERNEL32!GetFileSize` at `0x18003b5fe`
- `KERNEL32!GetFileSize` at `0x18003b5fe`
- `KERNEL32!DosDateTimeToFileTime` at `0x18003b5ea`
- `KERNEL32!DosDateTimeToFileTime` at `0x18003b5ea`
- `KERNEL32!FileTimeToDosDateTime` at `0x18003b5cd`
- `KERNEL32!FileTimeToDosDateTime` at `0x18003b5cd`
- `KERNEL32!GetFileTime` at `0x18003b5a2`
- `KERNEL32!GetFileTime` at `0x18003b5a2`

## pseudocode

```c
__int64 __fastcall GetPerfDllFileInfo(const unsigned __int16 *a1, FILETIME *a2)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  DWORD LastError; // ebx
  FILETIME FileSizeHigh; // [rsp+40h] [rbp-18h] BYREF
  WORD FatTime; // [rsp+70h] [rbp+18h] BYREF
  WORD FatDate; // [rsp+78h] [rbp+20h] BYREF

  FileSizeHigh.dwHighDateTime = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    if ( !GetFileTime(FileW, a2, 0, 0) )
      goto LABEL_7;
    FatDate = 0;
    FatTime = 0;
    if ( FileTimeToDosDateTime(a2, &FatDate, &FatTime) )
      DosDateTimeToFileTime(FatDate, FatTime, a2);
    FileSizeHigh.dwLowDateTime = GetFileSize(v4, &FileSizeHigh.dwHighDateTime);
    if ( FileSizeHigh.dwLowDateTime == -1 )
    {
LABEL_7:
      LastError = GetLastError();
    }
    else
    {
      a2[1] = FileSizeHigh;
      LastError = 0;
    }
    CloseHandle(v4);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003b544  mov     rax, rsp
0x18003b547  mov     [rax+8], rbx
0x18003b54b  push    rdi
0x18003b54c  sub     rsp, 50h
0x18003b550  mov     qword ptr [rax-28h], 0
0x18003b558  xor     r9d, r9d; lpSecurityAttributes
0x18003b55b  mov     rbx, rdx
0x18003b55e  mov     dword ptr [rax-30h], 80h
0x18003b565  mov     edx, 80000000h; dwDesiredAccess
0x18003b56a  mov     qword ptr [rax-18h], 0
0x18003b572  mov     dword ptr [rax-38h], 3
0x18003b579  lea     r8d, [r9+1]; dwShareMode
0x18003b57d  call    cs:__imp_CreateFileW
0x18003b584  nop     dword ptr [rax+rax+00h]
0x18003b589  mov     rdi, rax
0x18003b58c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b590  jz      loc_18003B63F
0x18003b596  xor     r9d, r9d; lpLastWriteTime
0x18003b599  xor     r8d, r8d; lpLastAccessTime
0x18003b59c  mov     rdx, rbx; lpCreationTime
0x18003b59f  mov     rcx, rax; hFile
0x18003b5a2  call    cs:__imp_GetFileTime
0x18003b5a9  nop     dword ptr [rax+rax+00h]
0x18003b5ae  test    eax, eax
0x18003b5b0  jz      short loc_18003B620
0x18003b5b2  xor     ecx, ecx
0x18003b5b4  lea     r8, [rsp+58h+FatTime]; lpFatTime
0x18003b5b9  mov     [rsp+58h+FatDate], cx
0x18003b5be  lea     rdx, [rsp+58h+FatDate]; lpFatDate
0x18003b5c3  xor     eax, eax
0x18003b5c5  mov     rcx, rbx; lpFileTime
0x18003b5c8  mov     [rsp+58h+FatTime], ax
0x18003b5cd  call    cs:__imp_FileTimeToDosDateTime
0x18003b5d4  nop     dword ptr [rax+rax+00h]
0x18003b5d9  test    eax, eax
0x18003b5db  jz      short loc_18003B5F6
0x18003b5dd  movzx   edx, [rsp+58h+FatTime]; wFatTime
0x18003b5e2  mov     r8, rbx; lpFileTime
0x18003b5e5  movzx   ecx, [rsp+58h+FatDate]; wFatDate
0x18003b5ea  call    cs:__imp_DosDateTimeToFileTime
0x18003b5f1  nop     dword ptr [rax+rax+00h]
0x18003b5f6  lea     rdx, [rsp+58h+FileSizeHigh.dwHighDateTime]; lpFileSizeHigh
0x18003b5fb  mov     rcx, rdi; hFile
0x18003b5fe  call    cs:__imp_GetFileSize
0x18003b605  nop     dword ptr [rax+rax+00h]
0x18003b60a  mov     [rsp+58h+FileSizeHigh.dwLowDateTime], eax
0x18003b60e  cmp     eax, 0FFFFFFFFh
0x18003b611  jz      short loc_18003B620
0x18003b613  mov     rax, qword ptr [rsp+58h+FileSizeHigh.dwLowDateTime]
0x18003b618  mov     [rbx+8], rax
0x18003b61c  xor     ebx, ebx
0x18003b61e  jmp     short loc_18003B62E
0x18003b620  call    cs:__imp_GetLastError
0x18003b627  nop     dword ptr [rax+rax+00h]
0x18003b62c  mov     ebx, eax
0x18003b62e  mov     rcx, rdi; hObject
0x18003b631  call    cs:__imp_CloseHandle
0x18003b638  nop     dword ptr [rax+rax+00h]
0x18003b63d  jmp     short loc_18003B64D
0x18003b63f  call    cs:__imp_GetLastError
0x18003b646  nop     dword ptr [rax+rax+00h]
0x18003b64b  mov     ebx, eax
0x18003b64d  mov     eax, ebx
0x18003b64f  mov     rbx, [rsp+58h+arg_0]
0x18003b654  add     rsp, 50h
0x18003b658  pop     rdi
0x18003b659  retn
```
