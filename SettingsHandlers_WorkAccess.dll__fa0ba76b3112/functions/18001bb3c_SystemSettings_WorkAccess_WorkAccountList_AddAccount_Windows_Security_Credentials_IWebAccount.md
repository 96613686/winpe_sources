# SystemSettings::WorkAccess::WorkAccountList::AddAccount(Windows::Security::Credentials::IWebAccount *)

- ea: `0x18001bb3c`
- end: `0x18001bea5`
- name: `?AddAccount@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUIWebAccount@Credentials@Security@Windows@@@Z`
- size: `873`
- prototype: `int(SystemSettings::WorkAccess::WorkAccountList *__hidden this, struct Windows::Security::Credentials::IWebAccount *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d930`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x18000c3f8`
- `0x180012130`
- `0x1800149e0`
- `0x180018420`
- `0x18001937c`
- `0x18001bb3c`
- `0x18001bf44`
- `0x18001d088`
- `0x18001d104`
- `0x18001d5c0`
- `0x1800431f8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bbeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bcc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bd08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bd46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bbeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bcc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bd08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bd46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be8b`

## string_xrefs

- `0x18001bb7e`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001bc14`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001bc5b`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001bd30`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001bd66`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001be22`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::AddAccount(
        SystemSettings::WorkAccess::WorkAccountList *this,
        struct Windows::Security::Credentials::IWebAccount *a2)
{
  int IsAccountPerUser; // edi
  __int64 v5; // rdx
  HSTRING *v7; // r8
  int UniqueIdOfWebAccount; // eax
  unsigned int v9; // ebx
  int Size; // eax
  bool v11; // bl
  unsigned int i; // r14d
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  HSTRING v18; // r8
  __int64 *v19; // rcx
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-30h] BYREF
  __int64 v24; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h] BYREF
  HSTRING v28; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct Windows::Security::Credentials::IWebAccount *v30; // [rsp+88h] [rbp+38h] BYREF
  int v31; // [rsp+90h] [rbp+40h] BYREF
  __int64 v32; // [rsp+98h] [rbp+48h] BYREF

  v30 = a2;
  LOBYTE(v23) = 0;
  LOBYTE(v31) = 0;
  LOBYTE(v32) = 0;
  IsAccountPerUser = SystemSettings::WorkAccess::WorkAccountList::IsAccountPerUser(this, a2, (bool *)&v23);
  if ( IsAccountPerUser < 0 )
  {
    v5 = 357;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)IsAccountPerUser,
      v23);
    return (unsigned int)IsAccountPerUser;
  }
  IsAccountPerUser = SystemSettings::WorkAccess::WorkAccountList::IsWorkAccount(this, a2, (bool *)&v31);
  if ( IsAccountPerUser < 0 )
  {
    v5 = 358;
    goto LABEL_3;
  }
  IsAccountPerUser = SystemSettings::WorkAccess::WorkAccountList::IsAADJAccount(this, a2, (bool *)&v32);
  if ( IsAccountPerUser < 0 )
  {
    v5 = 359;
    goto LABEL_3;
  }
  if ( !(_BYTE)v23 || !(_BYTE)v31 && !(_BYTE)v32 )
    return 0;
  v28 = 0;
  WindowsDeleteString(0);
  v28 = 0;
  UniqueIdOfWebAccount = SystemSettings::WorkAccess::GetUniqueIdOfWebAccount(
                           a2,
                           (struct Windows::Security::Credentials::IWebAccount *)&v28,
                           v7);
  v9 = UniqueIdOfWebAccount;
  if ( UniqueIdOfWebAccount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16C,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)UniqueIdOfWebAccount,
      v23);
LABEL_38:
    WindowsDeleteString(v28);
    return v9;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 288);
  LODWORD(v24) = 0;
  Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
           *((_QWORD *)this + 26),
           &v24);
  v9 = Size;
  if ( Size < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x172,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)Size,
      v23);
LABEL_36:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    goto LABEL_38;
  }
  v11 = 0;
  for ( i = 0; ; ++i )
  {
    if ( v11 )
      goto LABEL_40;
    if ( i >= (unsigned int)v24 )
      break;
    v27 = 0;
    v13 = *((_QWORD *)this + 26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v14 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
            v13,
            i,
            &v27);
    v9 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x178,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v14,
        v23);
LABEL_22:
      v19 = &v27;
LABEL_35:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v19);
      goto LABEL_36;
    }
    string = 0;
    v15 = v27;
    v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v17 = v16(v15, &string);
    v9 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v17,
        v23);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_22;
    }
    v11 = (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                          (Microsoft::WRL::Wrappers::Details *)string,
                          v28,
                          v18) == 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  }
  if ( !(_DWORD)v24 )
  {
    v24 = 0;
    if ( (_BYTE)v31 )
    {
      v32 = *((_QWORD *)this + 38);
      v31 = 0;
      v20 = Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,Windows::Security::Credentials::IWebAccount *,enum SystemSettings::WorkAccess::WorkAccountType,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *>(
              &v24,
              &v30,
              &v31,
              &v32);
      v9 = v20;
      if ( v20 < 0 )
      {
        v22 = 390;
LABEL_34:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
          (const char *)(unsigned int)v20,
          v23);
        v19 = &v24;
        goto LABEL_35;
      }
    }
    else
    {
      if ( !(_BYTE)v32 )
      {
LABEL_39:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        goto LABEL_40;
      }
      v32 = *((_QWORD *)this + 38);
      v31 = 1;
      v20 = Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,Windows::Security::Credentials::IWebAccount *,enum SystemSettings::WorkAccess::WorkAccountType,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *>(
              &v24,
              &v30,
              &v31,
              &v32);
      v9 = v20;
      if ( v20 < 0 )
      {
        v22 = 394;
        goto LABEL_34;
      }
    }
    if ( v24 )
    {
      LOBYTE(v21) = 1;
      v20 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
              *((_QWORD *)this + 26),
              0,
              v24,
              v21);
      v9 = v20;
      if ( v20 < 0 )
      {
        v22 = 403;
        goto LABEL_34;
      }
    }
    goto LABEL_39;
  }
LABEL_40:
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  WindowsDeleteString(v28);
  return 0;
}

```

## disassembly

```asm
0x18001bb3c  mov     [rsp-28h+arg_8], rdx
0x18001bb41  push    rbp
0x18001bb42  push    rbx
0x18001bb43  push    rsi
0x18001bb44  push    rdi
0x18001bb45  push    r14
0x18001bb47  mov     rbp, rsp
0x18001bb4a  sub     rsp, 50h
0x18001bb4e  mov     rbx, rdx
0x18001bb51  mov     rsi, rcx
0x18001bb54  xor     r14d, r14d
0x18001bb57  mov     byte ptr [rbp+var_30], r14b
0x18001bb5b  mov     byte ptr [rbp+arg_10], r14b
0x18001bb5f  mov     byte ptr [rbp+arg_18], r14b
0x18001bb63  lea     r8, [rbp+var_30]; bool *
0x18001bb67  call    ?IsAccountPerUser@WorkAccountList@WorkAccess@SystemSettings@@AEBAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z; SystemSettings::WorkAccess::WorkAccountList::IsAccountPerUser(Windows::Security::Credentials::IWebAccount *,bool *)
0x18001bb6c  mov     edi, eax
0x18001bb6e  test    eax, eax
0x18001bb70  jns     short loc_18001BB91
0x18001bb72  mov     edx, 165h; void *
0x18001bb77  mov     rcx, [rbp+28h]; this
0x18001bb7b  mov     r9d, edi; char *
0x18001bb7e  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001bb85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb8a  mov     eax, edi
0x18001bb8c  jmp     loc_18001BE99
0x18001bb91  lea     r8, [rbp+arg_10]; bool *
0x18001bb95  mov     rdx, rbx; struct Windows::Security::Credentials::IWebAccount *
0x18001bb98  mov     rcx, rsi; this
0x18001bb9b  call    ?IsWorkAccount@WorkAccountList@WorkAccess@SystemSettings@@AEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z; SystemSettings::WorkAccess::WorkAccountList::IsWorkAccount(Windows::Security::Credentials::IWebAccount *,bool *)
0x18001bba0  mov     edi, eax
0x18001bba2  test    eax, eax
0x18001bba4  jns     short loc_18001BBAD
0x18001bba6  mov     edx, 166h
0x18001bbab  jmp     short loc_18001BB77
0x18001bbad  lea     r8, [rbp+arg_18]; bool *
0x18001bbb1  mov     rdx, rbx; struct Windows::Security::Credentials::IWebAccount *
0x18001bbb4  mov     rcx, rsi; this
0x18001bbb7  call    ?IsAADJAccount@WorkAccountList@WorkAccess@SystemSettings@@AEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z; SystemSettings::WorkAccess::WorkAccountList::IsAADJAccount(Windows::Security::Credentials::IWebAccount *,bool *)
0x18001bbbc  mov     edi, eax
0x18001bbbe  test    eax, eax
0x18001bbc0  jns     short loc_18001BBC9
0x18001bbc2  mov     edx, 167h
0x18001bbc7  jmp     short loc_18001BB77
0x18001bbc9  xor     edi, edi
0x18001bbcb  cmp     byte ptr [rbp+var_30], dil
0x18001bbcf  jz      loc_18001BE97
0x18001bbd5  cmp     byte ptr [rbp+arg_10], dil
0x18001bbd9  jnz     short loc_18001BBE5
0x18001bbdb  cmp     byte ptr [rbp+arg_18], dil
0x18001bbdf  jz      loc_18001BE97
0x18001bbe5  mov     [rbp+var_8], rdi
0x18001bbe9  xor     ecx, ecx; string
0x18001bbeb  call    cs:__imp_WindowsDeleteString
0x18001bbf2  nop     dword ptr [rax+rax+00h]
0x18001bbf7  mov     [rbp+var_8], rdi
0x18001bbfb  lea     rdx, [rbp+var_8]; struct Windows::Security::Credentials::IWebAccount *
0x18001bbff  mov     rcx, rbx; this
0x18001bc02  call    ?GetUniqueIdOfWebAccount@WorkAccess@SystemSettings@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAPEAUHSTRING__@@@Z; SystemSettings::WorkAccess::GetUniqueIdOfWebAccount(Windows::Security::Credentials::IWebAccount *,HSTRING__ * *)
0x18001bc07  mov     ebx, eax
0x18001bc09  test    eax, eax
0x18001bc0b  jns     short loc_18001BC2A
0x18001bc0d  mov     rcx, [rbp+28h]; this
0x18001bc11  mov     r9d, eax; char *
0x18001bc14  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001bc1b  mov     edx, 16Ch; void *
0x18001bc20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc25  jmp     loc_18001BE53
0x18001bc2a  lea     rdx, [rsi+120h]
0x18001bc31  lea     rcx, [rbp+SRWLock]
0x18001bc35  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001bc3a  nop
0x18001bc3b  mov     dword ptr [rbp+var_28], edi
0x18001bc3e  lea     rdx, [rbp+var_28]
0x18001bc42  mov     rcx, [rsi+0D0h]
0x18001bc49  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x18001bc4e  mov     ebx, eax
0x18001bc50  test    eax, eax
0x18001bc52  jns     short loc_18001BC71
0x18001bc54  mov     rcx, [rbp+28h]; this
0x18001bc58  mov     r9d, eax; char *
0x18001bc5b  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001bc62  mov     edx, 172h; void *
0x18001bc67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc6c  jmp     loc_18001BE3D
0x18001bc71  mov     bl, dil
0x18001bc74  mov     r14d, edi
0x18001bc77  test    bl, bl
0x18001bc79  jnz     loc_18001BE71
0x18001bc7f  cmp     r14d, dword ptr [rbp+var_28]
0x18001bc83  jnb     loc_18001BD79
0x18001bc89  mov     [rbp+var_10], rdi
0x18001bc8d  mov     rbx, [rsi+0D0h]
0x18001bc94  lea     rcx, [rbp+var_10]
0x18001bc98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001bc9d  lea     r8, [rbp+var_10]
0x18001bca1  mov     edx, r14d
0x18001bca4  mov     rcx, rbx
0x18001bca7  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18001bcac  mov     ebx, eax
0x18001bcae  test    eax, eax
0x18001bcb0  js      loc_18001BD5F
0x18001bcb6  mov     [rbp+string], rdi
0x18001bcba  mov     rdi, [rbp+var_10]
0x18001bcbe  mov     rax, [rdi]
0x18001bcc1  mov     rbx, [rax+30h]
0x18001bcc5  xor     ecx, ecx; string
0x18001bcc7  call    cs:__imp_WindowsDeleteString
0x18001bcce  nop     dword ptr [rax+rax+00h]
0x18001bcd3  mov     [rbp+string], 0
0x18001bcdb  lea     rdx, [rbp+string]
0x18001bcdf  mov     rcx, rdi
0x18001bce2  mov     rax, rbx
0x18001bce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcea  mov     ebx, eax
0x18001bcec  xor     edi, edi
0x18001bcee  test    eax, eax
0x18001bcf0  js      short loc_18001BD29
0x18001bcf2  mov     rdx, [rbp+var_8]; HSTRING
0x18001bcf6  mov     rcx, [rbp+string]; this
0x18001bcfa  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18001bcff  test    eax, eax
0x18001bd01  setz    bl
0x18001bd04  mov     rcx, [rbp+string]; string
0x18001bd08  call    cs:__imp_WindowsDeleteString
0x18001bd0f  nop     dword ptr [rax+rax+00h]
0x18001bd14  mov     [rbp+string], rdi
0x18001bd18  lea     rcx, [rbp+var_10]
0x18001bd1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001bd21  inc     r14d
0x18001bd24  jmp     loc_18001BC77
0x18001bd29  mov     rcx, [rbp+28h]; this
0x18001bd2d  mov     r9d, eax; char *
0x18001bd30  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001bd37  mov     edx, 17Bh; void *
0x18001bd3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bd41  nop
0x18001bd42  mov     rcx, [rbp+string]; string
0x18001bd46  call    cs:__imp_WindowsDeleteString
0x18001bd4d  nop     dword ptr [rax+rax+00h]
0x18001bd52  mov     [rbp+string], rdi
0x18001bd56  lea     rcx, [rbp+var_10]
0x18001bd5a  jmp     loc_18001BE37
0x18001bd5f  mov     rcx, [rbp+28h]; this
0x18001bd63  mov     r9d, eax; char *
0x18001bd66  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001bd6d  mov     edx, 178h; void *
0x18001bd72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bd77  jmp     short loc_18001BD56
0x18001bd79  cmp     dword ptr [rbp+var_28], edi
0x18001bd7c  jnz     loc_18001BE71
0x18001bd82  mov     [rbp+var_28], rdi
0x18001bd86  cmp     byte ptr [rbp+arg_10], dil
0x18001bd8a  jz      short loc_18001BDBC
0x18001bd8c  mov     rax, [rsi+130h]
0x18001bd93  mov     [rbp+arg_18], rax
0x18001bd97  mov     [rbp+arg_10], edi
0x18001bd9a  lea     r9, [rbp+arg_18]
0x18001bd9e  lea     r8, [rbp+arg_10]
0x18001bda2  lea     rdx, [rbp+arg_8]
0x18001bda6  lea     rcx, [rbp+var_28]
0x18001bdaa  call    ??$MakeAndInitialize@VWorkAccountItem@WorkAccess@SystemSettings@@UISettingItem@DataModel@3@PEAUIWebAccount@Credentials@Security@Windows@@W4WorkAccountType@23@PEAUITokenBrokerInternalStatics@Web@Authentication@8Internal@9@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@012@$$QEAPEAUIWebAccount@Credentials@Security@Windows@@$$QEAW4WorkAccountType@WorkAccess@SystemSettings@@$$QEAPEAUITokenBrokerInternalStatics@Web@Authentication@6Internal@7@@Z; Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,Windows::Security::Credentials::IWebAccount *,SystemSettings::WorkAccess::WorkAccountType,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>,Windows::Security::Credentials::IWebAccount * &&,SystemSettings::WorkAccess::WorkAccountType &&,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &&)
0x18001bdaf  mov     ebx, eax
0x18001bdb1  test    eax, eax
0x18001bdb3  jns     short loc_18001BDFA
0x18001bdb5  mov     edx, 186h
0x18001bdba  jmp     short loc_18001BE1F
0x18001bdbc  cmp     byte ptr [rbp+arg_18], dil
0x18001bdc0  jz      loc_18001BE67
0x18001bdc6  mov     rax, [rsi+130h]
0x18001bdcd  mov     [rbp+arg_18], rax
0x18001bdd1  mov     [rbp+arg_10], 1
0x18001bdd8  lea     r9, [rbp+arg_18]
0x18001bddc  lea     r8, [rbp+arg_10]
0x18001bde0  lea     rdx, [rbp+arg_8]
0x18001bde4  lea     rcx, [rbp+var_28]
0x18001bde8  call    ??$MakeAndInitialize@VWorkAccountItem@WorkAccess@SystemSettings@@UISettingItem@DataModel@3@PEAUIWebAccount@Credentials@Security@Windows@@W4WorkAccountType@23@PEAUITokenBrokerInternalStatics@Web@Authentication@8Internal@9@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@012@$$QEAPEAUIWebAccount@Credentials@Security@Windows@@$$QEAW4WorkAccountType@WorkAccess@SystemSettings@@$$QEAPEAUITokenBrokerInternalStatics@Web@Authentication@6Internal@7@@Z; Microsoft::WRL::Details::MakeAndInitialize<SystemSettings::WorkAccess::WorkAccountItem,SystemSettings::DataModel::ISettingItem,Windows::Security::Credentials::IWebAccount *,SystemSettings::WorkAccess::WorkAccountType,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>,Windows::Security::Credentials::IWebAccount * &&,SystemSettings::WorkAccess::WorkAccountType &&,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * &&)
0x18001bded  mov     ebx, eax
0x18001bdef  test    eax, eax
0x18001bdf1  jns     short loc_18001BDFA
0x18001bdf3  mov     edx, 18Ah
0x18001bdf8  jmp     short loc_18001BE1F
0x18001bdfa  mov     r8, [rbp+var_28]
0x18001bdfe  test    r8, r8
0x18001be01  jz      short loc_18001BE67
0x18001be03  mov     r9b, 1
0x18001be06  xor     edx, edx
0x18001be08  mov     rcx, [rsi+0D0h]
0x18001be0f  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x18001be14  mov     ebx, eax
0x18001be16  test    eax, eax
0x18001be18  jns     short loc_18001BE67
0x18001be1a  mov     edx, 193h; void *
0x18001be1f  mov     r9d, eax; char *
0x18001be22  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001be29  mov     rcx, [rbp+28h]; this
0x18001be2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be32  nop
0x18001be33  lea     rcx, [rbp+var_28]
0x18001be37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001be3c  nop
0x18001be3d  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001be41  test    rcx, rcx
0x18001be44  jz      short loc_18001BE53
0x18001be46  call    cs:__imp_ReleaseSRWLockExclusive
0x18001be4d  nop     dword ptr [rax+rax+00h]
0x18001be52  nop
0x18001be53  mov     rcx, [rbp+var_8]; string
0x18001be57  call    cs:__imp_WindowsDeleteString
0x18001be5e  nop     dword ptr [rax+rax+00h]
0x18001be63  mov     eax, ebx
0x18001be65  jmp     short loc_18001BE99
0x18001be67  lea     rcx, [rbp+var_28]
0x18001be6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001be70  nop
0x18001be71  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001be75  test    rcx, rcx
0x18001be78  jz      short loc_18001BE87
0x18001be7a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001be81  nop     dword ptr [rax+rax+00h]
0x18001be86  nop
0x18001be87  mov     rcx, [rbp+var_8]; string
0x18001be8b  call    cs:__imp_WindowsDeleteString
0x18001be92  nop     dword ptr [rax+rax+00h]
0x18001be97  xor     eax, eax
0x18001be99  add     rsp, 50h
0x18001be9d  pop     r14
0x18001be9f  pop     rdi
0x18001bea0  pop     rsi
0x18001bea1  pop     rbx
0x18001bea2  pop     rbp
0x18001bea3  retn
```
