# PrecacheStoreLicenseForPackageResume2$dtor$2

- ea: `0x180012565`
- end: `0x180012571`
- name: `PrecacheStoreLicenseForPackageResume2$dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006ab0`

## pseudocode

```c
__int64 __fastcall PrecacheStoreLicenseForPackageResume2_dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::~HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>(a2 + 112);
}

```

## disassembly

```asm
0x180012565  lea     rcx, [rdx+70h]
0x18001256c  jmp     ??1?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::~HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>(void)
```
