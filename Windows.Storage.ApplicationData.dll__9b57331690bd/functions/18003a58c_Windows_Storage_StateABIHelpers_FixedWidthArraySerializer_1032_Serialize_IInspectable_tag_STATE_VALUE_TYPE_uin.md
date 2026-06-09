# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1032>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003a58c`
- end: `0x18003a6a3`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAI@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
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
- `0x1800398f4`
- `0x18003a58c`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a617`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a617`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a690`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1032>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  float *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  float *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<float,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1032>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (float **)&v15.pRaw);
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
  *apisetType = STATE_VALUE_SINGLE_ARRAY;
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
0x18003a58c  push    rbp
0x18003a58e  push    rbx
0x18003a58f  push    rsi
0x18003a590  push    rdi
0x18003a591  push    r14
0x18003a593  mov     rbp, rsp
0x18003a596  sub     rsp, 60h
0x18003a59a  mov     rdi, valueBytes
0x18003a59d  mov     [rbp+length], 0
0x18003a5a4  mov     r14, apisetType
0x18003a5a7  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a5af  lea     rax, [rbp+propertyValueBuffer]
0x18003a5b3  mov     [rbp+var_20.pRaw], 0
0x18003a5bb  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003a5bf  mov     [rbp+var_20.wrapper], rax
0x18003a5c3  lea     apisetType, [rbp+length]; length
0x18003a5c7  mov     [rbp+var_20.replace], 1
0x18003a5cb  mov     rsi, value
0x18003a5ce  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAI@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAM@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1032>::GetPropertyValueArrayBase(IInspectable *,uint *,float * *)
0x18003a5d3  lea     property, [rbp+var_20]; this
0x18003a5d7  mov     ebx, eax
0x18003a5d9  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a5de  test    ebx, ebx
0x18003a5e0  jns     short loc_18003A621
0x18003a5e2  mov     property, [rbp+28h]; callerReturnAddress
0x18003a5e6  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003a5ed  mov     r9d, ebx; hr
0x18003a5f0  mov     [rsp+60h+formatString], rax; formatString
0x18003a5f5  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a5fc  mov     edx, 4B2h; lineNumber
0x18003a601  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a606  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a60a  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a612  test    property, property
0x18003a615  jz      short loc_18003A61D
0x18003a617  call    cs:__imp_CoTaskMemFree
0x18003a61d  mov     eax, ebx
0x18003a61f  jmp     short loc_18003A698
0x18003a621  mov     eax, [rbp+length]
0x18003a624  shl     eax, 2
0x18003a627  mov     dword ptr [r14], 1Bh
0x18003a62e  mov     ecx, eax; cb
0x18003a630  mov     [rdi], eax
0x18003a632  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a637  mov     [rsi], rax
0x18003a63a  mov     edx, [rdi]
0x18003a63c  test    rax, rax
0x18003a63f  jnz     short loc_18003A670
0x18003a641  mov     property, [rbp+28h]; callerReturnAddress
0x18003a645  lea     rax, aNewU; "new %u"
0x18003a64c  mov     [rsp+60h+var_38], edx
0x18003a650  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a657  mov     ebx, 8007000Eh
0x18003a65c  mov     [rsp+60h+formatString], rax; formatString
0x18003a661  mov     r9d, ebx; hr
0x18003a664  mov     edx, 4B7h; lineNumber
0x18003a669  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a66e  jmp     short loc_18003A606
0x18003a670  mov     valueBytes, apisetType; Size
0x18003a673  mov     property, rax; void *
0x18003a676  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003a67a  call    memcpy_0
0x18003a67f  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a683  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a68b  test    property, property
0x18003a68e  jz      short loc_18003A696
0x18003a690  call    cs:__imp_CoTaskMemFree
0x18003a696  xor     eax, eax
0x18003a698  add     rsp, 60h
0x18003a69c  pop     r14
0x18003a69e  pop     rdi
0x18003a69f  pop     rsi
0x18003a6a0  pop     rbx
0x18003a6a1  pop     rbp
0x18003a6a2  retn
```
