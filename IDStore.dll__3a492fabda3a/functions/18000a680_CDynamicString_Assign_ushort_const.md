# CDynamicString::Assign(ushort const *)

- ea: `0x18000a680`
- end: `0x18000a7cf`
- name: `?Assign@CDynamicString@@QEAAJPEBG@Z`
- size: `335`
- prototype: `__int64 __fastcall(CDynamicString *this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007c30`
- `0x180013ff4`
- `0x180017760`
- `0x1800178a4`

## callees

- `0x18000a680`
- `0x18000fb96`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a707`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a787`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a707`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a787`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a7a4`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a7b9`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a7a4`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a7b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a774`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a774`

## pseudocode

```c
__int64 __fastcall CDynamicString::Assign(CDynamicString *this, const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  unsigned int v5; // r14d
  unsigned int v6; // ecx
  unsigned int v7; // ebp
  void *v8; // r15
  unsigned int v9; // r14d
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  unsigned int v12; // r14d
  size_t v13; // rbx
  __int64 v14; // rdx
  void *v16; // rbp
  HANDLE v17; // rax
  LPVOID v18; // rax

  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = *((_DWORD *)this + 3);
  if ( v5 || (v6 = *((_DWORD *)this + 6)) == 0 )
  {
LABEL_5:
    v7 = v4 + 1;
    *((_DWORD *)this + 2) = 0;
    if ( (int)v4 + 1 > v5 )
    {
      v8 = *(void **)this;
      v9 = v7 + (v7 >> 1) + 32;
      ProcessHeap = GetProcessHeap();
      if ( v8 )
        v11 = HeapReAlloc(ProcessHeap, 0, v8, 2 * v9);
      else
        v11 = HeapAlloc(ProcessHeap, 0, 2 * v9);
      if ( !v11 )
        return (unsigned int)-2147024882;
      *(_QWORD *)this = v11;
      *((_DWORD *)this + 3) = v9;
    }
    v12 = 0;
    v13 = 2LL * (unsigned int)v4;
    memcpy_0(*(void **)this, a2, v13);
    v14 = *(_QWORD *)this;
    *((_DWORD *)this + 2) = v7;
    *(_WORD *)(v13 + v14) = 0;
    return v12;
  }
  v16 = *(void **)this;
  v5 = v6 + (v6 >> 1) + 32;
  v17 = GetProcessHeap();
  if ( v16 )
    v18 = HeapReAlloc(v17, 0, v16, 2 * v5);
  else
    v18 = HeapAlloc(v17, 0, 2 * v5);
  if ( v18 )
  {
    *(_QWORD *)this = v18;
    *((_DWORD *)this + 3) = v5;
    goto LABEL_5;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000a680  mov     [rsp+arg_18], rbx
0x18000a685  push    rsi
0x18000a686  push    rdi
0x18000a687  push    r14
0x18000a689  sub     rsp, 20h
0x18000a68d  mov     rdi, rdx
0x18000a690  mov     rsi, rcx
0x18000a693  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a69a  nop     word ptr [rax+rax+00h]
0x18000a6a0  inc     rbx
0x18000a6a3  cmp     word ptr [rdx+rbx*2], 0
0x18000a6a8  jnz     short loc_18000A6A0
0x18000a6aa  mov     r14d, [rcx+0Ch]
0x18000a6ae  mov     [rsp+38h+arg_0], rbp
0x18000a6b3  mov     [rsp+38h+arg_10], r15
0x18000a6b8  test    r14d, r14d
0x18000a6bb  jnz     short loc_18000A6C8
0x18000a6bd  mov     ecx, [rcx+18h]
0x18000a6c0  test    ecx, ecx
0x18000a6c2  jnz     loc_18000A760
0x18000a6c8  lea     ebp, [rbx+1]
0x18000a6cb  mov     dword ptr [rsi+8], 0
0x18000a6d2  cmp     ebp, r14d
0x18000a6d5  jbe     short loc_18000A722
0x18000a6d7  mov     r15, [rsi]
0x18000a6da  mov     r14d, ebp
0x18000a6dd  shr     r14d, 1
0x18000a6e0  add     r14d, 20h ; ' '
0x18000a6e4  mov     [rsp+38h+arg_8], r12
0x18000a6e9  add     r14d, ebp
0x18000a6ec  lea     r12d, [r14+r14]
0x18000a6f0  call    cs:__imp_GetProcessHeap
0x18000a6f6  xor     edx, edx; dwFlags
0x18000a6f8  mov     rcx, rax; hHeap
0x18000a6fb  test    r15, r15
0x18000a6fe  jnz     loc_18000A7B3
0x18000a704  mov     r8d, r12d; dwBytes
0x18000a707  call    cs:__imp_HeapAlloc
0x18000a70d  mov     r12, [rsp+38h+arg_8]
0x18000a712  test    rax, rax
0x18000a715  jz      loc_18000A7C4
0x18000a71b  mov     [rsi], rax
0x18000a71e  mov     [rsi+0Ch], r14d
0x18000a722  mov     ecx, ebx
0x18000a724  mov     rdx, rdi; Src
0x18000a727  xor     r14d, r14d
0x18000a72a  lea     rbx, [rcx+rcx]
0x18000a72e  mov     rcx, [rsi]; void *
0x18000a731  mov     r8, rbx; Size
0x18000a734  call    memcpy_0
0x18000a739  mov     rdx, [rsi]
0x18000a73c  xor     ecx, ecx
0x18000a73e  mov     [rsi+8], ebp
0x18000a741  mov     [rbx+rdx], cx
0x18000a745  mov     eax, r14d
0x18000a748  mov     r15, [rsp+38h+arg_10]
0x18000a74d  mov     rbp, [rsp+38h+arg_0]
0x18000a752  mov     rbx, [rsp+38h+arg_18]
0x18000a757  add     rsp, 20h
0x18000a75b  pop     r14
0x18000a75d  pop     rdi
0x18000a75e  pop     rsi
0x18000a75f  retn
0x18000a760  mov     rbp, [rsi]
0x18000a763  mov     r14d, ecx
0x18000a766  shr     r14d, 1
0x18000a769  add     r14d, 20h ; ' '
0x18000a76d  add     r14d, ecx
0x18000a770  lea     r15d, [r14+r14]
0x18000a774  call    cs:__imp_GetProcessHeap
0x18000a77a  xor     edx, edx; dwFlags
0x18000a77c  mov     rcx, rax; hHeap
0x18000a77f  test    rbp, rbp
0x18000a782  jnz     short loc_18000A79E
0x18000a784  mov     r8d, r15d; dwBytes
0x18000a787  call    cs:__imp_HeapAlloc
0x18000a78d  test    rax, rax
0x18000a790  jz      short loc_18000A7AC
0x18000a792  mov     [rsi], rax
0x18000a795  mov     [rsi+0Ch], r14d
0x18000a799  jmp     loc_18000A6C8
0x18000a79e  mov     r9, r15; dwBytes
0x18000a7a1  mov     r8, rbp; lpMem
0x18000a7a4  call    cs:__imp_HeapReAlloc
0x18000a7aa  jmp     short loc_18000A78D
0x18000a7ac  mov     eax, 8007000Eh
0x18000a7b1  jmp     short loc_18000A748
0x18000a7b3  mov     r9, r12; dwBytes
0x18000a7b6  mov     r8, r15; lpMem
0x18000a7b9  call    cs:__imp_HeapReAlloc
0x18000a7bf  jmp     loc_18000A70D
0x18000a7c4  mov     r14d, 8007000Eh
0x18000a7ca  jmp     loc_18000A745
```
