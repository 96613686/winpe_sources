# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000ea94`
- end: `0x14000eb66`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d158`
- `0x14000d740`
- `0x14000e3d0`

## callees

- `0x1400061e4`
- `0x140007618`
- `0x14000ea94`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000eb36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000eb36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000eb28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000eb28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ead5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ead5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eaf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eb51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eaf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eb51`

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
0x14000ea94  push    rbx
0x14000ea96  push    rbp
0x14000ea97  push    rsi
0x14000ea98  push    rdi
0x14000ea99  push    r14
0x14000ea9b  push    r15
0x14000ea9d  sub     rsp, 28h
0x14000eaa1  mov     rdi, rcx
0x14000eaa4  mov     rbx, rdx
0x14000eaa7  mov     rcx, [rcx+10h]
0x14000eaab  mov     rax, [rdi+8]
0x14000eaaf  sub     rax, [rdi]
0x14000eab2  sub     rcx, [rdi]
0x14000eab5  add     rax, rdx
0x14000eab8  cmp     rax, rcx
0x14000eabb  jb      loc_14000EB57
0x14000eac1  lea     rax, [rcx+rcx]
0x14000eac5  cmp     rdx, rax
0x14000eac8  cmovb   rbx, rax
0x14000eacc  cmp     rcx, rbx
0x14000eacf  jnb     loc_14000EB57
0x14000ead5  call    cs:__imp_GetLastError
0x14000eadb  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000eadf  xor     ecx, ecx; dwFlags
0x14000eae1  mov     esi, eax
0x14000eae3  lea     r14, [rbx+40h]
0x14000eae7  mov     rdx, r14; dwBytes
0x14000eaea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000eaef  mov     rbx, rax
0x14000eaf2  test    rax, rax
0x14000eaf5  jnz     short loc_14000EB03
0x14000eaf7  mov     ecx, esi; dwErrCode
0x14000eaf9  call    cs:__imp_SetLastError
0x14000eaff  xor     al, al
0x14000eb01  jmp     short loc_14000EB59
0x14000eb03  mov     r15, [rdi+8]
0x14000eb07  mov     rdx, r14; DestinationSize
0x14000eb0a  sub     r15, [rdi]
0x14000eb0d  mov     rcx, rbx; Destination
0x14000eb10  mov     r8, [rdi]; Source
0x14000eb13  mov     r9, r15; SourceSize
0x14000eb16  call    memcpy_s
0x14000eb1b  mov     rbp, [rdi+18h]
0x14000eb1f  mov     [rdi+18h], rbx
0x14000eb23  test    rbp, rbp
0x14000eb26  jz      short loc_14000EB3C
0x14000eb28  call    cs:__imp_GetProcessHeap
0x14000eb2e  mov     r8, rbp; lpMem
0x14000eb31  xor     edx, edx; dwFlags
0x14000eb33  mov     rcx, rax; hHeap
0x14000eb36  call    cs:__imp_HeapFree
0x14000eb3c  lea     rax, [r15+rbx]
0x14000eb40  mov     [rdi], rbx
0x14000eb43  mov     [rdi+8], rax
0x14000eb47  mov     ecx, esi; dwErrCode
0x14000eb49  lea     rax, [r14+rbx]
0x14000eb4d  mov     [rdi+10h], rax
0x14000eb51  call    cs:__imp_SetLastError
0x14000eb57  mov     al, 1
0x14000eb59  add     rsp, 28h
0x14000eb5d  pop     r15
0x14000eb5f  pop     r14
0x14000eb61  pop     rdi
0x14000eb62  pop     rsi
0x14000eb63  pop     rbp
0x14000eb64  pop     rbx
0x14000eb65  retn
```
