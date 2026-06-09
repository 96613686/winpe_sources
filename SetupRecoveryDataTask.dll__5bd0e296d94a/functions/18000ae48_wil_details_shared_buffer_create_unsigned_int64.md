# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000ae48`
- end: `0x18000af0b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c28`
- `0x18000b320`

## callees

- `0x18000ae48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aee5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aee5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aed7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aed7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aeac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aeac`

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
0x18000ae48  push    rbx
0x18000ae4a  push    rbp
0x18000ae4b  push    rsi
0x18000ae4c  push    rdi
0x18000ae4d  sub     rsp, 28h
0x18000ae51  mov     rbp, rdx
0x18000ae54  mov     rdi, rcx
0x18000ae57  test    rdx, rdx
0x18000ae5a  jnz     short loc_18000AE9D
0x18000ae5c  mov     rcx, [rcx]
0x18000ae5f  test    rcx, rcx
0x18000ae62  jz      short loc_18000AE96
0x18000ae64  or      eax, 0FFFFFFFFh
0x18000ae67  lock xadd [rcx], eax
0x18000ae6b  cmp     eax, 1
0x18000ae6e  jnz     short loc_18000AE87
0x18000ae70  mov     rbx, [rdi]
0x18000ae73  call    cs:__imp_GetProcessHeap
0x18000ae79  mov     r8, rbx; lpMem
0x18000ae7c  xor     edx, edx; dwFlags
0x18000ae7e  mov     rcx, rax; hHeap
0x18000ae81  call    cs:__imp_HeapFree
0x18000ae87  mov     qword ptr [rdi], 0
0x18000ae8e  mov     qword ptr [rdi+8], 0
0x18000ae96  mov     eax, 1
0x18000ae9b  jmp     short loc_18000AF02
0x18000ae9d  call    cs:__imp_GetProcessHeap
0x18000aea3  lea     r8, [rbp+4]; dwBytes
0x18000aea7  xor     edx, edx; dwFlags
0x18000aea9  mov     rcx, rax; hHeap
0x18000aeac  call    cs:__imp_HeapAlloc
0x18000aeb2  mov     rsi, rax
0x18000aeb5  test    rax, rax
0x18000aeb8  jz      short loc_18000AF02
0x18000aeba  mov     dword ptr [rax], 0
0x18000aec0  mov     rcx, [rdi]
0x18000aec3  test    rcx, rcx
0x18000aec6  jz      short loc_18000AEF3
0x18000aec8  or      eax, 0FFFFFFFFh
0x18000aecb  lock xadd [rcx], eax
0x18000aecf  cmp     eax, 1
0x18000aed2  jnz     short loc_18000AEEB
0x18000aed4  mov     rbx, [rdi]
0x18000aed7  call    cs:__imp_GetProcessHeap
0x18000aedd  mov     r8, rbx; lpMem
0x18000aee0  xor     edx, edx; dwFlags
0x18000aee2  mov     rcx, rax; hHeap
0x18000aee5  call    cs:__imp_HeapFree
0x18000aeeb  mov     qword ptr [rdi+8], 0
0x18000aef3  mov     [rdi], rsi
0x18000aef6  mov     eax, 1
0x18000aefb  mov     [rdi+8], rbp
0x18000aeff  lock add [rsi], eax
0x18000af02  add     rsp, 28h
0x18000af06  pop     rdi
0x18000af07  pop     rsi
0x18000af08  pop     rbp
0x18000af09  pop     rbx
0x18000af0a  retn
```
