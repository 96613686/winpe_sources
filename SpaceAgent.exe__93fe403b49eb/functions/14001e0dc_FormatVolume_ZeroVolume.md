# FormatVolume_ZeroVolume

- ea: `0x14001e0dc`
- end: `0x14001e1d4`
- name: `FormatVolume_ZeroVolume`
- size: `248`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001dedc`

## callees

- `0x14001e0dc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001e1ab`
- `KERNEL32!CloseHandle` at `0x14001e1ab`
- `KERNEL32!WriteFile` at `0x14001e178`
- `KERNEL32!WriteFile` at `0x14001e178`
- `KERNEL32!HeapAlloc` at `0x14001e143`
- `KERNEL32!HeapAlloc` at `0x14001e143`
- `KERNEL32!HeapFree` at `0x14001e191`
- `KERNEL32!HeapFree` at `0x14001e191`
- `KERNEL32!GetProcessHeap` at `0x14001e0ea`
- `KERNEL32!GetProcessHeap` at `0x14001e0ea`
- `KERNEL32!SetLastError` at `0x14001e153`
- `KERNEL32!SetLastError` at `0x14001e1c1`
- `KERNEL32!SetLastError` at `0x14001e153`
- `KERNEL32!SetLastError` at `0x14001e1c1`
- `KERNEL32!GetLastError` at `0x14001e159`
- `KERNEL32!GetLastError` at `0x14001e181`
- `KERNEL32!GetLastError` at `0x14001e1b7`
- `KERNEL32!GetLastError` at `0x14001e159`
- `KERNEL32!GetLastError` at `0x14001e181`
- `KERNEL32!GetLastError` at `0x14001e1b7`
- `KERNEL32!CreateFileW` at `0x14001e11a`
- `KERNEL32!CreateFileW` at `0x14001e11a`

## pseudocode

```c
__int64 __fastcall FormatVolume_ZeroVolume(LPCWSTR lpFileName)
{
  HANDLE ProcessHeap; // rbp
  HANDLE FileW; // rsi
  void *v4; // rbx
  void *v5; // rax
  DWORD LastError; // edi
  BOOL v7; // r14d
  BOOL v8; // eax

  ProcessHeap = GetProcessHeap();
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LODWORD(v4) = 0;
LABEL_10:
    LastError = GetLastError();
    goto LABEL_11;
  }
  v5 = HeapAlloc(ProcessHeap, 8u, 0x10000u);
  v4 = v5;
  if ( v5 )
  {
    v7 = WriteFile(FileW, v5, 0x10000u, 0, 0);
    LastError = GetLastError();
    LODWORD(v4) = HeapFree(ProcessHeap, 0, v4);
    if ( v7 )
      LastError = 6;
    else
      LODWORD(v4) = 0;
  }
  else
  {
    SetLastError(8u);
    LastError = GetLastError();
  }
  v8 = CloseHandle(FileW);
  if ( (_DWORD)v4 )
  {
    LODWORD(v4) = v8;
    goto LABEL_10;
  }
LABEL_11:
  SetLastError(LastError);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001e0dc  push    rbx
0x14001e0de  push    rbp
0x14001e0df  push    rsi
0x14001e0e0  push    rdi
0x14001e0e1  push    r14
0x14001e0e3  sub     rsp, 40h
0x14001e0e7  mov     rbx, rcx
0x14001e0ea  call    cs:__imp_GetProcessHeap
0x14001e0f0  mov     r8d, 3; dwShareMode
0x14001e0f6  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x14001e0ff  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14001e107  xor     r9d, r9d; lpSecurityAttributes
0x14001e10a  mov     edx, 0C0000000h; dwDesiredAccess
0x14001e10f  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x14001e114  mov     rcx, rbx; lpFileName
0x14001e117  mov     rbp, rax
0x14001e11a  call    cs:__imp_CreateFileW
0x14001e120  mov     rsi, rax
0x14001e123  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001e127  jnz     short loc_14001E130
0x14001e129  xor     ebx, ebx
0x14001e12b  jmp     loc_14001E1B7
0x14001e130  mov     r14d, 10000h
0x14001e136  mov     edi, 8
0x14001e13b  mov     r8d, r14d; dwBytes
0x14001e13e  mov     edx, edi; dwFlags
0x14001e140  mov     rcx, rbp; hHeap
0x14001e143  call    cs:__imp_HeapAlloc
0x14001e149  mov     rbx, rax
0x14001e14c  test    rax, rax
0x14001e14f  jnz     short loc_14001E163
0x14001e151  mov     ecx, edi; dwErrCode
0x14001e153  call    cs:__imp_SetLastError
0x14001e159  call    cs:__imp_GetLastError
0x14001e15f  mov     edi, eax
0x14001e161  jmp     short loc_14001E1A8
0x14001e163  xor     r9d, r9d; lpNumberOfBytesWritten
0x14001e166  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x14001e16f  mov     r8d, r14d; nNumberOfBytesToWrite
0x14001e172  mov     rdx, rbx; lpBuffer
0x14001e175  mov     rcx, rsi; hFile
0x14001e178  call    cs:__imp_WriteFile
0x14001e17e  mov     r14d, eax
0x14001e181  call    cs:__imp_GetLastError
0x14001e187  mov     r8, rbx; lpMem
0x14001e18a  xor     edx, edx; dwFlags
0x14001e18c  mov     rcx, rbp; hHeap
0x14001e18f  mov     edi, eax
0x14001e191  call    cs:__imp_HeapFree
0x14001e197  mov     ebx, eax
0x14001e199  test    r14d, r14d
0x14001e19c  jz      short loc_14001E1A5
0x14001e19e  mov     edi, 6
0x14001e1a3  jmp     short loc_14001E1A8
0x14001e1a5  mov     ebx, r14d
0x14001e1a8  mov     rcx, rsi; hObject
0x14001e1ab  call    cs:__imp_CloseHandle
0x14001e1b1  test    ebx, ebx
0x14001e1b3  jz      short loc_14001E1BF
0x14001e1b5  mov     ebx, eax
0x14001e1b7  call    cs:__imp_GetLastError
0x14001e1bd  mov     edi, eax
0x14001e1bf  mov     ecx, edi; dwErrCode
0x14001e1c1  call    cs:__imp_SetLastError
0x14001e1c7  mov     eax, ebx
0x14001e1c9  add     rsp, 40h
0x14001e1cd  pop     r14
0x14001e1cf  pop     rdi
0x14001e1d0  pop     rsi
0x14001e1d1  pop     rbp
0x14001e1d2  pop     rbx
0x14001e1d3  retn
```
