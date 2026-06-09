# CDriveConfiguration::CancelConfigurationEntry(void *)

- ea: `0x18000f240`
- end: `0x18000f26f`
- name: `?CancelConfigurationEntry@CDriveConfiguration@@CAXPEAX@Z`
- size: `47`
- prototype: `void __fastcall(CDriveConfiguration *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000f240`
- `0x18000f280`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18000f251`
- `ole32!CoInitializeEx` at `0x18000f251`
- `ole32!CoUninitialize` at `0x18000f263`
- `ole32!CoUninitialize` at `0x18000f263`

## pseudocode

```c
void __fastcall CDriveConfiguration::CancelConfigurationEntry(CDriveConfiguration *a1)
{
  if ( a1 )
  {
    if ( CoInitializeEx(0, 0) >= 0 )
    {
      CDriveConfiguration::CancelConfiguration_Thread(a1);
      CoUninitialize();
    }
  }
}

```

## disassembly

```asm
0x18000f240  test    rcx, rcx
0x18000f243  jz      short locret_18000F26E
0x18000f245  push    rbx
0x18000f246  sub     rsp, 20h
0x18000f24a  mov     rbx, rcx
0x18000f24d  xor     edx, edx; dwCoInit
0x18000f24f  xor     ecx, ecx; pvReserved
0x18000f251  call    cs:__imp_CoInitializeEx
0x18000f257  test    eax, eax
0x18000f259  js      short loc_18000F269
0x18000f25b  mov     rcx, rbx; this
0x18000f25e  call    ?CancelConfiguration_Thread@CDriveConfiguration@@AEAAJXZ; CDriveConfiguration::CancelConfiguration_Thread(void)
0x18000f263  call    cs:__imp_CoUninitialize
0x18000f269  add     rsp, 20h
0x18000f26d  pop     rbx
0x18000f26e  retn
```
