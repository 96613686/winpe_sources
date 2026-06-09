# SetFilePathFullControlByTrustedAC(ushort const *,bool,ushort const *)

- ea: `0x180020678`
- end: `0x180020729`
- name: `?SetFilePathFullControlByTrustedAC@@YAJPEBG_N0@Z`
- size: `177`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000bc20`

## callees

- `0x180020678`
- `0x180020730`
- `0x1800209fc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020700`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800206af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800206af`

## pseudocode

```c
__int64 __fastcall SetFilePathFullControlByTrustedAC(const unsigned __int16 *a1, char a2, const unsigned __int16 *a3)
{
  __int64 v5; // rcx
  HANDLE FileW; // rdi
  int LastError; // ebx
  bool v9; // [rsp+20h] [rbp-28h]
  void *v10; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(a1, 0xE0000u, 0, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    v10 = 0;
    LOBYTE(v5) = a2;
    LastError = SetTrustedACSid(v5, a3, &v10);
    if ( !LastError )
      LastError = SetHandleAccessWithInheritance(FileW, SE_FILE_OBJECT, v10, 0x1F01FFu, v9);
    CloseHandle(FileW);
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180020678  mov     rax, rsp
0x18002067b  mov     [rax+8], rbx
0x18002067f  mov     [rax+10h], rsi
0x180020683  push    rdi
0x180020684  sub     rsp, 40h
0x180020688  mov     qword ptr [rax-18h], 0
0x180020690  mov     rbx, r8
0x180020693  mov     sil, dl
0x180020696  mov     dword ptr [rax-20h], 2000000h
0x18002069d  xor     r8d, r8d; dwShareMode
0x1800206a0  mov     dword ptr [rax-28h], 3
0x1800206a7  mov     edx, 0E0000h; dwDesiredAccess
0x1800206ac  xor     r9d, r9d; lpSecurityAttributes
0x1800206af  call    cs:__imp_CreateFileW
0x1800206b5  mov     rdi, rax
0x1800206b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800206bc  jz      short loc_180020700
0x1800206be  lea     r8, [rsp+48h+arg_18]
0x1800206c3  mov     [rsp+48h+arg_18], 0
0x1800206cc  mov     rdx, rbx
0x1800206cf  mov     cl, sil
0x1800206d2  call    _SetTrustedACSid
0x1800206d7  mov     ebx, eax
0x1800206d9  test    eax, eax
0x1800206db  jnz     short loc_1800206F5
0x1800206dd  mov     r8, [rsp+48h+arg_18]; void *
0x1800206e2  lea     edx, [rax+1]; ObjectType
0x1800206e5  mov     r9d, 1F01FFh; unsigned int
0x1800206eb  mov     rcx, rdi; handle
0x1800206ee  call    SetHandleAccessWithInheritance
0x1800206f3  mov     ebx, eax
0x1800206f5  mov     rcx, rdi; hObject
0x1800206f8  call    cs:__imp_CloseHandle
0x1800206fe  jmp     short loc_180020708
0x180020700  call    cs:__imp_GetLastError
0x180020706  mov     ebx, eax
0x180020708  test    ebx, ebx
0x18002070a  jz      short loc_180020717
0x18002070c  jle     short loc_180020717
0x18002070e  movzx   ebx, bx
0x180020711  or      ebx, 80070000h
0x180020717  mov     rsi, [rsp+48h+arg_8]
0x18002071c  mov     eax, ebx
0x18002071e  mov     rbx, [rsp+48h+arg_0]
0x180020723  add     rsp, 40h
0x180020727  pop     rdi
0x180020728  retn
```
