# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000be08`
- end: `0x18000becb`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e78`
- `0x18000c2f0`

## callees

- `0x18000be08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be97`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000be6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000be6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bea5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bea5`

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
0x18000be08  push    rbx
0x18000be0a  push    rbp
0x18000be0b  push    rsi
0x18000be0c  push    rdi
0x18000be0d  sub     rsp, 28h
0x18000be11  mov     rbp, rdx
0x18000be14  mov     rdi, rcx
0x18000be17  test    rdx, rdx
0x18000be1a  jnz     short loc_18000BE5D
0x18000be1c  mov     rcx, [rcx]
0x18000be1f  test    rcx, rcx
0x18000be22  jz      short loc_18000BE56
0x18000be24  or      eax, 0FFFFFFFFh
0x18000be27  lock xadd [rcx], eax
0x18000be2b  cmp     eax, 1
0x18000be2e  jnz     short loc_18000BE47
0x18000be30  mov     rbx, [rdi]
0x18000be33  call    cs:__imp_GetProcessHeap
0x18000be39  mov     r8, rbx; lpMem
0x18000be3c  xor     edx, edx; dwFlags
0x18000be3e  mov     rcx, rax; hHeap
0x18000be41  call    cs:__imp_HeapFree
0x18000be47  mov     qword ptr [rdi], 0
0x18000be4e  mov     qword ptr [rdi+8], 0
0x18000be56  mov     eax, 1
0x18000be5b  jmp     short loc_18000BEC2
0x18000be5d  call    cs:__imp_GetProcessHeap
0x18000be63  lea     r8, [rbp+4]; dwBytes
0x18000be67  xor     edx, edx; dwFlags
0x18000be69  mov     rcx, rax; hHeap
0x18000be6c  call    cs:__imp_HeapAlloc
0x18000be72  mov     rsi, rax
0x18000be75  test    rax, rax
0x18000be78  jz      short loc_18000BEC2
0x18000be7a  mov     dword ptr [rax], 0
0x18000be80  mov     rcx, [rdi]
0x18000be83  test    rcx, rcx
0x18000be86  jz      short loc_18000BEB3
0x18000be88  or      eax, 0FFFFFFFFh
0x18000be8b  lock xadd [rcx], eax
0x18000be8f  cmp     eax, 1
0x18000be92  jnz     short loc_18000BEAB
0x18000be94  mov     rbx, [rdi]
0x18000be97  call    cs:__imp_GetProcessHeap
0x18000be9d  mov     r8, rbx; lpMem
0x18000bea0  xor     edx, edx; dwFlags
0x18000bea2  mov     rcx, rax; hHeap
0x18000bea5  call    cs:__imp_HeapFree
0x18000beab  mov     qword ptr [rdi+8], 0
0x18000beb3  mov     [rdi], rsi
0x18000beb6  mov     eax, 1
0x18000bebb  mov     [rdi+8], rbp
0x18000bebf  lock add [rsi], eax
0x18000bec2  add     rsp, 28h
0x18000bec6  pop     rdi
0x18000bec7  pop     rsi
0x18000bec8  pop     rbp
0x18000bec9  pop     rbx
0x18000beca  retn
```
