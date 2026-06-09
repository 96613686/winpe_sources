# OSIntegration::DEH::Internal::AddStringAttribute(Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>,Windows::Internal::String const &,Windows::Internal::String const &)

- ea: `0x180061f04`
- end: `0x180062489`
- name: `?AddStringAttribute@Internal@DEH@OSIntegration@@YA_NV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@V?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAU1@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@3@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U56789@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@@56@V?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@@56@AEBVString@1Windows@@3@Z`
- size: `1413`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180061e60`
- `0x1801d86d0`

## callees

- `0x18000b3bc`
- `0x18001b84c`
- `0x180049b4c`
- `0x180061f04`
- `0x180098ed0`
- `0x1800ce018`
- `0x18012ba10`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180061f63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180061f96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180061f63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180061f96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180061f52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180061f52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180061f3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180061f83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180061f3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180061f83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800621b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006234e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800621b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006234e`

## string_xrefs

- `0x180062126`: `nameCollisionMap->Remove(keyName)`
- `0x180062400`: `attributes->Insert(keyName.Get(), propValue.Get(), &replaced)`
- `0x1800623a7`: `propertyValueFactory->CreateString(value, &propValue)`
- `0x180062376`: `nameCollisionMap->Insert(keyName, keyName, &replaced)`

## pseudocode

```c

```
