# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1400017b8`
- end: `0x140001892`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `218`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001dbc`
- `0x140002340`

## callees

- `0x1400017b8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400017fc`
- `KERNEL32!HeapFree` at `0x140001860`
- `KERNEL32!HeapFree` at `0x1400017fc`
- `KERNEL32!HeapFree` at `0x140001860`
- `KERNEL32!HeapAlloc` at `0x140001827`
- `KERNEL32!HeapAlloc` at `0x140001827`
- `KERNEL32!GetProcessHeap` at `0x1400017ee`
- `KERNEL32!GetProcessHeap` at `0x140001818`
- `KERNEL32!GetProcessHeap` at `0x140001852`
- `KERNEL32!GetProcessHeap` at `0x1400017ee`
- `KERNEL32!GetProcessHeap` at `0x140001818`
- `KERNEL32!GetProcessHeap` at `0x140001852`

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
0x1400017b8  mov     [rsp+arg_0], rbx
0x1400017bd  mov     [rsp+arg_8], rbp
0x1400017c2  mov     [rsp+arg_10], rsi
0x1400017c7  push    rdi
0x1400017c8  sub     rsp, 20h
0x1400017cc  mov     rbp, rdx
0x1400017cf  mov     rdi, rcx
0x1400017d2  test    rdx, rdx
0x1400017d5  jnz     short loc_140001818
0x1400017d7  mov     rcx, [rcx]
0x1400017da  test    rcx, rcx
0x1400017dd  jz      short loc_140001811
0x1400017df  or      eax, 0FFFFFFFFh
0x1400017e2  lock xadd [rcx], eax
0x1400017e6  cmp     eax, 1
0x1400017e9  jnz     short loc_140001802
0x1400017eb  mov     rbx, [rdi]
0x1400017ee  call    cs:__imp_GetProcessHeap
0x1400017f4  mov     r8, rbx; lpMem
0x1400017f7  xor     edx, edx; dwFlags
0x1400017f9  mov     rcx, rax; hHeap
0x1400017fc  call    cs:__imp_HeapFree
0x140001802  mov     qword ptr [rdi], 0
0x140001809  mov     qword ptr [rdi+8], 0
0x140001811  mov     eax, 1
0x140001816  jmp     short loc_14000187D
0x140001818  call    cs:__imp_GetProcessHeap
0x14000181e  lea     r8, [rbp+4]; dwBytes
0x140001822  xor     edx, edx; dwFlags
0x140001824  mov     rcx, rax; hHeap
0x140001827  call    cs:__imp_HeapAlloc
0x14000182d  mov     rsi, rax
0x140001830  test    rax, rax
0x140001833  jz      short loc_14000187D
0x140001835  mov     dword ptr [rax], 0
0x14000183b  mov     rcx, [rdi]
0x14000183e  test    rcx, rcx
0x140001841  jz      short loc_14000186E
0x140001843  or      eax, 0FFFFFFFFh
0x140001846  lock xadd [rcx], eax
0x14000184a  cmp     eax, 1
0x14000184d  jnz     short loc_140001866
0x14000184f  mov     rbx, [rdi]
0x140001852  call    cs:__imp_GetProcessHeap
0x140001858  mov     r8, rbx; lpMem
0x14000185b  xor     edx, edx; dwFlags
0x14000185d  mov     rcx, rax; hHeap
0x140001860  call    cs:__imp_HeapFree
0x140001866  mov     qword ptr [rdi+8], 0
0x14000186e  mov     [rdi], rsi
0x140001871  mov     eax, 1
0x140001876  mov     [rdi+8], rbp
0x14000187a  lock add [rsi], eax
0x14000187d  mov     rbx, [rsp+28h+arg_0]
0x140001882  mov     rbp, [rsp+28h+arg_8]
0x140001887  mov     rsi, [rsp+28h+arg_10]
0x14000188c  add     rsp, 20h
0x140001890  pop     rdi
0x140001891  retn
```
