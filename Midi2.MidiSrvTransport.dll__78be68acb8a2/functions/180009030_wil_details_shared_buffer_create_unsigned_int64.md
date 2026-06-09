# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180009030`
- end: `0x1800090f3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800080d0`
- `0x180009100`

## callees

- `0x180009030`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009094`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009094`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000905b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000905b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009069`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009069`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090cd`

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
0x180009030  push    rbx
0x180009032  push    rbp
0x180009033  push    rsi
0x180009034  push    rdi
0x180009035  sub     rsp, 28h
0x180009039  mov     rbp, rdx
0x18000903c  mov     rdi, rcx
0x18000903f  test    rdx, rdx
0x180009042  jnz     short loc_180009085
0x180009044  mov     rcx, [rcx]
0x180009047  test    rcx, rcx
0x18000904a  jz      short loc_18000907E
0x18000904c  or      eax, 0FFFFFFFFh
0x18000904f  lock xadd [rcx], eax
0x180009053  cmp     eax, 1
0x180009056  jnz     short loc_18000906F
0x180009058  mov     rbx, [rdi]
0x18000905b  call    cs:__imp_GetProcessHeap
0x180009061  mov     r8, rbx; lpMem
0x180009064  xor     edx, edx; dwFlags
0x180009066  mov     rcx, rax; hHeap
0x180009069  call    cs:__imp_HeapFree
0x18000906f  mov     qword ptr [rdi], 0
0x180009076  mov     qword ptr [rdi+8], 0
0x18000907e  mov     eax, 1
0x180009083  jmp     short loc_1800090EA
0x180009085  call    cs:__imp_GetProcessHeap
0x18000908b  lea     r8, [rbp+4]; dwBytes
0x18000908f  xor     edx, edx; dwFlags
0x180009091  mov     rcx, rax; hHeap
0x180009094  call    cs:__imp_HeapAlloc
0x18000909a  mov     rsi, rax
0x18000909d  test    rax, rax
0x1800090a0  jz      short loc_1800090EA
0x1800090a2  mov     dword ptr [rax], 0
0x1800090a8  mov     rcx, [rdi]
0x1800090ab  test    rcx, rcx
0x1800090ae  jz      short loc_1800090DB
0x1800090b0  or      eax, 0FFFFFFFFh
0x1800090b3  lock xadd [rcx], eax
0x1800090b7  cmp     eax, 1
0x1800090ba  jnz     short loc_1800090D3
0x1800090bc  mov     rbx, [rdi]
0x1800090bf  call    cs:__imp_GetProcessHeap
0x1800090c5  mov     r8, rbx; lpMem
0x1800090c8  xor     edx, edx; dwFlags
0x1800090ca  mov     rcx, rax; hHeap
0x1800090cd  call    cs:__imp_HeapFree
0x1800090d3  mov     qword ptr [rdi+8], 0
0x1800090db  mov     [rdi], rsi
0x1800090de  mov     eax, 1
0x1800090e3  mov     [rdi+8], rbp
0x1800090e7  lock add [rsi], eax
0x1800090ea  add     rsp, 28h
0x1800090ee  pop     rdi
0x1800090ef  pop     rsi
0x1800090f0  pop     rbp
0x1800090f1  pop     rbx
0x1800090f2  retn
```
