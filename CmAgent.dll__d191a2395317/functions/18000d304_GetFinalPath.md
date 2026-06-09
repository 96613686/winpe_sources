# GetFinalPath

- ea: `0x18000d304`
- end: `0x18000d456`
- name: `GetFinalPath`
- size: `338`
- prototype: `__int64 __fastcall(HANDLE hFile, PVOID *, DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000d268`
- `0x18000d80c`

## callees

- `0x18000d304`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d36e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d36e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d333`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d333`
- `ntdll!RtlAllocateHeap` at `0x18000d39b`
- `ntdll!RtlAllocateHeap` at `0x18000d39b`
- `ntdll!RtlFreeHeap` at `0x18000d3d3`
- `ntdll!RtlFreeHeap` at `0x18000d434`
- `ntdll!RtlFreeHeap` at `0x18000d3d3`
- `ntdll!RtlFreeHeap` at `0x18000d434`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000d34b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000d34b`

## pseudocode

```c
__int64 __fastcall GetFinalPath(HANDLE hFile, PVOID *a2, DWORD *a3)
{
  WCHAR *Heap; // rdi
  char v7; // si
  DWORD v8; // ebp
  DWORD FinalPathNameByHandleW; // ebp
  int v10; // eax
  unsigned int v11; // ebx
  signed int LastError; // eax
  int v13; // eax

  if ( !a2 )
    __int2c();
  if ( !a3 )
    __int2c();
  Heap = (WCHAR *)*a2;
  v7 = 0;
  v8 = *a3;
  while ( 1 )
  {
    SetLastError(0);
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, Heap, v8, 0);
    if ( FinalPathNameByHandleW )
    {
      if ( GetLastError() != 8 )
        break;
    }
    if ( GetLastError() != 8 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    if ( v7 )
    {
      v11 = -2147418113;
LABEL_22:
      if ( Heap )
      {
        if ( v7 )
        {
          LOBYTE(v13) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          if ( !v13 )
            __int2c();
        }
      }
      return v11;
    }
    v8 = FinalPathNameByHandleW + 1;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * v8);
    if ( !Heap )
      return (unsigned int)-2147024882;
    v7 = 1;
  }
  if ( v7 )
  {
    if ( *a2 )
    {
      LOBYTE(v10) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a2);
      if ( !v10 )
        __int2c();
    }
    *a2 = Heap;
    *a3 = FinalPathNameByHandleW;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d304  push    rbx
0x18000d306  push    rbp
0x18000d307  push    rsi
0x18000d308  push    rdi
0x18000d309  push    r14
0x18000d30b  push    r15
0x18000d30d  sub     rsp, 28h
0x18000d311  mov     r14, r8
0x18000d314  mov     rbx, rdx
0x18000d317  mov     r15, rcx
0x18000d31a  test    rdx, rdx
0x18000d31d  jnz     short loc_18000D321
0x18000d31f  int     2Ch; Windows NT - assertion failure
0x18000d321  test    r14, r14
0x18000d324  jnz     short loc_18000D328
0x18000d326  int     2Ch; Windows NT - assertion failure
0x18000d328  mov     rdi, [rdx]
0x18000d32b  xor     sil, sil
0x18000d32e  mov     ebp, [r8]
0x18000d331  xor     ecx, ecx; dwErrCode
0x18000d333  call    cs:__imp_SetLastError
0x18000d33a  nop     dword ptr [rax+rax+00h]
0x18000d33f  xor     r9d, r9d; dwFlags
0x18000d342  mov     r8d, ebp; cchFilePath
0x18000d345  mov     rdx, rdi; lpszFilePath
0x18000d348  mov     rcx, r15; hFile
0x18000d34b  call    cs:__imp_GetFinalPathNameByHandleW
0x18000d352  nop     dword ptr [rax+rax+00h]
0x18000d357  mov     ebp, eax
0x18000d359  test    eax, eax
0x18000d35b  jz      short loc_18000D36E
0x18000d35d  call    cs:__imp_GetLastError
0x18000d364  nop     dword ptr [rax+rax+00h]
0x18000d369  cmp     eax, 8
0x18000d36c  jnz     short loc_18000D3B7
0x18000d36e  call    cs:__imp_GetLastError
0x18000d375  nop     dword ptr [rax+rax+00h]
0x18000d37a  cmp     eax, 8
0x18000d37d  jnz     short loc_18000D3FD
0x18000d37f  test    sil, sil
0x18000d382  jnz     short loc_18000D3F6
0x18000d384  mov     rcx, gs:60h
0x18000d38d  inc     ebp
0x18000d38f  mov     r8d, ebp
0x18000d392  xor     edx, edx; Flags
0x18000d394  add     r8, r8; Size
0x18000d397  mov     rcx, [rcx+30h]; HeapHandle
0x18000d39b  call    cs:__imp_RtlAllocateHeap
0x18000d3a2  nop     dword ptr [rax+rax+00h]
0x18000d3a7  mov     rdi, rax
0x18000d3aa  test    rax, rax
0x18000d3ad  jz      short loc_18000D3EF
0x18000d3af  mov     sil, 1
0x18000d3b2  jmp     loc_18000D331
0x18000d3b7  test    sil, sil
0x18000d3ba  jz      short loc_18000D3EB
0x18000d3bc  mov     r8, [rbx]; P
0x18000d3bf  test    r8, r8
0x18000d3c2  jz      short loc_18000D3E5
0x18000d3c4  mov     rcx, gs:60h
0x18000d3cd  xor     edx, edx; Flags
0x18000d3cf  mov     rcx, [rcx+30h]; HeapHandle
0x18000d3d3  call    cs:__imp_RtlFreeHeap
0x18000d3da  nop     dword ptr [rax+rax+00h]
0x18000d3df  test    eax, eax
0x18000d3e1  jnz     short loc_18000D3E5
0x18000d3e3  int     2Ch; Windows NT - assertion failure
0x18000d3e5  mov     [rbx], rdi
0x18000d3e8  mov     [r14], ebp
0x18000d3eb  xor     ebx, ebx
0x18000d3ed  jmp     short loc_18000D446
0x18000d3ef  mov     ebx, 8007000Eh
0x18000d3f4  jmp     short loc_18000D446
0x18000d3f6  mov     ebx, 8000FFFFh
0x18000d3fb  jmp     short loc_18000D418
0x18000d3fd  call    cs:__imp_GetLastError
0x18000d404  nop     dword ptr [rax+rax+00h]
0x18000d409  mov     ebx, eax
0x18000d40b  test    eax, eax
0x18000d40d  jle     short loc_18000D418
0x18000d40f  movzx   ebx, ax
0x18000d412  or      ebx, 80070000h
0x18000d418  test    rdi, rdi
0x18000d41b  jz      short loc_18000D446
0x18000d41d  test    sil, sil
0x18000d420  jz      short loc_18000D446
0x18000d422  mov     rcx, gs:60h
0x18000d42b  mov     r8, rdi; P
0x18000d42e  xor     edx, edx; Flags
0x18000d430  mov     rcx, [rcx+30h]; HeapHandle
0x18000d434  call    cs:__imp_RtlFreeHeap
0x18000d43b  nop     dword ptr [rax+rax+00h]
0x18000d440  test    eax, eax
0x18000d442  jnz     short loc_18000D446
0x18000d444  int     2Ch; Windows NT - assertion failure
0x18000d446  mov     eax, ebx
0x18000d448  add     rsp, 28h
0x18000d44c  pop     r15
0x18000d44e  pop     r14
0x18000d450  pop     rdi
0x18000d451  pop     rsi
0x18000d452  pop     rbp
0x18000d453  pop     rbx
0x18000d454  retn
```
