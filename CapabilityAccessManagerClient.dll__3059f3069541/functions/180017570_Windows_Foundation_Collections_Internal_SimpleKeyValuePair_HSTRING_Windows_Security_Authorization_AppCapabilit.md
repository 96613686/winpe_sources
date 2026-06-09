# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180017570`
- end: `0x18001758d`
- name: `?GetRuntimeClassName@?$SimpleKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017586`

## string_xrefs

- `0x180017577`: `Windows.Foundation.Collections.IKeyValuePair`2<String, Windows.Security.Authorization.AppCapabilityAccess.AppCapabilityAccessStatus>`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(
           L"Windows.Foundation.Collections.IKeyValuePair`2<String, Windows.Security.Authorization.AppCapabilityAccess.App"
            "CapabilityAccessStatus>",
           0x84u,
           a2);
}

```

## disassembly

```asm
0x180017570  mov     qword ptr [rdx], 0
0x180017577  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IKeyValu"...
0x18001757e  mov     r8, rdx
0x180017581  mov     edx, 84h
0x180017586  jmp     cs:__imp_WindowsCreateString
```
