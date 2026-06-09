# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007de4`
- end: `0x180007ebe`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `218`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000811c`
- `0x1800086a0`

## callees

- `0x180007de4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e8c`

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
0x180007de4  mov     [rsp+arg_0], rbx
0x180007de9  mov     [rsp+arg_8], rbp
0x180007dee  mov     [rsp+arg_10], rsi
0x180007df3  push    rdi
0x180007df4  sub     rsp, 20h
0x180007df8  mov     rbp, rdx
0x180007dfb  mov     rdi, rcx
0x180007dfe  test    rdx, rdx
0x180007e01  jnz     short loc_180007E44
0x180007e03  mov     rcx, [rcx]
0x180007e06  test    rcx, rcx
0x180007e09  jz      short loc_180007E3D
0x180007e0b  or      eax, 0FFFFFFFFh
0x180007e0e  lock xadd [rcx], eax
0x180007e12  cmp     eax, 1
0x180007e15  jnz     short loc_180007E2E
0x180007e17  mov     rbx, [rdi]
0x180007e1a  call    cs:__imp_GetProcessHeap
0x180007e20  mov     r8, rbx; lpMem
0x180007e23  xor     edx, edx; dwFlags
0x180007e25  mov     rcx, rax; hHeap
0x180007e28  call    cs:__imp_HeapFree
0x180007e2e  mov     qword ptr [rdi], 0
0x180007e35  mov     qword ptr [rdi+8], 0
0x180007e3d  mov     eax, 1
0x180007e42  jmp     short loc_180007EA9
0x180007e44  call    cs:__imp_GetProcessHeap
0x180007e4a  lea     r8, [rbp+4]; dwBytes
0x180007e4e  xor     edx, edx; dwFlags
0x180007e50  mov     rcx, rax; hHeap
0x180007e53  call    cs:__imp_HeapAlloc
0x180007e59  mov     rsi, rax
0x180007e5c  test    rax, rax
0x180007e5f  jz      short loc_180007EA9
0x180007e61  mov     dword ptr [rax], 0
0x180007e67  mov     rcx, [rdi]
0x180007e6a  test    rcx, rcx
0x180007e6d  jz      short loc_180007E9A
0x180007e6f  or      eax, 0FFFFFFFFh
0x180007e72  lock xadd [rcx], eax
0x180007e76  cmp     eax, 1
0x180007e79  jnz     short loc_180007E92
0x180007e7b  mov     rbx, [rdi]
0x180007e7e  call    cs:__imp_GetProcessHeap
0x180007e84  mov     r8, rbx; lpMem
0x180007e87  xor     edx, edx; dwFlags
0x180007e89  mov     rcx, rax; hHeap
0x180007e8c  call    cs:__imp_HeapFree
0x180007e92  mov     qword ptr [rdi+8], 0
0x180007e9a  mov     [rdi], rsi
0x180007e9d  mov     eax, 1
0x180007ea2  mov     [rdi+8], rbp
0x180007ea6  lock add [rsi], eax
0x180007ea9  mov     rbx, [rsp+28h+arg_0]
0x180007eae  mov     rbp, [rsp+28h+arg_8]
0x180007eb3  mov     rsi, [rsp+28h+arg_10]
0x180007eb8  add     rsp, 20h
0x180007ebc  pop     rdi
0x180007ebd  retn
```
