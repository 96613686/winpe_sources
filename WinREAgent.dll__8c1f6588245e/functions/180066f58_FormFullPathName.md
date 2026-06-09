# FormFullPathName

- ea: `0x180066f58`
- end: `0x180066ff5`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180065870`
- `0x180065c98`
- `0x18006710c`
- `0x1800673b0`
- `0x180068ae8`

## callees

- `0x180066f58`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180066fd4`
- `KERNEL32!SetLastError` at `0x180066fe4`
- `KERNEL32!SetLastError` at `0x180066fd4`
- `KERNEL32!SetLastError` at `0x180066fe4`
- `KERNEL32!GetLastError` at `0x180066fca`
- `KERNEL32!GetLastError` at `0x180066fca`
- `KERNEL32!HeapAlloc` at `0x180066f9a`
- `KERNEL32!HeapAlloc` at `0x180066f9a`
- `KERNEL32!GetProcessHeap` at `0x180066f89`
- `KERNEL32!GetProcessHeap` at `0x180066f89`
- `KERNEL32!GetFullPathNameW` at `0x180066f78`
- `KERNEL32!GetFullPathNameW` at `0x180066fb5`
- `KERNEL32!GetFullPathNameW` at `0x180066f78`
- `KERNEL32!GetFullPathNameW` at `0x180066fb5`

## pseudocode

```c
WCHAR *__fastcall FormFullPathName(LPCWSTR lpFileName)
{
  DWORD FullPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v4; // rax
  WCHAR *v5; // rsi
  DWORD LastError; // ebx

  if ( lpFileName && *lpFileName )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    if ( FullPathNameW )
    {
      ProcessHeap = GetProcessHeap();
      v4 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
      v5 = v4;
      if ( v4 )
      {
        LastError = 0;
        if ( !GetFullPathNameW(lpFileName, FullPathNameW, v4, 0) )
          goto LABEL_9;
      }
      else
      {
        LastError = 14;
      }
LABEL_10:
      SetLastError(LastError);
      return v5;
    }
    v5 = 0;
LABEL_9:
    LastError = GetLastError();
    goto LABEL_10;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180066f58  push    rbx
0x180066f5a  push    rbp
0x180066f5b  push    rsi
0x180066f5c  push    rdi
0x180066f5d  sub     rsp, 28h
0x180066f61  mov     rdi, rcx
0x180066f64  test    rcx, rcx
0x180066f67  jz      short loc_180066FDF
0x180066f69  xor     eax, eax
0x180066f6b  cmp     ax, [rcx]
0x180066f6e  jz      short loc_180066FDF
0x180066f70  xor     r9d, r9d; lpFilePart
0x180066f73  xor     r8d, r8d; lpBuffer
0x180066f76  xor     edx, edx; nBufferLength
0x180066f78  call    cs:__imp_GetFullPathNameW
0x180066f7e  mov     ebp, eax
0x180066f80  test    eax, eax
0x180066f82  jz      short loc_180066FC8
0x180066f84  mov     ebx, ebp
0x180066f86  add     rbx, rbx
0x180066f89  call    cs:__imp_GetProcessHeap
0x180066f8f  mov     r8, rbx; dwBytes
0x180066f92  mov     edx, 8; dwFlags
0x180066f97  mov     rcx, rax; hHeap
0x180066f9a  call    cs:__imp_HeapAlloc
0x180066fa0  mov     rsi, rax
0x180066fa3  test    rax, rax
0x180066fa6  jz      short loc_180066FC1
0x180066fa8  xor     r9d, r9d; lpFilePart
0x180066fab  mov     r8, rax; lpBuffer
0x180066fae  mov     edx, ebp; nBufferLength
0x180066fb0  mov     rcx, rdi; lpFileName
0x180066fb3  xor     ebx, ebx
0x180066fb5  call    cs:__imp_GetFullPathNameW
0x180066fbb  test    eax, eax
0x180066fbd  jnz     short loc_180066FD2
0x180066fbf  jmp     short loc_180066FCA
0x180066fc1  mov     ebx, 0Eh
0x180066fc6  jmp     short loc_180066FD2
0x180066fc8  xor     esi, esi
0x180066fca  call    cs:__imp_GetLastError
0x180066fd0  mov     ebx, eax
0x180066fd2  mov     ecx, ebx; dwErrCode
0x180066fd4  call    cs:__imp_SetLastError
0x180066fda  mov     rax, rsi
0x180066fdd  jmp     short loc_180066FEC
0x180066fdf  mov     ecx, 57h ; 'W'; dwErrCode
0x180066fe4  call    cs:__imp_SetLastError
0x180066fea  xor     eax, eax
0x180066fec  add     rsp, 28h
0x180066ff0  pop     rdi
0x180066ff1  pop     rsi
0x180066ff2  pop     rbp
0x180066ff3  pop     rbx
0x180066ff4  retn
```
