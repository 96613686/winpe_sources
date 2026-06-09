# GetReparseTag

- ea: `0x18003ca10`
- end: `0x18003cb53`
- name: `GetReparseTag`
- size: `323`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18003c3b8`
- `0x18003cbdc`

## callees

- `0x18003ca10`
- `0x18003d238`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ca61`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ca61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ca78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cae5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cb09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ca78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cae5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cb09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ca8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ca8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003caf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cb17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003caf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cb17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cb33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cb33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cb03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cb03`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003cac2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003cac2`

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
0x18003ca10  mov     [rsp+arg_0], rbx
0x18003ca15  mov     [rsp+arg_8], rbp
0x18003ca1a  push    rsi
0x18003ca1b  push    rdi
0x18003ca1c  push    r14
0x18003ca1e  sub     rsp, 40h
0x18003ca22  mov     r14, rdx
0x18003ca25  mov     rdi, rcx
0x18003ca28  xor     edx, edx
0x18003ca2a  call    PrepareUnicodePathEx
0x18003ca2f  mov     rbp, rax
0x18003ca32  test    rax, rax
0x18003ca35  jz      loc_18003CB1F
0x18003ca3b  xor     ebx, ebx
0x18003ca3d  xor     r9d, r9d; lpSecurityAttributes
0x18003ca40  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x18003ca45  xor     edx, edx; dwDesiredAccess
0x18003ca47  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003ca4f  mov     rcx, rdi; lpFileName
0x18003ca52  mov     [r14], ebx
0x18003ca55  lea     r8d, [rbx+7]; dwShareMode
0x18003ca59  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18003ca61  call    cs:__imp_CreateFileW
0x18003ca67  mov     rsi, rax
0x18003ca6a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ca6e  jz      loc_18003CB09
0x18003ca74  mov     [rsp+58h+BytesReturned], ebx
0x18003ca78  call    cs:__imp_GetProcessHeap
0x18003ca7e  lea     edx, [rbx+8]; dwFlags
0x18003ca81  mov     r8d, 4000h; dwBytes
0x18003ca87  mov     rcx, rax; hHeap
0x18003ca8a  call    cs:__imp_HeapAlloc
0x18003ca90  mov     rdi, rax
0x18003ca93  test    rax, rax
0x18003ca96  jz      short loc_18003CAFB
0x18003ca98  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x18003ca9d  lea     rax, [rsp+58h+BytesReturned]
0x18003caa2  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x18003caa7  xor     r9d, r9d; nInBufferSize
0x18003caaa  mov     [rsp+58h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x18003cab2  xor     r8d, r8d; lpInBuffer
0x18003cab5  mov     edx, 900A8h; dwIoControlCode
0x18003caba  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; lpOutBuffer
0x18003cabf  mov     rcx, rsi; hDevice
0x18003cac2  call    cs:__imp_DeviceIoControl
0x18003cac8  test    eax, eax
0x18003caca  jz      short loc_18003CAD3
0x18003cacc  mov     eax, [rdi]
0x18003cace  mov     [r14], eax
0x18003cad1  jmp     short loc_18003CAE5
0x18003cad3  call    cs:__imp_GetLastError
0x18003cad9  mov     ebx, eax
0x18003cadb  mov     eax, 1Fh
0x18003cae0  test    ebx, ebx
0x18003cae2  cmovz   ebx, eax
0x18003cae5  call    cs:__imp_GetProcessHeap
0x18003caeb  mov     r8, rdi; lpMem
0x18003caee  xor     edx, edx; dwFlags
0x18003caf0  mov     rcx, rax; hHeap
0x18003caf3  call    cs:__imp_HeapFree
0x18003caf9  jmp     short loc_18003CB00
0x18003cafb  mov     ebx, 0Eh
0x18003cb00  mov     rcx, rsi; hObject
0x18003cb03  call    cs:__imp_CloseHandle
0x18003cb09  call    cs:__imp_GetProcessHeap
0x18003cb0f  mov     r8, rbp; lpMem
0x18003cb12  xor     edx, edx; dwFlags
0x18003cb14  mov     rcx, rax; hHeap
0x18003cb17  call    cs:__imp_HeapFree
0x18003cb1d  jmp     short loc_18003CB31
0x18003cb1f  call    cs:__imp_GetLastError
0x18003cb25  mov     ebx, eax
0x18003cb27  mov     eax, 1Fh
0x18003cb2c  test    ebx, ebx
0x18003cb2e  cmovz   ebx, eax
0x18003cb31  mov     ecx, ebx; dwErrCode
0x18003cb33  call    cs:__imp_SetLastError
0x18003cb39  mov     rbp, [rsp+58h+arg_8]
0x18003cb3e  xor     eax, eax
0x18003cb40  test    ebx, ebx
0x18003cb42  mov     rbx, [rsp+58h+arg_0]
0x18003cb47  setz    al
0x18003cb4a  add     rsp, 40h
0x18003cb4e  pop     r14
0x18003cb50  pop     rdi
0x18003cb51  pop     rsi
0x18003cb52  retn
```
