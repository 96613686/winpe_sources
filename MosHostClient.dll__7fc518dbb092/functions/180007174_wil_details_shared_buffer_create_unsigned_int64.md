# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007174`
- end: `0x180007237`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006524`
- `0x180007240`

## callees

- `0x180007174`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007211`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007211`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000719f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007203`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000719f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007203`

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
0x180007174  push    rbx
0x180007176  push    rbp
0x180007177  push    rsi
0x180007178  push    rdi
0x180007179  sub     rsp, 28h
0x18000717d  mov     rbp, rdx
0x180007180  mov     rdi, rcx
0x180007183  test    rdx, rdx
0x180007186  jnz     short loc_1800071C9
0x180007188  mov     rcx, [rcx]
0x18000718b  test    rcx, rcx
0x18000718e  jz      short loc_1800071C2
0x180007190  or      eax, 0FFFFFFFFh
0x180007193  lock xadd [rcx], eax
0x180007197  cmp     eax, 1
0x18000719a  jnz     short loc_1800071B3
0x18000719c  mov     rbx, [rdi]
0x18000719f  call    cs:__imp_GetProcessHeap
0x1800071a5  mov     r8, rbx; lpMem
0x1800071a8  xor     edx, edx; dwFlags
0x1800071aa  mov     rcx, rax; hHeap
0x1800071ad  call    cs:__imp_HeapFree
0x1800071b3  mov     qword ptr [rdi], 0
0x1800071ba  mov     qword ptr [rdi+8], 0
0x1800071c2  mov     eax, 1
0x1800071c7  jmp     short loc_18000722E
0x1800071c9  call    cs:__imp_GetProcessHeap
0x1800071cf  lea     r8, [rbp+4]; dwBytes
0x1800071d3  xor     edx, edx; dwFlags
0x1800071d5  mov     rcx, rax; hHeap
0x1800071d8  call    cs:__imp_HeapAlloc
0x1800071de  mov     rsi, rax
0x1800071e1  test    rax, rax
0x1800071e4  jz      short loc_18000722E
0x1800071e6  mov     dword ptr [rax], 0
0x1800071ec  mov     rcx, [rdi]
0x1800071ef  test    rcx, rcx
0x1800071f2  jz      short loc_18000721F
0x1800071f4  or      eax, 0FFFFFFFFh
0x1800071f7  lock xadd [rcx], eax
0x1800071fb  cmp     eax, 1
0x1800071fe  jnz     short loc_180007217
0x180007200  mov     rbx, [rdi]
0x180007203  call    cs:__imp_GetProcessHeap
0x180007209  mov     r8, rbx; lpMem
0x18000720c  xor     edx, edx; dwFlags
0x18000720e  mov     rcx, rax; hHeap
0x180007211  call    cs:__imp_HeapFree
0x180007217  mov     qword ptr [rdi+8], 0
0x18000721f  mov     [rdi], rsi
0x180007222  mov     eax, 1
0x180007227  mov     [rdi+8], rbp
0x18000722b  lock add [rsi], eax
0x18000722e  add     rsp, 28h
0x180007232  pop     rdi
0x180007233  pop     rsi
0x180007234  pop     rbp
0x180007235  pop     rbx
0x180007236  retn
```
