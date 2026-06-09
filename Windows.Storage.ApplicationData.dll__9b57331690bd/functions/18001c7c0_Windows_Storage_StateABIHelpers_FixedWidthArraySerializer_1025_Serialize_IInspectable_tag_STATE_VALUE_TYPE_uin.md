# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1025>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18001c7c0`
- end: `0x18001c8e8`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAB@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
- size: `296`
- prototype: `HRESULT __fastcall(IInspectable *property, tag_STATE_VALUE_TYPE *apisetType, unsigned int *valueBytes, unsigned __int8 **value)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000af34`

## callees

- `0x180009778`
- `0x18001c7c0`
- `0x1800202b8`
- `0x180024fc4`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8d5`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1025>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  unsigned __int8 *v8; // rcx
  unsigned __int8 *v9; // rcx
  size_t v11; // rcx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *p_propertyValueBuffer; // [rsp+40h] [rbp-20h]
  unsigned __int8 *v17; // [rsp+48h] [rbp-18h] BYREF
  char v18; // [rsp+50h] [rbp-10h]
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v17 = 0;
  p_propertyValueBuffer = &propertyValueBuffer;
  v18 = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1025>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             &v17);
  if ( v18 )
  {
    v8 = p_propertyValueBuffer->__ptr_.__value_;
    p_propertyValueBuffer->__ptr_.__value_ = v17;
    if ( v8 )
      CoTaskMemFree(v8);
  }
  if ( PropertyValueArrayBase < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x4B2u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
      PropertyValueArrayBase,
      "GetPropertyValueArrayBase");
LABEL_6:
    v9 = propertyValueBuffer.__ptr_.__value_;
    propertyValueBuffer.__ptr_.__value_ = 0;
    if ( v9 )
      CoTaskMemFree(v9);
    return (unsigned int)PropertyValueArrayBase;
  }
  v11 = length;
  *apisetType = STATE_VALUE_UINT8_ARRAY;
  *valueBytes = v11;
  v12 = (unsigned __int8 *)operator new(v11);
  *value = v12;
  if ( !v12 )
  {
    PropertyValueArrayBase = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x4B7u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
      -2147024882,
      "new %u",
      *valueBytes);
    goto LABEL_6;
  }
  memcpy_0(v12, propertyValueBuffer.__ptr_.__value_, *valueBytes);
  v13 = propertyValueBuffer.__ptr_.__value_;
  propertyValueBuffer.__ptr_.__value_ = 0;
  if ( v13 )
    CoTaskMemFree(v13);
  return 0;
}

```

## disassembly

```asm
0x18001c7c0  push    rbp
0x18001c7c2  push    rbx
0x18001c7c3  push    rsi
0x18001c7c4  push    rdi
0x18001c7c5  push    r14
0x18001c7c7  mov     rbp, rsp
0x18001c7ca  sub     rsp, 60h
0x18001c7ce  mov     rdi, valueBytes
0x18001c7d1  mov     [rbp+length], 0
0x18001c7d8  mov     r14, apisetType
0x18001c7db  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18001c7e3  lea     rax, [rbp+propertyValueBuffer]
0x18001c7e7  mov     [rbp+var_18], 0
0x18001c7ef  lea     valueBytes, [rbp+var_18]; value
0x18001c7f3  mov     [rbp+var_20], rax
0x18001c7f7  lea     apisetType, [rbp+length]; length
0x18001c7fb  mov     [rbp+var_10], 1
0x18001c7ff  mov     rsi, value
0x18001c802  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAB@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAE@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1025>::GetPropertyValueArrayBase(IInspectable *,uint *,uchar * *)
0x18001c807  cmp     [rbp+var_10], 0
0x18001c80b  mov     ebx, eax
0x18001c80d  jz      short loc_18001C828
0x18001c80f  mov     valueBytes, [rbp+var_20]
0x18001c813  mov     apisetType, [rbp+var_18]
0x18001c817  mov     property, [valueBytes]; pv
0x18001c81a  mov     [valueBytes], apisetType
0x18001c81d  test    property, property
0x18001c820  jz      short loc_18001C828
0x18001c822  call    cs:__imp_CoTaskMemFree
0x18001c828  test    ebx, ebx
0x18001c82a  jns     short loc_18001C86B
0x18001c82c  mov     property, [rbp+28h]; callerReturnAddress
0x18001c830  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18001c837  mov     r9d, ebx; hr
0x18001c83a  mov     [rsp+60h+formatString], rax; formatString
0x18001c83f  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001c846  mov     edx, 4B2h; lineNumber
0x18001c84b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001c850  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18001c854  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18001c85c  test    property, property
0x18001c85f  jz      short loc_18001C867
0x18001c861  call    cs:__imp_CoTaskMemFree
0x18001c867  mov     eax, ebx
0x18001c869  jmp     short loc_18001C8DD
0x18001c86b  mov     ecx, [rbp+length]; cb
0x18001c86e  mov     dword ptr [r14], 14h
0x18001c875  mov     [rdi], ecx
0x18001c877  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c87c  mov     [rsi], rax
0x18001c87f  mov     edx, [rdi]
0x18001c881  test    rax, rax
0x18001c884  jnz     short loc_18001C8B5
0x18001c886  mov     property, [rbp+28h]; callerReturnAddress
0x18001c88a  lea     rax, aNewU; "new %u"
0x18001c891  mov     [rsp+60h+var_38], edx
0x18001c895  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001c89c  mov     ebx, 8007000Eh
0x18001c8a1  mov     [rsp+60h+formatString], rax; formatString
0x18001c8a6  mov     r9d, ebx; hr
0x18001c8a9  mov     edx, 4B7h; lineNumber
0x18001c8ae  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001c8b3  jmp     short loc_18001C850
0x18001c8b5  mov     valueBytes, apisetType; Size
0x18001c8b8  mov     property, rax; void *
0x18001c8bb  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18001c8bf  call    memcpy_0
0x18001c8c4  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18001c8c8  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18001c8d0  test    property, property
0x18001c8d3  jz      short loc_18001C8DB
0x18001c8d5  call    cs:__imp_CoTaskMemFree
0x18001c8db  xor     eax, eax
0x18001c8dd  add     rsp, 60h
0x18001c8e1  pop     r14
0x18001c8e3  pop     rdi
0x18001c8e4  pop     rsi
0x18001c8e5  pop     rbx
0x18001c8e6  pop     rbp
0x18001c8e7  retn
```
