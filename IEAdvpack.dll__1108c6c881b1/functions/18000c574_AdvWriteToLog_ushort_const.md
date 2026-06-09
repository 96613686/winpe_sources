# AdvWriteToLog(ushort const *,...)

- ea: `0x18000c574`
- end: `0x18000c653`
- name: `?AdvWriteToLog@@YAXPEBGZZ`
- size: `223`
- prototype: `void(LPCVOID lpSource, ...)`
- caller_count: `26`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003be0`
- `0x180004880`
- `0x180005ea0`
- `0x1800079c0`
- `0x180008330`
- `0x180008644`
- `0x1800096f0`
- `0x180009c14`
- `0x18000b4b8`
- `0x18000b8f0`
- `0x18000bdb0`
- `0x18000c0c0`
- `0x18000c334`
- `0x18000d6cc`
- `0x18000d7ac`
- `0x18000d90c`
- `0x18000da30`
- `0x18000dbec`
- `0x18000e060`
- `0x18000f7b0`
- `0x180010050`
- `0x1800104c0`
- `0x180010ac0`
- `0x180010d50`
- `0x1800115b0`
- `0x180011940`

## callees

- `0x18000c574`
- `0x180017314`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000c63b`
- `KERNEL32!LocalFree` at `0x18000c645`
- `KERNEL32!LocalFree` at `0x18000c63b`
- `KERNEL32!LocalFree` at `0x18000c645`
- `KERNEL32!WriteFile` at `0x18000c632`
- `KERNEL32!WriteFile` at `0x18000c632`
- `KERNEL32!FormatMessageW` at `0x18000c5e7`
- `KERNEL32!FormatMessageW` at `0x18000c5e7`

## pseudocode

```c
void AdvWriteToLog(LPCVOID lpSource, ...)
{
  __int64 v1; // rbx
  int v2; // eax
  void *v3; // rdi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-18h] BYREF
  va_list v6; // [rsp+50h] [rbp-10h] BYREF
  LPCVOID lpBuffer; // [rsp+58h] [rbp-8h]
  va_list va; // [rsp+88h] [rbp+28h] BYREF

  va_start(va, lpSource);
  v1 = -1;
  v6 = 0;
  hMem = 0;
  NumberOfBytesWritten = 0;
  if ( g_hAdvLogFile != (HANDLE)-1LL )
  {
    va_copy(v6, va);
    FormatMessageW(0x500u, lpSource, 0, 0, (LPWSTR)&hMem, 0, &v6);
    if ( hMem )
    {
      lpBuffer = 0;
      v2 = ThunkToAnsi((LPCWCH)hMem);
      v3 = (void *)lpBuffer;
      if ( v2 >= 0 )
      {
        do
          ++v1;
        while ( *((_BYTE *)lpBuffer + v1) );
        WriteFile(g_hAdvLogFile, lpBuffer, v1, &NumberOfBytesWritten, 0);
      }
      LocalFree(v3);
      LocalFree(hMem);
    }
  }
}

```

## disassembly

```asm
0x18000c574  mov     r11, rsp
0x18000c577  mov     [r11+8], rcx
0x18000c57b  mov     [r11+10h], rdx
0x18000c57f  mov     [r11+18h], r8
0x18000c583  mov     [r11+20h], r9
0x18000c587  push    rbp
0x18000c588  push    rbx
0x18000c589  push    rdi
0x18000c58a  mov     rbp, rsp
0x18000c58d  sub     rsp, 60h
0x18000c591  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c595  mov     [rbp+var_10], 0
0x18000c59d  cmp     cs:?g_hAdvLogFile@@3PEAXEA, rbx; void * g_hAdvLogFile
0x18000c5a4  mov     [rbp+hMem], 0
0x18000c5ac  mov     [rbp+NumberOfBytesWritten], 0
0x18000c5b3  jz      loc_18000C64B
0x18000c5b9  lea     rax, [rbp+arg_8]
0x18000c5bd  mov     rdx, rcx; lpSource
0x18000c5c0  mov     [rbp+var_10], rax
0x18000c5c4  xor     r9d, r9d; dwLanguageId
0x18000c5c7  lea     rax, [rbp+var_10]
0x18000c5cb  xor     r8d, r8d; dwMessageId
0x18000c5ce  mov     [r11-48h], rax
0x18000c5d2  mov     ecx, 500h; dwFlags
0x18000c5d7  lea     rax, [rbp+hMem]
0x18000c5db  mov     [rsp+60h+nSize], 0; nSize
0x18000c5e3  mov     [r11-58h], rax
0x18000c5e7  call    cs:__imp_FormatMessageW
0x18000c5ed  mov     rcx, [rbp+hMem]; lpWideCharStr
0x18000c5f1  test    rcx, rcx
0x18000c5f4  jz      short loc_18000C64B
0x18000c5f6  lea     rdx, [rbp+lpBuffer]
0x18000c5fa  mov     [rbp+lpBuffer], 0
0x18000c602  call    ThunkToAnsi
0x18000c607  mov     rdi, [rbp+lpBuffer]
0x18000c60b  test    eax, eax
0x18000c60d  js      short loc_18000C638
0x18000c60f  inc     rbx
0x18000c612  cmp     byte ptr [rdi+rbx], 0
0x18000c616  jnz     short loc_18000C60F
0x18000c618  mov     rcx, cs:?g_hAdvLogFile@@3PEAXEA; hFile
0x18000c61f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000c623  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000c626  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x18000c62f  mov     rdx, rdi; lpBuffer
0x18000c632  call    cs:__imp_WriteFile
0x18000c638  mov     rcx, rdi; hMem
0x18000c63b  call    cs:__imp_LocalFree
0x18000c641  mov     rcx, [rbp+hMem]; hMem
0x18000c645  call    cs:__imp_LocalFree
0x18000c64b  add     rsp, 60h
0x18000c64f  pop     rdi
0x18000c650  pop     rbx
0x18000c651  pop     rbp
0x18000c652  retn
```
