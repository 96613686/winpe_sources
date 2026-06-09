# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1027>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003a230`
- end: `0x18003a346`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAD@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
- size: `278`
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
- `0x180039754`
- `0x18003a230`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a2bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a2bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a333`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1027>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  wchar_t *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  wchar_t *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<unsigned short,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1027>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (unsigned __int16 **)&v15.pRaw);
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
  v10 = 2 * length;
  *apisetType = STATE_VALUE_UINT16_ARRAY;
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
0x18003a230  push    rbp
0x18003a232  push    rbx
0x18003a233  push    rsi
0x18003a234  push    rdi
0x18003a235  push    r14
0x18003a237  mov     rbp, rsp
0x18003a23a  sub     rsp, 60h
0x18003a23e  mov     rdi, valueBytes
0x18003a241  mov     [rbp+length], 0
0x18003a248  mov     r14, apisetType
0x18003a24b  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a253  lea     rax, [rbp+propertyValueBuffer]
0x18003a257  mov     [rbp+var_20.pRaw], 0
0x18003a25f  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003a263  mov     [rbp+var_20.wrapper], rax
0x18003a267  lea     apisetType, [rbp+length]; length
0x18003a26b  mov     [rbp+var_20.replace], 1
0x18003a26f  mov     rsi, value
0x18003a272  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAD@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAG@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1027>::GetPropertyValueArrayBase(IInspectable *,uint *,ushort * *)
0x18003a277  lea     property, [rbp+var_20]; this
0x18003a27b  mov     ebx, eax
0x18003a27d  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a282  test    ebx, ebx
0x18003a284  jns     short loc_18003A2C5
0x18003a286  mov     property, [rbp+28h]; callerReturnAddress
0x18003a28a  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003a291  mov     r9d, ebx; hr
0x18003a294  mov     [rsp+60h+formatString], rax; formatString
0x18003a299  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a2a0  mov     edx, 4B2h; lineNumber
0x18003a2a5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a2aa  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a2ae  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a2b6  test    property, property
0x18003a2b9  jz      short loc_18003A2C1
0x18003a2bb  call    cs:__imp_CoTaskMemFree
0x18003a2c1  mov     eax, ebx
0x18003a2c3  jmp     short loc_18003A33B
0x18003a2c5  mov     eax, [rbp+length]
0x18003a2c8  add     eax, eax
0x18003a2ca  mov     dword ptr [r14], 16h
0x18003a2d1  mov     ecx, eax; cb
0x18003a2d3  mov     [rdi], eax
0x18003a2d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a2da  mov     [rsi], rax
0x18003a2dd  mov     edx, [rdi]
0x18003a2df  test    rax, rax
0x18003a2e2  jnz     short loc_18003A313
0x18003a2e4  mov     property, [rbp+28h]; callerReturnAddress
0x18003a2e8  lea     rax, aNewU; "new %u"
0x18003a2ef  mov     [rsp+60h+var_38], edx
0x18003a2f3  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a2fa  mov     ebx, 8007000Eh
0x18003a2ff  mov     [rsp+60h+formatString], rax; formatString
0x18003a304  mov     r9d, ebx; hr
0x18003a307  mov     edx, 4B7h; lineNumber
0x18003a30c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a311  jmp     short loc_18003A2AA
0x18003a313  mov     valueBytes, apisetType; Size
0x18003a316  mov     property, rax; void *
0x18003a319  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003a31d  call    memcpy_0
0x18003a322  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a326  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a32e  test    property, property
0x18003a331  jz      short loc_18003A339
0x18003a333  call    cs:__imp_CoTaskMemFree
0x18003a339  xor     eax, eax
0x18003a33b  add     rsp, 60h
0x18003a33f  pop     r14
0x18003a341  pop     rdi
0x18003a342  pop     rsi
0x18003a343  pop     rbx
0x18003a344  pop     rbp
0x18003a345  retn
```
