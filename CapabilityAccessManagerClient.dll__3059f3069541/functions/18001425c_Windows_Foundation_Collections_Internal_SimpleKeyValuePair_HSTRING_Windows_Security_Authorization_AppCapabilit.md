# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::~SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>(void)

- ea: `0x18001425c`
- end: `0x180014284`
- name: `??1?$SimpleKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$00@Internal@Collections@Foundation@Windows@@UEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014ce0`

## callees

- `0x1800141cc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014269`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::~SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>(
        __int64 a1)
{
  WindowsDeleteString(*(HSTRING *)(a1 + 64));
  *(_QWORD *)(a1 + 64) = 0;
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::FtmBase>(a1);
}

```

## disassembly

```asm
0x18001425c  push    rbx
0x18001425e  sub     rsp, 20h
0x180014262  mov     rbx, rcx
0x180014265  mov     rcx, [rcx+40h]; string
0x180014269  call    cs:__imp_WindowsDeleteString
0x18001426f  mov     rcx, rbx
0x180014272  mov     qword ptr [rbx+40h], 0
0x18001427a  add     rsp, 20h
0x18001427e  pop     rbx
0x18001427f  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::FtmBase>(void)
```
