# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1030>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003a46c`
- end: `0x18003a583`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAG@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
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
- `0x180039824`
- `0x18003a46c`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a4f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a570`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a4f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a570`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1030>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  __int64 *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  __int64 *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = &propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1030>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             &v15.pRaw);
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
  *apisetType = STATE_VALUE_INT64_ARRAY;
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
0x18003a46c  push    rbp
0x18003a46e  push    rbx
0x18003a46f  push    rsi
0x18003a470  push    rdi
0x18003a471  push    r14
0x18003a473  mov     rbp, rsp
0x18003a476  sub     rsp, 60h
0x18003a47a  mov     rdi, valueBytes
0x18003a47d  mov     [rbp+length], 0
0x18003a484  mov     r14, apisetType
0x18003a487  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a48f  lea     rax, [rbp+propertyValueBuffer]
0x18003a493  mov     [rbp+var_20.pRaw], 0
0x18003a49b  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003a49f  mov     [rbp+var_20.wrapper], rax
0x18003a4a3  lea     apisetType, [rbp+length]; length
0x18003a4a7  mov     [rbp+var_20.replace], 1
0x18003a4ab  mov     rsi, value
0x18003a4ae  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAG@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEA_J@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1030>::GetPropertyValueArrayBase(IInspectable *,uint *,__int64 * *)
0x18003a4b3  lea     property, [rbp+var_20]; this
0x18003a4b7  mov     ebx, eax
0x18003a4b9  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a4be  test    ebx, ebx
0x18003a4c0  jns     short loc_18003A501
0x18003a4c2  mov     property, [rbp+28h]; callerReturnAddress
0x18003a4c6  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003a4cd  mov     r9d, ebx; hr
0x18003a4d0  mov     [rsp+60h+formatString], rax; formatString
0x18003a4d5  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a4dc  mov     edx, 4B2h; lineNumber
0x18003a4e1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a4e6  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a4ea  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a4f2  test    property, property
0x18003a4f5  jz      short loc_18003A4FD
0x18003a4f7  call    cs:__imp_CoTaskMemFree
0x18003a4fd  mov     eax, ebx
0x18003a4ff  jmp     short loc_18003A578
0x18003a501  mov     eax, [rbp+length]
0x18003a504  shl     eax, 3
0x18003a507  mov     dword ptr [r14], 19h
0x18003a50e  mov     ecx, eax; cb
0x18003a510  mov     [rdi], eax
0x18003a512  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a517  mov     [rsi], rax
0x18003a51a  mov     edx, [rdi]
0x18003a51c  test    rax, rax
0x18003a51f  jnz     short loc_18003A550
0x18003a521  mov     property, [rbp+28h]; callerReturnAddress
0x18003a525  lea     rax, aNewU; "new %u"
0x18003a52c  mov     [rsp+60h+var_38], edx
0x18003a530  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a537  mov     ebx, 8007000Eh
0x18003a53c  mov     [rsp+60h+formatString], rax; formatString
0x18003a541  mov     r9d, ebx; hr
0x18003a544  mov     edx, 4B7h; lineNumber
0x18003a549  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a54e  jmp     short loc_18003A4E6
0x18003a550  mov     valueBytes, apisetType; Size
0x18003a553  mov     property, rax; void *
0x18003a556  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003a55a  call    memcpy_0
0x18003a55f  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a563  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a56b  test    property, property
0x18003a56e  jz      short loc_18003A576
0x18003a570  call    cs:__imp_CoTaskMemFree
0x18003a576  xor     eax, eax
0x18003a578  add     rsp, 60h
0x18003a57c  pop     r14
0x18003a57e  pop     rdi
0x18003a57f  pop     rsi
0x18003a580  pop     rbx
0x18003a581  pop     rbp
0x18003a582  retn
```
