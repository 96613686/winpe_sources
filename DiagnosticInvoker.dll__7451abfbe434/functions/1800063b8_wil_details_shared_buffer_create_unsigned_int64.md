# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800063b8`
- end: `0x18000647b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005834`
- `0x180006490`

## callees

- `0x1800063b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006455`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006455`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000640d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006447`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000640d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006447`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000641c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000641c`

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
0x1800063b8  push    rbx
0x1800063ba  push    rbp
0x1800063bb  push    rsi
0x1800063bc  push    rdi
0x1800063bd  sub     rsp, 28h
0x1800063c1  mov     rbp, rdx
0x1800063c4  mov     rdi, rcx
0x1800063c7  test    rdx, rdx
0x1800063ca  jnz     short loc_18000640D
0x1800063cc  mov     rcx, [rcx]
0x1800063cf  test    rcx, rcx
0x1800063d2  jz      short loc_180006406
0x1800063d4  or      eax, 0FFFFFFFFh
0x1800063d7  lock xadd [rcx], eax
0x1800063db  cmp     eax, 1
0x1800063de  jnz     short loc_1800063F7
0x1800063e0  mov     rbx, [rdi]
0x1800063e3  call    cs:__imp_GetProcessHeap
0x1800063e9  mov     r8, rbx; lpMem
0x1800063ec  xor     edx, edx; dwFlags
0x1800063ee  mov     rcx, rax; hHeap
0x1800063f1  call    cs:__imp_HeapFree
0x1800063f7  mov     qword ptr [rdi], 0
0x1800063fe  mov     qword ptr [rdi+8], 0
0x180006406  mov     eax, 1
0x18000640b  jmp     short loc_180006472
0x18000640d  call    cs:__imp_GetProcessHeap
0x180006413  lea     r8, [rbp+4]; dwBytes
0x180006417  xor     edx, edx; dwFlags
0x180006419  mov     rcx, rax; hHeap
0x18000641c  call    cs:__imp_HeapAlloc
0x180006422  mov     rsi, rax
0x180006425  test    rax, rax
0x180006428  jz      short loc_180006472
0x18000642a  mov     dword ptr [rax], 0
0x180006430  mov     rcx, [rdi]
0x180006433  test    rcx, rcx
0x180006436  jz      short loc_180006463
0x180006438  or      eax, 0FFFFFFFFh
0x18000643b  lock xadd [rcx], eax
0x18000643f  cmp     eax, 1
0x180006442  jnz     short loc_18000645B
0x180006444  mov     rbx, [rdi]
0x180006447  call    cs:__imp_GetProcessHeap
0x18000644d  mov     r8, rbx; lpMem
0x180006450  xor     edx, edx; dwFlags
0x180006452  mov     rcx, rax; hHeap
0x180006455  call    cs:__imp_HeapFree
0x18000645b  mov     qword ptr [rdi+8], 0
0x180006463  mov     [rdi], rsi
0x180006466  mov     eax, 1
0x18000646b  mov     [rdi+8], rbp
0x18000646f  lock add [rsi], eax
0x180006472  add     rsp, 28h
0x180006476  pop     rdi
0x180006477  pop     rsi
0x180006478  pop     rbp
0x180006479  pop     rbx
0x18000647a  retn
```
