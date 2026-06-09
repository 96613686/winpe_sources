# HrAlloc(void * *,ulong)

- ea: `0x180001740`
- end: `0x180001776`
- name: `?HrAlloc@@YAJPEAPEAXK@Z`
- size: `54`
- prototype: `__int64 __fastcall(void **, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b390`
- `0x18000d220`
- `0x18000f440`
- `0x18000ff30`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall HrAlloc(void **a1, unsigned int a2)
{
  void *v3; // rax
  unsigned int v4; // ecx

  v3 = (void *)((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, a2);
  v4 = 0;
  *a1 = v3;
  if ( !v3 )
    return (unsigned int)-2147024882;
  return v4;
}

```

## disassembly

```asm
0x180001740  push    rbx
0x180001742  sub     rsp, 20h
0x180001746  mov     rbx, rcx
0x180001749  mov     edx, edx
0x18000174b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180001752  mov     rax, [rcx]
0x180001755  mov     rax, [rax+18h]
0x180001759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000175e  xor     ecx, ecx
0x180001760  mov     [rbx], rax
0x180001763  test    rax, rax
0x180001766  mov     edx, 8007000Eh
0x18000176b  cmovz   ecx, edx
0x18000176e  mov     eax, ecx
0x180001770  add     rsp, 20h
0x180001774  pop     rbx
0x180001775  retn
```
