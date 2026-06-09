# OSIntegration::DEH::Internal::AddStringAttribute(Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>,Windows::Internal::String const &,Windows::Internal::String const &)

- ea: `0x18003a198`
- end: `0x18003a7a1`
- name: `?AddStringAttribute@Internal@DEH@OSIntegration@@YA_NV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@V?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAU1@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@3@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U56789@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@@56@V?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@@56@AEBVString@1Windows@@3@Z`
- size: `1545`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003a0f0`
- `0x18016b210`

## callees

- `0x180006970`
- `0x18003a198`
- `0x180073fc4`
- `0x180074000`
- `0x180074248`
- `0x180074504`
- `0x18008a740`
- `0x1800d7ad0`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003a1d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003a2e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003a1d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003a2e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003a2bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003a2fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003a2bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003a2fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003a2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003a2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a5f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a61e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a5f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a61e`

## string_xrefs

- `0x18003a5ac`: `nameCollisionMap->Remove(keyName)`
- `0x18003a70b`: `propertyValueFactory->CreateString(value, &propValue)`
- `0x18003a763`: `attributes->Insert(keyName.Get(), propValue.Get(), &replaced)`
- `0x18003a6de`: `nameCollisionMap->Insert(keyName, keyName, &replaced)`

## pseudocode

```c

```
