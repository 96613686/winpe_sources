# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007198`
- end: `0x18000725b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800064d0`
- `0x180007270`

## callees

- `0x180007198`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007227`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007227`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007235`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007235`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071fc`

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
0x180007198  push    rbx
0x18000719a  push    rbp
0x18000719b  push    rsi
0x18000719c  push    rdi
0x18000719d  sub     rsp, 28h
0x1800071a1  mov     rbp, rdx
0x1800071a4  mov     rdi, rcx
0x1800071a7  test    rdx, rdx
0x1800071aa  jnz     short loc_1800071ED
0x1800071ac  mov     rcx, [rcx]
0x1800071af  test    rcx, rcx
0x1800071b2  jz      short loc_1800071E6
0x1800071b4  or      eax, 0FFFFFFFFh
0x1800071b7  lock xadd [rcx], eax
0x1800071bb  cmp     eax, 1
0x1800071be  jnz     short loc_1800071D7
0x1800071c0  mov     rbx, [rdi]
0x1800071c3  call    cs:__imp_GetProcessHeap
0x1800071c9  mov     r8, rbx; lpMem
0x1800071cc  xor     edx, edx; dwFlags
0x1800071ce  mov     rcx, rax; hHeap
0x1800071d1  call    cs:__imp_HeapFree
0x1800071d7  mov     qword ptr [rdi], 0
0x1800071de  mov     qword ptr [rdi+8], 0
0x1800071e6  mov     eax, 1
0x1800071eb  jmp     short loc_180007252
0x1800071ed  call    cs:__imp_GetProcessHeap
0x1800071f3  lea     r8, [rbp+4]; dwBytes
0x1800071f7  xor     edx, edx; dwFlags
0x1800071f9  mov     rcx, rax; hHeap
0x1800071fc  call    cs:__imp_HeapAlloc
0x180007202  mov     rsi, rax
0x180007205  test    rax, rax
0x180007208  jz      short loc_180007252
0x18000720a  mov     dword ptr [rax], 0
0x180007210  mov     rcx, [rdi]
0x180007213  test    rcx, rcx
0x180007216  jz      short loc_180007243
0x180007218  or      eax, 0FFFFFFFFh
0x18000721b  lock xadd [rcx], eax
0x18000721f  cmp     eax, 1
0x180007222  jnz     short loc_18000723B
0x180007224  mov     rbx, [rdi]
0x180007227  call    cs:__imp_GetProcessHeap
0x18000722d  mov     r8, rbx; lpMem
0x180007230  xor     edx, edx; dwFlags
0x180007232  mov     rcx, rax; hHeap
0x180007235  call    cs:__imp_HeapFree
0x18000723b  mov     qword ptr [rdi+8], 0
0x180007243  mov     [rdi], rsi
0x180007246  mov     eax, 1
0x18000724b  mov     [rdi+8], rbp
0x18000724f  lock add [rsi], eax
0x180007252  add     rsp, 28h
0x180007256  pop     rdi
0x180007257  pop     rsi
0x180007258  pop     rbp
0x180007259  pop     rbx
0x18000725a  retn
```
