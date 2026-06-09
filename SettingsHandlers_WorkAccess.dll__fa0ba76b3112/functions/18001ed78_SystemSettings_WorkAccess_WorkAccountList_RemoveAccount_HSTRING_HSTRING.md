# SystemSettings::WorkAccess::WorkAccountList::RemoveAccount(HSTRING__ *,HSTRING__ *)

- ea: `0x18001ed78`
- end: `0x18001efd9`
- name: `?RemoveAccount@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUHSTRING__@@0@Z`
- size: `609`
- prototype: `int(SystemSettings::WorkAccess::WorkAccountList *__hidden this, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dba0`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x18000c3f8`
- `0x180012130`
- `0x1800165b0`
- `0x180018420`
- `0x18001bf44`
- `0x18001ed78`
- `0x180042b8c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ef4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ef4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eda0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ee9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eedd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ef23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ef5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ef9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eda0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ee9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eedd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ef23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ef5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ef9b`

## string_xrefs

- `0x18001edd0`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001ee1b`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001ef83`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001efb8`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::RemoveAccount(
        SystemSettings::WorkAccess::WorkAccountList *this,
        HSTRING a2,
        HSTRING a3)
{
  HSTRING *v6; // r9
  int v7; // eax
  unsigned int v8; // ebx
  int Size; // eax
  unsigned int i; // esi
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  HSTRING v16; // r8
  __int64 v17; // rdx
  HSTRING string; // [rsp+20h] [rbp-20h] BYREF
  __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-10h] BYREF
  HSTRING v22; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int v24; // [rsp+78h] [rbp+38h] BYREF

  WindowsDeleteString(0);
  v22 = 0;
  v7 = SystemSettings::WorkAccess::BuildUniqueIdFromAccountAndProviderId(a2, a3, (HSTRING)&v22, v6);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    goto LABEL_19;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 288);
  v24 = 0;
  Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
           *((_QWORD *)this + 26),
           &v24);
  v8 = Size;
  if ( Size < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)Size,
      (int)string);
LABEL_5:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    goto LABEL_19;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v24 )
      goto LABEL_16;
    v20 = 0;
    v11 = *((_QWORD *)this + 26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v12 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
            v11,
            i,
            &v20);
    v8 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CE,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v12,
        (int)string);
      goto LABEL_23;
    }
    string = 0;
    v13 = v20;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v15 = v14(v13, &string);
    v8 = v15;
    if ( v15 < 0 )
    {
      v17 = 465;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v15,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
LABEL_23:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      goto LABEL_5;
    }
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                          (Microsoft::WRL::Wrappers::Details *)string,
                          v22,
                          v16) )
      break;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  }
  v15 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
          *((_QWORD *)this + 26),
          i,
          0);
  v8 = v15;
  if ( v15 < 0 )
  {
    v17 = 469;
    goto LABEL_21;
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
LABEL_16:
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v8 = 0;
LABEL_19:
  WindowsDeleteString(v22);
  return v8;
}

```

## disassembly

```asm
0x18001ed78  mov     [rsp-18h+arg_0], rbx
0x18001ed7d  mov     [rsp-18h+arg_8], rsi
0x18001ed82  push    rbp
0x18001ed83  push    rdi
0x18001ed84  push    r14
0x18001ed86  mov     rbp, rsp
0x18001ed89  sub     rsp, 40h
0x18001ed8d  mov     rbx, r8
0x18001ed90  mov     rdi, rdx
0x18001ed93  mov     r14, rcx
0x18001ed96  mov     [rbp+var_8], 0
0x18001ed9e  xor     ecx, ecx; string
0x18001eda0  call    cs:__imp_WindowsDeleteString
0x18001eda7  nop     dword ptr [rax+rax+00h]
0x18001edac  mov     [rbp+var_8], 0
0x18001edb4  lea     r8, [rbp+var_8]; newString
0x18001edb8  mov     rdx, rbx; string2
0x18001edbb  mov     rcx, rdi; string1
0x18001edbe  call    ?BuildUniqueIdFromAccountAndProviderId@WorkAccess@SystemSettings@@YAJPEAUHSTRING__@@0PEAPEAU3@@Z; SystemSettings::WorkAccess::BuildUniqueIdFromAccountAndProviderId(HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18001edc3  mov     ebx, eax
0x18001edc5  test    eax, eax
0x18001edc7  jns     short loc_18001EDE6
0x18001edc9  mov     rcx, [rbp+18h]; this
0x18001edcd  mov     r9d, eax; char *
0x18001edd0  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001edd7  mov     edx, 1C4h; void *
0x18001eddc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ede1  jmp     loc_18001EF58
0x18001ede6  lea     rdx, [r14+120h]
0x18001eded  lea     rcx, [rbp+SRWLock]
0x18001edf1  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001edf6  nop
0x18001edf7  mov     [rbp+arg_18], 0
0x18001edfe  lea     rdx, [rbp+arg_18]
0x18001ee02  mov     rcx, [r14+0D0h]
0x18001ee09  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x18001ee0e  mov     ebx, eax
0x18001ee10  test    eax, eax
0x18001ee12  jns     short loc_18001EE4B
0x18001ee14  mov     rcx, [rbp+18h]; this
0x18001ee18  mov     r9d, eax; char *
0x18001ee1b  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001ee22  mov     edx, 1CAh; void *
0x18001ee27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee2c  nop
0x18001ee2d  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001ee31  test    rcx, rcx
0x18001ee34  jz      loc_18001EF58
0x18001ee3a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ee41  nop     dword ptr [rax+rax+00h]
0x18001ee46  jmp     loc_18001EF58
0x18001ee4b  xor     esi, esi
0x18001ee4d  cmp     esi, [rbp+arg_18]
0x18001ee50  jnb     loc_18001EF41
0x18001ee56  mov     [rbp+var_18], 0
0x18001ee5e  mov     rbx, [r14+0D0h]
0x18001ee65  lea     rcx, [rbp+var_18]
0x18001ee69  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ee6e  lea     r8, [rbp+var_18]
0x18001ee72  mov     edx, esi
0x18001ee74  mov     rcx, rbx
0x18001ee77  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18001ee7c  mov     ebx, eax
0x18001ee7e  test    eax, eax
0x18001ee80  js      loc_18001EFB1
0x18001ee86  mov     [rbp+string], 0
0x18001ee8e  mov     rdi, [rbp+var_18]
0x18001ee92  mov     rax, [rdi]
0x18001ee95  mov     rbx, [rax+30h]
0x18001ee99  xor     ecx, ecx; string
0x18001ee9b  call    cs:__imp_WindowsDeleteString
0x18001eea2  nop     dword ptr [rax+rax+00h]
0x18001eea7  mov     [rbp+string], 0
0x18001eeaf  lea     rdx, [rbp+string]
0x18001eeb3  mov     rcx, rdi
0x18001eeb6  mov     rax, rbx
0x18001eeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eebe  mov     ebx, eax
0x18001eec0  test    eax, eax
0x18001eec2  js      loc_18001EF7E
0x18001eec8  mov     rdx, [rbp+var_8]; HSTRING
0x18001eecc  mov     rcx, [rbp+string]; this
0x18001eed0  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18001eed5  test    eax, eax
0x18001eed7  jz      short loc_18001EF01
0x18001eed9  mov     rcx, [rbp+string]; string
0x18001eedd  call    cs:__imp_WindowsDeleteString
0x18001eee4  nop     dword ptr [rax+rax+00h]
0x18001eee9  mov     [rbp+string], 0
0x18001eef1  lea     rcx, [rbp+var_18]
0x18001eef5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eefa  inc     esi
0x18001eefc  jmp     loc_18001EE4D
0x18001ef01  xor     r8d, r8d
0x18001ef04  mov     edx, esi
0x18001ef06  mov     rcx, [r14+0D0h]
0x18001ef0d  call    ?RemoveAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(uint,bool)
0x18001ef12  mov     ebx, eax
0x18001ef14  test    eax, eax
0x18001ef16  jns     short loc_18001EF1F
0x18001ef18  mov     edx, 1D5h
0x18001ef1d  jmp     short loc_18001EF83
0x18001ef1f  mov     rcx, [rbp+string]; string
0x18001ef23  call    cs:__imp_WindowsDeleteString
0x18001ef2a  nop     dword ptr [rax+rax+00h]
0x18001ef2f  mov     [rbp+string], 0
0x18001ef37  lea     rcx, [rbp+var_18]
0x18001ef3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ef40  nop
0x18001ef41  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001ef45  test    rcx, rcx
0x18001ef48  jz      short loc_18001EF56
0x18001ef4a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ef51  nop     dword ptr [rax+rax+00h]
0x18001ef56  xor     ebx, ebx
0x18001ef58  mov     rcx, [rbp+var_8]; string
0x18001ef5c  call    cs:__imp_WindowsDeleteString
0x18001ef63  nop     dword ptr [rax+rax+00h]
0x18001ef68  mov     eax, ebx
0x18001ef6a  mov     rbx, [rsp+40h+arg_0]
0x18001ef6f  mov     rsi, [rsp+40h+arg_8]
0x18001ef74  add     rsp, 40h
0x18001ef78  pop     r14
0x18001ef7a  pop     rdi
0x18001ef7b  pop     rbp
0x18001ef7c  retn
0x18001ef7e  mov     edx, 1D1h; void *
0x18001ef83  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001ef8a  mov     r9d, eax; char *
0x18001ef8d  mov     rcx, [rbp+18h]; this
0x18001ef91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef96  nop
0x18001ef97  mov     rcx, [rbp+string]; string
0x18001ef9b  call    cs:__imp_WindowsDeleteString
0x18001efa2  nop     dword ptr [rax+rax+00h]
0x18001efa7  mov     [rbp+string], 0
0x18001efaf  jmp     short loc_18001EFCA
0x18001efb1  mov     rcx, [rbp+18h]; this
0x18001efb5  mov     r9d, eax; char *
0x18001efb8  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001efbf  mov     edx, 1CEh; void *
0x18001efc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001efc9  nop
0x18001efca  lea     rcx, [rbp+var_18]
0x18001efce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001efd3  jmp     loc_18001EE2D
```
