# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800174c0`
- end: `0x1800174dd`
- name: `?GetRuntimeClassName@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800174f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800174d6`

## string_xrefs

- `0x1800174c7`: `Windows.Foundation.Collections.IMap`2<String, Windows.Security.Authorization.AppCapabilityAccess.AppCapabilityAccessStatus>`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(
           L"Windows.Foundation.Collections.IMap`2<String, Windows.Security.Authorization.AppCapabilityAccess.AppCapabilityAccessStatus>",
           0x7Bu,
           a2);
}

```

## disassembly

```asm
0x1800174c0  mov     qword ptr [rdx], 0
0x1800174c7  lea     rcx, aWindowsFoundat_4; "Windows.Foundation.Collections.IMap`2<S"...
0x1800174ce  mov     r8, rdx
0x1800174d1  mov     edx, 7Bh ; '{'
0x1800174d6  jmp     cs:__imp_WindowsCreateString
```
