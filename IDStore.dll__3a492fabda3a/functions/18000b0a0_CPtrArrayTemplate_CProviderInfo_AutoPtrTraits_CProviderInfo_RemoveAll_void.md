# CPtrArrayTemplate<CProviderInfo,AutoPtrTraits<CProviderInfo>>::RemoveAll(void)

- ea: `0x18000b0a0`
- end: `0x18000b1ab`
- name: `?RemoveAll@?$CPtrArrayTemplate@VCProviderInfo@@U?$AutoPtrTraits@VCProviderInfo@@@@@@QEAAXXZ`
- size: `267`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ae70`
- `0x18000afb0`
- `0x180018fb8`

## callees

- `0x18000b0a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b160`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b160`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b11c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b187`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b11c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b187`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b105`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b12a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b14f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b195`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b105`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b12a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b14f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b195`

## pseudocode

```c
void __fastcall CPtrArrayTemplate<CProviderInfo,AutoPtrTraits<CProviderInfo>>::RemoveAll(__int64 a1)
{
  int v2; // ebx
  int v3; // ebp
  _QWORD *v4; // rdi
  void *v5; // r14
  HANDLE ProcessHeap; // rax
  void *v7; // r14
  HANDLE v8; // rax
  void *v9; // r14
  HANDLE v10; // rax
  void *v11; // rbx
  HANDLE v12; // rax

  if ( *(_QWORD *)a1 )
  {
    v2 = 0;
    v3 = *(_DWORD *)(a1 + 8);
    if ( v3 > 0 )
    {
      do
      {
        v4 = *(_QWORD **)(*(_QWORD *)a1 + 8LL * (unsigned int)v2);
        if ( v4 )
        {
          v5 = (void *)v4[10];
          if ( v5 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v5);
            v4[10] = 0;
            v4[11] = 0;
          }
          v7 = (void *)v4[6];
          if ( v7 )
          {
            v8 = GetProcessHeap();
            HeapFree(v8, 0, v7);
            v4[6] = 0;
            v4[7] = 0;
          }
          v9 = (void *)v4[2];
          if ( v9 )
          {
            v10 = GetProcessHeap();
            HeapFree(v10, 0, v9);
            v4[2] = 0;
            v4[3] = 0;
          }
          operator delete(v4);
        }
        ++v2;
      }
      while ( v2 < v3 );
    }
  }
  v11 = *(void **)a1;
  if ( *(_QWORD *)a1 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000b0a0  push    rbx
0x18000b0a2  push    rsi
0x18000b0a3  push    r15
0x18000b0a5  sub     rsp, 20h
0x18000b0a9  xor     r15d, r15d
0x18000b0ac  mov     rsi, rcx
0x18000b0af  cmp     [rcx], r15
0x18000b0b2  jz      loc_18000B17F
0x18000b0b8  mov     [rsp+38h+arg_0], rbp
0x18000b0bd  mov     ebx, r15d
0x18000b0c0  mov     ebp, [rcx+8]
0x18000b0c3  test    ebp, ebp
0x18000b0c5  jle     loc_18000B17A
0x18000b0cb  mov     [rsp+38h+arg_8], rdi
0x18000b0d0  mov     [rsp+38h+arg_10], r14
0x18000b0d5  nop     word ptr [rax+rax+00000000h]
0x18000b0e0  mov     rax, [rsi]
0x18000b0e3  mov     edx, ebx
0x18000b0e5  mov     rdi, [rax+rdx*8]
0x18000b0e9  test    rdi, rdi
0x18000b0ec  jz      short loc_18000B166
0x18000b0ee  mov     r14, [rdi+50h]
0x18000b0f2  test    r14, r14
0x18000b0f5  jz      short loc_18000B113
0x18000b0f7  call    cs:__imp_GetProcessHeap
0x18000b0fd  mov     r8, r14; lpMem
0x18000b100  xor     edx, edx; dwFlags
0x18000b102  mov     rcx, rax; hHeap
0x18000b105  call    cs:__imp_HeapFree
0x18000b10b  mov     [rdi+50h], r15
0x18000b10f  mov     [rdi+58h], r15
0x18000b113  mov     r14, [rdi+30h]
0x18000b117  test    r14, r14
0x18000b11a  jz      short loc_18000B138
0x18000b11c  call    cs:__imp_GetProcessHeap
0x18000b122  mov     r8, r14; lpMem
0x18000b125  xor     edx, edx; dwFlags
0x18000b127  mov     rcx, rax; hHeap
0x18000b12a  call    cs:__imp_HeapFree
0x18000b130  mov     [rdi+30h], r15
0x18000b134  mov     [rdi+38h], r15
0x18000b138  mov     r14, [rdi+10h]
0x18000b13c  test    r14, r14
0x18000b13f  jz      short loc_18000B15D
0x18000b141  call    cs:__imp_GetProcessHeap
0x18000b147  mov     r8, r14; lpMem
0x18000b14a  xor     edx, edx; dwFlags
0x18000b14c  mov     rcx, rax; hHeap
0x18000b14f  call    cs:__imp_HeapFree
0x18000b155  mov     [rdi+10h], r15
0x18000b159  mov     [rdi+18h], r15
0x18000b15d  mov     rcx, rdi
0x18000b160  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b166  inc     ebx
0x18000b168  cmp     ebx, ebp
0x18000b16a  jl      loc_18000B0E0
0x18000b170  mov     r14, [rsp+38h+arg_10]
0x18000b175  mov     rdi, [rsp+38h+arg_8]
0x18000b17a  mov     rbp, [rsp+38h+arg_0]
0x18000b17f  mov     rbx, [rsi]
0x18000b182  test    rbx, rbx
0x18000b185  jz      short loc_18000B1A2
0x18000b187  call    cs:__imp_GetProcessHeap
0x18000b18d  mov     r8, rbx; lpMem
0x18000b190  xor     edx, edx; dwFlags
0x18000b192  mov     rcx, rax; hHeap
0x18000b195  call    cs:__imp_HeapFree
0x18000b19b  mov     [rsi], r15
0x18000b19e  mov     [rsi+8], r15
0x18000b1a2  add     rsp, 20h
0x18000b1a6  pop     r15
0x18000b1a8  pop     rsi
0x18000b1a9  pop     rbx
0x18000b1aa  retn
```
