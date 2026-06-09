# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140006568`
- end: `0x14000662b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005610`
- `0x140006820`

## callees

- `0x140006568`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400065cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400065cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006593`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400065bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400065f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006593`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400065bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400065f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400065a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006605`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400065a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006605`

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
0x140006568  push    rbx
0x14000656a  push    rbp
0x14000656b  push    rsi
0x14000656c  push    rdi
0x14000656d  sub     rsp, 28h
0x140006571  mov     rbp, rdx
0x140006574  mov     rdi, rcx
0x140006577  test    rdx, rdx
0x14000657a  jnz     short loc_1400065BD
0x14000657c  mov     rcx, [rcx]
0x14000657f  test    rcx, rcx
0x140006582  jz      short loc_1400065B6
0x140006584  or      eax, 0FFFFFFFFh
0x140006587  lock xadd [rcx], eax
0x14000658b  cmp     eax, 1
0x14000658e  jnz     short loc_1400065A7
0x140006590  mov     rbx, [rdi]
0x140006593  call    cs:__imp_GetProcessHeap
0x140006599  mov     r8, rbx; lpMem
0x14000659c  xor     edx, edx; dwFlags
0x14000659e  mov     rcx, rax; hHeap
0x1400065a1  call    cs:__imp_HeapFree
0x1400065a7  mov     qword ptr [rdi], 0
0x1400065ae  mov     qword ptr [rdi+8], 0
0x1400065b6  mov     eax, 1
0x1400065bb  jmp     short loc_140006622
0x1400065bd  call    cs:__imp_GetProcessHeap
0x1400065c3  lea     r8, [rbp+4]; dwBytes
0x1400065c7  xor     edx, edx; dwFlags
0x1400065c9  mov     rcx, rax; hHeap
0x1400065cc  call    cs:__imp_HeapAlloc
0x1400065d2  mov     rsi, rax
0x1400065d5  test    rax, rax
0x1400065d8  jz      short loc_140006622
0x1400065da  mov     dword ptr [rax], 0
0x1400065e0  mov     rcx, [rdi]
0x1400065e3  test    rcx, rcx
0x1400065e6  jz      short loc_140006613
0x1400065e8  or      eax, 0FFFFFFFFh
0x1400065eb  lock xadd [rcx], eax
0x1400065ef  cmp     eax, 1
0x1400065f2  jnz     short loc_14000660B
0x1400065f4  mov     rbx, [rdi]
0x1400065f7  call    cs:__imp_GetProcessHeap
0x1400065fd  mov     r8, rbx; lpMem
0x140006600  xor     edx, edx; dwFlags
0x140006602  mov     rcx, rax; hHeap
0x140006605  call    cs:__imp_HeapFree
0x14000660b  mov     qword ptr [rdi+8], 0
0x140006613  mov     [rdi], rsi
0x140006616  mov     eax, 1
0x14000661b  mov     [rdi+8], rbp
0x14000661f  lock add [rsi], eax
0x140006622  add     rsp, 28h
0x140006626  pop     rdi
0x140006627  pop     rsi
0x140006628  pop     rbp
0x140006629  pop     rbx
0x14000662a  retn
```
