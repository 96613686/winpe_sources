# GetCurrDirectory

- ea: `0x18005fbac`
- end: `0x18005fc62`
- name: `GetCurrDirectory`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800611b8`

## callees

- `0x18005fbac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fbe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fbe1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fbd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fc12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fbd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fc12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fc20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fc20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fc00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fc37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fc00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fc37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fc49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fc49`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18005fbbf`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18005fbf6`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18005fbbf`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18005fbf6`

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
0x18005fbac  mov     [rsp+arg_0], rbx
0x18005fbb1  mov     [rsp+arg_8], rsi
0x18005fbb6  push    rdi
0x18005fbb7  sub     rsp, 20h
0x18005fbbb  xor     edx, edx; lpBuffer
0x18005fbbd  xor     ecx, ecx; nBufferLength
0x18005fbbf  call    cs:__imp_GetCurrentDirectoryW
0x18005fbc5  mov     esi, eax
0x18005fbc7  test    eax, eax
0x18005fbc9  jz      short loc_18005FC35
0x18005fbcb  mov     ebx, esi
0x18005fbcd  add     rbx, rbx
0x18005fbd0  call    cs:__imp_GetProcessHeap
0x18005fbd6  mov     r8, rbx; dwBytes
0x18005fbd9  mov     edx, 8; dwFlags
0x18005fbde  mov     rcx, rax; hHeap
0x18005fbe1  call    cs:__imp_HeapAlloc
0x18005fbe7  mov     rdi, rax
0x18005fbea  test    rax, rax
0x18005fbed  jz      short loc_18005FC2E
0x18005fbef  mov     rdx, rax; lpBuffer
0x18005fbf2  mov     ecx, esi; nBufferLength
0x18005fbf4  xor     ebx, ebx
0x18005fbf6  call    cs:__imp_GetCurrentDirectoryW
0x18005fbfc  test    eax, eax
0x18005fbfe  jnz     short loc_18005FC47
0x18005fc00  call    cs:__imp_GetLastError
0x18005fc06  mov     ebx, eax
0x18005fc08  mov     eax, 1Fh
0x18005fc0d  test    ebx, ebx
0x18005fc0f  cmovz   ebx, eax
0x18005fc12  call    cs:__imp_GetProcessHeap
0x18005fc18  mov     r8, rdi; lpMem
0x18005fc1b  xor     edx, edx; dwFlags
0x18005fc1d  mov     rcx, rax; hHeap
0x18005fc20  call    cs:__imp_HeapFree
0x18005fc26  test    eax, eax
0x18005fc28  jz      short loc_18005FC47
0x18005fc2a  xor     edi, edi
0x18005fc2c  jmp     short loc_18005FC47
0x18005fc2e  mov     ebx, 0Eh
0x18005fc33  jmp     short loc_18005FC47
0x18005fc35  xor     edi, edi
0x18005fc37  call    cs:__imp_GetLastError
0x18005fc3d  mov     ebx, eax
0x18005fc3f  lea     eax, [rdi+1Fh]
0x18005fc42  test    ebx, ebx
0x18005fc44  cmovz   ebx, eax
0x18005fc47  mov     ecx, ebx; dwErrCode
0x18005fc49  call    cs:__imp_SetLastError
0x18005fc4f  mov     rbx, [rsp+28h+arg_0]
0x18005fc54  mov     rax, rdi
0x18005fc57  mov     rsi, [rsp+28h+arg_8]
0x18005fc5c  add     rsp, 20h
0x18005fc60  pop     rdi
0x18005fc61  retn
```
