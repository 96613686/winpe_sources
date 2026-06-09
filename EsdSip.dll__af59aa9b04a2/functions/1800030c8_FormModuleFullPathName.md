# FormModuleFullPathName

- ea: `0x1800030c8`
- end: `0x1800031f3`
- name: `FormModuleFullPathName`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800028d0`

## callees

- `0x1800030c8`
- `0x1800032ae`
- `0x1800032e0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000318f`
- `KERNEL32!SetLastError` at `0x1800031a8`
- `KERNEL32!SetLastError` at `0x1800031c2`
- `KERNEL32!SetLastError` at `0x18000318f`
- `KERNEL32!SetLastError` at `0x1800031a8`
- `KERNEL32!SetLastError` at `0x1800031c2`
- `KERNEL32!GetProcessHeap` at `0x18000314f`
- `KERNEL32!GetProcessHeap` at `0x18000314f`
- `KERNEL32!GetLastError` at `0x180003185`
- `KERNEL32!GetLastError` at `0x1800031ae`
- `KERNEL32!GetLastError` at `0x180003185`
- `KERNEL32!GetLastError` at `0x1800031ae`
- `KERNEL32!GetFullPathNameW` at `0x18000313e`
- `KERNEL32!GetFullPathNameW` at `0x18000317b`
- `KERNEL32!GetFullPathNameW` at `0x18000313e`
- `KERNEL32!GetFullPathNameW` at `0x18000317b`
- `KERNEL32!GetModuleFileNameW` at `0x180003118`
- `KERNEL32!GetModuleFileNameW` at `0x180003118`
- `KERNEL32!HeapAlloc` at `0x18000315e`
- `KERNEL32!HeapAlloc` at `0x18000315e`

## pseudocode

```c
WCHAR *__fastcall FormModuleFullPathName(__int64 a1, LPWSTR *a2)
{
  WCHAR *v3; // rbx
  DWORD v4; // edi
  DWORD FullPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v7; // rax
  DWORD LastError; // esi
  WCHAR Filename[264]; // [rsp+20h] [rbp-238h] BYREF

  v3 = 0;
  memset_0(Filename, 0, 0x208u);
  if ( GetModuleFileNameW(*(HMODULE *)g_pgSubject.Data4, Filename, 0x104u) )
  {
    if ( Filename[0] )
    {
      v4 = 0;
      FullPathNameW = GetFullPathNameW(Filename, 0, 0, 0);
      if ( FullPathNameW )
      {
        ProcessHeap = GetProcessHeap();
        v7 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
        v3 = v7;
        if ( !v7 )
        {
          LastError = 14;
LABEL_7:
          SetLastError(LastError);
          if ( v3 )
            goto LABEL_13;
          goto LABEL_11;
        }
        LastError = 0;
        if ( GetFullPathNameW(Filename, FullPathNameW, v7, a2) )
          goto LABEL_7;
      }
      LastError = GetLastError();
      goto LABEL_7;
    }
    SetLastError(0x57u);
  }
LABEL_11:
  v4 = GetLastError();
  if ( !v4 )
    v4 = 31;
LABEL_13:
  SetLastError(v4);
  return v3;
}

```

## disassembly

```asm
0x1800030c8  mov     [rsp+arg_0], rbx
0x1800030cd  mov     [rsp+arg_10], rbp
0x1800030d2  push    rsi
0x1800030d3  push    rdi
0x1800030d4  push    r14
0x1800030d6  sub     rsp, 240h
0x1800030dd  mov     rax, cs:__security_cookie
0x1800030e4  xor     rax, rsp
0x1800030e7  mov     [rsp+258h+var_28], rax
0x1800030ef  mov     r14, rdx
0x1800030f2  lea     rcx, [rsp+258h+Filename]; void *
0x1800030f7  xor     edx, edx; Val
0x1800030f9  mov     r8d, 208h; Size
0x1800030ff  xor     ebx, ebx
0x180003101  call    memset_0
0x180003106  mov     rcx, qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data4; hModule
0x18000310d  lea     rdx, [rsp+258h+Filename]; lpFilename
0x180003112  mov     r8d, 104h; nSize
0x180003118  call    cs:__imp_GetModuleFileNameW
0x18000311e  test    eax, eax
0x180003120  jz      loc_1800031AE
0x180003126  xor     eax, eax
0x180003128  cmp     ax, [rsp+258h+Filename]
0x18000312d  jz      short loc_1800031A3
0x18000312f  xor     r9d, r9d; lpFilePart
0x180003132  lea     rcx, [rsp+258h+Filename]; lpFileName
0x180003137  xor     r8d, r8d; lpBuffer
0x18000313a  xor     edx, edx; nBufferLength
0x18000313c  xor     edi, edi
0x18000313e  call    cs:__imp_GetFullPathNameW
0x180003144  mov     ebp, eax
0x180003146  test    eax, eax
0x180003148  jz      short loc_180003185
0x18000314a  mov     ebx, ebp
0x18000314c  add     rbx, rbx
0x18000314f  call    cs:__imp_GetProcessHeap
0x180003155  mov     r8, rbx; dwBytes
0x180003158  lea     edx, [rdi+8]; dwFlags
0x18000315b  mov     rcx, rax; hHeap
0x18000315e  call    cs:__imp_HeapAlloc
0x180003164  mov     rbx, rax
0x180003167  test    rax, rax
0x18000316a  jz      short loc_18000319C
0x18000316c  mov     r9, r14; lpFilePart
0x18000316f  lea     rcx, [rsp+258h+Filename]; lpFileName
0x180003174  mov     r8, rax; lpBuffer
0x180003177  mov     edx, ebp; nBufferLength
0x180003179  xor     esi, esi
0x18000317b  call    cs:__imp_GetFullPathNameW
0x180003181  test    eax, eax
0x180003183  jnz     short loc_18000318D
0x180003185  call    cs:__imp_GetLastError
0x18000318b  mov     esi, eax
0x18000318d  mov     ecx, esi; dwErrCode
0x18000318f  call    cs:__imp_SetLastError
0x180003195  test    rbx, rbx
0x180003198  jnz     short loc_1800031C0
0x18000319a  jmp     short loc_1800031AE
0x18000319c  mov     esi, 0Eh
0x1800031a1  jmp     short loc_18000318D
0x1800031a3  mov     ecx, 57h ; 'W'; dwErrCode
0x1800031a8  call    cs:__imp_SetLastError
0x1800031ae  call    cs:__imp_GetLastError
0x1800031b4  mov     edi, eax
0x1800031b6  mov     eax, 1Fh
0x1800031bb  test    edi, edi
0x1800031bd  cmovz   edi, eax
0x1800031c0  mov     ecx, edi; dwErrCode
0x1800031c2  call    cs:__imp_SetLastError
0x1800031c8  mov     rax, rbx
0x1800031cb  mov     rcx, [rsp+258h+var_28]
0x1800031d3  xor     rcx, rsp; StackCookie
0x1800031d6  call    __security_check_cookie
0x1800031db  lea     r11, [rsp+258h+var_18]
0x1800031e3  mov     rbx, [r11+20h]
0x1800031e7  mov     rbp, [r11+30h]
0x1800031eb  mov     rsp, r11
0x1800031ee  pop     r14
0x1800031f0  pop     rdi
0x1800031f1  pop     rsi
0x1800031f2  retn
```
