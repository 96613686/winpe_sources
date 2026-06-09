# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1041>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003ad5c`
- end: `0x18003ae73`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EBB@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
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
- `0x180039ea4`
- `0x18003ad5c`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ade7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ade7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae60`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1041>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  Windows::Foundation::Point *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  Windows::Foundation::Point *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<Windows::Foundation::Point,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1041>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (Windows::Foundation::Point **)&v15.pRaw);
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
  *apisetType = STATE_VALUE_POINT_ARRAY;
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
0x18003ad5c  push    rbp
0x18003ad5e  push    rbx
0x18003ad5f  push    rsi
0x18003ad60  push    rdi
0x18003ad61  push    r14
0x18003ad63  mov     rbp, rsp
0x18003ad66  sub     rsp, 60h
0x18003ad6a  mov     rdi, valueBytes
0x18003ad6d  mov     [rbp+length], 0
0x18003ad74  mov     r14, apisetType
0x18003ad77  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003ad7f  lea     rax, [rbp+propertyValueBuffer]
0x18003ad83  mov     [rbp+var_20.pRaw], 0
0x18003ad8b  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003ad8f  mov     [rbp+var_20.wrapper], rax
0x18003ad93  lea     apisetType, [rbp+length]; length
0x18003ad97  mov     [rbp+var_20.replace], 1
0x18003ad9b  mov     rsi, value
0x18003ad9e  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EBB@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAUPoint@Foundation@4@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1041>::GetPropertyValueArrayBase(IInspectable *,uint *,Windows::Foundation::Point * *)
0x18003ada3  lea     property, [rbp+var_20]; this
0x18003ada7  mov     ebx, eax
0x18003ada9  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003adae  test    ebx, ebx
0x18003adb0  jns     short loc_18003ADF1
0x18003adb2  mov     property, [rbp+28h]; callerReturnAddress
0x18003adb6  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003adbd  mov     r9d, ebx; hr
0x18003adc0  mov     [rsp+60h+formatString], rax; formatString
0x18003adc5  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003adcc  mov     edx, 4B2h; lineNumber
0x18003add1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003add6  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003adda  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003ade2  test    property, property
0x18003ade5  jz      short loc_18003ADED
0x18003ade7  call    cs:__imp_CoTaskMemFree
0x18003aded  mov     eax, ebx
0x18003adef  jmp     short loc_18003AE68
0x18003adf1  mov     eax, [rbp+length]
0x18003adf4  shl     eax, 3
0x18003adf7  mov     dword ptr [r14], 24h ; '$'
0x18003adfe  mov     ecx, eax; cb
0x18003ae00  mov     [rdi], eax
0x18003ae02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ae07  mov     [rsi], rax
0x18003ae0a  mov     edx, [rdi]
0x18003ae0c  test    rax, rax
0x18003ae0f  jnz     short loc_18003AE40
0x18003ae11  mov     property, [rbp+28h]; callerReturnAddress
0x18003ae15  lea     rax, aNewU; "new %u"
0x18003ae1c  mov     [rsp+60h+var_38], edx
0x18003ae20  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003ae27  mov     ebx, 8007000Eh
0x18003ae2c  mov     [rsp+60h+formatString], rax; formatString
0x18003ae31  mov     r9d, ebx; hr
0x18003ae34  mov     edx, 4B7h; lineNumber
0x18003ae39  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003ae3e  jmp     short loc_18003ADD6
0x18003ae40  mov     valueBytes, apisetType; Size
0x18003ae43  mov     property, rax; void *
0x18003ae46  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003ae4a  call    memcpy_0
0x18003ae4f  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003ae53  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003ae5b  test    property, property
0x18003ae5e  jz      short loc_18003AE66
0x18003ae60  call    cs:__imp_CoTaskMemFree
0x18003ae66  xor     eax, eax
0x18003ae68  add     rsp, 60h
0x18003ae6c  pop     r14
0x18003ae6e  pop     rdi
0x18003ae6f  pop     rsi
0x18003ae70  pop     rbx
0x18003ae71  pop     rbp
0x18003ae72  retn
```
