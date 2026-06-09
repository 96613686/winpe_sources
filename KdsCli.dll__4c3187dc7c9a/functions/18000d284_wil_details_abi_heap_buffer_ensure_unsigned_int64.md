# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000d284`
- end: `0x18000d356`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c740`
- `0x18000cd04`
- `0x180014418`
- `0x180014a54`
- `0x180015bf8`

## callees

- `0x180001f4c`
- `0x18000c600`
- `0x18000d284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d341`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d326`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d326`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d318`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d318`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
  HANDLE ProcessHeap; // rax

  v3 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this >= v4 )
  {
    if ( a2 < 2 * v4 )
      v3 = 2 * v4;
    if ( v4 < v3 )
    {
      LastError = GetLastError();
      v6 = (v3 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v7 = (char *)wil::details::ProcessHeapAlloc(0, v6);
      v8 = v7;
      if ( !v7 )
      {
        SetLastError(LastError);
        return 0;
      }
      v10 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v7, v6, *(const void *const *)this, v10);
      v11 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v8;
      if ( v11 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v11);
      }
      *(_QWORD *)this = v8;
      *((_QWORD *)this + 1) = &v8[v10];
      *((_QWORD *)this + 2) = &v8[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000d284  push    rbx
0x18000d286  push    rbp
0x18000d287  push    rsi
0x18000d288  push    rdi
0x18000d289  push    r14
0x18000d28b  push    r15
0x18000d28d  sub     rsp, 28h
0x18000d291  mov     rdi, rcx
0x18000d294  mov     rbx, rdx
0x18000d297  mov     rcx, [rcx+10h]
0x18000d29b  mov     rax, [rdi+8]
0x18000d29f  sub     rax, [rdi]
0x18000d2a2  sub     rcx, [rdi]
0x18000d2a5  add     rax, rdx
0x18000d2a8  cmp     rax, rcx
0x18000d2ab  jb      loc_18000D347
0x18000d2b1  lea     rax, [rcx+rcx]
0x18000d2b5  cmp     rdx, rax
0x18000d2b8  cmovb   rbx, rax
0x18000d2bc  cmp     rcx, rbx
0x18000d2bf  jnb     loc_18000D347
0x18000d2c5  call    cs:__imp_GetLastError
0x18000d2cb  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000d2cf  xor     ecx, ecx; dwFlags
0x18000d2d1  mov     esi, eax
0x18000d2d3  lea     r14, [rbx+40h]
0x18000d2d7  mov     rdx, r14; dwBytes
0x18000d2da  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d2df  mov     rbx, rax
0x18000d2e2  test    rax, rax
0x18000d2e5  jnz     short loc_18000D2F3
0x18000d2e7  mov     ecx, esi; dwErrCode
0x18000d2e9  call    cs:__imp_SetLastError
0x18000d2ef  xor     al, al
0x18000d2f1  jmp     short loc_18000D349
0x18000d2f3  mov     r15, [rdi+8]
0x18000d2f7  mov     rdx, r14; DestinationSize
0x18000d2fa  sub     r15, [rdi]
0x18000d2fd  mov     rcx, rbx; Destination
0x18000d300  mov     r8, [rdi]; Source
0x18000d303  mov     r9, r15; SourceSize
0x18000d306  call    memcpy_s
0x18000d30b  mov     rbp, [rdi+18h]
0x18000d30f  mov     [rdi+18h], rbx
0x18000d313  test    rbp, rbp
0x18000d316  jz      short loc_18000D32C
0x18000d318  call    cs:__imp_GetProcessHeap
0x18000d31e  mov     r8, rbp; lpMem
0x18000d321  xor     edx, edx; dwFlags
0x18000d323  mov     rcx, rax; hHeap
0x18000d326  call    cs:__imp_HeapFree
0x18000d32c  lea     rax, [r15+rbx]
0x18000d330  mov     [rdi], rbx
0x18000d333  mov     [rdi+8], rax
0x18000d337  mov     ecx, esi; dwErrCode
0x18000d339  lea     rax, [r14+rbx]
0x18000d33d  mov     [rdi+10h], rax
0x18000d341  call    cs:__imp_SetLastError
0x18000d347  mov     al, 1
0x18000d349  add     rsp, 28h
0x18000d34d  pop     r15
0x18000d34f  pop     r14
0x18000d351  pop     rdi
0x18000d352  pop     rsi
0x18000d353  pop     rbp
0x18000d354  pop     rbx
0x18000d355  retn
```
