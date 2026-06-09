# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140009414`
- end: `0x1400094d7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400080d4`
- `0x1400094e0`

## callees

- `0x140009414`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009478`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009478`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000943f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400094a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000943f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400094a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000944d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400094b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000944d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400094b1`

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
0x140009414  push    rbx
0x140009416  push    rbp
0x140009417  push    rsi
0x140009418  push    rdi
0x140009419  sub     rsp, 28h
0x14000941d  mov     rbp, rdx
0x140009420  mov     rdi, rcx
0x140009423  test    rdx, rdx
0x140009426  jnz     short loc_140009469
0x140009428  mov     rcx, [rcx]
0x14000942b  test    rcx, rcx
0x14000942e  jz      short loc_140009462
0x140009430  or      eax, 0FFFFFFFFh
0x140009433  lock xadd [rcx], eax
0x140009437  cmp     eax, 1
0x14000943a  jnz     short loc_140009453
0x14000943c  mov     rbx, [rdi]
0x14000943f  call    cs:__imp_GetProcessHeap
0x140009445  mov     r8, rbx; lpMem
0x140009448  xor     edx, edx; dwFlags
0x14000944a  mov     rcx, rax; hHeap
0x14000944d  call    cs:__imp_HeapFree
0x140009453  mov     qword ptr [rdi], 0
0x14000945a  mov     qword ptr [rdi+8], 0
0x140009462  mov     eax, 1
0x140009467  jmp     short loc_1400094CE
0x140009469  call    cs:__imp_GetProcessHeap
0x14000946f  lea     r8, [rbp+4]; dwBytes
0x140009473  xor     edx, edx; dwFlags
0x140009475  mov     rcx, rax; hHeap
0x140009478  call    cs:__imp_HeapAlloc
0x14000947e  mov     rsi, rax
0x140009481  test    rax, rax
0x140009484  jz      short loc_1400094CE
0x140009486  mov     dword ptr [rax], 0
0x14000948c  mov     rcx, [rdi]
0x14000948f  test    rcx, rcx
0x140009492  jz      short loc_1400094BF
0x140009494  or      eax, 0FFFFFFFFh
0x140009497  lock xadd [rcx], eax
0x14000949b  cmp     eax, 1
0x14000949e  jnz     short loc_1400094B7
0x1400094a0  mov     rbx, [rdi]
0x1400094a3  call    cs:__imp_GetProcessHeap
0x1400094a9  mov     r8, rbx; lpMem
0x1400094ac  xor     edx, edx; dwFlags
0x1400094ae  mov     rcx, rax; hHeap
0x1400094b1  call    cs:__imp_HeapFree
0x1400094b7  mov     qword ptr [rdi+8], 0
0x1400094bf  mov     [rdi], rsi
0x1400094c2  mov     eax, 1
0x1400094c7  mov     [rdi+8], rbp
0x1400094cb  lock add [rsi], eax
0x1400094ce  add     rsp, 28h
0x1400094d2  pop     rdi
0x1400094d3  pop     rsi
0x1400094d4  pop     rbp
0x1400094d5  pop     rbx
0x1400094d6  retn
```
