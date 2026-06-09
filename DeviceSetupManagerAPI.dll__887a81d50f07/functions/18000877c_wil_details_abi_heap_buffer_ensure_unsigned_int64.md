# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000877c`
- end: `0x18000884e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005d7c`
- `0x1800063b8`
- `0x180007c80`

## callees

- `0x180005cd8`
- `0x18000877c`
- `0x180008bc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008810`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008810`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000881e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000881e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800087e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008839`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800087e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008839`

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
0x18000877c  push    rbx
0x18000877e  push    rbp
0x18000877f  push    rsi
0x180008780  push    rdi
0x180008781  push    r14
0x180008783  push    r15
0x180008785  sub     rsp, 28h
0x180008789  mov     rdi, rcx
0x18000878c  mov     rbx, rdx
0x18000878f  mov     rcx, [rcx+10h]
0x180008793  mov     rax, [rdi+8]
0x180008797  sub     rax, [rdi]
0x18000879a  sub     rcx, [rdi]
0x18000879d  add     rax, rdx
0x1800087a0  cmp     rax, rcx
0x1800087a3  jb      loc_18000883F
0x1800087a9  lea     rax, [rcx+rcx]
0x1800087ad  cmp     rdx, rax
0x1800087b0  cmovb   rbx, rax
0x1800087b4  cmp     rcx, rbx
0x1800087b7  jnb     loc_18000883F
0x1800087bd  call    cs:__imp_GetLastError
0x1800087c3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1800087c7  xor     ecx, ecx; dwFlags
0x1800087c9  mov     esi, eax
0x1800087cb  lea     r14, [rbx+40h]
0x1800087cf  mov     rdx, r14; dwBytes
0x1800087d2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800087d7  mov     rbx, rax
0x1800087da  test    rax, rax
0x1800087dd  jnz     short loc_1800087EB
0x1800087df  mov     ecx, esi; dwErrCode
0x1800087e1  call    cs:__imp_SetLastError
0x1800087e7  xor     al, al
0x1800087e9  jmp     short loc_180008841
0x1800087eb  mov     r15, [rdi+8]
0x1800087ef  mov     rdx, r14; DestinationSize
0x1800087f2  sub     r15, [rdi]
0x1800087f5  mov     rcx, rbx; Destination
0x1800087f8  mov     r8, [rdi]; Source
0x1800087fb  mov     r9, r15; SourceSize
0x1800087fe  call    memcpy_s
0x180008803  mov     rbp, [rdi+18h]
0x180008807  mov     [rdi+18h], rbx
0x18000880b  test    rbp, rbp
0x18000880e  jz      short loc_180008824
0x180008810  call    cs:__imp_GetProcessHeap
0x180008816  mov     r8, rbp; lpMem
0x180008819  xor     edx, edx; dwFlags
0x18000881b  mov     rcx, rax; hHeap
0x18000881e  call    cs:__imp_HeapFree
0x180008824  lea     rax, [r15+rbx]
0x180008828  mov     [rdi], rbx
0x18000882b  mov     [rdi+8], rax
0x18000882f  mov     ecx, esi; dwErrCode
0x180008831  lea     rax, [r14+rbx]
0x180008835  mov     [rdi+10h], rax
0x180008839  call    cs:__imp_SetLastError
0x18000883f  mov     al, 1
0x180008841  add     rsp, 28h
0x180008845  pop     r15
0x180008847  pop     r14
0x180008849  pop     rdi
0x18000884a  pop     rsi
0x18000884b  pop     rbp
0x18000884c  pop     rbx
0x18000884d  retn
```
