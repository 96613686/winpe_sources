# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180019f5c`
- end: `0x18001a044`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800193fc`
- `0x18001a050`

## callees

- `0x180019f5c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019fd2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019fd2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019f87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a003`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019f87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a003`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019f9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a017`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019f9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a017`

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
0x180019f5c  push    rbx
0x180019f5e  push    rbp
0x180019f5f  push    rsi
0x180019f60  push    rdi
0x180019f61  sub     rsp, 28h
0x180019f65  mov     rbp, rdx
0x180019f68  mov     rdi, rcx
0x180019f6b  test    rdx, rdx
0x180019f6e  jnz     short loc_180019FBD
0x180019f70  mov     rcx, [rcx]
0x180019f73  test    rcx, rcx
0x180019f76  jz      short loc_180019FB6
0x180019f78  or      eax, 0FFFFFFFFh
0x180019f7b  lock xadd [rcx], eax
0x180019f7f  cmp     eax, 1
0x180019f82  jnz     short loc_180019FA7
0x180019f84  mov     rbx, [rdi]
0x180019f87  call    cs:__imp_GetProcessHeap
0x180019f8e  nop     dword ptr [rax+rax+00h]
0x180019f93  mov     r8, rbx; lpMem
0x180019f96  xor     edx, edx; dwFlags
0x180019f98  mov     rcx, rax; hHeap
0x180019f9b  call    cs:__imp_HeapFree
0x180019fa2  nop     dword ptr [rax+rax+00h]
0x180019fa7  mov     qword ptr [rdi], 0
0x180019fae  mov     qword ptr [rdi+8], 0
0x180019fb6  mov     eax, 1
0x180019fbb  jmp     short loc_18001A03A
0x180019fbd  call    cs:__imp_GetProcessHeap
0x180019fc4  nop     dword ptr [rax+rax+00h]
0x180019fc9  lea     r8, [rbp+4]; dwBytes
0x180019fcd  xor     edx, edx; dwFlags
0x180019fcf  mov     rcx, rax; hHeap
0x180019fd2  call    cs:__imp_HeapAlloc
0x180019fd9  nop     dword ptr [rax+rax+00h]
0x180019fde  mov     rsi, rax
0x180019fe1  test    rax, rax
0x180019fe4  jz      short loc_18001A03A
0x180019fe6  mov     dword ptr [rax], 0
0x180019fec  mov     rcx, [rdi]
0x180019fef  test    rcx, rcx
0x180019ff2  jz      short loc_18001A02B
0x180019ff4  or      eax, 0FFFFFFFFh
0x180019ff7  lock xadd [rcx], eax
0x180019ffb  cmp     eax, 1
0x180019ffe  jnz     short loc_18001A023
0x18001a000  mov     rbx, [rdi]
0x18001a003  call    cs:__imp_GetProcessHeap
0x18001a00a  nop     dword ptr [rax+rax+00h]
0x18001a00f  mov     r8, rbx; lpMem
0x18001a012  xor     edx, edx; dwFlags
0x18001a014  mov     rcx, rax; hHeap
0x18001a017  call    cs:__imp_HeapFree
0x18001a01e  nop     dword ptr [rax+rax+00h]
0x18001a023  mov     qword ptr [rdi+8], 0
0x18001a02b  mov     [rdi], rsi
0x18001a02e  mov     eax, 1
0x18001a033  mov     [rdi+8], rbp
0x18001a037  lock add [rsi], eax
0x18001a03a  add     rsp, 28h
0x18001a03e  pop     rdi
0x18001a03f  pop     rsi
0x18001a040  pop     rbp
0x18001a041  pop     rbx
0x18001a042  retn
```
