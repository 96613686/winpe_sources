# CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::~CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>(void)

- ea: `0x180013c90`
- end: `0x180013cab`
- name: `??1?$CPtrArrayTemplate@VCProviderEntry@@U?$AutoPtrTraits@VCProviderEntry@@@@@@QEAA@XZ`
- size: `27`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013cb4`

## callees

- `0x18000b810`
- `0x18000b870`

## pseudocode

```c
__int64 __fastcall CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::~CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>(
        __int64 a1)
{
  CPtrArrayTemplate<CProviderEntry,AutoPtrTraits<CProviderEntry>>::RemoveAll();
  return CDynamicArray<CCertChainList *>::RemoveAll(a1);
}

```

## disassembly

```asm
0x180013c90  push    rbx
0x180013c92  sub     rsp, 20h
0x180013c96  mov     rbx, rcx
0x180013c99  call    ?RemoveAll@?$CPtrArrayTemplate@VCProviderEntry@@U?$AutoPtrTraits@VCProviderEntry@@@@@@QEAAXXZ
0x180013c9e  mov     rcx, rbx
0x180013ca1  add     rsp, 20h
0x180013ca5  pop     rbx
0x180013ca6  jmp     ?RemoveAll@?$CDynamicArray@PEAVCCertChainList@@@@QEAAXXZ
```
