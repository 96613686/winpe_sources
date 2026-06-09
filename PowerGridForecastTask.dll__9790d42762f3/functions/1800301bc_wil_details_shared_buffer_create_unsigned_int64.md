# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800301bc`
- end: `0x18003027f`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002dec8`
- `0x180030670`

## callees

- `0x1800301bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800301f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030259`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800301f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030259`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800301e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030211`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003024b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800301e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030211`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003024b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030220`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030220`

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
0x1800301bc  push    rbx
0x1800301be  push    rbp
0x1800301bf  push    rsi
0x1800301c0  push    rdi
0x1800301c1  sub     rsp, 28h
0x1800301c5  mov     rbp, rdx
0x1800301c8  mov     rdi, rcx
0x1800301cb  test    rdx, rdx
0x1800301ce  jnz     short loc_180030211
0x1800301d0  mov     rcx, [rcx]
0x1800301d3  test    rcx, rcx
0x1800301d6  jz      short loc_18003020A
0x1800301d8  or      eax, 0FFFFFFFFh
0x1800301db  lock xadd [rcx], eax
0x1800301df  cmp     eax, 1
0x1800301e2  jnz     short loc_1800301FB
0x1800301e4  mov     rbx, [rdi]
0x1800301e7  call    cs:__imp_GetProcessHeap
0x1800301ed  mov     r8, rbx; lpMem
0x1800301f0  xor     edx, edx; dwFlags
0x1800301f2  mov     rcx, rax; hHeap
0x1800301f5  call    cs:__imp_HeapFree
0x1800301fb  mov     qword ptr [rdi], 0
0x180030202  mov     qword ptr [rdi+8], 0
0x18003020a  mov     eax, 1
0x18003020f  jmp     short loc_180030276
0x180030211  call    cs:__imp_GetProcessHeap
0x180030217  lea     r8, [rbp+4]; dwBytes
0x18003021b  xor     edx, edx; dwFlags
0x18003021d  mov     rcx, rax; hHeap
0x180030220  call    cs:__imp_HeapAlloc
0x180030226  mov     rsi, rax
0x180030229  test    rax, rax
0x18003022c  jz      short loc_180030276
0x18003022e  mov     dword ptr [rax], 0
0x180030234  mov     rcx, [rdi]
0x180030237  test    rcx, rcx
0x18003023a  jz      short loc_180030267
0x18003023c  or      eax, 0FFFFFFFFh
0x18003023f  lock xadd [rcx], eax
0x180030243  cmp     eax, 1
0x180030246  jnz     short loc_18003025F
0x180030248  mov     rbx, [rdi]
0x18003024b  call    cs:__imp_GetProcessHeap
0x180030251  mov     r8, rbx; lpMem
0x180030254  xor     edx, edx; dwFlags
0x180030256  mov     rcx, rax; hHeap
0x180030259  call    cs:__imp_HeapFree
0x18003025f  mov     qword ptr [rdi+8], 0
0x180030267  mov     [rdi], rsi
0x18003026a  mov     eax, 1
0x18003026f  mov     [rdi+8], rbp
0x180030273  lock add [rsi], eax
0x180030276  add     rsp, 28h
0x18003027a  pop     rdi
0x18003027b  pop     rsi
0x18003027c  pop     rbp
0x18003027d  pop     rbx
0x18003027e  retn
```
