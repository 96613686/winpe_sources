# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000ea40`
- end: `0x18000eb03`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c3c8`
- `0x18000f570`

## callees

- `0x18000ea40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eadd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eadd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eaa4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eaa4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eacf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eacf`

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
0x18000ea40  push    rbx
0x18000ea42  push    rbp
0x18000ea43  push    rsi
0x18000ea44  push    rdi
0x18000ea45  sub     rsp, 28h
0x18000ea49  mov     rbp, rdx
0x18000ea4c  mov     rdi, rcx
0x18000ea4f  test    rdx, rdx
0x18000ea52  jnz     short loc_18000EA95
0x18000ea54  mov     rcx, [rcx]
0x18000ea57  test    rcx, rcx
0x18000ea5a  jz      short loc_18000EA8E
0x18000ea5c  or      eax, 0FFFFFFFFh
0x18000ea5f  lock xadd [rcx], eax
0x18000ea63  cmp     eax, 1
0x18000ea66  jnz     short loc_18000EA7F
0x18000ea68  mov     rbx, [rdi]
0x18000ea6b  call    cs:__imp_GetProcessHeap
0x18000ea71  mov     r8, rbx; lpMem
0x18000ea74  xor     edx, edx; dwFlags
0x18000ea76  mov     rcx, rax; hHeap
0x18000ea79  call    cs:__imp_HeapFree
0x18000ea7f  mov     qword ptr [rdi], 0
0x18000ea86  mov     qword ptr [rdi+8], 0
0x18000ea8e  mov     eax, 1
0x18000ea93  jmp     short loc_18000EAFA
0x18000ea95  call    cs:__imp_GetProcessHeap
0x18000ea9b  lea     r8, [rbp+4]; dwBytes
0x18000ea9f  xor     edx, edx; dwFlags
0x18000eaa1  mov     rcx, rax; hHeap
0x18000eaa4  call    cs:__imp_HeapAlloc
0x18000eaaa  mov     rsi, rax
0x18000eaad  test    rax, rax
0x18000eab0  jz      short loc_18000EAFA
0x18000eab2  mov     dword ptr [rax], 0
0x18000eab8  mov     rcx, [rdi]
0x18000eabb  test    rcx, rcx
0x18000eabe  jz      short loc_18000EAEB
0x18000eac0  or      eax, 0FFFFFFFFh
0x18000eac3  lock xadd [rcx], eax
0x18000eac7  cmp     eax, 1
0x18000eaca  jnz     short loc_18000EAE3
0x18000eacc  mov     rbx, [rdi]
0x18000eacf  call    cs:__imp_GetProcessHeap
0x18000ead5  mov     r8, rbx; lpMem
0x18000ead8  xor     edx, edx; dwFlags
0x18000eada  mov     rcx, rax; hHeap
0x18000eadd  call    cs:__imp_HeapFree
0x18000eae3  mov     qword ptr [rdi+8], 0
0x18000eaeb  mov     [rdi], rsi
0x18000eaee  mov     eax, 1
0x18000eaf3  mov     [rdi+8], rbp
0x18000eaf7  lock add [rsi], eax
0x18000eafa  add     rsp, 28h
0x18000eafe  pop     rdi
0x18000eaff  pop     rsi
0x18000eb00  pop     rbp
0x18000eb01  pop     rbx
0x18000eb02  retn
```
