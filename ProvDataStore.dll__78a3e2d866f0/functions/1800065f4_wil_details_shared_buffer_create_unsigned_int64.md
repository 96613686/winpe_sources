# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800065f4`
- end: `0x1800066b7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800056d0`
- `0x180006890`

## callees

- `0x1800065f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006658`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006658`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000662d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006691`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000662d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006691`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000661f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006683`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000661f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006683`

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
0x1800065f4  push    rbx
0x1800065f6  push    rbp
0x1800065f7  push    rsi
0x1800065f8  push    rdi
0x1800065f9  sub     rsp, 28h
0x1800065fd  mov     rbp, rdx
0x180006600  mov     rdi, rcx
0x180006603  test    rdx, rdx
0x180006606  jnz     short loc_180006649
0x180006608  mov     rcx, [rcx]
0x18000660b  test    rcx, rcx
0x18000660e  jz      short loc_180006642
0x180006610  or      eax, 0FFFFFFFFh
0x180006613  lock xadd [rcx], eax
0x180006617  cmp     eax, 1
0x18000661a  jnz     short loc_180006633
0x18000661c  mov     rbx, [rdi]
0x18000661f  call    cs:__imp_GetProcessHeap
0x180006625  mov     r8, rbx; lpMem
0x180006628  xor     edx, edx; dwFlags
0x18000662a  mov     rcx, rax; hHeap
0x18000662d  call    cs:__imp_HeapFree
0x180006633  mov     qword ptr [rdi], 0
0x18000663a  mov     qword ptr [rdi+8], 0
0x180006642  mov     eax, 1
0x180006647  jmp     short loc_1800066AE
0x180006649  call    cs:__imp_GetProcessHeap
0x18000664f  lea     r8, [rbp+4]; dwBytes
0x180006653  xor     edx, edx; dwFlags
0x180006655  mov     rcx, rax; hHeap
0x180006658  call    cs:__imp_HeapAlloc
0x18000665e  mov     rsi, rax
0x180006661  test    rax, rax
0x180006664  jz      short loc_1800066AE
0x180006666  mov     dword ptr [rax], 0
0x18000666c  mov     rcx, [rdi]
0x18000666f  test    rcx, rcx
0x180006672  jz      short loc_18000669F
0x180006674  or      eax, 0FFFFFFFFh
0x180006677  lock xadd [rcx], eax
0x18000667b  cmp     eax, 1
0x18000667e  jnz     short loc_180006697
0x180006680  mov     rbx, [rdi]
0x180006683  call    cs:__imp_GetProcessHeap
0x180006689  mov     r8, rbx; lpMem
0x18000668c  xor     edx, edx; dwFlags
0x18000668e  mov     rcx, rax; hHeap
0x180006691  call    cs:__imp_HeapFree
0x180006697  mov     qword ptr [rdi+8], 0
0x18000669f  mov     [rdi], rsi
0x1800066a2  mov     eax, 1
0x1800066a7  mov     [rdi+8], rbp
0x1800066ab  lock add [rsi], eax
0x1800066ae  add     rsp, 28h
0x1800066b2  pop     rdi
0x1800066b3  pop     rsi
0x1800066b4  pop     rbp
0x1800066b5  pop     rbx
0x1800066b6  retn
```
