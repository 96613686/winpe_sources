# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000ea38`
- end: `0x14000eafb`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c6ec`
- `0x14000ec60`

## callees

- `0x14000ea38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000ea9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000ea9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ea71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ead5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ea71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ead5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ea63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ea8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000eac7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ea63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ea8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000eac7`

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
0x14000ea38  push    rbx
0x14000ea3a  push    rbp
0x14000ea3b  push    rsi
0x14000ea3c  push    rdi
0x14000ea3d  sub     rsp, 28h
0x14000ea41  mov     rbp, rdx
0x14000ea44  mov     rdi, rcx
0x14000ea47  test    rdx, rdx
0x14000ea4a  jnz     short loc_14000EA8D
0x14000ea4c  mov     rcx, [rcx]
0x14000ea4f  test    rcx, rcx
0x14000ea52  jz      short loc_14000EA86
0x14000ea54  or      eax, 0FFFFFFFFh
0x14000ea57  lock xadd [rcx], eax
0x14000ea5b  cmp     eax, 1
0x14000ea5e  jnz     short loc_14000EA77
0x14000ea60  mov     rbx, [rdi]
0x14000ea63  call    cs:__imp_GetProcessHeap
0x14000ea69  mov     r8, rbx; lpMem
0x14000ea6c  xor     edx, edx; dwFlags
0x14000ea6e  mov     rcx, rax; hHeap
0x14000ea71  call    cs:__imp_HeapFree
0x14000ea77  mov     qword ptr [rdi], 0
0x14000ea7e  mov     qword ptr [rdi+8], 0
0x14000ea86  mov     eax, 1
0x14000ea8b  jmp     short loc_14000EAF2
0x14000ea8d  call    cs:__imp_GetProcessHeap
0x14000ea93  lea     r8, [rbp+4]; dwBytes
0x14000ea97  xor     edx, edx; dwFlags
0x14000ea99  mov     rcx, rax; hHeap
0x14000ea9c  call    cs:__imp_HeapAlloc
0x14000eaa2  mov     rsi, rax
0x14000eaa5  test    rax, rax
0x14000eaa8  jz      short loc_14000EAF2
0x14000eaaa  mov     dword ptr [rax], 0
0x14000eab0  mov     rcx, [rdi]
0x14000eab3  test    rcx, rcx
0x14000eab6  jz      short loc_14000EAE3
0x14000eab8  or      eax, 0FFFFFFFFh
0x14000eabb  lock xadd [rcx], eax
0x14000eabf  cmp     eax, 1
0x14000eac2  jnz     short loc_14000EADB
0x14000eac4  mov     rbx, [rdi]
0x14000eac7  call    cs:__imp_GetProcessHeap
0x14000eacd  mov     r8, rbx; lpMem
0x14000ead0  xor     edx, edx; dwFlags
0x14000ead2  mov     rcx, rax; hHeap
0x14000ead5  call    cs:__imp_HeapFree
0x14000eadb  mov     qword ptr [rdi+8], 0
0x14000eae3  mov     [rdi], rsi
0x14000eae6  mov     eax, 1
0x14000eaeb  mov     [rdi+8], rbp
0x14000eaef  lock add [rsi], eax
0x14000eaf2  add     rsp, 28h
0x14000eaf6  pop     rdi
0x14000eaf7  pop     rsi
0x14000eaf8  pop     rbp
0x14000eaf9  pop     rbx
0x14000eafa  retn
```
