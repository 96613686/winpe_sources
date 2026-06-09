# FormFullPathName

- ea: `0x180064a7c`
- end: `0x180064b4c`
- name: `FormFullPathName`
- size: `208`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180064e8c`
- `0x1800666b4`
- `0x180066b38`
- `0x180067990`

## callees

- `0x180064a7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064ad2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064ad2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064abb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064b1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064b34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064b1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064b34`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180064aa4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180064af3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180064aa4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180064af3`

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
0x180064a7c  push    rbx
0x180064a7e  push    rbp
0x180064a7f  push    rsi
0x180064a80  push    rdi
0x180064a81  sub     rsp, 28h
0x180064a85  mov     rdi, rcx
0x180064a88  test    rcx, rcx
0x180064a8b  jz      loc_180064B2F
0x180064a91  xor     eax, eax
0x180064a93  cmp     ax, [rcx]
0x180064a96  jz      loc_180064B2F
0x180064a9c  xor     r9d, r9d; lpFilePart
0x180064a9f  xor     r8d, r8d; lpBuffer
0x180064aa2  xor     edx, edx; nBufferLength
0x180064aa4  call    cs:__imp_GetFullPathNameW
0x180064aab  nop     dword ptr [rax+rax+00h]
0x180064ab0  mov     ebp, eax
0x180064ab2  test    eax, eax
0x180064ab4  jz      short loc_180064B0C
0x180064ab6  mov     ebx, ebp
0x180064ab8  add     rbx, rbx
0x180064abb  call    cs:__imp_GetProcessHeap
0x180064ac2  nop     dword ptr [rax+rax+00h]
0x180064ac7  mov     r8, rbx; dwBytes
0x180064aca  mov     edx, 8; dwFlags
0x180064acf  mov     rcx, rax; hHeap
0x180064ad2  call    cs:__imp_HeapAlloc
0x180064ad9  nop     dword ptr [rax+rax+00h]
0x180064ade  mov     rsi, rax
0x180064ae1  test    rax, rax
0x180064ae4  jz      short loc_180064B05
0x180064ae6  xor     r9d, r9d; lpFilePart
0x180064ae9  mov     r8, rax; lpBuffer
0x180064aec  mov     edx, ebp; nBufferLength
0x180064aee  mov     rcx, rdi; lpFileName
0x180064af1  xor     ebx, ebx
0x180064af3  call    cs:__imp_GetFullPathNameW
0x180064afa  nop     dword ptr [rax+rax+00h]
0x180064aff  test    eax, eax
0x180064b01  jnz     short loc_180064B1C
0x180064b03  jmp     short loc_180064B0E
0x180064b05  mov     ebx, 0Eh
0x180064b0a  jmp     short loc_180064B1C
0x180064b0c  xor     esi, esi
0x180064b0e  call    cs:__imp_GetLastError
0x180064b15  nop     dword ptr [rax+rax+00h]
0x180064b1a  mov     ebx, eax
0x180064b1c  mov     ecx, ebx; dwErrCode
0x180064b1e  call    cs:__imp_SetLastError
0x180064b25  nop     dword ptr [rax+rax+00h]
0x180064b2a  mov     rax, rsi
0x180064b2d  jmp     short loc_180064B42
0x180064b2f  mov     ecx, 57h ; 'W'; dwErrCode
0x180064b34  call    cs:__imp_SetLastError
0x180064b3b  nop     dword ptr [rax+rax+00h]
0x180064b40  xor     eax, eax
0x180064b42  add     rsp, 28h
0x180064b46  pop     rdi
0x180064b47  pop     rsi
0x180064b48  pop     rbp
0x180064b49  pop     rbx
0x180064b4a  retn
```
