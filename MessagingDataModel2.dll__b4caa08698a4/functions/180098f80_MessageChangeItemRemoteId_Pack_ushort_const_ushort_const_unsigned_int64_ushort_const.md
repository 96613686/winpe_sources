# MessageChangeItemRemoteId::_Pack(ushort const *,ushort const *,unsigned __int64,ushort const *)

- ea: `0x180098f80`
- end: `0x180099516`
- name: `?_Pack@MessageChangeItemRemoteId@@AEAAJPEBG0_K0@Z`
- size: `1430`
- prototype: `__int64 __usercall@<rax>(MessageChangeItemRemoteId *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int64@<r9>, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x180030bd0`
- `0x18003214c`
- `0x18006b108`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x180098ad0`
- `0x180098c58`
- `0x180098f80`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009907f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009907f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800993bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800993f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800993bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800993f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099497`

## string_xrefs

- `0x18009905e`: `Windows.Data.Json.JsonValue`
- `0x180098fdf`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall MessageChangeItemRemoteId::_Pack(
        MessageChangeItemRemoteId *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        const unsigned __int16 *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int ActivationFactory; // eax
  char v13; // r8
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v16; // rax
  int v17; // eax
  char v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v22; // rax
  char v23; // r8
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v26; // rax
  int v27; // eax
  char v28; // r8
  __int64 v29; // rsi
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v32; // rax
  int v33; // eax
  char v34; // r8
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v37; // rax
  int v38; // eax
  char v39; // r8
  __int64 v40; // rsi
  __int64 v41; // rbx
  __int64 (__fastcall *v42)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v43; // rax
  char v44; // r8
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v47; // rax
  int v48; // eax
  char v49; // r8
  __int64 v50; // rsi
  __int64 v51; // rbx
  __int64 (__fastcall *v52)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v53; // rax
  int v54; // eax
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, HSTRING *); // rbx
  int ContentWithoutPII; // eax
  int v58; // ecx
  PCWSTR StringRawBuffer; // rax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v62; // [rsp+48h] [rbp-99h]
  const unsigned __int16 *v63; // [rsp+50h] [rbp-91h]
  const WCHAR *v64; // [rsp+58h] [rbp-89h] BYREF
  const WCHAR *v65; // [rsp+60h] [rbp-81h] BYREF
  const WCHAR *v66; // [rsp+68h] [rbp-79h] BYREF
  _BYTE v67[8]; // [rsp+70h] [rbp-71h] BYREF
  __int64 v68; // [rsp+78h] [rbp-69h] BYREF
  __int64 v69; // [rsp+80h] [rbp-61h] BYREF
  __int64 v70; // [rsp+88h] [rbp-59h] BYREF
  HSTRING string; // [rsp+90h] [rbp-51h] BYREF
  __int64 v72; // [rsp+98h] [rbp-49h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-41h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v75; // [rsp+B0h] [rbp-31h] BYREF
  __int64 (__fastcall ***v76)(_QWORD, GUID *, __int64); // [rsp+B8h] [rbp-29h] BYREF
  _OWORD v77[2]; // [rsp+C0h] [rbp-21h] BYREF

  v65 = a2;
  v64 = a3;
  v63 = a5;
  v66 = a5;
  v76 = 0;
  v62 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v9 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v62, &v76);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v68 = 0;
    v11 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
            &v76,
            (__int64)&v68);
    v10 = v11;
    if ( v11 < 0 )
    {
      Log_HREvent_70(v11);
LABEL_5:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
      goto LABEL_41;
    }
    v69 = 0;
    v62 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = RoGetActivationFactory(v62, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v69);
    v10 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      Log_HREvent_70(ActivationFactory);
LABEL_8:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
      goto LABEL_5;
    }
    v14 = v69;
    v70 = 0;
    v15 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v69 + 80LL);
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v65, v13);
    v17 = v15(v14, v16[1].Reserved.Reserved1, &v70);
    v10 = v17;
    if ( v17 < 0
      || (v19 = v70,
          v67[0] = 0,
          v20 = v68,
          v21 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v68 + 80LL),
          v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD7B0,
                  v18),
          v17 = v21(v20, v22[1].Reserved.Reserved1, v19, v67),
          v10 = v17,
          v17 < 0) )
    {
      Log_HREvent_70(v17);
LABEL_11:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
      goto LABEL_8;
    }
    v24 = v69;
    v72 = 0;
    v25 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v69 + 80LL);
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v64, v23);
    v27 = v25(v24, v26[1].Reserved.Reserved1, &v72);
    v10 = v27;
    if ( v27 < 0
      || (v29 = v68,
          v30 = v72,
          v31 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v68 + 80LL),
          v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD7A0,
                  v28),
          v27 = v31(v29, v32[1].Reserved.Reserved1, v30, v67),
          v10 = v27,
          v27 < 0) )
    {
      Log_HREvent_70(v27);
LABEL_15:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      goto LABEL_11;
    }
    memset(v77, 0, sizeof(v77));
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v77);
    v33 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
            v77,
            L"%I64u",
            a4);
    v10 = v33;
    if ( v33 < 0 )
    {
      Log_HREvent_70(v33);
LABEL_19:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v77);
      goto LABEL_15;
    }
    v35 = v69;
    v73 = 0;
    v64 = *(const WCHAR **)&v77[0];
    v36 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v69 + 80LL);
    v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v64, v34);
    v38 = v36(v35, v37[1].Reserved.Reserved1, &v73);
    v10 = v38;
    if ( v38 < 0
      || (v40 = v68,
          v41 = v73,
          v42 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v68 + 80LL),
          v43 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD7A8,
                  v39),
          v38 = v42(v40, v43[1].Reserved.Reserved1, v41, v67),
          v10 = v38,
          v38 < 0) )
    {
      Log_HREvent_70(v38);
LABEL_22:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
      goto LABEL_19;
    }
    v45 = v69;
    v74 = 0;
    v46 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v69 + 80LL);
    v47 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v66, v44);
    v48 = v46(v45, v47[1].Reserved.Reserved1, &v74);
    v10 = v48;
    if ( v48 < 0
      || (v50 = v68,
          v51 = v74,
          v52 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v68 + 80LL),
          v53 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_1800FD798,
                  v49),
          v48 = v52(v50, v53[1].Reserved.Reserved1, v51, v67),
          v10 = v48,
          v48 < 0) )
    {
      Log_HREvent_70(v48);
LABEL_26:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
      goto LABEL_22;
    }
    v75 = 0;
    v54 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v76,
            (__int64)&v75);
    v10 = v54;
    if ( v54 < 0 )
    {
      Log_HREvent_70(v54);
LABEL_30:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
      goto LABEL_26;
    }
    v55 = v75;
    string = 0;
    v56 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v75 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    ContentWithoutPII = v56(v55, &string);
    v10 = ContentWithoutPII;
    if ( ContentWithoutPII >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               (char *)this + 120,
                               StringRawBuffer)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               (char *)this + 24,
                               a2)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               (char *)this + 56,
                               a3)
        || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               (char *)this + 88,
                               v63) )
      {
        v10 = -2147024882;
        v58 = -2147024882;
        goto LABEL_33;
      }
      *((_QWORD *)this + 23) = a4;
      ContentWithoutPII = MessageChangeItemRemoteId::_GenerateContentWithoutPII(this);
      v10 = ContentWithoutPII;
      if ( ContentWithoutPII >= 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v77);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
        v10 = 0;
        goto LABEL_41;
      }
    }
    v58 = ContentWithoutPII;
LABEL_33:
    Log_HREvent_70(v58);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_30;
  }
  Log_HREvent_70(v9);
LABEL_41:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
  return v10;
}

```

## disassembly

```asm
0x180098f80  push    rbp
0x180098f82  push    rbx
0x180098f83  push    rsi
0x180098f84  push    rdi
0x180098f85  push    r12
0x180098f87  push    r13
0x180098f89  push    r14
0x180098f8b  push    r15
0x180098f8d  lea     rbp, [rsp-17h]
0x180098f92  sub     rsp, 0F8h
0x180098f99  mov     rax, cs:__security_cookie
0x180098fa0  xor     rax, rsp
0x180098fa3  mov     [rbp+4Fh+var_50], rax
0x180098fa7  mov     rax, [rbp+4Fh+arg_20]
0x180098fab  xor     esi, esi
0x180098fad  mov     r15, r9
0x180098fb0  mov     [rsp+130h+var_D0], rdx
0x180098fb5  mov     r13, r8
0x180098fb8  mov     [rsp+130h+var_D8], r8
0x180098fbd  mov     r12, rdx
0x180098fc0  mov     [rsp+130h+var_E0], rax
0x180098fc5  mov     r14, rcx
0x180098fc8  mov     [rbp+4Fh+var_C8], rax
0x180098fcc  lea     edi, [rsi+1Ch]
0x180098fcf  mov     [rbp+4Fh+var_78], rsi
0x180098fd3  mov     r9d, edi; unsigned int
0x180098fd6  mov     [rsp+130h+var_E8], rsi
0x180098fdb  lea     r8d, [rsi+1Dh]; unsigned int
0x180098fdf  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180098fe6  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x180098feb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180098ff0  mov     rcx, [rsp+130h+var_E8]
0x180098ff5  lea     rdx, [rbp+4Fh+var_78]
0x180098ff9  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180098ffe  mov     ebx, eax
0x180099000  test    eax, eax
0x180099002  jns     short loc_180099017
0x180099004  lea     edx, [rsi+1]
0x180099007  mov     ecx, eax; int
0x180099009  lea     r9d, [rsi+65h]
0x18009900d  call    Log_HREvent_70
0x180099012  jmp     loc_1800994EB
0x180099017  lea     rdx, [rbp+4Fh+var_B8]
0x18009901b  mov     [rbp+4Fh+var_B8], rsi
0x18009901f  lea     rcx, [rbp+4Fh+var_78]
0x180099023  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>>)
0x180099028  mov     ebx, eax
0x18009902a  test    eax, eax
0x18009902c  jns     short loc_18009904C
0x18009902e  mov     edx, 1
0x180099033  mov     ecx, eax; int
0x180099035  lea     r9d, [rdx+67h]
0x180099039  call    Log_HREvent_70
0x18009903e  lea     rcx, [rbp+4Fh+var_B8]
0x180099042  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180099047  jmp     loc_1800994EB
0x18009904c  mov     r9d, 1Bh; unsigned int
0x180099052  mov     [rbp+4Fh+var_B0], rsi
0x180099056  mov     r8d, edi; unsigned int
0x180099059  mov     [rsp+130h+var_E8], rsi
0x18009905e  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180099065  lea     rcx, [rsp+130h+hstringHeader]; hstringHeader
0x18009906a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009906f  mov     rcx, [rsp+130h+var_E8]
0x180099074  lea     r8, [rbp+4Fh+var_B0]
0x180099078  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18009907f  call    cs:__imp_RoGetActivationFactory
0x180099085  mov     ebx, eax
0x180099087  test    eax, eax
0x180099089  jns     short loc_1800990A6
0x18009908b  mov     edx, 1
0x180099090  mov     ecx, eax; int
0x180099092  lea     r9d, [rdx+6Bh]
0x180099096  call    Log_HREvent_70
0x18009909b  lea     rcx, [rbp+4Fh+var_B0]
0x18009909f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800990a4  jmp     short loc_18009903E
0x1800990a6  mov     rdi, [rbp+4Fh+var_B0]
0x1800990aa  lea     rdx, [rsp+130h+var_D0]
0x1800990af  mov     [rbp+4Fh+var_A8], rsi
0x1800990b3  lea     rcx, [rsp+130h+hstringHeader]
0x1800990b8  mov     rax, [rdi]
0x1800990bb  mov     rbx, [rax+50h]
0x1800990bf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800990c4  lea     r8, [rbp+4Fh+var_A8]
0x1800990c8  mov     rcx, rdi
0x1800990cb  mov     rdx, [rax+18h]
0x1800990cf  mov     rax, rbx
0x1800990d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800990d7  mov     ebx, eax
0x1800990d9  test    eax, eax
0x1800990db  jns     short loc_1800990FA
0x1800990dd  mov     r9d, 71h ; 'q'
0x1800990e3  mov     edx, 1
0x1800990e8  mov     ecx, eax; int
0x1800990ea  call    Log_HREvent_70
0x1800990ef  lea     rcx, [rbp+4Fh+var_A8]
0x1800990f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800990f8  jmp     short loc_18009909B
0x1800990fa  mov     rbx, [rbp+4Fh+var_A8]
0x1800990fe  lea     rdx, off_1800FD7B0; "ChatServiceConversationId"
0x180099105  mov     [rbp+4Fh+var_C0], sil
0x180099109  lea     rcx, [rsp+130h+hstringHeader]
0x18009910e  mov     rsi, [rbp+4Fh+var_B8]
0x180099112  mov     rax, [rsi]
0x180099115  mov     rdi, [rax+50h]
0x180099119  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009911e  lea     r9, [rbp+4Fh+var_C0]
0x180099122  mov     r8, rbx
0x180099125  mov     rcx, rsi
0x180099128  mov     rdx, [rax+18h]
0x18009912c  mov     rax, rdi
0x18009912f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099134  mov     ebx, eax
0x180099136  test    eax, eax
0x180099138  jns     short loc_180099142
0x18009913a  mov     r9d, 75h ; 'u'
0x180099140  jmp     short loc_1800990E3
0x180099142  mov     rdi, [rbp+4Fh+var_B0]
0x180099146  lea     rdx, [rsp+130h+var_D8]
0x18009914b  mov     [rbp+4Fh+var_98], 0
0x180099153  lea     rcx, [rsp+130h+hstringHeader]
0x180099158  mov     rax, [rdi]
0x18009915b  mov     rbx, [rax+50h]
0x18009915f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180099164  lea     r8, [rbp+4Fh+var_98]
0x180099168  mov     rcx, rdi
0x18009916b  mov     rdx, [rax+18h]
0x18009916f  mov     rax, rbx
0x180099172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099177  mov     ebx, eax
0x180099179  test    eax, eax
0x18009917b  jns     short loc_18009919D
0x18009917d  mov     r9d, 7Ah ; 'z'
0x180099183  mov     edx, 1
0x180099188  mov     ecx, eax; int
0x18009918a  call    Log_HREvent_70
0x18009918f  lea     rcx, [rbp+4Fh+var_98]
0x180099193  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180099198  jmp     loc_1800990EF
0x18009919d  mov     rsi, [rbp+4Fh+var_B8]
0x1800991a1  lea     rdx, off_1800FD7A0; "ChatServiceMessageId"
0x1800991a8  mov     rbx, [rbp+4Fh+var_98]
0x1800991ac  lea     rcx, [rsp+130h+hstringHeader]
0x1800991b1  mov     rax, [rsi]
0x1800991b4  mov     rdi, [rax+50h]
0x1800991b8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800991bd  lea     r9, [rbp+4Fh+var_C0]
0x1800991c1  mov     r8, rbx
0x1800991c4  mov     rcx, rsi
0x1800991c7  mov     rdx, [rax+18h]
0x1800991cb  mov     rax, rdi
0x1800991ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800991d3  mov     ebx, eax
0x1800991d5  test    eax, eax
0x1800991d7  jns     short loc_1800991E1
0x1800991d9  mov     r9d, 7Dh ; '}'
0x1800991df  jmp     short loc_180099183
0x1800991e1  xorps   xmm0, xmm0
0x1800991e4  lea     rcx, [rbp+4Fh+var_70]
0x1800991e8  movups  [rbp+4Fh+var_70], xmm0
0x1800991ec  movups  [rbp+4Fh+var_60], xmm0
0x1800991f0  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800991f5  lea     rdx, aI64u; "%I64u"
0x1800991fc  mov     r8, r15
0x1800991ff  lea     rcx, [rbp+4Fh+var_70]
0x180099203  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180099208  mov     ebx, eax
0x18009920a  test    eax, eax
0x18009920c  jns     short loc_18009922E
0x18009920e  mov     edx, 1
0x180099213  mov     r9d, 81h
0x180099219  mov     ecx, eax; int
0x18009921b  call    Log_HREvent_70
0x180099220  lea     rcx, [rbp+4Fh+var_70]
0x180099224  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180099229  jmp     loc_18009918F
0x18009922e  mov     rcx, qword ptr [rbp+4Fh+var_70]
0x180099232  lea     rdx, [rsp+130h+var_D8]
0x180099237  mov     rdi, [rbp+4Fh+var_B0]
0x18009923b  mov     [rbp+4Fh+var_90], 0
0x180099243  mov     [rsp+130h+var_D8], rcx
0x180099248  lea     rcx, [rsp+130h+hstringHeader]
0x18009924d  mov     rax, [rdi]
0x180099250  mov     rbx, [rax+50h]
0x180099254  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180099259  lea     r8, [rbp+4Fh+var_90]
0x18009925d  mov     rcx, rdi
0x180099260  mov     rdx, [rax+18h]
0x180099264  mov     rax, rbx
0x180099267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009926c  mov     ebx, eax
0x18009926e  test    eax, eax
0x180099270  jns     short loc_18009928F
0x180099272  mov     r9d, 85h
0x180099278  mov     edx, 1
0x18009927d  mov     ecx, eax; int
0x18009927f  call    Log_HREvent_70
0x180099284  lea     rcx, [rbp+4Fh+var_90]
0x180099288  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009928d  jmp     short loc_180099220
0x18009928f  mov     rsi, [rbp+4Fh+var_B8]
0x180099293  lea     rdx, off_1800FD7A8; "ClientMessageId"
0x18009929a  mov     rbx, [rbp+4Fh+var_90]
0x18009929e  lea     rcx, [rsp+130h+hstringHeader]
0x1800992a3  mov     rax, [rsi]
0x1800992a6  mov     rdi, [rax+50h]
0x1800992aa  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800992af  lea     r9, [rbp+4Fh+var_C0]
0x1800992b3  mov     r8, rbx
0x1800992b6  mov     rcx, rsi
0x1800992b9  mov     rdx, [rax+18h]
0x1800992bd  mov     rax, rdi
0x1800992c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800992c5  mov     ebx, eax
0x1800992c7  test    eax, eax
0x1800992c9  jns     short loc_1800992D3
0x1800992cb  mov     r9d, 87h
0x1800992d1  jmp     short loc_180099278
0x1800992d3  mov     rdi, [rbp+4Fh+var_B0]
0x1800992d7  lea     rdx, [rbp+4Fh+var_C8]
0x1800992db  mov     [rbp+4Fh+var_88], 0
0x1800992e3  lea     rcx, [rsp+130h+hstringHeader]
0x1800992e8  mov     rax, [rdi]
0x1800992eb  mov     rbx, [rax+50h]
0x1800992ef  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800992f4  lea     r8, [rbp+4Fh+var_88]
0x1800992f8  mov     rcx, rdi
0x1800992fb  mov     rdx, [rax+18h]
0x1800992ff  mov     rax, rbx
0x180099302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099307  mov     ebx, eax
0x180099309  test    eax, eax
0x18009930b  jns     short loc_18009932D
0x18009930d  mov     r9d, 8Ch
0x180099313  mov     edx, 1
0x180099318  mov     ecx, eax; int
0x18009931a  call    Log_HREvent_70
0x18009931f  lea     rcx, [rbp+4Fh+var_88]
0x180099323  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180099328  jmp     loc_180099284
0x18009932d  mov     rsi, [rbp+4Fh+var_B8]
0x180099331  lea     rdx, off_1800FD798; "AsyncMediaServiceDocumentId"
0x180099338  mov     rbx, [rbp+4Fh+var_88]
0x18009933c  lea     rcx, [rsp+130h+hstringHeader]
0x180099341  mov     rax, [rsi]
0x180099344  mov     rdi, [rax+50h]
0x180099348  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009934d  lea     r9, [rbp+4Fh+var_C0]
0x180099351  mov     r8, rbx
0x180099354  mov     rcx, rsi
0x180099357  mov     rdx, [rax+18h]
0x18009935b  mov     rax, rdi
0x18009935e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099363  xor     esi, esi
0x180099365  mov     ebx, eax
0x180099367  test    eax, eax
0x180099369  jns     short loc_180099373
0x18009936b  mov     r9d, 8Fh
0x180099371  jmp     short loc_180099313
0x180099373  lea     rdx, [rbp+4Fh+var_80]
0x180099377  mov     [rbp+4Fh+var_80], rsi
0x18009937b  lea     rcx, [rbp+4Fh+var_78]
0x18009937f  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180099384  mov     ebx, eax
0x180099386  test    eax, eax
0x180099388  jns     short loc_1800993AA
0x18009938a  mov     edx, 1
0x18009938f  mov     r9d, 93h
0x180099395  mov     ecx, eax; int
0x180099397  call    Log_HREvent_70
0x18009939c  lea     rcx, [rbp+4Fh+var_80]
0x1800993a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800993a5  jmp     loc_18009931F
0x1800993aa  mov     rdi, [rbp+4Fh+var_80]
0x1800993ae  xor     ecx, ecx; string
0x1800993b0  mov     [rbp+4Fh+string], rsi
0x1800993b4  mov     rax, [rdi]
0x1800993b7  mov     rbx, [rax+38h]
0x1800993bb  call    cs:__imp_WindowsDeleteString
0x1800993c1  lea     rdx, [rbp+4Fh+string]
0x1800993c5  mov     [rbp+4Fh+string], rsi
0x1800993c9  mov     rcx, rdi
0x1800993cc  mov     rax, rbx
0x1800993cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800993d4  mov     ebx, eax
0x1800993d6  test    eax, eax
0x1800993d8  jns     short loc_1800993FC
0x1800993da  mov     r9d, 95h
0x1800993e0  mov     edx, 1
0x1800993e5  mov     ecx, eax; int
0x1800993e7  call    Log_HREvent_70
0x1800993ec  mov     rcx, [rbp+4Fh+string]; string
0x1800993f0  call    cs:__imp_WindowsDeleteString
0x1800993f6  mov     [rbp+4Fh+string], rsi
0x1800993fa  jmp     short loc_18009939C
0x1800993fc  mov     rcx, [rbp+4Fh+string]; string
0x180099400  xor     edx, edx; length
0x180099402  call    cs:__imp_WindowsGetStringRawBuffer
0x180099408  mov     rdx, rax
  ... truncated ...
```
