# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800059f8`
- end: `0x180005abb`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e70`
- `0x180005ad0`

## callees

- `0x1800059f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a87`

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
0x1800059f8  push    rbx
0x1800059fa  push    rbp
0x1800059fb  push    rsi
0x1800059fc  push    rdi
0x1800059fd  sub     rsp, 28h
0x180005a01  mov     rbp, rdx
0x180005a04  mov     rdi, rcx
0x180005a07  test    rdx, rdx
0x180005a0a  jnz     short loc_180005A4D
0x180005a0c  mov     rcx, [rcx]
0x180005a0f  test    rcx, rcx
0x180005a12  jz      short loc_180005A46
0x180005a14  or      eax, 0FFFFFFFFh
0x180005a17  lock xadd [rcx], eax
0x180005a1b  cmp     eax, 1
0x180005a1e  jnz     short loc_180005A37
0x180005a20  mov     rbx, [rdi]
0x180005a23  call    cs:__imp_GetProcessHeap
0x180005a29  mov     r8, rbx; lpMem
0x180005a2c  xor     edx, edx; dwFlags
0x180005a2e  mov     rcx, rax; hHeap
0x180005a31  call    cs:__imp_HeapFree
0x180005a37  mov     qword ptr [rdi], 0
0x180005a3e  mov     qword ptr [rdi+8], 0
0x180005a46  mov     eax, 1
0x180005a4b  jmp     short loc_180005AB2
0x180005a4d  call    cs:__imp_GetProcessHeap
0x180005a53  lea     r8, [rbp+4]; dwBytes
0x180005a57  xor     edx, edx; dwFlags
0x180005a59  mov     rcx, rax; hHeap
0x180005a5c  call    cs:__imp_HeapAlloc
0x180005a62  mov     rsi, rax
0x180005a65  test    rax, rax
0x180005a68  jz      short loc_180005AB2
0x180005a6a  mov     dword ptr [rax], 0
0x180005a70  mov     rcx, [rdi]
0x180005a73  test    rcx, rcx
0x180005a76  jz      short loc_180005AA3
0x180005a78  or      eax, 0FFFFFFFFh
0x180005a7b  lock xadd [rcx], eax
0x180005a7f  cmp     eax, 1
0x180005a82  jnz     short loc_180005A9B
0x180005a84  mov     rbx, [rdi]
0x180005a87  call    cs:__imp_GetProcessHeap
0x180005a8d  mov     r8, rbx; lpMem
0x180005a90  xor     edx, edx; dwFlags
0x180005a92  mov     rcx, rax; hHeap
0x180005a95  call    cs:__imp_HeapFree
0x180005a9b  mov     qword ptr [rdi+8], 0
0x180005aa3  mov     [rdi], rsi
0x180005aa6  mov     eax, 1
0x180005aab  mov     [rdi+8], rbp
0x180005aaf  lock add [rsi], eax
0x180005ab2  add     rsp, 28h
0x180005ab6  pop     rdi
0x180005ab7  pop     rsi
0x180005ab8  pop     rbp
0x180005ab9  pop     rbx
0x180005aba  retn
```
