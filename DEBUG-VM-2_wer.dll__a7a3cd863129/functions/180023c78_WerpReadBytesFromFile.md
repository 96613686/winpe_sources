# WerpReadBytesFromFile

- ea: `0x180023c78`
- end: `0x180023cf1`
- name: `WerpReadBytesFromFile`
- size: `121`
- prototype: `__int64 __fastcall(LPDWORD lpNumberOfBytesRead, HANDLE hFile, LARGE_INTEGER liDistanceToMove, LPVOID lpBuffer, DWORD nNumberOfBytesToRead)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180046204`

## callees

- `0x18000716c`
- `0x180023c78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ce2`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180023ca5`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180023ca5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180023cc6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180023cc6`

## pseudocode

```c
__int64 __fastcall WerpReadBytesFromFile(
        LPDWORD lpNumberOfBytesRead,
        HANDLE hFile,
        LARGE_INTEGER liDistanceToMove,
        LPVOID lpBuffer,
        DWORD nNumberOfBytesToRead)
{
  DWORD LastError; // eax

  *lpNumberOfBytesRead = 0;
  if ( SetFilePointerEx(hFile, liDistanceToMove, 0, 0)
    && ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, lpNumberOfBytesRead, 0) )
  {
    return 0;
  }
  LastError = GetLastError();
  return ERROR_HR_FROM_WIN32(LastError);
}

```

## disassembly

```asm
0x180023c78  mov     [rsp+arg_0], rbx
0x180023c7d  mov     [rsp+arg_8], rsi
0x180023c82  push    rdi
0x180023c83  sub     rsp, 30h
0x180023c87  mov     rax, r8
0x180023c8a  mov     dword ptr [rcx], 0
0x180023c90  mov     rbx, rdx
0x180023c93  mov     rsi, r9
0x180023c96  mov     rdi, rcx
0x180023c99  mov     rdx, rax; liDistanceToMove
0x180023c9c  mov     rcx, rbx; hFile
0x180023c9f  xor     r9d, r9d; dwMoveMethod
0x180023ca2  xor     r8d, r8d; lpNewFilePointer
0x180023ca5  call    cs:__imp_SetFilePointerEx
0x180023cab  test    eax, eax
0x180023cad  jz      short loc_180023CE2
0x180023caf  mov     r8d, [rsp+38h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180023cb4  mov     r9, rdi; lpNumberOfBytesRead
0x180023cb7  mov     rdx, rsi; lpBuffer
0x180023cba  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180023cc3  mov     rcx, rbx; hFile
0x180023cc6  call    cs:__imp_ReadFile
0x180023ccc  test    eax, eax
0x180023cce  jz      short loc_180023CE2
0x180023cd0  xor     eax, eax
0x180023cd2  mov     rbx, [rsp+38h+arg_0]
0x180023cd7  mov     rsi, [rsp+38h+arg_8]
0x180023cdc  add     rsp, 30h
0x180023ce0  pop     rdi
0x180023ce1  retn
0x180023ce2  call    cs:__imp_GetLastError
0x180023ce8  mov     ecx, eax; unsigned int
0x180023cea  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180023cef  jmp     short loc_180023CD2
```
