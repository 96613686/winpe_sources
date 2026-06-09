# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x1400082dc`
- end: `0x1400083ae`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400069e0`
- `0x140006fac`
- `0x140007cb0`

## callees

- `0x140004508`
- `0x140005808`
- `0x1400082dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008370`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008370`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000837e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000837e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000831d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000831d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008341`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008399`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008341`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008399`

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
0x1400082dc  push    rbx
0x1400082de  push    rbp
0x1400082df  push    rsi
0x1400082e0  push    rdi
0x1400082e1  push    r14
0x1400082e3  push    r15
0x1400082e5  sub     rsp, 28h
0x1400082e9  mov     rdi, rcx
0x1400082ec  mov     rbx, rdx
0x1400082ef  mov     rcx, [rcx+10h]
0x1400082f3  mov     rax, [rdi+8]
0x1400082f7  sub     rax, [rdi]
0x1400082fa  sub     rcx, [rdi]
0x1400082fd  add     rax, rdx
0x140008300  cmp     rax, rcx
0x140008303  jb      loc_14000839F
0x140008309  lea     rax, [rcx+rcx]
0x14000830d  cmp     rdx, rax
0x140008310  cmovb   rbx, rax
0x140008314  cmp     rcx, rbx
0x140008317  jnb     loc_14000839F
0x14000831d  call    cs:__imp_GetLastError
0x140008323  and     rbx, 0FFFFFFFFFFFFFFC0h
0x140008327  xor     ecx, ecx; dwFlags
0x140008329  mov     esi, eax
0x14000832b  lea     r14, [rbx+40h]
0x14000832f  mov     rdx, r14; dwBytes
0x140008332  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008337  mov     rbx, rax
0x14000833a  test    rax, rax
0x14000833d  jnz     short loc_14000834B
0x14000833f  mov     ecx, esi; dwErrCode
0x140008341  call    cs:__imp_SetLastError
0x140008347  xor     al, al
0x140008349  jmp     short loc_1400083A1
0x14000834b  mov     r15, [rdi+8]
0x14000834f  mov     rdx, r14; DestinationSize
0x140008352  sub     r15, [rdi]
0x140008355  mov     rcx, rbx; Destination
0x140008358  mov     r8, [rdi]; Source
0x14000835b  mov     r9, r15; SourceSize
0x14000835e  call    memcpy_s
0x140008363  mov     rbp, [rdi+18h]
0x140008367  mov     [rdi+18h], rbx
0x14000836b  test    rbp, rbp
0x14000836e  jz      short loc_140008384
0x140008370  call    cs:__imp_GetProcessHeap
0x140008376  mov     r8, rbp; lpMem
0x140008379  xor     edx, edx; dwFlags
0x14000837b  mov     rcx, rax; hHeap
0x14000837e  call    cs:__imp_HeapFree
0x140008384  lea     rax, [r15+rbx]
0x140008388  mov     [rdi], rbx
0x14000838b  mov     [rdi+8], rax
0x14000838f  mov     ecx, esi; dwErrCode
0x140008391  lea     rax, [r14+rbx]
0x140008395  mov     [rdi+10h], rax
0x140008399  call    cs:__imp_SetLastError
0x14000839f  mov     al, 1
0x1400083a1  add     rsp, 28h
0x1400083a5  pop     r15
0x1400083a7  pop     r14
0x1400083a9  pop     rdi
0x1400083aa  pop     rsi
0x1400083ab  pop     rbp
0x1400083ac  pop     rbx
0x1400083ad  retn
```
