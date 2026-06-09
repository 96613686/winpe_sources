# InstallQueue::_AppendWuCategoryIdIfNotRunning(WindowsUpdate::Internal::IFulfillmentDataInfo *,bool,std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>> &,std::vector<Microsoft::WRL::Wrappers::HString,std::allocator<Microsoft::WRL::Wrappers::HString>> &)

- ea: `0x18005c078`
- end: `0x18005c330`
- name: `?_AppendWuCategoryIdIfNotRunning@InstallQueue@@AEAAXPEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@_NAEAV?$map@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@@std@@@7@@std@@AEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@6@@Z`
- size: `696`
- prototype: `__int64 __usercall@<rax>(InstallQueue *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005e49c`

## callees

- `0x1800101f4`
- `0x18001c414`
- `0x18001ddb0`
- `0x18002c310`
- `0x18002ec2c`
- `0x1800309b0`
- `0x18004febc`
- `0x180052008`
- `0x1800578cc`
- `0x18005c078`
- `0x18005d568`
- `0x180063178`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c0b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c1d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c30e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c0b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c1d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c30e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c0f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c17b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c0f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c17b`

## string_xrefs

- `0x18005c0d4`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005c10e`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005c138`: `Found already queued item for update. productId = %s`
- `0x18005c14b`: `InstallQueue::_AppendWuCategoryIdIfNotRunning`
- `0x18005c1a0`: `InstallQueue::_AppendWuCategoryIdIfNotRunning`
- `0x18005c190`: `Pausing existing update. Will be restarted after a new scan. productId = %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HRESULT __fastcall InstallQueue::_AppendWuCategoryIdIfNotRunning(
        InstallQueue *this,
        __int64 a2,
        char a3,
        HSTRING *a4,
        __int64 a5)
{
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  _QWORD *v16; // rax
  int v17; // eax
  int v19; // [rsp+20h] [rbp-60h]
  __int64 v20; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  WindowsUpdate::Internal::InstallItem *v22; // [rsp+60h] [rbp-20h] BYREF
  HSTRING newString; // [rsp+68h] [rbp-18h] BYREF
  HSTRING v24[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  HSTRING v26; // [rsp+B8h] [rbp+38h] BYREF

  string = 0;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = v9(a2, &string);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x801,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      (const char *)(unsigned int)v10,
      v19);
  v22 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v22);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( (int)InstallQueue::_FindInstallItem(this, StringRawBuffer, &v22) >= 0 )
  {
    WindowsGetStringRawBuffer(string, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      0x807u,
      "InstallQueue::_AppendWuCategoryIdIfNotRunning",
      -1,
      L"Found already queued item for update. productId = %s",
      0,
      0);
    if ( a3 )
    {
      if ( *((_DWORD *)v22 + 70) == 1 )
      {
        WindowsGetStringRawBuffer(string, 0);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          0x811u,
          "InstallQueue::_AppendWuCategoryIdIfNotRunning",
          -1,
          L"Pausing existing update. Will be restarted after a new scan. productId = %s",
          0,
          0);
        WindowsUpdate::Internal::InstallItem::Pause(v22, 1, 0);
      }
    }
  }
  v26 = 0;
  v12 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 168LL);
  WindowsDeleteString(0);
  v26 = 0;
  if ( v12(a2, &v26) >= 0 )
  {
    std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>::find(
      a4,
      &newString,
      &v26);
    v20 = 0;
    if ( newString == *a4 )
    {
      newString = 0;
      v24[0] = v26;
      v13 = Microsoft::WRL::Wrappers::HString::Set(&newString, v24);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x842,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v13,
          v19);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
      v15 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(
              v14,
              &v20);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x843,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v15,
          v19);
      v16 = (_QWORD *)std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>::_Try_emplace<Microsoft::WRL::Wrappers::HString,>(
                        a4,
                        v24,
                        &v26);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
        *v16 + 40LL,
        &v20);
      std::vector<Microsoft::WRL::Wrappers::HString>::push_back(a5, &newString);
      WindowsDeleteString(newString);
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(
        &v20,
        newString + 10);
    }
    v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 104LL))(v20, a2);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x84B,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v17,
        v19);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
  }
  WindowsDeleteString(v26);
  v26 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v22);
  return WindowsDeleteString(string);
}

```

## disassembly

```asm
0x18005c078  mov     [rsp-28h+arg_0], rbx
0x18005c07d  mov     [rsp-28h+arg_10], rsi
0x18005c082  push    rbp
0x18005c083  push    rdi
0x18005c084  push    r12
0x18005c086  push    r14
0x18005c088  push    r15
0x18005c08a  mov     rbp, rsp
0x18005c08d  sub     rsp, 80h
0x18005c094  mov     rsi, r9
0x18005c097  mov     r15b, r8b
0x18005c09a  mov     r14, rdx
0x18005c09d  mov     rdi, rcx
0x18005c0a0  xor     r12d, r12d
0x18005c0a3  mov     [rbp+string], r12
0x18005c0a7  mov     rax, [rdx]
0x18005c0aa  mov     rbx, [rax+30h]
0x18005c0ae  xor     ecx, ecx; string
0x18005c0b0  call    cs:__imp_WindowsDeleteString
0x18005c0b6  mov     [rbp+string], r12
0x18005c0ba  lea     rdx, [rbp+string]
0x18005c0be  mov     rcx, r14
0x18005c0c1  mov     rax, rbx
0x18005c0c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c0c9  mov     rcx, [rbp+28h]; this
0x18005c0cd  test    eax, eax
0x18005c0cf  jns     short loc_18005C0E6
0x18005c0d1  mov     r9d, eax; char *
0x18005c0d4  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005c0db  mov     edx, 801h; void *
0x18005c0e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c0e6  mov     [rbp+var_20], r12
0x18005c0ea  lea     rcx, [rbp+var_20]
0x18005c0ee  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005c0f3  xor     edx, edx; length
0x18005c0f5  mov     rcx, [rbp+string]; string
0x18005c0f9  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c0ff  lea     r8, [rbp+var_20]; struct WindowsUpdate::Internal::InstallItem **
0x18005c103  mov     rdx, rax; unsigned __int16 *
0x18005c106  mov     rcx, rdi; this
0x18005c109  call    ?_FindInstallItem@InstallQueue@@AEAAJPEBGPEAPEAVInstallItem@Internal@WindowsUpdate@@@Z; InstallQueue::_FindInstallItem(ushort const *,WindowsUpdate::Internal::InstallItem * *)
0x18005c10e  lea     rdi, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005c115  test    eax, eax
0x18005c117  js      loc_18005C1C6
0x18005c11d  xor     edx, edx; length
0x18005c11f  mov     rcx, [rbp+string]; string
0x18005c123  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c129  mov     [rsp+80h+var_40], rax
0x18005c12e  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x18005c133  mov     [rsp+80h+var_50], r12; char *
0x18005c138  lea     rax, aFoundAlreadyQu; "Found already queued item for update. p"...
0x18005c13f  mov     [rsp+80h+var_58], rax; unsigned __int16 *
0x18005c144  or      ebx, 0FFFFFFFFh
0x18005c147  mov     [rsp+80h+var_60], ebx; int
0x18005c14b  lea     r9, aInstallqueueAp; "InstallQueue::_AppendWuCategoryIdIfNotR"...
0x18005c152  mov     r8d, 807h; unsigned int
0x18005c158  mov     rdx, rdi; char *
0x18005c15b  lea     ecx, [rbx+4]; unsigned int
0x18005c15e  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18005c163  test    r15b, r15b
0x18005c166  jz      short loc_18005C1C6
0x18005c168  mov     rax, [rbp+var_20]
0x18005c16c  cmp     dword ptr [rax+118h], 1
0x18005c173  jnz     short loc_18005C1C6
0x18005c175  xor     edx, edx; length
0x18005c177  mov     rcx, [rbp+string]; string
0x18005c17b  call    cs:__imp_WindowsGetStringRawBuffer
0x18005c181  mov     [rsp+80h+var_40], rax
0x18005c186  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x18005c18b  mov     [rsp+80h+var_50], r12; char *
0x18005c190  lea     rax, aPausingExistin; "Pausing existing update. Will be restar"...
0x18005c197  mov     [rsp+80h+var_58], rax; unsigned __int16 *
0x18005c19c  mov     [rsp+80h+var_60], ebx; int
0x18005c1a0  lea     r9, aInstallqueueAp; "InstallQueue::_AppendWuCategoryIdIfNotR"...
0x18005c1a7  mov     r8d, 811h; unsigned int
0x18005c1ad  mov     rdx, rdi; char *
0x18005c1b0  lea     ecx, [rbx+4]; unsigned int
0x18005c1b3  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18005c1b8  xor     r8d, r8d; HSTRING
0x18005c1bb  mov     dl, 1; bool
0x18005c1bd  mov     rcx, [rbp+var_20]; this
0x18005c1c1  call    ?Pause@InstallItem@Internal@WindowsUpdate@@QEAAJ_NPEAUHSTRING__@@@Z; WindowsUpdate::Internal::InstallItem::Pause(bool,HSTRING__ *)
0x18005c1c6  mov     [rbp+arg_8], r12
0x18005c1ca  mov     rax, [r14]
0x18005c1cd  mov     rbx, [rax+0A8h]
0x18005c1d4  xor     ecx, ecx; string
0x18005c1d6  call    cs:__imp_WindowsDeleteString
0x18005c1dc  mov     [rbp+arg_8], r12
0x18005c1e0  lea     rdx, [rbp+arg_8]
0x18005c1e4  mov     rcx, r14
0x18005c1e7  mov     rax, rbx
0x18005c1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c1ef  test    eax, eax
0x18005c1f1  js      loc_18005C2F2
0x18005c1f7  lea     r8, [rbp+arg_8]
0x18005c1fb  lea     rdx, [rbp+newString]
0x18005c1ff  mov     rcx, rsi
0x18005c202  call    ?find@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@@std@@@std@@@std@@@2@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>::find(Microsoft::WRL::Wrappers::HString const &)
0x18005c207  mov     [rbp+var_30], r12
0x18005c20b  mov     rdx, [rbp+newString]
0x18005c20f  cmp     rdx, [rsi]
0x18005c212  jnz     loc_18005C2AF
0x18005c218  mov     [rbp+newString], r12
0x18005c21c  mov     rax, [rbp+arg_8]
0x18005c220  mov     [rbp+var_10], rax
0x18005c224  lea     rdx, [rbp+var_10]; HSTRING *
0x18005c228  lea     rcx, [rbp+newString]; newString
0x18005c22c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18005c231  mov     rcx, [rbp+28h]; this
0x18005c235  test    eax, eax
0x18005c237  jns     short loc_18005C24A
0x18005c239  mov     r9d, eax; char *
0x18005c23c  mov     r8, rdi; unsigned int
0x18005c23f  mov     edx, 842h; void *
0x18005c244  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c24a  lea     rcx, [rbp+var_30]
0x18005c24e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005c253  lea     rdx, [rbp+var_30]
0x18005c257  call    ??$CreateExternalObjectVector@UIFulfillmentDataInfo@Internal@WindowsUpdate@@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@2Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0> * *)
0x18005c25c  mov     rcx, [rbp+28h]; this
0x18005c260  test    eax, eax
0x18005c262  jns     short loc_18005C275
0x18005c264  mov     r9d, eax; char *
0x18005c267  mov     r8, rdi; unsigned int
0x18005c26a  mov     edx, 843h; void *
0x18005c26f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c275  lea     r8, [rbp+arg_8]
0x18005c279  lea     rdx, [rbp+var_10]
0x18005c27d  mov     rcx, rsi
0x18005c280  call    ??$_Try_emplace@VHString@Wrappers@WRL@Microsoft@@$$V@?$map@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@@std@@@7@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@@std@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@@Z; std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>::_Try_emplace<Microsoft::WRL::Wrappers::HString,>(Microsoft::WRL::Wrappers::HString &&)
0x18005c285  mov     rcx, [rax]
0x18005c288  add     rcx, 28h ; '('
0x18005c28c  lea     rdx, [rbp+var_30]
0x18005c290  call    ??4?$ComPtr@U?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>> const &)
0x18005c295  lea     rdx, [rbp+newString]
0x18005c299  mov     rcx, [rbp+arg_20]
0x18005c29d  call    ?push_back@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@QEAAX$$QEAVHString@Wrappers@WRL@Microsoft@@@Z; std::vector<Microsoft::WRL::Wrappers::HString>::push_back(Microsoft::WRL::Wrappers::HString &&)
0x18005c2a2  nop
0x18005c2a3  mov     rcx, [rbp+newString]; string
0x18005c2a7  call    cs:__imp_WindowsDeleteString
0x18005c2ad  jmp     short loc_18005C2BC
0x18005c2af  add     rdx, 28h ; '('
0x18005c2b3  lea     rcx, [rbp+var_30]
0x18005c2b7  call    ??4?$ComPtr@U?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>> const &)
0x18005c2bc  mov     rcx, [rbp+var_30]
0x18005c2c0  mov     rax, [rcx]
0x18005c2c3  mov     rdx, r14
0x18005c2c6  mov     rax, [rax+68h]
0x18005c2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c2cf  mov     rcx, [rbp+28h]; this
0x18005c2d3  test    eax, eax
0x18005c2d5  jns     short loc_18005C2E8
0x18005c2d7  mov     r9d, eax; char *
0x18005c2da  mov     r8, rdi; unsigned int
0x18005c2dd  mov     edx, 84Bh; void *
0x18005c2e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c2e8  lea     rcx, [rbp+var_30]
0x18005c2ec  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005c2f1  nop
0x18005c2f2  mov     rcx, [rbp+arg_8]; string
0x18005c2f6  call    cs:__imp_WindowsDeleteString
0x18005c2fc  mov     [rbp+arg_8], r12
0x18005c300  lea     rcx, [rbp+var_20]
0x18005c304  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005c309  nop
0x18005c30a  mov     rcx, [rbp+string]; string
0x18005c30e  call    cs:__imp_WindowsDeleteString
0x18005c314  lea     r11, [rsp+80h+var_s0]
0x18005c31c  mov     rbx, [r11+30h]
0x18005c320  mov     rsi, [r11+40h]
0x18005c324  mov     rsp, r11
0x18005c327  pop     r15
0x18005c329  pop     r14
0x18005c32b  pop     r12
0x18005c32d  pop     rdi
0x18005c32e  pop     rbp
0x18005c32f  retn
```
