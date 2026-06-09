# BfspCreateTokenPrivilegesInformation

- ea: `0x18004d118`
- end: `0x18004d20c`
- name: `BfspCreateTokenPrivilegesInformation`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004646c`
- `0x180049234`
- `0x18004b38c`

## callees

- `0x1800085d4`
- `0x18004cdd4`
- `0x18004d118`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d1fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d1fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d1ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d1ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d15a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d15a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d204`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1d2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18004d19c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18004d19c`

## pseudocode

```c
__int64 __fastcall BfspCreateTokenPrivilegesInformation(__int64 a1, unsigned int a2, int a3, unsigned int **a4)
{
  SIZE_T v8; // r14
  HANDLE ProcessHeap; // rax
  __int64 LastError; // rsi
  unsigned int *v11; // rax
  unsigned int *v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // rsi
  HANDLE v16; // rax

  v8 = 12LL * a2 + 4;
  ProcessHeap = GetProcessHeap();
  LODWORD(LastError) = 8;
  v11 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v8);
  v12 = v11;
  if ( !v11 )
  {
    v13 = 0;
LABEL_11:
    SetLastError(LastError);
    return v13;
  }
  v13 = 1;
  memset_0(v11, 0, v8);
  v14 = 0;
  *v12 = a2;
  if ( a2 )
  {
    while ( 1 )
    {
      v13 = LookupPrivilegeValueW(0, *(LPCWSTR *)(a1 + 8 * v14), (PLUID)&v12[3 * v14 + 1]);
      if ( !v13 )
        break;
      if ( a3 )
        v12[3 * v14 + 3] = 2;
      v14 = (unsigned int)(v14 + 1);
      if ( (unsigned int)v14 >= a2 )
        goto LABEL_8;
    }
    LastError = GetLastError();
    BfspLogMessage(4, L"Failed to lookup privelege! Error code = %#x", LastError);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v12);
    goto LABEL_11;
  }
LABEL_8:
  *a4 = v12;
  return v13;
}

```

## disassembly

```asm
0x18004d118  push    rbx
0x18004d11a  push    rbp
0x18004d11b  push    rsi
0x18004d11c  push    rdi
0x18004d11d  push    r12
0x18004d11f  push    r13
0x18004d121  push    r14
0x18004d123  push    r15
0x18004d125  sub     rsp, 28h
0x18004d129  mov     ebp, edx
0x18004d12b  mov     r15, r9
0x18004d12e  mov     r12d, r8d
0x18004d131  mov     r13, rcx
0x18004d134  lea     r10, ds:0[rbp*2]
0x18004d13c  add     r10, rbp
0x18004d13f  lea     r14, ds:4[r10*4]
0x18004d147  call    cs:__imp_GetProcessHeap
0x18004d14d  mov     esi, 8
0x18004d152  mov     r8, r14; dwBytes
0x18004d155  mov     rcx, rax; hHeap
0x18004d158  mov     edx, esi; dwFlags
0x18004d15a  call    cs:__imp_HeapAlloc
0x18004d160  mov     rdi, rax
0x18004d163  test    rax, rax
0x18004d166  jnz     short loc_18004D16F
0x18004d168  xor     ebx, ebx
0x18004d16a  jmp     loc_18004D202
0x18004d16f  mov     r8, r14; Size
0x18004d172  xor     edx, edx; Val
0x18004d174  mov     rcx, rdi; void *
0x18004d177  mov     ebx, 1
0x18004d17c  call    memset_0
0x18004d181  xor     esi, esi
0x18004d183  mov     [rdi], ebp
0x18004d185  test    ebp, ebp
0x18004d187  jz      short loc_18004D1BC
0x18004d189  mov     rdx, [r13+rsi*8+0]; lpName
0x18004d18e  lea     r14, [rsi+rsi*2]
0x18004d192  lea     r8, [rdi+4]
0x18004d196  xor     ecx, ecx; lpSystemName
0x18004d198  lea     r8, [r8+r14*4]; lpLuid
0x18004d19c  call    cs:__imp_LookupPrivilegeValueW
0x18004d1a2  mov     ebx, eax
0x18004d1a4  test    eax, eax
0x18004d1a6  jz      short loc_18004D1D2
0x18004d1a8  test    r12d, r12d
0x18004d1ab  jz      short loc_18004D1B6
0x18004d1ad  mov     dword ptr [rdi+r14*4+0Ch], 2
0x18004d1b6  inc     esi
0x18004d1b8  cmp     esi, ebp
0x18004d1ba  jb      short loc_18004D189
0x18004d1bc  mov     [r15], rdi
0x18004d1bf  mov     eax, ebx
0x18004d1c1  add     rsp, 28h
0x18004d1c5  pop     r15
0x18004d1c7  pop     r14
0x18004d1c9  pop     r13
0x18004d1cb  pop     r12
0x18004d1cd  pop     rdi
0x18004d1ce  pop     rsi
0x18004d1cf  pop     rbp
0x18004d1d0  pop     rbx
0x18004d1d1  retn
0x18004d1d2  call    cs:__imp_GetLastError
0x18004d1d8  lea     rdx, aFailedToLookup; "Failed to lookup privelege! Error code "...
0x18004d1df  mov     ecx, 4
0x18004d1e4  mov     r8d, eax
0x18004d1e7  mov     esi, eax
0x18004d1e9  call    BfspLogMessage
0x18004d1ee  call    cs:__imp_GetProcessHeap
0x18004d1f4  mov     r8, rdi; lpMem
0x18004d1f7  xor     edx, edx; dwFlags
0x18004d1f9  mov     rcx, rax; hHeap
0x18004d1fc  call    cs:__imp_HeapFree
0x18004d202  mov     ecx, esi; dwErrCode
0x18004d204  call    cs:__imp_SetLastError
0x18004d20a  jmp     short loc_18004D1BF
```
