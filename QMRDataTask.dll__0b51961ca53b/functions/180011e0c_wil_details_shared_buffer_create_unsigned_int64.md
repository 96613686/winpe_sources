# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180011e0c`
- end: `0x180011ecf`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e40c`
- `0x180011fd0`

## callees

- `0x180011e0c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180011e37`
- `KERNEL32!GetProcessHeap` at `0x180011e61`
- `KERNEL32!GetProcessHeap` at `0x180011e9b`
- `KERNEL32!GetProcessHeap` at `0x180011e37`
- `KERNEL32!GetProcessHeap` at `0x180011e61`
- `KERNEL32!GetProcessHeap` at `0x180011e9b`
- `KERNEL32!HeapAlloc` at `0x180011e70`
- `KERNEL32!HeapAlloc` at `0x180011e70`
- `KERNEL32!HeapFree` at `0x180011e45`
- `KERNEL32!HeapFree` at `0x180011ea9`
- `KERNEL32!HeapFree` at `0x180011e45`
- `KERNEL32!HeapFree` at `0x180011ea9`

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
0x180011e0c  push    rbx
0x180011e0e  push    rbp
0x180011e0f  push    rsi
0x180011e10  push    rdi
0x180011e11  sub     rsp, 28h
0x180011e15  mov     rbp, rdx
0x180011e18  mov     rdi, rcx
0x180011e1b  test    rdx, rdx
0x180011e1e  jnz     short loc_180011E61
0x180011e20  mov     rcx, [rcx]
0x180011e23  test    rcx, rcx
0x180011e26  jz      short loc_180011E5A
0x180011e28  or      eax, 0FFFFFFFFh
0x180011e2b  lock xadd [rcx], eax
0x180011e2f  cmp     eax, 1
0x180011e32  jnz     short loc_180011E4B
0x180011e34  mov     rbx, [rdi]
0x180011e37  call    cs:__imp_GetProcessHeap
0x180011e3d  mov     r8, rbx; lpMem
0x180011e40  xor     edx, edx; dwFlags
0x180011e42  mov     rcx, rax; hHeap
0x180011e45  call    cs:__imp_HeapFree
0x180011e4b  mov     qword ptr [rdi], 0
0x180011e52  mov     qword ptr [rdi+8], 0
0x180011e5a  mov     eax, 1
0x180011e5f  jmp     short loc_180011EC6
0x180011e61  call    cs:__imp_GetProcessHeap
0x180011e67  lea     r8, [rbp+4]; dwBytes
0x180011e6b  xor     edx, edx; dwFlags
0x180011e6d  mov     rcx, rax; hHeap
0x180011e70  call    cs:__imp_HeapAlloc
0x180011e76  mov     rsi, rax
0x180011e79  test    rax, rax
0x180011e7c  jz      short loc_180011EC6
0x180011e7e  mov     dword ptr [rax], 0
0x180011e84  mov     rcx, [rdi]
0x180011e87  test    rcx, rcx
0x180011e8a  jz      short loc_180011EB7
0x180011e8c  or      eax, 0FFFFFFFFh
0x180011e8f  lock xadd [rcx], eax
0x180011e93  cmp     eax, 1
0x180011e96  jnz     short loc_180011EAF
0x180011e98  mov     rbx, [rdi]
0x180011e9b  call    cs:__imp_GetProcessHeap
0x180011ea1  mov     r8, rbx; lpMem
0x180011ea4  xor     edx, edx; dwFlags
0x180011ea6  mov     rcx, rax; hHeap
0x180011ea9  call    cs:__imp_HeapFree
0x180011eaf  mov     qword ptr [rdi+8], 0
0x180011eb7  mov     [rdi], rsi
0x180011eba  mov     eax, 1
0x180011ebf  mov     [rdi+8], rbp
0x180011ec3  lock add [rsi], eax
0x180011ec6  add     rsp, 28h
0x180011eca  pop     rdi
0x180011ecb  pop     rsi
0x180011ecc  pop     rbp
0x180011ecd  pop     rbx
0x180011ece  retn
```
