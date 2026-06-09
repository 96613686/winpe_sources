# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000d308`
- end: `0x14000d3cb`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c744`
- `0x14000d4e0`

## callees

- `0x14000d308`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d341`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d3a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d341`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d3a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d36c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d36c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d333`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d35d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d397`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d333`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d35d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d397`

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
0x14000d308  push    rbx
0x14000d30a  push    rbp
0x14000d30b  push    rsi
0x14000d30c  push    rdi
0x14000d30d  sub     rsp, 28h
0x14000d311  mov     rbp, rdx
0x14000d314  mov     rdi, rcx
0x14000d317  test    rdx, rdx
0x14000d31a  jnz     short loc_14000D35D
0x14000d31c  mov     rcx, [rcx]
0x14000d31f  test    rcx, rcx
0x14000d322  jz      short loc_14000D356
0x14000d324  or      eax, 0FFFFFFFFh
0x14000d327  lock xadd [rcx], eax
0x14000d32b  cmp     eax, 1
0x14000d32e  jnz     short loc_14000D347
0x14000d330  mov     rbx, [rdi]
0x14000d333  call    cs:__imp_GetProcessHeap
0x14000d339  mov     r8, rbx; lpMem
0x14000d33c  xor     edx, edx; dwFlags
0x14000d33e  mov     rcx, rax; hHeap
0x14000d341  call    cs:__imp_HeapFree
0x14000d347  mov     qword ptr [rdi], 0
0x14000d34e  mov     qword ptr [rdi+8], 0
0x14000d356  mov     eax, 1
0x14000d35b  jmp     short loc_14000D3C2
0x14000d35d  call    cs:__imp_GetProcessHeap
0x14000d363  lea     r8, [rbp+4]; dwBytes
0x14000d367  xor     edx, edx; dwFlags
0x14000d369  mov     rcx, rax; hHeap
0x14000d36c  call    cs:__imp_HeapAlloc
0x14000d372  mov     rsi, rax
0x14000d375  test    rax, rax
0x14000d378  jz      short loc_14000D3C2
0x14000d37a  mov     dword ptr [rax], 0
0x14000d380  mov     rcx, [rdi]
0x14000d383  test    rcx, rcx
0x14000d386  jz      short loc_14000D3B3
0x14000d388  or      eax, 0FFFFFFFFh
0x14000d38b  lock xadd [rcx], eax
0x14000d38f  cmp     eax, 1
0x14000d392  jnz     short loc_14000D3AB
0x14000d394  mov     rbx, [rdi]
0x14000d397  call    cs:__imp_GetProcessHeap
0x14000d39d  mov     r8, rbx; lpMem
0x14000d3a0  xor     edx, edx; dwFlags
0x14000d3a2  mov     rcx, rax; hHeap
0x14000d3a5  call    cs:__imp_HeapFree
0x14000d3ab  mov     qword ptr [rdi+8], 0
0x14000d3b3  mov     [rdi], rsi
0x14000d3b6  mov     eax, 1
0x14000d3bb  mov     [rdi+8], rbp
0x14000d3bf  lock add [rsi], eax
0x14000d3c2  add     rsp, 28h
0x14000d3c6  pop     rdi
0x14000d3c7  pop     rsi
0x14000d3c8  pop     rbp
0x14000d3c9  pop     rbx
0x14000d3ca  retn
```
