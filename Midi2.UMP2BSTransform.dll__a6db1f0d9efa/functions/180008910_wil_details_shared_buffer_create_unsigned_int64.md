# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180008910`
- end: `0x1800089d3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800079f0`
- `0x1800089e0`

## callees

- `0x180008910`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008974`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000893b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008965`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000899f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000893b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008965`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000899f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008949`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008949`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089ad`

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
0x180008910  push    rbx
0x180008912  push    rbp
0x180008913  push    rsi
0x180008914  push    rdi
0x180008915  sub     rsp, 28h
0x180008919  mov     rbp, rdx
0x18000891c  mov     rdi, rcx
0x18000891f  test    rdx, rdx
0x180008922  jnz     short loc_180008965
0x180008924  mov     rcx, [rcx]
0x180008927  test    rcx, rcx
0x18000892a  jz      short loc_18000895E
0x18000892c  or      eax, 0FFFFFFFFh
0x18000892f  lock xadd [rcx], eax
0x180008933  cmp     eax, 1
0x180008936  jnz     short loc_18000894F
0x180008938  mov     rbx, [rdi]
0x18000893b  call    cs:__imp_GetProcessHeap
0x180008941  mov     r8, rbx; lpMem
0x180008944  xor     edx, edx; dwFlags
0x180008946  mov     rcx, rax; hHeap
0x180008949  call    cs:__imp_HeapFree
0x18000894f  mov     qword ptr [rdi], 0
0x180008956  mov     qword ptr [rdi+8], 0
0x18000895e  mov     eax, 1
0x180008963  jmp     short loc_1800089CA
0x180008965  call    cs:__imp_GetProcessHeap
0x18000896b  lea     r8, [rbp+4]; dwBytes
0x18000896f  xor     edx, edx; dwFlags
0x180008971  mov     rcx, rax; hHeap
0x180008974  call    cs:__imp_HeapAlloc
0x18000897a  mov     rsi, rax
0x18000897d  test    rax, rax
0x180008980  jz      short loc_1800089CA
0x180008982  mov     dword ptr [rax], 0
0x180008988  mov     rcx, [rdi]
0x18000898b  test    rcx, rcx
0x18000898e  jz      short loc_1800089BB
0x180008990  or      eax, 0FFFFFFFFh
0x180008993  lock xadd [rcx], eax
0x180008997  cmp     eax, 1
0x18000899a  jnz     short loc_1800089B3
0x18000899c  mov     rbx, [rdi]
0x18000899f  call    cs:__imp_GetProcessHeap
0x1800089a5  mov     r8, rbx; lpMem
0x1800089a8  xor     edx, edx; dwFlags
0x1800089aa  mov     rcx, rax; hHeap
0x1800089ad  call    cs:__imp_HeapFree
0x1800089b3  mov     qword ptr [rdi+8], 0
0x1800089bb  mov     [rdi], rsi
0x1800089be  mov     eax, 1
0x1800089c3  mov     [rdi+8], rbp
0x1800089c7  lock add [rsi], eax
0x1800089ca  add     rsp, 28h
0x1800089ce  pop     rdi
0x1800089cf  pop     rsi
0x1800089d0  pop     rbp
0x1800089d1  pop     rbx
0x1800089d2  retn
```
