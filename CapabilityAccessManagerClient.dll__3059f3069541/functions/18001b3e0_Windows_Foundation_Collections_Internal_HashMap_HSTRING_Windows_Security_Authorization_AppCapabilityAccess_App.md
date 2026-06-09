# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::_Free(XWinRT::XHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>> *)

- ea: `0x18001b3e0`
- end: `0x18001b43c`
- name: `?_Free@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@CAXPEAV?$XHashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@XWinRT@@@XWinRT@@@Z`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015540`
- `0x18001b284`

## callees

- `0x180017068`
- `0x180017650`
- `0x180019ec0`
- `0x18001b3e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b414`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b414`

## pseudocode

```c
void __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::_Free(
        __int64 a1)
{
  HSTRING *Next; // rbx
  bool v3; // zf
  __int64 StartPosition; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    StartPosition = XWinRT::XHashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::GetStartPosition(a1);
    if ( StartPosition )
    {
      do
      {
        Next = (HSTRING *)XWinRT::XHashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::GetNext(
                            a1,
                            &StartPosition);
        WindowsDeleteString(*Next);
        v3 = StartPosition == 0;
        *Next = 0;
      }
      while ( !v3 );
    }
    XWinRT::XHashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::RemoveAll(a1);
  }
}

```

## disassembly

```asm
0x18001b3e0  test    rcx, rcx
0x18001b3e3  jz      short locret_18001B43B
0x18001b3e5  mov     [rsp+arg_8], rbx
0x18001b3ea  push    rdi
0x18001b3eb  sub     rsp, 20h
0x18001b3ef  mov     rdi, rcx
0x18001b3f2  call    ?GetStartPosition@?$XHashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@XWinRT@@@XWinRT@@QEBAPEAUTXPOSITION@2@XZ; XWinRT::XHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::GetStartPosition(void)
0x18001b3f7  mov     [rsp+28h+arg_0], rax
0x18001b3fc  test    rax, rax
0x18001b3ff  jz      short loc_18001B429
0x18001b401  lea     rdx, [rsp+28h+arg_0]
0x18001b406  mov     rcx, rdi
0x18001b409  call    ?GetNext@?$XHashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@XWinRT@@@XWinRT@@QEAAPEAVCPair@12@AEAPEAUTXPOSITION@2@@Z; XWinRT::XHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::GetNext(XWinRT::TXPOSITION * &)
0x18001b40e  mov     rbx, rax
0x18001b411  mov     rcx, [rax]; string
0x18001b414  call    cs:__imp_WindowsDeleteString
0x18001b41a  cmp     [rsp+28h+arg_0], 0
0x18001b420  mov     qword ptr [rbx], 0
0x18001b427  jnz     short loc_18001B401
0x18001b429  mov     rcx, rdi
0x18001b42c  call    ?RemoveAll@?$XHashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@UKeyTraits@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@6@V?$CElementTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@XWinRT@@@XWinRT@@QEAAJXZ; XWinRT::XHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::RemoveAll(void)
0x18001b431  mov     rbx, [rsp+28h+arg_8]
0x18001b436  add     rsp, 20h
0x18001b43a  pop     rdi
0x18001b43b  retn
```
