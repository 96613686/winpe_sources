# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000a0e4`
- end: `0x18000a1b7`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000604c`
- `0x180006660`
- `0x1800082fc`

## callees

- `0x180005ef0`
- `0x18000a0e4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a166`
- `msvcrt!memcpy_s` at `0x18000a166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a187`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a187`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a179`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a125`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a149`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a149`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1a2`

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
0x18000a0e4  push    rbx
0x18000a0e6  push    rbp
0x18000a0e7  push    rsi
0x18000a0e8  push    rdi
0x18000a0e9  push    r14
0x18000a0eb  push    r15
0x18000a0ed  sub     rsp, 28h
0x18000a0f1  mov     rdi, rcx
0x18000a0f4  mov     rbx, rdx
0x18000a0f7  mov     rcx, [rcx+10h]
0x18000a0fb  mov     rax, [rdi+8]
0x18000a0ff  sub     rax, [rdi]
0x18000a102  sub     rcx, [rdi]
0x18000a105  add     rax, rdx
0x18000a108  cmp     rax, rcx
0x18000a10b  jb      loc_18000A1A8
0x18000a111  lea     rax, [rcx+rcx]
0x18000a115  cmp     rdx, rax
0x18000a118  cmovb   rbx, rax
0x18000a11c  cmp     rcx, rbx
0x18000a11f  jnb     loc_18000A1A8
0x18000a125  call    cs:__imp_GetLastError
0x18000a12b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000a12f  xor     ecx, ecx; dwFlags
0x18000a131  mov     esi, eax
0x18000a133  lea     r14, [rbx+40h]
0x18000a137  mov     rdx, r14; dwBytes
0x18000a13a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a13f  mov     rbx, rax
0x18000a142  test    rax, rax
0x18000a145  jnz     short loc_18000A153
0x18000a147  mov     ecx, esi; dwErrCode
0x18000a149  call    cs:__imp_SetLastError
0x18000a14f  xor     al, al
0x18000a151  jmp     short loc_18000A1AA
0x18000a153  mov     r15, [rdi+8]
0x18000a157  mov     rdx, r14; DestinationSize
0x18000a15a  sub     r15, [rdi]
0x18000a15d  mov     rcx, rbx; Destination
0x18000a160  mov     r8, [rdi]; Source
0x18000a163  mov     r9, r15; SourceSize
0x18000a166  call    cs:__imp_memcpy_s
0x18000a16c  mov     rbp, [rdi+18h]
0x18000a170  mov     [rdi+18h], rbx
0x18000a174  test    rbp, rbp
0x18000a177  jz      short loc_18000A18D
0x18000a179  call    cs:__imp_GetProcessHeap
0x18000a17f  mov     r8, rbp; lpMem
0x18000a182  xor     edx, edx; dwFlags
0x18000a184  mov     rcx, rax; hHeap
0x18000a187  call    cs:__imp_HeapFree
0x18000a18d  lea     rax, [r15+rbx]
0x18000a191  mov     [rdi], rbx
0x18000a194  mov     [rdi+8], rax
0x18000a198  mov     ecx, esi; dwErrCode
0x18000a19a  lea     rax, [r14+rbx]
0x18000a19e  mov     [rdi+10h], rax
0x18000a1a2  call    cs:__imp_SetLastError
0x18000a1a8  mov     al, 1
0x18000a1aa  add     rsp, 28h
0x18000a1ae  pop     r15
0x18000a1b0  pop     r14
0x18000a1b2  pop     rdi
0x18000a1b3  pop     rsi
0x18000a1b4  pop     rbp
0x18000a1b5  pop     rbx
0x18000a1b6  retn
```
