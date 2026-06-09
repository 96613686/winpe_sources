# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x180027b50`
- end: `0x180027d02`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180024510`
- `0x180025210`
- `0x180025f6c`
- `0x1800265c8`
- `0x180027b50`
- `0x180027fa8`
- `0x180028eac`
- `0x180029bc0`
- `0x18002a068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027c98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027c98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027c2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027cab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027ce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027c2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027cab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027ce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180027b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180027b8d`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        _BYTE *a4)
{
  int v7; // ebx
  HSTRING v8; // rdi
  __int64 v9; // r14
  RTL_SRWLOCK *v10; // rcx
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-18h] BYREF
  RTL_SRWLOCK *v14; // [rsp+40h] [rbp-10h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+58h] BYREF

  *a4 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  newString = 0;
  LODWORD(v15) = WindowsDuplicateString(a2, &newString);
  v7 = v15;
  if ( (int)v15 >= 0 )
  {
    XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&string);
    v7 = v15;
    v8 = 0;
    if ( (int)v15 >= 0 )
    {
      XWinRT::SerializingLockPolicy::Write(&v14, a1 + 128, &v15);
      v7 = v15;
      if ( (int)v15 >= 0 )
      {
        XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v15, *(unsigned __int8 *)(a1 + 154), a1 + 156);
        XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
        v15 = 0;
        v7 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(
               a1 + 40,
               &newString,
               &v15);
        if ( v7 >= 0 )
        {
          v9 = v15;
          if ( v15 )
          {
            v8 = *(HSTRING *)(v15 + 8);
            WindowsDeleteString(0);
            *(_QWORD *)(v9 + 8) = string;
            string = 0;
            *a4 = 1;
          }
          else if ( *(_QWORD *)(a1 + 56) == 0x7FFFFFFF )
          {
            v7 = -2147024882;
          }
          else
          {
            v15 = 0;
            v7 = XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::SetAt(
                   a1 + 40,
                   &newString,
                   &string,
                   &v15);
            if ( v7 >= 0 )
            {
              newString = 0;
              string = 0;
            }
          }
        }
      }
      if ( v14 )
      {
        v10 = v14 + 1;
        if ( LODWORD(v14->Ptr) == 1 )
          LODWORD(v10->Ptr) += 0x10000000;
        else
          ReleaseSRWLockExclusive(v10);
      }
    }
    WindowsDeleteString(v8);
    WindowsDeleteString(string);
  }
  if ( v7 >= 0 )
    v7 = Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration,0,0,0>::RaiseEvent(
           (unsigned __int8)v15,
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
0x180027b50  mov     [rsp-38h+arg_0], rbx
0x180027b55  mov     [rsp-38h+arg_10], r8
0x180027b5a  push    rbp
0x180027b5b  push    rsi
0x180027b5c  push    rdi
0x180027b5d  push    r12
0x180027b5f  push    r13
0x180027b61  push    r14
0x180027b63  push    r15
0x180027b65  mov     rbp, rsp
0x180027b68  sub     rsp, 50h
0x180027b6c  mov     r15, r9
0x180027b6f  mov     byte ptr [r9], 0
0x180027b73  mov     r13, rdx
0x180027b76  mov     rsi, rcx
0x180027b79  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x180027b7e  lea     rdx, [rbp+newString]; newString
0x180027b82  mov     [rbp+newString], 0
0x180027b8a  mov     rcx, r13; string
0x180027b8d  call    cs:__imp_WindowsDuplicateString
0x180027b93  mov     dword ptr [rbp+arg_18], eax
0x180027b96  mov     ebx, eax
0x180027b98  test    eax, eax
0x180027b9a  js      loc_180027CB1
0x180027ba0  lea     r8, [rbp+arg_18]
0x180027ba4  lea     rdx, [rbp+arg_10]
0x180027ba8  lea     rcx, [rbp+string]; newString
0x180027bac  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x180027bb1  mov     ebx, dword ptr [rbp+arg_18]
0x180027bb4  xor     edi, edi
0x180027bb6  test    ebx, ebx
0x180027bb8  js      loc_180027C9E
0x180027bbe  lea     rdx, [rsi+80h]
0x180027bc5  lea     r8, [rbp+arg_18]
0x180027bc9  lea     rcx, [rbp+var_10]
0x180027bcd  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180027bd2  mov     ebx, dword ptr [rbp+arg_18]
0x180027bd5  test    ebx, ebx
0x180027bd7  js      loc_180027C7E
0x180027bdd  movzx   edx, byte ptr [rsi+9Ah]
0x180027be4  lea     r8, [rsi+9Ch]
0x180027beb  lea     rcx, [rbp+arg_18]
0x180027bef  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180027bf4  lea     rcx, [rsi+90h]; this
0x180027bfb  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180027c00  lea     r8, [rbp+arg_18]
0x180027c04  mov     [rbp+arg_18], rdi
0x180027c08  lea     rdx, [rbp+newString]
0x180027c0c  lea     rcx, [rsi+28h]
0x180027c10  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CPair * *)
0x180027c15  mov     ebx, eax
0x180027c17  test    eax, eax
0x180027c19  js      short loc_180027C7E
0x180027c1b  mov     r14, [rbp+arg_18]
0x180027c1f  test    r14, r14
0x180027c22  jz      short loc_180027C46
0x180027c24  mov     rdi, [r14+8]
0x180027c28  xor     ecx, ecx; string
0x180027c2a  call    cs:__imp_WindowsDeleteString
0x180027c30  mov     rax, [rbp+string]
0x180027c34  mov     [r14+8], rax
0x180027c38  mov     [rbp+string], 0
0x180027c40  mov     byte ptr [r15], 1
0x180027c44  jmp     short loc_180027C7E
0x180027c46  cmp     qword ptr [rsi+38h], 7FFFFFFFh
0x180027c4e  jnz     short loc_180027C57
0x180027c50  mov     ebx, 8007000Eh
0x180027c55  jmp     short loc_180027C7E
0x180027c57  lea     r9, [rbp+arg_18]
0x180027c5b  mov     [rbp+arg_18], rdi
0x180027c5f  lea     r8, [rbp+string]
0x180027c63  lea     rdx, [rbp+newString]
0x180027c67  lea     rcx, [rsi+28h]
0x180027c6b  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@0PEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::SetAt(HSTRING__ * const &,HSTRING__ * const &,XWinRT::TXPOSITION * *)
0x180027c70  mov     ebx, eax
0x180027c72  test    eax, eax
0x180027c74  js      short loc_180027C7E
0x180027c76  mov     [rbp+newString], rdi
0x180027c7a  mov     [rbp+string], rdi
0x180027c7e  mov     rax, [rbp+var_10]
0x180027c82  test    rax, rax
0x180027c85  jz      short loc_180027C9E
0x180027c87  cmp     dword ptr [rax], 1
0x180027c8a  lea     rcx, [rax+8]; SRWLock
0x180027c8e  jnz     short loc_180027C98
0x180027c90  add     dword ptr [rcx], 10000000h
0x180027c96  jmp     short loc_180027C9E
0x180027c98  call    cs:__imp_ReleaseSRWLockExclusive
0x180027c9e  mov     rcx, rdi; string
0x180027ca1  call    cs:__imp_WindowsDeleteString
0x180027ca7  mov     rcx, [rbp+string]; string
0x180027cab  call    cs:__imp_WindowsDeleteString
0x180027cb1  test    ebx, ebx
0x180027cb3  js      short loc_180027CDE
0x180027cb5  mov     al, [r15]
0x180027cb8  mov     r8, rsi
0x180027cbb  movzx   edx, byte ptr [rsi+99h]
0x180027cc2  neg     al
0x180027cc4  movzx   ecx, byte ptr [rbp+arg_18]
0x180027cc8  sbb     r9d, r9d
0x180027ccb  mov     [rsp+50h+var_30], r13
0x180027cd0  and     r9d, 2
0x180027cd4  inc     r9d
0x180027cd7  call    ?RaiseEvent@?$VectorOptions@UVariantConfiguration@FeatureConfiguration@Flighting@Internal@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration,0,0,0>::RaiseEvent(...)
0x180027cdc  mov     ebx, eax
0x180027cde  mov     rcx, [rbp+newString]; string
0x180027ce2  call    cs:__imp_WindowsDeleteString
0x180027ce8  mov     eax, ebx
0x180027cea  mov     rbx, [rsp+50h+arg_0]
0x180027cf2  add     rsp, 50h
0x180027cf6  pop     r15
0x180027cf8  pop     r14
0x180027cfa  pop     r13
0x180027cfc  pop     r12
0x180027cfe  pop     rdi
0x180027cff  pop     rsi
0x180027d00  pop     rbp
0x180027d01  retn
```
