# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x1800162c4`
- end: `0x180016397`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180013e70`
- `0x180014000`
- `0x1800147a8`
- `0x1800159a4`
- `0x180015b74`

## callees

- `0x18000edc0`
- `0x1800162c4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180016346`
- `msvcrt!memcpy_s` at `0x180016346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016329`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016382`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016329`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016305`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016359`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016359`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016367`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016367`

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
0x1800162c4  push    rbx
0x1800162c6  push    rbp
0x1800162c7  push    rsi
0x1800162c8  push    rdi
0x1800162c9  push    r14
0x1800162cb  push    r15
0x1800162cd  sub     rsp, 28h
0x1800162d1  mov     rdi, rcx
0x1800162d4  mov     rbx, rdx
0x1800162d7  mov     rcx, [rcx+10h]
0x1800162db  mov     rax, [rdi+8]
0x1800162df  sub     rax, [rdi]
0x1800162e2  sub     rcx, [rdi]
0x1800162e5  add     rax, rdx
0x1800162e8  cmp     rax, rcx
0x1800162eb  jb      loc_180016388
0x1800162f1  lea     rax, [rcx+rcx]
0x1800162f5  cmp     rdx, rax
0x1800162f8  cmovb   rbx, rax
0x1800162fc  cmp     rcx, rbx
0x1800162ff  jnb     loc_180016388
0x180016305  call    cs:__imp_GetLastError
0x18001630b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18001630f  xor     ecx, ecx; dwFlags
0x180016311  mov     esi, eax
0x180016313  lea     r14, [rbx+40h]
0x180016317  mov     rdx, r14; dwBytes
0x18001631a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001631f  mov     rbx, rax
0x180016322  test    rax, rax
0x180016325  jnz     short loc_180016333
0x180016327  mov     ecx, esi; dwErrCode
0x180016329  call    cs:__imp_SetLastError
0x18001632f  xor     al, al
0x180016331  jmp     short loc_18001638A
0x180016333  mov     r15, [rdi+8]
0x180016337  mov     rdx, r14; DestinationSize
0x18001633a  sub     r15, [rdi]
0x18001633d  mov     rcx, rbx; Destination
0x180016340  mov     r8, [rdi]; Source
0x180016343  mov     r9, r15; SourceSize
0x180016346  call    cs:__imp_memcpy_s
0x18001634c  mov     rbp, [rdi+18h]
0x180016350  mov     [rdi+18h], rbx
0x180016354  test    rbp, rbp
0x180016357  jz      short loc_18001636D
0x180016359  call    cs:__imp_GetProcessHeap
0x18001635f  mov     r8, rbp; lpMem
0x180016362  xor     edx, edx; dwFlags
0x180016364  mov     rcx, rax; hHeap
0x180016367  call    cs:__imp_HeapFree
0x18001636d  lea     rax, [r15+rbx]
0x180016371  mov     [rdi], rbx
0x180016374  mov     [rdi+8], rax
0x180016378  mov     ecx, esi; dwErrCode
0x18001637a  lea     rax, [r14+rbx]
0x18001637e  mov     [rdi+10h], rax
0x180016382  call    cs:__imp_SetLastError
0x180016388  mov     al, 1
0x18001638a  add     rsp, 28h
0x18001638e  pop     r15
0x180016390  pop     r14
0x180016392  pop     rdi
0x180016393  pop     rsi
0x180016394  pop     rbp
0x180016395  pop     rbx
0x180016396  retn
```
