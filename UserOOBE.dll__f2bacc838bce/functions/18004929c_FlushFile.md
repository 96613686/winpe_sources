# FlushFile

- ea: `0x18004929c`
- end: `0x180049368`
- name: `FlushFile`
- size: `204`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180048650`

## callees

- `0x18004929c`
- `0x18004997c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049328`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049328`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049336`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004930d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004933e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004930d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004933e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049348`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049357`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049348`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049357`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049318`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049318`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800492ed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800492ed`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180049301`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180049301`

## pseudocode

```c
__int64 __fastcall FlushFile(unsigned __int16 *a1)
{
  unsigned int v1; // edi
  const WCHAR *v2; // rax
  WCHAR *v3; // rbp
  HANDLE FileW; // rax
  void *v5; // rsi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax

  if ( a1 && *a1 )
  {
    v1 = 0;
    v2 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v3 = (WCHAR *)v2;
    if ( v2 )
    {
      FileW = CreateFileW(v2, 0xC0000000, 0, 0, 3u, 0x80u, 0);
      v5 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
      }
      else
      {
        LastError = 0;
        v1 = FlushFileBuffers(FileW);
        if ( !v1 )
          LastError = GetLastError();
        CloseHandle(v5);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    else
    {
      LastError = GetLastError();
    }
    SetLastError(LastError);
    return v1;
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
0x18004929c  push    rbx
0x18004929e  push    rbp
0x18004929f  push    rsi
0x1800492a0  push    rdi
0x1800492a1  sub     rsp, 48h
0x1800492a5  test    rcx, rcx
0x1800492a8  jz      loc_180049352
0x1800492ae  xor     eax, eax
0x1800492b0  cmp     ax, [rcx]
0x1800492b3  jz      loc_180049352
0x1800492b9  xor     edx, edx
0x1800492bb  xor     edi, edi
0x1800492bd  call    PrepareUnicodePathEx
0x1800492c2  mov     rbp, rax
0x1800492c5  test    rax, rax
0x1800492c8  jz      short loc_18004933E
0x1800492ca  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x1800492cf  xor     r9d, r9d; lpSecurityAttributes
0x1800492d2  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800492da  xor     r8d, r8d; dwShareMode
0x1800492dd  mov     edx, 0C0000000h; dwDesiredAccess
0x1800492e2  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800492ea  mov     rcx, rax; lpFileName
0x1800492ed  call    cs:__imp_CreateFileW
0x1800492f3  mov     rsi, rax
0x1800492f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800492fa  jz      short loc_180049320
0x1800492fc  mov     rcx, rax; hFile
0x1800492ff  xor     ebx, ebx
0x180049301  call    cs:__imp_FlushFileBuffers
0x180049307  mov     edi, eax
0x180049309  test    eax, eax
0x18004930b  jnz     short loc_180049315
0x18004930d  call    cs:__imp_GetLastError
0x180049313  mov     ebx, eax
0x180049315  mov     rcx, rsi; hObject
0x180049318  call    cs:__imp_CloseHandle
0x18004931e  jmp     short loc_180049328
0x180049320  call    cs:__imp_GetLastError
0x180049326  mov     ebx, eax
0x180049328  call    cs:__imp_GetProcessHeap
0x18004932e  mov     r8, rbp; lpMem
0x180049331  xor     edx, edx; dwFlags
0x180049333  mov     rcx, rax; hHeap
0x180049336  call    cs:__imp_HeapFree
0x18004933c  jmp     short loc_180049346
0x18004933e  call    cs:__imp_GetLastError
0x180049344  mov     ebx, eax
0x180049346  mov     ecx, ebx; dwErrCode
0x180049348  call    cs:__imp_SetLastError
0x18004934e  mov     eax, edi
0x180049350  jmp     short loc_18004935F
0x180049352  mov     ecx, 57h ; 'W'; dwErrCode
0x180049357  call    cs:__imp_SetLastError
0x18004935d  xor     eax, eax
0x18004935f  add     rsp, 48h
0x180049363  pop     rdi
0x180049364  pop     rsi
0x180049365  pop     rbp
0x180049366  pop     rbx
0x180049367  retn
```
