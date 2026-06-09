# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180009618`
- end: `0x180009700`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007cb4`
- `0x1800098a0`

## callees

- `0x180009618`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009643`
- `KERNEL32!GetProcessHeap` at `0x180009679`
- `KERNEL32!GetProcessHeap` at `0x1800096bf`
- `KERNEL32!GetProcessHeap` at `0x180009643`
- `KERNEL32!GetProcessHeap` at `0x180009679`
- `KERNEL32!GetProcessHeap` at `0x1800096bf`
- `KERNEL32!HeapFree` at `0x180009657`
- `KERNEL32!HeapFree` at `0x1800096d3`
- `KERNEL32!HeapFree` at `0x180009657`
- `KERNEL32!HeapFree` at `0x1800096d3`
- `KERNEL32!HeapAlloc` at `0x18000968e`
- `KERNEL32!HeapAlloc` at `0x18000968e`

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
0x180009618  push    rbx
0x18000961a  push    rbp
0x18000961b  push    rsi
0x18000961c  push    rdi
0x18000961d  sub     rsp, 28h
0x180009621  mov     rbp, rdx
0x180009624  mov     rdi, rcx
0x180009627  test    rdx, rdx
0x18000962a  jnz     short loc_180009679
0x18000962c  mov     rcx, [rcx]
0x18000962f  test    rcx, rcx
0x180009632  jz      short loc_180009672
0x180009634  or      eax, 0FFFFFFFFh
0x180009637  lock xadd [rcx], eax
0x18000963b  cmp     eax, 1
0x18000963e  jnz     short loc_180009663
0x180009640  mov     rbx, [rdi]
0x180009643  call    cs:__imp_GetProcessHeap
0x18000964a  nop     dword ptr [rax+rax+00h]
0x18000964f  mov     r8, rbx; lpMem
0x180009652  xor     edx, edx; dwFlags
0x180009654  mov     rcx, rax; hHeap
0x180009657  call    cs:__imp_HeapFree
0x18000965e  nop     dword ptr [rax+rax+00h]
0x180009663  mov     qword ptr [rdi], 0
0x18000966a  mov     qword ptr [rdi+8], 0
0x180009672  mov     eax, 1
0x180009677  jmp     short loc_1800096F6
0x180009679  call    cs:__imp_GetProcessHeap
0x180009680  nop     dword ptr [rax+rax+00h]
0x180009685  lea     r8, [rbp+4]; dwBytes
0x180009689  xor     edx, edx; dwFlags
0x18000968b  mov     rcx, rax; hHeap
0x18000968e  call    cs:__imp_HeapAlloc
0x180009695  nop     dword ptr [rax+rax+00h]
0x18000969a  mov     rsi, rax
0x18000969d  test    rax, rax
0x1800096a0  jz      short loc_1800096F6
0x1800096a2  mov     dword ptr [rax], 0
0x1800096a8  mov     rcx, [rdi]
0x1800096ab  test    rcx, rcx
0x1800096ae  jz      short loc_1800096E7
0x1800096b0  or      eax, 0FFFFFFFFh
0x1800096b3  lock xadd [rcx], eax
0x1800096b7  cmp     eax, 1
0x1800096ba  jnz     short loc_1800096DF
0x1800096bc  mov     rbx, [rdi]
0x1800096bf  call    cs:__imp_GetProcessHeap
0x1800096c6  nop     dword ptr [rax+rax+00h]
0x1800096cb  mov     r8, rbx; lpMem
0x1800096ce  xor     edx, edx; dwFlags
0x1800096d0  mov     rcx, rax; hHeap
0x1800096d3  call    cs:__imp_HeapFree
0x1800096da  nop     dword ptr [rax+rax+00h]
0x1800096df  mov     qword ptr [rdi+8], 0
0x1800096e7  mov     [rdi], rsi
0x1800096ea  mov     eax, 1
0x1800096ef  mov     [rdi+8], rbp
0x1800096f3  lock add [rsi], eax
0x1800096f6  add     rsp, 28h
0x1800096fa  pop     rdi
0x1800096fb  pop     rsi
0x1800096fc  pop     rbp
0x1800096fd  pop     rbx
0x1800096fe  retn
```
