# Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::SendCommand(Windows::Media::Devices::IAudioDeviceModule *,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer * *)

- ea: `0x14008b1c0`
- end: `0x14008b6dc`
- name: `?SendCommand@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@UEAAJPEAUIAudioDeviceModule@345@PEAUIBuffer@Streams@Storage@5@PEAPEAU7895@@Z`
- size: `1308`
- prototype: `__int64 __fastcall(Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *__hidden this, struct Windows::Media::Devices::IAudioDeviceModule *, struct Windows::Storage::Streams::IBuffer *, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x140016734`
- `0x140035d34`
- `0x140059a0c`
- `0x14005d0e0`
- `0x14008444c`
- `0x14008b1c0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14008b43d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14008b43d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b50a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b55f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b5f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b67b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b50a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b55f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b5f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14008b67b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14008b387`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14008b387`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14008b2af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14008b4a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14008b2af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14008b4a6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14008b44a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14008b44a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008b532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008b6a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008b6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008b532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008b6a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008b6b4`

## string_xrefs

- `0x14008b5b4`: `Windows.Storage.Streams.DataWriter`

## pseudocode

```c
__int64 __fastcall Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::SendCommand(
        Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *this,
        struct Windows::Media::Devices::IAudioDeviceModule *a2,
        struct Windows::Storage::Streams::IBuffer *a3,
        struct Windows::Storage::Streams::IBuffer **a4)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned __int64 v10; // r9
  int v11; // eax
  unsigned int v12; // r15d
  struct KSIDENTIFIER *v13; // rdi
  int v14; // eax
  __int64 (__fastcall *v15)(struct Windows::Media::Devices::IAudioDeviceModule *, HSTRING *); // rbx
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // rax
  int ActivationFactory; // eax
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, struct Windows::Storage::Streams::IBuffer *, __int64 *); // r14
  __int64 v25; // r8
  int v26; // eax
  int v27; // eax
  const OLECHAR *StringRawBuffer; // rax
  HRESULT v29; // eax
  int v30; // eax
  void *v31; // rbx
  int v32; // esi
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rdx
  unsigned int v37; // [rsp+20h] [rbp-59h]
  HSTRING string; // [rsp+30h] [rbp-49h] BYREF
  __int64 v39; // [rsp+38h] [rbp-41h] BYREF
  __int64 v40; // [rsp+40h] [rbp-39h] BYREF
  __int64 v41; // [rsp+48h] [rbp-31h] BYREF
  SIZE_T cb; // [rsp+50h] [rbp-29h] BYREF
  ULONG v43; // [rsp+58h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-19h] BYREF
  __int64 v45; // [rsp+78h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  cb = 0;
  v43 = 0;
  v41 = 0;
  v39 = 0;
  v40 = 0;
  string = 0;
  if ( a2 )
  {
    if ( !a3 )
    {
      v8 = 2546;
      goto LABEL_3;
    }
    if ( !a4 )
    {
      v9 = -2147467261;
      v8 = 2547;
      goto LABEL_4;
    }
    *a4 = 0;
    v11 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, char *))(*(_QWORD *)a3 + 56LL))(
            a3,
            (char *)&cb + 4);
    v9 = v11;
    if ( v11 < 0 )
    {
      v10 = (unsigned int)v11;
      v8 = 2551;
      goto LABEL_5;
    }
    v12 = HIDWORD(cb) + 48;
    v13 = (struct KSIDENTIFIER *)CoTaskMemAlloc((unsigned int)(HIDWORD(cb) + 48));
    if ( !v13 )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9FB,
        (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
        (const char *)0x8007000ELL,
        v37);
      goto LABEL_6;
    }
    v14 = (*(__int64 (__fastcall **)(struct Windows::Media::Devices::IAudioDeviceModule *, ULONG *))(*(_QWORD *)a2 + 64LL))(
            a2,
            &v43);
    v9 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9FF,
        (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
        (const char *)(unsigned int)v14,
        v37);
LABEL_45:
      WindowsDeleteString(string);
      string = 0;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
      goto LABEL_61;
    }
    v15 = *(__int64 (__fastcall **)(struct Windows::Media::Devices::IAudioDeviceModule *, HSTRING *))(*(_QWORD *)a2 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    v16 = v15(a2, &string);
    v9 = v16;
    if ( v16 < 0 )
    {
      v18 = (unsigned int)v16;
      v19 = 2560;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
        (const char *)v18,
        v37);
      goto LABEL_45;
    }
    v20 = v41;
    v41 = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v21 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      (HSTRING *)&hstringHeader,
                      (const unsigned __int16 (*)[35])v17);
    ActivationFactory = RoGetActivationFactory(*v21, &GUID_11fcbfc8_f93a_471b_b121_f379e349313c, &v41);
    v9 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v18 = (unsigned int)ActivationFactory;
      v19 = 2561;
      goto LABEL_44;
    }
    v23 = v41;
    v24 = *(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer *, __int64 *))(*(_QWORD *)v41 + 48LL);
    v25 = v40;
    v40 = 0;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v26 = v24(v23, a3, &v40);
    v9 = v26;
    if ( v26 < 0 )
    {
      v18 = (unsigned int)v26;
      v19 = 2562;
      goto LABEL_44;
    }
    v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct KSIDENTIFIER *))(*(_QWORD *)v40 + 112LL))(
            v40,
            HIDWORD(cb),
            v13 + 2);
    v9 = v27;
    if ( v27 < 0 )
    {
      v18 = (unsigned int)v27;
      v19 = 2563;
      goto LABEL_44;
    }
    v13->Set = GUID_c034fdb0_ff75_47c8_aa3c_ee46716b50c6;
    v13->Id = 2;
    v13->Flags = 1;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v29 = CLSIDFromString(StringRawBuffer, &v13[1].Set);
    v9 = v29;
    if ( v29 < 0 )
    {
      v18 = (unsigned int)v29;
      v19 = 2567;
      goto LABEL_44;
    }
    v13[1].Id = v43;
    v30 = Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::KsSendProperty(
            this,
            v13,
            v12,
            0,
            0,
            (unsigned int *)&cb);
    v9 = v30;
    if ( (!v30 || v30 == -2147024662) && (_DWORD)cb )
    {
      v31 = CoTaskMemAlloc((unsigned int)cb);
      if ( !v31 )
      {
        v9 = -2147024882;
        v19 = 2584;
LABEL_43:
        v18 = v9;
        goto LABEL_44;
      }
      v32 = Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::KsSendProperty(
              this,
              v13,
              v12,
              v31,
              cb,
              (unsigned int *)&cb);
      if ( v32 < 0 )
      {
        v33 = 2589;
LABEL_38:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
          (const char *)(unsigned int)v32,
          v37);
        WindowsDeleteString(string);
        string = 0;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
LABEL_39:
        CoTaskMemFree(v31);
LABEL_40:
        v9 = v32;
LABEL_61:
        CoTaskMemFree(v13);
        return v9;
      }
    }
    else
    {
      if ( v30 < 0 )
      {
        v19 = 2593;
        goto LABEL_43;
      }
      v31 = 0;
    }
    v34 = v39;
    v39 = 0;
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v45 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Storage.Streams.DataWriter",
      0x23u,
      0x22u);
    v32 = Windows::Foundation::ActivateInstance<Windows::Storage::Streams::IDataWriter>(v45, &v39);
    if ( v32 >= 0 )
    {
      if ( v31 )
      {
        v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v39 + 96LL))(v39, (unsigned int)cb, v31);
        if ( v32 < 0 )
        {
          v33 = 2601;
          goto LABEL_38;
        }
      }
      v32 = (*(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer **))(*(_QWORD *)v39 + 248LL))(
              v39,
              a4);
      if ( v32 >= 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
        if ( v31 )
          CoTaskMemFree(v31);
        v9 = 0;
        goto LABEL_61;
      }
      v35 = 2603;
    }
    else
    {
      v35 = 2597;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
      (const char *)(unsigned int)v32,
      v37);
    WindowsDeleteString(string);
    string = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    if ( !v31 )
      goto LABEL_40;
    goto LABEL_39;
  }
  v8 = 2545;
LABEL_3:
  v9 = -2147024809;
LABEL_4:
  v10 = v9;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
    (const char *)v10,
    v37);
LABEL_6:
  WindowsDeleteString(string);
  string = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  return v9;
}

```

## disassembly

```asm
0x14008b1c0  push    rbp
0x14008b1c2  push    rbx
0x14008b1c3  push    rsi
0x14008b1c4  push    rdi
0x14008b1c5  push    r12
0x14008b1c7  push    r13
0x14008b1c9  push    r14
0x14008b1cb  push    r15
0x14008b1cd  lea     rbp, [rsp-1Fh]
0x14008b1d2  sub     rsp, 98h
0x14008b1d9  mov     rax, cs:__security_cookie
0x14008b1e0  xor     rax, rsp
0x14008b1e3  mov     [rbp+57h+var_50], rax
0x14008b1e7  mov     r12, r9
0x14008b1ea  mov     rsi, r8
0x14008b1ed  mov     r14, rdx
0x14008b1f0  mov     r13, rcx
0x14008b1f3  xor     edi, edi
0x14008b1f5  mov     dword ptr [rbp+57h+cb], edi
0x14008b1f8  mov     dword ptr [rbp+57h+cb+4], edi
0x14008b1fb  mov     [rbp+57h+var_78], edi
0x14008b1fe  mov     [rbp+57h+var_88], rdi
0x14008b202  mov     [rbp+57h+var_98], rdi
0x14008b206  mov     [rbp+57h+var_90], rdi
0x14008b20a  mov     [rbp+57h+string], rdi
0x14008b20e  test    rdx, rdx
0x14008b211  jnz     short loc_14008B25E
0x14008b213  mov     edx, 9F1h; void *
0x14008b218  mov     ebx, 80070057h
0x14008b21d  mov     r9d, ebx; char *
0x14008b220  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14008b227  mov     rcx, [rbp+5Fh]; this
0x14008b22b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008b230  mov     rcx, [rbp+57h+string]; string
0x14008b234  call    cs:__imp_WindowsDeleteString
0x14008b23a  mov     [rbp+57h+string], rdi
0x14008b23e  lea     rcx, [rbp+57h+var_90]
0x14008b242  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b247  lea     rcx, [rbp+57h+var_98]
0x14008b24b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b250  lea     rcx, [rbp+57h+var_88]
0x14008b254  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b259  jmp     loc_14008B6BA
0x14008b25e  test    rsi, rsi
0x14008b261  jnz     short loc_14008B26A
0x14008b263  mov     edx, 9F2h
0x14008b268  jmp     short loc_14008B218
0x14008b26a  test    r12, r12
0x14008b26d  jnz     short loc_14008B27B
0x14008b26f  mov     ebx, 80004003h
0x14008b274  mov     edx, 9F3h
0x14008b279  jmp     short loc_14008B21D
0x14008b27b  mov     [r9], rdi
0x14008b27e  mov     rax, [r8]
0x14008b281  lea     rdx, [rbp+57h+cb+4]
0x14008b285  mov     rcx, rsi
0x14008b288  mov     rax, [rax+38h]
0x14008b28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b291  mov     ebx, eax
0x14008b293  test    eax, eax
0x14008b295  jns     short loc_14008B2A4
0x14008b297  mov     r9d, eax
0x14008b29a  mov     edx, 9F7h
0x14008b29f  jmp     loc_14008B220
0x14008b2a4  mov     r15d, dword ptr [rbp+57h+cb+4]
0x14008b2a8  add     r15d, 30h ; '0'
0x14008b2ac  mov     ecx, r15d; cb
0x14008b2af  call    cs:__imp_CoTaskMemAlloc
0x14008b2b5  mov     rdi, rax
0x14008b2b8  test    rax, rax
0x14008b2bb  jnz     short loc_14008B2DF
0x14008b2bd  mov     rcx, [rbp+5Fh]; this
0x14008b2c1  mov     ebx, 8007000Eh
0x14008b2c6  mov     r9d, ebx; char *
0x14008b2c9  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14008b2d0  mov     edx, 9FBh; void *
0x14008b2d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008b2da  jmp     loc_14008B230
0x14008b2df  mov     rax, [r14]
0x14008b2e2  lea     rdx, [rbp+57h+var_78]
0x14008b2e6  mov     rcx, r14
0x14008b2e9  mov     rax, [rax+40h]
0x14008b2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b2f2  mov     ebx, eax
0x14008b2f4  test    eax, eax
0x14008b2f6  jns     short loc_14008B318
0x14008b2f8  mov     rcx, [rbp+5Fh]; this
0x14008b2fc  mov     r9d, eax; char *
0x14008b2ff  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14008b306  mov     edx, 9FFh; void *
0x14008b30b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008b310  xor     r14d, r14d
0x14008b313  jmp     loc_14008B55B
0x14008b318  mov     rax, [r14]
0x14008b31b  mov     rbx, [rax+30h]
0x14008b31f  mov     rcx, [rbp+57h+string]; string
0x14008b323  call    cs:__imp_WindowsDeleteString
0x14008b329  mov     [rbp+57h+string], 0
0x14008b331  lea     rdx, [rbp+57h+string]
0x14008b335  mov     rcx, r14
0x14008b338  mov     rax, rbx
0x14008b33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b340  mov     ebx, eax
0x14008b342  xor     r14d, r14d
0x14008b345  test    eax, eax
0x14008b347  jns     short loc_14008B356
0x14008b349  mov     r9d, eax
0x14008b34c  mov     edx, 0A00h
0x14008b351  jmp     loc_14008B54B
0x14008b356  mov     rcx, [rbp+57h+var_88]
0x14008b35a  mov     [rbp+57h+var_88], r14
0x14008b35e  test    rcx, rcx
0x14008b361  jz      short loc_14008B370
0x14008b363  mov     rax, [rcx]
0x14008b366  mov     rax, [rax+10h]
0x14008b36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b36f  nop
0x14008b370  lea     rcx, [rbp+57h+hstringHeader]; string
0x14008b374  call    ??$?0$0CD@@StringReference@Internal@Windows@@QEAA@AEAY0CD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[35])
0x14008b379  lea     r8, [rbp+57h+var_88]
0x14008b37d  lea     rdx, _GUID_11fcbfc8_f93a_471b_b121_f379e349313c
0x14008b384  mov     rcx, [rax]
0x14008b387  call    cs:__imp_RoGetActivationFactory
0x14008b38d  mov     ebx, eax
0x14008b38f  test    eax, eax
0x14008b391  jns     short loc_14008B3A0
0x14008b393  mov     r9d, eax
0x14008b396  mov     edx, 0A01h
0x14008b39b  jmp     loc_14008B54B
0x14008b3a0  mov     rbx, [rbp+57h+var_88]
0x14008b3a4  mov     rax, [rbx]
0x14008b3a7  mov     r14, [rax+30h]
0x14008b3ab  mov     r8, [rbp+57h+var_90]
0x14008b3af  mov     [rbp+57h+var_90], 0
0x14008b3b7  test    r8, r8
0x14008b3ba  jz      short loc_14008B3CC
0x14008b3bc  mov     rcx, [r8]
0x14008b3bf  mov     rax, [rcx+10h]
0x14008b3c3  mov     rcx, r8
0x14008b3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b3cb  nop
0x14008b3cc  lea     r8, [rbp+57h+var_90]
0x14008b3d0  mov     rdx, rsi
0x14008b3d3  mov     rcx, rbx
0x14008b3d6  mov     rax, r14
0x14008b3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b3de  mov     ebx, eax
0x14008b3e0  xor     r14d, r14d
0x14008b3e3  test    eax, eax
0x14008b3e5  jns     short loc_14008B3F4
0x14008b3e7  mov     r9d, eax
0x14008b3ea  mov     edx, 0A02h
0x14008b3ef  jmp     loc_14008B54B
0x14008b3f4  mov     rcx, [rbp+57h+var_90]
0x14008b3f8  mov     rax, [rcx]
0x14008b3fb  lea     r8, [rdi+30h]
0x14008b3ff  mov     edx, dword ptr [rbp+57h+cb+4]
0x14008b402  mov     rax, [rax+70h]
0x14008b406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b40b  mov     ebx, eax
0x14008b40d  test    eax, eax
0x14008b40f  jns     short loc_14008B41E
0x14008b411  mov     r9d, eax
0x14008b414  mov     edx, 0A03h
0x14008b419  jmp     loc_14008B54B
0x14008b41e  movups  xmm0, xmmword ptr cs:_GUID_c034fdb0_ff75_47c8_aa3c_ee46716b50c6.Data1
0x14008b425  movdqu  xmmword ptr [rdi], xmm0
0x14008b429  mov     dword ptr [rdi+10h], 2
0x14008b430  mov     dword ptr [rdi+14h], 1
0x14008b437  xor     edx, edx; length
0x14008b439  mov     rcx, [rbp+57h+string]; string
0x14008b43d  call    cs:__imp_WindowsGetStringRawBuffer
0x14008b443  lea     rdx, [rdi+18h]; pclsid
0x14008b447  mov     rcx, rax; lpsz
0x14008b44a  call    cs:__imp_CLSIDFromString
0x14008b450  mov     ebx, eax
0x14008b452  test    eax, eax
0x14008b454  jns     short loc_14008B463
0x14008b456  mov     r9d, eax
0x14008b459  mov     edx, 0A07h
0x14008b45e  jmp     loc_14008B54B
0x14008b463  mov     eax, [rbp+57h+var_78]
0x14008b466  mov     [rdi+28h], eax
0x14008b469  lea     rax, [rbp+57h+cb]
0x14008b46d  mov     [rsp+0D0h+var_A8], rax; unsigned int *
0x14008b472  mov     [rsp+0D0h+var_B0], r14d; int
0x14008b477  xor     r9d, r9d; void *
0x14008b47a  mov     r8d, r15d; unsigned int
0x14008b47d  mov     rdx, rdi; struct KSIDENTIFIER *
0x14008b480  mov     rcx, r13; this
0x14008b483  call    ?KsSendProperty@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@AEAAJPEAUKSIDENTIFIER@@KPEAXIPEAK@Z; Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::KsSendProperty(KSIDENTIFIER *,ulong,void *,uint,ulong *)
0x14008b488  mov     ebx, eax
0x14008b48a  test    eax, eax
0x14008b48c  jz      short loc_14008B499
0x14008b48e  cmp     eax, 800700EAh
0x14008b493  jnz     loc_14008B53F
0x14008b499  mov     eax, dword ptr [rbp+57h+cb]
0x14008b49c  test    eax, eax
0x14008b49e  jz      loc_14008B53F
0x14008b4a4  mov     ecx, eax; cb
0x14008b4a6  call    cs:__imp_CoTaskMemAlloc
0x14008b4ac  mov     rbx, rax
0x14008b4af  test    rax, rax
0x14008b4b2  jnz     short loc_14008B4C3
0x14008b4b4  mov     ebx, 8007000Eh
0x14008b4b9  mov     edx, 0A18h
0x14008b4be  jmp     loc_14008B548
0x14008b4c3  mov     eax, dword ptr [rbp+57h+cb]
0x14008b4c6  lea     rcx, [rbp+57h+cb]
0x14008b4ca  mov     [rsp+0D0h+var_A8], rcx; unsigned int *
0x14008b4cf  mov     [rsp+0D0h+var_B0], eax; int
0x14008b4d3  mov     r9, rbx; void *
0x14008b4d6  mov     r8d, r15d; unsigned int
0x14008b4d9  mov     rdx, rdi; struct KSIDENTIFIER *
0x14008b4dc  mov     rcx, r13; this
0x14008b4df  call    ?KsSendProperty@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@AEAAJPEAUKSIDENTIFIER@@KPEAXIPEAK@Z; Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::KsSendProperty(KSIDENTIFIER *,ulong,void *,uint,ulong *)
0x14008b4e4  mov     esi, eax
0x14008b4e6  test    eax, eax
0x14008b4e8  jns     loc_14008B58C
0x14008b4ee  mov     edx, 0A1Dh; void *
0x14008b4f3  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14008b4fa  mov     r9d, esi; char *
0x14008b4fd  mov     rcx, [rbp+5Fh]; this
0x14008b501  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008b506  mov     rcx, [rbp+57h+string]; string
0x14008b50a  call    cs:__imp_WindowsDeleteString
0x14008b510  mov     [rbp+57h+string], r14
0x14008b514  lea     rcx, [rbp+57h+var_90]
0x14008b518  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b51d  lea     rcx, [rbp+57h+var_98]
0x14008b521  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b526  lea     rcx, [rbp+57h+var_88]
0x14008b52a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b52f  mov     rcx, rbx; pv
0x14008b532  call    cs:__imp_CoTaskMemFree
0x14008b538  mov     ebx, esi
0x14008b53a  jmp     loc_14008B6B1
0x14008b53f  test    ebx, ebx
0x14008b541  jns     short loc_14008B589
0x14008b543  mov     edx, 0A21h; void *
0x14008b548  mov     r9d, ebx; char *
0x14008b54b  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14008b552  mov     rcx, [rbp+5Fh]; this
0x14008b556  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008b55b  mov     rcx, [rbp+57h+string]; string
0x14008b55f  call    cs:__imp_WindowsDeleteString
0x14008b565  mov     [rbp+57h+string], r14
0x14008b569  lea     rcx, [rbp+57h+var_90]
0x14008b56d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b572  lea     rcx, [rbp+57h+var_98]
0x14008b576  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b57b  lea     rcx, [rbp+57h+var_88]
0x14008b57f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b584  jmp     loc_14008B6B1
0x14008b589  mov     rbx, r14
0x14008b58c  mov     rcx, [rbp+57h+var_98]
0x14008b590  mov     [rbp+57h+var_98], r14
0x14008b594  test    rcx, rcx
0x14008b597  jz      short loc_14008B5A6
0x14008b599  mov     rax, [rcx]
0x14008b59c  mov     rax, [rax+10h]
0x14008b5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b5a5  nop
0x14008b5a6  mov     [rbp+57h+var_58], r14
0x14008b5aa  mov     r9d, 22h ; '"'; unsigned int
0x14008b5b0  lea     r8d, [r9+1]; unsigned int
0x14008b5b4  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_DataWriter@@3QBGB; "Windows.Storage.Streams.DataWriter"
0x14008b5bb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x14008b5bf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14008b5c4  lea     rdx, [rbp+57h+var_98]
0x14008b5c8  mov     rcx, [rbp+57h+var_58]
0x14008b5cc  call    ??$ActivateInstance@UIDataWriter@Streams@Storage@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIDataWriter@Streams@Storage@1@@Z; Windows::Foundation::ActivateInstance<Windows::Storage::Streams::IDataWriter>(HSTRING__ *,Windows::Storage::Streams::IDataWriter * *)
0x14008b5d1  mov     esi, eax
0x14008b5d3  test    eax, eax
0x14008b5d5  jns     short loc_14008B626
0x14008b5d7  mov     edx, 0A25h; void *
0x14008b5dc  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14008b5e3  mov     r9d, esi; char *
0x14008b5e6  mov     rcx, [rbp+5Fh]; this
0x14008b5ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008b5ef  mov     rcx, [rbp+57h+string]; string
0x14008b5f3  call    cs:__imp_WindowsDeleteString
0x14008b5f9  mov     [rbp+57h+string], r14
0x14008b5fd  lea     rcx, [rbp+57h+var_90]
0x14008b601  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b606  lea     rcx, [rbp+57h+var_98]
0x14008b60a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b60f  lea     rcx, [rbp+57h+var_88]
0x14008b613  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008b618  test    rbx, rbx
0x14008b61b  jz      loc_14008B538
0x14008b621  jmp     loc_14008B52F
0x14008b626  test    rbx, rbx
0x14008b629  jz      short loc_14008B651
0x14008b62b  mov     rcx, [rbp+57h+var_98]
0x14008b62f  mov     rax, [rcx]
0x14008b632  mov     r8, rbx
0x14008b635  mov     edx, dword ptr [rbp+57h+cb]
0x14008b638  mov     rax, [rax+60h]
0x14008b63c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
