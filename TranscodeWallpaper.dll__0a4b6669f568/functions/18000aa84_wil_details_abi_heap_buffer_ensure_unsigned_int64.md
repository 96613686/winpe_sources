# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000aa84`
- end: `0x18000ab56`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008c40`
- `0x18000920c`
- `0x18000a454`

## callees

- `0x180005678`
- `0x180006fa4`
- `0x18000aa84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aac5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aae9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aae9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab41`

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
0x18000aa84  push    rbx
0x18000aa86  push    rbp
0x18000aa87  push    rsi
0x18000aa88  push    rdi
0x18000aa89  push    r14
0x18000aa8b  push    r15
0x18000aa8d  sub     rsp, 28h
0x18000aa91  mov     rdi, rcx
0x18000aa94  mov     rbx, rdx
0x18000aa97  mov     rcx, [rcx+10h]
0x18000aa9b  mov     rax, [rdi+8]
0x18000aa9f  sub     rax, [rdi]
0x18000aaa2  sub     rcx, [rdi]
0x18000aaa5  add     rax, rdx
0x18000aaa8  cmp     rax, rcx
0x18000aaab  jb      loc_18000AB47
0x18000aab1  lea     rax, [rcx+rcx]
0x18000aab5  cmp     rdx, rax
0x18000aab8  cmovb   rbx, rax
0x18000aabc  cmp     rcx, rbx
0x18000aabf  jnb     loc_18000AB47
0x18000aac5  call    cs:__imp_GetLastError
0x18000aacb  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000aacf  xor     ecx, ecx; dwFlags
0x18000aad1  mov     esi, eax
0x18000aad3  lea     r14, [rbx+40h]
0x18000aad7  mov     rdx, r14; dwBytes
0x18000aada  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000aadf  mov     rbx, rax
0x18000aae2  test    rax, rax
0x18000aae5  jnz     short loc_18000AAF3
0x18000aae7  mov     ecx, esi; dwErrCode
0x18000aae9  call    cs:__imp_SetLastError
0x18000aaef  xor     al, al
0x18000aaf1  jmp     short loc_18000AB49
0x18000aaf3  mov     r15, [rdi+8]
0x18000aaf7  mov     rdx, r14; DestinationSize
0x18000aafa  sub     r15, [rdi]
0x18000aafd  mov     rcx, rbx; Destination
0x18000ab00  mov     r8, [rdi]; Source
0x18000ab03  mov     r9, r15; SourceSize
0x18000ab06  call    memcpy_s
0x18000ab0b  mov     rbp, [rdi+18h]
0x18000ab0f  mov     [rdi+18h], rbx
0x18000ab13  test    rbp, rbp
0x18000ab16  jz      short loc_18000AB2C
0x18000ab18  call    cs:__imp_GetProcessHeap
0x18000ab1e  mov     r8, rbp; lpMem
0x18000ab21  xor     edx, edx; dwFlags
0x18000ab23  mov     rcx, rax; hHeap
0x18000ab26  call    cs:__imp_HeapFree
0x18000ab2c  lea     rax, [r15+rbx]
0x18000ab30  mov     [rdi], rbx
0x18000ab33  mov     [rdi+8], rax
0x18000ab37  mov     ecx, esi; dwErrCode
0x18000ab39  lea     rax, [r14+rbx]
0x18000ab3d  mov     [rdi+10h], rax
0x18000ab41  call    cs:__imp_SetLastError
0x18000ab47  mov     al, 1
0x18000ab49  add     rsp, 28h
0x18000ab4d  pop     r15
0x18000ab4f  pop     r14
0x18000ab51  pop     rdi
0x18000ab52  pop     rsi
0x18000ab53  pop     rbp
0x18000ab54  pop     rbx
0x18000ab55  retn
```
