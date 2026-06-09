# SystemSettings::WorkAccess::CCorpDeviceManagementEnrollmentCollection::AddEnrollmentToSettingsList(ushort const *,EnrollmentEnrollType)

- ea: `0x18003b6cc`
- end: `0x18003b823`
- name: `?AddEnrollmentToSettingsList@CCorpDeviceManagementEnrollmentCollection@WorkAccess@SystemSettings@@AEAAJPEBGW4EnrollmentEnrollType@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c430`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x18000c3f8`
- `0x1800149e0`
- `0x18003b6cc`
- `0x18003ba14`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b7c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b7f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b7c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b7f7`

## string_xrefs

- `0x18003b70d`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003b761`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003b7a9`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::WorkAccess::CCorpDeviceManagementEnrollmentCollection::AddEnrollmentToSettingsList(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-18h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  __int64 v20; // [rsp+78h] [rbp+40h] BYREF

  v17 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v6 = SystemSettings::WorkAccess::CEnrollmentProfileSetting::CreateInstance(a2, a3, &v17);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)v6,
      (int)v17);
    goto LABEL_15;
  }
  v20 = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
  v9 = **v17;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  v10 = v9(v8, &GUID_40c037cc_d8bf_489e_8697_d66baa3221bf, &v20);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)v10,
      (int)v17);
LABEL_5:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    goto LABEL_15;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, a1 + 296);
  v12 = *(_QWORD *)(a1 + 240);
  if ( !v12 )
  {
    v7 = -2147418113;
    v13 = 2147549183LL;
    v14 = 242;
    goto LABEL_8;
  }
  LOBYTE(v11) = 1;
  v15 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
          v12,
          0,
          v20,
          v11);
  v7 = v15;
  if ( v15 < 0 )
  {
    v13 = (unsigned int)v15;
    v14 = 243;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)v13,
      (int)v17);
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    goto LABEL_5;
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  v7 = 0;
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  return v7;
}

```

## disassembly

```asm
0x18003b6cc  push    rbp
0x18003b6ce  push    rbx
0x18003b6cf  push    rsi
0x18003b6d0  push    rdi
0x18003b6d1  mov     rbp, rsp
0x18003b6d4  sub     rsp, 38h
0x18003b6d8  mov     ebx, r8d
0x18003b6db  mov     rdi, rdx
0x18003b6de  mov     rsi, rcx
0x18003b6e1  mov     [rbp+var_18], 0
0x18003b6e9  lea     rcx, [rbp+var_18]
0x18003b6ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b6f2  lea     r8, [rbp+var_18]
0x18003b6f6  mov     edx, ebx
0x18003b6f8  mov     rcx, rdi
0x18003b6fb  call    ?CreateInstance@CEnrollmentProfileSetting@WorkAccess@SystemSettings@@SAJPEBGW4EnrollmentEnrollType@@PEAPEAV123@@Z; SystemSettings::WorkAccess::CEnrollmentProfileSetting::CreateInstance(ushort const *,EnrollmentEnrollType,SystemSettings::WorkAccess::CEnrollmentProfileSetting * *)
0x18003b700  mov     ebx, eax
0x18003b702  test    eax, eax
0x18003b704  jns     short loc_18003B723
0x18003b706  mov     rcx, [rbp+20h]; this
0x18003b70a  mov     r9d, eax; char *
0x18003b70d  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003b714  mov     edx, 0ECh; void *
0x18003b719  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b71e  jmp     loc_18003B80E
0x18003b723  mov     [rbp+arg_18], 0
0x18003b72b  mov     rbx, [rbp+var_18]
0x18003b72f  mov     rax, [rbx]
0x18003b732  mov     rdi, [rax]
0x18003b735  lea     rcx, [rbp+arg_18]
0x18003b739  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b73e  lea     r8, [rbp+arg_18]
0x18003b742  lea     rdx, _GUID_40c037cc_d8bf_489e_8697_d66baa3221bf
0x18003b749  mov     rcx, rbx
0x18003b74c  mov     rax, rdi
0x18003b74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b754  mov     ebx, eax
0x18003b756  test    eax, eax
0x18003b758  jns     short loc_18003B780
0x18003b75a  mov     rcx, [rbp+20h]; this
0x18003b75e  mov     r9d, eax; char *
0x18003b761  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003b768  mov     edx, 0EEh; void *
0x18003b76d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b772  lea     rcx, [rbp+arg_18]
0x18003b776  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b77b  jmp     loc_18003B80E
0x18003b780  lea     rdx, [rsi+128h]
0x18003b787  lea     rcx, [rbp+SRWLock]
0x18003b78b  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003b790  mov     rcx, [rsi+0F0h]
0x18003b797  test    rcx, rcx
0x18003b79a  jnz     short loc_18003B7D0
0x18003b79c  mov     ebx, 8000FFFFh
0x18003b7a1  mov     r9d, ebx; char *
0x18003b7a4  mov     edx, 0F2h; void *
0x18003b7a9  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003b7b0  mov     rcx, [rbp+20h]; this
0x18003b7b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b7b9  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003b7bd  test    rcx, rcx
0x18003b7c0  jz      short loc_18003B772
0x18003b7c2  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b7c9  nop     dword ptr [rax+rax+00h]
0x18003b7ce  jmp     short loc_18003B772
0x18003b7d0  mov     r9b, 1
0x18003b7d3  mov     r8, [rbp+arg_18]
0x18003b7d7  xor     edx, edx
0x18003b7d9  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x18003b7de  mov     ebx, eax
0x18003b7e0  test    eax, eax
0x18003b7e2  jns     short loc_18003B7EE
0x18003b7e4  mov     r9d, eax
0x18003b7e7  mov     edx, 0F3h
0x18003b7ec  jmp     short loc_18003B7A9
0x18003b7ee  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003b7f2  test    rcx, rcx
0x18003b7f5  jz      short loc_18003B803
0x18003b7f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b7fe  nop     dword ptr [rax+rax+00h]
0x18003b803  lea     rcx, [rbp+arg_18]
0x18003b807  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b80c  xor     ebx, ebx
0x18003b80e  lea     rcx, [rbp+var_18]
0x18003b812  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b817  mov     eax, ebx
0x18003b819  add     rsp, 38h
0x18003b81d  pop     rdi
0x18003b81e  pop     rsi
0x18003b81f  pop     rbx
0x18003b820  pop     rbp
0x18003b821  retn
```
