# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000a950`
- end: `0x18000aa13`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009a30`
- `0x18000aa20`

## callees

- `0x18000a950`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a9b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a9b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a989`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a9ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a989`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a9ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a97b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a97b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a9df`

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
0x18000a950  push    rbx
0x18000a952  push    rbp
0x18000a953  push    rsi
0x18000a954  push    rdi
0x18000a955  sub     rsp, 28h
0x18000a959  mov     rbp, rdx
0x18000a95c  mov     rdi, rcx
0x18000a95f  test    rdx, rdx
0x18000a962  jnz     short loc_18000A9A5
0x18000a964  mov     rcx, [rcx]
0x18000a967  test    rcx, rcx
0x18000a96a  jz      short loc_18000A99E
0x18000a96c  or      eax, 0FFFFFFFFh
0x18000a96f  lock xadd [rcx], eax
0x18000a973  cmp     eax, 1
0x18000a976  jnz     short loc_18000A98F
0x18000a978  mov     rbx, [rdi]
0x18000a97b  call    cs:__imp_GetProcessHeap
0x18000a981  mov     r8, rbx; lpMem
0x18000a984  xor     edx, edx; dwFlags
0x18000a986  mov     rcx, rax; hHeap
0x18000a989  call    cs:__imp_HeapFree
0x18000a98f  mov     qword ptr [rdi], 0
0x18000a996  mov     qword ptr [rdi+8], 0
0x18000a99e  mov     eax, 1
0x18000a9a3  jmp     short loc_18000AA0A
0x18000a9a5  call    cs:__imp_GetProcessHeap
0x18000a9ab  lea     r8, [rbp+4]; dwBytes
0x18000a9af  xor     edx, edx; dwFlags
0x18000a9b1  mov     rcx, rax; hHeap
0x18000a9b4  call    cs:__imp_HeapAlloc
0x18000a9ba  mov     rsi, rax
0x18000a9bd  test    rax, rax
0x18000a9c0  jz      short loc_18000AA0A
0x18000a9c2  mov     dword ptr [rax], 0
0x18000a9c8  mov     rcx, [rdi]
0x18000a9cb  test    rcx, rcx
0x18000a9ce  jz      short loc_18000A9FB
0x18000a9d0  or      eax, 0FFFFFFFFh
0x18000a9d3  lock xadd [rcx], eax
0x18000a9d7  cmp     eax, 1
0x18000a9da  jnz     short loc_18000A9F3
0x18000a9dc  mov     rbx, [rdi]
0x18000a9df  call    cs:__imp_GetProcessHeap
0x18000a9e5  mov     r8, rbx; lpMem
0x18000a9e8  xor     edx, edx; dwFlags
0x18000a9ea  mov     rcx, rax; hHeap
0x18000a9ed  call    cs:__imp_HeapFree
0x18000a9f3  mov     qword ptr [rdi+8], 0
0x18000a9fb  mov     [rdi], rsi
0x18000a9fe  mov     eax, 1
0x18000aa03  mov     [rdi+8], rbp
0x18000aa07  lock add [rsi], eax
0x18000aa0a  add     rsp, 28h
0x18000aa0e  pop     rdi
0x18000aa0f  pop     rsi
0x18000aa10  pop     rbp
0x18000aa11  pop     rbx
0x18000aa12  retn
```
