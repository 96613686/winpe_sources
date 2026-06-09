# FormFullPathName

- ea: `0x18002eed8`
- end: `0x18002ef75`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002dbac`
- `0x18002f238`
- `0x180030590`

## callees

- `0x18002eed8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ef54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ef64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ef54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ef64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ef4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ef4a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002eef8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002ef35`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002eef8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002ef35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ef1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ef1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ef09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ef09`

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
0x18002eed8  push    rbx
0x18002eeda  push    rbp
0x18002eedb  push    rsi
0x18002eedc  push    rdi
0x18002eedd  sub     rsp, 28h
0x18002eee1  mov     rdi, rcx
0x18002eee4  test    rcx, rcx
0x18002eee7  jz      short loc_18002EF5F
0x18002eee9  xor     eax, eax
0x18002eeeb  cmp     ax, [rcx]
0x18002eeee  jz      short loc_18002EF5F
0x18002eef0  xor     r9d, r9d; lpFilePart
0x18002eef3  xor     r8d, r8d; lpBuffer
0x18002eef6  xor     edx, edx; nBufferLength
0x18002eef8  call    cs:__imp_GetFullPathNameW
0x18002eefe  mov     ebp, eax
0x18002ef00  test    eax, eax
0x18002ef02  jz      short loc_18002EF48
0x18002ef04  mov     ebx, ebp
0x18002ef06  add     rbx, rbx
0x18002ef09  call    cs:__imp_GetProcessHeap
0x18002ef0f  mov     r8, rbx; dwBytes
0x18002ef12  mov     edx, 8; dwFlags
0x18002ef17  mov     rcx, rax; hHeap
0x18002ef1a  call    cs:__imp_HeapAlloc
0x18002ef20  mov     rsi, rax
0x18002ef23  test    rax, rax
0x18002ef26  jz      short loc_18002EF41
0x18002ef28  xor     r9d, r9d; lpFilePart
0x18002ef2b  mov     r8, rax; lpBuffer
0x18002ef2e  mov     edx, ebp; nBufferLength
0x18002ef30  mov     rcx, rdi; lpFileName
0x18002ef33  xor     ebx, ebx
0x18002ef35  call    cs:__imp_GetFullPathNameW
0x18002ef3b  test    eax, eax
0x18002ef3d  jnz     short loc_18002EF52
0x18002ef3f  jmp     short loc_18002EF4A
0x18002ef41  mov     ebx, 0Eh
0x18002ef46  jmp     short loc_18002EF52
0x18002ef48  xor     esi, esi
0x18002ef4a  call    cs:__imp_GetLastError
0x18002ef50  mov     ebx, eax
0x18002ef52  mov     ecx, ebx; dwErrCode
0x18002ef54  call    cs:__imp_SetLastError
0x18002ef5a  mov     rax, rsi
0x18002ef5d  jmp     short loc_18002EF6C
0x18002ef5f  mov     ecx, 57h ; 'W'; dwErrCode
0x18002ef64  call    cs:__imp_SetLastError
0x18002ef6a  xor     eax, eax
0x18002ef6c  add     rsp, 28h
0x18002ef70  pop     rdi
0x18002ef71  pop     rsi
0x18002ef72  pop     rbp
0x18002ef73  pop     rbx
0x18002ef74  retn
```
