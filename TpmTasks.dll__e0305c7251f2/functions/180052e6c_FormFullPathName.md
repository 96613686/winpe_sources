# FormFullPathName

- ea: `0x180052e6c`
- end: `0x180052f09`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180053234`

## callees

- `0x180052e6c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180052e8c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180052ec9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180052e8c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180052ec9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052e9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052e9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052eae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052eae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ee8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ee8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ede`

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
0x180052e6c  push    rbx
0x180052e6e  push    rbp
0x180052e6f  push    rsi
0x180052e70  push    rdi
0x180052e71  sub     rsp, 28h
0x180052e75  mov     rdi, rcx
0x180052e78  test    rcx, rcx
0x180052e7b  jz      short loc_180052EF3
0x180052e7d  xor     eax, eax
0x180052e7f  cmp     ax, [rcx]
0x180052e82  jz      short loc_180052EF3
0x180052e84  xor     r9d, r9d; lpFilePart
0x180052e87  xor     r8d, r8d; lpBuffer
0x180052e8a  xor     edx, edx; nBufferLength
0x180052e8c  call    cs:__imp_GetFullPathNameW
0x180052e92  mov     ebp, eax
0x180052e94  test    eax, eax
0x180052e96  jz      short loc_180052EDC
0x180052e98  mov     ebx, ebp
0x180052e9a  add     rbx, rbx
0x180052e9d  call    cs:__imp_GetProcessHeap
0x180052ea3  mov     r8, rbx; dwBytes
0x180052ea6  mov     edx, 8; dwFlags
0x180052eab  mov     rcx, rax; hHeap
0x180052eae  call    cs:__imp_HeapAlloc
0x180052eb4  mov     rsi, rax
0x180052eb7  test    rax, rax
0x180052eba  jz      short loc_180052ED5
0x180052ebc  xor     r9d, r9d; lpFilePart
0x180052ebf  mov     r8, rax; lpBuffer
0x180052ec2  mov     edx, ebp; nBufferLength
0x180052ec4  mov     rcx, rdi; lpFileName
0x180052ec7  xor     ebx, ebx
0x180052ec9  call    cs:__imp_GetFullPathNameW
0x180052ecf  test    eax, eax
0x180052ed1  jnz     short loc_180052EE6
0x180052ed3  jmp     short loc_180052EDE
0x180052ed5  mov     ebx, 0Eh
0x180052eda  jmp     short loc_180052EE6
0x180052edc  xor     esi, esi
0x180052ede  call    cs:__imp_GetLastError
0x180052ee4  mov     ebx, eax
0x180052ee6  mov     ecx, ebx; dwErrCode
0x180052ee8  call    cs:__imp_SetLastError
0x180052eee  mov     rax, rsi
0x180052ef1  jmp     short loc_180052F00
0x180052ef3  mov     ecx, 57h ; 'W'; dwErrCode
0x180052ef8  call    cs:__imp_SetLastError
0x180052efe  xor     eax, eax
0x180052f00  add     rsp, 28h
0x180052f04  pop     rdi
0x180052f05  pop     rsi
0x180052f06  pop     rbp
0x180052f07  pop     rbx
0x180052f08  retn
```
