# WinRTExpressionConversionContext::AddExpressionToTransformGroupPropertySet(Windows::UI::Composition::IExpressionAnimation *,Windows::UI::Composition::ICompositionPropertySet *)

- ea: `0x1805e12f8`
- end: `0x1805e16ce`
- name: `?AddExpressionToTransformGroupPropertySet@WinRTExpressionConversionContext@@QEAAXPEAUIExpressionAnimation@Composition@UI@Windows@@PEAUICompositionPropertySet@345@@Z`
- size: `982`
- prototype: `void __fastcall(WinRTExpressionConversionContext *this, Windows::UI::Composition::IExpressionAnimation *pExpression, Windows::UI::Composition::ICompositionPropertySet *pTransformGroupPropertySet)`
- caller_count: `7`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180191de0`
- `0x180489f00`
- `0x1804f4240`
- `0x1804f4940`
- `0x1804f4c00`
- `0x180650500`
- `0x1809dff20`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x18019385c`
- `0x1805e12f8`
- `0x1806861f4`
- `0x1806877a8`
- `0x180687890`
- `0x18069ba4c`
- `0x1806a3844`
- `0x1806a3aa4`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805e1424`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805e15b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805e16b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805e16c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805e1424`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805e15b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805e16b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805e16c7`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1805e1483`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1805e14e6`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1805e154a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1805e1607`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1805e1483`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1805e14e6`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1805e154a`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1805e1607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805e140e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805e159f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805e140e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805e159f`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=5
void __fastcall WinRTExpressionConversionContext::AddExpressionToTransformGroupPropertySet(
        WinRTExpressionConversionContext *this,
        Windows::UI::Composition::IExpressionAnimation *pExpression,
        Windows::UI::Composition::ICompositionPropertySet *pTransformGroupPropertySet)
{
  std::wstring *p_result; // rdx
  const wchar_t *v7; // rsi
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rbx
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v10; // r13
  unsigned int v11; // eax
  UINT32 v12; // edx
  signed int v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // ebx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v17; // eax
  HRESULT v18; // ebx
  HRESULT (__fastcall *v19)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v20; // eax
  HRESULT v21; // ebx
  __int64 v22; // rsi
  __int64 v23; // r14
  const wchar_t *v24; // rbx
  Windows::UI::Composition::ICompositionObject *ptr; // r12
  unsigned int v26; // eax
  UINT32 v27; // edx
  signed int v28; // eax
  HRESULT v29; // eax
  HRESULT v30; // ebx
  Windows::UI::Composition::ICompositionObject *v31; // rcx
  __int64 v32; // rcx
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+28h] [rbp-89h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionAnimation> spExpressionAsCompositionAnimation; // [rsp+30h] [rbp-81h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObject> spPropertySetAsCO; // [rsp+38h] [rbp-79h] BYREF
  _BYTE targetProperty[40]; // [rsp+40h] [rbp-71h] OVERLAPPED BYREF
  std::wstring result; // [rsp+68h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-29h] BYREF
  HSTRING string; // [rsp+A0h] [rbp-11h] BYREF

  memset(targetProperty, 0, sizeof(targetProperty));
  spPropertySetAsCO.ptr_ = 0;
  std::wstring::_Construct_empty((std::wstring *)&targetProperty[8]);
  std::wstring::_Append<unsigned short>((std::wstring *)&targetProperty[8], L"Expr", 4u);
  std::_Integral_to_string<unsigned short,int>(&result, this->m_expressionCount);
  p_result = &result;
  if ( result._Mypair._Myval2._Myres > 7 )
    p_result = (std::wstring *)result._Mypair._Myval2._Bx._Ptr;
  std::wstring::_Append<unsigned short>(
    (std::wstring *)&targetProperty[8],
    p_result->_Mypair._Myval2._Bx._Buf,
    result._Mypair._Myval2._Mysize);
  if ( result._Mypair._Myval2._Myres > 7 )
    std::_Deallocate<16>(result._Mypair._Myval2._Bx._Ptr, 2 * result._Mypair._Myval2._Myres + 2);
  v7 = (const wchar_t *)&targetProperty[8];
  if ( *(_QWORD *)&targetProperty[32] > 7u )
    v7 = *(const wchar_t **)&targetProperty[8];
  string = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( v7[v9] );
  if ( v9 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x1805E16CDLL);
  }
  v10 = pTransformGroupPropertySet->__vftable;
  v11 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v9);
  v12 = v11 - 1;
  if ( (unsigned int)v9 < v11 )
    v12 = v9;
  v13 = WindowsCreateStringReference(v7, v12, &hstringHeader, &string);
  if ( v13 < 0 )
    RaiseException(v13, 1u, 0, 0);
  result._Mypair._Myval2._Bx = *(std::_String_val<std::_Simple_types<unsigned short> >::_Bxty *)&WinRTExpressionConversionContext::c_identityMatrix3x2.M11;
  result._Mypair._Myval2._Mysize = *(_QWORD *)&WinRTExpressionConversionContext::c_identityMatrix3x2.M31;
  v14 = ((__int64 (__fastcall *)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING, std::wstring *))v10->InsertMatrix3x2)(
          pTransformGroupPropertySet,
          string,
          &result);
  v15 = v14;
  if ( v14 < 0 )
  {
    OnFailure_2990_(v14);
    spExpressionAsCompositionAnimation.ptr_ = 0;
    LODWORD(ppStowedExceptions) = 0;
    TraceForFailFast(v15);
    GetStowedExceptionsForFailFast(
      (_STOWED_EXCEPTION_INFORMATION_V2 ***)&spExpressionAsCompositionAnimation,
      (unsigned int *)&ppStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      v15,
      (unsigned int)ppStowedExceptions,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)spExpressionAsCompositionAnimation.ptr_);
  }
  QueryInterface = pTransformGroupPropertySet->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)targetProperty);
  v17 = QueryInterface(pTransformGroupPropertySet, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, (void **)targetProperty);
  v18 = v17;
  if ( v17 < 0 )
  {
    OnFailure_2990_(v17);
    spExpressionAsCompositionAnimation.ptr_ = 0;
    LODWORD(ppStowedExceptions) = 0;
    TraceForFailFast(v18);
    GetStowedExceptionsForFailFast(
      (_STOWED_EXCEPTION_INFORMATION_V2 ***)&spExpressionAsCompositionAnimation,
      (unsigned int *)&ppStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      v18,
      (unsigned int)ppStowedExceptions,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)spExpressionAsCompositionAnimation.ptr_);
  }
  v19 = pExpression->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spPropertySetAsCO);
  v20 = v19(pExpression, &GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca, (void **)&spPropertySetAsCO.ptr_);
  v21 = v20;
  if ( v20 < 0 )
  {
    OnFailure_2990_(v20);
    spExpressionAsCompositionAnimation.ptr_ = 0;
    LODWORD(ppStowedExceptions) = 0;
    TraceForFailFast(v21);
    GetStowedExceptionsForFailFast(
      (_STOWED_EXCEPTION_INFORMATION_V2 ***)&spExpressionAsCompositionAnimation,
      (unsigned int *)&ppStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      v21,
      (unsigned int)ppStowedExceptions,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)spExpressionAsCompositionAnimation.ptr_);
  }
  v22 = *(_QWORD *)targetProperty;
  v23 = **(_QWORD **)targetProperty;
  v24 = (const wchar_t *)&targetProperty[8];
  if ( *(_QWORD *)&targetProperty[32] > 7u )
    v24 = *(const wchar_t **)&targetProperty[8];
  string = 0;
  do
    ++v8;
  while ( v24[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  ptr = spPropertySetAsCO.ptr_;
  v26 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v8);
  v27 = v26 - 1;
  if ( (unsigned int)v8 < v26 )
    v27 = v8;
  v28 = WindowsCreateStringReference(v24, v27, &hstringHeader, &string);
  if ( v28 < 0 )
    RaiseException(v28, 1u, 0, 0);
  v29 = (*(__int64 (__fastcall **)(__int64, HSTRING, Windows::UI::Composition::ICompositionObject *))(v23 + 72))(
          v22,
          string,
          ptr);
  v30 = v29;
  if ( v29 < 0 )
  {
    OnFailure_2990_(v29);
    spExpressionAsCompositionAnimation.ptr_ = 0;
    LODWORD(ppStowedExceptions) = 0;
    TraceForFailFast(v30);
    GetStowedExceptionsForFailFast(
      (_STOWED_EXCEPTION_INFORMATION_V2 ***)&spExpressionAsCompositionAnimation,
      (unsigned int *)&ppStowedExceptions);
    RoFailFastWithErrorContextInternal2(
      v30,
      (unsigned int)ppStowedExceptions,
      (struct _STOWED_EXCEPTION_INFORMATION_V2 **const)spExpressionAsCompositionAnimation.ptr_);
  }
  ++this->m_expressionCount;
  if ( *(_QWORD *)&targetProperty[32] > 7u )
    std::_Deallocate<16>(*(void **)&targetProperty[8], 2LL * *(_QWORD *)&targetProperty[32] + 2);
  *(__m128i *)&targetProperty[24] = _mm_load_si128((const __m128i *)&_xmm);
  *(_WORD *)&targetProperty[8] = 0;
  v31 = spPropertySetAsCO.ptr_;
  if ( spPropertySetAsCO.ptr_ )
  {
    spPropertySetAsCO.ptr_ = 0;
    v31->Release(v31);
  }
  v32 = *(_QWORD *)targetProperty;
  if ( *(_QWORD *)targetProperty )
  {
    *(_QWORD *)targetProperty = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
}

```

## disassembly

```asm
0x1805e12f8  mov     rax, rsp
0x1805e12fb  mov     [rax+20h], rbx
0x1805e12ff  push    rbp
0x1805e1300  push    rsi
0x1805e1301  push    rdi
0x1805e1302  push    r12
0x1805e1304  push    r13
0x1805e1306  push    r14
0x1805e1308  push    r15
0x1805e130a  lea     rbp, [rax-5Fh]
0x1805e130e  sub     rsp, 0D0h
0x1805e1315  movaps  xmmword ptr [rax-48h], xmm6
0x1805e1319  movaps  xmmword ptr [rax-58h], xmm7
0x1805e131d  mov     rax, cs:__security_cookie
0x1805e1324  xor     rax, rsp
0x1805e1327  mov     [rbp+57h+var_60], rax
0x1805e132b  mov     r14, pTransformGroupPropertySet
0x1805e132e  mov     r12, pExpression
0x1805e1331  mov     r15, this
0x1805e1334  xor     r13d, r13d
0x1805e1337  mov     qword ptr [rbp+57h+targetProperty._Mypair._Myval2._Bx], r13
0x1805e133b  mov     [rbp+57h+spPropertySetAsCO.ptr_], r13
0x1805e133f  xorps   xmm0, xmm0
0x1805e1342  movups  xmmword ptr [rbp+57h+targetProperty._Mypair._Myval2._Bx+8], xmm0
0x1805e1346  xorps   xmm1, xmm1
0x1805e1349  movdqu  xmmword ptr [rbp+57h+targetProperty._Mypair._Myval2._Myres], xmm1
0x1805e134e  lea     this, [rbp+57h+targetProperty._Mypair._Myval2._Bx+8]; this
0x1805e1352  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1805e1357  nop
0x1805e1358  lea     r8d, [r13+4]; _Count
0x1805e135c  lea     pExpression, aExpr; "Expr"
0x1805e1363  lea     this, [rbp+57h+targetProperty._Mypair._Myval2._Bx+8]; this
0x1805e1367  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1805e136c  mov     edx, [r15+8]; _Val
0x1805e1370  lea     this, [rbp+57h+result]; result
0x1805e1374  call    ??$_Integral_to_string@GH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@H@Z; std::_Integral_to_string<ushort,int>(int)
0x1805e1379  nop
0x1805e137a  lea     pExpression, [rbp+57h+result]
0x1805e137e  cmp     [rbp+57h+result._Mypair._Myval2._Myres], 7
0x1805e1383  cmova   pExpression, qword ptr [rbp+57h+result._Mypair._Myval2._Bx]; _Ptr
0x1805e1388  mov     pTransformGroupPropertySet, [rbp+57h+result._Mypair._Myval2._Mysize]; _Count
0x1805e138c  lea     this, [rbp+57h+targetProperty._Mypair._Myval2._Bx+8]; this
0x1805e1390  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1805e1395  nop
0x1805e1396  mov     pExpression, [rbp+57h+result._Mypair._Myval2._Myres]
0x1805e139a  cmp     pExpression, 7
0x1805e139e  jbe     short loc_1805E13B1
0x1805e13a0  lea     pExpression, ds:2[pExpression*2]; _Bytes
0x1805e13a8  mov     this, qword ptr [rbp+57h+result._Mypair._Myval2._Bx]; _Ptr
0x1805e13ac  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1805e13b1  lea     rsi, [rbp+57h+targetProperty._Mypair._Myval2._Bx+8]
0x1805e13b5  cmp     [rbp+57h+var_A8], 7
0x1805e13ba  cmova   rsi, qword ptr [rbp+57h+targetProperty._Mypair._Myval2._Bx+8]
0x1805e13bf  mov     [rbp+57h+string], r13
0x1805e13c3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1805e13c7  mov     rbx, rdi
0x1805e13ca  inc     rbx
0x1805e13cd  cmp     [rsi+rbx*2], r13w
0x1805e13d2  jnz     short loc_1805E13CA
0x1805e13d4  mov     eax, 0FFFFFFFFh
0x1805e13d9  cmp     rbx, rax
0x1805e13dc  ja      loc_1805E16B8
0x1805e13e2  mov     r13, [r14]
0x1805e13e5  movups  xmm6, xmmword ptr cs:?c_identityMatrix3x2@WinRTExpressionConversionContext@@2UMatrix3x2@Numerics@Foundation@Windows@@B.M11; Windows::Foundation::Numerics::Matrix3x2 const WinRTExpressionConversionContext::c_identityMatrix3x2 ...
0x1805e13ec  movsd   xmm7, qword ptr cs:?c_identityMatrix3x2@WinRTExpressionConversionContext@@2UMatrix3x2@Numerics@Foundation@Windows@@B.M31; Windows::Foundation::Numerics::Matrix3x2 const WinRTExpressionConversionContext::c_identityMatrix3x2 ...
0x1805e13f4  mov     ecx, ebx; augend
0x1805e13f6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1805e13fb  lea     edx, [rax-1]
0x1805e13fe  cmp     ebx, eax
0x1805e1400  cmovb   edx, ebx; length
0x1805e1403  lea     r9, [rbp+57h+string]; string
0x1805e1407  lea     pTransformGroupPropertySet, [rbp+57h+hstringHeader]; hstringHeader
0x1805e140b  mov     this, rsi; sourceString
0x1805e140e  call    cs:__imp_WindowsCreateStringReference
0x1805e1414  test    eax, eax
0x1805e1416  jns     short loc_1805E142B
0x1805e1418  xor     r9d, r9d; lpArguments
0x1805e141b  xor     r8d, r8d; nNumberOfArguments
0x1805e141e  lea     edx, [r9+1]; dwExceptionFlags
0x1805e1422  mov     ecx, eax; dwExceptionCode
0x1805e1424  call    cs:__imp_RaiseException
0x1805e142a  nop
0x1805e142b  movaps  xmmword ptr [rbp+57h+result._Mypair._Myval2._Bx], xmm6
0x1805e142f  movsd   [rbp+57h+result._Mypair._Myval2._Mysize], xmm7
0x1805e1434  lea     pTransformGroupPropertySet, [rbp+57h+result]
0x1805e1438  mov     pExpression, [rbp+57h+string]
0x1805e143c  mov     this, r14
0x1805e143f  mov     rax, [r13+38h]
0x1805e1443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e1448  mov     ebx, eax
0x1805e144a  xor     r13d, r13d
0x1805e144d  test    eax, eax
0x1805e144f  jns     short loc_1805E1489
0x1805e1451  mov     ecx, eax; failedFrameHR
0x1805e1453  call    OnFailure_2990_
0x1805e1458  mov     [rsp+100h+spExpressionAsCompositionAnimation.ptr_], r13
0x1805e145d  mov     dword ptr [rsp+100h+ppStowedExceptions], r13d
0x1805e1462  mov     ecx, ebx; errorCode
0x1805e1464  call    TraceForFailFast
0x1805e1469  lea     pExpression, [rsp+100h+ppStowedExceptions]; pcStowedExceptions
0x1805e146e  lea     this, [rsp+100h+spExpressionAsCompositionAnimation]; pppStowedExceptions
0x1805e1473  call    GetStowedExceptionsForFailFast
0x1805e1478  mov     pTransformGroupPropertySet, [rsp+100h+spExpressionAsCompositionAnimation.ptr_]
0x1805e147d  mov     edx, dword ptr [rsp+100h+ppStowedExceptions]
0x1805e1481  mov     ecx, ebx
0x1805e1483  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1805e1489  mov     rax, [r14]
0x1805e148c  mov     rbx, [rax]
0x1805e148f  lea     this, [rbp+57h+targetProperty]; this
0x1805e1493  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1805e1498  lea     pTransformGroupPropertySet, [rbp+57h+targetProperty]
0x1805e149c  lea     pExpression, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x1805e14a3  mov     this, r14
0x1805e14a6  mov     rax, rbx
0x1805e14a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e14ae  mov     ebx, eax
0x1805e14b0  test    eax, eax
0x1805e14b2  jns     short loc_1805E14EC
0x1805e14b4  mov     ecx, eax; failedFrameHR
0x1805e14b6  call    OnFailure_2990_
0x1805e14bb  mov     [rsp+100h+spExpressionAsCompositionAnimation.ptr_], r13
0x1805e14c0  mov     dword ptr [rsp+100h+ppStowedExceptions], r13d
0x1805e14c5  mov     ecx, ebx; errorCode
0x1805e14c7  call    TraceForFailFast
0x1805e14cc  lea     pExpression, [rsp+100h+ppStowedExceptions]; pcStowedExceptions
0x1805e14d1  lea     this, [rsp+100h+spExpressionAsCompositionAnimation]; pppStowedExceptions
0x1805e14d6  call    GetStowedExceptionsForFailFast
0x1805e14db  mov     pTransformGroupPropertySet, [rsp+100h+spExpressionAsCompositionAnimation.ptr_]
0x1805e14e0  mov     edx, dword ptr [rsp+100h+ppStowedExceptions]
0x1805e14e4  mov     ecx, ebx
0x1805e14e6  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1805e14ec  mov     rax, [r12]
0x1805e14f0  mov     rbx, [rax]
0x1805e14f3  lea     this, [rbp+57h+spPropertySetAsCO]; this
0x1805e14f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1805e14fc  lea     pTransformGroupPropertySet, [rbp+57h+spPropertySetAsCO]
0x1805e1500  lea     pExpression, _GUID_464c4c2c_1caa_4061_9b40_e13fde1503ca
0x1805e1507  mov     this, r12
0x1805e150a  mov     rax, rbx
0x1805e150d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e1512  mov     ebx, eax
0x1805e1514  test    eax, eax
0x1805e1516  jns     short loc_1805E1550
0x1805e1518  mov     ecx, eax; failedFrameHR
0x1805e151a  call    OnFailure_2990_
0x1805e151f  mov     [rsp+100h+spExpressionAsCompositionAnimation.ptr_], r13
0x1805e1524  mov     dword ptr [rsp+100h+ppStowedExceptions], r13d
0x1805e1529  mov     ecx, ebx; errorCode
0x1805e152b  call    TraceForFailFast
0x1805e1530  lea     pExpression, [rsp+100h+ppStowedExceptions]; pcStowedExceptions
0x1805e1535  lea     this, [rsp+100h+spExpressionAsCompositionAnimation]; pppStowedExceptions
0x1805e153a  call    GetStowedExceptionsForFailFast
0x1805e153f  mov     pTransformGroupPropertySet, [rsp+100h+spExpressionAsCompositionAnimation.ptr_]
0x1805e1544  mov     edx, dword ptr [rsp+100h+ppStowedExceptions]
0x1805e1548  mov     ecx, ebx
0x1805e154a  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1805e1550  mov     rsi, qword ptr [rbp+57h+targetProperty._Mypair._Myval2._Bx]
0x1805e1554  mov     r14, [rsi]
0x1805e1557  lea     rbx, [rbp+57h+targetProperty._Mypair._Myval2._Bx+8]
0x1805e155b  cmp     [rbp+57h+var_A8], 7
0x1805e1560  cmova   rbx, qword ptr [rbp+57h+targetProperty._Mypair._Myval2._Bx+8]
0x1805e1565  mov     [rbp+57h+string], r13
0x1805e1569  inc     rdi
0x1805e156c  cmp     [rbx+rdi*2], r13w
0x1805e1571  jnz     short loc_1805E1569
0x1805e1573  mov     eax, 0FFFFFFFFh
0x1805e1578  cmp     rdi, rax
0x1805e157b  ja      loc_1805E16A2
0x1805e1581  mov     r12, [rbp+57h+spPropertySetAsCO.ptr_]
0x1805e1585  mov     ecx, edi; augend
0x1805e1587  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1805e158c  lea     edx, [rax-1]
0x1805e158f  cmp     edi, eax
0x1805e1591  cmovb   edx, edi; length
0x1805e1594  lea     r9, [rbp+57h+string]; string
0x1805e1598  lea     pTransformGroupPropertySet, [rbp+57h+hstringHeader]; hstringHeader
0x1805e159c  mov     this, rbx; sourceString
0x1805e159f  call    cs:__imp_WindowsCreateStringReference
0x1805e15a5  test    eax, eax
0x1805e15a7  jns     short loc_1805E15BC
0x1805e15a9  xor     r9d, r9d; lpArguments
0x1805e15ac  xor     r8d, r8d; nNumberOfArguments
0x1805e15af  lea     edx, [r9+1]; dwExceptionFlags
0x1805e15b3  mov     ecx, eax; dwExceptionCode
0x1805e15b5  call    cs:__imp_RaiseException
0x1805e15bb  nop
0x1805e15bc  mov     pTransformGroupPropertySet, r12
0x1805e15bf  mov     pExpression, [rbp+57h+string]
0x1805e15c3  mov     this, rsi
0x1805e15c6  mov     rax, [r14+48h]
0x1805e15ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e15cf  mov     ebx, eax
0x1805e15d1  test    eax, eax
0x1805e15d3  jns     short loc_1805E160D
0x1805e15d5  mov     ecx, eax; failedFrameHR
0x1805e15d7  call    OnFailure_2990_
0x1805e15dc  mov     [rsp+100h+spExpressionAsCompositionAnimation.ptr_], r13
0x1805e15e1  mov     dword ptr [rsp+100h+ppStowedExceptions], r13d
0x1805e15e6  mov     ecx, ebx; errorCode
0x1805e15e8  call    TraceForFailFast
0x1805e15ed  lea     pExpression, [rsp+100h+ppStowedExceptions]; pcStowedExceptions
0x1805e15f2  lea     this, [rsp+100h+spExpressionAsCompositionAnimation]; pppStowedExceptions
0x1805e15f7  call    GetStowedExceptionsForFailFast
0x1805e15fc  mov     pTransformGroupPropertySet, [rsp+100h+spExpressionAsCompositionAnimation.ptr_]
0x1805e1601  mov     edx, dword ptr [rsp+100h+ppStowedExceptions]
0x1805e1605  mov     ecx, ebx
0x1805e1607  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1805e160d  inc     dword ptr [r15+8]
0x1805e1611  mov     pExpression, [rbp+57h+var_A8]
0x1805e1615  cmp     pExpression, 7
0x1805e1619  jbe     short loc_1805E162C
0x1805e161b  lea     pExpression, ds:2[pExpression*2]; _Bytes
0x1805e1623  mov     this, qword ptr [rbp+57h+targetProperty._Mypair._Myval2._Bx+8]; _Ptr
0x1805e1627  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1805e162c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1805e1634  movdqu  xmmword ptr [rbp+57h+targetProperty._Mypair._Myval2._Myres], xmm0
0x1805e1639  mov     word ptr [rbp+57h+targetProperty._Mypair._Myval2._Bx+8], r13w
0x1805e163e  mov     this, [rbp+57h+spPropertySetAsCO.ptr_]
0x1805e1642  test    this, this
0x1805e1645  jz      short loc_1805E1658
0x1805e1647  mov     [rbp+57h+spPropertySetAsCO.ptr_], r13
0x1805e164b  mov     rax, [this]
0x1805e164e  mov     rax, [rax+10h]
0x1805e1652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e1657  nop
0x1805e1658  mov     this, qword ptr [rbp+57h+targetProperty._Mypair._Myval2._Bx]
0x1805e165c  test    this, this
0x1805e165f  jz      short loc_1805E1671
0x1805e1661  mov     qword ptr [rbp+57h+targetProperty._Mypair._Myval2._Bx], r13
0x1805e1665  mov     rax, [this]
0x1805e1668  mov     rax, [rax+10h]
0x1805e166c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e1671  mov     this, [rbp+57h+var_60]
0x1805e1675  xor     this, rsp; StackCookie
0x1805e1678  call    __security_check_cookie
0x1805e167d  lea     r11, [rsp+100h+var_30]
0x1805e1685  mov     rbx, [r11+58h]
0x1805e1689  movaps  xmm6, xmmword ptr [r11-10h]
0x1805e168e  movaps  xmm7, xmmword ptr [r11-20h]
0x1805e1693  mov     rsp, r11
0x1805e1696  pop     r15
0x1805e1698  pop     r14
0x1805e169a  pop     r13
0x1805e169c  pop     r12
0x1805e169e  pop     rdi
0x1805e169f  pop     rsi
0x1805e16a0  pop     rbp
0x1805e16a1  retn
0x1805e16a2  xor     r9d, r9d; lpArguments
0x1805e16a5  xor     r8d, r8d; nNumberOfArguments
0x1805e16a8  lea     edx, [r9+1]; dwExceptionFlags
0x1805e16ac  mov     ecx, 80070216h; dwExceptionCode
0x1805e16b1  call    cs:__imp_RaiseException
0x1805e16b7  int     3; Trap to Debugger
0x1805e16b8  xor     r9d, r9d; lpArguments
0x1805e16bb  xor     r8d, r8d; nNumberOfArguments
0x1805e16be  lea     edx, [r9+1]; dwExceptionFlags
0x1805e16c2  mov     ecx, 80070216h; dwExceptionCode
0x1805e16c7  call    cs:__imp_RaiseException
```
