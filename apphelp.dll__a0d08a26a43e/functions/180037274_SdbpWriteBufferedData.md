# SdbpWriteBufferedData

- ea: `0x180037274`
- end: `0x1800373b6`
- name: `SdbpWriteBufferedData`
- size: `322`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003fc80`
- `0x180040584`
- `0x18004098c`
- `0x18004525c`

## callees

- `0x18000f114`
- `0x180018f20`
- `0x180037274`
- `0x18005915d`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800372f1`
- `ntdll!RtlAllocateHeap` at `0x1800372f1`

## string_xrefs

- `0x180037310`: `SdbpWriteBufferedData`
- `0x180037394`: `SdbpWriteBufferedData`

## pseudocode

```c
__int64 __fastcall SdbpWriteBufferedData(__int64 a1, unsigned int a2, const void *a3, unsigned int a4, int a5)
{
  size_t v6; // rbp
  __int64 v8; // r14
  unsigned int v9; // edi
  unsigned int v10; // esi
  PVOID Heap; // rax
  PVOID v12; // r15
  const void *v13; // rdx

  v6 = a4;
  v8 = a2;
  if ( !*(_DWORD *)(a1 + 16) )
  {
    AslLogCallPrintf(1, "SdbpWriteBufferedData", 245, "Invalid parameter");
    return 0;
  }
  v9 = a2 + a4;
  if ( a2 + a4 < a2 )
  {
    AslLogCallPrintf(1, "SdbpWriteBufferedData", 250, "Invalid total buffer size");
    return 0;
  }
  if ( v9 > *(_DWORD *)(a1 + 2656) )
  {
    v10 = v9 + 2048;
    if ( v9 + 2048 < v9 )
    {
      AslLogCallPrintf(1, "SdbpWriteBufferedData", 263, "Invalid new buffer size");
      return 0;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v10);
    v12 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "SdbpWriteBufferedData", 270, "Failed to allocate %d bytes", v9 + 2048);
      return 0;
    }
    v13 = *(const void **)(a1 + 8);
    if ( v13 )
    {
      memcpy_0(Heap, v13, *(unsigned int *)(a1 + 2656));
      AslFree(NtCurrentPeb()->ProcessHeap, *(void **)(a1 + 8));
    }
    *(_QWORD *)(a1 + 8) = v12;
    *(_DWORD *)(a1 + 2656) = v10;
  }
  memcpy_0((void *)(*(_QWORD *)(a1 + 8) + v8), a3, v6);
  if ( !a5 && v9 > *(_DWORD *)(a1 + 20) )
    *(_DWORD *)(a1 + 20) = v9;
  return 1;
}

```

## disassembly

```asm
0x180037274  push    rbx
0x180037276  push    rbp
0x180037277  push    rsi
0x180037278  push    rdi
0x180037279  push    r12
0x18003727b  push    r14
0x18003727d  push    r15
0x18003727f  sub     rsp, 30h
0x180037283  cmp     dword ptr [rcx+10h], 0
0x180037287  mov     r12, r8
0x18003728a  mov     ebp, r9d
0x18003728d  mov     rbx, rcx
0x180037290  mov     r14d, edx
0x180037293  jnz     short loc_1800372A7
0x180037295  lea     r9, aInvalidParamet_1; "Invalid parameter"
0x18003729c  mov     r8d, 0F5h
0x1800372a2  jmp     loc_180037394
0x1800372a7  lea     edi, [r14+rbp]
0x1800372ab  cmp     edi, r14d
0x1800372ae  jb      loc_180037387
0x1800372b4  cmp     edi, [rcx+0A60h]
0x1800372ba  jbe     loc_18003735C
0x1800372c0  lea     esi, [rdi+800h]
0x1800372c6  cmp     esi, edi
0x1800372c8  jnb     short loc_1800372DC
0x1800372ca  lea     r9, aInvalidNewBuff; "Invalid new buffer size"
0x1800372d1  mov     r8d, 107h
0x1800372d7  jmp     loc_180037394
0x1800372dc  mov     rcx, gs:60h
0x1800372e5  mov     edx, 8; Flags
0x1800372ea  mov     r8d, esi; Size
0x1800372ed  mov     rcx, [rcx+30h]; HeapHandle
0x1800372f1  call    cs:__imp_RtlAllocateHeap
0x1800372f7  mov     r15, rax
0x1800372fa  test    rax, rax
0x1800372fd  jnz     short loc_180037324
0x1800372ff  lea     r9, aFailedToAlloca_34; "Failed to allocate %d bytes"
0x180037306  mov     [rsp+68h+var_48], esi
0x18003730a  mov     r8d, 10Eh
0x180037310  lea     rdx, aSdbpwritebuffe; "SdbpWriteBufferedData"
0x180037317  lea     ecx, [rax+1]
0x18003731a  call    AslLogCallPrintf
0x18003731f  jmp     loc_1800373A5
0x180037324  mov     rdx, [rbx+8]; Src
0x180037328  test    rdx, rdx
0x18003732b  jz      short loc_180037352
0x18003732d  mov     r8d, [rbx+0A60h]; Size
0x180037334  mov     rcx, r15; void *
0x180037337  call    memcpy_0
0x18003733c  mov     rcx, gs:60h
0x180037345  mov     rdx, [rbx+8]
0x180037349  mov     rcx, [rcx+30h]
0x18003734d  call    AslFree
0x180037352  mov     [rbx+8], r15
0x180037356  mov     [rbx+0A60h], esi
0x18003735c  mov     rcx, r14
0x18003735f  mov     r8, rbp; Size
0x180037362  add     rcx, [rbx+8]; void *
0x180037366  mov     rdx, r12; Src
0x180037369  call    memcpy_0
0x18003736e  cmp     [rsp+68h+arg_20], 0
0x180037376  jnz     short loc_180037380
0x180037378  cmp     edi, [rbx+14h]
0x18003737b  jbe     short loc_180037380
0x18003737d  mov     [rbx+14h], edi
0x180037380  mov     eax, 1
0x180037385  jmp     short loc_1800373A7
0x180037387  lea     r9, aInvalidTotalBu; "Invalid total buffer size"
0x18003738e  mov     r8d, 0FAh
0x180037394  lea     rdx, aSdbpwritebuffe; "SdbpWriteBufferedData"
0x18003739b  mov     ecx, 1
0x1800373a0  call    AslLogCallPrintf
0x1800373a5  xor     eax, eax
0x1800373a7  add     rsp, 30h
0x1800373ab  pop     r15
0x1800373ad  pop     r14
0x1800373af  pop     r12
0x1800373b1  pop     rdi
0x1800373b2  pop     rsi
0x1800373b3  pop     rbp
0x1800373b4  pop     rbx
0x1800373b5  retn
```
