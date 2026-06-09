# wil::details_abi::heap_buffer::reserve(unsigned __int64)

- ea: `0x140003f40`
- end: `0x140004015`
- name: `?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `213`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140003950`
- `0x140003bb8`
- `0x140003d20`
- `0x140003e30`
- `0x140003f10`

## callees

- `0x140003f40`
- `0x140006030`
- `0x14000837c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003fda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003fda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003fcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003ff5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003f87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003ff5`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::reserve(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  DWORD LastError; // esi
  unsigned __int64 v5; // r14
  char *v6; // rax
  char *v7; // rdi
  rsize_t v9; // r15
  void *v10; // rbp
  HANDLE ProcessHeap; // rax

  if ( *((_QWORD *)this + 2) - *(_QWORD *)this < a2 )
  {
    LastError = GetLastError();
    v5 = (a2 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
    v6 = (char *)wil::details::ProcessHeapAlloc(0, v5);
    v7 = v6;
    if ( !v6 )
    {
      SetLastError(LastError);
      return 0;
    }
    v9 = *((_QWORD *)this + 1) - *(_QWORD *)this;
    memcpy_s(v6, v5, *(const void *const *)this, v9);
    v10 = (void *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v7;
    if ( v10 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
    *(_QWORD *)this = v7;
    *((_QWORD *)this + 1) = &v7[v9];
    *((_QWORD *)this + 2) = &v7[v5];
    SetLastError(LastError);
  }
  return 1;
}

```

## disassembly

```asm
0x140003f40  mov     [rsp+arg_10], rbx
0x140003f45  push    rsi
0x140003f46  push    rdi
0x140003f47  push    r14
0x140003f49  sub     rsp, 20h
0x140003f4d  mov     rax, [rcx+10h]
0x140003f51  mov     rdi, rdx
0x140003f54  sub     rax, [rcx]
0x140003f57  mov     rbx, rcx
0x140003f5a  cmp     rax, rdx
0x140003f5d  jnb     loc_140004005
0x140003f63  call    cs:__imp_GetLastError
0x140003f69  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140003f6d  xor     ecx, ecx; dwFlags
0x140003f6f  mov     esi, eax
0x140003f71  lea     r14, [rdi+40h]
0x140003f75  mov     rdx, r14; dwBytes
0x140003f78  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003f7d  mov     rdi, rax
0x140003f80  test    rax, rax
0x140003f83  jnz     short loc_140003F9D
0x140003f85  mov     ecx, esi; dwErrCode
0x140003f87  call    cs:__imp_SetLastError
0x140003f8d  xor     al, al
0x140003f8f  mov     rbx, [rsp+38h+arg_10]
0x140003f94  add     rsp, 20h
0x140003f98  pop     r14
0x140003f9a  pop     rdi
0x140003f9b  pop     rsi
0x140003f9c  retn
0x140003f9d  mov     r8, [rbx]; Source
0x140003fa0  mov     rdx, r14; DestinationSize
0x140003fa3  mov     [rsp+38h+arg_0], rbp
0x140003fa8  mov     rcx, rdi; Destination
0x140003fab  mov     [rsp+38h+arg_8], r15
0x140003fb0  mov     r15, [rbx+8]
0x140003fb4  sub     r15, r8
0x140003fb7  mov     r9, r15; SourceSize
0x140003fba  call    memcpy_s
0x140003fbf  mov     rbp, [rbx+18h]
0x140003fc3  mov     [rbx+18h], rdi
0x140003fc7  test    rbp, rbp
0x140003fca  jz      short loc_140003FE0
0x140003fcc  call    cs:__imp_GetProcessHeap
0x140003fd2  mov     r8, rbp; lpMem
0x140003fd5  xor     edx, edx; dwFlags
0x140003fd7  mov     rcx, rax; hHeap
0x140003fda  call    cs:__imp_HeapFree
0x140003fe0  lea     rax, [r15+rdi]
0x140003fe4  mov     [rbx], rdi
0x140003fe7  mov     [rbx+8], rax
0x140003feb  mov     ecx, esi; dwErrCode
0x140003fed  lea     rax, [r14+rdi]
0x140003ff1  mov     [rbx+10h], rax
0x140003ff5  call    cs:__imp_SetLastError
0x140003ffb  mov     r15, [rsp+38h+arg_8]
0x140004000  mov     rbp, [rsp+38h+arg_0]
0x140004005  mov     rbx, [rsp+38h+arg_10]
0x14000400a  mov     al, 1
0x14000400c  add     rsp, 20h
0x140004010  pop     r14
0x140004012  pop     rdi
0x140004013  pop     rsi
0x140004014  retn
```
