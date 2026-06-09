# FormFinalPathNameEx

- ea: `0x1800649a4`
- end: `0x180064a75`
- name: `FormFinalPathNameEx`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x1800666b4`

## callees

- `0x180064890`
- `0x1800649a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064a40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064a56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064a40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064a56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a20`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800649e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800649e5`

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
0x1800649a4  mov     [rsp+arg_0], rbx
0x1800649a9  mov     [rsp+arg_8], rsi
0x1800649ae  push    rdi
0x1800649af  sub     rsp, 40h
0x1800649b3  test    rcx, rcx
0x1800649b6  jz      loc_180064A51
0x1800649bc  xor     eax, eax
0x1800649be  cmp     ax, [rcx]
0x1800649c1  jz      loc_180064A51
0x1800649c7  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x1800649cc  lea     r8d, [rax+7]; dwShareMode
0x1800649d0  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800649d8  xor     r9d, r9d; lpSecurityAttributes
0x1800649db  xor     edx, edx; dwDesiredAccess
0x1800649dd  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800649e5  call    cs:__imp_CreateFileW
0x1800649ec  nop     dword ptr [rax+rax+00h]
0x1800649f1  mov     rsi, rax
0x1800649f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800649f8  jz      short loc_180064A2E
0x1800649fa  xor     ebx, ebx
0x1800649fc  mov     rcx, rax; hFile
0x1800649ff  lea     edx, [rbx+1]
0x180064a02  call    FormFinalPathNameByHandle
0x180064a07  mov     rdi, rax
0x180064a0a  test    rax, rax
0x180064a0d  jnz     short loc_180064A1D
0x180064a0f  call    cs:__imp_GetLastError
0x180064a16  nop     dword ptr [rax+rax+00h]
0x180064a1b  mov     ebx, eax
0x180064a1d  mov     rcx, rsi; hObject
0x180064a20  call    cs:__imp_CloseHandle
0x180064a27  nop     dword ptr [rax+rax+00h]
0x180064a2c  jmp     short loc_180064A3E
0x180064a2e  xor     edi, edi
0x180064a30  call    cs:__imp_GetLastError
0x180064a37  nop     dword ptr [rax+rax+00h]
0x180064a3c  mov     ebx, eax
0x180064a3e  mov     ecx, ebx; dwErrCode
0x180064a40  call    cs:__imp_SetLastError
0x180064a47  nop     dword ptr [rax+rax+00h]
0x180064a4c  mov     rax, rdi
0x180064a4f  jmp     short loc_180064A64
0x180064a51  mov     ecx, 57h ; 'W'; dwErrCode
0x180064a56  call    cs:__imp_SetLastError
0x180064a5d  nop     dword ptr [rax+rax+00h]
0x180064a62  xor     eax, eax
0x180064a64  mov     rbx, [rsp+48h+arg_0]
0x180064a69  mov     rsi, [rsp+48h+arg_8]
0x180064a6e  add     rsp, 40h
0x180064a72  pop     rdi
0x180064a73  retn
```
