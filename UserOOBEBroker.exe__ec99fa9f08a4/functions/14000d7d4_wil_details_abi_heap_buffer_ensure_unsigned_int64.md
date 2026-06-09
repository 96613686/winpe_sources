# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000d7d4`
- end: `0x14000d8a7`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000aba0`
- `0x14000ad30`
- `0x14000b4d8`
- `0x14000ca88`
- `0x14000cc58`

## callees

- `0x140005088`
- `0x14000d7d4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000d877`
- `KERNEL32!HeapFree` at `0x14000d877`
- `KERNEL32!SetLastError` at `0x14000d839`
- `KERNEL32!SetLastError` at `0x14000d892`
- `KERNEL32!SetLastError` at `0x14000d839`
- `KERNEL32!SetLastError` at `0x14000d892`
- `KERNEL32!GetLastError` at `0x14000d815`
- `KERNEL32!GetLastError` at `0x14000d815`
- `KERNEL32!GetProcessHeap` at `0x14000d869`
- `KERNEL32!GetProcessHeap` at `0x14000d869`
- `msvcrt!memcpy_s` at `0x14000d856`
- `msvcrt!memcpy_s` at `0x14000d856`

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
0x14000d7d4  push    rbx
0x14000d7d6  push    rbp
0x14000d7d7  push    rsi
0x14000d7d8  push    rdi
0x14000d7d9  push    r14
0x14000d7db  push    r15
0x14000d7dd  sub     rsp, 28h
0x14000d7e1  mov     rdi, rcx
0x14000d7e4  mov     rbx, rdx
0x14000d7e7  mov     rcx, [rcx+10h]
0x14000d7eb  mov     rax, [rdi+8]
0x14000d7ef  sub     rax, [rdi]
0x14000d7f2  sub     rcx, [rdi]
0x14000d7f5  add     rax, rdx
0x14000d7f8  cmp     rax, rcx
0x14000d7fb  jb      loc_14000D898
0x14000d801  lea     rax, [rcx+rcx]
0x14000d805  cmp     rdx, rax
0x14000d808  cmovb   rbx, rax
0x14000d80c  cmp     rcx, rbx
0x14000d80f  jnb     loc_14000D898
0x14000d815  call    cs:__imp_GetLastError
0x14000d81b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000d81f  xor     ecx, ecx; dwFlags
0x14000d821  mov     esi, eax
0x14000d823  lea     r14, [rbx+40h]
0x14000d827  mov     rdx, r14; dwBytes
0x14000d82a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000d82f  mov     rbx, rax
0x14000d832  test    rax, rax
0x14000d835  jnz     short loc_14000D843
0x14000d837  mov     ecx, esi; dwErrCode
0x14000d839  call    cs:__imp_SetLastError
0x14000d83f  xor     al, al
0x14000d841  jmp     short loc_14000D89A
0x14000d843  mov     r15, [rdi+8]
0x14000d847  mov     rdx, r14; DestinationSize
0x14000d84a  sub     r15, [rdi]
0x14000d84d  mov     rcx, rbx; Destination
0x14000d850  mov     r8, [rdi]; Source
0x14000d853  mov     r9, r15; SourceSize
0x14000d856  call    cs:__imp_memcpy_s
0x14000d85c  mov     rbp, [rdi+18h]
0x14000d860  mov     [rdi+18h], rbx
0x14000d864  test    rbp, rbp
0x14000d867  jz      short loc_14000D87D
0x14000d869  call    cs:__imp_GetProcessHeap
0x14000d86f  mov     r8, rbp; lpMem
0x14000d872  xor     edx, edx; dwFlags
0x14000d874  mov     rcx, rax; hHeap
0x14000d877  call    cs:__imp_HeapFree
0x14000d87d  lea     rax, [r15+rbx]
0x14000d881  mov     [rdi], rbx
0x14000d884  mov     [rdi+8], rax
0x14000d888  mov     ecx, esi; dwErrCode
0x14000d88a  lea     rax, [r14+rbx]
0x14000d88e  mov     [rdi+10h], rax
0x14000d892  call    cs:__imp_SetLastError
0x14000d898  mov     al, 1
0x14000d89a  add     rsp, 28h
0x14000d89e  pop     r15
0x14000d8a0  pop     r14
0x14000d8a2  pop     rdi
0x14000d8a3  pop     rsi
0x14000d8a4  pop     rbp
0x14000d8a5  pop     rbx
0x14000d8a6  retn
```
