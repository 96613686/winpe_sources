# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000f454`
- end: `0x14000f527`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bde8`
- `0x14000c5f8`
- `0x14000dd0c`
- `0x14000dedc`

## callees

- `0x14000bc90`
- `0x14000f454`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000f4d6`
- `msvcrt!memcpy_s` at `0x14000f4d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f495`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f4b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f512`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f4b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f512`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f4f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f4f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f4e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f4e9`

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
0x14000f454  push    rbx
0x14000f456  push    rbp
0x14000f457  push    rsi
0x14000f458  push    rdi
0x14000f459  push    r14
0x14000f45b  push    r15
0x14000f45d  sub     rsp, 28h
0x14000f461  mov     rdi, rcx
0x14000f464  mov     rbx, rdx
0x14000f467  mov     rcx, [rcx+10h]
0x14000f46b  mov     rax, [rdi+8]
0x14000f46f  sub     rax, [rdi]
0x14000f472  sub     rcx, [rdi]
0x14000f475  add     rax, rdx
0x14000f478  cmp     rax, rcx
0x14000f47b  jb      loc_14000F518
0x14000f481  lea     rax, [rcx+rcx]
0x14000f485  cmp     rdx, rax
0x14000f488  cmovb   rbx, rax
0x14000f48c  cmp     rcx, rbx
0x14000f48f  jnb     loc_14000F518
0x14000f495  call    cs:__imp_GetLastError
0x14000f49b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000f49f  xor     ecx, ecx; dwFlags
0x14000f4a1  mov     esi, eax
0x14000f4a3  lea     r14, [rbx+40h]
0x14000f4a7  mov     rdx, r14; dwBytes
0x14000f4aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000f4af  mov     rbx, rax
0x14000f4b2  test    rax, rax
0x14000f4b5  jnz     short loc_14000F4C3
0x14000f4b7  mov     ecx, esi; dwErrCode
0x14000f4b9  call    cs:__imp_SetLastError
0x14000f4bf  xor     al, al
0x14000f4c1  jmp     short loc_14000F51A
0x14000f4c3  mov     r15, [rdi+8]
0x14000f4c7  mov     rdx, r14; DestinationSize
0x14000f4ca  sub     r15, [rdi]
0x14000f4cd  mov     rcx, rbx; Destination
0x14000f4d0  mov     r8, [rdi]; Source
0x14000f4d3  mov     r9, r15; SourceSize
0x14000f4d6  call    cs:__imp_memcpy_s
0x14000f4dc  mov     rbp, [rdi+18h]
0x14000f4e0  mov     [rdi+18h], rbx
0x14000f4e4  test    rbp, rbp
0x14000f4e7  jz      short loc_14000F4FD
0x14000f4e9  call    cs:__imp_GetProcessHeap
0x14000f4ef  mov     r8, rbp; lpMem
0x14000f4f2  xor     edx, edx; dwFlags
0x14000f4f4  mov     rcx, rax; hHeap
0x14000f4f7  call    cs:__imp_HeapFree
0x14000f4fd  lea     rax, [r15+rbx]
0x14000f501  mov     [rdi], rbx
0x14000f504  mov     [rdi+8], rax
0x14000f508  mov     ecx, esi; dwErrCode
0x14000f50a  lea     rax, [r14+rbx]
0x14000f50e  mov     [rdi+10h], rax
0x14000f512  call    cs:__imp_SetLastError
0x14000f518  mov     al, 1
0x14000f51a  add     rsp, 28h
0x14000f51e  pop     r15
0x14000f520  pop     r14
0x14000f522  pop     rdi
0x14000f523  pop     rsi
0x14000f524  pop     rbp
0x14000f525  pop     rbx
0x14000f526  retn
```
