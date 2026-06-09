# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_RecursivelyUpdateParentsOnProgress(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *)

- ea: `0x1800cb26c`
- end: `0x1800cb5d5`
- name: `?_RecursivelyUpdateParentsOnProgress@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAVAppInstallItem@23456@@Z`
- size: `873`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *__hidden this, struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a86bc`

## callees

- `0x1800101f4`
- `0x18001c414`
- `0x180028cd4`
- `0x18008b620`
- `0x18008d0a8`
- `0x18008e470`
- `0x1800bcc30`
- `0x1800c7538`
- `0x1800c7820`
- `0x1800c9dfc`
- `0x1800cb26c`
- `0x1800d195c`
- `0x18011e070`
- `0x18011e1d4`
- `0x18011e4cc`
- `0x18011efc0`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cb3c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cb476`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cb3c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cb476`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cb39c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cb45e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cb39c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cb45e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb2db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb30b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb4e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb4f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb2db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb30b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb4e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb4f1`

## string_xrefs

- `0x1800cb59c`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800cb560`: `INSTALL_AGENT_E_MAX_INSTALL_HIERARCHY_REACHED`
- `0x1800cb58f`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_RecursivelyUpdateParentsOnProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_RecursivelyUpdateParentsOnProgress(
        RTL_SRWLOCK *this,
        struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *a2)
{
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v2; // rbx
  int InstallItem; // r15d
  unsigned int i; // esi
  __int64 (__fastcall *v6)(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *, HSTRING *); // rdi
  bool IsCompleted; // r14
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v8; // rdi
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v9; // r12
  __int64 (__fastcall *v10)(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *, RTL_SRWLOCK **); // rdi
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v11; // rsi
  HSTRING v12; // rdi
  RTL_SRWLOCK *v13; // r14
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v14; // rdi
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v16; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING v18; // [rsp+60h] [rbp-20h] BYREF
  RTL_SRWLOCK *v19; // [rsp+68h] [rbp-18h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v20; // [rsp+70h] [rbp-10h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v21; // [rsp+78h] [rbp-8h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v22; // [rsp+C8h] [rbp+48h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v23; // [rsp+D0h] [rbp+50h] BYREF
  HSTRING v24; // [rsp+D8h] [rbp+58h] BYREF

  v22 = a2;
  v2 = a2;
  InstallItem = 0;
  v20 = a2;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v20);
  for ( i = 0; ; ++i )
  {
    LODWORD(v24) = i;
    if ( InstallItem < 0 || !v2 )
      break;
    if ( i >= 0x10 )
    {
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        0x341u,
        "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_RecursivelyUpdateParentsOnProgress",
        -2143309560,
        L"%hs",
        0,
        0,
        0,
        "INSTALL_AGENT_E_MAX_INSTALL_HIERARCHY_REACHED");
      break;
    }
    v18 = 0;
    string = 0;
    v16 = 0;
    v6 = *(__int64 (__fastcall **)(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *, HSTRING *))(*(_QWORD *)v2 + 48LL);
    WindowsDeleteString(0);
    v18 = 0;
    InstallItem = v6(v2, &v18);
    IsCompleted = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::IsCompleted(v2);
    if ( InstallItem < 0 )
      goto LABEL_12;
    WindowsDeleteString(string);
    string = 0;
    if ( (int)Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::get_ParentId(v2, &string) < 0
      || !string )
    {
      goto LABEL_12;
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v16);
    InstallItem = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_FindInstallItem(
                    (Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)this,
                    string,
                    0,
                    &v16);
    if ( InstallItem >= 0 )
    {
      v8 = v16;
      if ( (int)Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::_AddChildInstall(v16, v2) >= 0 )
        Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::OnProgress(v8, 0);
      Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_FireItemProgressEvent(
        (Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)this,
        v16);
LABEL_12:
      if ( !IsCompleted )
        goto LABEL_24;
LABEL_13:
      Microsoft::WRL::Details::Make<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerItemEventArgs,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * &>(
        &v21,
        &v22);
      AcquireSRWLockExclusive(this + 30);
      if ( !i || !Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::HasInstall(v2) )
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
          this[34].Ptr,
          v18);
      ReleaseSRWLockExclusive(this + 30);
      v9 = v21;
      v23 = v21;
      v19 = this;
      wil::AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerItemEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy>::AsyncInvokeAll<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerItemEventArgs *>(&this[35]);
      if ( v16 )
      {
        v19 = 0;
        v10 = *(__int64 (__fastcall **)(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *, RTL_SRWLOCK **))(*(_QWORD *)v2 + 80LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v19);
        InstallItem = v10(v2, &v19);
        if ( InstallItem >= 0 )
        {
          LODWORD(v23) = 0;
          InstallItem = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem **))v19->Ptr
                         + 6))(
                          v19,
                          &v23);
          if ( InstallItem >= 0 && (_DWORD)v23 == 7 )
          {
            v11 = v16;
            v12 = v18;
            v13 = (RTL_SRWLOCK *)((char *)v16 + 152);
            AcquireSRWLockExclusive((PSRWLOCK)v16 + 19);
            Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(
              *((_QWORD *)v11 + 23),
              v12);
            ReleaseSRWLockExclusive(v13);
            i = (unsigned int)v24;
          }
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v19);
      }
      if ( v9 )
      {
        v21 = 0;
        (*(void (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      goto LABEL_24;
    }
    if ( IsCompleted )
    {
      InstallItem = 0;
      goto LABEL_13;
    }
    v23 = v2;
    v24 = string;
    v19 = this;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v16);
    InstallItem = Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>(
                    &v16,
                    &v19,
                    &v24,
                    &v23);
    if ( InstallItem >= 0 )
      InstallItem = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_NewInstallItem((Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)this);
LABEL_24:
    v14 = v16;
    if ( v2 != v16 )
    {
      v23 = v16;
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v23);
      v23 = v2;
      v2 = v14;
      v20 = v14;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v23);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v16);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v18);
    v18 = 0;
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
  return (unsigned int)InstallItem;
}

```

## disassembly

```asm
0x1800cb26c  mov     [rsp-38h+arg_0], rbx
0x1800cb271  mov     [rsp-38h+arg_8], rdx
0x1800cb276  push    rbp
0x1800cb277  push    rsi
0x1800cb278  push    rdi
0x1800cb279  push    r12
0x1800cb27b  push    r13
0x1800cb27d  push    r14
0x1800cb27f  push    r15
0x1800cb281  mov     rbp, rsp
0x1800cb284  sub     rsp, 80h
0x1800cb28b  mov     rbx, rdx
0x1800cb28e  mov     r13, rcx
0x1800cb291  xor     r12d, r12d
0x1800cb294  mov     r15d, r12d
0x1800cb297  mov     [rbp+var_10], rdx
0x1800cb29b  lea     rcx, [rbp+var_10]
0x1800cb29f  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800cb2a4  nop
0x1800cb2a5  mov     esi, r12d
0x1800cb2a8  mov     dword ptr [rbp+arg_18], esi
0x1800cb2ab  test    r15d, r15d
0x1800cb2ae  js      loc_1800CB5AE
0x1800cb2b4  test    rbx, rbx
0x1800cb2b7  jz      loc_1800CB5AE
0x1800cb2bd  cmp     esi, 10h
0x1800cb2c0  jnb     loc_1800CB560
0x1800cb2c6  mov     [rbp+var_20], r12
0x1800cb2ca  mov     [rbp+string], r12
0x1800cb2ce  mov     [rbp+var_30], r12
0x1800cb2d2  mov     rax, [rbx]
0x1800cb2d5  mov     rdi, [rax+30h]
0x1800cb2d9  xor     ecx, ecx; string
0x1800cb2db  call    cs:__imp_WindowsDeleteString
0x1800cb2e1  mov     [rbp+var_20], r12
0x1800cb2e5  lea     rdx, [rbp+var_20]
0x1800cb2e9  mov     rcx, rbx
0x1800cb2ec  mov     rax, rdi
0x1800cb2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb2f4  mov     r15d, eax
0x1800cb2f7  mov     rcx, rbx; this
0x1800cb2fa  call    ?IsCompleted@AppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::IsCompleted(void)
0x1800cb2ff  mov     r14b, al
0x1800cb302  test    r15d, r15d
0x1800cb305  js      short loc_1800CB37B
0x1800cb307  mov     rcx, [rbp+string]; string
0x1800cb30b  call    cs:__imp_WindowsDeleteString
0x1800cb311  mov     [rbp+string], r12
0x1800cb315  lea     rdx, [rbp+string]; HSTRING *
0x1800cb319  mov     rcx, rbx; this
0x1800cb31c  call    ?get_ParentId@AppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAAJPEAPEAUHSTRING__@@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::get_ParentId(HSTRING__ * *)
0x1800cb321  test    eax, eax
0x1800cb323  js      short loc_1800CB37B
0x1800cb325  cmp     [rbp+string], r12
0x1800cb329  jz      short loc_1800CB37B
0x1800cb32b  lea     rcx, [rbp+var_30]
0x1800cb32f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cb334  lea     r9, [rbp+var_30]; struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem **
0x1800cb338  xor     r8d, r8d; bool
0x1800cb33b  mov     rdx, [rbp+string]; HSTRING
0x1800cb33f  mov     rcx, r13; this
0x1800cb342  call    ?_FindInstallItem@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUHSTRING__@@_NPEAPEAVAppInstallItem@23456@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_FindInstallItem(HSTRING__ *,bool,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * *)
0x1800cb347  mov     r15d, eax
0x1800cb34a  test    eax, eax
0x1800cb34c  js      loc_1800CB502
0x1800cb352  mov     rdi, [rbp+var_30]
0x1800cb356  mov     rdx, rbx; struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *
0x1800cb359  mov     rcx, rdi; this
0x1800cb35c  call    ?_AddChildInstall@AppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAV123456@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::_AddChildInstall(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *)
0x1800cb361  test    eax, eax
0x1800cb363  js      short loc_1800CB36F
0x1800cb365  xor     edx, edx; struct WindowsUpdate::Internal::IInstallItem *
0x1800cb367  mov     rcx, rdi; this
0x1800cb36a  call    ?OnProgress@AppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAAJPEAUIInstallItem@Internal@WindowsUpdate@@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::OnProgress(WindowsUpdate::Internal::IInstallItem *)
0x1800cb36f  mov     rdx, [rbp+var_30]; struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *
0x1800cb373  mov     rcx, r13; this
0x1800cb376  call    ?_FireItemProgressEvent@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAXPEAVAppInstallItem@23456@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_FireItemProgressEvent(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *)
0x1800cb37b  test    r14b, r14b
0x1800cb37e  jz      loc_1800CB4AA
0x1800cb384  lea     rdx, [rbp+arg_8]
0x1800cb388  lea     rcx, [rbp+var_8]
0x1800cb38c  call    ??$Make@VAppInstallManagerItemEventArgs@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAPEAVAppInstallItem@23456@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAppInstallManagerItemEventArgs@InstallControl@Preview@Store@ApplicationModel@Windows@@@12@AEAPEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; Microsoft::WRL::Details::Make<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerItemEventArgs,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * &>(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * &)
0x1800cb391  nop
0x1800cb392  lea     rdi, [r13+0F0h]
0x1800cb399  mov     rcx, rdi; SRWLock
0x1800cb39c  call    cs:__imp_AcquireSRWLockExclusive
0x1800cb3a2  test    esi, esi
0x1800cb3a4  jz      short loc_1800CB3B2
0x1800cb3a6  mov     rcx, rbx; this
0x1800cb3a9  call    ?HasInstall@AppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem::HasInstall(void)
0x1800cb3ae  test    al, al
0x1800cb3b0  jnz     short loc_1800CB3C2
0x1800cb3b2  mov     rdx, [rbp+var_20]
0x1800cb3b6  mov     rcx, [r13+110h]
0x1800cb3bd  call    ?Remove@?$HashMap@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@7@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@9Collections@Foundation@7@U?$HashMapOptions@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@7@$0A@$00$0A@@9Collections@Foundation@7@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)
0x1800cb3c2  mov     rcx, rdi; SRWLock
0x1800cb3c5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cb3cb  mov     r12, [rbp+var_8]
0x1800cb3cf  mov     [rbp+arg_10], r12
0x1800cb3d3  mov     [rbp+var_18], r13
0x1800cb3d7  lea     rcx, [r13+118h]
0x1800cb3de  lea     r8, [rbp+arg_10]
0x1800cb3e2  lea     rdx, [rbp+var_18]
0x1800cb3e6  call    ??$AsyncInvokeAll@PEAVAppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAVAppInstallManagerItemEventArgs@23456@@?$AsyncEventSourceT@U?$ITypedEventHandler@PEAVAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAVAppInstallManagerItemEventArgs@23456@@Foundation@Windows@@VGitEventSourceSupportsAgile@Internal@3@U?$InvokeModeOptions@$01@WRL@Microsoft@@$00Uerr_returncode_policy@wil@@@wil@@QEAAJAEBQEAVAppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEBQEAVAppInstallManagerItemEventArgs@34567@@Z; wil::AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerItemEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy>::AsyncInvokeAll<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerItemEventArgs *>(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl * const &,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerItemEventArgs * const &)
0x1800cb3eb  cmp     [rbp+var_30], 0
0x1800cb3f0  jz      loc_1800CB489
0x1800cb3f6  mov     [rbp+var_18], 0
0x1800cb3fe  mov     rax, [rbx]
0x1800cb401  mov     rdi, [rax+50h]
0x1800cb405  lea     rcx, [rbp+var_18]
0x1800cb409  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cb40e  lea     rdx, [rbp+var_18]
0x1800cb412  mov     rcx, rbx
0x1800cb415  mov     rax, rdi
0x1800cb418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb41d  mov     r15d, eax
0x1800cb420  test    eax, eax
0x1800cb422  js      short loc_1800CB47F
0x1800cb424  mov     dword ptr [rbp+arg_10], 0
0x1800cb42b  mov     rcx, [rbp+var_18]
0x1800cb42f  mov     rax, [rcx]
0x1800cb432  lea     rdx, [rbp+arg_10]
0x1800cb436  mov     rax, [rax+30h]
0x1800cb43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb43f  mov     r15d, eax
0x1800cb442  test    eax, eax
0x1800cb444  js      short loc_1800CB47F
0x1800cb446  cmp     dword ptr [rbp+arg_10], 7
0x1800cb44a  jnz     short loc_1800CB47F
0x1800cb44c  mov     rsi, [rbp+var_30]
0x1800cb450  mov     rdi, [rbp+var_20]
0x1800cb454  lea     r14, [rsi+98h]
0x1800cb45b  mov     rcx, r14; SRWLock
0x1800cb45e  call    cs:__imp_AcquireSRWLockExclusive
0x1800cb464  mov     rdx, rdi
0x1800cb467  mov     rcx, [rsi+0B8h]
0x1800cb46e  call    ?Remove@?$HashMap@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@7@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@9Collections@Foundation@7@U?$HashMapOptions@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@7@$0A@$00$0A@@9Collections@Foundation@7@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Remove(HSTRING__ *)
0x1800cb473  mov     rcx, r14; SRWLock
0x1800cb476  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cb47c  mov     esi, dword ptr [rbp+arg_18]
0x1800cb47f  lea     rcx, [rbp+var_18]
0x1800cb483  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cb488  nop
0x1800cb489  test    r12, r12
0x1800cb48c  jz      short loc_1800CB4A7
0x1800cb48e  mov     [rbp+var_8], 0
0x1800cb496  mov     rax, [r12]
0x1800cb49a  mov     rcx, r12
0x1800cb49d  mov     rax, [rax+10h]
0x1800cb4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb4a6  nop
0x1800cb4a7  xor     r12d, r12d
0x1800cb4aa  mov     rdi, [rbp+var_30]
0x1800cb4ae  cmp     rbx, rdi
0x1800cb4b1  jz      short loc_1800CB4D5
0x1800cb4b3  mov     [rbp+arg_10], rdi
0x1800cb4b7  lea     rcx, [rbp+arg_10]
0x1800cb4bb  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800cb4c0  mov     [rbp+arg_10], rbx
0x1800cb4c4  mov     rbx, rdi
0x1800cb4c7  mov     [rbp+var_10], rbx
0x1800cb4cb  lea     rcx, [rbp+arg_10]
0x1800cb4cf  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cb4d4  nop
0x1800cb4d5  lea     rcx, [rbp+var_30]
0x1800cb4d9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cb4de  nop
0x1800cb4df  mov     rcx, [rbp+string]; string
0x1800cb4e3  call    cs:__imp_WindowsDeleteString
0x1800cb4e9  mov     [rbp+string], r12
0x1800cb4ed  mov     rcx, [rbp+var_20]; string
0x1800cb4f1  call    cs:__imp_WindowsDeleteString
0x1800cb4f7  mov     [rbp+var_20], r12
0x1800cb4fb  inc     esi
0x1800cb4fd  jmp     loc_1800CB2A8
0x1800cb502  test    r14b, r14b
0x1800cb505  jnz     short loc_1800CB558
0x1800cb507  mov     [rbp+arg_10], rbx
0x1800cb50b  mov     rax, [rbp+string]
0x1800cb50f  mov     [rbp+arg_18], rax
0x1800cb513  mov     [rbp+var_18], r13
0x1800cb517  lea     rcx, [rbp+var_30]
0x1800cb51b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cb520  lea     r9, [rbp+arg_10]
0x1800cb524  lea     r8, [rbp+arg_18]
0x1800cb528  lea     rdx, [rbp+var_18]
0x1800cb52c  lea     rcx, [rbp+var_30]
0x1800cb530  call    ??$MakeAndInitialize@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@V123456@PEAVAppInstallManagerImpl@23456@PEAUHSTRING__@@PEAV123456@@Details@WRL@Microsoft@@YAJPEAPEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@$$QEAPEAVAppInstallManagerImpl@45678@$$QEAPEAUHSTRING__@@$$QEAPEAV345678@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl * &&,HSTRING__ * &&,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * &&)
0x1800cb535  mov     r15d, eax
0x1800cb538  test    eax, eax
0x1800cb53a  js      loc_1800CB4AA
0x1800cb540  lea     r8, [rbp+var_30]
0x1800cb544  mov     rdx, [rbp+string]
0x1800cb548  mov     rcx, r13; this
0x1800cb54b  call    ?_NewInstallItem@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUHSTRING__@@AEAV?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_NewInstallItem(HSTRING__ *,Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem> &)
0x1800cb550  mov     r15d, eax
0x1800cb553  jmp     loc_1800CB4AA
0x1800cb558  mov     r15d, r12d
0x1800cb55b  jmp     loc_1800CB384
0x1800cb560  lea     rax, aInstallAgentEM; "INSTALL_AGENT_E_MAX_INSTALL_HIERARCHY_R"...
0x1800cb567  mov     [rsp+80h+var_38], rax
0x1800cb56c  mov     [rsp+80h+var_40], r12
0x1800cb571  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x1800cb576  mov     [rsp+80h+var_50], r12; char *
0x1800cb57b  lea     rax, aHs_1; "%hs"
0x1800cb582  mov     [rsp+80h+var_58], rax; unsigned __int16 *
0x1800cb587  mov     [rsp+80h+var_60], 803FB108h; int
0x1800cb58f  lea     r9, aWindowsApplica_56; "Windows::ApplicationModel::Store::Previ"...
0x1800cb596  mov     r8d, 341h; unsigned int
0x1800cb59c  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800cb5a3  mov     ecx, 1; unsigned int
0x1800cb5a8  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800cb5ad  nop
0x1800cb5ae  lea     rcx, [rbp+var_10]
0x1800cb5b2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800cb5b7  mov     eax, r15d
0x1800cb5ba  mov     rbx, [rsp+80h+arg_0]
0x1800cb5c2  add     rsp, 80h
0x1800cb5c9  pop     r15
0x1800cb5cb  pop     r14
0x1800cb5cd  pop     r13
0x1800cb5cf  pop     r12
0x1800cb5d1  pop     rdi
0x1800cb5d2  pop     rsi
0x1800cb5d3  pop     rbp
0x1800cb5d4  retn
```
