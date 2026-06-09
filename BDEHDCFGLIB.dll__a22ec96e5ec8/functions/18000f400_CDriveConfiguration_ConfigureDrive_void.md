# CDriveConfiguration::ConfigureDrive(void)

- ea: `0x18000f400`
- end: `0x18000f41d`
- name: `?ConfigureDrive@CDriveConfiguration@@QEAAJXZ`
- size: `29`
- prototype: `__int64 __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `msvcrt!_beginthread` at `0x18000f410`
- `msvcrt!_beginthread` at `0x18000f410`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::ConfigureDrive(CDriveConfiguration *this)
{
  _beginthread(CDriveConfiguration::DriveConfigurationEntry, 0, this);
  return 0;
}

```

## disassembly

```asm
0x18000f400  sub     rsp, 28h
0x18000f404  mov     r8, rcx; ArgList
0x18000f407  xor     edx, edx; StackSize
0x18000f409  lea     rcx, ?DriveConfigurationEntry@CDriveConfiguration@@CAXPEAX@Z; StartAddress
0x18000f410  call    cs:__imp__beginthread
0x18000f416  xor     eax, eax
0x18000f418  add     rsp, 28h
0x18000f41c  retn
```
