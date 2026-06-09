# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180009d2c`
- end: `0x180009dff`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007afc`
- `0x180008110`
- `0x180009348`

## callees

- `0x180007a58`
- `0x180009d2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009dae`
- `msvcrt!memcpy_s` at `0x180009dae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009dcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009dcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009dc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009dc1`

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
0x180009d2c  push    rbx
0x180009d2e  push    rbp
0x180009d2f  push    rsi
0x180009d30  push    rdi
0x180009d31  push    r14
0x180009d33  push    r15
0x180009d35  sub     rsp, 28h
0x180009d39  mov     rdi, rcx
0x180009d3c  mov     rbx, rdx
0x180009d3f  mov     rcx, [rcx+10h]
0x180009d43  mov     rax, [rdi+8]
0x180009d47  sub     rax, [rdi]
0x180009d4a  sub     rcx, [rdi]
0x180009d4d  add     rax, rdx
0x180009d50  cmp     rax, rcx
0x180009d53  jb      loc_180009DF0
0x180009d59  lea     rax, [rcx+rcx]
0x180009d5d  cmp     rdx, rax
0x180009d60  cmovb   rbx, rax
0x180009d64  cmp     rcx, rbx
0x180009d67  jnb     loc_180009DF0
0x180009d6d  call    cs:__imp_GetLastError
0x180009d73  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180009d77  xor     ecx, ecx; dwFlags
0x180009d79  mov     esi, eax
0x180009d7b  lea     r14, [rbx+40h]
0x180009d7f  mov     rdx, r14; dwBytes
0x180009d82  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009d87  mov     rbx, rax
0x180009d8a  test    rax, rax
0x180009d8d  jnz     short loc_180009D9B
0x180009d8f  mov     ecx, esi; dwErrCode
0x180009d91  call    cs:__imp_SetLastError
0x180009d97  xor     al, al
0x180009d99  jmp     short loc_180009DF2
0x180009d9b  mov     r15, [rdi+8]
0x180009d9f  mov     rdx, r14; DestinationSize
0x180009da2  sub     r15, [rdi]
0x180009da5  mov     rcx, rbx; Destination
0x180009da8  mov     r8, [rdi]; Source
0x180009dab  mov     r9, r15; SourceSize
0x180009dae  call    cs:__imp_memcpy_s
0x180009db4  mov     rbp, [rdi+18h]
0x180009db8  mov     [rdi+18h], rbx
0x180009dbc  test    rbp, rbp
0x180009dbf  jz      short loc_180009DD5
0x180009dc1  call    cs:__imp_GetProcessHeap
0x180009dc7  mov     r8, rbp; lpMem
0x180009dca  xor     edx, edx; dwFlags
0x180009dcc  mov     rcx, rax; hHeap
0x180009dcf  call    cs:__imp_HeapFree
0x180009dd5  lea     rax, [r15+rbx]
0x180009dd9  mov     [rdi], rbx
0x180009ddc  mov     [rdi+8], rax
0x180009de0  mov     ecx, esi; dwErrCode
0x180009de2  lea     rax, [r14+rbx]
0x180009de6  mov     [rdi+10h], rax
0x180009dea  call    cs:__imp_SetLastError
0x180009df0  mov     al, 1
0x180009df2  add     rsp, 28h
0x180009df6  pop     r15
0x180009df8  pop     r14
0x180009dfa  pop     rdi
0x180009dfb  pop     rsi
0x180009dfc  pop     rbp
0x180009dfd  pop     rbx
0x180009dfe  retn
```
