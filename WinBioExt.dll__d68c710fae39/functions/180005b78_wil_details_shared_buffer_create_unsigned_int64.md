# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180005b78`
- end: `0x180005c3b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005004`
- `0x180005c50`

## callees

- `0x180005b78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bdc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bdc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ba3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ba3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c15`

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
0x180005b78  push    rbx
0x180005b7a  push    rbp
0x180005b7b  push    rsi
0x180005b7c  push    rdi
0x180005b7d  sub     rsp, 28h
0x180005b81  mov     rbp, rdx
0x180005b84  mov     rdi, rcx
0x180005b87  test    rdx, rdx
0x180005b8a  jnz     short loc_180005BCD
0x180005b8c  mov     rcx, [rcx]
0x180005b8f  test    rcx, rcx
0x180005b92  jz      short loc_180005BC6
0x180005b94  or      eax, 0FFFFFFFFh
0x180005b97  lock xadd [rcx], eax
0x180005b9b  cmp     eax, 1
0x180005b9e  jnz     short loc_180005BB7
0x180005ba0  mov     rbx, [rdi]
0x180005ba3  call    cs:__imp_GetProcessHeap
0x180005ba9  mov     r8, rbx; lpMem
0x180005bac  xor     edx, edx; dwFlags
0x180005bae  mov     rcx, rax; hHeap
0x180005bb1  call    cs:__imp_HeapFree
0x180005bb7  mov     qword ptr [rdi], 0
0x180005bbe  mov     qword ptr [rdi+8], 0
0x180005bc6  mov     eax, 1
0x180005bcb  jmp     short loc_180005C32
0x180005bcd  call    cs:__imp_GetProcessHeap
0x180005bd3  lea     r8, [rbp+4]; dwBytes
0x180005bd7  xor     edx, edx; dwFlags
0x180005bd9  mov     rcx, rax; hHeap
0x180005bdc  call    cs:__imp_HeapAlloc
0x180005be2  mov     rsi, rax
0x180005be5  test    rax, rax
0x180005be8  jz      short loc_180005C32
0x180005bea  mov     dword ptr [rax], 0
0x180005bf0  mov     rcx, [rdi]
0x180005bf3  test    rcx, rcx
0x180005bf6  jz      short loc_180005C23
0x180005bf8  or      eax, 0FFFFFFFFh
0x180005bfb  lock xadd [rcx], eax
0x180005bff  cmp     eax, 1
0x180005c02  jnz     short loc_180005C1B
0x180005c04  mov     rbx, [rdi]
0x180005c07  call    cs:__imp_GetProcessHeap
0x180005c0d  mov     r8, rbx; lpMem
0x180005c10  xor     edx, edx; dwFlags
0x180005c12  mov     rcx, rax; hHeap
0x180005c15  call    cs:__imp_HeapFree
0x180005c1b  mov     qword ptr [rdi+8], 0
0x180005c23  mov     [rdi], rsi
0x180005c26  mov     eax, 1
0x180005c2b  mov     [rdi+8], rbp
0x180005c2f  lock add [rsi], eax
0x180005c32  add     rsp, 28h
0x180005c36  pop     rdi
0x180005c37  pop     rsi
0x180005c38  pop     rbp
0x180005c39  pop     rbx
0x180005c3a  retn
```
