# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1400064e8`
- end: `0x1400065ab`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005564`
- `0x1400068d0`

## callees

- `0x1400064e8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140006521`
- `KERNEL32!HeapFree` at `0x140006585`
- `KERNEL32!HeapFree` at `0x140006521`
- `KERNEL32!HeapFree` at `0x140006585`
- `KERNEL32!HeapAlloc` at `0x14000654c`
- `KERNEL32!HeapAlloc` at `0x14000654c`
- `KERNEL32!GetProcessHeap` at `0x140006513`
- `KERNEL32!GetProcessHeap` at `0x14000653d`
- `KERNEL32!GetProcessHeap` at `0x140006577`
- `KERNEL32!GetProcessHeap` at `0x140006513`
- `KERNEL32!GetProcessHeap` at `0x14000653d`
- `KERNEL32!GetProcessHeap` at `0x140006577`

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
0x1400064e8  push    rbx
0x1400064ea  push    rbp
0x1400064eb  push    rsi
0x1400064ec  push    rdi
0x1400064ed  sub     rsp, 28h
0x1400064f1  mov     rbp, rdx
0x1400064f4  mov     rdi, rcx
0x1400064f7  test    rdx, rdx
0x1400064fa  jnz     short loc_14000653D
0x1400064fc  mov     rcx, [rcx]
0x1400064ff  test    rcx, rcx
0x140006502  jz      short loc_140006536
0x140006504  or      eax, 0FFFFFFFFh
0x140006507  lock xadd [rcx], eax
0x14000650b  cmp     eax, 1
0x14000650e  jnz     short loc_140006527
0x140006510  mov     rbx, [rdi]
0x140006513  call    cs:__imp_GetProcessHeap
0x140006519  mov     r8, rbx; lpMem
0x14000651c  xor     edx, edx; dwFlags
0x14000651e  mov     rcx, rax; hHeap
0x140006521  call    cs:__imp_HeapFree
0x140006527  mov     qword ptr [rdi], 0
0x14000652e  mov     qword ptr [rdi+8], 0
0x140006536  mov     eax, 1
0x14000653b  jmp     short loc_1400065A2
0x14000653d  call    cs:__imp_GetProcessHeap
0x140006543  lea     r8, [rbp+4]; dwBytes
0x140006547  xor     edx, edx; dwFlags
0x140006549  mov     rcx, rax; hHeap
0x14000654c  call    cs:__imp_HeapAlloc
0x140006552  mov     rsi, rax
0x140006555  test    rax, rax
0x140006558  jz      short loc_1400065A2
0x14000655a  mov     dword ptr [rax], 0
0x140006560  mov     rcx, [rdi]
0x140006563  test    rcx, rcx
0x140006566  jz      short loc_140006593
0x140006568  or      eax, 0FFFFFFFFh
0x14000656b  lock xadd [rcx], eax
0x14000656f  cmp     eax, 1
0x140006572  jnz     short loc_14000658B
0x140006574  mov     rbx, [rdi]
0x140006577  call    cs:__imp_GetProcessHeap
0x14000657d  mov     r8, rbx; lpMem
0x140006580  xor     edx, edx; dwFlags
0x140006582  mov     rcx, rax; hHeap
0x140006585  call    cs:__imp_HeapFree
0x14000658b  mov     qword ptr [rdi+8], 0
0x140006593  mov     [rdi], rsi
0x140006596  mov     eax, 1
0x14000659b  mov     [rdi+8], rbp
0x14000659f  lock add [rsi], eax
0x1400065a2  add     rsp, 28h
0x1400065a6  pop     rdi
0x1400065a7  pop     rsi
0x1400065a8  pop     rbp
0x1400065a9  pop     rbx
0x1400065aa  retn
```
