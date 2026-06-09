# Windows::Storage::StateABIHelpers::CreatePropertyValueFromSettingData(uchar const *,uint,tag_STATE_VALUE_TYPE,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)

- ea: `0x180009ea8`
- end: `0x18000aa6e`
- name: `?CreatePropertyValueFromSettingData@StateABIHelpers@Storage@Windows@@YAJPEBEIW4tag_STATE_VALUE_TYPE@@AEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z`
- size: `3014`
- prototype: `HRESULT __fastcall(const unsigned __int8 *valueBuffer, const unsigned int valueBufferBytes, const tag_STATE_VALUE_TYPE valueType, Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterface, IInspectable **propertyValue)`
- caller_count: `3`
- callee_count: `42`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007dc0`
- `0x180009d90`
- `0x180034a88`

## callees

- `0x180005b30`
- `0x180006008`
- `0x180006144`
- `0x1800063cc`
- `0x180006cec`
- `0x180006e24`
- `0x1800070a8`
- `0x180007158`
- `0x180007580`
- `0x180009778`
- `0x180009ea8`
- `0x18000aa74`
- `0x18000aab0`
- `0x1800127c0`
- `0x18001c4b8`
- `0x18001ccec`
- `0x18001cfc4`
- `0x180022790`
- `0x1800228dc`
- `0x18003d388`
- `0x18003da4c`
- `0x18003dad8`
- `0x18003db64`
- `0x18003dbf4`
- `0x18003dc84`
- `0x18003dd14`
- `0x18003dda4`
- `0x18003de34`
- `0x18003dec0`
- `0x18003df50`
- `0x18003dfe0`
- `0x18003e070`
- `0x18003e100`
- `0x18003e190`
- `0x18003e220`
- `0x18003e2ac`
- `0x18003e338`
- `0x18003e3c4`
- `0x18003e450`
- `0x18003e4dc`
- `0x18003e568`
- `0x180042010`

## string_xrefs

- `0x18000a04e`: `CreatePropertyValue %u`
- `0x18000a0db`: `CreatePropertyValue %u`
- `0x18000a144`: `CreatePropertyValue %u`
- `0x18000a266`: `CreatePropertyValue %u`
- `0x18000aa28`: `CreatePropertyValue %u`
- `0x180009f4f`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a074`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a101`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a1a6`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a21a`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a369`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a3a8`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a3e2`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a440`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a4e8`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a522`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a55c`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a596`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a5d0`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a60a`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a644`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a67c`: `FixedWidthSingleValueDeserializer %u size %u`
- `0x18000a313`: `CreateEmpty %u size %u`
- `0x18000a16c`: `VariableWidthSingleValueDeserializer %u size %u`
- `0x18000a28a`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a4b0`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a6c4`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a6fe`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a738`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a772`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a7ac`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a7e6`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a820`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a858`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a892`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a8cc`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a906`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a940`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a97a`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a9b4`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000aa4c`: `FixedWidthArrayDeserializer %u size %u`
- `0x18000a9ee`: `VariableWidthArrayDeserializer %u size %u`

## pseudocode

```c
HRESULT __fastcall Windows::Storage::StateABIHelpers::CreatePropertyValueFromSettingData(
        const unsigned __int8 *valueBuffer,
        unsigned int valueBufferBytes,
        tag_STATE_VALUE_TYPE valueType,
        Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterface,
        IInspectable **propertyValue)
{
  HRESULT v6; // edi
  Windows::Foundation::IPropertyValueStatics *ptr; // rcx
  Windows::Foundation::IPropertyValueStatics_vtbl *v9; // rax
  IInspectable *v10; // rdx
  __int64 v11; // [rsp+28h] [rbp-38h]
  __int64 v12; // [rsp+28h] [rbp-38h]
  __int64 v13; // [rsp+28h] [rbp-38h]
  __int64 v14; // [rsp+28h] [rbp-38h]
  __int64 v15; // [rsp+28h] [rbp-38h]
  RoVariant newProperty; // [rsp+40h] [rbp-20h] BYREF
  RoVariant *p_newProperty; // [rsp+50h] [rbp-10h]
  IInspectable *pI; // [rsp+58h] [rbp-8h] BYREF
  void *retaddr; // [rsp+68h] [rbp+8h]

  if ( valueType > STATE_VALUE_RECT )
  {
    if ( valueType <= STATE_VALUE_CHAR16_ARRAY )
    {
      switch ( valueType )
      {
        case STATE_VALUE_CHAR16_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1034>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xCDu,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              29,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_UINT8_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::PropertyValueTraits<1025>::CreatePropertyValue(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x36u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
              v6,
              "CreatePropertyValue %u",
              valueBufferBytes);
            LODWORD(v14) = 20;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x97u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              v14,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_INT16_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1026>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x9Du,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              21,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_UINT16_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1027>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xA3u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              22,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_INT32_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1028>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xA9u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              23,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_UINT32_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1029>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xAFu,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              24,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_INT64_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1030>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xB5u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              25,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_UINT64_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1031>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xBBu,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              26,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_SINGLE_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1032>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xC1u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              27,
              valueBufferBytes);
            return v6;
          }
          break;
        default:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1033>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xC7u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              28,
              valueBufferBytes);
            return v6;
          }
          break;
      }
    }
    else
    {
      switch ( valueType )
      {
        case STATE_VALUE_BOOLEAN_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::PropertyValueTraits<1035>::CreatePropertyValue(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x36u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
              v6,
              "CreatePropertyValue %u",
              valueBufferBytes);
            LODWORD(v15) = 30;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xD3u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              v15,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_STRING_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::VariableWidthArrayDeserializer<1036>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xD9u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "VariableWidthArrayDeserializer %u size %u",
              31,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_DATETIME_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1038>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xDFu,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              33,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_TIMESPAN_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1039>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xE5u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              34,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_GUID_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1040>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xEBu,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              35,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_POINT_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1041>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xF1u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              36,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_SIZE_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1042>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xF7u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              37,
              valueBufferBytes);
            return v6;
          }
          break;
        case STATE_VALUE_RECT_ARRAY:
          v6 = Windows::Storage::StateABIHelpers::FixedWidthArrayDeserializer<1043>::Deserialize(
                 valueBuffer,
                 valueBufferBytes,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xFDu,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
              v6,
              "FixedWidthArrayDeserializer %u size %u",
              38,
              valueBufferBytes);
            return v6;
          }
          break;
        default:
          return wil::details::in1diag3::Return_Win32Msg(
                   retaddr,
                   0x101u,
                   "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
                   0x65Eu,
                   "Type %u",
                   valueType);
      }
    }
    return 0;
  }
  if ( valueType == STATE_VALUE_RECT )
  {
    v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<19>::Deserialize(
           valueBuffer,
           valueBufferBytes,
           propertyValueStaticInterface,
           propertyValue);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x91u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
        v6,
        "FixedWidthSingleValueDeserializer %u size %u",
        19,
        valueBufferBytes);
      return v6;
    }
    return 0;
  }
  if ( valueType > STATE_VALUE_DOUBLE )
  {
    switch ( valueType )
    {
      case STATE_VALUE_CHAR16:
        v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<10>::Deserialize(
               valueBuffer,
               valueBufferBytes,
               propertyValueStaticInterface,
               propertyValue);
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x61u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
            v6,
            "FixedWidthSingleValueDeserializer %u size %u",
            10,
            valueBufferBytes);
          return v6;
        }
        break;
      case STATE_VALUE_BOOLEAN:
        if ( valueBufferBytes == 1 )
        {
          v6 = Windows::Storage::StateABIHelpers::PropertyValueTraits<11>::CreatePropertyValue(
                 valueBuffer,
                 propertyValueStaticInterface,
                 propertyValue);
          if ( v6 >= 0 )
            return 0;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x21u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
            v6,
            "CreatePropertyValue %u",
            1);
        }
        else
        {
          v6 = wil::details::in1diag3::Return_Win32Msg(
                 retaddr,
                 0x1Eu,
                 "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
                 0x5B6u,
                 "Size %u",
                 valueBufferBytes);
          if ( v6 >= 0 )
            return 0;
        }
        LODWORD(v12) = 11;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x67u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
          v6,
          "FixedWidthSingleValueDeserializer %u size %u",
          v12,
          valueBufferBytes);
        return v6;
      case STATE_VALUE_STRING:
        v6 = Windows::Storage::StateABIHelpers::PropertyValueTraits<12>::CreatePropertyValue(
               valueBuffer,
               valueBufferBytes,
               propertyValueStaticInterface,
               propertyValue);
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x49u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
            v6,
            "CreatePropertyValue %u",
            valueBufferBytes);
          LODWORD(v13) = 12;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x6Du,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
            v6,
            "VariableWidthSingleValueDeserializer %u size %u",
            v13,
            valueBufferBytes);
          return v6;
        }
        break;
      case STATE_VALUE_DATETIME:
        v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<14>::Deserialize(
               valueBuffer,
               valueBufferBytes,
               propertyValueStaticInterface,
               propertyValue);
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x73u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
            v6,
            "FixedWidthSingleValueDeserializer %u size %u",
            14,
            valueBufferBytes);
          return v6;
        }
        break;
      case STATE_VALUE_TIMESPAN:
        v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<15>::Deserialize(
               valueBuffer,
               valueBufferBytes,
               propertyValueStaticInterface,
               propertyValue);
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x79u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
            v6,
            "FixedWidthSingleValueDeserializer %u size %u",
            15,
            valueBufferBytes);
          return v6;
        }
        break;
      case STATE_VALUE_GUID:
        v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<16>::Deserialize(
               valueBuffer,
               valueBufferBytes,
               propertyValueStaticInterface,
               propertyValue);
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x7Fu,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
            v6,
            "FixedWidthSingleValueDeserializer %u size %u",
            16,
            valueBufferBytes);
          return v6;
        }
        break;
      case STATE_VALUE_POINT:
        v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<17>::Deserialize(
               valueBuffer,
               valueBufferBytes,
               propertyValueStaticInterface,
               propertyValue);
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x85u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
            v6,
            "FixedWidthSingleValueDeserializer %u size %u",
            17,
            valueBufferBytes);
          return v6;
        }
        break;
      case STATE_VALUE_SIZE:
        v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<18>::Deserialize(
               valueBuffer,
               valueBufferBytes,
               propertyValueStaticInterface,
               propertyValue);
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x8Bu,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
            v6,
            "FixedWidthSingleValueDeserializer %u size %u",
            18,
            valueBufferBytes);
          return v6;
        }
        break;
      default:
        return wil::details::in1diag3::Return_Win32Msg(
                 retaddr,
                 0x101u,
                 "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
                 0x65Eu,
                 "Type %u",
                 valueType);
    }
    return 0;
  }
  switch ( valueType )
  {
    case STATE_VALUE_DOUBLE:
      v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<9>::Deserialize(
             valueBuffer,
             valueBufferBytes,
             propertyValueStaticInterface,
             propertyValue);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x5Bu,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
          v6,
          "FixedWidthSingleValueDeserializer %u size %u",
          9,
          valueBufferBytes);
        return v6;
      }
      return 0;
    case STATE_VALUE_UNDEFINED:
      ptr = propertyValueStaticInterface->ptr_;
      newProperty._pI = 0;
      newProperty._hrState = 0;
      v9 = ptr->__vftable;
      p_newProperty = &newProperty;
      pI = 0;
      v6 = v9->CreateEmpty(ptr, &pI);
      RoVariant::Attach(p_newProperty, pI);
      v10 = newProperty._pI;
      newProperty._pI = 0;
      newProperty._hrState = 0;
      *propertyValue = v10;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x24u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
          v6,
          "CreateEmpty %u size %u",
          0,
          valueBufferBytes);
        RoVariant::~RoVariant(&newProperty);
        return v6;
      }
      return 0;
    case STATE_VALUE_UINT8:
      v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<1>::Deserialize(
             valueBuffer,
             valueBufferBytes,
             propertyValueStaticInterface,
             propertyValue);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x2Bu,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
          v6,
          "FixedWidthSingleValueDeserializer %u size %u",
          1,
          valueBufferBytes);
        return v6;
      }
      return 0;
    case STATE_VALUE_INT16:
      v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<2>::Deserialize(
             valueBuffer,
             valueBufferBytes,
             propertyValueStaticInterface,
             propertyValue);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x31u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
          v6,
          "FixedWidthSingleValueDeserializer %u size %u",
          2,
          valueBufferBytes);
        return v6;
      }
      return 0;
    case STATE_VALUE_UINT16:
      v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<3>::Deserialize(
             valueBuffer,
             valueBufferBytes,
             propertyValueStaticInterface,
             propertyValue);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x37u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
          v6,
          "FixedWidthSingleValueDeserializer %u size %u",
          3,
          valueBufferBytes);
        return v6;
      }
      return 0;
    case STATE_VALUE_INT32:
      v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<4>::Deserialize(
             valueBuffer,
             valueBufferBytes,
             propertyValueStaticInterface,
             propertyValue);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x3Du,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
          v6,
          "FixedWidthSingleValueDeserializer %u size %u",
          4,
          valueBufferBytes);
        return v6;
      }
      return 0;
    case STATE_VALUE_UINT32:
      v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<5>::Deserialize(
             valueBuffer,
             valueBufferBytes,
             propertyValueStaticInterface,
             propertyValue);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x43u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
          v6,
          "FixedWidthSingleValueDeserializer %u size %u",
          5,
          valueBufferBytes);
        return v6;
      }
      return 0;
    case STATE_VALUE_INT64:
      if ( valueBufferBytes == 8 )
      {
        v6 = Windows::Storage::StateABIHelpers::PropertyValueTraits<6>::CreatePropertyValue(
               (const __int64 *)valueBuffer,
               propertyValueStaticInterface,
               propertyValue);
        if ( v6 >= 0 )
          return 0;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x21u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
          v6,
          "CreatePropertyValue %u",
          8);
      }
      else
      {
        v6 = wil::details::in1diag3::Return_Win32Msg(
               retaddr,
               0x1Eu,
               "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIApiSetValueToSettingProperty.hpp",
               0x5B6u,
               "Size %u",
               valueBufferBytes);
        if ( v6 >= 0 )
          return 0;
      }
      LODWORD(v11) = 6;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x49u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
        v6,
        "FixedWidthSingleValueDeserializer %u size %u",
        v11,
        valueBufferBytes);
      return v6;
    case STATE_VALUE_UINT64:
      v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<7>::Deserialize(
             valueBuffer,
             valueBufferBytes,
             propertyValueStaticInterface,
             propertyValue);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x4Fu,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
          v6,
          "FixedWidthSingleValueDeserializer %u size %u",
          7,
          valueBufferBytes);
        return v6;
      }
      return 0;
  }
  if ( valueType != STATE_VALUE_SINGLE )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             0x101u,
             "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
             0x65Eu,
             "Type %u",
             valueType);
  v6 = Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<8>::Deserialize(
         valueBuffer,
         valueBufferBytes,
         propertyValueStaticInterface,
         propertyValue);
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    0x55u,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabiapisetvaluetosettingproperty.cpp",
    v6,
    "FixedWidthSingleValueDeserializer %u size %u",
    8,
    valueBufferBytes);
  return v6;
}

```

## disassembly

```asm
0x180009ea8  mov     [rsp-8+arg_0], rbx
0x180009ead  mov     [rsp-8+arg_8], rdi
0x180009eb2  push    rbp
0x180009eb3  mov     rbp, rsp
0x180009eb6  sub     rsp, 60h
0x180009eba  mov     r10, propertyValueStaticInterface
0x180009ebd  mov     ebx, valueBufferBytes
0x180009ebf  cmp     valueType, 13h
0x180009ec3  jg      loc_180009F6D
0x180009ec9  jz      loc_18000A662
0x180009ecf  cmp     valueType, 9
0x180009ed3  jg      loc_18000A0A7
0x180009ed9  jz      loc_18000A4CE
0x180009edf  mov     valueBufferBytes, valueType
0x180009ee2  test    valueType, valueType
0x180009ee5  jz      loc_18000A2AC
0x180009eeb  sub     valueBufferBytes, 1
0x180009eee  jz      loc_18000A540
0x180009ef4  sub     valueBufferBytes, 1
0x180009ef7  jz      loc_18000A506
0x180009efd  sub     valueBufferBytes, 1
0x180009f00  jz      loc_18000A3C6
0x180009f06  sub     valueBufferBytes, 1
0x180009f09  jz      loc_18000A34D
0x180009f0f  sub     valueBufferBytes, 1
0x180009f12  jz      loc_18000A18A
0x180009f18  sub     valueBufferBytes, 1
0x180009f1b  jz      loc_18000A033
0x180009f21  sub     valueBufferBytes, 1
0x180009f24  jz      loc_18000A1FE
0x180009f2a  cmp     valueBufferBytes, 1
0x180009f2d  jnz     loc_180009FC2
0x180009f33  mov     propertyValueStaticInterface, [rbp+arg_20]; propertyValue
0x180009f37  mov     r8, r10; propertyValueStaticInterface
0x180009f3a  mov     valueBufferBytes, ebx; valueBufferBytes
0x180009f3c  call    ?Deserialize@?$FixedWidthSingleValueDeserializer@$07@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<8>::Deserialize(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x180009f41  mov     edi, eax
0x180009f43  test    eax, eax
0x180009f45  jns     loc_18000A021
0x180009f4b  mov     [rsp+60h+var_30], ebx
0x180009f4f  lea     rdx, aFixedwidthsing; "FixedWidthSingleValueDeserializer %u si"...
0x180009f56  mov     dword ptr [rsp+60h+var_38], 8
0x180009f5e  mov     [rsp+60h+formatString], rdx
0x180009f63  mov     valueBufferBytes, 55h ; 'U'
0x180009f68  jmp     loc_18000A08D
0x180009f6d  cmp     valueType, 1Dh
0x180009f71  jle     loc_18000A238
0x180009f77  mov     valueBufferBytes, valueType
0x180009f7a  sub     valueBufferBytes, 1Eh
0x180009f7d  jz      loc_18000AA0C
0x180009f83  sub     valueBufferBytes, 1
0x180009f86  jz      loc_18000A9D2
0x180009f8c  sub     valueBufferBytes, 2
0x180009f8f  jz      loc_18000A998
0x180009f95  sub     valueBufferBytes, 1
0x180009f98  jz      loc_18000A95E
0x180009f9e  sub     valueBufferBytes, 1
0x180009fa1  jz      loc_18000A924
0x180009fa7  sub     valueBufferBytes, 1
0x180009faa  jz      loc_18000A8EA
0x180009fb0  sub     valueBufferBytes, 1
0x180009fb3  jz      loc_18000A8B0
0x180009fb9  cmp     valueBufferBytes, 1
0x180009fbc  jz      loc_18000A876
0x180009fc2  mov     valueBuffer, [rbp+8]; callerReturnAddress
0x180009fc6  lea     rax, aTypeU; "Type %u"
0x180009fcd  mov     dword ptr [rsp+60h+var_38], valueType
0x180009fd2  mov     r9d, 65Eh; err
0x180009fd8  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\appmodel\\statemanage"...
0x180009fdf  mov     [rsp+60h+formatString], rax; formatString
0x180009fe4  mov     valueBufferBytes, 101h; lineNumber
0x180009fe9  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180009fee  jmp     short loc_18000A023
0x180009ff0  mov     valueBuffer, [rbp+8]; callerReturnAddress
0x180009ff4  lea     rax, aSizeU; "Size %u"
0x180009ffb  mov     dword ptr [rsp+60h+var_38], ebx
0x180009fff  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000a006  mov     r9d, 5B6h; err
0x18000a00c  mov     [rsp+60h+formatString], rax; formatString
0x18000a011  mov     valueBufferBytes, 1Eh; lineNumber
0x18000a016  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000a01b  mov     edi, eax
0x18000a01d  test    eax, eax
0x18000a01f  js      short loc_18000A070
0x18000a021  xor     eax, eax
0x18000a023  mov     rbx, [rsp+60h+arg_0]
0x18000a028  mov     rdi, [rsp+60h+arg_8]
0x18000a02d  add     rsp, 60h
0x18000a031  pop     rbp
0x18000a032  retn
0x18000a033  cmp     ebx, 8
0x18000a036  jnz     short loc_180009FF0
0x18000a038  mov     r8, [rbp+arg_20]; propertyValue
0x18000a03c  mov     rdx, r10; propertyValueStaticInterface
0x18000a03f  call    ?CreatePropertyValue@?$PropertyValueTraits@$05@StateABIHelpers@Storage@Windows@@SAJPEB_JAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<6>::CreatePropertyValue(__int64 const *,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x18000a044  mov     edi, eax
0x18000a046  test    eax, eax
0x18000a048  jns     short loc_18000A021
0x18000a04a  mov     valueBuffer, [rbp+8]; callerReturnAddress
0x18000a04e  lea     rax, aCreateproperty_2; "CreatePropertyValue %u"
0x18000a055  mov     dword ptr [rsp+60h+var_38], ebx
0x18000a059  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000a060  mov     r9d, edi; hr
0x18000a063  mov     [rsp+60h+formatString], rax; formatString
0x18000a068  lea     valueBufferBytes, [rbx+19h]; lineNumber
0x18000a06b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a070  mov     [rsp+60h+var_30], ebx
0x18000a074  lea     rdx, aFixedwidthsing; "FixedWidthSingleValueDeserializer %u si"...
0x18000a07b  mov     dword ptr [rsp+60h+var_38], 6
0x18000a083  mov     [rsp+60h+formatString], rdx; formatString
0x18000a088  mov     valueBufferBytes, 49h ; 'I'; lineNumber
0x18000a08d  mov     valueBuffer, [rbp+8]; callerReturnAddress
0x18000a091  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000a098  mov     r9d, edi; hr
0x18000a09b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a0a0  mov     eax, edi
0x18000a0a2  jmp     loc_18000A023
0x18000a0a7  mov     valueBufferBytes, valueType
0x18000a0aa  sub     valueBufferBytes, 0Ah
0x18000a0ad  jz      loc_18000A628
0x18000a0b3  sub     valueBufferBytes, 1
0x18000a0b6  jnz     short loc_18000A11F
0x18000a0b8  cmp     ebx, 1
0x18000a0bb  jnz     loc_18000A1C4
0x18000a0c1  mov     r8, [rbp+arg_20]; propertyValue
0x18000a0c5  mov     rdx, r10; propertyValueStaticInterface
0x18000a0c8  call    ?CreatePropertyValue@?$PropertyValueTraits@$0L@@StateABIHelpers@Storage@Windows@@SAJPEBEAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<11>::CreatePropertyValue(uchar const *,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x18000a0cd  mov     edi, eax
0x18000a0cf  test    eax, eax
0x18000a0d1  jns     loc_18000A021
0x18000a0d7  mov     valueBuffer, [rbp+8]; callerReturnAddress
0x18000a0db  lea     rax, aCreateproperty_2; "CreatePropertyValue %u"
0x18000a0e2  mov     dword ptr [rsp+60h+var_38], ebx
0x18000a0e6  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000a0ed  mov     r9d, edi; hr
0x18000a0f0  mov     [rsp+60h+formatString], rax; formatString
0x18000a0f5  lea     valueBufferBytes, [rbx+20h]; lineNumber
0x18000a0f8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a0fd  mov     [rsp+60h+var_30], ebx
0x18000a101  lea     rdx, aFixedwidthsing; "FixedWidthSingleValueDeserializer %u si"...
0x18000a108  mov     dword ptr [rsp+60h+var_38], 0Bh
0x18000a110  mov     [rsp+60h+formatString], rdx
0x18000a115  mov     valueBufferBytes, 67h ; 'g'
0x18000a11a  jmp     loc_18000A08D
0x18000a11f  sub     valueBufferBytes, 1
0x18000a122  jnz     loc_18000A387
0x18000a128  mov     propertyValueStaticInterface, [rbp+arg_20]; propertyValue
0x18000a12c  mov     r8, r10; propertyValueStaticInterface
0x18000a12f  mov     valueBufferBytes, ebx; valueBufferBytes
0x18000a131  call    ?CreatePropertyValue@?$PropertyValueTraits@$0M@@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<12>::CreatePropertyValue(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x18000a136  mov     edi, eax
0x18000a138  test    eax, eax
0x18000a13a  jns     loc_18000A021
0x18000a140  mov     valueBuffer, [rbp+8]; callerReturnAddress
0x18000a144  lea     rax, aCreateproperty_2; "CreatePropertyValue %u"
0x18000a14b  mov     dword ptr [rsp+60h+var_38], ebx
0x18000a14f  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000a156  mov     r9d, edi; hr
0x18000a159  mov     [rsp+60h+formatString], rax; formatString
0x18000a15e  mov     valueBufferBytes, 49h ; 'I'; lineNumber
0x18000a163  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a168  mov     [rsp+60h+var_30], ebx
0x18000a16c  lea     rax, aVariablewidths; "VariableWidthSingleValueDeserializer %u"...
0x18000a173  mov     dword ptr [rsp+60h+var_38], 0Ch
0x18000a17b  mov     valueBufferBytes, 6Dh ; 'm'
0x18000a180  mov     [rsp+60h+formatString], rax
0x18000a185  jmp     loc_18000A08D
0x18000a18a  mov     propertyValueStaticInterface, [rbp+arg_20]; propertyValue
0x18000a18e  mov     r8, r10; propertyValueStaticInterface
0x18000a191  mov     valueBufferBytes, ebx; valueBufferBytes
0x18000a193  call    ?Deserialize@?$FixedWidthSingleValueDeserializer@$04@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<5>::Deserialize(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x18000a198  mov     edi, eax
0x18000a19a  test    eax, eax
0x18000a19c  jns     loc_18000A021
0x18000a1a2  mov     [rsp+60h+var_30], ebx
0x18000a1a6  lea     rdx, aFixedwidthsing; "FixedWidthSingleValueDeserializer %u si"...
0x18000a1ad  mov     dword ptr [rsp+60h+var_38], 5
0x18000a1b5  mov     [rsp+60h+formatString], rdx
0x18000a1ba  mov     valueBufferBytes, 43h ; 'C'
0x18000a1bf  jmp     loc_18000A08D
0x18000a1c4  mov     valueBuffer, [rbp+8]; callerReturnAddress
0x18000a1c8  lea     rax, aSizeU; "Size %u"
0x18000a1cf  mov     dword ptr [rsp+60h+var_38], ebx
0x18000a1d3  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000a1da  mov     r9d, 5B6h; err
0x18000a1e0  mov     [rsp+60h+formatString], rax; formatString
0x18000a1e5  mov     valueBufferBytes, 1Eh; lineNumber
0x18000a1ea  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000a1ef  mov     edi, eax
0x18000a1f1  test    eax, eax
0x18000a1f3  jns     loc_18000A021
0x18000a1f9  jmp     loc_18000A0FD
0x18000a1fe  mov     propertyValueStaticInterface, [rbp+arg_20]; propertyValue
0x18000a202  mov     r8, r10; propertyValueStaticInterface
0x18000a205  mov     valueBufferBytes, ebx; valueBufferBytes
0x18000a207  call    ?Deserialize@?$FixedWidthSingleValueDeserializer@$06@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<7>::Deserialize(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x18000a20c  mov     edi, eax
0x18000a20e  test    eax, eax
0x18000a210  jns     loc_18000A021
0x18000a216  mov     [rsp+60h+var_30], ebx
0x18000a21a  lea     rdx, aFixedwidthsing; "FixedWidthSingleValueDeserializer %u si"...
0x18000a221  mov     dword ptr [rsp+60h+var_38], 7
0x18000a229  mov     [rsp+60h+formatString], rdx
0x18000a22e  mov     valueBufferBytes, 4Fh ; 'O'
0x18000a233  jmp     loc_18000A08D
0x18000a238  jz      loc_18000A83E
0x18000a23e  mov     valueBufferBytes, valueType
0x18000a241  sub     valueBufferBytes, 14h
0x18000a244  jnz     loc_18000A45E
0x18000a24a  mov     propertyValueStaticInterface, [rbp+arg_20]; propertyValue
0x18000a24e  mov     r8, r10; propertyValueStaticInterface
0x18000a251  mov     valueBufferBytes, ebx; elements
0x18000a253  call    ?CreatePropertyValue@?$PropertyValueTraits@$0EAB@@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1025>::CreatePropertyValue(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x18000a258  mov     edi, eax
0x18000a25a  test    eax, eax
0x18000a25c  jns     loc_18000A021
0x18000a262  mov     valueBuffer, [rbp+8]; callerReturnAddress
0x18000a266  lea     rax, aCreateproperty_2; "CreatePropertyValue %u"
0x18000a26d  mov     dword ptr [rsp+60h+var_38], ebx
0x18000a271  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000a278  mov     r9d, edi; hr
0x18000a27b  mov     [rsp+60h+formatString], rax; formatString
0x18000a280  mov     valueBufferBytes, 36h ; '6'; lineNumber
0x18000a285  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a28a  lea     rdx, aFixedwidtharra; "FixedWidthArrayDeserializer %u size %u"
0x18000a291  mov     [rsp+60h+var_30], ebx
0x18000a295  mov     dword ptr [rsp+60h+var_38], 14h
0x18000a29d  mov     [rsp+60h+formatString], rdx
0x18000a2a2  mov     valueBufferBytes, 97h
0x18000a2a7  jmp     loc_18000A08D
0x18000a2ac  mov     valueBuffer, [propertyValueStaticInterface]
0x18000a2af  lea     rdx, [rbp+newProperty]
0x18000a2b3  mov     [rbp+newProperty._pI], 0
0x18000a2bb  mov     [rbp+newProperty._hrState], 0
0x18000a2c2  mov     rax, [valueBuffer]
0x18000a2c5  mov     [rbp+var_10], rdx
0x18000a2c9  lea     rdx, [rbp+pI]
0x18000a2cd  mov     [rbp+pI], 0
0x18000a2d5  mov     rax, [rax+30h]
0x18000a2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2de  mov     rdx, [rbp+pI]; pI
0x18000a2e2  mov     edi, eax
0x18000a2e4  mov     valueBuffer, [rbp+var_10]; this
0x18000a2e8  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18000a2ed  mov     rdx, [rbp+newProperty._pI]
0x18000a2f1  mov     valueBuffer, [rbp+arg_20]
0x18000a2f5  mov     [rbp+newProperty._pI], 0
0x18000a2fd  mov     [rbp+newProperty._hrState], 0
0x18000a304  mov     [valueBuffer], rdx
0x18000a307  test    edi, edi
0x18000a309  jns     loc_18000A021
0x18000a30f  mov     valueBuffer, [rbp+8]; callerReturnAddress
0x18000a313  lea     rax, aCreateemptyUSi; "CreateEmpty %u size %u"
0x18000a31a  mov     [rsp+60h+var_30], ebx
0x18000a31e  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000a325  mov     dword ptr [rsp+60h+var_38], 0
0x18000a32d  mov     r9d, edi; hr
0x18000a330  mov     valueBufferBytes, 24h ; '$'; lineNumber
0x18000a335  mov     [rsp+60h+formatString], rax; formatString
0x18000a33a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a33f  lea     valueBuffer, [rbp+newProperty]; this
0x18000a343  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18000a348  jmp     loc_18000A0A0
0x18000a34d  mov     propertyValueStaticInterface, [rbp+arg_20]; propertyValue
0x18000a351  mov     r8, r10; propertyValueStaticInterface
0x18000a354  mov     valueBufferBytes, ebx; valueBufferBytes
0x18000a356  call    ?Deserialize@?$FixedWidthSingleValueDeserializer@$03@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<4>::Deserialize(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x18000a35b  mov     edi, eax
0x18000a35d  test    eax, eax
0x18000a35f  jns     loc_18000A021
0x18000a365  mov     [rsp+60h+var_30], ebx
0x18000a369  lea     rdx, aFixedwidthsing; "FixedWidthSingleValueDeserializer %u si"...
0x18000a370  mov     dword ptr [rsp+60h+var_38], 4
0x18000a378  mov     [rsp+60h+formatString], rdx
0x18000a37d  mov     valueBufferBytes, 3Dh ; '='
0x18000a382  jmp     loc_18000A08D
0x18000a387  sub     valueBufferBytes, 2
0x18000a38a  jnz     short loc_18000A400
0x18000a38c  mov     propertyValueStaticInterface, [rbp+arg_20]; propertyValue
0x18000a390  mov     r8, r10; propertyValueStaticInterface
0x18000a393  mov     valueBufferBytes, ebx; valueBufferBytes
0x18000a395  call    ?Deserialize@?$FixedWidthSingleValueDeserializer@$0O@@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<14>::Deserialize(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x18000a39a  mov     edi, eax
0x18000a39c  test    eax, eax
0x18000a39e  jns     loc_18000A021
0x18000a3a4  mov     [rsp+60h+var_30], ebx
0x18000a3a8  lea     rdx, aFixedwidthsing; "FixedWidthSingleValueDeserializer %u si"...
0x18000a3af  mov     dword ptr [rsp+60h+var_38], 0Eh
0x18000a3b7  mov     [rsp+60h+formatString], rdx
0x18000a3bc  mov     valueBufferBytes, 73h ; 's'
0x18000a3c1  jmp     loc_18000A08D
0x18000a3c6  mov     propertyValueStaticInterface, [rbp+arg_20]; propertyValue
0x18000a3ca  mov     r8, r10; propertyValueStaticInterface
0x18000a3cd  mov     valueBufferBytes, ebx; valueBufferBytes
0x18000a3cf  call    ?Deserialize@?$FixedWidthSingleValueDeserializer@$02@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::FixedWidthSingleValueDeserializer<3>::Deserialize(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x18000a3d4  mov     edi, eax
0x18000a3d6  test    eax, eax
0x18000a3d8  jns     loc_18000A021
0x18000a3de  mov     [rsp+60h+var_30], ebx
0x18000a3e2  lea     rdx, aFixedwidthsing; "FixedWidthSingleValueDeserializer %u si"...
  ... truncated ...
```
