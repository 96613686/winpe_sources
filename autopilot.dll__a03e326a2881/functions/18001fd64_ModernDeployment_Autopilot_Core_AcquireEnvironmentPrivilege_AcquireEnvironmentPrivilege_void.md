# ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::~AcquireEnvironmentPrivilege(void)

- ea: `0x18001fd64`
- end: `0x18001fd7b`
- name: `??1AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180028e43`

## callees

- `0x18001fd64`

## import_xrefs

- `ntdll!RtlReleasePrivilege` at `0x18001fd70`
- `ntdll!RtlReleasePrivilege` at `0x18001fd70`

## pseudocode

```c
void __fastcall ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::~AcquireEnvironmentPrivilege(
        void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    RtlReleasePrivilege(v1);
}

```

## disassembly

```asm
0x18001fd64  sub     rsp, 28h
0x18001fd68  mov     rcx, [rcx]; ReturnedState
0x18001fd6b  test    rcx, rcx
0x18001fd6e  jz      short loc_18001FD76
0x18001fd70  call    cs:__imp_RtlReleasePrivilege
0x18001fd76  add     rsp, 28h
0x18001fd7a  retn
```
