# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140005608`
- end: `0x1400056cb`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004a74`
- `0x1400056e0`

## callees

- `0x140005608`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005633`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000565d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005697`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005633`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000565d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005697`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005641`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400056a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005641`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400056a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000566c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000566c`

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
0x140005608  push    rbx
0x14000560a  push    rbp
0x14000560b  push    rsi
0x14000560c  push    rdi
0x14000560d  sub     rsp, 28h
0x140005611  mov     rbp, rdx
0x140005614  mov     rdi, rcx
0x140005617  test    rdx, rdx
0x14000561a  jnz     short loc_14000565D
0x14000561c  mov     rcx, [rcx]
0x14000561f  test    rcx, rcx
0x140005622  jz      short loc_140005656
0x140005624  or      eax, 0FFFFFFFFh
0x140005627  lock xadd [rcx], eax
0x14000562b  cmp     eax, 1
0x14000562e  jnz     short loc_140005647
0x140005630  mov     rbx, [rdi]
0x140005633  call    cs:__imp_GetProcessHeap
0x140005639  mov     r8, rbx; lpMem
0x14000563c  xor     edx, edx; dwFlags
0x14000563e  mov     rcx, rax; hHeap
0x140005641  call    cs:__imp_HeapFree
0x140005647  mov     qword ptr [rdi], 0
0x14000564e  mov     qword ptr [rdi+8], 0
0x140005656  mov     eax, 1
0x14000565b  jmp     short loc_1400056C2
0x14000565d  call    cs:__imp_GetProcessHeap
0x140005663  lea     r8, [rbp+4]; dwBytes
0x140005667  xor     edx, edx; dwFlags
0x140005669  mov     rcx, rax; hHeap
0x14000566c  call    cs:__imp_HeapAlloc
0x140005672  mov     rsi, rax
0x140005675  test    rax, rax
0x140005678  jz      short loc_1400056C2
0x14000567a  mov     dword ptr [rax], 0
0x140005680  mov     rcx, [rdi]
0x140005683  test    rcx, rcx
0x140005686  jz      short loc_1400056B3
0x140005688  or      eax, 0FFFFFFFFh
0x14000568b  lock xadd [rcx], eax
0x14000568f  cmp     eax, 1
0x140005692  jnz     short loc_1400056AB
0x140005694  mov     rbx, [rdi]
0x140005697  call    cs:__imp_GetProcessHeap
0x14000569d  mov     r8, rbx; lpMem
0x1400056a0  xor     edx, edx; dwFlags
0x1400056a2  mov     rcx, rax; hHeap
0x1400056a5  call    cs:__imp_HeapFree
0x1400056ab  mov     qword ptr [rdi+8], 0
0x1400056b3  mov     [rdi], rsi
0x1400056b6  mov     eax, 1
0x1400056bb  mov     [rdi+8], rbp
0x1400056bf  lock add [rsi], eax
0x1400056c2  add     rsp, 28h
0x1400056c6  pop     rdi
0x1400056c7  pop     rsi
0x1400056c8  pop     rbp
0x1400056c9  pop     rbx
0x1400056ca  retn
```
