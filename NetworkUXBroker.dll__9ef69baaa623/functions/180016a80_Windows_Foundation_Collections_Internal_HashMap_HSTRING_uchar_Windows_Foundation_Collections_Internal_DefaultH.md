# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(HSTRING__ *,uchar,uchar *)

- ea: `0x180016a80`
- end: `0x180016bf1`
- name: `?Insert@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@EPEAE@Z`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800114dc`
- `0x1800138b0`
- `0x180013ca0`
- `0x180016a80`
- `0x1800173c4`
- `0x1800184a0`
- `0x1800194a0`
- `0x18001a140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016bd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016bd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180016abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180016abd`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Insert(
        __int64 a1,
        HSTRING a2,
        char a3,
        _BYTE *a4)
{
  HRESULT v8; // ebx
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  HSTRING newString; // [rsp+30h] [rbp-10h] BYREF
  RTL_SRWLOCK *v13; // [rsp+38h] [rbp-8h] BYREF
  __int64 v14; // [rsp+88h] [rbp+48h] BYREF

  *a4 = 0;
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized();
  newString = 0;
  v8 = WindowsDuplicateString(a2, &newString);
  if ( v8 >= 0 )
  {
    LODWORD(v14) = 0;
    XWinRT::SerializingLockPolicy::Write(&v13, a1 + 128, &v14);
    v8 = v14;
    if ( (int)v14 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v14, *(unsigned __int8 *)(a1 + 154), a1 + 156);
      XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
      v14 = 0;
      v8 = XWinRT::XHashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<unsigned char>>::Lookup(
             a1 + 40,
             &newString,
             &v14);
      if ( v8 >= 0 )
      {
        if ( v14 )
        {
          *(_BYTE *)(v14 + 8) = a3;
          *a4 = 1;
        }
        else if ( *(_QWORD *)(a1 + 56) == 0x7FFFFFFF )
        {
          v8 = -2147024882;
        }
        else
        {
          v14 = 0;
          LOBYTE(v9) = a3;
          v8 = XWinRT::XHashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<unsigned char>>::SetAt(
                 a1 + 40,
                 &newString,
                 v9,
                 &v14);
          if ( v8 >= 0 )
            newString = 0;
        }
      }
    }
    if ( v13 )
    {
      v10 = v13 + 1;
      if ( LODWORD(v13->Ptr) == 1 )
        LODWORD(v10->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v10);
    }
  }
  if ( v8 >= 0 )
    v8 = Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>::RaiseEvent(
           (unsigned __int8)v14,
           *(unsigned __int8 *)(a1 + 153),
           a1,
           *a4 != 0 ? 3 : 1,
           a2);
  WindowsDeleteString(newString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016a80  mov     [rsp-28h+arg_0], rbx
0x180016a85  mov     [rsp-28h+arg_8], rsi
0x180016a8a  push    rbp
0x180016a8b  push    rdi
0x180016a8c  push    r12
0x180016a8e  push    r14
0x180016a90  push    r15
0x180016a92  mov     rbp, rsp
0x180016a95  sub     rsp, 40h
0x180016a99  mov     rsi, r9
0x180016a9c  mov     byte ptr [r9], 0
0x180016aa0  mov     r14b, r8b
0x180016aa3  mov     r12, rdx
0x180016aa6  mov     rdi, rcx
0x180016aa9  call    ?EnsureInitialized@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::EnsureInitialized(void)
0x180016aae  lea     rdx, [rbp+newString]; newString
0x180016ab2  mov     [rbp+newString], 0
0x180016aba  mov     rcx, r12; string
0x180016abd  call    cs:__imp_WindowsDuplicateString
0x180016ac3  mov     ebx, eax
0x180016ac5  test    eax, eax
0x180016ac7  js      loc_180016BA2
0x180016acd  lea     rdx, [rdi+80h]
0x180016ad4  mov     dword ptr [rbp+arg_18], 0
0x180016adb  lea     r8, [rbp+arg_18]
0x180016adf  lea     rcx, [rbp+var_8]
0x180016ae3  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180016ae8  mov     ebx, dword ptr [rbp+arg_18]
0x180016aeb  test    ebx, ebx
0x180016aed  js      loc_180016B82
0x180016af3  movzx   edx, byte ptr [rdi+9Ah]
0x180016afa  lea     r8, [rdi+9Ch]
0x180016b01  lea     rcx, [rbp+arg_18]
0x180016b05  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180016b0a  lea     rcx, [rdi+90h]; this
0x180016b11  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x180016b16  lea     r8, [rbp+arg_18]
0x180016b1a  mov     [rbp+arg_18], 0
0x180016b22  lea     rdx, [rbp+newString]
0x180016b26  lea     rcx, [rdi+28h]
0x180016b2a  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::CPair * *)
0x180016b2f  mov     ebx, eax
0x180016b31  test    eax, eax
0x180016b33  js      short loc_180016B82
0x180016b35  mov     rax, [rbp+arg_18]
0x180016b39  test    rax, rax
0x180016b3c  jz      short loc_180016B47
0x180016b3e  mov     [rax+8], r14b
0x180016b42  mov     byte ptr [rsi], 1
0x180016b45  jmp     short loc_180016B82
0x180016b47  cmp     qword ptr [rdi+38h], 7FFFFFFFh
0x180016b4f  jnz     short loc_180016B58
0x180016b51  mov     ebx, 8007000Eh
0x180016b56  jmp     short loc_180016B82
0x180016b58  lea     r9, [rbp+arg_18]
0x180016b5c  mov     [rbp+arg_18], 0
0x180016b64  mov     r8b, r14b
0x180016b67  lea     rdx, [rbp+newString]
0x180016b6b  lea     rcx, [rdi+28h]
0x180016b6f  call    ?SetAt@?$XHashMap@PEAUHSTRING__@@EUKeyTraits@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@E@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@EPEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<uchar>>::SetAt(HSTRING__ * const &,uchar,XWinRT::TXPOSITION * *)
0x180016b74  mov     ebx, eax
0x180016b76  test    eax, eax
0x180016b78  js      short loc_180016B82
0x180016b7a  mov     [rbp+newString], 0
0x180016b82  mov     rax, [rbp+var_8]
0x180016b86  test    rax, rax
0x180016b89  jz      short loc_180016BA2
0x180016b8b  cmp     dword ptr [rax], 1
0x180016b8e  lea     rcx, [rax+8]; SRWLock
0x180016b92  jnz     short loc_180016B9C
0x180016b94  add     dword ptr [rcx], 10000000h
0x180016b9a  jmp     short loc_180016BA2
0x180016b9c  call    cs:__imp_ReleaseSRWLockExclusive
0x180016ba2  test    ebx, ebx
0x180016ba4  js      short loc_180016BCE
0x180016ba6  mov     al, [rsi]
0x180016ba8  mov     r8, rdi
0x180016bab  movzx   edx, byte ptr [rdi+99h]
0x180016bb2  neg     al
0x180016bb4  movzx   ecx, byte ptr [rbp+arg_18]
0x180016bb8  sbb     r9d, r9d
0x180016bbb  mov     [rsp+40h+var_20], r12
0x180016bc0  and     r9d, 2
0x180016bc4  inc     r9d
0x180016bc7  call    ?RaiseEvent@?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>::RaiseEvent(...)
0x180016bcc  mov     ebx, eax
0x180016bce  mov     rcx, [rbp+newString]; string
0x180016bd2  call    cs:__imp_WindowsDeleteString
0x180016bd8  mov     rsi, [rsp+40h+arg_8]
0x180016bdd  mov     eax, ebx
0x180016bdf  mov     rbx, [rsp+40h+arg_0]
0x180016be4  add     rsp, 40h
0x180016be8  pop     r15
0x180016bea  pop     r14
0x180016bec  pop     r12
0x180016bee  pop     rdi
0x180016bef  pop     rbp
0x180016bf0  retn
```
