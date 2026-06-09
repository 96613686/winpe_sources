# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140007424`
- end: `0x1400074e7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006780`
- `0x1400074f0`

## callees

- `0x140007424`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000745d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400074c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000745d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400074c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000744f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007479`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400074b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000744f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007479`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400074b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007488`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007488`

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
0x140007424  push    rbx
0x140007426  push    rbp
0x140007427  push    rsi
0x140007428  push    rdi
0x140007429  sub     rsp, 28h
0x14000742d  mov     rbp, rdx
0x140007430  mov     rdi, rcx
0x140007433  test    rdx, rdx
0x140007436  jnz     short loc_140007479
0x140007438  mov     rcx, [rcx]
0x14000743b  test    rcx, rcx
0x14000743e  jz      short loc_140007472
0x140007440  or      eax, 0FFFFFFFFh
0x140007443  lock xadd [rcx], eax
0x140007447  cmp     eax, 1
0x14000744a  jnz     short loc_140007463
0x14000744c  mov     rbx, [rdi]
0x14000744f  call    cs:__imp_GetProcessHeap
0x140007455  mov     r8, rbx; lpMem
0x140007458  xor     edx, edx; dwFlags
0x14000745a  mov     rcx, rax; hHeap
0x14000745d  call    cs:__imp_HeapFree
0x140007463  mov     qword ptr [rdi], 0
0x14000746a  mov     qword ptr [rdi+8], 0
0x140007472  mov     eax, 1
0x140007477  jmp     short loc_1400074DE
0x140007479  call    cs:__imp_GetProcessHeap
0x14000747f  lea     r8, [rbp+4]; dwBytes
0x140007483  xor     edx, edx; dwFlags
0x140007485  mov     rcx, rax; hHeap
0x140007488  call    cs:__imp_HeapAlloc
0x14000748e  mov     rsi, rax
0x140007491  test    rax, rax
0x140007494  jz      short loc_1400074DE
0x140007496  mov     dword ptr [rax], 0
0x14000749c  mov     rcx, [rdi]
0x14000749f  test    rcx, rcx
0x1400074a2  jz      short loc_1400074CF
0x1400074a4  or      eax, 0FFFFFFFFh
0x1400074a7  lock xadd [rcx], eax
0x1400074ab  cmp     eax, 1
0x1400074ae  jnz     short loc_1400074C7
0x1400074b0  mov     rbx, [rdi]
0x1400074b3  call    cs:__imp_GetProcessHeap
0x1400074b9  mov     r8, rbx; lpMem
0x1400074bc  xor     edx, edx; dwFlags
0x1400074be  mov     rcx, rax; hHeap
0x1400074c1  call    cs:__imp_HeapFree
0x1400074c7  mov     qword ptr [rdi+8], 0
0x1400074cf  mov     [rdi], rsi
0x1400074d2  mov     eax, 1
0x1400074d7  mov     [rdi+8], rbp
0x1400074db  lock add [rsi], eax
0x1400074de  add     rsp, 28h
0x1400074e2  pop     rdi
0x1400074e3  pop     rsi
0x1400074e4  pop     rbp
0x1400074e5  pop     rbx
0x1400074e6  retn
```
