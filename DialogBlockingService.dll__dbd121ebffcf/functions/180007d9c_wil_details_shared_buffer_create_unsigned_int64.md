# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007d9c`
- end: `0x180007e5f`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b88`
- `0x180007e70`

## callees

- `0x180007d9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007dc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007df1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007dc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007df1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e2b`

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
0x180007d9c  push    rbx
0x180007d9e  push    rbp
0x180007d9f  push    rsi
0x180007da0  push    rdi
0x180007da1  sub     rsp, 28h
0x180007da5  mov     rbp, rdx
0x180007da8  mov     rdi, rcx
0x180007dab  test    rdx, rdx
0x180007dae  jnz     short loc_180007DF1
0x180007db0  mov     rcx, [rcx]
0x180007db3  test    rcx, rcx
0x180007db6  jz      short loc_180007DEA
0x180007db8  or      eax, 0FFFFFFFFh
0x180007dbb  lock xadd [rcx], eax
0x180007dbf  cmp     eax, 1
0x180007dc2  jnz     short loc_180007DDB
0x180007dc4  mov     rbx, [rdi]
0x180007dc7  call    cs:__imp_GetProcessHeap
0x180007dcd  mov     r8, rbx; lpMem
0x180007dd0  xor     edx, edx; dwFlags
0x180007dd2  mov     rcx, rax; hHeap
0x180007dd5  call    cs:__imp_HeapFree
0x180007ddb  mov     qword ptr [rdi], 0
0x180007de2  mov     qword ptr [rdi+8], 0
0x180007dea  mov     eax, 1
0x180007def  jmp     short loc_180007E56
0x180007df1  call    cs:__imp_GetProcessHeap
0x180007df7  lea     r8, [rbp+4]; dwBytes
0x180007dfb  xor     edx, edx; dwFlags
0x180007dfd  mov     rcx, rax; hHeap
0x180007e00  call    cs:__imp_HeapAlloc
0x180007e06  mov     rsi, rax
0x180007e09  test    rax, rax
0x180007e0c  jz      short loc_180007E56
0x180007e0e  mov     dword ptr [rax], 0
0x180007e14  mov     rcx, [rdi]
0x180007e17  test    rcx, rcx
0x180007e1a  jz      short loc_180007E47
0x180007e1c  or      eax, 0FFFFFFFFh
0x180007e1f  lock xadd [rcx], eax
0x180007e23  cmp     eax, 1
0x180007e26  jnz     short loc_180007E3F
0x180007e28  mov     rbx, [rdi]
0x180007e2b  call    cs:__imp_GetProcessHeap
0x180007e31  mov     r8, rbx; lpMem
0x180007e34  xor     edx, edx; dwFlags
0x180007e36  mov     rcx, rax; hHeap
0x180007e39  call    cs:__imp_HeapFree
0x180007e3f  mov     qword ptr [rdi+8], 0
0x180007e47  mov     [rdi], rsi
0x180007e4a  mov     eax, 1
0x180007e4f  mov     [rdi+8], rbp
0x180007e53  lock add [rsi], eax
0x180007e56  add     rsp, 28h
0x180007e5a  pop     rdi
0x180007e5b  pop     rsi
0x180007e5c  pop     rbp
0x180007e5d  pop     rbx
0x180007e5e  retn
```
