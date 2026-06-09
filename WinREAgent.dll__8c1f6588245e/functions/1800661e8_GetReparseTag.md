# GetReparseTag

- ea: `0x1800661e8`
- end: `0x180066315`
- name: `GetReparseTag`
- size: `301`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x180065c98`
- `0x18006642c`

## callees

- `0x1800661c8`
- `0x1800661e8`
- `0x1800673b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800662d0`
- `KERNEL32!CloseHandle` at `0x1800662d0`
- `KERNEL32!SetLastError` at `0x1800662f5`
- `KERNEL32!SetLastError` at `0x1800662f5`
- `KERNEL32!HeapFree` at `0x1800662c0`
- `KERNEL32!HeapFree` at `0x1800662e4`
- `KERNEL32!HeapFree` at `0x1800662c0`
- `KERNEL32!HeapFree` at `0x1800662e4`
- `KERNEL32!HeapAlloc` at `0x180066262`
- `KERNEL32!HeapAlloc` at `0x180066262`
- `KERNEL32!GetProcessHeap` at `0x180066250`
- `KERNEL32!GetProcessHeap` at `0x1800662b2`
- `KERNEL32!GetProcessHeap` at `0x1800662d6`
- `KERNEL32!GetProcessHeap` at `0x180066250`
- `KERNEL32!GetProcessHeap` at `0x1800662b2`
- `KERNEL32!GetProcessHeap` at `0x1800662d6`
- `KERNEL32!CreateFileW` at `0x180066239`
- `KERNEL32!CreateFileW` at `0x180066239`
- `KERNEL32!DeviceIoControl` at `0x18006629a`
- `KERNEL32!DeviceIoControl` at `0x18006629a`

## pseudocode

```c
_BOOL8 __fastcall GetReparseTag(unsigned __int16 *lpFileName, _DWORD *a2)
{
  void *v4; // rbp
  DWORD v5; // ebx
  HANDLE FileW; // rsi
  HANDLE ProcessHeap; // rax
  _DWORD *v8; // rdi
  HANDLE v9; // rax
  HANDLE v10; // rax
  DWORD BytesReturned; // [rsp+70h] [rbp+18h] BYREF

  v4 = (void *)PrepareUnicodePathEx(lpFileName);
  if ( v4 )
  {
    v5 = 0;
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
          *a2 = *v8;
        else
          v5 = GET_LASTERROR_FORCE();
        v9 = GetProcessHeap();
        HeapFree(v9, 0, v8);
      }
      else
      {
        v5 = 14;
      }
      CloseHandle(FileW);
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v4);
  }
  else
  {
    v5 = GET_LASTERROR_FORCE();
  }
  SetLastError(v5);
  return v5 == 0;
}

```

## disassembly

```asm
0x1800661e8  mov     [rsp+arg_0], rbx
0x1800661ed  mov     [rsp+arg_8], rbp
0x1800661f2  push    rsi
0x1800661f3  push    rdi
0x1800661f4  push    r14
0x1800661f6  sub     rsp, 40h
0x1800661fa  mov     r14, rdx
0x1800661fd  mov     rdi, rcx
0x180066200  xor     edx, edx
0x180066202  call    PrepareUnicodePathEx
0x180066207  mov     rbp, rax
0x18006620a  test    rax, rax
0x18006620d  jz      loc_1800662EC
0x180066213  xor     ebx, ebx
0x180066215  xor     r9d, r9d; lpSecurityAttributes
0x180066218  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x18006621d  xor     edx, edx; dwDesiredAccess
0x18006621f  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180066227  mov     rcx, rdi; lpFileName
0x18006622a  mov     [r14], ebx
0x18006622d  lea     r8d, [rbx+7]; dwShareMode
0x180066231  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x180066239  call    cs:__imp_CreateFileW
0x18006623f  mov     rsi, rax
0x180066242  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180066246  jz      loc_1800662D6
0x18006624c  mov     [rsp+58h+BytesReturned], ebx
0x180066250  call    cs:__imp_GetProcessHeap
0x180066256  lea     edx, [rbx+8]; dwFlags
0x180066259  mov     r8d, 4000h; dwBytes
0x18006625f  mov     rcx, rax; hHeap
0x180066262  call    cs:__imp_HeapAlloc
0x180066268  mov     rdi, rax
0x18006626b  test    rax, rax
0x18006626e  jz      short loc_1800662C8
0x180066270  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x180066275  lea     rax, [rsp+58h+BytesReturned]
0x18006627a  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x18006627f  xor     r9d, r9d; nInBufferSize
0x180066282  mov     [rsp+58h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x18006628a  xor     r8d, r8d; lpInBuffer
0x18006628d  mov     edx, 900A8h; dwIoControlCode
0x180066292  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; lpOutBuffer
0x180066297  mov     rcx, rsi; hDevice
0x18006629a  call    cs:__imp_DeviceIoControl
0x1800662a0  test    eax, eax
0x1800662a2  jz      short loc_1800662AB
0x1800662a4  mov     eax, [rdi]
0x1800662a6  mov     [r14], eax
0x1800662a9  jmp     short loc_1800662B2
0x1800662ab  call    GET_LASTERROR_FORCE
0x1800662b0  mov     ebx, eax
0x1800662b2  call    cs:__imp_GetProcessHeap
0x1800662b8  mov     r8, rdi; lpMem
0x1800662bb  xor     edx, edx; dwFlags
0x1800662bd  mov     rcx, rax; hHeap
0x1800662c0  call    cs:__imp_HeapFree
0x1800662c6  jmp     short loc_1800662CD
0x1800662c8  mov     ebx, 0Eh
0x1800662cd  mov     rcx, rsi; hObject
0x1800662d0  call    cs:__imp_CloseHandle
0x1800662d6  call    cs:__imp_GetProcessHeap
0x1800662dc  mov     r8, rbp; lpMem
0x1800662df  xor     edx, edx; dwFlags
0x1800662e1  mov     rcx, rax; hHeap
0x1800662e4  call    cs:__imp_HeapFree
0x1800662ea  jmp     short loc_1800662F3
0x1800662ec  call    GET_LASTERROR_FORCE
0x1800662f1  mov     ebx, eax
0x1800662f3  mov     ecx, ebx; dwErrCode
0x1800662f5  call    cs:__imp_SetLastError
0x1800662fb  mov     rbp, [rsp+58h+arg_8]
0x180066300  xor     eax, eax
0x180066302  test    ebx, ebx
0x180066304  mov     rbx, [rsp+58h+arg_0]
0x180066309  setz    al
0x18006630c  add     rsp, 40h
0x180066310  pop     r14
0x180066312  pop     rdi
0x180066313  pop     rsi
0x180066314  retn
```
