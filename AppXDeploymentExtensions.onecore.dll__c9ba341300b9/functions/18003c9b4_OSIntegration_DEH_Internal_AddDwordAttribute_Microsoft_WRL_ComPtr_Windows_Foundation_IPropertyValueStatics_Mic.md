# OSIntegration::DEH::Internal::AddDwordAttribute(Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>,Windows::Internal::String const &,ulong)

- ea: `0x18003c9b4`
- end: `0x18003cf31`
- name: `?AddDwordAttribute@Internal@DEH@OSIntegration@@YA_NV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@V?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAU1@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@3@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U56789@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@@56@V?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@@56@AEBVString@1Windows@@K@Z`
- size: `1405`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003c910`
- `0x1801d8770`

## callees

- `0x18000b3bc`
- `0x18001b84c`
- `0x18003c9b4`
- `0x180049b4c`
- `0x180098ed0`
- `0x1800ce018`
- `0x18012ba10`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003ca08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003ca82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003ca08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003ca82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003c9fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003c9fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003c9ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003c9ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cc98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ce41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cc98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ce41`

## string_xrefs

- `0x18003ce9a`: `propertyValueFactory->CreateUInt32(value, &propValue)`
- `0x18003cc0b`: `nameCollisionMap->Remove(keyName)`
- `0x18003cef3`: `attributes->Insert(keyName.Get(), propValue.Get(), &replaced)`
- `0x18003ce69`: `nameCollisionMap->Insert(keyName, keyName, &replaced)`

## pseudocode

```c

```
