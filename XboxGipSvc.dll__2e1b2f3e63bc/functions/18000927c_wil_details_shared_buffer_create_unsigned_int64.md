# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000927c`
- end: `0x18000933f`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008780`
- `0x180009350`

## callees

- `0x18000927c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800092e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800092e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800092b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009319`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800092b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009319`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000930b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000930b`

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
0x18000927c  push    rbx
0x18000927e  push    rbp
0x18000927f  push    rsi
0x180009280  push    rdi
0x180009281  sub     rsp, 28h
0x180009285  mov     rbp, rdx
0x180009288  mov     rdi, rcx
0x18000928b  test    rdx, rdx
0x18000928e  jnz     short loc_1800092D1
0x180009290  mov     rcx, [rcx]
0x180009293  test    rcx, rcx
0x180009296  jz      short loc_1800092CA
0x180009298  or      eax, 0FFFFFFFFh
0x18000929b  lock xadd [rcx], eax
0x18000929f  cmp     eax, 1
0x1800092a2  jnz     short loc_1800092BB
0x1800092a4  mov     rbx, [rdi]
0x1800092a7  call    cs:__imp_GetProcessHeap
0x1800092ad  mov     r8, rbx; lpMem
0x1800092b0  xor     edx, edx; dwFlags
0x1800092b2  mov     rcx, rax; hHeap
0x1800092b5  call    cs:__imp_HeapFree
0x1800092bb  mov     qword ptr [rdi], 0
0x1800092c2  mov     qword ptr [rdi+8], 0
0x1800092ca  mov     eax, 1
0x1800092cf  jmp     short loc_180009336
0x1800092d1  call    cs:__imp_GetProcessHeap
0x1800092d7  lea     r8, [rbp+4]; dwBytes
0x1800092db  xor     edx, edx; dwFlags
0x1800092dd  mov     rcx, rax; hHeap
0x1800092e0  call    cs:__imp_HeapAlloc
0x1800092e6  mov     rsi, rax
0x1800092e9  test    rax, rax
0x1800092ec  jz      short loc_180009336
0x1800092ee  mov     dword ptr [rax], 0
0x1800092f4  mov     rcx, [rdi]
0x1800092f7  test    rcx, rcx
0x1800092fa  jz      short loc_180009327
0x1800092fc  or      eax, 0FFFFFFFFh
0x1800092ff  lock xadd [rcx], eax
0x180009303  cmp     eax, 1
0x180009306  jnz     short loc_18000931F
0x180009308  mov     rbx, [rdi]
0x18000930b  call    cs:__imp_GetProcessHeap
0x180009311  mov     r8, rbx; lpMem
0x180009314  xor     edx, edx; dwFlags
0x180009316  mov     rcx, rax; hHeap
0x180009319  call    cs:__imp_HeapFree
0x18000931f  mov     qword ptr [rdi+8], 0
0x180009327  mov     [rdi], rsi
0x18000932a  mov     eax, 1
0x18000932f  mov     [rdi+8], rbp
0x180009333  lock add [rsi], eax
0x180009336  add     rsp, 28h
0x18000933a  pop     rdi
0x18000933b  pop     rsi
0x18000933c  pop     rbp
0x18000933d  pop     rbx
0x18000933e  retn
```
