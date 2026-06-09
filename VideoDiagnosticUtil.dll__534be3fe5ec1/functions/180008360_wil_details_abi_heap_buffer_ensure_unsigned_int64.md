# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180008360`
- end: `0x180008458`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800055b8`
- `0x180005be0`
- `0x180006f40`

## callees

- `0x1800054f8`
- `0x180008360`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800083ee`
- `msvcrt!memcpy_s` at `0x1800083ee`
- `KERNEL32!GetProcessHeap` at `0x180008407`
- `KERNEL32!GetProcessHeap` at `0x180008407`
- `KERNEL32!HeapFree` at `0x18000841b`
- `KERNEL32!HeapFree` at `0x18000841b`
- `KERNEL32!GetLastError` at `0x1800083a1`
- `KERNEL32!GetLastError` at `0x1800083a1`
- `KERNEL32!SetLastError` at `0x1800083cb`
- `KERNEL32!SetLastError` at `0x18000843c`
- `KERNEL32!SetLastError` at `0x1800083cb`
- `KERNEL32!SetLastError` at `0x18000843c`

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
0x180008360  push    rbx
0x180008362  push    rbp
0x180008363  push    rsi
0x180008364  push    rdi
0x180008365  push    r14
0x180008367  push    r15
0x180008369  sub     rsp, 28h
0x18000836d  mov     rdi, rcx
0x180008370  mov     rbx, rdx
0x180008373  mov     rcx, [rcx+10h]
0x180008377  mov     rax, [rdi+8]
0x18000837b  sub     rax, [rdi]
0x18000837e  sub     rcx, [rdi]
0x180008381  add     rax, rdx
0x180008384  cmp     rax, rcx
0x180008387  jb      loc_180008448
0x18000838d  lea     rax, [rcx+rcx]
0x180008391  cmp     rdx, rax
0x180008394  cmovb   rbx, rax
0x180008398  cmp     rcx, rbx
0x18000839b  jnb     loc_180008448
0x1800083a1  call    cs:__imp_GetLastError
0x1800083a8  nop     dword ptr [rax+rax+00h]
0x1800083ad  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1800083b1  xor     ecx, ecx; dwFlags
0x1800083b3  mov     esi, eax
0x1800083b5  lea     r14, [rbx+40h]
0x1800083b9  mov     rdx, r14; dwBytes
0x1800083bc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800083c1  mov     rbx, rax
0x1800083c4  test    rax, rax
0x1800083c7  jnz     short loc_1800083DB
0x1800083c9  mov     ecx, esi; dwErrCode
0x1800083cb  call    cs:__imp_SetLastError
0x1800083d2  nop     dword ptr [rax+rax+00h]
0x1800083d7  xor     al, al
0x1800083d9  jmp     short loc_18000844A
0x1800083db  mov     r15, [rdi+8]
0x1800083df  mov     rdx, r14; DestinationSize
0x1800083e2  sub     r15, [rdi]
0x1800083e5  mov     rcx, rbx; Destination
0x1800083e8  mov     r8, [rdi]; Source
0x1800083eb  mov     r9, r15; SourceSize
0x1800083ee  call    cs:__imp_memcpy_s
0x1800083f5  nop     dword ptr [rax+rax+00h]
0x1800083fa  mov     rbp, [rdi+18h]
0x1800083fe  mov     [rdi+18h], rbx
0x180008402  test    rbp, rbp
0x180008405  jz      short loc_180008427
0x180008407  call    cs:__imp_GetProcessHeap
0x18000840e  nop     dword ptr [rax+rax+00h]
0x180008413  mov     r8, rbp; lpMem
0x180008416  xor     edx, edx; dwFlags
0x180008418  mov     rcx, rax; hHeap
0x18000841b  call    cs:__imp_HeapFree
0x180008422  nop     dword ptr [rax+rax+00h]
0x180008427  lea     rax, [r15+rbx]
0x18000842b  mov     [rdi], rbx
0x18000842e  mov     [rdi+8], rax
0x180008432  mov     ecx, esi; dwErrCode
0x180008434  lea     rax, [r14+rbx]
0x180008438  mov     [rdi+10h], rax
0x18000843c  call    cs:__imp_SetLastError
0x180008443  nop     dword ptr [rax+rax+00h]
0x180008448  mov     al, 1
0x18000844a  add     rsp, 28h
0x18000844e  pop     r15
0x180008450  pop     r14
0x180008452  pop     rdi
0x180008453  pop     rsi
0x180008454  pop     rbp
0x180008455  pop     rbx
0x180008456  retn
```
