# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180007cdc`
- end: `0x180007daf`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800055f8`
- `0x180005df4`
- `0x180007058`
- `0x180007228`

## callees

- `0x1800054b8`
- `0x180007cdc`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180007d5e`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x180007d5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d9a`

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
0x180007cdc  push    rbx
0x180007cde  push    rbp
0x180007cdf  push    rsi
0x180007ce0  push    rdi
0x180007ce1  push    r14
0x180007ce3  push    r15
0x180007ce5  sub     rsp, 28h
0x180007ce9  mov     rdi, rcx
0x180007cec  mov     rbx, rdx
0x180007cef  mov     rcx, [rcx+10h]
0x180007cf3  mov     rax, [rdi+8]
0x180007cf7  sub     rax, [rdi]
0x180007cfa  sub     rcx, [rdi]
0x180007cfd  add     rax, rdx
0x180007d00  cmp     rax, rcx
0x180007d03  jb      loc_180007DA0
0x180007d09  lea     rax, [rcx+rcx]
0x180007d0d  cmp     rdx, rax
0x180007d10  cmovb   rbx, rax
0x180007d14  cmp     rcx, rbx
0x180007d17  jnb     loc_180007DA0
0x180007d1d  call    cs:__imp_GetLastError
0x180007d23  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180007d27  xor     ecx, ecx; dwFlags
0x180007d29  mov     esi, eax
0x180007d2b  lea     r14, [rbx+40h]
0x180007d2f  mov     rdx, r14; dwBytes
0x180007d32  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007d37  mov     rbx, rax
0x180007d3a  test    rax, rax
0x180007d3d  jnz     short loc_180007D4B
0x180007d3f  mov     ecx, esi; dwErrCode
0x180007d41  call    cs:__imp_SetLastError
0x180007d47  xor     al, al
0x180007d49  jmp     short loc_180007DA2
0x180007d4b  mov     r15, [rdi+8]
0x180007d4f  mov     rdx, r14; DestinationSize
0x180007d52  sub     r15, [rdi]
0x180007d55  mov     rcx, rbx; Destination
0x180007d58  mov     r8, [rdi]; Source
0x180007d5b  mov     r9, r15; SourceSize
0x180007d5e  call    cs:__imp_memcpy_s
0x180007d64  mov     rbp, [rdi+18h]
0x180007d68  mov     [rdi+18h], rbx
0x180007d6c  test    rbp, rbp
0x180007d6f  jz      short loc_180007D85
0x180007d71  call    cs:__imp_GetProcessHeap
0x180007d77  mov     r8, rbp; lpMem
0x180007d7a  xor     edx, edx; dwFlags
0x180007d7c  mov     rcx, rax; hHeap
0x180007d7f  call    cs:__imp_HeapFree
0x180007d85  lea     rax, [r15+rbx]
0x180007d89  mov     [rdi], rbx
0x180007d8c  mov     [rdi+8], rax
0x180007d90  mov     ecx, esi; dwErrCode
0x180007d92  lea     rax, [r14+rbx]
0x180007d96  mov     [rdi+10h], rax
0x180007d9a  call    cs:__imp_SetLastError
0x180007da0  mov     al, 1
0x180007da2  add     rsp, 28h
0x180007da6  pop     r15
0x180007da8  pop     r14
0x180007daa  pop     rdi
0x180007dab  pop     rsi
0x180007dac  pop     rbp
0x180007dad  pop     rbx
0x180007dae  retn
```
