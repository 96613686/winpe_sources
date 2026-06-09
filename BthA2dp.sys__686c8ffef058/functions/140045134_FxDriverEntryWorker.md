# FxDriverEntryWorker

- ea: `0x140045134`
- end: `0x14004529c`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140045100`

## callees

- `0x14003c5e0`
- `0x1400450bc`
- `0x140045134`
- `0x1400452e4`
- `0x140045540`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400451f0`
- `ntoskrnl!DbgPrintEx` at `0x1400451f0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140045175`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140045175`
- `WDFLDR!WdfVersionBind` at `0x140045195`
- `WDFLDR!WdfVersionBind` at `0x140045195`
- `WDFLDR!WdfLdrQueryInterface` at `0x140045236`
- `WDFLDR!WdfLdrQueryInterface` at `0x140045236`

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
  result = WdfVersionBind(DriverObject, &WPP_MAIN_CB.Queue, &WdfBindInfo, &WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
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
      if ( off_14006F2C8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, _QWORD))((char *)v10 + 4))(
            &WdfBindInfo,
            *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
      }
      goto LABEL_10;
    }
    if ( *(_BYTE *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 48LL) )
    {
      if ( DriverObject->DriverUnload )
        qword_14006F718 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140045134  push    rbx
0x140045136  push    rsi
0x140045137  push    rdi
0x140045138  push    r14
0x14004513a  sub     rsp, 58h
0x14004513e  mov     rsi, rdx
0x140045141  mov     rdi, rcx
0x140045144  test    rcx, rcx
0x140045147  jnz     short loc_140045153
0x140045149  call    DriverEntry
0x14004514e  jmp     loc_140045265
0x140045153  lea     rax, WPP_MAIN_CB.Queue+20h
0x14004515a  mov     dword ptr cs:WPP_MAIN_CB.Queue, 2080000h
0x140045164  lea     r14, WPP_MAIN_CB.Queue
0x14004516b  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x140045172  mov     rcx, r14; DestinationString
0x140045175  call    cs:__imp_RtlCopyUnicodeString
0x14004517c  nop     dword ptr [rax+rax+00h]
0x140045181  lea     r9, WPP_MAIN_CB.Queue+10h
0x140045188  mov     rdx, r14
0x14004518b  lea     r8, WdfBindInfo
0x140045192  mov     rcx, rdi
0x140045195  call    cs:__imp_WdfVersionBind
0x14004519c  nop     dword ptr [rax+rax+00h]
0x1400451a1  test    eax, eax
0x1400451a3  js      loc_140045265
0x1400451a9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x1400451ae  mov     ebx, eax
0x1400451b0  test    eax, eax
0x1400451b2  js      loc_14004525E
0x1400451b8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400451bd  mov     ebx, eax
0x1400451bf  test    eax, eax
0x1400451c1  js      loc_14004525E
0x1400451c7  mov     rdx, rsi; RegistryPath
0x1400451ca  mov     rcx, rdi; DriverObject
0x1400451cd  call    DriverEntry
0x1400451d2  mov     ebx, eax
0x1400451d4  test    eax, eax
0x1400451d6  jns     loc_140045270
0x1400451dc  xor     edx, edx; Level
0x1400451de  mov     [rsp+78h+var_58], r14
0x1400451e3  mov     r9d, eax
0x1400451e6  lea     r8, Format; "DriverEntry failed 0x%x for driver %wZ"...
0x1400451ed  lea     ecx, [rdx+4Dh]; ComponentId
0x1400451f0  call    cs:__imp_DbgPrintEx
0x1400451f7  nop     dword ptr [rax+rax+00h]
0x1400451fc  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140045203  cmp     cs:off_14006F2C8, rax
0x14004520a  jz      short loc_14004525E
0x14004520c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140045213  mov     [rsp+78h+var_3C], 0
0x14004521c  lea     rcx, [rsp+78h+var_48]
0x140045221  mov     [rsp+78h+var_48], rax
0x140045226  mov     [rsp+78h+var_34], 0
0x14004522e  mov     [rsp+78h+var_40], 18h
0x140045236  call    cs:__imp_WdfLdrQueryInterface
0x14004523d  nop     dword ptr [rax+rax+00h]
0x140045242  test    eax, eax
0x140045244  js      short loc_14004525E
0x140045246  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14004524d  lea     rcx, WdfBindInfo
0x140045254  mov     rax, [rsp+78h+var_3C+4]
0x140045259  call    _guard_dispatch_icall
0x14004525e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x140045263  mov     eax, ebx
0x140045265  add     rsp, 58h
0x140045269  pop     r14
0x14004526b  pop     rdi
0x14004526c  pop     rsi
0x14004526d  pop     rbx
0x14004526e  retn
0x140045270  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140045277  cmp     byte ptr [rax+30h], 0
0x14004527b  jz      short loc_140045298
0x14004527d  mov     rax, [rdi+68h]
0x140045281  test    rax, rax
0x140045284  jz      short loc_14004528D
0x140045286  mov     cs:qword_14006F718, rax
0x14004528d  lea     rax, FxStubDriverUnload
0x140045294  mov     [rdi+68h], rax
0x140045298  xor     eax, eax
0x14004529a  jmp     short loc_140045265
```
