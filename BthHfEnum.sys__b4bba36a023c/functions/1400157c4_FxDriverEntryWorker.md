# FxDriverEntryWorker

- ea: `0x1400157c4`
- end: `0x14001592c`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015790`

## callees

- `0x140015754`
- `0x1400157c4`
- `0x140015974`
- `0x140015bd0`
- `0x14001ae00`
- `0x14003003c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140015880`
- `ntoskrnl!DbgPrintEx` at `0x140015880`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140015805`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140015805`
- `WDFLDR!WdfVersionBind` at `0x140015825`
- `WDFLDR!WdfVersionBind` at `0x140015825`
- `WDFLDR!WdfLdrQueryInterface` at `0x1400158c6`
- `WDFLDR!WdfLdrQueryInterface` at `0x1400158c6`

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
  WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)qword_1400227A0;
  RtlCopyUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.Queue, RegistryPath);
  result = WdfVersionBind(DriverObject, &WPP_MAIN_CB.Queue, &WdfBindInfo, &WdfDriverGlobals);
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
      if ( off_1400225D8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
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
        qword_1400229A8 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400157c4  push    rbx
0x1400157c6  push    rsi
0x1400157c7  push    rdi
0x1400157c8  push    r14
0x1400157ca  sub     rsp, 58h
0x1400157ce  mov     rsi, rdx
0x1400157d1  mov     rdi, rcx
0x1400157d4  test    rcx, rcx
0x1400157d7  jnz     short loc_1400157E3
0x1400157d9  call    DriverEntry
0x1400157de  jmp     loc_1400158F5
0x1400157e3  lea     rax, qword_1400227A0
0x1400157ea  mov     dword ptr cs:WPP_MAIN_CB.Queue, 2080000h
0x1400157f4  lea     r14, WPP_MAIN_CB.Queue
0x1400157fb  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x140015802  mov     rcx, r14; DestinationString
0x140015805  call    cs:__imp_RtlCopyUnicodeString
0x14001580c  nop     dword ptr [rax+rax+00h]
0x140015811  lea     r9, WdfDriverGlobals
0x140015818  mov     rdx, r14
0x14001581b  lea     r8, WdfBindInfo
0x140015822  mov     rcx, rdi
0x140015825  call    cs:__imp_WdfVersionBind
0x14001582c  nop     dword ptr [rax+rax+00h]
0x140015831  test    eax, eax
0x140015833  js      loc_1400158F5
0x140015839  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x14001583e  mov     ebx, eax
0x140015840  test    eax, eax
0x140015842  js      loc_1400158EE
0x140015848  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x14001584d  mov     ebx, eax
0x14001584f  test    eax, eax
0x140015851  js      loc_1400158EE
0x140015857  mov     rdx, rsi; RegistryPath
0x14001585a  mov     rcx, rdi; DriverObject
0x14001585d  call    DriverEntry
0x140015862  mov     ebx, eax
0x140015864  test    eax, eax
0x140015866  jns     loc_140015900
0x14001586c  xor     edx, edx; Level
0x14001586e  mov     [rsp+78h+var_58], r14
0x140015873  mov     r9d, eax
0x140015876  lea     r8, Format; "DriverEntry failed 0x%x for driver %wZ"...
0x14001587d  lea     ecx, [rdx+4Dh]; ComponentId
0x140015880  call    cs:__imp_DbgPrintEx
0x140015887  nop     dword ptr [rax+rax+00h]
0x14001588c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140015893  cmp     cs:off_1400225D8, rax
0x14001589a  jz      short loc_1400158EE
0x14001589c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x1400158a3  mov     [rsp+78h+var_3C], 0
0x1400158ac  lea     rcx, [rsp+78h+var_48]
0x1400158b1  mov     [rsp+78h+var_48], rax
0x1400158b6  mov     [rsp+78h+var_34], 0
0x1400158be  mov     [rsp+78h+var_40], 18h
0x1400158c6  call    cs:__imp_WdfLdrQueryInterface
0x1400158cd  nop     dword ptr [rax+rax+00h]
0x1400158d2  test    eax, eax
0x1400158d4  js      short loc_1400158EE
0x1400158d6  mov     rdx, cs:WdfDriverGlobals
0x1400158dd  lea     rcx, WdfBindInfo
0x1400158e4  mov     rax, [rsp+78h+var_3C+4]
0x1400158e9  call    _guard_dispatch_icall
0x1400158ee  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x1400158f3  mov     eax, ebx
0x1400158f5  add     rsp, 58h
0x1400158f9  pop     r14
0x1400158fb  pop     rdi
0x1400158fc  pop     rsi
0x1400158fd  pop     rbx
0x1400158fe  retn
0x140015900  mov     rax, cs:WdfDriverGlobals
0x140015907  cmp     byte ptr [rax+30h], 0
0x14001590b  jz      short loc_140015928
0x14001590d  mov     rax, [rdi+68h]
0x140015911  test    rax, rax
0x140015914  jz      short loc_14001591D
0x140015916  mov     cs:qword_1400229A8, rax
0x14001591d  lea     rax, FxStubDriverUnload
0x140015924  mov     [rdi+68h], rax
0x140015928  xor     eax, eax
0x14001592a  jmp     short loc_1400158F5
```
