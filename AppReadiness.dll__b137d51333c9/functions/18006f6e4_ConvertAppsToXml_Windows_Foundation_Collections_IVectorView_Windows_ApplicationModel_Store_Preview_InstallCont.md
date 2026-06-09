# ConvertAppsToXml(Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,ushort * *)

- ea: `0x18006f6e4`
- end: `0x18006f9af`
- name: `?ConvertAppsToXml@@YAJPEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@PEAPEAG@Z`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180070700`

## callees

- `0x180002958`
- `0x18001f0dc`
- `0x18006f6e4`
- `0x180075b58`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18006f923`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18006f923`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006f753`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006f753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f957`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18006f94a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18006f94a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006f938`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006f938`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f982`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006f982`
- `XmlLite!CreateXmlWriter` at `0x18006f72b`
- `XmlLite!CreateXmlWriter` at `0x18006f72b`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18006f785`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18006f785`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ConvertAppsToXml(__int64 a1, _QWORD *a2)
{
  HRESULT HGlobalFromStream; // ebx
  unsigned int v5; // edi
  __int64 (__fastcall *v6)(__int64, _QWORD, struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData **); // rbx
  const void *v7; // r14
  SIZE_T v8; // rsi
  char *v9; // rax
  char *v10; // rdi
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *v12[2]; // [rsp+30h] [rbp-10h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+78h] [rbp+38h] BYREF
  void *ppvObject; // [rsp+80h] [rbp+40h] BYREF
  LPSTREAM ppstm; // [rsp+88h] [rbp+48h] BYREF

  *a2 = 0;
  ppstm = 0;
  ppvObject = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
  HGlobalFromStream = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( HGlobalFromStream >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
    HGlobalFromStream = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( HGlobalFromStream >= 0 )
    {
      ppOutput = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppOutput);
      HGlobalFromStream = CreateXmlWriterOutputWithEncodingName((IUnknown *)ppstm, 0, L"utf-16", &ppOutput);
      if ( HGlobalFromStream >= 0 )
      {
        HGlobalFromStream = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(
                              ppvObject,
                              ppOutput);
        if ( HGlobalFromStream >= 0 )
        {
          HGlobalFromStream = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(
                                ppvObject,
                                3,
                                1);
          if ( HGlobalFromStream >= 0 )
            HGlobalFromStream = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppvObject + 40LL))(
                                  ppvObject,
                                  2,
                                  0);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppOutput);
      if ( HGlobalFromStream >= 0 )
      {
        HGlobalFromStream = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject
                                                                                               + 216LL))(
                              ppvObject,
                              0,
                              L"ptl",
                              0);
        if ( HGlobalFromStream >= 0 )
        {
          HGlobalFromStream = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject
                                                                                                 + 216LL))(
                                ppvObject,
                                0,
                                L"pts",
                                0);
          if ( HGlobalFromStream >= 0 )
          {
            LODWORD(ppOutput) = 0;
            HGlobalFromStream = (*(__int64 (__fastcall **)(__int64, IXmlWriterOutput **))(*(_QWORD *)a1 + 56LL))(
                                  a1,
                                  &ppOutput);
            v5 = 0;
            if ( (_DWORD)ppOutput )
            {
              while ( HGlobalFromStream >= 0 )
              {
                v12[0] = 0;
                v6 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData **))(*(_QWORD *)a1 + 48LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v12);
                HGlobalFromStream = v6(a1, v5, v12);
                if ( HGlobalFromStream >= 0 )
                  HGlobalFromStream = WritePtElement((struct IXmlWriter *)ppvObject, v12[0]);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v12);
                if ( ++v5 >= (unsigned int)ppOutput )
                  goto LABEL_15;
              }
            }
            else
            {
LABEL_15:
              if ( HGlobalFromStream >= 0 )
              {
                HGlobalFromStream = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
                if ( HGlobalFromStream >= 0 )
                {
                  HGlobalFromStream = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
                  if ( HGlobalFromStream >= 0 )
                  {
                    HGlobalFromStream = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
                    if ( HGlobalFromStream >= 0 )
                    {
                      ppOutput = 0;
                      HGlobalFromStream = GetHGlobalFromStream(ppstm, (HGLOBAL *)&ppOutput);
                      if ( HGlobalFromStream >= 0 )
                      {
                        HGlobalFromStream = -2147024882;
                        v7 = GlobalLock(ppOutput);
                        if ( v7 )
                        {
                          v8 = GlobalSize(ppOutput);
                          v9 = (char *)CoTaskMemAlloc(v8 + 2);
                          v10 = v9;
                          if ( v9 )
                          {
                            memcpy_0(v9, v7, v8);
                            *(_WORD *)&v10[v8] = 0;
                            *a2 = v10;
                            HGlobalFromStream = 0;
                          }
                          GlobalUnlock(ppOutput);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x18006f6e4  mov     [rsp-28h+arg_0], rbx
0x18006f6e9  push    rbp
0x18006f6ea  push    rsi
0x18006f6eb  push    rdi
0x18006f6ec  push    r14
0x18006f6ee  push    r15
0x18006f6f0  mov     rbp, rsp
0x18006f6f3  sub     rsp, 40h
0x18006f6f7  mov     r15, rdx
0x18006f6fa  mov     rsi, rcx
0x18006f6fd  mov     qword ptr [rdx], 0
0x18006f704  mov     [rbp+ppstm], 0
0x18006f70c  mov     [rbp+ppvObject], 0
0x18006f714  lea     rcx, [rbp+ppvObject]
0x18006f718  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f71d  xor     r8d, r8d; pMalloc
0x18006f720  lea     rdx, [rbp+ppvObject]; ppvObject
0x18006f724  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18006f72b  call    cs:__imp_CreateXmlWriter
0x18006f731  mov     ebx, eax
0x18006f733  test    eax, eax
0x18006f735  js      loc_18006F989
0x18006f73b  lea     rcx, [rbp+ppstm]
0x18006f73f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f744  lea     r8, [rbp+ppstm]; ppstm
0x18006f748  mov     r14d, 1
0x18006f74e  mov     edx, r14d; fDeleteOnRelease
0x18006f751  xor     ecx, ecx; hGlobal
0x18006f753  call    cs:__imp_CreateStreamOnHGlobal
0x18006f759  mov     ebx, eax
0x18006f75b  test    eax, eax
0x18006f75d  js      loc_18006F989
0x18006f763  mov     [rbp+ppOutput], 0
0x18006f76b  lea     rcx, [rbp+ppOutput]
0x18006f76f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f774  lea     r9, [rbp+ppOutput]; ppOutput
0x18006f778  lea     r8, pwszEncodingName; "utf-16"
0x18006f77f  xor     edx, edx; pMalloc
0x18006f781  mov     rcx, [rbp+ppstm]; pOutputStream
0x18006f785  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18006f78b  mov     ebx, eax
0x18006f78d  test    eax, eax
0x18006f78f  js      short loc_18006F7E1
0x18006f791  mov     rcx, [rbp+ppvObject]
0x18006f795  mov     rax, [rcx]
0x18006f798  mov     rdx, [rbp+ppOutput]
0x18006f79c  mov     rax, [rax+18h]
0x18006f7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7a5  mov     ebx, eax
0x18006f7a7  test    eax, eax
0x18006f7a9  js      short loc_18006F7E1
0x18006f7ab  mov     rcx, [rbp+ppvObject]
0x18006f7af  mov     rax, [rcx]
0x18006f7b2  mov     r8d, r14d
0x18006f7b5  lea     edx, [r14+2]
0x18006f7b9  mov     rax, [rax+28h]
0x18006f7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7c2  mov     ebx, eax
0x18006f7c4  test    eax, eax
0x18006f7c6  js      short loc_18006F7E1
0x18006f7c8  mov     rcx, [rbp+ppvObject]
0x18006f7cc  mov     rax, [rcx]
0x18006f7cf  xor     r8d, r8d
0x18006f7d2  lea     edx, [r14+1]
0x18006f7d6  mov     rax, [rax+28h]
0x18006f7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7df  mov     ebx, eax
0x18006f7e1  lea     rcx, [rbp+ppOutput]
0x18006f7e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f7ea  test    ebx, ebx
0x18006f7ec  js      loc_18006F989
0x18006f7f2  mov     rcx, [rbp+ppvObject]
0x18006f7f6  mov     rax, [rcx]
0x18006f7f9  xor     r9d, r9d
0x18006f7fc  lea     r8, aPtl; "ptl"
0x18006f803  xor     edx, edx
0x18006f805  mov     rax, [rax+0D8h]
0x18006f80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f811  mov     ebx, eax
0x18006f813  test    eax, eax
0x18006f815  js      loc_18006F989
0x18006f81b  mov     rcx, [rbp+ppvObject]
0x18006f81f  mov     rax, [rcx]
0x18006f822  xor     r9d, r9d
0x18006f825  lea     r8, aPts_0; "pts"
0x18006f82c  xor     edx, edx
0x18006f82e  mov     rax, [rax+0D8h]
0x18006f835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f83a  mov     ebx, eax
0x18006f83c  test    eax, eax
0x18006f83e  js      loc_18006F989
0x18006f844  mov     dword ptr [rbp+ppOutput], 0
0x18006f84b  mov     rax, [rsi]
0x18006f84e  lea     rdx, [rbp+ppOutput]
0x18006f852  mov     rcx, rsi
0x18006f855  mov     rax, [rax+38h]
0x18006f859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f85e  mov     ebx, eax
0x18006f860  xor     edi, edi
0x18006f862  cmp     dword ptr [rbp+ppOutput], edi
0x18006f865  jbe     short loc_18006F8BE
0x18006f867  test    ebx, ebx
0x18006f869  js      loc_18006F989
0x18006f86f  mov     [rbp+var_10], 0
0x18006f877  mov     rax, [rsi]
0x18006f87a  mov     rbx, [rax+30h]
0x18006f87e  lea     rcx, [rbp+var_10]
0x18006f882  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f887  lea     r8, [rbp+var_10]
0x18006f88b  mov     edx, edi
0x18006f88d  mov     rcx, rsi
0x18006f890  mov     rax, rbx
0x18006f893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f898  mov     ebx, eax
0x18006f89a  test    eax, eax
0x18006f89c  js      short loc_18006F8AD
0x18006f89e  mov     rdx, [rbp+var_10]; struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *
0x18006f8a2  mov     rcx, [rbp+ppvObject]; struct IXmlWriter *
0x18006f8a6  call    ?WritePtElement@@YAJPEAUIXmlWriter@@PEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; WritePtElement(IXmlWriter *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *)
0x18006f8ab  mov     ebx, eax
0x18006f8ad  lea     rcx, [rbp+var_10]
0x18006f8b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f8b6  add     edi, r14d
0x18006f8b9  cmp     edi, dword ptr [rbp+ppOutput]
0x18006f8bc  jb      short loc_18006F867
0x18006f8be  test    ebx, ebx
0x18006f8c0  js      loc_18006F989
0x18006f8c6  mov     rcx, [rbp+ppvObject]
0x18006f8ca  mov     rax, [rcx]
0x18006f8cd  mov     rax, [rax+78h]
0x18006f8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f8d6  mov     ebx, eax
0x18006f8d8  test    eax, eax
0x18006f8da  js      loc_18006F989
0x18006f8e0  mov     rcx, [rbp+ppvObject]
0x18006f8e4  mov     rax, [rcx]
0x18006f8e7  mov     rax, [rax+78h]
0x18006f8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f8f0  mov     ebx, eax
0x18006f8f2  test    eax, eax
0x18006f8f4  js      loc_18006F989
0x18006f8fa  mov     rcx, [rbp+ppvObject]
0x18006f8fe  mov     rax, [rcx]
0x18006f901  mov     rax, [rax+0F8h]
0x18006f908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f90d  mov     ebx, eax
0x18006f90f  test    eax, eax
0x18006f911  js      short loc_18006F989
0x18006f913  mov     [rbp+ppOutput], 0
0x18006f91b  lea     rdx, [rbp+ppOutput]; phglobal
0x18006f91f  mov     rcx, [rbp+ppstm]; pstm
0x18006f923  call    cs:__imp_GetHGlobalFromStream
0x18006f929  mov     ebx, eax
0x18006f92b  test    eax, eax
0x18006f92d  js      short loc_18006F989
0x18006f92f  mov     ebx, 8007000Eh
0x18006f934  mov     rcx, [rbp+ppOutput]; hMem
0x18006f938  call    cs:__imp_GlobalLock
0x18006f93e  mov     r14, rax
0x18006f941  test    rax, rax
0x18006f944  jz      short loc_18006F989
0x18006f946  mov     rcx, [rbp+ppOutput]; hMem
0x18006f94a  call    cs:__imp_GlobalSize
0x18006f950  mov     rsi, rax
0x18006f953  lea     rcx, [rax+2]; cb
0x18006f957  call    cs:__imp_CoTaskMemAlloc
0x18006f95d  mov     rdi, rax
0x18006f960  test    rax, rax
0x18006f963  jz      short loc_18006F97E
0x18006f965  mov     r8, rsi; Size
0x18006f968  mov     rdx, r14; Src
0x18006f96b  mov     rcx, rax; void *
0x18006f96e  call    memcpy_0
0x18006f973  mov     word ptr [rdi+rsi], 0
0x18006f979  mov     [r15], rdi
0x18006f97c  xor     ebx, ebx
0x18006f97e  mov     rcx, [rbp+ppOutput]; hMem
0x18006f982  call    cs:__imp_GlobalUnlock
0x18006f988  nop
0x18006f989  lea     rcx, [rbp+ppvObject]
0x18006f98d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f992  nop
0x18006f993  lea     rcx, [rbp+ppstm]
0x18006f997  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f99c  mov     eax, ebx
0x18006f99e  mov     rbx, [rsp+40h+arg_0]
0x18006f9a3  add     rsp, 40h
0x18006f9a7  pop     r15
0x18006f9a9  pop     r14
0x18006f9ab  pop     rdi
0x18006f9ac  pop     rsi
0x18006f9ad  pop     rbp
0x18006f9ae  retn
```
