# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180006cd8`
- end: `0x180006d9b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800059c4`
- `0x180007150`

## callees

- `0x180006cd8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006d3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006d3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d75`

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
0x180006cd8  push    rbx
0x180006cda  push    rbp
0x180006cdb  push    rsi
0x180006cdc  push    rdi
0x180006cdd  sub     rsp, 28h
0x180006ce1  mov     rbp, rdx
0x180006ce4  mov     rdi, rcx
0x180006ce7  test    rdx, rdx
0x180006cea  jnz     short loc_180006D2D
0x180006cec  mov     rcx, [rcx]
0x180006cef  test    rcx, rcx
0x180006cf2  jz      short loc_180006D26
0x180006cf4  or      eax, 0FFFFFFFFh
0x180006cf7  lock xadd [rcx], eax
0x180006cfb  cmp     eax, 1
0x180006cfe  jnz     short loc_180006D17
0x180006d00  mov     rbx, [rdi]
0x180006d03  call    cs:__imp_GetProcessHeap
0x180006d09  mov     r8, rbx; lpMem
0x180006d0c  xor     edx, edx; dwFlags
0x180006d0e  mov     rcx, rax; hHeap
0x180006d11  call    cs:__imp_HeapFree
0x180006d17  mov     qword ptr [rdi], 0
0x180006d1e  mov     qword ptr [rdi+8], 0
0x180006d26  mov     eax, 1
0x180006d2b  jmp     short loc_180006D92
0x180006d2d  call    cs:__imp_GetProcessHeap
0x180006d33  lea     r8, [rbp+4]; dwBytes
0x180006d37  xor     edx, edx; dwFlags
0x180006d39  mov     rcx, rax; hHeap
0x180006d3c  call    cs:__imp_HeapAlloc
0x180006d42  mov     rsi, rax
0x180006d45  test    rax, rax
0x180006d48  jz      short loc_180006D92
0x180006d4a  mov     dword ptr [rax], 0
0x180006d50  mov     rcx, [rdi]
0x180006d53  test    rcx, rcx
0x180006d56  jz      short loc_180006D83
0x180006d58  or      eax, 0FFFFFFFFh
0x180006d5b  lock xadd [rcx], eax
0x180006d5f  cmp     eax, 1
0x180006d62  jnz     short loc_180006D7B
0x180006d64  mov     rbx, [rdi]
0x180006d67  call    cs:__imp_GetProcessHeap
0x180006d6d  mov     r8, rbx; lpMem
0x180006d70  xor     edx, edx; dwFlags
0x180006d72  mov     rcx, rax; hHeap
0x180006d75  call    cs:__imp_HeapFree
0x180006d7b  mov     qword ptr [rdi+8], 0
0x180006d83  mov     [rdi], rsi
0x180006d86  mov     eax, 1
0x180006d8b  mov     [rdi+8], rbp
0x180006d8f  lock add [rsi], eax
0x180006d92  add     rsp, 28h
0x180006d96  pop     rdi
0x180006d97  pop     rsi
0x180006d98  pop     rbp
0x180006d99  pop     rbx
0x180006d9a  retn
```
