# XamlDiagnostics::GetEnums(uint *,EnumType * *)

- ea: `0x1809b0010`
- end: `0x1809b041e`
- name: `?GetEnums@XamlDiagnostics@@UEAAJPEAIPEAPEAUEnumType@@@Z`
- size: `1038`
- prototype: `HRESULT __fastcall(XamlDiagnostics *this, unsigned int *pCount, EnumType **ppEnums)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004bc0`
- `0x180004d14`
- `0x180004d2c`
- `0x1800990a0`
- `0x1805313a4`
- `0x1806225c4`
- `0x1806861f4`
- `0x180688828`
- `0x180743c48`
- `0x18076e110`
- `0x18076f098`
- `0x18076f0a4`
- `0x1807b4260`
- `0x1809ae188`
- `0x1809b0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1809b010a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1809b010a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1809b02b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1809b02b2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1809b0241`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1809b0252`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1809b0241`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1809b0252`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1809b013c`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1809b0161`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1809b013c`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1809b0161`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1809b01f2`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1809b01ff`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1809b0239`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1809b024a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1809b01f2`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1809b01ff`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1809b0239`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1809b024a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1809b0130`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1809b0155`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1809b0130`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1809b0155`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XamlDiagnostics::GetEnums(XamlDiagnostics *this, unsigned int *pCount, EnumType **ppEnums)
{
  EnumType **v3; // r15
  HRESULT v4; // ecx
  __int64 v5; // rsi
  char v6; // r12
  int v7; // r13d
  __int64 v8; // r8
  HRESULT v9; // ebx
  DebugTool::DebugEnumInfo2 *Myfirst; // r14
  DebugTool::DebugEnumInfo2 *Mylast; // rdi
  const wchar_t *StringRawBuffer; // rax
  SAFEARRAY *Vector; // rbx
  SAFEARRAY *v14; // r15
  wchar_t *m_ptr; // rcx
  std::pair<int,unsigned short const *> *v16; // rdx
  unsigned __int64 v17; // r12
  wchar_t *v18; // rcx
  EnumType *v19; // rdx
  signed __int64 v20; // rdx
  size_t v21; // rbx
  EnumType *v22; // rdi
  std::allocator<DebugTool::DebugEnumInfo2> *v23; // r8
  EnumType *v24; // rcx
  __int64 v25; // rax
  std::allocator<DebugTool::DebugEnumInfo2> *v26; // r8
  char v27; // [rsp+20h] [rbp-A9h]
  ComValueCollection<EnumType> result; // [rsp+28h] [rbp-A1h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > valueString; // [rsp+40h] [rbp-89h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > name; // [rsp+48h] [rbp-81h] BYREF
  Collection<DebugTool::DebugEnumInfo2> enums; // [rsp+50h] [rbp-79h] BYREF
  DebugTool::DebugEnumInfo2 *v32; // [rsp+70h] [rbp-59h]
  EnumType **v33; // [rsp+78h] [rbp-51h]
  unsigned int *v34; // [rsp+80h] [rbp-49h]
  EnumType enumType; // [rsp+88h] [rbp-41h] BYREF
  std::function<long __cdecl(void)> function; // [rsp+A0h] [rbp-29h] BYREF

  v3 = ppEnums;
  v33 = ppEnums;
  v34 = pCount;
  v4 = tls_index;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v6 = *(_BYTE *)(v5 + 320);
  v27 = v6;
  v7 = *(_DWORD *)(v5 + 324);
  *(_BYTE *)(v5 + 320) = 1;
  *(_DWORD *)(v5 + 324) = 0;
  if ( !ppEnums )
  {
    OnNewFailure_1172_(v4);
    *(_DWORD *)(v5 + 324) = v7;
    v25 = 2147500035LL;
LABEL_24:
    *(_BYTE *)(v5 + 320) = v6;
    return v25;
  }
  *ppEnums = 0;
  *pCount = 0;
  enums.__vftable = (Collection<DebugTool::DebugEnumInfo2>_vtbl *)Collection<DebugTool::DebugEnumInfo2>::`vftable';
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>((std::vector<DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0>> *)&enums.m_vector);
  function._Mystorage._Ptrs[0] = (std::_Func_base<long> *)std::_Func_impl_no_alloc__lambda_37e17ed62652cb07abceba93af3e1421__long_::_vftable_;
  function._Mystorage._Ptrs[1] = (std::_Func_base<long> *)(v8 - 8);
  function._Mystorage._Ptrs[2] = (std::_Func_base<long> *)&enums;
  function._Mystorage._Ptrs[7] = (std::_Func_base<long> *)&function;
  v9 = XamlDiagnosticsHelpers::RunOnUIThread(*(Windows::UI::Core::ICoreDispatcher **)(v8 + 144), &function);
  std::_Func_class<long,CDependencyObject *,enum CFlyoutBase::MajorPlacementMode>::_Tidy((std::_Func_class<long,enum ABI::Windows::Foundation::AsyncStatus,IInspectable *> *)&function);
  if ( v9 < 0 )
  {
    OnFailure_2990_(v9);
    if ( enums.m_vector._Mypair._Myval2._Myfirst )
    {
      std::_Destroy_range<std::allocator<DebugTool::DebugEnumInfo2>>(
        enums.m_vector._Mypair._Myval2._Myfirst,
        enums.m_vector._Mypair._Myval2._Mylast,
        v26);
      std::_Deallocate<16>(
        enums.m_vector._Mypair._Myval2._Myfirst,
        40 * (enums.m_vector._Mypair._Myval2._Myend - enums.m_vector._Mypair._Myval2._Myfirst));
    }
    *(_DWORD *)(v5 + 324) = v7;
    v25 = (unsigned int)v9;
    goto LABEL_24;
  }
  DirectUI::TrackerPtrVector<Windows::Foundation::IEventHandler<Windows::UI::Xaml::Controls::ScrollViewerViewChangingEventArgs *>>::TrackerPtrVector<Windows::Foundation::IEventHandler<Windows::UI::Xaml::Controls::ScrollViewerViewChangingEventArgs *>>((DirectUI::TrackerPtrVector<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> > *)&result);
  Myfirst = enums.m_vector._Mypair._Myval2._Myfirst;
  Mylast = enums.m_vector._Mypair._Myval2._Mylast;
  v32 = enums.m_vector._Mypair._Myval2._Mylast;
  if ( enums.m_vector._Mypair._Myval2._Myfirst != enums.m_vector._Mypair._Myval2._Mylast )
  {
    do
    {
      StringRawBuffer = WindowsGetStringRawBuffer(Myfirst->m_name._hstring, 0);
      wil::make_bstr_nothrow(&name, StringRawBuffer);
      Vector = SafeArrayCreateVector(
                 0x16u,
                 0,
                 Myfirst->m_values._Mypair._Myval2._Mylast - Myfirst->m_values._Mypair._Myval2._Myfirst);
      SafeArrayLock(Vector);
      v14 = SafeArrayCreateVector(
              8u,
              0,
              Myfirst->m_values._Mypair._Myval2._Mylast - Myfirst->m_values._Mypair._Myval2._Myfirst);
      SafeArrayLock(v14);
      m_ptr = name.m_ptr;
      name.m_ptr = 0;
      enumType.Name = m_ptr;
      v16 = Myfirst->m_values._Mypair._Myval2._Myfirst;
      if ( Myfirst->m_values._Mypair._Myval2._Mylast - v16 )
      {
        v17 = 0;
        do
        {
          wil::make_bstr_nothrow(&valueString, v16[v17].second);
          *((_DWORD *)Vector->pvData + v17) = Myfirst->m_values._Mypair._Myval2._Myfirst[v17].first;
          v18 = valueString.m_ptr;
          valueString.m_ptr = 0;
          *((_QWORD *)v14->pvData + v17) = v18;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&valueString);
          ++v17;
          v16 = Myfirst->m_values._Mypair._Myval2._Myfirst;
        }
        while ( v17 < Myfirst->m_values._Mypair._Myval2._Mylast - v16 );
        Mylast = v32;
      }
      SafeArrayUnlock(Vector);
      enumType.ValueInts = Vector;
      SafeArrayUnlock(v14);
      enumType.ValueStrings = v14;
      v19 = result.m_vector._Mypair._Myval2._Mylast;
      if ( result.m_vector._Mypair._Myval2._Mylast == result.m_vector._Mypair._Myval2._Myend )
      {
        std::vector<HighlightRegion>::_Emplace_reallocate<HighlightRegion const &>(
          (std::vector<std::pair<CDependencyObject *,AccessKeys::AKAccessKey>> *)&result,
          (std::pair<CDependencyObject *,AccessKeys::AKAccessKey> *const)result.m_vector._Mypair._Myval2._Mylast,
          (std::pair<CDependencyObject *,AccessKeys::AKAccessKey> *)&enumType);
      }
      else
      {
        *(_OWORD *)result.m_vector._Mypair._Myval2._Mylast = *(_OWORD *)&enumType.Name;
        v19->ValueStrings = v14;
        ++result.m_vector._Mypair._Myval2._Mylast;
      }
      SafeArrayUnlock(0);
      SafeArrayDestroy(0);
      SafeArrayUnlock(0);
      SafeArrayDestroy(0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&name);
      ++Myfirst;
    }
    while ( Myfirst != Mylast );
    v6 = v27;
    v3 = v33;
  }
  v20 = result.m_vector._Mypair._Myval2._Mylast - result.m_vector._Mypair._Myval2._Myfirst;
  *v34 = v20;
  v21 = 24 * v20;
  v22 = (EnumType *)CoTaskMemAlloc(24 * v20);
  memset_0(v22, 0, v21);
  memmove_0(
    v22,
    result.m_vector._Mypair._Myval2._Myfirst,
    (char *)result.m_vector._Mypair._Myval2._Mylast - (char *)result.m_vector._Mypair._Myval2._Myfirst);
  v24 = result.m_vector._Mypair._Myval2._Myfirst;
  if ( result.m_vector._Mypair._Myval2._Myfirst != result.m_vector._Mypair._Myval2._Mylast )
    result.m_vector._Mypair._Myval2._Mylast = result.m_vector._Mypair._Myval2._Myfirst;
  *v3 = v22;
  if ( v24 )
  {
    std::_Deallocate<16>(v24, 24 * (result.m_vector._Mypair._Myval2._Myend - v24));
    memset(&result, 0, sizeof(result));
  }
  if ( enums.m_vector._Mypair._Myval2._Myfirst )
  {
    std::_Destroy_range<std::allocator<DebugTool::DebugEnumInfo2>>(
      enums.m_vector._Mypair._Myval2._Myfirst,
      enums.m_vector._Mypair._Myval2._Mylast,
      v23);
    std::_Deallocate<16>(
      enums.m_vector._Mypair._Myval2._Myfirst,
      40 * (enums.m_vector._Mypair._Myval2._Myend - enums.m_vector._Mypair._Myval2._Myfirst));
  }
  *(_BYTE *)(v5 + 320) = v6;
  *(_DWORD *)(v5 + 324) = v7;
  return 0;
}

```

## disassembly

```asm
0x1809b0010  mov     [rsp-8+arg_18], rbx
0x1809b0015  push    rbp
0x1809b0016  push    rsi
0x1809b0017  push    rdi
0x1809b0018  push    r12
0x1809b001a  push    r13
0x1809b001c  push    r14
0x1809b001e  push    r15
0x1809b0020  lea     rbp, [rsp-27h]
0x1809b0025  sub     rsp, 0F0h
0x1809b002c  mov     rax, cs:__security_cookie
0x1809b0033  xor     rax, rsp
0x1809b0036  mov     [rbp+57h+var_40], rax
0x1809b003a  mov     r15, ppEnums
0x1809b003d  mov     [rbp+57h+var_A8], ppEnums
0x1809b0041  mov     [rbp+57h+var_A0], pCount
0x1809b0045  mov     ppEnums, this
0x1809b0048  mov     ecx, cs:_tls_index; failedFrameHR
0x1809b004e  mov     rax, gs:58h
0x1809b0057  mov     rsi, [rax+this*8]
0x1809b005b  mov     r14d, 140h
0x1809b0061  mov     r12b, [r14+rsi]
0x1809b0065  mov     [rsp+120h+var_100], r12b
0x1809b006a  mov     ebx, 144h
0x1809b006f  mov     r13d, [rbx+rsi]
0x1809b0073  mov     byte ptr [r14+rsi], 1
0x1809b0078  xor     edi, edi
0x1809b007a  mov     [rbx+rsi], edi
0x1809b007d  test    r15, r15
0x1809b0080  jz      loc_1809B03E5
0x1809b0086  mov     [r15], rdi
0x1809b0089  mov     [pCount], edi
0x1809b008b  lea     rax, ??_7?$Collection@VDebugEnumInfo2@DebugTool@@@@6B@; const Collection<DebugTool::DebugEnumInfo2>::`vftable'
0x1809b0092  mov     [rbp+57h+enums.__vftable], rax
0x1809b0096  lea     this, [rbp+57h+enums.m_vector]; this
0x1809b009a  call    ??$?0AEBV?$allocator@U?$pair@QEAVCDependencyObject@@UDeferredInfo@CDeferredMapping@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVCDependencyObject@@UDeferredInfo@CDeferredMapping@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@QEAVCDependencyObject@@UDeferredInfo@CDeferredMapping@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>>>>>>(std::allocator<std::pair<CDependencyObject * const,CDeferredMapping::DeferredInfo>> const &)
0x1809b009f  lea     rax, std___Func_impl_no_alloc__lambda_37e17ed62652cb07abceba93af3e1421__long____vftable_
0x1809b00a6  mov     qword ptr [rbp+57h+function._Mystorage], rax
0x1809b00aa  lea     rax, [ppEnums-8]
0x1809b00ae  mov     qword ptr [rbp+57h+function._Mystorage+8], rax
0x1809b00b2  lea     rax, [rbp+57h+enums]
0x1809b00b6  mov     qword ptr [rbp+57h+function._Mystorage+10h], rax
0x1809b00ba  lea     rax, [rbp+57h+function]
0x1809b00be  mov     qword ptr [rbp+57h+function._Mystorage+38h], rax
0x1809b00c2  lea     pCount, [rbp+57h+function]; function
0x1809b00c6  mov     this, [ppEnums+90h]; pDispatcher
0x1809b00cd  call    ?RunOnUIThread@XamlDiagnosticsHelpers@@SAJPEAUICoreDispatcher@Core@UI@Windows@@AEBV?$function@$$A6AJXZ@std@@@Z; XamlDiagnosticsHelpers::RunOnUIThread(Windows::UI::Core::ICoreDispatcher *,std::function<long (void)> const &)
0x1809b00d2  mov     ebx, eax
0x1809b00d4  lea     this, [rbp+57h+function]; this
0x1809b00d8  call    ?_Tidy@?$_Func_class@JPEAVCDependencyObject@@W4MajorPlacementMode@CFlyoutBase@@@std@@IEAAXXZ; std::_Func_class<long,CDependencyObject *,CFlyoutBase::MajorPlacementMode>::_Tidy(void)
0x1809b00dd  test    ebx, ebx
0x1809b00df  js      loc_1809B038C
0x1809b00e5  lea     this, [rsp+120h+result]; this
0x1809b00ea  call    ??0?$TrackerPtrVector@U?$IEventHandler@PEAVScrollViewerViewChangingEventArgs@Controls@Xaml@UI@Windows@@@Foundation@Windows@@@DirectUI@@QEAA@XZ; DirectUI::TrackerPtrVector<Windows::Foundation::IEventHandler<Windows::UI::Xaml::Controls::ScrollViewerViewChangingEventArgs *>>::TrackerPtrVector<Windows::Foundation::IEventHandler<Windows::UI::Xaml::Controls::ScrollViewerViewChangingEventArgs *>>(void)
0x1809b00ef  mov     r14, [rbp+57h+enums.m_vector._Mypair._Myval2._Myfirst]
0x1809b00f3  mov     rdi, [rbp+57h+enums.m_vector._Mypair._Myval2._Mylast]
0x1809b00f7  mov     [rbp+57h+var_B0], rdi
0x1809b00fb  cmp     r14, rdi
0x1809b00fe  jz      loc_1809B0279
0x1809b0104  xor     edx, edx; length
0x1809b0106  mov     this, [r14+8]; string
0x1809b010a  call    cs:__imp_WindowsGetStringRawBuffer
0x1809b0110  mov     pCount, rax; source
0x1809b0113  lea     this, [rsp+120h+name]; result
0x1809b0118  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1809b011d  mov     ppEnums, [r14+18h]
0x1809b0121  sub     ppEnums, [r14+10h]
0x1809b0125  sar     ppEnums, 4; cElements
0x1809b0129  mov     ecx, 16h; vt
0x1809b012e  xor     edx, edx; lLbound
0x1809b0130  call    cs:__imp_SafeArrayCreateVector
0x1809b0136  mov     rbx, rax
0x1809b0139  mov     this, rax; psa
0x1809b013c  call    cs:__imp_SafeArrayLock
0x1809b0142  mov     ppEnums, [r14+18h]
0x1809b0146  sub     ppEnums, [r14+10h]
0x1809b014a  sar     ppEnums, 4; cElements
0x1809b014e  mov     ecx, 8; vt
0x1809b0153  xor     edx, edx; lLbound
0x1809b0155  call    cs:__imp_SafeArrayCreateVector
0x1809b015b  mov     r15, rax
0x1809b015e  mov     this, rax; psa
0x1809b0161  call    cs:__imp_SafeArrayLock
0x1809b0167  mov     this, [rsp+120h+name.m_ptr]
0x1809b016c  mov     [rsp+120h+name.m_ptr], 0
0x1809b0175  mov     [rbp+57h+enumType.Name], this
0x1809b0179  mov     pCount, [r14+10h]
0x1809b017d  mov     this, [r14+18h]
0x1809b0181  sub     this, pCount
0x1809b0184  sar     this, 4
0x1809b0188  test    this, this
0x1809b018b  jz      short loc_1809B01EF
0x1809b018d  xor     r12d, r12d
0x1809b0190  mov     rdi, r12
0x1809b0193  add     rdi, rdi
0x1809b0196  mov     pCount, [pCount+rdi*8+8]; source
0x1809b019b  lea     this, [rsp+120h+valueString]; result
0x1809b01a0  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1809b01a5  mov     rax, [r14+10h]
0x1809b01a9  mov     this, [rbx+10h]
0x1809b01ad  mov     eax, [rax+rdi*8]
0x1809b01b0  mov     [this+r12*4], eax
0x1809b01b4  mov     this, [rsp+120h+valueString.m_ptr]
0x1809b01b9  mov     [rsp+120h+valueString.m_ptr], 0
0x1809b01c2  mov     rax, [r15+10h]
0x1809b01c6  mov     [rax+r12*8], this
0x1809b01ca  lea     this, [rsp+120h+valueString]; this
0x1809b01cf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1809b01d4  inc     r12
0x1809b01d7  mov     pCount, [r14+10h]
0x1809b01db  mov     rax, [r14+18h]
0x1809b01df  sub     rax, pCount
0x1809b01e2  sar     rax, 4
0x1809b01e6  cmp     r12, rax
0x1809b01e9  jb      short loc_1809B0190
0x1809b01eb  mov     rdi, [rbp+57h+var_B0]
0x1809b01ef  mov     this, rbx; psa
0x1809b01f2  call    cs:__imp_SafeArrayUnlock
0x1809b01f8  mov     [rbp+57h+enumType.ValueInts], rbx
0x1809b01fc  mov     this, r15; psa
0x1809b01ff  call    cs:__imp_SafeArrayUnlock
0x1809b0205  mov     [rbp+57h+enumType.ValueStrings], r15
0x1809b0209  mov     pCount, [rsp+120h+result.m_vector._Mypair._Myval2._Mylast]; _Whereptr
0x1809b020e  cmp     pCount, [rsp+120h+result.m_vector._Mypair._Myval2._Myend]
0x1809b0213  jz      short loc_1809B0228
0x1809b0215  movups  xmm0, xmmword ptr [rbp+57h+enumType.Name]
0x1809b0219  movups  xmmword ptr [pCount], xmm0
0x1809b021c  mov     [pCount+10h], r15
0x1809b0220  add     [rsp+120h+result.m_vector._Mypair._Myval2._Mylast], 18h
0x1809b0226  jmp     short loc_1809B0237
0x1809b0228  lea     ppEnums, [rbp+57h+enumType]; <_Val_0>
0x1809b022c  lea     this, [rsp+120h+result]; this
0x1809b0231  call    ??$_Emplace_reallocate@AEBVHighlightRegion@@@?$vector@VHighlightRegion@@V?$allocator@VHighlightRegion@@@std@@@std@@AEAAPEAVHighlightRegion@@QEAV2@AEBV2@@Z; std::vector<HighlightRegion>::_Emplace_reallocate<HighlightRegion const &>(HighlightRegion * const,HighlightRegion const &)
0x1809b0236  nop
0x1809b0237  xor     ecx, ecx; psa
0x1809b0239  call    cs:__imp_SafeArrayUnlock
0x1809b023f  xor     ecx, ecx; psa
0x1809b0241  call    cs:__imp_SafeArrayDestroy
0x1809b0247  nop
0x1809b0248  xor     ecx, ecx; psa
0x1809b024a  call    cs:__imp_SafeArrayUnlock
0x1809b0250  xor     ecx, ecx; psa
0x1809b0252  call    cs:__imp_SafeArrayDestroy
0x1809b0258  nop
0x1809b0259  lea     this, [rsp+120h+name]; this
0x1809b025e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1809b0263  add     r14, 28h ; '('
0x1809b0267  cmp     r14, rdi
0x1809b026a  jnz     loc_1809B0104
0x1809b0270  mov     r12b, [rsp+120h+var_100]
0x1809b0275  mov     r15, [rbp+57h+var_A8]
0x1809b0279  mov     this, [rsp+120h+result.m_vector._Mypair._Myval2._Mylast]
0x1809b027e  sub     this, [rsp+120h+result.m_vector._Mypair._Myval2._Myfirst]
0x1809b0283  mov     r14, 2AAAAAAAAAAAAAABh
0x1809b028d  mov     rax, r14
0x1809b0290  imul    this
0x1809b0293  sar     pCount, 2
0x1809b0297  mov     rax, pCount
0x1809b029a  shr     rax, 3Fh
0x1809b029e  add     pCount, rax
0x1809b02a1  mov     rax, [rbp+57h+var_A0]
0x1809b02a5  mov     [rax], edx
0x1809b02a7  lea     rbx, [pCount+pCount*2]
0x1809b02ab  shl     rbx, 3
0x1809b02af  mov     this, rbx; cb
0x1809b02b2  call    cs:__imp_CoTaskMemAlloc
0x1809b02b8  mov     rdi, rax
0x1809b02bb  mov     ppEnums, rbx; Size
0x1809b02be  xor     edx, edx; Val
0x1809b02c0  mov     this, rax; void *
0x1809b02c3  call    memset_0
0x1809b02c8  mov     pCount, [rsp+120h+result.m_vector._Mypair._Myval2._Myfirst]; Src
0x1809b02cd  mov     ppEnums, [rsp+120h+result.m_vector._Mypair._Myval2._Mylast]
0x1809b02d2  sub     ppEnums, pCount; Size
0x1809b02d5  mov     this, rdi; void *
0x1809b02d8  call    memmove_0
0x1809b02dd  mov     this, [rsp+120h+result.m_vector._Mypair._Myval2._Myfirst]; _Ptr
0x1809b02e2  cmp     this, [rsp+120h+result.m_vector._Mypair._Myval2._Mylast]
0x1809b02e7  jz      short loc_1809B02EE
0x1809b02e9  mov     [rsp+120h+result.m_vector._Mypair._Myval2._Mylast], this
0x1809b02ee  mov     [r15], rdi
0x1809b02f1  test    this, this
0x1809b02f4  jz      short loc_1809B0331
0x1809b02f6  mov     pCount, [rsp+120h+result.m_vector._Mypair._Myval2._Myend]
0x1809b02fb  sub     pCount, this
0x1809b02fe  mov     rax, r14
0x1809b0301  imul    pCount
0x1809b0304  sar     pCount, 2
0x1809b0308  mov     rax, pCount
0x1809b030b  shr     rax, 3Fh
0x1809b030f  add     pCount, rax
0x1809b0312  lea     pCount, [pCount+pCount*2]
0x1809b0316  shl     pCount, 3; _Bytes
0x1809b031a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1809b031f  xorps   xmm0, xmm0
0x1809b0322  movdqu  xmmword ptr [rsp+120h+result.m_vector._Mypair._Myval2._Myfirst], xmm0
0x1809b0328  mov     [rsp+120h+result.m_vector._Mypair._Myval2._Myend], 0
0x1809b0331  mov     this, [rbp+57h+enums.m_vector._Mypair._Myval2._Myfirst]; _First
0x1809b0335  test    this, this
0x1809b0338  jz      short loc_1809B0376
0x1809b033a  mov     pCount, [rbp+57h+enums.m_vector._Mypair._Myval2._Mylast]; _Last
0x1809b033e  call    ??$_Destroy_range@V?$allocator@VDebugEnumInfo2@DebugTool@@@std@@@std@@YAXPEAVDebugEnumInfo2@DebugTool@@QEAV12@AEAV?$allocator@VDebugEnumInfo2@DebugTool@@@0@@Z; std::_Destroy_range<std::allocator<DebugTool::DebugEnumInfo2>>(DebugTool::DebugEnumInfo2 *,DebugTool::DebugEnumInfo2 * const,std::allocator<DebugTool::DebugEnumInfo2> &)
0x1809b0343  mov     this, [rbp+57h+enums.m_vector._Mypair._Myval2._Myfirst]; _Ptr
0x1809b0347  mov     pCount, [rbp+57h+enums.m_vector._Mypair._Myval2._Myend]
0x1809b034b  sub     pCount, this
0x1809b034e  mov     rax, 6666666666666667h
0x1809b0358  imul    pCount
0x1809b035b  sar     pCount, 4
0x1809b035f  mov     rax, pCount
0x1809b0362  shr     rax, 3Fh
0x1809b0366  add     pCount, rax
0x1809b0369  lea     pCount, [pCount+pCount*4]
0x1809b036d  shl     pCount, 3; _Bytes
0x1809b0371  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1809b0376  mov     eax, 140h
0x1809b037b  mov     [rax+rsi], r12b
0x1809b037f  mov     eax, 144h
0x1809b0384  mov     [rax+rsi], r13d
0x1809b0388  xor     eax, eax
0x1809b038a  jmp     short loc_1809B03F7
0x1809b038c  mov     ecx, ebx; failedFrameHR
0x1809b038e  call    OnFailure_2990_
0x1809b0393  mov     this, [rbp+57h+enums.m_vector._Mypair._Myval2._Myfirst]; _First
0x1809b0397  test    this, this
0x1809b039a  jz      short loc_1809B03D8
0x1809b039c  mov     pCount, [rbp+57h+enums.m_vector._Mypair._Myval2._Mylast]; _Last
0x1809b03a0  call    ??$_Destroy_range@V?$allocator@VDebugEnumInfo2@DebugTool@@@std@@@std@@YAXPEAVDebugEnumInfo2@DebugTool@@QEAV12@AEAV?$allocator@VDebugEnumInfo2@DebugTool@@@0@@Z; std::_Destroy_range<std::allocator<DebugTool::DebugEnumInfo2>>(DebugTool::DebugEnumInfo2 *,DebugTool::DebugEnumInfo2 * const,std::allocator<DebugTool::DebugEnumInfo2> &)
0x1809b03a5  mov     this, [rbp+57h+enums.m_vector._Mypair._Myval2._Myfirst]; _Ptr
0x1809b03a9  mov     pCount, [rbp+57h+enums.m_vector._Mypair._Myval2._Myend]
0x1809b03ad  sub     pCount, this
0x1809b03b0  mov     rax, 6666666666666667h
0x1809b03ba  imul    pCount
0x1809b03bd  sar     pCount, 4
0x1809b03c1  mov     rax, pCount
0x1809b03c4  shr     rax, 3Fh
0x1809b03c8  add     pCount, rax
0x1809b03cb  lea     pCount, [pCount+pCount*4]
0x1809b03cf  shl     pCount, 3; _Bytes
0x1809b03d3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1809b03d8  mov     eax, 144h
0x1809b03dd  mov     [rax+rsi], r13d
0x1809b03e1  mov     eax, ebx
0x1809b03e3  jmp     short loc_1809B03F3
0x1809b03e5  call    OnNewFailure_1172_
0x1809b03ea  mov     [rbx+rsi], r13d
0x1809b03ee  mov     eax, 80004003h
0x1809b03f3  mov     [r14+rsi], r12b
0x1809b03f7  mov     this, [rbp+57h+var_40]
0x1809b03fb  xor     this, rsp; StackCookie
0x1809b03fe  call    __security_check_cookie
0x1809b0403  mov     rbx, [rsp+120h+arg_18]
0x1809b040b  add     rsp, 0F0h
0x1809b0412  pop     r15
0x1809b0414  pop     r14
0x1809b0416  pop     r13
0x1809b0418  pop     r12
0x1809b041a  pop     rdi
0x1809b041b  pop     rsi
0x1809b041c  pop     rbp
0x1809b041d  retn
```
