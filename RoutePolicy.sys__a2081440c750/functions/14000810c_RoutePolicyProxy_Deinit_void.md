# RoutePolicyProxy::Deinit(void)

- ea: `0x14000810c`
- end: `0x1400081e5`
- name: `?Deinit@RoutePolicyProxy@@YAXXZ`
- size: `217`
- prototype: `void __fastcall(RoutePolicyProxy *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140008060`

## callees

- `0x140001008`
- `0x14000810c`
- `0x14000a680`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140008144`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140008144`
- `ntoskrnl!IoDeleteDevice` at `0x140008196`
- `ntoskrnl!IoDeleteDevice` at `0x140008196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400081bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400081bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008133`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008133`

## string_xrefs

- `0x14000816a`: `IoDeleteSymbolicLink failed`

## pseudocode

```c
void __fastcall RoutePolicyProxy::Deinit(RoutePolicyProxy *this)
{
  NTSTATUS v1; // eax
  int v2; // r8d
  int v3; // r9d
  NTSTATUS v4; // [rsp+30h] [rbp-38h] BYREF
  const char *v5; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\??\\RoutePolicy");
  v1 = IoDeleteSymbolicLink(&DestinationString);
  if ( v1 < 0 && (unsigned int)dword_140012050 > 3 )
  {
    v4 = v1;
    v5 = "IoDeleteSymbolicLink failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_140012050,
      (unsigned int)byte_1400108C1,
      v2,
      v3,
      (__int64)&v5,
      (__int64)&v4);
  }
  IoDeleteDevice(DeviceObject);
  DeviceObject = 0;
  if ( SecurityDescriptor )
  {
    ExFreePoolWithTag(SecurityDescriptor, 0);
    SecurityDescriptor = 0;
  }
}

```

## disassembly

```asm
0x14000810c  sub     rsp, 68h
0x140008110  mov     rax, cs:__security_cookie
0x140008117  xor     rax, rsp
0x14000811a  mov     [rsp+68h+var_18], rax
0x14000811f  xorps   xmm0, xmm0
0x140008122  lea     rdx, SourceString; "\\??\\RoutePolicy"
0x140008129  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14000812e  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140008133  call    cs:__imp_RtlInitUnicodeString
0x14000813a  nop     dword ptr [rax+rax+00h]
0x14000813f  lea     rcx, [rsp+68h+DestinationString]; SymbolicLinkName
0x140008144  call    cs:__imp_IoDeleteSymbolicLink
0x14000814b  nop     dword ptr [rax+rax+00h]
0x140008150  test    eax, eax
0x140008152  jns     short loc_14000818F
0x140008154  mov     ecx, cs:dword_140012050
0x14000815a  cmp     ecx, 3
0x14000815d  jbe     short loc_14000818F
0x14000815f  mov     [rsp+68h+var_38], eax
0x140008163  lea     rdx, byte_1400108C1
0x14000816a  lea     rax, aIodeletesymbol; "IoDeleteSymbolicLink failed"
0x140008171  mov     [rsp+68h+var_30], rax
0x140008176  lea     rax, [rsp+68h+var_38]
0x14000817b  mov     [rsp+68h+var_40], rax
0x140008180  lea     rax, [rsp+68h+var_30]
0x140008185  mov     [rsp+68h+var_48], rax
0x14000818a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000818f  mov     rcx, cs:DeviceObject; DeviceObject
0x140008196  call    cs:__imp_IoDeleteDevice
0x14000819d  nop     dword ptr [rax+rax+00h]
0x1400081a2  mov     rcx, cs:SecurityDescriptor; P
0x1400081a9  mov     cs:DeviceObject, 0
0x1400081b4  test    rcx, rcx
0x1400081b7  jz      short loc_1400081D2
0x1400081b9  xor     edx, edx; Tag
0x1400081bb  call    cs:__imp_ExFreePoolWithTag
0x1400081c2  nop     dword ptr [rax+rax+00h]
0x1400081c7  mov     cs:SecurityDescriptor, 0
0x1400081d2  mov     rcx, [rsp+68h+var_18]
0x1400081d7  xor     rcx, rsp; StackCookie
0x1400081da  call    __security_check_cookie
0x1400081df  add     rsp, 68h
0x1400081e3  retn
```
