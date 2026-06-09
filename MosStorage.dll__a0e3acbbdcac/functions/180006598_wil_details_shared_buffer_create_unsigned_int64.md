# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180006598`
- end: `0x18000665b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a20`
- `0x180006670`

## callees

- `0x180006598`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800065fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800065fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006635`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006635`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006627`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006627`

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
0x180006598  push    rbx
0x18000659a  push    rbp
0x18000659b  push    rsi
0x18000659c  push    rdi
0x18000659d  sub     rsp, 28h
0x1800065a1  mov     rbp, rdx
0x1800065a4  mov     rdi, rcx
0x1800065a7  test    rdx, rdx
0x1800065aa  jnz     short loc_1800065ED
0x1800065ac  mov     rcx, [rcx]
0x1800065af  test    rcx, rcx
0x1800065b2  jz      short loc_1800065E6
0x1800065b4  or      eax, 0FFFFFFFFh
0x1800065b7  lock xadd [rcx], eax
0x1800065bb  cmp     eax, 1
0x1800065be  jnz     short loc_1800065D7
0x1800065c0  mov     rbx, [rdi]
0x1800065c3  call    cs:__imp_GetProcessHeap
0x1800065c9  mov     r8, rbx; lpMem
0x1800065cc  xor     edx, edx; dwFlags
0x1800065ce  mov     rcx, rax; hHeap
0x1800065d1  call    cs:__imp_HeapFree
0x1800065d7  mov     qword ptr [rdi], 0
0x1800065de  mov     qword ptr [rdi+8], 0
0x1800065e6  mov     eax, 1
0x1800065eb  jmp     short loc_180006652
0x1800065ed  call    cs:__imp_GetProcessHeap
0x1800065f3  lea     r8, [rbp+4]; dwBytes
0x1800065f7  xor     edx, edx; dwFlags
0x1800065f9  mov     rcx, rax; hHeap
0x1800065fc  call    cs:__imp_HeapAlloc
0x180006602  mov     rsi, rax
0x180006605  test    rax, rax
0x180006608  jz      short loc_180006652
0x18000660a  mov     dword ptr [rax], 0
0x180006610  mov     rcx, [rdi]
0x180006613  test    rcx, rcx
0x180006616  jz      short loc_180006643
0x180006618  or      eax, 0FFFFFFFFh
0x18000661b  lock xadd [rcx], eax
0x18000661f  cmp     eax, 1
0x180006622  jnz     short loc_18000663B
0x180006624  mov     rbx, [rdi]
0x180006627  call    cs:__imp_GetProcessHeap
0x18000662d  mov     r8, rbx; lpMem
0x180006630  xor     edx, edx; dwFlags
0x180006632  mov     rcx, rax; hHeap
0x180006635  call    cs:__imp_HeapFree
0x18000663b  mov     qword ptr [rdi+8], 0
0x180006643  mov     [rdi], rsi
0x180006646  mov     eax, 1
0x18000664b  mov     [rdi+8], rbp
0x18000664f  lock add [rsi], eax
0x180006652  add     rsp, 28h
0x180006656  pop     rdi
0x180006657  pop     rsi
0x180006658  pop     rbp
0x180006659  pop     rbx
0x18000665a  retn
```
