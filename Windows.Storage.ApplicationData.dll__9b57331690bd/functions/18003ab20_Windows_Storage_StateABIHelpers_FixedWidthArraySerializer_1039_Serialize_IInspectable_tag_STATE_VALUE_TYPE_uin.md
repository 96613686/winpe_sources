# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1039>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003ab20`
- end: `0x18003ac37`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAP@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
- size: `279`
- prototype: `HRESULT __fastcall(IInspectable *property, tag_STATE_VALUE_TYPE *apisetType, unsigned int *valueBytes, unsigned __int8 **value)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000af34`

## callees

- `0x180009778`
- `0x1800226d8`
- `0x180024fc4`
- `0x180039d04`
- `0x18003ab20`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003abab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003abab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac24`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1039>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  Windows::Foundation::TimeSpan *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  Windows::Foundation::TimeSpan *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<Windows::Foundation::TimeSpan,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1039>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (Windows::Foundation::TimeSpan **)&v15.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v15);
  if ( PropertyValueArrayBase < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x4B2u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
      PropertyValueArrayBase,
      "GetPropertyValueArrayBase");
LABEL_3:
    v8 = propertyValueBuffer.__ptr_.__value_;
    propertyValueBuffer.__ptr_.__value_ = 0;
    if ( v8 )
      CoTaskMemFree(v8);
    return (unsigned int)PropertyValueArrayBase;
  }
  v10 = 8 * length;
  *apisetType = STATE_VALUE_TIMESPAN_ARRAY;
  *valueBytes = v10;
  v11 = (unsigned __int8 *)operator new(v10);
  *value = v11;
  if ( !v11 )
  {
    PropertyValueArrayBase = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x4B7u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
      -2147024882,
      "new %u",
      *valueBytes);
    goto LABEL_3;
  }
  memcpy_0(v11, propertyValueBuffer.__ptr_.__value_, *valueBytes);
  v12 = propertyValueBuffer.__ptr_.__value_;
  propertyValueBuffer.__ptr_.__value_ = 0;
  if ( v12 )
    CoTaskMemFree(v12);
  return 0;
}

```

## disassembly

```asm
0x18003ab20  push    rbp
0x18003ab22  push    rbx
0x18003ab23  push    rsi
0x18003ab24  push    rdi
0x18003ab25  push    r14
0x18003ab27  mov     rbp, rsp
0x18003ab2a  sub     rsp, 60h
0x18003ab2e  mov     rdi, valueBytes
0x18003ab31  mov     [rbp+length], 0
0x18003ab38  mov     r14, apisetType
0x18003ab3b  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003ab43  lea     rax, [rbp+propertyValueBuffer]
0x18003ab47  mov     [rbp+var_20.pRaw], 0
0x18003ab4f  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003ab53  mov     [rbp+var_20.wrapper], rax
0x18003ab57  lea     apisetType, [rbp+length]; length
0x18003ab5b  mov     [rbp+var_20.replace], 1
0x18003ab5f  mov     rsi, value
0x18003ab62  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAP@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAUTimeSpan@Foundation@4@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1039>::GetPropertyValueArrayBase(IInspectable *,uint *,Windows::Foundation::TimeSpan * *)
0x18003ab67  lea     property, [rbp+var_20]; this
0x18003ab6b  mov     ebx, eax
0x18003ab6d  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003ab72  test    ebx, ebx
0x18003ab74  jns     short loc_18003ABB5
0x18003ab76  mov     property, [rbp+28h]; callerReturnAddress
0x18003ab7a  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003ab81  mov     r9d, ebx; hr
0x18003ab84  mov     [rsp+60h+formatString], rax; formatString
0x18003ab89  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003ab90  mov     edx, 4B2h; lineNumber
0x18003ab95  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003ab9a  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003ab9e  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003aba6  test    property, property
0x18003aba9  jz      short loc_18003ABB1
0x18003abab  call    cs:__imp_CoTaskMemFree
0x18003abb1  mov     eax, ebx
0x18003abb3  jmp     short loc_18003AC2C
0x18003abb5  mov     eax, [rbp+length]
0x18003abb8  shl     eax, 3
0x18003abbb  mov     dword ptr [r14], 22h ; '"'
0x18003abc2  mov     ecx, eax; cb
0x18003abc4  mov     [rdi], eax
0x18003abc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003abcb  mov     [rsi], rax
0x18003abce  mov     edx, [rdi]
0x18003abd0  test    rax, rax
0x18003abd3  jnz     short loc_18003AC04
0x18003abd5  mov     property, [rbp+28h]; callerReturnAddress
0x18003abd9  lea     rax, aNewU; "new %u"
0x18003abe0  mov     [rsp+60h+var_38], edx
0x18003abe4  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003abeb  mov     ebx, 8007000Eh
0x18003abf0  mov     [rsp+60h+formatString], rax; formatString
0x18003abf5  mov     r9d, ebx; hr
0x18003abf8  mov     edx, 4B7h; lineNumber
0x18003abfd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003ac02  jmp     short loc_18003AB9A
0x18003ac04  mov     valueBytes, apisetType; Size
0x18003ac07  mov     property, rax; void *
0x18003ac0a  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003ac0e  call    memcpy_0
0x18003ac13  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003ac17  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003ac1f  test    property, property
0x18003ac22  jz      short loc_18003AC2A
0x18003ac24  call    cs:__imp_CoTaskMemFree
0x18003ac2a  xor     eax, eax
0x18003ac2c  add     rsp, 60h
0x18003ac30  pop     r14
0x18003ac32  pop     rdi
0x18003ac33  pop     rsi
0x18003ac34  pop     rbx
0x18003ac35  pop     rbp
0x18003ac36  retn
```
