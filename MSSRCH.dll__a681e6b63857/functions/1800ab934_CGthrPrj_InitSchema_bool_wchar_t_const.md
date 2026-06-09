# CGthrPrj::InitSchema(bool,wchar_t const *)

- ea: `0x1800ab934`
- end: `0x1800abccb`
- name: `?InitSchema@CGthrPrj@@QEAAX_NPEB_W@Z`
- size: `919`
- prototype: `void __fastcall(CGthrPrj *this, char, unsigned __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ccddc`
- `0x1800e1880`

## callees

- `0x18000a23c`
- `0x18000e628`
- `0x18000ee18`
- `0x18001d5b0`
- `0x1800269b0`
- `0x180029db0`
- `0x18002e44c`
- `0x18008a0c0`
- `0x18009087c`
- `0x180097558`
- `0x1800ab934`
- `0x1800abe78`
- `0x1800e2374`
- `0x1800e95f0`
- `0x1800fe17c`
- `0x18010910c`
- `0x18010ae68`
- `0x1801244c0`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ab98c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ab98c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab9cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab9cd`
- `OLEAUT32!__imp_VariantClear` at `0x1800abb26`
- `OLEAUT32!__imp_VariantClear` at `0x1800abc5a`
- `OLEAUT32!__imp_VariantClear` at `0x1800abb26`
- `OLEAUT32!__imp_VariantClear` at `0x1800abc5a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ab96a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ab96a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800abb9d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800abb9d`

## string_xrefs

- `0x1800ab963`: `tquery.dll`
- `0x1800ab9c3`: `CreatePropMapperStorage`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CGthrPrj::InitSchema(CGthrPrj *this, char a2, unsigned __int64 a3)
{
  HMODULE LibraryW; // rbx
  const char *v7; // r9
  HMODULE v8; // rsi
  FARPROC ProcAddress; // rbx
  const char *v10; // r9
  const int *v11; // r10
  __int64 v12; // r8
  const wchar_t *v13; // r9
  int v14; // eax
  int v15; // eax
  int v16; // esi
  struct IUnknown *v17; // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  struct IUnknown *v19; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v20; // [rsp+38h] [rbp-C8h] BYREF
  struct IIndexCColumnEnum *v21; // [rsp+40h] [rbp-C0h] BYREF
  struct IEnumUnknown *v22; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v23; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  void **v25; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+80h] [rbp-80h]
  unsigned int v28; // [rsp+84h] [rbp-7Ch]
  char v29; // [rsp+88h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  LibraryW = LoadLibraryW(L"tquery.dll");
  v8 = (HMODULE)*((_QWORD *)this + 335);
  if ( v8 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v19);
    FreeLibrary(v8);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v19);
  }
  *((_QWORD *)this + 335) = LibraryW;
  if ( !LibraryW )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x80A,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
      v7);
  ProcAddress = GetProcAddress(LibraryW, "CreatePropMapperStorage");
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x80E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
      v10);
  v25 = &CLMString::`vftable';
  v26 = (wchar_t *)&v29;
  v27 = 65;
  CLMString::AssignInConstructor((CLMString *)&v25, *((const wchar_t **)this + 39), 0xFFFFFFFF);
  v11 = &CCICommonPathString::`vftable';
  v25 = (void **)&CCICommonPathString::`vftable';
  v12 = v28;
  if ( !v28 || v26[v28 - 1] != 92 )
  {
    CLMString::Assign((CLMString *)&v25, L"\\", v28, 0xFFFFFFFF);
    v12 = v28;
    v11 = (const int *)v25;
  }
  (*((void (__fastcall **)(void ***, const wchar_t *, __int64, __int64))v11 + 4))(&v25, L"PropMap", v12, 0xFFFFFFFFLL);
  FSOp::CreateDirectoryWithSecurity(v26, 0, (const WCHAR *)(a3 & -(__int64)(*((_BYTE *)this + 2428) != 0)), v13);
  v20 = 0;
  v14 = ((__int64 (__fastcall *)(wchar_t *, struct IUnknown **))ProcAddress)(v26, &v20);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x81F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
      (const char *)(unsigned int)v14,
      ppv);
  if ( a2 )
  {
    ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg, v20);
    v15 = (*(__int64 (__fastcall **)(char *, const wchar_t *, VARIANTARG *))(*((_QWORD *)this + 320) + 40LL))(
            (char *)this + 2560,
            L"PropertyMapper",
            &pvarg);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x825,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
        (const char *)(unsigned int)v15,
        ppv);
    VariantClear(&pvarg);
  }
  v19 = 0;
  v16 = ATL::CComObject<CSchemaCache>::CreateInstance(&v19);
  if ( v16 >= 0 )
  {
    v17 = v19;
    v23 = v19;
    if ( v19 )
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->AddRef)(v19);
    TComNoUnkPointer<CPlugin>::operator=(&v17[3], v20);
    v19 = 0;
    if ( CoCreateInstance(&CLSID_PropertySystem, 0, 1u, &GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3, (LPVOID *)&v19) >= 0 )
    {
      v22 = 0;
      if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, GUID *, struct IEnumUnknown **))v19->lpVtbl[2].QueryInterface)(
             v19,
             0,
             &GUID_00000100_0000_0000_c000_000000000046,
             &v22) >= 0 )
      {
        v21 = 0;
        if ( (int)EnumColumnsFromPropertyDescription(v22, &v21) >= 0 )
          CSchemaCache::AddParser((CSchemaCache *)v17, v21);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    }
    if ( a2 )
    {
      TComNoUnkPointer<CPlugin>::operator=((char *)this + 2688, v17);
      ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg, v17);
      v16 = (*(__int64 (__fastcall **)(char *, const wchar_t *, VARIANTARG *))(*((_QWORD *)this + 320) + 40LL))(
              (char *)this + 2560,
              L"Schema",
              &pvarg);
      VariantClear(&pvarg);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    TComPointer<CGatherStore>::~TComPointer<CGatherStore>(&v23);
  }
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x845,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgatherprj.cxx",
      (const char *)(unsigned int)v16,
      ppv);
  TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v20);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v25);
}

```

## disassembly

```asm
0x1800ab934  mov     [rsp-8+arg_8], rbx
0x1800ab939  push    rbp
0x1800ab93a  push    rsi
0x1800ab93b  push    rdi
0x1800ab93c  push    r14
0x1800ab93e  push    r15
0x1800ab940  lea     rbp, [rsp-20h]
0x1800ab945  sub     rsp, 120h
0x1800ab94c  mov     rax, cs:__security_cookie
0x1800ab953  xor     rax, rsp
0x1800ab956  mov     [rbp+40h+var_30], rax
0x1800ab95a  mov     r15, r8
0x1800ab95d  mov     r14b, dl
0x1800ab960  mov     rdi, rcx
0x1800ab963  lea     rcx, LibFileName; "tquery.dll"
0x1800ab96a  call    cs:__imp_LoadLibraryW
0x1800ab970  mov     rbx, rax
0x1800ab973  mov     rsi, [rdi+0A78h]
0x1800ab97a  test    rsi, rsi
0x1800ab97d  jz      short loc_1800AB99C
0x1800ab97f  lea     rcx, [rsp+140h+var_110]; this
0x1800ab984  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800ab989  mov     rcx, rsi; hLibModule
0x1800ab98c  call    cs:__imp_FreeLibrary
0x1800ab992  lea     rcx, [rsp+140h+var_110]; this
0x1800ab997  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800ab99c  mov     [rdi+0A78h], rbx
0x1800ab9a3  test    rbx, rbx
0x1800ab9a6  setz    al
0x1800ab9a9  mov     rcx, [rbp+48h]; this
0x1800ab9ad  test    al, al
0x1800ab9af  jz      short loc_1800AB9C3
0x1800ab9b1  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800ab9b8  mov     edx, 80Ah; void *
0x1800ab9bd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ab9c3  lea     rdx, aCreatepropmapp; "CreatePropMapperStorage"
0x1800ab9ca  mov     rcx, rbx; hModule
0x1800ab9cd  call    cs:__imp_GetProcAddress
0x1800ab9d3  mov     rbx, rax
0x1800ab9d6  mov     rcx, [rbp+48h]; this
0x1800ab9da  test    rax, rax
0x1800ab9dd  jnz     short loc_1800AB9F1
0x1800ab9df  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800ab9e6  mov     edx, 80Eh; void *
0x1800ab9eb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ab9f1  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x1800ab9f8  mov     [rsp+140h+var_D0], rax
0x1800ab9fd  lea     rax, [rbp+40h+var_B8]
0x1800aba01  mov     [rsp+140h+var_C8], rax
0x1800aba06  mov     [rbp+40h+var_C0], 41h ; 'A'
0x1800aba0d  or      esi, 0FFFFFFFFh
0x1800aba10  mov     r8d, esi; unsigned int
0x1800aba13  mov     rdx, [rdi+138h]; wchar_t *
0x1800aba1a  lea     rcx, [rsp+140h+var_D0]; this
0x1800aba1f  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x1800aba24  lea     r10, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1800aba2b  mov     [rsp+140h+var_D0], r10
0x1800aba30  mov     r8d, [rbp+40h+var_BC]; unsigned int
0x1800aba34  test    r8d, r8d
0x1800aba37  jz      short loc_1800ABA49
0x1800aba39  lea     ecx, [r8-1]
0x1800aba3d  mov     rax, [rsp+140h+var_C8]
0x1800aba42  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x1800aba47  jz      short loc_1800ABA66
0x1800aba49  mov     r9d, esi; unsigned int
0x1800aba4c  lea     rdx, StringValue; "\\"
0x1800aba53  lea     rcx, [rsp+140h+var_D0]; this
0x1800aba58  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x1800aba5d  mov     r8d, [rbp+40h+var_BC]
0x1800aba61  mov     r10, [rsp+140h+var_D0]
0x1800aba66  mov     r9d, esi
0x1800aba69  lea     rdx, aPropmap; "PropMap"
0x1800aba70  lea     rcx, [rsp+140h+var_D0]
0x1800aba75  mov     rax, [r10+20h]
0x1800aba79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aba7e  mov     al, [rdi+97Ch]
0x1800aba84  neg     al
0x1800aba86  sbb     r8, r8
0x1800aba89  and     r8, r15; void *
0x1800aba8c  xor     edx, edx; wchar_t *
0x1800aba8e  mov     rcx, [rsp+140h+var_C8]; this
0x1800aba93  call    ?CreateDirectoryWithSecurity@FSOp@@YAXPEB_WPEAX0@Z; FSOp::CreateDirectoryWithSecurity(wchar_t const *,void *,wchar_t const *)
0x1800aba98  mov     [rsp+140h+var_108], 0
0x1800abaa1  lea     rdx, [rsp+140h+var_108]
0x1800abaa6  mov     rcx, [rsp+140h+var_C8]
0x1800abaab  mov     rax, rbx
0x1800abaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abab3  mov     rcx, [rbp+48h]; this
0x1800abab7  test    eax, eax
0x1800abab9  jns     short loc_1800ABAD0
0x1800ababb  mov     r9d, eax; char *
0x1800ababe  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800abac5  mov     edx, 81Fh; void *
0x1800abaca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800abad0  test    r14b, r14b
0x1800abad3  jz      short loc_1800ABB2C
0x1800abad5  mov     rdx, [rsp+140h+var_108]; struct IUnknown *
0x1800abada  lea     rcx, [rsp+140h+pvarg]; this
0x1800abadf  call    ??0CComVariant@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComVariant::CComVariant(IUnknown *)
0x1800abae4  nop
0x1800abae5  lea     rcx, [rdi+0A00h]
0x1800abaec  mov     rax, [rcx]
0x1800abaef  lea     r8, [rsp+140h+pvarg]
0x1800abaf4  lea     rdx, aPropertymapper; "PropertyMapper"
0x1800abafb  mov     rax, [rax+28h]
0x1800abaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abb04  mov     rcx, [rbp+48h]; this
0x1800abb08  test    eax, eax
0x1800abb0a  jns     short loc_1800ABB21
0x1800abb0c  mov     r9d, eax; char *
0x1800abb0f  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800abb16  mov     edx, 825h; void *
0x1800abb1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800abb21  lea     rcx, [rsp+140h+pvarg]; pvarg
0x1800abb26  call    cs:__imp_VariantClear
0x1800abb2c  mov     [rsp+140h+var_110], 0
0x1800abb35  lea     rcx, [rsp+140h+var_110]
0x1800abb3a  call    ?CreateInstance@?$CComObject@VCSchemaCache@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CSchemaCache>::CreateInstance(ATL::CComObject<CSchemaCache> * *)
0x1800abb3f  mov     esi, eax
0x1800abb41  test    eax, eax
0x1800abb43  js      loc_1800ABC76
0x1800abb49  mov     rbx, [rsp+140h+var_110]
0x1800abb4e  mov     [rsp+140h+var_F0], rbx
0x1800abb53  test    rbx, rbx
0x1800abb56  jz      short loc_1800ABB68
0x1800abb58  mov     rcx, [rbx]
0x1800abb5b  mov     rax, [rcx+8]
0x1800abb5f  mov     rcx, rbx
0x1800abb62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abb67  nop
0x1800abb68  lea     rcx, [rbx+18h]
0x1800abb6c  mov     rdx, [rsp+140h+var_108]
0x1800abb71  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x1800abb76  mov     [rsp+140h+var_110], 0
0x1800abb7f  lea     rax, [rsp+140h+var_110]
0x1800abb84  mov     qword ptr [rsp+140h+ppv], rax; int
0x1800abb89  lea     r9, _GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3; riid
0x1800abb90  xor     edx, edx; pUnkOuter
0x1800abb92  lea     r8d, [rdx+1]; dwClsContext
0x1800abb96  lea     rcx, CLSID_PropertySystem; rclsid
0x1800abb9d  call    cs:__imp_CoCreateInstance
0x1800abba3  test    eax, eax
0x1800abba5  js      short loc_1800ABC12
0x1800abba7  mov     [rsp+140h+var_F8], 0
0x1800abbb0  mov     rcx, [rsp+140h+var_110]
0x1800abbb5  mov     rax, [rcx]
0x1800abbb8  lea     r9, [rsp+140h+var_F8]
0x1800abbbd  lea     r8, _GUID_00000100_0000_0000_c000_000000000046
0x1800abbc4  xor     edx, edx
0x1800abbc6  mov     rax, [rax+30h]
0x1800abbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abbcf  test    eax, eax
0x1800abbd1  js      short loc_1800ABC08
0x1800abbd3  mov     [rsp+140h+var_100], 0
0x1800abbdc  lea     rdx, [rsp+140h+var_100]; struct IIndexCColumnEnum **
0x1800abbe1  mov     rcx, [rsp+140h+var_F8]; struct IEnumUnknown *
0x1800abbe6  call    ?EnumColumnsFromPropertyDescription@@YAJPEAUIEnumUnknown@@PEAPEAUIIndexCColumnEnum@@@Z; EnumColumnsFromPropertyDescription(IEnumUnknown *,IIndexCColumnEnum * *)
0x1800abbeb  test    eax, eax
0x1800abbed  js      short loc_1800ABBFD
0x1800abbef  mov     rdx, [rsp+140h+var_100]; struct IIndexCColumnEnum *
0x1800abbf4  mov     rcx, rbx; this
0x1800abbf7  call    ?AddParser@CSchemaCache@@QEAAXPEAUIIndexCColumnEnum@@@Z; CSchemaCache::AddParser(IIndexCColumnEnum *)
0x1800abbfc  nop
0x1800abbfd  lea     rcx, [rsp+140h+var_100]
0x1800abc02  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800abc07  nop
0x1800abc08  lea     rcx, [rsp+140h+var_F8]
0x1800abc0d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800abc12  test    r14b, r14b
0x1800abc15  jz      short loc_1800ABC61
0x1800abc17  lea     rcx, [rdi+0A80h]
0x1800abc1e  mov     rdx, rbx
0x1800abc21  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x1800abc26  mov     rdx, rbx; struct IUnknown *
0x1800abc29  lea     rcx, [rsp+140h+pvarg]; this
0x1800abc2e  call    ??0CComVariant@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComVariant::CComVariant(IUnknown *)
0x1800abc33  nop
0x1800abc34  lea     rcx, [rdi+0A00h]
0x1800abc3b  mov     rax, [rcx]
0x1800abc3e  lea     r8, [rsp+140h+pvarg]
0x1800abc43  lea     rdx, aSchema; "Schema"
0x1800abc4a  mov     rax, [rax+28h]
0x1800abc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abc53  mov     esi, eax
0x1800abc55  lea     rcx, [rsp+140h+pvarg]; pvarg
0x1800abc5a  call    cs:__imp_VariantClear
0x1800abc60  nop
0x1800abc61  lea     rcx, [rsp+140h+var_110]
0x1800abc66  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800abc6b  nop
0x1800abc6c  lea     rcx, [rsp+140h+var_F0]
0x1800abc71  call    ??1?$TComPointer@VCGatherStore@@@@QEAA@XZ; TComPointer<CGatherStore>::~TComPointer<CGatherStore>(void)
0x1800abc76  mov     rcx, [rbp+48h]; this
0x1800abc7a  test    esi, esi
0x1800abc7c  jns     short loc_1800ABC93
0x1800abc7e  mov     r9d, esi; char *
0x1800abc81  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800abc88  mov     edx, 845h; void *
0x1800abc8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800abc93  lea     rcx, [rsp+140h+var_108]
0x1800abc98  call    ??1?$TComPointer@UIGatherStoreManagerProvider@@@@QEAA@XZ; TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(void)
0x1800abc9d  nop
0x1800abc9e  lea     rcx, [rsp+140h+var_D0]
0x1800abca3  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800abca8  mov     rcx, [rbp+40h+var_30]
0x1800abcac  xor     rcx, rsp; StackCookie
0x1800abcaf  call    __security_check_cookie
0x1800abcb4  mov     rbx, [rsp+140h+arg_8]
0x1800abcbc  add     rsp, 120h
0x1800abcc3  pop     r15
0x1800abcc5  pop     r14
0x1800abcc7  pop     rdi
0x1800abcc8  pop     rsi
0x1800abcc9  pop     rbp
0x1800abcca  retn
```
