# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,IInspectable *,uchar *)

- ea: `0x1800227c0`
- end: `0x180022987`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180017708`
- `0x180018268`
- `0x1800195d4`
- `0x18001c248`
- `0x18001d104`
- `0x18001e71c`
- `0x180020f44`
- `0x1800227c0`
- `0x180023198`
- `0x1800244e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002291d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002291d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800227ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800227ff`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  int v7; // edi
  __int64 v8; // r14
  __int64 v9; // rbx
  RTL_SRWLOCK *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-18h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h] BYREF
  RTL_SRWLOCK *v15; // [rsp+48h] [rbp-8h] BYREF
  __int64 v16; // [rsp+90h] [rbp+40h] BYREF
  __int64 v17; // [rsp+98h] [rbp+48h] BYREF

  v16 = a3;
  *a4 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  newString = 0;
  LODWORD(v17) = WindowsDuplicateString(a2, &newString);
  v7 = v17;
  if ( (int)v17 >= 0 )
  {
    XWinRT::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>(
      &v12,
      &v16,
      &v17);
    v7 = v17;
    v14 = 0;
    if ( (int)v17 < 0 )
    {
LABEL_16:
      XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&v14);
      XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&v12);
      goto LABEL_17;
    }
    XWinRT::SerializingLockPolicy::Write(&v15, a1 + 128, &v17);
    v7 = v17;
    if ( (int)v17 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v17, *(unsigned __int8 *)(a1 + 154), a1 + 156);
      XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
      v17 = 0;
      v7 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(
             a1 + 40,
             &newString,
             &v17);
      if ( v7 >= 0 )
      {
        v8 = v17;
        if ( v17 )
        {
          v9 = *(_QWORD *)(v17 + 8);
          XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(&v14);
          *(_QWORD *)(v8 + 8) = v12;
          *a4 = 1;
          v14 = v9;
LABEL_11:
          v12 = 0;
          goto LABEL_12;
        }
        if ( *(_QWORD *)(a1 + 56) == 0x7FFFFFFF )
        {
          v7 = -2147024882;
          goto LABEL_12;
        }
        v17 = 0;
        v7 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::SetAt(
               a1 + 40,
               &newString,
               &v12,
               &v17);
        if ( v7 >= 0 )
        {
          newString = 0;
          goto LABEL_11;
        }
      }
    }
LABEL_12:
    if ( v15 )
    {
      v10 = v15 + 1;
      if ( LODWORD(v15->Ptr) == 1 )
        LODWORD(v10->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v10);
    }
    goto LABEL_16;
  }
LABEL_17:
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(
           (unsigned __int8)v17,
           *(unsigned __int8 *)(a1 + 153),
           a1,
           *a4 != 0 ? 3 : 1,
           a2);
  WindowsDeleteString(newString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800227c0  mov     [rsp-28h+arg_0], rbx
0x1800227c5  mov     [rsp-28h+arg_8], rsi
0x1800227ca  mov     [rsp-28h+arg_10], r8
0x1800227cf  push    rbp
0x1800227d0  push    rdi
0x1800227d1  push    r12
0x1800227d3  push    r14
0x1800227d5  push    r15
0x1800227d7  mov     rbp, rsp
0x1800227da  sub     rsp, 50h
0x1800227de  mov     r15, r9
0x1800227e1  mov     byte ptr [r9], 0
0x1800227e5  mov     r12, rdx
0x1800227e8  mov     rsi, rcx
0x1800227eb  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x1800227f0  lea     rdx, [rbp+newString]; newString
0x1800227f4  mov     [rbp+newString], 0
0x1800227fc  mov     rcx, r12; string
0x1800227ff  call    cs:__imp_WindowsDuplicateString
0x180022805  mov     dword ptr [rbp+arg_18], eax
0x180022808  mov     edi, eax
0x18002280a  test    eax, eax
0x18002280c  js      loc_180022935
0x180022812  lea     r8, [rbp+arg_18]
0x180022816  lea     rdx, [rbp+arg_10]
0x18002281a  lea     rcx, [rbp+var_20]
0x18002281e  call    ??$?0PEAUIInspectable@@@?$AutoValue@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUIInspectable@@PEAJ@Z; XWinRT::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>(IInspectable * const &,long *)
0x180022823  mov     edi, dword ptr [rbp+arg_18]
0x180022826  mov     [rbp+var_10], 0
0x18002282e  test    edi, edi
0x180022830  js      loc_180022923
0x180022836  lea     rdx, [rsi+80h]
0x18002283d  lea     r8, [rbp+arg_18]
0x180022841  lea     rcx, [rbp+var_8]
0x180022845  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18002284a  mov     edi, dword ptr [rbp+arg_18]
0x18002284d  test    edi, edi
0x18002284f  js      loc_180022903
0x180022855  movzx   edx, byte ptr [rsi+9Ah]
0x18002285c  lea     r8, [rsi+9Ch]
0x180022863  lea     rcx, [rbp+arg_18]
0x180022867  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18002286c  lea     rcx, [rsi+90h]; this
0x180022873  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180022878  lea     r8, [rbp+arg_18]
0x18002287c  mov     [rbp+arg_18], 0
0x180022884  lea     rdx, [rbp+newString]
0x180022888  lea     rcx, [rsi+28h]
0x18002288c  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x180022891  mov     edi, eax
0x180022893  test    eax, eax
0x180022895  js      short loc_180022903
0x180022897  mov     r14, [rbp+arg_18]
0x18002289b  test    r14, r14
0x18002289e  jz      short loc_1800228BF
0x1800228a0  mov     rbx, [r14+8]
0x1800228a4  lea     rcx, [rbp+var_10]
0x1800228a8  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x1800228ad  mov     rax, [rbp+var_20]
0x1800228b1  mov     [r14+8], rax
0x1800228b5  mov     byte ptr [r15], 1
0x1800228b9  mov     [rbp+var_10], rbx
0x1800228bd  jmp     short loc_1800228FB
0x1800228bf  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x1800228c7  jnz     short loc_1800228D0
0x1800228c9  mov     edi, 8007000Eh
0x1800228ce  jmp     short loc_180022903
0x1800228d0  lea     r9, [rbp+arg_18]
0x1800228d4  mov     [rbp+arg_18], 0
0x1800228dc  lea     r8, [rbp+var_20]
0x1800228e0  lea     rdx, [rbp+newString]
0x1800228e4  lea     rcx, [rsi+28h]
0x1800228e8  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBQEAUIInspectable@@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::SetAt(HSTRING__ * const &,IInspectable * const &,XWinRT::TXPOSITION * *)
0x1800228ed  mov     edi, eax
0x1800228ef  test    eax, eax
0x1800228f1  js      short loc_180022903
0x1800228f3  mov     [rbp+newString], 0
0x1800228fb  mov     [rbp+var_20], 0
0x180022903  mov     rax, [rbp+var_8]
0x180022907  test    rax, rax
0x18002290a  jz      short loc_180022923
0x18002290c  cmp     dword ptr [rax], 1
0x18002290f  lea     rcx, [rax+8]; SRWLock
0x180022913  jnz     short loc_18002291D
0x180022915  add     dword ptr [rcx], 10000000h
0x18002291b  jmp     short loc_180022923
0x18002291d  call    cs:__imp_ReleaseSRWLockExclusive
0x180022923  lea     rcx, [rbp+var_10]
0x180022927  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18002292c  lea     rcx, [rbp+var_20]
0x180022930  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x180022935  test    edi, edi
0x180022937  js      short loc_180022962
0x180022939  mov     al, [r15]
0x18002293c  mov     r8, rsi
0x18002293f  movzx   edx, byte ptr [rsi+99h]
0x180022946  neg     al
0x180022948  movzx   ecx, byte ptr [rbp+arg_18]
0x18002294c  sbb     r9d, r9d
0x18002294f  mov     [rsp+50h+var_30], r12
0x180022954  and     r9d, 2
0x180022958  inc     r9d
0x18002295b  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x180022960  mov     edi, eax
0x180022962  mov     rcx, [rbp+newString]; string
0x180022966  call    cs:__imp_WindowsDeleteString
0x18002296c  lea     r11, [rsp+50h+var_s0]
0x180022971  mov     eax, edi
0x180022973  mov     rbx, [r11+30h]
0x180022977  mov     rsi, [r11+38h]
0x18002297b  mov     rsp, r11
0x18002297e  pop     r15
0x180022980  pop     r14
0x180022982  pop     r12
0x180022984  pop     rdi
0x180022985  pop     rbp
0x180022986  retn
```
