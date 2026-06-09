# SystemSettings::WorkAccess::WorkAccountList::UpdateAccount(Windows::Security::Credentials::IWebAccount *)

- ea: `0x18001fc24`
- end: `0x18001feca`
- name: `?UpdateAccount@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUIWebAccount@Credentials@Security@Windows@@@Z`
- size: `678`
- prototype: `int(SystemSettings::WorkAccess::WorkAccountList *__hidden this, struct Windows::Security::Credentials::IWebAccount *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d9d0`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x18000c3f8`
- `0x180012130`
- `0x180015464`
- `0x180018420`
- `0x18001bf44`
- `0x18001d104`
- `0x18001fc24`
- `0x1800406e4`
- `0x1800431f8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fe16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fea6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fe16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fea6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fd44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fd86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fdef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001feb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fd44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fd86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fdef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001feb7`

## string_xrefs

- `0x18001fc93`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001fcde`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001fe4e`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001fe81`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::UpdateAccount(
        SystemSettings::WorkAccess::WorkAccountList *this,
        struct Windows::Security::Credentials::IWebAccount *a2)
{
  HSTRING *v4; // r8
  int UniqueIdOfWebAccount; // eax
  unsigned int v6; // ebx
  int Size; // eax
  unsigned int i; // esi
  __int64 v9; // rbx
  int v10; // eax
  SystemSettings::DataModel::CSettingBase *v11; // rdi
  __int64 (__fastcall *v12)(SystemSettings::DataModel::CSettingBase *, HSTRING *); // rbx
  int v13; // eax
  HSTRING v14; // r8
  SystemSettings::DataModel::CSettingBase *v15; // rbx
  SystemSettings::DataModel::CSettingBase *v17; // [rsp+20h] [rbp-20h] BYREF
  HSTRING v18; // [rsp+28h] [rbp-18h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v21; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  LOBYTE(v21) = 0;
  if ( (int)SystemSettings::WorkAccess::WorkAccountList::IsAccountPerUser(this, a2, (bool *)&v21) < 0 || !(_BYTE)v21 )
    return 0;
  WindowsDeleteString(0);
  v18 = 0;
  UniqueIdOfWebAccount = SystemSettings::WorkAccess::GetUniqueIdOfWebAccount(
                           a2,
                           (struct Windows::Security::Credentials::IWebAccount *)&v18,
                           v4);
  v6 = UniqueIdOfWebAccount;
  if ( UniqueIdOfWebAccount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)UniqueIdOfWebAccount,
      (int)v17);
LABEL_23:
    WindowsDeleteString(v18);
    return v6;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, (char *)this + 288);
  v21 = 0;
  Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
           *((_QWORD *)this + 26),
           &v21);
  v6 = Size;
  if ( Size < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)Size,
      (int)v17);
LABEL_21:
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    goto LABEL_23;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v21 )
      goto LABEL_14;
    v17 = 0;
    v9 = *((_QWORD *)this + 26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    v10 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
            v9,
            i,
            &v17);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AE,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v10,
        (int)v17);
      goto LABEL_20;
    }
    string = 0;
    v11 = v17;
    v12 = *(__int64 (__fastcall **)(SystemSettings::DataModel::CSettingBase *, HSTRING *))(*(_QWORD *)v17 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v13 = v12(v11, &string);
    v6 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B1,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v13,
        (int)v17);
      WindowsDeleteString(string);
      string = 0;
LABEL_20:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      goto LABEL_21;
    }
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                          (Microsoft::WRL::Wrappers::Details *)string,
                          v18,
                          v14) )
      break;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  }
  v15 = v17;
  Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::operator=((char *)v17 + 216, a2);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(v15, L"Description");
  SystemSettings::DataModel::CSettingBase::OnValueChanged(v15, (const unsigned __int16 *)&stru_18005B328);
  SystemSettings::DataModel::CSettingBase::OnValueChanged(v15, (const unsigned __int16 *)&stru_18005B370);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
LABEL_14:
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  WindowsDeleteString(v18);
  return 0;
}

```

## disassembly

```asm
0x18001fc24  mov     [rsp-28h+arg_0], rbx
0x18001fc29  push    rbp
0x18001fc2a  push    rsi
0x18001fc2b  push    rdi
0x18001fc2c  push    r14
0x18001fc2e  push    r15
0x18001fc30  mov     rbp, rsp
0x18001fc33  sub     rsp, 40h
0x18001fc37  mov     r14, rdx
0x18001fc3a  mov     r15, rcx
0x18001fc3d  mov     byte ptr [rbp+arg_10], 0
0x18001fc41  lea     r8, [rbp+arg_10]; bool *
0x18001fc45  call    ?IsAccountPerUser@WorkAccountList@WorkAccess@SystemSettings@@AEBAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z; SystemSettings::WorkAccess::WorkAccountList::IsAccountPerUser(Windows::Security::Credentials::IWebAccount *,bool *)
0x18001fc4a  test    eax, eax
0x18001fc4c  js      loc_18001FE33
0x18001fc52  cmp     byte ptr [rbp+arg_10], 0
0x18001fc56  jz      loc_18001FE33
0x18001fc5c  mov     [rbp+var_18], 0
0x18001fc64  xor     ecx, ecx; string
0x18001fc66  call    cs:__imp_WindowsDeleteString
0x18001fc6d  nop     dword ptr [rax+rax+00h]
0x18001fc72  mov     [rbp+var_18], 0
0x18001fc7a  lea     rdx, [rbp+var_18]; struct Windows::Security::Credentials::IWebAccount *
0x18001fc7e  mov     rcx, r14; this
0x18001fc81  call    ?GetUniqueIdOfWebAccount@WorkAccess@SystemSettings@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAPEAUHSTRING__@@@Z; SystemSettings::WorkAccess::GetUniqueIdOfWebAccount(Windows::Security::Credentials::IWebAccount *,HSTRING__ * *)
0x18001fc86  mov     ebx, eax
0x18001fc88  test    eax, eax
0x18001fc8a  jns     short loc_18001FCA9
0x18001fc8c  mov     rcx, [rbp+28h]; this
0x18001fc90  mov     r9d, eax; char *
0x18001fc93  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001fc9a  mov     edx, 1A3h; void *
0x18001fc9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fca4  jmp     loc_18001FEB3
0x18001fca9  lea     rdx, [r15+120h]
0x18001fcb0  lea     rcx, [rbp+SRWLock]
0x18001fcb4  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001fcb9  nop
0x18001fcba  mov     [rbp+arg_10], 0
0x18001fcc1  lea     rdx, [rbp+arg_10]
0x18001fcc5  mov     rcx, [r15+0D0h]
0x18001fccc  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x18001fcd1  mov     ebx, eax
0x18001fcd3  test    eax, eax
0x18001fcd5  jns     short loc_18001FCF4
0x18001fcd7  mov     rcx, [rbp+28h]; this
0x18001fcdb  mov     r9d, eax; char *
0x18001fcde  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001fce5  mov     edx, 1A9h; void *
0x18001fcea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fcef  jmp     loc_18001FE9D
0x18001fcf4  xor     esi, esi
0x18001fcf6  cmp     esi, [rbp+arg_10]
0x18001fcf9  jnb     loc_18001FE0D
0x18001fcff  mov     [rbp+var_20], 0
0x18001fd07  mov     rbx, [r15+0D0h]
0x18001fd0e  lea     rcx, [rbp+var_20]
0x18001fd12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fd17  lea     r8, [rbp+var_20]
0x18001fd1b  mov     edx, esi
0x18001fd1d  mov     rcx, rbx
0x18001fd20  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18001fd25  mov     ebx, eax
0x18001fd27  test    eax, eax
0x18001fd29  js      loc_18001FE7A
0x18001fd2f  mov     [rbp+string], 0
0x18001fd37  mov     rdi, [rbp+var_20]
0x18001fd3b  mov     rax, [rdi]
0x18001fd3e  mov     rbx, [rax+30h]
0x18001fd42  xor     ecx, ecx; string
0x18001fd44  call    cs:__imp_WindowsDeleteString
0x18001fd4b  nop     dword ptr [rax+rax+00h]
0x18001fd50  mov     [rbp+string], 0
0x18001fd58  lea     rdx, [rbp+string]
0x18001fd5c  mov     rcx, rdi
0x18001fd5f  mov     rax, rbx
0x18001fd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd67  mov     ebx, eax
0x18001fd69  test    eax, eax
0x18001fd6b  js      loc_18001FE47
0x18001fd71  mov     rdx, [rbp+var_18]; HSTRING
0x18001fd75  mov     rcx, [rbp+string]; this
0x18001fd79  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18001fd7e  test    eax, eax
0x18001fd80  jz      short loc_18001FDAA
0x18001fd82  mov     rcx, [rbp+string]; string
0x18001fd86  call    cs:__imp_WindowsDeleteString
0x18001fd8d  nop     dword ptr [rax+rax+00h]
0x18001fd92  mov     [rbp+string], 0
0x18001fd9a  lea     rcx, [rbp+var_20]
0x18001fd9e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fda3  inc     esi
0x18001fda5  jmp     loc_18001FCF6
0x18001fdaa  mov     rbx, [rbp+var_20]
0x18001fdae  lea     rcx, [rbx+0D8h]
0x18001fdb5  mov     rdx, r14
0x18001fdb8  call    ??4?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIWebAccount@Credentials@Security@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::operator=(Windows::Security::Credentials::IWebAccount *)
0x18001fdbd  lea     rdx, aDescription; "Description"
0x18001fdc4  mov     rcx, rbx; this
0x18001fdc7  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18001fdcc  lea     rdx, stru_18005B328; unsigned __int16 *
0x18001fdd3  mov     rcx, rbx; this
0x18001fdd6  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18001fddb  lea     rdx, stru_18005B370; unsigned __int16 *
0x18001fde2  mov     rcx, rbx; this
0x18001fde5  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18001fdea  nop
0x18001fdeb  mov     rcx, [rbp+string]; string
0x18001fdef  call    cs:__imp_WindowsDeleteString
0x18001fdf6  nop     dword ptr [rax+rax+00h]
0x18001fdfb  mov     [rbp+string], 0
0x18001fe03  lea     rcx, [rbp+var_20]
0x18001fe07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fe0c  nop
0x18001fe0d  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001fe11  test    rcx, rcx
0x18001fe14  jz      short loc_18001FE23
0x18001fe16  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fe1d  nop     dword ptr [rax+rax+00h]
0x18001fe22  nop
0x18001fe23  mov     rcx, [rbp+var_18]; string
0x18001fe27  call    cs:__imp_WindowsDeleteString
0x18001fe2e  nop     dword ptr [rax+rax+00h]
0x18001fe33  xor     eax, eax
0x18001fe35  mov     rbx, [rsp+40h+arg_0]
0x18001fe3a  add     rsp, 40h
0x18001fe3e  pop     r15
0x18001fe40  pop     r14
0x18001fe42  pop     rdi
0x18001fe43  pop     rsi
0x18001fe44  pop     rbp
0x18001fe45  retn
0x18001fe47  mov     rcx, [rbp+28h]; this
0x18001fe4b  mov     r9d, eax; char *
0x18001fe4e  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001fe55  mov     edx, 1B1h; void *
0x18001fe5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe5f  nop
0x18001fe60  mov     rcx, [rbp+string]; string
0x18001fe64  call    cs:__imp_WindowsDeleteString
0x18001fe6b  nop     dword ptr [rax+rax+00h]
0x18001fe70  mov     [rbp+string], 0
0x18001fe78  jmp     short loc_18001FE93
0x18001fe7a  mov     rcx, [rbp+28h]; this
0x18001fe7e  mov     r9d, eax; char *
0x18001fe81  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001fe88  mov     edx, 1AEh; void *
0x18001fe8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe92  nop
0x18001fe93  lea     rcx, [rbp+var_20]
0x18001fe97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001fe9c  nop
0x18001fe9d  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001fea1  test    rcx, rcx
0x18001fea4  jz      short loc_18001FEB3
0x18001fea6  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fead  nop     dword ptr [rax+rax+00h]
0x18001feb2  nop
0x18001feb3  mov     rcx, [rbp+var_18]; string
0x18001feb7  call    cs:__imp_WindowsDeleteString
0x18001febe  nop     dword ptr [rax+rax+00h]
0x18001fec3  mov     eax, ebx
0x18001fec5  jmp     loc_18001FE35
```
