# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000d520`
- end: `0x18000d5e3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007d78`
- `0x18000d6e0`

## callees

- `0x18000d520`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d559`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d5bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d559`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d5bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d54b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d575`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d5af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d54b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d575`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d5af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d584`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d584`

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
0x18000d520  push    rbx
0x18000d522  push    rbp
0x18000d523  push    rsi
0x18000d524  push    rdi
0x18000d525  sub     rsp, 28h
0x18000d529  mov     rbp, rdx
0x18000d52c  mov     rdi, rcx
0x18000d52f  test    rdx, rdx
0x18000d532  jnz     short loc_18000D575
0x18000d534  mov     rcx, [rcx]
0x18000d537  test    rcx, rcx
0x18000d53a  jz      short loc_18000D56E
0x18000d53c  or      eax, 0FFFFFFFFh
0x18000d53f  lock xadd [rcx], eax
0x18000d543  cmp     eax, 1
0x18000d546  jnz     short loc_18000D55F
0x18000d548  mov     rbx, [rdi]
0x18000d54b  call    cs:__imp_GetProcessHeap
0x18000d551  mov     r8, rbx; lpMem
0x18000d554  xor     edx, edx; dwFlags
0x18000d556  mov     rcx, rax; hHeap
0x18000d559  call    cs:__imp_HeapFree
0x18000d55f  mov     qword ptr [rdi], 0
0x18000d566  mov     qword ptr [rdi+8], 0
0x18000d56e  mov     eax, 1
0x18000d573  jmp     short loc_18000D5DA
0x18000d575  call    cs:__imp_GetProcessHeap
0x18000d57b  lea     r8, [rbp+4]; dwBytes
0x18000d57f  xor     edx, edx; dwFlags
0x18000d581  mov     rcx, rax; hHeap
0x18000d584  call    cs:__imp_HeapAlloc
0x18000d58a  mov     rsi, rax
0x18000d58d  test    rax, rax
0x18000d590  jz      short loc_18000D5DA
0x18000d592  mov     dword ptr [rax], 0
0x18000d598  mov     rcx, [rdi]
0x18000d59b  test    rcx, rcx
0x18000d59e  jz      short loc_18000D5CB
0x18000d5a0  or      eax, 0FFFFFFFFh
0x18000d5a3  lock xadd [rcx], eax
0x18000d5a7  cmp     eax, 1
0x18000d5aa  jnz     short loc_18000D5C3
0x18000d5ac  mov     rbx, [rdi]
0x18000d5af  call    cs:__imp_GetProcessHeap
0x18000d5b5  mov     r8, rbx; lpMem
0x18000d5b8  xor     edx, edx; dwFlags
0x18000d5ba  mov     rcx, rax; hHeap
0x18000d5bd  call    cs:__imp_HeapFree
0x18000d5c3  mov     qword ptr [rdi+8], 0
0x18000d5cb  mov     [rdi], rsi
0x18000d5ce  mov     eax, 1
0x18000d5d3  mov     [rdi+8], rbp
0x18000d5d7  lock add [rsi], eax
0x18000d5da  add     rsp, 28h
0x18000d5de  pop     rdi
0x18000d5df  pop     rsi
0x18000d5e0  pop     rbp
0x18000d5e1  pop     rbx
0x18000d5e2  retn
```
