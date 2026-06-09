# CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::~CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>(void)

- ea: `0x180013c28`
- end: `0x180013c8a`
- name: `??1?$CPtrArrayTemplate@VCCertChainList@@U?$AutoPtrTraits@VCCertChainList@@@@@@QEAA@XZ`
- size: `98`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013be8`
- `0x180014c2c`

## callees

- `0x18000b870`
- `0x180013c28`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>::~CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>(
        __int64 a1)
{
  int v2; // esi
  __int64 i; // rdi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  if ( *(_QWORD *)a1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    for ( i = 0; (int)i < v2; i = (unsigned int)(i + 1) )
    {
      v4 = *(void (__fastcall ****)(_QWORD, __int64))(*(_QWORD *)a1 + 8 * i);
      if ( v4 )
        (**v4)(v4, 1);
    }
  }
  CDynamicArray<CCertChainList *>::RemoveAll(a1);
  return CDynamicArray<CCertChainList *>::RemoveAll(a1);
}

```

## disassembly

```asm
0x180013c28  mov     [rsp+arg_0], rbx
0x180013c2d  mov     [rsp+arg_8], rsi
0x180013c32  push    rdi
0x180013c33  sub     rsp, 20h
0x180013c37  cmp     qword ptr [rcx], 0
0x180013c3b  mov     rbx, rcx
0x180013c3e  jz      short loc_180013C6B
0x180013c40  mov     esi, [rcx+8]
0x180013c43  xor     edi, edi
0x180013c45  test    esi, esi
0x180013c47  jle     short loc_180013C6B
0x180013c49  mov     rax, [rbx]
0x180013c4c  mov     rcx, [rax+rdi*8]
0x180013c50  test    rcx, rcx
0x180013c53  jz      short loc_180013C65
0x180013c55  mov     rax, [rcx]
0x180013c58  mov     edx, 1
0x180013c5d  mov     rax, [rax]
0x180013c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c65  inc     edi
0x180013c67  cmp     edi, esi
0x180013c69  jl      short loc_180013C49
0x180013c6b  mov     rcx, rbx
0x180013c6e  call    ?RemoveAll@?$CDynamicArray@PEAVCCertChainList@@@@QEAAXXZ; CDynamicArray<CCertChainList *>::RemoveAll(void)
0x180013c73  mov     rcx, rbx
0x180013c76  mov     rbx, [rsp+28h+arg_0]
0x180013c7b  mov     rsi, [rsp+28h+arg_8]
0x180013c80  add     rsp, 20h
0x180013c84  pop     rdi
0x180013c85  jmp     ?RemoveAll@?$CDynamicArray@PEAVCCertChainList@@@@QEAAXXZ; CDynamicArray<CCertChainList *>::RemoveAll(void)
```
