# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180016758`
- end: `0x180016840`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180015184`
- `0x1800169e0`

## callees

- `0x180016758`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180016797`
- `KERNEL32!HeapFree` at `0x180016813`
- `KERNEL32!HeapFree` at `0x180016797`
- `KERNEL32!HeapFree` at `0x180016813`
- `KERNEL32!HeapAlloc` at `0x1800167ce`
- `KERNEL32!HeapAlloc` at `0x1800167ce`
- `KERNEL32!GetProcessHeap` at `0x180016783`
- `KERNEL32!GetProcessHeap` at `0x1800167b9`
- `KERNEL32!GetProcessHeap` at `0x1800167ff`
- `KERNEL32!GetProcessHeap` at `0x180016783`
- `KERNEL32!GetProcessHeap` at `0x1800167b9`
- `KERNEL32!GetProcessHeap` at `0x1800167ff`

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
0x180016758  push    rbx
0x18001675a  push    rbp
0x18001675b  push    rsi
0x18001675c  push    rdi
0x18001675d  sub     rsp, 28h
0x180016761  mov     rbp, rdx
0x180016764  mov     rdi, rcx
0x180016767  test    rdx, rdx
0x18001676a  jnz     short loc_1800167B9
0x18001676c  mov     rcx, [rcx]
0x18001676f  test    rcx, rcx
0x180016772  jz      short loc_1800167B2
0x180016774  or      eax, 0FFFFFFFFh
0x180016777  lock xadd [rcx], eax
0x18001677b  cmp     eax, 1
0x18001677e  jnz     short loc_1800167A3
0x180016780  mov     rbx, [rdi]
0x180016783  call    cs:__imp_GetProcessHeap
0x18001678a  nop     dword ptr [rax+rax+00h]
0x18001678f  mov     r8, rbx; lpMem
0x180016792  xor     edx, edx; dwFlags
0x180016794  mov     rcx, rax; hHeap
0x180016797  call    cs:__imp_HeapFree
0x18001679e  nop     dword ptr [rax+rax+00h]
0x1800167a3  mov     qword ptr [rdi], 0
0x1800167aa  mov     qword ptr [rdi+8], 0
0x1800167b2  mov     eax, 1
0x1800167b7  jmp     short loc_180016836
0x1800167b9  call    cs:__imp_GetProcessHeap
0x1800167c0  nop     dword ptr [rax+rax+00h]
0x1800167c5  lea     r8, [rbp+4]; dwBytes
0x1800167c9  xor     edx, edx; dwFlags
0x1800167cb  mov     rcx, rax; hHeap
0x1800167ce  call    cs:__imp_HeapAlloc
0x1800167d5  nop     dword ptr [rax+rax+00h]
0x1800167da  mov     rsi, rax
0x1800167dd  test    rax, rax
0x1800167e0  jz      short loc_180016836
0x1800167e2  mov     dword ptr [rax], 0
0x1800167e8  mov     rcx, [rdi]
0x1800167eb  test    rcx, rcx
0x1800167ee  jz      short loc_180016827
0x1800167f0  or      eax, 0FFFFFFFFh
0x1800167f3  lock xadd [rcx], eax
0x1800167f7  cmp     eax, 1
0x1800167fa  jnz     short loc_18001681F
0x1800167fc  mov     rbx, [rdi]
0x1800167ff  call    cs:__imp_GetProcessHeap
0x180016806  nop     dword ptr [rax+rax+00h]
0x18001680b  mov     r8, rbx; lpMem
0x18001680e  xor     edx, edx; dwFlags
0x180016810  mov     rcx, rax; hHeap
0x180016813  call    cs:__imp_HeapFree
0x18001681a  nop     dword ptr [rax+rax+00h]
0x18001681f  mov     qword ptr [rdi+8], 0
0x180016827  mov     [rdi], rsi
0x18001682a  mov     eax, 1
0x18001682f  mov     [rdi+8], rbp
0x180016833  lock add [rsi], eax
0x180016836  add     rsp, 28h
0x18001683a  pop     rdi
0x18001683b  pop     rsi
0x18001683c  pop     rbp
0x18001683d  pop     rbx
0x18001683e  retn
```
