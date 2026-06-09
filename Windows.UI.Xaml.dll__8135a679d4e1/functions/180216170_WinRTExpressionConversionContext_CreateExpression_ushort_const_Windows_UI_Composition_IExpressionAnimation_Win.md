# WinRTExpressionConversionContext::CreateExpression(ushort const *,Windows::UI::Composition::IExpressionAnimation * *,Windows::UI::Composition::ICompositionPropertySet * *)

- ea: `0x180216170`
- end: `0x180216639`
- name: `?CreateExpression@WinRTExpressionConversionContext@@QEAAXPEBGPEAPEAUIExpressionAnimation@Composition@UI@Windows@@PEAPEAUICompositionPropertySet@345@@Z`
- size: `1225`
- prototype: `void __fastcall(WinRTExpressionConversionContext *this, const wchar_t *expressionString, Windows::UI::Composition::IExpressionAnimation **expression, Windows::UI::Composition::ICompositionPropertySet **propertySet)`
- caller_count: `15`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18010f33c`
- `0x180191de0`
- `0x180193160`
- `0x180194a2c`
- `0x180489f00`
- `0x1804f3700`
- `0x1804f4240`
- `0x1804f4588`
- `0x1804f47c0`
- `0x1804f4940`
- `0x1804f4c00`
- `0x1804f4f40`
- `0x1805b40b8`
- `0x1809dff20`
- `0x1809e1184`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x180216170`
- `0x180216640`
- `0x1806877a8`
- `0x180687890`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802161fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021637b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180216502`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802165fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802161fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18021637b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180216502`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802165fa`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802164eb`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18021653e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180216575`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802165ac`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802165e3`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18021662d`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802164eb`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18021653e`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180216575`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802165ac`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802165e3`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x18021662d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180216216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180216397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180216216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180216397`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall WinRTExpressionConversionContext::CreateExpression(
        WinRTExpressionConversionContext *this,
        const wchar_t *expressionString,
        Windows::UI::Composition::IExpressionAnimation **expression,
        Windows::UI::Composition::ICompositionPropertySet **propertySet)
{
  Windows::UI::Composition::ICompositor *ptr; // rdi
  Windows::UI::Composition::ICompositor_vtbl *v8; // r14
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rdx
  signed int v11; // eax
  HRESULT v12; // eax
  HRESULT v13; // ebx
  Windows::UI::Composition::IExpressionAnimation *v14; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT v16; // eax
  HRESULT v17; // ebx
  Windows::UI::Composition::IExpressionAnimation *v18; // rbx
  HRESULT (__fastcall *v19)(IUnknown *, const _GUID *, void **); // rdi
  Windows::UI::Composition::ICompositionObject *v20; // rcx
  HRESULT v21; // eax
  HRESULT v22; // ebx
  Windows::UI::Composition::ICompositionObject *v23; // rbx
  HRESULT (__fastcall *get_Properties)(Windows::UI::Composition::ICompositionObject *, Windows::UI::Composition::ICompositionPropertySet **); // rdi
  Windows::UI::Composition::ICompositionPropertySet *v25; // rcx
  HRESULT v26; // eax
  HRESULT v27; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v28; // rbx
  HRESULT (__fastcall *v29)(IUnknown *, const _GUID *, void **); // rdi
  Windows::UI::Composition::ICompositionObject *v30; // rcx
  HRESULT v31; // eax
  HRESULT v32; // ebx
  Windows::UI::Composition::ICompositionAnimation *v33; // rbx
  Windows::UI::Composition::ICompositionAnimation_vtbl *v34; // r14
  Windows::UI::Composition::ICompositionObject *v35; // rdi
  signed int v36; // eax
  HRESULT v37; // eax
  HRESULT v38; // ebx
  Windows::UI::Composition::ICompositionPropertySet *v39; // rcx
  Windows::UI::Composition::ICompositionObject *v40; // rdx
  Windows::UI::Composition::ICompositionObject *v41; // rcx
  Windows::UI::Composition::ICompositionAnimation *v42; // rcx
  Windows::UI::Composition::IExpressionAnimation *v43; // rcx
  unsigned int cStowedExceptions; // [rsp+20h] [rbp-49h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+28h] [rbp-41h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::IExpressionAnimation> expr; // [rsp+30h] [rbp-39h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionPropertySet> expressionPropertySet; // [rsp+38h] [rbp-31h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> psICO; // [rsp+40h] [rbp-29h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> exprICO; // [rsp+48h] [rbp-21h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> exprICA; // [rsp+50h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-11h] BYREF
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF

  expr.ptr_ = 0;
  exprICA.ptr_ = 0;
  exprICO.ptr_ = 0;
  expressionPropertySet.ptr_ = 0;
  psICO.ptr_ = 0;
  ptr = this->m_spCompositor.ptr_;
  v8 = this->m_spCompositor.ptr_->__vftable;
  v9 = -1;
  if ( !expressionString )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&expr);
    v12 = v8->CreateExpressionAnimation(ptr, &expr.ptr_);
    v13 = v12;
    if ( v12 >= 0 )
      goto LABEL_9;
    goto LABEL_47;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&expr);
  string = 0;
  v10 = -1;
  do
    ++v10;
  while ( expressionString[v10] );
  if ( v10 > 0xFFFFFFFF || (int)v10 + 1 < (unsigned int)v10 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v11 = WindowsCreateStringReference(expressionString, v10, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v12 = v8->CreateExpressionAnimationWithExpression(ptr, string, &expr.ptr_);
  v13 = v12;
  if ( v12 < 0 )
  {
LABEL_47:
    OnFailure_2990_(v12);
    cStowedExceptions = 0;
    ppStowedExceptions = 0;
    TraceForFailFast(v13);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v13, cStowedExceptions, ppStowedExceptions);
  }
LABEL_9:
  DCompTreeHost::SetTracingCookie(expr.ptr_, Expression);
  v14 = expr.ptr_;
  QueryInterface = expr.ptr_->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&exprICA);
  v16 = QueryInterface(v14, &GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca, (void **)&exprICA.ptr_);
  v17 = v16;
  if ( v16 < 0 )
  {
    OnFailure_2990_(v16);
    ppStowedExceptions = 0;
    cStowedExceptions = 0;
    TraceForFailFast(v17);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v17, cStowedExceptions, ppStowedExceptions);
  }
  v18 = expr.ptr_;
  v19 = expr.ptr_->QueryInterface;
  v20 = exprICO.ptr_;
  if ( exprICO.ptr_ )
  {
    exprICO.ptr_ = 0;
    v20->Release(v20);
  }
  v21 = v19(v18, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, (void **)&exprICO.ptr_);
  v22 = v21;
  if ( v21 < 0 )
  {
    OnFailure_2990_(v21);
    ppStowedExceptions = 0;
    cStowedExceptions = 0;
    TraceForFailFast(v22);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v22, cStowedExceptions, ppStowedExceptions);
  }
  v23 = exprICO.ptr_;
  get_Properties = exprICO.ptr_->get_Properties;
  v25 = expressionPropertySet.ptr_;
  if ( expressionPropertySet.ptr_ )
  {
    expressionPropertySet.ptr_ = 0;
    v25->Release(v25);
  }
  v26 = get_Properties(v23, &expressionPropertySet.ptr_);
  v27 = v26;
  if ( v26 < 0 )
  {
    OnFailure_2990_(v26);
    ppStowedExceptions = 0;
    cStowedExceptions = 0;
    TraceForFailFast(v27);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v27, cStowedExceptions, ppStowedExceptions);
  }
  v28 = expressionPropertySet.ptr_;
  v29 = expressionPropertySet.ptr_->QueryInterface;
  v30 = psICO.ptr_;
  if ( psICO.ptr_ )
  {
    psICO.ptr_ = 0;
    v30->Release(v30);
  }
  v31 = v29(v28, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, (void **)&psICO.ptr_);
  v32 = v31;
  if ( v31 < 0 )
  {
    OnFailure_2990_(v31);
    ppStowedExceptions = 0;
    cStowedExceptions = 0;
    TraceForFailFast(v32);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v32, cStowedExceptions, ppStowedExceptions);
  }
  v33 = exprICA.ptr_;
  v34 = exprICA.ptr_->__vftable;
  string = 0;
  do
    ++v9;
  while ( ExpressionHelper::sc_paramName_PropertySet[v9] );
  if ( v9 > 0xFFFFFFFF || (int)v9 + 1 < (unsigned int)v9 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v35 = psICO.ptr_;
  v36 = WindowsCreateStringReference(ExpressionHelper::sc_paramName_PropertySet, v9, &hstringHeader, &string);
  if ( v36 < 0 )
  {
    RaiseException(v36, 1u, 0, 0);
    __debugbreak();
  }
  v37 = v34->SetReferenceParameter(v33, string, v35);
  v38 = v37;
  if ( v37 < 0 )
  {
    OnFailure_2990_(v37);
    ppStowedExceptions = 0;
    cStowedExceptions = 0;
    TraceForFailFast(v38);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v38, cStowedExceptions, ppStowedExceptions);
  }
  if ( expr.ptr_ )
    expr.ptr_->AddRef(expr.ptr_);
  *expression = expr.ptr_;
  v39 = expressionPropertySet.ptr_;
  if ( expressionPropertySet.ptr_ )
  {
    expressionPropertySet.ptr_->AddRef(expressionPropertySet.ptr_);
    v39 = expressionPropertySet.ptr_;
  }
  *propertySet = v39;
  v40 = psICO.ptr_;
  if ( psICO.ptr_ )
  {
    psICO.ptr_ = 0;
    v40->Release(v40);
    v39 = expressionPropertySet.ptr_;
  }
  if ( v39 )
  {
    expressionPropertySet.ptr_ = 0;
    v39->Release(v39);
  }
  v41 = exprICO.ptr_;
  if ( exprICO.ptr_ )
  {
    exprICO.ptr_ = 0;
    v41->Release(v41);
  }
  v42 = exprICA.ptr_;
  if ( exprICA.ptr_ )
  {
    exprICA.ptr_ = 0;
    v42->Release(v42);
  }
  v43 = expr.ptr_;
  if ( expr.ptr_ )
  {
    expr.ptr_ = 0;
    v43->Release(v43);
  }
}

```

## disassembly

```asm
0x180216170  push    rbp
0x180216172  push    rbx
0x180216173  push    rsi
0x180216174  push    rdi
0x180216175  push    r12
0x180216177  push    r13
0x180216179  push    r14
0x18021617b  push    r15
0x18021617d  lea     rbp, [rsp-1Fh]
0x180216182  sub     rsp, 88h
0x180216189  mov     rax, cs:__security_cookie
0x180216190  xor     rax, rsp
0x180216193  mov     [rbp+57h+var_48], rax
0x180216197  mov     r12, propertySet
0x18021619a  mov     r15, expression
0x18021619d  mov     rbx, expressionString
0x1802161a0  xor     r13d, r13d
0x1802161a3  mov     [rbp+57h+expr.ptr_], r13
0x1802161a7  mov     [rbp+57h+exprICA.ptr_], r13
0x1802161ab  mov     [rbp+57h+exprICO.ptr_], r13
0x1802161af  mov     [rbp+57h+expressionPropertySet.ptr_], r13
0x1802161b3  mov     [rbp+57h+psICO.ptr_], r13
0x1802161b7  mov     rdi, [this]
0x1802161ba  mov     r14, [rdi]
0x1802161bd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1802161c1  lea     this, [rbp+57h+expr]; this
0x1802161c5  test    expressionString, expressionString
0x1802161c8  jz      loc_18021649F
0x1802161ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802161d3  mov     [rbp+57h+string], r13
0x1802161d7  mov     expressionString, rsi
0x1802161da  inc     expressionString; length
0x1802161dd  cmp     [rbx+expressionString*2], r13w
0x1802161e2  jnz     short loc_1802161DA
0x1802161e4  mov     eax, 0FFFFFFFFh
0x1802161e9  cmp     expressionString, rax
0x1802161ec  jbe     short loc_180216204
0x1802161ee  xor     r9d, r9d; lpArguments
0x1802161f1  xor     r8d, r8d; nNumberOfArguments
0x1802161f4  lea     edx, [propertySet+1]; dwExceptionFlags
0x1802161f8  mov     ecx, 80070216h; dwExceptionCode
0x1802161fd  call    cs:__imp_RaiseException
0x180216203  int     3; Trap to Debugger
0x180216204  lea     eax, [expressionString+1]
0x180216207  cmp     eax, edx
0x180216209  jb      short loc_1802161EE
0x18021620b  lea     propertySet, [rbp+57h+string]; string
0x18021620f  lea     expression, [rbp+57h+hstringHeader]; hstringHeader
0x180216213  mov     this, rbx; sourceString
0x180216216  call    cs:__imp_WindowsCreateStringReference
0x18021621c  test    eax, eax
0x18021621e  js      loc_1802164F6
0x180216224  lea     expression, [rbp+57h+expr]
0x180216228  mov     expressionString, [rbp+57h+string]
0x18021622c  mov     this, rdi
0x18021622f  mov     rax, [r14+70h]
0x180216233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216238  mov     ebx, eax
0x18021623a  test    eax, eax
0x18021623c  js      loc_180216509
0x180216242  mov     edx, 5; category
0x180216247  mov     this, [rbp+57h+expr.ptr_]; compositionObject
0x18021624b  call    ?SetTracingCookie@DCompTreeHost@@SAIPEAUIInspectable@@W4TracingCookieCategory@1@@Z; DCompTreeHost::SetTracingCookie(IInspectable *,DCompTreeHost::TracingCookieCategory)
0x180216250  mov     rbx, [rbp+57h+expr.ptr_]
0x180216254  mov     rax, [rbx]
0x180216257  mov     rdi, [rax]
0x18021625a  lea     this, [rbp+57h+exprICA]; this
0x18021625e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180216263  lea     expression, [rbp+57h+exprICA]
0x180216267  lea     expressionString, _GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca
0x18021626e  mov     this, rbx
0x180216271  mov     rax, rdi
0x180216274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216279  mov     ebx, eax
0x18021627b  test    eax, eax
0x18021627d  js      loc_180216512
0x180216283  mov     rbx, [rbp+57h+expr.ptr_]
0x180216287  mov     rax, [rbx]
0x18021628a  mov     rdi, [rax]
0x18021628d  mov     this, [rbp+57h+exprICO.ptr_]
0x180216291  test    this, this
0x180216294  jz      short loc_1802162A6
0x180216296  mov     [rbp+57h+exprICO.ptr_], r13
0x18021629a  mov     expressionString, [this]
0x18021629d  mov     rax, [expressionString+10h]
0x1802162a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802162a6  lea     expression, [rbp+57h+exprICO]
0x1802162aa  lea     expressionString, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x1802162b1  mov     this, rbx
0x1802162b4  mov     rax, rdi
0x1802162b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802162bc  mov     ebx, eax
0x1802162be  test    eax, eax
0x1802162c0  js      loc_180216549
0x1802162c6  mov     rbx, [rbp+57h+exprICO.ptr_]
0x1802162ca  mov     rax, [rbx]
0x1802162cd  mov     rdi, [rax+40h]
0x1802162d1  mov     this, [rbp+57h+expressionPropertySet.ptr_]
0x1802162d5  test    this, this
0x1802162d8  jz      short loc_1802162EA
0x1802162da  mov     [rbp+57h+expressionPropertySet.ptr_], r13
0x1802162de  mov     expressionString, [this]
0x1802162e1  mov     rax, [expressionString+10h]
0x1802162e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802162ea  lea     expressionString, [rbp+57h+expressionPropertySet]
0x1802162ee  mov     this, rbx
0x1802162f1  mov     rax, rdi
0x1802162f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802162f9  mov     ebx, eax
0x1802162fb  test    eax, eax
0x1802162fd  js      loc_180216580
0x180216303  mov     rbx, [rbp+57h+expressionPropertySet.ptr_]
0x180216307  mov     rax, [rbx]
0x18021630a  mov     rdi, [rax]
0x18021630d  mov     this, [rbp+57h+psICO.ptr_]
0x180216311  test    this, this
0x180216314  jz      short loc_180216326
0x180216316  mov     [rbp+57h+psICO.ptr_], r13
0x18021631a  mov     expression, [this]
0x18021631d  mov     rax, [expression+10h]
0x180216321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216326  lea     expression, [rbp+57h+psICO]
0x18021632a  lea     expressionString, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x180216331  mov     this, rbx
0x180216334  mov     rax, rdi
0x180216337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021633c  mov     ebx, eax
0x18021633e  test    eax, eax
0x180216340  js      loc_1802165B7
0x180216346  mov     rbx, [rbp+57h+exprICA.ptr_]
0x18021634a  mov     r14, [rbx]
0x18021634d  mov     [rbp+57h+string], r13
0x180216351  mov     this, cs:?sc_paramName_PropertySet@ExpressionHelper@@2QEBGEB; sourceString
0x180216358  inc     rsi
0x18021635b  cmp     [this+rsi*2], r13w
0x180216360  jnz     short loc_180216358
0x180216362  mov     eax, 0FFFFFFFFh
0x180216367  cmp     rsi, rax
0x18021636a  jbe     short loc_180216382
0x18021636c  xor     r9d, r9d; lpArguments
0x18021636f  xor     r8d, r8d; nNumberOfArguments
0x180216372  lea     edx, [propertySet+1]; dwExceptionFlags
0x180216376  mov     ecx, 80070216h; dwExceptionCode
0x18021637b  call    cs:__imp_RaiseException
0x180216381  int     3; Trap to Debugger
0x180216382  lea     eax, [rsi+1]
0x180216385  cmp     eax, esi
0x180216387  jb      short loc_18021636C
0x180216389  mov     rdi, [rbp+57h+psICO.ptr_]
0x18021638d  lea     propertySet, [rbp+57h+string]; string
0x180216391  lea     expression, [rbp+57h+hstringHeader]; hstringHeader
0x180216395  mov     edx, esi; length
0x180216397  call    cs:__imp_WindowsCreateStringReference
0x18021639d  test    eax, eax
0x18021639f  js      loc_1802165EE
0x1802163a5  mov     expression, rdi
0x1802163a8  mov     expressionString, [rbp+57h+string]
0x1802163ac  mov     this, rbx
0x1802163af  mov     rax, [r14+60h]
0x1802163b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802163b8  mov     ebx, eax
0x1802163ba  test    eax, eax
0x1802163bc  js      loc_180216601
0x1802163c2  mov     this, [rbp+57h+expr.ptr_]
0x1802163c6  test    this, this
0x1802163c9  jz      short loc_1802163D8
0x1802163cb  mov     rax, [this]
0x1802163ce  mov     rax, [rax+8]
0x1802163d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802163d7  nop
0x1802163d8  mov     rax, [rbp+57h+expr.ptr_]
0x1802163dc  mov     [r15], rax
0x1802163df  mov     this, [rbp+57h+expressionPropertySet.ptr_]
0x1802163e3  test    this, this
0x1802163e6  jz      short loc_1802163F8
0x1802163e8  mov     rax, [this]
0x1802163eb  mov     rax, [rax+8]
0x1802163ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802163f4  mov     this, [rbp+57h+expressionPropertySet.ptr_]
0x1802163f8  mov     [r12], this
0x1802163fc  mov     expressionString, [rbp+57h+psICO.ptr_]
0x180216400  test    expressionString, expressionString
0x180216403  jz      short loc_18021641C
0x180216405  mov     [rbp+57h+psICO.ptr_], r13
0x180216409  mov     rax, [expressionString]
0x18021640c  mov     this, expressionString
0x18021640f  mov     rax, [rax+10h]
0x180216413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216418  mov     this, [rbp+57h+expressionPropertySet.ptr_]
0x18021641c  test    this, this
0x18021641f  jz      short loc_180216432
0x180216421  mov     [rbp+57h+expressionPropertySet.ptr_], r13
0x180216425  mov     rax, [this]
0x180216428  mov     rax, [rax+10h]
0x18021642c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216431  nop
0x180216432  mov     this, [rbp+57h+exprICO.ptr_]
0x180216436  test    this, this
0x180216439  jz      short loc_18021644C
0x18021643b  mov     [rbp+57h+exprICO.ptr_], r13
0x18021643f  mov     rax, [this]
0x180216442  mov     rax, [rax+10h]
0x180216446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021644b  nop
0x18021644c  mov     this, [rbp+57h+exprICA.ptr_]
0x180216450  test    this, this
0x180216453  jz      short loc_180216466
0x180216455  mov     [rbp+57h+exprICA.ptr_], r13
0x180216459  mov     rax, [this]
0x18021645c  mov     rax, [rax+10h]
0x180216460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216465  nop
0x180216466  mov     this, [rbp+57h+expr.ptr_]
0x18021646a  test    this, this
0x18021646d  jz      short loc_18021647F
0x18021646f  mov     [rbp+57h+expr.ptr_], r13
0x180216473  mov     rax, [this]
0x180216476  mov     rax, [rax+10h]
0x18021647a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021647f  mov     this, [rbp+57h+var_48]
0x180216483  xor     this, rsp; StackCookie
0x180216486  call    __security_check_cookie
0x18021648b  add     rsp, 88h
0x180216492  pop     r15
0x180216494  pop     r14
0x180216496  pop     r13
0x180216498  pop     r12
0x18021649a  pop     rdi
0x18021649b  pop     rsi
0x18021649c  pop     rbx
0x18021649d  pop     rbp
0x18021649e  retn
0x18021649f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802164a4  nop
0x1802164a5  lea     expressionString, [rbp+57h+expr]
0x1802164a9  mov     this, rdi
0x1802164ac  mov     rax, [r14+68h]
0x1802164b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802164b5  mov     ebx, eax
0x1802164b7  test    eax, eax
0x1802164b9  jns     loc_180216242
0x1802164bf  mov     ecx, eax; failedFrameHR
0x1802164c1  call    OnFailure_2990_
0x1802164c6  mov     [rbp+57h+cStowedExceptions], r13d
0x1802164ca  mov     [rbp+57h+ppStowedExceptions], r13
0x1802164ce  mov     ecx, ebx; errorCode
0x1802164d0  call    TraceForFailFast
0x1802164d5  lea     expressionString, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x1802164d9  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x1802164dd  call    GetStowedExceptionsForFailFast
0x1802164e2  mov     expression, [rbp+57h+ppStowedExceptions]
0x1802164e6  mov     edx, [rbp+57h+cStowedExceptions]
0x1802164e9  mov     ecx, ebx
0x1802164eb  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1802164f1  jmp     loc_180216242
0x1802164f6  xor     r9d, r9d; lpArguments
0x1802164f9  xor     r8d, r8d; nNumberOfArguments
0x1802164fc  lea     edx, [propertySet+1]; dwExceptionFlags
0x180216500  mov     ecx, eax; dwExceptionCode
0x180216502  call    cs:__imp_RaiseException
0x180216508  int     3; Trap to Debugger
0x180216509  mov     ecx, ebx; failedFrameHR
0x18021650b  call    OnFailure_2990_
0x180216510  jmp     short loc_1802164C6
0x180216512  mov     ecx, ebx; failedFrameHR
0x180216514  call    OnFailure_2990_
0x180216519  mov     [rbp+57h+ppStowedExceptions], r13
0x18021651d  mov     [rbp+57h+cStowedExceptions], r13d
0x180216521  mov     ecx, ebx; errorCode
0x180216523  call    TraceForFailFast
0x180216528  lea     expressionString, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x18021652c  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x180216530  call    GetStowedExceptionsForFailFast
0x180216535  mov     expression, [rbp+57h+ppStowedExceptions]
0x180216539  mov     edx, [rbp+57h+cStowedExceptions]
0x18021653c  mov     ecx, ebx
0x18021653e  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180216544  jmp     loc_180216283
0x180216549  mov     ecx, ebx; failedFrameHR
0x18021654b  call    OnFailure_2990_
0x180216550  mov     [rbp+57h+ppStowedExceptions], r13
0x180216554  mov     [rbp+57h+cStowedExceptions], r13d
0x180216558  mov     ecx, ebx; errorCode
0x18021655a  call    TraceForFailFast
0x18021655f  lea     expressionString, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x180216563  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x180216567  call    GetStowedExceptionsForFailFast
0x18021656c  mov     expression, [rbp+57h+ppStowedExceptions]
0x180216570  mov     edx, [rbp+57h+cStowedExceptions]
0x180216573  mov     ecx, ebx
0x180216575  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x18021657b  jmp     loc_1802162C6
0x180216580  mov     ecx, ebx; failedFrameHR
0x180216582  call    OnFailure_2990_
0x180216587  mov     [rbp+57h+ppStowedExceptions], r13
0x18021658b  mov     [rbp+57h+cStowedExceptions], r13d
0x18021658f  mov     ecx, ebx; errorCode
0x180216591  call    TraceForFailFast
0x180216596  lea     expressionString, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x18021659a  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
  ... truncated ...
```
