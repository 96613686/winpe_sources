# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180006e60`
- end: `0x180006f23`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006060`
- `0x180006f30`

## callees

- `0x180006e60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006efd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006efd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ec4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ec4`

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
0x180006e60  push    rbx
0x180006e62  push    rbp
0x180006e63  push    rsi
0x180006e64  push    rdi
0x180006e65  sub     rsp, 28h
0x180006e69  mov     rbp, rdx
0x180006e6c  mov     rdi, rcx
0x180006e6f  test    rdx, rdx
0x180006e72  jnz     short loc_180006EB5
0x180006e74  mov     rcx, [rcx]
0x180006e77  test    rcx, rcx
0x180006e7a  jz      short loc_180006EAE
0x180006e7c  or      eax, 0FFFFFFFFh
0x180006e7f  lock xadd [rcx], eax
0x180006e83  cmp     eax, 1
0x180006e86  jnz     short loc_180006E9F
0x180006e88  mov     rbx, [rdi]
0x180006e8b  call    cs:__imp_GetProcessHeap
0x180006e91  mov     r8, rbx; lpMem
0x180006e94  xor     edx, edx; dwFlags
0x180006e96  mov     rcx, rax; hHeap
0x180006e99  call    cs:__imp_HeapFree
0x180006e9f  mov     qword ptr [rdi], 0
0x180006ea6  mov     qword ptr [rdi+8], 0
0x180006eae  mov     eax, 1
0x180006eb3  jmp     short loc_180006F1A
0x180006eb5  call    cs:__imp_GetProcessHeap
0x180006ebb  lea     r8, [rbp+4]; dwBytes
0x180006ebf  xor     edx, edx; dwFlags
0x180006ec1  mov     rcx, rax; hHeap
0x180006ec4  call    cs:__imp_HeapAlloc
0x180006eca  mov     rsi, rax
0x180006ecd  test    rax, rax
0x180006ed0  jz      short loc_180006F1A
0x180006ed2  mov     dword ptr [rax], 0
0x180006ed8  mov     rcx, [rdi]
0x180006edb  test    rcx, rcx
0x180006ede  jz      short loc_180006F0B
0x180006ee0  or      eax, 0FFFFFFFFh
0x180006ee3  lock xadd [rcx], eax
0x180006ee7  cmp     eax, 1
0x180006eea  jnz     short loc_180006F03
0x180006eec  mov     rbx, [rdi]
0x180006eef  call    cs:__imp_GetProcessHeap
0x180006ef5  mov     r8, rbx; lpMem
0x180006ef8  xor     edx, edx; dwFlags
0x180006efa  mov     rcx, rax; hHeap
0x180006efd  call    cs:__imp_HeapFree
0x180006f03  mov     qword ptr [rdi+8], 0
0x180006f0b  mov     [rdi], rsi
0x180006f0e  mov     eax, 1
0x180006f13  mov     [rdi+8], rbp
0x180006f17  lock add [rsi], eax
0x180006f1a  add     rsp, 28h
0x180006f1e  pop     rdi
0x180006f1f  pop     rsi
0x180006f20  pop     rbp
0x180006f21  pop     rbx
0x180006f22  retn
```
