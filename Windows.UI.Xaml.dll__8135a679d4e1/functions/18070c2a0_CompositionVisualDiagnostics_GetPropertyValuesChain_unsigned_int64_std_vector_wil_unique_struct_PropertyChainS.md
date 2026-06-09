# CompositionVisualDiagnostics::GetPropertyValuesChain(unsigned __int64,std::vector<wil::unique_struct<PropertyChainSource,void (*)(PropertyChainSource *),&CoDeallocPropertyChainSource(PropertyChainSource *),std::nullptr_t,0>,std::allocator<wil::unique_struct<PropertyChainSource,void (*)(PropertyChainSource *),&CoDeallocPropertyChainSource(PropertyChainSource *),std::nullptr_t,0>>> &,std::vector<wil::unique_struct<PropertyChainValue,void (*)(PropertyChainValue *),&CoDeallocPropertyChainValue(PropertyChainValue *),std::nullptr_t,0>,std::allocator<wil::unique_struct<PropertyChainValue,void (*)(PropertyChainValue *),&CoDeallocPropertyChainValue(PropertyChainValue *),std::nullptr_t,0>>> &)

- ea: `0x18070c2a0`
- end: `0x18070c4c7`
- name: `?GetPropertyValuesChain@CompositionVisualDiagnostics@@QEAAJ_KAEAV?$vector@V?$unique_struct@UPropertyChainSource@@P6AXPEAU1@@Z$1?CoDeallocPropertyChainSource@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UPropertyChainSource@@P6AXPEAU1@@Z$1?CoDeallocPropertyChainSource@@YAX0@Z$$T$0A@@wil@@@std@@@std@@AEAV?$vector@V?$unique_struct@UPropertyChainValue@@P6AXPEAU1@@Z$1?CoDeallocPropertyChainValue@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UPropertyChainValue@@P6AXPEAU1@@Z$1?CoDeallocPropertyChainValue@@YAX0@Z$$T$0A@@wil@@@std@@@3@@Z`
- size: `551`
- prototype: `HRESULT __fastcall(CompositionVisualDiagnostics *this, unsigned __int64 targetHandle, std::vector<wil::unique_struct<PropertyChainSource,void (__cdecl*)(PropertyChainSource *),&CoDeallocPropertyChainSource,std::nullptr_t,0>> *propertySources, std::vector<wil::unique_struct<PropertyChainValue,void (__cdecl*)(PropertyChainValue *),&CoDeallocPropertyChainValue,std::nullptr_t,0>> *propertyValues)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180691890`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x1804bd840`
- `0x18051dd30`
- `0x18070c2a0`
- `0x18070c4d0`
- `0x18076e110`
- `0x18076f0a4`
- `0x1809afc8c`
- `0x1809b21f0`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18070c306`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18070c306`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18070c326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18070c326`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18070c3cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18070c462`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18070c482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18070c3cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18070c462`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18070c482`
- `OLEAUT32!__imp_SysAllocString` at `0x18070c347`
- `OLEAUT32!__imp_SysAllocString` at `0x18070c358`
- `OLEAUT32!__imp_SysAllocString` at `0x18070c347`
- `OLEAUT32!__imp_SysAllocString` at `0x18070c358`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CompositionVisualDiagnostics::GetPropertyValuesChain(
        CompositionVisualDiagnostics *this,
        unsigned __int64 targetHandle,
        std::vector<wil::unique_struct<PropertyChainSource,void (__cdecl*)(PropertyChainSource *),&CoDeallocPropertyChainSource,std::nullptr_t,0>> *propertySources,
        std::_Func_base<bool,CompositionDiagnostics::CompositionPropertyInfo const &> *propertyValues)
{
  HRESULT ElementOrProperty; // eax
  unsigned int v9; // ebx
  HRESULT v10; // eax
  _GUID *v11; // rax
  unsigned int i; // ebx
  std::function<bool __cdecl(CompositionDiagnostics::CompositionPropertyInfo const &)> *p_callback; // rdx
  unsigned int iidsCount; // [rsp+20h] [rbp-99h] BYREF
  _GUID *iids; // [rsp+28h] [rbp-91h] BYREF
  HRESULT readAllPropertyValuesHR; // [rsp+30h] [rbp-89h] BYREF
  Microsoft::WRL::ComPtr<IInspectable> target; // [rsp+38h] [rbp-81h] BYREF
  wil::unique_struct<PropertyChainSource,void (__cdecl*)(PropertyChainSource *),&CoDeallocPropertyChainSource,std::nullptr_t,0> source; // [rsp+40h] [rbp-79h] BYREF
  wil::details::ScopeExitFn<<lambda_509e4eb7585beccaabad0bdb904998ff> > fnCleanup; // [rsp+80h] [rbp-39h]
  std::function<bool __cdecl(CompositionDiagnostics::CompositionPropertyInfo const &)> callback; // [rsp+90h] [rbp-29h] BYREF

  target.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&target);
  ElementOrProperty = XamlDiagnosticsShared::HandleStore::FindElementOrProperty(
                        &this->m_handles,
                        targetHandle,
                        &target.ptr_);
  v9 = ElementOrProperty;
  if ( ElementOrProperty < 0 )
  {
    OnFailure_2990_(ElementOrProperty);
  }
  else
  {
    EnterCriticalSection(&this->m_handles.m_handleMapLock.cs_);
    iids = (_GUID *)&this->m_handles.m_handleMapLock;
    HandleMap::ReleaseProperties(&this->m_handles.m_handleMap, targetHandle);
    if ( this != (CompositionVisualDiagnostics *)-88LL )
      LeaveCriticalSection(&this->m_handles.m_handleMapLock.cs_);
    memset_0(&source, 0, sizeof(source));
    source.Handle = targetHandle;
    source.TargetType = SysAllocString(&pressedKeys);
    source.Name = SysAllocString(&pressedKeys);
    source.Source = BaseValueSourceLocal;
    std::vector<wil::unique_struct<PropertyChainSource,void (*)(PropertyChainSource *),&void CoDeallocPropertyChainSource(PropertyChainSource *),std::nullptr_t,0>>::push_back(
      propertySources,
      &source);
    readAllPropertyValuesHR = 0;
    iids = 0;
    fnCleanup.m_exitFunctor.iids = &iids;
    fnCleanup.m_shouldRun = 1;
    iidsCount = 0;
    v10 = target.ptr_->GetIids(target.ptr_, &iidsCount, &iids);
    v9 = v10;
    if ( v10 < 0 )
    {
      OnFailure_2990_(v10);
      CoTaskMemFree(iids);
      CoDeallocPropertyChainSource(&source);
    }
    else
    {
      v11 = iids;
      if ( iids )
      {
        for ( i = 0; i < iidsCount; v11 = iids )
        {
          callback._Mystorage._Ptrs[0] = (std::_Func_base<bool,CompositionDiagnostics::CompositionPropertyInfo const &> *)std::_Func_impl_no_alloc__lambda_16d8b58fe43643d85b2e94da49607522__bool_CompositionDiagnostics::CompositionPropertyInfo_const___::_vftable_;
          callback._Mystorage._Ptrs[1] = (std::_Func_base<bool,CompositionDiagnostics::CompositionPropertyInfo const &> *)this;
          callback._Mystorage._Ptrs[2] = (std::_Func_base<bool,CompositionDiagnostics::CompositionPropertyInfo const &> *)&target;
          callback._Mystorage._Ptrs[3] = (std::_Func_base<bool,CompositionDiagnostics::CompositionPropertyInfo const &> *)&readAllPropertyValuesHR;
          callback._Mystorage._Ptrs[4] = propertyValues;
          callback._Mystorage._Ptrs[7] = (std::_Func_base<bool,CompositionDiagnostics::CompositionPropertyInfo const &> *)&callback;
          CompositionDiagnostics::CompositionPropertyInfo::For_Each_Property(&v11[i], &callback);
          if ( callback._Mystorage._Ptrs[7] )
          {
            p_callback = &callback;
            LOBYTE(p_callback) = callback._Mystorage._Ptrs[7] != (std::_Func_base<bool,CompositionDiagnostics::CompositionPropertyInfo const &> *)&callback;
            callback._Mystorage._Ptrs[7]->_Delete_this(callback._Mystorage._Ptrs[7], (bool)p_callback);
          }
          ++i;
        }
        v9 = readAllPropertyValuesHR;
        CoTaskMemFree(v11);
        CoDeallocPropertyChainSource(&source);
      }
      else
      {
        CoTaskMemFree(0);
        CoDeallocPropertyChainSource(&source);
        v9 = -2147467259;
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&target);
  return v9;
}

```

## disassembly

```asm
0x18070c2a0  push    rbp
0x18070c2a2  push    rbx
0x18070c2a3  push    rsi
0x18070c2a4  push    rdi
0x18070c2a5  push    r12
0x18070c2a7  push    r14
0x18070c2a9  push    r15
0x18070c2ab  lea     rbp, [rsp-27h]
0x18070c2b0  sub     rsp, 0E0h
0x18070c2b7  mov     rax, cs:__security_cookie
0x18070c2be  xor     rax, rsp
0x18070c2c1  mov     [rbp+57h+var_40], rax
0x18070c2c5  mov     r15, propertyValues
0x18070c2c8  mov     r12, propertySources
0x18070c2cb  mov     rsi, targetHandle
0x18070c2ce  mov     r14, this
0x18070c2d1  mov     [rsp+110h+target.ptr_], 0
0x18070c2da  lea     this, [rsp+110h+target]; this
0x18070c2df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18070c2e4  lea     propertySources, [rsp+110h+target]; elementOrProperty
0x18070c2e9  mov     targetHandle, rsi; elementOrPropertyHandle
0x18070c2ec  lea     this, [r14+18h]; this
0x18070c2f0  call    ?FindElementOrProperty@HandleStore@XamlDiagnosticsShared@@QEAAJ_KPEAPEAUIInspectable@@@Z; XamlDiagnosticsShared::HandleStore::FindElementOrProperty(unsigned __int64,IInspectable * *)
0x18070c2f5  mov     ebx, eax
0x18070c2f7  test    eax, eax
0x18070c2f9  js      loc_18070C495
0x18070c2ff  lea     rbx, [r14+58h]
0x18070c303  mov     this, rbx; lpCriticalSection
0x18070c306  call    cs:__imp_EnterCriticalSection
0x18070c30c  mov     [rsp+110h+iids], rbx
0x18070c311  mov     targetHandle, rsi; ownerHandle
0x18070c314  lea     this, [r14+18h]; this
0x18070c318  call    ?ReleaseProperties@HandleMap@@QEAAX_K@Z; HandleMap::ReleaseProperties(unsigned __int64)
0x18070c31d  nop
0x18070c31e  test    rbx, rbx
0x18070c321  jz      short loc_18070C32C
0x18070c323  mov     this, rbx; lpCriticalSection
0x18070c326  call    cs:__imp_LeaveCriticalSection
0x18070c32c  xor     edx, edx; Val
0x18070c32e  lea     r8d, [targetHandle+40h]; Size
0x18070c332  lea     this, [rbp+57h+source]; void *
0x18070c336  call    memset_0
0x18070c33b  nop
0x18070c33c  mov     [rbp+57h+source.Handle], rsi
0x18070c340  lea     this, pressedKeys; psz
0x18070c347  call    cs:__imp_SysAllocString
0x18070c34d  mov     [rbp+57h+source.TargetType], rax
0x18070c351  lea     this, pressedKeys; psz
0x18070c358  call    cs:__imp_SysAllocString
0x18070c35e  mov     [rbp+57h+source.Name], rax
0x18070c362  mov     [rbp+57h+source.Source], 4
0x18070c369  lea     targetHandle, [rbp+57h+source]; _Val
0x18070c36d  mov     this, r12; this
0x18070c370  call    ?push_back@?$vector@V?$unique_struct@UPropertyChainSource@@P6AXPEAU1@@Z$1?CoDeallocPropertyChainSource@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@UPropertyChainSource@@P6AXPEAU1@@Z$1?CoDeallocPropertyChainSource@@YAX0@Z$$T$0A@@wil@@@std@@@std@@QEAAX$$QEAV?$unique_struct@UPropertyChainSource@@P6AXPEAU1@@Z$1?CoDeallocPropertyChainSource@@YAX0@Z$$T$0A@@wil@@@Z; std::vector<wil::unique_struct<PropertyChainSource,void (*)(PropertyChainSource *),&CoDeallocPropertyChainSource(PropertyChainSource *),std::nullptr_t,0>>::push_back(wil::unique_struct<PropertyChainSource,void (*)(PropertyChainSource *),&CoDeallocPropertyChainSource(PropertyChainSource *),std::nullptr_t,0> &&)
0x18070c375  mov     [rsp+110h+readAllPropertyValuesHR], 0
0x18070c37d  mov     [rsp+110h+iids], 0
0x18070c386  lea     rax, [rsp+110h+iids]
0x18070c38b  mov     [rbp+57h+fnCleanup.m_exitFunctor.iids], rax
0x18070c38f  mov     [rbp+57h+fnCleanup.m_shouldRun], 1
0x18070c393  mov     [rsp+110h+iidsCount], 0
0x18070c39b  mov     this, [rsp+110h+target.ptr_]
0x18070c3a0  mov     rax, [this]
0x18070c3a3  lea     propertySources, [rsp+110h+iids]
0x18070c3a8  lea     targetHandle, [rsp+110h+iidsCount]
0x18070c3ad  mov     rax, [rax+18h]
0x18070c3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18070c3b6  mov     ebx, eax
0x18070c3b8  test    eax, eax
0x18070c3ba  js      loc_18070C475
0x18070c3c0  mov     rax, [rsp+110h+iids]
0x18070c3c5  test    rax, rax
0x18070c3c8  jnz     short loc_18070C3E7
0x18070c3ca  xor     ecx, ecx; pv
0x18070c3cc  call    cs:__imp_CoTaskMemFree
0x18070c3d2  nop
0x18070c3d3  lea     this, [rbp+57h+source]; source
0x18070c3d7  call    ?CoDeallocPropertyChainSource@@YAXPEAUPropertyChainSource@@@Z; CoDeallocPropertyChainSource(PropertyChainSource *)
0x18070c3dc  nop
0x18070c3dd  mov     ebx, 80004005h
0x18070c3e2  jmp     loc_18070C49D
0x18070c3e7  xor     ebx, ebx
0x18070c3e9  cmp     [rsp+110h+iidsCount], ebx
0x18070c3ed  jbe     short loc_18070C45B
0x18070c3ef  lea     this, std___Func_impl_no_alloc__lambda_16d8b58fe43643d85b2e94da49607522__bool_CompositionDiagnostics__CompositionPropertyInfo_const______vftable_
0x18070c3f6  mov     qword ptr [rbp+57h+callback._Mystorage], this
0x18070c3fa  mov     qword ptr [rbp+57h+callback._Mystorage+8], r14
0x18070c3fe  lea     this, [rsp+110h+target]
0x18070c403  mov     qword ptr [rbp+57h+callback._Mystorage+10h], this
0x18070c407  lea     this, [rsp+110h+readAllPropertyValuesHR]
0x18070c40c  mov     qword ptr [rbp+57h+callback._Mystorage+18h], this
0x18070c410  mov     qword ptr [rbp+57h+callback._Mystorage+20h], r15
0x18070c414  lea     this, [rbp+57h+callback]
0x18070c418  mov     qword ptr [rbp+57h+callback._Mystorage+38h], this
0x18070c41c  mov     ecx, ebx
0x18070c41e  shl     this, 4
0x18070c422  add     this, rax; iid
0x18070c425  lea     targetHandle, [rbp+57h+callback]; callback
0x18070c429  call    ?For_Each_Property@CompositionPropertyInfo@CompositionDiagnostics@@SAXAEBU_GUID@@AEBV?$function@$$A6A_NAEBVCompositionPropertyInfo@CompositionDiagnostics@@@Z@std@@@Z; CompositionDiagnostics::CompositionPropertyInfo::For_Each_Property(_GUID const &,std::function<bool (CompositionDiagnostics::CompositionPropertyInfo const &)> const &)
0x18070c42e  nop
0x18070c42f  mov     this, qword ptr [rbp+57h+callback._Mystorage+38h]
0x18070c433  test    this, this
0x18070c436  jz      short loc_18070C44E
0x18070c438  mov     rax, [this]
0x18070c43b  lea     targetHandle, [rbp+57h+callback]
0x18070c43f  cmp     this, targetHandle
0x18070c442  setnz   dl
0x18070c445  mov     rax, [rax+20h]
0x18070c449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18070c44e  inc     ebx
0x18070c450  mov     rax, [rsp+110h+iids]
0x18070c455  cmp     ebx, [rsp+110h+iidsCount]
0x18070c459  jb      short loc_18070C3EF
0x18070c45b  mov     ebx, [rsp+110h+readAllPropertyValuesHR]
0x18070c45f  mov     this, rax; pv
0x18070c462  call    cs:__imp_CoTaskMemFree
0x18070c468  nop
0x18070c469  lea     this, [rbp+57h+source]; source
0x18070c46d  call    ?CoDeallocPropertyChainSource@@YAXPEAUPropertyChainSource@@@Z; CoDeallocPropertyChainSource(PropertyChainSource *)
0x18070c472  nop
0x18070c473  jmp     short loc_18070C49D
0x18070c475  mov     ecx, eax; failedFrameHR
0x18070c477  call    OnFailure_2990_
0x18070c47c  nop
0x18070c47d  mov     this, [rsp+110h+iids]; pv
0x18070c482  call    cs:__imp_CoTaskMemFree
0x18070c488  nop
0x18070c489  lea     this, [rbp+57h+source]; source
0x18070c48d  call    ?CoDeallocPropertyChainSource@@YAXPEAUPropertyChainSource@@@Z; CoDeallocPropertyChainSource(PropertyChainSource *)
0x18070c492  nop
0x18070c493  jmp     short loc_18070C49D
0x18070c495  mov     ecx, eax; failedFrameHR
0x18070c497  call    OnFailure_2990_
0x18070c49c  nop
0x18070c49d  lea     this, [rsp+110h+target]; this
0x18070c4a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18070c4a7  mov     eax, ebx
0x18070c4a9  mov     this, [rbp+57h+var_40]
0x18070c4ad  xor     this, rsp; StackCookie
0x18070c4b0  call    __security_check_cookie
0x18070c4b5  add     rsp, 0E0h
0x18070c4bc  pop     r15
0x18070c4be  pop     r14
0x18070c4c0  pop     r12
0x18070c4c2  pop     rdi
0x18070c4c3  pop     rsi
0x18070c4c4  pop     rbx
0x18070c4c5  pop     rbp
0x18070c4c6  retn
```
