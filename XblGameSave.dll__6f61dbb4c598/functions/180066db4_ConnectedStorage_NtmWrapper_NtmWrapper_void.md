# ConnectedStorage::NtmWrapper::NtmWrapper(void)

- ea: `0x180066db4`
- end: `0x180066f15`
- name: `??0NtmWrapper@ConnectedStorage@@QEAA@XZ`
- size: `353`
- prototype: `char *__fastcall(char *pv)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003edec`
- `0x180041660`

## callees

- `0x18000a040`
- `0x18000aae4`
- `0x18000cbc8`
- `0x18000cc14`
- `0x18000cc58`
- `0x180010f88`
- `0x180011430`
- `0x180012ff8`
- `0x18001b9c8`
- `0x18003be5c`
- `0x180066d08`
- `0x180066db4`
- `0x1800678a8`
- `0x1800680bc`
- `0x1800682e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066ed0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066ddd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066e09`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066e5e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066ddd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066e09`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066e5e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180066eb3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180066eb3`

## string_xrefs

- `0x180066ee2`: `NtmWrapper -- CreateThreadpoolWait failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char *__fastcall ConnectedStorage::NtmWrapper::NtmWrapper(char *pv)
{
  const WCHAR *v2; // rax
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  const unsigned __int16 *v5; // r8
  _BYTE v7[64]; // [rsp+20h] [rbp-58h] BYREF

  *(_QWORD *)pv = &ConnectedStorage::NtmWrapper::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)(pv + 8));
  *((_DWORD *)pv + 12) = 0;
  *((_QWORD *)pv + 7) = 0;
  ConnectedStorage::NtmWrapper::MakeEventName(pv + 64);
  pv[96] = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(pv + 104));
  *((_DWORD *)pv + 36) = 0;
  std::list<ConnectedStorage::NtmTransferWrapper>::list<ConnectedStorage::NtmTransferWrapper>(pv + 152);
  std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(pv + 168);
  std::list<_GUID>::_Alloc_sentinel_and_proxy();
  *((_DWORD *)pv + 46) = 0;
  std::unique_ptr<ConnectedStorage::File>::unique_ptr<ConnectedStorage::File>((_QWORD *)pv + 24);
  InitializeCriticalSection((LPCRITICAL_SECTION)pv + 5);
  *((_DWORD *)pv + 60) = 0;
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(pv + 64);
  ConnectedStorage::Event::Event((_QWORD *)pv + 31, 0, v2);
  ConnectedStorage::NtmProvider::NtmProvider((ConnectedStorage::NtmProvider *)v7);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(pv + 56);
  ConnectedStorage::NtmProvider::CreateInstance(
    (ConnectedStorage::NtmProvider *)v7,
    (struct INetworkTransferManager **)pv + 7);
  ThreadpoolWait = CreateThreadpoolWait(ConnectedStorage::NtmWrapper::StaticThreadpoolWaitCallback, pv, 0);
  std::unique_ptr<_TP_WAIT,ConnectedStorage::TpWaitCloser>::reset(pv + 192, ThreadpoolWait);
  if ( !(unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(pv + 192) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)LastError,
      (int)L"NtmWrapper -- CreateThreadpoolWait failed",
      v5);
  }
  ConnectedStorage::NtmProvider::~NtmProvider((ConnectedStorage::NtmProvider *)v7);
  return pv;
}

```

## disassembly

```asm
0x180066db4  mov     [rsp+arg_8], rbx
0x180066db9  mov     [rsp+arg_10], rsi
0x180066dbe  mov     [rsp+arg_0], rcx
0x180066dc3  push    rdi
0x180066dc4  push    r14
0x180066dc6  push    r15
0x180066dc8  sub     rsp, 60h
0x180066dcc  mov     r15, rcx
0x180066dcf  lea     rax, ??_7NtmWrapper@ConnectedStorage@@6B@; const ConnectedStorage::NtmWrapper::`vftable'
0x180066dd6  mov     [rcx], rax
0x180066dd9  add     rcx, 8; lpCriticalSection
0x180066ddd  call    cs:__imp_InitializeCriticalSection
0x180066de3  mov     dword ptr [r15+30h], 0
0x180066deb  lea     r14, [r15+38h]
0x180066def  mov     qword ptr [r14], 0
0x180066df6  lea     rcx, [r15+40h]
0x180066dfa  call    ?MakeEventName@NtmWrapper@ConnectedStorage@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConnectedStorage::NtmWrapper::MakeEventName(void)
0x180066dff  nop
0x180066e00  mov     byte ptr [r15+60h], 0
0x180066e05  lea     rcx, [r15+68h]; lpCriticalSection
0x180066e09  call    cs:__imp_InitializeCriticalSection
0x180066e0f  mov     dword ptr [r15+90h], 0
0x180066e1a  lea     rcx, [r15+98h]
0x180066e21  call    ??0?$list@VNtmTransferWrapper@ConnectedStorage@@V?$allocator@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::list<ConnectedStorage::NtmTransferWrapper>::list<ConnectedStorage::NtmTransferWrapper>(void)
0x180066e26  nop
0x180066e27  lea     rcx, [r15+0A8h]
0x180066e2e  call    ??0?$weak_ptr@VAtomManager@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(void)
0x180066e33  call    ?_Alloc_sentinel_and_proxy@?$list@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAXXZ; std::list<_GUID>::_Alloc_sentinel_and_proxy(void)
0x180066e38  nop
0x180066e39  mov     dword ptr [r15+0B8h], 0
0x180066e44  lea     rsi, [r15+0C0h]
0x180066e4b  mov     rcx, rsi
0x180066e4e  call    ??$?0U?$default_delete@VFile@ConnectedStorage@@@std@@$0A@@?$unique_ptr@VFile@ConnectedStorage@@U?$default_delete@VFile@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConnectedStorage::File>::unique_ptr<ConnectedStorage::File>(void)
0x180066e53  nop
0x180066e54  lea     rbx, [r15+0C8h]
0x180066e5b  mov     rcx, rbx; lpCriticalSection
0x180066e5e  call    cs:__imp_InitializeCriticalSection
0x180066e64  mov     dword ptr [rbx+28h], 0
0x180066e6b  lea     rcx, [r15+40h]
0x180066e6f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180066e74  lea     rcx, [r15+0F8h]
0x180066e7b  mov     r8, rax
0x180066e7e  xor     edx, edx
0x180066e80  call    ??0Event@ConnectedStorage@@QEAA@W4ResetMode@01@PEBG@Z; ConnectedStorage::Event::Event(ConnectedStorage::Event::ResetMode,ushort const *)
0x180066e85  nop
0x180066e86  lea     rcx, [rsp+78h+var_58]; this
0x180066e8b  call    ??0NtmProvider@ConnectedStorage@@QEAA@XZ; ConnectedStorage::NtmProvider::NtmProvider(void)
0x180066e90  nop
0x180066e91  mov     rcx, r14
0x180066e94  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066e99  mov     rdx, r14; struct INetworkTransferManager **
0x180066e9c  lea     rcx, [rsp+78h+var_58]; this
0x180066ea1  call    ?CreateInstance@NtmProvider@ConnectedStorage@@QEAAXPEAPEAUINetworkTransferManager@@@Z; ConnectedStorage::NtmProvider::CreateInstance(INetworkTransferManager * *)
0x180066ea6  xor     r8d, r8d; pcbe
0x180066ea9  mov     rdx, r15; pv
0x180066eac  lea     rcx, ?StaticThreadpoolWaitCallback@NtmWrapper@ConnectedStorage@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180066eb3  call    cs:__imp_CreateThreadpoolWait
0x180066eb9  mov     rdx, rax
0x180066ebc  mov     rcx, rsi
0x180066ebf  call    ?reset@?$unique_ptr@U_TP_WAIT@@UTpWaitCloser@ConnectedStorage@@@std@@QEAAXPEAU_TP_WAIT@@@Z; std::unique_ptr<_TP_WAIT,ConnectedStorage::TpWaitCloser>::reset(_TP_WAIT *)
0x180066ec4  mov     rcx, rsi
0x180066ec7  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x180066ecc  test    al, al
0x180066ece  jnz     short loc_180066EF1
0x180066ed0  call    cs:__imp_GetLastError
0x180066ed6  test    eax, eax
0x180066ed8  jle     short loc_180066EE2
0x180066eda  movzx   eax, ax
0x180066edd  or      eax, 80070000h
0x180066ee2  lea     rdx, aNtmwrapperCrea; "NtmWrapper -- CreateThreadpoolWait fail"...
0x180066ee9  mov     ecx, eax; this
0x180066eeb  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180066ef1  lea     rcx, [rsp+78h+var_58]; this
0x180066ef6  call    ??1NtmProvider@ConnectedStorage@@QEAA@XZ; ConnectedStorage::NtmProvider::~NtmProvider(void)
0x180066efb  nop
0x180066efc  mov     rax, r15
0x180066eff  lea     r11, [rsp+78h+var_18]
0x180066f04  mov     rbx, [r11+28h]
0x180066f08  mov     rsi, [r11+30h]
0x180066f0c  mov     rsp, r11
0x180066f0f  pop     r15
0x180066f11  pop     r14
0x180066f13  pop     rdi
0x180066f14  retn
```
