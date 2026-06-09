# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180019734`
- end: `0x1800197f7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800185c8`
- `0x1800198f0`

## callees

- `0x180019734`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019798`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019798`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001976d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800197d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001976d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800197d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001975f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800197c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001975f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800197c3`

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
0x180019734  push    rbx
0x180019736  push    rbp
0x180019737  push    rsi
0x180019738  push    rdi
0x180019739  sub     rsp, 28h
0x18001973d  mov     rbp, rdx
0x180019740  mov     rdi, rcx
0x180019743  test    rdx, rdx
0x180019746  jnz     short loc_180019789
0x180019748  mov     rcx, [rcx]
0x18001974b  test    rcx, rcx
0x18001974e  jz      short loc_180019782
0x180019750  or      eax, 0FFFFFFFFh
0x180019753  lock xadd [rcx], eax
0x180019757  cmp     eax, 1
0x18001975a  jnz     short loc_180019773
0x18001975c  mov     rbx, [rdi]
0x18001975f  call    cs:__imp_GetProcessHeap
0x180019765  mov     r8, rbx; lpMem
0x180019768  xor     edx, edx; dwFlags
0x18001976a  mov     rcx, rax; hHeap
0x18001976d  call    cs:__imp_HeapFree
0x180019773  mov     qword ptr [rdi], 0
0x18001977a  mov     qword ptr [rdi+8], 0
0x180019782  mov     eax, 1
0x180019787  jmp     short loc_1800197EE
0x180019789  call    cs:__imp_GetProcessHeap
0x18001978f  lea     r8, [rbp+4]; dwBytes
0x180019793  xor     edx, edx; dwFlags
0x180019795  mov     rcx, rax; hHeap
0x180019798  call    cs:__imp_HeapAlloc
0x18001979e  mov     rsi, rax
0x1800197a1  test    rax, rax
0x1800197a4  jz      short loc_1800197EE
0x1800197a6  mov     dword ptr [rax], 0
0x1800197ac  mov     rcx, [rdi]
0x1800197af  test    rcx, rcx
0x1800197b2  jz      short loc_1800197DF
0x1800197b4  or      eax, 0FFFFFFFFh
0x1800197b7  lock xadd [rcx], eax
0x1800197bb  cmp     eax, 1
0x1800197be  jnz     short loc_1800197D7
0x1800197c0  mov     rbx, [rdi]
0x1800197c3  call    cs:__imp_GetProcessHeap
0x1800197c9  mov     r8, rbx; lpMem
0x1800197cc  xor     edx, edx; dwFlags
0x1800197ce  mov     rcx, rax; hHeap
0x1800197d1  call    cs:__imp_HeapFree
0x1800197d7  mov     qword ptr [rdi+8], 0
0x1800197df  mov     [rdi], rsi
0x1800197e2  mov     eax, 1
0x1800197e7  mov     [rdi+8], rbp
0x1800197eb  lock add [rsi], eax
0x1800197ee  add     rsp, 28h
0x1800197f2  pop     rdi
0x1800197f3  pop     rsi
0x1800197f4  pop     rbp
0x1800197f5  pop     rbx
0x1800197f6  retn
```
