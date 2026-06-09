# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140004780`
- end: `0x140004843`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004034`
- `0x140004850`

## callees

- `0x140004780`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400047ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400047d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000480f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400047ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400047d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000480f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400047e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400047e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400047b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000481d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400047b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000481d`

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
0x140004780  push    rbx
0x140004782  push    rbp
0x140004783  push    rsi
0x140004784  push    rdi
0x140004785  sub     rsp, 28h
0x140004789  mov     rbp, rdx
0x14000478c  mov     rdi, rcx
0x14000478f  test    rdx, rdx
0x140004792  jnz     short loc_1400047D5
0x140004794  mov     rcx, [rcx]
0x140004797  test    rcx, rcx
0x14000479a  jz      short loc_1400047CE
0x14000479c  or      eax, 0FFFFFFFFh
0x14000479f  lock xadd [rcx], eax
0x1400047a3  cmp     eax, 1
0x1400047a6  jnz     short loc_1400047BF
0x1400047a8  mov     rbx, [rdi]
0x1400047ab  call    cs:__imp_GetProcessHeap
0x1400047b1  mov     r8, rbx; lpMem
0x1400047b4  xor     edx, edx; dwFlags
0x1400047b6  mov     rcx, rax; hHeap
0x1400047b9  call    cs:__imp_HeapFree
0x1400047bf  mov     qword ptr [rdi], 0
0x1400047c6  mov     qword ptr [rdi+8], 0
0x1400047ce  mov     eax, 1
0x1400047d3  jmp     short loc_14000483A
0x1400047d5  call    cs:__imp_GetProcessHeap
0x1400047db  lea     r8, [rbp+4]; dwBytes
0x1400047df  xor     edx, edx; dwFlags
0x1400047e1  mov     rcx, rax; hHeap
0x1400047e4  call    cs:__imp_HeapAlloc
0x1400047ea  mov     rsi, rax
0x1400047ed  test    rax, rax
0x1400047f0  jz      short loc_14000483A
0x1400047f2  mov     dword ptr [rax], 0
0x1400047f8  mov     rcx, [rdi]
0x1400047fb  test    rcx, rcx
0x1400047fe  jz      short loc_14000482B
0x140004800  or      eax, 0FFFFFFFFh
0x140004803  lock xadd [rcx], eax
0x140004807  cmp     eax, 1
0x14000480a  jnz     short loc_140004823
0x14000480c  mov     rbx, [rdi]
0x14000480f  call    cs:__imp_GetProcessHeap
0x140004815  mov     r8, rbx; lpMem
0x140004818  xor     edx, edx; dwFlags
0x14000481a  mov     rcx, rax; hHeap
0x14000481d  call    cs:__imp_HeapFree
0x140004823  mov     qword ptr [rdi+8], 0
0x14000482b  mov     [rdi], rsi
0x14000482e  mov     eax, 1
0x140004833  mov     [rdi+8], rbp
0x140004837  lock add [rsi], eax
0x14000483a  add     rsp, 28h
0x14000483e  pop     rdi
0x14000483f  pop     rsi
0x140004840  pop     rbp
0x140004841  pop     rbx
0x140004842  retn
```
