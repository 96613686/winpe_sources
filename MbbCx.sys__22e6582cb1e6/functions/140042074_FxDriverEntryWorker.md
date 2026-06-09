# FxDriverEntryWorker

- ea: `0x140042074`
- end: `0x1400421dc`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140042040`

## callees

- `0x140041f20`
- `0x140042074`
- `0x140042224`
- `0x1400423bc`
- `0x140047e90`
- `0x14006703c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140042130`
- `ntoskrnl!DbgPrintEx` at `0x140042130`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400420b5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400420b5`
- `WDFLDR!WdfLdrQueryInterface` at `0x140042176`
- `WDFLDR!WdfLdrQueryInterface` at `0x140042176`
- `WDFLDR!WdfVersionBind` at `0x1400420d5`
- `WDFLDR!WdfVersionBind` at `0x1400420d5`

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
  LODWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) = 34078720;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = &WPP_MAIN_CB.SectorSize;
  RtlCopyUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink, RegistryPath);
  result = WdfVersionBind(DriverObject, &WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink, &qword_14005E070, &WdfDriverGlobals);
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
      DbgPrintEx(
        0x4Du,
        0,
        "DriverEntry failed 0x%x for driver %wZ\n",
        (unsigned int)v7,
        &WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink);
      if ( off_14005EFE8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, PWDF_DRIVER_GLOBALS))((char *)v10 + 4))(&qword_14005E070, WdfDriverGlobals);
      }
      goto LABEL_10;
    }
    if ( WdfDriverGlobals->DisplaceDriverUnload )
    {
      if ( DriverObject->DriverUnload )
        qword_14005F4D8 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140042074  push    rbx
0x140042076  push    rsi
0x140042077  push    rdi
0x140042078  push    r14
0x14004207a  sub     rsp, 58h
0x14004207e  mov     rsi, rdx
0x140042081  mov     rdi, rcx
0x140042084  test    rcx, rcx
0x140042087  jnz     short loc_140042093
0x140042089  call    DriverEntry
0x14004208e  jmp     loc_1400421A5
0x140042093  lea     rax, WPP_MAIN_CB.SectorSize
0x14004209a  mov     dword ptr cs:WPP_MAIN_CB.Queue+8, 2080000h
0x1400420a4  lea     r14, WPP_MAIN_CB.Queue+8
0x1400420ab  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x1400420b2  mov     rcx, r14; DestinationString
0x1400420b5  call    cs:__imp_RtlCopyUnicodeString
0x1400420bc  nop     dword ptr [rax+rax+00h]
0x1400420c1  lea     r9, WdfDriverGlobals
0x1400420c8  mov     rdx, r14
0x1400420cb  lea     r8, qword_14005E070
0x1400420d2  mov     rcx, rdi
0x1400420d5  call    cs:__imp_WdfVersionBind
0x1400420dc  nop     dword ptr [rax+rax+00h]
0x1400420e1  test    eax, eax
0x1400420e3  js      loc_1400421A5
0x1400420e9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x1400420ee  mov     ebx, eax
0x1400420f0  test    eax, eax
0x1400420f2  js      loc_14004219E
0x1400420f8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400420fd  mov     ebx, eax
0x1400420ff  test    eax, eax
0x140042101  js      loc_14004219E
0x140042107  mov     rdx, rsi; RegistryPath
0x14004210a  mov     rcx, rdi; DriverObject
0x14004210d  call    DriverEntry
0x140042112  mov     ebx, eax
0x140042114  test    eax, eax
0x140042116  jns     loc_1400421B0
0x14004211c  xor     edx, edx; Level
0x14004211e  mov     [rsp+78h+var_58], r14
0x140042123  mov     r9d, eax
0x140042126  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x14004212d  lea     ecx, [rdx+4Dh]; ComponentId
0x140042130  call    cs:__imp_DbgPrintEx
0x140042137  nop     dword ptr [rax+rax+00h]
0x14004213c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140042143  cmp     cs:off_14005EFE8, rax
0x14004214a  jz      short loc_14004219E
0x14004214c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140042153  mov     [rsp+78h+var_3C], 0
0x14004215c  lea     rcx, [rsp+78h+var_48]
0x140042161  mov     [rsp+78h+var_48], rax
0x140042166  mov     [rsp+78h+var_34], 0
0x14004216e  mov     [rsp+78h+var_40], 18h
0x140042176  call    cs:__imp_WdfLdrQueryInterface
0x14004217d  nop     dword ptr [rax+rax+00h]
0x140042182  test    eax, eax
0x140042184  js      short loc_14004219E
0x140042186  mov     rdx, cs:WdfDriverGlobals
0x14004218d  lea     rcx, qword_14005E070
0x140042194  mov     rax, [rsp+78h+var_3C+4]
0x140042199  call    _guard_dispatch_icall
0x14004219e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x1400421a3  mov     eax, ebx
0x1400421a5  add     rsp, 58h
0x1400421a9  pop     r14
0x1400421ab  pop     rdi
0x1400421ac  pop     rsi
0x1400421ad  pop     rbx
0x1400421ae  retn
0x1400421b0  mov     rax, cs:WdfDriverGlobals
0x1400421b7  cmp     byte ptr [rax+30h], 0
0x1400421bb  jz      short loc_1400421D8
0x1400421bd  mov     rax, [rdi+68h]
0x1400421c1  test    rax, rax
0x1400421c4  jz      short loc_1400421CD
0x1400421c6  mov     cs:qword_14005F4D8, rax
0x1400421cd  lea     rax, FxStubDriverUnload
0x1400421d4  mov     [rdi+68h], rax
0x1400421d8  xor     eax, eax
0x1400421da  jmp     short loc_1400421A5
```
