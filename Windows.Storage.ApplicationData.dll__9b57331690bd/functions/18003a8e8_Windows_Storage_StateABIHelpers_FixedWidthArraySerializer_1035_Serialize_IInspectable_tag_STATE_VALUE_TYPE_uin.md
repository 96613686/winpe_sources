# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1035>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003a8e8`
- end: `0x18003a9fa`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAL@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
- size: `274`
- prototype: `HRESULT __fastcall(IInspectable *property, tag_STATE_VALUE_TYPE *apisetType, unsigned int *valueBytes, unsigned __int8 **value)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000af34`

## callees

- `0x180009778`
- `0x18001b304`
- `0x180024fc4`
- `0x180039b64`
- `0x18003a8e8`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a973`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a9e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a973`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a9e7`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1035>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  unsigned __int8 *v8; // rcx
  size_t v10; // rcx
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = &propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1035>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             &v15.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v15);
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
  v10 = length;
  *apisetType = STATE_VALUE_BOOLEAN_ARRAY;
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
0x18003a8e8  push    rbp
0x18003a8ea  push    rbx
0x18003a8eb  push    rsi
0x18003a8ec  push    rdi
0x18003a8ed  push    r14
0x18003a8ef  mov     rbp, rsp
0x18003a8f2  sub     rsp, 60h
0x18003a8f6  mov     rdi, valueBytes
0x18003a8f9  mov     [rbp+length], 0
0x18003a900  mov     r14, apisetType
0x18003a903  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a90b  lea     rax, [rbp+propertyValueBuffer]
0x18003a90f  mov     [rbp+var_20.pRaw], 0
0x18003a917  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003a91b  mov     [rbp+var_20.wrapper], rax
0x18003a91f  lea     apisetType, [rbp+length]; length
0x18003a923  mov     [rbp+var_20.replace], 1
0x18003a927  mov     rsi, value
0x18003a92a  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAL@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAE@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1035>::GetPropertyValueArrayBase(IInspectable *,uint *,uchar * *)
0x18003a92f  lea     property, [rbp+var_20]; this
0x18003a933  mov     ebx, eax
0x18003a935  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a93a  test    ebx, ebx
0x18003a93c  jns     short loc_18003A97D
0x18003a93e  mov     property, [rbp+28h]; callerReturnAddress
0x18003a942  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003a949  mov     r9d, ebx; hr
0x18003a94c  mov     [rsp+60h+formatString], rax; formatString
0x18003a951  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a958  mov     edx, 4B2h; lineNumber
0x18003a95d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a962  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a966  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a96e  test    property, property
0x18003a971  jz      short loc_18003A979
0x18003a973  call    cs:__imp_CoTaskMemFree
0x18003a979  mov     eax, ebx
0x18003a97b  jmp     short loc_18003A9EF
0x18003a97d  mov     ecx, [rbp+length]; cb
0x18003a980  mov     dword ptr [r14], 1Eh
0x18003a987  mov     [rdi], ecx
0x18003a989  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a98e  mov     [rsi], rax
0x18003a991  mov     edx, [rdi]
0x18003a993  test    rax, rax
0x18003a996  jnz     short loc_18003A9C7
0x18003a998  mov     property, [rbp+28h]; callerReturnAddress
0x18003a99c  lea     rax, aNewU; "new %u"
0x18003a9a3  mov     [rsp+60h+var_38], edx
0x18003a9a7  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a9ae  mov     ebx, 8007000Eh
0x18003a9b3  mov     [rsp+60h+formatString], rax; formatString
0x18003a9b8  mov     r9d, ebx; hr
0x18003a9bb  mov     edx, 4B7h; lineNumber
0x18003a9c0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a9c5  jmp     short loc_18003A962
0x18003a9c7  mov     valueBytes, apisetType; Size
0x18003a9ca  mov     property, rax; void *
0x18003a9cd  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003a9d1  call    memcpy_0
0x18003a9d6  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a9da  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a9e2  test    property, property
0x18003a9e5  jz      short loc_18003A9ED
0x18003a9e7  call    cs:__imp_CoTaskMemFree
0x18003a9ed  xor     eax, eax
0x18003a9ef  add     rsp, 60h
0x18003a9f3  pop     r14
0x18003a9f5  pop     rdi
0x18003a9f6  pop     rsi
0x18003a9f7  pop     rbx
0x18003a9f8  pop     rbp
0x18003a9f9  retn
```
