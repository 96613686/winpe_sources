# FormFullPathName

- ea: `0x18003ce30`
- end: `0x18003cecd`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18003bfb0`
- `0x18003c3b8`
- `0x18003d238`
- `0x18003e3e0`

## callees

- `0x18003ce30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003ce50`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003ce8d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003ce50`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003ce8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ce61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ce61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ce72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ce72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ceac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cebc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ceac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cea2`

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
0x18003ce30  push    rbx
0x18003ce32  push    rbp
0x18003ce33  push    rsi
0x18003ce34  push    rdi
0x18003ce35  sub     rsp, 28h
0x18003ce39  mov     rdi, rcx
0x18003ce3c  test    rcx, rcx
0x18003ce3f  jz      short loc_18003CEB7
0x18003ce41  xor     eax, eax
0x18003ce43  cmp     ax, [rcx]
0x18003ce46  jz      short loc_18003CEB7
0x18003ce48  xor     r9d, r9d; lpFilePart
0x18003ce4b  xor     r8d, r8d; lpBuffer
0x18003ce4e  xor     edx, edx; nBufferLength
0x18003ce50  call    cs:__imp_GetFullPathNameW
0x18003ce56  mov     ebp, eax
0x18003ce58  test    eax, eax
0x18003ce5a  jz      short loc_18003CEA0
0x18003ce5c  mov     ebx, ebp
0x18003ce5e  add     rbx, rbx
0x18003ce61  call    cs:__imp_GetProcessHeap
0x18003ce67  mov     r8, rbx; dwBytes
0x18003ce6a  mov     edx, 8; dwFlags
0x18003ce6f  mov     rcx, rax; hHeap
0x18003ce72  call    cs:__imp_HeapAlloc
0x18003ce78  mov     rsi, rax
0x18003ce7b  test    rax, rax
0x18003ce7e  jz      short loc_18003CE99
0x18003ce80  xor     r9d, r9d; lpFilePart
0x18003ce83  mov     r8, rax; lpBuffer
0x18003ce86  mov     edx, ebp; nBufferLength
0x18003ce88  mov     rcx, rdi; lpFileName
0x18003ce8b  xor     ebx, ebx
0x18003ce8d  call    cs:__imp_GetFullPathNameW
0x18003ce93  test    eax, eax
0x18003ce95  jnz     short loc_18003CEAA
0x18003ce97  jmp     short loc_18003CEA2
0x18003ce99  mov     ebx, 0Eh
0x18003ce9e  jmp     short loc_18003CEAA
0x18003cea0  xor     esi, esi
0x18003cea2  call    cs:__imp_GetLastError
0x18003cea8  mov     ebx, eax
0x18003ceaa  mov     ecx, ebx; dwErrCode
0x18003ceac  call    cs:__imp_SetLastError
0x18003ceb2  mov     rax, rsi
0x18003ceb5  jmp     short loc_18003CEC4
0x18003ceb7  mov     ecx, 57h ; 'W'; dwErrCode
0x18003cebc  call    cs:__imp_SetLastError
0x18003cec2  xor     eax, eax
0x18003cec4  add     rsp, 28h
0x18003cec8  pop     rdi
0x18003cec9  pop     rsi
0x18003ceca  pop     rbp
0x18003cecb  pop     rbx
0x18003cecc  retn
```
