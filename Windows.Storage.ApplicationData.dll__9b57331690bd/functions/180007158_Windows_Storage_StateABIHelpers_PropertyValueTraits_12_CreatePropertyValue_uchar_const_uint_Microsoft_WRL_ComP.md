# Windows::Storage::StateABIHelpers::PropertyValueTraits<12>::CreatePropertyValue(uchar const *,uint,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)

- ea: `0x180007158`
- end: `0x180007279`
- name: `?CreatePropertyValue@?$PropertyValueTraits@$0M@@StateABIHelpers@Storage@Windows@@SAJPEBEIAEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z`
- size: `289`
- prototype: `HRESULT __fastcall(const unsigned __int8 *valueBuffer, const unsigned int valueBufferBytes, Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterface, IInspectable **propertyValue)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009ea8`

## callees

- `0x180007158`
- `0x180007580`
- `0x180009778`
- `0x1800127c0`
- `0x1800173ec`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000717e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000717e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800071f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800071f5`

## string_xrefs

- `0x18000720c`: `WindowsCreateString %u`
- `0x18000724d`: `CreateString %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::PropertyValueTraits<12>::CreatePropertyValue(
        const wchar_t *valueBuffer,
        unsigned int valueBufferBytes,
        Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterface,
        IInspectable **propertyValue)
{
  int v7; // ebx
  Windows::Foundation::IPropertyValueStatics *ptr; // rcx
  Windows::Foundation::IPropertyValueStatics_vtbl *v9; // rax
  HSTRING__ *m_ptr; // rcx
  PCWSTR StringRawBuffer; // rax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > string; // [rsp+30h] [rbp-30h] BYREF
  RoVariant newProperty; // [rsp+38h] [rbp-28h] BYREF
  RoVariant *p_newProperty; // [rsp+48h] [rbp-18h]
  IInspectable *pI; // [rsp+50h] [rbp-10h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]

  string.m_ptr = 0;
  v7 = WindowsCreateString(valueBuffer, (valueBufferBytes >> 1) - 1, &string.m_ptr);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x18Du,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
      v7,
      "WindowsCreateString %u",
      valueBufferBytes);
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    return (unsigned int)v7;
  }
  ptr = propertyValueStaticInterface->ptr_;
  newProperty._pI = 0;
  newProperty._hrState = 0;
  v9 = ptr->__vftable;
  p_newProperty = &newProperty;
  pI = 0;
  v7 = v9->CreateString(ptr, string.m_ptr, &pI);
  RoVariant::Attach(p_newProperty, pI);
  m_ptr = string.m_ptr;
  if ( v7 < 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string.m_ptr, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x191u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABISettingPropertyToApiSetValue.hpp",
      v7,
      "CreateString %ws",
      StringRawBuffer);
    RoVariant::~RoVariant(&newProperty);
    goto LABEL_8;
  }
  *propertyValue = newProperty._pI;
  newProperty._pI = 0;
  newProperty._hrState = 0;
  if ( m_ptr )
    WindowsDeleteString(m_ptr);
  return 0;
}

```

## disassembly

```asm
0x180007158  push    rbp
0x18000715a  push    rbx
0x18000715b  push    rsi
0x18000715c  push    rdi
0x18000715d  push    r14
0x18000715f  mov     rbp, rsp
0x180007162  sub     rsp, 60h
0x180007166  mov     edi, valueBufferBytes
0x180007168  mov     [rbp+string.m_ptr], 0
0x180007170  shr     valueBufferBytes, 1
0x180007172  mov     r14, propertyValueStaticInterface
0x180007175  dec     valueBufferBytes; length
0x180007177  lea     propertyValueStaticInterface, [rbp+string]; string
0x18000717b  mov     rsi, propertyValue
0x18000717e  call    cs:__imp_WindowsCreateString
0x180007184  mov     ebx, eax
0x180007186  test    eax, eax
0x180007188  js      short loc_180007208
0x18000718a  mov     valueBuffer, [r14]
0x18000718d  lea     rdx, [rbp+newProperty]
0x180007191  mov     [rbp+newProperty._pI], 0
0x180007199  lea     propertyValueStaticInterface, [rbp+pI]
0x18000719d  mov     [rbp+newProperty._hrState], 0
0x1800071a4  mov     rax, [valueBuffer]
0x1800071a7  mov     [rbp+var_18], rdx
0x1800071ab  mov     rdx, [rbp+string.m_ptr]
0x1800071af  mov     [rbp+pI], 0
0x1800071b7  mov     rax, [rax+90h]
0x1800071be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c3  mov     rdx, [rbp+pI]; pI
0x1800071c7  mov     ebx, eax
0x1800071c9  mov     valueBuffer, [rbp+var_18]; this
0x1800071cd  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x1800071d2  mov     valueBuffer, [rbp+string.m_ptr]; string
0x1800071d6  test    ebx, ebx
0x1800071d8  js      short loc_180007232
0x1800071da  mov     rax, [rbp+newProperty._pI]
0x1800071de  mov     [rsi], rax
0x1800071e1  mov     [rbp+newProperty._pI], 0
0x1800071e9  mov     [rbp+newProperty._hrState], 0
0x1800071f0  test    valueBuffer, valueBuffer
0x1800071f3  jz      short loc_1800071FB
0x1800071f5  call    cs:__imp_WindowsDeleteString
0x1800071fb  xor     eax, eax
0x1800071fd  add     rsp, 60h
0x180007201  pop     r14
0x180007203  pop     rdi
0x180007204  pop     rsi
0x180007205  pop     rbx
0x180007206  pop     rbp
0x180007207  retn
0x180007208  mov     valueBuffer, [rbp+28h]; callerReturnAddress
0x18000720c  lea     rax, aWindowscreates_2; "WindowsCreateString %u"
0x180007213  mov     dword ptr [rsp+60h+var_38], edi
0x180007217  lea     propertyValueStaticInterface, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000721e  mov     r9d, ebx; hr
0x180007221  mov     [rsp+60h+formatString], rax; formatString
0x180007226  mov     valueBufferBytes, 18Dh; lineNumber
0x18000722b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007230  jmp     short loc_18000726C
0x180007232  xor     valueBufferBytes, valueBufferBytes; length
0x180007234  call    cs:__imp_WindowsGetStringRawBuffer
0x18000723a  mov     valueBuffer, [rbp+28h]; callerReturnAddress
0x18000723e  lea     propertyValueStaticInterface, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\statemanage"...
0x180007245  mov     [rsp+60h+var_38], rax
0x18000724a  mov     r9d, ebx; hr
0x18000724d  lea     rax, aCreatestringWs; "CreateString %ws"
0x180007254  mov     valueBufferBytes, 191h; lineNumber
0x180007259  mov     [rsp+60h+formatString], rax; formatString
0x18000725e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007263  lea     valueBuffer, [rbp+newProperty]; this
0x180007267  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18000726c  lea     valueBuffer, [rbp+string]; this
0x180007270  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180007275  mov     eax, ebx
0x180007277  jmp     short loc_1800071FD
```
