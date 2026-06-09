# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180008474`
- end: `0x180008537`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800071c8`
- `0x180008630`

## callees

- `0x180008474`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008511`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800084d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800084d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000849f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008503`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000849f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008503`

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
0x180008474  push    rbx
0x180008476  push    rbp
0x180008477  push    rsi
0x180008478  push    rdi
0x180008479  sub     rsp, 28h
0x18000847d  mov     rbp, rdx
0x180008480  mov     rdi, rcx
0x180008483  test    rdx, rdx
0x180008486  jnz     short loc_1800084C9
0x180008488  mov     rcx, [rcx]
0x18000848b  test    rcx, rcx
0x18000848e  jz      short loc_1800084C2
0x180008490  or      eax, 0FFFFFFFFh
0x180008493  lock xadd [rcx], eax
0x180008497  cmp     eax, 1
0x18000849a  jnz     short loc_1800084B3
0x18000849c  mov     rbx, [rdi]
0x18000849f  call    cs:__imp_GetProcessHeap
0x1800084a5  mov     r8, rbx; lpMem
0x1800084a8  xor     edx, edx; dwFlags
0x1800084aa  mov     rcx, rax; hHeap
0x1800084ad  call    cs:__imp_HeapFree
0x1800084b3  mov     qword ptr [rdi], 0
0x1800084ba  mov     qword ptr [rdi+8], 0
0x1800084c2  mov     eax, 1
0x1800084c7  jmp     short loc_18000852E
0x1800084c9  call    cs:__imp_GetProcessHeap
0x1800084cf  lea     r8, [rbp+4]; dwBytes
0x1800084d3  xor     edx, edx; dwFlags
0x1800084d5  mov     rcx, rax; hHeap
0x1800084d8  call    cs:__imp_HeapAlloc
0x1800084de  mov     rsi, rax
0x1800084e1  test    rax, rax
0x1800084e4  jz      short loc_18000852E
0x1800084e6  mov     dword ptr [rax], 0
0x1800084ec  mov     rcx, [rdi]
0x1800084ef  test    rcx, rcx
0x1800084f2  jz      short loc_18000851F
0x1800084f4  or      eax, 0FFFFFFFFh
0x1800084f7  lock xadd [rcx], eax
0x1800084fb  cmp     eax, 1
0x1800084fe  jnz     short loc_180008517
0x180008500  mov     rbx, [rdi]
0x180008503  call    cs:__imp_GetProcessHeap
0x180008509  mov     r8, rbx; lpMem
0x18000850c  xor     edx, edx; dwFlags
0x18000850e  mov     rcx, rax; hHeap
0x180008511  call    cs:__imp_HeapFree
0x180008517  mov     qword ptr [rdi+8], 0
0x18000851f  mov     [rdi], rsi
0x180008522  mov     eax, 1
0x180008527  mov     [rdi+8], rbp
0x18000852b  lock add [rsi], eax
0x18000852e  add     rsp, 28h
0x180008532  pop     rdi
0x180008533  pop     rsi
0x180008534  pop     rbp
0x180008535  pop     rbx
0x180008536  retn
```
