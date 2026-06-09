# Windows::ApplicationModel::Resources::Core::CResourceCandidate::GetValueAsFileAsync(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> * *)

- ea: `0x1800842e0`
- end: `0x1800844f0`
- name: `?GetValueAsFileAsync@CResourceCandidate@Core@Resources@ApplicationModel@Windows@@UEAAJPEAPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@5@@Z`
- size: `528`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x18002c8d0`
- `0x18003ac44`
- `0x180054824`
- `0x1800842e0`
- `0x1800862f0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800843dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800844be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800843dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800844be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800843ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800844cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800843ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800844cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084383`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180084383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008436c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008436c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800843a5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800843a5`

## string_xrefs

- `0x180084338`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecandidate.cpp`
- `0x1800843b8`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecandidate.cpp`
- `0x180084440`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecandidate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceCandidate::GetValueAsFileAsync(
        __int64 a1,
        _QWORD *a2)
{
  int ValueStringByType; // eax
  unsigned int v4; // ebx
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  unsigned int v8; // edi
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  void *v17; // rbx
  HANDLE v18; // rax
  int v19; // [rsp+20h] [rbp-50h] BYREF
  __int64 v20; // [rsp+28h] [rbp-48h] BYREF
  __int64 v21; // [rsp+30h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a2 = 0;
  lpMem = 0;
  LOBYTE(v19) = 0;
  ValueStringByType = Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetValueStringByType(
                        *(_QWORD *)(a1 + 80),
                        1u,
                        (const unsigned __int16 **)&lpMem,
                        (bool *)&v19);
  v4 = ValueStringByType;
  if ( ValueStringByType < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecandidate.cpp",
      (const char *)(unsigned int)ValueStringByType,
      v19);
    return v4;
  }
  v21 = 0;
  if ( WindowsCreateStringReference(L"Windows.Storage.StorageFile", 0x1Bu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v21);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f, &v21);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecandidate.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v21);
LABEL_7:
    if ( (_BYTE)v19 )
    {
      v9 = lpMem;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
    return v8;
  }
  v20 = 0;
  v11 = v21;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v21 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v20);
  Windows::Internal::StringReference::_ConstructorHelper(&string, (PCWSTR)lpMem);
  v13 = v12(v11, string, &v20);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecandidate.cpp",
      (const char *)(unsigned int)v13,
      v19);
    v14 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_7;
  }
  v16 = v20;
  v20 = 0;
  *a2 = v16;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v21);
  if ( (_BYTE)v19 )
  {
    v17 = lpMem;
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v17);
  }
  return 0;
}

```

## disassembly

```asm
0x1800842e0  mov     [rsp-18h+arg_10], rbx
0x1800842e5  push    rbp
0x1800842e6  push    rsi
0x1800842e7  push    rdi
0x1800842e8  mov     rbp, rsp
0x1800842eb  sub     rsp, 70h
0x1800842ef  mov     rax, cs:__security_cookie
0x1800842f6  xor     rax, rsp
0x1800842f9  mov     [rbp+var_10], rax
0x1800842fd  mov     rsi, rdx
0x180084300  mov     qword ptr [rdx], 0
0x180084307  mov     [rbp+lpMem], 0
0x18008430f  mov     byte ptr [rbp+var_50], 0
0x180084313  lea     r9, [rbp+var_50]
0x180084317  lea     r8, [rbp+lpMem]
0x18008431b  mov     edi, 1
0x180084320  mov     edx, edi
0x180084322  mov     rcx, [rcx+50h]
0x180084326  call    ?GetValueStringByType@CResolvedInstanceInternal@Runtime@Resources@Microsoft@@QEBAJW4ResourceValueType@MrmEnvironment@34@PEAPEBGPEA_N@Z; Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetValueStringByType(Microsoft::Resources::MrmEnvironment::ResourceValueType,ushort const * *,bool *)
0x18008432b  mov     ebx, eax
0x18008432d  test    eax, eax
0x18008432f  jns     short loc_180084350
0x180084331  mov     rcx, [rbp+18h]; this
0x180084335  mov     r9d, eax; char *
0x180084338  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18008433f  mov     edx, 0ACh; void *
0x180084344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084349  mov     eax, ebx
0x18008434b  jmp     loc_1800844D4
0x180084350  mov     [rbp+var_40], 0
0x180084358  lea     r9, [rbp+string]; string
0x18008435c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180084360  mov     edx, 1Bh; length
0x180084365  lea     rcx, ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x18008436c  call    cs:__imp_WindowsCreateStringReference
0x180084372  test    eax, eax
0x180084374  jns     short loc_18008438A
0x180084376  xor     r9d, r9d; lpArguments
0x180084379  xor     r8d, r8d; nNumberOfArguments
0x18008437c  mov     edx, edi; dwExceptionFlags
0x18008437e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180084383  call    cs:__imp_RaiseException
0x180084389  nop
0x18008438a  mov     rbx, [rbp+string]
0x18008438e  lea     rcx, [rbp+var_40]
0x180084392  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180084397  lea     r8, [rbp+var_40]
0x18008439b  lea     rdx, _GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f
0x1800843a2  mov     rcx, rbx
0x1800843a5  call    cs:__imp_RoGetActivationFactory
0x1800843ab  mov     edi, eax
0x1800843ad  test    eax, eax
0x1800843af  jns     short loc_1800843F7
0x1800843b1  mov     rcx, [rbp+18h]; this
0x1800843b5  mov     r9d, eax; char *
0x1800843b8  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800843bf  mov     edx, 0B7h; void *
0x1800843c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800843c9  lea     rcx, [rbp+var_40]
0x1800843cd  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800843d2  cmp     byte ptr [rbp+var_50], 0
0x1800843d6  jz      short loc_1800843F0
0x1800843d8  mov     rbx, [rbp+lpMem]
0x1800843dc  call    cs:__imp_GetProcessHeap
0x1800843e2  mov     r8, rbx; lpMem
0x1800843e5  xor     edx, edx; dwFlags
0x1800843e7  mov     rcx, rax; hHeap
0x1800843ea  call    cs:__imp_HeapFree
0x1800843f0  mov     eax, edi
0x1800843f2  jmp     loc_1800844D4
0x1800843f7  mov     [rbp+var_48], 0
0x1800843ff  mov     rdi, [rbp+var_40]
0x180084403  mov     rax, [rdi]
0x180084406  mov     rbx, [rax+30h]
0x18008440a  lea     rcx, [rbp+var_48]
0x18008440e  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180084413  mov     rdx, [rbp+lpMem]; sourceString
0x180084417  lea     rcx, [rbp+string]; string
0x18008441b  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180084420  lea     r8, [rbp+var_48]
0x180084424  mov     rdx, [rbp+string]
0x180084428  mov     rcx, rdi
0x18008442b  mov     rax, rbx
0x18008442e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084433  mov     edi, eax
0x180084435  test    eax, eax
0x180084437  jns     short loc_180084493
0x180084439  mov     rcx, [rbp+18h]; this
0x18008443d  mov     r9d, eax; char *
0x180084440  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180084447  mov     edx, 0BAh; void *
0x18008444c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084451  nop
0x180084452  mov     rcx, [rbp+var_48]
0x180084456  test    rcx, rcx
0x180084459  jz      short loc_180084470
0x18008445b  mov     [rbp+var_48], 0
0x180084463  mov     rax, [rcx]
0x180084466  mov     rax, [rax+10h]
0x18008446a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008446f  nop
0x180084470  mov     rcx, [rbp+var_40]
0x180084474  test    rcx, rcx
0x180084477  jz      short loc_18008448E
0x180084479  mov     [rbp+var_40], 0
0x180084481  mov     rax, [rcx]
0x180084484  mov     rax, [rax+10h]
0x180084488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008448d  nop
0x18008448e  jmp     loc_1800843D2
0x180084493  mov     rax, [rbp+var_48]
0x180084497  mov     [rbp+var_48], 0
0x18008449f  mov     [rsi], rax
0x1800844a2  lea     rcx, [rbp+var_48]
0x1800844a6  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800844ab  lea     rcx, [rbp+var_40]
0x1800844af  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800844b4  cmp     byte ptr [rbp+var_50], 0
0x1800844b8  jz      short loc_1800844D2
0x1800844ba  mov     rbx, [rbp+lpMem]
0x1800844be  call    cs:__imp_GetProcessHeap
0x1800844c4  mov     r8, rbx; lpMem
0x1800844c7  xor     edx, edx; dwFlags
0x1800844c9  mov     rcx, rax; hHeap
0x1800844cc  call    cs:__imp_HeapFree
0x1800844d2  xor     eax, eax
0x1800844d4  mov     rcx, [rbp+var_10]
0x1800844d8  xor     rcx, rsp; StackCookie
0x1800844db  call    __security_check_cookie
0x1800844e0  mov     rbx, [rsp+70h+arg_10]
0x1800844e8  add     rsp, 70h
0x1800844ec  pop     rdi
0x1800844ed  pop     rsi
0x1800844ee  pop     rbp
0x1800844ef  retn
```
