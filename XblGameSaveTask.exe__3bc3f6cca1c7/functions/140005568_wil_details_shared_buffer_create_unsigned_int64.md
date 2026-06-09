# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140005568`
- end: `0x14000562b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400049d0`
- `0x140005640`

## callees

- `0x140005568`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400055cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400055cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400055a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005605`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400055a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005605`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005593`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400055bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400055f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005593`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400055bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400055f7`

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
0x140005568  push    rbx
0x14000556a  push    rbp
0x14000556b  push    rsi
0x14000556c  push    rdi
0x14000556d  sub     rsp, 28h
0x140005571  mov     rbp, rdx
0x140005574  mov     rdi, rcx
0x140005577  test    rdx, rdx
0x14000557a  jnz     short loc_1400055BD
0x14000557c  mov     rcx, [rcx]
0x14000557f  test    rcx, rcx
0x140005582  jz      short loc_1400055B6
0x140005584  or      eax, 0FFFFFFFFh
0x140005587  lock xadd [rcx], eax
0x14000558b  cmp     eax, 1
0x14000558e  jnz     short loc_1400055A7
0x140005590  mov     rbx, [rdi]
0x140005593  call    cs:__imp_GetProcessHeap
0x140005599  mov     r8, rbx; lpMem
0x14000559c  xor     edx, edx; dwFlags
0x14000559e  mov     rcx, rax; hHeap
0x1400055a1  call    cs:__imp_HeapFree
0x1400055a7  mov     qword ptr [rdi], 0
0x1400055ae  mov     qword ptr [rdi+8], 0
0x1400055b6  mov     eax, 1
0x1400055bb  jmp     short loc_140005622
0x1400055bd  call    cs:__imp_GetProcessHeap
0x1400055c3  lea     r8, [rbp+4]; dwBytes
0x1400055c7  xor     edx, edx; dwFlags
0x1400055c9  mov     rcx, rax; hHeap
0x1400055cc  call    cs:__imp_HeapAlloc
0x1400055d2  mov     rsi, rax
0x1400055d5  test    rax, rax
0x1400055d8  jz      short loc_140005622
0x1400055da  mov     dword ptr [rax], 0
0x1400055e0  mov     rcx, [rdi]
0x1400055e3  test    rcx, rcx
0x1400055e6  jz      short loc_140005613
0x1400055e8  or      eax, 0FFFFFFFFh
0x1400055eb  lock xadd [rcx], eax
0x1400055ef  cmp     eax, 1
0x1400055f2  jnz     short loc_14000560B
0x1400055f4  mov     rbx, [rdi]
0x1400055f7  call    cs:__imp_GetProcessHeap
0x1400055fd  mov     r8, rbx; lpMem
0x140005600  xor     edx, edx; dwFlags
0x140005602  mov     rcx, rax; hHeap
0x140005605  call    cs:__imp_HeapFree
0x14000560b  mov     qword ptr [rdi+8], 0
0x140005613  mov     [rdi], rsi
0x140005616  mov     eax, 1
0x14000561b  mov     [rdi+8], rbp
0x14000561f  lock add [rsi], eax
0x140005622  add     rsp, 28h
0x140005626  pop     rdi
0x140005627  pop     rsi
0x140005628  pop     rbp
0x140005629  pop     rbx
0x14000562a  retn
```
