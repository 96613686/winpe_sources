# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1033>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003a6ac`
- end: `0x18003a7c3`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAJ@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
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
- `0x1800399c4`
- `0x18003a6ac`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a7b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a7b0`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1033>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  long double *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  long double *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<double,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1033>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (long double **)&v15.pRaw);
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
  *apisetType = STATE_VALUE_DOUBLE_ARRAY;
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
0x18003a6ac  push    rbp
0x18003a6ae  push    rbx
0x18003a6af  push    rsi
0x18003a6b0  push    rdi
0x18003a6b1  push    r14
0x18003a6b3  mov     rbp, rsp
0x18003a6b6  sub     rsp, 60h
0x18003a6ba  mov     rdi, valueBytes
0x18003a6bd  mov     [rbp+length], 0
0x18003a6c4  mov     r14, apisetType
0x18003a6c7  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a6cf  lea     rax, [rbp+propertyValueBuffer]
0x18003a6d3  mov     [rbp+var_20.pRaw], 0
0x18003a6db  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003a6df  mov     [rbp+var_20.wrapper], rax
0x18003a6e3  lea     apisetType, [rbp+length]; length
0x18003a6e7  mov     [rbp+var_20.replace], 1
0x18003a6eb  mov     rsi, value
0x18003a6ee  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAJ@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAN@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1033>::GetPropertyValueArrayBase(IInspectable *,uint *,double * *)
0x18003a6f3  lea     property, [rbp+var_20]; this
0x18003a6f7  mov     ebx, eax
0x18003a6f9  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a6fe  test    ebx, ebx
0x18003a700  jns     short loc_18003A741
0x18003a702  mov     property, [rbp+28h]; callerReturnAddress
0x18003a706  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003a70d  mov     r9d, ebx; hr
0x18003a710  mov     [rsp+60h+formatString], rax; formatString
0x18003a715  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a71c  mov     edx, 4B2h; lineNumber
0x18003a721  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a726  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a72a  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a732  test    property, property
0x18003a735  jz      short loc_18003A73D
0x18003a737  call    cs:__imp_CoTaskMemFree
0x18003a73d  mov     eax, ebx
0x18003a73f  jmp     short loc_18003A7B8
0x18003a741  mov     eax, [rbp+length]
0x18003a744  shl     eax, 3
0x18003a747  mov     dword ptr [r14], 1Ch
0x18003a74e  mov     ecx, eax; cb
0x18003a750  mov     [rdi], eax
0x18003a752  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a757  mov     [rsi], rax
0x18003a75a  mov     edx, [rdi]
0x18003a75c  test    rax, rax
0x18003a75f  jnz     short loc_18003A790
0x18003a761  mov     property, [rbp+28h]; callerReturnAddress
0x18003a765  lea     rax, aNewU; "new %u"
0x18003a76c  mov     [rsp+60h+var_38], edx
0x18003a770  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a777  mov     ebx, 8007000Eh
0x18003a77c  mov     [rsp+60h+formatString], rax; formatString
0x18003a781  mov     r9d, ebx; hr
0x18003a784  mov     edx, 4B7h; lineNumber
0x18003a789  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a78e  jmp     short loc_18003A726
0x18003a790  mov     valueBytes, apisetType; Size
0x18003a793  mov     property, rax; void *
0x18003a796  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003a79a  call    memcpy_0
0x18003a79f  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a7a3  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a7ab  test    property, property
0x18003a7ae  jz      short loc_18003A7B6
0x18003a7b0  call    cs:__imp_CoTaskMemFree
0x18003a7b6  xor     eax, eax
0x18003a7b8  add     rsp, 60h
0x18003a7bc  pop     r14
0x18003a7be  pop     rdi
0x18003a7bf  pop     rsi
0x18003a7c0  pop     rbx
0x18003a7c1  pop     rbp
0x18003a7c2  retn
```
