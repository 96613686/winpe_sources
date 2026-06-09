# Windows::Internal::Security::CPropertiesSerializer::HStringPropertyBagToPropertySet(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x1800170cc`
- end: `0x1800174ca`
- name: `?HStringPropertyBagToPropertySet@CPropertiesSerializer@Security@Internal@Windows@@SAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@4@PEAPEAUIPropertySet@674@@Z`
- size: `1022`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800471e0`

## callees

- `0x180007350`
- `0x18000f8e8`
- `0x180016f44`
- `0x1800170cc`
- `0x1800175c0`
- `0x180025c10`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800174bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800174bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800173a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800173a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001723a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001723a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017300`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800173c6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800173c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001715f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001715f`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::CPropertiesSerializer::HStringPropertyBagToPropertySet(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        LPVOID *a2)
{
  int ActivationFactory; // ebx
  HSTRING v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 (__fastcall *v9)(__int64, __int64 *); // rdi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  LPVOID v22; // rdi
  __int64 (__fastcall *v23)(LPVOID, GUID *, __int64 *); // rbx
  char v24; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v25[7]; // [rsp+31h] [rbp-58h] BYREF
  __int64 v26; // [rsp+38h] [rbp-51h] BYREF
  __int64 v27; // [rsp+40h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v29; // [rsp+50h] [rbp-39h] BYREF
  HSTRING string; // [rsp+58h] [rbp-31h] BYREF
  __int64 v31; // [rsp+60h] [rbp-29h] BYREF
  __int64 v32; // [rsp+68h] [rbp-21h] BYREF
  __int64 *v33; // [rsp+70h] [rbp-19h] BYREF
  __int64 v34; // [rsp+78h] [rbp-11h] BYREF
  __int64 v35; // [rsp+80h] [rbp-9h] BYREF
  int v36; // [rsp+88h] [rbp-1h]
  HSTRING v37; // [rsp+90h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp+Fh] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  ppv = 0;
  v32 = 0;
  v34 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  ActivationFactory = CoCreateInstance(
                        &GUID_f1c46d71_b791_4110_8d5c_7108f22c1010,
                        0,
                        1u,
                        &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
                        &ppv);
  if ( ActivationFactory >= 0 )
  {
    v22 = ppv;
    v23 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v32);
    ActivationFactory = v23(v22, &GUID_deab70f3_3a9c_40e6_a680_2ee376c5eaed, &v32);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 48LL))(v32, 1);
      if ( ActivationFactory >= 0 )
        ActivationFactory = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&ppv,
                              (__int64)&v34);
    }
  }
  v31 = 0;
  v27 = 0;
  v24 = 0;
  if ( ActivationFactory >= 0 )
  {
    v19 = **a1;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v31);
    ActivationFactory = v19(a1, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v31);
    if ( ActivationFactory >= 0 )
    {
      v20 = v31;
      v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL);
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v27);
      ActivationFactory = v21(v20, &v27);
      if ( ActivationFactory >= 0 )
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 56LL))(v27, &v24);
    }
  }
  v33 = 0;
  if ( ActivationFactory >= 0 )
  {
    if ( WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &v37) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = RoGetActivationFactory(v37, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v33);
  }
  v25[0] = 0;
  v6 = 0;
  v29 = 0;
  v35 = 0;
  v36 = 0;
  v26 = 0;
  string = 0;
  if ( ActivationFactory >= 0 )
  {
    while ( v24 )
    {
      v7 = v27;
      v8 = v26;
      v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 48LL);
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      ActivationFactory = v9(v7, &v26);
      if ( ActivationFactory < 0 )
        goto LABEL_19;
      v10 = v26;
      v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      ActivationFactory = v11(v10, &string);
      if ( ActivationFactory < 0 )
        goto LABEL_19;
      v12 = v26;
      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 56LL);
      WindowsDeleteString(v29);
      v29 = 0;
      ActivationFactory = v13(v12, &v29);
      if ( ActivationFactory < 0 )
        goto LABEL_19;
      v14 = *v33;
      v37 = (HSTRING)&v35;
      hstringHeader.Reserved.Reserved1 = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING_HEADER *))(v14 + 144))(
                            v33,
                            v29,
                            &hstringHeader);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v37);
      if ( ActivationFactory >= 0 )
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v34 + 80LL))(
                              v34,
                              string,
                              v35,
                              v25);
      if ( ActivationFactory < 0
        || (ActivationFactory = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 64LL))(v27, &v24),
            ActivationFactory < 0) )
      {
LABEL_19:
        v6 = v29;
        break;
      }
      v6 = v29;
    }
  }
  *a2 = ppv;
  ppv = 0;
  if ( v6 )
    WindowsDeleteString(v6);
  if ( string )
    WindowsDeleteString(string);
  v15 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  RoVariant::~RoVariant((RoVariant *)&v35);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  v16 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  v18 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800170cc  mov     [rsp-8+arg_10], rbx
0x1800170d1  push    rbp
0x1800170d2  push    rsi
0x1800170d3  push    rdi
0x1800170d4  push    r14
0x1800170d6  push    r15
0x1800170d8  lea     rbp, [rsp-37h]
0x1800170dd  sub     rsp, 0C0h
0x1800170e4  mov     rax, cs:__security_cookie
0x1800170eb  xor     rax, rsp
0x1800170ee  mov     [rbp+57h+var_30], rax
0x1800170f2  xor     r15d, r15d
0x1800170f5  mov     r14, rdx
0x1800170f8  mov     rsi, rcx
0x1800170fb  test    rcx, rcx
0x1800170fe  jnz     short loc_180017128
0x180017100  mov     eax, 80070057h
0x180017105  mov     rcx, [rbp+57h+var_30]
0x180017109  xor     rcx, rsp; StackCookie
0x18001710c  call    __security_check_cookie
0x180017111  mov     rbx, [rsp+0E0h+arg_10]
0x180017119  add     rsp, 0C0h
0x180017120  pop     r15
0x180017122  pop     r14
0x180017124  pop     rdi
0x180017125  pop     rsi
0x180017126  pop     rbp
0x180017127  retn
0x180017128  test    r14, r14
0x18001712b  jz      short loc_180017100
0x18001712d  lea     rcx, [rbp+57h+var_98]
0x180017131  mov     [rbp+57h+var_98], r15
0x180017135  mov     [rbp+57h+var_78], r15
0x180017139  mov     [rbp+57h+var_68], r15
0x18001713d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017142  xor     edx, edx; pUnkOuter
0x180017144  lea     rax, [rbp+57h+var_98]
0x180017148  lea     r9, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; riid
0x18001714f  mov     [rsp+0E0h+ppv], rax; ppv
0x180017154  lea     rcx, _GUID_f1c46d71_b791_4110_8d5c_7108f22c1010; rclsid
0x18001715b  lea     r8d, [rdx+1]; dwClsContext
0x18001715f  call    cs:__imp_CoCreateInstance
0x180017165  mov     ebx, eax
0x180017167  test    eax, eax
0x180017169  jns     loc_18001744A
0x18001716f  mov     [rbp+57h+var_80], r15
0x180017173  mov     [rbp+57h+var_A0], r15
0x180017177  mov     [rbp+57h+var_B0], r15b
0x18001717b  test    ebx, ebx
0x18001717d  jns     loc_1800173D3
0x180017183  mov     [rbp+57h+var_70], r15
0x180017187  test    ebx, ebx
0x180017189  jns     loc_180017395
0x18001718f  mov     [rbp+57h+var_AF], r15b
0x180017193  mov     rcx, r15
0x180017196  mov     [rbp+57h+var_90], rcx
0x18001719a  mov     [rbp+57h+var_60], r15
0x18001719e  mov     [rbp+57h+var_58], r15d
0x1800171a2  mov     [rbp+57h+var_A8], r15
0x1800171a6  mov     [rbp+57h+string], r15
0x1800171aa  test    ebx, ebx
0x1800171ac  js      loc_1800172E1
0x1800171b2  cmp     [rbp+57h+var_B0], r15b
0x1800171b6  jz      loc_1800172E1
0x1800171bc  mov     rbx, [rbp+57h+var_A0]
0x1800171c0  mov     rcx, [rbp+57h+var_A8]
0x1800171c4  mov     rax, [rbx]
0x1800171c7  mov     rdi, [rax+30h]
0x1800171cb  test    rcx, rcx
0x1800171ce  jz      short loc_1800171E0
0x1800171d0  mov     [rbp+57h+var_A8], r15
0x1800171d4  mov     rdx, [rcx]
0x1800171d7  mov     rax, [rdx+10h]
0x1800171db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e0  lea     rdx, [rbp+57h+var_A8]
0x1800171e4  mov     rcx, rbx
0x1800171e7  mov     rax, rdi
0x1800171ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ef  mov     ebx, eax
0x1800171f1  test    eax, eax
0x1800171f3  js      loc_1800172DD
0x1800171f9  mov     rdi, [rbp+57h+var_A8]
0x1800171fd  mov     rcx, [rbp+57h+string]; string
0x180017201  mov     rax, [rdi]
0x180017204  mov     rbx, [rax+30h]
0x180017208  call    cs:__imp_WindowsDeleteString
0x18001720e  lea     rdx, [rbp+57h+string]
0x180017212  mov     [rbp+57h+string], r15
0x180017216  mov     rcx, rdi
0x180017219  mov     rax, rbx
0x18001721c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017221  mov     ebx, eax
0x180017223  test    eax, eax
0x180017225  js      loc_1800172DD
0x18001722b  mov     rdi, [rbp+57h+var_A8]
0x18001722f  mov     rcx, [rbp+57h+var_90]; string
0x180017233  mov     rax, [rdi]
0x180017236  mov     rbx, [rax+38h]
0x18001723a  call    cs:__imp_WindowsDeleteString
0x180017240  lea     rdx, [rbp+57h+var_90]
0x180017244  mov     [rbp+57h+var_90], r15
0x180017248  mov     rcx, rdi
0x18001724b  mov     rax, rbx
0x18001724e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017253  mov     ebx, eax
0x180017255  test    eax, eax
0x180017257  js      loc_1800172DD
0x18001725d  mov     rcx, [rbp+57h+var_70]
0x180017261  lea     rdx, [rbp+57h+var_60]
0x180017265  lea     r8, [rbp+57h+hstringHeader]
0x180017269  mov     rax, [rcx]
0x18001726c  mov     [rbp+57h+var_50], rdx
0x180017270  mov     rdx, [rbp+57h+var_90]
0x180017274  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r15
0x180017278  mov     rax, [rax+90h]
0x18001727f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017284  lea     rcx, [rbp+57h+var_50]; this
0x180017288  mov     ebx, eax
0x18001728a  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x18001728f  mov     eax, ebx
0x180017291  shr     eax, 1Fh
0x180017294  xor     al, 1
0x180017296  jz      short loc_1800172B6
0x180017298  mov     rcx, [rbp+57h+var_68]
0x18001729c  lea     r9, [rbp+57h+var_AF]
0x1800172a0  mov     r8, [rbp+57h+var_60]
0x1800172a4  mov     rdx, [rbp+57h+string]
0x1800172a8  mov     rax, [rcx]
0x1800172ab  mov     rax, [rax+50h]
0x1800172af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172b4  mov     ebx, eax
0x1800172b6  test    ebx, ebx
0x1800172b8  js      short loc_1800172DD
0x1800172ba  mov     rcx, [rbp+57h+var_A0]
0x1800172be  lea     rdx, [rbp+57h+var_B0]
0x1800172c2  mov     rax, [rcx]
0x1800172c5  mov     rax, [rax+40h]
0x1800172c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172ce  mov     ebx, eax
0x1800172d0  test    eax, eax
0x1800172d2  js      short loc_1800172DD
0x1800172d4  mov     rcx, [rbp+57h+var_90]
0x1800172d8  jmp     loc_1800171B2
0x1800172dd  mov     rcx, [rbp+57h+var_90]; string
0x1800172e1  mov     rax, [rbp+57h+var_98]
0x1800172e5  mov     [r14], rax
0x1800172e8  mov     [rbp+57h+var_98], r15
0x1800172ec  test    rcx, rcx
0x1800172ef  jz      short loc_1800172F7
0x1800172f1  call    cs:__imp_WindowsDeleteString
0x1800172f7  mov     rcx, [rbp+57h+string]; string
0x1800172fb  test    rcx, rcx
0x1800172fe  jz      short loc_180017306
0x180017300  call    cs:__imp_WindowsDeleteString
0x180017306  mov     rcx, [rbp+57h+var_A8]
0x18001730a  test    rcx, rcx
0x18001730d  jz      short loc_18001731F
0x18001730f  mov     [rbp+57h+var_A8], r15
0x180017313  mov     rax, [rcx]
0x180017316  mov     rax, [rax+10h]
0x18001731a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001731f  lea     rcx, [rbp+57h+var_60]; this
0x180017323  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180017328  lea     rcx, [rbp+57h+var_70]
0x18001732c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017331  mov     rcx, [rbp+57h+var_A0]
0x180017335  test    rcx, rcx
0x180017338  jz      short loc_18001734A
0x18001733a  mov     [rbp+57h+var_A0], r15
0x18001733e  mov     rax, [rcx]
0x180017341  mov     rax, [rax+10h]
0x180017345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001734a  mov     rcx, [rbp+57h+var_80]
0x18001734e  test    rcx, rcx
0x180017351  jz      short loc_180017363
0x180017353  mov     [rbp+57h+var_80], r15
0x180017357  mov     rax, [rcx]
0x18001735a  mov     rax, [rax+10h]
0x18001735e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017363  lea     rcx, [rbp+57h+var_68]
0x180017367  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001736c  mov     rcx, [rbp+57h+var_78]
0x180017370  test    rcx, rcx
0x180017373  jz      short loc_180017385
0x180017375  mov     [rbp+57h+var_78], r15
0x180017379  mov     rax, [rcx]
0x18001737c  mov     rax, [rax+10h]
0x180017380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017385  lea     rcx, [rbp+57h+var_98]
0x180017389  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001738e  mov     eax, ebx
0x180017390  jmp     loc_180017105
0x180017395  lea     r9, [rbp+57h+var_50]; string
0x180017399  mov     edx, 20h ; ' '; length
0x18001739e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800173a2  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800173a9  call    cs:__imp_WindowsCreateStringReference
0x1800173af  test    eax, eax
0x1800173b1  js      loc_1800174B0
0x1800173b7  mov     rcx, [rbp+57h+var_50]
0x1800173bb  lea     r8, [rbp+57h+var_70]
0x1800173bf  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800173c6  call    cs:__imp_RoGetActivationFactory
0x1800173cc  mov     ebx, eax
0x1800173ce  jmp     loc_18001718F
0x1800173d3  mov     rax, [rsi]
0x1800173d6  lea     rcx, [rbp+57h+var_80]
0x1800173da  mov     rbx, [rax]
0x1800173dd  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800173e2  lea     r8, [rbp+57h+var_80]
0x1800173e6  mov     rcx, rsi
0x1800173e9  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x1800173f0  mov     rax, rbx
0x1800173f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173f8  mov     ebx, eax
0x1800173fa  test    eax, eax
0x1800173fc  js      loc_180017183
0x180017402  mov     rdi, [rbp+57h+var_80]
0x180017406  lea     rcx, [rbp+57h+var_A0]
0x18001740a  mov     rax, [rdi]
0x18001740d  mov     rbx, [rax+30h]
0x180017411  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180017416  lea     rdx, [rbp+57h+var_A0]
0x18001741a  mov     rcx, rdi
0x18001741d  mov     rax, rbx
0x180017420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017425  mov     ebx, eax
0x180017427  test    eax, eax
0x180017429  js      loc_180017183
0x18001742f  mov     rcx, [rbp+57h+var_A0]
0x180017433  lea     rdx, [rbp+57h+var_B0]
0x180017437  mov     rax, [rcx]
0x18001743a  mov     rax, [rax+38h]
0x18001743e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017443  mov     ebx, eax
0x180017445  jmp     loc_180017183
0x18001744a  mov     rdi, [rbp+57h+var_98]
0x18001744e  lea     rcx, [rbp+57h+var_78]
0x180017452  mov     rax, [rdi]
0x180017455  mov     rbx, [rax]
0x180017458  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18001745d  lea     r8, [rbp+57h+var_78]
0x180017461  mov     rcx, rdi
0x180017464  lea     rdx, _GUID_deab70f3_3a9c_40e6_a680_2ee376c5eaed
0x18001746b  mov     rax, rbx
0x18001746e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017473  mov     ebx, eax
0x180017475  test    eax, eax
0x180017477  js      loc_18001716F
0x18001747d  mov     rcx, [rbp+57h+var_78]
0x180017481  mov     edx, 1
0x180017486  mov     rax, [rcx]
0x180017489  mov     rax, [rax+30h]
0x18001748d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017492  mov     ebx, eax
0x180017494  test    eax, eax
0x180017496  js      loc_18001716F
0x18001749c  lea     rdx, [rbp+57h+var_68]
0x1800174a0  lea     rcx, [rbp+57h+var_98]
0x1800174a4  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800174a9  mov     ebx, eax
0x1800174ab  jmp     loc_18001716F
0x1800174b0  xor     r9d, r9d; lpArguments
0x1800174b3  xor     r8d, r8d; nNumberOfArguments
0x1800174b6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800174bb  lea     edx, [r9+1]; dwExceptionFlags
0x1800174bf  call    cs:__imp_RaiseException
0x1800174c5  jmp     loc_1800173B7
```
