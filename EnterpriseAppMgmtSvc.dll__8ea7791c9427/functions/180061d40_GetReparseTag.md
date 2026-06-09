# GetReparseTag

- ea: `0x180061d40`
- end: `0x180061e83`
- name: `GetReparseTag`
- size: `323`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x1800616e8`
- `0x180061f0c`

## callees

- `0x18005fd24`
- `0x180061d40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061dba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061dba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061da8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061e15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061e39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061da8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061e15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061e39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061e23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061e47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061e23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061e63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061e63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e33`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061d91`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061d91`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180061df2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180061df2`

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
0x180061d40  mov     [rsp+arg_0], rbx
0x180061d45  mov     [rsp+arg_8], rbp
0x180061d4a  push    rsi
0x180061d4b  push    rdi
0x180061d4c  push    r14
0x180061d4e  sub     rsp, 40h
0x180061d52  mov     r14, rdx
0x180061d55  mov     rdi, rcx
0x180061d58  xor     edx, edx
0x180061d5a  call    PrepareUnicodePathEx
0x180061d5f  mov     rbp, rax
0x180061d62  test    rax, rax
0x180061d65  jz      loc_180061E4F
0x180061d6b  xor     ebx, ebx
0x180061d6d  xor     r9d, r9d; lpSecurityAttributes
0x180061d70  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x180061d75  xor     edx, edx; dwDesiredAccess
0x180061d77  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180061d7f  mov     rcx, rdi; lpFileName
0x180061d82  mov     [r14], ebx
0x180061d85  lea     r8d, [rbx+7]; dwShareMode
0x180061d89  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x180061d91  call    cs:__imp_CreateFileW
0x180061d97  mov     rsi, rax
0x180061d9a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180061d9e  jz      loc_180061E39
0x180061da4  mov     [rsp+58h+BytesReturned], ebx
0x180061da8  call    cs:__imp_GetProcessHeap
0x180061dae  lea     edx, [rbx+8]; dwFlags
0x180061db1  mov     r8d, 4000h; dwBytes
0x180061db7  mov     rcx, rax; hHeap
0x180061dba  call    cs:__imp_HeapAlloc
0x180061dc0  mov     rdi, rax
0x180061dc3  test    rax, rax
0x180061dc6  jz      short loc_180061E2B
0x180061dc8  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x180061dcd  lea     rax, [rsp+58h+BytesReturned]
0x180061dd2  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x180061dd7  xor     r9d, r9d; nInBufferSize
0x180061dda  mov     [rsp+58h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x180061de2  xor     r8d, r8d; lpInBuffer
0x180061de5  mov     edx, 900A8h; dwIoControlCode
0x180061dea  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; lpOutBuffer
0x180061def  mov     rcx, rsi; hDevice
0x180061df2  call    cs:__imp_DeviceIoControl
0x180061df8  test    eax, eax
0x180061dfa  jz      short loc_180061E03
0x180061dfc  mov     eax, [rdi]
0x180061dfe  mov     [r14], eax
0x180061e01  jmp     short loc_180061E15
0x180061e03  call    cs:__imp_GetLastError
0x180061e09  mov     ebx, eax
0x180061e0b  mov     eax, 1Fh
0x180061e10  test    ebx, ebx
0x180061e12  cmovz   ebx, eax
0x180061e15  call    cs:__imp_GetProcessHeap
0x180061e1b  mov     r8, rdi; lpMem
0x180061e1e  xor     edx, edx; dwFlags
0x180061e20  mov     rcx, rax; hHeap
0x180061e23  call    cs:__imp_HeapFree
0x180061e29  jmp     short loc_180061E30
0x180061e2b  mov     ebx, 0Eh
0x180061e30  mov     rcx, rsi; hObject
0x180061e33  call    cs:__imp_CloseHandle
0x180061e39  call    cs:__imp_GetProcessHeap
0x180061e3f  mov     r8, rbp; lpMem
0x180061e42  xor     edx, edx; dwFlags
0x180061e44  mov     rcx, rax; hHeap
0x180061e47  call    cs:__imp_HeapFree
0x180061e4d  jmp     short loc_180061E61
0x180061e4f  call    cs:__imp_GetLastError
0x180061e55  mov     ebx, eax
0x180061e57  mov     eax, 1Fh
0x180061e5c  test    ebx, ebx
0x180061e5e  cmovz   ebx, eax
0x180061e61  mov     ecx, ebx; dwErrCode
0x180061e63  call    cs:__imp_SetLastError
0x180061e69  mov     rbp, [rsp+58h+arg_8]
0x180061e6e  xor     eax, eax
0x180061e70  test    ebx, ebx
0x180061e72  mov     rbx, [rsp+58h+arg_0]
0x180061e77  setz    al
0x180061e7a  add     rsp, 40h
0x180061e7e  pop     r14
0x180061e80  pop     rdi
0x180061e81  pop     rsi
0x180061e82  retn
```
