# FormFinalPathNameEx

- ea: `0x18003cd7c`
- end: `0x18003ce29`
- name: `FormFinalPathNameEx`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x180035878`
- `0x18003bfb0`
- `0x18004acc8`

## callees

- `0x18003cc94`
- `0x18003cd7c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cdbf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003cdbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ce01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ce11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ce01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ce11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cde2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cdf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cde2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cdf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cded`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cded`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameEx(const WCHAR *a1, int a2)
{
  char *FileW; // rax
  char *v4; // rsi
  DWORD LastError; // ebx
  WCHAR *v6; // rdi

  if ( a1 && *a1 && (a2 & 0xFFFFFFF8) == 0 )
  {
    FileW = (char *)CreateFileW(a1, 0, 7u, 0, 3u, 0x2200000u, 0);
    v4 = FileW;
    if ( FileW == (char *)-1LL )
    {
      v6 = 0;
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
      v6 = FormFinalPathNameByHandle(FileW, a2);
      if ( !v6 )
        LastError = GetLastError();
      CloseHandle(v4);
    }
    SetLastError(LastError);
    return v6;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18003cd7c  mov     [rsp+arg_0], rbx
0x18003cd81  mov     [rsp+arg_8], rsi
0x18003cd86  push    rdi
0x18003cd87  sub     rsp, 40h
0x18003cd8b  mov     edi, edx
0x18003cd8d  test    rcx, rcx
0x18003cd90  jz      short loc_18003CE0C
0x18003cd92  xor     eax, eax
0x18003cd94  cmp     ax, [rcx]
0x18003cd97  jz      short loc_18003CE0C
0x18003cd99  test    edx, 0FFFFFFF8h
0x18003cd9f  jnz     short loc_18003CE0C
0x18003cda1  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x18003cda6  lea     r8d, [rax+7]; dwShareMode
0x18003cdaa  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003cdb2  xor     r9d, r9d; lpSecurityAttributes
0x18003cdb5  xor     edx, edx; dwDesiredAccess
0x18003cdb7  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18003cdbf  call    cs:__imp_CreateFileW
0x18003cdc5  mov     rsi, rax
0x18003cdc8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003cdcc  jz      short loc_18003CDF5
0x18003cdce  mov     edx, edi
0x18003cdd0  mov     rcx, rax; hFile
0x18003cdd3  xor     ebx, ebx
0x18003cdd5  call    FormFinalPathNameByHandle
0x18003cdda  mov     rdi, rax
0x18003cddd  test    rax, rax
0x18003cde0  jnz     short loc_18003CDEA
0x18003cde2  call    cs:__imp_GetLastError
0x18003cde8  mov     ebx, eax
0x18003cdea  mov     rcx, rsi; hObject
0x18003cded  call    cs:__imp_CloseHandle
0x18003cdf3  jmp     short loc_18003CDFF
0x18003cdf5  xor     edi, edi
0x18003cdf7  call    cs:__imp_GetLastError
0x18003cdfd  mov     ebx, eax
0x18003cdff  mov     ecx, ebx; dwErrCode
0x18003ce01  call    cs:__imp_SetLastError
0x18003ce07  mov     rax, rdi
0x18003ce0a  jmp     short loc_18003CE19
0x18003ce0c  mov     ecx, 57h ; 'W'; dwErrCode
0x18003ce11  call    cs:__imp_SetLastError
0x18003ce17  xor     eax, eax
0x18003ce19  mov     rbx, [rsp+48h+arg_0]
0x18003ce1e  mov     rsi, [rsp+48h+arg_8]
0x18003ce23  add     rsp, 40h
0x18003ce27  pop     rdi
0x18003ce28  retn
```
