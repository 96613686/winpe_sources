# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000c310`
- end: `0x18000c3d3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009a3c`
- `0x18000ccc0`

## callees

- `0x18000c310`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000c374`
- `KERNEL32!HeapAlloc` at `0x18000c374`
- `KERNEL32!GetProcessHeap` at `0x18000c33b`
- `KERNEL32!GetProcessHeap` at `0x18000c365`
- `KERNEL32!GetProcessHeap` at `0x18000c39f`
- `KERNEL32!GetProcessHeap` at `0x18000c33b`
- `KERNEL32!GetProcessHeap` at `0x18000c365`
- `KERNEL32!GetProcessHeap` at `0x18000c39f`
- `KERNEL32!HeapFree` at `0x18000c349`
- `KERNEL32!HeapFree` at `0x18000c3ad`
- `KERNEL32!HeapFree` at `0x18000c349`
- `KERNEL32!HeapFree` at `0x18000c3ad`

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
      this[1] = a2;
      result = 1;
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
0x18000c310  push    rbx
0x18000c312  push    rbp
0x18000c313  push    rsi
0x18000c314  push    rdi
0x18000c315  sub     rsp, 28h
0x18000c319  mov     rbp, rdx
0x18000c31c  mov     rdi, rcx
0x18000c31f  test    rdx, rdx
0x18000c322  jnz     short loc_18000C365
0x18000c324  mov     rcx, [rcx]
0x18000c327  test    rcx, rcx
0x18000c32a  jz      short loc_18000C35E
0x18000c32c  or      eax, 0FFFFFFFFh
0x18000c32f  lock xadd [rcx], eax
0x18000c333  cmp     eax, 1
0x18000c336  jnz     short loc_18000C34F
0x18000c338  mov     rbx, [rdi]
0x18000c33b  call    cs:__imp_GetProcessHeap
0x18000c341  mov     r8, rbx; lpMem
0x18000c344  xor     edx, edx; dwFlags
0x18000c346  mov     rcx, rax; hHeap
0x18000c349  call    cs:__imp_HeapFree
0x18000c34f  mov     qword ptr [rdi], 0
0x18000c356  mov     qword ptr [rdi+8], 0
0x18000c35e  mov     eax, 1
0x18000c363  jmp     short loc_18000C3CA
0x18000c365  call    cs:__imp_GetProcessHeap
0x18000c36b  mov     rcx, rax; hHeap
0x18000c36e  lea     r8, [rbp+4]; dwBytes
0x18000c372  xor     edx, edx; dwFlags
0x18000c374  call    cs:__imp_HeapAlloc
0x18000c37a  mov     rsi, rax
0x18000c37d  test    rax, rax
0x18000c380  jz      short loc_18000C3CA
0x18000c382  mov     dword ptr [rax], 0
0x18000c388  mov     rcx, [rdi]
0x18000c38b  test    rcx, rcx
0x18000c38e  jz      short loc_18000C3BB
0x18000c390  or      eax, 0FFFFFFFFh
0x18000c393  lock xadd [rcx], eax
0x18000c397  cmp     eax, 1
0x18000c39a  jnz     short loc_18000C3B3
0x18000c39c  mov     rbx, [rdi]
0x18000c39f  call    cs:__imp_GetProcessHeap
0x18000c3a5  mov     r8, rbx; lpMem
0x18000c3a8  xor     edx, edx; dwFlags
0x18000c3aa  mov     rcx, rax; hHeap
0x18000c3ad  call    cs:__imp_HeapFree
0x18000c3b3  mov     qword ptr [rdi+8], 0
0x18000c3bb  mov     [rdi], rsi
0x18000c3be  mov     [rdi+8], rbp
0x18000c3c2  mov     eax, 1
0x18000c3c7  lock add [rsi], eax
0x18000c3ca  add     rsp, 28h
0x18000c3ce  pop     rdi
0x18000c3cf  pop     rsi
0x18000c3d0  pop     rbp
0x18000c3d1  pop     rbx
0x18000c3d2  retn
```
