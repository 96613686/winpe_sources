# SystemSettings::WorkAccess::WorkAccountList::SetAccountBusy(HSTRING__ *,HSTRING__ *,bool)

- ea: `0x18001f454`
- end: `0x18001f6b2`
- name: `?SetAccountBusy@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUHSTRING__@@0_N@Z`
- size: `606`
- prototype: `int(SystemSettings::WorkAccess::WorkAccountList *__hidden this, HSTRING, HSTRING, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001da70`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x18000c3f8`
- `0x180012130`
- `0x180018420`
- `0x18001bf44`
- `0x18001f454`
- `0x180042b8c`
- `0x1800440f0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f51b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f623`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f51b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f623`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f57c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f5be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f5fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f674`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f57c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f5be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f5fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f674`

## string_xrefs

- `0x18001f4b1`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001f4fc`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001f65c`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001f691`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::SetAccountBusy(
        SystemSettings::WorkAccess::WorkAccountList *this,
        HSTRING a2,
        HSTRING a3,
        char a4)
{
  HSTRING *v7; // r9
  int v8; // eax
  unsigned int v9; // ebx
  int Size; // eax
  unsigned int i; // esi
  __int64 v12; // rbx
  int v13; // eax
  SystemSettings::WorkAccess::WorkAccountItem *v14; // rdi
  __int64 (__fastcall *v15)(SystemSettings::WorkAccess::WorkAccountItem *, HSTRING *); // rbx
  int v16; // eax
  HSTRING v17; // r8
  bool v18; // dl
  __int64 v19; // rdx
  HSTRING string; // [rsp+20h] [rbp-20h] BYREF
  SystemSettings::WorkAccess::WorkAccountItem *v22; // [rsp+28h] [rbp-18h] BYREF
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-10h] BYREF
  HSTRING v24; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int v26; // [rsp+78h] [rbp+38h] BYREF

  LOBYTE(v26) = a4;
  WindowsDeleteString(0);
  v24 = 0;
  v8 = SystemSettings::WorkAccess::BuildUniqueIdFromAccountAndProviderId(a2, a3, (HSTRING)&v24, v7);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
    goto LABEL_19;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 288);
  v26 = 0;
  Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
           *((_QWORD *)this + 26),
           &v26);
  v9 = Size;
  if ( Size < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E8,
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
    if ( i >= v26 )
      goto LABEL_16;
    v22 = 0;
    v12 = *((_QWORD *)this + 26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v13 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
            v12,
            i,
            &v22);
    v9 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v13,
        (int)string);
      goto LABEL_23;
    }
    string = 0;
    v14 = v22;
    v15 = *(__int64 (__fastcall **)(SystemSettings::WorkAccess::WorkAccountItem *, HSTRING *))(*(_QWORD *)v22 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v16 = v15(v14, &string);
    v9 = v16;
    if ( v16 < 0 )
    {
      v19 = 495;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v16,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
LABEL_23:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      goto LABEL_5;
    }
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                          (Microsoft::WRL::Wrappers::Details *)string,
                          v24,
                          v17) )
      break;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  }
  v16 = SystemSettings::WorkAccess::WorkAccountItem::SetAccountBusy(v22, v18);
  v9 = v16;
  if ( v16 < 0 )
  {
    v19 = 500;
    goto LABEL_21;
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
LABEL_16:
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v9 = 0;
LABEL_19:
  WindowsDeleteString(v24);
  return v9;
}

```

## disassembly

```asm
0x18001f454  mov     [rsp-18h+arg_0], rbx
0x18001f459  mov     [rsp-18h+arg_8], rsi
0x18001f45e  mov     byte ptr [rsp-18h+arg_18], r9b
0x18001f463  push    rbp
0x18001f464  push    rdi
0x18001f465  push    r14
0x18001f467  mov     rbp, rsp
0x18001f46a  sub     rsp, 40h
0x18001f46e  mov     rbx, r8
0x18001f471  mov     rdi, rdx
0x18001f474  mov     r14, rcx
0x18001f477  mov     [rbp+var_8], 0
0x18001f47f  xor     ecx, ecx; string
0x18001f481  call    cs:__imp_WindowsDeleteString
0x18001f488  nop     dword ptr [rax+rax+00h]
0x18001f48d  mov     [rbp+var_8], 0
0x18001f495  lea     r8, [rbp+var_8]; newString
0x18001f499  mov     rdx, rbx; string2
0x18001f49c  mov     rcx, rdi; string1
0x18001f49f  call    ?BuildUniqueIdFromAccountAndProviderId@WorkAccess@SystemSettings@@YAJPEAUHSTRING__@@0PEAPEAU3@@Z; SystemSettings::WorkAccess::BuildUniqueIdFromAccountAndProviderId(HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18001f4a4  mov     ebx, eax
0x18001f4a6  test    eax, eax
0x18001f4a8  jns     short loc_18001F4C7
0x18001f4aa  mov     rcx, [rbp+18h]; this
0x18001f4ae  mov     r9d, eax; char *
0x18001f4b1  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001f4b8  mov     edx, 1E2h; void *
0x18001f4bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f4c2  jmp     loc_18001F631
0x18001f4c7  lea     rdx, [r14+120h]
0x18001f4ce  lea     rcx, [rbp+SRWLock]
0x18001f4d2  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001f4d7  nop
0x18001f4d8  mov     [rbp+arg_18], 0
0x18001f4df  lea     rdx, [rbp+arg_18]
0x18001f4e3  mov     rcx, [r14+0D0h]
0x18001f4ea  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x18001f4ef  mov     ebx, eax
0x18001f4f1  test    eax, eax
0x18001f4f3  jns     short loc_18001F52C
0x18001f4f5  mov     rcx, [rbp+18h]; this
0x18001f4f9  mov     r9d, eax; char *
0x18001f4fc  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001f503  mov     edx, 1E8h; void *
0x18001f508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f50d  nop
0x18001f50e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001f512  test    rcx, rcx
0x18001f515  jz      loc_18001F631
0x18001f51b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f522  nop     dword ptr [rax+rax+00h]
0x18001f527  jmp     loc_18001F631
0x18001f52c  xor     esi, esi
0x18001f52e  cmp     esi, [rbp+arg_18]
0x18001f531  jnb     loc_18001F61A
0x18001f537  mov     [rbp+var_18], 0
0x18001f53f  mov     rbx, [r14+0D0h]
0x18001f546  lea     rcx, [rbp+var_18]
0x18001f54a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f54f  lea     r8, [rbp+var_18]
0x18001f553  mov     edx, esi
0x18001f555  mov     rcx, rbx
0x18001f558  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18001f55d  mov     ebx, eax
0x18001f55f  test    eax, eax
0x18001f561  js      loc_18001F68A
0x18001f567  mov     [rbp+string], 0
0x18001f56f  mov     rdi, [rbp+var_18]
0x18001f573  mov     rax, [rdi]
0x18001f576  mov     rbx, [rax+30h]
0x18001f57a  xor     ecx, ecx; string
0x18001f57c  call    cs:__imp_WindowsDeleteString
0x18001f583  nop     dword ptr [rax+rax+00h]
0x18001f588  mov     [rbp+string], 0
0x18001f590  lea     rdx, [rbp+string]
0x18001f594  mov     rcx, rdi
0x18001f597  mov     rax, rbx
0x18001f59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f59f  mov     ebx, eax
0x18001f5a1  test    eax, eax
0x18001f5a3  js      loc_18001F657
0x18001f5a9  mov     rdx, [rbp+var_8]; HSTRING
0x18001f5ad  mov     rcx, [rbp+string]; this
0x18001f5b1  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18001f5b6  test    eax, eax
0x18001f5b8  jz      short loc_18001F5E2
0x18001f5ba  mov     rcx, [rbp+string]; string
0x18001f5be  call    cs:__imp_WindowsDeleteString
0x18001f5c5  nop     dword ptr [rax+rax+00h]
0x18001f5ca  mov     [rbp+string], 0
0x18001f5d2  lea     rcx, [rbp+var_18]
0x18001f5d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f5db  inc     esi
0x18001f5dd  jmp     loc_18001F52E
0x18001f5e2  mov     rcx, [rbp+var_18]; this
0x18001f5e6  call    ?SetAccountBusy@WorkAccountItem@WorkAccess@SystemSettings@@QEAAJ_N@Z; SystemSettings::WorkAccess::WorkAccountItem::SetAccountBusy(bool)
0x18001f5eb  mov     ebx, eax
0x18001f5ed  test    eax, eax
0x18001f5ef  jns     short loc_18001F5F8
0x18001f5f1  mov     edx, 1F4h
0x18001f5f6  jmp     short loc_18001F65C
0x18001f5f8  mov     rcx, [rbp+string]; string
0x18001f5fc  call    cs:__imp_WindowsDeleteString
0x18001f603  nop     dword ptr [rax+rax+00h]
0x18001f608  mov     [rbp+string], 0
0x18001f610  lea     rcx, [rbp+var_18]
0x18001f614  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f619  nop
0x18001f61a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001f61e  test    rcx, rcx
0x18001f621  jz      short loc_18001F62F
0x18001f623  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f62a  nop     dword ptr [rax+rax+00h]
0x18001f62f  xor     ebx, ebx
0x18001f631  mov     rcx, [rbp+var_8]; string
0x18001f635  call    cs:__imp_WindowsDeleteString
0x18001f63c  nop     dword ptr [rax+rax+00h]
0x18001f641  mov     eax, ebx
0x18001f643  mov     rbx, [rsp+40h+arg_0]
0x18001f648  mov     rsi, [rsp+40h+arg_8]
0x18001f64d  add     rsp, 40h
0x18001f651  pop     r14
0x18001f653  pop     rdi
0x18001f654  pop     rbp
0x18001f655  retn
0x18001f657  mov     edx, 1EFh; void *
0x18001f65c  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001f663  mov     r9d, eax; char *
0x18001f666  mov     rcx, [rbp+18h]; this
0x18001f66a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f66f  nop
0x18001f670  mov     rcx, [rbp+string]; string
0x18001f674  call    cs:__imp_WindowsDeleteString
0x18001f67b  nop     dword ptr [rax+rax+00h]
0x18001f680  mov     [rbp+string], 0
0x18001f688  jmp     short loc_18001F6A3
0x18001f68a  mov     rcx, [rbp+18h]; this
0x18001f68e  mov     r9d, eax; char *
0x18001f691  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001f698  mov     edx, 1ECh; void *
0x18001f69d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6a2  nop
0x18001f6a3  lea     rcx, [rbp+var_18]
0x18001f6a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f6ac  jmp     loc_18001F50E
```
