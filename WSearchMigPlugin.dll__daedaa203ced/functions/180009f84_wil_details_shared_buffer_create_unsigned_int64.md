# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180009f84`
- end: `0x18000a047`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b04`
- `0x18000a140`

## callees

- `0x180009f84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009faf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a013`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009faf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a013`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009fbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a021`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009fbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a021`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009fe8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009fe8`

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
0x180009f84  push    rbx
0x180009f86  push    rbp
0x180009f87  push    rsi
0x180009f88  push    rdi
0x180009f89  sub     rsp, 28h
0x180009f8d  mov     rbp, rdx
0x180009f90  mov     rdi, rcx
0x180009f93  test    rdx, rdx
0x180009f96  jnz     short loc_180009FD9
0x180009f98  mov     rcx, [rcx]
0x180009f9b  test    rcx, rcx
0x180009f9e  jz      short loc_180009FD2
0x180009fa0  or      eax, 0FFFFFFFFh
0x180009fa3  lock xadd [rcx], eax
0x180009fa7  cmp     eax, 1
0x180009faa  jnz     short loc_180009FC3
0x180009fac  mov     rbx, [rdi]
0x180009faf  call    cs:__imp_GetProcessHeap
0x180009fb5  mov     r8, rbx; lpMem
0x180009fb8  xor     edx, edx; dwFlags
0x180009fba  mov     rcx, rax; hHeap
0x180009fbd  call    cs:__imp_HeapFree
0x180009fc3  mov     qword ptr [rdi], 0
0x180009fca  mov     qword ptr [rdi+8], 0
0x180009fd2  mov     eax, 1
0x180009fd7  jmp     short loc_18000A03E
0x180009fd9  call    cs:__imp_GetProcessHeap
0x180009fdf  lea     r8, [rbp+4]; dwBytes
0x180009fe3  xor     edx, edx; dwFlags
0x180009fe5  mov     rcx, rax; hHeap
0x180009fe8  call    cs:__imp_HeapAlloc
0x180009fee  mov     rsi, rax
0x180009ff1  test    rax, rax
0x180009ff4  jz      short loc_18000A03E
0x180009ff6  mov     dword ptr [rax], 0
0x180009ffc  mov     rcx, [rdi]
0x180009fff  test    rcx, rcx
0x18000a002  jz      short loc_18000A02F
0x18000a004  or      eax, 0FFFFFFFFh
0x18000a007  lock xadd [rcx], eax
0x18000a00b  cmp     eax, 1
0x18000a00e  jnz     short loc_18000A027
0x18000a010  mov     rbx, [rdi]
0x18000a013  call    cs:__imp_GetProcessHeap
0x18000a019  mov     r8, rbx; lpMem
0x18000a01c  xor     edx, edx; dwFlags
0x18000a01e  mov     rcx, rax; hHeap
0x18000a021  call    cs:__imp_HeapFree
0x18000a027  mov     qword ptr [rdi+8], 0
0x18000a02f  mov     [rdi], rsi
0x18000a032  mov     eax, 1
0x18000a037  mov     [rdi+8], rbp
0x18000a03b  lock add [rsi], eax
0x18000a03e  add     rsp, 28h
0x18000a042  pop     rdi
0x18000a043  pop     rsi
0x18000a044  pop     rbp
0x18000a045  pop     rbx
0x18000a046  retn
```
