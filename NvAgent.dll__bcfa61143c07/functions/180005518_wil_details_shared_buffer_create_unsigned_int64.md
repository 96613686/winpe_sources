# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180005518`
- end: `0x1800055db`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004980`
- `0x1800055f0`

## callees

- `0x180005518`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005543`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000556d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005543`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000556d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000557c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000557c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055b5`

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
0x180005518  push    rbx
0x18000551a  push    rbp
0x18000551b  push    rsi
0x18000551c  push    rdi
0x18000551d  sub     rsp, 28h
0x180005521  mov     rbp, rdx
0x180005524  mov     rdi, rcx
0x180005527  test    rdx, rdx
0x18000552a  jnz     short loc_18000556D
0x18000552c  mov     rcx, [rcx]
0x18000552f  test    rcx, rcx
0x180005532  jz      short loc_180005566
0x180005534  or      eax, 0FFFFFFFFh
0x180005537  lock xadd [rcx], eax
0x18000553b  cmp     eax, 1
0x18000553e  jnz     short loc_180005557
0x180005540  mov     rbx, [rdi]
0x180005543  call    cs:__imp_GetProcessHeap
0x180005549  mov     r8, rbx; lpMem
0x18000554c  xor     edx, edx; dwFlags
0x18000554e  mov     rcx, rax; hHeap
0x180005551  call    cs:__imp_HeapFree
0x180005557  mov     qword ptr [rdi], 0
0x18000555e  mov     qword ptr [rdi+8], 0
0x180005566  mov     eax, 1
0x18000556b  jmp     short loc_1800055D2
0x18000556d  call    cs:__imp_GetProcessHeap
0x180005573  lea     r8, [rbp+4]; dwBytes
0x180005577  xor     edx, edx; dwFlags
0x180005579  mov     rcx, rax; hHeap
0x18000557c  call    cs:__imp_HeapAlloc
0x180005582  mov     rsi, rax
0x180005585  test    rax, rax
0x180005588  jz      short loc_1800055D2
0x18000558a  mov     dword ptr [rax], 0
0x180005590  mov     rcx, [rdi]
0x180005593  test    rcx, rcx
0x180005596  jz      short loc_1800055C3
0x180005598  or      eax, 0FFFFFFFFh
0x18000559b  lock xadd [rcx], eax
0x18000559f  cmp     eax, 1
0x1800055a2  jnz     short loc_1800055BB
0x1800055a4  mov     rbx, [rdi]
0x1800055a7  call    cs:__imp_GetProcessHeap
0x1800055ad  mov     r8, rbx; lpMem
0x1800055b0  xor     edx, edx; dwFlags
0x1800055b2  mov     rcx, rax; hHeap
0x1800055b5  call    cs:__imp_HeapFree
0x1800055bb  mov     qword ptr [rdi+8], 0
0x1800055c3  mov     [rdi], rsi
0x1800055c6  mov     eax, 1
0x1800055cb  mov     [rdi+8], rbp
0x1800055cf  lock add [rsi], eax
0x1800055d2  add     rsp, 28h
0x1800055d6  pop     rdi
0x1800055d7  pop     rsi
0x1800055d8  pop     rbp
0x1800055d9  pop     rbx
0x1800055da  retn
```
