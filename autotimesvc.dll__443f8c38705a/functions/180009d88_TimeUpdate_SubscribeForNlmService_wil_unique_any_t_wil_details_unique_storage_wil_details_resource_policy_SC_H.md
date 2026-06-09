# TimeUpdate::SubscribeForNlmService(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &)

- ea: `0x180009d88`
- end: `0x180009edd`
- name: `?SubscribeForNlmService@TimeUpdate@@AEAAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, SC_HANDLE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800081ac`

## callees

- `0x180001010`
- `0x180001218`
- `0x1800012f0`
- `0x180007e24`
- `0x180009d88`
- `0x18000a9e4`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180009db2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180009db2`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180009deb`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180009deb`

## pseudocode

```c
__int64 __fastcall TimeUpdate::SubscribeForNlmService(__int64 a1, SC_HANDLE *a2)
{
  SC_HANDLE v4; // rcx
  SC_HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  DWORD v8; // edi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = *a2;
  if ( !*a2 )
  {
    v5 = OpenServiceW(*(SC_HANDLE *)(a1 + 640), L"netprofm", 4u);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
      a2,
      v5);
    v4 = *a2;
    if ( !*a2 )
    {
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x3FF, v6, v7);
      return 5000;
    }
  }
  v8 = NotifyServiceStatusChangeW(v4, 9u, (PSERVICE_NOTIFYW)(a1 + 496));
  if ( v8 )
  {
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
      a2,
      0);
    if ( v8 != 1294 )
    {
      if ( (unsigned int)dword_18001C010 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 0x400000000200LL) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18001C010,
          (__int64)byte_180016399,
          0,
          0);
      return 5000;
    }
    if ( (unsigned int)dword_18001C010 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_18001C010,
        (__int64)&dword_18001659C,
        0,
        0);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_18001C010 > 4 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)&dword_18001C010,
          (__int64)&dword_180016484,
          0,
          0);
    }
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x180009d88  mov     [rsp+arg_0], rbx
0x180009d8d  push    rdi
0x180009d8e  sub     rsp, 30h
0x180009d92  mov     rdi, rcx
0x180009d95  mov     rbx, rdx
0x180009d98  mov     rcx, [rdx]; hService
0x180009d9b  test    rcx, rcx
0x180009d9e  jnz     short loc_180009DDF
0x180009da0  lea     r8d, [rcx+4]; dwDesiredAccess
0x180009da4  mov     rcx, [rdi+280h]; hSCManager
0x180009dab  lea     rdx, ServiceName; "netprofm"
0x180009db2  call    cs:__imp_OpenServiceW
0x180009db8  mov     rdx, rax
0x180009dbb  mov     rcx, rbx
0x180009dbe  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x180009dc3  mov     rcx, [rbx]
0x180009dc6  test    rcx, rcx
0x180009dc9  jnz     short loc_180009DDF
0x180009dcb  mov     rcx, [rsp+38h]; this
0x180009dd0  mov     edx, 3FFh; void *
0x180009dd5  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180009dda  jmp     loc_180009ECD
0x180009ddf  lea     r8, [rdi+1F0h]; pNotifyBuffer
0x180009de6  mov     edx, 9; dwNotifyMask
0x180009deb  call    cs:__imp_NotifyServiceStatusChangeW
0x180009df1  mov     edi, eax
0x180009df3  test    eax, eax
0x180009df5  jnz     short loc_180009E38
0x180009df7  mov     eax, cs:dword_18001C010
0x180009dfd  cmp     eax, 4
0x180009e00  jbe     short loc_180009E30
0x180009e02  mov     edx, 200h
0x180009e07  lea     rcx, dword_18001C010
0x180009e0e  call    _tlgKeywordOn
0x180009e13  test    al, al
0x180009e15  jz      short loc_180009E30
0x180009e17  xor     r9d, r9d
0x180009e1a  lea     rdx, dword_180016484
0x180009e21  xor     r8d, r8d
0x180009e24  lea     rcx, dword_18001C010
0x180009e2b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180009e30  or      eax, 0FFFFFFFFh
0x180009e33  jmp     loc_180009ED2
0x180009e38  xor     edx, edx
0x180009e3a  mov     rcx, rbx
0x180009e3d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x180009e42  mov     eax, cs:dword_18001C010
0x180009e48  cmp     edi, 50Eh
0x180009e4e  jnz     short loc_180009E87
0x180009e50  cmp     eax, 3
0x180009e53  jbe     short loc_180009E83
0x180009e55  mov     edx, 200h
0x180009e5a  lea     rcx, dword_18001C010
0x180009e61  call    _tlgKeywordOn
0x180009e66  test    al, al
0x180009e68  jz      short loc_180009E83
0x180009e6a  xor     r9d, r9d
0x180009e6d  lea     rdx, dword_18001659C
0x180009e74  xor     r8d, r8d
0x180009e77  lea     rcx, dword_18001C010
0x180009e7e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180009e83  xor     eax, eax
0x180009e85  jmp     short loc_180009ED2
0x180009e87  cmp     eax, 2
0x180009e8a  jbe     short loc_180009ECD
0x180009e8c  mov     rdx, 400000000200h
0x180009e96  lea     rcx, dword_18001C010
0x180009e9d  call    _tlgKeywordOn
0x180009ea2  test    al, al
0x180009ea4  jz      short loc_180009ECD
0x180009ea6  lea     rax, [rsp+38h+arg_8]
0x180009eab  mov     [rsp+38h+arg_8], edi
0x180009eaf  xor     r9d, r9d
0x180009eb2  mov     [rsp+38h+var_18], rax
0x180009eb7  xor     r8d, r8d
0x180009eba  lea     rdx, byte_180016399
0x180009ec1  lea     rcx, dword_18001C010
0x180009ec8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180009ecd  mov     eax, 1388h
0x180009ed2  mov     rbx, [rsp+38h+arg_0]
0x180009ed7  add     rsp, 30h
0x180009edb  pop     rdi
0x180009edc  retn
```
