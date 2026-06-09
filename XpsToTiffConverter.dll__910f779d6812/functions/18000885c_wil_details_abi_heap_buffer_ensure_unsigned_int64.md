# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000885c`
- end: `0x18000892e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005c3c`
- `0x1800062b8`
- `0x180007d40`

## callees

- `0x180005b98`
- `0x18000885c`
- `0x180008f08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000889d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000889d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008919`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008919`

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
0x18000885c  push    rbx
0x18000885e  push    rbp
0x18000885f  push    rsi
0x180008860  push    rdi
0x180008861  push    r14
0x180008863  push    r15
0x180008865  sub     rsp, 28h
0x180008869  mov     rdi, rcx
0x18000886c  mov     rbx, rdx
0x18000886f  mov     rcx, [rcx+10h]
0x180008873  mov     rax, [rdi+8]
0x180008877  sub     rax, [rdi]
0x18000887a  sub     rcx, [rdi]
0x18000887d  add     rax, rdx
0x180008880  cmp     rax, rcx
0x180008883  jb      loc_18000891F
0x180008889  lea     rax, [rcx+rcx]
0x18000888d  cmp     rdx, rax
0x180008890  cmovb   rbx, rax
0x180008894  cmp     rcx, rbx
0x180008897  jnb     loc_18000891F
0x18000889d  call    cs:__imp_GetLastError
0x1800088a3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1800088a7  xor     ecx, ecx; dwFlags
0x1800088a9  mov     esi, eax
0x1800088ab  lea     r14, [rbx+40h]
0x1800088af  mov     rdx, r14; dwBytes
0x1800088b2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800088b7  mov     rbx, rax
0x1800088ba  test    rax, rax
0x1800088bd  jnz     short loc_1800088CB
0x1800088bf  mov     ecx, esi; dwErrCode
0x1800088c1  call    cs:__imp_SetLastError
0x1800088c7  xor     al, al
0x1800088c9  jmp     short loc_180008921
0x1800088cb  mov     r15, [rdi+8]
0x1800088cf  mov     rdx, r14; DestinationSize
0x1800088d2  sub     r15, [rdi]
0x1800088d5  mov     rcx, rbx; Destination
0x1800088d8  mov     r8, [rdi]; Source
0x1800088db  mov     r9, r15; SourceSize
0x1800088de  call    memcpy_s
0x1800088e3  mov     rbp, [rdi+18h]
0x1800088e7  mov     [rdi+18h], rbx
0x1800088eb  test    rbp, rbp
0x1800088ee  jz      short loc_180008904
0x1800088f0  call    cs:__imp_GetProcessHeap
0x1800088f6  mov     r8, rbp; lpMem
0x1800088f9  xor     edx, edx; dwFlags
0x1800088fb  mov     rcx, rax; hHeap
0x1800088fe  call    cs:__imp_HeapFree
0x180008904  lea     rax, [r15+rbx]
0x180008908  mov     [rdi], rbx
0x18000890b  mov     [rdi+8], rax
0x18000890f  mov     ecx, esi; dwErrCode
0x180008911  lea     rax, [r14+rbx]
0x180008915  mov     [rdi+10h], rax
0x180008919  call    cs:__imp_SetLastError
0x18000891f  mov     al, 1
0x180008921  add     rsp, 28h
0x180008925  pop     r15
0x180008927  pop     r14
0x180008929  pop     rdi
0x18000892a  pop     rsi
0x18000892b  pop     rbp
0x18000892c  pop     rbx
0x18000892d  retn
```
