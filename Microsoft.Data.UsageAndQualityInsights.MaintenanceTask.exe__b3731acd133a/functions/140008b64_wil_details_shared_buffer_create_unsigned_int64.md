# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140008b64`
- end: `0x140008c27`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400076f8`
- `0x140008d20`

## callees

- `0x140008b64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008bb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008bf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008bb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008bf3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008bc8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008bc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c01`

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
0x140008b64  push    rbx
0x140008b66  push    rbp
0x140008b67  push    rsi
0x140008b68  push    rdi
0x140008b69  sub     rsp, 28h
0x140008b6d  mov     rbp, rdx
0x140008b70  mov     rdi, rcx
0x140008b73  test    rdx, rdx
0x140008b76  jnz     short loc_140008BB9
0x140008b78  mov     rcx, [rcx]
0x140008b7b  test    rcx, rcx
0x140008b7e  jz      short loc_140008BB2
0x140008b80  or      eax, 0FFFFFFFFh
0x140008b83  lock xadd [rcx], eax
0x140008b87  cmp     eax, 1
0x140008b8a  jnz     short loc_140008BA3
0x140008b8c  mov     rbx, [rdi]
0x140008b8f  call    cs:__imp_GetProcessHeap
0x140008b95  mov     r8, rbx; lpMem
0x140008b98  xor     edx, edx; dwFlags
0x140008b9a  mov     rcx, rax; hHeap
0x140008b9d  call    cs:__imp_HeapFree
0x140008ba3  mov     qword ptr [rdi], 0
0x140008baa  mov     qword ptr [rdi+8], 0
0x140008bb2  mov     eax, 1
0x140008bb7  jmp     short loc_140008C1E
0x140008bb9  call    cs:__imp_GetProcessHeap
0x140008bbf  lea     r8, [rbp+4]; dwBytes
0x140008bc3  xor     edx, edx; dwFlags
0x140008bc5  mov     rcx, rax; hHeap
0x140008bc8  call    cs:__imp_HeapAlloc
0x140008bce  mov     rsi, rax
0x140008bd1  test    rax, rax
0x140008bd4  jz      short loc_140008C1E
0x140008bd6  mov     dword ptr [rax], 0
0x140008bdc  mov     rcx, [rdi]
0x140008bdf  test    rcx, rcx
0x140008be2  jz      short loc_140008C0F
0x140008be4  or      eax, 0FFFFFFFFh
0x140008be7  lock xadd [rcx], eax
0x140008beb  cmp     eax, 1
0x140008bee  jnz     short loc_140008C07
0x140008bf0  mov     rbx, [rdi]
0x140008bf3  call    cs:__imp_GetProcessHeap
0x140008bf9  mov     r8, rbx; lpMem
0x140008bfc  xor     edx, edx; dwFlags
0x140008bfe  mov     rcx, rax; hHeap
0x140008c01  call    cs:__imp_HeapFree
0x140008c07  mov     qword ptr [rdi+8], 0
0x140008c0f  mov     [rdi], rsi
0x140008c12  mov     eax, 1
0x140008c17  mov     [rdi+8], rbp
0x140008c1b  lock add [rsi], eax
0x140008c1e  add     rsp, 28h
0x140008c22  pop     rdi
0x140008c23  pop     rsi
0x140008c24  pop     rbp
0x140008c25  pop     rbx
0x140008c26  retn
```
