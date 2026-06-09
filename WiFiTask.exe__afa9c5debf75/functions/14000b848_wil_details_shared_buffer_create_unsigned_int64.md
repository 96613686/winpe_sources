# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000b848`
- end: `0x14000b90b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140009e70`
- `0x14000ba10`

## callees

- `0x14000b848`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b8e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b8e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b873`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b89d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b8d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b873`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b89d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b8d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b8ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b8ac`

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
0x14000b848  push    rbx
0x14000b84a  push    rbp
0x14000b84b  push    rsi
0x14000b84c  push    rdi
0x14000b84d  sub     rsp, 28h
0x14000b851  mov     rbp, rdx
0x14000b854  mov     rdi, rcx
0x14000b857  test    rdx, rdx
0x14000b85a  jnz     short loc_14000B89D
0x14000b85c  mov     rcx, [rcx]
0x14000b85f  test    rcx, rcx
0x14000b862  jz      short loc_14000B896
0x14000b864  or      eax, 0FFFFFFFFh
0x14000b867  lock xadd [rcx], eax
0x14000b86b  cmp     eax, 1
0x14000b86e  jnz     short loc_14000B887
0x14000b870  mov     rbx, [rdi]
0x14000b873  call    cs:__imp_GetProcessHeap
0x14000b879  mov     r8, rbx; lpMem
0x14000b87c  xor     edx, edx; dwFlags
0x14000b87e  mov     rcx, rax; hHeap
0x14000b881  call    cs:__imp_HeapFree
0x14000b887  mov     qword ptr [rdi], 0
0x14000b88e  mov     qword ptr [rdi+8], 0
0x14000b896  mov     eax, 1
0x14000b89b  jmp     short loc_14000B902
0x14000b89d  call    cs:__imp_GetProcessHeap
0x14000b8a3  lea     r8, [rbp+4]; dwBytes
0x14000b8a7  xor     edx, edx; dwFlags
0x14000b8a9  mov     rcx, rax; hHeap
0x14000b8ac  call    cs:__imp_HeapAlloc
0x14000b8b2  mov     rsi, rax
0x14000b8b5  test    rax, rax
0x14000b8b8  jz      short loc_14000B902
0x14000b8ba  mov     dword ptr [rax], 0
0x14000b8c0  mov     rcx, [rdi]
0x14000b8c3  test    rcx, rcx
0x14000b8c6  jz      short loc_14000B8F3
0x14000b8c8  or      eax, 0FFFFFFFFh
0x14000b8cb  lock xadd [rcx], eax
0x14000b8cf  cmp     eax, 1
0x14000b8d2  jnz     short loc_14000B8EB
0x14000b8d4  mov     rbx, [rdi]
0x14000b8d7  call    cs:__imp_GetProcessHeap
0x14000b8dd  mov     r8, rbx; lpMem
0x14000b8e0  xor     edx, edx; dwFlags
0x14000b8e2  mov     rcx, rax; hHeap
0x14000b8e5  call    cs:__imp_HeapFree
0x14000b8eb  mov     qword ptr [rdi+8], 0
0x14000b8f3  mov     [rdi], rsi
0x14000b8f6  mov     eax, 1
0x14000b8fb  mov     [rdi+8], rbp
0x14000b8ff  lock add [rsi], eax
0x14000b902  add     rsp, 28h
0x14000b906  pop     rdi
0x14000b907  pop     rsi
0x14000b908  pop     rbp
0x14000b909  pop     rbx
0x14000b90a  retn
```
