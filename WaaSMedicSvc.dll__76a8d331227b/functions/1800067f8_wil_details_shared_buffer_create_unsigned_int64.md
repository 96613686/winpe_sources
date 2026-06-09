# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800067f8`
- end: `0x1800068bb`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c30`
- `0x1800068d0`

## callees

- `0x1800067f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006831`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006895`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006831`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006895`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006823`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000684d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006887`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006823`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000684d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006887`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000685c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000685c`

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
0x1800067f8  push    rbx
0x1800067fa  push    rbp
0x1800067fb  push    rsi
0x1800067fc  push    rdi
0x1800067fd  sub     rsp, 28h
0x180006801  mov     rbp, rdx
0x180006804  mov     rdi, rcx
0x180006807  test    rdx, rdx
0x18000680a  jnz     short loc_18000684D
0x18000680c  mov     rcx, [rcx]
0x18000680f  test    rcx, rcx
0x180006812  jz      short loc_180006846
0x180006814  or      eax, 0FFFFFFFFh
0x180006817  lock xadd [rcx], eax
0x18000681b  cmp     eax, 1
0x18000681e  jnz     short loc_180006837
0x180006820  mov     rbx, [rdi]
0x180006823  call    cs:__imp_GetProcessHeap
0x180006829  mov     r8, rbx; lpMem
0x18000682c  xor     edx, edx; dwFlags
0x18000682e  mov     rcx, rax; hHeap
0x180006831  call    cs:__imp_HeapFree
0x180006837  mov     qword ptr [rdi], 0
0x18000683e  mov     qword ptr [rdi+8], 0
0x180006846  mov     eax, 1
0x18000684b  jmp     short loc_1800068B2
0x18000684d  call    cs:__imp_GetProcessHeap
0x180006853  lea     r8, [rbp+4]; dwBytes
0x180006857  xor     edx, edx; dwFlags
0x180006859  mov     rcx, rax; hHeap
0x18000685c  call    cs:__imp_HeapAlloc
0x180006862  mov     rsi, rax
0x180006865  test    rax, rax
0x180006868  jz      short loc_1800068B2
0x18000686a  mov     dword ptr [rax], 0
0x180006870  mov     rcx, [rdi]
0x180006873  test    rcx, rcx
0x180006876  jz      short loc_1800068A3
0x180006878  or      eax, 0FFFFFFFFh
0x18000687b  lock xadd [rcx], eax
0x18000687f  cmp     eax, 1
0x180006882  jnz     short loc_18000689B
0x180006884  mov     rbx, [rdi]
0x180006887  call    cs:__imp_GetProcessHeap
0x18000688d  mov     r8, rbx; lpMem
0x180006890  xor     edx, edx; dwFlags
0x180006892  mov     rcx, rax; hHeap
0x180006895  call    cs:__imp_HeapFree
0x18000689b  mov     qword ptr [rdi+8], 0
0x1800068a3  mov     [rdi], rsi
0x1800068a6  mov     eax, 1
0x1800068ab  mov     [rdi+8], rbp
0x1800068af  lock add [rsi], eax
0x1800068b2  add     rsp, 28h
0x1800068b6  pop     rdi
0x1800068b7  pop     rsi
0x1800068b8  pop     rbp
0x1800068b9  pop     rbx
0x1800068ba  retn
```
