# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x140006524`
- end: `0x1400065f7`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ad48`
- `0x14000b350`
- `0x14000c44c`

## callees

- `0x140005cd0`
- `0x140006524`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006565`
- `KERNEL32!GetLastError` at `0x140006565`
- `KERNEL32!HeapFree` at `0x1400065c7`
- `KERNEL32!HeapFree` at `0x1400065c7`
- `KERNEL32!GetProcessHeap` at `0x1400065b9`
- `KERNEL32!GetProcessHeap` at `0x1400065b9`
- `KERNEL32!SetLastError` at `0x140006589`
- `KERNEL32!SetLastError` at `0x1400065e2`
- `KERNEL32!SetLastError` at `0x140006589`
- `KERNEL32!SetLastError` at `0x1400065e2`
- `msvcrt!memcpy_s` at `0x1400065a6`
- `msvcrt!memcpy_s` at `0x1400065a6`

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
0x140006524  push    rbx
0x140006526  push    rbp
0x140006527  push    rsi
0x140006528  push    rdi
0x140006529  push    r14
0x14000652b  push    r15
0x14000652d  sub     rsp, 28h
0x140006531  mov     rdi, rcx
0x140006534  mov     rbx, rdx
0x140006537  mov     rcx, [rcx+10h]
0x14000653b  mov     rax, [rdi+8]
0x14000653f  sub     rax, [rdi]
0x140006542  sub     rcx, [rdi]
0x140006545  add     rax, rdx
0x140006548  cmp     rax, rcx
0x14000654b  jb      loc_1400065E8
0x140006551  lea     rax, [rcx+rcx]
0x140006555  cmp     rdx, rax
0x140006558  cmovb   rbx, rax
0x14000655c  cmp     rcx, rbx
0x14000655f  jnb     loc_1400065E8
0x140006565  call    cs:__imp_GetLastError
0x14000656b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000656f  xor     ecx, ecx; dwFlags
0x140006571  mov     esi, eax
0x140006573  lea     r14, [rbx+40h]
0x140006577  mov     rdx, r14; dwBytes
0x14000657a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000657f  mov     rbx, rax
0x140006582  test    rax, rax
0x140006585  jnz     short loc_140006593
0x140006587  mov     ecx, esi; dwErrCode
0x140006589  call    cs:__imp_SetLastError
0x14000658f  xor     al, al
0x140006591  jmp     short loc_1400065EA
0x140006593  mov     r15, [rdi+8]
0x140006597  mov     rdx, r14; DestinationSize
0x14000659a  sub     r15, [rdi]
0x14000659d  mov     rcx, rbx; Destination
0x1400065a0  mov     r8, [rdi]; Source
0x1400065a3  mov     r9, r15; SourceSize
0x1400065a6  call    cs:__imp_memcpy_s
0x1400065ac  mov     rbp, [rdi+18h]
0x1400065b0  mov     [rdi+18h], rbx
0x1400065b4  test    rbp, rbp
0x1400065b7  jz      short loc_1400065CD
0x1400065b9  call    cs:__imp_GetProcessHeap
0x1400065bf  mov     r8, rbp; lpMem
0x1400065c2  xor     edx, edx; dwFlags
0x1400065c4  mov     rcx, rax; hHeap
0x1400065c7  call    cs:__imp_HeapFree
0x1400065cd  lea     rax, [r15+rbx]
0x1400065d1  mov     [rdi], rbx
0x1400065d4  mov     [rdi+8], rax
0x1400065d8  mov     ecx, esi; dwErrCode
0x1400065da  lea     rax, [r14+rbx]
0x1400065de  mov     [rdi+10h], rax
0x1400065e2  call    cs:__imp_SetLastError
0x1400065e8  mov     al, 1
0x1400065ea  add     rsp, 28h
0x1400065ee  pop     r15
0x1400065f0  pop     r14
0x1400065f2  pop     rdi
0x1400065f3  pop     rsi
0x1400065f4  pop     rbp
0x1400065f5  pop     rbx
0x1400065f6  retn
```
