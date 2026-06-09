# SystemSettings::Personalization::CSlideshowSourceManager::_GetValue_PossibleFeedValues(IInspectable * *)

- ea: `0x180146edc`
- end: `0x1801472a4`
- name: `?_GetValue_PossibleFeedValues@CSlideshowSourceManager@Personalization@SystemSettings@@AEAAJPEAPEAUIInspectable@@@Z`
- size: `968`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::CSlideshowSourceManager *__hidden this, struct IInspectable **)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180144310`

## callees

- `0x18001098c`
- `0x1800109b0`
- `0x1800109d4`
- `0x180011bb0`
- `0x18001f3c8`
- `0x180020170`
- `0x1800201c4`
- `0x1800251ec`
- `0x18002b5f0`
- `0x18003cdf0`
- `0x18003d280`
- `0x18004d1ac`
- `0x18009b0b8`
- `0x180143b00`
- `0x180146edc`
- `0x180147818`
- `0x180147a50`
- `0x18019f468`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180147158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180147170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180147196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801471aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180147158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180147170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180147196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801471aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180146f76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180147269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180146f76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180147269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180146fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180146fae`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::Personalization::CSlideshowSourceManager::_GetValue_PossibleFeedValues(
        SystemSettings::Personalization::CSlideshowSourceManager *this,
        struct IInspectable **a2)
{
  struct IInspectable *v2; // r13
  unsigned int v4; // r12d
  void *v5; // rax
  __int64 v6; // rbx
  int ResourceStringById; // edi
  HSTRING v8; // rbx
  HSTRING *v9; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v11; // r9
  unsigned int v12; // edx
  SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO *v13; // rcx
  SystemSettings::Personalization::CSlideshowSingleton *v14; // rcx
  __int64 v15; // r14
  __int64 v16; // rax
  bool v17; // cf
  unsigned __int64 v18; // rax
  _QWORD *v19; // rax
  const WCHAR *v20; // rdx
  _QWORD *v21; // rdi
  unsigned int v22; // r14d
  SystemSettings::Personalization::CSlideshowSourceManager *v23; // rcx
  unsigned int v24; // eax
  LPVOID *v25; // r14
  LPVOID *v26; // r15
  unsigned int v27; // r14d
  __int64 v28; // r9
  SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO *v29; // rcx
  __int64 v31; // [rsp+30h] [rbp-30h] BYREF
  struct ILSCSlideshowFeedManager *v32; // [rsp+38h] [rbp-28h] BYREF
  struct IInspectable *v33; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v35[2]; // [rsp+50h] [rbp-10h] BYREF
  struct IInspectable *v36; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int64 v37; // [rsp+B0h] [rbp+50h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+58h] BYREF

  v36 = (struct IInspectable *)a2;
  v2 = (struct IInspectable *)a2;
  v4 = 0;
  *a2 = 0;
  v31 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v31);
  v31 = 0;
  v5 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  v37 = (unsigned __int64)v5;
  v6 = 0;
  if ( v5 )
  {
    v6 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(v5);
    v37 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(&v37);
  if ( v6 )
  {
    ResourceStringById = 0;
    v31 = v6;
  }
  else
  {
    ResourceStringById = -2147024882;
  }
  v33 = 0;
  v8 = 0;
  string = 0;
  if ( ResourceStringById >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Personalize_LockScreenSlideshowSource_FeedList_Us"
                                                         "eLocalFoldersEntry",
                           &string,
                           v9);
    if ( ResourceStringById < 0 )
    {
      v8 = string;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      v8 = string;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(StringRawBuffer, &v33);
      if ( ResourceStringById >= 0 )
      {
        LOBYTE(v11) = 1;
        ResourceStringById = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
                               v31,
                               0,
                               v33,
                               v11);
        if ( ResourceStringById >= 0 )
        {
          v13 = (SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO *)*((_QWORD *)this + 31);
          if ( v13 )
          {
            SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO::`vector deleting destructor'(
              v13,
              v12);
            *((_QWORD *)this + 31) = 0;
            *((_DWORD *)this + 64) = 0;
          }
        }
      }
    }
  }
  v32 = 0;
  if ( ResourceStringById >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    if ( (int)SystemSettings::Personalization::CSlideshowSingleton::GetFeedManager(v14, &v32) < 0 )
      goto LABEL_53;
    LODWORD(v37) = 0;
    pv = 0;
    v35[0] = 0;
    ResourceStringById = (*(__int64 (__fastcall **)(struct ILSCSlideshowFeedManager *, LPVOID *, LPVOID *, unsigned __int64 *))(*(_QWORD *)v32 + 24LL))(
                           v32,
                           &pv,
                           v35,
                           &v37);
    if ( ResourceStringById >= 0 )
    {
      v15 = (unsigned int)v37;
      v16 = 24LL * (unsigned int)v37;
      if ( !is_mul_ok((unsigned int)v37, 0x18u) )
        v16 = -1;
      v17 = __CFADD__(v16, 8);
      v18 = v16 + 8;
      if ( v17 )
        v18 = -1;
      v19 = operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
      if ( v19 )
      {
        *v19 = v15;
        v21 = v19 + 1;
        `eh vector constructor iterator'(
          v19 + 1,
          0x18u,
          (unsigned int)v15,
          std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>,
          (void (*)(void *))SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO::~FEED_LIST_APP_INFO);
      }
      else
      {
        v21 = 0;
      }
      *((_QWORD *)this + 31) = v21;
      if ( v21 )
      {
        ResourceStringById = 0;
        *((_DWORD *)this + 64) = v37;
        v22 = 0;
        while ( v22 < *((_DWORD *)this + 64) )
        {
          v20 = (const WCHAR *)*((_QWORD *)pv + v22);
          if ( !v20 )
          {
            ResourceStringById = -2147467261;
            break;
          }
          ResourceStringById = Windows::Internal::String::_InitializeHelper(
                                 (HSTRING *)(*((_QWORD *)this + 31) + 8LL + 24LL * v22),
                                 v20);
          if ( ResourceStringById >= 0 )
          {
            ResourceStringById = SystemSettings::Personalization::CSlideshowSourceManager::_SetAppName(
                                   v23,
                                   (struct SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO *)(*((_QWORD *)this + 31) + 24LL * v22++));
            if ( ResourceStringById >= 0 )
              continue;
          }
          break;
        }
      }
      else
      {
        ResourceStringById = -2147024882;
      }
      v24 = v37;
      LODWORD(string) = v37;
      v25 = (LPVOID *)v35[0];
      v26 = (LPVOID *)pv;
      if ( (_DWORD)v37 )
      {
        do
        {
          if ( v26 )
          {
            CoTaskMemFree(v26[v4]);
            v24 = (unsigned int)string;
          }
          if ( v25 )
          {
            CoTaskMemFree(v25[v4]);
            v24 = (unsigned int)string;
          }
          ++v4;
        }
        while ( v4 < v24 );
        v2 = v36;
      }
      if ( v26 )
        CoTaskMemFree(v26);
      if ( v25 )
        CoTaskMemFree(v25);
      if ( ResourceStringById >= 0 )
        ResourceStringById = SystemSettings::Personalization::CSlideshowSourceManager::_RenameDuplicateAppNames(this);
      v27 = 0;
      while ( ResourceStringById >= 0 )
      {
        if ( v27 >= *((_DWORD *)this + 64) )
          goto LABEL_53;
        v36 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(
                               *(HSTRING *)(*((_QWORD *)this + 31) + 24LL * v27),
                               &v36);
        if ( ResourceStringById >= 0 )
        {
          LOBYTE(v28) = 1;
          ResourceStringById = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
                                 v31,
                                 0,
                                 v36,
                                 v28);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        ++v27;
      }
      v29 = (SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO *)*((_QWORD *)this + 31);
      if ( v29 )
      {
        SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO::`vector deleting destructor'(
          v29,
          (unsigned int)v20);
        *((_QWORD *)this + 31) = 0;
        *((_DWORD *)this + 64) = 0;
        if ( ResourceStringById >= 0 )
LABEL_53:
          ResourceStringById = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(
                                 v31,
                                 &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                                 v2);
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  WindowsDeleteString(v8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v31);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x180146edc  mov     [rsp-38h+arg_0], rbx
0x180146ee1  mov     [rsp-38h+arg_8], rdx
0x180146ee6  push    rbp
0x180146ee7  push    rsi
0x180146ee8  push    rdi
0x180146ee9  push    r12
0x180146eeb  push    r13
0x180146eed  push    r14
0x180146eef  push    r15
0x180146ef1  mov     rbp, rsp
0x180146ef4  sub     rsp, 60h
0x180146ef8  mov     r13, rdx
0x180146efb  mov     rsi, rcx
0x180146efe  xor     r12d, r12d
0x180146f01  mov     [rdx], r12
0x180146f04  mov     [rbp+var_30], r12
0x180146f08  lea     rcx, [rbp+var_30]
0x180146f0c  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180146f11  mov     [rbp+var_30], r12
0x180146f15  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180146f1c  mov     ecx, 0B8h; unsigned __int64
0x180146f21  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180146f26  mov     [rbp+arg_10], rax
0x180146f2a  mov     ebx, r12d
0x180146f2d  test    rax, rax
0x180146f30  jz      short loc_180146F41
0x180146f32  mov     rcx, rax
0x180146f35  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::permission)
0x180146f3a  mov     rbx, rax
0x180146f3d  mov     [rbp+arg_10], r12
0x180146f41  lea     rcx, [rbp+arg_10]
0x180146f45  call    ??1?$MakeAllocator@VCBrailleTableLanguageOutputSetting@Accessibility@SystemSettings@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(void)
0x180146f4a  mov     r15d, 8007000Eh
0x180146f50  test    rbx, rbx
0x180146f53  jnz     short loc_180146F5A
0x180146f55  mov     edi, r15d
0x180146f58  jmp     short loc_180146F61
0x180146f5a  mov     edi, r12d
0x180146f5d  mov     [rbp+var_30], rbx
0x180146f61  mov     [rbp+var_20], r12
0x180146f65  mov     rbx, r12
0x180146f68  mov     [rbp+string], rbx
0x180146f6c  test    edi, edi
0x180146f6e  js      loc_180147009
0x180146f74  xor     ecx, ecx; string
0x180146f76  call    cs:__imp_WindowsDeleteString
0x180146f7d  nop     dword ptr [rax+rax+00h]
0x180146f82  mov     [rbp+string], r12
0x180146f86  lea     rdx, [rbp+string]; HSTRING *
0x180146f8a  lea     rcx, aSystemsettings_865; "SystemSettings_Personalize_LockScreenSl"...
0x180146f91  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180146f96  mov     edi, eax
0x180146f98  test    eax, eax
0x180146f9a  js      short loc_180147005
0x180146f9c  lea     rcx, [rbp+var_20]
0x180146fa0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180146fa5  xor     edx, edx; length
0x180146fa7  mov     rbx, [rbp+string]
0x180146fab  mov     rcx, rbx; string
0x180146fae  call    cs:__imp_WindowsGetStringRawBuffer
0x180146fb5  nop     dword ptr [rax+rax+00h]
0x180146fba  lea     rdx, [rbp+var_20]; struct IInspectable **
0x180146fbe  mov     rcx, rax; unsigned __int16 *
0x180146fc1  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180146fc6  mov     edi, eax
0x180146fc8  test    eax, eax
0x180146fca  js      short loc_180147009
0x180146fcc  mov     r9b, 1
0x180146fcf  mov     r8, [rbp+var_20]
0x180146fd3  xor     edx, edx
0x180146fd5  mov     rcx, [rbp+var_30]
0x180146fd9  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x180146fde  mov     edi, eax
0x180146fe0  test    eax, eax
0x180146fe2  js      short loc_180147009
0x180146fe4  mov     rcx, [rsi+0F8h]; this
0x180146feb  test    rcx, rcx
0x180146fee  jz      short loc_180147009
0x180146ff0  call    ??_EFEED_LIST_APP_INFO@CSlideshowSourceManager@Personalization@SystemSettings@@QEAAPEAXI@Z; SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO::`vector deleting destructor'(uint)
0x180146ff5  mov     [rsi+0F8h], r12
0x180146ffc  mov     [rsi+100h], r12d
0x180147003  jmp     short loc_180147009
0x180147005  mov     rbx, [rbp+string]
0x180147009  mov     [rbp+var_28], r12
0x18014700d  test    edi, edi
0x18014700f  js      loc_18014725C
0x180147015  lea     rcx, [rbp+var_28]
0x180147019  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014701e  lea     rdx, [rbp+var_28]; struct ILSCSlideshowFeedManager **
0x180147022  call    ?GetFeedManager@CSlideshowSingleton@Personalization@SystemSettings@@QEAAJPEAPEAUILSCSlideshowFeedManager@@@Z; SystemSettings::Personalization::CSlideshowSingleton::GetFeedManager(ILSCSlideshowFeedManager * *)
0x180147027  test    eax, eax
0x180147029  js      loc_180147247
0x18014702f  mov     dword ptr [rbp+arg_10], r12d
0x180147033  mov     [rbp+pv], r12
0x180147037  mov     [rbp+var_10], r12
0x18014703b  mov     rcx, [rbp+var_28]
0x18014703f  mov     rax, [rcx]
0x180147042  lea     r9, [rbp+arg_10]
0x180147046  lea     r8, [rbp+var_10]
0x18014704a  lea     rdx, [rbp+pv]
0x18014704e  mov     rax, [rax+18h]
0x180147052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147057  mov     edi, eax
0x180147059  test    eax, eax
0x18014705b  js      loc_18014725C
0x180147061  mov     r14d, dword ptr [rbp+arg_10]
0x180147065  mov     eax, 18h
0x18014706a  mul     r14
0x18014706d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180147074  cmovb   rax, rcx
0x180147078  add     rax, 8
0x18014707c  cmovb   rax, rcx
0x180147080  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180147087  mov     rcx, rax; unsigned __int64
0x18014708a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18014708f  test    rax, rax
0x180147092  jz      short loc_1801470C0
0x180147094  mov     [rax], r14
0x180147097  lea     rdi, [rax+8]
0x18014709b  lea     rax, ??1FEED_LIST_APP_INFO@CSlideshowSourceManager@Personalization@SystemSettings@@QEAA@XZ; SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO::~FEED_LIST_APP_INFO(void)
0x1801470a2  mov     [rsp+60h+var_40], rax; void (*)(void *)
0x1801470a7  lea     r9, ??0?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x1801470ae  mov     r8d, r14d; unsigned __int64
0x1801470b1  mov     edx, 18h; unsigned __int64
0x1801470b6  mov     rcx, rdi; void *
0x1801470b9  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1801470be  jmp     short loc_1801470C3
0x1801470c0  mov     rdi, r12
0x1801470c3  mov     [rsi+0F8h], rdi
0x1801470ca  test    rdi, rdi
0x1801470cd  jz      short loc_180147137
0x1801470cf  mov     edi, r12d
0x1801470d2  mov     eax, dword ptr [rbp+arg_10]
0x1801470d5  mov     [rsi+100h], eax
0x1801470db  mov     r14d, r12d
0x1801470de  cmp     r14d, [rsi+100h]
0x1801470e5  jnb     short loc_18014713A
0x1801470e7  mov     ecx, r14d
0x1801470ea  mov     rax, [rbp+pv]
0x1801470ee  mov     rdx, [rax+rcx*8]; sourceString
0x1801470f2  test    rdx, rdx
0x1801470f5  jz      short loc_180147130
0x1801470f7  lea     r15, [rcx+rcx*2]
0x1801470fb  mov     rcx, [rsi+0F8h]
0x180147102  add     rcx, 8
0x180147106  lea     rcx, [rcx+r15*8]; this
0x18014710a  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18014710f  mov     edi, eax
0x180147111  test    eax, eax
0x180147113  js      short loc_18014713A
0x180147115  mov     rax, [rsi+0F8h]
0x18014711c  lea     rdx, [rax+r15*8]; struct SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO *
0x180147120  call    ?_SetAppName@CSlideshowSourceManager@Personalization@SystemSettings@@AEAAJPEAUFEED_LIST_APP_INFO@123@@Z; SystemSettings::Personalization::CSlideshowSourceManager::_SetAppName(SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO *)
0x180147125  mov     edi, eax
0x180147127  inc     r14d
0x18014712a  test    eax, eax
0x18014712c  jns     short loc_1801470DE
0x18014712e  jmp     short loc_18014713A
0x180147130  mov     edi, 80004003h
0x180147135  jmp     short loc_18014713A
0x180147137  mov     edi, r15d
0x18014713a  mov     eax, dword ptr [rbp+arg_10]
0x18014713d  mov     dword ptr [rbp+string], eax
0x180147140  mov     r14, [rbp+var_10]
0x180147144  mov     r15, [rbp+pv]
0x180147148  test    eax, eax
0x18014714a  jz      short loc_18014718B
0x18014714c  mov     r13d, r12d
0x18014714f  test    r15, r15
0x180147152  jz      short loc_180147167
0x180147154  mov     rcx, [r15+r13*8]; pv
0x180147158  call    cs:__imp_CoTaskMemFree
0x18014715f  nop     dword ptr [rax+rax+00h]
0x180147164  mov     eax, dword ptr [rbp+string]
0x180147167  test    r14, r14
0x18014716a  jz      short loc_18014717F
0x18014716c  mov     rcx, [r14+r13*8]; pv
0x180147170  call    cs:__imp_CoTaskMemFree
0x180147177  nop     dword ptr [rax+rax+00h]
0x18014717c  mov     eax, dword ptr [rbp+string]
0x18014717f  inc     r12d
0x180147182  cmp     r12d, eax
0x180147185  jb      short loc_18014714C
0x180147187  mov     r13, [rbp+arg_8]
0x18014718b  xor     r12d, r12d
0x18014718e  test    r15, r15
0x180147191  jz      short loc_1801471A2
0x180147193  mov     rcx, r15; pv
0x180147196  call    cs:__imp_CoTaskMemFree
0x18014719d  nop     dword ptr [rax+rax+00h]
0x1801471a2  test    r14, r14
0x1801471a5  jz      short loc_1801471B6
0x1801471a7  mov     rcx, r14; pv
0x1801471aa  call    cs:__imp_CoTaskMemFree
0x1801471b1  nop     dword ptr [rax+rax+00h]
0x1801471b6  test    edi, edi
0x1801471b8  js      short loc_1801471C4
0x1801471ba  mov     rcx, rsi; this
0x1801471bd  call    ?_RenameDuplicateAppNames@CSlideshowSourceManager@Personalization@SystemSettings@@AEAAJXZ; SystemSettings::Personalization::CSlideshowSourceManager::_RenameDuplicateAppNames(void)
0x1801471c2  mov     edi, eax
0x1801471c4  mov     r14d, r12d
0x1801471c7  jmp     short loc_180147220
0x1801471c9  cmp     r14d, [rsi+100h]
0x1801471d0  jnb     short loc_180147247
0x1801471d2  mov     [rbp+arg_8], r12
0x1801471d6  lea     rcx, [rbp+arg_8]
0x1801471da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801471df  mov     eax, r14d
0x1801471e2  lea     r8, [rax+rax*2]
0x1801471e6  mov     rcx, [rsi+0F8h]
0x1801471ed  lea     rdx, [rbp+arg_8]; struct IInspectable **
0x1801471f1  mov     rcx, [rcx+r8*8]; HSTRING
0x1801471f5  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1801471fa  mov     edi, eax
0x1801471fc  test    eax, eax
0x1801471fe  js      short loc_180147214
0x180147200  mov     r9b, 1
0x180147203  mov     r8, [rbp+arg_8]
0x180147207  xor     edx, edx
0x180147209  mov     rcx, [rbp+var_30]
0x18014720d  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x180147212  mov     edi, eax
0x180147214  lea     rcx, [rbp+arg_8]
0x180147218  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014721d  inc     r14d
0x180147220  test    edi, edi
0x180147222  jns     short loc_1801471C9
0x180147224  mov     rcx, [rsi+0F8h]; this
0x18014722b  test    rcx, rcx
0x18014722e  jz      short loc_18014725C
0x180147230  call    ??_EFEED_LIST_APP_INFO@CSlideshowSourceManager@Personalization@SystemSettings@@QEAAPEAXI@Z; SystemSettings::Personalization::CSlideshowSourceManager::FEED_LIST_APP_INFO::`vector deleting destructor'(uint)
0x180147235  mov     [rsi+0F8h], r12
0x18014723c  mov     [rsi+100h], r12d
0x180147243  test    edi, edi
0x180147245  js      short loc_18014725C
0x180147247  mov     r8, r13
0x18014724a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180147251  mov     rcx, [rbp+var_30]
0x180147255  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x18014725a  mov     edi, eax
0x18014725c  lea     rcx, [rbp+var_28]
0x180147260  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180147265  nop
0x180147266  mov     rcx, rbx; string
0x180147269  call    cs:__imp_WindowsDeleteString
0x180147270  nop     dword ptr [rax+rax+00h]
0x180147275  nop
0x180147276  lea     rcx, [rbp+var_20]
0x18014727a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014727f  nop
0x180147280  lea     rcx, [rbp+var_30]
0x180147284  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180147289  mov     eax, edi
0x18014728b  mov     rbx, [rsp+60h+arg_0]
0x180147293  add     rsp, 60h
0x180147297  pop     r15
0x180147299  pop     r14
0x18014729b  pop     r13
0x18014729d  pop     r12
0x18014729f  pop     rdi
0x1801472a0  pop     rsi
0x1801472a1  pop     rbp
0x1801472a2  retn
```
