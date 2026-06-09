# FormFullPathName

- ea: `0x180049664`
- end: `0x180049701`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004997c`

## callees

- `0x180049664`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049695`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049695`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800496a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800496a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800496d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800496d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800496e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800496f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800496e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800496f0`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180049684`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800496c1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180049684`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800496c1`

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
0x180049664  push    rbx
0x180049666  push    rbp
0x180049667  push    rsi
0x180049668  push    rdi
0x180049669  sub     rsp, 28h
0x18004966d  mov     rdi, rcx
0x180049670  test    rcx, rcx
0x180049673  jz      short loc_1800496EB
0x180049675  xor     eax, eax
0x180049677  cmp     ax, [rcx]
0x18004967a  jz      short loc_1800496EB
0x18004967c  xor     r9d, r9d; lpFilePart
0x18004967f  xor     r8d, r8d; lpBuffer
0x180049682  xor     edx, edx; nBufferLength
0x180049684  call    cs:__imp_GetFullPathNameW
0x18004968a  mov     ebp, eax
0x18004968c  test    eax, eax
0x18004968e  jz      short loc_1800496D4
0x180049690  mov     ebx, ebp
0x180049692  add     rbx, rbx
0x180049695  call    cs:__imp_GetProcessHeap
0x18004969b  mov     r8, rbx; dwBytes
0x18004969e  mov     edx, 8; dwFlags
0x1800496a3  mov     rcx, rax; hHeap
0x1800496a6  call    cs:__imp_HeapAlloc
0x1800496ac  mov     rsi, rax
0x1800496af  test    rax, rax
0x1800496b2  jz      short loc_1800496CD
0x1800496b4  xor     r9d, r9d; lpFilePart
0x1800496b7  mov     r8, rax; lpBuffer
0x1800496ba  mov     edx, ebp; nBufferLength
0x1800496bc  mov     rcx, rdi; lpFileName
0x1800496bf  xor     ebx, ebx
0x1800496c1  call    cs:__imp_GetFullPathNameW
0x1800496c7  test    eax, eax
0x1800496c9  jnz     short loc_1800496DE
0x1800496cb  jmp     short loc_1800496D6
0x1800496cd  mov     ebx, 0Eh
0x1800496d2  jmp     short loc_1800496DE
0x1800496d4  xor     esi, esi
0x1800496d6  call    cs:__imp_GetLastError
0x1800496dc  mov     ebx, eax
0x1800496de  mov     ecx, ebx; dwErrCode
0x1800496e0  call    cs:__imp_SetLastError
0x1800496e6  mov     rax, rsi
0x1800496e9  jmp     short loc_1800496F8
0x1800496eb  mov     ecx, 57h ; 'W'; dwErrCode
0x1800496f0  call    cs:__imp_SetLastError
0x1800496f6  xor     eax, eax
0x1800496f8  add     rsp, 28h
0x1800496fc  pop     rdi
0x1800496fd  pop     rsi
0x1800496fe  pop     rbp
0x1800496ff  pop     rbx
0x180049700  retn
```
