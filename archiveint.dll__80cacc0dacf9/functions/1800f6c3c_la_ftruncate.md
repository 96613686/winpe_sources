# la_ftruncate

- ea: `0x1800f6c3c`
- end: `0x1800f6cc8`
- name: `la_ftruncate`
- size: `140`
- prototype: `__int64 __fastcall(HANDLE hFile, LONG lDistanceToMove)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800f4c10`

## callees

- `0x1800149c0`
- `0x1800f6c3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f6c5c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f6c5c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800f6cb1`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800f6cb1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800f6c86`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800f6c86`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800f6c51`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800f6c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6c9f`

## pseudocode

```c
__int64 __fastcall la_ftruncate(HANDLE hFile, __int64 lDistanceToMove)
{
  LONG v2; // edi
  DWORD LastError; // eax
  LONG v6; // [rsp+3Ch] [rbp+14h]
  LONG DistanceToMoveHigh; // [rsp+44h] [rbp+1Ch] BYREF

  v6 = HIDWORD(lDistanceToMove);
  v2 = lDistanceToMove;
  if ( GetFileType(hFile) != 1 )
  {
    *(_DWORD *)_o__errno() = 9;
    return 0xFFFFFFFFLL;
  }
  DistanceToMoveHigh = v6;
  if ( SetFilePointer(hFile, v2, &DistanceToMoveHigh, 0) == -1 && GetLastError() || !SetEndOfFile(hFile) )
  {
    LastError = GetLastError();
    _la_dosmaperr(LastError);
    return 0xFFFFFFFFLL;
  }
  return 0;
}

```

## disassembly

```asm
0x1800f6c3c  mov     [rsp+arg_0], rbx
0x1800f6c41  mov     [rsp+arg_8], rdx
0x1800f6c46  push    rdi
0x1800f6c47  sub     rsp, 20h
0x1800f6c4b  mov     rdi, rdx
0x1800f6c4e  mov     rbx, rcx
0x1800f6c51  call    cs:__imp_GetFileType
0x1800f6c57  cmp     eax, 1
0x1800f6c5a  jz      short loc_1800F6C6D
0x1800f6c5c  call    cs:__imp__o__errno
0x1800f6c62  mov     dword ptr [rax], 9
0x1800f6c68  or      eax, 0FFFFFFFFh
0x1800f6c6b  jmp     short loc_1800F6CBD
0x1800f6c6d  mov     eax, dword ptr [rsp+28h+arg_8+4]
0x1800f6c71  lea     r8, [rsp+28h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800f6c76  xor     r9d, r9d; dwMoveMethod
0x1800f6c79  mov     [rsp+28h+DistanceToMoveHigh], eax
0x1800f6c7d  mov     edx, edi; lDistanceToMove
0x1800f6c7f  mov     [rsp+28h+arg_10], edi
0x1800f6c83  mov     rcx, rbx; hFile
0x1800f6c86  call    cs:__imp_SetFilePointer
0x1800f6c8c  mov     [rsp+28h+arg_10], eax
0x1800f6c90  cmp     eax, 0FFFFFFFFh
0x1800f6c93  jnz     short loc_1800F6CAE
0x1800f6c95  call    cs:__imp_GetLastError
0x1800f6c9b  test    eax, eax
0x1800f6c9d  jz      short loc_1800F6CAE
0x1800f6c9f  call    cs:__imp_GetLastError
0x1800f6ca5  mov     ecx, eax
0x1800f6ca7  call    __la_dosmaperr
0x1800f6cac  jmp     short loc_1800F6C68
0x1800f6cae  mov     rcx, rbx; hFile
0x1800f6cb1  call    cs:__imp_SetEndOfFile
0x1800f6cb7  test    eax, eax
0x1800f6cb9  jz      short loc_1800F6C9F
0x1800f6cbb  xor     eax, eax
0x1800f6cbd  mov     rbx, [rsp+28h+arg_0]
0x1800f6cc2  add     rsp, 20h
0x1800f6cc6  pop     rdi
0x1800f6cc7  retn
```
