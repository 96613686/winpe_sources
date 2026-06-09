# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000f388`
- end: `0x14000f44b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d498`
- `0x14000f660`

## callees

- `0x14000f388`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f3ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f3ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f3c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f425`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f3c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f425`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f3b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f3dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f417`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f3b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f3dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f417`

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
0x14000f388  push    rbx
0x14000f38a  push    rbp
0x14000f38b  push    rsi
0x14000f38c  push    rdi
0x14000f38d  sub     rsp, 28h
0x14000f391  mov     rbp, rdx
0x14000f394  mov     rdi, rcx
0x14000f397  test    rdx, rdx
0x14000f39a  jnz     short loc_14000F3DD
0x14000f39c  mov     rcx, [rcx]
0x14000f39f  test    rcx, rcx
0x14000f3a2  jz      short loc_14000F3D6
0x14000f3a4  or      eax, 0FFFFFFFFh
0x14000f3a7  lock xadd [rcx], eax
0x14000f3ab  cmp     eax, 1
0x14000f3ae  jnz     short loc_14000F3C7
0x14000f3b0  mov     rbx, [rdi]
0x14000f3b3  call    cs:__imp_GetProcessHeap
0x14000f3b9  mov     r8, rbx; lpMem
0x14000f3bc  xor     edx, edx; dwFlags
0x14000f3be  mov     rcx, rax; hHeap
0x14000f3c1  call    cs:__imp_HeapFree
0x14000f3c7  mov     qword ptr [rdi], 0
0x14000f3ce  mov     qword ptr [rdi+8], 0
0x14000f3d6  mov     eax, 1
0x14000f3db  jmp     short loc_14000F442
0x14000f3dd  call    cs:__imp_GetProcessHeap
0x14000f3e3  lea     r8, [rbp+4]; dwBytes
0x14000f3e7  xor     edx, edx; dwFlags
0x14000f3e9  mov     rcx, rax; hHeap
0x14000f3ec  call    cs:__imp_HeapAlloc
0x14000f3f2  mov     rsi, rax
0x14000f3f5  test    rax, rax
0x14000f3f8  jz      short loc_14000F442
0x14000f3fa  mov     dword ptr [rax], 0
0x14000f400  mov     rcx, [rdi]
0x14000f403  test    rcx, rcx
0x14000f406  jz      short loc_14000F433
0x14000f408  or      eax, 0FFFFFFFFh
0x14000f40b  lock xadd [rcx], eax
0x14000f40f  cmp     eax, 1
0x14000f412  jnz     short loc_14000F42B
0x14000f414  mov     rbx, [rdi]
0x14000f417  call    cs:__imp_GetProcessHeap
0x14000f41d  mov     r8, rbx; lpMem
0x14000f420  xor     edx, edx; dwFlags
0x14000f422  mov     rcx, rax; hHeap
0x14000f425  call    cs:__imp_HeapFree
0x14000f42b  mov     qword ptr [rdi+8], 0
0x14000f433  mov     [rdi], rsi
0x14000f436  mov     eax, 1
0x14000f43b  mov     [rdi+8], rbp
0x14000f43f  lock add [rsi], eax
0x14000f442  add     rsp, 28h
0x14000f446  pop     rdi
0x14000f447  pop     rsi
0x14000f448  pop     rbp
0x14000f449  pop     rbx
0x14000f44a  retn
```
