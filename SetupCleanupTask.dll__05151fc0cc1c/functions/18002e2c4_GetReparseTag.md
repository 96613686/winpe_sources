# GetReparseTag

- ea: `0x18002e2c4`
- end: `0x18002e407`
- name: `GetReparseTag`
- size: `323`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18002dbac`
- `0x18002e520`

## callees

- `0x18002e2c4`
- `0x18002f238`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e3e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e3e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e3b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e3b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e315`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e315`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e33e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e33e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e32c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e3bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e32c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e3bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e3a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e3cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e3a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e3cb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002e376`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002e376`

## pseudocode

```c
_BOOL8 __fastcall GetReparseTag(unsigned __int16 *lpFileName, _DWORD *a2)
{
  void *v4; // rbp
  DWORD LastError; // ebx
  HANDLE FileW; // rsi
  HANDLE ProcessHeap; // rax
  _DWORD *v8; // rdi
  HANDLE v9; // rax
  HANDLE v10; // rax
  DWORD BytesReturned; // [rsp+70h] [rbp+18h] BYREF

  v4 = (void *)PrepareUnicodePathEx(lpFileName);
  if ( v4 )
  {
    LastError = 0;
    *a2 = 0;
    FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x2200000u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      BytesReturned = 0;
      ProcessHeap = GetProcessHeap();
      v8 = HeapAlloc(ProcessHeap, 8u, 0x4000u);
      if ( v8 )
      {
        if ( DeviceIoControl(FileW, 0x900A8u, 0, 0, v8, 0x4000u, &BytesReturned, 0) )
        {
          *a2 = *v8;
        }
        else
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 31;
        }
        v9 = GetProcessHeap();
        HeapFree(v9, 0, v8);
      }
      else
      {
        LastError = 14;
      }
      CloseHandle(FileW);
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v4);
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 31;
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18002e2c4  mov     [rsp+arg_0], rbx
0x18002e2c9  mov     [rsp+arg_8], rbp
0x18002e2ce  push    rsi
0x18002e2cf  push    rdi
0x18002e2d0  push    r14
0x18002e2d2  sub     rsp, 40h
0x18002e2d6  mov     r14, rdx
0x18002e2d9  mov     rdi, rcx
0x18002e2dc  xor     edx, edx
0x18002e2de  call    PrepareUnicodePathEx
0x18002e2e3  mov     rbp, rax
0x18002e2e6  test    rax, rax
0x18002e2e9  jz      loc_18002E3D3
0x18002e2ef  xor     ebx, ebx
0x18002e2f1  xor     r9d, r9d; lpSecurityAttributes
0x18002e2f4  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x18002e2f9  xor     edx, edx; dwDesiredAccess
0x18002e2fb  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18002e303  mov     rcx, rdi; lpFileName
0x18002e306  mov     [r14], ebx
0x18002e309  lea     r8d, [rbx+7]; dwShareMode
0x18002e30d  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18002e315  call    cs:__imp_CreateFileW
0x18002e31b  mov     rsi, rax
0x18002e31e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e322  jz      loc_18002E3BD
0x18002e328  mov     [rsp+58h+BytesReturned], ebx
0x18002e32c  call    cs:__imp_GetProcessHeap
0x18002e332  lea     edx, [rbx+8]; dwFlags
0x18002e335  mov     r8d, 4000h; dwBytes
0x18002e33b  mov     rcx, rax; hHeap
0x18002e33e  call    cs:__imp_HeapAlloc
0x18002e344  mov     rdi, rax
0x18002e347  test    rax, rax
0x18002e34a  jz      short loc_18002E3AF
0x18002e34c  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x18002e351  lea     rax, [rsp+58h+BytesReturned]
0x18002e356  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x18002e35b  xor     r9d, r9d; nInBufferSize
0x18002e35e  mov     [rsp+58h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x18002e366  xor     r8d, r8d; lpInBuffer
0x18002e369  mov     edx, 900A8h; dwIoControlCode
0x18002e36e  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; lpOutBuffer
0x18002e373  mov     rcx, rsi; hDevice
0x18002e376  call    cs:__imp_DeviceIoControl
0x18002e37c  test    eax, eax
0x18002e37e  jz      short loc_18002E387
0x18002e380  mov     eax, [rdi]
0x18002e382  mov     [r14], eax
0x18002e385  jmp     short loc_18002E399
0x18002e387  call    cs:__imp_GetLastError
0x18002e38d  mov     ebx, eax
0x18002e38f  mov     eax, 1Fh
0x18002e394  test    ebx, ebx
0x18002e396  cmovz   ebx, eax
0x18002e399  call    cs:__imp_GetProcessHeap
0x18002e39f  mov     r8, rdi; lpMem
0x18002e3a2  xor     edx, edx; dwFlags
0x18002e3a4  mov     rcx, rax; hHeap
0x18002e3a7  call    cs:__imp_HeapFree
0x18002e3ad  jmp     short loc_18002E3B4
0x18002e3af  mov     ebx, 0Eh
0x18002e3b4  mov     rcx, rsi; hObject
0x18002e3b7  call    cs:__imp_CloseHandle
0x18002e3bd  call    cs:__imp_GetProcessHeap
0x18002e3c3  mov     r8, rbp; lpMem
0x18002e3c6  xor     edx, edx; dwFlags
0x18002e3c8  mov     rcx, rax; hHeap
0x18002e3cb  call    cs:__imp_HeapFree
0x18002e3d1  jmp     short loc_18002E3E5
0x18002e3d3  call    cs:__imp_GetLastError
0x18002e3d9  mov     ebx, eax
0x18002e3db  mov     eax, 1Fh
0x18002e3e0  test    ebx, ebx
0x18002e3e2  cmovz   ebx, eax
0x18002e3e5  mov     ecx, ebx; dwErrCode
0x18002e3e7  call    cs:__imp_SetLastError
0x18002e3ed  mov     rbp, [rsp+58h+arg_8]
0x18002e3f2  xor     eax, eax
0x18002e3f4  test    ebx, ebx
0x18002e3f6  mov     rbx, [rsp+58h+arg_0]
0x18002e3fb  setz    al
0x18002e3fe  add     rsp, 40h
0x18002e402  pop     r14
0x18002e404  pop     rdi
0x18002e405  pop     rsi
0x18002e406  retn
```
