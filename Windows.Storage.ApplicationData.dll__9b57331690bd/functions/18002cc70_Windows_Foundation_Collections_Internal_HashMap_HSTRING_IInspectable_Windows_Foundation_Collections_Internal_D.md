# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::Remove(HSTRING__ *)

- ea: `0x18002cc70`
- end: `0x18002ce48`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `472`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *this, HSTRING__ *key)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000d5e0`
- `0x18000e2c0`
- `0x18000e2f0`
- `0x1800156d0`
- `0x1800158d0`
- `0x180016060`
- `0x180016360`
- `0x180016450`
- `0x180016ddc`
- `0x18002cc70`
- `0x18002d3d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cddf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cddf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cd54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cdf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cd54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cdf1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002cd32`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002cd32`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::Remove(
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *this,
        HSTRING__ *key)
{
  int v3; // edi
  HSTRING m_key; // rbx
  XWinRT::detail::ReentrancyGuard<1> *v5; // rax
  int v6; // eax
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *v7; // rsi
  IInspectable *m_value; // rdi
  __int64 v9; // r9
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode **m_ppBins; // rdx
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *v11; // rax
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *m_pNext; // rcx
  _RTL_SRWLOCK *v13; // rcx
  XWinRT::detail::LockHolder<XWinRT::ComLock,XWinRT::detail::AcquireWrite> acquired; // [rsp+30h] [rbp-30h] BYREF
  XWinRT::detail::ReentrancyGuard<1> guard; // [rsp+38h] [rbp-28h] BYREF
  XWinRT::detail::ReentrancyGuard<1> v17; // [rsp+48h] [rbp-18h] BYREF
  HSTRING__ *v18; // [rsp+98h] [rbp+38h] BYREF
  XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CPair *pPair; // [rsp+A0h] [rbp+40h] BYREF
  XWinRT::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *> > sOldValue; // [rsp+A8h] [rbp+48h] BYREF

  v18 = key;
  guard._hr = -2147483627;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::EnsureInitialized(this);
  guard._pGuard = 0;
  if ( v3 >= 0 )
  {
    m_key = 0;
    sOldValue._value = 0;
    LODWORD(pPair) = 0;
    XWinRT::SerializingLockPolicy::Write(&acquired, &this->_comLock, (HRESULT *)&pPair);
    v3 = (int)pPair;
    if ( (int)pPair >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(&v17, this->_listeners, &this->_reentrancyGuard);
      XWinRT::detail::ReentrancyGuard<1>::operator=(&guard, v5);
      v6 = XWinRT::detail::ReentrancyGuard<1>::hr(&guard);
      pPair = 0;
      v3 = v6;
      if ( v6 >= 0 )
      {
        v3 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(
               &this->_hashMap,
               &v18,
               &pPair);
        if ( v3 >= 0 )
        {
          v7 = (XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::KeyTraits,XWinRT::CElementTraits<IInspectable *> >::CNode *)pPair;
          if ( pPair )
          {
            v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion(&this->_versionManager);
            if ( v3 >= 0 )
            {
              m_key = v7->m_key;
              WindowsDeleteString(0);
              m_value = v7->m_value;
              XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>((Windows::Storage::IApplicationDataContainer **)&sOldValue);
              sOldValue._value = m_value;
              if ( v7 )
              {
                v9 = v7->m_nHash % this->_hashMap.m_nBins;
                m_ppBins = this->_hashMap.m_ppBins;
                v11 = m_ppBins[v9];
                if ( v7 == v11 )
                {
                  v11 = 0;
                }
                else
                {
                  while ( v11->m_pNext != v7 )
                    v11 = v11->m_pNext;
                }
                m_pNext = v7->m_pNext;
                if ( v11 )
                  v11->m_pNext = m_pNext;
                else
                  m_ppBins[v9] = m_pNext;
                XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::FreeNode(
                  &this->_hashMap,
                  v7);
                v3 = 0;
              }
              else
              {
                m_key = 0;
                v3 = -2147418113;
                sOldValue._value = 0;
              }
            }
          }
          else
          {
            v3 = -2147483637;
            RoOriginateError(2147483659LL, 0);
          }
        }
      }
    }
    if ( acquired._pLock )
    {
      v13 = (_RTL_SRWLOCK *)&acquired._pLock->8;
      if ( acquired._pLock->kind == Kind_StaReentrancy )
        *(_DWORD *)&v13->0 += 0x10000000;
      else
        ReleaseSRWLockExclusive(v13);
    }
    XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>((Windows::Storage::IApplicationDataContainer **)&sOldValue);
    WindowsDeleteString(m_key);
  }
  if ( v3 >= 0 )
    v3 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>::RaiseEvent(
           &guard,
           &this->_evtMapChanged,
           (Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *> *)((unsigned __int64)&this->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *> >
                                                                                          & -(__int64)(this != 0)),
           CollectionChange_ItemRemoved,
           v18);
  if ( guard._pGuard )
    *guard._pGuard = 0;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002cc70  mov     [rsp-28h+arg_8], key
0x18002cc75  push    rbp
0x18002cc76  push    rbx
0x18002cc77  push    rsi
0x18002cc78  push    rdi
0x18002cc79  push    r14
0x18002cc7b  mov     rbp, rsp
0x18002cc7e  sub     rsp, 60h
0x18002cc82  mov     r14, this
0x18002cc85  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::EnsureInitialized(void)
0x18002cc8a  mov     [rbp+guard._hr], 80000015h
0x18002cc91  mov     edi, eax
0x18002cc93  mov     [rbp+guard._pGuard], 0
0x18002cc9b  test    eax, eax
0x18002cc9d  js      loc_18002CDF7
0x18002cca3  xor     ebx, ebx
0x18002cca5  lea     key, [r14+88h]; lock
0x18002ccac  lea     r8, [rbp+pPair]; phr
0x18002ccb0  mov     [rbp+sOldValue._value], rbx
0x18002ccb4  lea     this, [rbp+acquired]; result
0x18002ccb8  mov     dword ptr [rbp+pPair], ebx
0x18002ccbb  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18002ccc0  mov     edi, dword ptr [rbp+pPair]
0x18002ccc3  test    edi, edi
0x18002ccc5  js      loc_18002CDC5
0x18002cccb  mov     edx, [r14+0C0h]; listeners
0x18002ccd2  lea     r8, [r14+0C4h]; pGuard
0x18002ccd9  lea     this, [rbp+var_18]; this
0x18002ccdd  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x18002cce2  mov     key, rax
0x18002cce5  lea     this, [rbp+guard]
0x18002cce9  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x18002ccee  lea     this, [rbp+guard]; this
0x18002ccf2  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x18002ccf7  mov     [rbp+pPair], rbx
0x18002ccfb  mov     edi, eax
0x18002ccfd  test    eax, eax
0x18002ccff  js      loc_18002CDC5
0x18002cd05  lea     this, [r14+30h]; this
0x18002cd09  lea     r8, [rbp+pPair]; retval
0x18002cd0d  lea     key, [rbp+arg_8]; key
0x18002cd11  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x18002cd16  mov     edi, eax
0x18002cd18  test    eax, eax
0x18002cd1a  js      loc_18002CDC5
0x18002cd20  mov     rsi, [rbp+pPair]
0x18002cd24  test    rsi, rsi
0x18002cd27  jnz     short loc_18002CD3D
0x18002cd29  mov     edi, 8000000Bh
0x18002cd2e  xor     edx, edx
0x18002cd30  mov     ecx, edi
0x18002cd32  call    cs:__imp_RoOriginateError
0x18002cd38  jmp     loc_18002CDC5
0x18002cd3d  lea     this, [r14+98h]; this
0x18002cd44  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18002cd49  mov     edi, eax
0x18002cd4b  test    eax, eax
0x18002cd4d  js      short loc_18002CDC5
0x18002cd4f  mov     rbx, [rsi]
0x18002cd52  xor     ecx, ecx; string
0x18002cd54  call    cs:__imp_WindowsDeleteString
0x18002cd5a  mov     rdi, [rsi+8]
0x18002cd5e  lea     this, [rbp+sOldValue]; initializedElement
0x18002cd62  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18002cd67  mov     [rbp+sOldValue._value], rdi
0x18002cd6b  test    rsi, rsi
0x18002cd6e  jz      short loc_18002CDBA
0x18002cd70  mov     eax, [rsi+18h]
0x18002cd73  xor     edx, edx
0x18002cd75  div     dword ptr [r14+48h]
0x18002cd79  mov     r9d, edx
0x18002cd7c  mov     key, [r14+38h]
0x18002cd80  mov     rax, [key+r9*8]
0x18002cd84  cmp     rsi, rax
0x18002cd87  jnz     short loc_18002CD91
0x18002cd89  xor     eax, eax
0x18002cd8b  jmp     short loc_18002CD97
0x18002cd8d  mov     rax, [rax+10h]
0x18002cd91  cmp     [rax+10h], rsi
0x18002cd95  jnz     short loc_18002CD8D
0x18002cd97  mov     this, [rsi+10h]
0x18002cd9b  test    rax, rax
0x18002cd9e  jnz     short loc_18002CDA6
0x18002cda0  mov     [key+r9*8], this
0x18002cda4  jmp     short loc_18002CDAA
0x18002cda6  mov     [rax+10h], this
0x18002cdaa  mov     key, rsi; pNode
0x18002cdad  lea     this, [r14+30h]; this
0x18002cdb1  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CNode *)
0x18002cdb6  xor     edi, edi
0x18002cdb8  jmp     short loc_18002CDC5
0x18002cdba  xor     ebx, ebx
0x18002cdbc  mov     edi, 8000FFFFh
0x18002cdc1  mov     [rbp+sOldValue._value], rbx
0x18002cdc5  mov     rax, [rbp+acquired._pLock]
0x18002cdc9  test    rax, rax
0x18002cdcc  jz      short loc_18002CDE5
0x18002cdce  cmp     dword ptr [rax], 1
0x18002cdd1  lea     this, [rax+8]; SRWLock
0x18002cdd5  jnz     short loc_18002CDDF
0x18002cdd7  add     dword ptr [this], 10000000h
0x18002cddd  jmp     short loc_18002CDE5
0x18002cddf  call    cs:__imp_ReleaseSRWLockExclusive
0x18002cde5  lea     this, [rbp+sOldValue]; initializedElement
0x18002cde9  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18002cdee  mov     this, rbx; string
0x18002cdf1  call    cs:__imp_WindowsDeleteString
0x18002cdf7  test    edi, edi
0x18002cdf9  js      short loc_18002CE2C
0x18002cdfb  lea     this, [r14+18h]
0x18002cdff  mov     rax, r14
0x18002ce02  neg     rax
0x18002ce05  lea     key, [r14+0A8h]; e
0x18002ce0c  mov     rax, [rbp+arg_8]
0x18002ce10  mov     r9d, 2; change
0x18002ce16  sbb     r8, r8
0x18002ce19  mov     [rsp+60h+var_40], rax; key
0x18002ce1e  and     r8, this; sender
0x18002ce21  lea     this, [rbp+guard]; guard
0x18002ce25  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$EventSource@U?$MapChangedEventHandler@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@PEAU?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@345@W4CollectionChange@345@PEAUHSTRING__@@@Z; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Microsoft::WRL::EventSource<Windows::Foundation::Collections::MapChangedEventHandler<HSTRING__ *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::CollectionChange,HSTRING__ *)
0x18002ce2a  mov     edi, eax
0x18002ce2c  mov     rax, [rbp+guard._pGuard]
0x18002ce30  test    rax, rax
0x18002ce33  jz      short loc_18002CE3B
0x18002ce35  mov     dword ptr [rax], 0
0x18002ce3b  mov     eax, edi
0x18002ce3d  add     rsp, 60h
0x18002ce41  pop     r14
0x18002ce43  pop     rdi
0x18002ce44  pop     rsi
0x18002ce45  pop     rbx
0x18002ce46  pop     rbp
0x18002ce47  retn
```
