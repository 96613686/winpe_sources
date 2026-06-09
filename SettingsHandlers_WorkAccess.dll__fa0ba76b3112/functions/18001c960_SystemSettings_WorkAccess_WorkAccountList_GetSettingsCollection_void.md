# SystemSettings::WorkAccess::WorkAccountList::GetSettingsCollection(void)

- ea: `0x18001c960`
- end: `0x18001cb13`
- name: `?GetSettingsCollection@WorkAccountList@WorkAccess@SystemSettings@@MEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::WorkAccountList *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cdd0`
- `0x18001ce20`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x18000c3f8`
- `0x18000f074`
- `0x180014d48`
- `0x180015ea0`
- `0x180017140`
- `0x1800196c4`
- `0x180019820`
- `0x18001a154`
- `0x18001a7f4`
- `0x18001c00c`
- `0x18001c960`
- `0x18001cf48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c986`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c986`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ca5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ca73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ca5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ca73`

## string_xrefs

- `0x18001c9cd`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001ca3e`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001cac4`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::GetSettingsCollection(
        SystemSettings::WorkAccess::WorkAccountList *this)
{
  int v2; // edi
  int v3; // eax
  unsigned int v4; // edi
  _QWORD *v6; // rax
  int v7; // eax
  __int64 v8; // rax
  int v9[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+50h] [rbp+20h] BYREF
  PSRWLOCK SRWLock; // [rsp+58h] [rbp+28h] BYREF
  char v13; // [rsp+60h] [rbp+30h] BYREF

  if ( *((_QWORD *)this + 26) )
  {
    EnterCriticalSection(&CriticalSection);
    v11 = &CriticalSection;
    v2 = dword_18006C090;
    if ( dword_18006C090 < 0 )
      HIBYTE(word_18006C018) = 1;
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v11);
    if ( v2 < 0 )
    {
      SystemSettings::DataModel::CSettingBase::SetIsUpdating(this, 1u);
    }
    else
    {
      v3 = SystemSettings::WorkAccess::WorkAccountList::EnsureTokenBrokerInternalStatics(this);
      v4 = v3;
      if ( v3 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFA,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
          (const char *)(unsigned int)v3,
          v9[0]);
        return v4;
      }
      v11 = 0;
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 288);
      if ( !*((_BYTE *)this + 296) && !*((_BYTE *)this + 297) )
      {
        SystemSettings::DataModel::CSettingBase::SetIsUpdating(this, 1u);
        v6 = (_QWORD *)_lambda_9dece6d741847fb774fb9364fa73d27b_::_lambda_9dece6d741847fb774fb9364fa73d27b_(
                         v9,
                         this,
                         &v11);
        v7 = SystemSettings::WorkAccess::SwitchToBrokerCallingContext__lambda_6e156cf47127949868d32e176a6524b2___(v6);
        v4 = v7;
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x108,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
            (const char *)(unsigned int)v7,
            v9[0]);
          if ( SRWLock )
            ReleaseSRWLockExclusive(SRWLock);
          goto LABEL_18;
        }
      }
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      if ( v11 )
      {
        SRWLock = (PSRWLOCK)this;
        Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::WorkAccountList>::InternalAddRef(&SRWLock);
        v8 = lambda_ca7c40deb2c133cfe173aee77ba73d46_::_lambda_ca7c40deb2c133cfe173aee77ba73d46_(&v13, &SRWLock);
        v4 = StartOperationAndThen_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Foundation::Collections::IVectorView_Windows::Security::Credentials::WebAccount_______Windows::Foundation::IAsyncOperation_Windows::Foundation::Collections::IVectorView_Windows::Security::Credentials::WebAccount________lambda_ca7c40deb2c133cfe173aee77ba73d46___(
               v11,
               v8);
        lambda_ecba395f2b7723cca14456807c386eb0_::__lambda_ecba395f2b7723cca14456807c386eb0_(&v13);
        if ( (v4 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x129,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
            (const char *)v4,
            v9[0]);
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::Release(this);
LABEL_18:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
          return v4;
        }
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::Release(this);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c960  push    rbp
0x18001c962  push    rbx
0x18001c963  push    rdi
0x18001c964  mov     rbp, rsp
0x18001c967  sub     rsp, 30h
0x18001c96b  mov     rbx, rcx
0x18001c96e  cmp     qword ptr [rcx+0D0h], 0
0x18001c976  jz      loc_18001CB08
0x18001c97c  lea     rdi, CriticalSection
0x18001c983  mov     rcx, rdi; lpCriticalSection
0x18001c986  call    cs:__imp_EnterCriticalSection
0x18001c98d  nop     dword ptr [rax+rax+00h]
0x18001c992  mov     [rbp+arg_0], rdi
0x18001c996  mov     edi, cs:dword_18006C090
0x18001c99c  test    edi, edi
0x18001c99e  jns     short loc_18001C9A7
0x18001c9a0  mov     byte ptr cs:word_18006C018+1, 1
0x18001c9a7  lea     rcx, [rbp+arg_0]; this
0x18001c9ab  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001c9b0  mov     rcx, rbx; this
0x18001c9b3  test    edi, edi
0x18001c9b5  js      loc_18001CB01
0x18001c9bb  call    ?EnsureTokenBrokerInternalStatics@WorkAccountList@WorkAccess@SystemSettings@@AEAAJXZ; SystemSettings::WorkAccess::WorkAccountList::EnsureTokenBrokerInternalStatics(void)
0x18001c9c0  mov     edi, eax
0x18001c9c2  test    eax, eax
0x18001c9c4  jns     short loc_18001C9E5
0x18001c9c6  mov     rcx, [rbp+18h]; this
0x18001c9ca  mov     r9d, eax; char *
0x18001c9cd  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001c9d4  mov     edx, 0FAh; void *
0x18001c9d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c9de  mov     eax, edi
0x18001c9e0  jmp     loc_18001CB0A
0x18001c9e5  mov     [rbp+arg_0], 0
0x18001c9ed  lea     rdx, [rbx+120h]
0x18001c9f4  lea     rcx, [rbp+SRWLock]
0x18001c9f8  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001c9fd  cmp     byte ptr [rbx+128h], 0
0x18001ca04  jnz     short loc_18001CA6A
0x18001ca06  cmp     byte ptr [rbx+129h], 0
0x18001ca0d  jnz     short loc_18001CA6A
0x18001ca0f  mov     dl, 1; unsigned __int8
0x18001ca11  mov     rcx, rbx; this
0x18001ca14  call    ?SetIsUpdating@CSettingBase@DataModel@SystemSettings@@UEAA_NE@Z; SystemSettings::DataModel::CSettingBase::SetIsUpdating(uchar)
0x18001ca19  lea     r8, [rbp+arg_0]
0x18001ca1d  mov     rdx, rbx
0x18001ca20  lea     rcx, [rbp+var_10]
0x18001ca24  call    ??0_lambda_9dece6d741847fb774fb9364fa73d27b_@@QEAA@PEAVTokenBrokerSingleton@DataModel@SystemSettings@@AEAV?$ComPtr@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Z; _lambda_9dece6d741847fb774fb9364fa73d27b_::_lambda_9dece6d741847fb774fb9364fa73d27b_(SystemSettings::DataModel::TokenBrokerSingleton *,Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>> &)
0x18001ca29  mov     rcx, rax
0x18001ca2c  call    SystemSettings__WorkAccess__SwitchToBrokerCallingContext__lambda_6e156cf47127949868d32e176a6524b2___
0x18001ca31  mov     edi, eax
0x18001ca33  test    eax, eax
0x18001ca35  jns     short loc_18001CA6A
0x18001ca37  mov     rcx, [rbp+18h]; this
0x18001ca3b  mov     r9d, eax; char *
0x18001ca3e  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001ca45  mov     edx, 108h; void *
0x18001ca4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca4f  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001ca53  test    rcx, rcx
0x18001ca56  jz      loc_18001CADF
0x18001ca5c  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ca63  nop     dword ptr [rax+rax+00h]
0x18001ca68  jmp     short loc_18001CADF
0x18001ca6a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001ca6e  test    rcx, rcx
0x18001ca71  jz      short loc_18001CA7F
0x18001ca73  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ca7a  nop     dword ptr [rax+rax+00h]
0x18001ca7f  cmp     [rbp+arg_0], 0
0x18001ca84  jz      short loc_18001CAF6
0x18001ca86  mov     [rbp+SRWLock], rbx
0x18001ca8a  lea     rcx, [rbp+SRWLock]
0x18001ca8e  call    ?InternalAddRef@?$ComPtr@VWorkAccountList@WorkAccess@SystemSettings@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SystemSettings::WorkAccess::WorkAccountList>::InternalAddRef(void)
0x18001ca93  nop
0x18001ca94  lea     rdx, [rbp+SRWLock]
0x18001ca98  lea     rcx, [rbp+arg_10]
0x18001ca9c  call    _lambda_ca7c40deb2c133cfe173aee77ba73d46____lambda_ca7c40deb2c133cfe173aee77ba73d46_
0x18001caa1  nop
0x18001caa2  mov     rdx, rax
0x18001caa5  mov     rcx, [rbp+arg_0]
0x18001caa9  call    StartOperationAndThen_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Foundation__Collections__IVectorView_Windows__Security__Credentials__WebAccount_______Windows__Foundation__IAsyncOperation_Windows__Foundation__Collections__IVectorView_Windows__Security__Credentials__WebAccount________lambda_ca7c40deb2c133cfe173aee77ba73d46___
0x18001caae  mov     edi, eax
0x18001cab0  lea     rcx, [rbp+arg_10]
0x18001cab4  call    _lambda_ecba395f2b7723cca14456807c386eb0_____lambda_ecba395f2b7723cca14456807c386eb0_
0x18001cab9  test    edi, edi
0x18001cabb  jns     short loc_18001CAED
0x18001cabd  mov     rcx, [rbp+18h]; this
0x18001cac1  mov     r9d, edi; char *
0x18001cac4  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001cacb  mov     edx, 129h; void *
0x18001cad0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cad5  nop
0x18001cad6  mov     rcx, rbx
0x18001cad9  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::Release(void)
0x18001cade  nop
0x18001cadf  lea     rcx, [rbp+arg_0]
0x18001cae3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001cae8  jmp     loc_18001C9DE
0x18001caed  mov     rcx, rbx
0x18001caf0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::Release(void)
0x18001caf5  nop
0x18001caf6  lea     rcx, [rbp+arg_0]
0x18001cafa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001caff  jmp     short loc_18001CB08
0x18001cb01  mov     dl, 1; unsigned __int8
0x18001cb03  call    ?SetIsUpdating@CSettingBase@DataModel@SystemSettings@@UEAA_NE@Z; SystemSettings::DataModel::CSettingBase::SetIsUpdating(uchar)
0x18001cb08  xor     eax, eax
0x18001cb0a  add     rsp, 30h
0x18001cb0e  pop     rdi
0x18001cb0f  pop     rbx
0x18001cb10  pop     rbp
0x18001cb11  retn
```
