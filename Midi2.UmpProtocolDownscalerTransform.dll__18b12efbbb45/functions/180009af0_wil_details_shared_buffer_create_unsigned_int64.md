# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180009af0`
- end: `0x180009bb3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008bd0`
- `0x180009bc0`

## callees

- `0x180009af0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b8d`

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
0x180009af0  push    rbx
0x180009af2  push    rbp
0x180009af3  push    rsi
0x180009af4  push    rdi
0x180009af5  sub     rsp, 28h
0x180009af9  mov     rbp, rdx
0x180009afc  mov     rdi, rcx
0x180009aff  test    rdx, rdx
0x180009b02  jnz     short loc_180009B45
0x180009b04  mov     rcx, [rcx]
0x180009b07  test    rcx, rcx
0x180009b0a  jz      short loc_180009B3E
0x180009b0c  or      eax, 0FFFFFFFFh
0x180009b0f  lock xadd [rcx], eax
0x180009b13  cmp     eax, 1
0x180009b16  jnz     short loc_180009B2F
0x180009b18  mov     rbx, [rdi]
0x180009b1b  call    cs:__imp_GetProcessHeap
0x180009b21  mov     r8, rbx; lpMem
0x180009b24  xor     edx, edx; dwFlags
0x180009b26  mov     rcx, rax; hHeap
0x180009b29  call    cs:__imp_HeapFree
0x180009b2f  mov     qword ptr [rdi], 0
0x180009b36  mov     qword ptr [rdi+8], 0
0x180009b3e  mov     eax, 1
0x180009b43  jmp     short loc_180009BAA
0x180009b45  call    cs:__imp_GetProcessHeap
0x180009b4b  lea     r8, [rbp+4]; dwBytes
0x180009b4f  xor     edx, edx; dwFlags
0x180009b51  mov     rcx, rax; hHeap
0x180009b54  call    cs:__imp_HeapAlloc
0x180009b5a  mov     rsi, rax
0x180009b5d  test    rax, rax
0x180009b60  jz      short loc_180009BAA
0x180009b62  mov     dword ptr [rax], 0
0x180009b68  mov     rcx, [rdi]
0x180009b6b  test    rcx, rcx
0x180009b6e  jz      short loc_180009B9B
0x180009b70  or      eax, 0FFFFFFFFh
0x180009b73  lock xadd [rcx], eax
0x180009b77  cmp     eax, 1
0x180009b7a  jnz     short loc_180009B93
0x180009b7c  mov     rbx, [rdi]
0x180009b7f  call    cs:__imp_GetProcessHeap
0x180009b85  mov     r8, rbx; lpMem
0x180009b88  xor     edx, edx; dwFlags
0x180009b8a  mov     rcx, rax; hHeap
0x180009b8d  call    cs:__imp_HeapFree
0x180009b93  mov     qword ptr [rdi+8], 0
0x180009b9b  mov     [rdi], rsi
0x180009b9e  mov     eax, 1
0x180009ba3  mov     [rdi+8], rbp
0x180009ba7  lock add [rsi], eax
0x180009baa  add     rsp, 28h
0x180009bae  pop     rdi
0x180009baf  pop     rsi
0x180009bb0  pop     rbp
0x180009bb1  pop     rbx
0x180009bb2  retn
```
