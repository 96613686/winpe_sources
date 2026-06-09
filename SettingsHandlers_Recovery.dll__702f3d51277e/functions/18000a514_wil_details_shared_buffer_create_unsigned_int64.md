# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000a514`
- end: `0x18000a5d7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009038`
- `0x18000a6c0`

## callees

- `0x18000a514`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a53f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a569`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a53f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a569`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a54d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a54d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a578`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a578`

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
0x18000a514  push    rbx
0x18000a516  push    rbp
0x18000a517  push    rsi
0x18000a518  push    rdi
0x18000a519  sub     rsp, 28h
0x18000a51d  mov     rbp, rdx
0x18000a520  mov     rdi, rcx
0x18000a523  test    rdx, rdx
0x18000a526  jnz     short loc_18000A569
0x18000a528  mov     rcx, [rcx]
0x18000a52b  test    rcx, rcx
0x18000a52e  jz      short loc_18000A562
0x18000a530  or      eax, 0FFFFFFFFh
0x18000a533  lock xadd [rcx], eax
0x18000a537  cmp     eax, 1
0x18000a53a  jnz     short loc_18000A553
0x18000a53c  mov     rbx, [rdi]
0x18000a53f  call    cs:__imp_GetProcessHeap
0x18000a545  mov     r8, rbx; lpMem
0x18000a548  xor     edx, edx; dwFlags
0x18000a54a  mov     rcx, rax; hHeap
0x18000a54d  call    cs:__imp_HeapFree
0x18000a553  mov     qword ptr [rdi], 0
0x18000a55a  mov     qword ptr [rdi+8], 0
0x18000a562  mov     eax, 1
0x18000a567  jmp     short loc_18000A5CE
0x18000a569  call    cs:__imp_GetProcessHeap
0x18000a56f  lea     r8, [rbp+4]; dwBytes
0x18000a573  xor     edx, edx; dwFlags
0x18000a575  mov     rcx, rax; hHeap
0x18000a578  call    cs:__imp_HeapAlloc
0x18000a57e  mov     rsi, rax
0x18000a581  test    rax, rax
0x18000a584  jz      short loc_18000A5CE
0x18000a586  mov     dword ptr [rax], 0
0x18000a58c  mov     rcx, [rdi]
0x18000a58f  test    rcx, rcx
0x18000a592  jz      short loc_18000A5BF
0x18000a594  or      eax, 0FFFFFFFFh
0x18000a597  lock xadd [rcx], eax
0x18000a59b  cmp     eax, 1
0x18000a59e  jnz     short loc_18000A5B7
0x18000a5a0  mov     rbx, [rdi]
0x18000a5a3  call    cs:__imp_GetProcessHeap
0x18000a5a9  mov     r8, rbx; lpMem
0x18000a5ac  xor     edx, edx; dwFlags
0x18000a5ae  mov     rcx, rax; hHeap
0x18000a5b1  call    cs:__imp_HeapFree
0x18000a5b7  mov     qword ptr [rdi+8], 0
0x18000a5bf  mov     [rdi], rsi
0x18000a5c2  mov     eax, 1
0x18000a5c7  mov     [rdi+8], rbp
0x18000a5cb  lock add [rsi], eax
0x18000a5ce  add     rsp, 28h
0x18000a5d2  pop     rdi
0x18000a5d3  pop     rsi
0x18000a5d4  pop     rbp
0x18000a5d5  pop     rbx
0x18000a5d6  retn
```
