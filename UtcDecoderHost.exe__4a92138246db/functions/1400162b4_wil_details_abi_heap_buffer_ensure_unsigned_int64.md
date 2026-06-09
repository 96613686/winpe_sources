# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x1400162b4`
- end: `0x140016386`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400146e0`
- `0x140014cac`
- `0x140015c8c`

## callees

- `0x14000bfc8`
- `0x14000d608`
- `0x1400162b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016356`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016356`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016348`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016348`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016319`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016371`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016319`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162f5`

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
0x1400162b4  push    rbx
0x1400162b6  push    rbp
0x1400162b7  push    rsi
0x1400162b8  push    rdi
0x1400162b9  push    r14
0x1400162bb  push    r15
0x1400162bd  sub     rsp, 28h
0x1400162c1  mov     rdi, rcx
0x1400162c4  mov     rbx, rdx
0x1400162c7  mov     rcx, [rcx+10h]
0x1400162cb  mov     rax, [rdi+8]
0x1400162cf  sub     rax, [rdi]
0x1400162d2  sub     rcx, [rdi]
0x1400162d5  add     rax, rdx
0x1400162d8  cmp     rax, rcx
0x1400162db  jb      loc_140016377
0x1400162e1  lea     rax, [rcx+rcx]
0x1400162e5  cmp     rdx, rax
0x1400162e8  cmovb   rbx, rax
0x1400162ec  cmp     rcx, rbx
0x1400162ef  jnb     loc_140016377
0x1400162f5  call    cs:__imp_GetLastError
0x1400162fb  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1400162ff  xor     ecx, ecx; dwFlags
0x140016301  mov     esi, eax
0x140016303  lea     r14, [rbx+40h]
0x140016307  mov     rdx, r14; dwBytes
0x14001630a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001630f  mov     rbx, rax
0x140016312  test    rax, rax
0x140016315  jnz     short loc_140016323
0x140016317  mov     ecx, esi; dwErrCode
0x140016319  call    cs:__imp_SetLastError
0x14001631f  xor     al, al
0x140016321  jmp     short loc_140016379
0x140016323  mov     r15, [rdi+8]
0x140016327  mov     rdx, r14; DestinationSize
0x14001632a  sub     r15, [rdi]
0x14001632d  mov     rcx, rbx; Destination
0x140016330  mov     r8, [rdi]; Source
0x140016333  mov     r9, r15; SourceSize
0x140016336  call    memcpy_s
0x14001633b  mov     rbp, [rdi+18h]
0x14001633f  mov     [rdi+18h], rbx
0x140016343  test    rbp, rbp
0x140016346  jz      short loc_14001635C
0x140016348  call    cs:__imp_GetProcessHeap
0x14001634e  mov     r8, rbp; lpMem
0x140016351  xor     edx, edx; dwFlags
0x140016353  mov     rcx, rax; hHeap
0x140016356  call    cs:__imp_HeapFree
0x14001635c  lea     rax, [r15+rbx]
0x140016360  mov     [rdi], rbx
0x140016363  mov     [rdi+8], rax
0x140016367  mov     ecx, esi; dwErrCode
0x140016369  lea     rax, [r14+rbx]
0x14001636d  mov     [rdi+10h], rax
0x140016371  call    cs:__imp_SetLastError
0x140016377  mov     al, 1
0x140016379  add     rsp, 28h
0x14001637d  pop     r15
0x14001637f  pop     r14
0x140016381  pop     rdi
0x140016382  pop     rsi
0x140016383  pop     rbp
0x140016384  pop     rbx
0x140016385  retn
```
