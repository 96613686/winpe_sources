# CShtOle::LoadMssearchExcludedExtensions(void)

- ea: `0x1800f0d2c`
- end: `0x1800f119c`
- name: `?LoadMssearchExcludedExtensions@CShtOle@@AEAAJXZ`
- size: `1136`
- prototype: `__int64 __fastcall(CShtOle *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f0c94`

## callees

- `0x1800601c0`
- `0x180096bac`
- `0x1800f0d2c`
- `0x1800f7bfc`
- `0x18010ed78`
- `0x18016c928`
- `0x180188d90`
- `0x18018a0f9`
- `0x1801fe624`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f0df1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f0df1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f0d7e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f0d7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f0dd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f0dd3`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800f0e18`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800f0e18`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f0eb5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f0f80`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f10f3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f0eb5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f0f80`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f10f3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800f10b1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800f10b1`

## string_xrefs

- `0x1800f0d9f`: `SOFTWARE\Microsoft\Windows Search\Gather\Windows\SystemIndex\Extensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CShtOle::LoadMssearchExcludedExtensions(CShtOle *this)
{
  HANDLE *v2; // rbx
  HKEY *v4; // rdi
  bool v5; // al
  wchar_t *v6; // rdx
  HANDLE EventW; // rax
  HRESULT Instance_0; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v10; // rax
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v13; // rax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  char *v17; // r14
  __int64 v18; // r8
  UINT v19; // r15d
  UINT i; // edi
  OLECHAR *v21; // rsi
  __int64 v22; // rax
  __int16 v23; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h] BYREF
  LPVOID ppv[2]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v36[264]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = (HANDLE *)((char *)this + 176);
  if ( *((_DWORD *)this + 40) && (!*v2 || WaitForSingleObject(*v2, 0)) )
    return 0;
  v4 = (HKEY *)((char *)this + 168);
  if ( !*((_QWORD *)this + 21) )
  {
    v5 = MapRegistryKeyPath(
           (const wchar_t *)this,
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows Search\\Gather\\Windows\\SystemIndex\\Extensions",
           v36);
    v6 = v36;
    if ( !v5 )
      v6 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search\\Gather\\Windows\\SystemIndex\\Extensions";
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x10u, (PHKEY)this + 21);
  }
  EventW = *v2;
  if ( *v2 || (EventW = CreateEventW(0, 0, 0, 0), (*v2 = EventW) != 0) )
  {
    if ( *v4 )
      RegNotifyChangeKeyValue(*v4, 1, 5u, EventW, 1);
  }
  ppv[0] = 0;
  Instance_0 = CoCreateInstance_0(
                 &GUID_9e175b68_f52a_11d8_b9a5_505054503030,
                 0,
                 0x15u,
                 &GUID_5480f00f_4b80_4deb_ae21_50521db448ed,
                 ppv);
  v34 = 0;
  if ( Instance_0 >= 0 )
    Instance_0 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv[0] + 56LL))(ppv[0], &v34);
  v9 = 0;
  v27 = 0;
  if ( Instance_0 >= 0 )
  {
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Windows");
    Instance_0 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD *))(*(_QWORD *)v34 + 64LL))(v34, bstrString, &v27);
    if ( Instance_0 == 1 && !v27 )
      Instance_0 = -2147467259;
    SysFreeString(bstrString);
    v9 = v27;
  }
  v10 = 0;
  v33 = 0;
  if ( Instance_0 >= 0 )
  {
    Instance_0 = (**v9)(v9, &GUID_b1d80e6f_8302_46bc_8905_e151c3e0a207, &v33);
    v10 = v33;
  }
  v11 = 0;
  v32 = 0;
  if ( Instance_0 >= 0 )
  {
    Instance_0 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v10 + 64LL))(
                   v10,
                   &v32);
    v11 = v32;
  }
  v31 = 0;
  if ( Instance_0 >= 0 )
    Instance_0 = (**v11)(v11, &GUID_b05651ea_9b10_425e_b616_1fcd828db3b1, &v31);
  v12 = 0;
  v26 = 0;
  if ( Instance_0 >= 0 )
  {
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SystemIndex");
    Instance_0 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD *))(*(_QWORD *)v31 + 64LL))(v31, bstrString, &v26);
    if ( Instance_0 == 1 && !v26 )
      Instance_0 = -2147467259;
    SysFreeString(bstrString);
    v12 = v26;
  }
  v13 = 0;
  v30 = 0;
  if ( Instance_0 >= 0 )
  {
    Instance_0 = (**v12)(v12, &GUID_9d23d738_e1c6_4cb0_b0a4_866f5a352be7, &v30);
    v13 = v30;
  }
  v14 = 0;
  v29 = 0;
  if ( Instance_0 >= 0 )
  {
    Instance_0 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v13 + 64LL))(
                   v13,
                   &v29);
    v14 = v29;
  }
  v15 = 0;
  v28 = 0;
  if ( Instance_0 >= 0 )
  {
    Instance_0 = (**v14)(v14, &GUID_fce7ec00_38e9_4837_9f8c_a0313215b86f, &v28);
    v15 = v28;
  }
  v16 = 0;
  v25 = 0;
  if ( Instance_0 >= 0 )
  {
    Instance_0 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 96LL))(v15, &v25);
    v16 = v25;
  }
  v23 = 0;
  if ( Instance_0 >= 0 )
  {
    Instance_0 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v16 + 96LL))(v16, &v23);
    if ( Instance_0 >= 0 && !v23 )
    {
      bstrString = 0;
      Instance_0 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 112LL))(v25, &bstrString);
      if ( Instance_0 >= 0 )
      {
        v17 = (char *)this + 88;
        ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,int,ATL::CStringElementTraitsI<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CDefaultCharTraits<wchar_t>>,ATL::CElementTraits<int>>::RemoveAll((char *)this + 88);
        LOBYTE(v18) = 1;
        ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,int,ATL::CStringElementTraitsI<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CDefaultCharTraits<wchar_t>>,ATL::CElementTraits<int>>::InitHashTable(
          (char *)this + 88,
          257,
          v18);
        *((_DWORD *)this + 40) = 1;
        v19 = SysStringLen(bstrString);
        for ( i = 0; i < v19; i += v22 + 1 )
        {
          v21 = &bstrString[i];
          ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,int,ATL::CStringElementTraitsI<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CDefaultCharTraits<wchar_t>>,ATL::CElementTraits<int>>::SetAt(
            v17,
            v21);
          v22 = -1;
          do
            ++v22;
          while ( v21[v22] );
        }
      }
      SysFreeString(bstrString);
    }
  }
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v25);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v28);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v29);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v30);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v26);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v31);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v32);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v33);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v27);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(&v34);
  ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(ppv);
  return (unsigned int)Instance_0;
}

```

## disassembly

```asm
0x1800f0d2c  mov     [rsp-8+arg_8], rbx
0x1800f0d31  mov     [rsp-8+arg_10], rsi
0x1800f0d36  push    rbp
0x1800f0d37  push    rdi
0x1800f0d38  push    r12
0x1800f0d3a  push    r14
0x1800f0d3c  push    r15
0x1800f0d3e  lea     rbp, [rsp-1C0h]
0x1800f0d46  sub     rsp, 2C0h
0x1800f0d4d  mov     rax, cs:__security_cookie
0x1800f0d54  xor     rax, rsp
0x1800f0d57  mov     [rbp+1E0h+var_30], rax
0x1800f0d5e  mov     rsi, rcx
0x1800f0d61  lea     rbx, [rcx+0B0h]
0x1800f0d68  xor     r12d, r12d
0x1800f0d6b  cmp     [rcx+0A0h], r12d
0x1800f0d72  jz      short loc_1800F0D8F
0x1800f0d74  mov     rcx, [rbx]; hHandle
0x1800f0d77  test    rcx, rcx
0x1800f0d7a  jz      short loc_1800F0D88
0x1800f0d7c  xor     edx, edx; dwMilliseconds
0x1800f0d7e  call    cs:__imp_WaitForSingleObject
0x1800f0d84  test    eax, eax
0x1800f0d86  jz      short loc_1800F0D8F
0x1800f0d88  xor     eax, eax
0x1800f0d8a  jmp     loc_1800F1171
0x1800f0d8f  lea     rdi, [rsi+0A8h]
0x1800f0d96  cmp     [rdi], r12
0x1800f0d99  jnz     short loc_1800F0DD9
0x1800f0d9b  lea     r9, [rbp+1E0h+var_240]; wchar_t *
0x1800f0d9f  lea     r14, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows Search\\Ga"...
0x1800f0da6  mov     r8, r14; wchar_t *
0x1800f0da9  mov     r15, 0FFFFFFFF80000002h
0x1800f0db0  mov     rdx, r15; HKEY
0x1800f0db3  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x1800f0db8  lea     rdx, [rbp+1E0h+var_240]
0x1800f0dbc  test    al, al
0x1800f0dbe  cmovz   rdx, r14; lpSubKey
0x1800f0dc2  mov     [rsp+2E0h+phkResult], rdi; phkResult
0x1800f0dc7  mov     r9d, 10h; samDesired
0x1800f0dcd  xor     r8d, r8d; ulOptions
0x1800f0dd0  mov     rcx, r15; hKey
0x1800f0dd3  call    cs:__imp_RegOpenKeyExW
0x1800f0dd9  mov     rax, [rbx]
0x1800f0ddc  mov     r15d, 1
0x1800f0de2  test    rax, rax
0x1800f0de5  jnz     short loc_1800F0DFF
0x1800f0de7  xor     r9d, r9d; lpName
0x1800f0dea  xor     r8d, r8d; bInitialState
0x1800f0ded  xor     edx, edx; bManualReset
0x1800f0def  xor     ecx, ecx; lpEventAttributes
0x1800f0df1  call    cs:__imp_CreateEventW
0x1800f0df7  mov     [rbx], rax
0x1800f0dfa  test    rax, rax
0x1800f0dfd  jz      short loc_1800F0E1E
0x1800f0dff  mov     rcx, [rdi]; hKey
0x1800f0e02  test    rcx, rcx
0x1800f0e05  jz      short loc_1800F0E1E
0x1800f0e07  mov     dword ptr [rsp+2E0h+phkResult], r15d; fAsynchronous
0x1800f0e0c  mov     r9, rax; hEvent
0x1800f0e0f  mov     r8d, 5; dwNotifyFilter
0x1800f0e15  mov     edx, r15d; bWatchSubtree
0x1800f0e18  call    cs:__imp_RegNotifyChangeKeyValue
0x1800f0e1e  mov     [rbp+1E0h+ppv], r12
0x1800f0e22  lea     rax, [rbp+1E0h+ppv]
0x1800f0e26  mov     [rsp+2E0h+phkResult], rax; ppv
0x1800f0e2b  lea     r9, _GUID_5480f00f_4b80_4deb_ae21_50521db448ed; riid
0x1800f0e32  xor     edx, edx; pUnkOuter
0x1800f0e34  lea     r8d, [rdx+15h]; dwClsContext
0x1800f0e38  lea     rcx, _GUID_9e175b68_f52a_11d8_b9a5_505054503030; rclsid
0x1800f0e3f  call    CoCreateInstance_0
0x1800f0e44  mov     ebx, eax
0x1800f0e46  mov     [rbp+1E0h+var_258], r12
0x1800f0e4a  test    eax, eax
0x1800f0e4c  js      short loc_1800F0E64
0x1800f0e4e  mov     rcx, [rbp+1E0h+ppv]
0x1800f0e52  mov     rax, [rcx]
0x1800f0e55  lea     rdx, [rbp+1E0h+var_258]
0x1800f0e59  mov     rax, [rax+38h]
0x1800f0e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0e62  mov     ebx, eax
0x1800f0e64  mov     rcx, r12
0x1800f0e67  mov     [rsp+2E0h+var_290], rcx
0x1800f0e6c  mov     edi, 80004005h
0x1800f0e71  test    ebx, ebx
0x1800f0e73  js      short loc_1800F0EC0
0x1800f0e75  lea     rdx, aWindows; "Windows"
0x1800f0e7c  lea     rcx, [rsp+2E0h+bstrString]; this
0x1800f0e81  call    ??0CComBSTR@ATL@@QEAA@PEB_W@Z; ATL::CComBSTR::CComBSTR(wchar_t const *)
0x1800f0e86  nop
0x1800f0e87  mov     rcx, [rbp+1E0h+var_258]
0x1800f0e8b  mov     rax, [rcx]
0x1800f0e8e  lea     r8, [rsp+2E0h+var_290]
0x1800f0e93  mov     rdx, [rsp+2E0h+bstrString]
0x1800f0e98  mov     rax, [rax+40h]
0x1800f0e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0ea1  mov     ebx, eax
0x1800f0ea3  cmp     eax, r15d
0x1800f0ea6  jnz     short loc_1800F0EB0
0x1800f0ea8  cmp     [rsp+2E0h+var_290], r12
0x1800f0ead  cmovz   ebx, edi
0x1800f0eb0  mov     rcx, [rsp+2E0h+bstrString]; bstrString
0x1800f0eb5  call    cs:__imp_SysFreeString
0x1800f0ebb  mov     rcx, [rsp+2E0h+var_290]
0x1800f0ec0  mov     rax, r12
0x1800f0ec3  mov     [rbp+1E0h+var_260], rax
0x1800f0ec7  test    ebx, ebx
0x1800f0ec9  js      short loc_1800F0EE7
0x1800f0ecb  mov     rax, [rcx]
0x1800f0ece  lea     r8, [rbp+1E0h+var_260]
0x1800f0ed2  lea     rdx, _GUID_b1d80e6f_8302_46bc_8905_e151c3e0a207
0x1800f0ed9  mov     rax, [rax]
0x1800f0edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0ee1  mov     ebx, eax
0x1800f0ee3  mov     rax, [rbp+1E0h+var_260]
0x1800f0ee7  mov     rcx, r12
0x1800f0eea  mov     [rsp+2E0h+var_268], rcx
0x1800f0eef  test    ebx, ebx
0x1800f0ef1  js      short loc_1800F0F11
0x1800f0ef3  mov     rcx, [rax]
0x1800f0ef6  mov     r8, [rcx+40h]
0x1800f0efa  lea     rdx, [rsp+2E0h+var_268]
0x1800f0eff  mov     rcx, rax
0x1800f0f02  mov     rax, r8
0x1800f0f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0f0a  mov     ebx, eax
0x1800f0f0c  mov     rcx, [rsp+2E0h+var_268]
0x1800f0f11  mov     [rsp+2E0h+var_270], r12
0x1800f0f16  test    ebx, ebx
0x1800f0f18  js      short loc_1800F0F33
0x1800f0f1a  mov     rax, [rcx]
0x1800f0f1d  lea     r8, [rsp+2E0h+var_270]
0x1800f0f22  lea     rdx, _GUID_b05651ea_9b10_425e_b616_1fcd828db3b1
0x1800f0f29  mov     rax, [rax]
0x1800f0f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0f31  mov     ebx, eax
0x1800f0f33  mov     rcx, r12
0x1800f0f36  mov     [rsp+2E0h+var_298], rcx
0x1800f0f3b  test    ebx, ebx
0x1800f0f3d  js      short loc_1800F0F8B
0x1800f0f3f  lea     rdx, aSystemindex; "SystemIndex"
0x1800f0f46  lea     rcx, [rsp+2E0h+bstrString]; this
0x1800f0f4b  call    ??0CComBSTR@ATL@@QEAA@PEB_W@Z; ATL::CComBSTR::CComBSTR(wchar_t const *)
0x1800f0f50  nop
0x1800f0f51  mov     rcx, [rsp+2E0h+var_270]
0x1800f0f56  mov     rax, [rcx]
0x1800f0f59  lea     r8, [rsp+2E0h+var_298]
0x1800f0f5e  mov     rdx, [rsp+2E0h+bstrString]
0x1800f0f63  mov     rax, [rax+40h]
0x1800f0f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0f6c  mov     ebx, eax
0x1800f0f6e  cmp     eax, r15d
0x1800f0f71  jnz     short loc_1800F0F7B
0x1800f0f73  cmp     [rsp+2E0h+var_298], r12
0x1800f0f78  cmovz   ebx, edi
0x1800f0f7b  mov     rcx, [rsp+2E0h+bstrString]; bstrString
0x1800f0f80  call    cs:__imp_SysFreeString
0x1800f0f86  mov     rcx, [rsp+2E0h+var_298]
0x1800f0f8b  mov     rax, r12
0x1800f0f8e  mov     [rsp+2E0h+var_278], rax
0x1800f0f93  test    ebx, ebx
0x1800f0f95  js      short loc_1800F0FB5
0x1800f0f97  mov     rax, [rcx]
0x1800f0f9a  lea     r8, [rsp+2E0h+var_278]
0x1800f0f9f  lea     rdx, _GUID_9d23d738_e1c6_4cb0_b0a4_866f5a352be7
0x1800f0fa6  mov     rax, [rax]
0x1800f0fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0fae  mov     ebx, eax
0x1800f0fb0  mov     rax, [rsp+2E0h+var_278]
0x1800f0fb5  mov     rcx, r12
0x1800f0fb8  mov     [rsp+2E0h+var_280], rcx
0x1800f0fbd  test    ebx, ebx
0x1800f0fbf  js      short loc_1800F0FDF
0x1800f0fc1  mov     rcx, [rax]
0x1800f0fc4  mov     r8, [rcx+40h]
0x1800f0fc8  lea     rdx, [rsp+2E0h+var_280]
0x1800f0fcd  mov     rcx, rax
0x1800f0fd0  mov     rax, r8
0x1800f0fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0fd8  mov     ebx, eax
0x1800f0fda  mov     rcx, [rsp+2E0h+var_280]
0x1800f0fdf  mov     rax, r12
0x1800f0fe2  mov     [rsp+2E0h+var_288], rax
0x1800f0fe7  test    ebx, ebx
0x1800f0fe9  js      short loc_1800F1009
0x1800f0feb  mov     rax, [rcx]
0x1800f0fee  lea     r8, [rsp+2E0h+var_288]
0x1800f0ff3  lea     rdx, _GUID_fce7ec00_38e9_4837_9f8c_a0313215b86f
0x1800f0ffa  mov     rax, [rax]
0x1800f0ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1002  mov     ebx, eax
0x1800f1004  mov     rax, [rsp+2E0h+var_288]
0x1800f1009  mov     rcx, r12
0x1800f100c  mov     [rsp+2E0h+var_2A0], rcx
0x1800f1011  test    ebx, ebx
0x1800f1013  js      short loc_1800F1033
0x1800f1015  mov     rcx, [rax]
0x1800f1018  mov     r8, [rcx+60h]
0x1800f101c  lea     rdx, [rsp+2E0h+var_2A0]
0x1800f1021  mov     rcx, rax
0x1800f1024  mov     rax, r8
0x1800f1027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f102c  mov     ebx, eax
0x1800f102e  mov     rcx, [rsp+2E0h+var_2A0]
0x1800f1033  mov     [rsp+2E0h+var_2B0], r12w
0x1800f1039  test    ebx, ebx
0x1800f103b  js      loc_1800F10FA
0x1800f1041  mov     rax, [rcx]
0x1800f1044  lea     rdx, [rsp+2E0h+var_2B0]
0x1800f1049  mov     rax, [rax+60h]
0x1800f104d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1052  mov     ebx, eax
0x1800f1054  test    eax, eax
0x1800f1056  js      loc_1800F10FA
0x1800f105c  cmp     r12w, [rsp+2E0h+var_2B0]
0x1800f1062  jnz     loc_1800F10FA
0x1800f1068  mov     [rsp+2E0h+bstrString], r12
0x1800f106d  mov     rcx, [rsp+2E0h+var_2A0]
0x1800f1072  mov     rax, [rcx]
0x1800f1075  lea     rdx, [rsp+2E0h+bstrString]
0x1800f107a  mov     rax, [rax+70h]
0x1800f107e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1083  mov     ebx, eax
0x1800f1085  test    eax, eax
0x1800f1087  js      short loc_1800F10EE
0x1800f1089  lea     r14, [rsi+58h]
0x1800f108d  mov     rcx, r14
0x1800f1090  call    ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@HV?$CStringElementTraitsI@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@_W@2@@2@V?$CElementTraits@H@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,int,ATL::CStringElementTraitsI<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CDefaultCharTraits<wchar_t>>,ATL::CElementTraits<int>>::RemoveAll(void)
0x1800f1095  mov     r8b, r15b
0x1800f1098  mov     edx, 101h
0x1800f109d  mov     rcx, r14
0x1800f10a0  call    ?InitHashTable@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@HV?$CStringElementTraitsI@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@_W@2@@2@V?$CElementTraits@H@2@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,int,ATL::CStringElementTraitsI<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CDefaultCharTraits<wchar_t>>,ATL::CElementTraits<int>>::InitHashTable(uint,bool)
0x1800f10a5  mov     [rsi+0A0h], r15d
0x1800f10ac  mov     rcx, [rsp+2E0h+bstrString]; pbstr
0x1800f10b1  call    cs:__imp_SysStringLen
0x1800f10b7  mov     r15d, eax
0x1800f10ba  mov     edi, r12d
0x1800f10bd  test    eax, eax
0x1800f10bf  jz      short loc_1800F10EE
0x1800f10c1  mov     edx, edi
0x1800f10c3  mov     rcx, [rsp+2E0h+bstrString]
0x1800f10c8  lea     rsi, [rcx+rdx*2]
0x1800f10cc  mov     rdx, rsi
0x1800f10cf  mov     rcx, r14
0x1800f10d2  call    ?SetAt@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@HV?$CStringElementTraitsI@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@_W@2@@2@V?$CElementTraits@H@2@@ATL@@QEAAPEAU__POSITION@@PEB_WH@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,int,ATL::CStringElementTraitsI<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CDefaultCharTraits<wchar_t>>,ATL::CElementTraits<int>>::SetAt(wchar_t const *,int)
0x1800f10d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f10db  inc     rax
0x1800f10de  cmp     [rsi+rax*2], r12w
0x1800f10e3  jnz     short loc_1800F10DB
0x1800f10e5  inc     edi
0x1800f10e7  add     edi, eax
0x1800f10e9  cmp     edi, r15d
0x1800f10ec  jb      short loc_1800F10C1
0x1800f10ee  mov     rcx, [rsp+2E0h+bstrString]; bstrString
0x1800f10f3  call    cs:__imp_SysFreeString
0x1800f10f9  nop
0x1800f10fa  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x1800f10ff  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f1104  nop
0x1800f1105  lea     rcx, [rsp+2E0h+var_288]; void *
0x1800f110a  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f110f  nop
0x1800f1110  lea     rcx, [rsp+2E0h+var_280]; void *
0x1800f1115  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f111a  nop
0x1800f111b  lea     rcx, [rsp+2E0h+var_278]; void *
0x1800f1120  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f1125  nop
0x1800f1126  lea     rcx, [rsp+2E0h+var_298]; void *
0x1800f112b  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f1130  nop
0x1800f1131  lea     rcx, [rsp+2E0h+var_270]; void *
0x1800f1136  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f113b  nop
0x1800f113c  lea     rcx, [rsp+2E0h+var_268]; void *
0x1800f1141  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f1146  nop
0x1800f1147  lea     rcx, [rbp+1E0h+var_260]; void *
0x1800f114b  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f1150  nop
0x1800f1151  lea     rcx, [rsp+2E0h+var_290]; void *
0x1800f1156  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f115b  nop
0x1800f115c  lea     rcx, [rbp+1E0h+var_258]; void *
0x1800f1160  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f1165  nop
0x1800f1166  lea     rcx, [rbp+1E0h+ppv]; void *
0x1800f116a  call    ??1?$CComPtrBase@UIFTELanguageResourcePool@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFTELanguageResourcePool>::~CComPtrBase<IFTELanguageResourcePool>(void)
0x1800f116f  mov     eax, ebx
0x1800f1171  mov     rcx, [rbp+1E0h+var_30]
0x1800f1178  xor     rcx, rsp; StackCookie
0x1800f117b  call    __security_check_cookie
0x1800f1180  lea     r11, [rsp+2E0h+var_20]
0x1800f1188  mov     rbx, [r11+38h]
0x1800f118c  mov     rsi, [r11+40h]
0x1800f1190  mov     rsp, r11
0x1800f1193  pop     r15
0x1800f1195  pop     r14
0x1800f1197  pop     r12
0x1800f1199  pop     rdi
  ... truncated ...
```
