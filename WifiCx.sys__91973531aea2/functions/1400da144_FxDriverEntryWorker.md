# FxDriverEntryWorker

- ea: `0x1400da144`
- end: `0x1400da2ac`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400da110`

## callees

- `0x1400da0d0`
- `0x1400da144`
- `0x1400da2f4`
- `0x1400da564`
- `0x1400dfd40`
- `0x14012103c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400da200`
- `ntoskrnl!DbgPrintEx` at `0x1400da200`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400da185`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400da185`
- `WDFLDR!WdfLdrQueryInterface` at `0x1400da246`
- `WDFLDR!WdfLdrQueryInterface` at `0x1400da246`
- `WDFLDR!WdfVersionBind` at `0x1400da1a5`
- `WDFLDR!WdfVersionBind` at `0x1400da1a5`

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
  WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext;
  RtlCopyUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.Queue, RegistryPath);
  result = WdfVersionBind(DriverObject, &WPP_MAIN_CB.Queue, &qword_14010EC80, &WdfDriverGlobals);
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
      if ( off_140110640 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, PWDF_DRIVER_GLOBALS))((char *)v10 + 4))(&qword_14010EC80, WdfDriverGlobals);
      }
      goto LABEL_10;
    }
    if ( WdfDriverGlobals->DisplaceDriverUnload )
    {
      if ( DriverObject->DriverUnload )
        qword_140110B68 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400da144  push    rbx
0x1400da146  push    rsi
0x1400da147  push    rdi
0x1400da148  push    r14
0x1400da14a  sub     rsp, 58h
0x1400da14e  mov     rsi, rdx
0x1400da151  mov     rdi, rcx
0x1400da154  test    rcx, rcx
0x1400da157  jnz     short loc_1400DA163
0x1400da159  call    DriverEntry
0x1400da15e  jmp     loc_1400DA275
0x1400da163  lea     rax, WPP_MAIN_CB.Queue+20h
0x1400da16a  mov     dword ptr cs:WPP_MAIN_CB.Queue, 2080000h
0x1400da174  lea     r14, WPP_MAIN_CB.Queue
0x1400da17b  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x1400da182  mov     rcx, r14; DestinationString
0x1400da185  call    cs:__imp_RtlCopyUnicodeString
0x1400da18c  nop     dword ptr [rax+rax+00h]
0x1400da191  lea     r9, WdfDriverGlobals
0x1400da198  mov     rdx, r14
0x1400da19b  lea     r8, qword_14010EC80
0x1400da1a2  mov     rcx, rdi
0x1400da1a5  call    cs:__imp_WdfVersionBind
0x1400da1ac  nop     dword ptr [rax+rax+00h]
0x1400da1b1  test    eax, eax
0x1400da1b3  js      loc_1400DA275
0x1400da1b9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x1400da1be  mov     ebx, eax
0x1400da1c0  test    eax, eax
0x1400da1c2  js      loc_1400DA26E
0x1400da1c8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400da1cd  mov     ebx, eax
0x1400da1cf  test    eax, eax
0x1400da1d1  js      loc_1400DA26E
0x1400da1d7  mov     rdx, rsi; RegistryPath
0x1400da1da  mov     rcx, rdi; DriverObject
0x1400da1dd  call    DriverEntry
0x1400da1e2  mov     ebx, eax
0x1400da1e4  test    eax, eax
0x1400da1e6  jns     loc_1400DA280
0x1400da1ec  xor     edx, edx; Level
0x1400da1ee  mov     [rsp+78h+var_58], r14
0x1400da1f3  mov     r9d, eax
0x1400da1f6  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x1400da1fd  lea     ecx, [rdx+4Dh]; ComponentId
0x1400da200  call    cs:__imp_DbgPrintEx
0x1400da207  nop     dword ptr [rax+rax+00h]
0x1400da20c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x1400da213  cmp     cs:off_140110640, rax
0x1400da21a  jz      short loc_1400DA26E
0x1400da21c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x1400da223  mov     [rsp+78h+var_3C], 0
0x1400da22c  lea     rcx, [rsp+78h+var_48]
0x1400da231  mov     [rsp+78h+var_48], rax
0x1400da236  mov     [rsp+78h+var_34], 0
0x1400da23e  mov     [rsp+78h+var_40], 18h
0x1400da246  call    cs:__imp_WdfLdrQueryInterface
0x1400da24d  nop     dword ptr [rax+rax+00h]
0x1400da252  test    eax, eax
0x1400da254  js      short loc_1400DA26E
0x1400da256  mov     rdx, cs:WdfDriverGlobals
0x1400da25d  lea     rcx, qword_14010EC80
0x1400da264  mov     rax, [rsp+78h+var_3C+4]
0x1400da269  call    _guard_dispatch_icall
0x1400da26e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x1400da273  mov     eax, ebx
0x1400da275  add     rsp, 58h
0x1400da279  pop     r14
0x1400da27b  pop     rdi
0x1400da27c  pop     rsi
0x1400da27d  pop     rbx
0x1400da27e  retn
0x1400da280  mov     rax, cs:WdfDriverGlobals
0x1400da287  cmp     byte ptr [rax+30h], 0
0x1400da28b  jz      short loc_1400DA2A8
0x1400da28d  mov     rax, [rdi+68h]
0x1400da291  test    rax, rax
0x1400da294  jz      short loc_1400DA29D
0x1400da296  mov     cs:qword_140110B68, rax
0x1400da29d  lea     rax, FxStubDriverUnload
0x1400da2a4  mov     [rdi+68h], rax
0x1400da2a8  xor     eax, eax
0x1400da2aa  jmp     short loc_1400DA275
```
