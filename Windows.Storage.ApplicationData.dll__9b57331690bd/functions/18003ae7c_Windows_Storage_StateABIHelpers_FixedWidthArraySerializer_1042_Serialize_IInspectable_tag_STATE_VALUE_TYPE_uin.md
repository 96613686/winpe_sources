# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1042>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003ae7c`
- end: `0x18003af93`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EBC@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
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
- `0x180039f74`
- `0x18003ae7c`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af80`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1042>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  Windows::Foundation::Size *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  Windows::Foundation::Size *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<Windows::Foundation::Size,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1042>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (Windows::Foundation::Size **)&v15.pRaw);
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
  *apisetType = STATE_VALUE_SIZE_ARRAY;
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
0x18003ae7c  push    rbp
0x18003ae7e  push    rbx
0x18003ae7f  push    rsi
0x18003ae80  push    rdi
0x18003ae81  push    r14
0x18003ae83  mov     rbp, rsp
0x18003ae86  sub     rsp, 60h
0x18003ae8a  mov     rdi, valueBytes
0x18003ae8d  mov     [rbp+length], 0
0x18003ae94  mov     r14, apisetType
0x18003ae97  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003ae9f  lea     rax, [rbp+propertyValueBuffer]
0x18003aea3  mov     [rbp+var_20.pRaw], 0
0x18003aeab  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003aeaf  mov     [rbp+var_20.wrapper], rax
0x18003aeb3  lea     apisetType, [rbp+length]; length
0x18003aeb7  mov     [rbp+var_20.replace], 1
0x18003aebb  mov     rsi, value
0x18003aebe  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EBC@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAUSize@Foundation@4@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1042>::GetPropertyValueArrayBase(IInspectable *,uint *,Windows::Foundation::Size * *)
0x18003aec3  lea     property, [rbp+var_20]; this
0x18003aec7  mov     ebx, eax
0x18003aec9  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003aece  test    ebx, ebx
0x18003aed0  jns     short loc_18003AF11
0x18003aed2  mov     property, [rbp+28h]; callerReturnAddress
0x18003aed6  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003aedd  mov     r9d, ebx; hr
0x18003aee0  mov     [rsp+60h+formatString], rax; formatString
0x18003aee5  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003aeec  mov     edx, 4B2h; lineNumber
0x18003aef1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003aef6  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003aefa  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003af02  test    property, property
0x18003af05  jz      short loc_18003AF0D
0x18003af07  call    cs:__imp_CoTaskMemFree
0x18003af0d  mov     eax, ebx
0x18003af0f  jmp     short loc_18003AF88
0x18003af11  mov     eax, [rbp+length]
0x18003af14  shl     eax, 3
0x18003af17  mov     dword ptr [r14], 25h ; '%'
0x18003af1e  mov     ecx, eax; cb
0x18003af20  mov     [rdi], eax
0x18003af22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003af27  mov     [rsi], rax
0x18003af2a  mov     edx, [rdi]
0x18003af2c  test    rax, rax
0x18003af2f  jnz     short loc_18003AF60
0x18003af31  mov     property, [rbp+28h]; callerReturnAddress
0x18003af35  lea     rax, aNewU; "new %u"
0x18003af3c  mov     [rsp+60h+var_38], edx
0x18003af40  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003af47  mov     ebx, 8007000Eh
0x18003af4c  mov     [rsp+60h+formatString], rax; formatString
0x18003af51  mov     r9d, ebx; hr
0x18003af54  mov     edx, 4B7h; lineNumber
0x18003af59  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003af5e  jmp     short loc_18003AEF6
0x18003af60  mov     valueBytes, apisetType; Size
0x18003af63  mov     property, rax; void *
0x18003af66  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003af6a  call    memcpy_0
0x18003af6f  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003af73  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003af7b  test    property, property
0x18003af7e  jz      short loc_18003AF86
0x18003af80  call    cs:__imp_CoTaskMemFree
0x18003af86  xor     eax, eax
0x18003af88  add     rsp, 60h
0x18003af8c  pop     r14
0x18003af8e  pop     rdi
0x18003af8f  pop     rsi
0x18003af90  pop     rbx
0x18003af91  pop     rbp
0x18003af92  retn
```
