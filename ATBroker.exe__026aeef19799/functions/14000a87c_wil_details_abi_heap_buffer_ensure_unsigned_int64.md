# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000a87c`
- end: `0x14000a94f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400077a0`
- `0x140007930`
- `0x140008194`
- `0x140009b34`
- `0x140009d04`

## callees

- `0x1400075c8`
- `0x14000a87c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000a91f`
- `KERNEL32!HeapFree` at `0x14000a91f`
- `KERNEL32!SetLastError` at `0x14000a8e1`
- `KERNEL32!SetLastError` at `0x14000a93a`
- `KERNEL32!SetLastError` at `0x14000a8e1`
- `KERNEL32!SetLastError` at `0x14000a93a`
- `KERNEL32!GetLastError` at `0x14000a8bd`
- `KERNEL32!GetLastError` at `0x14000a8bd`
- `KERNEL32!GetProcessHeap` at `0x14000a911`
- `KERNEL32!GetProcessHeap` at `0x14000a911`
- `msvcrt!memcpy_s` at `0x14000a8fe`
- `msvcrt!memcpy_s` at `0x14000a8fe`

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
0x14000a87c  push    rbx
0x14000a87e  push    rbp
0x14000a87f  push    rsi
0x14000a880  push    rdi
0x14000a881  push    r14
0x14000a883  push    r15
0x14000a885  sub     rsp, 28h
0x14000a889  mov     rdi, rcx
0x14000a88c  mov     rbx, rdx
0x14000a88f  mov     rcx, [rcx+10h]
0x14000a893  mov     rax, [rdi+8]
0x14000a897  sub     rax, [rdi]
0x14000a89a  sub     rcx, [rdi]
0x14000a89d  add     rax, rdx
0x14000a8a0  cmp     rax, rcx
0x14000a8a3  jb      loc_14000A940
0x14000a8a9  lea     rax, [rcx+rcx]
0x14000a8ad  cmp     rdx, rax
0x14000a8b0  cmovb   rbx, rax
0x14000a8b4  cmp     rcx, rbx
0x14000a8b7  jnb     loc_14000A940
0x14000a8bd  call    cs:__imp_GetLastError
0x14000a8c3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000a8c7  xor     ecx, ecx; dwFlags
0x14000a8c9  mov     esi, eax
0x14000a8cb  lea     r14, [rbx+40h]
0x14000a8cf  mov     rdx, r14; dwBytes
0x14000a8d2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000a8d7  mov     rbx, rax
0x14000a8da  test    rax, rax
0x14000a8dd  jnz     short loc_14000A8EB
0x14000a8df  mov     ecx, esi; dwErrCode
0x14000a8e1  call    cs:__imp_SetLastError
0x14000a8e7  xor     al, al
0x14000a8e9  jmp     short loc_14000A942
0x14000a8eb  mov     r15, [rdi+8]
0x14000a8ef  mov     rdx, r14; DestinationSize
0x14000a8f2  sub     r15, [rdi]
0x14000a8f5  mov     rcx, rbx; Destination
0x14000a8f8  mov     r8, [rdi]; Source
0x14000a8fb  mov     r9, r15; SourceSize
0x14000a8fe  call    cs:__imp_memcpy_s
0x14000a904  mov     rbp, [rdi+18h]
0x14000a908  mov     [rdi+18h], rbx
0x14000a90c  test    rbp, rbp
0x14000a90f  jz      short loc_14000A925
0x14000a911  call    cs:__imp_GetProcessHeap
0x14000a917  mov     r8, rbp; lpMem
0x14000a91a  xor     edx, edx; dwFlags
0x14000a91c  mov     rcx, rax; hHeap
0x14000a91f  call    cs:__imp_HeapFree
0x14000a925  lea     rax, [r15+rbx]
0x14000a929  mov     [rdi], rbx
0x14000a92c  mov     [rdi+8], rax
0x14000a930  mov     ecx, esi; dwErrCode
0x14000a932  lea     rax, [r14+rbx]
0x14000a936  mov     [rdi+10h], rax
0x14000a93a  call    cs:__imp_SetLastError
0x14000a940  mov     al, 1
0x14000a942  add     rsp, 28h
0x14000a946  pop     r15
0x14000a948  pop     r14
0x14000a94a  pop     rdi
0x14000a94b  pop     rsi
0x14000a94c  pop     rbp
0x14000a94d  pop     rbx
0x14000a94e  retn
```
