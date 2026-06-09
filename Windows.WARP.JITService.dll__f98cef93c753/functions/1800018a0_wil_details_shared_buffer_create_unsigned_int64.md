# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800018a0`
- end: `0x180001963`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001edc`
- `0x180002580`

## callees

- `0x1800018a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800018d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000193d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800018d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000193d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800018cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800018f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000192f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800018cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800018f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000192f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001904`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001904`

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
0x1800018a0  push    rbx
0x1800018a2  push    rbp
0x1800018a3  push    rsi
0x1800018a4  push    rdi
0x1800018a5  sub     rsp, 28h
0x1800018a9  mov     rbp, rdx
0x1800018ac  mov     rdi, rcx
0x1800018af  test    rdx, rdx
0x1800018b2  jnz     short loc_1800018F5
0x1800018b4  mov     rcx, [rcx]
0x1800018b7  test    rcx, rcx
0x1800018ba  jz      short loc_1800018EE
0x1800018bc  or      eax, 0FFFFFFFFh
0x1800018bf  lock xadd [rcx], eax
0x1800018c3  cmp     eax, 1
0x1800018c6  jnz     short loc_1800018DF
0x1800018c8  mov     rbx, [rdi]
0x1800018cb  call    cs:__imp_GetProcessHeap
0x1800018d1  mov     r8, rbx; lpMem
0x1800018d4  xor     edx, edx; dwFlags
0x1800018d6  mov     rcx, rax; hHeap
0x1800018d9  call    cs:__imp_HeapFree
0x1800018df  mov     qword ptr [rdi], 0
0x1800018e6  mov     qword ptr [rdi+8], 0
0x1800018ee  mov     eax, 1
0x1800018f3  jmp     short loc_18000195A
0x1800018f5  call    cs:__imp_GetProcessHeap
0x1800018fb  lea     r8, [rbp+4]; dwBytes
0x1800018ff  xor     edx, edx; dwFlags
0x180001901  mov     rcx, rax; hHeap
0x180001904  call    cs:__imp_HeapAlloc
0x18000190a  mov     rsi, rax
0x18000190d  test    rax, rax
0x180001910  jz      short loc_18000195A
0x180001912  mov     dword ptr [rax], 0
0x180001918  mov     rcx, [rdi]
0x18000191b  test    rcx, rcx
0x18000191e  jz      short loc_18000194B
0x180001920  or      eax, 0FFFFFFFFh
0x180001923  lock xadd [rcx], eax
0x180001927  cmp     eax, 1
0x18000192a  jnz     short loc_180001943
0x18000192c  mov     rbx, [rdi]
0x18000192f  call    cs:__imp_GetProcessHeap
0x180001935  mov     r8, rbx; lpMem
0x180001938  xor     edx, edx; dwFlags
0x18000193a  mov     rcx, rax; hHeap
0x18000193d  call    cs:__imp_HeapFree
0x180001943  mov     qword ptr [rdi+8], 0
0x18000194b  mov     [rdi], rsi
0x18000194e  mov     eax, 1
0x180001953  mov     [rdi+8], rbp
0x180001957  lock add [rsi], eax
0x18000195a  add     rsp, 28h
0x18000195e  pop     rdi
0x18000195f  pop     rsi
0x180001960  pop     rbp
0x180001961  pop     rbx
0x180001962  retn
```
