# HWCompTreeNodeWinRT::StartFacadeGlueExpression(Windows::UI::Composition::IVisual *,ushort const *,Windows::UI::Composition::IExpressionAnimation *)

- ea: `0x18039072c`
- end: `0x1803909f0`
- name: `?StartFacadeGlueExpression@HWCompTreeNodeWinRT@@IEAAXPEAUIVisual@Composition@UI@Windows@@PEBGPEAUIExpressionAnimation@345@@Z`
- size: `708`
- prototype: `void __fastcall(HWCompTreeNodeWinRT *this, Windows::UI::Composition::IVisual *visual, const wchar_t *propertyName, Windows::UI::Composition::IExpressionAnimation *expressionAnimation)`
- caller_count: `6`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180190b60`
- `0x18044bba8`
- `0x1804d95b0`
- `0x1804d9724`
- `0x1804da1d0`
- `0x180509aec`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x18019385c`
- `0x18039072c`
- `0x180390b8c`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039093f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180390955`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180390968`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803909b2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18039093f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180390955`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180390968`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803909b2`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039099b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803909e5`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18039099b`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1803909e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803907f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803908b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803907f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803908b6`

## pseudocode

```c
void __fastcall HWCompTreeNodeWinRT::StartFacadeGlueExpression(
        HWCompTreeNodeWinRT *this,
        Windows::UI::Composition::IVisual *visual,
        const wchar_t *propertyName,
        Windows::UI::Composition::IExpressionAnimation *expressionAnimation)
{
  CCoreServices *m_coreServices; // rdi
  Windows::UI::Composition::IExpressionAnimation_vtbl *v9; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  Windows::UI::Composition::ICompositionAnimation *ptr; // r13
  CUIElement *m_pUIElementNoRef; // r8
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> *BackingCompositionObject; // rax
  const wchar_t *v14; // rsi
  Windows::UI::Composition::ICompositionObject *v15; // r14
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rbx
  unsigned int v18; // eax
  UINT32 v19; // edx
  signed int v20; // eax
  HRESULT v21; // eax
  Windows::UI::Composition::ICompositionObject *v22; // rdx
  HRESULT v23; // ebx
  Windows::UI::Composition::IVisual_vtbl *v24; // rax
  HRESULT (__fastcall *v25)(IUnknown *, const _GUID *, void **); // rbx
  Windows::UI::Composition::ICompositionObject *v26; // rbx
  Windows::UI::Composition::ICompositionObject_vtbl *v27; // r14
  Windows::UI::Composition::ICompositionAnimation *v28; // rsi
  unsigned int v29; // eax
  UINT32 v30; // edx
  signed int v31; // eax
  HRESULT v32; // eax
  HRESULT v33; // ebx
  Windows::UI::Composition::ICompositionObject *v34; // rcx
  Windows::UI::Composition::ICompositionAnimation *v35; // rcx
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> cStowedExceptions; // [rsp+20h] [rbp-58h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+28h] [rbp-50h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> ca; // [rsp+30h] [rbp-48h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> visualCO; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  HSTRING string; // [rsp+58h] [rbp-20h] BYREF

  m_coreServices = this->m_sharedState.m_ptr->m_value.m_coreServices;
  v9 = expressionAnimation->__vftable;
  ca.ptr_ = 0;
  QueryInterface = v9->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&ca);
  QueryInterface(expressionAnimation, &GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca, (void **)&ca.ptr_);
  ptr = ca.ptr_;
  m_pUIElementNoRef = this->m_pUIElementNoRef;
  ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)ca.ptr_->__vftable;
  BackingCompositionObject = FacadeStorage::GetBackingCompositionObject(
                               &m_coreServices->m_facadeStorage,
                               &cStowedExceptions,
                               m_pUIElementNoRef);
  v14 = s_PS;
  v15 = BackingCompositionObject->ptr_;
  v16 = -1;
  string = 0;
  v17 = -1;
  do
    ++v17;
  while ( s_PS[v17] );
  if ( v17 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v17);
  v19 = v18 - 1;
  if ( (unsigned int)v17 < v18 )
    v19 = v17;
  v20 = WindowsCreateStringReference(v14, v19, &hstringHeader, &string);
  if ( v20 < 0 )
  {
    RaiseException(v20, 1u, 0, 0);
    __debugbreak();
  }
  v21 = ((__int64 (__fastcall *)(Windows::UI::Composition::ICompositionAnimation *, HSTRING, Windows::UI::Composition::ICompositionObject *))ppStowedExceptions[12])(
          ptr,
          string,
          v15);
  v22 = cStowedExceptions.ptr_;
  string = 0;
  v23 = v21;
  if ( cStowedExceptions.ptr_ )
  {
    cStowedExceptions.ptr_ = 0;
    v22->Release(v22);
  }
  if ( v23 < 0 )
  {
    OnFailure_2990_(v23);
    ppStowedExceptions = 0;
    LODWORD(cStowedExceptions.ptr_) = 0;
    TraceForFailFast(v23);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v23, (unsigned int)cStowedExceptions.ptr_, ppStowedExceptions);
  }
  v24 = visual->__vftable;
  visualCO.ptr_ = 0;
  v25 = v24->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&visualCO);
  v25(visual, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, (void **)&visualCO.ptr_);
  v26 = visualCO.ptr_;
  v27 = visualCO.ptr_->__vftable;
  string = 0;
  do
    ++v16;
  while ( propertyName[v16] );
  if ( v16 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v28 = ca.ptr_;
  v29 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v16);
  v30 = v29 - 1;
  if ( (unsigned int)v16 < v29 )
    v30 = v16;
  v31 = WindowsCreateStringReference(propertyName, v30, &hstringHeader, &string);
  if ( v31 < 0 )
  {
    RaiseException(v31, 1u, 0, 0);
    __debugbreak();
  }
  v32 = v27->StartAnimation(v26, string, v28);
  v33 = v32;
  if ( v32 < 0 )
  {
    OnFailure_2990_(v32);
    ppStowedExceptions = 0;
    LODWORD(cStowedExceptions.ptr_) = 0;
    TraceForFailFast(v33);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v33, (unsigned int)cStowedExceptions.ptr_, ppStowedExceptions);
  }
  v34 = visualCO.ptr_;
  if ( visualCO.ptr_ )
  {
    visualCO.ptr_ = 0;
    v34->Release(v34);
  }
  v35 = ca.ptr_;
  if ( ca.ptr_ )
  {
    ca.ptr_ = 0;
    v35->Release(v35);
  }
}

```

## disassembly

```asm
0x18039072c  push    rbp
0x18039072e  push    rbx
0x18039072f  push    rsi
0x180390730  push    rdi
0x180390731  push    r12
0x180390733  push    r13
0x180390735  push    r14
0x180390737  push    r15
0x180390739  mov     rbp, rsp
0x18039073c  sub     rsp, 78h
0x180390740  mov     rax, cs:__security_cookie
0x180390747  xor     rax, rsp
0x18039074a  mov     [rbp+var_18], rax
0x18039074e  mov     rax, [this+10h]
0x180390752  mov     r14, this
0x180390755  lea     this, [rbp+ca]; this
0x180390759  mov     rsi, expressionAnimation
0x18039075c  mov     r15, propertyName
0x18039075f  mov     r12, visual
0x180390762  mov     rdi, [rax]
0x180390765  mov     rax, [expressionAnimation]
0x180390768  mov     [rbp+ca.ptr_], 0
0x180390770  mov     rbx, [rax]
0x180390773  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180390778  lea     propertyName, [rbp+ca]
0x18039077c  mov     this, rsi
0x18039077f  lea     visual, _GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca
0x180390786  mov     rax, rbx
0x180390789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039078e  mov     r13, [rbp+ca.ptr_]
0x180390792  lea     visual, [rbp+cStowedExceptions]; result
0x180390796  mov     propertyName, [r14+98h]; object
0x18039079d  lea     this, [rdi+978h]; this
0x1803907a4  mov     rax, [r13+0]
0x1803907a8  mov     [rbp+ppStowedExceptions], rax
0x1803907ac  call    ?GetBackingCompositionObject@FacadeStorage@@QEBA?AV?$ComPtr@UICompositionObject@Composition@UI@Windows@@@WRL@Microsoft@@PEBVCDependencyObject@@@Z; FacadeStorage::GetBackingCompositionObject(CDependencyObject const *)
0x1803907b1  mov     rsi, cs:?s_PS@@3PEBGEB; ushort const * const s_PS
0x1803907b8  mov     r14, [rax]
0x1803907bb  xor     eax, eax
0x1803907bd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1803907c1  mov     [rbp+string], rax
0x1803907c5  mov     rbx, rdi
0x1803907c8  inc     rbx
0x1803907cb  cmp     [rsi+rbx*2], ax
0x1803907cf  jnz     short loc_1803907C8
0x1803907d1  mov     eax, 0FFFFFFFFh
0x1803907d6  cmp     rbx, rax
0x1803907d9  ja      loc_180390946
0x1803907df  mov     ecx, ebx; augend
0x1803907e1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1803907e6  cmp     ebx, eax
0x1803907e8  lea     expressionAnimation, [rbp+string]; string
0x1803907ec  lea     propertyName, [rbp+hstringHeader]; hstringHeader
0x1803907f0  mov     this, rsi; sourceString
0x1803907f3  lea     edx, [rax-1]
0x1803907f6  cmovb   edx, ebx; length
0x1803907f9  call    cs:__imp_WindowsCreateStringReference
0x1803907ff  test    eax, eax
0x180390801  js      loc_18039095C
0x180390807  mov     rax, [rbp+ppStowedExceptions]
0x18039080b  mov     propertyName, r14
0x18039080e  mov     visual, [rbp+string]
0x180390812  mov     this, r13
0x180390815  mov     rax, [rax+60h]
0x180390819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18039081e  mov     visual, [rbp+cStowedExceptions]
0x180390822  xor     r13d, r13d
0x180390825  mov     [rbp+string], r13
0x180390829  mov     ebx, eax
0x18039082b  test    visual, visual
0x18039082e  jz      short loc_180390843
0x180390830  mov     [rbp+cStowedExceptions], r13
0x180390834  mov     this, [visual]
0x180390837  mov     rax, [this+10h]
0x18039083b  mov     this, visual
0x18039083e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180390843  test    ebx, ebx
0x180390845  js      loc_18039096F
0x18039084b  mov     rax, [r12]
0x18039084f  lea     this, [rbp+visualCO]; this
0x180390853  mov     [rbp+visualCO.ptr_], r13
0x180390857  mov     rbx, [rax]
0x18039085a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18039085f  lea     propertyName, [rbp+visualCO]
0x180390863  mov     this, r12
0x180390866  lea     visual, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x18039086d  mov     rax, rbx
0x180390870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180390875  mov     rbx, [rbp+visualCO.ptr_]
0x180390879  mov     r14, [rbx]
0x18039087c  mov     [rbp+string], r13
0x180390880  inc     rdi
0x180390883  cmp     [r15+rdi*2], r13w
0x180390888  jnz     short loc_180390880
0x18039088a  mov     eax, 0FFFFFFFFh
0x18039088f  cmp     rdi, rax
0x180390892  ja      loc_180390930
0x180390898  mov     rsi, [rbp+ca.ptr_]
0x18039089c  mov     ecx, edi; augend
0x18039089e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1803908a3  cmp     edi, eax
0x1803908a5  lea     expressionAnimation, [rbp+string]; string
0x1803908a9  lea     propertyName, [rbp+hstringHeader]; hstringHeader
0x1803908ad  mov     this, r15; sourceString
0x1803908b0  lea     edx, [rax-1]
0x1803908b3  cmovb   edx, edi; length
0x1803908b6  call    cs:__imp_WindowsCreateStringReference
0x1803908bc  test    eax, eax
0x1803908be  js      loc_1803909A6
0x1803908c4  mov     visual, [rbp+string]
0x1803908c8  mov     propertyName, rsi
0x1803908cb  mov     rax, [r14+48h]
0x1803908cf  mov     this, rbx
0x1803908d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803908d7  mov     ebx, eax
0x1803908d9  test    eax, eax
0x1803908db  js      loc_1803909B9
0x1803908e1  mov     this, [rbp+visualCO.ptr_]
0x1803908e5  test    this, this
0x1803908e8  jz      short loc_1803908FA
0x1803908ea  mov     [rbp+visualCO.ptr_], r13
0x1803908ee  mov     rax, [this]
0x1803908f1  mov     rax, [rax+10h]
0x1803908f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803908fa  mov     this, [rbp+ca.ptr_]
0x1803908fe  test    this, this
0x180390901  jz      short loc_180390913
0x180390903  mov     [rbp+ca.ptr_], r13
0x180390907  mov     rax, [this]
0x18039090a  mov     rax, [rax+10h]
0x18039090e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180390913  mov     this, [rbp+var_18]
0x180390917  xor     this, rsp; StackCookie
0x18039091a  call    __security_check_cookie
0x18039091f  add     rsp, 78h
0x180390923  pop     r15
0x180390925  pop     r14
0x180390927  pop     r13
0x180390929  pop     r12
0x18039092b  pop     rdi
0x18039092c  pop     rsi
0x18039092d  pop     rbx
0x18039092e  pop     rbp
0x18039092f  retn
0x180390930  xor     r9d, r9d; lpArguments
0x180390933  xor     r8d, r8d; nNumberOfArguments
0x180390936  mov     ecx, 80070216h; dwExceptionCode
0x18039093b  lea     edx, [expressionAnimation+1]; dwExceptionFlags
0x18039093f  call    cs:__imp_RaiseException
0x180390945  int     3; Trap to Debugger
0x180390946  xor     r9d, r9d; lpArguments
0x180390949  xor     r8d, r8d; nNumberOfArguments
0x18039094c  mov     ecx, 80070216h; dwExceptionCode
0x180390951  lea     edx, [expressionAnimation+1]; dwExceptionFlags
0x180390955  call    cs:__imp_RaiseException
0x18039095b  int     3; Trap to Debugger
0x18039095c  xor     r9d, r9d; lpArguments
0x18039095f  xor     r8d, r8d; nNumberOfArguments
0x180390962  mov     ecx, eax; dwExceptionCode
0x180390964  lea     edx, [expressionAnimation+1]; dwExceptionFlags
0x180390968  call    cs:__imp_RaiseException
0x18039096e  int     3; Trap to Debugger
0x18039096f  mov     ecx, ebx; failedFrameHR
0x180390971  call    OnFailure_2990_
0x180390976  mov     ecx, ebx; errorCode
0x180390978  mov     [rbp+ppStowedExceptions], r13
0x18039097c  mov     dword ptr [rbp+cStowedExceptions], r13d
0x180390980  call    TraceForFailFast
0x180390985  lea     visual, [rbp+cStowedExceptions]; pcStowedExceptions
0x180390989  lea     this, [rbp+ppStowedExceptions]; pppStowedExceptions
0x18039098d  call    GetStowedExceptionsForFailFast
0x180390992  mov     propertyName, [rbp+ppStowedExceptions]
0x180390996  mov     ecx, ebx
0x180390998  mov     edx, dword ptr [rbp+cStowedExceptions]
0x18039099b  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1803909a1  jmp     loc_18039084B
0x1803909a6  xor     r9d, r9d; lpArguments
0x1803909a9  xor     r8d, r8d; nNumberOfArguments
0x1803909ac  mov     ecx, eax; dwExceptionCode
0x1803909ae  lea     edx, [expressionAnimation+1]; dwExceptionFlags
0x1803909b2  call    cs:__imp_RaiseException
0x1803909b8  int     3; Trap to Debugger
0x1803909b9  mov     ecx, ebx; failedFrameHR
0x1803909bb  call    OnFailure_2990_
0x1803909c0  mov     ecx, ebx; errorCode
0x1803909c2  mov     [rbp+ppStowedExceptions], r13
0x1803909c6  mov     dword ptr [rbp+cStowedExceptions], r13d
0x1803909ca  call    TraceForFailFast
0x1803909cf  lea     visual, [rbp+cStowedExceptions]; pcStowedExceptions
0x1803909d3  lea     this, [rbp+ppStowedExceptions]; pppStowedExceptions
0x1803909d7  call    GetStowedExceptionsForFailFast
0x1803909dc  mov     propertyName, [rbp+ppStowedExceptions]
0x1803909e0  mov     ecx, ebx
0x1803909e2  mov     edx, dword ptr [rbp+cStowedExceptions]
0x1803909e5  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1803909eb  jmp     loc_1803908E1
```
