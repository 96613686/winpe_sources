# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180015cac`
- end: `0x180015d81`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `213`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180013438`
- `0x180013a58`
- `0x180014fa0`
- `0x180015170`

## callees

- `0x18001315c`
- `0x180015cac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015d2f`
- `msvcrt!memcpy_s` at `0x180015d2f`
- `KERNEL32!HeapFree` at `0x180015d50`
- `KERNEL32!HeapFree` at `0x180015d50`
- `KERNEL32!GetProcessHeap` at `0x180015d42`
- `KERNEL32!GetProcessHeap` at `0x180015d42`
- `KERNEL32!GetLastError` at `0x180015ced`
- `KERNEL32!GetLastError` at `0x180015ced`
- `KERNEL32!SetLastError` at `0x180015d11`
- `KERNEL32!SetLastError` at `0x180015d6b`
- `KERNEL32!SetLastError` at `0x180015d11`
- `KERNEL32!SetLastError` at `0x180015d6b`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r8
  char *v8; // rax
  char *v9; // rbx
  rsize_t v11; // r15
  void *v12; // rbp
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
0x180015cac  push    rbx
0x180015cae  push    rbp
0x180015caf  push    rsi
0x180015cb0  push    rdi
0x180015cb1  push    r14
0x180015cb3  push    r15
0x180015cb5  sub     rsp, 28h
0x180015cb9  mov     rbx, rdx
0x180015cbc  mov     rdi, rcx
0x180015cbf  mov     rcx, [rcx+10h]
0x180015cc3  sub     rcx, [rdi]
0x180015cc6  mov     rax, [rdi+8]
0x180015cca  sub     rax, [rdi]
0x180015ccd  add     rax, rdx
0x180015cd0  cmp     rax, rcx
0x180015cd3  jb      loc_180015D72
0x180015cd9  lea     rax, [rcx+rcx]
0x180015cdd  cmp     rdx, rax
0x180015ce0  cmovb   rbx, rax
0x180015ce4  cmp     rcx, rbx
0x180015ce7  jnb     loc_180015D72
0x180015ced  call    cs:__imp_GetLastError
0x180015cf3  mov     esi, eax
0x180015cf5  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180015cf9  lea     r14, [rbx+40h]
0x180015cfd  mov     rdx, r14; dwBytes
0x180015d00  xor     ecx, ecx; dwFlags
0x180015d02  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015d07  mov     rbx, rax
0x180015d0a  test    rax, rax
0x180015d0d  jnz     short loc_180015D1C
0x180015d0f  mov     ecx, esi; dwErrCode
0x180015d11  call    cs:__imp_SetLastError
0x180015d17  nop
0x180015d18  xor     al, al
0x180015d1a  jmp     short loc_180015D74
0x180015d1c  mov     r15, [rdi+8]
0x180015d20  sub     r15, [rdi]
0x180015d23  mov     r9, r15; SourceSize
0x180015d26  mov     r8, [rdi]; Source
0x180015d29  mov     rdx, r14; DestinationSize
0x180015d2c  mov     rcx, rbx; Destination
0x180015d2f  call    cs:__imp_memcpy_s
0x180015d35  mov     rbp, [rdi+18h]
0x180015d39  mov     [rdi+18h], rbx
0x180015d3d  test    rbp, rbp
0x180015d40  jz      short loc_180015D56
0x180015d42  call    cs:__imp_GetProcessHeap
0x180015d48  mov     rcx, rax; hHeap
0x180015d4b  mov     r8, rbp; lpMem
0x180015d4e  xor     edx, edx; dwFlags
0x180015d50  call    cs:__imp_HeapFree
0x180015d56  mov     [rdi], rbx
0x180015d59  lea     rax, [r15+rbx]
0x180015d5d  mov     [rdi+8], rax
0x180015d61  lea     rax, [r14+rbx]
0x180015d65  mov     [rdi+10h], rax
0x180015d69  mov     ecx, esi; dwErrCode
0x180015d6b  call    cs:__imp_SetLastError
0x180015d71  nop
0x180015d72  mov     al, 1
0x180015d74  add     rsp, 28h
0x180015d78  pop     r15
0x180015d7a  pop     r14
0x180015d7c  pop     rdi
0x180015d7d  pop     rsi
0x180015d7e  pop     rbp
0x180015d7f  pop     rbx
0x180015d80  retn
```
