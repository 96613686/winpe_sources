# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180005718`
- end: `0x1800057db`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004b90`
- `0x1800057f0`

## callees

- `0x180005718`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000577c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000577c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005751`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005751`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005743`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000576d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005743`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000576d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a7`

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
0x180005718  push    rbx
0x18000571a  push    rbp
0x18000571b  push    rsi
0x18000571c  push    rdi
0x18000571d  sub     rsp, 28h
0x180005721  mov     rbp, rdx
0x180005724  mov     rdi, rcx
0x180005727  test    rdx, rdx
0x18000572a  jnz     short loc_18000576D
0x18000572c  mov     rcx, [rcx]
0x18000572f  test    rcx, rcx
0x180005732  jz      short loc_180005766
0x180005734  or      eax, 0FFFFFFFFh
0x180005737  lock xadd [rcx], eax
0x18000573b  cmp     eax, 1
0x18000573e  jnz     short loc_180005757
0x180005740  mov     rbx, [rdi]
0x180005743  call    cs:__imp_GetProcessHeap
0x180005749  mov     r8, rbx; lpMem
0x18000574c  xor     edx, edx; dwFlags
0x18000574e  mov     rcx, rax; hHeap
0x180005751  call    cs:__imp_HeapFree
0x180005757  mov     qword ptr [rdi], 0
0x18000575e  mov     qword ptr [rdi+8], 0
0x180005766  mov     eax, 1
0x18000576b  jmp     short loc_1800057D2
0x18000576d  call    cs:__imp_GetProcessHeap
0x180005773  lea     r8, [rbp+4]; dwBytes
0x180005777  xor     edx, edx; dwFlags
0x180005779  mov     rcx, rax; hHeap
0x18000577c  call    cs:__imp_HeapAlloc
0x180005782  mov     rsi, rax
0x180005785  test    rax, rax
0x180005788  jz      short loc_1800057D2
0x18000578a  mov     dword ptr [rax], 0
0x180005790  mov     rcx, [rdi]
0x180005793  test    rcx, rcx
0x180005796  jz      short loc_1800057C3
0x180005798  or      eax, 0FFFFFFFFh
0x18000579b  lock xadd [rcx], eax
0x18000579f  cmp     eax, 1
0x1800057a2  jnz     short loc_1800057BB
0x1800057a4  mov     rbx, [rdi]
0x1800057a7  call    cs:__imp_GetProcessHeap
0x1800057ad  mov     r8, rbx; lpMem
0x1800057b0  xor     edx, edx; dwFlags
0x1800057b2  mov     rcx, rax; hHeap
0x1800057b5  call    cs:__imp_HeapFree
0x1800057bb  mov     qword ptr [rdi+8], 0
0x1800057c3  mov     [rdi], rsi
0x1800057c6  mov     eax, 1
0x1800057cb  mov     [rdi+8], rbp
0x1800057cf  lock add [rsi], eax
0x1800057d2  add     rsp, 28h
0x1800057d6  pop     rdi
0x1800057d7  pop     rsi
0x1800057d8  pop     rbp
0x1800057d9  pop     rbx
0x1800057da  retn
```
