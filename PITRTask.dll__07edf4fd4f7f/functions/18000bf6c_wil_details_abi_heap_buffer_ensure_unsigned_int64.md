# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000bf6c`
- end: `0x18000c03f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ab8`
- `0x1800089dc`
- `0x180009800`
- `0x1800099f4`
- `0x180009f30`

## callees

- `0x1800070ec`
- `0x18000bf6c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000bfee`
- `msvcrt!memcpy_s` at `0x18000bfee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c001`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c001`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c00f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c00f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bfd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c02a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bfd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c02a`

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
0x18000bf6c  push    rbx
0x18000bf6e  push    rbp
0x18000bf6f  push    rsi
0x18000bf70  push    rdi
0x18000bf71  push    r14
0x18000bf73  push    r15
0x18000bf75  sub     rsp, 28h
0x18000bf79  mov     rdi, rcx
0x18000bf7c  mov     rbx, rdx
0x18000bf7f  mov     rcx, [rcx+10h]
0x18000bf83  mov     rax, [rdi+8]
0x18000bf87  sub     rax, [rdi]
0x18000bf8a  sub     rcx, [rdi]
0x18000bf8d  add     rax, rdx
0x18000bf90  cmp     rax, rcx
0x18000bf93  jb      loc_18000C030
0x18000bf99  lea     rax, [rcx+rcx]
0x18000bf9d  cmp     rdx, rax
0x18000bfa0  cmovb   rbx, rax
0x18000bfa4  cmp     rcx, rbx
0x18000bfa7  jnb     loc_18000C030
0x18000bfad  call    cs:__imp_GetLastError
0x18000bfb3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000bfb7  xor     ecx, ecx; dwFlags
0x18000bfb9  mov     esi, eax
0x18000bfbb  lea     r14, [rbx+40h]
0x18000bfbf  mov     rdx, r14; dwBytes
0x18000bfc2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bfc7  mov     rbx, rax
0x18000bfca  test    rax, rax
0x18000bfcd  jnz     short loc_18000BFDB
0x18000bfcf  mov     ecx, esi; dwErrCode
0x18000bfd1  call    cs:__imp_SetLastError
0x18000bfd7  xor     al, al
0x18000bfd9  jmp     short loc_18000C032
0x18000bfdb  mov     r15, [rdi+8]
0x18000bfdf  mov     rdx, r14; DestinationSize
0x18000bfe2  sub     r15, [rdi]
0x18000bfe5  mov     rcx, rbx; Destination
0x18000bfe8  mov     r8, [rdi]; Source
0x18000bfeb  mov     r9, r15; SourceSize
0x18000bfee  call    cs:__imp_memcpy_s
0x18000bff4  mov     rbp, [rdi+18h]
0x18000bff8  mov     [rdi+18h], rbx
0x18000bffc  test    rbp, rbp
0x18000bfff  jz      short loc_18000C015
0x18000c001  call    cs:__imp_GetProcessHeap
0x18000c007  mov     r8, rbp; lpMem
0x18000c00a  xor     edx, edx; dwFlags
0x18000c00c  mov     rcx, rax; hHeap
0x18000c00f  call    cs:__imp_HeapFree
0x18000c015  lea     rax, [r15+rbx]
0x18000c019  mov     [rdi], rbx
0x18000c01c  mov     [rdi+8], rax
0x18000c020  mov     ecx, esi; dwErrCode
0x18000c022  lea     rax, [r14+rbx]
0x18000c026  mov     [rdi+10h], rax
0x18000c02a  call    cs:__imp_SetLastError
0x18000c030  mov     al, 1
0x18000c032  add     rsp, 28h
0x18000c036  pop     r15
0x18000c038  pop     r14
0x18000c03a  pop     rdi
0x18000c03b  pop     rsi
0x18000c03c  pop     rbp
0x18000c03d  pop     rbx
0x18000c03e  retn
```
