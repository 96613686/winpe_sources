# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180007bbc`
- end: `0x180007c8e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000587c`
- `0x180005eb0`
- `0x1800071a8`

## callees

- `0x1800057d8`
- `0x180007bbc`
- `0x180007ed4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c79`

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
0x180007bbc  push    rbx
0x180007bbe  push    rbp
0x180007bbf  push    rsi
0x180007bc0  push    rdi
0x180007bc1  push    r14
0x180007bc3  push    r15
0x180007bc5  sub     rsp, 28h
0x180007bc9  mov     rdi, rcx
0x180007bcc  mov     rbx, rdx
0x180007bcf  mov     rcx, [rcx+10h]
0x180007bd3  mov     rax, [rdi+8]
0x180007bd7  sub     rax, [rdi]
0x180007bda  sub     rcx, [rdi]
0x180007bdd  add     rax, rdx
0x180007be0  cmp     rax, rcx
0x180007be3  jb      loc_180007C7F
0x180007be9  lea     rax, [rcx+rcx]
0x180007bed  cmp     rdx, rax
0x180007bf0  cmovb   rbx, rax
0x180007bf4  cmp     rcx, rbx
0x180007bf7  jnb     loc_180007C7F
0x180007bfd  call    cs:__imp_GetLastError
0x180007c03  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180007c07  xor     ecx, ecx; dwFlags
0x180007c09  mov     esi, eax
0x180007c0b  lea     r14, [rbx+40h]
0x180007c0f  mov     rdx, r14; dwBytes
0x180007c12  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007c17  mov     rbx, rax
0x180007c1a  test    rax, rax
0x180007c1d  jnz     short loc_180007C2B
0x180007c1f  mov     ecx, esi; dwErrCode
0x180007c21  call    cs:__imp_SetLastError
0x180007c27  xor     al, al
0x180007c29  jmp     short loc_180007C81
0x180007c2b  mov     r15, [rdi+8]
0x180007c2f  mov     rdx, r14; DestinationSize
0x180007c32  sub     r15, [rdi]
0x180007c35  mov     rcx, rbx; Destination
0x180007c38  mov     r8, [rdi]; Source
0x180007c3b  mov     r9, r15; SourceSize
0x180007c3e  call    memcpy_s
0x180007c43  mov     rbp, [rdi+18h]
0x180007c47  mov     [rdi+18h], rbx
0x180007c4b  test    rbp, rbp
0x180007c4e  jz      short loc_180007C64
0x180007c50  call    cs:__imp_GetProcessHeap
0x180007c56  mov     r8, rbp; lpMem
0x180007c59  xor     edx, edx; dwFlags
0x180007c5b  mov     rcx, rax; hHeap
0x180007c5e  call    cs:__imp_HeapFree
0x180007c64  lea     rax, [r15+rbx]
0x180007c68  mov     [rdi], rbx
0x180007c6b  mov     [rdi+8], rax
0x180007c6f  mov     ecx, esi; dwErrCode
0x180007c71  lea     rax, [r14+rbx]
0x180007c75  mov     [rdi+10h], rax
0x180007c79  call    cs:__imp_SetLastError
0x180007c7f  mov     al, 1
0x180007c81  add     rsp, 28h
0x180007c85  pop     r15
0x180007c87  pop     r14
0x180007c89  pop     rdi
0x180007c8a  pop     rsi
0x180007c8b  pop     rbp
0x180007c8c  pop     rbx
0x180007c8d  retn
```
