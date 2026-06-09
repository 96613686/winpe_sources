# AppReadiness::Tasks::ActivateApps::OnStarted(void)

- ea: `0x18006ca30`
- end: `0x18006ccab`
- name: `?OnStarted@ActivateApps@Tasks@AppReadiness@@MEAAXXZ`
- size: `635`
- prototype: `void __fastcall(AppReadiness::Tasks::ActivateApps *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005270`
- `0x18000a470`
- `0x18000e4a0`
- `0x1800148b0`
- `0x180017e74`
- `0x180019260`
- `0x1800269b4`
- `0x180027a4c`
- `0x18002bf58`
- `0x18003e210`
- `0x18003eca8`
- `0x18003ecb4`
- `0x18006ca30`
- `0x180075ae0`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006cc75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006cc75`
- `ntdll!NtQueryWnfStateData` at `0x18006cb66`
- `ntdll!NtQueryWnfStateData` at `0x18006cb66`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18006cbf4`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18006cbf4`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQuerySystemStateBroadcastChannels` at `0x18006cada`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQuerySystemStateBroadcastChannels` at `0x18006cada`

## string_xrefs

- `0x18006caf3`: `onecoreuap\shell\appreadiness\src\tasks\activateapps.cpp`
- `0x18006cb7f`: `onecoreuap\shell\appreadiness\src\tasks\activateapps.cpp`
- `0x18006cc0d`: `onecoreuap\shell\appreadiness\src\tasks\activateapps.cpp`
- `0x18006caff`: `AppReadiness::Tasks::ActivateApps::OnStarted`
- `0x18006cb8b`: `AppReadiness::Tasks::ActivateApps::OnStarted`
- `0x18006cc19`: `AppReadiness::Tasks::ActivateApps::OnStarted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AppReadiness::Tasks::ActivateApps::OnStarted(AppReadiness::Tasks::ActivateApps *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  _QWORD *MainPackageId; // rax
  int SystemStateBroadcastChannels; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v15; // [rsp+58h] [rbp-A8h]
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v17; // [rsp+68h] [rbp-98h]
  __int64 v18; // [rsp+70h] [rbp-90h] BYREF
  _QWORD pExceptionObject[5]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v20[64]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-20h]
  _BYTE v22[4096]; // [rsp+100h] [rbp+0h] BYREF

  v2 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::ActivateApps *, PSRWLOCK *))(*(_QWORD *)this + 80LL))(
         this,
         &SRWLock);
  std::weak_ptr<AppReadiness::PackageInfo>::lock(v2, &v16);
  if ( v15 )
    std::_Ref_count_base::_Decwref(v15);
  v3 = (*(__int64 (__fastcall **)(AppReadiness::Tasks::ActivateApps *))(*(_QWORD *)this + 112LL))(this);
  MainPackageId = AppReadiness::PackageInfo::GetMainPackageId(v16, pExceptionObject, v3);
  std::wstring::operator=((char *)this + 336, MainPackageId);
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(pExceptionObject);
  memset_0(v20, 0, 0x60u);
  SystemStateBroadcastChannels = BiPtQuerySystemStateBroadcastChannels(v20);
  v6 = ResultFromWin32FromStatus(SystemStateBroadcastChannels);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v6,
      "BiPtQuerySystemStateBroadcastChannels(&channels)",
      "AppReadiness::Tasks::ActivateApps::OnStarted",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\activateapps.cpp",
      79);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v18 = v21;
  v12 = 4096;
  v11 = 0;
  v7 = NtQueryWnfStateData(&v18, 0, 0, &v11, v22, &v12);
  v8 = ResultFromWin32FromStatus(v7);
  if ( v8 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v8,
      "NtQueryWnfStateData(&stateName, 0, nullptr, &changeStamp, buffer, &bufferLen)",
      "AppReadiness::Tasks::ActivateApps::OnStarted",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\activateapps.cpp",
      85);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v13 = 0;
  v9 = RtlSubscribeWnfStateChangeNotification(
         &v13,
         v18,
         v11,
         AppReadiness::Tasks::ActivateApps::WnfCallback,
         this,
         0,
         0,
         0);
  v10 = ResultFromWin32FromStatus(v9);
  if ( v10 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v10,
      "RtlSubscribeWnfStateChangeNotification(&subscription, stateName, changeStamp, &ActivateApps::WnfCallback, this, nullptr, 0, 0)",
      "AppReadiness::Tasks::ActivateApps::OnStarted",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\activateapps.cpp",
      88);
    throw (Windows::HResultException *)pExceptionObject;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 56);
  *((_QWORD *)this + 31) = v18;
  *((_QWORD *)this + 32) = v13;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
}

```

## disassembly

```asm
0x18006ca30  mov     [rsp-8+arg_8], rbx
0x18006ca35  push    rbp
0x18006ca36  lea     rbp, [rsp-1010h]
0x18006ca3e  mov     eax, 1110h
0x18006ca43  call    _alloca_probe
0x18006ca48  sub     rsp, rax
0x18006ca4b  mov     rax, cs:__security_cookie
0x18006ca52  xor     rax, rsp
0x18006ca55  mov     [rbp+1010h+var_10], rax
0x18006ca5c  mov     rbx, rcx
0x18006ca5f  mov     rax, [rcx]
0x18006ca62  lea     rdx, [rsp+1110h+SRWLock]
0x18006ca67  mov     rax, [rax+50h]
0x18006ca6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca70  lea     rdx, [rsp+1110h+var_10B0]
0x18006ca75  mov     rcx, rax
0x18006ca78  call    ?lock@?$weak_ptr@VPackageInfo@AppReadiness@@@std@@QEBA?AV?$shared_ptr@VPackageInfo@AppReadiness@@@2@XZ; std::weak_ptr<AppReadiness::PackageInfo>::lock(void)
0x18006ca7d  nop
0x18006ca7e  mov     rcx, [rsp+1110h+var_10B8]; this
0x18006ca83  test    rcx, rcx
0x18006ca86  jz      short loc_18006CA8D
0x18006ca88  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18006ca8d  mov     rax, [rbx]
0x18006ca90  mov     rcx, rbx
0x18006ca93  mov     rax, [rax+70h]
0x18006ca97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca9c  mov     r8, rax
0x18006ca9f  lea     rdx, [rsp+1110h+pExceptionObject]
0x18006caa4  mov     rcx, [rsp+1110h+var_10B0]
0x18006caa9  call    ?GetMainPackageId@PackageInfo@AppReadiness@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVUser@2@@Z; AppReadiness::PackageInfo::GetMainPackageId(AppReadiness::User *)
0x18006caae  lea     rcx, [rbx+150h]
0x18006cab5  mov     rdx, rax
0x18006cab8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006cabd  lea     rcx, [rsp+1110h+pExceptionObject]
0x18006cac2  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18006cac7  xor     edx, edx; Val
0x18006cac9  lea     r8d, [rdx+60h]; Size
0x18006cacd  lea     rcx, [rbp+1010h+var_1070]; void *
0x18006cad1  call    memset_0
0x18006cad6  lea     rcx, [rbp+1010h+var_1070]
0x18006cada  call    cs:__imp_BiPtQuerySystemStateBroadcastChannels
0x18006cae0  mov     ecx, eax; int
0x18006cae2  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18006cae7  test    eax, eax
0x18006cae9  jns     short loc_18006CB2B
0x18006caeb  mov     [rsp+1110h+var_10E8], 4Fh ; 'O'; int
0x18006caf3  lea     rcx, aOnecoreuapShel_12; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18006cafa  mov     [rsp+1110h+var_10F0], rcx; char *
0x18006caff  lea     r9, aAppreadinessTa_5; "AppReadiness::Tasks::ActivateApps::OnSt"...
0x18006cb06  lea     r8, aBiptquerysyste_0; "BiPtQuerySystemStateBroadcastChannels(&"...
0x18006cb0d  mov     edx, eax; int
0x18006cb0f  lea     rcx, [rsp+1110h+pExceptionObject]; this
0x18006cb14  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18006cb19  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18006cb20  lea     rcx, [rsp+1110h+pExceptionObject]; pExceptionObject
0x18006cb25  call    _CxxThrowException_0
0x18006cb2b  mov     rax, [rbp+1010h+var_1030]
0x18006cb2f  mov     [rsp+1110h+var_10A0], rax
0x18006cb34  mov     [rsp+1110h+var_10CC], 1000h
0x18006cb3c  mov     [rsp+1110h+var_10D0], 0
0x18006cb44  lea     rax, [rsp+1110h+var_10CC]
0x18006cb49  mov     qword ptr [rsp+1110h+var_10E8], rax
0x18006cb4e  lea     rax, [rbp+1010h+var_1010]
0x18006cb52  mov     [rsp+1110h+var_10F0], rax
0x18006cb57  lea     r9, [rsp+1110h+var_10D0]
0x18006cb5c  xor     r8d, r8d
0x18006cb5f  xor     edx, edx
0x18006cb61  lea     rcx, [rsp+1110h+var_10A0]
0x18006cb66  call    cs:__imp_NtQueryWnfStateData
0x18006cb6c  mov     ecx, eax; int
0x18006cb6e  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18006cb73  test    eax, eax
0x18006cb75  jns     short loc_18006CBB7
0x18006cb77  mov     [rsp+1110h+var_10E8], 55h ; 'U'; int
0x18006cb7f  lea     rcx, aOnecoreuapShel_12; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18006cb86  mov     [rsp+1110h+var_10F0], rcx; char *
0x18006cb8b  lea     r9, aAppreadinessTa_5; "AppReadiness::Tasks::ActivateApps::OnSt"...
0x18006cb92  lea     r8, aNtquerywnfstat_0; "NtQueryWnfStateData(&stateName, 0, null"...
0x18006cb99  mov     edx, eax; int
0x18006cb9b  lea     rcx, [rsp+1110h+pExceptionObject]; this
0x18006cba0  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18006cba5  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18006cbac  lea     rcx, [rsp+1110h+pExceptionObject]; pExceptionObject
0x18006cbb1  call    _CxxThrowException_0
0x18006cbb7  mov     [rsp+1110h+var_10C8], 0
0x18006cbc0  mov     [rsp+1110h+var_10D8], 0
0x18006cbc8  mov     [rsp+1110h+var_10E0], 0
0x18006cbd0  mov     qword ptr [rsp+1110h+var_10E8], 0
0x18006cbd9  mov     [rsp+1110h+var_10F0], rbx
0x18006cbde  lea     r9, ?WnfCallback@ActivateApps@Tasks@AppReadiness@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; AppReadiness::Tasks::ActivateApps::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18006cbe5  mov     r8d, [rsp+1110h+var_10D0]
0x18006cbea  mov     rdx, [rsp+1110h+var_10A0]
0x18006cbef  lea     rcx, [rsp+1110h+var_10C8]
0x18006cbf4  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18006cbfa  mov     ecx, eax; int
0x18006cbfc  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18006cc01  test    eax, eax
0x18006cc03  jns     short loc_18006CC45
0x18006cc05  mov     [rsp+1110h+var_10E8], 58h ; 'X'; int
0x18006cc0d  lea     rcx, aOnecoreuapShel_12; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18006cc14  mov     [rsp+1110h+var_10F0], rcx; char *
0x18006cc19  lea     r9, aAppreadinessTa_5; "AppReadiness::Tasks::ActivateApps::OnSt"...
0x18006cc20  lea     r8, aRtlsubscribewn; "RtlSubscribeWnfStateChangeNotification("...
0x18006cc27  mov     edx, eax; int
0x18006cc29  lea     rcx, [rsp+1110h+pExceptionObject]; this
0x18006cc2e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18006cc33  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18006cc3a  lea     rcx, [rsp+1110h+pExceptionObject]; pExceptionObject
0x18006cc3f  call    _CxxThrowException_0
0x18006cc45  lea     rdx, [rbx+38h]
0x18006cc49  lea     rcx, [rsp+1110h+SRWLock]
0x18006cc4e  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18006cc53  mov     rax, [rsp+1110h+var_10A0]
0x18006cc58  mov     [rbx+0F8h], rax
0x18006cc5f  mov     rax, [rsp+1110h+var_10C8]
0x18006cc64  mov     [rbx+100h], rax
0x18006cc6b  mov     rcx, [rsp+1110h+SRWLock]; SRWLock
0x18006cc70  test    rcx, rcx
0x18006cc73  jz      short loc_18006CC7C
0x18006cc75  call    cs:__imp_ReleaseSRWLockExclusive
0x18006cc7b  nop
0x18006cc7c  mov     rcx, [rsp+1110h+var_10A8]; this
0x18006cc81  test    rcx, rcx
0x18006cc84  jz      short loc_18006CC8B
0x18006cc86  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006cc8b  mov     rcx, [rbp+1010h+var_10]
0x18006cc92  xor     rcx, rsp; StackCookie
0x18006cc95  call    __security_check_cookie
0x18006cc9a  mov     rbx, [rsp+1110h+arg_8]
0x18006cca2  add     rsp, 1110h
0x18006cca9  pop     rbp
0x18006ccaa  retn
```
