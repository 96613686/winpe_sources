# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800071b4`
- end: `0x180007277`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006164`
- `0x180007590`

## callees

- `0x1800071b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007209`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007243`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007209`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007243`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007251`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007251`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007218`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007218`

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
0x1800071b4  push    rbx
0x1800071b6  push    rbp
0x1800071b7  push    rsi
0x1800071b8  push    rdi
0x1800071b9  sub     rsp, 28h
0x1800071bd  mov     rbp, rdx
0x1800071c0  mov     rdi, rcx
0x1800071c3  test    rdx, rdx
0x1800071c6  jnz     short loc_180007209
0x1800071c8  mov     rcx, [rcx]
0x1800071cb  test    rcx, rcx
0x1800071ce  jz      short loc_180007202
0x1800071d0  or      eax, 0FFFFFFFFh
0x1800071d3  lock xadd [rcx], eax
0x1800071d7  cmp     eax, 1
0x1800071da  jnz     short loc_1800071F3
0x1800071dc  mov     rbx, [rdi]
0x1800071df  call    cs:__imp_GetProcessHeap
0x1800071e5  mov     r8, rbx; lpMem
0x1800071e8  xor     edx, edx; dwFlags
0x1800071ea  mov     rcx, rax; hHeap
0x1800071ed  call    cs:__imp_HeapFree
0x1800071f3  mov     qword ptr [rdi], 0
0x1800071fa  mov     qword ptr [rdi+8], 0
0x180007202  mov     eax, 1
0x180007207  jmp     short loc_18000726E
0x180007209  call    cs:__imp_GetProcessHeap
0x18000720f  lea     r8, [rbp+4]; dwBytes
0x180007213  xor     edx, edx; dwFlags
0x180007215  mov     rcx, rax; hHeap
0x180007218  call    cs:__imp_HeapAlloc
0x18000721e  mov     rsi, rax
0x180007221  test    rax, rax
0x180007224  jz      short loc_18000726E
0x180007226  mov     dword ptr [rax], 0
0x18000722c  mov     rcx, [rdi]
0x18000722f  test    rcx, rcx
0x180007232  jz      short loc_18000725F
0x180007234  or      eax, 0FFFFFFFFh
0x180007237  lock xadd [rcx], eax
0x18000723b  cmp     eax, 1
0x18000723e  jnz     short loc_180007257
0x180007240  mov     rbx, [rdi]
0x180007243  call    cs:__imp_GetProcessHeap
0x180007249  mov     r8, rbx; lpMem
0x18000724c  xor     edx, edx; dwFlags
0x18000724e  mov     rcx, rax; hHeap
0x180007251  call    cs:__imp_HeapFree
0x180007257  mov     qword ptr [rdi+8], 0
0x18000725f  mov     [rdi], rsi
0x180007262  mov     eax, 1
0x180007267  mov     [rdi+8], rbp
0x18000726b  lock add [rsi], eax
0x18000726e  add     rsp, 28h
0x180007272  pop     rdi
0x180007273  pop     rsi
0x180007274  pop     rbp
0x180007275  pop     rbx
0x180007276  retn
```
