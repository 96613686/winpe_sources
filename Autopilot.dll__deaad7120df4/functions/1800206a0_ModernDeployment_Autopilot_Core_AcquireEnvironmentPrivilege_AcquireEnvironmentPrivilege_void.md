# ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::~AcquireEnvironmentPrivilege(void)

- ea: `0x1800206a0`
- end: `0x1800206be`
- name: `??1AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a12d`

## callees

- `0x1800206a0`

## import_xrefs

- `ntdll!RtlReleasePrivilege` at `0x1800206ac`
- `ntdll!RtlReleasePrivilege` at `0x1800206ac`

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
0x1800206a0  sub     rsp, 28h
0x1800206a4  mov     rcx, [rcx]; ReturnedState
0x1800206a7  test    rcx, rcx
0x1800206aa  jz      short loc_1800206B8
0x1800206ac  call    cs:__imp_RtlReleasePrivilege
0x1800206b3  nop     dword ptr [rax+rax+00h]
0x1800206b8  add     rsp, 28h
0x1800206bc  retn
```
