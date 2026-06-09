# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x180032b10`
- end: `0x180032cac`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@@6784@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `412`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > *this, HSTRING__ *key)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000e280`
- `0x18000e29c`
- `0x18000e2c0`
- `0x18000f010`
- `0x180010d90`
- `0x1800145f0`
- `0x1800156d0`
- `0x180016360`
- `0x180032b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032c58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032c58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032c6a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180032bab`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180032bab`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > *this,
        HSTRING__ *key)
{
  int v3; // edi
  HSTRING m_key; // rbx
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode *v5; // rsi
  Windows::Storage::IApplicationDataContainer *m_value; // rdi
  __int64 v7; // r8
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode **m_ppBins; // rdx
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode *v9; // rax
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode *m_pNext; // rcx
  _RTL_SRWLOCK *v11; // rcx
  XWinRT::detail::LockHolder<XWinRT::ComLock,XWinRT::detail::AcquireWrite> acquired; // [rsp+30h] [rbp-10h] BYREF
  HSTRING__ *v14; // [rsp+78h] [rbp+38h] BYREF
  XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CPair *pPair; // [rsp+80h] [rbp+40h] BYREF
  XWinRT::AutoValue<Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *> > sOldValue; // [rsp+88h] [rbp+48h] BYREF

  v14 = key;
  v3 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(this);
  if ( v3 >= 0 )
  {
    m_key = 0;
    sOldValue._value = 0;
    LODWORD(pPair) = 0;
    XWinRT::SerializingLockPolicy::Write(&acquired, &this->_comLock, (HRESULT *)&pPair);
    v3 = (int)pPair;
    if ( (int)pPair >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(
        (XWinRT::detail::ReentrancyGuard<0> *)&pPair,
        *(_BYTE *)&this->_listeners,
        &this->_reentrancyGuard);
      pPair = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::Lookup(
             &this->_hashMap,
             &v14,
             &pPair);
      if ( v3 >= 0 )
      {
        v5 = (XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *> >::CNode *)pPair;
        if ( pPair )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion(&this->_versionManager);
          if ( v3 >= 0 )
          {
            m_key = v5->m_key;
            WindowsDeleteString(0);
            m_value = v5->m_value;
            XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&sOldValue._value);
            sOldValue._value = m_value;
            if ( v5 )
            {
              v7 = v5->m_nHash % this->_hashMap.m_nBins;
              m_ppBins = this->_hashMap.m_ppBins;
              v9 = m_ppBins[v7];
              if ( v5 == v9 )
              {
                v9 = 0;
              }
              else
              {
                while ( v9->m_pNext != v5 )
                  v9 = v9->m_pNext;
              }
              m_pNext = v5->m_pNext;
              if ( v9 )
                v9->m_pNext = m_pNext;
              else
                m_ppBins[v7] = m_pNext;
              XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::FreeNode(
                &this->_hashMap,
                v5);
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
    if ( acquired._pLock )
    {
      v11 = (_RTL_SRWLOCK *)&acquired._pLock->8;
      if ( acquired._pLock->kind == Kind_StaReentrancy )
        *(_DWORD *)&v11->0 += 0x10000000;
      else
        ReleaseSRWLockExclusive(v11);
    }
    XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&sOldValue._value);
    WindowsDeleteString(m_key);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
                           (unsigned __int8)pPair,
                           *(_BYTE *)&this->_evtMapChanged,
                           this,
                           2,
                           v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180032b10  mov     [rsp-28h+arg_0], rbx
0x180032b15  mov     [rsp-28h+arg_8], key
0x180032b1a  push    rbp
0x180032b1b  push    rsi
0x180032b1c  push    rdi
0x180032b1d  push    r14
0x180032b1f  push    r15
0x180032b21  mov     rbp, rsp
0x180032b24  sub     rsp, 40h
0x180032b28  mov     r14, this
0x180032b2b  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@@6784@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x180032b30  mov     edi, eax
0x180032b32  test    eax, eax
0x180032b34  js      loc_180032C70
0x180032b3a  xor     ebx, ebx
0x180032b3c  lea     key, [r14+80h]; lock
0x180032b43  lea     r8, [rbp+pPair]; phr
0x180032b47  mov     [rbp+sOldValue._value], rbx
0x180032b4b  lea     this, [rbp+acquired]; result
0x180032b4f  mov     dword ptr [rbp+pPair], ebx
0x180032b52  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180032b57  mov     edi, dword ptr [rbp+pPair]
0x180032b5a  test    edi, edi
0x180032b5c  js      loc_180032C3E
0x180032b62  movzx   edx, byte ptr [r14+9Ah]
0x180032b6a  lea     r8, [r14+9Ch]
0x180032b71  lea     this, [rbp+pPair]; this
0x180032b75  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180032b7a  lea     r8, [rbp+pPair]; retval
0x180032b7e  mov     [rbp+pPair], rbx
0x180032b82  lea     key, [rbp+arg_8]; key
0x180032b86  lea     this, [r14+28h]; this
0x180032b8a  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIApplicationDataContainer@Storage@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@@6784@@Internal@Collections@Foundation@4@V?$CElementTraits@PEAUIApplicationDataContainer@Storage@Windows@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::CPair * *)
0x180032b8f  mov     edi, eax
0x180032b91  test    eax, eax
0x180032b93  js      loc_180032C3E
0x180032b99  mov     rsi, [rbp+pPair]
0x180032b9d  test    rsi, rsi
0x180032ba0  jnz     short loc_180032BB6
0x180032ba2  mov     edi, 8000000Bh
0x180032ba7  xor     edx, edx
0x180032ba9  mov     ecx, edi
0x180032bab  call    cs:__imp_RoOriginateError
0x180032bb1  jmp     loc_180032C3E
0x180032bb6  lea     this, [r14+90h]; this
0x180032bbd  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180032bc2  mov     edi, eax
0x180032bc4  test    eax, eax
0x180032bc6  js      short loc_180032C3E
0x180032bc8  mov     rbx, [rsi]
0x180032bcb  xor     ecx, ecx; string
0x180032bcd  call    cs:__imp_WindowsDeleteString
0x180032bd3  mov     rdi, [rsi+8]
0x180032bd7  lea     this, [rbp+sOldValue]; initializedElement
0x180032bdb  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x180032be0  mov     [rbp+sOldValue._value], rdi
0x180032be4  test    rsi, rsi
0x180032be7  jz      short loc_180032C33
0x180032be9  mov     eax, [rsi+18h]
0x180032bec  xor     edx, edx
0x180032bee  div     dword ptr [r14+40h]
0x180032bf2  mov     r8d, edx
0x180032bf5  mov     key, [r14+30h]
0x180032bf9  mov     rax, [key+r8*8]
0x180032bfd  cmp     rsi, rax
0x180032c00  jnz     short loc_180032C0A
0x180032c02  xor     eax, eax
0x180032c04  jmp     short loc_180032C10
0x180032c06  mov     rax, [rax+10h]
0x180032c0a  cmp     [rax+10h], rsi
0x180032c0e  jnz     short loc_180032C06
0x180032c10  mov     this, [rsi+10h]
0x180032c14  test    rax, rax
0x180032c17  jnz     short loc_180032C1F
0x180032c19  mov     [key+r8*8], this
0x180032c1d  jmp     short loc_180032C23
0x180032c1f  mov     [rax+10h], this
0x180032c23  mov     key, rsi; pNode
0x180032c26  lea     this, [r14+28h]; this
0x180032c2a  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAUIApplicationDataContainer@Storage@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@@6784@@Internal@Collections@Foundation@4@V?$CElementTraits@PEAUIApplicationDataContainer@Storage@Windows@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,Windows::Storage::IApplicationDataContainer *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<Windows::Storage::IApplicationDataContainer *>>::CNode *)
0x180032c2f  xor     edi, edi
0x180032c31  jmp     short loc_180032C3E
0x180032c33  xor     ebx, ebx
0x180032c35  mov     edi, 8000FFFFh
0x180032c3a  mov     [rbp+sOldValue._value], rbx
0x180032c3e  mov     rax, [rbp+acquired._pLock]
0x180032c42  test    rax, rax
0x180032c45  jz      short loc_180032C5E
0x180032c47  cmp     dword ptr [rax], 1
0x180032c4a  lea     this, [rax+8]; SRWLock
0x180032c4e  jnz     short loc_180032C58
0x180032c50  add     dword ptr [this], 10000000h
0x180032c56  jmp     short loc_180032C5E
0x180032c58  call    cs:__imp_ReleaseSRWLockExclusive
0x180032c5e  lea     this, [rbp+sOldValue]; initializedElement
0x180032c62  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x180032c67  mov     this, rbx; string
0x180032c6a  call    cs:__imp_WindowsDeleteString
0x180032c70  test    edi, edi
0x180032c72  js      short loc_180032C99
0x180032c74  mov     rax, [rbp+arg_8]
0x180032c78  mov     r9d, 2
0x180032c7e  movzx   edx, byte ptr [r14+99h]
0x180032c86  mov     r8, r14
0x180032c89  movzx   ecx, byte ptr [rbp+pPair]
0x180032c8d  mov     [rsp+40h+var_20], rax
0x180032c92  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x180032c97  mov     edi, eax
0x180032c99  mov     rbx, [rsp+40h+arg_0]
0x180032c9e  mov     eax, edi
0x180032ca0  add     rsp, 40h
0x180032ca4  pop     r15
0x180032ca6  pop     r14
0x180032ca8  pop     rdi
0x180032ca9  pop     rsi
0x180032caa  pop     rbp
0x180032cab  retn
```
