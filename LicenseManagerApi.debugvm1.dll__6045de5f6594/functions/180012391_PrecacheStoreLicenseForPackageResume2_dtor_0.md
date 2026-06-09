# PrecacheStoreLicenseForPackageResume2$dtor$0

- ea: `0x180012391`
- end: `0x18001239d`
- name: `PrecacheStoreLicenseForPackageResume2$dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006b04`

## pseudocode

```c
__int64 __fastcall PrecacheStoreLicenseForPackageResume2_dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::~HandleT<LocalAllocStringBufferTraits>(a2 + 128);
}

```

## disassembly

```asm
0x180012391  lea     rcx, [rdx+80h]
0x180012398  jmp     ??1?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::~HandleT<LocalAllocStringBufferTraits>(void)
```
