# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,IInspectable *,uchar *)

- ea: `0x180048630`
- end: `0x1800487f7`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x18000ca48`
- `0x18000ca64`
- `0x18000dde0`
- `0x180018480`
- `0x18001cf8c`
- `0x18003e460`
- `0x1800457a4`
- `0x180048630`
- `0x180048ed8`
- `0x18004b050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004878d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004878d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004866f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004866f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800487d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800487d6`

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
0x180048630  mov     [rsp-28h+arg_0], rbx
0x180048635  mov     [rsp-28h+arg_8], rsi
0x18004863a  mov     [rsp-28h+arg_10], r8
0x18004863f  push    rbp
0x180048640  push    rdi
0x180048641  push    r12
0x180048643  push    r14
0x180048645  push    r15
0x180048647  mov     rbp, rsp
0x18004864a  sub     rsp, 50h
0x18004864e  mov     r15, r9
0x180048651  mov     byte ptr [r9], 0
0x180048655  mov     r12, rdx
0x180048658  mov     rsi, rcx
0x18004865b  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x180048660  lea     rdx, [rbp+newString]; newString
0x180048664  mov     [rbp+newString], 0
0x18004866c  mov     rcx, r12; string
0x18004866f  call    cs:__imp_WindowsDuplicateString
0x180048675  mov     dword ptr [rbp+arg_18], eax
0x180048678  mov     edi, eax
0x18004867a  test    eax, eax
0x18004867c  js      loc_1800487A5
0x180048682  lea     r8, [rbp+arg_18]
0x180048686  lea     rdx, [rbp+arg_10]
0x18004868a  lea     rcx, [rbp+var_20]
0x18004868e  call    ??$?0PEAUIInspectable@@@?$AutoValue@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUIInspectable@@PEAJ@Z; XWinRT::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>(IInspectable * const &,long *)
0x180048693  mov     edi, dword ptr [rbp+arg_18]
0x180048696  mov     [rbp+var_10], 0
0x18004869e  test    edi, edi
0x1800486a0  js      loc_180048793
0x1800486a6  lea     rdx, [rsi+80h]
0x1800486ad  lea     r8, [rbp+arg_18]
0x1800486b1  lea     rcx, [rbp+var_8]
0x1800486b5  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800486ba  mov     edi, dword ptr [rbp+arg_18]
0x1800486bd  test    edi, edi
0x1800486bf  js      loc_180048773
0x1800486c5  movzx   edx, byte ptr [rsi+9Ah]
0x1800486cc  lea     r8, [rsi+9Ch]
0x1800486d3  lea     rcx, [rbp+arg_18]
0x1800486d7  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x1800486dc  lea     rcx, [rsi+90h]; this
0x1800486e3  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1800486e8  lea     r8, [rbp+arg_18]
0x1800486ec  mov     [rbp+arg_18], 0
0x1800486f4  lea     rdx, [rbp+newString]
0x1800486f8  lea     rcx, [rsi+28h]
0x1800486fc  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x180048701  mov     edi, eax
0x180048703  test    eax, eax
0x180048705  js      short loc_180048773
0x180048707  mov     r14, [rbp+arg_18]
0x18004870b  test    r14, r14
0x18004870e  jz      short loc_18004872F
0x180048710  mov     rbx, [r14+8]
0x180048714  lea     rcx, [rbp+var_10]
0x180048718  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18004871d  mov     rax, [rbp+var_20]
0x180048721  mov     [r14+8], rax
0x180048725  mov     byte ptr [r15], 1
0x180048729  mov     [rbp+var_10], rbx
0x18004872d  jmp     short loc_18004876B
0x18004872f  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x180048737  jnz     short loc_180048740
0x180048739  mov     edi, 8007000Eh
0x18004873e  jmp     short loc_180048773
0x180048740  lea     r9, [rbp+arg_18]
0x180048744  mov     [rbp+arg_18], 0
0x18004874c  lea     r8, [rbp+var_20]
0x180048750  lea     rdx, [rbp+newString]
0x180048754  lea     rcx, [rsi+28h]
0x180048758  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBQEAUIInspectable@@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::SetAt(HSTRING__ * const &,IInspectable * const &,XWinRT::TXPOSITION * *)
0x18004875d  mov     edi, eax
0x18004875f  test    eax, eax
0x180048761  js      short loc_180048773
0x180048763  mov     [rbp+newString], 0
0x18004876b  mov     [rbp+var_20], 0
0x180048773  mov     rax, [rbp+var_8]
0x180048777  test    rax, rax
0x18004877a  jz      short loc_180048793
0x18004877c  cmp     dword ptr [rax], 1
0x18004877f  lea     rcx, [rax+8]; SRWLock
0x180048783  jnz     short loc_18004878D
0x180048785  add     dword ptr [rcx], 10000000h
0x18004878b  jmp     short loc_180048793
0x18004878d  call    cs:__imp_ReleaseSRWLockExclusive
0x180048793  lea     rcx, [rbp+var_10]
0x180048797  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18004879c  lea     rcx, [rbp+var_20]
0x1800487a0  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x1800487a5  test    edi, edi
0x1800487a7  js      short loc_1800487D2
0x1800487a9  mov     al, [r15]
0x1800487ac  mov     r8, rsi
0x1800487af  movzx   edx, byte ptr [rsi+99h]
0x1800487b6  neg     al
0x1800487b8  movzx   ecx, byte ptr [rbp+arg_18]
0x1800487bc  sbb     r9d, r9d
0x1800487bf  mov     [rsp+50h+var_30], r12
0x1800487c4  and     r9d, 2
0x1800487c8  inc     r9d
0x1800487cb  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>::RaiseEvent(...)
0x1800487d0  mov     edi, eax
0x1800487d2  mov     rcx, [rbp+newString]; string
0x1800487d6  call    cs:__imp_WindowsDeleteString
0x1800487dc  lea     r11, [rsp+50h+var_s0]
0x1800487e1  mov     eax, edi
0x1800487e3  mov     rbx, [r11+30h]
0x1800487e7  mov     rsi, [r11+38h]
0x1800487eb  mov     rsp, r11
0x1800487ee  pop     r15
0x1800487f0  pop     r14
0x1800487f2  pop     r12
0x1800487f4  pop     rdi
0x1800487f5  pop     rbp
0x1800487f6  retn
```
