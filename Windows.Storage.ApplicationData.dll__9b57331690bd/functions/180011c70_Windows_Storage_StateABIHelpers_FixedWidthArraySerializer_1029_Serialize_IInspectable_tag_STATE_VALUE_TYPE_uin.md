# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1029>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x180011c70`
- end: `0x180011d9d`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAF@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
- size: `301`
- prototype: `HRESULT __fastcall(IInspectable *property, tag_STATE_VALUE_TYPE *apisetType, unsigned int *valueBytes, unsigned __int8 **value)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000af34`

## callees

- `0x180009778`
- `0x180011c70`
- `0x180011da4`
- `0x180024fc4`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011cd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011cd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d8a`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1029>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  unsigned int *v8; // rcx
  unsigned int *v9; // rcx
  unsigned int v11; // eax
  unsigned __int8 *v12; // rax
  unsigned int *v13; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<unsigned int,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wistd::unique_ptr<unsigned int,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *p_propertyValueBuffer; // [rsp+40h] [rbp-20h]
  unsigned int *v17; // [rsp+48h] [rbp-18h] BYREF
  char v18; // [rsp+50h] [rbp-10h]
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v17 = 0;
  p_propertyValueBuffer = &propertyValueBuffer;
  v18 = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1029>::GetPropertyValueArrayBase(
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
  v11 = 4 * length;
  *apisetType = STATE_VALUE_UINT32_ARRAY;
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
0x180011c70  push    rbp
0x180011c72  push    rbx
0x180011c73  push    rsi
0x180011c74  push    rdi
0x180011c75  push    r14
0x180011c77  mov     rbp, rsp
0x180011c7a  sub     rsp, 60h
0x180011c7e  mov     rdi, valueBytes
0x180011c81  mov     [rbp+length], 0
0x180011c88  mov     r14, apisetType
0x180011c8b  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x180011c93  lea     rax, [rbp+propertyValueBuffer]
0x180011c97  mov     [rbp+var_18], 0
0x180011c9f  lea     valueBytes, [rbp+var_18]; value
0x180011ca3  mov     [rbp+var_20], rax
0x180011ca7  lea     apisetType, [rbp+length]; length
0x180011cab  mov     [rbp+var_10], 1
0x180011caf  mov     rsi, value
0x180011cb2  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAF@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAI@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1029>::GetPropertyValueArrayBase(IInspectable *,uint *,uint * *)
0x180011cb7  cmp     [rbp+var_10], 0
0x180011cbb  mov     ebx, eax
0x180011cbd  jz      short loc_180011CD8
0x180011cbf  mov     valueBytes, [rbp+var_20]
0x180011cc3  mov     apisetType, [rbp+var_18]
0x180011cc7  mov     property, [valueBytes]; pv
0x180011cca  mov     [valueBytes], apisetType
0x180011ccd  test    property, property
0x180011cd0  jz      short loc_180011CD8
0x180011cd2  call    cs:__imp_CoTaskMemFree
0x180011cd8  test    ebx, ebx
0x180011cda  jns     short loc_180011D1B
0x180011cdc  mov     property, [rbp+28h]; callerReturnAddress
0x180011ce0  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x180011ce7  mov     r9d, ebx; hr
0x180011cea  mov     [rsp+60h+formatString], rax; formatString
0x180011cef  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x180011cf6  mov     edx, 4B2h; lineNumber
0x180011cfb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180011d00  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x180011d04  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x180011d0c  test    property, property
0x180011d0f  jz      short loc_180011D17
0x180011d11  call    cs:__imp_CoTaskMemFree
0x180011d17  mov     eax, ebx
0x180011d19  jmp     short loc_180011D92
0x180011d1b  mov     eax, [rbp+length]
0x180011d1e  shl     eax, 2
0x180011d21  mov     dword ptr [r14], 18h
0x180011d28  mov     ecx, eax; cb
0x180011d2a  mov     [rdi], eax
0x180011d2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011d31  mov     [rsi], rax
0x180011d34  mov     edx, [rdi]
0x180011d36  test    rax, rax
0x180011d39  jnz     short loc_180011D6A
0x180011d3b  mov     property, [rbp+28h]; callerReturnAddress
0x180011d3f  lea     rax, aNewU; "new %u"
0x180011d46  mov     [rsp+60h+var_38], edx
0x180011d4a  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x180011d51  mov     ebx, 8007000Eh
0x180011d56  mov     [rsp+60h+formatString], rax; formatString
0x180011d5b  mov     r9d, ebx; hr
0x180011d5e  mov     edx, 4B7h; lineNumber
0x180011d63  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180011d68  jmp     short loc_180011D00
0x180011d6a  mov     valueBytes, apisetType; Size
0x180011d6d  mov     property, rax; void *
0x180011d70  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x180011d74  call    memcpy_0
0x180011d79  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x180011d7d  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x180011d85  test    property, property
0x180011d88  jz      short loc_180011D90
0x180011d8a  call    cs:__imp_CoTaskMemFree
0x180011d90  xor     eax, eax
0x180011d92  add     rsp, 60h
0x180011d96  pop     r14
0x180011d98  pop     rdi
0x180011d99  pop     rsi
0x180011d9a  pop     rbx
0x180011d9b  pop     rbp
0x180011d9c  retn
```
