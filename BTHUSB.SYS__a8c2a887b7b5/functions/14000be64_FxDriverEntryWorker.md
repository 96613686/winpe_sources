# FxDriverEntryWorker

- ea: `0x14000be64`
- end: `0x14000bfcc`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000be30`

## callees

- `0x14000bd0c`
- `0x14000be64`
- `0x14000c014`
- `0x14000c1ac`
- `0x14000de00`
- `0x14001d03c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000bf20`
- `ntoskrnl!DbgPrintEx` at `0x14000bf20`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bea5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bea5`
- `WDFLDR!WdfLdrQueryInterface` at `0x14000bf66`
- `WDFLDR!WdfLdrQueryInterface` at `0x14000bf66`
- `WDFLDR!WdfVersionBind` at `0x14000bec5`
- `WDFLDR!WdfVersionBind` at `0x14000bec5`

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
  WPP_MAIN_CB.Queue.ListEntry.Blink = (_LIST_ENTRY *)&WPP_MAIN_CB.Dpc.DpcListEntry;
  RtlCopyUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.Queue, RegistryPath);
  result = WdfVersionBind(
             DriverObject,
             &WPP_MAIN_CB.Queue,
             &qword_1400130C0,
             &WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
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
      if ( off_140013228 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, _LIST_ENTRY *))((char *)v10 + 4))(
            &qword_1400130C0,
            WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
      }
      goto LABEL_10;
    }
    if ( LOBYTE(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink[3].Flink) )
    {
      if ( DriverObject->DriverUnload )
        qword_1400135E8 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000be64  push    rbx
0x14000be66  push    rsi
0x14000be67  push    rdi
0x14000be68  push    r14
0x14000be6a  sub     rsp, 58h
0x14000be6e  mov     rsi, rdx
0x14000be71  mov     rdi, rcx
0x14000be74  test    rcx, rcx
0x14000be77  jnz     short loc_14000BE83
0x14000be79  call    DriverEntry
0x14000be7e  jmp     loc_14000BF95
0x14000be83  lea     rax, WPP_MAIN_CB.Dpc.DpcListEntry
0x14000be8a  mov     dword ptr cs:WPP_MAIN_CB.Queue, 2080000h
0x14000be94  lea     r14, WPP_MAIN_CB.Queue
0x14000be9b  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x14000bea2  mov     rcx, r14; DestinationString
0x14000bea5  call    cs:__imp_RtlCopyUnicodeString
0x14000beac  nop     dword ptr [rax+rax+00h]
0x14000beb1  lea     r9, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000beb8  mov     rdx, r14
0x14000bebb  lea     r8, qword_1400130C0
0x14000bec2  mov     rcx, rdi
0x14000bec5  call    cs:__imp_WdfVersionBind
0x14000becc  nop     dword ptr [rax+rax+00h]
0x14000bed1  test    eax, eax
0x14000bed3  js      loc_14000BF95
0x14000bed9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x14000bede  mov     ebx, eax
0x14000bee0  test    eax, eax
0x14000bee2  js      loc_14000BF8E
0x14000bee8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x14000beed  mov     ebx, eax
0x14000beef  test    eax, eax
0x14000bef1  js      loc_14000BF8E
0x14000bef7  mov     rdx, rsi; RegistryPath
0x14000befa  mov     rcx, rdi; DriverObject
0x14000befd  call    DriverEntry
0x14000bf02  mov     ebx, eax
0x14000bf04  test    eax, eax
0x14000bf06  jns     loc_14000BFA0
0x14000bf0c  xor     edx, edx; Level
0x14000bf0e  mov     [rsp+78h+var_58], r14
0x14000bf13  mov     r9d, eax
0x14000bf16  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x14000bf1d  lea     ecx, [rdx+4Dh]; ComponentId
0x14000bf20  call    cs:__imp_DbgPrintEx
0x14000bf27  nop     dword ptr [rax+rax+00h]
0x14000bf2c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x14000bf33  cmp     cs:off_140013228, rax
0x14000bf3a  jz      short loc_14000BF8E
0x14000bf3c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x14000bf43  mov     [rsp+78h+var_3C], 0
0x14000bf4c  lea     rcx, [rsp+78h+var_48]
0x14000bf51  mov     [rsp+78h+var_48], rax
0x14000bf56  mov     [rsp+78h+var_34], 0
0x14000bf5e  mov     [rsp+78h+var_40], 18h
0x14000bf66  call    cs:__imp_WdfLdrQueryInterface
0x14000bf6d  nop     dword ptr [rax+rax+00h]
0x14000bf72  test    eax, eax
0x14000bf74  js      short loc_14000BF8E
0x14000bf76  mov     rdx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000bf7d  lea     rcx, qword_1400130C0
0x14000bf84  mov     rax, [rsp+78h+var_3C+4]
0x14000bf89  call    _guard_dispatch_icall
0x14000bf8e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x14000bf93  mov     eax, ebx
0x14000bf95  add     rsp, 58h
0x14000bf99  pop     r14
0x14000bf9b  pop     rdi
0x14000bf9c  pop     rsi
0x14000bf9d  pop     rbx
0x14000bf9e  retn
0x14000bfa0  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000bfa7  cmp     byte ptr [rax+30h], 0
0x14000bfab  jz      short loc_14000BFC8
0x14000bfad  mov     rax, [rdi+68h]
0x14000bfb1  test    rax, rax
0x14000bfb4  jz      short loc_14000BFBD
0x14000bfb6  mov     cs:qword_1400135E8, rax
0x14000bfbd  lea     rax, FxStubDriverUnload
0x14000bfc4  mov     [rdi+68h], rax
0x14000bfc8  xor     eax, eax
0x14000bfca  jmp     short loc_14000BF95
```
