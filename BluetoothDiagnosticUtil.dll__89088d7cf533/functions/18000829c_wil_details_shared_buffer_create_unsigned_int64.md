# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000829c`
- end: `0x180008384`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800072cc`
- `0x180008670`

## callees

- `0x18000829c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800082db`
- `KERNEL32!HeapFree` at `0x180008357`
- `KERNEL32!HeapFree` at `0x1800082db`
- `KERNEL32!HeapFree` at `0x180008357`
- `KERNEL32!GetProcessHeap` at `0x1800082c7`
- `KERNEL32!GetProcessHeap` at `0x1800082fd`
- `KERNEL32!GetProcessHeap` at `0x180008343`
- `KERNEL32!GetProcessHeap` at `0x1800082c7`
- `KERNEL32!GetProcessHeap` at `0x1800082fd`
- `KERNEL32!GetProcessHeap` at `0x180008343`
- `KERNEL32!HeapAlloc` at `0x180008312`
- `KERNEL32!HeapAlloc` at `0x180008312`

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
0x18000829c  push    rbx
0x18000829e  push    rbp
0x18000829f  push    rsi
0x1800082a0  push    rdi
0x1800082a1  sub     rsp, 28h
0x1800082a5  mov     rbp, rdx
0x1800082a8  mov     rdi, rcx
0x1800082ab  test    rdx, rdx
0x1800082ae  jnz     short loc_1800082FD
0x1800082b0  mov     rcx, [rcx]
0x1800082b3  test    rcx, rcx
0x1800082b6  jz      short loc_1800082F6
0x1800082b8  or      eax, 0FFFFFFFFh
0x1800082bb  lock xadd [rcx], eax
0x1800082bf  cmp     eax, 1
0x1800082c2  jnz     short loc_1800082E7
0x1800082c4  mov     rbx, [rdi]
0x1800082c7  call    cs:__imp_GetProcessHeap
0x1800082ce  nop     dword ptr [rax+rax+00h]
0x1800082d3  mov     r8, rbx; lpMem
0x1800082d6  xor     edx, edx; dwFlags
0x1800082d8  mov     rcx, rax; hHeap
0x1800082db  call    cs:__imp_HeapFree
0x1800082e2  nop     dword ptr [rax+rax+00h]
0x1800082e7  mov     qword ptr [rdi], 0
0x1800082ee  mov     qword ptr [rdi+8], 0
0x1800082f6  mov     eax, 1
0x1800082fb  jmp     short loc_18000837A
0x1800082fd  call    cs:__imp_GetProcessHeap
0x180008304  nop     dword ptr [rax+rax+00h]
0x180008309  lea     r8, [rbp+4]; dwBytes
0x18000830d  xor     edx, edx; dwFlags
0x18000830f  mov     rcx, rax; hHeap
0x180008312  call    cs:__imp_HeapAlloc
0x180008319  nop     dword ptr [rax+rax+00h]
0x18000831e  mov     rsi, rax
0x180008321  test    rax, rax
0x180008324  jz      short loc_18000837A
0x180008326  mov     dword ptr [rax], 0
0x18000832c  mov     rcx, [rdi]
0x18000832f  test    rcx, rcx
0x180008332  jz      short loc_18000836B
0x180008334  or      eax, 0FFFFFFFFh
0x180008337  lock xadd [rcx], eax
0x18000833b  cmp     eax, 1
0x18000833e  jnz     short loc_180008363
0x180008340  mov     rbx, [rdi]
0x180008343  call    cs:__imp_GetProcessHeap
0x18000834a  nop     dword ptr [rax+rax+00h]
0x18000834f  mov     r8, rbx; lpMem
0x180008352  xor     edx, edx; dwFlags
0x180008354  mov     rcx, rax; hHeap
0x180008357  call    cs:__imp_HeapFree
0x18000835e  nop     dword ptr [rax+rax+00h]
0x180008363  mov     qword ptr [rdi+8], 0
0x18000836b  mov     [rdi], rsi
0x18000836e  mov     eax, 1
0x180008373  mov     [rdi+8], rbp
0x180008377  lock add [rsi], eax
0x18000837a  add     rsp, 28h
0x18000837e  pop     rdi
0x18000837f  pop     rsi
0x180008380  pop     rbp
0x180008381  pop     rbx
0x180008382  retn
```
