# FormFullPathName

- ea: `0x1801ab80c`
- end: `0x1801ab8dc`
- name: `FormFullPathName`
- size: `208`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801aba40`

## callees

- `0x1801ab80c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ab89e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ab89e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ab8ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ab8c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ab8ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ab8c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ab862`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ab862`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ab84b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ab84b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801ab834`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801ab883`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801ab834`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801ab883`

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
0x1801ab80c  push    rbx
0x1801ab80e  push    rbp
0x1801ab80f  push    rsi
0x1801ab810  push    rdi
0x1801ab811  sub     rsp, 28h
0x1801ab815  mov     rdi, rcx
0x1801ab818  test    rcx, rcx
0x1801ab81b  jz      loc_1801AB8BF
0x1801ab821  xor     eax, eax
0x1801ab823  cmp     ax, [rcx]
0x1801ab826  jz      loc_1801AB8BF
0x1801ab82c  xor     r9d, r9d; lpFilePart
0x1801ab82f  xor     r8d, r8d; lpBuffer
0x1801ab832  xor     edx, edx; nBufferLength
0x1801ab834  call    cs:__imp_GetFullPathNameW
0x1801ab83b  nop     dword ptr [rax+rax+00h]
0x1801ab840  mov     ebp, eax
0x1801ab842  test    eax, eax
0x1801ab844  jz      short loc_1801AB89C
0x1801ab846  mov     ebx, ebp
0x1801ab848  add     rbx, rbx
0x1801ab84b  call    cs:__imp_GetProcessHeap
0x1801ab852  nop     dword ptr [rax+rax+00h]
0x1801ab857  mov     r8, rbx; dwBytes
0x1801ab85a  mov     edx, 8; dwFlags
0x1801ab85f  mov     rcx, rax; hHeap
0x1801ab862  call    cs:__imp_HeapAlloc
0x1801ab869  nop     dword ptr [rax+rax+00h]
0x1801ab86e  mov     rsi, rax
0x1801ab871  test    rax, rax
0x1801ab874  jz      short loc_1801AB895
0x1801ab876  xor     r9d, r9d; lpFilePart
0x1801ab879  mov     r8, rax; lpBuffer
0x1801ab87c  mov     edx, ebp; nBufferLength
0x1801ab87e  mov     rcx, rdi; lpFileName
0x1801ab881  xor     ebx, ebx
0x1801ab883  call    cs:__imp_GetFullPathNameW
0x1801ab88a  nop     dword ptr [rax+rax+00h]
0x1801ab88f  test    eax, eax
0x1801ab891  jnz     short loc_1801AB8AC
0x1801ab893  jmp     short loc_1801AB89E
0x1801ab895  mov     ebx, 0Eh
0x1801ab89a  jmp     short loc_1801AB8AC
0x1801ab89c  xor     esi, esi
0x1801ab89e  call    cs:__imp_GetLastError
0x1801ab8a5  nop     dword ptr [rax+rax+00h]
0x1801ab8aa  mov     ebx, eax
0x1801ab8ac  mov     ecx, ebx; dwErrCode
0x1801ab8ae  call    cs:__imp_SetLastError
0x1801ab8b5  nop     dword ptr [rax+rax+00h]
0x1801ab8ba  mov     rax, rsi
0x1801ab8bd  jmp     short loc_1801AB8D2
0x1801ab8bf  mov     ecx, 57h ; 'W'; dwErrCode
0x1801ab8c4  call    cs:__imp_SetLastError
0x1801ab8cb  nop     dword ptr [rax+rax+00h]
0x1801ab8d0  xor     eax, eax
0x1801ab8d2  add     rsp, 28h
0x1801ab8d6  pop     rdi
0x1801ab8d7  pop     rsi
0x1801ab8d8  pop     rbp
0x1801ab8d9  pop     rbx
0x1801ab8da  retn
```
