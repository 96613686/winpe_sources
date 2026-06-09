# CMidi2KSAggregateMidiEndpointManager2::OnFilterDeviceInterfaceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)

- ea: `0x18003ee80`
- end: `0x18003ef83`
- name: `?OnFilterDeviceInterfaceUpdated@CMidi2KSAggregateMidiEndpointManager2@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180005f2c`
- `0x180005fa4`
- `0x180010b94`
- `0x1800117d8`
- `0x1800254f8`
- `0x18003ee80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ef7c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ef7c`

## string_xrefs

- `0x18003eee2`: `CMidi2KSAggregateMidiEndpointManager2::OnFilterDeviceInterfaceUpdated`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMidi2KSAggregateMidiEndpointManager2::OnFilterDeviceInterfaceUpdated(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _DWORD *v6; // rdi
  __int64 v7; // rax
  int v8; // r8d
  int v9; // r9d
  const wchar_t *v10; // rax
  void *v11; // rdi
  int v12; // eax
  HANDLE ProcessHeap; // rax
  __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  const char *v16; // [rsp+48h] [rbp-30h] BYREF
  LPVOID lpMem[5]; // [rsp+50h] [rbp-28h] BYREF
  const wchar_t *v18; // [rsp+98h] [rbp+20h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v7 = *(_QWORD *)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(
                      a3,
                      lpMem);
    v10 = v7 ? *(const wchar_t **)(v7 + 16) : &S1;
    v18 = v10;
    v15 = a1;
    v16 = "CMidi2KSAggregateMidiEndpointManager2::OnFilterDeviceInterfaceUpdated";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)&word_180089766,
      v8,
      v9,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v18);
    v11 = lpMem[0];
    if ( lpMem[0] )
    {
      v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( v12 )
      {
        if ( v12 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v11);
      }
    }
  }
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return 0;
}

```

## disassembly

```asm
0x18003ee80  mov     [rsp+arg_0], rbx
0x18003ee85  mov     [rsp+arg_10], r8
0x18003ee8a  mov     [rsp+arg_8], rdx
0x18003ee8f  push    rbp
0x18003ee90  push    rsi
0x18003ee91  push    rdi
0x18003ee92  sub     rsp, 60h
0x18003ee96  mov     rbx, r8
0x18003ee99  mov     rsi, rdx
0x18003ee9c  mov     rbp, rcx
0x18003ee9f  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18003eea4  mov     rdi, [rax+8]
0x18003eea8  mov     eax, [rdi]
0x18003eeaa  cmp     eax, 4
0x18003eead  jbe     loc_18003EF49
0x18003eeb3  lea     rdx, [rsp+78h+lpMem]
0x18003eeb8  mov     rcx, rbx
0x18003eebb  call    ?Id@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Id(void)
0x18003eec0  mov     rax, [rax]
0x18003eec3  test    rax, rax
0x18003eec6  jz      short loc_18003EECE
0x18003eec8  mov     rax, [rax+10h]
0x18003eecc  jmp     short loc_18003EED5
0x18003eece  lea     rax, S1
0x18003eed5  mov     [rsp+78h+arg_18], rax
0x18003eedd  mov     [rsp+78h+var_38], rbp
0x18003eee2  lea     rax, aCmidi2ksaggreg_0; "CMidi2KSAggregateMidiEndpointManager2::"...
0x18003eee9  mov     [rsp+78h+var_30], rax
0x18003eeee  lea     rax, [rsp+78h+arg_18]
0x18003eef6  mov     [rsp+78h+var_48], rax
0x18003eefb  lea     rax, [rsp+78h+var_38]
0x18003ef00  mov     [rsp+78h+var_50], rax
0x18003ef05  lea     rax, [rsp+78h+var_30]
0x18003ef0a  mov     [rsp+78h+var_58], rax
0x18003ef0f  lea     rdx, word_180089766
0x18003ef16  mov     rcx, rdi
0x18003ef19  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18003ef1e  mov     rdi, [rsp+78h+lpMem]
0x18003ef23  test    rdi, rdi
0x18003ef26  jz      short loc_18003EF49
0x18003ef28  or      eax, 0FFFFFFFFh
0x18003ef2b  lock xadd [rdi+18h], eax
0x18003ef30  sub     eax, 1
0x18003ef33  jnz     short loc_18003EF78
0x18003ef35  nop
0x18003ef36  call    WINRT_IMPL_GetProcessHeap
0x18003ef3b  mov     rcx, rax; hHeap
0x18003ef3e  mov     r8, rdi; lpMem
0x18003ef41  xor     edx, edx; dwFlags
0x18003ef43  call    WINRT_IMPL_HeapFree
0x18003ef48  nop
0x18003ef49  cmp     qword ptr [rsi], 0
0x18003ef4d  jz      short loc_18003EF58
0x18003ef4f  mov     rcx, rsi
0x18003ef52  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003ef57  nop
0x18003ef58  cmp     qword ptr [rbx], 0
0x18003ef5c  jz      short loc_18003EF66
0x18003ef5e  mov     rcx, rbx
0x18003ef61  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003ef66  xor     eax, eax
0x18003ef68  mov     rbx, [rsp+78h+arg_0]
0x18003ef70  add     rsp, 60h
0x18003ef74  pop     rdi
0x18003ef75  pop     rsi
0x18003ef76  pop     rbp
0x18003ef77  retn
0x18003ef78  test    eax, eax
0x18003ef7a  jns     short loc_18003EF49
0x18003ef7c  call    cs:__imp_abort
```
