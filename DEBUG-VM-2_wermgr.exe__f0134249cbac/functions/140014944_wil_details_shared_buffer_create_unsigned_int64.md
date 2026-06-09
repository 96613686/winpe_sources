# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140014944`
- end: `0x140014a07`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140013858`
- `0x140014a20`

## callees

- `0x140014944`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001496f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014999`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400149d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001496f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014999`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400149d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001497d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400149e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001497d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400149e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400149a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400149a8`

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
0x140014944  push    rbx
0x140014946  push    rbp
0x140014947  push    rsi
0x140014948  push    rdi
0x140014949  sub     rsp, 28h
0x14001494d  mov     rbp, rdx
0x140014950  mov     rdi, rcx
0x140014953  test    rdx, rdx
0x140014956  jnz     short loc_140014999
0x140014958  mov     rcx, [rcx]
0x14001495b  test    rcx, rcx
0x14001495e  jz      short loc_140014992
0x140014960  or      eax, 0FFFFFFFFh
0x140014963  lock xadd [rcx], eax
0x140014967  cmp     eax, 1
0x14001496a  jnz     short loc_140014983
0x14001496c  mov     rbx, [rdi]
0x14001496f  call    cs:__imp_GetProcessHeap
0x140014975  mov     r8, rbx; lpMem
0x140014978  xor     edx, edx; dwFlags
0x14001497a  mov     rcx, rax; hHeap
0x14001497d  call    cs:__imp_HeapFree
0x140014983  mov     qword ptr [rdi], 0
0x14001498a  mov     qword ptr [rdi+8], 0
0x140014992  mov     eax, 1
0x140014997  jmp     short loc_1400149FE
0x140014999  call    cs:__imp_GetProcessHeap
0x14001499f  lea     r8, [rbp+4]; dwBytes
0x1400149a3  xor     edx, edx; dwFlags
0x1400149a5  mov     rcx, rax; hHeap
0x1400149a8  call    cs:__imp_HeapAlloc
0x1400149ae  mov     rsi, rax
0x1400149b1  test    rax, rax
0x1400149b4  jz      short loc_1400149FE
0x1400149b6  mov     dword ptr [rax], 0
0x1400149bc  mov     rcx, [rdi]
0x1400149bf  test    rcx, rcx
0x1400149c2  jz      short loc_1400149EF
0x1400149c4  or      eax, 0FFFFFFFFh
0x1400149c7  lock xadd [rcx], eax
0x1400149cb  cmp     eax, 1
0x1400149ce  jnz     short loc_1400149E7
0x1400149d0  mov     rbx, [rdi]
0x1400149d3  call    cs:__imp_GetProcessHeap
0x1400149d9  mov     r8, rbx; lpMem
0x1400149dc  xor     edx, edx; dwFlags
0x1400149de  mov     rcx, rax; hHeap
0x1400149e1  call    cs:__imp_HeapFree
0x1400149e7  mov     qword ptr [rdi+8], 0
0x1400149ef  mov     [rdi], rsi
0x1400149f2  mov     eax, 1
0x1400149f7  mov     [rdi+8], rbp
0x1400149fb  lock add [rsi], eax
0x1400149fe  add     rsp, 28h
0x140014a02  pop     rdi
0x140014a03  pop     rsi
0x140014a04  pop     rbp
0x140014a05  pop     rbx
0x140014a06  retn
```
