# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,IInspectable *,uchar *)

- ea: `0x18001f4a0`
- end: `0x18001f668`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x18001b868`
- `0x18001b9e4`
- `0x18001c848`
- `0x18001d4a8`
- `0x18001d798`
- `0x18001f4a0`
- `0x18001f8f8`
- `0x180020560`
- `0x180020dbc`
- `0x180021274`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f5fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f5fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001f4df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001f4df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  HRESULT v7; // edi
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
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  newString = 0;
  v7 = WindowsDuplicateString(a2, &newString);
  LODWORD(v17) = v7;
  if ( v7 >= 0 )
  {
    XWinRT::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>(
      &v12,
      &v16,
      &v17);
    v14 = 0;
    v7 = v17;
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
          v14 = v9;
          *(_QWORD *)(v8 + 8) = v12;
          *a4 = 1;
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
    v7 = Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(
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
0x18001f4a0  mov     [rsp-28h+arg_0], rbx
0x18001f4a5  mov     [rsp-28h+arg_8], rsi
0x18001f4aa  mov     [rsp-28h+arg_10], r8
0x18001f4af  push    rbp
0x18001f4b0  push    rdi
0x18001f4b1  push    r12
0x18001f4b3  push    r14
0x18001f4b5  push    r15
0x18001f4b7  mov     rbp, rsp
0x18001f4ba  sub     rsp, 50h
0x18001f4be  mov     r15, r9
0x18001f4c1  mov     r12, rdx
0x18001f4c4  mov     rsi, rcx
0x18001f4c7  mov     byte ptr [r9], 0
0x18001f4cb  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x18001f4d0  mov     [rbp+newString], 0
0x18001f4d8  lea     rdx, [rbp+newString]; newString
0x18001f4dc  mov     rcx, r12; string
0x18001f4df  call    cs:__imp_WindowsDuplicateString
0x18001f4e5  mov     edi, eax
0x18001f4e7  mov     dword ptr [rbp+arg_18], eax
0x18001f4ea  test    eax, eax
0x18001f4ec  js      loc_18001F616
0x18001f4f2  lea     r8, [rbp+arg_18]
0x18001f4f6  lea     rdx, [rbp+arg_10]
0x18001f4fa  lea     rcx, [rbp+var_20]
0x18001f4fe  call    ??$?0PEAUIInspectable@@@?$AutoValue@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUIInspectable@@PEAJ@Z; XWinRT::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>::AutoValue<IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>(IInspectable * const &,long *)
0x18001f503  mov     [rbp+var_10], 0
0x18001f50b  mov     edi, dword ptr [rbp+arg_18]
0x18001f50e  test    edi, edi
0x18001f510  js      loc_18001F604
0x18001f516  lea     rdx, [rsi+80h]
0x18001f51d  lea     r8, [rbp+arg_18]
0x18001f521  lea     rcx, [rbp+var_8]
0x18001f525  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x18001f52a  mov     edi, dword ptr [rbp+arg_18]
0x18001f52d  test    edi, edi
0x18001f52f  js      loc_18001F5E3
0x18001f535  lea     r8, [rsi+9Ch]
0x18001f53c  movzx   edx, byte ptr [rsi+9Ah]
0x18001f543  lea     rcx, [rbp+arg_18]
0x18001f547  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18001f54c  lea     rcx, [rsi+90h]; this
0x18001f553  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x18001f558  mov     [rbp+arg_18], 0
0x18001f560  lea     r8, [rbp+arg_18]
0x18001f564  lea     rdx, [rbp+newString]
0x18001f568  lea     rcx, [rsi+28h]
0x18001f56c  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x18001f571  mov     edi, eax
0x18001f573  test    eax, eax
0x18001f575  js      short loc_18001F5E3
0x18001f577  mov     r14, [rbp+arg_18]
0x18001f57b  test    r14, r14
0x18001f57e  jz      short loc_18001F59F
0x18001f580  mov     rbx, [r14+8]
0x18001f584  lea     rcx, [rbp+var_10]
0x18001f588  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18001f58d  mov     [rbp+var_10], rbx
0x18001f591  mov     rax, [rbp+var_20]
0x18001f595  mov     [r14+8], rax
0x18001f599  mov     byte ptr [r15], 1
0x18001f59d  jmp     short loc_18001F5DB
0x18001f59f  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x18001f5a7  jnz     short loc_18001F5B0
0x18001f5a9  mov     edi, 8007000Eh
0x18001f5ae  jmp     short loc_18001F5E3
0x18001f5b0  mov     [rbp+arg_18], 0
0x18001f5b8  lea     r9, [rbp+arg_18]
0x18001f5bc  lea     r8, [rbp+var_20]
0x18001f5c0  lea     rdx, [rbp+newString]
0x18001f5c4  lea     rcx, [rsi+28h]
0x18001f5c8  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@AEBQEAUIInspectable@@PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::SetAt(HSTRING__ * const &,IInspectable * const &,XWinRT::TXPOSITION * *)
0x18001f5cd  mov     edi, eax
0x18001f5cf  test    eax, eax
0x18001f5d1  js      short loc_18001F5E3
0x18001f5d3  mov     [rbp+newString], 0
0x18001f5db  mov     [rbp+var_20], 0
0x18001f5e3  mov     rax, [rbp+var_8]
0x18001f5e7  test    rax, rax
0x18001f5ea  jz      short loc_18001F604
0x18001f5ec  lea     rcx, [rax+8]; SRWLock
0x18001f5f0  cmp     dword ptr [rax], 1
0x18001f5f3  jnz     short loc_18001F5FD
0x18001f5f5  add     dword ptr [rcx], 10000000h
0x18001f5fb  jmp     short loc_18001F604
0x18001f5fd  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f603  nop
0x18001f604  lea     rcx, [rbp+var_10]
0x18001f608  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18001f60d  lea     rcx, [rbp+var_20]
0x18001f611  call    ??$Destroy@UIInspectable@@@InterfaceLifetimeTraits@XWinRT@@SAXPEAPEAUIInspectable@@@Z; XWinRT::InterfaceLifetimeTraits::Destroy<IInspectable>(IInspectable * *)
0x18001f616  test    edi, edi
0x18001f618  js      short loc_18001F643
0x18001f61a  mov     al, [r15]
0x18001f61d  neg     al
0x18001f61f  sbb     r9d, r9d
0x18001f622  and     r9d, 2
0x18001f626  inc     r9d
0x18001f629  mov     [rsp+50h+var_30], r12
0x18001f62e  mov     r8, rsi
0x18001f631  movzx   edx, byte ptr [rsi+99h]
0x18001f638  movzx   ecx, byte ptr [rbp+arg_18]
0x18001f63c  call    ?RaiseEvent@?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,0,0>::RaiseEvent(...)
0x18001f641  mov     edi, eax
0x18001f643  mov     rcx, [rbp+newString]; string
0x18001f647  call    cs:__imp_WindowsDeleteString
0x18001f64d  mov     eax, edi
0x18001f64f  lea     r11, [rsp+50h+var_s0]
0x18001f654  mov     rbx, [r11+30h]
0x18001f658  mov     rsi, [r11+38h]
0x18001f65c  mov     rsp, r11
0x18001f65f  pop     r15
0x18001f661  pop     r14
0x18001f663  pop     r12
0x18001f665  pop     rdi
0x18001f666  pop     rbp
0x18001f667  retn
```
