# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000c40c`
- end: `0x18000c4ec`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `224`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007f44`
- `0x180008998`
- `0x18000a048`
- `0x18000a220`

## callees

- `0x180007dfc`
- `0x18000c40c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c498`
- `msvcrt!memcpy_s` at `0x18000c498`
- `KERNEL32!SetLastError` at `0x18000c47a`
- `KERNEL32!SetLastError` at `0x18000c4d6`
- `KERNEL32!SetLastError` at `0x18000c47a`
- `KERNEL32!SetLastError` at `0x18000c4d6`
- `KERNEL32!GetProcessHeap` at `0x18000c4ac`
- `KERNEL32!GetProcessHeap` at `0x18000c4ac`
- `KERNEL32!HeapFree` at `0x18000c4ba`
- `KERNEL32!HeapFree` at `0x18000c4ba`
- `KERNEL32!GetLastError` at `0x18000c44d`
- `KERNEL32!GetLastError` at `0x18000c44d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
  HANDLE ProcessHeap; // rax

  v2 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this >= v4 )
  {
    if ( a2 < 2 * v4 )
      v2 = 2 * v4;
    if ( v4 < v2 )
    {
      LastError = GetLastError();
      v6 = (v2 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
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
0x18000c40c  push    rbx
0x18000c40e  push    rbp
0x18000c40f  push    rsi
0x18000c410  push    rdi
0x18000c411  push    r14
0x18000c413  push    r15
0x18000c415  sub     rsp, 28h
0x18000c419  mov     rbx, rdx
0x18000c41c  mov     rdi, rcx
0x18000c41f  mov     rcx, [rcx+10h]
0x18000c423  sub     rcx, [rdi]
0x18000c426  mov     rax, [rdi+8]
0x18000c42a  sub     rax, [rdi]
0x18000c42d  add     rax, rdx
0x18000c430  cmp     rax, rcx
0x18000c433  jb      loc_18000C4DD
0x18000c439  lea     rax, [rcx+rcx]
0x18000c43d  cmp     rdx, rax
0x18000c440  cmovb   rbx, rax
0x18000c444  cmp     rcx, rbx
0x18000c447  jnb     loc_18000C4DD
0x18000c44d  call    cs:__imp_GetLastError
0x18000c453  mov     esi, eax
0x18000c455  mov     [rsp+58h+arg_0], 0
0x18000c45a  mov     [rsp+58h+arg_4], eax
0x18000c45e  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000c462  lea     r14, [rbx+40h]
0x18000c466  mov     rdx, r14; dwBytes
0x18000c469  xor     ecx, ecx; dwFlags
0x18000c46b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c470  mov     rbx, rax
0x18000c473  test    rax, rax
0x18000c476  jnz     short loc_18000C485
0x18000c478  mov     ecx, esi; dwErrCode
0x18000c47a  call    cs:__imp_SetLastError
0x18000c480  nop
0x18000c481  xor     al, al
0x18000c483  jmp     short loc_18000C4DF
0x18000c485  mov     r15, [rdi+8]
0x18000c489  sub     r15, [rdi]
0x18000c48c  mov     r9, r15; SourceSize
0x18000c48f  mov     r8, [rdi]; Source
0x18000c492  mov     rdx, r14; DestinationSize
0x18000c495  mov     rcx, rbx; Destination
0x18000c498  call    cs:__imp_memcpy_s
0x18000c49e  nop
0x18000c49f  mov     rbp, [rdi+18h]
0x18000c4a3  mov     [rdi+18h], rbx
0x18000c4a7  test    rbp, rbp
0x18000c4aa  jz      short loc_18000C4C1
0x18000c4ac  call    cs:__imp_GetProcessHeap
0x18000c4b2  mov     rcx, rax; hHeap
0x18000c4b5  mov     r8, rbp; lpMem
0x18000c4b8  xor     edx, edx; dwFlags
0x18000c4ba  call    cs:__imp_HeapFree
0x18000c4c0  nop
0x18000c4c1  mov     [rdi], rbx
0x18000c4c4  lea     rax, [r15+rbx]
0x18000c4c8  mov     [rdi+8], rax
0x18000c4cc  lea     rax, [r14+rbx]
0x18000c4d0  mov     [rdi+10h], rax
0x18000c4d4  mov     ecx, esi; dwErrCode
0x18000c4d6  call    cs:__imp_SetLastError
0x18000c4dc  nop
0x18000c4dd  mov     al, 1
0x18000c4df  add     rsp, 28h
0x18000c4e3  pop     r15
0x18000c4e5  pop     r14
0x18000c4e7  pop     rdi
0x18000c4e8  pop     rsi
0x18000c4e9  pop     rbp
0x18000c4ea  pop     rbx
0x18000c4eb  retn
```
