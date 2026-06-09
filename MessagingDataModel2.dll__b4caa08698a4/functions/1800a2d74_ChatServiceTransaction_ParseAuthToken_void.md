# ChatServiceTransaction::_ParseAuthToken(void)

- ea: `0x1800a2d74`
- end: `0x1800a2ffe`
- name: `?_ParseAuthToken@ChatServiceTransaction@@AEAAJXZ`
- size: `650`
- prototype: `__int64 __fastcall(ChatServiceTransaction *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a2d40`

## callees

- `0x180005c50`
- `0x180030bd0`
- `0x180084738`
- `0x18009ace8`
- `0x1800a22a4`
- `0x1800a23d4`
- `0x1800a2d74`
- `0x1800b3b88`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2ef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2ef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2edd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2fac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2edd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2fac`

## pseudocode

```c
__int64 __fastcall ChatServiceTransaction::_ParseAuthToken(ChatServiceTransaction *this)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64); // rcx
  void (*v6)(void); // rax
  char v8; // r8
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, PVOID, _BYTE *); // rbx
  HSTRING_HEADER *v12; // rax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, PVOID, HSTRING *); // rbx
  char v15; // r8
  HSTRING_HEADER *v16; // rax
  int v17; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v19; // rcx
  int v20; // eax
  int v21; // eax
  struct ChatServiceRegistrationToken *v22; // rbx
  __int64 v23; // rcx
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64); // rcx
  struct ChatServiceHttpHeader *v25; // [rsp+30h] [rbp-19h] BYREF
  struct ChatServiceRegistrationToken *v26; // [rsp+38h] [rbp-11h] BYREF
  HSTRING_HEADER v27; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v28[8]; // [rsp+60h] [rbp+17h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64); // [rsp+68h] [rbp+1Fh] BYREF
  HSTRING string; // [rsp+70h] [rbp+27h] BYREF
  __int64 v31; // [rsp+78h] [rbp+2Fh] BYREF

  v2 = *((_QWORD *)this + 2);
  v29 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v2 + 64LL))(
         v2,
         &v29);
  v4 = v3;
  if ( v3 < 0 )
  {
    Log_HREvent_78(v3);
    v5 = v29;
    if ( !v29 )
      return (unsigned int)v4;
    v29 = 0;
    v6 = (void (*)(void))(*v5)[2];
LABEL_4:
    v6();
    return (unsigned int)v4;
  }
  v31 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpResponseHeaderCollection>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>(
         &v29,
         (__int64)&v31);
  if ( v4 < 0
    || (v10 = v31,
        v28[0] = 0,
        v11 = *(__int64 (__fastcall **)(__int64, PVOID, _BYTE *))(*(_QWORD *)v31 + 64LL),
        v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v27, (const WCHAR **)off_1800FD7D8, v8),
        v4 = v11(v10, v12[1].Reserved.Reserved1, v28),
        v4 < 0) )
  {
    Log_HREvent_78(v4);
LABEL_8:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    v9 = v29;
    if ( !v29 )
      return (unsigned int)v4;
    v29 = 0;
    v6 = (void (*)(void))(*v9)[2];
    goto LABEL_4;
  }
  if ( v28[0] )
  {
    v13 = v31;
    string = 0;
    v14 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v31 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v27, (const WCHAR **)off_1800FD7D8, v15);
    v17 = v14(v13, v16[1].Reserved.Reserved1, &string);
    v4 = v17;
    if ( v17 < 0 )
    {
      Log_HREvent_78(v17);
LABEL_14:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_8;
    }
    v25 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v20 = ChatServiceHttpHeader::CreateInstance(v19, StringRawBuffer, &v25);
    v4 = v20;
    if ( v20 < 0 )
    {
      Log_HREvent_78(v20);
LABEL_17:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
      goto LABEL_14;
    }
    v26 = 0;
    v21 = ChatServiceRegistrationToken::CreateInstance(v25, &v26);
    v4 = v21;
    if ( v21 < 0 )
    {
      Log_HREvent_78(v21);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
      goto LABEL_17;
    }
    v22 = v26;
    if ( *((struct ChatServiceRegistrationToken **)this + 9) != v26 )
    {
      if ( v26 )
        (*(void (__fastcall **)(struct ChatServiceRegistrationToken *))(*(_QWORD *)v26 + 8LL))(v26);
      v23 = *((_QWORD *)this + 9);
      *((_QWORD *)this + 9) = v22;
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    WindowsDeleteString(string);
    string = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v24 = v29;
  if ( v29 )
  {
    v29 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v24)[2])(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a2d74  mov     [rsp-8+arg_8], rbx
0x1800a2d79  mov     [rsp-8+arg_10], rsi
0x1800a2d7e  push    rbp
0x1800a2d7f  push    rdi
0x1800a2d80  push    r14
0x1800a2d82  lea     rbp, [rsp-47h]
0x1800a2d87  sub     rsp, 90h
0x1800a2d8e  mov     rax, cs:__security_cookie
0x1800a2d95  xor     rax, rsp
0x1800a2d98  mov     [rbp+57h+var_20], rax
0x1800a2d9c  mov     rsi, rcx
0x1800a2d9f  lea     rdx, [rbp+57h+var_38]
0x1800a2da3  mov     rcx, [rcx+10h]
0x1800a2da7  xor     r14d, r14d
0x1800a2daa  mov     [rbp+57h+var_38], r14
0x1800a2dae  mov     rax, [rcx]
0x1800a2db1  mov     rax, [rax+40h]
0x1800a2db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2dba  mov     ebx, eax
0x1800a2dbc  test    eax, eax
0x1800a2dbe  jns     short loc_1800A2DF1
0x1800a2dc0  lea     edx, [r14+1]
0x1800a2dc4  mov     r9d, 0C5h
0x1800a2dca  mov     ecx, eax; int
0x1800a2dcc  call    Log_HREvent_78
0x1800a2dd1  mov     rcx, [rbp+57h+var_38]
0x1800a2dd5  test    rcx, rcx
0x1800a2dd8  jz      short loc_1800A2DEA
0x1800a2dda  mov     [rbp+57h+var_38], r14
0x1800a2dde  mov     rdx, [rcx]
0x1800a2de1  mov     rax, [rdx+10h]
0x1800a2de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2dea  mov     eax, ebx
0x1800a2dec  jmp     loc_1800A2FDA
0x1800a2df1  lea     rdx, [rbp+57h+var_28]
0x1800a2df5  mov     [rbp+57h+var_28], r14
0x1800a2df9  lea     rcx, [rbp+57h+var_38]
0x1800a2dfd  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@?$ComPtr@UIHttpResponseHeaderCollection@Headers@Http@Web@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpResponseHeaderCollection>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>>)
0x1800a2e02  mov     ebx, eax
0x1800a2e04  test    eax, eax
0x1800a2e06  jns     short loc_1800A2E39
0x1800a2e08  mov     r9d, 0C8h
0x1800a2e0e  mov     edx, 1
0x1800a2e13  mov     ecx, ebx; int
0x1800a2e15  call    Log_HREvent_78
0x1800a2e1a  lea     rcx, [rbp+57h+var_28]
0x1800a2e1e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2e23  mov     rcx, [rbp+57h+var_38]
0x1800a2e27  test    rcx, rcx
0x1800a2e2a  jz      short loc_1800A2DEA
0x1800a2e2c  mov     [rbp+57h+var_38], r14
0x1800a2e30  mov     rax, [rcx]
0x1800a2e33  mov     rax, [rax+10h]
0x1800a2e37  jmp     short loc_1800A2DE5
0x1800a2e39  mov     rdi, [rbp+57h+var_28]
0x1800a2e3d  lea     rdx, off_1800FD7D8; "Set-RegistrationToken"
0x1800a2e44  mov     [rbp+57h+var_40], r14b
0x1800a2e48  lea     rcx, [rbp+57h+var_60]
0x1800a2e4c  mov     rax, [rdi]
0x1800a2e4f  mov     rbx, [rax+40h]
0x1800a2e53  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a2e58  lea     r8, [rbp+57h+var_40]
0x1800a2e5c  mov     rcx, rdi
0x1800a2e5f  mov     rdx, [rax+18h]
0x1800a2e63  mov     rax, rbx
0x1800a2e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2e6b  mov     ebx, eax
0x1800a2e6d  test    eax, eax
0x1800a2e6f  jns     short loc_1800A2E79
0x1800a2e71  mov     r9d, 0CBh
0x1800a2e77  jmp     short loc_1800A2E0E
0x1800a2e79  cmp     [rbp+57h+var_40], r14b
0x1800a2e7d  jz      loc_1800A2FB6
0x1800a2e83  mov     rdi, [rbp+57h+var_28]
0x1800a2e87  xor     ecx, ecx; string
0x1800a2e89  mov     [rbp+57h+string], r14
0x1800a2e8d  mov     rax, [rdi]
0x1800a2e90  mov     rbx, [rax+30h]
0x1800a2e94  call    cs:__imp_WindowsDeleteString
0x1800a2e9a  lea     rdx, off_1800FD7D8; "Set-RegistrationToken"
0x1800a2ea1  mov     [rbp+57h+string], r14
0x1800a2ea5  lea     rcx, [rbp+57h+var_60]
0x1800a2ea9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a2eae  lea     r8, [rbp+57h+string]
0x1800a2eb2  mov     rcx, rdi
0x1800a2eb5  mov     rdx, [rax+18h]
0x1800a2eb9  mov     rax, rbx
0x1800a2ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2ec1  mov     ebx, eax
0x1800a2ec3  test    eax, eax
0x1800a2ec5  jns     short loc_1800A2EEC
0x1800a2ec7  mov     edx, 1
0x1800a2ecc  mov     r9d, 0D4h
0x1800a2ed2  mov     ecx, eax; int
0x1800a2ed4  call    Log_HREvent_78
0x1800a2ed9  mov     rcx, [rbp+57h+string]; string
0x1800a2edd  call    cs:__imp_WindowsDeleteString
0x1800a2ee3  mov     [rbp+57h+string], r14
0x1800a2ee7  jmp     loc_1800A2E1A
0x1800a2eec  mov     rcx, [rbp+57h+string]; string
0x1800a2ef0  xor     edx, edx; length
0x1800a2ef2  mov     [rbp+57h+var_70], r14
0x1800a2ef6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2efc  mov     rdx, rax; unsigned __int16 *
0x1800a2eff  lea     r8, [rbp+57h+var_70]; struct ChatServiceHttpHeader **
0x1800a2f03  call    ?CreateInstance@ChatServiceHttpHeader@@SAJPEBG0PEAPEAV1@@Z; ChatServiceHttpHeader::CreateInstance(ushort const *,ushort const *,ChatServiceHttpHeader * *)
0x1800a2f08  mov     ebx, eax
0x1800a2f0a  test    eax, eax
0x1800a2f0c  jns     short loc_1800A2F2B
0x1800a2f0e  mov     edx, 1
0x1800a2f13  mov     r9d, 0D8h
0x1800a2f19  mov     ecx, eax; int
0x1800a2f1b  call    Log_HREvent_78
0x1800a2f20  lea     rcx, [rbp+57h+var_70]
0x1800a2f24  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a2f29  jmp     short loc_1800A2ED9
0x1800a2f2b  mov     rcx, [rbp+57h+var_70]; struct ChatServiceHttpHeader *
0x1800a2f2f  lea     rdx, [rbp+57h+var_68]; struct ChatServiceRegistrationToken **
0x1800a2f33  mov     [rbp+57h+var_68], r14
0x1800a2f37  call    ?CreateInstance@ChatServiceRegistrationToken@@SAJPEAVChatServiceHttpHeader@@PEAPEAV1@@Z; ChatServiceRegistrationToken::CreateInstance(ChatServiceHttpHeader *,ChatServiceRegistrationToken * *)
0x1800a2f3c  mov     ebx, eax
0x1800a2f3e  test    eax, eax
0x1800a2f40  jns     short loc_1800A2F5F
0x1800a2f42  mov     edx, 1
0x1800a2f47  mov     r9d, 0DBh
0x1800a2f4d  mov     ecx, eax; int
0x1800a2f4f  call    Log_HREvent_78
0x1800a2f54  lea     rcx, [rbp+57h+var_68]
0x1800a2f58  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a2f5d  jmp     short loc_1800A2F20
0x1800a2f5f  mov     rbx, [rbp+57h+var_68]
0x1800a2f63  cmp     [rsi+48h], rbx
0x1800a2f67  jz      short loc_1800A2F96
0x1800a2f69  test    rbx, rbx
0x1800a2f6c  jz      short loc_1800A2F7D
0x1800a2f6e  mov     rax, [rbx]
0x1800a2f71  mov     rcx, rbx
0x1800a2f74  mov     rax, [rax+8]
0x1800a2f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f7d  mov     rcx, [rsi+48h]
0x1800a2f81  mov     [rsi+48h], rbx
0x1800a2f85  test    rcx, rcx
0x1800a2f88  jz      short loc_1800A2F96
0x1800a2f8a  mov     rax, [rcx]
0x1800a2f8d  mov     rax, [rax+10h]
0x1800a2f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2f96  lea     rcx, [rbp+57h+var_68]
0x1800a2f9a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a2f9f  lea     rcx, [rbp+57h+var_70]
0x1800a2fa3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a2fa8  mov     rcx, [rbp+57h+string]; string
0x1800a2fac  call    cs:__imp_WindowsDeleteString
0x1800a2fb2  mov     [rbp+57h+string], r14
0x1800a2fb6  lea     rcx, [rbp+57h+var_28]
0x1800a2fba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2fbf  mov     rcx, [rbp+57h+var_38]
0x1800a2fc3  test    rcx, rcx
0x1800a2fc6  jz      short loc_1800A2FD8
0x1800a2fc8  mov     [rbp+57h+var_38], r14
0x1800a2fcc  mov     rax, [rcx]
0x1800a2fcf  mov     rax, [rax+10h]
0x1800a2fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2fd8  xor     eax, eax
0x1800a2fda  mov     rcx, [rbp+57h+var_20]
0x1800a2fde  xor     rcx, rsp; StackCookie
0x1800a2fe1  call    __security_check_cookie
0x1800a2fe6  lea     r11, [rsp+0A0h+var_10]
0x1800a2fee  mov     rbx, [r11+28h]
0x1800a2ff2  mov     rsi, [r11+30h]
0x1800a2ff6  mov     rsp, r11
0x1800a2ff9  pop     r14
0x1800a2ffb  pop     rdi
0x1800a2ffc  pop     rbp
0x1800a2ffd  retn
```
