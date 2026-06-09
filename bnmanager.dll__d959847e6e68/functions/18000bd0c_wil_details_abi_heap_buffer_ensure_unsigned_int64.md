# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000bd0c`
- end: `0x18000bdde`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000903c`
- `0x180009678`
- `0x18000b1c8`

## callees

- `0x180008e98`
- `0x18000bd0c`
- `0x18000c398`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bdae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bdae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bda0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdc9`

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
0x18000bd0c  push    rbx
0x18000bd0e  push    rbp
0x18000bd0f  push    rsi
0x18000bd10  push    rdi
0x18000bd11  push    r14
0x18000bd13  push    r15
0x18000bd15  sub     rsp, 28h
0x18000bd19  mov     rdi, rcx
0x18000bd1c  mov     rbx, rdx
0x18000bd1f  mov     rcx, [rcx+10h]
0x18000bd23  mov     rax, [rdi+8]
0x18000bd27  sub     rax, [rdi]
0x18000bd2a  sub     rcx, [rdi]
0x18000bd2d  add     rax, rdx
0x18000bd30  cmp     rax, rcx
0x18000bd33  jb      loc_18000BDCF
0x18000bd39  lea     rax, [rcx+rcx]
0x18000bd3d  cmp     rdx, rax
0x18000bd40  cmovb   rbx, rax
0x18000bd44  cmp     rcx, rbx
0x18000bd47  jnb     loc_18000BDCF
0x18000bd4d  call    cs:__imp_GetLastError
0x18000bd53  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000bd57  xor     ecx, ecx; dwFlags
0x18000bd59  mov     esi, eax
0x18000bd5b  lea     r14, [rbx+40h]
0x18000bd5f  mov     rdx, r14; dwBytes
0x18000bd62  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bd67  mov     rbx, rax
0x18000bd6a  test    rax, rax
0x18000bd6d  jnz     short loc_18000BD7B
0x18000bd6f  mov     ecx, esi; dwErrCode
0x18000bd71  call    cs:__imp_SetLastError
0x18000bd77  xor     al, al
0x18000bd79  jmp     short loc_18000BDD1
0x18000bd7b  mov     r15, [rdi+8]
0x18000bd7f  mov     rdx, r14; DestinationSize
0x18000bd82  sub     r15, [rdi]
0x18000bd85  mov     rcx, rbx; Destination
0x18000bd88  mov     r8, [rdi]; Source
0x18000bd8b  mov     r9, r15; SourceSize
0x18000bd8e  call    memcpy_s
0x18000bd93  mov     rbp, [rdi+18h]
0x18000bd97  mov     [rdi+18h], rbx
0x18000bd9b  test    rbp, rbp
0x18000bd9e  jz      short loc_18000BDB4
0x18000bda0  call    cs:__imp_GetProcessHeap
0x18000bda6  mov     r8, rbp; lpMem
0x18000bda9  xor     edx, edx; dwFlags
0x18000bdab  mov     rcx, rax; hHeap
0x18000bdae  call    cs:__imp_HeapFree
0x18000bdb4  lea     rax, [r15+rbx]
0x18000bdb8  mov     [rdi], rbx
0x18000bdbb  mov     [rdi+8], rax
0x18000bdbf  mov     ecx, esi; dwErrCode
0x18000bdc1  lea     rax, [r14+rbx]
0x18000bdc5  mov     [rdi+10h], rax
0x18000bdc9  call    cs:__imp_SetLastError
0x18000bdcf  mov     al, 1
0x18000bdd1  add     rsp, 28h
0x18000bdd5  pop     r15
0x18000bdd7  pop     r14
0x18000bdd9  pop     rdi
0x18000bdda  pop     rsi
0x18000bddb  pop     rbp
0x18000bddc  pop     rbx
0x18000bddd  retn
```
