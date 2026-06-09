# CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::RemoveAll(void)

- ea: `0x18000b810`
- end: `0x18000b86a`
- name: `?RemoveAll@?$CPtrArrayTemplate@VCProviderEntry@@U?$AutoPtrTraits@VCProviderEntry@@@@@@QEAAXXZ`
- size: `90`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c65c`
- `0x180013c90`

## callees

- `0x18000b810`
- `0x18000b870`
- `0x18001b010`

## pseudocode

```c
void __fastcall CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::RemoveAll(__int64 a1)
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
}

```

## disassembly

```asm
0x18000b810  mov     [rsp+arg_0], rbx
0x18000b815  mov     [rsp+arg_8], rsi
0x18000b81a  push    rdi
0x18000b81b  sub     rsp, 20h
0x18000b81f  cmp     qword ptr [rcx], 0
0x18000b823  mov     rbx, rcx
0x18000b826  jz      short loc_18000B853
0x18000b828  mov     esi, [rcx+8]
0x18000b82b  xor     edi, edi
0x18000b82d  test    esi, esi
0x18000b82f  jle     short loc_18000B853
0x18000b831  mov     rax, [rbx]
0x18000b834  mov     rcx, [rax+rdi*8]
0x18000b838  test    rcx, rcx
0x18000b83b  jz      short loc_18000B84D
0x18000b83d  mov     rax, [rcx]
0x18000b840  mov     edx, 1
0x18000b845  mov     rax, [rax]
0x18000b848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b84d  inc     edi
0x18000b84f  cmp     edi, esi
0x18000b851  jl      short loc_18000B831
0x18000b853  mov     rcx, rbx
0x18000b856  mov     rbx, [rsp+28h+arg_0]
0x18000b85b  mov     rsi, [rsp+28h+arg_8]
0x18000b860  add     rsp, 20h
0x18000b864  pop     rdi
0x18000b865  jmp     ?RemoveAll@?$CDynamicArray@PEAVCCertChainList@@@@QEAAXXZ; CDynamicArray<CCertChainList *>::RemoveAll(void)
```
