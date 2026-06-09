# Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1026>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x18003a114`
- end: `0x18003a22a`
- name: `?Serialize@?$FixedWidthArraySerializer@$0EAC@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
- size: `278`
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
- `0x180039684`
- `0x18003a114`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a19f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a217`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a19f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a217`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::FixedWidthArraySerializer<1026>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  __int16 *v8; // rcx
  unsigned int v10; // eax
  unsigned __int8 *v11; // rax
  __int16 *v12; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<short,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v15; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v15.pRaw = 0;
  v15.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v15.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1026>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (__int16 **)&v15.pRaw);
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
  v10 = 2 * length;
  *apisetType = STATE_VALUE_INT16_ARRAY;
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
0x18003a114  push    rbp
0x18003a116  push    rbx
0x18003a117  push    rsi
0x18003a118  push    rdi
0x18003a119  push    r14
0x18003a11b  mov     rbp, rsp
0x18003a11e  sub     rsp, 60h
0x18003a122  mov     rdi, valueBytes
0x18003a125  mov     [rbp+length], 0
0x18003a12c  mov     r14, apisetType
0x18003a12f  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a137  lea     rax, [rbp+propertyValueBuffer]
0x18003a13b  mov     [rbp+var_20.pRaw], 0
0x18003a143  lea     valueBytes, [rbp+var_20.pRaw]; value
0x18003a147  mov     [rbp+var_20.wrapper], rax
0x18003a14b  lea     apisetType, [rbp+length]; length
0x18003a14f  mov     [rbp+var_20.replace], 1
0x18003a153  mov     rsi, value
0x18003a156  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAC@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAF@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1026>::GetPropertyValueArrayBase(IInspectable *,uint *,short * *)
0x18003a15b  lea     property, [rbp+var_20]; this
0x18003a15f  mov     ebx, eax
0x18003a161  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003a166  test    ebx, ebx
0x18003a168  jns     short loc_18003A1A9
0x18003a16a  mov     property, [rbp+28h]; callerReturnAddress
0x18003a16e  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x18003a175  mov     r9d, ebx; hr
0x18003a178  mov     [rsp+60h+formatString], rax; formatString
0x18003a17d  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a184  mov     edx, 4B2h; lineNumber
0x18003a189  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a18e  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a192  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a19a  test    property, property
0x18003a19d  jz      short loc_18003A1A5
0x18003a19f  call    cs:__imp_CoTaskMemFree
0x18003a1a5  mov     eax, ebx
0x18003a1a7  jmp     short loc_18003A21F
0x18003a1a9  mov     eax, [rbp+length]
0x18003a1ac  add     eax, eax
0x18003a1ae  mov     dword ptr [r14], 15h
0x18003a1b5  mov     ecx, eax; cb
0x18003a1b7  mov     [rdi], eax
0x18003a1b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a1be  mov     [rsi], rax
0x18003a1c1  mov     edx, [rdi]
0x18003a1c3  test    rax, rax
0x18003a1c6  jnz     short loc_18003A1F7
0x18003a1c8  mov     property, [rbp+28h]; callerReturnAddress
0x18003a1cc  lea     rax, aNewU; "new %u"
0x18003a1d3  mov     [rsp+60h+var_38], edx
0x18003a1d7  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003a1de  mov     ebx, 8007000Eh
0x18003a1e3  mov     [rsp+60h+formatString], rax; formatString
0x18003a1e8  mov     r9d, ebx; hr
0x18003a1eb  mov     edx, 4B7h; lineNumber
0x18003a1f0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a1f5  jmp     short loc_18003A18E
0x18003a1f7  mov     valueBytes, apisetType; Size
0x18003a1fa  mov     property, rax; void *
0x18003a1fd  mov     apisetType, [rbp+propertyValueBuffer.__ptr_.__value_]; Src
0x18003a201  call    memcpy_0
0x18003a206  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x18003a20a  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x18003a212  test    property, property
0x18003a215  jz      short loc_18003A21D
0x18003a217  call    cs:__imp_CoTaskMemFree
0x18003a21d  xor     eax, eax
0x18003a21f  add     rsp, 60h
0x18003a223  pop     r14
0x18003a225  pop     rdi
0x18003a226  pop     rsi
0x18003a227  pop     rbx
0x18003a228  pop     rbp
0x18003a229  retn
```
