# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1040>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003ac40`
- end: `0x18003ad55`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EBA@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
- size: `277`
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
- `0x180039dd4`
- `0x18003ac40`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003accb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ad42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003accb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ad42`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1040>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  _GUID *v8; // rcx
  size_t v10; // rcx
  unsigned __int8 *v11; // rax
  _GUID *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<_GUID,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1040>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (_GUID **)&v15.pRaw);
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
  v10 = 16 * length;
  *apisetType = STATE_VALUE_GUID_ARRAY;
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
0x18003ac40  push    rbp
0x18003ac42  push    rbx
0x18003ac43  push    rsi
0x18003ac44  push    rdi
0x18003ac45  push    r14
0x18003ac47  mov     rbp, rsp
0x18003ac4a  sub     rsp, 60h
0x18003ac4e  mov     rdi, valueBytes
0x18003ac51  mov     [rbp+length], 0
0x18003ac58  mov     r14, apisetType
0x18003ac5b  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003ac63  lea     rax, [rbp+propertyValueBuffer]
0x18003ac67  mov     [rbp+var_20.pRaw], 0
0x18003ac6f  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003ac73  mov     [rbp+var_20.wrapper], rax
0x18003ac77  lea     apisetType, [rbp+length]; length
0x18003ac7b  mov     [rbp+var_20.replace], 1
0x18003ac7f  mov     rsi, value
0x18003ac82  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EBA@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAU_GUID@@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1040>::GetPropertyValueArrayBase(IInspectable *,uint *,_GUID * *)
0x18003ac87  lea     property, [rbp+var_20]; this
0x18003ac8b  mov     ebx, eax
0x18003ac8d  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003ac92  test    ebx, ebx
0x18003ac94  jns     short loc_18003ACD5
0x18003ac96  mov     property, [rbp+28h]; callerReturnAddress
0x18003ac9a  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003aca1  mov     r9d, ebx; hr
0x18003aca4  mov     [rsp+60h+formatString], rax; formatString
0x18003aca9  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003acb0  mov     edx, 4B2h; lineNumber
0x18003acb5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003acba  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003acbe  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003acc6  test    property, property
0x18003acc9  jz      short loc_18003ACD1
0x18003accb  call    cs:__imp_CoTaskMemFree
0x18003acd1  mov     eax, ebx
0x18003acd3  jmp     short loc_18003AD4A
0x18003acd5  mov     ecx, [rbp+length]
0x18003acd8  shl     ecx, 4; cb
0x18003acdb  mov     dword ptr [r14], 23h ; '#'
0x18003ace2  mov     [rdi], ecx
0x18003ace4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ace9  mov     [rsi], rax
0x18003acec  mov     edx, [rdi]
0x18003acee  test    rax, rax
0x18003acf1  jnz     short loc_18003AD22
0x18003acf3  mov     property, [rbp+28h]; callerReturnAddress
0x18003acf7  lea     rax, aNewU; "new %u"
0x18003acfe  mov     [rsp+60h+var_38], edx
0x18003ad02  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003ad09  mov     ebx, 8007000Eh
0x18003ad0e  mov     [rsp+60h+formatString], rax; formatString
0x18003ad13  mov     r9d, ebx; hr
0x18003ad16  mov     edx, 4B7h; lineNumber
0x18003ad1b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003ad20  jmp     short loc_18003ACBA
0x18003ad22  mov     valueBytes, apisetType; Size
0x18003ad25  mov     property, rax; void *
0x18003ad28  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003ad2c  call    memcpy_0
0x18003ad31  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003ad35  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003ad3d  test    property, property
0x18003ad40  jz      short loc_18003AD48
0x18003ad42  call    cs:__imp_CoTaskMemFree
0x18003ad48  xor     eax, eax
0x18003ad4a  add     rsp, 60h
0x18003ad4e  pop     r14
0x18003ad50  pop     rdi
0x18003ad51  pop     rsi
0x18003ad52  pop     rbx
0x18003ad53  pop     rbp
0x18003ad54  retn
```
