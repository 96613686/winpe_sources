# CAudioPump::~CAudioPump(void)

- ea: `0x140016c94`
- end: `0x140016ee3`
- name: `??1CAudioPump@@QEAA@XZ`
- size: `591`
- prototype: `void __fastcall(CAudioPump *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140016c48`

## callees

- `0x140008124`
- `0x14000a39c`
- `0x14000e590`
- `0x1400121d0`
- `0x1400127bc`
- `0x140016c94`
- `0x140016eec`
- `0x140016f30`
- `0x140016f68`
- `0x140070fa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016dc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016dc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140016ea5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140016eb2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140016ea5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140016eb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016d77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016d77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016d18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016d05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016d10`
- `ntdll!NtSetTimerResolution` at `0x140016d9a`
- `ntdll!NtSetTimerResolution` at `0x140016d9a`

## pseudocode

```c
void __fastcall CAudioPump::~CAudioPump(CAudioPump *this)
{
  wil::details **v2; // rbp
  wil::details **v3; // r12
  char *v4; // rsi
  DWORD LastError; // ebx
  wil::details **v6; // r13
  const char *v7; // r9
  wil::details **v8; // rbx
  void *v9; // rdx
  wil::details *v10; // rcx
  void *v11; // rdx
  void *v12; // rdx
  void *v13; // rdx
  wil::details *v14; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  ULONG ActualResolution; // [rsp+70h] [rbp+8h] BYREF

  *(_QWORD *)this = &CAudioPump::`vftable'{for `IAudioPump'};
  *((_QWORD *)this + 1) = &CAudioPump::`vftable'{for `IAudioPumpLogging'};
  if ( (unsigned __int64)(*((_QWORD *)this + 15) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CAudioPump::SignalAndWaitForThread(this);
  v2 = (wil::details **)((char *)this + 280);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 280,
    0);
  v3 = (wil::details **)((char *)this + 288);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 288,
    0);
  v4 = (char *)*((_QWORD *)this + 37);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v4);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 37) = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 264,
    0);
  wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset((char *)this + 408);
  wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset((char *)this + 424);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 432,
    0);
  v6 = (wil::details **)((char *)this + 416);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 416,
    0);
  if ( *((_BYTE *)this + 73) )
  {
    EnterCriticalSection(&CAudioPump::s_AudioPumpTimerResolutionCountLock);
    if ( _InterlockedExchangeAdd(&CAudioPump::s_AudioPumpTimerResolutionCount, 0xFFFFFFFF) == 1 )
    {
      ActualResolution = 0;
      if ( NtSetTimerResolution(0, 0, &ActualResolution) < 0 )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x8B9,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
          v7);
    }
    LeaveCriticalSection(&CAudioPump::s_AudioPumpTimerResolutionCountLock);
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset((char *)this + 80);
  wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset((char *)this + 208);
  v8 = (wil::details **)((char *)this + 312);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 312,
    0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((char *)this + 4720);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 4688);
  v10 = (wil::details *)*((_QWORD *)this + 54);
  if ( v10 )
    wil::details::CloseHandle(v10, v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 424);
  if ( *v6 )
    wil::details::CloseHandle(*v6, v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 408);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 328);
  if ( *v8 )
    wil::details::CloseHandle(*v8, v12);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 296);
  if ( *v3 )
    wil::details::CloseHandle(*v3, v13);
  if ( *v2 )
    wil::details::CloseHandle(*v2, v13);
  v14 = (wil::details *)*((_QWORD *)this + 33);
  if ( v14 )
    wil::details::CloseHandle(v14, v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 256);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 208);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 120);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 80);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CAudioPump *)((char *)this + 24));
}

```

## disassembly

```asm
0x140016c94  push    rbx
0x140016c96  push    rbp
0x140016c97  push    rsi
0x140016c98  push    rdi
0x140016c99  push    r12
0x140016c9b  push    r13
0x140016c9d  push    r14
0x140016c9f  push    r15
0x140016ca1  sub     rsp, 28h
0x140016ca5  mov     rdi, rcx
0x140016ca8  lea     rax, ??_7CAudioPump@@6BIAudioPump@@@; const CAudioPump::`vftable'{for `IAudioPump'}
0x140016caf  mov     [rcx], rax
0x140016cb2  lea     rax, ??_7CAudioPump@@6BIAudioPumpLogging@@@; const CAudioPump::`vftable'{for `IAudioPumpLogging'}
0x140016cb9  mov     [rcx+8], rax
0x140016cbd  mov     rax, [rcx+78h]
0x140016cc1  dec     rax
0x140016cc4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140016cc8  ja      short loc_140016CCF
0x140016cca  call    ?SignalAndWaitForThread@CAudioPump@@AEAAXXZ; CAudioPump::SignalAndWaitForThread(void)
0x140016ccf  lea     rbp, [rdi+118h]
0x140016cd6  xor     edx, edx
0x140016cd8  mov     rcx, rbp
0x140016cdb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140016ce0  lea     r12, [rdi+120h]
0x140016ce7  xor     edx, edx
0x140016ce9  mov     rcx, r12
0x140016cec  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140016cf1  lea     r14, [rdi+128h]
0x140016cf8  mov     rsi, [r14]
0x140016cfb  lea     rax, [rsi-1]
0x140016cff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140016d03  ja      short loc_140016D1E
0x140016d05  call    cs:__imp_GetLastError
0x140016d0b  mov     ebx, eax
0x140016d0d  mov     rcx, rsi; hObject
0x140016d10  call    cs:__imp_CloseHandle
0x140016d16  mov     ecx, ebx; dwErrCode
0x140016d18  call    cs:__imp_SetLastError
0x140016d1e  xor     ebx, ebx
0x140016d20  mov     [r14], rbx
0x140016d23  lea     rcx, [rdi+108h]
0x140016d2a  xor     edx, edx
0x140016d2c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140016d31  lea     rcx, [rdi+198h]
0x140016d38  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x140016d3d  lea     rsi, [rdi+1A8h]
0x140016d44  mov     rcx, rsi
0x140016d47  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x140016d4c  lea     rcx, [rdi+1B0h]
0x140016d53  xor     edx, edx
0x140016d55  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140016d5a  lea     r13, [rdi+1A0h]
0x140016d61  xor     edx, edx
0x140016d63  mov     rcx, r13
0x140016d66  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140016d6b  cmp     [rdi+49h], bl
0x140016d6e  jz      short loc_140016DC7
0x140016d70  lea     rcx, ?s_AudioPumpTimerResolutionCountLock@CAudioPump@@1Vcritical_section@wil@@A; lpCriticalSection
0x140016d77  call    cs:__imp_EnterCriticalSection
0x140016d7d  or      eax, 0FFFFFFFFh
0x140016d80  lock xadd cs:?s_AudioPumpTimerResolutionCount@CAudioPump@@1JA, eax; long CAudioPump::s_AudioPumpTimerResolutionCount
0x140016d88  cmp     eax, 1
0x140016d8b  jnz     short loc_140016DBA
0x140016d8d  mov     [rsp+68h+ActualResolution], ebx
0x140016d91  lea     r8, [rsp+68h+ActualResolution]; ActualResolution
0x140016d96  xor     edx, edx; SetOrUnset
0x140016d98  xor     ecx, ecx; RequestedResolution
0x140016d9a  call    cs:__imp_NtSetTimerResolution
0x140016da0  test    eax, eax
0x140016da2  jns     short loc_140016DBA
0x140016da4  mov     rcx, [rsp+68h]; this
0x140016da9  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140016db0  mov     edx, 8B9h; void *
0x140016db5  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140016dba  lea     rcx, ?s_AudioPumpTimerResolutionCountLock@CAudioPump@@1Vcritical_section@wil@@A; lpCriticalSection
0x140016dc1  call    cs:__imp_LeaveCriticalSection
0x140016dc7  lea     rcx, [rdi+50h]
0x140016dcb  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x140016dd0  lea     rcx, [rdi+0D0h]
0x140016dd7  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x140016ddc  lea     rbx, [rdi+138h]
0x140016de3  xor     edx, edx
0x140016de5  mov     rcx, rbx
0x140016de8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140016ded  lea     rcx, [rdi+1270h]
0x140016df4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140016df9  lea     rcx, [rdi+1250h]
0x140016e00  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140016e05  mov     rcx, [rdi+1B0h]; this
0x140016e0c  test    rcx, rcx
0x140016e0f  jz      short loc_140016E16
0x140016e11  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140016e16  mov     rcx, rsi
0x140016e19  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140016e1e  mov     rcx, [r13+0]; this
0x140016e22  test    rcx, rcx
0x140016e25  jz      short loc_140016E2C
0x140016e27  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140016e2c  lea     rcx, [rdi+198h]
0x140016e33  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140016e38  lea     rcx, [rdi+148h]
0x140016e3f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140016e44  mov     rcx, [rbx]; this
0x140016e47  test    rcx, rcx
0x140016e4a  jz      short loc_140016E51
0x140016e4c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140016e51  mov     rcx, r14
0x140016e54  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140016e59  mov     rcx, [r12]; this
0x140016e5d  test    rcx, rcx
0x140016e60  jz      short loc_140016E67
0x140016e62  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140016e67  mov     rcx, [rbp+0]; this
0x140016e6b  test    rcx, rcx
0x140016e6e  jz      short loc_140016E75
0x140016e70  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140016e75  mov     rcx, [rdi+108h]; this
0x140016e7c  test    rcx, rcx
0x140016e7f  jz      short loc_140016E86
0x140016e81  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140016e86  lea     rcx, [rdi+100h]
0x140016e8d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140016e92  lea     rcx, [rdi+0D0h]
0x140016e99  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140016e9e  lea     rcx, [rdi+0A8h]; lpCriticalSection
0x140016ea5  call    cs:__imp_DeleteCriticalSection
0x140016eab  lea     rcx, [rdi+80h]; lpCriticalSection
0x140016eb2  call    cs:__imp_DeleteCriticalSection
0x140016eb8  lea     rcx, [rdi+78h]
0x140016ebc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140016ec1  lea     rcx, [rdi+50h]
0x140016ec5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140016eca  lea     rcx, [rdi+18h]; this
0x140016ece  add     rsp, 28h
0x140016ed2  pop     r15
0x140016ed4  pop     r14
0x140016ed6  pop     r13
0x140016ed8  pop     r12
0x140016eda  pop     rdi
0x140016edb  pop     rsi
0x140016edc  pop     rbp
0x140016edd  pop     rbx
0x140016ede  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
