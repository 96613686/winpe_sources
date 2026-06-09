# WofpOpenVolumeWithFlagsAndAttributes

- ea: `0x18004cdc0`
- end: `0x18004cec7`
- name: `WofpOpenVolumeWithFlagsAndAttributes`
- size: `263`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path`

## callers

- `0x18004c820`

## callees

- `0x18004cdc0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004ce9a`
- `KERNEL32!HeapFree` at `0x18004ceb3`
- `KERNEL32!HeapFree` at `0x18004ce9a`
- `KERNEL32!HeapFree` at `0x18004ceb3`
- `KERNEL32!HeapAlloc` at `0x18004cde3`
- `KERNEL32!HeapAlloc` at `0x18004ce22`
- `KERNEL32!HeapAlloc` at `0x18004cde3`
- `KERNEL32!HeapAlloc` at `0x18004ce22`
- `KERNEL32!GetProcessHeap` at `0x18004cdd2`
- `KERNEL32!GetProcessHeap` at `0x18004ce11`
- `KERNEL32!GetProcessHeap` at `0x18004ce8c`
- `KERNEL32!GetProcessHeap` at `0x18004cea5`
- `KERNEL32!GetProcessHeap` at `0x18004cdd2`
- `KERNEL32!GetProcessHeap` at `0x18004ce11`
- `KERNEL32!GetProcessHeap` at `0x18004ce8c`
- `KERNEL32!GetProcessHeap` at `0x18004cea5`
- `KERNEL32!CreateFileW` at `0x18004ce83`
- `KERNEL32!CreateFileW` at `0x18004ce83`
- `KERNEL32!GetVolumePathNameW` at `0x18004ce07`
- `KERNEL32!GetVolumePathNameW` at `0x18004ce07`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004ce3c`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004ce3c`

## pseudocode

```c
__int64 __fastcall WofpOpenVolumeWithFlagsAndAttributes(LPCWSTR lpszFileName)
{
  __int64 FileW; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v4; // rax
  WCHAR *v5; // rsi
  WCHAR *v6; // rbx
  HANDLE v7; // rax
  WCHAR *v8; // rax
  __int64 v9; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax

  FileW = -1;
  ProcessHeap = GetProcessHeap();
  v4 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v5 = v4;
  if ( v4 )
  {
    v6 = 0;
    if ( GetVolumePathNameW(lpszFileName, v4, 0x104u) )
    {
      v7 = GetProcessHeap();
      v8 = (WCHAR *)HeapAlloc(v7, 0, 0x208u);
      v6 = v8;
      if ( v8 )
      {
        if ( GetVolumeNameForVolumeMountPointW(v5, v8, 0x104u) )
        {
          do
            ++FileW;
          while ( v6[FileW] );
          v9 = (unsigned int)(FileW - 1);
          if ( v6[v9] == 92 )
            v6[v9] = 0;
          FileW = (__int64)CreateFileW(v6, 0x80000000, 7u, 0, 3u, 0x80u, 0);
        }
      }
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v5);
    if ( v6 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v6);
    }
  }
  return FileW;
}

```

## disassembly

```asm
0x18004cdc0  push    rbx
0x18004cdc2  push    rbp
0x18004cdc3  push    rsi
0x18004cdc4  push    rdi
0x18004cdc5  push    r14
0x18004cdc7  sub     rsp, 40h
0x18004cdcb  mov     rbp, rcx
0x18004cdce  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004cdd2  call    cs:__imp_GetProcessHeap
0x18004cdd8  xor     edx, edx; dwFlags
0x18004cdda  mov     r8d, 208h; dwBytes
0x18004cde0  mov     rcx, rax; hHeap
0x18004cde3  call    cs:__imp_HeapAlloc
0x18004cde9  xor     r14d, r14d
0x18004cdec  mov     rsi, rax
0x18004cdef  test    rax, rax
0x18004cdf2  jz      loc_18004CEB9
0x18004cdf8  mov     r8d, 104h; cchBufferLength
0x18004cdfe  mov     rdx, rax; lpszVolumePathName
0x18004ce01  mov     rcx, rbp; lpszFileName
0x18004ce04  mov     ebx, r14d
0x18004ce07  call    cs:__imp_GetVolumePathNameW
0x18004ce0d  test    eax, eax
0x18004ce0f  jz      short loc_18004CE8C
0x18004ce11  call    cs:__imp_GetProcessHeap
0x18004ce17  xor     edx, edx; dwFlags
0x18004ce19  mov     r8d, 208h; dwBytes
0x18004ce1f  mov     rcx, rax; hHeap
0x18004ce22  call    cs:__imp_HeapAlloc
0x18004ce28  mov     rbx, rax
0x18004ce2b  test    rax, rax
0x18004ce2e  jz      short loc_18004CE8C
0x18004ce30  mov     r8d, 104h; cchBufferLength
0x18004ce36  mov     rdx, rax; lpszVolumeName
0x18004ce39  mov     rcx, rsi; lpszVolumeMountPoint
0x18004ce3c  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004ce42  test    eax, eax
0x18004ce44  jz      short loc_18004CE8C
0x18004ce46  inc     rdi
0x18004ce49  cmp     [rbx+rdi*2], r14w
0x18004ce4e  jnz     short loc_18004CE46
0x18004ce50  lea     eax, [rdi-1]
0x18004ce53  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x18004ce58  jnz     short loc_18004CE5F
0x18004ce5a  mov     [rbx+rax*2], r14w
0x18004ce5f  xor     r9d, r9d; lpSecurityAttributes
0x18004ce62  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x18004ce67  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004ce6f  mov     edx, 80000000h; dwDesiredAccess
0x18004ce74  mov     rcx, rbx; lpFileName
0x18004ce77  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18004ce7f  lea     r8d, [r9+7]; dwShareMode
0x18004ce83  call    cs:__imp_CreateFileW
0x18004ce89  mov     rdi, rax
0x18004ce8c  call    cs:__imp_GetProcessHeap
0x18004ce92  mov     r8, rsi; lpMem
0x18004ce95  xor     edx, edx; dwFlags
0x18004ce97  mov     rcx, rax; hHeap
0x18004ce9a  call    cs:__imp_HeapFree
0x18004cea0  test    rbx, rbx
0x18004cea3  jz      short loc_18004CEB9
0x18004cea5  call    cs:__imp_GetProcessHeap
0x18004ceab  mov     r8, rbx; lpMem
0x18004ceae  xor     edx, edx; dwFlags
0x18004ceb0  mov     rcx, rax; hHeap
0x18004ceb3  call    cs:__imp_HeapFree
0x18004ceb9  mov     rax, rdi
0x18004cebc  add     rsp, 40h
0x18004cec0  pop     r14
0x18004cec2  pop     rdi
0x18004cec3  pop     rsi
0x18004cec4  pop     rbp
0x18004cec5  pop     rbx
0x18004cec6  retn
```
