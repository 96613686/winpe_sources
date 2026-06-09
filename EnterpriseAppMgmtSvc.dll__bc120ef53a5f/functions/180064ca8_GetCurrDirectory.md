# GetCurrDirectory

- ea: `0x180064ca8`
- end: `0x180064d99`
- name: `GetCurrDirectory`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18006655c`

## callees

- `0x180064ca8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064ced`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064ced`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064cd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064d30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064cd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064d30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064d44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064d44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064d79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064d79`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180064cbb`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180064d08`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180064cbb`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180064d08`

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
0x180064ca8  mov     [rsp+arg_0], rbx
0x180064cad  mov     [rsp+arg_8], rsi
0x180064cb2  push    rdi
0x180064cb3  sub     rsp, 20h
0x180064cb7  xor     edx, edx; lpBuffer
0x180064cb9  xor     ecx, ecx; nBufferLength
0x180064cbb  call    cs:__imp_GetCurrentDirectoryW
0x180064cc2  nop     dword ptr [rax+rax+00h]
0x180064cc7  mov     esi, eax
0x180064cc9  test    eax, eax
0x180064ccb  jz      loc_180064D5F
0x180064cd1  mov     ebx, esi
0x180064cd3  add     rbx, rbx
0x180064cd6  call    cs:__imp_GetProcessHeap
0x180064cdd  nop     dword ptr [rax+rax+00h]
0x180064ce2  mov     r8, rbx; dwBytes
0x180064ce5  mov     edx, 8; dwFlags
0x180064cea  mov     rcx, rax; hHeap
0x180064ced  call    cs:__imp_HeapAlloc
0x180064cf4  nop     dword ptr [rax+rax+00h]
0x180064cf9  mov     rdi, rax
0x180064cfc  test    rax, rax
0x180064cff  jz      short loc_180064D58
0x180064d01  mov     rdx, rax; lpBuffer
0x180064d04  mov     ecx, esi; nBufferLength
0x180064d06  xor     ebx, ebx
0x180064d08  call    cs:__imp_GetCurrentDirectoryW
0x180064d0f  nop     dword ptr [rax+rax+00h]
0x180064d14  test    eax, eax
0x180064d16  jnz     short loc_180064D77
0x180064d18  call    cs:__imp_GetLastError
0x180064d1f  nop     dword ptr [rax+rax+00h]
0x180064d24  mov     ebx, eax
0x180064d26  mov     eax, 1Fh
0x180064d2b  test    ebx, ebx
0x180064d2d  cmovz   ebx, eax
0x180064d30  call    cs:__imp_GetProcessHeap
0x180064d37  nop     dword ptr [rax+rax+00h]
0x180064d3c  mov     r8, rdi; lpMem
0x180064d3f  xor     edx, edx; dwFlags
0x180064d41  mov     rcx, rax; hHeap
0x180064d44  call    cs:__imp_HeapFree
0x180064d4b  nop     dword ptr [rax+rax+00h]
0x180064d50  test    eax, eax
0x180064d52  jz      short loc_180064D77
0x180064d54  xor     edi, edi
0x180064d56  jmp     short loc_180064D77
0x180064d58  mov     ebx, 0Eh
0x180064d5d  jmp     short loc_180064D77
0x180064d5f  xor     edi, edi
0x180064d61  call    cs:__imp_GetLastError
0x180064d68  nop     dword ptr [rax+rax+00h]
0x180064d6d  mov     ebx, eax
0x180064d6f  lea     eax, [rdi+1Fh]
0x180064d72  test    ebx, ebx
0x180064d74  cmovz   ebx, eax
0x180064d77  mov     ecx, ebx; dwErrCode
0x180064d79  call    cs:__imp_SetLastError
0x180064d80  nop     dword ptr [rax+rax+00h]
0x180064d85  mov     rbx, [rsp+28h+arg_0]
0x180064d8a  mov     rax, rdi
0x180064d8d  mov     rsi, [rsp+28h+arg_8]
0x180064d92  add     rsp, 20h
0x180064d96  pop     rdi
0x180064d97  retn
```
