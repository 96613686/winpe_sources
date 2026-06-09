# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180009a7c`
- end: `0x180009b4e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008184`
- `0x180008750`
- `0x180009478`

## callees

- `0x1800048f8`
- `0x180005d78`
- `0x180009a7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009abd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ae1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ae1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b39`

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
0x180009a7c  push    rbx
0x180009a7e  push    rbp
0x180009a7f  push    rsi
0x180009a80  push    rdi
0x180009a81  push    r14
0x180009a83  push    r15
0x180009a85  sub     rsp, 28h
0x180009a89  mov     rdi, rcx
0x180009a8c  mov     rbx, rdx
0x180009a8f  mov     rcx, [rcx+10h]
0x180009a93  mov     rax, [rdi+8]
0x180009a97  sub     rax, [rdi]
0x180009a9a  sub     rcx, [rdi]
0x180009a9d  add     rax, rdx
0x180009aa0  cmp     rax, rcx
0x180009aa3  jb      loc_180009B3F
0x180009aa9  lea     rax, [rcx+rcx]
0x180009aad  cmp     rdx, rax
0x180009ab0  cmovb   rbx, rax
0x180009ab4  cmp     rcx, rbx
0x180009ab7  jnb     loc_180009B3F
0x180009abd  call    cs:__imp_GetLastError
0x180009ac3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180009ac7  xor     ecx, ecx; dwFlags
0x180009ac9  mov     esi, eax
0x180009acb  lea     r14, [rbx+40h]
0x180009acf  mov     rdx, r14; dwBytes
0x180009ad2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009ad7  mov     rbx, rax
0x180009ada  test    rax, rax
0x180009add  jnz     short loc_180009AEB
0x180009adf  mov     ecx, esi; dwErrCode
0x180009ae1  call    cs:__imp_SetLastError
0x180009ae7  xor     al, al
0x180009ae9  jmp     short loc_180009B41
0x180009aeb  mov     r15, [rdi+8]
0x180009aef  mov     rdx, r14; DestinationSize
0x180009af2  sub     r15, [rdi]
0x180009af5  mov     rcx, rbx; Destination
0x180009af8  mov     r8, [rdi]; Source
0x180009afb  mov     r9, r15; SourceSize
0x180009afe  call    memcpy_s
0x180009b03  mov     rbp, [rdi+18h]
0x180009b07  mov     [rdi+18h], rbx
0x180009b0b  test    rbp, rbp
0x180009b0e  jz      short loc_180009B24
0x180009b10  call    cs:__imp_GetProcessHeap
0x180009b16  mov     r8, rbp; lpMem
0x180009b19  xor     edx, edx; dwFlags
0x180009b1b  mov     rcx, rax; hHeap
0x180009b1e  call    cs:__imp_HeapFree
0x180009b24  lea     rax, [r15+rbx]
0x180009b28  mov     [rdi], rbx
0x180009b2b  mov     [rdi+8], rax
0x180009b2f  mov     ecx, esi; dwErrCode
0x180009b31  lea     rax, [r14+rbx]
0x180009b35  mov     [rdi+10h], rax
0x180009b39  call    cs:__imp_SetLastError
0x180009b3f  mov     al, 1
0x180009b41  add     rsp, 28h
0x180009b45  pop     r15
0x180009b47  pop     r14
0x180009b49  pop     rdi
0x180009b4a  pop     rsi
0x180009b4b  pop     rbp
0x180009b4c  pop     rbx
0x180009b4d  retn
```
