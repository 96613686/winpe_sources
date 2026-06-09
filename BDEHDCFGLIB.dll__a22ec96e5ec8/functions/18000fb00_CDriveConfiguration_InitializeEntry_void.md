# CDriveConfiguration::InitializeEntry(void *)

- ea: `0x18000fb00`
- end: `0x18000fb2b`
- name: `?InitializeEntry@CDriveConfiguration@@CAXPEAX@Z`
- size: `43`
- prototype: `void __fastcall(CDriveConfiguration *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000fb00`
- `0x180010800`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18000fb0d`
- `ole32!CoInitializeEx` at `0x18000fb0d`
- `ole32!CoUninitialize` at `0x18000fb1f`
- `ole32!CoUninitialize` at `0x18000fb1f`

## pseudocode

```c
void __fastcall CDriveConfiguration::InitializeEntry(CDriveConfiguration *a1)
{
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    CDriveConfiguration::Thread_Initialize(a1);
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x18000fb00  push    rbx
0x18000fb02  sub     rsp, 20h
0x18000fb06  mov     rbx, rcx
0x18000fb09  xor     edx, edx; dwCoInit
0x18000fb0b  xor     ecx, ecx; pvReserved
0x18000fb0d  call    cs:__imp_CoInitializeEx
0x18000fb13  test    eax, eax
0x18000fb15  js      short loc_18000FB25
0x18000fb17  mov     rcx, rbx; this
0x18000fb1a  call    ?Thread_Initialize@CDriveConfiguration@@AEAAJXZ; CDriveConfiguration::Thread_Initialize(void)
0x18000fb1f  call    cs:__imp_CoUninitialize
0x18000fb25  add     rsp, 20h
0x18000fb29  pop     rbx
0x18000fb2a  retn
```
