# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000a130`
- end: `0x18000a1f3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009210`
- `0x18000a200`

## callees

- `0x18000a130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a194`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a194`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a15b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a185`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a15b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a185`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a169`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a169`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1cd`

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
0x18000a130  push    rbx
0x18000a132  push    rbp
0x18000a133  push    rsi
0x18000a134  push    rdi
0x18000a135  sub     rsp, 28h
0x18000a139  mov     rbp, rdx
0x18000a13c  mov     rdi, rcx
0x18000a13f  test    rdx, rdx
0x18000a142  jnz     short loc_18000A185
0x18000a144  mov     rcx, [rcx]
0x18000a147  test    rcx, rcx
0x18000a14a  jz      short loc_18000A17E
0x18000a14c  or      eax, 0FFFFFFFFh
0x18000a14f  lock xadd [rcx], eax
0x18000a153  cmp     eax, 1
0x18000a156  jnz     short loc_18000A16F
0x18000a158  mov     rbx, [rdi]
0x18000a15b  call    cs:__imp_GetProcessHeap
0x18000a161  mov     r8, rbx; lpMem
0x18000a164  xor     edx, edx; dwFlags
0x18000a166  mov     rcx, rax; hHeap
0x18000a169  call    cs:__imp_HeapFree
0x18000a16f  mov     qword ptr [rdi], 0
0x18000a176  mov     qword ptr [rdi+8], 0
0x18000a17e  mov     eax, 1
0x18000a183  jmp     short loc_18000A1EA
0x18000a185  call    cs:__imp_GetProcessHeap
0x18000a18b  lea     r8, [rbp+4]; dwBytes
0x18000a18f  xor     edx, edx; dwFlags
0x18000a191  mov     rcx, rax; hHeap
0x18000a194  call    cs:__imp_HeapAlloc
0x18000a19a  mov     rsi, rax
0x18000a19d  test    rax, rax
0x18000a1a0  jz      short loc_18000A1EA
0x18000a1a2  mov     dword ptr [rax], 0
0x18000a1a8  mov     rcx, [rdi]
0x18000a1ab  test    rcx, rcx
0x18000a1ae  jz      short loc_18000A1DB
0x18000a1b0  or      eax, 0FFFFFFFFh
0x18000a1b3  lock xadd [rcx], eax
0x18000a1b7  cmp     eax, 1
0x18000a1ba  jnz     short loc_18000A1D3
0x18000a1bc  mov     rbx, [rdi]
0x18000a1bf  call    cs:__imp_GetProcessHeap
0x18000a1c5  mov     r8, rbx; lpMem
0x18000a1c8  xor     edx, edx; dwFlags
0x18000a1ca  mov     rcx, rax; hHeap
0x18000a1cd  call    cs:__imp_HeapFree
0x18000a1d3  mov     qword ptr [rdi+8], 0
0x18000a1db  mov     [rdi], rsi
0x18000a1de  mov     eax, 1
0x18000a1e3  mov     [rdi+8], rbp
0x18000a1e7  lock add [rsi], eax
0x18000a1ea  add     rsp, 28h
0x18000a1ee  pop     rdi
0x18000a1ef  pop     rsi
0x18000a1f0  pop     rbp
0x18000a1f1  pop     rbx
0x18000a1f2  retn
```
