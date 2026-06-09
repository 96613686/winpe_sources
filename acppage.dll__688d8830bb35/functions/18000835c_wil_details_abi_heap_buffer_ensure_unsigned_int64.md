# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000835c`
- end: `0x18000842f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e98`
- `0x180006694`
- `0x180007690`
- `0x180007860`
- `0x180009988`

## callees

- `0x180005d58`
- `0x18000835c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800083de`
- `msvcrt!memcpy_s` at `0x1800083de`
- `KERNEL32!HeapFree` at `0x1800083ff`
- `KERNEL32!HeapFree` at `0x1800083ff`
- `KERNEL32!SetLastError` at `0x1800083c1`
- `KERNEL32!SetLastError` at `0x18000841a`
- `KERNEL32!SetLastError` at `0x1800083c1`
- `KERNEL32!SetLastError` at `0x18000841a`
- `KERNEL32!GetLastError` at `0x18000839d`
- `KERNEL32!GetLastError` at `0x18000839d`
- `KERNEL32!GetProcessHeap` at `0x1800083f1`
- `KERNEL32!GetProcessHeap` at `0x1800083f1`

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
0x18000835c  push    rbx
0x18000835e  push    rbp
0x18000835f  push    rsi
0x180008360  push    rdi
0x180008361  push    r14
0x180008363  push    r15
0x180008365  sub     rsp, 28h
0x180008369  mov     rdi, rcx
0x18000836c  mov     rbx, rdx
0x18000836f  mov     rcx, [rcx+10h]
0x180008373  mov     rax, [rdi+8]
0x180008377  sub     rax, [rdi]
0x18000837a  sub     rcx, [rdi]
0x18000837d  add     rax, rdx
0x180008380  cmp     rax, rcx
0x180008383  jb      loc_180008420
0x180008389  lea     rax, [rcx+rcx]
0x18000838d  cmp     rdx, rax
0x180008390  cmovb   rbx, rax
0x180008394  cmp     rcx, rbx
0x180008397  jnb     loc_180008420
0x18000839d  call    cs:__imp_GetLastError
0x1800083a3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1800083a7  xor     ecx, ecx; dwFlags
0x1800083a9  mov     esi, eax
0x1800083ab  lea     r14, [rbx+40h]
0x1800083af  mov     rdx, r14; dwBytes
0x1800083b2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800083b7  mov     rbx, rax
0x1800083ba  test    rax, rax
0x1800083bd  jnz     short loc_1800083CB
0x1800083bf  mov     ecx, esi; dwErrCode
0x1800083c1  call    cs:__imp_SetLastError
0x1800083c7  xor     al, al
0x1800083c9  jmp     short loc_180008422
0x1800083cb  mov     r15, [rdi+8]
0x1800083cf  mov     rdx, r14; DestinationSize
0x1800083d2  sub     r15, [rdi]
0x1800083d5  mov     rcx, rbx; Destination
0x1800083d8  mov     r8, [rdi]; Source
0x1800083db  mov     r9, r15; SourceSize
0x1800083de  call    cs:__imp_memcpy_s
0x1800083e4  mov     rbp, [rdi+18h]
0x1800083e8  mov     [rdi+18h], rbx
0x1800083ec  test    rbp, rbp
0x1800083ef  jz      short loc_180008405
0x1800083f1  call    cs:__imp_GetProcessHeap
0x1800083f7  mov     r8, rbp; lpMem
0x1800083fa  xor     edx, edx; dwFlags
0x1800083fc  mov     rcx, rax; hHeap
0x1800083ff  call    cs:__imp_HeapFree
0x180008405  lea     rax, [r15+rbx]
0x180008409  mov     [rdi], rbx
0x18000840c  mov     [rdi+8], rax
0x180008410  mov     ecx, esi; dwErrCode
0x180008412  lea     rax, [r14+rbx]
0x180008416  mov     [rdi+10h], rax
0x18000841a  call    cs:__imp_SetLastError
0x180008420  mov     al, 1
0x180008422  add     rsp, 28h
0x180008426  pop     r15
0x180008428  pop     r14
0x18000842a  pop     rdi
0x18000842b  pop     rsi
0x18000842c  pop     rbp
0x18000842d  pop     rbx
0x18000842e  retn
```
