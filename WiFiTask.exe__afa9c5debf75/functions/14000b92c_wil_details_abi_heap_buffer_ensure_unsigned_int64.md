# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000b92c`
- end: `0x14000b9fe`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140007ed0`
- `0x140008074`
- `0x1400088c8`
- `0x14000a88c`
- `0x14000aa94`

## callees

- `0x140007d2c`
- `0x14000b92c`
- `0x14000c1a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b9ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b9ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b9c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b9c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b991`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b9e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b991`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b9e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b96d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b96d`

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
0x14000b92c  push    rbx
0x14000b92e  push    rbp
0x14000b92f  push    rsi
0x14000b930  push    rdi
0x14000b931  push    r14
0x14000b933  push    r15
0x14000b935  sub     rsp, 28h
0x14000b939  mov     rdi, rcx
0x14000b93c  mov     rbx, rdx
0x14000b93f  mov     rcx, [rcx+10h]
0x14000b943  mov     rax, [rdi+8]
0x14000b947  sub     rax, [rdi]
0x14000b94a  sub     rcx, [rdi]
0x14000b94d  add     rax, rdx
0x14000b950  cmp     rax, rcx
0x14000b953  jb      loc_14000B9EF
0x14000b959  lea     rax, [rcx+rcx]
0x14000b95d  cmp     rdx, rax
0x14000b960  cmovb   rbx, rax
0x14000b964  cmp     rcx, rbx
0x14000b967  jnb     loc_14000B9EF
0x14000b96d  call    cs:__imp_GetLastError
0x14000b973  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000b977  xor     ecx, ecx; dwFlags
0x14000b979  mov     esi, eax
0x14000b97b  lea     r14, [rbx+40h]
0x14000b97f  mov     rdx, r14; dwBytes
0x14000b982  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000b987  mov     rbx, rax
0x14000b98a  test    rax, rax
0x14000b98d  jnz     short loc_14000B99B
0x14000b98f  mov     ecx, esi; dwErrCode
0x14000b991  call    cs:__imp_SetLastError
0x14000b997  xor     al, al
0x14000b999  jmp     short loc_14000B9F1
0x14000b99b  mov     r15, [rdi+8]
0x14000b99f  mov     rdx, r14; DestinationSize
0x14000b9a2  sub     r15, [rdi]
0x14000b9a5  mov     rcx, rbx; Destination
0x14000b9a8  mov     r8, [rdi]; Source
0x14000b9ab  mov     r9, r15; SourceSize
0x14000b9ae  call    memcpy_s
0x14000b9b3  mov     rbp, [rdi+18h]
0x14000b9b7  mov     [rdi+18h], rbx
0x14000b9bb  test    rbp, rbp
0x14000b9be  jz      short loc_14000B9D4
0x14000b9c0  call    cs:__imp_GetProcessHeap
0x14000b9c6  mov     r8, rbp; lpMem
0x14000b9c9  xor     edx, edx; dwFlags
0x14000b9cb  mov     rcx, rax; hHeap
0x14000b9ce  call    cs:__imp_HeapFree
0x14000b9d4  lea     rax, [r15+rbx]
0x14000b9d8  mov     [rdi], rbx
0x14000b9db  mov     [rdi+8], rax
0x14000b9df  mov     ecx, esi; dwErrCode
0x14000b9e1  lea     rax, [r14+rbx]
0x14000b9e5  mov     [rdi+10h], rax
0x14000b9e9  call    cs:__imp_SetLastError
0x14000b9ef  mov     al, 1
0x14000b9f1  add     rsp, 28h
0x14000b9f5  pop     r15
0x14000b9f7  pop     r14
0x14000b9f9  pop     rdi
0x14000b9fa  pop     rsi
0x14000b9fb  pop     rbp
0x14000b9fc  pop     rbx
0x14000b9fd  retn
```
