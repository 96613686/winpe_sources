# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180008f3c`
- end: `0x18000900e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800062e8`
- `0x180006488`
- `0x180006cc4`
- `0x180008250`
- `0x180008458`

## callees

- `0x1800061a8`
- `0x180008f3c`
- `0x1800094bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ff9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ff9`

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
0x180008f3c  push    rbx
0x180008f3e  push    rbp
0x180008f3f  push    rsi
0x180008f40  push    rdi
0x180008f41  push    r14
0x180008f43  push    r15
0x180008f45  sub     rsp, 28h
0x180008f49  mov     rdi, rcx
0x180008f4c  mov     rbx, rdx
0x180008f4f  mov     rcx, [rcx+10h]
0x180008f53  mov     rax, [rdi+8]
0x180008f57  sub     rax, [rdi]
0x180008f5a  sub     rcx, [rdi]
0x180008f5d  add     rax, rdx
0x180008f60  cmp     rax, rcx
0x180008f63  jb      loc_180008FFF
0x180008f69  lea     rax, [rcx+rcx]
0x180008f6d  cmp     rdx, rax
0x180008f70  cmovb   rbx, rax
0x180008f74  cmp     rcx, rbx
0x180008f77  jnb     loc_180008FFF
0x180008f7d  call    cs:__imp_GetLastError
0x180008f83  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180008f87  xor     ecx, ecx; dwFlags
0x180008f89  mov     esi, eax
0x180008f8b  lea     r14, [rbx+40h]
0x180008f8f  mov     rdx, r14; dwBytes
0x180008f92  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008f97  mov     rbx, rax
0x180008f9a  test    rax, rax
0x180008f9d  jnz     short loc_180008FAB
0x180008f9f  mov     ecx, esi; dwErrCode
0x180008fa1  call    cs:__imp_SetLastError
0x180008fa7  xor     al, al
0x180008fa9  jmp     short loc_180009001
0x180008fab  mov     r15, [rdi+8]
0x180008faf  mov     rdx, r14; DestinationSize
0x180008fb2  sub     r15, [rdi]
0x180008fb5  mov     rcx, rbx; Destination
0x180008fb8  mov     r8, [rdi]; Source
0x180008fbb  mov     r9, r15; SourceSize
0x180008fbe  call    memcpy_s
0x180008fc3  mov     rbp, [rdi+18h]
0x180008fc7  mov     [rdi+18h], rbx
0x180008fcb  test    rbp, rbp
0x180008fce  jz      short loc_180008FE4
0x180008fd0  call    cs:__imp_GetProcessHeap
0x180008fd6  mov     r8, rbp; lpMem
0x180008fd9  xor     edx, edx; dwFlags
0x180008fdb  mov     rcx, rax; hHeap
0x180008fde  call    cs:__imp_HeapFree
0x180008fe4  lea     rax, [r15+rbx]
0x180008fe8  mov     [rdi], rbx
0x180008feb  mov     [rdi+8], rax
0x180008fef  mov     ecx, esi; dwErrCode
0x180008ff1  lea     rax, [r14+rbx]
0x180008ff5  mov     [rdi+10h], rax
0x180008ff9  call    cs:__imp_SetLastError
0x180008fff  mov     al, 1
0x180009001  add     rsp, 28h
0x180009005  pop     r15
0x180009007  pop     r14
0x180009009  pop     rdi
0x18000900a  pop     rsi
0x18000900b  pop     rbp
0x18000900c  pop     rbx
0x18000900d  retn
```
