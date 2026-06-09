# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000eb4c`
- end: `0x18000ec1e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a018`
- `0x18000a1bc`
- `0x18000aa58`
- `0x18000d31c`
- `0x18000d524`

## callees

- `0x180009ccc`
- `0x18000eb4c`
- `0x18000fbf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ebe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ebe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ebb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ec09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ebb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ec09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb8d`

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
0x18000eb4c  push    rbx
0x18000eb4e  push    rbp
0x18000eb4f  push    rsi
0x18000eb50  push    rdi
0x18000eb51  push    r14
0x18000eb53  push    r15
0x18000eb55  sub     rsp, 28h
0x18000eb59  mov     rdi, rcx
0x18000eb5c  mov     rbx, rdx
0x18000eb5f  mov     rcx, [rcx+10h]
0x18000eb63  mov     rax, [rdi+8]
0x18000eb67  sub     rax, [rdi]
0x18000eb6a  sub     rcx, [rdi]
0x18000eb6d  add     rax, rdx
0x18000eb70  cmp     rax, rcx
0x18000eb73  jb      loc_18000EC0F
0x18000eb79  lea     rax, [rcx+rcx]
0x18000eb7d  cmp     rdx, rax
0x18000eb80  cmovb   rbx, rax
0x18000eb84  cmp     rcx, rbx
0x18000eb87  jnb     loc_18000EC0F
0x18000eb8d  call    cs:__imp_GetLastError
0x18000eb93  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000eb97  xor     ecx, ecx; dwFlags
0x18000eb99  mov     esi, eax
0x18000eb9b  lea     r14, [rbx+40h]
0x18000eb9f  mov     rdx, r14; dwBytes
0x18000eba2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000eba7  mov     rbx, rax
0x18000ebaa  test    rax, rax
0x18000ebad  jnz     short loc_18000EBBB
0x18000ebaf  mov     ecx, esi; dwErrCode
0x18000ebb1  call    cs:__imp_SetLastError
0x18000ebb7  xor     al, al
0x18000ebb9  jmp     short loc_18000EC11
0x18000ebbb  mov     r15, [rdi+8]
0x18000ebbf  mov     rdx, r14; DestinationSize
0x18000ebc2  sub     r15, [rdi]
0x18000ebc5  mov     rcx, rbx; Destination
0x18000ebc8  mov     r8, [rdi]; Source
0x18000ebcb  mov     r9, r15; SourceSize
0x18000ebce  call    memcpy_s
0x18000ebd3  mov     rbp, [rdi+18h]
0x18000ebd7  mov     [rdi+18h], rbx
0x18000ebdb  test    rbp, rbp
0x18000ebde  jz      short loc_18000EBF4
0x18000ebe0  call    cs:__imp_GetProcessHeap
0x18000ebe6  mov     r8, rbp; lpMem
0x18000ebe9  xor     edx, edx; dwFlags
0x18000ebeb  mov     rcx, rax; hHeap
0x18000ebee  call    cs:__imp_HeapFree
0x18000ebf4  lea     rax, [r15+rbx]
0x18000ebf8  mov     [rdi], rbx
0x18000ebfb  mov     [rdi+8], rax
0x18000ebff  mov     ecx, esi; dwErrCode
0x18000ec01  lea     rax, [r14+rbx]
0x18000ec05  mov     [rdi+10h], rax
0x18000ec09  call    cs:__imp_SetLastError
0x18000ec0f  mov     al, 1
0x18000ec11  add     rsp, 28h
0x18000ec15  pop     r15
0x18000ec17  pop     r14
0x18000ec19  pop     rdi
0x18000ec1a  pop     rsi
0x18000ec1b  pop     rbp
0x18000ec1c  pop     rbx
0x18000ec1d  retn
```
