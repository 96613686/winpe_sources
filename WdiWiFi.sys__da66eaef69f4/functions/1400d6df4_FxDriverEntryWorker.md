# FxDriverEntryWorker

- ea: `0x1400d6df4`
- end: `0x1400d6f5c`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400d6dc0`

## callees

- `0x1400c5dbc`
- `0x1400d6d84`
- `0x1400d6df4`
- `0x1400d6fa4`
- `0x1400d7200`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400d6e35`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400d6e35`
- `ntoskrnl!DbgPrintEx` at `0x1400d6eb0`
- `ntoskrnl!DbgPrintEx` at `0x1400d6eb0`
- `WDFLDR!WdfLdrQueryInterface` at `0x1400d6ef6`
- `WDFLDR!WdfLdrQueryInterface` at `0x1400d6ef6`
- `WDFLDR!WdfVersionBind` at `0x1400d6e55`
- `WDFLDR!WdfVersionBind` at `0x1400d6e55`

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
  LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink) = 34078720;
  WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)&WPP_MAIN_CB.DeviceQueue;
  RtlCopyUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.Queue, RegistryPath);
  result = WdfVersionBind(DriverObject, &WPP_MAIN_CB.Queue, &WdfBindInfo, &WPP_MAIN_CB.AlignmentRequirement);
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
      DbgPrintEx(0x4Du, 0, "DriverEntry failed 0x%x for driver %wZ\n", (unsigned int)v7, &WPP_MAIN_CB.Queue);
      if ( off_1400F9FE8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, _QWORD))((char *)v10 + 4))(
            &WdfBindInfo,
            *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement);
      }
      goto LABEL_10;
    }
    if ( *(_BYTE *)(*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement + 48LL) )
    {
      if ( DriverObject->DriverUnload )
        qword_1400FA438 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400d6df4  push    rbx
0x1400d6df6  push    rsi
0x1400d6df7  push    rdi
0x1400d6df8  push    r14
0x1400d6dfa  sub     rsp, 58h
0x1400d6dfe  mov     rsi, rdx
0x1400d6e01  mov     rdi, rcx
0x1400d6e04  test    rcx, rcx
0x1400d6e07  jnz     short loc_1400D6E13
0x1400d6e09  call    DriverEntry
0x1400d6e0e  jmp     loc_1400D6F25
0x1400d6e13  lea     rax, WPP_MAIN_CB.DeviceQueue
0x1400d6e1a  mov     dword ptr cs:WPP_MAIN_CB.Queue, 2080000h
0x1400d6e24  lea     r14, WPP_MAIN_CB.Queue
0x1400d6e2b  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x1400d6e32  mov     rcx, r14; DestinationString
0x1400d6e35  call    cs:__imp_RtlCopyUnicodeString
0x1400d6e3c  nop     dword ptr [rax+rax+00h]
0x1400d6e41  lea     r9, WPP_MAIN_CB.AlignmentRequirement
0x1400d6e48  mov     rdx, r14
0x1400d6e4b  lea     r8, WdfBindInfo
0x1400d6e52  mov     rcx, rdi
0x1400d6e55  call    cs:__imp_WdfVersionBind
0x1400d6e5c  nop     dword ptr [rax+rax+00h]
0x1400d6e61  test    eax, eax
0x1400d6e63  js      loc_1400D6F25
0x1400d6e69  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x1400d6e6e  mov     ebx, eax
0x1400d6e70  test    eax, eax
0x1400d6e72  js      loc_1400D6F1E
0x1400d6e78  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400d6e7d  mov     ebx, eax
0x1400d6e7f  test    eax, eax
0x1400d6e81  js      loc_1400D6F1E
0x1400d6e87  mov     rdx, rsi; RegistryPath
0x1400d6e8a  mov     rcx, rdi; DriverObject
0x1400d6e8d  call    DriverEntry
0x1400d6e92  mov     ebx, eax
0x1400d6e94  test    eax, eax
0x1400d6e96  jns     loc_1400D6F30
0x1400d6e9c  xor     edx, edx; Level
0x1400d6e9e  mov     [rsp+78h+var_58], r14
0x1400d6ea3  mov     r9d, eax
0x1400d6ea6  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x1400d6ead  lea     ecx, [rdx+4Dh]; ComponentId
0x1400d6eb0  call    cs:__imp_DbgPrintEx
0x1400d6eb7  nop     dword ptr [rax+rax+00h]
0x1400d6ebc  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x1400d6ec3  cmp     cs:off_1400F9FE8, rax
0x1400d6eca  jz      short loc_1400D6F1E
0x1400d6ecc  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x1400d6ed3  mov     [rsp+78h+var_3C], 0
0x1400d6edc  lea     rcx, [rsp+78h+var_48]
0x1400d6ee1  mov     [rsp+78h+var_48], rax
0x1400d6ee6  mov     [rsp+78h+var_34], 0
0x1400d6eee  mov     [rsp+78h+var_40], 18h
0x1400d6ef6  call    cs:__imp_WdfLdrQueryInterface
0x1400d6efd  nop     dword ptr [rax+rax+00h]
0x1400d6f02  test    eax, eax
0x1400d6f04  js      short loc_1400D6F1E
0x1400d6f06  mov     rdx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x1400d6f0d  lea     rcx, WdfBindInfo
0x1400d6f14  mov     rax, [rsp+78h+var_3C+4]
0x1400d6f19  call    _guard_dispatch_icall
0x1400d6f1e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x1400d6f23  mov     eax, ebx
0x1400d6f25  add     rsp, 58h
0x1400d6f29  pop     r14
0x1400d6f2b  pop     rdi
0x1400d6f2c  pop     rsi
0x1400d6f2d  pop     rbx
0x1400d6f2e  retn
0x1400d6f30  mov     rax, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x1400d6f37  cmp     byte ptr [rax+30h], 0
0x1400d6f3b  jz      short loc_1400D6F58
0x1400d6f3d  mov     rax, [rdi+68h]
0x1400d6f41  test    rax, rax
0x1400d6f44  jz      short loc_1400D6F4D
0x1400d6f46  mov     cs:qword_1400FA438, rax
0x1400d6f4d  lea     rax, FxStubDriverUnload
0x1400d6f54  mov     [rdi+68h], rax
0x1400d6f58  xor     eax, eax
0x1400d6f5a  jmp     short loc_1400D6F25
```
