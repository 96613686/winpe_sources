# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800069a8`
- end: `0x180006a6b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005de4`
- `0x180006e10`

## callees

- `0x1800069a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006a0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a45`

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
0x1800069a8  push    rbx
0x1800069aa  push    rbp
0x1800069ab  push    rsi
0x1800069ac  push    rdi
0x1800069ad  sub     rsp, 28h
0x1800069b1  mov     rbp, rdx
0x1800069b4  mov     rdi, rcx
0x1800069b7  test    rdx, rdx
0x1800069ba  jnz     short loc_1800069FD
0x1800069bc  mov     rcx, [rcx]
0x1800069bf  test    rcx, rcx
0x1800069c2  jz      short loc_1800069F6
0x1800069c4  or      eax, 0FFFFFFFFh
0x1800069c7  lock xadd [rcx], eax
0x1800069cb  cmp     eax, 1
0x1800069ce  jnz     short loc_1800069E7
0x1800069d0  mov     rbx, [rdi]
0x1800069d3  call    cs:__imp_GetProcessHeap
0x1800069d9  mov     r8, rbx; lpMem
0x1800069dc  xor     edx, edx; dwFlags
0x1800069de  mov     rcx, rax; hHeap
0x1800069e1  call    cs:__imp_HeapFree
0x1800069e7  mov     qword ptr [rdi], 0
0x1800069ee  mov     qword ptr [rdi+8], 0
0x1800069f6  mov     eax, 1
0x1800069fb  jmp     short loc_180006A62
0x1800069fd  call    cs:__imp_GetProcessHeap
0x180006a03  lea     r8, [rbp+4]; dwBytes
0x180006a07  xor     edx, edx; dwFlags
0x180006a09  mov     rcx, rax; hHeap
0x180006a0c  call    cs:__imp_HeapAlloc
0x180006a12  mov     rsi, rax
0x180006a15  test    rax, rax
0x180006a18  jz      short loc_180006A62
0x180006a1a  mov     dword ptr [rax], 0
0x180006a20  mov     rcx, [rdi]
0x180006a23  test    rcx, rcx
0x180006a26  jz      short loc_180006A53
0x180006a28  or      eax, 0FFFFFFFFh
0x180006a2b  lock xadd [rcx], eax
0x180006a2f  cmp     eax, 1
0x180006a32  jnz     short loc_180006A4B
0x180006a34  mov     rbx, [rdi]
0x180006a37  call    cs:__imp_GetProcessHeap
0x180006a3d  mov     r8, rbx; lpMem
0x180006a40  xor     edx, edx; dwFlags
0x180006a42  mov     rcx, rax; hHeap
0x180006a45  call    cs:__imp_HeapFree
0x180006a4b  mov     qword ptr [rdi+8], 0
0x180006a53  mov     [rdi], rsi
0x180006a56  mov     eax, 1
0x180006a5b  mov     [rdi+8], rbp
0x180006a5f  lock add [rsi], eax
0x180006a62  add     rsp, 28h
0x180006a66  pop     rdi
0x180006a67  pop     rsi
0x180006a68  pop     rbp
0x180006a69  pop     rbx
0x180006a6a  retn
```
