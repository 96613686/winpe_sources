# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1028>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003a34c`
- end: `0x18003a463`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAE@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
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
- `0x18002484c`
- `0x180024fc4`
- `0x18003a34c`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a450`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1028>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  int *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  int *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<int,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1028>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (int **)&v15.pRaw);
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
  v10 = 4 * length;
  *apisetType = STATE_VALUE_INT32_ARRAY;
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
0x18003a34c  push    rbp
0x18003a34e  push    rbx
0x18003a34f  push    rsi
0x18003a350  push    rdi
0x18003a351  push    r14
0x18003a353  mov     rbp, rsp
0x18003a356  sub     rsp, 60h
0x18003a35a  mov     rdi, valueBytes
0x18003a35d  mov     [rbp+length], 0
0x18003a364  mov     r14, apisetType
0x18003a367  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a36f  lea     rax, [rbp+propertyValueBuffer]
0x18003a373  mov     [rbp+var_20.pRaw], 0
0x18003a37b  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003a37f  mov     [rbp+var_20.wrapper], rax
0x18003a383  lea     apisetType, [rbp+length]; length
0x18003a387  mov     [rbp+var_20.replace], 1
0x18003a38b  mov     rsi, value
0x18003a38e  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAE@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAH@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1028>::GetPropertyValueArrayBase(IInspectable *,uint *,int * *)
0x18003a393  lea     property, [rbp+var_20]; this
0x18003a397  mov     ebx, eax
0x18003a399  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a39e  test    ebx, ebx
0x18003a3a0  jns     short loc_18003A3E1
0x18003a3a2  mov     property, [rbp+28h]; callerReturnAddress
0x18003a3a6  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003a3ad  mov     r9d, ebx; hr
0x18003a3b0  mov     [rsp+60h+formatString], rax; formatString
0x18003a3b5  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a3bc  mov     edx, 4B2h; lineNumber
0x18003a3c1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a3c6  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a3ca  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a3d2  test    property, property
0x18003a3d5  jz      short loc_18003A3DD
0x18003a3d7  call    cs:__imp_CoTaskMemFree
0x18003a3dd  mov     eax, ebx
0x18003a3df  jmp     short loc_18003A458
0x18003a3e1  mov     eax, [rbp+length]
0x18003a3e4  shl     eax, 2
0x18003a3e7  mov     dword ptr [r14], 17h
0x18003a3ee  mov     ecx, eax; cb
0x18003a3f0  mov     [rdi], eax
0x18003a3f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a3f7  mov     [rsi], rax
0x18003a3fa  mov     edx, [rdi]
0x18003a3fc  test    rax, rax
0x18003a3ff  jnz     short loc_18003A430
0x18003a401  mov     property, [rbp+28h]; callerReturnAddress
0x18003a405  lea     rax, aNewU; "new %u"
0x18003a40c  mov     [rsp+60h+var_38], edx
0x18003a410  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a417  mov     ebx, 8007000Eh
0x18003a41c  mov     [rsp+60h+formatString], rax; formatString
0x18003a421  mov     r9d, ebx; hr
0x18003a424  mov     edx, 4B7h; lineNumber
0x18003a429  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a42e  jmp     short loc_18003A3C6
0x18003a430  mov     valueBytes, apisetType; Size
0x18003a433  mov     property, rax; void *
0x18003a436  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003a43a  call    memcpy_0
0x18003a43f  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a443  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a44b  test    property, property
0x18003a44e  jz      short loc_18003A456
0x18003a450  call    cs:__imp_CoTaskMemFree
0x18003a456  xor     eax, eax
0x18003a458  add     rsp, 60h
0x18003a45c  pop     r14
0x18003a45e  pop     rdi
0x18003a45f  pop     rsi
0x18003a460  pop     rbx
0x18003a461  pop     rbp
0x18003a462  retn
```
