# CDriveConfiguration::CancelConfiguration(void)

- ea: `0x18000f210`
- end: `0x18000f231`
- name: `?CancelConfiguration@CDriveConfiguration@@QEAAJXZ`
- size: `33`
- prototype: `__int64 __fastcall(CDriveConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `msvcrt!_beginthread` at `0x18000f224`
- `msvcrt!_beginthread` at `0x18000f224`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::CancelConfiguration(CDriveConfiguration *this)
{
  *((_BYTE *)this + 12) = 1;
  _beginthread(CDriveConfiguration::CancelConfigurationEntry, 0, this);
  return 0;
}

```

## disassembly

```asm
0x18000f210  sub     rsp, 28h
0x18000f214  mov     byte ptr [rcx+0Ch], 1
0x18000f218  mov     r8, rcx; ArgList
0x18000f21b  lea     rcx, ?CancelConfigurationEntry@CDriveConfiguration@@CAXPEAX@Z; StartAddress
0x18000f222  xor     edx, edx; StackSize
0x18000f224  call    cs:__imp__beginthread
0x18000f22a  xor     eax, eax
0x18000f22c  add     rsp, 28h
0x18000f230  retn
```
