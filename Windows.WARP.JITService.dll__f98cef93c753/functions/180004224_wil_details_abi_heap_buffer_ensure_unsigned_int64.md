# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180004224`
- end: `0x1800042f6`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800046cc`
- `0x1800054f0`
- `0x180006050`

## callees

- `0x180001224`
- `0x1800017fc`
- `0x180004224`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800042c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800042c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800042b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800042b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004265`

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
      memcpy_s(v8, v6, *(const void *const *)this, v11);
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
0x180004224  push    rbx
0x180004226  push    rbp
0x180004227  push    rsi
0x180004228  push    rdi
0x180004229  push    r14
0x18000422b  push    r15
0x18000422d  sub     rsp, 28h
0x180004231  mov     rdi, rcx
0x180004234  mov     rbx, rdx
0x180004237  mov     rcx, [rcx+10h]
0x18000423b  mov     rax, [rdi+8]
0x18000423f  sub     rax, [rdi]
0x180004242  sub     rcx, [rdi]
0x180004245  add     rax, rdx
0x180004248  cmp     rax, rcx
0x18000424b  jb      loc_1800042E7
0x180004251  lea     rax, [rcx+rcx]
0x180004255  cmp     rdx, rax
0x180004258  cmovb   rbx, rax
0x18000425c  cmp     rcx, rbx
0x18000425f  jnb     loc_1800042E7
0x180004265  call    cs:__imp_GetLastError
0x18000426b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000426f  xor     ecx, ecx; dwFlags
0x180004271  mov     esi, eax
0x180004273  lea     r14, [rbx+40h]
0x180004277  mov     rdx, r14; dwBytes
0x18000427a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000427f  mov     rbx, rax
0x180004282  test    rax, rax
0x180004285  jnz     short loc_180004293
0x180004287  mov     ecx, esi; dwErrCode
0x180004289  call    cs:__imp_SetLastError
0x18000428f  xor     al, al
0x180004291  jmp     short loc_1800042E9
0x180004293  mov     r15, [rdi+8]
0x180004297  mov     rdx, r14; DestinationSize
0x18000429a  sub     r15, [rdi]
0x18000429d  mov     rcx, rbx; Destination
0x1800042a0  mov     r8, [rdi]; Source
0x1800042a3  mov     r9, r15; SourceSize
0x1800042a6  call    memcpy_s
0x1800042ab  mov     rbp, [rdi+18h]
0x1800042af  mov     [rdi+18h], rbx
0x1800042b3  test    rbp, rbp
0x1800042b6  jz      short loc_1800042CC
0x1800042b8  call    cs:__imp_GetProcessHeap
0x1800042be  mov     r8, rbp; lpMem
0x1800042c1  xor     edx, edx; dwFlags
0x1800042c3  mov     rcx, rax; hHeap
0x1800042c6  call    cs:__imp_HeapFree
0x1800042cc  lea     rax, [r15+rbx]
0x1800042d0  mov     [rdi], rbx
0x1800042d3  mov     [rdi+8], rax
0x1800042d7  mov     ecx, esi; dwErrCode
0x1800042d9  lea     rax, [r14+rbx]
0x1800042dd  mov     [rdi+10h], rax
0x1800042e1  call    cs:__imp_SetLastError
0x1800042e7  mov     al, 1
0x1800042e9  add     rsp, 28h
0x1800042ed  pop     r15
0x1800042ef  pop     r14
0x1800042f1  pop     rdi
0x1800042f2  pop     rsi
0x1800042f3  pop     rbp
0x1800042f4  pop     rbx
0x1800042f5  retn
```
