# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000d5fc`
- end: `0x18000d6ce`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800060a8`
- `0x18000624c`
- `0x180006a98`
- `0x1800084e4`
- `0x1800086ec`

## callees

- `0x180005f68`
- `0x18000d5fc`
- `0x18000e674`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d63d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d63d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d661`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d661`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d69e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d69e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d690`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d690`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r8
  char *v8; // rax
  char *v9; // rbx
  rsize_t v11; // r15
  void *v12; // rbp
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
      v8 = (char *)wil::details::ProcessHeapAlloc(0, v6, v7);
      v9 = v8;
      if ( !v8 )
      {
        SetLastError(LastError);
        return 0;
      }
      v11 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s_0(v8, v6, *(const void *const *)this, v11);
      v12 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v9;
      if ( v12 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
      *(_QWORD *)this = v9;
      *((_QWORD *)this + 1) = &v9[v11];
      *((_QWORD *)this + 2) = &v9[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000d5fc  push    rbx
0x18000d5fe  push    rbp
0x18000d5ff  push    rsi
0x18000d600  push    rdi
0x18000d601  push    r14
0x18000d603  push    r15
0x18000d605  sub     rsp, 28h
0x18000d609  mov     rdi, rcx
0x18000d60c  mov     rbx, rdx
0x18000d60f  mov     rcx, [rcx+10h]
0x18000d613  mov     rax, [rdi+8]
0x18000d617  sub     rax, [rdi]
0x18000d61a  sub     rcx, [rdi]
0x18000d61d  add     rax, rdx
0x18000d620  cmp     rax, rcx
0x18000d623  jb      loc_18000D6BF
0x18000d629  lea     rax, [rcx+rcx]
0x18000d62d  cmp     rdx, rax
0x18000d630  cmovb   rbx, rax
0x18000d634  cmp     rcx, rbx
0x18000d637  jnb     loc_18000D6BF
0x18000d63d  call    cs:__imp_GetLastError
0x18000d643  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000d647  xor     ecx, ecx; dwFlags
0x18000d649  mov     esi, eax
0x18000d64b  lea     r14, [rbx+40h]
0x18000d64f  mov     rdx, r14; dwBytes
0x18000d652  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d657  mov     rbx, rax
0x18000d65a  test    rax, rax
0x18000d65d  jnz     short loc_18000D66B
0x18000d65f  mov     ecx, esi; dwErrCode
0x18000d661  call    cs:__imp_SetLastError
0x18000d667  xor     al, al
0x18000d669  jmp     short loc_18000D6C1
0x18000d66b  mov     r15, [rdi+8]
0x18000d66f  mov     rdx, r14; DestinationSize
0x18000d672  sub     r15, [rdi]
0x18000d675  mov     rcx, rbx; Destination
0x18000d678  mov     r8, [rdi]; Source
0x18000d67b  mov     r9, r15; SourceSize
0x18000d67e  call    memcpy_s_0
0x18000d683  mov     rbp, [rdi+18h]
0x18000d687  mov     [rdi+18h], rbx
0x18000d68b  test    rbp, rbp
0x18000d68e  jz      short loc_18000D6A4
0x18000d690  call    cs:__imp_GetProcessHeap
0x18000d696  mov     r8, rbp; lpMem
0x18000d699  xor     edx, edx; dwFlags
0x18000d69b  mov     rcx, rax; hHeap
0x18000d69e  call    cs:__imp_HeapFree
0x18000d6a4  lea     rax, [r15+rbx]
0x18000d6a8  mov     [rdi], rbx
0x18000d6ab  mov     [rdi+8], rax
0x18000d6af  mov     ecx, esi; dwErrCode
0x18000d6b1  lea     rax, [r14+rbx]
0x18000d6b5  mov     [rdi+10h], rax
0x18000d6b9  call    cs:__imp_SetLastError
0x18000d6bf  mov     al, 1
0x18000d6c1  add     rsp, 28h
0x18000d6c5  pop     r15
0x18000d6c7  pop     r14
0x18000d6c9  pop     rdi
0x18000d6ca  pop     rsi
0x18000d6cb  pop     rbp
0x18000d6cc  pop     rbx
0x18000d6cd  retn
```
