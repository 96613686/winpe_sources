# FxDriverEntryWorker

- ea: `0x140008d94`
- end: `0x140008efc`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008d60`

## callees

- `0x140008c5c`
- `0x140008d94`
- `0x140008f44`
- `0x1400090d0`
- `0x14000a6c0`
- `0x14001903c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140008e50`
- `ntoskrnl!DbgPrintEx` at `0x140008e50`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140008dd5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140008dd5`
- `WDFLDR!WdfLdrQueryInterface` at `0x140008e96`
- `WDFLDR!WdfLdrQueryInterface` at `0x140008e96`
- `WDFLDR!WdfVersionBind` at `0x140008df5`
- `WDFLDR!WdfVersionBind` at `0x140008df5`

## pseudocode

```c
NTSTATUS __fastcall FxDriverEntryWorker(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  struct _WDF_BIND_INFO *v5; // rcx
  int inited; // ebx
  NTSTATUS v7; // eax
  GUID *v8; // [rsp+30h] [rbp-48h] BYREF
  int v9; // [rsp+38h] [rbp-40h]
  _QWORD v10[7]; // [rsp+3Ch] [rbp-3Ch] BYREF

  if ( !DriverObject )
    return DriverEntry(0, RegistryPath);
  *(_DWORD *)&DestinationString.Length = 34078720;
  DestinationString.Buffer = (wchar_t *)qword_140012410;
  RtlCopyUnicodeString(&DestinationString, RegistryPath);
  result = WdfVersionBind(DriverObject, &DestinationString, &WdfBindInfo, &WdfDriverGlobals);
  if ( result >= 0 )
  {
    inited = FxStubBindClasses(v5);
    if ( inited < 0 || (inited = FxStubInitTypes(), inited < 0) )
    {
LABEL_10:
      FxStubDriverUnloadCommon();
      return inited;
    }
    v7 = DriverEntry(DriverObject, RegistryPath);
    inited = v7;
    if ( v7 < 0 )
    {
      DbgPrintEx(0x4Du, 0, "DriverEntry failed 0x%x for driver %wZ\n", (unsigned int)v7, &DestinationString);
      if ( off_140012358 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, PWDF_DRIVER_GLOBALS))((char *)v10 + 4))(&WdfBindInfo, WdfDriverGlobals);
      }
      goto LABEL_10;
    }
    if ( WdfDriverGlobals->DisplaceDriverUnload )
    {
      if ( DriverObject->DriverUnload )
        qword_140012618 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140008d94  push    rbx
0x140008d96  push    rsi
0x140008d97  push    rdi
0x140008d98  push    r14
0x140008d9a  sub     rsp, 58h
0x140008d9e  mov     rsi, rdx
0x140008da1  mov     rdi, rcx
0x140008da4  test    rcx, rcx
0x140008da7  jnz     short loc_140008DB3
0x140008da9  call    DriverEntry
0x140008dae  jmp     loc_140008EC5
0x140008db3  lea     rax, qword_140012410
0x140008dba  mov     dword ptr cs:DestinationString.Length, 2080000h
0x140008dc4  lea     r14, DestinationString
0x140008dcb  mov     cs:DestinationString.Buffer, rax
0x140008dd2  mov     rcx, r14; DestinationString
0x140008dd5  call    cs:__imp_RtlCopyUnicodeString
0x140008ddc  nop     dword ptr [rax+rax+00h]
0x140008de1  lea     r9, WdfDriverGlobals
0x140008de8  mov     rdx, r14
0x140008deb  lea     r8, WdfBindInfo
0x140008df2  mov     rcx, rdi
0x140008df5  call    cs:__imp_WdfVersionBind
0x140008dfc  nop     dword ptr [rax+rax+00h]
0x140008e01  test    eax, eax
0x140008e03  js      loc_140008EC5
0x140008e09  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x140008e0e  mov     ebx, eax
0x140008e10  test    eax, eax
0x140008e12  js      loc_140008EBE
0x140008e18  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x140008e1d  mov     ebx, eax
0x140008e1f  test    eax, eax
0x140008e21  js      loc_140008EBE
0x140008e27  mov     rdx, rsi; RegistryPath
0x140008e2a  mov     rcx, rdi; DriverObject
0x140008e2d  call    DriverEntry
0x140008e32  mov     ebx, eax
0x140008e34  test    eax, eax
0x140008e36  jns     loc_140008ED0
0x140008e3c  xor     edx, edx; Level
0x140008e3e  mov     [rsp+78h+var_58], r14
0x140008e43  mov     r9d, eax
0x140008e46  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x140008e4d  lea     ecx, [rdx+4Dh]; ComponentId
0x140008e50  call    cs:__imp_DbgPrintEx
0x140008e57  nop     dword ptr [rax+rax+00h]
0x140008e5c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140008e63  cmp     cs:off_140012358, rax
0x140008e6a  jz      short loc_140008EBE
0x140008e6c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140008e73  mov     [rsp+78h+var_3C], 0
0x140008e7c  lea     rcx, [rsp+78h+var_48]
0x140008e81  mov     [rsp+78h+var_48], rax
0x140008e86  mov     [rsp+78h+var_34], 0
0x140008e8e  mov     [rsp+78h+var_40], 18h
0x140008e96  call    cs:__imp_WdfLdrQueryInterface
0x140008e9d  nop     dword ptr [rax+rax+00h]
0x140008ea2  test    eax, eax
0x140008ea4  js      short loc_140008EBE
0x140008ea6  mov     rdx, cs:WdfDriverGlobals
0x140008ead  lea     rcx, WdfBindInfo
0x140008eb4  mov     rax, [rsp+78h+var_3C+4]
0x140008eb9  call    _guard_dispatch_icall
0x140008ebe  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x140008ec3  mov     eax, ebx
0x140008ec5  add     rsp, 58h
0x140008ec9  pop     r14
0x140008ecb  pop     rdi
0x140008ecc  pop     rsi
0x140008ecd  pop     rbx
0x140008ece  retn
0x140008ed0  mov     rax, cs:WdfDriverGlobals
0x140008ed7  cmp     byte ptr [rax+30h], 0
0x140008edb  jz      short loc_140008EF8
0x140008edd  mov     rax, [rdi+68h]
0x140008ee1  test    rax, rax
0x140008ee4  jz      short loc_140008EED
0x140008ee6  mov     cs:qword_140012618, rax
0x140008eed  lea     rax, FxStubDriverUnload
0x140008ef4  mov     [rdi+68h], rax
0x140008ef8  xor     eax, eax
0x140008efa  jmp     short loc_140008EC5
```
