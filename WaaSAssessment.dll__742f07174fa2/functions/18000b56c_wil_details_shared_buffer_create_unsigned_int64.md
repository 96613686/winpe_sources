# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000b56c`
- end: `0x18000b62f`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aed4`
- `0x18000b810`

## callees

- `0x18000b56c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b597`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b597`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b609`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b609`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b5d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b5d0`

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
0x18000b56c  push    rbx
0x18000b56e  push    rbp
0x18000b56f  push    rsi
0x18000b570  push    rdi
0x18000b571  sub     rsp, 28h
0x18000b575  mov     rbp, rdx
0x18000b578  mov     rdi, rcx
0x18000b57b  test    rdx, rdx
0x18000b57e  jnz     short loc_18000B5C1
0x18000b580  mov     rcx, [rcx]
0x18000b583  test    rcx, rcx
0x18000b586  jz      short loc_18000B5BA
0x18000b588  or      eax, 0FFFFFFFFh
0x18000b58b  lock xadd [rcx], eax
0x18000b58f  cmp     eax, 1
0x18000b592  jnz     short loc_18000B5AB
0x18000b594  mov     rbx, [rdi]
0x18000b597  call    cs:__imp_GetProcessHeap
0x18000b59d  mov     r8, rbx; lpMem
0x18000b5a0  xor     edx, edx; dwFlags
0x18000b5a2  mov     rcx, rax; hHeap
0x18000b5a5  call    cs:__imp_HeapFree
0x18000b5ab  mov     qword ptr [rdi], 0
0x18000b5b2  mov     qword ptr [rdi+8], 0
0x18000b5ba  mov     eax, 1
0x18000b5bf  jmp     short loc_18000B626
0x18000b5c1  call    cs:__imp_GetProcessHeap
0x18000b5c7  lea     r8, [rbp+4]; dwBytes
0x18000b5cb  xor     edx, edx; dwFlags
0x18000b5cd  mov     rcx, rax; hHeap
0x18000b5d0  call    cs:__imp_HeapAlloc
0x18000b5d6  mov     rsi, rax
0x18000b5d9  test    rax, rax
0x18000b5dc  jz      short loc_18000B626
0x18000b5de  mov     dword ptr [rax], 0
0x18000b5e4  mov     rcx, [rdi]
0x18000b5e7  test    rcx, rcx
0x18000b5ea  jz      short loc_18000B617
0x18000b5ec  or      eax, 0FFFFFFFFh
0x18000b5ef  lock xadd [rcx], eax
0x18000b5f3  cmp     eax, 1
0x18000b5f6  jnz     short loc_18000B60F
0x18000b5f8  mov     rbx, [rdi]
0x18000b5fb  call    cs:__imp_GetProcessHeap
0x18000b601  mov     r8, rbx; lpMem
0x18000b604  xor     edx, edx; dwFlags
0x18000b606  mov     rcx, rax; hHeap
0x18000b609  call    cs:__imp_HeapFree
0x18000b60f  mov     qword ptr [rdi+8], 0
0x18000b617  mov     [rdi], rsi
0x18000b61a  mov     eax, 1
0x18000b61f  mov     [rdi+8], rbp
0x18000b623  lock add [rsi], eax
0x18000b626  add     rsp, 28h
0x18000b62a  pop     rdi
0x18000b62b  pop     rsi
0x18000b62c  pop     rbp
0x18000b62d  pop     rbx
0x18000b62e  retn
```
