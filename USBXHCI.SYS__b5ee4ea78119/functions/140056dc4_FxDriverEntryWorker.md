# FxDriverEntryWorker

- ea: `0x140056dc4`
- end: `0x140056f2c`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140056d90`

## callees

- `0x140056d54`
- `0x140056dc4`
- `0x140056f74`
- `0x1400571e4`
- `0x1400599b0`
- `0x14007553c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140056e80`
- `ntoskrnl!DbgPrintEx` at `0x140056e80`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140056e05`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140056e05`
- `WDFLDR!WdfLdrQueryInterface` at `0x140056ec6`
- `WDFLDR!WdfLdrQueryInterface` at `0x140056ec6`
- `WDFLDR!WdfVersionBind` at `0x140056e25`
- `WDFLDR!WdfVersionBind` at `0x140056e25`

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
  DestinationString.Buffer = (wchar_t *)qword_14006CA80;
  RtlCopyUnicodeString(&DestinationString, RegistryPath);
  result = WdfVersionBind(DriverObject, &DestinationString, &qword_14006C740, &WdfDriverGlobals);
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
      if ( off_14006C8B8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, PWDF_DRIVER_GLOBALS))((char *)v10 + 4))(&qword_14006C740, WdfDriverGlobals);
      }
      goto LABEL_10;
    }
    if ( WdfDriverGlobals->DisplaceDriverUnload )
    {
      if ( DriverObject->DriverUnload )
        qword_14006CC88 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140056dc4  push    rbx
0x140056dc6  push    rsi
0x140056dc7  push    rdi
0x140056dc8  push    r14
0x140056dca  sub     rsp, 58h
0x140056dce  mov     rsi, rdx
0x140056dd1  mov     rdi, rcx
0x140056dd4  test    rcx, rcx
0x140056dd7  jnz     short loc_140056DE3
0x140056dd9  call    DriverEntry
0x140056dde  jmp     loc_140056EF5
0x140056de3  lea     rax, qword_14006CA80
0x140056dea  mov     dword ptr cs:DestinationString.Length, 2080000h
0x140056df4  lea     r14, DestinationString
0x140056dfb  mov     cs:DestinationString.Buffer, rax
0x140056e02  mov     rcx, r14; DestinationString
0x140056e05  call    cs:__imp_RtlCopyUnicodeString
0x140056e0c  nop     dword ptr [rax+rax+00h]
0x140056e11  lea     r9, WdfDriverGlobals
0x140056e18  mov     rdx, r14
0x140056e1b  lea     r8, qword_14006C740
0x140056e22  mov     rcx, rdi
0x140056e25  call    cs:__imp_WdfVersionBind
0x140056e2c  nop     dword ptr [rax+rax+00h]
0x140056e31  test    eax, eax
0x140056e33  js      loc_140056EF5
0x140056e39  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x140056e3e  mov     ebx, eax
0x140056e40  test    eax, eax
0x140056e42  js      loc_140056EEE
0x140056e48  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x140056e4d  mov     ebx, eax
0x140056e4f  test    eax, eax
0x140056e51  js      loc_140056EEE
0x140056e57  mov     rdx, rsi; RegistryPath
0x140056e5a  mov     rcx, rdi; DriverObject
0x140056e5d  call    DriverEntry
0x140056e62  mov     ebx, eax
0x140056e64  test    eax, eax
0x140056e66  jns     loc_140056F00
0x140056e6c  xor     edx, edx; Level
0x140056e6e  mov     [rsp+78h+var_58], r14
0x140056e73  mov     r9d, eax
0x140056e76  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x140056e7d  lea     ecx, [rdx+4Dh]; ComponentId
0x140056e80  call    cs:__imp_DbgPrintEx
0x140056e87  nop     dword ptr [rax+rax+00h]
0x140056e8c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140056e93  cmp     cs:off_14006C8B8, rax
0x140056e9a  jz      short loc_140056EEE
0x140056e9c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140056ea3  mov     [rsp+78h+var_3C], 0
0x140056eac  lea     rcx, [rsp+78h+var_48]
0x140056eb1  mov     [rsp+78h+var_48], rax
0x140056eb6  mov     [rsp+78h+var_34], 0
0x140056ebe  mov     [rsp+78h+var_40], 18h
0x140056ec6  call    cs:__imp_WdfLdrQueryInterface
0x140056ecd  nop     dword ptr [rax+rax+00h]
0x140056ed2  test    eax, eax
0x140056ed4  js      short loc_140056EEE
0x140056ed6  mov     rdx, cs:WdfDriverGlobals
0x140056edd  lea     rcx, qword_14006C740
0x140056ee4  mov     rax, [rsp+78h+var_3C+4]
0x140056ee9  call    _guard_dispatch_icall
0x140056eee  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x140056ef3  mov     eax, ebx
0x140056ef5  add     rsp, 58h
0x140056ef9  pop     r14
0x140056efb  pop     rdi
0x140056efc  pop     rsi
0x140056efd  pop     rbx
0x140056efe  retn
0x140056f00  mov     rax, cs:WdfDriverGlobals
0x140056f07  cmp     byte ptr [rax+30h], 0
0x140056f0b  jz      short loc_140056F28
0x140056f0d  mov     rax, [rdi+68h]
0x140056f11  test    rax, rax
0x140056f14  jz      short loc_140056F1D
0x140056f16  mov     cs:qword_14006CC88, rax
0x140056f1d  lea     rax, FxStubDriverUnload
0x140056f24  mov     [rdi+68h], rax
0x140056f28  xor     eax, eax
0x140056f2a  jmp     short loc_140056EF5
```
