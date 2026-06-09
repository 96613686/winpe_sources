# FxDriverEntryWorker

- ea: `0x14015c664`
- end: `0x14015c7cc`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14015c630`

## callees

- `0x14015c5f4`
- `0x14015c664`
- `0x14015c814`
- `0x14015ca84`
- `0x140165580`
- `0x1402102b0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14015c6a5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14015c6a5`
- `ntoskrnl!DbgPrintEx` at `0x14015c720`
- `ntoskrnl!DbgPrintEx` at `0x14015c720`
- `WDFLDR!WdfLdrQueryInterface` at `0x14015c766`
- `WDFLDR!WdfLdrQueryInterface` at `0x14015c766`
- `WDFLDR!WdfVersionBind` at `0x14015c6c5`
- `WDFLDR!WdfVersionBind` at `0x14015c6c5`

## pseudocode

```c
__int64 __fastcall FxDriverEntryWorker(struct _DRIVER_OBJECT *a1, struct _UNICODE_STRING *a2)
{
  __int64 result; // rax
  struct _WDF_BIND_INFO *v5; // rcx
  int inited; // ebx
  int v7; // eax
  GUID *v8; // [rsp+30h] [rbp-48h] BYREF
  int v9; // [rsp+38h] [rbp-40h]
  _QWORD v10[7]; // [rsp+3Ch] [rbp-3Ch] BYREF

  if ( !a1 )
    return Driver::Make(0, a2);
  LODWORD(WPP_MAIN_CB.SecurityDescriptor) = 34078720;
  *(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock = qword_140197E40;
  RtlCopyUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.SecurityDescriptor, a2);
  result = WdfVersionBind(a1, &WPP_MAIN_CB.SecurityDescriptor, &qword_140197680, &WdfDriverGlobals);
  if ( (int)result >= 0 )
  {
    inited = FxStubBindClasses(v5);
    if ( inited < 0 || (inited = FxStubInitTypes(), inited < 0) )
    {
LABEL_10:
      FxStubDriverUnloadCommon();
      return (unsigned int)inited;
    }
    v7 = Driver::Make(a1, a2);
    inited = v7;
    if ( v7 < 0 )
    {
      DbgPrintEx(
        0x4Du,
        0,
        "DriverEntry failed 0x%x for driver %wZ\n",
        (unsigned int)v7,
        &WPP_MAIN_CB.SecurityDescriptor);
      if ( off_1401979A8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, PWDF_DRIVER_GLOBALS))((char *)v10 + 4))(&qword_140197680, WdfDriverGlobals);
      }
      goto LABEL_10;
    }
    if ( WdfDriverGlobals->DisplaceDriverUnload )
    {
      if ( a1->DriverUnload )
        qword_140198048 = (__int64)a1->DriverUnload;
      a1->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14015c664  push    rbx
0x14015c666  push    rsi
0x14015c667  push    rdi
0x14015c668  push    r14
0x14015c66a  sub     rsp, 58h
0x14015c66e  mov     rsi, rdx
0x14015c671  mov     rdi, rcx
0x14015c674  test    rcx, rcx
0x14015c677  jnz     short loc_14015C683
0x14015c679  call    ?Make@Driver@@SAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@@Z; Driver::Make(_DRIVER_OBJECT *,_UNICODE_STRING *)
0x14015c67e  jmp     loc_14015C795
0x14015c683  lea     rax, qword_140197E40
0x14015c68a  mov     dword ptr cs:WPP_MAIN_CB.SecurityDescriptor, 2080000h
0x14015c694  lea     r14, WPP_MAIN_CB.SecurityDescriptor
0x14015c69b  mov     qword ptr cs:WPP_MAIN_CB.DeviceLock.Header.___u0, rax
0x14015c6a2  mov     rcx, r14; DestinationString
0x14015c6a5  call    cs:__imp_RtlCopyUnicodeString
0x14015c6ac  nop     dword ptr [rax+rax+00h]
0x14015c6b1  lea     r9, WdfDriverGlobals
0x14015c6b8  mov     rdx, r14
0x14015c6bb  lea     r8, qword_140197680
0x14015c6c2  mov     rcx, rdi
0x14015c6c5  call    cs:__imp_WdfVersionBind
0x14015c6cc  nop     dword ptr [rax+rax+00h]
0x14015c6d1  test    eax, eax
0x14015c6d3  js      loc_14015C795
0x14015c6d9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x14015c6de  mov     ebx, eax
0x14015c6e0  test    eax, eax
0x14015c6e2  js      loc_14015C78E
0x14015c6e8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x14015c6ed  mov     ebx, eax
0x14015c6ef  test    eax, eax
0x14015c6f1  js      loc_14015C78E
0x14015c6f7  mov     rdx, rsi; struct _UNICODE_STRING *
0x14015c6fa  mov     rcx, rdi; struct _DRIVER_OBJECT *
0x14015c6fd  call    ?Make@Driver@@SAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@@Z; Driver::Make(_DRIVER_OBJECT *,_UNICODE_STRING *)
0x14015c702  mov     ebx, eax
0x14015c704  test    eax, eax
0x14015c706  jns     loc_14015C7A0
0x14015c70c  xor     edx, edx; Level
0x14015c70e  mov     [rsp+78h+var_58], r14
0x14015c713  mov     r9d, eax
0x14015c716  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x14015c71d  lea     ecx, [rdx+4Dh]; ComponentId
0x14015c720  call    cs:__imp_DbgPrintEx
0x14015c727  nop     dword ptr [rax+rax+00h]
0x14015c72c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x14015c733  cmp     cs:off_1401979A8, rax
0x14015c73a  jz      short loc_14015C78E
0x14015c73c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x14015c743  mov     [rsp+78h+var_3C], 0
0x14015c74c  lea     rcx, [rsp+78h+var_48]
0x14015c751  mov     [rsp+78h+var_48], rax
0x14015c756  mov     [rsp+78h+var_34], 0
0x14015c75e  mov     [rsp+78h+var_40], 18h
0x14015c766  call    cs:__imp_WdfLdrQueryInterface
0x14015c76d  nop     dword ptr [rax+rax+00h]
0x14015c772  test    eax, eax
0x14015c774  js      short loc_14015C78E
0x14015c776  mov     rdx, cs:WdfDriverGlobals
0x14015c77d  lea     rcx, qword_140197680
0x14015c784  mov     rax, [rsp+78h+var_3C+4]
0x14015c789  call    _guard_dispatch_icall
0x14015c78e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x14015c793  mov     eax, ebx
0x14015c795  add     rsp, 58h
0x14015c799  pop     r14
0x14015c79b  pop     rdi
0x14015c79c  pop     rsi
0x14015c79d  pop     rbx
0x14015c79e  retn
0x14015c7a0  mov     rax, cs:WdfDriverGlobals
0x14015c7a7  cmp     byte ptr [rax+30h], 0
0x14015c7ab  jz      short loc_14015C7C8
0x14015c7ad  mov     rax, [rdi+68h]
0x14015c7b1  test    rax, rax
0x14015c7b4  jz      short loc_14015C7BD
0x14015c7b6  mov     cs:qword_140198048, rax
0x14015c7bd  lea     rax, FxStubDriverUnload
0x14015c7c4  mov     [rdi+68h], rax
0x14015c7c8  xor     eax, eax
0x14015c7ca  jmp     short loc_14015C795
```
