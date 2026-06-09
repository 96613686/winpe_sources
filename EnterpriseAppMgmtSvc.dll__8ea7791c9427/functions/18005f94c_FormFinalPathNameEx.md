# FormFinalPathNameEx

- ea: `0x18005f94c`
- end: `0x18005f9f0`
- name: `FormFinalPathNameEx`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x1800612f0`

## callees

- `0x18005f864`
- `0x18005f94c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f9be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f9be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f9c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f9d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f9c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f9d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f9b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f9b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f985`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f985`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameEx(const WCHAR *a1)
{
  char *FileW; // rax
  char *v2; // rsi
  DWORD LastError; // ebx
  WCHAR *v4; // rdi

  if ( a1 && *a1 )
  {
    FileW = (char *)CreateFileW(a1, 0, 7u, 0, 3u, 0x2200000u, 0);
    v2 = FileW;
    if ( FileW == (char *)-1LL )
    {
      v4 = 0;
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
      v4 = FormFinalPathNameByHandle(FileW, 1);
      if ( !v4 )
        LastError = GetLastError();
      CloseHandle(v2);
    }
    SetLastError(LastError);
    return v4;
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
0x18005f94c  mov     [rsp+arg_0], rbx
0x18005f951  mov     [rsp+arg_8], rsi
0x18005f956  push    rdi
0x18005f957  sub     rsp, 40h
0x18005f95b  test    rcx, rcx
0x18005f95e  jz      short loc_18005F9D3
0x18005f960  xor     eax, eax
0x18005f962  cmp     ax, [rcx]
0x18005f965  jz      short loc_18005F9D3
0x18005f967  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x18005f96c  lea     r8d, [rax+7]; dwShareMode
0x18005f970  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18005f978  xor     r9d, r9d; lpSecurityAttributes
0x18005f97b  xor     edx, edx; dwDesiredAccess
0x18005f97d  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18005f985  call    cs:__imp_CreateFileW
0x18005f98b  mov     rsi, rax
0x18005f98e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005f992  jz      short loc_18005F9BC
0x18005f994  xor     ebx, ebx
0x18005f996  mov     rcx, rax; hFile
0x18005f999  lea     edx, [rbx+1]
0x18005f99c  call    FormFinalPathNameByHandle
0x18005f9a1  mov     rdi, rax
0x18005f9a4  test    rax, rax
0x18005f9a7  jnz     short loc_18005F9B1
0x18005f9a9  call    cs:__imp_GetLastError
0x18005f9af  mov     ebx, eax
0x18005f9b1  mov     rcx, rsi; hObject
0x18005f9b4  call    cs:__imp_CloseHandle
0x18005f9ba  jmp     short loc_18005F9C6
0x18005f9bc  xor     edi, edi
0x18005f9be  call    cs:__imp_GetLastError
0x18005f9c4  mov     ebx, eax
0x18005f9c6  mov     ecx, ebx; dwErrCode
0x18005f9c8  call    cs:__imp_SetLastError
0x18005f9ce  mov     rax, rdi
0x18005f9d1  jmp     short loc_18005F9E0
0x18005f9d3  mov     ecx, 57h ; 'W'; dwErrCode
0x18005f9d8  call    cs:__imp_SetLastError
0x18005f9de  xor     eax, eax
0x18005f9e0  mov     rbx, [rsp+48h+arg_0]
0x18005f9e5  mov     rsi, [rsp+48h+arg_8]
0x18005f9ea  add     rsp, 40h
0x18005f9ee  pop     rdi
0x18005f9ef  retn
```
