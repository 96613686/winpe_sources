# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180009d1c`
- end: `0x180009dee`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180006d78`
- `0x1800075f8`
- `0x180008f34`
- `0x18000913c`
- `0x18000aabc`

## callees

- `0x180006c38`
- `0x180009d1c`
- `0x18000a168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009dbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009dbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009db0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009db0`

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
0x180009d1c  push    rbx
0x180009d1e  push    rbp
0x180009d1f  push    rsi
0x180009d20  push    rdi
0x180009d21  push    r14
0x180009d23  push    r15
0x180009d25  sub     rsp, 28h
0x180009d29  mov     rdi, rcx
0x180009d2c  mov     rbx, rdx
0x180009d2f  mov     rcx, [rcx+10h]
0x180009d33  mov     rax, [rdi+8]
0x180009d37  sub     rax, [rdi]
0x180009d3a  sub     rcx, [rdi]
0x180009d3d  add     rax, rdx
0x180009d40  cmp     rax, rcx
0x180009d43  jb      loc_180009DDF
0x180009d49  lea     rax, [rcx+rcx]
0x180009d4d  cmp     rdx, rax
0x180009d50  cmovb   rbx, rax
0x180009d54  cmp     rcx, rbx
0x180009d57  jnb     loc_180009DDF
0x180009d5d  call    cs:__imp_GetLastError
0x180009d63  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180009d67  xor     ecx, ecx; dwFlags
0x180009d69  mov     esi, eax
0x180009d6b  lea     r14, [rbx+40h]
0x180009d6f  mov     rdx, r14; dwBytes
0x180009d72  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009d77  mov     rbx, rax
0x180009d7a  test    rax, rax
0x180009d7d  jnz     short loc_180009D8B
0x180009d7f  mov     ecx, esi; dwErrCode
0x180009d81  call    cs:__imp_SetLastError
0x180009d87  xor     al, al
0x180009d89  jmp     short loc_180009DE1
0x180009d8b  mov     r15, [rdi+8]
0x180009d8f  mov     rdx, r14; DestinationSize
0x180009d92  sub     r15, [rdi]
0x180009d95  mov     rcx, rbx; Destination
0x180009d98  mov     r8, [rdi]; Source
0x180009d9b  mov     r9, r15; SourceSize
0x180009d9e  call    memcpy_s
0x180009da3  mov     rbp, [rdi+18h]
0x180009da7  mov     [rdi+18h], rbx
0x180009dab  test    rbp, rbp
0x180009dae  jz      short loc_180009DC4
0x180009db0  call    cs:__imp_GetProcessHeap
0x180009db6  mov     r8, rbp; lpMem
0x180009db9  xor     edx, edx; dwFlags
0x180009dbb  mov     rcx, rax; hHeap
0x180009dbe  call    cs:__imp_HeapFree
0x180009dc4  lea     rax, [r15+rbx]
0x180009dc8  mov     [rdi], rbx
0x180009dcb  mov     [rdi+8], rax
0x180009dcf  mov     ecx, esi; dwErrCode
0x180009dd1  lea     rax, [r14+rbx]
0x180009dd5  mov     [rdi+10h], rax
0x180009dd9  call    cs:__imp_SetLastError
0x180009ddf  mov     al, 1
0x180009de1  add     rsp, 28h
0x180009de5  pop     r15
0x180009de7  pop     r14
0x180009de9  pop     rdi
0x180009dea  pop     rsi
0x180009deb  pop     rbp
0x180009dec  pop     rbx
0x180009ded  retn
```
