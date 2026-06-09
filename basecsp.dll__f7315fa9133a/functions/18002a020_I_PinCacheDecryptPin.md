# I_PinCacheDecryptPin

- ea: `0x18002a020`
- end: `0x18002a0c8`
- name: `I_PinCacheDecryptPin`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a368`
- `0x18002a9d0`

## callees

- `0x18000a766`
- `0x18002a020`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a0ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a0ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a0a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a0a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a05a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a05a`
- `CRYPTBASE!SystemFunction041` at `0x18002a084`
- `CRYPTBASE!SystemFunction041` at `0x18002a084`

## pseudocode

```c
__int64 __fastcall I_PinCacheDecryptPin(__int64 a1, void **a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  SIZE_T v9; // r8
  void *v10; // rax
  void *v11; // rbp
  void *v12; // rsi
  HANDLE v13; // rax

  if ( *(_DWORD *)(a1 + 24) )
  {
    v7 = *(_DWORD *)(a1 + 24);
    ProcessHeap = GetProcessHeap();
    v9 = v7;
    v6 = 8;
    v10 = HeapAlloc(ProcessHeap, 8u, v9);
    *a2 = v10;
    v11 = v10;
    if ( !v10
      || (memcpy_0(v10, *(const void **)(a1 + 16), *(unsigned int *)(a1 + 24)),
          (v6 = SystemFunction041(v11, *(_DWORD *)(a1 + 24), 0)) != 0) )
    {
      v12 = *a2;
      if ( *a2 )
      {
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v12);
        *a2 = 0;
      }
    }
    else
    {
      *a3 = *(_DWORD *)(a1 + 28);
    }
  }
  else
  {
    v6 = 0;
    *a2 = 0;
    *a3 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18002a020  push    rbx
0x18002a022  push    rbp
0x18002a023  push    rsi
0x18002a024  push    rdi
0x18002a025  push    r14
0x18002a027  sub     rsp, 20h
0x18002a02b  cmp     dword ptr [rcx+18h], 0
0x18002a02f  mov     r14, r8
0x18002a032  mov     rdi, rdx
0x18002a035  mov     rsi, rcx
0x18002a038  jnz     short loc_18002A044
0x18002a03a  xor     ebx, ebx
0x18002a03c  mov     [rdx], rbx
0x18002a03f  mov     [r8], ebx
0x18002a042  jmp     short loc_18002A0BB
0x18002a044  mov     ebx, [rcx+18h]
0x18002a047  call    cs:__imp_GetProcessHeap
0x18002a04d  mov     r8d, ebx; dwBytes
0x18002a050  mov     ebx, 8
0x18002a055  mov     edx, ebx; dwFlags
0x18002a057  mov     rcx, rax; hHeap
0x18002a05a  call    cs:__imp_HeapAlloc
0x18002a060  mov     [rdi], rax
0x18002a063  mov     rbp, rax
0x18002a066  test    rax, rax
0x18002a069  jz      short loc_18002A098
0x18002a06b  mov     r8d, [rsi+18h]; Size
0x18002a06f  mov     rcx, rax; void *
0x18002a072  mov     rdx, [rsi+10h]; Src
0x18002a076  call    memcpy_0
0x18002a07b  mov     edx, [rsi+18h]; MemorySize
0x18002a07e  xor     r8d, r8d; OptionFlags
0x18002a081  mov     rcx, rbp; Memory
0x18002a084  call    cs:__imp_SystemFunction041
0x18002a08a  mov     ebx, eax
0x18002a08c  test    eax, eax
0x18002a08e  jnz     short loc_18002A098
0x18002a090  mov     ecx, [rsi+1Ch]
0x18002a093  mov     [r14], ecx
0x18002a096  jmp     short loc_18002A0BB
0x18002a098  mov     rsi, [rdi]
0x18002a09b  test    rsi, rsi
0x18002a09e  jz      short loc_18002A0BB
0x18002a0a0  call    cs:__imp_GetProcessHeap
0x18002a0a6  mov     r8, rsi; lpMem
0x18002a0a9  xor     edx, edx; dwFlags
0x18002a0ab  mov     rcx, rax; hHeap
0x18002a0ae  call    cs:__imp_HeapFree
0x18002a0b4  mov     qword ptr [rdi], 0
0x18002a0bb  mov     eax, ebx
0x18002a0bd  add     rsp, 20h
0x18002a0c1  pop     r14
0x18002a0c3  pop     rdi
0x18002a0c4  pop     rsi
0x18002a0c5  pop     rbp
0x18002a0c6  pop     rbx
0x18002a0c7  retn
```
