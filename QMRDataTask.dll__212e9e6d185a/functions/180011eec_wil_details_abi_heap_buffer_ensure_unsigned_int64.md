# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180011eec`
- end: `0x180011fbf`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c6bc`
- `0x18000c84c`
- `0x18000d068`
- `0x180010684`
- `0x180010854`

## callees

- `0x18000c118`
- `0x180011eec`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011f6e`
- `msvcrt!memcpy_s` at `0x180011f6e`
- `KERNEL32!GetLastError` at `0x180011f2d`
- `KERNEL32!GetLastError` at `0x180011f2d`
- `KERNEL32!GetProcessHeap` at `0x180011f81`
- `KERNEL32!GetProcessHeap` at `0x180011f81`
- `KERNEL32!HeapFree` at `0x180011f8f`
- `KERNEL32!HeapFree` at `0x180011f8f`
- `KERNEL32!SetLastError` at `0x180011f51`
- `KERNEL32!SetLastError` at `0x180011faa`
- `KERNEL32!SetLastError` at `0x180011f51`
- `KERNEL32!SetLastError` at `0x180011faa`

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
0x180011eec  push    rbx
0x180011eee  push    rbp
0x180011eef  push    rsi
0x180011ef0  push    rdi
0x180011ef1  push    r14
0x180011ef3  push    r15
0x180011ef5  sub     rsp, 28h
0x180011ef9  mov     rdi, rcx
0x180011efc  mov     rbx, rdx
0x180011eff  mov     rcx, [rcx+10h]
0x180011f03  mov     rax, [rdi+8]
0x180011f07  sub     rax, [rdi]
0x180011f0a  sub     rcx, [rdi]
0x180011f0d  add     rax, rdx
0x180011f10  cmp     rax, rcx
0x180011f13  jb      loc_180011FB0
0x180011f19  lea     rax, [rcx+rcx]
0x180011f1d  cmp     rdx, rax
0x180011f20  cmovb   rbx, rax
0x180011f24  cmp     rcx, rbx
0x180011f27  jnb     loc_180011FB0
0x180011f2d  call    cs:__imp_GetLastError
0x180011f33  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180011f37  xor     ecx, ecx; dwFlags
0x180011f39  mov     esi, eax
0x180011f3b  lea     r14, [rbx+40h]
0x180011f3f  mov     rdx, r14; dwBytes
0x180011f42  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180011f47  mov     rbx, rax
0x180011f4a  test    rax, rax
0x180011f4d  jnz     short loc_180011F5B
0x180011f4f  mov     ecx, esi; dwErrCode
0x180011f51  call    cs:__imp_SetLastError
0x180011f57  xor     al, al
0x180011f59  jmp     short loc_180011FB2
0x180011f5b  mov     r15, [rdi+8]
0x180011f5f  mov     rdx, r14; DestinationSize
0x180011f62  sub     r15, [rdi]
0x180011f65  mov     rcx, rbx; Destination
0x180011f68  mov     r8, [rdi]; Source
0x180011f6b  mov     r9, r15; SourceSize
0x180011f6e  call    cs:__imp_memcpy_s
0x180011f74  mov     rbp, [rdi+18h]
0x180011f78  mov     [rdi+18h], rbx
0x180011f7c  test    rbp, rbp
0x180011f7f  jz      short loc_180011F95
0x180011f81  call    cs:__imp_GetProcessHeap
0x180011f87  mov     r8, rbp; lpMem
0x180011f8a  xor     edx, edx; dwFlags
0x180011f8c  mov     rcx, rax; hHeap
0x180011f8f  call    cs:__imp_HeapFree
0x180011f95  lea     rax, [r15+rbx]
0x180011f99  mov     [rdi], rbx
0x180011f9c  mov     [rdi+8], rax
0x180011fa0  mov     ecx, esi; dwErrCode
0x180011fa2  lea     rax, [r14+rbx]
0x180011fa6  mov     [rdi+10h], rax
0x180011faa  call    cs:__imp_SetLastError
0x180011fb0  mov     al, 1
0x180011fb2  add     rsp, 28h
0x180011fb6  pop     r15
0x180011fb8  pop     r14
0x180011fba  pop     rdi
0x180011fbb  pop     rsi
0x180011fbc  pop     rbp
0x180011fbd  pop     rbx
0x180011fbe  retn
```
