# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180008a30`
- end: `0x180008af3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007b10`
- `0x180008b00`

## callees

- `0x180008a30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008abf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008abf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008acd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008acd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a94`

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
0x180008a30  push    rbx
0x180008a32  push    rbp
0x180008a33  push    rsi
0x180008a34  push    rdi
0x180008a35  sub     rsp, 28h
0x180008a39  mov     rbp, rdx
0x180008a3c  mov     rdi, rcx
0x180008a3f  test    rdx, rdx
0x180008a42  jnz     short loc_180008A85
0x180008a44  mov     rcx, [rcx]
0x180008a47  test    rcx, rcx
0x180008a4a  jz      short loc_180008A7E
0x180008a4c  or      eax, 0FFFFFFFFh
0x180008a4f  lock xadd [rcx], eax
0x180008a53  cmp     eax, 1
0x180008a56  jnz     short loc_180008A6F
0x180008a58  mov     rbx, [rdi]
0x180008a5b  call    cs:__imp_GetProcessHeap
0x180008a61  mov     r8, rbx; lpMem
0x180008a64  xor     edx, edx; dwFlags
0x180008a66  mov     rcx, rax; hHeap
0x180008a69  call    cs:__imp_HeapFree
0x180008a6f  mov     qword ptr [rdi], 0
0x180008a76  mov     qword ptr [rdi+8], 0
0x180008a7e  mov     eax, 1
0x180008a83  jmp     short loc_180008AEA
0x180008a85  call    cs:__imp_GetProcessHeap
0x180008a8b  lea     r8, [rbp+4]; dwBytes
0x180008a8f  xor     edx, edx; dwFlags
0x180008a91  mov     rcx, rax; hHeap
0x180008a94  call    cs:__imp_HeapAlloc
0x180008a9a  mov     rsi, rax
0x180008a9d  test    rax, rax
0x180008aa0  jz      short loc_180008AEA
0x180008aa2  mov     dword ptr [rax], 0
0x180008aa8  mov     rcx, [rdi]
0x180008aab  test    rcx, rcx
0x180008aae  jz      short loc_180008ADB
0x180008ab0  or      eax, 0FFFFFFFFh
0x180008ab3  lock xadd [rcx], eax
0x180008ab7  cmp     eax, 1
0x180008aba  jnz     short loc_180008AD3
0x180008abc  mov     rbx, [rdi]
0x180008abf  call    cs:__imp_GetProcessHeap
0x180008ac5  mov     r8, rbx; lpMem
0x180008ac8  xor     edx, edx; dwFlags
0x180008aca  mov     rcx, rax; hHeap
0x180008acd  call    cs:__imp_HeapFree
0x180008ad3  mov     qword ptr [rdi+8], 0
0x180008adb  mov     [rdi], rsi
0x180008ade  mov     eax, 1
0x180008ae3  mov     [rdi+8], rbp
0x180008ae7  lock add [rsi], eax
0x180008aea  add     rsp, 28h
0x180008aee  pop     rdi
0x180008aef  pop     rsi
0x180008af0  pop     rbp
0x180008af1  pop     rbx
0x180008af2  retn
```
