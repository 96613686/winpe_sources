# WritePtElement(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *)

- ea: `0x18001f0dc`
- end: `0x18001f5a9`
- name: `?WritePtElement@@YAJPEAUIXmlWriter@@PEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z`
- size: `1229`
- prototype: `__int64 __fastcall(struct IXmlWriter *, struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006f6e4`

## callees

- `0x180002958`
- `0x18001f0dc`
- `0x180037b90`
- `0x18006e360`
- `0x18006e3cc`
- `0x180073a54`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f23d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f23d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WritePtElement(
        struct IXmlWriter *a1,
        struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *a2)
{
  int v4; // edi
  __int64 v5; // r8
  __int64 (__fastcall *v6)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, __int64 *); // rbx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, HSTRING *); // rbx
  HRESULT (__stdcall *WriteElementString)(IXmlWriter *, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  int (__fastcall *v11)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, _QWORD *); // rbx
  unsigned int i; // r14d
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, _QWORD, struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage **); // rbx
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *v15; // rcx
  unsigned int j; // r14d
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, _QWORD, struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage **); // rbx
  const unsigned __int16 *v19; // r8
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *v20; // rcx
  __int64 v21; // rcx
  int v23; // [rsp+30h] [rbp-20h] BYREF
  int v24; // [rsp+34h] [rbp-1Ch] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *v25; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-10h] BYREF
  HSTRING string; // [rsp+90h] [rbp+40h] BYREF
  __int64 v28; // [rsp+98h] [rbp+48h] BYREF

  v4 = WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(
         (__int64)a1,
         (__int64)a2,
         (__int64 (__fastcall *)(__int64, HSTRING *)) Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData::`vcall'{64,{flat}},
         (__int64)L"pfn");
  if ( v4 >= 0 )
  {
    v4 = WriteBoolElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData>(
           (__int64)a1,
           (__int64)a2,
           v5);
    if ( v4 >= 0 )
    {
      v4 = WriteI64Element<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData>(
             (__int64)a1,
             (__int64)a2);
      if ( v4 >= 0 )
      {
        v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a1->lpVtbl->WriteStartElement)(
               a1,
               0,
               L"ats",
               0);
        if ( v4 >= 0 )
        {
          v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a1->lpVtbl->WriteStartElement)(
                 a1,
                 0,
                 L"at",
                 0);
          if ( v4 >= 0 )
          {
            v4 = WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(
                   (__int64)a1,
                   (__int64)a2,
                   (__int64 (__fastcall *)(__int64, HSTRING *)) Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData::`vcall'{128,{flat}},
                   (__int64)L"n");
            if ( v4 >= 0 )
            {
              v4 = WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(
                     (__int64)a1,
                     (__int64)a2,
                     (__int64 (__fastcall *)(__int64, HSTRING *)) Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData::`vcall'{128,{flat}},
                     (__int64)L"sn");
              if ( v4 >= 0 )
              {
                v28 = 0;
                v6 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, __int64 *))(*(_QWORD *)a2 + 96LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
                v4 = v6(a2, &v28);
                if ( v4 >= 0 )
                {
                  string = 0;
                  v7 = v28;
                  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v28 + 48LL);
                  WindowsDeleteString(0);
                  string = 0;
                  v4 = v8(v7, 0, &string);
                  if ( v4 >= 0 )
                  {
                    WriteElementString = a1->lpVtbl->WriteElementString;
                    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                    v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD, PCWSTR))WriteElementString)(
                           a1,
                           0,
                           L"mai",
                           0,
                           StringRawBuffer);
                  }
                  WindowsDeleteString(string);
                }
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
                if ( v4 >= 0 )
                {
                  v26[0] = 0;
                  LODWORD(string) = 0;
                  v11 = *(int (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, _QWORD *))(*(_QWORD *)a2 + 136LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v26);
                  if ( v11(a2, v26) >= 0
                    && (*(int (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)v26[0] + 56LL))(v26[0], &string) >= 0 )
                  {
                    for ( i = 0; i < (unsigned int)string; ++i )
                    {
                      v25 = 0;
                      v23 = 0;
                      v24 = 0;
                      LODWORD(v28) = 0;
                      v13 = v26[0];
                      v14 = *(int (__fastcall **)(__int64, _QWORD, struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage **))(*(_QWORD *)v26[0] + 48LL);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
                      if ( v14(v13, i, &v25) >= 0
                        && (*(int (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *, int *))(*(_QWORD *)v25 + 56LL))(
                             v25,
                             &v23) >= 0
                        && (*(int (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *, int *))(*(_QWORD *)v25 + 64LL))(
                             v25,
                             &v24) >= 0
                        && (*(int (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *, __int64 *))(*(_QWORD *)v25 + 48LL))(
                             v25,
                             &v28) >= 0
                        && (_DWORD)v28 == 1
                        && v23 == 90
                        && v24 == 90 )
                      {
                        WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(
                          (__int64)a1,
                          (__int64)v25,
                          (__int64 (__fastcall *)(__int64, HSTRING *)) Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::`vcall'{72,{flat}},
                          (__int64)L"bg");
                        WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(
                          (__int64)a1,
                          (__int64)v25,
                          (__int64 (__fastcall *)(__int64, HSTRING *)) Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::`vcall'{80,{flat}},
                          (__int64)L"fg");
                        WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(
                          (__int64)a1,
                          (__int64)v25,
                          (__int64 (__fastcall *)(__int64, HSTRING *)) Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::`vcall'{88,{flat}},
                          (__int64)L"logo");
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
                        break;
                      }
                      v15 = v25;
                      if ( v25 )
                      {
                        v25 = 0;
                        (*(void (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *))(*(_QWORD *)v15 + 16LL))(v15);
                      }
                    }
                    v4 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const wchar_t *, _QWORD))a1->lpVtbl->WriteStartElement)(
                           a1,
                           0,
                           L"imgs",
                           0);
                    if ( v4 >= 0 )
                    {
                      for ( j = 0; j < (unsigned int)string; ++j )
                      {
                        v25 = 0;
                        v23 = 0;
                        LODWORD(v28) = 0;
                        v24 = 0;
                        v17 = v26[0];
                        v18 = *(int (__fastcall **)(__int64, _QWORD, struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage **))(*(_QWORD *)v26[0] + 48LL);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
                        if ( v18(v17, j, &v25) < 0
                          || (*(int (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *, int *))(*(_QWORD *)v25 + 56LL))(
                               v25,
                               &v23) < 0
                          || (*(int (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *, __int64 *))(*(_QWORD *)v25 + 64LL))(
                               v25,
                               &v28) < 0
                          || (*(int (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *, int *))(*(_QWORD *)v25 + 48LL))(
                               v25,
                               &v24) < 0
                          || v24 )
                        {
                          goto LABEL_48;
                        }
                        if ( v23 == 150 )
                        {
                          if ( (_DWORD)v28 == 150 )
                          {
                            v19 = L"1";
LABEL_47:
                            WriteImgNode(a1, v25, v19);
                          }
                        }
                        else
                        {
                          if ( v23 != 310 )
                          {
                            if ( v23 != 70 || (_DWORD)v28 != 70 )
                              goto LABEL_48;
                            v19 = L"4";
                            goto LABEL_47;
                          }
                          if ( (_DWORD)v28 == 150 )
                          {
                            v19 = L"3";
                            goto LABEL_47;
                          }
                          if ( (_DWORD)v28 == 310 )
                          {
                            v19 = L"5";
                            goto LABEL_47;
                          }
                        }
LABEL_48:
                        v20 = v25;
                        if ( v25 )
                        {
                          v25 = 0;
                          (*(void (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *))(*(_QWORD *)v20 + 16LL))(v20);
                        }
                      }
                      v4 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteEndElement)(a1);
                    }
                  }
                  v21 = v26[0];
                  if ( v26[0] )
                  {
                    v26[0] = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                  }
                  if ( v4 >= 0 )
                  {
                    v4 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteEndElement)(a1);
                    if ( v4 >= 0 )
                      return ((unsigned int (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteEndElement)(a1);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f0dc  mov     [rsp-28h+arg_0], rbx
0x18001f0e1  push    rbp
0x18001f0e2  push    rsi
0x18001f0e3  push    rdi
0x18001f0e4  push    r14
0x18001f0e6  push    r15
0x18001f0e8  mov     rbp, rsp
0x18001f0eb  sub     rsp, 50h
0x18001f0ef  mov     r14, rdx
0x18001f0f2  mov     rsi, rcx
0x18001f0f5  lea     r9, aPfn_0; "pfn"
0x18001f0fc  lea     r8, ??_9IAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@$BEA@AA; [thunk]: Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData::`vcall'{64,{flat}}
0x18001f103  call    ??$WriteStringElement@UIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@@YAJPEAUIXmlWriter@@PEAUIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJPEAPEAUHSTRING__@@@ZPEBG@Z; WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *,long (Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::*)(HSTRING__ * *),ushort const *)
0x18001f108  mov     edi, eax
0x18001f10a  xor     r15d, r15d
0x18001f10d  test    eax, eax
0x18001f10f  js      loc_18001F593
0x18001f115  mov     rdx, r14
0x18001f118  mov     rcx, rsi
0x18001f11b  call    ??$WriteBoolElement@UIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@@YAJPEAUIXmlWriter@@PEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJPEAE@ZPEBG@Z; WriteBoolElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData>(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,long (Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData::*)(uchar *),ushort const *)
0x18001f120  mov     edi, eax
0x18001f122  test    eax, eax
0x18001f124  js      loc_18001F593
0x18001f12a  mov     rdx, r14
0x18001f12d  mov     rcx, rsi
0x18001f130  call    ??$WriteI64Element@UIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@@YAJPEAUIXmlWriter@@PEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJPEA_K@ZPEBG@Z; WriteI64Element<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData>(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,long (Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData::*)(unsigned __int64 *),ushort const *)
0x18001f135  mov     edi, eax
0x18001f137  test    eax, eax
0x18001f139  js      loc_18001F593
0x18001f13f  mov     rax, [rsi]
0x18001f142  xor     r9d, r9d
0x18001f145  lea     r8, aAts; "ats"
0x18001f14c  xor     edx, edx
0x18001f14e  mov     rcx, rsi
0x18001f151  mov     rax, [rax+0D8h]
0x18001f158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f15d  mov     edi, eax
0x18001f15f  test    eax, eax
0x18001f161  js      loc_18001F593
0x18001f167  mov     rax, [rsi]
0x18001f16a  xor     r9d, r9d
0x18001f16d  lea     r8, aAt; "at"
0x18001f174  xor     edx, edx
0x18001f176  mov     rcx, rsi
0x18001f179  mov     rax, [rax+0D8h]
0x18001f180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f185  mov     edi, eax
0x18001f187  test    eax, eax
0x18001f189  js      loc_18001F593
0x18001f18f  lea     r9, aN; "n"
0x18001f196  lea     r8, ??_9IAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@$BIA@AA; [thunk]: Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData::`vcall'{128,{flat}}
0x18001f19d  mov     rdx, r14
0x18001f1a0  mov     rcx, rsi
0x18001f1a3  call    ??$WriteStringElement@UIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@@YAJPEAUIXmlWriter@@PEAUIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJPEAPEAUHSTRING__@@@ZPEBG@Z; WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *,long (Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::*)(HSTRING__ * *),ushort const *)
0x18001f1a8  mov     edi, eax
0x18001f1aa  test    eax, eax
0x18001f1ac  js      loc_18001F593
0x18001f1b2  lea     r9, aSn_0; "sn"
0x18001f1b9  lea     r8, ??_9IAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@$BIA@AA; [thunk]: Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData::`vcall'{128,{flat}}
0x18001f1c0  mov     rdx, r14
0x18001f1c3  mov     rcx, rsi
0x18001f1c6  call    ??$WriteStringElement@UIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@@YAJPEAUIXmlWriter@@PEAUIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJPEAPEAUHSTRING__@@@ZPEBG@Z; WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *,long (Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::*)(HSTRING__ * *),ushort const *)
0x18001f1cb  mov     edi, eax
0x18001f1cd  test    eax, eax
0x18001f1cf  js      loc_18001F593
0x18001f1d5  mov     [rbp+arg_18], r15
0x18001f1d9  mov     rax, [r14]
0x18001f1dc  mov     rbx, [rax+60h]
0x18001f1e0  lea     rcx, [rbp+arg_18]
0x18001f1e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f1e9  lea     rdx, [rbp+arg_18]
0x18001f1ed  mov     rcx, r14
0x18001f1f0  mov     rax, rbx
0x18001f1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1f8  mov     edi, eax
0x18001f1fa  test    eax, eax
0x18001f1fc  js      short loc_18001F26C
0x18001f1fe  mov     [rbp+string], r15
0x18001f202  mov     rdi, [rbp+arg_18]
0x18001f206  mov     rax, [rdi]
0x18001f209  mov     rbx, [rax+30h]
0x18001f20d  xor     ecx, ecx; string
0x18001f20f  call    cs:__imp_WindowsDeleteString
0x18001f215  mov     [rbp+string], r15
0x18001f219  lea     r8, [rbp+string]
0x18001f21d  xor     edx, edx
0x18001f21f  mov     rcx, rdi
0x18001f222  mov     rax, rbx
0x18001f225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f22a  mov     edi, eax
0x18001f22c  test    eax, eax
0x18001f22e  js      short loc_18001F261
0x18001f230  mov     rax, [rsi]
0x18001f233  mov     rbx, [rax+68h]
0x18001f237  xor     edx, edx; length
0x18001f239  mov     rcx, [rbp+string]; string
0x18001f23d  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f243  mov     [rsp+50h+var_30], rax
0x18001f248  xor     r9d, r9d
0x18001f24b  lea     r8, aMai; "mai"
0x18001f252  xor     edx, edx
0x18001f254  mov     rcx, rsi
0x18001f257  mov     rax, rbx
0x18001f25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f25f  mov     edi, eax
0x18001f261  mov     rcx, [rbp+string]; string
0x18001f265  call    cs:__imp_WindowsDeleteString
0x18001f26b  nop
0x18001f26c  lea     rcx, [rbp+arg_18]
0x18001f270  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f275  test    edi, edi
0x18001f277  js      loc_18001F593
0x18001f27d  mov     [rbp+var_10], r15
0x18001f281  mov     dword ptr [rbp+string], r15d
0x18001f285  mov     rax, [r14]
0x18001f288  mov     rbx, [rax+88h]
0x18001f28f  lea     rcx, [rbp+var_10]
0x18001f293  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f298  lea     rdx, [rbp+var_10]
0x18001f29c  mov     rcx, r14
0x18001f29f  mov     rax, rbx
0x18001f2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2a7  test    eax, eax
0x18001f2a9  js      loc_18001F54F
0x18001f2af  mov     rcx, [rbp+var_10]
0x18001f2b3  mov     rax, [rcx]
0x18001f2b6  lea     rdx, [rbp+string]
0x18001f2ba  mov     rax, [rax+38h]
0x18001f2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2c3  test    eax, eax
0x18001f2c5  js      loc_18001F54F
0x18001f2cb  mov     r14d, r15d
0x18001f2ce  cmp     r14d, dword ptr [rbp+string]
0x18001f2d2  jnb     loc_18001F3E6
0x18001f2d8  mov     [rbp+var_18], r15
0x18001f2dc  mov     [rbp+var_20], r15d
0x18001f2e0  mov     [rbp+var_1C], r15d
0x18001f2e4  mov     dword ptr [rbp+arg_18], r15d
0x18001f2e8  mov     rdi, [rbp+var_10]
0x18001f2ec  mov     rax, [rdi]
0x18001f2ef  mov     rbx, [rax+30h]
0x18001f2f3  lea     rcx, [rbp+var_18]
0x18001f2f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f2fc  lea     r8, [rbp+var_18]
0x18001f300  mov     edx, r14d
0x18001f303  mov     rcx, rdi
0x18001f306  mov     rax, rbx
0x18001f309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f30e  test    eax, eax
0x18001f310  js      short loc_18001F36C
0x18001f312  mov     rcx, [rbp+var_18]
0x18001f316  mov     rax, [rcx]
0x18001f319  lea     rdx, [rbp+var_20]
0x18001f31d  mov     rax, [rax+38h]
0x18001f321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f326  test    eax, eax
0x18001f328  js      short loc_18001F36C
0x18001f32a  mov     rcx, [rbp+var_18]
0x18001f32e  mov     rax, [rcx]
0x18001f331  lea     rdx, [rbp+var_1C]
0x18001f335  mov     rax, [rax+40h]
0x18001f339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f33e  test    eax, eax
0x18001f340  js      short loc_18001F36C
0x18001f342  mov     rcx, [rbp+var_18]
0x18001f346  mov     rax, [rcx]
0x18001f349  lea     rdx, [rbp+arg_18]
0x18001f34d  mov     rax, [rax+30h]
0x18001f351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f356  test    eax, eax
0x18001f358  js      short loc_18001F36C
0x18001f35a  cmp     dword ptr [rbp+arg_18], 1
0x18001f35e  jnz     short loc_18001F36C
0x18001f360  cmp     [rbp+var_20], 5Ah ; 'Z'
0x18001f364  jnz     short loc_18001F36C
0x18001f366  cmp     [rbp+var_1C], 5Ah ; 'Z'
0x18001f36a  jz      short loc_18001F38E
0x18001f36c  mov     rcx, [rbp+var_18]
0x18001f370  test    rcx, rcx
0x18001f373  jz      short loc_18001F386
0x18001f375  mov     [rbp+var_18], r15
0x18001f379  mov     rax, [rcx]
0x18001f37c  mov     rax, [rax+10h]
0x18001f380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f385  nop
0x18001f386  inc     r14d
0x18001f389  jmp     loc_18001F2CE
0x18001f38e  lea     r9, aBg_0; "bg"
0x18001f395  lea     r8, ??_9IAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@$BEI@AA; [thunk]: Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::`vcall'{72,{flat}}
0x18001f39c  mov     rdx, [rbp+var_18]
0x18001f3a0  mov     rcx, rsi
0x18001f3a3  call    ??$WriteStringElement@UIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@@YAJPEAUIXmlWriter@@PEAUIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJPEAPEAUHSTRING__@@@ZPEBG@Z; WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *,long (Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::*)(HSTRING__ * *),ushort const *)
0x18001f3a8  lea     r9, aFg_0; "fg"
0x18001f3af  lea     r8, ??_9IAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@$BFA@AA; [thunk]: Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::`vcall'{80,{flat}}
0x18001f3b6  mov     rdx, [rbp+var_18]
0x18001f3ba  mov     rcx, rsi
0x18001f3bd  call    ??$WriteStringElement@UIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@@YAJPEAUIXmlWriter@@PEAUIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJPEAPEAUHSTRING__@@@ZPEBG@Z; WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *,long (Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::*)(HSTRING__ * *),ushort const *)
0x18001f3c2  lea     r9, aLogo_0; "logo"
0x18001f3c9  lea     r8, ??_9IAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@$BFI@AA; [thunk]: Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::`vcall'{88,{flat}}
0x18001f3d0  mov     rdx, [rbp+var_18]
0x18001f3d4  mov     rcx, rsi
0x18001f3d7  call    ??$WriteStringElement@UIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@@YAJPEAUIXmlWriter@@PEAUIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@P81234567@EAAJPEAPEAUHSTRING__@@@ZPEBG@Z; WriteStringElement<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage>(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *,long (Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage::*)(HSTRING__ * *),ushort const *)
0x18001f3dc  nop
0x18001f3dd  lea     rcx, [rbp+var_18]
0x18001f3e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f3e6  mov     rax, [rsi]
0x18001f3e9  xor     r9d, r9d
0x18001f3ec  lea     r8, aImgs; "imgs"
0x18001f3f3  xor     edx, edx
0x18001f3f5  mov     rcx, rsi
0x18001f3f8  mov     rax, [rax+0D8h]
0x18001f3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f404  mov     edi, eax
0x18001f406  test    eax, eax
0x18001f408  js      loc_18001F54F
0x18001f40e  mov     r14d, r15d
0x18001f411  cmp     dword ptr [rbp+string], r15d
0x18001f415  jbe     loc_18001F53E
0x18001f41b  mov     [rbp+var_18], r15
0x18001f41f  mov     [rbp+var_20], r15d
0x18001f423  mov     dword ptr [rbp+arg_18], r15d
0x18001f427  mov     [rbp+var_1C], r15d
0x18001f42b  mov     rdi, [rbp+var_10]
0x18001f42f  mov     rax, [rdi]
0x18001f432  mov     rbx, [rax+30h]
0x18001f436  lea     rcx, [rbp+var_18]
0x18001f43a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f43f  lea     r8, [rbp+var_18]
0x18001f443  mov     edx, r14d
0x18001f446  mov     rcx, rdi
0x18001f449  mov     rax, rbx
0x18001f44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f451  test    eax, eax
0x18001f453  js      loc_18001F517
0x18001f459  mov     rcx, [rbp+var_18]
0x18001f45d  mov     rax, [rcx]
0x18001f460  lea     rdx, [rbp+var_20]
0x18001f464  mov     rax, [rax+38h]
0x18001f468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f46d  test    eax, eax
0x18001f46f  js      loc_18001F517
0x18001f475  mov     rcx, [rbp+var_18]
0x18001f479  mov     rax, [rcx]
0x18001f47c  lea     rdx, [rbp+arg_18]
0x18001f480  mov     rax, [rax+40h]
0x18001f484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f489  test    eax, eax
0x18001f48b  js      loc_18001F517
0x18001f491  mov     rcx, [rbp+var_18]
0x18001f495  mov     rax, [rcx]
0x18001f498  lea     rdx, [rbp+var_1C]
0x18001f49c  mov     rax, [rax+30h]
0x18001f4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4a5  test    eax, eax
0x18001f4a7  js      short loc_18001F517
0x18001f4a9  cmp     [rbp+var_1C], r15d
0x18001f4ad  jnz     short loc_18001F517
0x18001f4af  mov     eax, [rbp+var_20]
0x18001f4b2  cmp     eax, 96h
0x18001f4b7  jnz     short loc_18001F4C7
0x18001f4b9  cmp     dword ptr [rbp+arg_18], eax
0x18001f4bc  jnz     short loc_18001F517
0x18001f4be  lea     r8, a1; "1"
0x18001f4c5  jmp     short loc_18001F50A
0x18001f4c7  mov     ecx, dword ptr [rbp+arg_18]
0x18001f4ca  cmp     eax, 136h
0x18001f4cf  jnz     short loc_18001F4E2
0x18001f4d1  cmp     ecx, 96h
0x18001f4d7  jnz     short loc_18001F4FB
0x18001f4d9  lea     r8, a3; "3"
0x18001f4e0  jmp     short loc_18001F50A
0x18001f4e2  cmp     eax, 46h ; 'F'
0x18001f4e5  jnz     short loc_18001F4F4
0x18001f4e7  cmp     ecx, eax
0x18001f4e9  jnz     short loc_18001F517
0x18001f4eb  lea     r8, a4; "4"
0x18001f4f2  jmp     short loc_18001F50A
0x18001f4f4  cmp     eax, 136h
0x18001f4f9  jnz     short loc_18001F517
0x18001f4fb  cmp     ecx, 136h
0x18001f501  jnz     short loc_18001F517
0x18001f503  lea     r8, a5; "5"
0x18001f50a  mov     rdx, [rbp+var_18]; struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *
0x18001f50e  mov     rcx, rsi; struct IXmlWriter *
0x18001f511  call    ?WriteImgNode@@YAJPEAUIXmlWriter@@PEAUIAppImage@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEBG@Z; WriteImgNode(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppImage *,ushort const *)
0x18001f516  nop
0x18001f517  mov     rcx, [rbp+var_18]
0x18001f51b  test    rcx, rcx
0x18001f51e  jz      short loc_18001F531
0x18001f520  mov     [rbp+var_18], r15
0x18001f524  mov     rax, [rcx]
0x18001f527  mov     rax, [rax+10h]
0x18001f52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f530  nop
0x18001f531  inc     r14d
0x18001f534  cmp     r14d, dword ptr [rbp+string]
0x18001f538  jb      loc_18001F41B
0x18001f53e  mov     rax, [rsi]
0x18001f541  mov     rcx, rsi
0x18001f544  mov     rax, [rax+78h]
  ... truncated ...
```
