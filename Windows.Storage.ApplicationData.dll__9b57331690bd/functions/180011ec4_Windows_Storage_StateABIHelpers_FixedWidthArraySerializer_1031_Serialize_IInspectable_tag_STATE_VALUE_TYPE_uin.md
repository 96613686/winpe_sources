# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1031>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x180011ec4`
- end: `0x180011ff1`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAH@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
- size: `301`
- prototype: `HRESULT __fastcall(IInspectable *property, tag_STATE_VALUE_TYPE *apisetType, unsigned int *valueBytes, unsigned __int8 **value)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000af34`

## callees

- `0x180009778`
- `0x180011ec4`
- `0x180011ff8`
- `0x180024fc4`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fde`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1031>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  unsigned __int64 *v8; // rcx
  unsigned __int64 *v9; // rcx
  unsigned int v11; // eax
  unsigned __int8 *v12; // rax
  unsigned __int64 *v13; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<unsigned __int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wistd::unique_ptr<unsigned __int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *p_propertyValueBuffer; // [rsp+40h] [rbp-20h]
  unsigned __int64 *v17; // [rsp+48h] [rbp-18h] BYREF
  char v18; // [rsp+50h] [rbp-10h]
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v17 = 0;
  p_propertyValueBuffer = &propertyValueBuffer;
  v18 = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1031>::GetPropertyValueArrayBase(
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
  v11 = 8 * length;
  *apisetType = STATE_VALUE_UINT64_ARRAY;
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
0x180011ec4  push    rbp
0x180011ec6  push    rbx
0x180011ec7  push    rsi
0x180011ec8  push    rdi
0x180011ec9  push    r14
0x180011ecb  mov     rbp, rsp
0x180011ece  sub     rsp, 60h
0x180011ed2  mov     rdi, valueBytes
0x180011ed5  mov     [rbp+length], 0
0x180011edc  mov     r14, apisetType
0x180011edf  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x180011ee7  lea     rax, [rbp+propertyValueBuffer]
0x180011eeb  mov     [rbp+var_18], 0
0x180011ef3  lea     valueBytes, [rbp+var_18]; value
0x180011ef7  mov     [rbp+var_20], rax
0x180011efb  lea     apisetType, [rbp+length]; length
0x180011eff  mov     [rbp+var_10], 1
0x180011f03  mov     rsi, value
0x180011f06  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAH@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEA_K@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1031>::GetPropertyValueArrayBase(IInspectable *,uint *,unsigned __int64 * *)
0x180011f0b  cmp     [rbp+var_10], 0
0x180011f0f  mov     ebx, eax
0x180011f11  jz      short loc_180011F2C
0x180011f13  mov     valueBytes, [rbp+var_20]
0x180011f17  mov     apisetType, [rbp+var_18]
0x180011f1b  mov     property, [valueBytes]; pv
0x180011f1e  mov     [valueBytes], apisetType
0x180011f21  test    property, property
0x180011f24  jz      short loc_180011F2C
0x180011f26  call    cs:__imp_CoTaskMemFree
0x180011f2c  test    ebx, ebx
0x180011f2e  jns     short loc_180011F6F
0x180011f30  mov     property, [rbp+28h]; callerReturnAddress
0x180011f34  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x180011f3b  mov     r9d, ebx; hr
0x180011f3e  mov     [rsp+60h+formatString], rax; formatString
0x180011f43  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x180011f4a  mov     edx, 4B2h; lineNumber
0x180011f4f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180011f54  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x180011f58  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x180011f60  test    property, property
0x180011f63  jz      short loc_180011F6B
0x180011f65  call    cs:__imp_CoTaskMemFree
0x180011f6b  mov     eax, ebx
0x180011f6d  jmp     short loc_180011FE6
0x180011f6f  mov     eax, [rbp+length]
0x180011f72  shl     eax, 3
0x180011f75  mov     dword ptr [r14], 1Ah
0x180011f7c  mov     ecx, eax; cb
0x180011f7e  mov     [rdi], eax
0x180011f80  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011f85  mov     [rsi], rax
0x180011f88  mov     edx, [rdi]
0x180011f8a  test    rax, rax
0x180011f8d  jnz     short loc_180011FBE
0x180011f8f  mov     property, [rbp+28h]; callerReturnAddress
0x180011f93  lea     rax, aNewU; "new %u"
0x180011f9a  mov     [rsp+60h+var_38], edx
0x180011f9e  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x180011fa5  mov     ebx, 8007000Eh
0x180011faa  mov     [rsp+60h+formatString], rax; formatString
0x180011faf  mov     r9d, ebx; hr
0x180011fb2  mov     edx, 4B7h; lineNumber
0x180011fb7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180011fbc  jmp     short loc_180011F54
0x180011fbe  mov     valueBytes, apisetType; Size
0x180011fc1  mov     property, rax; void *
0x180011fc4  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x180011fc8  call    memcpy_0
0x180011fcd  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x180011fd1  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x180011fd9  test    property, property
0x180011fdc  jz      short loc_180011FE4
0x180011fde  call    cs:__imp_CoTaskMemFree
0x180011fe4  xor     eax, eax
0x180011fe6  add     rsp, 60h
0x180011fea  pop     r14
0x180011fec  pop     rdi
0x180011fed  pop     rsi
0x180011fee  pop     rbx
0x180011fef  pop     rbp
0x180011ff0  retn
```
