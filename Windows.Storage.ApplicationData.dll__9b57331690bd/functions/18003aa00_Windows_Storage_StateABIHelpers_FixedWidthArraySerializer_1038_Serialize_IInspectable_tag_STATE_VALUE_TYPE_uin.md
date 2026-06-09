# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1038>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003aa00`
- end: `0x18003ab17`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAO@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
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
- `0x180039c34`
- `0x18003aa00`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aa8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aa8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab04`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1038>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  Windows::Foundation::DateTime *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  Windows::Foundation::DateTime *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<Windows::Foundation::DateTime,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1038>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (Windows::Foundation::DateTime **)&v15.pRaw);
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
  *apisetType = STATE_VALUE_DATETIME_ARRAY;
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
0x18003aa00  push    rbp
0x18003aa02  push    rbx
0x18003aa03  push    rsi
0x18003aa04  push    rdi
0x18003aa05  push    r14
0x18003aa07  mov     rbp, rsp
0x18003aa0a  sub     rsp, 60h
0x18003aa0e  mov     rdi, valueBytes
0x18003aa11  mov     [rbp+length], 0
0x18003aa18  mov     r14, apisetType
0x18003aa1b  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003aa23  lea     rax, [rbp+propertyValueBuffer]
0x18003aa27  mov     [rbp+var_20.pRaw], 0
0x18003aa2f  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003aa33  mov     [rbp+var_20.wrapper], rax
0x18003aa37  lea     apisetType, [rbp+length]; length
0x18003aa3b  mov     [rbp+var_20.replace], 1
0x18003aa3f  mov     rsi, value
0x18003aa42  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAO@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAUDateTime@Foundation@4@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1038>::GetPropertyValueArrayBase(IInspectable *,uint *,Windows::Foundation::DateTime * *)
0x18003aa47  lea     property, [rbp+var_20]; this
0x18003aa4b  mov     ebx, eax
0x18003aa4d  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003aa52  test    ebx, ebx
0x18003aa54  jns     short loc_18003AA95
0x18003aa56  mov     property, [rbp+28h]; callerReturnAddress
0x18003aa5a  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003aa61  mov     r9d, ebx; hr
0x18003aa64  mov     [rsp+60h+formatString], rax; formatString
0x18003aa69  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003aa70  mov     edx, 4B2h; lineNumber
0x18003aa75  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003aa7a  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003aa7e  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003aa86  test    property, property
0x18003aa89  jz      short loc_18003AA91
0x18003aa8b  call    cs:__imp_CoTaskMemFree
0x18003aa91  mov     eax, ebx
0x18003aa93  jmp     short loc_18003AB0C
0x18003aa95  mov     eax, [rbp+length]
0x18003aa98  shl     eax, 3
0x18003aa9b  mov     dword ptr [r14], 21h ; '!'
0x18003aaa2  mov     ecx, eax; cb
0x18003aaa4  mov     [rdi], eax
0x18003aaa6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003aaab  mov     [rsi], rax
0x18003aaae  mov     edx, [rdi]
0x18003aab0  test    rax, rax
0x18003aab3  jnz     short loc_18003AAE4
0x18003aab5  mov     property, [rbp+28h]; callerReturnAddress
0x18003aab9  lea     rax, aNewU; "new %u"
0x18003aac0  mov     [rsp+60h+var_38], edx
0x18003aac4  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003aacb  mov     ebx, 8007000Eh
0x18003aad0  mov     [rsp+60h+formatString], rax; formatString
0x18003aad5  mov     r9d, ebx; hr
0x18003aad8  mov     edx, 4B7h; lineNumber
0x18003aadd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003aae2  jmp     short loc_18003AA7A
0x18003aae4  mov     valueBytes, apisetType; Size
0x18003aae7  mov     property, rax; void *
0x18003aaea  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003aaee  call    memcpy_0
0x18003aaf3  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003aaf7  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003aaff  test    property, property
0x18003ab02  jz      short loc_18003AB0A
0x18003ab04  call    cs:__imp_CoTaskMemFree
0x18003ab0a  xor     eax, eax
0x18003ab0c  add     rsp, 60h
0x18003ab10  pop     r14
0x18003ab12  pop     rdi
0x18003ab13  pop     rsi
0x18003ab14  pop     rbx
0x18003ab15  pop     rbp
0x18003ab16  retn
```
