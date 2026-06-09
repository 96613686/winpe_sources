# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800071c4`
- end: `0x180007287`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006554`
- `0x180007290`

## callees

- `0x1800071c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007228`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007228`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007261`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007261`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007219`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007253`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007219`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007253`

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
0x1800071c4  push    rbx
0x1800071c6  push    rbp
0x1800071c7  push    rsi
0x1800071c8  push    rdi
0x1800071c9  sub     rsp, 28h
0x1800071cd  mov     rbp, rdx
0x1800071d0  mov     rdi, rcx
0x1800071d3  test    rdx, rdx
0x1800071d6  jnz     short loc_180007219
0x1800071d8  mov     rcx, [rcx]
0x1800071db  test    rcx, rcx
0x1800071de  jz      short loc_180007212
0x1800071e0  or      eax, 0FFFFFFFFh
0x1800071e3  lock xadd [rcx], eax
0x1800071e7  cmp     eax, 1
0x1800071ea  jnz     short loc_180007203
0x1800071ec  mov     rbx, [rdi]
0x1800071ef  call    cs:__imp_GetProcessHeap
0x1800071f5  mov     r8, rbx; lpMem
0x1800071f8  xor     edx, edx; dwFlags
0x1800071fa  mov     rcx, rax; hHeap
0x1800071fd  call    cs:__imp_HeapFree
0x180007203  mov     qword ptr [rdi], 0
0x18000720a  mov     qword ptr [rdi+8], 0
0x180007212  mov     eax, 1
0x180007217  jmp     short loc_18000727E
0x180007219  call    cs:__imp_GetProcessHeap
0x18000721f  lea     r8, [rbp+4]; dwBytes
0x180007223  xor     edx, edx; dwFlags
0x180007225  mov     rcx, rax; hHeap
0x180007228  call    cs:__imp_HeapAlloc
0x18000722e  mov     rsi, rax
0x180007231  test    rax, rax
0x180007234  jz      short loc_18000727E
0x180007236  mov     dword ptr [rax], 0
0x18000723c  mov     rcx, [rdi]
0x18000723f  test    rcx, rcx
0x180007242  jz      short loc_18000726F
0x180007244  or      eax, 0FFFFFFFFh
0x180007247  lock xadd [rcx], eax
0x18000724b  cmp     eax, 1
0x18000724e  jnz     short loc_180007267
0x180007250  mov     rbx, [rdi]
0x180007253  call    cs:__imp_GetProcessHeap
0x180007259  mov     r8, rbx; lpMem
0x18000725c  xor     edx, edx; dwFlags
0x18000725e  mov     rcx, rax; hHeap
0x180007261  call    cs:__imp_HeapFree
0x180007267  mov     qword ptr [rdi+8], 0
0x18000726f  mov     [rdi], rsi
0x180007272  mov     eax, 1
0x180007277  mov     [rdi+8], rbp
0x18000727b  lock add [rsi], eax
0x18000727e  add     rsp, 28h
0x180007282  pop     rdi
0x180007283  pop     rsi
0x180007284  pop     rbp
0x180007285  pop     rbx
0x180007286  retn
```
