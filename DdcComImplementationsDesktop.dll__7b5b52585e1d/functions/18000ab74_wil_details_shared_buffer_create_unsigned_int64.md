# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000ab74`
- end: `0x18000ac37`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800098e8`
- `0x18000ad30`

## callees

- `0x18000ab74`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000abad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000abad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000abc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000abc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac03`

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
0x18000ab74  push    rbx
0x18000ab76  push    rbp
0x18000ab77  push    rsi
0x18000ab78  push    rdi
0x18000ab79  sub     rsp, 28h
0x18000ab7d  mov     rbp, rdx
0x18000ab80  mov     rdi, rcx
0x18000ab83  test    rdx, rdx
0x18000ab86  jnz     short loc_18000ABC9
0x18000ab88  mov     rcx, [rcx]
0x18000ab8b  test    rcx, rcx
0x18000ab8e  jz      short loc_18000ABC2
0x18000ab90  or      eax, 0FFFFFFFFh
0x18000ab93  lock xadd [rcx], eax
0x18000ab97  cmp     eax, 1
0x18000ab9a  jnz     short loc_18000ABB3
0x18000ab9c  mov     rbx, [rdi]
0x18000ab9f  call    cs:__imp_GetProcessHeap
0x18000aba5  mov     r8, rbx; lpMem
0x18000aba8  xor     edx, edx; dwFlags
0x18000abaa  mov     rcx, rax; hHeap
0x18000abad  call    cs:__imp_HeapFree
0x18000abb3  mov     qword ptr [rdi], 0
0x18000abba  mov     qword ptr [rdi+8], 0
0x18000abc2  mov     eax, 1
0x18000abc7  jmp     short loc_18000AC2E
0x18000abc9  call    cs:__imp_GetProcessHeap
0x18000abcf  lea     r8, [rbp+4]; dwBytes
0x18000abd3  xor     edx, edx; dwFlags
0x18000abd5  mov     rcx, rax; hHeap
0x18000abd8  call    cs:__imp_HeapAlloc
0x18000abde  mov     rsi, rax
0x18000abe1  test    rax, rax
0x18000abe4  jz      short loc_18000AC2E
0x18000abe6  mov     dword ptr [rax], 0
0x18000abec  mov     rcx, [rdi]
0x18000abef  test    rcx, rcx
0x18000abf2  jz      short loc_18000AC1F
0x18000abf4  or      eax, 0FFFFFFFFh
0x18000abf7  lock xadd [rcx], eax
0x18000abfb  cmp     eax, 1
0x18000abfe  jnz     short loc_18000AC17
0x18000ac00  mov     rbx, [rdi]
0x18000ac03  call    cs:__imp_GetProcessHeap
0x18000ac09  mov     r8, rbx; lpMem
0x18000ac0c  xor     edx, edx; dwFlags
0x18000ac0e  mov     rcx, rax; hHeap
0x18000ac11  call    cs:__imp_HeapFree
0x18000ac17  mov     qword ptr [rdi+8], 0
0x18000ac1f  mov     [rdi], rsi
0x18000ac22  mov     eax, 1
0x18000ac27  mov     [rdi+8], rbp
0x18000ac2b  lock add [rsi], eax
0x18000ac2e  add     rsp, 28h
0x18000ac32  pop     rdi
0x18000ac33  pop     rsi
0x18000ac34  pop     rbp
0x18000ac35  pop     rbx
0x18000ac36  retn
```
