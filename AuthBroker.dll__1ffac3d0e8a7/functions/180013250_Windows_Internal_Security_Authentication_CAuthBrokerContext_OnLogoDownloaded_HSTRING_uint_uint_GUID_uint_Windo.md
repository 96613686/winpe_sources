# Windows::Internal::Security::Authentication::CAuthBrokerContext::OnLogoDownloaded(HSTRING__ *,uint,uint,_GUID,uint,Windows::Storage::Streams::IBuffer *)

- ea: `0x180013250`
- end: `0x18001347b`
- name: `?OnLogoDownloaded@CAuthBrokerContext@Authentication@Security@Internal@Windows@@UEAAJPEAUHSTRING__@@IIU_GUID@@IPEAUIBuffer@Streams@Storage@5@@Z`
- size: `555`
- prototype: `HRESULT __fastcall(Windows::Internal::Security::Authentication::CAuthBrokerContext *this, HSTRING__ *url, unsigned int width, unsigned int height, _GUID pixelFormat, unsigned int stride, Windows::Storage::Streams::IBuffer *bitmap)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006060`
- `0x180013250`
- `0x180013ed0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800133d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800133d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800133bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800133bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013354`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013354`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::CAuthBrokerContext::OnLogoDownloaded(
        Windows::Internal::Security::Authentication::CAuthBrokerContext *this,
        HSTRING url,
        unsigned int width,
        unsigned int height,
        _GUID *pixelFormat,
        unsigned int stride,
        Windows::Storage::Streams::IBuffer *bitmap)
{
  int Instance; // ebx
  unsigned __int8 *v12; // rdi
  __int64 (__fastcall *v13)(unsigned __int8 *, _QWORD, _QWORD, _QWORD, unsigned int, _DWORD, unsigned __int8 *, Microsoft::WRL::ComPtr<IWICImagingFactory> *); // rbx
  unsigned __int8 *v14; // rbx
  _GUID v15; // xmm6
  const wchar_t *StringRawBuffer; // rax
  IWICBitmap *ptr; // rcx
  Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBufferByteAccess> buffer; // [rsp+58h] [rbp-51h] BYREF
  Microsoft::WRL::ComPtr<IWICBitmap> pBitmap; // [rsp+60h] [rbp-49h] BYREF
  Microsoft::WRL::ComPtr<IWICImagingFactory> pWICFactory; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int8 *imageData; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int8 *v23; // [rsp+78h] [rbp-31h] BYREF
  _GUID v24[6]; // [rsp+88h] [rbp-21h] BYREF

  pWICFactory.ptr_ = 0;
  *(_QWORD *)&v24[0].Data1 = pixelFormat;
  imageData = 0;
  pBitmap.ptr_ = 0;
  Instance = 0;
  v23 = 0;
  LODWORD(buffer.ptr_) = 0;
  if ( !bitmap )
    goto LABEL_12;
  Instance = bitmap->get_Length(bitmap, (unsigned int *)&buffer);
  if ( Instance < 0 )
    goto $Cleanup_0;
  if ( width > 0x400 || height > 0x400 || LODWORD(buffer.ptr_) > 0x400000 )
  {
    Instance = -2147024883;
  }
  else
  {
    Instance = bitmap->QueryInterface(bitmap, &GUID_905a0fef_bc53_11df_8c49_001e4fc686da, (void **)&pBitmap);
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(IWICBitmap *, unsigned __int8 **))pBitmap.ptr_->GetSize)(pBitmap.ptr_, &v23);
      if ( Instance >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&imageData);
        Instance = CoCreateInstance(
                     &CLSID_WICImagingFactory2,
                     0,
                     1u,
                     &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                     (LPVOID *)&imageData);
        if ( Instance >= 0 )
        {
          v12 = imageData;
          v13 = *(__int64 (__fastcall **)(unsigned __int8 *, _QWORD, _QWORD, _QWORD, unsigned int, _DWORD, unsigned __int8 *, Microsoft::WRL::ComPtr<IWICImagingFactory> *))(*(_QWORD *)imageData + 160LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&pWICFactory);
          Instance = v13(v12, width, height, *(_QWORD *)&v24[0].Data1, stride, buffer.ptr_, v23, &pWICFactory);
          if ( Instance >= 0 )
          {
            if ( WindowsIsStringEmpty(url)
              || (v14 = v23,
                  v15 = *(_GUID *)*(_QWORD *)&v24[0].Data1,
                  StringRawBuffer = WindowsGetStringRawBuffer(url, 0),
                  v24[0] = v15,
                  Instance = Windows::Internal::Security::Authentication::CAuthBrokerContext::SaveLogoForUrl(
                               (Windows::Internal::Security::Authentication::CAuthBrokerContext *)v24,
                               StringRawBuffer,
                               width,
                               height,
                               v24,
                               stride,
                               v14,
                               (unsigned __int16)buffer.ptr_),
                  Instance >= 0) )
            {
LABEL_12:
              ((void (__fastcall *)(IWebAuthDialog *))this->m_pWebAuthDialog->SetApplicationImage)(this->m_pWebAuthDialog);
            }
          }
        }
      }
    }
  }
$Cleanup_0:
  ptr = pBitmap.ptr_;
  if ( pBitmap.ptr_ )
  {
    pBitmap.ptr_ = 0;
    ptr->Release(ptr);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&pWICFactory);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&imageData);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180013250  mov     rax, rsp
0x180013253  push    rbp
0x180013254  push    rbx
0x180013255  push    rsi
0x180013256  push    rdi
0x180013257  push    r12
0x180013259  push    r13
0x18001325b  push    r14
0x18001325d  push    r15
0x18001325f  lea     rbp, [rax-47h]
0x180013263  sub     rsp, 0A8h
0x18001326a  mov     rdi, [rbp+3Fh+arg_30]
0x18001326e  xor     r12d, r12d
0x180013271  movaps  xmmword ptr [rax-58h], xmm6
0x180013275  mov     r15, url
0x180013278  mov     rax, qword ptr [rbp+3Fh+pixelFormat.Data1]
0x18001327c  mov     edx, r12d
0x18001327f  mov     [rbp+3Fh+pWICFactory.ptr_], url
0x180013283  mov     r14d, height
0x180013286  mov     qword ptr [rbp+3Fh+var_60], rax
0x18001328a  mov     esi, width
0x18001328d  mov     [rbp+3Fh+imageData], r12
0x180013291  mov     r13, this
0x180013294  mov     [rbp+3Fh+pBitmap.ptr_], r12
0x180013298  mov     ebx, r12d
0x18001329b  mov     [rbp+3Fh+var_70], r12
0x18001329f  mov     dword ptr [rbp+3Fh+buffer.ptr_], r12d
0x1800132a3  test    rdi, rdi
0x1800132a6  jz      loc_180013417
0x1800132ac  mov     rax, [rdi]
0x1800132af  lea     url, [rbp+3Fh+buffer]
0x1800132b3  mov     this, rdi
0x1800132b6  mov     rax, [rax+38h]
0x1800132ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132bf  mov     ebx, eax
0x1800132c1  test    eax, eax
0x1800132c3  js      $Cleanup_0
0x1800132c9  mov     eax, 400h
0x1800132ce  cmp     esi, eax
0x1800132d0  ja      loc_180013474
0x1800132d6  cmp     r14d, eax
0x1800132d9  ja      loc_180013474
0x1800132df  cmp     dword ptr [rbp+3Fh+buffer.ptr_], 400000h
0x1800132e6  ja      loc_180013474
0x1800132ec  mov     rax, [rdi]
0x1800132ef  lea     r8, [rbp+3Fh+pBitmap]
0x1800132f3  lea     url, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x1800132fa  mov     this, rdi
0x1800132fd  mov     rax, [rax]
0x180013300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013305  mov     ebx, eax
0x180013307  test    eax, eax
0x180013309  js      $Cleanup_0
0x18001330f  mov     this, [rbp+3Fh+pBitmap.ptr_]
0x180013313  lea     url, [rbp+3Fh+var_70]
0x180013317  mov     rax, [this]
0x18001331a  mov     rax, [rax+18h]
0x18001331e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013323  mov     ebx, eax
0x180013325  test    eax, eax
0x180013327  js      $Cleanup_0
0x18001332d  lea     this, [rbp+3Fh+imageData]; this
0x180013331  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013336  lea     rax, [rbp+3Fh+imageData]
0x18001333a  xor     edx, edx; pUnkOuter
0x18001333c  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180013343  mov     [rsp+0E0h+ppv], rax; ppv
0x180013348  lea     width, [r12+1]; dwClsContext
0x18001334d  lea     this, CLSID_WICImagingFactory2; rclsid
0x180013354  call    cs:__imp_CoCreateInstance
0x18001335a  mov     ebx, eax
0x18001335c  test    eax, eax
0x18001335e  js      $Cleanup_0
0x180013364  mov     rdi, [rbp+3Fh+imageData]
0x180013368  lea     this, [rbp+3Fh+pWICFactory]; this
0x18001336c  mov     rax, [rdi]
0x18001336f  mov     rbx, [rax+0A0h]
0x180013376  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001337b  mov     url, [rbp+3Fh+var_70]
0x18001337f  lea     rax, [rbp+3Fh+pWICFactory]
0x180013383  mov     width, dword ptr [rbp+3Fh+buffer.ptr_]
0x180013387  mov     this, rdi
0x18001338a  mov     r12d, dword ptr [rbp+3Fh+pixelFormat.Data4]
0x18001338e  mov     r9, qword ptr [rbp+3Fh+var_60]
0x180013392  mov     [rsp+38h], rax
0x180013397  mov     rax, rbx
0x18001339a  mov     [rsp+0E0h+var_B0], url
0x18001339f  mov     edx, esi
0x1800133a1  mov     dword ptr [rsp+0E0h+var_B8], width
0x1800133a6  mov     width, r14d
0x1800133a9  mov     dword ptr [rsp+0E0h+ppv], r12d
0x1800133ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133b3  mov     ebx, eax
0x1800133b5  test    eax, eax
0x1800133b7  js      short $Cleanup_0
0x1800133b9  mov     this, r15; string
0x1800133bc  call    cs:__imp_WindowsIsStringEmpty
0x1800133c2  test    eax, eax
0x1800133c4  jnz     short loc_180013413
0x1800133c6  mov     rax, qword ptr [rbp+3Fh+var_60]
0x1800133ca  xor     edx, edx; length
0x1800133cc  mov     rbx, [rbp+3Fh+var_70]
0x1800133d0  mov     this, r15; string
0x1800133d3  movups  xmm6, xmmword ptr [rax]
0x1800133d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800133dc  movzx   ecx, word ptr [rbp+3Fh+buffer.ptr_]
0x1800133e0  movzx   height, r14w
0x1800133e4  mov     [rsp+38h], cx
0x1800133e9  movzx   width, si
0x1800133ed  mov     [rsp+0E0h+var_B0], rbx
0x1800133f2  lea     this, [rbp+3Fh+var_60]
0x1800133f6  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x1800133fb  mov     url, rax
0x1800133fe  mov     [rsp+0E0h+ppv], this
0x180013403  movdqu  [rbp+3Fh+var_60], xmm6
0x180013408  call    ?SaveLogoForUrl@CAuthBrokerContext@Authentication@Security@Internal@Windows@@QEAAJPEBGGGU_GUID@@KPEAEG@Z; Windows::Internal::Security::Authentication::CAuthBrokerContext::SaveLogoForUrl(ushort const *,ushort,ushort,_GUID,ulong,uchar *,ushort)
0x18001340d  mov     ebx, eax
0x18001340f  test    eax, eax
0x180013411  js      short $Cleanup_0
0x180013413  mov     url, [rbp+3Fh+pWICFactory.ptr_]
0x180013417  mov     this, [r13+58h]
0x18001341b  mov     rax, [this]
0x18001341e  mov     rax, [rax+30h]
0x180013422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013427  mov     this, [rbp+3Fh+pBitmap.ptr_]
0x18001342b  test    this, this
0x18001342e  jz      short loc_180013444
0x180013430  mov     [rbp+3Fh+pBitmap.ptr_], 0
0x180013438  mov     rax, [this]
0x18001343b  mov     rax, [rax+10h]
0x18001343f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013444  lea     this, [rbp+3Fh+pWICFactory]; this
0x180013448  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001344d  lea     this, [rbp+3Fh+imageData]; this
0x180013451  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013456  movaps  xmm6, xmmword ptr [rsp+90h]
0x18001345e  mov     eax, ebx
0x180013460  add     rsp, 0A8h
0x180013467  pop     r15
0x180013469  pop     r14
0x18001346b  pop     r13
0x18001346d  pop     r12
0x18001346f  pop     rdi
0x180013470  pop     rsi
0x180013471  pop     rbx
0x180013472  pop     rbp
0x180013473  retn
0x180013474  mov     ebx, 8007000Dh
0x180013479  jmp     short $Cleanup_0
```
