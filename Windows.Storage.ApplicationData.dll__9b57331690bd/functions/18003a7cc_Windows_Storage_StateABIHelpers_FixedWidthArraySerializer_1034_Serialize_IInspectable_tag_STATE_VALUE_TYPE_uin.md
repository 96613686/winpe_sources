# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1034>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003a7cc`
- end: `0x18003a8e2`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAK@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
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
- `0x180039a94`
- `0x18003a7cc`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8cf`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1034>::Serialize(
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
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1034>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (wchar_t **)&v15.pRaw);
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
  *apisetType = STATE_VALUE_CHAR16_ARRAY;
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
0x18003a7cc  push    rbp
0x18003a7ce  push    rbx
0x18003a7cf  push    rsi
0x18003a7d0  push    rdi
0x18003a7d1  push    r14
0x18003a7d3  mov     rbp, rsp
0x18003a7d6  sub     rsp, 60h
0x18003a7da  mov     rdi, valueBytes
0x18003a7dd  mov     [rbp+length], 0
0x18003a7e4  mov     r14, apisetType
0x18003a7e7  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a7ef  lea     rax, [rbp+propertyValueBuffer]
0x18003a7f3  mov     [rbp+var_20.pRaw], 0
0x18003a7fb  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003a7ff  mov     [rbp+var_20.wrapper], rax
0x18003a803  lea     apisetType, [rbp+length]; length
0x18003a807  mov     [rbp+var_20.replace], 1
0x18003a80b  mov     rsi, value
0x18003a80e  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAK@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAG@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1034>::GetPropertyValueArrayBase(IInspectable *,uint *,ushort * *)
0x18003a813  lea     property, [rbp+var_20]; this
0x18003a817  mov     ebx, eax
0x18003a819  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a81e  test    ebx, ebx
0x18003a820  jns     short loc_18003A861
0x18003a822  mov     property, [rbp+28h]; callerReturnAddress
0x18003a826  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003a82d  mov     r9d, ebx; hr
0x18003a830  mov     [rsp+60h+formatString], rax; formatString
0x18003a835  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a83c  mov     edx, 4B2h; lineNumber
0x18003a841  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a846  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a84a  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a852  test    property, property
0x18003a855  jz      short loc_18003A85D
0x18003a857  call    cs:__imp_CoTaskMemFree
0x18003a85d  mov     eax, ebx
0x18003a85f  jmp     short loc_18003A8D7
0x18003a861  mov     eax, [rbp+length]
0x18003a864  add     eax, eax
0x18003a866  mov     dword ptr [r14], 1Dh
0x18003a86d  mov     ecx, eax; cb
0x18003a86f  mov     [rdi], eax
0x18003a871  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a876  mov     [rsi], rax
0x18003a879  mov     edx, [rdi]
0x18003a87b  test    rax, rax
0x18003a87e  jnz     short loc_18003A8AF
0x18003a880  mov     property, [rbp+28h]; callerReturnAddress
0x18003a884  lea     rax, aNewU; "new %u"
0x18003a88b  mov     [rsp+60h+var_38], edx
0x18003a88f  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a896  mov     ebx, 8007000Eh
0x18003a89b  mov     [rsp+60h+formatString], rax; formatString
0x18003a8a0  mov     r9d, ebx; hr
0x18003a8a3  mov     edx, 4B7h; lineNumber
0x18003a8a8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a8ad  jmp     short loc_18003A846
0x18003a8af  mov     valueBytes, apisetType; Size
0x18003a8b2  mov     property, rax; void *
0x18003a8b5  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003a8b9  call    memcpy_0
0x18003a8be  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a8c2  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a8ca  test    property, property
0x18003a8cd  jz      short loc_18003A8D5
0x18003a8cf  call    cs:__imp_CoTaskMemFree
0x18003a8d5  xor     eax, eax
0x18003a8d7  add     rsp, 60h
0x18003a8db  pop     r14
0x18003a8dd  pop     rdi
0x18003a8de  pop     rsi
0x18003a8df  pop     rbx
0x18003a8e0  pop     rbp
0x18003a8e1  retn
```
