# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180009044`
- end: `0x180009107`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007bd8`
- `0x180009200`

## callees

- `0x180009044`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800090a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800090a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000907d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000907d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000906f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009099`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000906f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009099`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090d3`

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
0x180009044  push    rbx
0x180009046  push    rbp
0x180009047  push    rsi
0x180009048  push    rdi
0x180009049  sub     rsp, 28h
0x18000904d  mov     rbp, rdx
0x180009050  mov     rdi, rcx
0x180009053  test    rdx, rdx
0x180009056  jnz     short loc_180009099
0x180009058  mov     rcx, [rcx]
0x18000905b  test    rcx, rcx
0x18000905e  jz      short loc_180009092
0x180009060  or      eax, 0FFFFFFFFh
0x180009063  lock xadd [rcx], eax
0x180009067  cmp     eax, 1
0x18000906a  jnz     short loc_180009083
0x18000906c  mov     rbx, [rdi]
0x18000906f  call    cs:__imp_GetProcessHeap
0x180009075  mov     r8, rbx; lpMem
0x180009078  xor     edx, edx; dwFlags
0x18000907a  mov     rcx, rax; hHeap
0x18000907d  call    cs:__imp_HeapFree
0x180009083  mov     qword ptr [rdi], 0
0x18000908a  mov     qword ptr [rdi+8], 0
0x180009092  mov     eax, 1
0x180009097  jmp     short loc_1800090FE
0x180009099  call    cs:__imp_GetProcessHeap
0x18000909f  lea     r8, [rbp+4]; dwBytes
0x1800090a3  xor     edx, edx; dwFlags
0x1800090a5  mov     rcx, rax; hHeap
0x1800090a8  call    cs:__imp_HeapAlloc
0x1800090ae  mov     rsi, rax
0x1800090b1  test    rax, rax
0x1800090b4  jz      short loc_1800090FE
0x1800090b6  mov     dword ptr [rax], 0
0x1800090bc  mov     rcx, [rdi]
0x1800090bf  test    rcx, rcx
0x1800090c2  jz      short loc_1800090EF
0x1800090c4  or      eax, 0FFFFFFFFh
0x1800090c7  lock xadd [rcx], eax
0x1800090cb  cmp     eax, 1
0x1800090ce  jnz     short loc_1800090E7
0x1800090d0  mov     rbx, [rdi]
0x1800090d3  call    cs:__imp_GetProcessHeap
0x1800090d9  mov     r8, rbx; lpMem
0x1800090dc  xor     edx, edx; dwFlags
0x1800090de  mov     rcx, rax; hHeap
0x1800090e1  call    cs:__imp_HeapFree
0x1800090e7  mov     qword ptr [rdi+8], 0
0x1800090ef  mov     [rdi], rsi
0x1800090f2  mov     eax, 1
0x1800090f7  mov     [rdi+8], rbp
0x1800090fb  lock add [rsi], eax
0x1800090fe  add     rsp, 28h
0x180009102  pop     rdi
0x180009103  pop     rsi
0x180009104  pop     rbp
0x180009105  pop     rbx
0x180009106  retn
```
