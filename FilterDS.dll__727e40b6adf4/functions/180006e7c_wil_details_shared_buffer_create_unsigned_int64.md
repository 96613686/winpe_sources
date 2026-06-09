# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180006e7c`
- end: `0x180006f3f`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d94`
- `0x180007260`

## callees

- `0x180006e7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ea7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ed1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ea7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ed1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ee0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ee0`

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
0x180006e7c  push    rbx
0x180006e7e  push    rbp
0x180006e7f  push    rsi
0x180006e80  push    rdi
0x180006e81  sub     rsp, 28h
0x180006e85  mov     rbp, rdx
0x180006e88  mov     rdi, rcx
0x180006e8b  test    rdx, rdx
0x180006e8e  jnz     short loc_180006ED1
0x180006e90  mov     rcx, [rcx]
0x180006e93  test    rcx, rcx
0x180006e96  jz      short loc_180006ECA
0x180006e98  or      eax, 0FFFFFFFFh
0x180006e9b  lock xadd [rcx], eax
0x180006e9f  cmp     eax, 1
0x180006ea2  jnz     short loc_180006EBB
0x180006ea4  mov     rbx, [rdi]
0x180006ea7  call    cs:__imp_GetProcessHeap
0x180006ead  mov     r8, rbx; lpMem
0x180006eb0  xor     edx, edx; dwFlags
0x180006eb2  mov     rcx, rax; hHeap
0x180006eb5  call    cs:__imp_HeapFree
0x180006ebb  mov     qword ptr [rdi], 0
0x180006ec2  mov     qword ptr [rdi+8], 0
0x180006eca  mov     eax, 1
0x180006ecf  jmp     short loc_180006F36
0x180006ed1  call    cs:__imp_GetProcessHeap
0x180006ed7  lea     r8, [rbp+4]; dwBytes
0x180006edb  xor     edx, edx; dwFlags
0x180006edd  mov     rcx, rax; hHeap
0x180006ee0  call    cs:__imp_HeapAlloc
0x180006ee6  mov     rsi, rax
0x180006ee9  test    rax, rax
0x180006eec  jz      short loc_180006F36
0x180006eee  mov     dword ptr [rax], 0
0x180006ef4  mov     rcx, [rdi]
0x180006ef7  test    rcx, rcx
0x180006efa  jz      short loc_180006F27
0x180006efc  or      eax, 0FFFFFFFFh
0x180006eff  lock xadd [rcx], eax
0x180006f03  cmp     eax, 1
0x180006f06  jnz     short loc_180006F1F
0x180006f08  mov     rbx, [rdi]
0x180006f0b  call    cs:__imp_GetProcessHeap
0x180006f11  mov     r8, rbx; lpMem
0x180006f14  xor     edx, edx; dwFlags
0x180006f16  mov     rcx, rax; hHeap
0x180006f19  call    cs:__imp_HeapFree
0x180006f1f  mov     qword ptr [rdi+8], 0
0x180006f27  mov     [rdi], rsi
0x180006f2a  mov     eax, 1
0x180006f2f  mov     [rdi+8], rbp
0x180006f33  lock add [rsi], eax
0x180006f36  add     rsp, 28h
0x180006f3a  pop     rdi
0x180006f3b  pop     rsi
0x180006f3c  pop     rbp
0x180006f3d  pop     rbx
0x180006f3e  retn
```
