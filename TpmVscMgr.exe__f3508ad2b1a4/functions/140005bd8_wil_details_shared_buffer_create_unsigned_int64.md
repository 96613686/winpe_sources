# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140005bd8`
- end: `0x140005c9b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005060`
- `0x140005cb0`

## callees

- `0x140005bd8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140005c11`
- `KERNEL32!HeapFree` at `0x140005c75`
- `KERNEL32!HeapFree` at `0x140005c11`
- `KERNEL32!HeapFree` at `0x140005c75`
- `KERNEL32!HeapAlloc` at `0x140005c3c`
- `KERNEL32!HeapAlloc` at `0x140005c3c`
- `KERNEL32!GetProcessHeap` at `0x140005c03`
- `KERNEL32!GetProcessHeap` at `0x140005c2d`
- `KERNEL32!GetProcessHeap` at `0x140005c67`
- `KERNEL32!GetProcessHeap` at `0x140005c03`
- `KERNEL32!GetProcessHeap` at `0x140005c2d`
- `KERNEL32!GetProcessHeap` at `0x140005c67`

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
0x140005bd8  push    rbx
0x140005bda  push    rbp
0x140005bdb  push    rsi
0x140005bdc  push    rdi
0x140005bdd  sub     rsp, 28h
0x140005be1  mov     rbp, rdx
0x140005be4  mov     rdi, rcx
0x140005be7  test    rdx, rdx
0x140005bea  jnz     short loc_140005C2D
0x140005bec  mov     rcx, [rcx]
0x140005bef  test    rcx, rcx
0x140005bf2  jz      short loc_140005C26
0x140005bf4  or      eax, 0FFFFFFFFh
0x140005bf7  lock xadd [rcx], eax
0x140005bfb  cmp     eax, 1
0x140005bfe  jnz     short loc_140005C17
0x140005c00  mov     rbx, [rdi]
0x140005c03  call    cs:__imp_GetProcessHeap
0x140005c09  mov     r8, rbx; lpMem
0x140005c0c  xor     edx, edx; dwFlags
0x140005c0e  mov     rcx, rax; hHeap
0x140005c11  call    cs:__imp_HeapFree
0x140005c17  mov     qword ptr [rdi], 0
0x140005c1e  mov     qword ptr [rdi+8], 0
0x140005c26  mov     eax, 1
0x140005c2b  jmp     short loc_140005C92
0x140005c2d  call    cs:__imp_GetProcessHeap
0x140005c33  lea     r8, [rbp+4]; dwBytes
0x140005c37  xor     edx, edx; dwFlags
0x140005c39  mov     rcx, rax; hHeap
0x140005c3c  call    cs:__imp_HeapAlloc
0x140005c42  mov     rsi, rax
0x140005c45  test    rax, rax
0x140005c48  jz      short loc_140005C92
0x140005c4a  mov     dword ptr [rax], 0
0x140005c50  mov     rcx, [rdi]
0x140005c53  test    rcx, rcx
0x140005c56  jz      short loc_140005C83
0x140005c58  or      eax, 0FFFFFFFFh
0x140005c5b  lock xadd [rcx], eax
0x140005c5f  cmp     eax, 1
0x140005c62  jnz     short loc_140005C7B
0x140005c64  mov     rbx, [rdi]
0x140005c67  call    cs:__imp_GetProcessHeap
0x140005c6d  mov     r8, rbx; lpMem
0x140005c70  xor     edx, edx; dwFlags
0x140005c72  mov     rcx, rax; hHeap
0x140005c75  call    cs:__imp_HeapFree
0x140005c7b  mov     qword ptr [rdi+8], 0
0x140005c83  mov     [rdi], rsi
0x140005c86  mov     eax, 1
0x140005c8b  mov     [rdi+8], rbp
0x140005c8f  lock add [rsi], eax
0x140005c92  add     rsp, 28h
0x140005c96  pop     rdi
0x140005c97  pop     rsi
0x140005c98  pop     rbp
0x140005c99  pop     rbx
0x140005c9a  retn
```
