# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,Windows::Storage::IApplicationDataContainer *,uchar *)

- ea: `0x18000dd10`
- end: `0x18000e27a`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@@6784@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIApplicationDataContainer@Storage@5@PEAE@Z`
- size: `1386`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > *this, HSTRING__ *key, Windows::Storage::IApplicationDataContainer *value, unsigned __int8 *replaced)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000cfa0`
- `0x18000dd10`
- `0x18000e280`
- `0x18000e29c`
- `0x18000e2c0`
- `0x18000e8d0`
- `0x18000f0b0`
- `0x18000f1ac`
- `0x1800254e8`
- `0x180026620`
- `0x1800415d6`
- `0x1800415ee`
- `0x180042010`

## import_xrefs

- `msvcrt!malloc` at `0x18000e19b`
- `msvcrt!malloc` at `0x18000e19b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000df76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000df76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dda4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dda4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000dd57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000dd57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dde0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000de66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e04a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e05e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e15a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dde0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000de66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e04a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e05e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e15a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dfba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dfba`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000e225`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000e225`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > *this,
        HSTRING key,
        Windows::Storage::IApplicationDataContainer *value,
        unsigned __int8 *replaced)
{
  HRESULT v7; // r14d
  XWinRT::ComLock *p_comLock; // rdi
  Windows::Storage::IApplicationDataContainer *m_value; // rsi
  PCWSTR StringRawBuffer; // rax
  unsigned int v11; // r12d
  unsigned int v12; // r15d
  unsigned __int64 i; // rcx
  int v14; // edx
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode **m_ppBins; // r13
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode *j; // r13
  unsigned int *v17; // r14
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > *v18; // r15
  PCWSTR v19; // rax
  unsigned __int64 v20; // rdx
  int v21; // ecx
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode **v22; // r15
  __int64 v23; // rdx
  unsigned int v24; // r13d
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode *k; // r15
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > *v26; // r9
  __int64 v27; // r8
  unsigned __int64 m_nElements; // rdx
  unsigned __int8 *v29; // r12
  __int64 v31; // r9
  HSTRING m_key; // rcx
  HSTRING__ *v33; // r14
  wchar_t *v34; // rax
  PCWSTR v35; // rax
  unsigned __int64 v36; // r15
  unsigned __int64 v37; // rax
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode **v38; // rax
  unsigned int m_nBlockSize; // r14d
  unsigned __int64 v40; // rax
  HSTRING v41; // rcx
  HSTRING__ *v42; // r14
  PCWSTR v43; // rax
  PCWSTR v44; // r13
  PCWSTR v45; // rax
  XWinRT::XPlex *v46; // rax
  int v47; // r8d
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode *v48; // rdx
  unsigned int v49; // eax
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> > *v50; // r10
  XWinRT::SecureVersionTag::Tag *v51; // rax
  XWinRT::SecureVersionTag::Tag *v52; // r14
  UINT32 length; // [rsp+30h] [rbp-38h] BYREF
  UINT32 v54; // [rsp+34h] [rbp-34h] BYREF
  XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > sNewKey; // [rsp+38h] [rbp-30h] BYREF
  XWinRT::detail::ReentrancyGuard<0> v56; // [rsp+40h] [rbp-28h] BYREF
  unsigned int *p_m_nBins; // [rsp+48h] [rbp-20h]
  XWinRT::AutoValue<Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *> > sOldValue; // [rsp+50h] [rbp-18h] BYREF
  void *Buf1; // [rsp+58h] [rbp-10h]

  *replaced = 0;
  if ( !this->_initialized )
    RoOriginateError(2147549183LL, 0);
  sNewKey._value = 0;
  v7 = WindowsDuplicateString(key, &sNewKey._value);
  if ( v7 >= 0 )
  {
    if ( value )
      value->AddRef(value);
    p_comLock = &this->_comLock;
    sOldValue._value = 0;
    m_value = 0;
    if ( this->_comLock.kind == Kind_StaReentrancy )
    {
      if ( !this->_comLock.asSrl._val )
        this->_comLock.asSrl._val = -268435456;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)&this->_comLock.8);
    }
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v56, *(_BYTE *)&this->_listeners, &this->_reentrancyGuard);
    if ( this->_versionManager._pTag->_iRefCount > 1 )
    {
      v51 = (XWinRT::SecureVersionTag::Tag *)operator new(4u, &std::nothrow);
      v52 = v51;
      if ( v51 )
      {
        v51->_iRefCount = 1;
        XWinRT::SecureVersionTag::Tag::Release(this->_versionManager._pTag);
        this->_versionManager._pTag = v52;
      }
    }
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(sNewKey._value, &length);
    v11 = -2128831035;
    v12 = -2128831035;
    for ( i = 0; i < 2 * (unsigned __int64)length; v12 = 16777619 * (v12 ^ v14) )
      v14 = *((unsigned __int8 *)StringRawBuffer + i++);
    m_ppBins = this->_hashMap.m_ppBins;
    if ( m_ppBins )
    {
      p_m_nBins = &this->_hashMap.m_nBins;
      for ( j = m_ppBins[v12 % this->_hashMap.m_nBins]; ; j = j->m_pNext )
      {
        if ( !j )
        {
          v17 = p_m_nBins;
          v18 = this;
          goto LABEL_15;
        }
        if ( j->m_nHash == v12 )
        {
          m_key = j->m_key;
          v33 = sNewKey._value;
          v54 = 0;
          v34 = (wchar_t *)WindowsGetStringRawBuffer(m_key, &v54);
          length = 0;
          Buf1 = v34;
          v35 = WindowsGetStringRawBuffer(v33, &length);
          if ( v54 == length && !memcmp_0(Buf1, v35, 2LL * length) )
            break;
        }
      }
      m_value = j->m_value;
      XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&sOldValue._value);
      v29 = replaced;
      j->m_value = value;
      value = 0;
      v7 = 0;
      *replaced = 1;
      goto LABEL_34;
    }
    v18 = this;
    v17 = &this->_hashMap.m_nBins;
    p_m_nBins = &this->_hashMap.m_nBins;
LABEL_15:
    if ( v18->_hashMap.m_nElements == 0x7FFFFFFF )
    {
      v29 = replaced;
      v7 = -2147024882;
      goto LABEL_35;
    }
    v54 = 0;
    v19 = WindowsGetStringRawBuffer(sNewKey._value, &v54);
    v20 = 0;
    if ( 2LL * v54 )
    {
      do
      {
        v21 = *((unsigned __int8 *)v19 + v20++);
        v11 = 16777619 * (v11 ^ v21);
      }
      while ( v20 < 2 * (unsigned __int64)v54 );
      v17 = &v18->_hashMap.m_nBins;
      p_m_nBins = &v18->_hashMap.m_nBins;
    }
    v22 = v18->_hashMap.m_ppBins;
    v23 = v11 % *v17;
    v24 = v23;
    LODWORD(Buf1) = v23;
    if ( v22 )
    {
      for ( k = v22[v23]; k; k = k->m_pNext )
      {
        if ( k->m_nHash == v11 )
        {
          v41 = k->m_key;
          v42 = sNewKey._value;
          LODWORD(sOldValue._value) = 0;
          v43 = WindowsGetStringRawBuffer(v41, (UINT32 *)&sOldValue);
          length = 0;
          v44 = v43;
          v45 = WindowsGetStringRawBuffer(v42, &length);
          if ( LODWORD(sOldValue._value) == length && !memcmp_0(v44, v45, 2LL * length) )
            goto LABEL_26;
        }
      }
      v17 = p_m_nBins;
      v24 = (unsigned int)Buf1;
    }
    v26 = this;
    if ( !this->_hashMap.m_ppBins )
    {
      v36 = *v17;
      v37 = 8 * v36;
      if ( !is_mul_ok(v36, 8u) )
        v37 = -1;
      v38 = (XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode **)operator new[](v37, &std::nothrow);
      this->_hashMap.m_ppBins = v38;
      if ( !v38 )
        goto LABEL_62;
      if ( (unsigned int)v36 > 0x1FFFFFFF )
      {
LABEL_30:
        v7 = -2147418113;
        goto LABEL_33;
      }
      memset_0(v38, 0, 8 * v36);
      *v17 = v36;
      XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::UpdateRehashThresholds(&this->_hashMap);
    }
    k = v26->_hashMap.m_pFree;
    if ( k )
      goto LABEL_25;
    m_nBlockSize = v26->_hashMap.m_nBlockSize;
    v40 = 32LL * m_nBlockSize;
    if ( is_mul_ok(m_nBlockSize, 0x20u) && v40 + 8 >= v40 )
    {
      v46 = (XWinRT::XPlex *)malloc(v40 + 8);
      if ( v46 )
      {
        v26 = this;
        v47 = m_nBlockSize - 1;
        v48 = (XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode *)&v46[4 * m_nBlockSize - 3];
        v46->pNext = this->_hashMap.m_pBlocks;
        this->_hashMap.m_pBlocks = v46;
        if ( (int)(m_nBlockSize - 1) >= 0 )
        {
          do
          {
            k = v48;
            v48->m_pNext = this->_hashMap.m_pFree;
            this->_hashMap.m_pFree = v48--;
            --v47;
          }
          while ( v47 >= 0 );
          if ( k )
          {
LABEL_25:
            v26->_hashMap.m_pFree = k->m_pNext;
            k->m_key = sNewKey._value;
            k->m_nHash = v11;
            ++v26->_hashMap.m_nElements;
            v27 = v24;
            k->m_pNext = v26->_hashMap.m_ppBins[v27];
            v26->_hashMap.m_ppBins[v27] = k;
            m_nElements = v26->_hashMap.m_nElements;
            if ( m_nElements <= v26->_hashMap.m_nHiRehashThreshold
              || v26->_hashMap.m_nLockCount
              || (v49 = XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::PickSize(
                          &v26->_hashMap,
                          m_nElements),
                  v7 = XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::Rehash(
                         v50,
                         v49),
                  v7 >= 0) )
            {
LABEL_26:
              k->m_value = value;
              v7 = 0;
              sNewKey._value = 0;
              value = 0;
            }
            goto LABEL_33;
          }
        }
        goto LABEL_30;
      }
    }
LABEL_62:
    v7 = -2147024882;
LABEL_33:
    v29 = replaced;
LABEL_34:
    v18 = this;
LABEL_35:
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
    if ( v7 >= 0 )
    {
      v31 = 3;
      if ( !*v29 )
        v31 = 1;
      v7 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
             (unsigned __int8)this,
             *(_BYTE *)&v18->_evtMapChanged,
             v18,
             v31,
             key);
    }
  }
  WindowsDeleteString(sNewKey._value);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000dd10  mov     [rsp-30h+arg_18], replaced
0x18000dd15  mov     [rsp-30h+arg_8], key
0x18000dd1a  mov     qword ptr [rsp-30h+guard], this
0x18000dd1f  push    rbp
0x18000dd20  push    rbx
0x18000dd21  push    rdi
0x18000dd22  push    r13
0x18000dd24  push    r14
0x18000dd26  push    r15
0x18000dd28  mov     rbp, rsp
0x18000dd2b  sub     rsp, 68h
0x18000dd2f  mov     byte ptr [replaced], 0
0x18000dd33  mov     rbx, value
0x18000dd36  cmp     byte ptr [this+98h], 0
0x18000dd3d  mov     rdi, key
0x18000dd40  mov     r13, this
0x18000dd43  jz      loc_18000E21E
0x18000dd49  xor     r15d, r15d
0x18000dd4c  lea     key, [rbp+sNewKey]; newString
0x18000dd50  mov     this, rdi; string
0x18000dd53  mov     [rbp+sNewKey._value], r15
0x18000dd57  call    cs:__imp_WindowsDuplicateString
0x18000dd5d  mov     r14d, eax
0x18000dd60  test    eax, eax
0x18000dd62  js      loc_18000DFB6
0x18000dd68  mov     [rsp+68h+arg_10], rsi
0x18000dd70  mov     [rsp+68h+var_8], r12
0x18000dd75  test    rbx, rbx
0x18000dd78  jz      short loc_18000DD89
0x18000dd7a  mov     rax, [rbx]
0x18000dd7d  mov     this, rbx
0x18000dd80  mov     rax, [rax+8]
0x18000dd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd89  lea     rdi, [r13+80h]
0x18000dd90  mov     [rbp+sOldValue._value], r15
0x18000dd94  cmp     dword ptr [rdi], 1
0x18000dd97  mov     rsi, r15
0x18000dd9a  jz      loc_18000E026
0x18000dda0  lea     this, [rdi+8]; SRWLock
0x18000dda4  call    cs:__imp_AcquireSRWLockExclusive
0x18000ddaa  movzx   edx, byte ptr [r13+9Ah]
0x18000ddb2  lea     value, [r13+9Ch]
0x18000ddb9  lea     this, [rbp+var_28]; this
0x18000ddbd  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18000ddc2  mov     rax, [r13+90h]
0x18000ddc9  mov     ecx, [rax]
0x18000ddcb  cmp     ecx, 1
0x18000ddce  jg      loc_18000E230
0x18000ddd4  mov     this, [rbp+sNewKey._value]; string
0x18000ddd8  lea     key, [rbp+length]; length
0x18000dddc  mov     [rbp+length], r15d
0x18000dde0  call    cs:__imp_WindowsGetStringRawBuffer
0x18000dde6  mov     r8d, [rbp+length]
0x18000ddea  mov     r12d, 811C9DC5h
0x18000ddf0  mov     r15d, r12d
0x18000ddf3  mov     this, rsi
0x18000ddf6  add     value, value
0x18000ddf9  jz      short loc_18000DE16
0x18000ddfb  nop     dword ptr [rax+rax+00h]
0x18000de00  movzx   edx, byte ptr [rax+this]
0x18000de04  inc     this
0x18000de07  xor     edx, r15d
0x18000de0a  imul    r15d, edx, 1000193h
0x18000de11  cmp     this, value
0x18000de14  jb      short loc_18000DE00
0x18000de16  mov     r13, [r13+30h]
0x18000de1a  test    r13, r13
0x18000de1d  jz      loc_18000E18A
0x18000de23  mov     r14, qword ptr [rbp+guard]
0x18000de27  xor     edx, edx
0x18000de29  add     r14, 40h ; '@'
0x18000de2d  mov     eax, r15d
0x18000de30  mov     [rbp+var_20], r14
0x18000de34  div     dword ptr [r14]
0x18000de37  mov     r13, [r13+key*8+0]
0x18000de3c  test    r13, r13
0x18000de3f  jnz     loc_18000DF33
0x18000de45  mov     r14, [rbp+var_20]
0x18000de49  mov     r15, qword ptr [rbp+guard]
0x18000de4d  cmp     qword ptr [r15+38h], 7FFFFFFFh
0x18000de55  jz      loc_18000E26B
0x18000de5b  mov     this, [rbp+sNewKey._value]; string
0x18000de5f  lea     key, [rbp+var_34]; length
0x18000de63  mov     [rbp+var_34], esi
0x18000de66  call    cs:__imp_WindowsGetStringRawBuffer
0x18000de6c  mov     r8d, [rbp+var_34]
0x18000de70  mov     key, rsi
0x18000de73  add     value, value
0x18000de76  jz      short loc_18000DE9E
0x18000de78  nop     dword ptr [rax+rax+00000000h]
0x18000de80  movzx   ecx, byte ptr [rax+key]
0x18000de84  inc     key
0x18000de87  xor     ecx, r12d
0x18000de8a  imul    r12d, ecx, 1000193h
0x18000de91  cmp     key, value
0x18000de94  jb      short loc_18000DE80
0x18000de96  lea     r14, [r15+40h]
0x18000de9a  mov     [rbp+var_20], r14
0x18000de9e  mov     r15, [r15+30h]
0x18000dea2  xor     edx, edx
0x18000dea4  mov     eax, r12d
0x18000dea7  div     dword ptr [r14]
0x18000deaa  mov     r13d, edx
0x18000dead  mov     dword ptr [rbp+Buf1], r13d
0x18000deb1  test    r15, r15
0x18000deb4  jz      short loc_18000DECB
0x18000deb6  mov     r15, [r15+key*8]
0x18000deba  test    r15, r15
0x18000debd  jnz     loc_18000E007
0x18000dec3  mov     r14, [rbp+var_20]
0x18000dec7  mov     r13d, dword ptr [rbp+Buf1]
0x18000decb  mov     replaced, qword ptr [rbp+guard]
0x18000decf  cmp     [replaced+30h], rsi
0x18000ded3  jz      loc_18000E0AE
0x18000ded9  mov     r15, [replaced+70h]
0x18000dedd  test    r15, r15
0x18000dee0  jz      loc_18000E114
0x18000dee6  mov     rax, [r15+10h]
0x18000deea  mov     [replaced+70h], rax
0x18000deee  mov     rax, [rbp+sNewKey._value]
0x18000def2  mov     [r15], rax
0x18000def5  mov     [r15+18h], r12d
0x18000def9  inc     qword ptr [replaced+38h]
0x18000defd  mov     eax, r13d
0x18000df00  lea     value, ds:0[rax*8]
0x18000df08  mov     rax, [replaced+30h]
0x18000df0c  mov     key, [value+rax]
0x18000df10  mov     [r15+10h], key
0x18000df14  mov     rax, [replaced+30h]
0x18000df18  mov     [value+rax], r15
0x18000df1c  mov     key, [replaced+38h]; nElements
0x18000df20  cmp     key, [replaced+50h]
0x18000df24  ja      loc_18000E1EE
0x18000df2a  mov     [r15+8], rbx
0x18000df2e  xor     r14d, r14d
0x18000df31  jmp     short loc_18000DF56
0x18000df33  cmp     [r13+18h], r15d
0x18000df37  jz      loc_18000E03B
0x18000df3d  mov     r13, [r13+10h]
0x18000df41  jmp     loc_18000DE3C
0x18000df46  test    r15, r15
0x18000df49  jnz     short loc_18000DEE6
0x18000df4b  mov     r14d, 8000FFFFh
0x18000df51  test    r14d, r14d
0x18000df54  js      short loc_18000DF5C
0x18000df56  mov     [rbp+sNewKey._value], rsi
0x18000df5a  xor     ebx, ebx
0x18000df5c  mov     r12, [rbp+arg_18]
0x18000df60  mov     r15, qword ptr [rbp+guard]
0x18000df64  test    rdi, rdi
0x18000df67  jz      short loc_18000DF7C
0x18000df69  cmp     dword ptr [rdi], 1
0x18000df6c  jz      loc_18000E01A
0x18000df72  lea     this, [rdi+8]; SRWLock
0x18000df76  call    cs:__imp_ReleaseSRWLockExclusive
0x18000df7c  test    rsi, rsi
0x18000df7f  jz      short loc_18000DF90
0x18000df81  mov     rax, [rsi]
0x18000df84  mov     this, rsi
0x18000df87  mov     rax, [rax+10h]
0x18000df8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df90  mov     rsi, [rsp+68h+arg_10]
0x18000df98  test    rbx, rbx
0x18000df9b  jz      short loc_18000DFAC
0x18000df9d  mov     rax, [rbx]
0x18000dfa0  mov     this, rbx
0x18000dfa3  mov     rax, [rax+10h]
0x18000dfa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfac  test    r14d, r14d
0x18000dfaf  jns     short loc_18000DFD1
0x18000dfb1  mov     r12, [rsp+68h+var_8]
0x18000dfb6  mov     this, [rbp+sNewKey._value]; string
0x18000dfba  call    cs:__imp_WindowsDeleteString
0x18000dfc0  mov     eax, r14d
0x18000dfc3  add     rsp, 68h
0x18000dfc7  pop     r15
0x18000dfc9  pop     r14
0x18000dfcb  pop     r13
0x18000dfcd  pop     rdi
0x18000dfce  pop     rbx
0x18000dfcf  pop     rbp
0x18000dfd0  retn
0x18000dfd1  cmp     byte ptr [r12], 0
0x18000dfd6  mov     eax, 1
0x18000dfdb  movzx   edx, byte ptr [r15+99h]
0x18000dfe3  mov     r9d, 3
0x18000dfe9  movzx   ecx, byte ptr [rbp+guard]
0x18000dfed  cmovz   r9d, eax
0x18000dff1  mov     rax, [rbp+arg_8]
0x18000dff5  mov     value, r15
0x18000dff8  mov     [rsp+68h+var_48], rax
0x18000dffd  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x18000e002  mov     r14d, eax
0x18000e005  jmp     short loc_18000DFB1
0x18000e007  cmp     [r15+18h], r12d
0x18000e00b  jz      loc_18000E139
0x18000e011  mov     r15, [r15+10h]
0x18000e015  jmp     loc_18000DEBA
0x18000e01a  add     dword ptr [rdi+8], 10000000h
0x18000e021  jmp     loc_18000DF7C
0x18000e026  cmp     [rdi+8], esi
0x18000e029  jnz     loc_18000DDAA
0x18000e02f  mov     dword ptr [rdi+8], 0F0000000h
0x18000e036  jmp     loc_18000DDAA
0x18000e03b  mov     this, [r13+0]; string
0x18000e03f  lea     key, [rbp+var_34]; length
0x18000e043  mov     r14, [rbp+sNewKey._value]
0x18000e047  mov     [rbp+var_34], esi
0x18000e04a  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e050  lea     key, [rbp+length]; length
0x18000e054  mov     [rbp+length], esi
0x18000e057  mov     this, r14; string
0x18000e05a  mov     [rbp+Buf1], rax
0x18000e05e  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e064  mov     ecx, [rbp+length]
0x18000e067  cmp     [rbp+var_34], ecx
0x18000e06a  jnz     loc_18000DF3D
0x18000e070  mov     r8d, ecx
0x18000e073  mov     key, rax; Buf2
0x18000e076  mov     this, [rbp+Buf1]; Buf1
0x18000e07a  add     value, value; Size
0x18000e07d  call    memcmp_0
0x18000e082  test    eax, eax
0x18000e084  jnz     loc_18000DF3D
0x18000e08a  mov     rsi, [r13+8]
0x18000e08e  lea     this, [rbp+sOldValue]; initializedElement
0x18000e092  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18000e097  mov     r12, [rbp+arg_18]
0x18000e09b  mov     [r13+8], rbx
0x18000e09f  xor     ebx, ebx
0x18000e0a1  xor     r14d, r14d
0x18000e0a4  mov     byte ptr [r12], 1
0x18000e0a9  jmp     loc_18000DF60
0x18000e0ae  mov     r15d, [r14]
0x18000e0b1  mov     this, 0FFFFFFFFFFFFFFFFh
0x18000e0b8  mov     eax, 8
0x18000e0bd  mul     r15
0x18000e0c0  lea     key, ?nothrow@std@@3Unothrow_t@1@B; x
0x18000e0c7  cmovb   rax, this
0x18000e0cb  mov     this, rax; count
0x18000e0ce  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000e0d3  mov     this, qword ptr [rbp+guard]
0x18000e0d7  mov     [this+30h], rax
0x18000e0db  test    rax, rax
0x18000e0de  jz      short loc_18000E12E
0x18000e0e0  cmp     r15d, 1FFFFFFFh
0x18000e0e7  ja      loc_18000DF4B
0x18000e0ed  lea     value, ds:0[r15*8]; Size
0x18000e0f5  xor     edx, edx; Val
0x18000e0f7  mov     this, rax; void *
0x18000e0fa  call    memset_0
0x18000e0ff  mov     replaced, qword ptr [rbp+guard]
0x18000e103  mov     [r14], r15d
0x18000e106  lea     this, [replaced+28h]; this
0x18000e10a  call    ?UpdateRehashThresholds@?$XHashMap@PEAUHSTRING__@@PEAUIApplicationDataContainer@Storage@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@@6784@@Internal@Collections@Foundation@4@V?$CElementTraits@PEAUIApplicationDataContainer@Storage@Windows@@@XWinRT@@@XWinRT@@AEAAXXZ; XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::UpdateRehashThresholds(void)
0x18000e10f  jmp     loc_18000DED9
0x18000e114  mov     r14d, [replaced+64h]
0x18000e118  mov     eax, 20h ; ' '
0x18000e11d  mul     r14
0x18000e120  test    key, key
0x18000e123  jnz     short loc_18000E12E
0x18000e125  lea     this, [rax+8]; Size
0x18000e129  cmp     this, rax
0x18000e12c  jnb     short loc_18000E19B
0x18000e12e  mov     r14d, 8007000Eh
0x18000e134  jmp     loc_18000DF51
0x18000e139  mov     this, [r15]; string
0x18000e13c  lea     key, [rbp+sOldValue]; length
0x18000e140  mov     r14, [rbp+sNewKey._value]
0x18000e144  mov     dword ptr [rbp+sOldValue._value], esi
0x18000e147  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e14d  lea     key, [rbp+length]; length
0x18000e151  mov     [rbp+length], esi
0x18000e154  mov     this, r14; string
0x18000e157  mov     r13, rax
0x18000e15a  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e160  mov     ecx, [rbp+length]
0x18000e163  cmp     dword ptr [rbp+sOldValue._value], ecx
0x18000e166  jnz     loc_18000E011
0x18000e16c  mov     r8d, ecx
0x18000e16f  mov     key, rax; Buf2
0x18000e172  add     value, value; Size
0x18000e175  mov     this, r13; Buf1
0x18000e178  call    memcmp_0
0x18000e17d  test    eax, eax
0x18000e17f  jz      loc_18000DF2A
0x18000e185  jmp     loc_18000E011
0x18000e18a  mov     r15, qword ptr [rbp+guard]
0x18000e18e  lea     r14, [r15+40h]
0x18000e192  mov     [rbp+var_20], r14
0x18000e196  jmp     loc_18000DE4D
0x18000e19b  call    cs:__imp_malloc
0x18000e1a1  test    rax, rax
0x18000e1a4  jz      short loc_18000E12E
0x18000e1a6  mov     replaced, qword ptr [rbp+guard]
0x18000e1aa  lea     r8d, [r14-1]
0x18000e1ae  mov     edx, r8d
0x18000e1b1  shl     key, 5
0x18000e1b5  add     key, 8
0x18000e1b9  mov     this, [replaced+68h]
  ... truncated ...
```
