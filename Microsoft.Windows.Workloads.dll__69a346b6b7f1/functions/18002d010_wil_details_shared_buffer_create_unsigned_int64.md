# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18002d010`
- end: `0x18002d0f7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `231`
- prototype: `bool __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002d360`
- `0x18002dbe0`

## callees

- `0x18002d010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002d051`
- `KERNEL32!HeapFree` at `0x18002d0c7`
- `KERNEL32!HeapFree` at `0x18002d051`
- `KERNEL32!HeapFree` at `0x18002d0c7`
- `KERNEL32!GetProcessHeap` at `0x18002d043`
- `KERNEL32!GetProcessHeap` at `0x18002d07d`
- `KERNEL32!GetProcessHeap` at `0x18002d0b9`
- `KERNEL32!GetProcessHeap` at `0x18002d043`
- `KERNEL32!GetProcessHeap` at `0x18002d07d`
- `KERNEL32!GetProcessHeap` at `0x18002d0b9`
- `KERNEL32!HeapAlloc` at `0x18002d08c`
- `KERNEL32!HeapAlloc` at `0x18002d08c`

## pseudocode

```c
bool __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  volatile signed __int32 *v7; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // r14
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    v7 = (volatile signed __int32 *)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = v7;
    if ( v7 )
    {
      *v7 = 0;
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
      this[1] = a2;
      _InterlockedIncrement(v9);
      LOBYTE(v7) = 1;
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
    LOBYTE(v7) = 1;
  }
  return (char)v7;
}

```

## disassembly

```asm
0x18002d010  mov     [rsp+arg_8], rbx
0x18002d015  mov     [rsp+arg_10], rbp
0x18002d01a  push    rdi
0x18002d01b  sub     rsp, 20h
0x18002d01f  mov     rbp, rdx
0x18002d022  mov     rdi, rcx
0x18002d025  test    rdx, rdx
0x18002d028  jnz     short loc_18002D078
0x18002d02a  mov     rcx, [rcx]
0x18002d02d  test    rcx, rcx
0x18002d030  jz      short loc_18002D066
0x18002d032  mov     eax, 0FFFFFFFFh
0x18002d037  lock xadd [rcx], eax
0x18002d03b  cmp     eax, 1
0x18002d03e  jnz     short loc_18002D057
0x18002d040  mov     rbx, [rdi]
0x18002d043  call    cs:__imp_GetProcessHeap
0x18002d049  mov     r8, rbx; lpMem
0x18002d04c  xor     edx, edx; dwFlags
0x18002d04e  mov     rcx, rax; hHeap
0x18002d051  call    cs:__imp_HeapFree
0x18002d057  mov     qword ptr [rdi], 0
0x18002d05e  mov     qword ptr [rdi+8], 0
0x18002d066  mov     al, 1
0x18002d068  mov     rbx, [rsp+28h+arg_8]
0x18002d06d  mov     rbp, [rsp+28h+arg_10]
0x18002d072  add     rsp, 20h
0x18002d076  pop     rdi
0x18002d077  retn
0x18002d078  mov     [rsp+28h+arg_0], r14
0x18002d07d  call    cs:__imp_GetProcessHeap
0x18002d083  lea     r8, [rbp+4]; dwBytes
0x18002d087  xor     edx, edx; dwFlags
0x18002d089  mov     rcx, rax; hHeap
0x18002d08c  call    cs:__imp_HeapAlloc
0x18002d092  mov     r14, rax
0x18002d095  test    rax, rax
0x18002d098  jz      short loc_18002D0E2
0x18002d09a  mov     dword ptr [rax], 0
0x18002d0a0  mov     rcx, [rdi]
0x18002d0a3  test    rcx, rcx
0x18002d0a6  jz      short loc_18002D0D5
0x18002d0a8  mov     eax, 0FFFFFFFFh
0x18002d0ad  lock xadd [rcx], eax
0x18002d0b1  cmp     eax, 1
0x18002d0b4  jnz     short loc_18002D0CD
0x18002d0b6  mov     rbx, [rdi]
0x18002d0b9  call    cs:__imp_GetProcessHeap
0x18002d0bf  mov     r8, rbx; lpMem
0x18002d0c2  xor     edx, edx; dwFlags
0x18002d0c4  mov     rcx, rax; hHeap
0x18002d0c7  call    cs:__imp_HeapFree
0x18002d0cd  mov     qword ptr [rdi+8], 0
0x18002d0d5  mov     [rdi], r14
0x18002d0d8  mov     [rdi+8], rbp
0x18002d0dc  lock inc dword ptr [r14]
0x18002d0e0  mov     al, 1
0x18002d0e2  mov     r14, [rsp+28h+arg_0]
0x18002d0e7  mov     rbx, [rsp+28h+arg_8]
0x18002d0ec  mov     rbp, [rsp+28h+arg_10]
0x18002d0f1  add     rsp, 20h
0x18002d0f5  pop     rdi
0x18002d0f6  retn
```
