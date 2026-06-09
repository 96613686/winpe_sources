# CreateVideoSourceReaderFromStream(IStream *,_GUID const &,void * *)

- ea: `0x180041a7c`
- end: `0x180041d41`
- name: `?CreateVideoSourceReaderFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `709`
- prototype: `__int64 __fastcall(struct IStream *pStream, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180041790`
- `0x1800d77b8`

## callees

- `0x180013244`
- `0x180013660`
- `0x18003217c`
- `0x180041a7c`
- `0x1800e5010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180041bdc`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180041bdc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041cb8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041cb8`
- `MFPlat!MFCreateAttributes` at `0x180041b07`
- `MFPlat!MFCreateAttributes` at `0x180041b07`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x180041ab8`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x180041ab8`
- `MFPlat!MFCreateSourceResolver` at `0x180041add`
- `MFPlat!MFCreateSourceResolver` at `0x180041add`

## pseudocode

```c
__int64 __fastcall CreateVideoSourceReaderFromStream(struct IStream *pStream, const struct _GUID *a2, void **a3)
{
  HRESULT v5; // ebx
  IMFSourceResolver *v6; // rdi
  HRESULT (__stdcall *CreateObjectFromByteStream)(IMFSourceResolver *, IMFByteStream *, LPCWSTR, DWORD, IPropertyStore *, MF_OBJECT_TYPE *, IUnknown **); // rbx
  LPVOID v9; // [rsp+40h] [rbp-40h] BYREF
  __int64 v10; // [rsp+48h] [rbp-38h] BYREF
  IMFSourceResolver *ppISourceResolver; // [rsp+50h] [rbp-30h] BYREF
  IMFByteStream *ppByteStream; // [rsp+58h] [rbp-28h] BYREF
  __int128 v13; // [rsp+60h] [rbp-20h] BYREF
  __int64 v14; // [rsp+70h] [rbp-10h]
  const struct _GUID *v15; // [rsp+A8h] [rbp+28h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+B0h] [rbp+30h] BYREF
  void *ppv; // [rsp+B8h] [rbp+38h] BYREF

  v15 = a2;
  *a3 = 0;
  ppByteStream = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppByteStream);
  v5 = MFCreateMFByteStreamOnStream(pStream, &ppByteStream);
  if ( v5 >= 0 )
  {
    ppISourceResolver = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppISourceResolver);
    v5 = MFCreateSourceResolver(&ppISourceResolver);
    if ( v5 >= 0 )
    {
      ppMFAttributes = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
      v5 = MFCreateAttributes(&ppMFAttributes, 8u);
      if ( v5 >= 0 )
      {
        v5 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               &MF_SOURCE_READER_ENABLE_VIDEO_PROCESSING,
               1);
        if ( v5 >= 0 )
        {
          ((void (__fastcall *)(IMFAttributes *, GUID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &GUID_9561c3e8_ea9e_4435_9b1e_a93e691894d8,
            1);
          ((void (__fastcall *)(IMFAttributes *, GUID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &GUID_5ae557b8_77af_41f5_9fa6_4db2fe1d4bca,
            256);
          ((void (__fastcall *)(IMFAttributes *, GUID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &GUID_7262a16a_d2dc_4e75_9ba8_65c0c6d32b13,
            256);
          ((void (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            MF_LOW_LATENCY,
            1);
          ppv = 0;
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
          v5 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
          if ( v5 >= 0 )
          {
            v14 = 0;
            v13 = 0;
            LOWORD(v13) = 11;
            WORD4(v13) = -1;
            v5 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                   ppv,
                   &MFPKEY_MediaSource_DisableReadAhead,
                   &v13);
            if ( v5 >= 0 )
            {
              v6 = ppISourceResolver;
              LODWORD(v15) = 0;
              v10 = 0;
              CreateObjectFromByteStream = ppISourceResolver->lpVtbl->CreateObjectFromByteStream;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
              v5 = ((__int64 (__fastcall *)(IMFSourceResolver *, IMFByteStream *, _QWORD, __int64, void *, const struct _GUID **, __int64 *))CreateObjectFromByteStream)(
                     v6,
                     ppByteStream,
                     0,
                     65553,
                     ppv,
                     &v15,
                     &v10);
              if ( v5 >= 0 )
              {
                v9 = 0;
                Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v9);
                v5 = CoCreateInstance(
                       &CLSID_MFReadWriteClassFactory,
                       0,
                       1u,
                       &GUID_e7fe2e12_661c_40da_92f9_4f002ab67627,
                       &v9);
                if ( v5 >= 0 )
                  v5 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, IMFAttributes *, GUID *, void **))(*(_QWORD *)v9 + 32LL))(
                         v9,
                         &CLSID_MFSourceReader,
                         v10,
                         ppMFAttributes,
                         &GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993,
                         a3);
                Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v9);
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
            }
          }
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppISourceResolver);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppByteStream);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180041a7c  mov     [rsp-18h+arg_0], rbx
0x180041a81  mov     [rsp-18h+arg_8], rdx
0x180041a86  push    rbp
0x180041a87  push    rsi
0x180041a88  push    rdi
0x180041a89  mov     rbp, rsp
0x180041a8c  sub     rsp, 80h
0x180041a93  mov     rbx, rcx
0x180041a96  mov     qword ptr [r8], 0
0x180041a9d  lea     rcx, [rbp+ppByteStream]
0x180041aa1  mov     [rbp+ppByteStream], 0
0x180041aa9  mov     rsi, r8
0x180041aac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041ab1  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x180041ab5  mov     rcx, rbx; pStream
0x180041ab8  call    cs:__imp_MFCreateMFByteStreamOnStream
0x180041abe  mov     ebx, eax
0x180041ac0  test    eax, eax
0x180041ac2  js      loc_180041D23
0x180041ac8  lea     rcx, [rbp+ppISourceResolver]
0x180041acc  mov     [rbp+ppISourceResolver], 0
0x180041ad4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041ad9  lea     rcx, [rbp+ppISourceResolver]; ppISourceResolver
0x180041add  call    cs:__imp_MFCreateSourceResolver
0x180041ae3  mov     ebx, eax
0x180041ae5  test    eax, eax
0x180041ae7  js      loc_180041D1A
0x180041aed  lea     rcx, [rbp+ppMFAttributes]
0x180041af1  mov     [rbp+ppMFAttributes], 0
0x180041af9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041afe  mov     edx, 8; cInitialSize
0x180041b03  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180041b07  call    cs:__imp_MFCreateAttributes
0x180041b0d  mov     ebx, eax
0x180041b0f  test    eax, eax
0x180041b11  js      loc_180041D11
0x180041b17  mov     rcx, [rbp+ppMFAttributes]
0x180041b1b  lea     rdx, MF_SOURCE_READER_ENABLE_VIDEO_PROCESSING
0x180041b22  mov     r8d, 1
0x180041b28  mov     rax, [rcx]
0x180041b2b  mov     rax, [rax+0A8h]
0x180041b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b37  mov     ebx, eax
0x180041b39  test    eax, eax
0x180041b3b  js      loc_180041D11
0x180041b41  mov     rcx, [rbp+ppMFAttributes]
0x180041b45  lea     rdx, _GUID_9561c3e8_ea9e_4435_9b1e_a93e691894d8
0x180041b4c  mov     r8d, 1
0x180041b52  mov     rax, [rcx]
0x180041b55  mov     rax, [rax+0A8h]
0x180041b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b61  mov     rcx, [rbp+ppMFAttributes]
0x180041b65  lea     rdx, _GUID_5ae557b8_77af_41f5_9fa6_4db2fe1d4bca
0x180041b6c  mov     ebx, 100h
0x180041b71  mov     r8d, ebx
0x180041b74  mov     rax, [rcx]
0x180041b77  mov     rax, [rax+0A8h]
0x180041b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b83  mov     rcx, [rbp+ppMFAttributes]
0x180041b87  lea     rdx, _GUID_7262a16a_d2dc_4e75_9ba8_65c0c6d32b13
0x180041b8e  mov     r8d, ebx
0x180041b91  mov     rax, [rcx]
0x180041b94  mov     rax, [rax+0A8h]
0x180041b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ba0  mov     rcx, [rbp+ppMFAttributes]
0x180041ba4  lea     rdx, MF_LOW_LATENCY
0x180041bab  mov     r8d, 1
0x180041bb1  mov     rax, [rcx]
0x180041bb4  mov     rax, [rax+0A8h]
0x180041bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bc0  lea     rcx, [rbp+ppv]
0x180041bc4  mov     [rbp+ppv], 0
0x180041bcc  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180041bd1  lea     rdx, [rbp+ppv]; ppv
0x180041bd5  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180041bdc  call    cs:__imp_PSCreateMemoryPropertyStore
0x180041be2  mov     ebx, eax
0x180041be4  test    eax, eax
0x180041be6  js      loc_180041D08
0x180041bec  mov     rcx, [rbp+ppv]
0x180041bf0  lea     r8, [rbp+var_20]
0x180041bf4  xor     eax, eax
0x180041bf6  lea     rdx, MFPKEY_MediaSource_DisableReadAhead
0x180041bfd  mov     [rbp+var_10], rax
0x180041c01  xorps   xmm0, xmm0
0x180041c04  mov     eax, 0Bh
0x180041c09  movups  [rbp+var_20], xmm0
0x180041c0d  mov     word ptr [rbp+var_20], ax
0x180041c11  or      eax, 0FFFFFFFFh
0x180041c14  mov     word ptr [rbp+var_20+8], ax
0x180041c18  mov     rax, [rcx]
0x180041c1b  mov     rax, [rax+30h]
0x180041c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c24  mov     ebx, eax
0x180041c26  test    eax, eax
0x180041c28  js      loc_180041D08
0x180041c2e  mov     rdi, [rbp+ppISourceResolver]
0x180041c32  lea     rcx, [rbp+var_38]
0x180041c36  mov     dword ptr [rbp+arg_8], 0
0x180041c3d  mov     [rbp+var_38], 0
0x180041c45  mov     rax, [rdi]
0x180041c48  mov     rbx, [rax+20h]
0x180041c4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041c51  mov     r8, [rbp+ppv]
0x180041c55  lea     rax, [rbp+var_38]
0x180041c59  mov     rdx, [rbp+ppByteStream]
0x180041c5d  mov     r9d, 10011h
0x180041c63  mov     [rsp+80h+var_50], rax
0x180041c68  mov     rcx, rdi
0x180041c6b  lea     rax, [rbp+arg_8]
0x180041c6f  mov     [rsp+80h+var_58], rax
0x180041c74  mov     rax, rbx
0x180041c77  mov     [rsp+80h+var_60], r8
0x180041c7c  xor     r8d, r8d
0x180041c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c84  mov     ebx, eax
0x180041c86  test    eax, eax
0x180041c88  js      short loc_180041CFF
0x180041c8a  lea     rcx, [rbp+var_40]
0x180041c8e  mov     [rbp+var_40], 0
0x180041c96  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180041c9b  xor     edx, edx; pUnkOuter
0x180041c9d  lea     rax, [rbp+var_40]
0x180041ca1  lea     r9, _GUID_e7fe2e12_661c_40da_92f9_4f002ab67627; riid
0x180041ca8  mov     [rsp+80h+var_60], rax; ppv
0x180041cad  lea     rcx, CLSID_MFReadWriteClassFactory; rclsid
0x180041cb4  lea     r8d, [rdx+1]; dwClsContext
0x180041cb8  call    cs:__imp_CoCreateInstance
0x180041cbe  mov     ebx, eax
0x180041cc0  test    eax, eax
0x180041cc2  js      short loc_180041CF6
0x180041cc4  mov     rcx, [rbp+var_40]
0x180041cc8  lea     rdx, _GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993
0x180041ccf  mov     r9, [rbp+ppMFAttributes]
0x180041cd3  mov     r8, [rbp+var_38]
0x180041cd7  mov     [rsp+80h+var_58], rsi
0x180041cdc  mov     rax, [rcx]
0x180041cdf  mov     [rsp+80h+var_60], rdx
0x180041ce4  lea     rdx, CLSID_MFSourceReader
0x180041ceb  mov     rax, [rax+20h]
0x180041cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cf4  mov     ebx, eax
0x180041cf6  lea     rcx, [rbp+var_40]
0x180041cfa  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180041cff  lea     rcx, [rbp+var_38]
0x180041d03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041d08  lea     rcx, [rbp+ppv]
0x180041d0c  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180041d11  lea     rcx, [rbp+ppMFAttributes]
0x180041d15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041d1a  lea     rcx, [rbp+ppISourceResolver]
0x180041d1e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041d23  lea     rcx, [rbp+ppByteStream]
0x180041d27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041d2c  mov     eax, ebx
0x180041d2e  mov     rbx, [rsp+80h+arg_0]
0x180041d36  add     rsp, 80h
0x180041d3d  pop     rdi
0x180041d3e  pop     rsi
0x180041d3f  pop     rbp
0x180041d40  retn
```
