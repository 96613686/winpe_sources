# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::Insert(HSTRING__ *,IInspectable *,uchar *)

- ea: `0x18000e950`
- end: `0x18000ef74`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z`
- size: `1572`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *this, HSTRING__ *key, IInspectable *value, unsigned __int8 *replaced)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000cee0`
- `0x18000cfa0`
- `0x18000daa0`
- `0x18000dbd0`
- `0x18000e2c0`
- `0x18000e8d0`
- `0x18000e950`
- `0x18000ef7c`
- `0x18002086c`
- `0x1800222e0`
- `0x1800254e8`
- `0x180026620`
- `0x18002d3d4`
- `0x1800415ee`
- `0x180042010`

## import_xrefs

- `msvcrt!malloc` at `0x18000ecec`
- `msvcrt!malloc` at `0x18000ecec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eb0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eb0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e9fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e9fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000e9b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000ee80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000e9b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000ee80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ea6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ebe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ea6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ebe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000eb7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000eb7c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000eeda`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000eeda`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::Insert(
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *this,
        HSTRING key,
        IInspectable *value,
        Windows::Foundation::Collections::Internal::MapChangedEventArgs<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > *replaced)
{
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *v6; // r15
  int v7; // r14d
  HRESULT v8; // r12d
  IInspectable *m_value; // rsi
  XWinRT::ComLock *p_comLock; // rdi
  bool v11; // zf
  int listeners; // ecx
  HSTRING__ *p_reentrancyGuard; // r13
  int reentrancyGuard; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned int v16; // r15d
  unsigned int v17; // r14d
  XWinRT::StringEquals *i; // rcx
  int v19; // edx
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *v20; // r8
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode **m_ppBins; // r13
  volatile int *p_m_nBins; // r12
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *j; // r13
  Windows::Foundation::Collections::Internal::MapChangedEventArgs<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > *ptr; // r14
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *> > *v25; // rbx
  int v26; // eax
  PCWSTR v28; // rax
  XWinRT::StringEquals *v29; // rcx
  unsigned __int64 v30; // rdx
  int v31; // ecx
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *v32; // r9
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode **v33; // r14
  __int64 v34; // rdx
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *k; // r14
  unsigned __int64 v36; // r13
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> > *p_hashMap; // r12
  HSTRING__ *v38; // rax
  unsigned __int64 m_nElements; // rdx
  unsigned int m_nBlockSize; // r14d
  unsigned __int64 v41; // rax
  XWinRT::XPlex *v42; // rax
  int v43; // r8d
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *v44; // rdx
  unsigned __int64 v45; // r14
  unsigned __int64 v46; // rax
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode **v47; // rax
  HSTRING__ *m_key; // rdx
  HSTRING__ *v49; // rdx
  unsigned int v50; // eax
  Windows::Foundation::Collections::Internal::MapChangedEventArgs<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > *v51; // rdi
  XWinRT::SecureVersionTag::Tag *v52; // rax
  XWinRT::SecureVersionTag::Tag *v53; // r14
  bool fEquals[4]; // [rsp+28h] [rbp-19h] BYREF
  UINT32 length; // [rsp+2Ch] [rbp-15h] BYREF
  XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > sNewKey; // [rsp+30h] [rbp-11h]
  XWinRT::detail::ReentrancyGuard<1> guard; // [rsp+38h] [rbp-9h] BYREF
  HSTRING__ *v58; // [rsp+48h] [rbp+7h]
  Microsoft::WRL::EventSource<Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2> >::InvokeAll::__l2::<lambda_555ece05eb40144c1e2673634c4732a3> initializedElement; // [rsp+58h] [rbp+17h] BYREF
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *v60; // [rsp+A8h] [rbp+67h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+6Fh]
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::MapChangedEventArgs<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > result; // [rsp+C0h] [rbp+7Fh] BYREF

  result.ptr_ = replaced;
  string = key;
  v60 = this;
  LOBYTE(replaced->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *>,IWeakReferenceSource>::Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *>::Windows::Foundation::Collections::IMapChangedEventArgs_impl<HSTRING__ *>::IInspectable::IUnknown::__vftable) = 0;
  v6 = this;
  if ( !this->_initialized )
    RoOriginateError(2147549183LL, 0);
  v7 = -2147483627;
  sNewKey._value = 0;
  LODWORD(guard._pGuard) = -2147483627;
  *(_QWORD *)&guard._hr = 0;
  v8 = WindowsDuplicateString(key, (HSTRING *)&guard);
  if ( v8 >= 0 )
  {
    if ( value )
      value->AddRef(value);
    m_value = 0;
    p_comLock = &v6->_comLock;
    v11 = v6->_comLock.kind == Kind_StaReentrancy;
    initializedElement.<args_0> = 0;
    if ( v11 )
    {
      if ( !v6->_comLock.asSrl._val )
        v6->_comLock.asSrl._val = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)&v6->_comLock.8);
    }
    listeners = v6->_listeners;
    p_reentrancyGuard = (HSTRING__ *)&v6->_reentrancyGuard;
    reentrancyGuard = v6->_reentrancyGuard;
    sNewKey._value = (HSTRING__ *)&v6->_reentrancyGuard;
    if ( reentrancyGuard || (v7 = 0, listeners <= 0) )
    {
      p_reentrancyGuard = 0;
      sNewKey._value = 0;
    }
    else
    {
      *(_DWORD *)p_reentrancyGuard = 1;
    }
    v58 = p_reentrancyGuard;
    LODWORD(guard._pGuard) = v7;
    v8 = XWinRT::detail::ReentrancyGuard<1>::hr((XWinRT::detail::ReentrancyGuard<1> *)&guard._pGuard);
    if ( v8 < 0 )
      goto LABEL_24;
    if ( v6->_versionManager._pTag->_iRefCount > 1 )
    {
      v52 = (XWinRT::SecureVersionTag::Tag *)operator new(4u, &std::nothrow);
      v53 = v52;
      if ( v52 )
      {
        v52->_iRefCount = 1;
        XWinRT::SecureVersionTag::Tag::Release(v6->_versionManager._pTag);
        v6->_versionManager._pTag = v53;
      }
    }
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&guard._hr, &length);
    v16 = -2128831035;
    v17 = -2128831035;
    for ( i = 0; (unsigned __int64)i < 2 * (unsigned __int64)length; v17 = 16777619 * (v17 ^ v19) )
      v19 = (unsigned __int8)(i++)[(_QWORD)StringRawBuffer];
    v20 = v60;
    m_ppBins = v60->_hashMap.m_ppBins;
    p_m_nBins = (volatile int *)&v60->_hashMap.m_nBins;
    guard._pGuard = (volatile int *)&v60->_hashMap.m_nBins;
    if ( m_ppBins )
    {
      for ( j = m_ppBins[v17 % *p_m_nBins]; ; j = j->m_pNext )
      {
        if ( !j )
        {
          p_m_nBins = guard._pGuard;
          v20 = v60;
          goto LABEL_43;
        }
        if ( j->m_nHash == v17 )
        {
          m_key = j->m_key;
          fEquals[0] = 0;
          v8 = XWinRT::StringEquals::operator()(i, m_key, *(HSTRING__ **)&guard._hr, fEquals);
          if ( v8 < 0 )
            goto LABEL_73;
          if ( fEquals[0] )
            break;
        }
      }
      m_value = j->m_value;
      XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>((Windows::Storage::IApplicationDataContainer **)&initializedElement);
      ptr = result.ptr_;
      v6 = v60;
      j->m_value = value;
      value = 0;
      p_reentrancyGuard = sNewKey._value;
      v8 = 0;
      LOBYTE(ptr->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *>,IWeakReferenceSource>::Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *>::Windows::Foundation::Collections::IMapChangedEventArgs_impl<HSTRING__ *>::IInspectable::IUnknown::__vftable) = 1;
      goto LABEL_25;
    }
LABEL_43:
    if ( v20->_hashMap.m_nElements == 0x7FFFFFFF )
    {
      v8 = -2147024882;
LABEL_73:
      v6 = v60;
      goto LABEL_23;
    }
    length = 0;
    v28 = WindowsGetStringRawBuffer(*(HSTRING *)&guard._hr, &length);
    v30 = 0;
    if ( 2LL * length )
    {
      do
      {
        v31 = *((unsigned __int8 *)v28 + v30++);
        v29 = (XWinRT::StringEquals *)(v16 ^ v31);
        v16 = 16777619 * (_DWORD)v29;
      }
      while ( v30 < 2 * (unsigned __int64)length );
      v32 = v60;
      p_m_nBins = (volatile int *)&v60->_hashMap.m_nBins;
      guard._pGuard = (volatile int *)&v60->_hashMap.m_nBins;
    }
    else
    {
      v32 = v60;
    }
    v33 = v32->_hashMap.m_ppBins;
    v34 = v16 % *p_m_nBins;
    initializedElement.<args_0> = (Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *> **)(unsigned int)v34;
    if ( v33 )
    {
      for ( k = v33[v34]; ; k = k->m_pNext )
      {
        if ( !k )
        {
          v36 = (unsigned __int64)initializedElement.<args_0>;
          p_m_nBins = guard._pGuard;
          v32 = v60;
          goto LABEL_53;
        }
        if ( k->m_nHash == v16 )
        {
          v49 = k->m_key;
          fEquals[0] = 0;
          v8 = XWinRT::StringEquals::operator()(v29, v49, *(HSTRING__ **)&guard._hr, fEquals);
          if ( v8 < 0 )
            goto LABEL_73;
          if ( fEquals[0] )
            break;
        }
      }
      v6 = v60;
      goto LABEL_57;
    }
    v36 = (unsigned int)v34;
LABEL_53:
    guard._pGuard = (volatile int *)&v32->_hashMap;
    if ( v32->_hashMap.m_ppBins )
    {
      p_hashMap = &v32->_hashMap;
    }
    else
    {
      v45 = *(unsigned int *)p_m_nBins;
      v46 = 8 * v45;
      if ( !is_mul_ok(v45, 8u) )
        v46 = -1;
      v47 = (XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode **)operator new[](v46, &std::nothrow);
      v60->_hashMap.m_ppBins = v47;
      if ( !v47 )
        goto LABEL_20;
      if ( (unsigned int)v45 > 0x1FFFFFFF )
        goto LABEL_64;
      memset_0(v47, 0, 8 * v45);
      *p_m_nBins = v45;
      p_hashMap = (XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> > *)guard._pGuard;
      XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::UpdateRehashThresholds((XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> > *)guard._pGuard);
      v32 = v60;
    }
    k = v32->_hashMap.m_pFree;
    if ( k )
      goto LABEL_56;
    m_nBlockSize = v32->_hashMap.m_nBlockSize;
    v41 = 32LL * m_nBlockSize;
    if ( is_mul_ok(m_nBlockSize, 0x20u) && v41 + 8 >= v41 )
    {
      v42 = (XWinRT::XPlex *)malloc(v41 + 8);
      if ( v42 )
      {
        v32 = v60;
        v43 = m_nBlockSize - 1;
        v44 = (XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *)&v42[4 * m_nBlockSize - 3];
        v42->pNext = v60->_hashMap.m_pBlocks;
        v32->_hashMap.m_pBlocks = v42;
        if ( (int)(m_nBlockSize - 1) >= 0 )
        {
          do
          {
            k = v44;
            v44->m_pNext = v32->_hashMap.m_pFree;
            v32->_hashMap.m_pFree = v44--;
            --v43;
          }
          while ( v43 >= 0 );
          v36 = LODWORD(initializedElement.<args_0>);
          if ( k )
          {
LABEL_56:
            v32->_hashMap.m_pFree = k->m_pNext;
            v38 = *(HSTRING__ **)&guard._hr;
            k->m_nHash = v16;
            v6 = v60;
            k->m_key = v38;
            ++v6->_hashMap.m_nElements;
            k->m_pNext = v6->_hashMap.m_ppBins[v36];
            v6->_hashMap.m_ppBins[v36] = k;
            m_nElements = v6->_hashMap.m_nElements;
            if ( m_nElements <= v6->_hashMap.m_nHiRehashThreshold
              || v6->_hashMap.m_nLockCount
              || (v50 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::PickSize(
                          p_hashMap,
                          m_nElements),
                  v8 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Rehash(
                         p_hashMap,
                         v50),
                  v8 >= 0) )
            {
LABEL_57:
              k->m_value = value;
              v8 = 0;
              *(_QWORD *)&guard._hr = 0;
              value = 0;
              goto LABEL_23;
            }
LABEL_21:
            v6 = v60;
LABEL_23:
            p_reentrancyGuard = sNewKey._value;
LABEL_24:
            ptr = result.ptr_;
LABEL_25:
            if ( p_comLock )
            {
              if ( p_comLock->kind == Kind_StaReentrancy )
                p_comLock->asSrl._val += 0x10000000;
              else
                ReleaseSRWLockExclusive((PSRWLOCK)&p_comLock->8);
            }
            if ( m_value )
              m_value->Release(m_value);
            if ( value )
              value->Release(value);
            if ( v8 >= 0 )
            {
              v25 = &v6->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *> >;
              if ( !v6 )
                v25 = 0;
              v26 = 3;
              if ( !LOBYTE(ptr->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *>,IWeakReferenceSource>::Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *>::Windows::Foundation::Collections::IMapChangedEventArgs_impl<HSTRING__ *>::IInspectable::IUnknown::__vftable) )
                v26 = 1;
              v8 = 0;
              LODWORD(v60) = v26;
              if ( p_reentrancyGuard )
              {
                Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::MapChangedEventArgs<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>,enum Windows::Foundation::Collections::CollectionChange &>(
                  &result,
                  (Windows::Foundation::Collections::CollectionChange *)&v60);
                v51 = result.ptr_;
                if ( result.ptr_ )
                {
                  v8 = WindowsDuplicateString(string, &result.ptr_->_key);
                  if ( v8 >= 0 )
                  {
                    result.ptr_ = v51;
                    initializedElement.<args_0> = (Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *> **)&v60;
                    v60 = (Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *)v25;
                    initializedElement.<args_1> = (Windows::Foundation::Collections::Internal::MapChangedEventArgs<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > **)&result;
                    Microsoft::WRL::EventSource<Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::DoInvoke<_lambda_555ece05eb40144c1e2673634c4732a3_>(
                      &v6->_evtMapChanged,
                      &initializedElement);
                  }
                  if ( v51 )
                    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::Release((Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> > *)v51);
                }
              }
            }
            goto LABEL_38;
          }
        }
LABEL_64:
        v8 = -2147418113;
        goto LABEL_21;
      }
    }
LABEL_20:
    v8 = -2147024882;
    goto LABEL_21;
  }
LABEL_38:
  WindowsDeleteString(*(HSTRING *)&guard._hr);
  *(_QWORD *)&guard._hr = 0;
  if ( sNewKey._value )
    *(_DWORD *)sNewKey._value = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000e950  mov     rax, rsp
0x18000e953  mov     [rax+20h], replaced
0x18000e957  mov     [rax+10h], key
0x18000e95b  mov     [rax+8], this
0x18000e95f  push    rbp
0x18000e960  push    r12
0x18000e962  lea     rbp, [rax-5Fh]
0x18000e966  sub     rsp, 88h
0x18000e96d  mov     [rax+18h], rbx
0x18000e971  mov     rbx, value
0x18000e974  mov     [rax-20h], rdi
0x18000e978  mov     rdi, key
0x18000e97b  mov     [rax-30h], r14
0x18000e97f  mov     byte ptr [replaced], 0
0x18000e983  cmp     byte ptr [this+0A0h], 0
0x18000e98a  mov     [rax-38h], r15
0x18000e98e  mov     r15, this
0x18000e991  jz      loc_18000EED3
0x18000e997  xor     eax, eax
0x18000e999  lea     key, [rbp+57h+guard]; newString
0x18000e99d  mov     r14d, 80000015h
0x18000e9a3  mov     [rbp+57h+sNewKey._value], rax
0x18000e9a7  mov     this, rdi; string
0x18000e9aa  mov     dword ptr [rbp+57h+guard._pGuard], r14d
0x18000e9ae  mov     qword ptr [rbp+57h+guard._hr], rax
0x18000e9b2  call    cs:__imp_WindowsDuplicateString
0x18000e9b8  mov     r12d, eax
0x18000e9bb  test    eax, eax
0x18000e9bd  js      loc_18000EB78
0x18000e9c3  mov     [rsp+80h], rsi
0x18000e9cb  mov     [rsp+90h+var_20], r13
0x18000e9d0  test    rbx, rbx
0x18000e9d3  jz      short loc_18000E9E4
0x18000e9d5  mov     rax, [rbx]
0x18000e9d8  mov     this, rbx
0x18000e9db  mov     rax, [rax+8]
0x18000e9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9e4  xor     esi, esi
0x18000e9e6  lea     rdi, [r15+88h]
0x18000e9ed  cmp     dword ptr [rdi], 1
0x18000e9f0  mov     [rbp+57h+initializedElement], rsi
0x18000e9f4  jz      loc_18000EDBD
0x18000e9fa  lea     this, [rdi+8]; SRWLock
0x18000e9fe  call    cs:__imp_AcquireSRWLockExclusive
0x18000ea04  mov     ecx, [r15+0C0h]
0x18000ea0b  lea     r13, [r15+0C4h]
0x18000ea12  mov     eax, [r13+0]
0x18000ea16  mov     [rbp+57h+sNewKey._value], r13
0x18000ea1a  test    eax, eax
0x18000ea1c  jnz     short loc_18000EA29
0x18000ea1e  xor     r14d, r14d
0x18000ea21  test    ecx, ecx
0x18000ea23  jg      loc_18000EEE5
0x18000ea29  xor     r13d, r13d
0x18000ea2c  mov     [rbp+57h+sNewKey._value], r13
0x18000ea30  lea     this, [rbp+57h+guard._pGuard]; this
0x18000ea34  mov     [rbp+57h+var_50], r13
0x18000ea38  mov     dword ptr [rbp+57h+guard._pGuard], r14d
0x18000ea3c  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x18000ea41  mov     r12d, eax
0x18000ea44  test    eax, eax
0x18000ea46  js      loc_18000EAF5
0x18000ea4c  mov     rax, [r15+98h]
0x18000ea53  mov     ecx, [rax]
0x18000ea55  cmp     ecx, 1
0x18000ea58  jg      loc_18000EEF2
0x18000ea5e  xor     ecx, ecx
0x18000ea60  lea     key, [rbp+57h+length]; length
0x18000ea64  mov     [rbp+57h+length], ecx
0x18000ea67  mov     this, qword ptr [rbp+57h+guard._hr]; string
0x18000ea6b  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ea71  mov     r8d, [rbp+57h+length]
0x18000ea75  mov     r15d, 811C9DC5h
0x18000ea7b  mov     r14d, r15d
0x18000ea7e  mov     this, rsi
0x18000ea81  add     value, value
0x18000ea84  jz      short loc_18000EA9C
0x18000ea86  movzx   edx, byte ptr [rax+this]
0x18000ea8a  inc     this; this
0x18000ea8d  xor     edx, r14d
0x18000ea90  imul    r14d, edx, 1000193h
0x18000ea97  cmp     this, value
0x18000ea9a  jb      short loc_18000EA86
0x18000ea9c  mov     value, [rbp+57h+arg_0]
0x18000eaa0  mov     r13, [value+38h]
0x18000eaa4  lea     r12, [value+48h]
0x18000eaa8  mov     [rbp+57h+guard._pGuard], r12
0x18000eaac  test    r13, r13
0x18000eaaf  jz      loc_18000EBCE
0x18000eab5  xor     edx, edx
0x18000eab7  mov     eax, r14d
0x18000eaba  div     dword ptr [r12]
0x18000eabe  mov     r13, [r13+key*8+0]
0x18000eac3  test    r13, r13
0x18000eac6  jz      loc_18000EBC6
0x18000eacc  cmp     [r13+18h], r14d
0x18000ead0  jz      loc_18000EDD2
0x18000ead6  mov     r13, [r13+10h]
0x18000eada  jmp     short loc_18000EAC3
0x18000eadc  mov     r12d, 8007000Eh
0x18000eae2  mov     r15, [rbp+57h+arg_0]
0x18000eae6  test    r12d, r12d
0x18000eae9  js      short loc_18000EAF1
0x18000eaeb  mov     qword ptr [rbp+57h+guard._hr], rsi
0x18000eaef  xor     ebx, ebx
0x18000eaf1  mov     r13, [rbp+57h+sNewKey._value]
0x18000eaf5  mov     r14, [rbp+57h+result.ptr_]
0x18000eaf9  test    rdi, rdi
0x18000eafc  jz      short loc_18000EB11
0x18000eafe  cmp     dword ptr [rdi], 1
0x18000eb01  jz      loc_18000EBBA
0x18000eb07  lea     this, [rdi+8]; SRWLock
0x18000eb0b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000eb11  test    rsi, rsi
0x18000eb14  jz      short loc_18000EB25
0x18000eb16  mov     rax, [rsi]
0x18000eb19  mov     this, rsi
0x18000eb1c  mov     rax, [rax+10h]
0x18000eb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb25  mov     rsi, [rsp+80h]
0x18000eb2d  test    rbx, rbx
0x18000eb30  jz      short loc_18000EB41
0x18000eb32  mov     rax, [rbx]
0x18000eb35  mov     this, rbx
0x18000eb38  mov     rax, [rax+10h]
0x18000eb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb41  test    r12d, r12d
0x18000eb44  js      short loc_18000EB73
0x18000eb46  xor     eax, eax
0x18000eb48  lea     rbx, [r15+18h]
0x18000eb4c  test    r15, r15
0x18000eb4f  mov     ecx, 1
0x18000eb54  cmovz   rbx, rax
0x18000eb58  cmp     byte ptr [r14], 0
0x18000eb5c  mov     eax, 3
0x18000eb61  cmovz   eax, ecx
0x18000eb64  xor     r12d, r12d
0x18000eb67  mov     dword ptr [rbp+57h+arg_0], eax
0x18000eb6a  test    r13, r13
0x18000eb6d  jnz     loc_18000EE5E
0x18000eb73  mov     r13, [rsp+90h+var_20]
0x18000eb78  mov     this, qword ptr [rbp+57h+guard._hr]; string
0x18000eb7c  call    cs:__imp_WindowsDeleteString
0x18000eb82  mov     rax, [rbp+57h+sNewKey._value]
0x18000eb86  xor     ecx, ecx
0x18000eb88  mov     r15, [rsp+90h+var_30]
0x18000eb8d  mov     r14, [rsp+90h+var_28]
0x18000eb92  mov     rdi, [rsp+90h+var_18]
0x18000eb97  mov     rbx, [rsp+90h+arg_10]
0x18000eb9f  mov     qword ptr [rbp+57h+guard._hr], this
0x18000eba3  test    rax, rax
0x18000eba6  jnz     loc_18000EF6D
0x18000ebac  mov     eax, r12d
0x18000ebaf  add     rsp, 88h
0x18000ebb6  pop     r12
0x18000ebb8  pop     rbp
0x18000ebb9  retn
0x18000ebba  add     dword ptr [rdi+8], 10000000h
0x18000ebc1  jmp     loc_18000EB11
0x18000ebc6  mov     r12, [rbp+57h+guard._pGuard]
0x18000ebca  mov     value, [rbp+57h+arg_0]
0x18000ebce  cmp     qword ptr [value+40h], 7FFFFFFFh
0x18000ebd6  jz      loc_18000EF62
0x18000ebdc  mov     this, qword ptr [rbp+57h+guard._hr]; string
0x18000ebe0  lea     key, [rbp+57h+length]; length
0x18000ebe4  mov     [rbp+57h+length], esi
0x18000ebe7  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ebed  mov     r8d, [rbp+57h+length]
0x18000ebf1  mov     key, rsi
0x18000ebf4  add     value, value
0x18000ebf7  jz      loc_18000EE55
0x18000ebfd  nop     dword ptr [rax]
0x18000ec00  movzx   ecx, byte ptr [rax+key]
0x18000ec04  inc     key
0x18000ec07  xor     ecx, r15d; this
0x18000ec0a  imul    r15d, ecx, 1000193h
0x18000ec11  cmp     key, value
0x18000ec14  jb      short loc_18000EC00
0x18000ec16  mov     replaced, [rbp+57h+arg_0]
0x18000ec1a  lea     r12, [replaced+48h]
0x18000ec1e  mov     [rbp+57h+guard._pGuard], r12
0x18000ec22  mov     r14, [replaced+38h]
0x18000ec26  xor     edx, edx
0x18000ec28  mov     eax, r15d
0x18000ec2b  div     dword ptr [r12]
0x18000ec2f  mov     eax, edx
0x18000ec31  mov     [rbp+57h+initializedElement], rax
0x18000ec35  test    r14, r14
0x18000ec38  jz      loc_18000EECB
0x18000ec3e  mov     r14, [r14+key*8]
0x18000ec42  test    r14, r14
0x18000ec45  jz      short loc_18000EC57
0x18000ec47  cmp     [r14+18h], r15d
0x18000ec4b  jz      loc_18000EDFB
0x18000ec51  mov     r14, [r14+10h]
0x18000ec55  jmp     short loc_18000EC42
0x18000ec57  mov     r13, [rbp+57h+initializedElement]
0x18000ec5b  mov     r12, [rbp+57h+guard._pGuard]
0x18000ec5f  mov     replaced, [rbp+57h+arg_0]
0x18000ec63  lea     rax, [replaced+30h]
0x18000ec67  mov     [rbp+57h+guard._pGuard], rax
0x18000ec6b  cmp     [replaced+38h], rsi
0x18000ec6f  jz      loc_18000ED52
0x18000ec75  mov     r12, rax
0x18000ec78  mov     r14, [replaced+78h]
0x18000ec7c  test    r14, r14
0x18000ec7f  jz      short loc_18000ECCA
0x18000ec81  mov     rax, [r14+10h]
0x18000ec85  mov     [replaced+78h], rax
0x18000ec89  mov     rax, qword ptr [rbp+57h+guard._hr]
0x18000ec8d  mov     [r14+18h], r15d
0x18000ec91  mov     r15, [rbp+57h+arg_0]
0x18000ec95  mov     [r14], rax
0x18000ec98  inc     qword ptr [r15+40h]
0x18000ec9c  mov     rax, [r15+38h]
0x18000eca0  mov     key, [rax+r13*8]
0x18000eca4  mov     [r14+10h], key
0x18000eca8  mov     rax, [r15+38h]
0x18000ecac  mov     [rax+r13*8], r14
0x18000ecb0  mov     key, [r15+40h]; nElements
0x18000ecb4  cmp     key, [r15+58h]
0x18000ecb8  ja      loc_18000EE29
0x18000ecbe  mov     [r14+8], rbx
0x18000ecc2  xor     r12d, r12d
0x18000ecc5  jmp     loc_18000EAEB
0x18000ecca  mov     r14d, [replaced+6Ch]
0x18000ecce  mov     eax, 20h ; ' '
0x18000ecd3  mul     r14
0x18000ecd6  test    key, key
0x18000ecd9  jnz     loc_18000EADC
0x18000ecdf  lea     this, [rax+8]; Size
0x18000ece3  cmp     this, rax
0x18000ece6  jb      loc_18000EADC
0x18000ecec  call    cs:__imp_malloc
0x18000ecf2  test    rax, rax
0x18000ecf5  jz      loc_18000EADC
0x18000ecfb  mov     replaced, [rbp+57h+arg_0]
0x18000ecff  lea     r8d, [r14-1]
0x18000ed03  mov     edx, r8d
0x18000ed06  shl     key, 5
0x18000ed0a  add     key, 8
0x18000ed0e  mov     this, [replaced+70h]
0x18000ed12  add     key, rax
0x18000ed15  mov     [rax], this
0x18000ed18  mov     [replaced+70h], rax
0x18000ed1c  test    r8d, r8d
0x18000ed1f  js      short loc_18000ED47
0x18000ed21  mov     rax, [replaced+78h]
0x18000ed25  mov     r14, key
0x18000ed28  mov     [key+10h], rax
0x18000ed2c  mov     [replaced+78h], key
0x18000ed30  sub     key, 20h ; ' '
0x18000ed34  sub     r8d, 1
0x18000ed38  jns     short loc_18000ED21
0x18000ed3a  mov     r13d, dword ptr [rbp+57h+initializedElement]
0x18000ed3e  test    r14, r14
0x18000ed41  jnz     loc_18000EC81
0x18000ed47  mov     r12d, 8000FFFFh
0x18000ed4d  jmp     loc_18000EAE2
0x18000ed52  mov     r14d, [r12]
0x18000ed56  mov     this, 0FFFFFFFFFFFFFFFFh
0x18000ed5d  mov     eax, 8
0x18000ed62  mul     r14
0x18000ed65  lea     key, ?nothrow@std@@3Unothrow_t@1@B; x
0x18000ed6c  cmovb   rax, this
0x18000ed70  mov     this, rax; count
0x18000ed73  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ed78  mov     this, [rbp+57h+arg_0]
0x18000ed7c  mov     [this+38h], rax
0x18000ed80  test    rax, rax
0x18000ed83  jz      loc_18000EADC
0x18000ed89  cmp     r14d, 1FFFFFFFh
0x18000ed90  ja      short loc_18000ED47
0x18000ed92  lea     value, ds:0[r14*8]; Size
0x18000ed9a  xor     edx, edx; Val
0x18000ed9c  mov     this, rax; void *
0x18000ed9f  call    memset_0
0x18000eda4  mov     [r12], r14d
0x18000eda8  mov     r12, [rbp+57h+guard._pGuard]
0x18000edac  mov     this, r12; this
0x18000edaf  call    ?UpdateRehashThresholds@?$XHashMap@PEAUHSTRING__@@PEAUIApplicationDataContainer@Storage@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@@6784@@Internal@Collections@Foundation@4@V?$CElementTraits@PEAUIApplicationDataContainer@Storage@Windows@@@XWinRT@@@XWinRT@@AEAAXXZ; XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::UpdateRehashThresholds(void)
0x18000edb4  mov     replaced, [rbp+57h+arg_0]
0x18000edb8  jmp     loc_18000EC78
0x18000edbd  cmp     [rdi+8], esi
0x18000edc0  jnz     loc_18000EA04
0x18000edc6  mov     dword ptr [rdi+8], 0F0000000h
0x18000edcd  jmp     loc_18000EA04
0x18000edd2  mov     value, qword ptr [rbp+57h+guard._hr]; strRhs
0x18000edd6  lea     replaced, [rbp+57h+fEquals]; fEquals
0x18000edda  mov     key, [r13+0]; strLhs
0x18000edde  mov     [rbp+57h+fEquals], sil
0x18000ede2  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18000ede7  mov     r12d, eax
0x18000edea  test    eax, eax
0x18000edec  jns     loc_18000EF2D
0x18000edf2  mov     r15, [rbp+57h+arg_0]
0x18000edf6  jmp     loc_18000EAF1
0x18000edfb  mov     value, qword ptr [rbp+57h+guard._hr]; strRhs
0x18000edff  lea     replaced, [rbp+57h+fEquals]; fEquals
0x18000ee03  mov     key, [r14]; strLhs
  ... truncated ...
```
