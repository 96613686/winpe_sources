# Windows::Networking::UX::Internal::WlanClient::~WlanClient(void)

- ea: `0x18001239c`
- end: `0x1800124b8`
- name: `??1WlanClient@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `284`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::WlanClient *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020474`

## callees

- `0x180008e30`
- `0x18000de4c`
- `0x18001215c`
- `0x180012208`
- `0x180012330`
- `0x18001239c`
- `0x180013fd0`
- `0x180016b94`
- `0x18007a4e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001247b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001247b`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180012456`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180012456`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::WlanClient::~WlanClient(
        Windows::Networking::UX::Internal::WlanClient *this)
{
  PVOID *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r8

  *(_QWORD *)this = &Windows::Networking::UX::Internal::WlanClient::`vftable'{for `Windows::Networking::UX::Internal::ITetheringStationNotificationHandler'};
  *((_QWORD *)this + 1) = &Windows::Networking::UX::Internal::WlanClient::`vftable'{for `CServiceStatusListener'};
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 2) != -1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    Windows::Networking::UX::Internal::WlanClient::DeInit(this);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 )
    WPP_SF_(v2[2], 11, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
  Windows::Networking::UX::Internal::ProfileManager::~ProfileManager((Windows::Networking::UX::Internal::WlanClient *)((char *)this + 656));
  v3 = (void *)*((_QWORD *)this + 81);
  *((_QWORD *)this + 81) = 0;
  if ( v3 )
    WlanFreeMemory(v3);
  std::unique_ptr<Windows::Networking::UX::Internal::TetheringNotificationContext>::~unique_ptr<Windows::Networking::UX::Internal::TetheringNotificationContext>((char *)this + 640);
  std::unique_ptr<Windows::Networking::UX::Internal::TetheringNotificationContext>::~unique_ptr<Windows::Networking::UX::Internal::TetheringNotificationContext>((char *)this + 632);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 592));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    (char *)this + 584,
    v4,
    v5);
  *((_QWORD *)this + 3) = &CServiceMonitor::`vftable';
  CServiceMonitor::Stop((Windows::Networking::UX::Internal::WlanClient *)((char *)this + 24));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>((char *)this + 16);
}

```

## disassembly

```asm
0x18001239c  mov     [rsp+arg_0], rbx
0x1800123a1  mov     [rsp+arg_8], rsi
0x1800123a6  push    rdi
0x1800123a7  sub     rsp, 20h
0x1800123ab  mov     rbx, rcx
0x1800123ae  lea     rax, ??_7WlanClient@Internal@UX@Networking@Windows@@6BITetheringStationNotificationHandler@1234@@; const Windows::Networking::UX::Internal::WlanClient::`vftable'{for `Windows::Networking::UX::Internal::ITetheringStationNotificationHandler'}
0x1800123b5  mov     [rcx], rax
0x1800123b8  lea     rax, ??_7WlanClient@Internal@UX@Networking@Windows@@6BCServiceStatusListener@@@; const Windows::Networking::UX::Internal::WlanClient::`vftable'{for `CServiceStatusListener'}
0x1800123bf  mov     [rcx+8], rax
0x1800123c3  lea     rsi, WPP_GLOBAL_Control
0x1800123ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123d1  cmp     rcx, rsi
0x1800123d4  jz      short loc_1800123F8
0x1800123d6  test    byte ptr [rcx+1Ch], 40h
0x1800123da  jz      short loc_1800123F8
0x1800123dc  mov     edx, 0Ah
0x1800123e1  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x1800123e8  mov     rcx, [rcx+10h]
0x1800123ec  call    WPP_SF_
0x1800123f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123f8  cmp     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1800123fd  jz      short loc_180012413
0x1800123ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012404  mov     rcx, rbx; this
0x180012407  call    ?DeInit@WlanClient@Internal@UX@Networking@Windows@@QEAAXXZ; Windows::Networking::UX::Internal::WlanClient::DeInit(void)
0x18001240c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012413  cmp     rcx, rsi
0x180012416  jz      short loc_180012433
0x180012418  test    byte ptr [rcx+1Ch], 40h
0x18001241c  jz      short loc_180012433
0x18001241e  mov     edx, 0Bh
0x180012423  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001242a  mov     rcx, [rcx+10h]
0x18001242e  call    WPP_SF_
0x180012433  lea     rcx, [rbx+290h]; this
0x18001243a  call    ??1ProfileManager@Internal@UX@Networking@Windows@@QEAA@XZ; Windows::Networking::UX::Internal::ProfileManager::~ProfileManager(void)
0x18001243f  mov     rcx, [rbx+288h]; pMemory
0x180012446  mov     qword ptr [rbx+288h], 0
0x180012451  test    rcx, rcx
0x180012454  jz      short loc_18001245C
0x180012456  call    cs:__imp_WlanFreeMemory
0x18001245c  lea     rcx, [rbx+280h]
0x180012463  call    ??1?$unique_ptr@UTetheringNotificationContext@Internal@UX@Networking@Windows@@U?$default_delete@UTetheringNotificationContext@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::TetheringNotificationContext>::~unique_ptr<Windows::Networking::UX::Internal::TetheringNotificationContext>(void)
0x180012468  lea     rcx, [rbx+278h]
0x18001246f  call    ??1?$unique_ptr@UTetheringNotificationContext@Internal@UX@Networking@Windows@@U?$default_delete@UTetheringNotificationContext@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::TetheringNotificationContext>::~unique_ptr<Windows::Networking::UX::Internal::TetheringNotificationContext>(void)
0x180012474  lea     rcx, [rbx+250h]; lpCriticalSection
0x18001247b  call    cs:__imp_DeleteCriticalSection
0x180012481  lea     rcx, [rbx+248h]
0x180012488  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001248d  lea     rcx, [rbx+18h]; this
0x180012491  lea     rax, ??_7CServiceMonitor@@6B@; const CServiceMonitor::`vftable'
0x180012498  mov     [rcx], rax
0x18001249b  call    ?Stop@CServiceMonitor@@QEAAJXZ; CServiceMonitor::Stop(void)
0x1800124a0  lea     rcx, [rbx+10h]
0x1800124a4  mov     rbx, [rsp+28h+arg_0]
0x1800124a9  mov     rsi, [rsp+28h+arg_8]
0x1800124ae  add     rsp, 20h
0x1800124b2  pop     rdi
0x1800124b3  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWlanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWlanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
```
