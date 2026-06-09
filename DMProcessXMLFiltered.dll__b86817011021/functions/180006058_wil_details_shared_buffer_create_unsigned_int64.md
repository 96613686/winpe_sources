# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180006058`
- end: `0x18000611b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800054d0`
- `0x180006130`

## callees

- `0x180006058`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006083`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006083`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006091`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006091`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800060bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800060bc`

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
0x180006058  push    rbx
0x18000605a  push    rbp
0x18000605b  push    rsi
0x18000605c  push    rdi
0x18000605d  sub     rsp, 28h
0x180006061  mov     rbp, rdx
0x180006064  mov     rdi, rcx
0x180006067  test    rdx, rdx
0x18000606a  jnz     short loc_1800060AD
0x18000606c  mov     rcx, [rcx]
0x18000606f  test    rcx, rcx
0x180006072  jz      short loc_1800060A6
0x180006074  or      eax, 0FFFFFFFFh
0x180006077  lock xadd [rcx], eax
0x18000607b  cmp     eax, 1
0x18000607e  jnz     short loc_180006097
0x180006080  mov     rbx, [rdi]
0x180006083  call    cs:__imp_GetProcessHeap
0x180006089  mov     r8, rbx; lpMem
0x18000608c  xor     edx, edx; dwFlags
0x18000608e  mov     rcx, rax; hHeap
0x180006091  call    cs:__imp_HeapFree
0x180006097  mov     qword ptr [rdi], 0
0x18000609e  mov     qword ptr [rdi+8], 0
0x1800060a6  mov     eax, 1
0x1800060ab  jmp     short loc_180006112
0x1800060ad  call    cs:__imp_GetProcessHeap
0x1800060b3  lea     r8, [rbp+4]; dwBytes
0x1800060b7  xor     edx, edx; dwFlags
0x1800060b9  mov     rcx, rax; hHeap
0x1800060bc  call    cs:__imp_HeapAlloc
0x1800060c2  mov     rsi, rax
0x1800060c5  test    rax, rax
0x1800060c8  jz      short loc_180006112
0x1800060ca  mov     dword ptr [rax], 0
0x1800060d0  mov     rcx, [rdi]
0x1800060d3  test    rcx, rcx
0x1800060d6  jz      short loc_180006103
0x1800060d8  or      eax, 0FFFFFFFFh
0x1800060db  lock xadd [rcx], eax
0x1800060df  cmp     eax, 1
0x1800060e2  jnz     short loc_1800060FB
0x1800060e4  mov     rbx, [rdi]
0x1800060e7  call    cs:__imp_GetProcessHeap
0x1800060ed  mov     r8, rbx; lpMem
0x1800060f0  xor     edx, edx; dwFlags
0x1800060f2  mov     rcx, rax; hHeap
0x1800060f5  call    cs:__imp_HeapFree
0x1800060fb  mov     qword ptr [rdi+8], 0
0x180006103  mov     [rdi], rsi
0x180006106  mov     eax, 1
0x18000610b  mov     [rdi+8], rbp
0x18000610f  lock add [rsi], eax
0x180006112  add     rsp, 28h
0x180006116  pop     rdi
0x180006117  pop     rsi
0x180006118  pop     rbp
0x180006119  pop     rbx
0x18000611a  retn
```
