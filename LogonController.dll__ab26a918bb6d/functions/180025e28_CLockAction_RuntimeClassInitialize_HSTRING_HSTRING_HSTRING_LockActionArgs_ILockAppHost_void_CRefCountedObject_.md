# CLockAction::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *,HSTRING__ *,LockActionArgs *,ILockAppHost *,void *,CRefCountedObject<LockScreenCpuBooster> *,CRefCountedObject<LockScreenIOBooster> *)

- ea: `0x180025e28`
- end: `0x180026489`
- name: `?RuntimeClassInitialize@CLockAction@@QEAAJPEAUHSTRING__@@00PEAVLockActionArgs@@PEAUILockAppHost@@PEAXPEAV?$CRefCountedObject@VLockScreenCpuBooster@@@@PEAV?$CRefCountedObject@VLockScreenIOBooster@@@@@Z`
- size: `1633`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, HANDLE hSourceHandle, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025ac0`

## callees

- `0x180008094`
- `0x18000df10`
- `0x180017dec`
- `0x18001c56c`
- `0x18001c860`
- `0x18001db70`
- `0x18001f3a0`
- `0x180025220`
- `0x180025e28`
- `0x180026490`
- `0x180026824`
- `0x180026e70`
- `0x180026ea0`
- `0x180028b8c`
- `0x18002f554`
- `0x1800315a0`
- `0x18003fa40`
- `0x180044f68`
- `0x18005b3e4`
- `0x18005d488`
- `0x18005d4e8`
- `0x180065bac`
- `0x18006c000`
- `0x18008d4c0`
- `0x18008e560`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x1800261fc`
- `KERNEL32!DuplicateHandle` at `0x1800261fc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002622e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026401`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026435`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002622e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026401`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026435`
- `KERNEL32!GetCurrentProcess` at `0x1800261cd`
- `KERNEL32!GetCurrentProcess` at `0x1800261d6`
- `KERNEL32!GetCurrentProcess` at `0x1800261cd`
- `KERNEL32!GetCurrentProcess` at `0x1800261d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025f1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025f1d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800263a5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800263a5`
- `ntdll!NtPowerInformation` at `0x180026283`
- `ntdll!NtPowerInformation` at `0x180026283`

## pseudocode

```c
__int64 __fastcall CLockAction::RuntimeClassInitialize(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        __int64 a5,
        struct ILockAppHost *a6,
        HANDLE hSourceHandle,
        void *a8,
        void *a9)
{
  HRESULT v10; // eax
  unsigned int LastError; // edi
  LPVOID v12; // rcx
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, __int64 *, GUID *, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, _QWORD); // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64); // rsi
  unsigned int v23; // r9d
  __int64 v24; // rcx
  __int64 v25; // rcx
  HANDLE CurrentProcess; // rbx
  HANDLE v27; // rax
  const char *v28; // r9
  int v29; // eax
  NTSTATUS v30; // eax
  HRESULT Guid; // eax
  __int64 v32; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v39; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v40; // [rsp+58h] [rbp-A8h] BYREF
  int OutputBuffer; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v43; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v44; // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER Buf1; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h]
  _QWORD v47[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v43 = a2;
  v44 = a3;
  v39 = a4;
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v47,
    "CLockAction_RuntimeClassInitialize_Activity");
  v47[0] = &LogonControllerTelemetry::CLockAction_RuntimeClassInitialize_Activity::`vftable';
  *(struct _GUID *)&Buf1.Reserved.Reserved1 = *GetFirstRunTelemetryCorrelationId((struct _GUID *)&Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v47,
      &Buf1);
  LogonControllerTelemetry::CLockAction_RuntimeClassInitialize_Activity::StartActivity((LogonControllerTelemetry::CLockAction_RuntimeClassInitialize_Activity *)v47);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockReliability_UnlockIfLockAppDidntShow>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_LockReliability_UnlockIfLockAppDidntShow>::GetImpl'::`2'::impl);
  *(_BYTE *)(a1 + 565) = 1;
  v40 = 0;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v40);
  v10 = CoCreateInstance(
          &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
          0,
          0x404u,
          &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
          &v40);
  LastError = v10;
  if ( v10 >= 0 )
  {
    v13 = v40;
    v42 = 0;
    v14 = *(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, __int64 *))(*(_QWORD *)v40 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v42);
    v15 = v14(v13, qword_1800AFCF0, &GUID_2e8fcb18_a0ee_41ad_8ef8_77fb3a370ca5, &v42);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
        (const char *)(unsigned int)v15,
        ppv);
LABEL_64:
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v40);
      LogonControllerTelemetry::CLockAction_RuntimeClassInitialize_Activity::~CLockAction_RuntimeClassInitialize_Activity((LogonControllerTelemetry::CLockAction_RuntimeClassInitialize_Activity *)v47);
      return LastError;
    }
    v16 = v42;
    v37 = 0;
    v17 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v42 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v37);
    v46 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &Buf1,
      L"Windows.Internal.ShellExperience.LockScreen",
      0x2Cu,
      0x2Bu);
    v18 = v17(v16, v46, &v37);
    LastError = v18;
    if ( v18 >= 0 )
    {
      v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
      v22 = **v37;
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(a1 + 432);
      v18 = v22(v21, &GUID_a40cce11_67ee_4e74_8c46_91edb265261c, a1 + 432);
      LastError = v18;
      if ( v18 >= 0 )
      {
        if ( !*(_BYTE *)(a1 + 565) || CLockAction::s_numberOfConsecutiveUnlocksIfLockAppDidntShow < 1 )
        {
          if ( dword_1800D354C == -1 )
          {
            dword_1800D354C = 0;
            LODWORD(SRWLock) = 0;
            if ( (int)SHRegGetBOOLWithREGSAM(
                        HKEY_LOCAL_MACHINE,
                        L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\TestHooks",
                        L"DebugBackstopVisual",
                        v23,
                        (int *)&SRWLock) >= 0 )
            {
              if ( (_DWORD)SRWLock )
                dword_1800D354C = 1;
            }
          }
          Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 320);
          *(_BYTE *)(a1 + 256) = *(_BYTE *)a5;
          *(_BYTE *)(a1 + 257) = *(_BYTE *)(a5 + 1);
          *(_BYTE *)(a1 + 258) = *(_BYTE *)(a5 + 2);
          *(_BYTE *)(a1 + 259) = *(_BYTE *)(a5 + 3);
          *(_BYTE *)(a1 + 260) = *(_BYTE *)(a5 + 4);
          if ( *(void **)(a1 + 576) != a8 )
          {
            Buf1.Reserved.Reserved1 = a8;
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::InternalAddRef(&Buf1);
            v24 = *(_QWORD *)(a1 + 576);
            *(_QWORD *)(a1 + 576) = a8;
            if ( v24 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
          if ( *(void **)(a1 + 584) != a9 )
          {
            Buf1.Reserved.Reserved1 = a9;
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::InternalAddRef(&Buf1);
            v25 = *(_QWORD *)(a1 + 584);
            *(_QWORD *)(a1 + 584) = a9;
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          CurrentProcess = GetCurrentProcess();
          v27 = GetCurrentProcess();
          if ( DuplicateHandle(v27, hSourceHandle, CurrentProcess, (LPHANDLE)(a1 + 448), 0, 0, 2u) )
          {
            v29 = CLockAction::_SubscribeToPowerSettingNotifications((CLockAction *)a1);
            if ( v29 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xA5,
                (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
                (const char *)(unsigned int)v29,
                ppva);
            *(_BYTE *)(a1 + 316) = 1;
            OutputBuffer = 0;
            v30 = NtPowerInformation(SystemVideoState, 0, 0, &OutputBuffer, 4u);
            if ( v30 >= 0 )
              *(_BYTE *)(a1 + 316) = OutputBuffer != 0;
            else
              wil::details::in1diag3::_Log_NtStatus(
                retaddr,
                (void *)0xAA,
                (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
                (const char *)(unsigned int)v30,
                ppvb);
            Guid = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 208), &v43);
            LastError = Guid;
            if ( Guid >= 0 )
            {
              Guid = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 216), &v44);
              LastError = Guid;
              if ( Guid >= 0 )
              {
                Guid = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 224), &v39);
                LastError = Guid;
                if ( Guid >= 0 )
                {
                  v39 = *(HSTRING *)(a5 + 8);
                  Guid = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 232), &v39);
                  LastError = Guid;
                  if ( Guid >= 0 )
                  {
                    v39 = *(HSTRING *)(a5 + 16);
                    Guid = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 240), &v39);
                    LastError = Guid;
                    if ( Guid >= 0 )
                    {
                      v39 = *(HSTRING *)(a5 + 24);
                      Guid = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 248), &v39);
                      LastError = Guid;
                      if ( Guid >= 0 )
                      {
                        Guid = CoCreateGuid((GUID *)(a1 + 288));
                        LastError = Guid;
                        if ( Guid >= 0 )
                        {
                          Guid = CLockAction::_CacheLockAppHostInstance((CLockAction *)a1, a6);
                          LastError = Guid;
                          if ( Guid >= 0 )
                          {
                            Guid = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 32) + 104LL))(a1 + 32);
                            LastError = Guid;
                            if ( Guid >= 0 )
                            {
                              wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
                                v47,
                                0);
                              if ( SRWLock )
                                ReleaseSRWLockExclusive(SRWLock);
                              Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v37);
                              LastError = 0;
                              goto LABEL_64;
                            }
                            if ( Guid == -2147417825 )
                            {
                              if ( SRWLock )
                                ReleaseSRWLockExclusive(SRWLock);
                              Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v37);
                              LastError = -2147417825;
                              goto LABEL_64;
                            }
                            v32 = 183;
                          }
                          else
                          {
                            v32 = 182;
                          }
                        }
                        else
                        {
                          v32 = 181;
                        }
                      }
                      else
                      {
                        v32 = 180;
                      }
                    }
                    else
                    {
                      v32 = 179;
                    }
                  }
                  else
                  {
                    v32 = 178;
                  }
                }
                else
                {
                  v32 = 177;
                }
              }
              else
              {
                v32 = 176;
              }
            }
            else
            {
              v32 = 175;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v32,
              (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
              (const char *)(unsigned int)Guid,
              ppvb);
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0xA1,
                          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
                          v28);
          }
          if ( SRWLock )
            ReleaseSRWLockExclusive(SRWLock);
          goto LABEL_13;
        }
        LogonControllerTelemetry::AbortingDueToConsecutiveLockAppShownFailures();
        LastError = -2147467260;
        v19 = 126;
        v20 = 2147500036LL;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
          (const char *)v20,
          ppv);
LABEL_13:
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v37);
        goto LABEL_64;
      }
      v19 = 116;
    }
    else
    {
      v19 = 115;
    }
    v20 = (unsigned int)v18;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6F,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockaction.cpp",
    (const char *)(unsigned int)v10,
    ppv);
  v12 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v47[0] = &LogonControllerTelemetry::CLockAction_RuntimeClassInitialize_Activity::`vftable';
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v47);
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v47);
  return LastError;
}

```

## disassembly

```asm
0x180025e28  push    rbp
0x180025e2a  push    rbx
0x180025e2b  push    rsi
0x180025e2c  push    rdi
0x180025e2d  push    r12
0x180025e2f  push    r13
0x180025e31  push    r14
0x180025e33  push    r15
0x180025e35  lea     rbp, [rsp-108h]
0x180025e3d  sub     rsp, 208h
0x180025e44  mov     rax, cs:__security_cookie
0x180025e4b  xor     rax, rsp
0x180025e4e  mov     [rbp+140h+var_50], rax
0x180025e55  mov     r15, [rbp+140h+arg_20]
0x180025e5c  mov     r14, rcx
0x180025e5f  mov     r13, [rbp+140h+arg_28]
0x180025e66  lea     rcx, [rbp+140h+var_1A0]
0x180025e6a  mov     r12, [rbp+140h+hSourceHandle]
0x180025e71  mov     [rsp+240h+var_1D0], rdx
0x180025e76  lea     rdx, aClockactionRun; "CLockAction_RuntimeClassInitialize_Acti"...
0x180025e7d  mov     [rsp+240h+var_1C8], r8
0x180025e82  mov     [rsp+240h+var_1F0], r9
0x180025e87  call    ??0?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180025e8c  lea     rax, ??_7CLockAction_RuntimeClassInitialize_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockAction_RuntimeClassInitialize_Activity::`vftable'
0x180025e93  lea     rcx, [rbp+140h+Buf1]; retstr
0x180025e97  mov     [rbp+140h+var_1A0], rax
0x180025e9b  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x180025ea0  mov     r8d, 10h; Size
0x180025ea6  lea     rdx, GUID_NULL; Buf2
0x180025ead  lea     rcx, [rbp+140h+Buf1]; Buf1
0x180025eb1  movups  xmm0, xmmword ptr [rax]
0x180025eb4  movdqu  xmmword ptr [rbp+140h+Buf1], xmm0
0x180025eb9  call    memcmp_0
0x180025ebe  xor     esi, esi
0x180025ec0  test    eax, eax
0x180025ec2  jz      short loc_180025ED1
0x180025ec4  lea     rdx, [rbp+140h+Buf1]
0x180025ec8  lea     rcx, [rbp+140h+var_1A0]
0x180025ecc  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x180025ed1  lea     rcx, [rbp+140h+var_1A0]; this
0x180025ed5  call    ?StartActivity@CLockAction_RuntimeClassInitialize_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLockAction_RuntimeClassInitialize_Activity::StartActivity(void)
0x180025eda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LockReliability_UnlockIfLockAppDidntShow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LockReliability_UnlockIfLockAppDidntShow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockReliability_UnlockIfLockAppDidntShow> `wil::Feature<__WilFeatureTraits_Feature_LockReliability_UnlockIfLockAppDidntShow>::GetImpl(void)'::`2'::impl
0x180025ee1  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_LockReliability_UnlockIfLockAppDidntShow@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LockReliability_UnlockIfLockAppDidntShow>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180025ee6  lea     rcx, [rsp+240h+var_1E8]
0x180025eeb  mov     byte ptr [r14+235h], 1
0x180025ef3  mov     [rsp+240h+var_1E8], rsi
0x180025ef8  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180025efd  lea     rax, [rsp+240h+var_1E8]
0x180025f02  xor     edx, edx; pUnkOuter
0x180025f04  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180025f0b  mov     [rsp+240h+ppv], rax; int
0x180025f10  mov     r8d, 404h; dwClsContext
0x180025f16  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180025f1d  call    cs:__imp_CoCreateInstance
0x180025f23  mov     edi, eax
0x180025f25  test    eax, eax
0x180025f27  jns     short loc_180025F81
0x180025f29  mov     rcx, [rbp+148h]; this
0x180025f30  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x180025f37  mov     r9d, eax; char *
0x180025f3a  mov     edx, 6Fh ; 'o'; void *
0x180025f3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f44  mov     rcx, [rsp+240h+var_1E8]
0x180025f49  test    rcx, rcx
0x180025f4c  jz      short loc_180025F5F
0x180025f4e  mov     [rsp+240h+var_1E8], rsi
0x180025f53  mov     rax, [rcx]
0x180025f56  mov     rax, [rax+10h]
0x180025f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f5f  lea     rax, ??_7CLockAction_RuntimeClassInitialize_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockAction_RuntimeClassInitialize_Activity::`vftable'
0x180025f66  lea     rcx, [rbp+140h+var_1A0]
0x180025f6a  mov     [rbp+140h+var_1A0], rax
0x180025f6e  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180025f73  lea     rcx, [rbp+140h+var_1A0]
0x180025f77  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180025f7c  jmp     loc_180026464
0x180025f81  mov     rdi, [rsp+240h+var_1E8]
0x180025f86  lea     rcx, [rsp+240h+var_1D8]
0x180025f8b  mov     [rsp+240h+var_1D8], rsi
0x180025f90  mov     rax, [rdi]
0x180025f93  mov     rbx, [rax+18h]
0x180025f97  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180025f9c  lea     r9, [rsp+240h+var_1D8]
0x180025fa1  mov     rcx, rdi
0x180025fa4  lea     r8, _GUID_2e8fcb18_a0ee_41ad_8ef8_77fb3a370ca5
0x180025fab  mov     rax, rbx
0x180025fae  lea     rdx, qword_1800AFCF0
0x180025fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fba  mov     edi, eax
0x180025fbc  test    eax, eax
0x180025fbe  jns     short loc_180025FE0
0x180025fc0  mov     rcx, [rbp+148h]; this
0x180025fc7  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x180025fce  mov     r9d, eax; char *
0x180025fd1  mov     edx, 71h ; 'q'; void *
0x180025fd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025fdb  jmp     loc_180026447
0x180025fe0  mov     rdi, [rsp+240h+var_1D8]
0x180025fe5  lea     rcx, [rsp+240h+var_200]
0x180025fea  mov     [rsp+240h+var_200], rsi
0x180025fef  mov     rax, [rdi]
0x180025ff2  mov     rbx, [rax+30h]
0x180025ff6  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180025ffb  mov     r9d, 2Bh ; '+'; unsigned int
0x180026001  mov     [rbp+140h+var_1A8], rsi
0x180026005  lea     rdx, aWindowsInterna; "Windows.Internal.ShellExperience.LockSc"...
0x18002600c  lea     rcx, [rbp+140h+Buf1]; hstringHeader
0x180026010  lea     r8d, [r9+1]; unsigned int
0x180026014  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026019  mov     rdx, [rbp+140h+var_1A8]
0x18002601d  lea     r8, [rsp+240h+var_200]
0x180026022  mov     rcx, rdi
0x180026025  mov     rax, rbx
0x180026028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002602d  mov     edi, eax
0x18002602f  test    eax, eax
0x180026031  jns     short loc_18002605D
0x180026033  mov     edx, 73h ; 's'; void *
0x180026038  mov     r9d, eax; char *
0x18002603b  mov     rcx, [rbp+148h]; this
0x180026042  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x180026049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002604e  lea     rcx, [rsp+240h+var_200]
0x180026053  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180026058  jmp     loc_180026447
0x18002605d  mov     rbx, [rsp+240h+var_200]
0x180026062  lea     rdi, [r14+1B0h]
0x180026069  mov     rcx, rdi
0x18002606c  mov     rax, [rbx]
0x18002606f  mov     rsi, [rax]
0x180026072  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180026077  mov     r8, rdi
0x18002607a  lea     rdx, _GUID_a40cce11_67ee_4e74_8c46_91edb265261c
0x180026081  mov     rcx, rbx
0x180026084  mov     rax, rsi
0x180026087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002608c  xor     esi, esi
0x18002608e  mov     edi, eax
0x180026090  test    eax, eax
0x180026092  jns     short loc_180026099
0x180026094  lea     edx, [rsi+74h]
0x180026097  jmp     short loc_180026038
0x180026099  mov     edi, 1
0x18002609e  cmp     [r14+235h], sil
0x1800260a5  jz      short loc_1800260C7
0x1800260a7  cmp     cs:?s_numberOfConsecutiveUnlocksIfLockAppDidntShow@CLockAction@@0FA, di; short CLockAction::s_numberOfConsecutiveUnlocksIfLockAppDidntShow
0x1800260ae  jl      short loc_1800260C7
0x1800260b0  call    ?AbortingDueToConsecutiveLockAppShownFailures@LogonControllerTelemetry@@SAXXZ; LogonControllerTelemetry::AbortingDueToConsecutiveLockAppShownFailures(void)
0x1800260b5  mov     edi, 80004004h
0x1800260ba  mov     edx, 7Eh ; '~'
0x1800260bf  mov     r9d, edi
0x1800260c2  jmp     loc_18002603B
0x1800260c7  cmp     cs:dword_1800D354C, 0FFFFFFFFh
0x1800260ce  jnz     short loc_18002610E
0x1800260d0  lea     rax, [rsp+240h+SRWLock]
0x1800260d5  mov     cs:dword_1800D354C, esi
0x1800260db  lea     r8, aDebugbackstopv; "DebugBackstopVisual"
0x1800260e2  mov     [rsp+240h+ppv], rax; int *
0x1800260e7  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800260ee  mov     dword ptr [rsp+240h+SRWLock], esi
0x1800260f2  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800260f9  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1800260fe  test    eax, eax
0x180026100  js      short loc_18002610E
0x180026102  cmp     dword ptr [rsp+240h+SRWLock], esi
0x180026106  jz      short loc_18002610E
0x180026108  mov     cs:dword_1800D354C, edi
0x18002610e  lea     rdx, [r14+140h]
0x180026115  lea     rcx, [rsp+240h+SRWLock]
0x18002611a  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18002611f  mov     al, [r15]
0x180026122  mov     rbx, [rbp+140h+arg_38]
0x180026129  mov     [r14+100h], al
0x180026130  mov     al, [r15+1]
0x180026134  mov     [r14+101h], al
0x18002613b  mov     al, [r15+2]
0x18002613f  mov     [r14+102h], al
0x180026146  mov     al, [r15+3]
0x18002614a  mov     [r14+103h], al
0x180026151  mov     al, [r15+4]
0x180026155  mov     [r14+104h], al
0x18002615c  cmp     [r14+240h], rbx
0x180026163  jz      short loc_180026191
0x180026165  lea     rcx, [rbp+140h+Buf1]
0x180026169  mov     qword ptr [rbp+140h+Buf1], rbx
0x18002616d  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::InternalAddRef(void)
0x180026172  mov     rcx, [r14+240h]
0x180026179  mov     [r14+240h], rbx
0x180026180  test    rcx, rcx
0x180026183  jz      short loc_180026191
0x180026185  mov     rax, [rcx]
0x180026188  mov     rax, [rax+10h]
0x18002618c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026191  mov     rbx, [rbp+140h+arg_40]
0x180026198  cmp     [r14+248h], rbx
0x18002619f  jz      short loc_1800261CD
0x1800261a1  lea     rcx, [rbp+140h+Buf1]
0x1800261a5  mov     qword ptr [rbp+140h+Buf1], rbx
0x1800261a9  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::InternalAddRef(void)
0x1800261ae  mov     rcx, [r14+248h]
0x1800261b5  mov     [r14+248h], rbx
0x1800261bc  test    rcx, rcx
0x1800261bf  jz      short loc_1800261CD
0x1800261c1  mov     rax, [rcx]
0x1800261c4  mov     rax, [rax+10h]
0x1800261c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261cd  call    cs:__imp_GetCurrentProcess
0x1800261d3  mov     rbx, rax
0x1800261d6  call    cs:__imp_GetCurrentProcess
0x1800261dc  mov     [rsp+240h+dwOptions], 2; dwOptions
0x1800261e4  lea     r9, [r14+1C0h]; lpTargetHandle
0x1800261eb  mov     rcx, rax; hSourceProcessHandle
0x1800261ee  mov     [rsp+240h+bInheritHandle], esi; bInheritHandle
0x1800261f2  mov     r8, rbx; hTargetProcessHandle
0x1800261f5  mov     dword ptr [rsp+240h+ppv], esi; int
0x1800261f9  mov     rdx, r12; hSourceHandle
0x1800261fc  call    cs:__imp_DuplicateHandle
0x180026202  test    eax, eax
0x180026204  jnz     short loc_180026239
0x180026206  mov     rcx, [rbp+148h]; this
0x18002620d  lea     r8, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x180026214  mov     edx, 0A1h; void *
0x180026219  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002621e  mov     edi, eax
0x180026220  mov     rcx, [rsp+240h+SRWLock]; SRWLock
0x180026225  test    rcx, rcx
0x180026228  jz      loc_18002604E
0x18002622e  call    cs:__imp_ReleaseSRWLockExclusive
0x180026234  jmp     loc_18002604E
0x180026239  mov     rcx, r14; this
0x18002623c  call    ?_SubscribeToPowerSettingNotifications@CLockAction@@AEAAJXZ; CLockAction::_SubscribeToPowerSettingNotifications(void)
0x180026241  lea     rbx, aPcshellShellAu_15; "pcshell\\shell\\auth\\authux\\controlle"...
0x180026248  test    eax, eax
0x18002624a  jns     short loc_180026263
0x18002624c  mov     rcx, [rbp+148h]; this
0x180026253  mov     r9d, eax; char *
0x180026256  mov     r8, rbx; unsigned int
0x180026259  mov     edx, 0A5h; void *
0x18002625e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026263  xor     edx, edx; InputBuffer
0x180026265  mov     [r14+13Ch], dil
0x18002626c  lea     r9, [rsp+240h+OutputBuffer]; OutputBuffer
0x180026271  mov     [rsp+240h+OutputBuffer], esi
0x180026275  xor     r8d, r8d; InputBufferLength
0x180026278  mov     dword ptr [rsp+240h+ppv], 4; int
0x180026280  lea     ecx, [rdx+1Dh]; PowerInformationLevel
0x180026283  call    cs:__imp_NtPowerInformation
0x180026289  test    eax, eax
0x18002628b  jns     short loc_1800262A6
0x18002628d  mov     rcx, [rbp+148h]; this
0x180026294  mov     r9d, eax; char *
0x180026297  mov     r8, rbx; unsigned int
0x18002629a  mov     edx, 0AAh; void *
0x18002629f  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800262a4  jmp     short loc_1800262B4
0x1800262a6  cmp     [rsp+240h+OutputBuffer], esi
0x1800262aa  setnz   al
0x1800262ad  mov     [r14+13Ch], al
0x1800262b4  lea     rcx, [r14+0D0h]; newString
0x1800262bb  lea     rdx, [rsp+240h+var_1D0]; HSTRING *
0x1800262c0  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800262c5  mov     edi, eax
0x1800262c7  test    eax, eax
0x1800262c9  jns     short loc_1800262E7
0x1800262cb  mov     edx, 0AFh; void *
0x1800262d0  mov     rcx, [rbp+148h]; this
0x1800262d7  mov     r9d, eax; char *
0x1800262da  mov     r8, rbx; unsigned int
0x1800262dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800262e2  jmp     loc_180026220
0x1800262e7  lea     rcx, [r14+0D8h]; newString
0x1800262ee  lea     rdx, [rsp+240h+var_1C8]; HSTRING *
0x1800262f3  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800262f8  mov     edi, eax
0x1800262fa  test    eax, eax
0x1800262fc  jns     short loc_180026305
0x1800262fe  mov     edx, 0B0h
0x180026303  jmp     short loc_1800262D0
0x180026305  lea     rcx, [r14+0E0h]; newString
0x18002630c  lea     rdx, [rsp+240h+var_1F0]; HSTRING *
0x180026311  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180026316  mov     edi, eax
0x180026318  test    eax, eax
0x18002631a  jns     short loc_180026323
0x18002631c  mov     edx, 0B1h
0x180026321  jmp     short loc_1800262D0
0x180026323  mov     rax, [r15+8]
0x180026327  lea     rcx, [r14+0E8h]; newString
0x18002632e  lea     rdx, [rsp+240h+var_1F0]; HSTRING *
0x180026333  mov     [rsp+240h+var_1F0], rax
0x180026338  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18002633d  mov     edi, eax
0x18002633f  test    eax, eax
0x180026341  jns     short loc_18002634A
0x180026343  mov     edx, 0B2h
0x180026348  jmp     short loc_1800262D0
0x18002634a  mov     rax, [r15+10h]
0x18002634e  lea     rcx, [r14+0F0h]; newString
0x180026355  lea     rdx, [rsp+240h+var_1F0]; HSTRING *
0x18002635a  mov     [rsp+240h+var_1F0], rax
  ... truncated ...
```
