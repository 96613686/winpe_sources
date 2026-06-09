# Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)

- ea: `0x18000c830`
- end: `0x18000c849`
- name: `??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `25`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bb28`
- `0x18000cbac`
- `0x180012960`
- `0x180012e00`
- `0x180012f94`
- `0x180013bd0`
- `0x1800148f8`
- `0x180014df0`
- `0x18001b5ef`
- `0x18001b60d`
- `0x18001b66c`
- `0x18001b68a`
- `0x18001b6a8`
- `0x18001b6e7`

## callees

- `0x18000edd8`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::InternalRelease(a1);
}

```

## disassembly

```asm
0x18000c830  mov     [rsp+arg_0], rcx
0x18000c835  sub     rsp, 28h
0x18000c839  mov     rcx, [rsp+28h+arg_0]
0x18000c83e  call    ?InternalRelease@?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::InternalRelease(void)
0x18000c843  nop
0x18000c844  add     rsp, 28h
0x18000c848  retn
```
