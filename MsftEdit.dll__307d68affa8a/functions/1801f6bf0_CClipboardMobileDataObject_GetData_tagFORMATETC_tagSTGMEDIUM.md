# CClipboardMobileDataObject::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x1801f6bf0`
- end: `0x1801f6f5f`
- name: `?GetData@CClipboardMobileDataObject@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `879`
- prototype: `__int64 __fastcall(CClipboardMobileDataObject *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180048d5c`
- `0x18013bad0`
- `0x18013c8fe`
- `0x18014f444`
- `0x1801f665c`
- `0x1801f68e8`
- `0x1801f6bf0`
- `0x1801f73e0`
- `0x1801f74a0`
- `0x1801f750c`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1801f6c8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1801f6c8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801f6d96`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801f6d96`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801f6ec5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801f6ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f6db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6f34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6f34`

## pseudocode

```c
__int64 __fastcall CClipboardMobileDataObject::GetData(
        CClipboardMobileDataObject *this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3)
{
  unsigned int v5; // ebx
  __int16 v6; // r14
  __int64 *v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v12; // rbx
  int v13; // ecx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  HBITMAP v16; // rdi
  UINT32 v17; // r14d
  HBITMAP v18; // rax
  __int64 v20; // [rsp+30h] [rbp-99h] BYREF
  HANDLE hHandle; // [rsp+38h] [rbp-91h] BYREF
  UINT32 length; // [rsp+40h] [rbp-89h] BYREF
  HSTRING string; // [rsp+48h] [rbp-81h] BYREF
  HSTRING v24; // [rsp+50h] [rbp-79h] BYREF
  __int64 v25; // [rsp+58h] [rbp-71h] BYREF
  _QWORD v26[2]; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v27[7]; // [rsp+70h] [rbp-59h] BYREF
  _QWORD *v28; // [rsp+A8h] [rbp-21h]
  _QWORD v29[7]; // [rsp+B0h] [rbp-19h] BYREF
  _QWORD *v30; // [rsp+E8h] [rbp+1Fh]

  *(_OWORD *)&a3->tymed = 0;
  a3->pUnkForRelease = 0;
  v24 = 0;
  string = 0;
  v5 = CClipboardMobileDataObject::SupportsFormatEtc(this, a2, (struct Microsoft::WRL::Wrappers::HString *)&v24);
  if ( !v5 )
  {
    v6 = SupportedFormat(v24);
    if ( v6 == 1038 )
    {
      v5 = (*(__int64 (__fastcall **)(CClipboardMobileDataObject *, struct tagSTGMEDIUM *))(*(_QWORD *)this + 96LL))(
             this,
             a3);
      goto LABEL_34;
    }
    hHandle = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( !hHandle )
    {
      CEventWrapper::~CEventWrapper((CEventWrapper *)&hHandle);
      v5 = -2147418113;
      goto LABEL_34;
    }
    v20 = 0;
    v26[0] = &hHandle;
    v26[1] = &string;
    v7 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_HSTRING_____::___Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_HSTRING______Microsoft::WRL::FtmBase___lambda_3e59cf71de9fa25b6f7d6f3697c38bba_____1_Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus___lambda_3e59cf71de9fa25b6f7d6f3697c38bba____(
                      &v25,
                      v26);
    v8 = *v7;
    *v7 = 0;
    if ( v25 )
    {
      v25 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>>::Release();
    }
    if ( !v8 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      CEventWrapper::~CEventWrapper((CEventWrapper *)&hHandle);
      v5 = -2147467259;
      goto LABEL_34;
    }
    if ( v6 == 13 )
    {
      v9 = *((_QWORD *)this + 1);
      v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 96LL);
    }
    else
    {
      if ( v6 != 1026 )
      {
LABEL_15:
        v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 48LL))(v20, v8);
        if ( !v5 )
        {
          WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
          v26[0] = 0;
          length = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
          v12 = StringRawBuffer;
          if ( !StringRawBuffer )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
            CEventWrapper::~CEventWrapper((CEventWrapper *)&hHandle);
            v5 = -2147024882;
            goto LABEL_34;
          }
          if ( v6 == 13 )
            goto LABEL_29;
          if ( length < 3 )
            goto LABEL_23;
          v13 = 1953651835 - *(_DWORD *)StringRawBuffer;
          if ( *(_DWORD *)StringRawBuffer == 1953651835 )
            v13 = 12646 - StringRawBuffer[2];
          if ( !v13 )
          {
LABEL_29:
            v17 = 2 * length + 2;
            v18 = (HBITMAP)GlobalAlloc(0x40u, (int)v17);
            v16 = v18;
            if ( !v18 )
            {
              v5 = -2147024882;
              goto LABEL_33;
            }
            memcpy_0(v18, v12, v17 - 2LL);
          }
          else
          {
LABEL_23:
            v29[0] = off_180286F10;
            v30 = v29;
            v27[0] = off_180286F40;
            v28 = v27;
            StringUtil::ConvertFromUnicodeRtf(
              (_DWORD)StringRawBuffer,
              length,
              (unsigned int)v26,
              (unsigned int)v27,
              (__int64)v29);
            if ( v28 )
            {
              v14 = v27;
              LOBYTE(v14) = v28 != v27;
              (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v28 + 32LL))(v28, v14);
              v28 = 0;
            }
            if ( v30 )
            {
              v15 = v29;
              LOBYTE(v15) = v30 != v29;
              (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v30 + 32LL))(v30, v15);
            }
            v16 = (HBITMAP)v26[0];
            if ( !v26[0] )
            {
              v5 = -2147467259;
              goto LABEL_33;
            }
          }
          v5 = 0;
          a3->tymed = 1;
          a3->hBitmap = v16;
        }
LABEL_33:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
        CEventWrapper::~CEventWrapper((CEventWrapper *)&hHandle);
        goto LABEL_34;
      }
      v9 = *((_QWORD *)this + 1);
      v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 136LL);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v5 = v10(v9, &v20);
    if ( v5 )
      goto LABEL_33;
    goto LABEL_15;
  }
LABEL_34:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v24);
  return v5;
}

```

## disassembly

```asm
0x1801f6bf0  mov     [rsp-8+arg_8], rbx
0x1801f6bf5  push    rbp
0x1801f6bf6  push    rsi
0x1801f6bf7  push    rdi
0x1801f6bf8  push    r14
0x1801f6bfa  push    r15
0x1801f6bfc  lea     rbp, [rsp-37h]
0x1801f6c01  sub     rsp, 100h
0x1801f6c08  mov     rax, cs:__security_cookie
0x1801f6c0f  xor     rax, rsp
0x1801f6c12  mov     [rbp+57h+var_30], rax
0x1801f6c16  xor     eax, eax
0x1801f6c18  xorps   xmm0, xmm0
0x1801f6c1b  movups  xmmword ptr [r8], xmm0
0x1801f6c1f  mov     [r8+10h], rax
0x1801f6c23  mov     r15, r8
0x1801f6c26  lea     r8, [rbp+57h+var_D0]; struct Microsoft::WRL::Wrappers::HString *
0x1801f6c2a  mov     [rbp+57h+var_D0], rax
0x1801f6c2e  mov     rdi, rcx
0x1801f6c31  mov     [rsp+120h+string], rax
0x1801f6c36  call    ?SupportsFormatEtc@CClipboardMobileDataObject@@AEAAJPEBUtagFORMATETC@@AEAVHString@Wrappers@WRL@Microsoft@@@Z; CClipboardMobileDataObject::SupportsFormatEtc(tagFORMATETC const *,Microsoft::WRL::Wrappers::HString &)
0x1801f6c3b  mov     ebx, eax
0x1801f6c3d  test    eax, eax
0x1801f6c3f  jnz     loc_1801F6F1C
0x1801f6c45  mov     rcx, [rbp+57h+var_D0]
0x1801f6c49  call    SupportedFormat
0x1801f6c4e  movzx   r14d, ax
0x1801f6c52  mov     eax, 40Eh
0x1801f6c57  cmp     r14w, ax
0x1801f6c5b  jnz     short loc_1801F6C76
0x1801f6c5d  mov     rax, [rdi]
0x1801f6c60  mov     rdx, r15
0x1801f6c63  mov     rcx, rdi
0x1801f6c66  mov     rax, [rax+60h]
0x1801f6c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6c6f  mov     ebx, eax
0x1801f6c71  jmp     loc_1801F6F1C
0x1801f6c76  xor     edx, edx; lpName
0x1801f6c78  mov     [rsp+120h+hHandle], 0
0x1801f6c81  xor     ecx, ecx; lpEventAttributes
0x1801f6c83  mov     r9d, 1F0003h; dwDesiredAccess
0x1801f6c89  lea     r8d, [rdx+1]; dwFlags
0x1801f6c8d  call    cs:__imp_CreateEventExW
0x1801f6c93  mov     [rsp+120h+hHandle], rax
0x1801f6c98  test    rax, rax
0x1801f6c9b  jnz     short loc_1801F6CB1
0x1801f6c9d  lea     rcx, [rsp+120h+hHandle]; this
0x1801f6ca2  call    ??1CEventWrapper@@QEAA@XZ; CEventWrapper::~CEventWrapper(void)
0x1801f6ca7  mov     ebx, 8000FFFFh
0x1801f6cac  jmp     loc_1801F6F1C
0x1801f6cb1  lea     rax, [rsp+120h+hHandle]
0x1801f6cb6  mov     [rsp+120h+var_F0], 0
0x1801f6cbf  mov     [rbp+57h+var_C0], rax
0x1801f6cc3  lea     rdx, [rbp+57h+var_C0]
0x1801f6cc7  lea     rax, [rsp+120h+string]
0x1801f6ccc  lea     rcx, [rbp+57h+var_C8]
0x1801f6cd0  mov     [rbp+57h+var_B8], rax
0x1801f6cd4  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_HSTRING__________Windows__Foundation__IAsyncOperation_HSTRING________enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__IAsyncOperationCompletedHandler_HSTRING______Microsoft__WRL__FtmBase___lambda_3e59cf71de9fa25b6f7d6f3697c38bba_____1_Windows__Foundation__IAsyncOperation_HSTRING________enum_ABI__Windows__Foundation__AsyncStatus___lambda_3e59cf71de9fa25b6f7d6f3697c38bba____
0x1801f6cd9  mov     rsi, [rax]
0x1801f6cdc  mov     qword ptr [rax], 0
0x1801f6ce3  mov     rcx, [rbp+57h+var_C8]
0x1801f6ce7  test    rcx, rcx
0x1801f6cea  jz      short loc_1801F6CF9
0x1801f6cec  mov     [rbp+57h+var_C8], 0
0x1801f6cf4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>>::Release(void)
0x1801f6cf9  test    rsi, rsi
0x1801f6cfc  jnz     short loc_1801F6D1C
0x1801f6cfe  lea     rcx, [rsp+120h+var_F0]
0x1801f6d03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6d08  lea     rcx, [rsp+120h+hHandle]; this
0x1801f6d0d  call    ??1CEventWrapper@@QEAA@XZ; CEventWrapper::~CEventWrapper(void)
0x1801f6d12  mov     ebx, 80004005h
0x1801f6d17  jmp     loc_1801F6F1C
0x1801f6d1c  cmp     r14w, 0Dh
0x1801f6d21  jz      short loc_1801F6D3E
0x1801f6d23  mov     eax, 402h
0x1801f6d28  cmp     r14w, ax
0x1801f6d2c  jnz     short loc_1801F6D6D
0x1801f6d2e  mov     rdi, [rdi+8]
0x1801f6d32  mov     rax, [rdi]
0x1801f6d35  mov     rbx, [rax+88h]
0x1801f6d3c  jmp     short loc_1801F6D49
0x1801f6d3e  mov     rdi, [rdi+8]
0x1801f6d42  mov     rax, [rdi]
0x1801f6d45  mov     rbx, [rax+60h]
0x1801f6d49  lea     rcx, [rsp+120h+var_F0]
0x1801f6d4e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6d53  lea     rdx, [rsp+120h+var_F0]
0x1801f6d58  mov     rcx, rdi
0x1801f6d5b  mov     rax, rbx
0x1801f6d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6d63  mov     ebx, eax
0x1801f6d65  test    eax, eax
0x1801f6d67  jnz     loc_1801F6EF9
0x1801f6d6d  mov     rcx, [rsp+120h+var_F0]
0x1801f6d72  mov     rdx, rsi
0x1801f6d75  mov     rax, [rcx]
0x1801f6d78  mov     rax, [rax+30h]
0x1801f6d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6d81  mov     ebx, eax
0x1801f6d83  test    eax, eax
0x1801f6d85  jnz     loc_1801F6EF9
0x1801f6d8b  mov     rcx, [rsp+120h+hHandle]; hHandle
0x1801f6d90  xor     r8d, r8d; bAlertable
0x1801f6d93  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801f6d96  call    cs:__imp_WaitForSingleObjectEx
0x1801f6d9c  mov     rcx, [rsp+120h+string]; string
0x1801f6da1  lea     rdx, [rsp+120h+length]; length
0x1801f6da6  mov     [rbp+57h+var_C0], 0
0x1801f6dae  mov     [rsp+120h+length], ebx
0x1801f6db2  call    cs:__imp_WindowsGetStringRawBuffer
0x1801f6db8  mov     rbx, rax
0x1801f6dbb  test    rax, rax
0x1801f6dbe  jnz     short loc_1801F6DED
0x1801f6dc0  mov     rax, [rsi]
0x1801f6dc3  mov     rcx, rsi
0x1801f6dc6  mov     rax, [rax+10h]
0x1801f6dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6dcf  lea     rcx, [rsp+120h+var_F0]
0x1801f6dd4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6dd9  lea     rcx, [rsp+120h+hHandle]; this
0x1801f6dde  call    ??1CEventWrapper@@QEAA@XZ; CEventWrapper::~CEventWrapper(void)
0x1801f6de3  mov     ebx, 8007000Eh
0x1801f6de8  jmp     loc_1801F6F1C
0x1801f6ded  mov     edx, [rsp+120h+length]
0x1801f6df1  cmp     r14w, 0Dh
0x1801f6df6  jz      loc_1801F6EB5
0x1801f6dfc  cmp     edx, 3
0x1801f6dff  jb      short loc_1801F6E20
0x1801f6e01  mov     ecx, cs:dword_1802BF308
0x1801f6e07  sub     ecx, [rax]
0x1801f6e09  jnz     short loc_1801F6E18
0x1801f6e0b  movzx   ecx, cs:word_1802BF30C
0x1801f6e12  movzx   eax, word ptr [rax+4]
0x1801f6e16  sub     ecx, eax
0x1801f6e18  test    ecx, ecx
0x1801f6e1a  jz      loc_1801F6EB5
0x1801f6e20  lea     rax, off_180286F10
0x1801f6e27  mov     rcx, rbx
0x1801f6e2a  mov     [rbp+57h+var_70], rax
0x1801f6e2e  lea     r9, [rbp+57h+var_B0]
0x1801f6e32  lea     rax, [rbp+57h+var_70]
0x1801f6e36  mov     [rbp+57h+var_38], rax
0x1801f6e3a  lea     r8, [rbp+57h+var_C0]
0x1801f6e3e  lea     rax, off_180286F40
0x1801f6e45  mov     [rbp+57h+var_B0], rax
0x1801f6e49  lea     rax, [rbp+57h+var_B0]
0x1801f6e4d  mov     [rbp+57h+var_78], rax
0x1801f6e51  lea     rax, [rbp+57h+var_70]
0x1801f6e55  mov     [rsp+120h+var_100], rax
0x1801f6e5a  call    ?ConvertFromUnicodeRtf@StringUtil@@SAXPEBGIPEAPEADAEBV?$function@$$A6APEADAEBI@Z@std@@AEBV?$function@$$A6AXPEAD@Z@3@@Z; StringUtil::ConvertFromUnicodeRtf(ushort const *,uint,char * *,std::function<char * (uint const &)> const &,std::function<void (char *)> const &)
0x1801f6e5f  mov     rcx, [rbp+57h+var_78]
0x1801f6e63  test    rcx, rcx
0x1801f6e66  jz      short loc_1801F6E86
0x1801f6e68  mov     rax, [rcx]
0x1801f6e6b  lea     rdx, [rbp+57h+var_B0]
0x1801f6e6f  cmp     rcx, rdx
0x1801f6e72  setnz   dl
0x1801f6e75  mov     rax, [rax+20h]
0x1801f6e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6e7e  mov     [rbp+57h+var_78], 0
0x1801f6e86  mov     rcx, [rbp+57h+var_38]
0x1801f6e8a  test    rcx, rcx
0x1801f6e8d  jz      short loc_1801F6EA5
0x1801f6e8f  mov     rax, [rcx]
0x1801f6e92  lea     rdx, [rbp+57h+var_70]
0x1801f6e96  cmp     rcx, rdx
0x1801f6e99  setnz   dl
0x1801f6e9c  mov     rax, [rax+20h]
0x1801f6ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6ea5  mov     rdi, [rbp+57h+var_C0]
0x1801f6ea9  test    rdi, rdi
0x1801f6eac  jnz     short loc_1801F6EEC
0x1801f6eae  mov     ebx, 80004005h
0x1801f6eb3  jmp     short loc_1801F6EF9
0x1801f6eb5  lea     r14d, ds:2[rdx*2]
0x1801f6ebd  mov     ecx, 40h ; '@'; uFlags
0x1801f6ec2  movsxd  rdx, r14d; dwBytes
0x1801f6ec5  call    cs:__imp_GlobalAlloc
0x1801f6ecb  mov     rdi, rax
0x1801f6ece  test    rax, rax
0x1801f6ed1  jnz     short loc_1801F6EDA
0x1801f6ed3  mov     ebx, 8007000Eh
0x1801f6ed8  jmp     short loc_1801F6EF9
0x1801f6eda  mov     r8d, r14d
0x1801f6edd  mov     rdx, rbx; Src
0x1801f6ee0  sub     r8, 2; Size
0x1801f6ee4  mov     rcx, rax; void *
0x1801f6ee7  call    memcpy_0
0x1801f6eec  xor     ebx, ebx
0x1801f6eee  mov     dword ptr [r15], 1
0x1801f6ef5  mov     [r15+8], rdi
0x1801f6ef9  mov     rax, [rsi]
0x1801f6efc  mov     rcx, rsi
0x1801f6eff  mov     rax, [rax+10h]
0x1801f6f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6f08  lea     rcx, [rsp+120h+var_F0]
0x1801f6f0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6f12  lea     rcx, [rsp+120h+hHandle]; this
0x1801f6f17  call    ??1CEventWrapper@@QEAA@XZ; CEventWrapper::~CEventWrapper(void)
0x1801f6f1c  mov     rcx, [rsp+120h+string]; string
0x1801f6f21  call    cs:__imp_WindowsDeleteString
0x1801f6f27  mov     rcx, [rbp+57h+var_D0]; string
0x1801f6f2b  mov     [rsp+120h+string], 0
0x1801f6f34  call    cs:__imp_WindowsDeleteString
0x1801f6f3a  mov     eax, ebx
0x1801f6f3c  mov     rcx, [rbp+57h+var_30]
0x1801f6f40  xor     rcx, rsp; StackCookie
0x1801f6f43  call    __security_check_cookie
0x1801f6f48  mov     rbx, [rsp+120h+arg_8]
0x1801f6f50  add     rsp, 100h
0x1801f6f57  pop     r15
0x1801f6f59  pop     r14
0x1801f6f5b  pop     rdi
0x1801f6f5c  pop     rsi
0x1801f6f5d  pop     rbp
0x1801f6f5e  retn
```
