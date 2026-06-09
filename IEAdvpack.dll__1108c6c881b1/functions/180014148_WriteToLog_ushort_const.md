# WriteToLog(ushort const *,...)

- ea: `0x180014148`
- end: `0x1800141eb`
- name: `?WriteToLog@@YAXPEBGZZ`
- size: `163`
- prototype: `void(LPCVOID lpSource, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180013280`
- `0x1800135d8`
- `0x180013acc`

## callees

- `0x180014148`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800141de`
- `KERNEL32!LocalFree` at `0x1800141de`
- `KERNEL32!WriteFile` at `0x1800141d3`
- `KERNEL32!WriteFile` at `0x1800141d3`
- `KERNEL32!FormatMessageW` at `0x1800141a6`
- `KERNEL32!FormatMessageW` at `0x1800141a6`

## pseudocode

```c
void WriteToLog(LPCVOID lpSource, ...)
{
  __int64 v1; // rbx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-38h] BYREF
  LPCVOID lpBuffer; // [rsp+48h] [rbp-30h] BYREF
  va_list v4; // [rsp+50h] [rbp-28h] BYREF
  va_list va; // [rsp+88h] [rbp+10h] BYREF

  va_start(va, lpSource);
  v1 = -1;
  v4 = 0;
  lpBuffer = 0;
  NumberOfBytesWritten = 0;
  if ( g_hLogFile != (HANDLE)-1LL )
  {
    va_copy(v4, va);
    FormatMessageW(0x500u, lpSource, 0, 0, (LPWSTR)&lpBuffer, 0, &v4);
    if ( lpBuffer )
    {
      do
        ++v1;
      while ( *((_WORD *)lpBuffer + v1) );
      WriteFile(g_hLogFile, lpBuffer, v1, &NumberOfBytesWritten, 0);
      LocalFree((HLOCAL)lpBuffer);
    }
  }
}

```

## disassembly

```asm
0x180014148  mov     r11, rsp
0x18001414b  mov     [r11+8], rcx
0x18001414f  mov     [r11+10h], rdx
0x180014153  mov     [r11+18h], r8
0x180014157  mov     [r11+20h], r9
0x18001415b  push    rbx
0x18001415c  push    rdi
0x18001415d  sub     rsp, 68h
0x180014161  xor     edi, edi
0x180014163  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014167  cmp     cs:?g_hLogFile@@3PEAXEA, rbx; void * g_hLogFile
0x18001416e  mov     [r11-28h], rdi
0x180014172  mov     [r11-30h], rdi
0x180014176  mov     [rsp+78h+NumberOfBytesWritten], edi
0x18001417a  jz      short loc_1800141E4
0x18001417c  lea     rax, [r11+10h]
0x180014180  mov     rdx, rcx; lpSource
0x180014183  mov     [r11-28h], rax
0x180014187  xor     r9d, r9d; dwLanguageId
0x18001418a  lea     rax, [r11-28h]
0x18001418e  xor     r8d, r8d; dwMessageId
0x180014191  mov     [r11-48h], rax
0x180014195  mov     ecx, 500h; dwFlags
0x18001419a  lea     rax, [r11-30h]
0x18001419e  mov     [rsp+78h+nSize], edi; nSize
0x1800141a2  mov     [r11-58h], rax
0x1800141a6  call    cs:__imp_FormatMessageW
0x1800141ac  mov     rdx, [rsp+78h+lpBuffer]; lpBuffer
0x1800141b1  test    rdx, rdx
0x1800141b4  jz      short loc_1800141E4
0x1800141b6  inc     rbx
0x1800141b9  cmp     [rdx+rbx*2], di
0x1800141bd  jnz     short loc_1800141B6
0x1800141bf  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hFile
0x1800141c6  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800141cb  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800141ce  mov     [rsp+78h+lpOverlapped], rdi; lpOverlapped
0x1800141d3  call    cs:__imp_WriteFile
0x1800141d9  mov     rcx, [rsp+78h+lpBuffer]; hMem
0x1800141de  call    cs:__imp_LocalFree
0x1800141e4  add     rsp, 68h
0x1800141e8  pop     rdi
0x1800141e9  pop     rbx
0x1800141ea  retn
```
