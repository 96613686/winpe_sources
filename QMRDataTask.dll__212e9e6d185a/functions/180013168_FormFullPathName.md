# FormFullPathName

- ea: `0x180013168`
- end: `0x180013205`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001331c`

## callees

- `0x180013168`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180013188`
- `KERNEL32!GetFullPathNameW` at `0x1800131c5`
- `KERNEL32!GetFullPathNameW` at `0x180013188`
- `KERNEL32!GetFullPathNameW` at `0x1800131c5`
- `KERNEL32!GetLastError` at `0x1800131da`
- `KERNEL32!GetLastError` at `0x1800131da`
- `KERNEL32!GetProcessHeap` at `0x180013199`
- `KERNEL32!GetProcessHeap` at `0x180013199`
- `KERNEL32!HeapAlloc` at `0x1800131aa`
- `KERNEL32!HeapAlloc` at `0x1800131aa`
- `KERNEL32!SetLastError` at `0x1800131e4`
- `KERNEL32!SetLastError` at `0x1800131f4`
- `KERNEL32!SetLastError` at `0x1800131e4`
- `KERNEL32!SetLastError` at `0x1800131f4`

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
0x180013168  push    rbx
0x18001316a  push    rbp
0x18001316b  push    rsi
0x18001316c  push    rdi
0x18001316d  sub     rsp, 28h
0x180013171  mov     rdi, rcx
0x180013174  test    rcx, rcx
0x180013177  jz      short loc_1800131EF
0x180013179  xor     eax, eax
0x18001317b  cmp     ax, [rcx]
0x18001317e  jz      short loc_1800131EF
0x180013180  xor     r9d, r9d; lpFilePart
0x180013183  xor     r8d, r8d; lpBuffer
0x180013186  xor     edx, edx; nBufferLength
0x180013188  call    cs:__imp_GetFullPathNameW
0x18001318e  mov     ebp, eax
0x180013190  test    eax, eax
0x180013192  jz      short loc_1800131D8
0x180013194  mov     ebx, ebp
0x180013196  add     rbx, rbx
0x180013199  call    cs:__imp_GetProcessHeap
0x18001319f  mov     r8, rbx; dwBytes
0x1800131a2  mov     edx, 8; dwFlags
0x1800131a7  mov     rcx, rax; hHeap
0x1800131aa  call    cs:__imp_HeapAlloc
0x1800131b0  mov     rsi, rax
0x1800131b3  test    rax, rax
0x1800131b6  jz      short loc_1800131D1
0x1800131b8  xor     r9d, r9d; lpFilePart
0x1800131bb  mov     r8, rax; lpBuffer
0x1800131be  mov     edx, ebp; nBufferLength
0x1800131c0  mov     rcx, rdi; lpFileName
0x1800131c3  xor     ebx, ebx
0x1800131c5  call    cs:__imp_GetFullPathNameW
0x1800131cb  test    eax, eax
0x1800131cd  jnz     short loc_1800131E2
0x1800131cf  jmp     short loc_1800131DA
0x1800131d1  mov     ebx, 0Eh
0x1800131d6  jmp     short loc_1800131E2
0x1800131d8  xor     esi, esi
0x1800131da  call    cs:__imp_GetLastError
0x1800131e0  mov     ebx, eax
0x1800131e2  mov     ecx, ebx; dwErrCode
0x1800131e4  call    cs:__imp_SetLastError
0x1800131ea  mov     rax, rsi
0x1800131ed  jmp     short loc_1800131FC
0x1800131ef  mov     ecx, 57h ; 'W'; dwErrCode
0x1800131f4  call    cs:__imp_SetLastError
0x1800131fa  xor     eax, eax
0x1800131fc  add     rsp, 28h
0x180013200  pop     rdi
0x180013201  pop     rsi
0x180013202  pop     rbp
0x180013203  pop     rbx
0x180013204  retn
```
