# SetDefaultValues

- ea: `0x1805ec4d4`
- end: `0x1805ec766`
- name: `SetDefaultValues`
- size: `658`
- prototype: `HRESULT __fastcall(Windows::UI::Composition::ICompositionPropertySet *manipulationPropertySet)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180706ccc`
- `0x1807b1b08`

## callees

- `0x180004bc0`
- `0x1805ec4d4`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec6ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec701`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec714`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec727`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec73a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec6ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec701`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec714`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec727`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1805ec73a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec562`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec5b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec60b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec562`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec5b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec60b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1805ec659`

## pseudocode

```c
__int64 __fastcall SetDefaultValues(Windows::UI::Composition::ICompositionPropertySet *manipulationPropertySet)
{
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v1; // rdi
  signed int v3; // eax
  HRESULT (__fastcall *InsertVector3)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, Windows::Foundation::Numerics::Vector3); // rax
  HRESULT v5; // eax
  unsigned int v6; // edi
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v7; // rdi
  signed int v8; // eax
  HRESULT (__fastcall *v9)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, Windows::Foundation::Numerics::Vector3); // rax
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v10; // rdi
  signed int v11; // eax
  HRESULT (__fastcall *v12)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, Windows::Foundation::Numerics::Vector3); // rax
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v13; // rdi
  signed int v14; // eax
  HRESULT (__fastcall *v15)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, Windows::Foundation::Numerics::Vector3); // rax
  Windows::UI::Composition::ICompositionPropertySet_vtbl *v16; // rdi
  signed int v17; // eax
  HRESULT (__fastcall *InsertMatrix4x4)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING__ *, Windows::Foundation::Numerics::Matrix4x4); // rax
  HRESULT v19; // eax
  unsigned int v20; // ebx
  __int64 v22; // [rsp+20h] [rbp-49h] BYREF
  int v23; // [rsp+28h] [rbp-41h]
  _OWORD v24[4]; // [rsp+30h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF

  v1 = manipulationPropertySet->__vftable;
  string = 0;
  v3 = WindowsCreateStringReference(L"Translation", 0xBu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  InsertVector3 = v1->InsertVector3;
  v22 = 0;
  v23 = 0;
  v5 = ((__int64 (__fastcall *)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING, __int64 *))InsertVector3)(
         manipulationPropertySet,
         string,
         &v22);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_12;
  v7 = manipulationPropertySet->__vftable;
  string = 0;
  v8 = WindowsCreateStringReference(L"Pan", 3u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v9 = v7->InsertVector3;
  v22 = 0;
  v23 = 0;
  v5 = ((__int64 (__fastcall *)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING, __int64 *))v9)(
         manipulationPropertySet,
         string,
         &v22);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_12;
  v10 = manipulationPropertySet->__vftable;
  string = 0;
  v11 = WindowsCreateStringReference(L"Scale", 5u, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v12 = v10->InsertVector3;
  v22 = 0x3F8000003F800000LL;
  v23 = 1065353216;
  v5 = ((__int64 (__fastcall *)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING, __int64 *))v12)(
         manipulationPropertySet,
         string,
         &v22);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_12;
  v13 = manipulationPropertySet->__vftable;
  string = 0;
  v14 = WindowsCreateStringReference(L"CenterPoint", 0xBu, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
    __debugbreak();
  }
  v15 = v13->InsertVector3;
  v22 = 0;
  v23 = 0;
  v5 = ((__int64 (__fastcall *)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING, __int64 *))v15)(
         manipulationPropertySet,
         string,
         &v22);
  v6 = v5;
  if ( v5 < 0 )
  {
LABEL_12:
    OnFailure_2990_(v5);
    return v6;
  }
  else
  {
    v16 = manipulationPropertySet->__vftable;
    string = 0;
    v17 = WindowsCreateStringReference(L"Matrix", 6u, &hstringHeader, &string);
    if ( v17 < 0 )
    {
      RaiseException(v17, 1u, 0, 0);
      __debugbreak();
    }
    InsertMatrix4x4 = v16->InsertMatrix4x4;
    v24[0] = _mm_load_si128((const __m128i *)&_xmm);
    v24[1] = _mm_load_si128((const __m128i *)&_xmm);
    v24[2] = _mm_load_si128((const __m128i *)&_xmm);
    v24[3] = _mm_load_si128((const __m128i *)&_xmm);
    v19 = ((__int64 (__fastcall *)(Windows::UI::Composition::ICompositionPropertySet *, HSTRING, _OWORD *))InsertMatrix4x4)(
            manipulationPropertySet,
            string,
            v24);
    v20 = v19;
    if ( v19 >= 0 )
    {
      return 0;
    }
    else
    {
      OnFailure_2990_(v19);
      return v20;
    }
  }
}

```

## disassembly

```asm
0x1805ec4d4  push    rbp
0x1805ec4d6  push    rbx
0x1805ec4d7  push    rdi
0x1805ec4d8  push    r14
0x1805ec4da  lea     rbp, [rsp-3Fh]
0x1805ec4df  sub     rsp, 0A8h
0x1805ec4e6  mov     rax, cs:__security_cookie
0x1805ec4ed  xor     rax, rsp
0x1805ec4f0  mov     [rbp+57h+var_30], rax
0x1805ec4f4  mov     rdi, [manipulationPropertySet]
0x1805ec4f7  lea     r9, [rbp+57h+string]; string
0x1805ec4fb  xor     r14d, r14d
0x1805ec4fe  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1805ec502  mov     rbx, manipulationPropertySet
0x1805ec505  mov     [rbp+57h+string], r14
0x1805ec509  lea     manipulationPropertySet, aTranslation; "Translation"
0x1805ec510  lea     edx, [r14+0Bh]; length
0x1805ec514  call    cs:__imp_WindowsCreateStringReference
0x1805ec51a  test    eax, eax
0x1805ec51c  js      loc_1805EC6E2
0x1805ec522  mov     rdx, [rbp+57h+string]
0x1805ec526  lea     r8, [rbp+57h+var_A0]
0x1805ec52a  mov     rax, [rdi+60h]
0x1805ec52e  mov     manipulationPropertySet, rbx
0x1805ec531  mov     [rbp+57h+var_A0], r14
0x1805ec535  mov     [rbp+57h+var_98], r14d
0x1805ec539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805ec53e  mov     edi, eax
0x1805ec540  test    eax, eax
0x1805ec542  js      loc_1805EC6D7
0x1805ec548  mov     rdi, [rbx]
0x1805ec54b  lea     r9, [rbp+57h+string]; string
0x1805ec54f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1805ec553  mov     [rbp+57h+string], r14
0x1805ec557  lea     edx, [r14+3]; length
0x1805ec55b  lea     manipulationPropertySet, aPan; "Pan"
0x1805ec562  call    cs:__imp_WindowsCreateStringReference
0x1805ec568  test    eax, eax
0x1805ec56a  js      loc_1805EC6F5
0x1805ec570  mov     rdx, [rbp+57h+string]
0x1805ec574  lea     r8, [rbp+57h+var_A0]
0x1805ec578  mov     rax, [rdi+60h]
0x1805ec57c  mov     manipulationPropertySet, rbx
0x1805ec57f  mov     [rbp+57h+var_A0], r14
0x1805ec583  mov     [rbp+57h+var_98], r14d
0x1805ec587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805ec58c  mov     edi, eax
0x1805ec58e  test    eax, eax
0x1805ec590  js      loc_1805EC75A
0x1805ec596  mov     rdi, [rbx]
0x1805ec599  lea     r9, [rbp+57h+string]; string
0x1805ec59d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1805ec5a1  mov     [rbp+57h+string], r14
0x1805ec5a5  lea     edx, [r14+5]; length
0x1805ec5a9  lea     manipulationPropertySet, aScale; "Scale"
0x1805ec5b0  call    cs:__imp_WindowsCreateStringReference
0x1805ec5b6  test    eax, eax
0x1805ec5b8  js      loc_1805EC708
0x1805ec5be  mov     rdx, [rbp+57h+string]
0x1805ec5c2  lea     r8, [rbp+57h+var_A0]
0x1805ec5c6  mov     rax, [rdi+60h]
0x1805ec5ca  mov     manipulationPropertySet, rbx
0x1805ec5cd  mov     dword ptr [rbp+57h+var_A0], 3F800000h
0x1805ec5d4  mov     dword ptr [rbp+57h+var_A0+4], 3F800000h
0x1805ec5db  mov     [rbp+57h+var_98], 3F800000h
0x1805ec5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805ec5e7  mov     edi, eax
0x1805ec5e9  test    eax, eax
0x1805ec5eb  js      loc_1805EC751
0x1805ec5f1  mov     rdi, [rbx]
0x1805ec5f4  lea     r9, [rbp+57h+string]; string
0x1805ec5f8  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1805ec5fc  mov     [rbp+57h+string], r14
0x1805ec600  lea     edx, [r14+0Bh]; length
0x1805ec604  lea     manipulationPropertySet, aCenterpoint; "CenterPoint"
0x1805ec60b  call    cs:__imp_WindowsCreateStringReference
0x1805ec611  test    eax, eax
0x1805ec613  js      loc_1805EC71B
0x1805ec619  mov     rdx, [rbp+57h+string]
0x1805ec61d  lea     r8, [rbp+57h+var_A0]
0x1805ec621  mov     rax, [rdi+60h]
0x1805ec625  mov     manipulationPropertySet, rbx
0x1805ec628  mov     [rbp+57h+var_A0], r14
0x1805ec62c  mov     [rbp+57h+var_98], r14d
0x1805ec630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805ec635  mov     edi, eax
0x1805ec637  test    eax, eax
0x1805ec639  js      loc_1805EC748
0x1805ec63f  mov     rdi, [rbx]
0x1805ec642  lea     r9, [rbp+57h+string]; string
0x1805ec646  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1805ec64a  mov     [rbp+57h+string], r14
0x1805ec64e  lea     edx, [r14+6]; length
0x1805ec652  lea     manipulationPropertySet, aMatrix; "Matrix"
0x1805ec659  call    cs:__imp_WindowsCreateStringReference
0x1805ec65f  test    eax, eax
0x1805ec661  js      loc_1805EC72E
0x1805ec667  movdqa  xmm0, cs:__xmm@0000000000000000000000003f800000
0x1805ec66f  lea     r8, [rbp+57h+var_90]
0x1805ec673  movdqa  xmm1, cs:__xmm@00000000000000003f80000000000000
0x1805ec67b  mov     manipulationPropertySet, rbx
0x1805ec67e  mov     rdx, [rbp+57h+string]
0x1805ec682  mov     rax, [rdi+40h]
0x1805ec686  movaps  [rbp+57h+var_90], xmm0
0x1805ec68a  movdqa  xmm0, cs:__xmm@000000003f8000000000000000000000
0x1805ec692  movaps  [rbp+57h+var_80], xmm1
0x1805ec696  movdqa  xmm1, cs:__xmm@3f800000000000000000000000000000
0x1805ec69e  movaps  [rbp+57h+var_70], xmm0
0x1805ec6a2  movaps  [rbp+57h+var_60], xmm1
0x1805ec6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805ec6ab  mov     ebx, eax
0x1805ec6ad  test    eax, eax
0x1805ec6af  jns     loc_1805EC741
0x1805ec6b5  mov     ecx, eax; failedFrameHR
0x1805ec6b7  call    OnFailure_2990_
0x1805ec6bc  mov     eax, ebx
0x1805ec6be  mov     manipulationPropertySet, [rbp+57h+var_30]
0x1805ec6c2  xor     manipulationPropertySet, rsp; StackCookie
0x1805ec6c5  call    __security_check_cookie
0x1805ec6ca  add     rsp, 0A8h
0x1805ec6d1  pop     r14
0x1805ec6d3  pop     rdi
0x1805ec6d4  pop     rbx
0x1805ec6d5  pop     rbp
0x1805ec6d6  retn
0x1805ec6d7  mov     ecx, edi; failedFrameHR
0x1805ec6d9  call    OnFailure_2990_
0x1805ec6de  mov     eax, edi
0x1805ec6e0  jmp     short loc_1805EC6BE
0x1805ec6e2  xor     r9d, r9d; lpArguments
0x1805ec6e5  xor     r8d, r8d; nNumberOfArguments
0x1805ec6e8  mov     ecx, eax; dwExceptionCode
0x1805ec6ea  lea     edx, [r9+1]; dwExceptionFlags
0x1805ec6ee  call    cs:__imp_RaiseException
0x1805ec6f4  int     3; Trap to Debugger
0x1805ec6f5  xor     r9d, r9d; lpArguments
0x1805ec6f8  xor     r8d, r8d; nNumberOfArguments
0x1805ec6fb  mov     ecx, eax; dwExceptionCode
0x1805ec6fd  lea     edx, [r9+1]; dwExceptionFlags
0x1805ec701  call    cs:__imp_RaiseException
0x1805ec707  int     3; Trap to Debugger
0x1805ec708  xor     r9d, r9d; lpArguments
0x1805ec70b  xor     r8d, r8d; nNumberOfArguments
0x1805ec70e  mov     ecx, eax; dwExceptionCode
0x1805ec710  lea     edx, [r9+1]; dwExceptionFlags
0x1805ec714  call    cs:__imp_RaiseException
0x1805ec71a  int     3; Trap to Debugger
0x1805ec71b  xor     r9d, r9d; lpArguments
0x1805ec71e  xor     r8d, r8d; nNumberOfArguments
0x1805ec721  mov     ecx, eax; dwExceptionCode
0x1805ec723  lea     edx, [r9+1]; dwExceptionFlags
0x1805ec727  call    cs:__imp_RaiseException
0x1805ec72d  int     3; Trap to Debugger
0x1805ec72e  xor     r9d, r9d; lpArguments
0x1805ec731  xor     r8d, r8d; nNumberOfArguments
0x1805ec734  mov     ecx, eax; dwExceptionCode
0x1805ec736  lea     edx, [r9+1]; dwExceptionFlags
0x1805ec73a  call    cs:__imp_RaiseException
0x1805ec740  int     3; Trap to Debugger
0x1805ec741  xor     eax, eax
0x1805ec743  jmp     loc_1805EC6BE
0x1805ec748  mov     ecx, edi; failedFrameHR
0x1805ec74a  call    OnFailure_2990_
0x1805ec74f  jmp     short loc_1805EC6DE
0x1805ec751  mov     ecx, edi; failedFrameHR
0x1805ec753  call    OnFailure_2990_
0x1805ec758  jmp     short loc_1805EC6DE
0x1805ec75a  mov     ecx, edi; failedFrameHR
0x1805ec75c  call    OnFailure_2990_
0x1805ec761  jmp     loc_1805EC6DE
```
