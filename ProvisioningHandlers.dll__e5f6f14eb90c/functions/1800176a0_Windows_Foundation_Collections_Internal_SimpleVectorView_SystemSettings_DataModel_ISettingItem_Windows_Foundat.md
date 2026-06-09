# Windows::Foundation::Collections::Internal::SimpleVectorView<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,XWinRT::IntVersionTag,1>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800176a0`
- end: `0x1800176bd`
- name: `?GetRuntimeClassName@?$SimpleVectorView@PEAUISettingItem@DataModel@SystemSettings@@V?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800176d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800176b6`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,XWinRT::IntVersionTag,1>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(
           L"Windows.Foundation.Collections.IVectorView`1<SystemSettings.DataModel.ISettingItem>",
           0x53u,
           a2);
}

```

## disassembly

```asm
0x1800176a0  mov     qword ptr [rdx], 0
0x1800176a7  lea     rcx, aWindowsFoundat_5; "Windows.Foundation.Collections.IVectorV"...
0x1800176ae  mov     r8, rdx
0x1800176b1  mov     edx, 53h ; 'S'
0x1800176b6  jmp     cs:__imp_WindowsCreateString
```
