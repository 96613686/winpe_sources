# GetReparseTag

- ea: `0x180067250`
- end: `0x1800673dc`
- name: `GetReparseTag`
- size: `396`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x180066b38`
- `0x180067480`

## callees

- `0x180064e8c`
- `0x180067250`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800672d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800672d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800672be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067343`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067379`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800672be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067343`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067357`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006738d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067357`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006738d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006732b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006739b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006732b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006739b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800673b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800673b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006736d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006736d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800672a1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800672a1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180067314`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180067314`

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
0x180067250  mov     [rsp+arg_0], rbx
0x180067255  mov     [rsp+arg_8], rbp
0x18006725a  push    rsi
0x18006725b  push    rdi
0x18006725c  push    r14
0x18006725e  sub     rsp, 40h
0x180067262  mov     r14, rdx
0x180067265  mov     rdi, rcx
0x180067268  xor     edx, edx
0x18006726a  call    PrepareUnicodePathEx
0x18006726f  mov     rbp, rax
0x180067272  test    rax, rax
0x180067275  jz      loc_18006739B
0x18006727b  xor     ebx, ebx
0x18006727d  xor     r9d, r9d; lpSecurityAttributes
0x180067280  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x180067285  xor     edx, edx; dwDesiredAccess
0x180067287  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18006728f  mov     rcx, rdi; lpFileName
0x180067292  mov     [r14], ebx
0x180067295  lea     r8d, [rbx+7]; dwShareMode
0x180067299  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800672a1  call    cs:__imp_CreateFileW
0x1800672a8  nop     dword ptr [rax+rax+00h]
0x1800672ad  mov     rsi, rax
0x1800672b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800672b4  jz      loc_180067379
0x1800672ba  mov     [rsp+58h+BytesReturned], ebx
0x1800672be  call    cs:__imp_GetProcessHeap
0x1800672c5  nop     dword ptr [rax+rax+00h]
0x1800672ca  lea     edx, [rbx+8]; dwFlags
0x1800672cd  mov     r8d, 4000h; dwBytes
0x1800672d3  mov     rcx, rax; hHeap
0x1800672d6  call    cs:__imp_HeapAlloc
0x1800672dd  nop     dword ptr [rax+rax+00h]
0x1800672e2  mov     rdi, rax
0x1800672e5  test    rax, rax
0x1800672e8  jz      short loc_180067365
0x1800672ea  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x1800672ef  lea     rax, [rsp+58h+BytesReturned]
0x1800672f4  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x1800672f9  xor     r9d, r9d; nInBufferSize
0x1800672fc  mov     [rsp+58h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x180067304  xor     r8d, r8d; lpInBuffer
0x180067307  mov     edx, 900A8h; dwIoControlCode
0x18006730c  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; lpOutBuffer
0x180067311  mov     rcx, rsi; hDevice
0x180067314  call    cs:__imp_DeviceIoControl
0x18006731b  nop     dword ptr [rax+rax+00h]
0x180067320  test    eax, eax
0x180067322  jz      short loc_18006732B
0x180067324  mov     eax, [rdi]
0x180067326  mov     [r14], eax
0x180067329  jmp     short loc_180067343
0x18006732b  call    cs:__imp_GetLastError
0x180067332  nop     dword ptr [rax+rax+00h]
0x180067337  mov     ebx, eax
0x180067339  mov     eax, 1Fh
0x18006733e  test    ebx, ebx
0x180067340  cmovz   ebx, eax
0x180067343  call    cs:__imp_GetProcessHeap
0x18006734a  nop     dword ptr [rax+rax+00h]
0x18006734f  mov     r8, rdi; lpMem
0x180067352  xor     edx, edx; dwFlags
0x180067354  mov     rcx, rax; hHeap
0x180067357  call    cs:__imp_HeapFree
0x18006735e  nop     dword ptr [rax+rax+00h]
0x180067363  jmp     short loc_18006736A
0x180067365  mov     ebx, 0Eh
0x18006736a  mov     rcx, rsi; hObject
0x18006736d  call    cs:__imp_CloseHandle
0x180067374  nop     dword ptr [rax+rax+00h]
0x180067379  call    cs:__imp_GetProcessHeap
0x180067380  nop     dword ptr [rax+rax+00h]
0x180067385  mov     r8, rbp; lpMem
0x180067388  xor     edx, edx; dwFlags
0x18006738a  mov     rcx, rax; hHeap
0x18006738d  call    cs:__imp_HeapFree
0x180067394  nop     dword ptr [rax+rax+00h]
0x180067399  jmp     short loc_1800673B3
0x18006739b  call    cs:__imp_GetLastError
0x1800673a2  nop     dword ptr [rax+rax+00h]
0x1800673a7  mov     ebx, eax
0x1800673a9  mov     eax, 1Fh
0x1800673ae  test    ebx, ebx
0x1800673b0  cmovz   ebx, eax
0x1800673b3  mov     ecx, ebx; dwErrCode
0x1800673b5  call    cs:__imp_SetLastError
0x1800673bc  nop     dword ptr [rax+rax+00h]
0x1800673c1  mov     rbp, [rsp+58h+arg_8]
0x1800673c6  xor     eax, eax
0x1800673c8  test    ebx, ebx
0x1800673ca  mov     rbx, [rsp+58h+arg_0]
0x1800673cf  setz    al
0x1800673d2  add     rsp, 40h
0x1800673d6  pop     r14
0x1800673d8  pop     rdi
0x1800673d9  pop     rsi
0x1800673da  retn
```
