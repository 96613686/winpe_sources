# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007398`
- end: `0x18000745b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800062f0`
- `0x180007780`

## callees

- `0x180007398`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007427`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007427`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007435`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007435`

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
0x180007398  push    rbx
0x18000739a  push    rbp
0x18000739b  push    rsi
0x18000739c  push    rdi
0x18000739d  sub     rsp, 28h
0x1800073a1  mov     rbp, rdx
0x1800073a4  mov     rdi, rcx
0x1800073a7  test    rdx, rdx
0x1800073aa  jnz     short loc_1800073ED
0x1800073ac  mov     rcx, [rcx]
0x1800073af  test    rcx, rcx
0x1800073b2  jz      short loc_1800073E6
0x1800073b4  or      eax, 0FFFFFFFFh
0x1800073b7  lock xadd [rcx], eax
0x1800073bb  cmp     eax, 1
0x1800073be  jnz     short loc_1800073D7
0x1800073c0  mov     rbx, [rdi]
0x1800073c3  call    cs:__imp_GetProcessHeap
0x1800073c9  mov     r8, rbx; lpMem
0x1800073cc  xor     edx, edx; dwFlags
0x1800073ce  mov     rcx, rax; hHeap
0x1800073d1  call    cs:__imp_HeapFree
0x1800073d7  mov     qword ptr [rdi], 0
0x1800073de  mov     qword ptr [rdi+8], 0
0x1800073e6  mov     eax, 1
0x1800073eb  jmp     short loc_180007452
0x1800073ed  call    cs:__imp_GetProcessHeap
0x1800073f3  lea     r8, [rbp+4]; dwBytes
0x1800073f7  xor     edx, edx; dwFlags
0x1800073f9  mov     rcx, rax; hHeap
0x1800073fc  call    cs:__imp_HeapAlloc
0x180007402  mov     rsi, rax
0x180007405  test    rax, rax
0x180007408  jz      short loc_180007452
0x18000740a  mov     dword ptr [rax], 0
0x180007410  mov     rcx, [rdi]
0x180007413  test    rcx, rcx
0x180007416  jz      short loc_180007443
0x180007418  or      eax, 0FFFFFFFFh
0x18000741b  lock xadd [rcx], eax
0x18000741f  cmp     eax, 1
0x180007422  jnz     short loc_18000743B
0x180007424  mov     rbx, [rdi]
0x180007427  call    cs:__imp_GetProcessHeap
0x18000742d  mov     r8, rbx; lpMem
0x180007430  xor     edx, edx; dwFlags
0x180007432  mov     rcx, rax; hHeap
0x180007435  call    cs:__imp_HeapFree
0x18000743b  mov     qword ptr [rdi+8], 0
0x180007443  mov     [rdi], rsi
0x180007446  mov     eax, 1
0x18000744b  mov     [rdi+8], rbp
0x18000744f  lock add [rsi], eax
0x180007452  add     rsp, 28h
0x180007456  pop     rdi
0x180007457  pop     rsi
0x180007458  pop     rbp
0x180007459  pop     rbx
0x18000745a  retn
```
