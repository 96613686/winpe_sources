# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000bb9c`
- end: `0x14000bc6e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400092cc`
- `0x14000989c`
- `0x14000b178`

## callees

- `0x140009228`
- `0x14000bb9c`
- `0x14000bfd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bbdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bbdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bc01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bc59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bc01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bc59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bc30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bc30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bc3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bc3e`

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
0x14000bb9c  push    rbx
0x14000bb9e  push    rbp
0x14000bb9f  push    rsi
0x14000bba0  push    rdi
0x14000bba1  push    r14
0x14000bba3  push    r15
0x14000bba5  sub     rsp, 28h
0x14000bba9  mov     rdi, rcx
0x14000bbac  mov     rbx, rdx
0x14000bbaf  mov     rcx, [rcx+10h]
0x14000bbb3  mov     rax, [rdi+8]
0x14000bbb7  sub     rax, [rdi]
0x14000bbba  sub     rcx, [rdi]
0x14000bbbd  add     rax, rdx
0x14000bbc0  cmp     rax, rcx
0x14000bbc3  jb      loc_14000BC5F
0x14000bbc9  lea     rax, [rcx+rcx]
0x14000bbcd  cmp     rdx, rax
0x14000bbd0  cmovb   rbx, rax
0x14000bbd4  cmp     rcx, rbx
0x14000bbd7  jnb     loc_14000BC5F
0x14000bbdd  call    cs:__imp_GetLastError
0x14000bbe3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000bbe7  xor     ecx, ecx; dwFlags
0x14000bbe9  mov     esi, eax
0x14000bbeb  lea     r14, [rbx+40h]
0x14000bbef  mov     rdx, r14; dwBytes
0x14000bbf2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000bbf7  mov     rbx, rax
0x14000bbfa  test    rax, rax
0x14000bbfd  jnz     short loc_14000BC0B
0x14000bbff  mov     ecx, esi; dwErrCode
0x14000bc01  call    cs:__imp_SetLastError
0x14000bc07  xor     al, al
0x14000bc09  jmp     short loc_14000BC61
0x14000bc0b  mov     r15, [rdi+8]
0x14000bc0f  mov     rdx, r14; DestinationSize
0x14000bc12  sub     r15, [rdi]
0x14000bc15  mov     rcx, rbx; Destination
0x14000bc18  mov     r8, [rdi]; Source
0x14000bc1b  mov     r9, r15; SourceSize
0x14000bc1e  call    memcpy_s
0x14000bc23  mov     rbp, [rdi+18h]
0x14000bc27  mov     [rdi+18h], rbx
0x14000bc2b  test    rbp, rbp
0x14000bc2e  jz      short loc_14000BC44
0x14000bc30  call    cs:__imp_GetProcessHeap
0x14000bc36  mov     r8, rbp; lpMem
0x14000bc39  xor     edx, edx; dwFlags
0x14000bc3b  mov     rcx, rax; hHeap
0x14000bc3e  call    cs:__imp_HeapFree
0x14000bc44  lea     rax, [r15+rbx]
0x14000bc48  mov     [rdi], rbx
0x14000bc4b  mov     [rdi+8], rax
0x14000bc4f  mov     ecx, esi; dwErrCode
0x14000bc51  lea     rax, [r14+rbx]
0x14000bc55  mov     [rdi+10h], rax
0x14000bc59  call    cs:__imp_SetLastError
0x14000bc5f  mov     al, 1
0x14000bc61  add     rsp, 28h
0x14000bc65  pop     r15
0x14000bc67  pop     r14
0x14000bc69  pop     rdi
0x14000bc6a  pop     rsi
0x14000bc6b  pop     rbp
0x14000bc6c  pop     rbx
0x14000bc6d  retn
```
