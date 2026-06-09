# Windows::ApplicationModel::Contacts::Internal::PostContactActionControl::_CreateItemFromConnectedServiceAccount(Windows::ApplicationModel::Contacts::IContactConnectedServiceAccount *,Windows::ApplicationModel::Contacts::Internal::ContactServiceActions,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)

- ea: `0x1801e0380`
- end: `0x1801e059d`
- name: `?_CreateItemFromConnectedServiceAccount@PostContactActionControl@Internal@Contacts@ApplicationModel@Windows@@MEAAJPEAUIContactConnectedServiceAccount@345@W4ContactServiceActions@2345@PEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@5@PEAUIContactPreferenceManager@2345@PEAPEAUIContactActionControlItem@2345@@Z`
- size: `541`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009dd0`
- `0x18001c710`
- `0x180053740`
- `0x18011b9b0`
- `0x180142e10`
- `0x1801d6950`
- `0x1801dfc14`
- `0x1801e0108`
- `0x1801e0380`
- `0x1801e0e04`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e03d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e03e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e03f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0557`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e03d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e03e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e03f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0557`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e04a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e04a0`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::PostContactActionControl::_CreateItemFromConnectedServiceAccount(
        __int64 a1,
        __int64 *a2,
        int a3,
        __int64 *a4,
        __int64 a5,
        _QWORD *a6)
{
  int ConnectedServiceAccountData; // eax
  HSTRING v11; // rbx
  int Instance; // r14d
  HSTRING v13; // rdi
  HSTRING v14; // rsi
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v16; // r13
  __int64 v17; // rax
  __int64 v18; // r15
  HSTRING v19; // r12
  __int64 v20; // r14
  unsigned int v21; // eax
  HSTRING string; // [rsp+50h] [rbp-49h] BYREF
  HSTRING v24; // [rsp+58h] [rbp-41h] BYREF
  HSTRING v25; // [rsp+60h] [rbp-39h] BYREF
  __int64 v26; // [rsp+68h] [rbp-31h]
  _QWORD *v27; // [rsp+70h] [rbp-29h]
  __int64 v28; // [rsp+78h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-19h] BYREF
  __int64 v30; // [rsp+98h] [rbp-1h]

  v28 = a5;
  v26 = a1;
  v27 = a6;
  *a6 = 0;
  WindowsDeleteString(0);
  v24 = 0;
  WindowsDeleteString(0);
  v25 = 0;
  WindowsDeleteString(0);
  string = 0;
  ConnectedServiceAccountData = Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_GetConnectedServiceAccountData(
                                  a2,
                                  a3,
                                  a4,
                                  &string,
                                  &v25,
                                  &v24);
  v11 = string;
  Instance = ConnectedServiceAccountData;
  v13 = v25;
  v14 = v24;
  if ( ConnectedServiceAccountData >= 0 && string )
  {
    string = 0;
    v30 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.Contacts.Contact",
      0x2Au,
      0x29u);
    Instance = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContact2>>(
                 v30,
                 &string);
    if ( Instance >= 0 )
    {
      Instance = Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_CopyContactNameAndThumbnail(
                   *(__int64 (__fastcall ****)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *))(a1 + 112),
                   (__int64 (__fastcall ***)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *))string);
      if ( Instance >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
        Instance = Windows::ApplicationModel::Contacts::Internal::PostContactActionControl::_CopyMatchingContactConnectedServiceAccounts(
                     *(struct Windows::ApplicationModel::Contacts::IContact2 **)(a1 + 112),
                     (struct Windows::ApplicationModel::Contacts::IContact2 *)string,
                     StringRawBuffer);
        if ( Instance >= 0 )
        {
          v16 = *(_QWORD *)(a1 + 120);
          v24 = (HSTRING)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 120LL))(a1);
          v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v24);
          v18 = *(_QWORD *)(a1 + 72);
          v19 = string;
          v20 = *(_QWORD *)(v17 + 24);
          v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 112LL))(v26);
          Instance = Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(
                       v21,
                       v19,
                       v18,
                       v20,
                       v14,
                       v13,
                       v11,
                       v16,
                       v28,
                       v27);
        }
      }
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
  }
  WindowsDeleteString(v14);
  WindowsDeleteString(v13);
  WindowsDeleteString(v11);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801e0380  mov     [rsp-8+arg_10], rbx
0x1801e0385  push    rbp
0x1801e0386  push    rsi
0x1801e0387  push    rdi
0x1801e0388  push    r12
0x1801e038a  push    r13
0x1801e038c  push    r14
0x1801e038e  push    r15
0x1801e0390  lea     rbp, [rsp-17h]
0x1801e0395  sub     rsp, 0B0h
0x1801e039c  mov     rax, cs:__security_cookie
0x1801e03a3  xor     rax, rsp
0x1801e03a6  mov     [rbp+47h+var_40], rax
0x1801e03aa  mov     rax, [rbp+47h+arg_20]
0x1801e03ae  mov     r15, rcx
0x1801e03b1  mov     [rbp+47h+var_68], rax
0x1801e03b5  xor     r12d, r12d
0x1801e03b8  mov     rax, [rbp+47h+arg_28]
0x1801e03bc  mov     rsi, r9
0x1801e03bf  mov     [rbp+47h+var_78], rcx
0x1801e03c3  mov     ebx, r8d
0x1801e03c6  xor     ecx, ecx; string
0x1801e03c8  mov     [rbp+47h+var_70], rax
0x1801e03cc  mov     rdi, rdx
0x1801e03cf  mov     [rax], r12
0x1801e03d2  call    cs:__imp_WindowsDeleteString
0x1801e03d9  nop     dword ptr [rax+rax+00h]
0x1801e03de  xor     ecx, ecx; string
0x1801e03e0  mov     [rbp+47h+var_88], r12
0x1801e03e4  call    cs:__imp_WindowsDeleteString
0x1801e03eb  nop     dword ptr [rax+rax+00h]
0x1801e03f0  xor     ecx, ecx; string
0x1801e03f2  mov     [rbp+47h+var_80], r12
0x1801e03f6  call    cs:__imp_WindowsDeleteString
0x1801e03fd  nop     dword ptr [rax+rax+00h]
0x1801e0402  lea     rax, [rbp+47h+var_88]
0x1801e0406  mov     [rbp+47h+string], r12
0x1801e040a  mov     [rsp+0E0h+var_B8], rax
0x1801e040f  lea     r9, [rbp+47h+string]
0x1801e0413  lea     rax, [rbp+47h+var_80]
0x1801e0417  mov     r8, rsi
0x1801e041a  mov     edx, ebx
0x1801e041c  mov     [rsp+0E0h+var_C0], rax
0x1801e0421  mov     rcx, rdi
0x1801e0424  call    ?_GetConnectedServiceAccountData@ContactActionControlBase@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContactConnectedServiceAccount@345@W4ContactServiceActions@2345@PEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@5@PEAPEAUHSTRING__@@33@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_GetConnectedServiceAccountData(Windows::ApplicationModel::Contacts::IContactConnectedServiceAccount *,Windows::ApplicationModel::Contacts::Internal::ContactServiceActions,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1801e0429  mov     rbx, [rbp+47h+string]
0x1801e042d  mov     r14d, eax
0x1801e0430  mov     rdi, [rbp+47h+var_80]
0x1801e0434  mov     rsi, [rbp+47h+var_88]
0x1801e0438  test    eax, eax
0x1801e043a  js      loc_1801E0545
0x1801e0440  test    rbx, rbx
0x1801e0443  jz      loc_1801E0545
0x1801e0449  lea     r9d, [r12+29h]; unsigned int
0x1801e044e  mov     [rbp+47h+string], r12
0x1801e0452  lea     r8d, [r12+2Ah]; unsigned int
0x1801e0457  mov     [rbp+47h+var_48], r12
0x1801e045b  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Contacts_Contact@@3QBGB; "Windows.ApplicationModel.Contacts.Conta"...
0x1801e0462  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x1801e0466  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e046b  mov     rcx, [rbp+47h+var_48]
0x1801e046f  lea     rdx, [rbp+47h+string]
0x1801e0473  call    ??$ActivateInstance@V?$ComPtr@UIContact2@Contacts@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIContact2@Contacts@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContact2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContact2>>)
0x1801e0478  mov     r14d, eax
0x1801e047b  test    eax, eax
0x1801e047d  js      loc_1801E053C
0x1801e0483  mov     rdx, [rbp+47h+string]; struct Windows::ApplicationModel::Contacts::IContact2 *
0x1801e0487  mov     rcx, [r15+70h]; struct Windows::ApplicationModel::Contacts::IContact2 *
0x1801e048b  call    ?_CopyContactNameAndThumbnail@ContactActionControlBase@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContact2@345@0@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_CopyContactNameAndThumbnail(Windows::ApplicationModel::Contacts::IContact2 *,Windows::ApplicationModel::Contacts::IContact2 *)
0x1801e0490  mov     r14d, eax
0x1801e0493  test    eax, eax
0x1801e0495  js      loc_1801E053C
0x1801e049b  xor     edx, edx; length
0x1801e049d  mov     rcx, rbx; string
0x1801e04a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e04a7  nop     dword ptr [rax+rax+00h]
0x1801e04ac  mov     rdx, [rbp+47h+string]; struct Windows::ApplicationModel::Contacts::IContact2 *
0x1801e04b0  mov     r8, rax; unsigned __int16 *
0x1801e04b3  mov     rcx, [r15+70h]; struct Windows::ApplicationModel::Contacts::IContact2 *
0x1801e04b7  call    ?_CopyMatchingContactConnectedServiceAccounts@PostContactActionControl@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContact2@345@0PEBG@Z; Windows::ApplicationModel::Contacts::Internal::PostContactActionControl::_CopyMatchingContactConnectedServiceAccounts(Windows::ApplicationModel::Contacts::IContact2 *,Windows::ApplicationModel::Contacts::IContact2 *,ushort const *)
0x1801e04bc  mov     r14d, eax
0x1801e04bf  test    eax, eax
0x1801e04c1  js      short loc_1801E053C
0x1801e04c3  mov     rax, [r15]
0x1801e04c6  mov     rcx, r15
0x1801e04c9  mov     r13, [r15+78h]
0x1801e04cd  mov     rax, [rax+78h]
0x1801e04d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e04d6  lea     rdx, [rbp+47h+var_88]
0x1801e04da  mov     [rbp+47h+var_88], rax
0x1801e04de  lea     rcx, [rbp+47h+hstringHeader]
0x1801e04e2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801e04e7  mov     rcx, [rbp+47h+var_78]
0x1801e04eb  mov     r15, [r15+48h]
0x1801e04ef  mov     r12, [rbp+47h+string]
0x1801e04f3  mov     r14, [rax+18h]
0x1801e04f7  mov     rax, [rcx]
0x1801e04fa  mov     rax, [rax+70h]
0x1801e04fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0503  mov     rcx, [rbp+47h+var_70]
0x1801e0507  mov     r9, r14
0x1801e050a  mov     [rsp+0E0h+var_98], rcx
0x1801e050f  mov     r8, r15
0x1801e0512  mov     rcx, [rbp+47h+var_68]
0x1801e0516  mov     rdx, r12
0x1801e0519  mov     [rsp+0E0h+var_A0], rcx
0x1801e051e  mov     ecx, eax
0x1801e0520  mov     [rsp+0E0h+var_A8], r13
0x1801e0525  mov     [rsp+0E0h+var_B0], rbx
0x1801e052a  mov     [rsp+0E0h+var_B8], rdi
0x1801e052f  mov     [rsp+0E0h+var_C0], rsi
0x1801e0534  call    ?ContactActionControlItem_CreateInstance@Internal@Contacts@ApplicationModel@Windows@@YAJW4ControlType@1234@PEAUIContact2@234@PEAUHSTRING__@@2222PEAUIShellItem@@PEAUIContactPreferenceManager@1234@PEAPEAUIContactActionControlItem@1234@@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(Windows::ApplicationModel::Contacts::Internal::ControlType,Windows::ApplicationModel::Contacts::IContact2 *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,IShellItem *,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)
0x1801e0539  mov     r14d, eax
0x1801e053c  lea     rcx, [rbp+47h+string]
0x1801e0540  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e0545  mov     rcx, rsi; string
0x1801e0548  call    cs:__imp_WindowsDeleteString
0x1801e054f  nop     dword ptr [rax+rax+00h]
0x1801e0554  mov     rcx, rdi; string
0x1801e0557  call    cs:__imp_WindowsDeleteString
0x1801e055e  nop     dword ptr [rax+rax+00h]
0x1801e0563  mov     rcx, rbx; string
0x1801e0566  call    cs:__imp_WindowsDeleteString
0x1801e056d  nop     dword ptr [rax+rax+00h]
0x1801e0572  mov     eax, r14d
0x1801e0575  mov     rcx, [rbp+47h+var_40]
0x1801e0579  xor     rcx, rsp; StackCookie
0x1801e057c  call    __security_check_cookie
0x1801e0581  mov     rbx, [rsp+0E0h+arg_10]
0x1801e0589  add     rsp, 0B0h
0x1801e0590  pop     r15
0x1801e0592  pop     r14
0x1801e0594  pop     r13
0x1801e0596  pop     r12
0x1801e0598  pop     rdi
0x1801e0599  pop     rsi
0x1801e059a  pop     rbp
0x1801e059b  retn
```
