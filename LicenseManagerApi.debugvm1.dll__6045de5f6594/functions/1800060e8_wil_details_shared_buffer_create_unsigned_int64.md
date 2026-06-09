# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800060e8`
- end: `0x1800061ab`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005560`
- `0x1800061c0`

## callees

- `0x1800060e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006121`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006185`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006121`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006185`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006113`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000613d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006177`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006113`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000613d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006177`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000614c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000614c`

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
0x1800060e8  push    rbx
0x1800060ea  push    rbp
0x1800060eb  push    rsi
0x1800060ec  push    rdi
0x1800060ed  sub     rsp, 28h
0x1800060f1  mov     rbp, rdx
0x1800060f4  mov     rdi, rcx
0x1800060f7  test    rdx, rdx
0x1800060fa  jnz     short loc_18000613D
0x1800060fc  mov     rcx, [rcx]
0x1800060ff  test    rcx, rcx
0x180006102  jz      short loc_180006136
0x180006104  or      eax, 0FFFFFFFFh
0x180006107  lock xadd [rcx], eax
0x18000610b  cmp     eax, 1
0x18000610e  jnz     short loc_180006127
0x180006110  mov     rbx, [rdi]
0x180006113  call    cs:__imp_GetProcessHeap
0x180006119  mov     r8, rbx; lpMem
0x18000611c  xor     edx, edx; dwFlags
0x18000611e  mov     rcx, rax; hHeap
0x180006121  call    cs:__imp_HeapFree
0x180006127  mov     qword ptr [rdi], 0
0x18000612e  mov     qword ptr [rdi+8], 0
0x180006136  mov     eax, 1
0x18000613b  jmp     short loc_1800061A2
0x18000613d  call    cs:__imp_GetProcessHeap
0x180006143  lea     r8, [rbp+4]; dwBytes
0x180006147  xor     edx, edx; dwFlags
0x180006149  mov     rcx, rax; hHeap
0x18000614c  call    cs:__imp_HeapAlloc
0x180006152  mov     rsi, rax
0x180006155  test    rax, rax
0x180006158  jz      short loc_1800061A2
0x18000615a  mov     dword ptr [rax], 0
0x180006160  mov     rcx, [rdi]
0x180006163  test    rcx, rcx
0x180006166  jz      short loc_180006193
0x180006168  or      eax, 0FFFFFFFFh
0x18000616b  lock xadd [rcx], eax
0x18000616f  cmp     eax, 1
0x180006172  jnz     short loc_18000618B
0x180006174  mov     rbx, [rdi]
0x180006177  call    cs:__imp_GetProcessHeap
0x18000617d  mov     r8, rbx; lpMem
0x180006180  xor     edx, edx; dwFlags
0x180006182  mov     rcx, rax; hHeap
0x180006185  call    cs:__imp_HeapFree
0x18000618b  mov     qword ptr [rdi+8], 0
0x180006193  mov     [rdi], rsi
0x180006196  mov     eax, 1
0x18000619b  mov     [rdi+8], rbp
0x18000619f  lock add [rsi], eax
0x1800061a2  add     rsp, 28h
0x1800061a6  pop     rdi
0x1800061a7  pop     rsi
0x1800061a8  pop     rbp
0x1800061a9  pop     rbx
0x1800061aa  retn
```
