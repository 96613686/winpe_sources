# CDriveConfiguration::DriveConfigurationEntry(void *)

- ea: `0x18000f890`
- end: `0x18000f8bb`
- name: `?DriveConfigurationEntry@CDriveConfiguration@@CAXPEAX@Z`
- size: `43`
- prototype: `void __fastcall(CDriveConfiguration *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000f890`
- `0x1800101a0`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18000f89d`
- `ole32!CoInitializeEx` at `0x18000f89d`
- `ole32!CoUninitialize` at `0x18000f8af`
- `ole32!CoUninitialize` at `0x18000f8af`

## pseudocode

```c
void __fastcall CDriveConfiguration::DriveConfigurationEntry(CDriveConfiguration *a1)
{
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    CDriveConfiguration::Thread_ConfigureDrive(a1);
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x18000f890  push    rbx
0x18000f892  sub     rsp, 20h
0x18000f896  mov     rbx, rcx
0x18000f899  xor     edx, edx; dwCoInit
0x18000f89b  xor     ecx, ecx; pvReserved
0x18000f89d  call    cs:__imp_CoInitializeEx
0x18000f8a3  test    eax, eax
0x18000f8a5  js      short loc_18000F8B5
0x18000f8a7  mov     rcx, rbx; this
0x18000f8aa  call    ?Thread_ConfigureDrive@CDriveConfiguration@@AEAAJXZ; CDriveConfiguration::Thread_ConfigureDrive(void)
0x18000f8af  call    cs:__imp_CoUninitialize
0x18000f8b5  add     rsp, 20h
0x18000f8b9  pop     rbx
0x18000f8ba  retn
```
