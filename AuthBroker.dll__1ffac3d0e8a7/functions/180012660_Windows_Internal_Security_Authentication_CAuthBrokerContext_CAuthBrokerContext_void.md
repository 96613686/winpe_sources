# Windows::Internal::Security::Authentication::CAuthBrokerContext::~CAuthBrokerContext(void)

- ea: `0x180012660`
- end: `0x18001275e`
- name: `??1CAuthBrokerContext@Authentication@Security@Internal@Windows@@UEAA@XZ`
- size: `254`
- prototype: `void __fastcall(Windows::Internal::Security::Authentication::CAuthBrokerContext *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800127b0`

## callees

- `0x180006060`
- `0x180006e5c`
- `0x180012640`
- `0x180012660`
- `0x18001e1d4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001270b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001270b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800126bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800126bf`
- `ntdll!RtlDeleteCriticalSection` at `0x1800126f6`
- `ntdll!RtlDeleteCriticalSection` at `0x1800126f6`

## pseudocode

```c
void __fastcall Windows::Internal::Security::Authentication::CAuthBrokerContext::~CAuthBrokerContext(
        Windows::Internal::Security::Authentication::CAuthBrokerContext *this)
{
  _AUTH_COOKIE_ENTRY *m_cookieEntry; // rsi
  unsigned int m_cookieCount; // ebp
  __int64 i; // rdi
  __int64 j; // rdi
  void *v6; // rcx

  m_cookieEntry = this->m_cookieEntry;
  this->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Security::Authentication::IAuthBroker,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Windows::Internal::Security::Authentication::IAuthBroker::IInspectable::IUnknown::lpVtbl = (Windows::Internal::Security::Authentication::CAuthBrokerContext_vtbl *)Windows::Internal::Security::Authentication::CAuthBrokerContext::`vftable'{for `Windows::Internal::Security::Authentication::IAuthBroker'};
  this->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Security::Authentication::IAuthBroker,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::IWeakReferenceSource::IUnknown::lpVtbl = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >_vtbl *)Windows::Internal::Security::Authentication::CAuthBrokerContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings>>'};
  this->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Security::Authentication::IAuthBroker,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::IAuthBrokerWindowUserInputAction::IUnknown::lpVtbl = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >_vtbl *)Windows::Internal::Security::Authentication::CAuthBrokerContext::`vftable'{for `IAuthBrokerWindowUserInputAction'};
  this->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Security::Authentication::IAuthBroker,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWABAccountsSettings>::IWABAccountsSettings::IUnknown::lpVtbl = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IWABAccountsSettings> >_vtbl *)Windows::Internal::Security::Authentication::CAuthBrokerContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IWABAccountsSettings>>'};
  if ( m_cookieEntry )
  {
    m_cookieCount = this->m_cookieCount;
    for ( i = 0; (unsigned int)i < m_cookieCount; i = (unsigned int)(i + 1) )
      FreeCookieEntry(&m_cookieEntry[i]);
    LocalFree(m_cookieEntry);
  }
  Windows::Internal::String::~String(&this->m_Password);
  Windows::Internal::String::~String(&this->m_UserName);
  Windows::Internal::String::~String(&this->m_urlString);
  if ( this->m_formCreds._fInitialized )
  {
    RtlDeleteCriticalSection(&this->m_formCreds._cs);
    for ( j = 0; j != 8; ++j )
    {
      v6 = this->m_formCreds._Threads[j];
      if ( v6 )
      {
        CloseHandle(v6);
        this->m_formCreds._Threads[j] = 0;
      }
    }
  }
  this->m_formCreds._fInitialized = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&this->m_authHost);
  Windows::Internal::String::~String(&this->m_responseData);
  Windows::Internal::String::~String(&this->m_terminateUrl);
  Windows::Internal::String::~String(&this->m_startUrl);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings>>(this);
}

```

## disassembly

```asm
0x180012660  push    rbx
0x180012662  push    rbp
0x180012663  push    rsi
0x180012664  push    rdi
0x180012665  sub     rsp, 28h
0x180012669  mov     rsi, [this+68h]
0x18001266d  lea     rax, ??_7CAuthBrokerContext@Authentication@Security@Internal@Windows@@6BIAuthBroker@1234@@; const Windows::Internal::Security::Authentication::CAuthBrokerContext::`vftable'{for `Windows::Internal::Security::Authentication::IAuthBroker'}
0x180012674  mov     [this], rax
0x180012677  lea     rax, ??_7CAuthBrokerContext@Authentication@Security@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAuthBrokerWindowUserInputAction@@U?$CloakedIid@UIWABAccountsSettings@@@23@@Details@WRL@Microsoft@@@; const Windows::Internal::Security::Authentication::CAuthBrokerContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings>>'}
0x18001267e  mov     [this+8], rax
0x180012682  lea     rax, ??_7CAuthBrokerContext@Authentication@Security@Internal@Windows@@6BIAuthBrokerWindowUserInputAction@@@; const Windows::Internal::Security::Authentication::CAuthBrokerContext::`vftable'{for `IAuthBrokerWindowUserInputAction'}
0x180012689  mov     [this+10h], rax
0x18001268d  lea     rax, ??_7CAuthBrokerContext@Authentication@Security@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIWABAccountsSettings@@@23@@Details@WRL@Microsoft@@@; const Windows::Internal::Security::Authentication::CAuthBrokerContext::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IWABAccountsSettings>>'}
0x180012694  mov     [this+18h], rax
0x180012698  mov     rbx, this
0x18001269b  test    rsi, rsi
0x18001269e  jz      short loc_1800126C5
0x1800126a0  mov     ebp, [this+60h]
0x1800126a3  xor     edi, edi
0x1800126a5  test    ebp, ebp
0x1800126a7  jz      short loc_1800126BC
0x1800126a9  lea     rdx, [rdi+rdi*4]
0x1800126ad  lea     this, [rsi+rdx*8]; cookieEntry
0x1800126b1  call    _FreeCookieEntry
0x1800126b6  inc     edi
0x1800126b8  cmp     edi, ebp
0x1800126ba  jb      short loc_1800126A9
0x1800126bc  mov     this, rsi; hMem
0x1800126bf  call    cs:__imp_LocalFree
0x1800126c5  lea     this, [rbx+108h]; this
0x1800126cc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800126d1  lea     this, [rbx+100h]; this
0x1800126d8  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800126dd  lea     this, [rbx+0F8h]; this
0x1800126e4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800126e9  cmp     byte ptr [rbx+78h], 0
0x1800126ed  jz      short loc_180012726
0x1800126ef  lea     this, [rbx+80h]; CriticalSection
0x1800126f6  call    cs:__imp_RtlDeleteCriticalSection
0x1800126fc  xor     edi, edi
0x1800126fe  mov     this, [rbx+rdi*8+0A8h]; hObject
0x180012706  test    this, this
0x180012709  jz      short loc_18001271D
0x18001270b  call    cs:__imp_CloseHandle
0x180012711  mov     qword ptr [rbx+rdi*8+0A8h], 0
0x18001271d  inc     rdi
0x180012720  cmp     rdi, 8
0x180012724  jnz     short loc_1800126FE
0x180012726  lea     this, [rbx+70h]; this
0x18001272a  mov     byte ptr [rbx+78h], 0
0x18001272e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012733  lea     this, [rbx+50h]; this
0x180012737  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001273c  lea     this, [rbx+38h]; this
0x180012740  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180012745  lea     this, [rbx+30h]; this
0x180012749  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001274e  mov     this, rbx
0x180012751  add     rsp, 28h
0x180012755  pop     rdi
0x180012756  pop     rsi
0x180012757  pop     rbp
0x180012758  pop     rbx
0x180012759  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAuthBroker@Authentication@Security@Internal@Windows@@UIAuthBrokerWindowUserInputAction@@U?$CloakedIid@UIWABAccountsSettings@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Security::Authentication::IAuthBroker,IAuthBrokerWindowUserInputAction,Microsoft::WRL::CloakedIid<IWABAccountsSettings>>(void)
```
