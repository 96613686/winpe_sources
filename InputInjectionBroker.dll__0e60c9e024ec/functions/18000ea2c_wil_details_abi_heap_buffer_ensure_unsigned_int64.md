# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000ea2c`
- end: `0x18000eaff`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cd10`
- `0x18000d2b8`
- `0x18000e13c`

## callees

- `0x1800047d8`
- `0x18000ea2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000eaae`
- `msvcrt!memcpy_s` at `0x18000eaae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eac1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eacf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eacf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eaea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eaea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea6d`

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
0x18000ea2c  push    rbx
0x18000ea2e  push    rbp
0x18000ea2f  push    rsi
0x18000ea30  push    rdi
0x18000ea31  push    r14
0x18000ea33  push    r15
0x18000ea35  sub     rsp, 28h
0x18000ea39  mov     rdi, rcx
0x18000ea3c  mov     rbx, rdx
0x18000ea3f  mov     rcx, [rcx+10h]
0x18000ea43  mov     rax, [rdi+8]
0x18000ea47  sub     rax, [rdi]
0x18000ea4a  sub     rcx, [rdi]
0x18000ea4d  add     rax, rdx
0x18000ea50  cmp     rax, rcx
0x18000ea53  jb      loc_18000EAF0
0x18000ea59  lea     rax, [rcx+rcx]
0x18000ea5d  cmp     rdx, rax
0x18000ea60  cmovb   rbx, rax
0x18000ea64  cmp     rcx, rbx
0x18000ea67  jnb     loc_18000EAF0
0x18000ea6d  call    cs:__imp_GetLastError
0x18000ea73  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000ea77  xor     ecx, ecx; dwFlags
0x18000ea79  mov     esi, eax
0x18000ea7b  lea     r14, [rbx+40h]
0x18000ea7f  mov     rdx, r14; dwBytes
0x18000ea82  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ea87  mov     rbx, rax
0x18000ea8a  test    rax, rax
0x18000ea8d  jnz     short loc_18000EA9B
0x18000ea8f  mov     ecx, esi; dwErrCode
0x18000ea91  call    cs:__imp_SetLastError
0x18000ea97  xor     al, al
0x18000ea99  jmp     short loc_18000EAF2
0x18000ea9b  mov     r15, [rdi+8]
0x18000ea9f  mov     rdx, r14; DestinationSize
0x18000eaa2  sub     r15, [rdi]
0x18000eaa5  mov     rcx, rbx; Destination
0x18000eaa8  mov     r8, [rdi]; Source
0x18000eaab  mov     r9, r15; SourceSize
0x18000eaae  call    cs:__imp_memcpy_s
0x18000eab4  mov     rbp, [rdi+18h]
0x18000eab8  mov     [rdi+18h], rbx
0x18000eabc  test    rbp, rbp
0x18000eabf  jz      short loc_18000EAD5
0x18000eac1  call    cs:__imp_GetProcessHeap
0x18000eac7  mov     r8, rbp; lpMem
0x18000eaca  xor     edx, edx; dwFlags
0x18000eacc  mov     rcx, rax; hHeap
0x18000eacf  call    cs:__imp_HeapFree
0x18000ead5  lea     rax, [r15+rbx]
0x18000ead9  mov     [rdi], rbx
0x18000eadc  mov     [rdi+8], rax
0x18000eae0  mov     ecx, esi; dwErrCode
0x18000eae2  lea     rax, [r14+rbx]
0x18000eae6  mov     [rdi+10h], rax
0x18000eaea  call    cs:__imp_SetLastError
0x18000eaf0  mov     al, 1
0x18000eaf2  add     rsp, 28h
0x18000eaf6  pop     r15
0x18000eaf8  pop     r14
0x18000eafa  pop     rdi
0x18000eafb  pop     rsi
0x18000eafc  pop     rbp
0x18000eafd  pop     rbx
0x18000eafe  retn
```
