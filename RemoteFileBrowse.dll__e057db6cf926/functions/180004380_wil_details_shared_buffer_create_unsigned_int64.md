# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180004380`
- end: `0x180004443`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c34`
- `0x180004450`

## callees

- `0x180004380`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000440f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000440f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800043e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800043e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000441d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000441d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180004380  push    rbx
0x180004382  push    rbp
0x180004383  push    rsi
0x180004384  push    rdi
0x180004385  sub     rsp, 28h
0x180004389  mov     rbp, rdx
0x18000438c  mov     rdi, rcx
0x18000438f  test    rdx, rdx
0x180004392  jnz     short loc_1800043D5
0x180004394  mov     rcx, [rcx]
0x180004397  test    rcx, rcx
0x18000439a  jz      short loc_1800043CE
0x18000439c  or      eax, 0FFFFFFFFh
0x18000439f  lock xadd [rcx], eax
0x1800043a3  cmp     eax, 1
0x1800043a6  jnz     short loc_1800043BF
0x1800043a8  mov     rbx, [rdi]
0x1800043ab  call    cs:__imp_GetProcessHeap
0x1800043b1  mov     r8, rbx; lpMem
0x1800043b4  xor     edx, edx; dwFlags
0x1800043b6  mov     rcx, rax; hHeap
0x1800043b9  call    cs:__imp_HeapFree
0x1800043bf  mov     qword ptr [rdi], 0
0x1800043c6  mov     qword ptr [rdi+8], 0
0x1800043ce  mov     eax, 1
0x1800043d3  jmp     short loc_18000443A
0x1800043d5  call    cs:__imp_GetProcessHeap
0x1800043db  lea     r8, [rbp+4]; dwBytes
0x1800043df  xor     edx, edx; dwFlags
0x1800043e1  mov     rcx, rax; hHeap
0x1800043e4  call    cs:__imp_HeapAlloc
0x1800043ea  mov     rsi, rax
0x1800043ed  test    rax, rax
0x1800043f0  jz      short loc_18000443A
0x1800043f2  mov     dword ptr [rax], 0
0x1800043f8  mov     rcx, [rdi]
0x1800043fb  test    rcx, rcx
0x1800043fe  jz      short loc_18000442B
0x180004400  or      eax, 0FFFFFFFFh
0x180004403  lock xadd [rcx], eax
0x180004407  cmp     eax, 1
0x18000440a  jnz     short loc_180004423
0x18000440c  mov     rbx, [rdi]
0x18000440f  call    cs:__imp_GetProcessHeap
0x180004415  mov     r8, rbx; lpMem
0x180004418  xor     edx, edx; dwFlags
0x18000441a  mov     rcx, rax; hHeap
0x18000441d  call    cs:__imp_HeapFree
0x180004423  mov     qword ptr [rdi+8], 0
0x18000442b  mov     [rdi], rsi
0x18000442e  mov     eax, 1
0x180004433  mov     [rdi+8], rbp
0x180004437  lock add [rsi], eax
0x18000443a  add     rsp, 28h
0x18000443e  pop     rdi
0x18000443f  pop     rsi
0x180004440  pop     rbp
0x180004441  pop     rbx
0x180004442  retn
```
