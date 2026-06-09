# Csl::AcquiredPrivileges::~AcquiredPrivileges(void)

- ea: `0x180024d60`
- end: `0x180024d8b`
- name: `??1AcquiredPrivileges@Csl@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(void **this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004b30`
- `0x18001fb70`
- `0x1800282d4`

## callees

- `0x180024d60`

## import_xrefs

- `ntdll!RtlReleasePrivilege` at `0x180024d71`
- `ntdll!RtlReleasePrivilege` at `0x180024d71`

## pseudocode

```c
void __fastcall Csl::AcquiredPrivileges::~AcquiredPrivileges(void **this)
{
  void *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    RtlReleasePrivilege(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180024d60  push    rbx
0x180024d62  sub     rsp, 20h
0x180024d66  mov     rbx, rcx
0x180024d69  mov     rcx, [rcx]; ReturnedState
0x180024d6c  test    rcx, rcx
0x180024d6f  jz      short loc_180024D84
0x180024d71  call    cs:__imp_RtlReleasePrivilege
0x180024d78  nop     dword ptr [rax+rax+00h]
0x180024d7d  mov     qword ptr [rbx], 0
0x180024d84  add     rsp, 20h
0x180024d88  pop     rbx
0x180024d89  retn
```
