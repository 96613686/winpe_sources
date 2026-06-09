# Windows::Storage::StateABIHelpers::VariableWidthArraySerializer<1036>::Serialize(IInspectable *,tag_STATE_VALUE_TYPE *,uint *,uchar * *)

- ea: `0x180022eec`
- end: `0x1800230d3`
- name: `?Serialize@?$VariableWidthArraySerializer@$0EAM@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAW4tag_STATE_VALUE_TYPE@@PEAIPEAPEAE@Z`
- size: `487`
- prototype: `HRESULT __fastcall(IInspectable *property, tag_STATE_VALUE_TYPE *apisetType, unsigned int *valueBytes, unsigned __int8 **value)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000af34`

## callees

- `0x180009778`
- `0x18000aa74`
- `0x1800226d8`
- `0x180022d1c`
- `0x180022eec`
- `0x180024fc4`
- `0x180025004`
- `0x1800415e2`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180022fa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180023017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180022fa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180023017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800230bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800230bc`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::VariableWidthArraySerializer<1036>::Serialize(
        IInspectable *property,
        tag_STATE_VALUE_TYPE *apisetType,
        unsigned int *valueBytes,
        unsigned __int8 **value)
{
  HRESULT PropertyValueArrayBase; // ebx
  HSTRING__ **v8; // rcx
  HSTRING__ **v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // esi
  UINT32 StringLen; // eax
  unsigned __int8 *v14; // rax
  _DWORD *v15; // rbx
  HSTRING__ **v16; // r14
  unsigned int i; // esi
  UINT32 v18; // edx
  __int64 v19; // r15
  PCWSTR StringRawBuffer; // rax
  HSTRING__ **v21; // rcx
  unsigned int length; // [rsp+30h] [rbp-30h] BYREF
  wistd::unique_ptr<HSTRING__ *,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > propertyValueBuffer; // [rsp+38h] [rbp-28h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > > v24; // [rsp+40h] [rbp-20h] BYREF
  void *retaddr; // [rsp+98h] [rbp+38h]

  length = 0;
  propertyValueBuffer.__ptr_.__value_ = 0;
  v24.pRaw = 0;
  v24.wrapper = (wistd::unique_ptr<__int64,wil::function_deleter<void (__cdecl*)(void *),&CoTaskMemFree> > *)&propertyValueBuffer;
  v24.replace = 1;
  PropertyValueArrayBase = Windows::Storage::StateABIHelpers::PropertyValueTraits<1036>::GetPropertyValueArrayBase(
                             property,
                             &length,
                             (HSTRING__ ***)&v24.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v24);
  if ( PropertyValueArrayBase < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x4E6u,
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
  v10 = propertyValueBuffer.__ptr_.__value_;
  v11 = 0;
  *apisetType = STATE_VALUE_STRING_ARRAY;
  v12 = 0;
  for ( *valueBytes = 0; v12 < length; v11 = *valueBytes )
  {
    StringLen = WindowsGetStringLen(*v10);
    ++v12;
    ++v10;
    *valueBytes += 2 * StringLen + 6;
  }
  v14 = (unsigned __int8 *)operator new(v11);
  *value = v14;
  v15 = v14;
  if ( !v14 )
  {
    PropertyValueArrayBase = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x4F6u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
      -2147024882,
      "new %u",
      *valueBytes);
    goto LABEL_3;
  }
  v16 = propertyValueBuffer.__ptr_.__value_;
  for ( i = 0; i < length; ++i )
  {
    v18 = 2 * WindowsGetStringLen(*v16) + 2;
    v19 = v18;
    if ( (__int64)v15 + v18 - (_QWORD)*value + 4 > *valueBytes )
    {
      operator delete(*value);
      *value = 0;
      PropertyValueArrayBase = wil::details::in1diag3::Return_Win32Msg(
                                 retaddr,
                                 0x505u,
                                 "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
                                 0x6Fu,
                                 "Bytes %u",
                                 *valueBytes);
      goto LABEL_3;
    }
    *v15 = v18;
    StringRawBuffer = WindowsGetStringRawBuffer(*v16, 0);
    memcpy_0(v15 + 1, StringRawBuffer, (unsigned int)v19);
    v15 = (_DWORD *)((char *)v15 + v19 + 4);
    ++v16;
  }
  v21 = propertyValueBuffer.__ptr_.__value_;
  propertyValueBuffer.__ptr_.__value_ = 0;
  if ( v21 )
    CoTaskMemFree(v21);
  return 0;
}

```

## disassembly

```asm
0x180022eec  push    rbp
0x180022eee  push    rbx
0x180022eef  push    rsi
0x180022ef0  push    rdi
0x180022ef1  push    r12
0x180022ef3  push    r14
0x180022ef5  push    r15
0x180022ef7  mov     rbp, rsp
0x180022efa  sub     rsp, 60h
0x180022efe  mov     rdi, valueBytes
0x180022f01  mov     [rbp+length], 0
0x180022f08  mov     rsi, apisetType
0x180022f0b  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x180022f13  lea     rax, [rbp+propertyValueBuffer]
0x180022f17  mov     [rbp+var_20.pRaw], 0
0x180022f1f  lea     valueBytes, [rbp+var_20.pRaw]; value
0x180022f23  mov     [rbp+var_20.wrapper], rax
0x180022f27  lea     apisetType, [rbp+length]; length
0x180022f2b  mov     [rbp+var_20.replace], 1
0x180022f2f  mov     r12, value
0x180022f32  call    ?GetPropertyValueArrayBase@?$PropertyValueTraits@$0EAM@@StateABIHelpers@Storage@Windows@@SAJPEAUIInspectable@@PEAIPEAPEAPEAUHSTRING__@@@Z; Windows::Storage::StateABIHelpers::PropertyValueTraits<1036>::GetPropertyValueArrayBase(IInspectable *,uint *,HSTRING__ * * *)
0x180022f37  lea     property, [rbp+var_20]; this
0x180022f3b  mov     ebx, eax
0x180022f3d  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180022f42  test    ebx, ebx
0x180022f44  jns     short loc_180022F88
0x180022f46  mov     property, [rbp+38h]; callerReturnAddress
0x180022f4a  lea     rax, aGetpropertyval_2; "GetPropertyValueArrayBase"
0x180022f51  mov     r9d, ebx; hr
0x180022f54  mov     [rsp+60h+formatString], rax; formatString
0x180022f59  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x180022f60  mov     edx, 4E6h; lineNumber
0x180022f65  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180022f6a  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x180022f6e  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x180022f76  test    property, property
0x180022f79  jz      short loc_180022F81
0x180022f7b  call    cs:__imp_CoTaskMemFree
0x180022f81  mov     eax, ebx
0x180022f83  jmp     loc_1800230C4
0x180022f88  mov     rbx, [rbp+propertyValueBuffer.__ptr_.__value_]
0x180022f8c  xor     eax, eax
0x180022f8e  mov     dword ptr [rsi], 1Fh
0x180022f94  xor     esi, esi
0x180022f96  mov     dword ptr [rdi], 0
0x180022f9c  cmp     [rbp+length], eax
0x180022f9f  jbe     short loc_180022FBE
0x180022fa1  mov     property, [rbx]; string
0x180022fa4  call    cs:__imp_WindowsGetStringLen
0x180022faa  inc     esi
0x180022fac  lea     rbx, [rbx+8]
0x180022fb0  add     eax, eax
0x180022fb2  add     eax, 6
0x180022fb5  add     [rdi], eax
0x180022fb7  mov     eax, [rdi]
0x180022fb9  cmp     esi, [rbp+length]
0x180022fbc  jb      short loc_180022FA1
0x180022fbe  mov     ecx, eax; cb
0x180022fc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022fc5  mov     [r12], rax
0x180022fc9  mov     rbx, rax
0x180022fcc  test    rax, rax
0x180022fcf  jnz     short loc_180023005
0x180022fd1  mov     eax, [rdi]
0x180022fd3  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x180022fda  mov     property, [rbp+38h]; callerReturnAddress
0x180022fde  mov     ebx, 8007000Eh
0x180022fe3  mov     [rsp+60h+var_38], eax
0x180022fe7  mov     r9d, ebx; hr
0x180022fea  lea     rax, aNewU; "new %u"
0x180022ff1  mov     edx, 4F6h; lineNumber
0x180022ff6  mov     [rsp+60h+formatString], rax; formatString
0x180022ffb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023000  jmp     loc_180022F6A
0x180023005  mov     r14, [rbp+propertyValueBuffer.__ptr_.__value_]
0x180023009  xor     esi, esi
0x18002300b  cmp     esi, [rbp+length]
0x18002300e  jnb     loc_1800230AB
0x180023014  mov     property, [r14]; string
0x180023017  call    cs:__imp_WindowsGetStringLen
0x18002301d  lea     edx, ds:2[rax*2]
0x180023024  mov     eax, [rdi]
0x180023026  mov     ecx, edx
0x180023028  sub     property, [r12]
0x18002302c  add     property, 4
0x180023030  mov     r15d, edx
0x180023033  add     property, rbx
0x180023036  cmp     property, rax
0x180023039  jg      short loc_180023066
0x18002303b  mov     [rbx], edx
0x18002303d  xor     edx, edx; length
0x18002303f  mov     property, [r14]; string
0x180023042  call    cs:__imp_WindowsGetStringRawBuffer
0x180023048  lea     property, [rbx+4]; void *
0x18002304c  mov     r8d, r15d; Size
0x18002304f  mov     apisetType, rax; Src
0x180023052  call    memcpy_0
0x180023057  add     rbx, 4
0x18002305b  inc     esi
0x18002305d  add     rbx, r15
0x180023060  add     r14, 8
0x180023064  jmp     short loc_18002300B
0x180023066  mov     property, [r12]; p
0x18002306a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002306f  mov     property, [rbp+38h]; callerReturnAddress
0x180023073  lea     valueBytes, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002307a  mov     qword ptr [r12], 0
0x180023082  mov     r9d, 6Fh ; 'o'; err
0x180023088  mov     eax, [rdi]
0x18002308a  mov     edx, 505h; lineNumber
0x18002308f  mov     [rsp+60h+var_38], eax
0x180023093  lea     rax, aBytesU; "Bytes %u"
0x18002309a  mov     [rsp+60h+formatString], rax; formatString
0x18002309f  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800230a4  mov     ebx, eax
0x1800230a6  jmp     loc_180022F6A
0x1800230ab  mov     property, [rbp+propertyValueBuffer.__ptr_.__value_]; pv
0x1800230af  mov     [rbp+propertyValueBuffer.__ptr_.__value_], 0
0x1800230b7  test    property, property
0x1800230ba  jz      short loc_1800230C2
0x1800230bc  call    cs:__imp_CoTaskMemFree
0x1800230c2  xor     eax, eax
0x1800230c4  add     rsp, 60h
0x1800230c8  pop     r15
0x1800230ca  pop     r14
0x1800230cc  pop     r12
0x1800230ce  pop     rdi
0x1800230cf  pop     rsi
0x1800230d0  pop     rbx
0x1800230d1  pop     rbp
0x1800230d2  retn
```
