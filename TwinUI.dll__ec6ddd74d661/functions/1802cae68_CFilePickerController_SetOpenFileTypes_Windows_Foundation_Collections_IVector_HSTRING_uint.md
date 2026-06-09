# CFilePickerController::_SetOpenFileTypes(Windows::Foundation::Collections::IVector<HSTRING__ *> *,uint)

- ea: `0x1802cae68`
- end: `0x1802cb6fc`
- name: `?_SetOpenFileTypes@CFilePickerController@@AEAAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@I@Z`
- size: `2196`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802c82a8`

## callees

- `0x18000e2b0`
- `0x1800308d0`
- `0x1800378dc`
- `0x180041f54`
- `0x180062060`
- `0x1800ad170`
- `0x1800b2c68`
- `0x1800b3f74`
- `0x1800bb088`
- `0x1800f721c`
- `0x1800f7264`
- `0x1800f72b0`
- `0x1802bdae0`
- `0x1802c5ec8`
- `0x1802cae68`
- `0x1803716f4`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802caed9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802caf16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802caf6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb1c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb24f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb2d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb349`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb407`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb49f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb5b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb64f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb6a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802caed9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802caf16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802caf6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb1c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb24f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb2d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb349`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb407`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb49f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb5b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb64f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802cb6a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cb05b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802cb05b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1802cb007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1802cb007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb1a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb2bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb32f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb3ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb68f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb1a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb2bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb32f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb3ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cb68f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CFilePickerController::_SetOpenFileTypes(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // r13
  __int64 v4; // r15
  void *v5; // rcx
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  char *v9; // rsi
  unsigned __int64 v10; // r14
  __int64 v11; // r12
  unsigned int v12; // ecx
  _QWORD *v13; // rdi
  HLOCAL v14; // rbx
  int v15; // eax
  int v16; // r15d
  HRESULT v17; // eax
  int v18; // eax
  PCWSTR StringRawBuffer; // rax
  int v20; // eax
  int v21; // eax
  char *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r12
  __int64 v25; // r15
  bool v26; // zf
  HLOCAL v27; // rax
  __int64 v28; // r12
  unsigned __int64 j; // rdi
  char *v30; // rsi
  unsigned __int64 v31; // rdi
  unsigned __int64 m; // r14
  unsigned __int64 k; // rdi
  unsigned __int64 i; // rdi
  char v35; // dl
  int v36; // eax
  unsigned __int64 n; // rdi
  int v38; // eax
  int v39; // r14d
  char *v40; // rsi
  unsigned __int64 v41; // rdi
  unsigned __int64 ii; // r15
  char *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  int v46; // r12d
  int v47; // eax
  unsigned __int64 jj; // rdi
  int v49; // eax
  unsigned __int64 kk; // rdi
  unsigned __int64 mm; // rdi
  HSTRING string1; // [rsp+20h] [rbp-69h] BYREF
  __int64 v54; // [rsp+28h] [rbp-61h] BYREF
  __int64 v55; // [rsp+30h] [rbp-59h]
  __int64 v56; // [rsp+38h] [rbp-51h]
  HSTRING string2; // [rsp+40h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-41h] BYREF
  int v59; // [rsp+50h] [rbp-39h]
  void *v60; // [rsp+58h] [rbp-31h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-21h] BYREF
  __int64 v63; // [rsp+70h] [rbp-19h]
  __int64 v64; // [rsp+78h] [rbp-11h]
  __int64 v65; // [rsp+80h] [rbp-9h]
  unsigned int v66; // [rsp+88h] [rbp-1h]
  HSTRING newString; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  char v71; // [rsp+100h] [rbp+77h]
  unsigned __int64 v72; // [rsp+108h] [rbp+7Fh] BYREF

  v3 = a3;
  v4 = a2;
  v66 = a3 + 1;
  v60 = 0;
  v72 = 0;
  v6 = ULongLongMult(a3 + 1, 0x10u, &v72);
  if ( v6 < 0 || (v6 = CTCoAllocPolicy::Alloc(v5, 1u, v72, &v60), v6 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BD,
      (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
      (const char *)(unsigned int)v6,
      (int)string1);
    goto LABEL_82;
  }
  hMem = 0;
  LocalFree(0);
  v7 = ConstructStringFromCurrentDll(&hMem, 1051);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C3,
      (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
      (const char *)(unsigned int)v7,
      (int)string1);
    LocalFree(hMem);
LABEL_82:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v60);
    return (unsigned int)v6;
  }
  string1 = 0;
  v8 = Windows::Internal::String::Initialize(&string1, L"*", 1u);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C8,
      (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
      (const char *)(unsigned int)v8,
      (int)string1);
    Windows::Internal::String::~String((Windows::Internal::String *)&string1);
    LocalFree(hMem);
    goto LABEL_82;
  }
  v71 = 0;
  v59 = 0;
  v9 = 0;
  pv = 0;
  v10 = 0;
  v63 = 0;
  v64 = 0;
  v11 = 0;
  v65 = 0;
  v12 = 0;
  v13 = v60;
  v14 = hMem;
  while ( 1 )
  {
    LODWORD(v72) = v12;
    if ( v12 >= (unsigned int)v3 )
      break;
    string2 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v4 + 48LL))(v4, v12, &string2);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CD,
        (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
        (const char *)(unsigned int)v15,
        (int)string1);
      Windows::Internal::String::~String((Windows::Internal::String *)&string2);
      if ( v9 )
      {
        for ( i = 0; i < v10; ++i )
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9[24 * i]);
        CoTaskMemFree(v9);
      }
      goto LABEL_75;
    }
    string = 0;
    if ( (unsigned __int8)Windows::Internal::operator!=(&string1, &string2) )
    {
      newString = 0;
      v17 = WindowsConcatString(string1, string2, &newString);
      v18 = Windows::Internal::String::FreeAndAssignOnSuccess(v17, newString, &string);
      v16 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D4,
          (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
          (const char *)(unsigned int)v18,
          (int)string1);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        Windows::Internal::String::~String((Windows::Internal::String *)&string2);
        if ( v9 )
        {
          for ( j = 0; j < v10; ++j )
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9[24 * j]);
          CoTaskMemFree(v9);
        }
        goto LABEL_75;
      }
    }
    else
    {
      Windows::Internal::String::Initialize(&string, &string1);
      v71 = 1;
      v59 = v72;
    }
    v54 = 0;
    v55 = 0;
    v56 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &v54,
            StringRawBuffer,
            -1);
    v16 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5DE,
        (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
        (const char *)(unsigned int)v20,
        (int)string1);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&string2);
      if ( v9 )
      {
        for ( k = 0; k < v10; ++k )
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9[24 * k]);
        CoTaskMemFree(v9);
      }
      goto LABEL_75;
    }
    if ( v10 == v11 )
    {
      v21 = CTSimpleArray<CPickerController::SHELL_VIEW_CACHE_ENTRY,4294967294,CTPolicyCoTaskMem<CPickerController::SHELL_VIEW_CACHE_ENTRY>,CSimpleArrayStandardCompareHelper<CPickerController::SHELL_VIEW_CACHE_ENTRY>,CSimpleArrayStandardMergeHelper<CPickerController::SHELL_VIEW_CACHE_ENTRY>>::_EnsureCapacity(
              &pv,
              v10 + 1);
      v16 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5DF,
          (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
          (const char *)(unsigned int)v21,
          (int)string1);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        Windows::Internal::String::~String((Windows::Internal::String *)&string2);
        v30 = (char *)pv;
        if ( pv )
        {
          v31 = 0;
          for ( m = v63; v31 < m; ++v31 )
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30[24 * v31]);
          CoTaskMemFree(v30);
        }
LABEL_75:
        Windows::Internal::String::~String((Windows::Internal::String *)&string1);
        LocalFree(v14);
        v6 = v16;
        goto LABEL_82;
      }
      v10 = v63;
      v9 = (char *)pv;
    }
    v63 = ++v10;
    v22 = &v9[24 * v10 - 24];
    if ( v22 )
    {
      *((_QWORD *)v22 + 1) = v55;
      *((_QWORD *)v22 + 2) = v56;
      v23 = v54;
      v54 = 0;
      v56 = 0;
      v55 = 0;
      *(_QWORD *)v22 = v23;
    }
    v24 = (unsigned int)v72;
    v25 = 24LL * (unsigned int)v72;
    v26 = (unsigned __int8)Windows::Internal::operator==(&string1, &string2) == 0;
    v27 = v14;
    if ( v26 )
      v27 = *(HLOCAL *)&v9[v25];
    v28 = 2 * v24;
    v13[v28] = v27;
    v13[v28 + 1] = *(_QWORD *)&v9[v25];
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Windows::Internal::String::~String((Windows::Internal::String *)&string2);
    v12 = v72 + 1;
    v11 = v65;
    v4 = a2;
  }
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v35 = v71;
  if ( v71 )
  {
    v46 = v59;
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
    v55 = -1;
    v56 = -1;
    v36 = FlattenHSTRINGVectorIntoExtensionList(v4, &v54);
    v16 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5ED,
        (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
        (const char *)(unsigned int)v36,
        (int)string1);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
      if ( v9 )
      {
        for ( n = 0; n < v10; ++n )
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9[24 * n]);
        CoTaskMemFree(v9);
      }
      goto LABEL_75;
    }
    if ( v10 == v11 )
    {
      v38 = CTSimpleArray<CPickerController::SHELL_VIEW_CACHE_ENTRY,4294967294,CTPolicyCoTaskMem<CPickerController::SHELL_VIEW_CACHE_ENTRY>,CSimpleArrayStandardCompareHelper<CPickerController::SHELL_VIEW_CACHE_ENTRY>,CSimpleArrayStandardMergeHelper<CPickerController::SHELL_VIEW_CACHE_ENTRY>>::_EnsureCapacity(
              &pv,
              v10 + 1);
      v39 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F3,
          (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
          (const char *)(unsigned int)v38,
          (int)string1);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
        v40 = (char *)pv;
        if ( pv )
        {
          v41 = 0;
          for ( ii = v63; v41 < ii; ++v41 )
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40[24 * v41]);
          CoTaskMemFree(v40);
        }
        Windows::Internal::String::~String((Windows::Internal::String *)&string1);
        LocalFree(v14);
        v6 = v39;
        goto LABEL_82;
      }
      v10 = v63;
      v9 = (char *)pv;
    }
    v63 = ++v10;
    v43 = &v9[24 * v10 - 24];
    if ( v43 )
    {
      *((_QWORD *)v43 + 1) = v55;
      *((_QWORD *)v43 + 2) = v56;
      v44 = v54;
      v54 = 0;
      v56 = 0;
      v55 = 0;
      *(_QWORD *)v43 = v44;
    }
    v45 = 2 * v3;
    v13[v45] = v14;
    v13[v45 + 1] = *(_QWORD *)&v9[24 * v3];
    v46 = v3;
    v35 = 0;
  }
  if ( !v35 )
    LODWORD(v3) = v66;
  v47 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**(_QWORD **)(a1 + 1016) + 32LL))(
          *(_QWORD *)(a1 + 1016),
          (unsigned int)v3,
          v13);
  v16 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5FA,
      (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
      (const char *)(unsigned int)v47,
      (int)string1);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
    if ( v9 )
    {
      for ( jj = 0; jj < v10; ++jj )
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9[24 * jj]);
      CoTaskMemFree(v9);
    }
    goto LABEL_75;
  }
  v49 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 1016) + 40LL))(
          *(_QWORD *)(a1 + 1016),
          (unsigned int)(v46 + 1));
  v16 = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5FD,
      (unsigned int)"shell\\twinui\\picker\\filepickercontroller.cpp",
      (const char *)(unsigned int)v49,
      (int)string1);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
    if ( v9 )
    {
      for ( kk = 0; kk < v10; ++kk )
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9[24 * kk]);
      CoTaskMemFree(v9);
    }
    goto LABEL_75;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v54);
  if ( v9 )
  {
    for ( mm = 0; mm < v10; ++mm )
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v9[24 * mm]);
    CoTaskMemFree(v9);
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&string1);
  LocalFree(v14);
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v60);
  return 0;
}

```

## disassembly

```asm
0x1802cae68  mov     [rsp-8+arg_8], rdx
0x1802cae6d  mov     [rsp-8+arg_0], rcx
0x1802cae72  push    rbp
0x1802cae73  push    rbx
0x1802cae74  push    rsi
0x1802cae75  push    rdi
0x1802cae76  push    r12
0x1802cae78  push    r13
0x1802cae7a  push    r14
0x1802cae7c  push    r15
0x1802cae7e  lea     rbp, [rsp-1Fh]
0x1802cae83  sub     rsp, 0A8h
0x1802cae8a  mov     r13d, r8d
0x1802cae8d  mov     r15, rdx
0x1802cae90  lea     eax, [r13+1]
0x1802cae94  mov     [rbp+57h+var_58], eax
0x1802cae97  xor     edi, edi
0x1802cae99  mov     [rbp+57h+var_88], rdi
0x1802cae9d  mov     [rbp+57h+arg_18], rdi
0x1802caea1  mov     ecx, eax; unsigned __int64
0x1802caea3  lea     r8, [rbp+57h+arg_18]; unsigned __int64 *
0x1802caea7  lea     edx, [rdi+10h]; unsigned __int64
0x1802caeaa  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1802caeaf  mov     ebx, eax
0x1802caeb1  test    eax, eax
0x1802caeb3  js      loc_1802CB6C3
0x1802caeb9  lea     r9, [rbp+57h+var_88]; void **
0x1802caebd  mov     r8, [rbp+57h+arg_18]; unsigned __int64
0x1802caec1  lea     edx, [rdi+1]; unsigned int
0x1802caec4  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1802caec9  mov     ebx, eax
0x1802caecb  test    eax, eax
0x1802caecd  js      loc_1802CB6C3
0x1802caed3  mov     [rbp+57h+hMem], rdi
0x1802caed7  xor     ecx, ecx; hMem
0x1802caed9  call    cs:__imp_LocalFree
0x1802caee0  nop     dword ptr [rax+rax+00h]
0x1802caee5  mov     edx, 41Bh
0x1802caeea  lea     rcx, [rbp+57h+hMem]
0x1802caeee  call    ConstructStringFromCurrentDll
0x1802caef3  mov     ebx, eax
0x1802caef5  test    eax, eax
0x1802caef7  jns     short loc_1802CAF28
0x1802caef9  mov     rcx, [rbp+5Fh]; this
0x1802caefd  mov     r9d, eax; char *
0x1802caf00  lea     r8, aShellTwinuiPic_3; "shell\\twinui\\picker\\filepickercontro"...
0x1802caf07  mov     edx, 5C3h; void *
0x1802caf0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802caf11  nop
0x1802caf12  mov     rcx, [rbp+57h+hMem]; hMem
0x1802caf16  call    cs:__imp_LocalFree
0x1802caf1d  nop     dword ptr [rax+rax+00h]
0x1802caf22  nop
0x1802caf23  jmp     loc_1802CB6DC
0x1802caf28  mov     [rbp+57h+string1], rdi
0x1802caf2c  mov     r8d, 1; length
0x1802caf32  lea     rdx, asc_180414808; "*"
0x1802caf39  lea     rcx, [rbp+57h+string1]; this
0x1802caf3d  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x1802caf42  mov     ebx, eax
0x1802caf44  test    eax, eax
0x1802caf46  jns     short loc_1802CAF81
0x1802caf48  mov     rcx, [rbp+5Fh]; this
0x1802caf4c  mov     r9d, eax; char *
0x1802caf4f  lea     r8, aShellTwinuiPic_3; "shell\\twinui\\picker\\filepickercontro"...
0x1802caf56  mov     edx, 5C8h; void *
0x1802caf5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802caf60  nop
0x1802caf61  lea     rcx, [rbp+57h+string1]; this
0x1802caf65  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802caf6a  nop
0x1802caf6b  mov     rcx, [rbp+57h+hMem]; hMem
0x1802caf6f  call    cs:__imp_LocalFree
0x1802caf76  nop     dword ptr [rax+rax+00h]
0x1802caf7b  nop
0x1802caf7c  jmp     loc_1802CB6DC
0x1802caf81  mov     [rbp+57h+arg_10], dil
0x1802caf85  mov     [rbp+57h+var_90], edi
0x1802caf88  mov     rsi, rdi
0x1802caf8b  mov     [rbp+57h+pv], rdi
0x1802caf8f  mov     r14, rdi
0x1802caf92  mov     [rbp+57h+var_70], rdi
0x1802caf96  mov     [rbp+57h+var_68], rdi
0x1802caf9a  mov     r12, rdi
0x1802caf9d  mov     [rbp+57h+var_60], rdi
0x1802cafa1  mov     ecx, edi
0x1802cafa3  mov     rdi, [rbp+57h+var_88]
0x1802cafa7  mov     rbx, [rbp+57h+hMem]
0x1802cafab  mov     dword ptr [rbp+57h+arg_18], ecx
0x1802cafae  cmp     ecx, r13d
0x1802cafb1  jnb     loc_1802CB35B
0x1802cafb7  mov     [rbp+57h+string2], 0
0x1802cafbf  mov     rax, [r15]
0x1802cafc2  lea     r8, [rbp+57h+string2]
0x1802cafc6  mov     edx, ecx
0x1802cafc8  mov     rcx, r15
0x1802cafcb  mov     rax, [rax+30h]
0x1802cafcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802cafd4  mov     r15d, eax
0x1802cafd7  test    eax, eax
0x1802cafd9  js      loc_1802CB2E8
0x1802cafdf  xor     r15d, r15d
0x1802cafe2  mov     [rbp+57h+string], r15
0x1802cafe6  lea     rdx, [rbp+57h+string2]
0x1802cafea  lea     rcx, [rbp+57h+string1]
0x1802cafee  call    ??9Internal@Windows@@YA_NAEBVString@01@0@Z; Windows::Internal::operator!=(Windows::Internal::String const &,Windows::Internal::String const &)
0x1802caff3  test    al, al
0x1802caff5  jz      short loc_1802CB032
0x1802caff7  mov     [rbp+57h+newString], r15
0x1802caffb  lea     r8, [rbp+57h+newString]; newString
0x1802cafff  mov     rdx, [rbp+57h+string2]; string2
0x1802cb003  mov     rcx, [rbp+57h+string1]; string1
0x1802cb007  call    cs:__imp_WindowsConcatString
0x1802cb00e  nop     dword ptr [rax+rax+00h]
0x1802cb013  lea     r8, [rbp+57h+string]; HSTRING *
0x1802cb017  mov     rdx, [rbp+57h+newString]; HSTRING
0x1802cb01b  mov     ecx, eax; int
0x1802cb01d  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x1802cb022  mov     r15d, eax
0x1802cb025  test    eax, eax
0x1802cb027  js      loc_1802CB155
0x1802cb02d  xor     r15d, r15d
0x1802cb030  jmp     short loc_1802CB049
0x1802cb032  lea     rdx, [rbp+57h+string1]; HSTRING *
0x1802cb036  lea     rcx, [rbp+57h+string]; this
0x1802cb03a  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x1802cb03f  mov     [rbp+57h+arg_10], 1
0x1802cb043  mov     eax, dword ptr [rbp+57h+arg_18]
0x1802cb046  mov     [rbp+57h+var_90], eax
0x1802cb049  mov     [rbp+57h+var_B8], r15
0x1802cb04d  mov     [rbp+57h+var_B0], r15
0x1802cb051  mov     [rbp+57h+var_A8], r15
0x1802cb055  xor     edx, edx; length
0x1802cb057  mov     rcx, [rbp+57h+string]; string
0x1802cb05b  call    cs:__imp_WindowsGetStringRawBuffer
0x1802cb062  nop     dword ptr [rax+rax+00h]
0x1802cb067  or      r8, 0FFFFFFFFFFFFFFFFh
0x1802cb06b  mov     rdx, rax
0x1802cb06e  lea     rcx, [rbp+57h+var_B8]
0x1802cb072  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1802cb077  mov     r15d, eax
0x1802cb07a  test    eax, eax
0x1802cb07c  js      loc_1802CB261
0x1802cb082  cmp     r14, r12
0x1802cb085  jnz     short loc_1802CB0A7
0x1802cb087  lea     rdx, [r14+1]
0x1802cb08b  lea     rcx, [rbp+57h+pv]
0x1802cb08f  call    ?_EnsureCapacity@?$CTSimpleArray@USHELL_VIEW_CACHE_ENTRY@CPickerController@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@USHELL_VIEW_CACHE_ENTRY@CPickerController@@@@V?$CSimpleArrayStandardCompareHelper@USHELL_VIEW_CACHE_ENTRY@CPickerController@@@@V?$CSimpleArrayStandardMergeHelper@USHELL_VIEW_CACHE_ENTRY@CPickerController@@@@@@QEAAJ_K0@Z; CTSimpleArray<CPickerController::SHELL_VIEW_CACHE_ENTRY,4294967294,CTPolicyCoTaskMem<CPickerController::SHELL_VIEW_CACHE_ENTRY>,CSimpleArrayStandardCompareHelper<CPickerController::SHELL_VIEW_CACHE_ENTRY>,CSimpleArrayStandardMergeHelper<CPickerController::SHELL_VIEW_CACHE_ENTRY>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1802cb094  mov     r15d, eax
0x1802cb097  test    eax, eax
0x1802cb099  js      loc_1802CB1D2
0x1802cb09f  mov     r14, [rbp+57h+var_70]
0x1802cb0a3  mov     rsi, [rbp+57h+pv]
0x1802cb0a7  inc     r14
0x1802cb0aa  mov     [rbp+57h+var_70], r14
0x1802cb0ae  lea     rcx, [r14-1]
0x1802cb0b2  lea     rcx, [rcx+rcx*2]
0x1802cb0b6  lea     rcx, [rsi+rcx*8]
0x1802cb0ba  test    rcx, rcx
0x1802cb0bd  jz      short loc_1802CB0EE
0x1802cb0bf  mov     rax, [rbp+57h+var_B0]
0x1802cb0c3  mov     [rcx+8], rax
0x1802cb0c7  mov     rax, [rbp+57h+var_A8]
0x1802cb0cb  mov     [rcx+10h], rax
0x1802cb0cf  mov     rax, [rbp+57h+var_B8]
0x1802cb0d3  mov     [rbp+57h+var_B8], 0
0x1802cb0db  mov     [rbp+57h+var_A8], 0
0x1802cb0e3  mov     [rbp+57h+var_B0], 0
0x1802cb0eb  mov     [rcx], rax
0x1802cb0ee  mov     r12d, dword ptr [rbp+57h+arg_18]
0x1802cb0f2  lea     rax, [r12+r12*2]
0x1802cb0f6  lea     r15, ds:0[rax*8]
0x1802cb0fe  lea     rdx, [rbp+57h+string2]
0x1802cb102  lea     rcx, [rbp+57h+string1]
0x1802cb106  call    ??8Internal@Windows@@YA_NAEBVString@01@0@Z; Windows::Internal::operator==(Windows::Internal::String const &,Windows::Internal::String const &)
0x1802cb10b  test    al, al
0x1802cb10d  mov     rax, rbx
0x1802cb110  jnz     short loc_1802CB116
0x1802cb112  mov     rax, [r15+rsi]
0x1802cb116  add     r12, r12
0x1802cb119  mov     [rdi+r12*8], rax
0x1802cb11d  mov     rax, [r15+rsi]
0x1802cb121  mov     [rdi+r12*8+8], rax
0x1802cb126  lea     rcx, [rbp+57h+var_B8]
0x1802cb12a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802cb12f  nop
0x1802cb130  lea     rcx, [rbp+57h+string]; this
0x1802cb134  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb139  nop
0x1802cb13a  lea     rcx, [rbp+57h+string2]; this
0x1802cb13e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb143  mov     ecx, dword ptr [rbp+57h+arg_18]
0x1802cb146  inc     ecx
0x1802cb148  mov     r12, [rbp+57h+var_60]
0x1802cb14c  mov     r15, [rbp+57h+arg_8]
0x1802cb150  jmp     loc_1802CAFAB
0x1802cb155  mov     rcx, [rbp+5Fh]; this
0x1802cb159  mov     r9d, r15d; char *
0x1802cb15c  lea     r8, aShellTwinuiPic_3; "shell\\twinui\\picker\\filepickercontro"...
0x1802cb163  mov     edx, 5D4h; void *
0x1802cb168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cb16d  nop
0x1802cb16e  lea     rcx, [rbp+57h+string]; this
0x1802cb172  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb177  nop
0x1802cb178  lea     rcx, [rbp+57h+string2]; this
0x1802cb17c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb181  nop
0x1802cb182  test    rsi, rsi
0x1802cb185  jz      short loc_1802CB1B3
0x1802cb187  xor     edi, edi
0x1802cb189  test    r14, r14
0x1802cb18c  jz      short loc_1802CB1A3
0x1802cb18e  lea     rax, [rdi+rdi*2]
0x1802cb192  lea     rcx, [rsi+rax*8]
0x1802cb196  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802cb19b  inc     rdi
0x1802cb19e  cmp     rdi, r14
0x1802cb1a1  jb      short loc_1802CB18E
0x1802cb1a3  mov     rcx, rsi; pv
0x1802cb1a6  call    cs:__imp_CoTaskMemFree
0x1802cb1ad  nop     dword ptr [rax+rax+00h]
0x1802cb1b2  nop
0x1802cb1b3  lea     rcx, [rbp+57h+string1]; this
0x1802cb1b7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb1bc  nop
0x1802cb1bd  mov     rcx, rbx; hMem
0x1802cb1c0  call    cs:__imp_LocalFree
0x1802cb1c7  nop     dword ptr [rax+rax+00h]
0x1802cb1cc  nop
0x1802cb1cd  jmp     loc_1802CB65C
0x1802cb1d2  mov     rcx, [rbp+5Fh]; this
0x1802cb1d6  mov     r9d, r15d; char *
0x1802cb1d9  lea     r8, aShellTwinuiPic_3; "shell\\twinui\\picker\\filepickercontro"...
0x1802cb1e0  mov     edx, 5DFh; void *
0x1802cb1e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cb1ea  nop
0x1802cb1eb  lea     rcx, [rbp+57h+var_B8]
0x1802cb1ef  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802cb1f4  nop
0x1802cb1f5  lea     rcx, [rbp+57h+string]; this
0x1802cb1f9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb1fe  nop
0x1802cb1ff  lea     rcx, [rbp+57h+string2]; this
0x1802cb203  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb208  nop
0x1802cb209  mov     rsi, [rbp+57h+pv]
0x1802cb20d  test    rsi, rsi
0x1802cb210  jz      short loc_1802CB242
0x1802cb212  xor     edi, edi
0x1802cb214  mov     r14, [rbp+57h+var_70]
0x1802cb218  test    r14, r14
0x1802cb21b  jz      short loc_1802CB232
0x1802cb21d  lea     rax, [rdi+rdi*2]
0x1802cb221  lea     rcx, [rsi+rax*8]
0x1802cb225  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802cb22a  inc     rdi
0x1802cb22d  cmp     rdi, r14
0x1802cb230  jb      short loc_1802CB21D
0x1802cb232  mov     rcx, rsi; pv
0x1802cb235  call    cs:__imp_CoTaskMemFree
0x1802cb23c  nop     dword ptr [rax+rax+00h]
0x1802cb241  nop
0x1802cb242  lea     rcx, [rbp+57h+string1]; this
0x1802cb246  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb24b  nop
0x1802cb24c  mov     rcx, rbx; hMem
0x1802cb24f  call    cs:__imp_LocalFree
0x1802cb256  nop     dword ptr [rax+rax+00h]
0x1802cb25b  nop
0x1802cb25c  jmp     loc_1802CB65C
0x1802cb261  mov     rcx, [rbp+5Fh]; this
0x1802cb265  mov     r9d, r15d; char *
0x1802cb268  lea     r8, aShellTwinuiPic_3; "shell\\twinui\\picker\\filepickercontro"...
0x1802cb26f  mov     edx, 5DEh; void *
0x1802cb274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cb279  nop
0x1802cb27a  lea     rcx, [rbp+57h+var_B8]
0x1802cb27e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802cb283  nop
0x1802cb284  lea     rcx, [rbp+57h+string]; this
0x1802cb288  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb28d  nop
0x1802cb28e  lea     rcx, [rbp+57h+string2]; this
0x1802cb292  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802cb297  nop
0x1802cb298  test    rsi, rsi
0x1802cb29b  jz      short loc_1802CB2C9
0x1802cb29d  xor     edi, edi
0x1802cb29f  test    r14, r14
0x1802cb2a2  jz      short loc_1802CB2B9
0x1802cb2a4  lea     rax, [rdi+rdi*2]
0x1802cb2a8  lea     rcx, [rsi+rax*8]
0x1802cb2ac  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802cb2b1  inc     rdi
0x1802cb2b4  cmp     rdi, r14
0x1802cb2b7  jb      short loc_1802CB2A4
0x1802cb2b9  mov     rcx, rsi; pv
0x1802cb2bc  call    cs:__imp_CoTaskMemFree
0x1802cb2c3  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
