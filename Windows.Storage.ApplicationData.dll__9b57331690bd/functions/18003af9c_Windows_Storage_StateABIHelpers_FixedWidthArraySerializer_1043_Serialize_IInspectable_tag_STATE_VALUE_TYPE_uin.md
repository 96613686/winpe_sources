# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1043>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003af9c`
- end: `0x18003b0b1`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EBD@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
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
- `0x18003a044`
- `0x18003af9c`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b09e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b09e`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1043>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  Windows::Foundation::Rect *v8; // rcx
  size_t v10; // rcx
  unsigned __int8 *v11; // rax
  Windows::Foundation::Rect *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<Windows::Foundation::Rect,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1043>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (Windows::Foundation::Rect **)&v15.pRaw);
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
  *apisetType = STATE_VALUE_RECT_ARRAY;
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
0x18003af9c  push    rbp
0x18003af9e  push    rbx
0x18003af9f  push    rsi
0x18003afa0  push    rdi
0x18003afa1  push    r14
0x18003afa3  mov     rbp, rsp
0x18003afa6  sub     rsp, 60h
0x18003afaa  mov     rdi, valueBytes
0x18003afad  mov     [rbp+length], 0
0x18003afb4  mov     r14, apisetType
0x18003afb7  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003afbf  lea     rax, [rbp+propertyValueBuffer]
0x18003afc3  mov     [rbp+var_20.pRaw], 0
0x18003afcb  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003afcf  mov     [rbp+var_20.wrapper], rax
0x18003afd3  lea     apisetType, [rbp+length]; length
0x18003afd7  mov     [rbp+var_20.replace], 1
0x18003afdb  mov     rsi, value
0x18003afde  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EBD@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAURect@Foundation@4@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1043>::GetPropertyValueArrayBase(IInspectable *,uint *,Windows::Foundation::Rect * *)
0x18003afe3  lea     property, [rbp+var_20]; this
0x18003afe7  mov     ebx, eax
0x18003afe9  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003afee  test    ebx, ebx
0x18003aff0  jns     short loc_18003B031
0x18003aff2  mov     property, [rbp+28h]; callerReturnAddress
0x18003aff6  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003affd  mov     r9d, ebx; hr
0x18003b000  mov     [rsp+60h+formatString], rax; formatString
0x18003b005  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003b00c  mov     edx, 4B2h; lineNumber
0x18003b011  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b016  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003b01a  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003b022  test    property, property
0x18003b025  jz      short loc_18003B02D
0x18003b027  call    cs:__imp_CoTaskMemFree
0x18003b02d  mov     eax, ebx
0x18003b02f  jmp     short loc_18003B0A6
0x18003b031  mov     ecx, [rbp+length]
0x18003b034  shl     ecx, 4; cb
0x18003b037  mov     dword ptr [r14], 26h ; '&'
0x18003b03e  mov     [rdi], ecx
0x18003b040  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b045  mov     [rsi], rax
0x18003b048  mov     edx, [rdi]
0x18003b04a  test    rax, rax
0x18003b04d  jnz     short loc_18003B07E
0x18003b04f  mov     property, [rbp+28h]; callerReturnAddress
0x18003b053  lea     rax, aNewU; "new %u"
0x18003b05a  mov     [rsp+60h+var_38], edx
0x18003b05e  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003b065  mov     ebx, 8007000Eh
0x18003b06a  mov     [rsp+60h+formatString], rax; formatString
0x18003b06f  mov     r9d, ebx; hr
0x18003b072  mov     edx, 4B7h; lineNumber
0x18003b077  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b07c  jmp     short loc_18003B016
0x18003b07e  mov     valueBytes, apisetType; Size
0x18003b081  mov     property, rax; void *
0x18003b084  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003b088  call    memcpy_0
0x18003b08d  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003b091  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003b099  test    property, property
0x18003b09c  jz      short loc_18003B0A4
0x18003b09e  call    cs:__imp_CoTaskMemFree
0x18003b0a4  xor     eax, eax
0x18003b0a6  add     rsp, 60h
0x18003b0aa  pop     r14
0x18003b0ac  pop     rdi
0x18003b0ad  pop     rsi
0x18003b0ae  pop     rbx
0x18003b0af  pop     rbp
0x18003b0b0  retn
```
