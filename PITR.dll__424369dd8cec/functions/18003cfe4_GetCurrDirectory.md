# GetCurrDirectory

- ea: `0x18003cfe4`
- end: `0x18003d09a`
- name: `GetCurrDirectory`
- size: `182`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003be78`

## callees

- `0x18003cfe4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d04a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d04a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d019`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d058`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d058`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d081`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d06f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003cff7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003d02e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003cff7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003d02e`

## pseudocode

```c
WCHAR *GetCurrDirectory()
{
  DWORD CurrentDirectoryW; // esi
  HANDLE ProcessHeap; // rax
  WCHAR *v2; // rax
  WCHAR *v3; // rdi
  DWORD LastError; // ebx
  HANDLE v5; // rax

  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  if ( CurrentDirectoryW )
  {
    ProcessHeap = GetProcessHeap();
    v2 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * CurrentDirectoryW);
    v3 = v2;
    if ( v2 )
    {
      LastError = 0;
      if ( !GetCurrentDirectoryW(CurrentDirectoryW, v2) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 31;
        v5 = GetProcessHeap();
        if ( HeapFree(v5, 0, v3) )
          v3 = 0;
      }
    }
    else
    {
      LastError = 14;
    }
  }
  else
  {
    v3 = 0;
    LastError = GetLastError();
    if ( !LastError )
      LastError = 31;
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x18003cfe4  mov     [rsp+arg_0], rbx
0x18003cfe9  mov     [rsp+arg_8], rsi
0x18003cfee  push    rdi
0x18003cfef  sub     rsp, 20h
0x18003cff3  xor     edx, edx; lpBuffer
0x18003cff5  xor     ecx, ecx; nBufferLength
0x18003cff7  call    cs:__imp_GetCurrentDirectoryW
0x18003cffd  mov     esi, eax
0x18003cfff  test    eax, eax
0x18003d001  jz      short loc_18003D06D
0x18003d003  mov     ebx, esi
0x18003d005  add     rbx, rbx
0x18003d008  call    cs:__imp_GetProcessHeap
0x18003d00e  mov     r8, rbx; dwBytes
0x18003d011  mov     edx, 8; dwFlags
0x18003d016  mov     rcx, rax; hHeap
0x18003d019  call    cs:__imp_HeapAlloc
0x18003d01f  mov     rdi, rax
0x18003d022  test    rax, rax
0x18003d025  jz      short loc_18003D066
0x18003d027  mov     rdx, rax; lpBuffer
0x18003d02a  mov     ecx, esi; nBufferLength
0x18003d02c  xor     ebx, ebx
0x18003d02e  call    cs:__imp_GetCurrentDirectoryW
0x18003d034  test    eax, eax
0x18003d036  jnz     short loc_18003D07F
0x18003d038  call    cs:__imp_GetLastError
0x18003d03e  mov     ebx, eax
0x18003d040  mov     eax, 1Fh
0x18003d045  test    ebx, ebx
0x18003d047  cmovz   ebx, eax
0x18003d04a  call    cs:__imp_GetProcessHeap
0x18003d050  mov     r8, rdi; lpMem
0x18003d053  xor     edx, edx; dwFlags
0x18003d055  mov     rcx, rax; hHeap
0x18003d058  call    cs:__imp_HeapFree
0x18003d05e  test    eax, eax
0x18003d060  jz      short loc_18003D07F
0x18003d062  xor     edi, edi
0x18003d064  jmp     short loc_18003D07F
0x18003d066  mov     ebx, 0Eh
0x18003d06b  jmp     short loc_18003D07F
0x18003d06d  xor     edi, edi
0x18003d06f  call    cs:__imp_GetLastError
0x18003d075  mov     ebx, eax
0x18003d077  lea     eax, [rdi+1Fh]
0x18003d07a  test    ebx, ebx
0x18003d07c  cmovz   ebx, eax
0x18003d07f  mov     ecx, ebx; dwErrCode
0x18003d081  call    cs:__imp_SetLastError
0x18003d087  mov     rbx, [rsp+28h+arg_0]
0x18003d08c  mov     rax, rdi
0x18003d08f  mov     rsi, [rsp+28h+arg_8]
0x18003d094  add     rsp, 20h
0x18003d098  pop     rdi
0x18003d099  retn
```
