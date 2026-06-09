# OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::~CustomInstallActionWinRTHelper(void)

- ea: `0x1400084d0`
- end: `0x1400084ef`
- name: `??1CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400086ac`

## callees

- `0x1400084a0`
- `0x1400098dc`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::~CustomInstallActionWinRTHelper(
        OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *this)
{
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease((char *)this + 88);
  OSIntegration::DEH::Internal::CustomInstallAction::~CustomInstallAction(this);
}

```

## disassembly

```asm
0x1400084d0  push    rbx
0x1400084d2  sub     rsp, 20h
0x1400084d6  mov     rbx, rcx
0x1400084d9  add     rcx, 58h ; 'X'
0x1400084dd  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x1400084e2  mov     rcx, rbx; this
0x1400084e5  add     rsp, 20h
0x1400084e9  pop     rbx
0x1400084ea  jmp     ??1CustomInstallAction@Internal@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::Internal::CustomInstallAction::~CustomInstallAction(void)
```
