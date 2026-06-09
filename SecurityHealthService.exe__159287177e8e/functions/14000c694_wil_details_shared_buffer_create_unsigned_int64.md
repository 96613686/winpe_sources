# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000c694`
- end: `0x14000c757`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b5a8`
- `0x14000c770`

## callees

- `0x14000c694`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c6cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c731`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c6cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c731`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c6f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c6f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c6bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c6e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c723`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c6bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c6e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c723`

## pseudocode

```c
__int64 __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rsi
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    result = (__int64)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = (volatile signed __int32 *)result;
    if ( result )
    {
      *(_DWORD *)result = 0;
      if ( *this )
      {
        if ( _InterlockedExchangeAdd(*this, 0xFFFFFFFF) == 1 )
        {
          v10 = *this;
          v11 = GetProcessHeap();
          HeapFree(v11, 0, (LPVOID)v10);
        }
        this[1] = 0;
      }
      *this = v9;
      result = 1;
      this[1] = a2;
      _InterlockedAdd(v9, 1u);
    }
  }
  else
  {
    v4 = *this;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 )
      {
        v5 = *this;
        v6 = GetProcessHeap();
        HeapFree(v6, 0, (LPVOID)v5);
      }
      *this = 0;
      this[1] = 0;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x14000c694  push    rbx
0x14000c696  push    rbp
0x14000c697  push    rsi
0x14000c698  push    rdi
0x14000c699  sub     rsp, 28h
0x14000c69d  mov     rbp, rdx
0x14000c6a0  mov     rdi, rcx
0x14000c6a3  test    rdx, rdx
0x14000c6a6  jnz     short loc_14000C6E9
0x14000c6a8  mov     rcx, [rcx]
0x14000c6ab  test    rcx, rcx
0x14000c6ae  jz      short loc_14000C6E2
0x14000c6b0  or      eax, 0FFFFFFFFh
0x14000c6b3  lock xadd [rcx], eax
0x14000c6b7  cmp     eax, 1
0x14000c6ba  jnz     short loc_14000C6D3
0x14000c6bc  mov     rbx, [rdi]
0x14000c6bf  call    cs:__imp_GetProcessHeap
0x14000c6c5  mov     r8, rbx; lpMem
0x14000c6c8  xor     edx, edx; dwFlags
0x14000c6ca  mov     rcx, rax; hHeap
0x14000c6cd  call    cs:__imp_HeapFree
0x14000c6d3  mov     qword ptr [rdi], 0
0x14000c6da  mov     qword ptr [rdi+8], 0
0x14000c6e2  mov     eax, 1
0x14000c6e7  jmp     short loc_14000C74E
0x14000c6e9  call    cs:__imp_GetProcessHeap
0x14000c6ef  lea     r8, [rbp+4]; dwBytes
0x14000c6f3  xor     edx, edx; dwFlags
0x14000c6f5  mov     rcx, rax; hHeap
0x14000c6f8  call    cs:__imp_HeapAlloc
0x14000c6fe  mov     rsi, rax
0x14000c701  test    rax, rax
0x14000c704  jz      short loc_14000C74E
0x14000c706  mov     dword ptr [rax], 0
0x14000c70c  mov     rcx, [rdi]
0x14000c70f  test    rcx, rcx
0x14000c712  jz      short loc_14000C73F
0x14000c714  or      eax, 0FFFFFFFFh
0x14000c717  lock xadd [rcx], eax
0x14000c71b  cmp     eax, 1
0x14000c71e  jnz     short loc_14000C737
0x14000c720  mov     rbx, [rdi]
0x14000c723  call    cs:__imp_GetProcessHeap
0x14000c729  mov     r8, rbx; lpMem
0x14000c72c  xor     edx, edx; dwFlags
0x14000c72e  mov     rcx, rax; hHeap
0x14000c731  call    cs:__imp_HeapFree
0x14000c737  mov     qword ptr [rdi+8], 0
0x14000c73f  mov     [rdi], rsi
0x14000c742  mov     eax, 1
0x14000c747  mov     [rdi+8], rbp
0x14000c74b  lock add [rsi], eax
0x14000c74e  add     rsp, 28h
0x14000c752  pop     rdi
0x14000c753  pop     rsi
0x14000c754  pop     rbp
0x14000c755  pop     rbx
0x14000c756  retn
```
