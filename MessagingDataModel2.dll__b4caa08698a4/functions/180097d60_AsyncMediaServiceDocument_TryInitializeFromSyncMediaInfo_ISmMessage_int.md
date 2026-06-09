# AsyncMediaServiceDocument::_TryInitializeFromSyncMediaInfo(ISmMessage *,int *)

- ea: `0x180097d60`
- end: `0x18009852c`
- name: `?_TryInitializeFromSyncMediaInfo@AsyncMediaServiceDocument@@AEAAJPEAUISmMessage@@PEAH@Z`
- size: `1996`
- prototype: `__int64 __fastcall(AsyncMediaServiceDocument *__hidden this, struct ISmMessage *, int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001f50`
- `0x180005c50`
- `0x180008870`
- `0x18000b6d4`
- `0x18000b7d4`
- `0x180030bd0`
- `0x18005d394`
- `0x18006b108`
- `0x180084738`
- `0x18009201c`
- `0x1800967ac`
- `0x180096cac`
- `0x180097014`
- `0x180097d60`
- `0x1800b1ea8`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180097fa8`
- `msvcrt!_wcsicmp` at `0x180097fa8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180097e68`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180097e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097f95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800981fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800982b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800982c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097f95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800981fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800982b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800982c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097f31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097f7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800981be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098270`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009830b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800983a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800983c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800983f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800984bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097f31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097f7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800981be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098270`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009830b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800983a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800983c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800983f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800984bf`

## string_xrefs

- `0x180097e3d`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall AsyncMediaServiceDocument::_TryInitializeFromSyncMediaInfo(
        AsyncMediaServiceDocument *this,
        struct ISmMessage *a2,
        int *a3)
{
  __int64 v5; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int ActivationFactory; // eax
  char v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, PVOID, HSTRING *); // rbx
  char v19; // r8
  HSTRING_HEADER *v20; // rax
  int v21; // eax
  const wchar_t *StringRawBuffer; // rax
  char v23; // r8
  WCHAR *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v30; // rax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rax
  int CommitmentContent; // eax
  unsigned int v35; // r14d
  int v36; // eax
  int v37; // eax
  int v38; // eax
  const OLECHAR *v39; // rdi
  __int64 (__fastcall *v40)(const OLECHAR *, PVOID, HSTRING *); // rbx
  char v41; // r8
  HSTRING_HEADER *v42; // rax
  int v43; // eax
  PCWSTR v44; // rax
  const OLECHAR *v45; // rdi
  __int64 (__fastcall *v46)(const OLECHAR *, PVOID, HSTRING *); // rbx
  char v47; // r8
  HSTRING_HEADER *v48; // rax
  int v49; // eax
  const OLECHAR *v50; // rdi
  __int64 (__fastcall *v51)(const OLECHAR *, PVOID, HSTRING *); // rbx
  char v52; // r8
  HSTRING_HEADER *v53; // rax
  int v54; // eax
  const unsigned __int16 *v55; // rbx
  const unsigned __int16 *v56; // rax
  int v57; // eax
  __int64 v58; // rcx
  int v59; // ecx
  int v60; // ecx
  int v61; // ecx
  __int64 v62; // rcx
  __int64 v63; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v66; // [rsp+48h] [rbp-B8h]
  HSTRING_HEADER v67; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v68; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  __int64 v70; // [rsp+80h] [rbp-80h] BYREF
  __int64 v71; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v72)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-70h] BYREF
  __int64 v73; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v74; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v75; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v76; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *String1; // [rsp+B8h] [rbp-48h] BYREF
  const OLECHAR *v78; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v79; // [rsp+C8h] [rbp-38h] BYREF
  struct AsyncMediaServiceContent *v80; // [rsp+D0h] [rbp-30h] BYREF
  int v81; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING v82; // [rsp+E0h] [rbp-20h] BYREF
  _WORD *v83; // [rsp+E8h] [rbp-18h]
  __int16 v84; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v85; // [rsp+F2h] [rbp-Eh]
  int v86; // [rsp+FAh] [rbp-6h]
  __int16 v87; // [rsp+FEh] [rbp-2h]
  unsigned int v88; // [rsp+100h] [rbp+0h] BYREF
  __int64 v89; // [rsp+108h] [rbp+8h] BYREF

  *a3 = 0;
  v5 = *(_QWORD *)a2;
  v89 = 0;
  v7 = (*(__int64 (__fastcall **)(struct ISmMessage *, __int64 *))(v5 + 720))(a2, &v89);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v82 = (HSTRING)&v84;
    v85 = 0;
    v83 = &v84;
    v86 = 0;
    v87 = 0;
    v84 = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             &v82,
                             v89) )
    {
      v8 = -2147024882;
      Log_HREvent_69(-2147024882);
LABEL_5:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v82);
      goto LABEL_76;
    }
    if ( v82 == (HSTRING)v83 )
    {
LABEL_75:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v82);
      v8 = 0;
      goto LABEL_76;
    }
    v68 = 0;
    v66 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ActivationFactory = RoGetActivationFactory(v66, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v68);
    v8 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      Log_HREvent_69(ActivationFactory);
      v11 = v68;
      if ( v68 )
      {
        v68 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      goto LABEL_5;
    }
    v12 = v68;
    v71 = 0;
    v76 = v82;
    v13 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v68 + 48LL);
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&v76, v10);
    v15 = v13(v12, v14[1].Reserved.Reserved1, &v71);
    v8 = v15;
    if ( v15 < 0 )
    {
      Log_HREvent_69(v15);
      goto LABEL_12;
    }
    v17 = v71;
    string = 0;
    v18 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v71 + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800FD778,
            v19);
    v21 = v18(v17, v20[1].Reserved.Reserved1, &string);
    v8 = v21;
    if ( v21 < 0 )
    {
      Log_HREvent_69(v21);
LABEL_16:
      WindowsDeleteString(string);
      string = 0;
LABEL_12:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
      v16 = v68;
      if ( v68 )
      {
        v68 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      goto LABEL_5;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( _wcsicmp(L"1.0", StringRawBuffer) )
    {
      if ( (unsigned int)dword_1800FD5F0 > 3 )
      {
        v24 = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
        v78 = L"1.0";
        v76 = (HSTRING)v24;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v25,
          (int)&unk_1800F2150,
          v26,
          v27,
          &v78,
          (const OLECHAR **)&v76);
      }
LABEL_73:
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
      v63 = v68;
      if ( v68 )
      {
        v68 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      }
      goto LABEL_75;
    }
    v28 = v71;
    v72 = 0;
    v29 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD))(*(_QWORD *)v71 + 72LL);
    v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_1800FD768,
            v23);
    v31 = v29(v28, v30[1].Reserved.Reserved1, &v72);
    v8 = v31;
    if ( v31 >= 0 )
    {
      v73 = 0;
      v32 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
              &v72,
              (__int64)&v73);
      v8 = v32;
      if ( v32 < 0
        || (v88 = 0,
            v32 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v73 + 56LL))(v73, &v88),
            v8 = v32,
            v32 < 0) )
      {
        Log_HREvent_69(v32);
      }
      else
      {
        v33 = *(_QWORD *)a2;
        v75 = 0;
        CommitmentContent = (*(__int64 (__fastcall **)(struct ISmMessage *, __int64 *))(v33 + 240))(a2, &v75);
        v8 = CommitmentContent;
        if ( CommitmentContent >= 0 )
        {
          v35 = 0;
          v81 = 0;
          while ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v75 + 24LL))(v75) )
          {
            v70 = 0;
            v36 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v75 + 32LL))(v75, &v70);
            v8 = v36;
            if ( v36 < 0 )
            {
              Log_HREvent_69(v36);
              goto LABEL_69;
            }
            String1 = 0;
            v37 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v70 + 48LL))(v70, &String1);
            v8 = v37;
            if ( v37 < 0 )
            {
              v61 = v37;
              goto LABEL_66;
            }
            LODWORD(v80) = 0;
            MimeTypeToMediaType(String1, (enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 *)&v80);
            if ( !(_DWORD)v80 )
            {
              v8 = -2147418113;
              goto LABEL_64;
            }
            if ( (_DWORD)v80 != 1 && (_DWORD)v80 != 6 )
            {
              if ( v35 >= v88 )
              {
                v8 = -2147024809;
LABEL_64:
                v61 = v8;
LABEL_66:
                Log_HREvent_69(v61);
                goto LABEL_67;
              }
              v78 = 0;
              v38 = (*v72)[6](v72, (GUID *)v35, (__int64)&v78);
              v8 = v38;
              if ( v38 < 0 )
              {
                Log_HREvent_69(v38);
                goto LABEL_61;
              }
              v39 = v78;
              v74 = 0;
              v40 = *(__int64 (__fastcall **)(const OLECHAR *, PVOID, HSTRING *))(*(_QWORD *)v78 + 80LL);
              WindowsDeleteString(0);
              v74 = 0;
              v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v67,
                      (const WCHAR **)off_1800FD758,
                      v41);
              v43 = v40(v39, v42[1].Reserved.Reserved1, &v74);
              v8 = v43;
              if ( v43 < 0 )
              {
                v60 = v43;
                goto LABEL_58;
              }
              v44 = WindowsGetStringRawBuffer(v74, 0);
              if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                       (char *)this + 24,
                                       v44) )
              {
                v8 = -2147024882;
                v60 = -2147024882;
LABEL_58:
                Log_HREvent_69(v60);
                goto LABEL_59;
              }
              v45 = v78;
              v79 = 0;
              v46 = *(__int64 (__fastcall **)(const OLECHAR *, PVOID, HSTRING *))(*(_QWORD *)v78 + 80LL);
              WindowsDeleteString(0);
              v79 = 0;
              v48 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v67,
                      (const WCHAR **)off_1800FD760,
                      v47);
              v49 = v46(v45, v48[1].Reserved.Reserved1, &v79);
              v8 = v49;
              if ( v49 < 0 )
              {
                Log_HREvent_69(v49);
                goto LABEL_55;
              }
              v50 = v78;
              v76 = 0;
              v51 = *(__int64 (__fastcall **)(const OLECHAR *, PVOID, HSTRING *))(*(_QWORD *)v78 + 80LL);
              WindowsDeleteString(0);
              v76 = 0;
              v53 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v67,
                      (const WCHAR **)off_1800FD750,
                      v52);
              v54 = v51(v50, v53[1].Reserved.Reserved1, &v76);
              v8 = v54;
              if ( v54 < 0 )
              {
                Log_HREvent_69(v54);
                goto LABEL_53;
              }
              v80 = 0;
              v55 = WindowsGetStringRawBuffer(v76, 0);
              v56 = WindowsGetStringRawBuffer(v79, 0);
              v57 = AsyncMediaServiceContent::CreateInstance(v56, v55, &v80);
              v8 = v57;
              if ( v57 < 0 )
              {
                v59 = v57;
LABEL_51:
                Log_HREvent_69(v59);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
LABEL_53:
                WindowsDeleteString(v76);
                v76 = 0;
LABEL_55:
                WindowsDeleteString(v79);
                v79 = 0;
LABEL_59:
                WindowsDeleteString(v74);
                v74 = 0;
LABEL_61:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
LABEL_67:
                tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&String1);
LABEL_69:
                v62 = v70;
                if ( v70 )
                {
                  v70 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                }
                goto LABEL_29;
              }
              if ( !*(_QWORD *)utl::_HashTable<unsigned int,utl::pair<unsigned int const,ATL::CComPtr<AsyncMediaServiceContent>>,utl::hash<unsigned int>,utl::equal_to<unsigned int>,utl::allocator<utl::pair<unsigned int const,ATL::CComPtr<AsyncMediaServiceContent>>>,0>::emplace<unsigned int &,ATL::CComPtr<AsyncMediaServiceContent> &,0>(
                                 (__int64)this + 56,
                                 (__int64)&hstringHeader,
                                 &v81,
                                 &v80) )
              {
                v8 = -2147024882;
                v59 = -2147024882;
                goto LABEL_51;
              }
              ++v35;
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
              WindowsDeleteString(v76);
              v76 = 0;
              WindowsDeleteString(v79);
              v79 = 0;
              WindowsDeleteString(v74);
              v74 = 0;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
            }
            tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&String1);
            v58 = v70;
            if ( v70 )
            {
              v70 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
            }
            ++v81;
          }
          CommitmentContent = AsyncMediaServiceDocument::_GenerateCommitmentContent(this);
          v8 = CommitmentContent;
          if ( CommitmentContent < 0 )
            goto LABEL_28;
          *a3 = 1;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
          goto LABEL_73;
        }
LABEL_28:
        Log_HREvent_69(CommitmentContent);
LABEL_29:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    }
    else
    {
      Log_HREvent_69(v31);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
    goto LABEL_16;
  }
  Log_HREvent_69(v7);
LABEL_76:
  tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v89);
  return v8;
}

```

## disassembly

```asm
0x180097d60  mov     [rsp-8+arg_18], rbx
0x180097d65  push    rbp
0x180097d66  push    rsi
0x180097d67  push    rdi
0x180097d68  push    r12
0x180097d6a  push    r13
0x180097d6c  push    r14
0x180097d6e  push    r15
0x180097d70  lea     rbp, [rsp-20h]
0x180097d75  sub     rsp, 120h
0x180097d7c  mov     rax, cs:__security_cookie
0x180097d83  xor     rax, rsp
0x180097d86  mov     [rbp+50h+var_40], rax
0x180097d8a  mov     rsi, rdx
0x180097d8d  xor     r13d, r13d
0x180097d90  mov     [r8], r13d
0x180097d93  mov     r15, rcx
0x180097d96  mov     rax, [rdx]
0x180097d99  mov     rcx, rsi
0x180097d9c  lea     rdx, [rbp+50h+var_48]
0x180097da0  mov     [rbp+50h+var_48], r13
0x180097da4  mov     r12, r8
0x180097da7  mov     rax, [rax+2D0h]
0x180097dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097db3  mov     ebx, eax
0x180097db5  test    eax, eax
0x180097db7  jns     short loc_180097DCF
0x180097db9  lea     edx, [r13+1]
0x180097dbd  mov     r9d, 0BAh
0x180097dc3  mov     ecx, eax; int
0x180097dc5  call    Log_HREvent_69
0x180097dca  jmp     loc_1800984FA
0x180097dcf  mov     rdx, [rbp+50h+var_48]
0x180097dd3  lea     rax, [rbp+50h+var_60]
0x180097dd7  mov     [rbp+50h+var_70], rax
0x180097ddb  lea     rcx, [rbp+50h+var_70]
0x180097ddf  lea     rax, [rbp+50h+var_60]
0x180097de3  mov     [rbp+50h+var_5E], r13
0x180097de7  mov     [rbp+50h+var_68], rax
0x180097deb  mov     [rbp+50h+var_56], r13d
0x180097def  mov     [rbp+50h+var_52], r13w
0x180097df4  mov     [rbp+50h+var_60], r13w
0x180097df9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180097dfe  test    al, al
0x180097e00  jnz     short loc_180097E24
0x180097e02  mov     ebx, 8007000Eh
0x180097e07  xor     edx, edx
0x180097e09  mov     ecx, ebx; int
0x180097e0b  mov     r9d, 0BCh
0x180097e11  call    Log_HREvent_69
0x180097e16  lea     rcx, [rbp+50h+var_70]
0x180097e1a  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180097e1f  jmp     loc_1800984FA
0x180097e24  mov     rax, [rbp+50h+var_68]
0x180097e28  cmp     [rbp+50h+var_70], rax
0x180097e2c  jz      loc_1800984EE
0x180097e32  mov     r9d, 1Ch; unsigned int
0x180097e38  mov     [rsp+150h+var_E0], r13
0x180097e3d  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180097e44  mov     [rsp+150h+var_108], r13
0x180097e49  lea     rcx, [rsp+150h+hstringHeader]; hstringHeader
0x180097e4e  lea     r8d, [r9+1]; unsigned int
0x180097e52  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180097e57  mov     rcx, [rsp+150h+var_108]
0x180097e5c  lea     r8, [rsp+150h+var_E0]
0x180097e61  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180097e68  call    cs:__imp_RoGetActivationFactory
0x180097e6e  mov     ebx, eax
0x180097e70  test    eax, eax
0x180097e72  jns     short loc_180097EA9
0x180097e74  mov     edx, 1
0x180097e79  mov     r9d, 0C6h
0x180097e7f  mov     ecx, eax; int
0x180097e81  call    Log_HREvent_69
0x180097e86  mov     rdx, [rsp+150h+var_E0]
0x180097e8b  test    rdx, rdx
0x180097e8e  jz      short loc_180097E16
0x180097e90  mov     [rsp+150h+var_E0], r13
0x180097e95  mov     rcx, [rdx]
0x180097e98  mov     rax, [rcx+10h]
0x180097e9c  mov     rcx, rdx
0x180097e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ea4  jmp     loc_180097E16
0x180097ea9  mov     rcx, [rbp+50h+var_70]
0x180097ead  lea     rdx, [rbp+50h+var_A0]
0x180097eb1  mov     rdi, [rsp+150h+var_E0]
0x180097eb6  mov     [rbp+50h+var_C8], r13
0x180097eba  mov     [rbp+50h+var_A0], rcx
0x180097ebe  lea     rcx, [rsp+150h+hstringHeader]
0x180097ec3  mov     rax, [rdi]
0x180097ec6  mov     rbx, [rax+30h]
0x180097eca  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180097ecf  lea     r8, [rbp+50h+var_C8]
0x180097ed3  mov     rcx, rdi
0x180097ed6  mov     rdx, [rax+18h]
0x180097eda  mov     rax, rbx
0x180097edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ee2  mov     ebx, eax
0x180097ee4  test    eax, eax
0x180097ee6  jns     short loc_180097F1F
0x180097ee8  mov     edx, 1
0x180097eed  mov     r9d, 0C9h
0x180097ef3  mov     ecx, eax; int
0x180097ef5  call    Log_HREvent_69
0x180097efa  lea     rcx, [rbp+50h+var_C8]
0x180097efe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097f03  mov     rcx, [rsp+150h+var_E0]
0x180097f08  test    rcx, rcx
0x180097f0b  jz      loc_180097E16
0x180097f11  mov     [rsp+150h+var_E0], r13
0x180097f16  mov     rax, [rcx]
0x180097f19  mov     rax, [rax+10h]
0x180097f1d  jmp     short loc_180097E9F
0x180097f1f  mov     rdi, [rbp+50h+var_C8]
0x180097f23  xor     ecx, ecx; string
0x180097f25  mov     [rsp+150h+string], r13
0x180097f2a  mov     rax, [rdi]
0x180097f2d  mov     rbx, [rax+50h]
0x180097f31  call    cs:__imp_WindowsDeleteString
0x180097f37  lea     rdx, off_1800FD778; "version"
0x180097f3e  mov     [rsp+150h+string], r13
0x180097f43  lea     rcx, [rsp+150h+hstringHeader]
0x180097f48  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180097f4d  lea     r8, [rsp+150h+string]
0x180097f52  mov     rcx, rdi
0x180097f55  mov     rdx, [rax+18h]
0x180097f59  mov     rax, rbx
0x180097f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f61  mov     ebx, eax
0x180097f63  test    eax, eax
0x180097f65  jns     short loc_180097F8E
0x180097f67  mov     edx, 1
0x180097f6c  mov     r9d, 0CDh
0x180097f72  mov     ecx, eax; int
0x180097f74  call    Log_HREvent_69
0x180097f79  mov     rcx, [rsp+150h+string]; string
0x180097f7e  call    cs:__imp_WindowsDeleteString
0x180097f84  mov     [rsp+150h+string], r13
0x180097f89  jmp     loc_180097EFA
0x180097f8e  mov     rcx, [rsp+150h+string]; string
0x180097f93  xor     edx, edx; length
0x180097f95  call    cs:__imp_WindowsGetStringRawBuffer
0x180097f9b  lea     rbx, a10; "1.0"
0x180097fa2  mov     rdx, rax; String2
0x180097fa5  mov     rcx, rbx; String1
0x180097fa8  call    cs:__imp__wcsicmp
0x180097fae  test    eax, eax
0x180097fb0  jz      short loc_180097FF9
0x180097fb2  mov     eax, cs:dword_1800FD5F0
0x180097fb8  cmp     eax, 3
0x180097fbb  jbe     loc_1800984BA
0x180097fc1  mov     rcx, [rsp+150h+string]; string
0x180097fc6  xor     edx, edx; length
0x180097fc8  call    cs:__imp_WindowsGetStringRawBuffer
0x180097fce  lea     rdx, unk_1800F2150
0x180097fd5  mov     [rbp+50h+var_90], rbx
0x180097fd9  mov     [rbp+50h+var_A0], rax
0x180097fdd  lea     rax, [rbp+50h+var_A0]
0x180097fe1  mov     [rsp+150h+var_128], rax
0x180097fe6  lea     rax, [rbp+50h+var_90]
0x180097fea  mov     [rsp+150h+var_130], rax
0x180097fef  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180097ff4  jmp     loc_1800984BA
0x180097ff9  mov     rdi, [rbp+50h+var_C8]
0x180097ffd  lea     rdx, off_1800FD768; "mediacontentlist"
0x180098004  mov     [rbp+50h+var_C0], r13
0x180098008  lea     rcx, [rsp+150h+hstringHeader]
0x18009800d  mov     rax, [rdi]
0x180098010  mov     rbx, [rax+48h]
0x180098014  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180098019  lea     r8, [rbp+50h+var_C0]
0x18009801d  mov     rcx, rdi
0x180098020  mov     rdx, [rax+18h]
0x180098024  mov     rax, rbx
0x180098027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009802c  mov     ebx, eax
0x18009802e  test    eax, eax
0x180098030  jns     short loc_180098052
0x180098032  mov     edx, 1
0x180098037  mov     r9d, 0DEh
0x18009803d  mov     ecx, eax; int
0x18009803f  call    Log_HREvent_69
0x180098044  lea     rcx, [rbp+50h+var_C0]
0x180098048  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009804d  jmp     loc_180097F79
0x180098052  lea     rdx, [rbp+50h+var_B8]
0x180098056  mov     [rbp+50h+var_B8], r13
0x18009805a  lea     rcx, [rbp+50h+var_C0]
0x18009805e  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x180098063  mov     ebx, eax
0x180098065  test    eax, eax
0x180098067  jns     short loc_180098086
0x180098069  mov     r9d, 0E1h
0x18009806f  mov     edx, 1
0x180098074  mov     ecx, eax; int
0x180098076  call    Log_HREvent_69
0x18009807b  lea     rcx, [rbp+50h+var_B8]
0x18009807f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098084  jmp     short loc_180098044
0x180098086  mov     rcx, [rbp+50h+var_B8]
0x18009808a  lea     rdx, [rbp+50h+var_50]
0x18009808e  mov     [rbp+50h+var_50], r13d
0x180098092  mov     rax, [rcx]
0x180098095  mov     rax, [rax+38h]
0x180098099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009809e  mov     ebx, eax
0x1800980a0  test    eax, eax
0x1800980a2  jns     short loc_1800980AC
0x1800980a4  mov     r9d, 0E4h
0x1800980aa  jmp     short loc_18009806F
0x1800980ac  mov     rax, [rsi]
0x1800980af  lea     rdx, [rbp+50h+var_A8]
0x1800980b3  mov     rcx, rsi
0x1800980b6  mov     [rbp+50h+var_A8], r13
0x1800980ba  mov     rax, [rax+0F0h]
0x1800980c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800980c6  mov     ebx, eax
0x1800980c8  test    eax, eax
0x1800980ca  jns     short loc_1800980E9
0x1800980cc  mov     edx, 1
0x1800980d1  mov     r9d, 0EBh
0x1800980d7  mov     ecx, eax; int
0x1800980d9  call    Log_HREvent_69
0x1800980de  lea     rcx, [rbp+50h+var_A8]
0x1800980e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800980e7  jmp     short loc_18009807B
0x1800980e9  mov     r14d, r13d
0x1800980ec  mov     [rbp+50h+var_78], r13d
0x1800980f0  mov     esi, 1
0x1800980f5  mov     rcx, [rbp+50h+var_A8]
0x1800980f9  mov     rax, [rcx]
0x1800980fc  mov     rax, [rax+18h]
0x180098100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098105  test    eax, eax
0x180098107  jnz     loc_180098480
0x18009810d  mov     rcx, [rbp+50h+var_A8]
0x180098111  lea     rdx, [rbp+50h+var_D0]
0x180098115  mov     [rbp+50h+var_D0], r13
0x180098119  mov     rax, [rcx]
0x18009811c  mov     rax, [rax+20h]
0x180098120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098125  mov     ebx, eax
0x180098127  test    eax, eax
0x180098129  js      loc_18009844F
0x18009812f  mov     rcx, [rbp+50h+var_D0]
0x180098133  lea     rdx, [rbp+50h+String1]
0x180098137  mov     [rbp+50h+String1], r13
0x18009813b  mov     rax, [rcx]
0x18009813e  mov     rax, [rax+30h]
0x180098142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098147  mov     ebx, eax
0x180098149  test    eax, eax
0x18009814b  js      loc_180098435
0x180098151  mov     rcx, [rbp+50h+String1]; String1
0x180098155  lea     rdx, [rbp+50h+var_80]; enum Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 *
0x180098159  mov     dword ptr [rbp+50h+var_80], r13d
0x18009815d  call    ?MimeTypeToMediaType@@YAXPEBGPEAW4__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008@Messaging@@@Z; MimeTypeToMediaType(ushort const *,Messaging::__MIDL___MIDL_itf_messagingdatamodel_0000_0000_0008 *)
0x180098162  mov     eax, dword ptr [rbp+50h+var_80]
0x180098165  test    eax, eax
0x180098167  jz      loc_180098424
0x18009816d  cmp     eax, esi
0x18009816f  jz      loc_18009833A
0x180098175  cmp     eax, 6
0x180098178  jz      loc_18009833A
0x18009817e  cmp     r14d, [rbp+50h+var_50]
0x180098182  jnb     loc_180098417
0x180098188  mov     rcx, [rbp+50h+var_C0]
0x18009818c  lea     r8, [rbp+50h+var_90]
0x180098190  mov     [rbp+50h+var_90], r13
0x180098194  mov     edx, r14d
0x180098197  mov     rax, [rcx]
0x18009819a  mov     rax, [rax+30h]
0x18009819e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800981a3  mov     ebx, eax
0x1800981a5  test    eax, eax
0x1800981a7  js      loc_1800983FD
0x1800981ad  mov     rdi, [rbp+50h+var_90]
0x1800981b1  xor     ecx, ecx; string
0x1800981b3  mov     [rbp+50h+var_B0], r13
0x1800981b7  mov     rax, [rdi]
0x1800981ba  mov     rbx, [rax+50h]
0x1800981be  call    cs:__imp_WindowsDeleteString
0x1800981c4  lea     rdx, off_1800FD758; "documentid"
0x1800981cb  mov     [rbp+50h+var_B0], r13
0x1800981cf  lea     rcx, [rsp+150h+var_100]
0x1800981d4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800981d9  lea     r8, [rbp+50h+var_B0]
0x1800981dd  mov     rcx, rdi
0x1800981e0  mov     rdx, [rax+18h]
0x1800981e4  mov     rax, rbx
0x1800981e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800981ec  mov     ebx, eax
0x1800981ee  test    eax, eax
0x1800981f0  js      loc_1800983DE
0x1800981f6  mov     rcx, [rbp+50h+var_B0]; string
0x1800981fa  xor     edx, edx; length
0x1800981fc  call    cs:__imp_WindowsGetStringRawBuffer
0x180098202  mov     rdx, rax
0x180098205  lea     rcx, [r15+18h]
0x180098209  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
  ... truncated ...
```
