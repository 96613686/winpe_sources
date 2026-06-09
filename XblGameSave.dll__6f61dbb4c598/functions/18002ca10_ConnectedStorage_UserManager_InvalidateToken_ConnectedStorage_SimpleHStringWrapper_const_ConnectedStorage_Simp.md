# ConnectedStorage::UserManager::InvalidateToken(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)

- ea: `0x18002ca10`
- end: `0x18002cd0d`
- name: `?InvalidateToken@UserManager@ConnectedStorage@@UEBAXAEBVSimpleHStringWrapper@2@00@Z`
- size: `765`
- prototype: `void __fastcall(ConnectedStorage::UserManager *__hidden this, const struct ConnectedStorage::SimpleHStringWrapper *, const struct ConnectedStorage::SimpleHStringWrapper *, const struct ConnectedStorage::SimpleHStringWrapper *)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180010e6c`
- `0x180012c98`
- `0x18001b9c8`
- `0x18001c090`
- `0x18001c63c`
- `0x180020898`
- `0x1800294dc`
- `0x1800298cc`
- `0x180029e84`
- `0x18002a1c0`
- `0x18002afdc`
- `0x18002ca10`
- `0x18002d880`
- `0x18002da8c`
- `0x180085038`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbb8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ca7d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ca7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cc22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002cc22`

## string_xrefs

- `0x18002ca87`: `CoCreateInstance( __uuidof(XblAuthManager), nullptr, CLSCTX_LOCAL_SERVER, IID_PPV_ARGS(&authManager))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ConnectedStorage::UserManager::InvalidateToken(
        ConnectedStorage::UserManager *this,
        HSTRING *a2,
        const struct ConnectedStorage::SimpleHStringWrapper *a3,
        const struct ConnectedStorage::SimpleHStringWrapper *a4)
{
  ConnectedStorage::UserManager *v4; // rbx
  HRESULT v5; // eax
  const unsigned __int16 *v6; // r8
  __int64 AuthHeaderForCachedUser; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r14
  struct IUnknown *v12; // rdx
  ConnectedStorage *v13; // rcx
  unsigned __int64 v14; // rsi
  LPVOID v15; // rdi
  int (__fastcall *v16)(LPVOID, __int64, unsigned __int64, const wchar_t *, PCWSTR, const WCHAR *, _QWORD, _DWORD, ConnectedStorage::UserManager **, __int64 *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  char *v21; // r8
  ConnectedStorage::UserManager *v22; // [rsp+60h] [rbp-108h] BYREF
  __int64 v23; // [rsp+68h] [rbp-100h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-F8h] BYREF
  const struct ConnectedStorage::SimpleHStringWrapper *v25; // [rsp+78h] [rbp-F0h] BYREF
  _QWORD v26[2]; // [rsp+80h] [rbp-E8h] BYREF
  HSTRING *v27; // [rsp+90h] [rbp-D8h]
  IUnknown *ppOldObject; // [rsp+98h] [rbp-D0h] BYREF
  _BYTE v29[8]; // [rsp+A0h] [rbp-C8h] BYREF
  _BYTE v30[8]; // [rsp+A8h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[4]; // [rsp+B0h] [rbp-B8h] BYREF
  _BYTE v32[16]; // [rsp+D0h] [rbp-98h] BYREF
  __int64 v33; // [rsp+E0h] [rbp-88h]
  _DWORD v34[16]; // [rsp+F0h] [rbp-78h] BYREF

  v4 = this;
  v27 = a2;
  v22 = this;
  v26[0] = a3;
  v25 = a4;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  v5 = CoCreateInstance(
         &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
         0,
         4u,
         &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
         &ppv);
  if ( v5 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v5,
      (int)L"CoCreateInstance( __uuidof(XblAuthManager), nullptr, CLSCTX_LOCAL_SERVER, IID_PPV_ARGS(&authManager))",
      v6);
  std::wstring::wstring(v32);
  try
  {
    AuthHeaderForCachedUser = ConnectedStorage::UserManager::GetAuthHeaderForCachedUser(
                                v4,
                                lpCriticalSection,
                                v26[0],
                                v25);
    std::wstring::operator=(v32, AuthHeaderForCachedUser);
    std::wstring::_Tidy_deallocate(lpCriticalSection);
  }
  catch ( ConnectedStorage::ComError v34 )
  {
    LODWORD(v23) = v34[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v34);
    v4 = v22;
    if ( (int)v23 < 0 )
      goto LABEL_8;
  }
  catch ( std::bad_alloc )
  {
    v4 = v22;
    goto LABEL_8;
  }
  catch ( ... )
  {
    v4 = v22;
    goto LABEL_8;
  }
  if ( v33 )
  {
    std::wstring::wstring(lpCriticalSection);
    ConnectedStorage::UserManager::UpdateAuthHeaderCache(v4, v26[0], v25, lpCriticalSection);
    std::wstring::_Tidy_deallocate(lpCriticalSection);
    goto LABEL_11;
  }
LABEL_8:
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)v4 + 168),
    v21);
  std::vector<ConnectedStorage::BlobRecord>::end((char *)v4 + 216, v29);
  v9 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v8, v30);
  v26[1] = v25;
  std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ConnectedStorage::UserManager::UserInfo_______lambda_a717a87f1fe21e15a1e5700b403a2f5e___(
    &v25,
    *v9,
    v10,
    v26);
  v11 = *(_QWORD *)v25;
  LeaveCriticalSection(lpCriticalSection[0]);
  ConnectedStorage::ScopedCallContext::ScopedCallContext(&ppOldObject, v12);
  v22 = 0;
  v23 = 0;
  v14 = (unsigned __int64)L"49312658" & -(__int64)ConnectedStorage::IsRunningOnConsole(v13);
  v15 = ppv;
  v16 = *(int (__fastcall **)(LPVOID, __int64, unsigned __int64, const wchar_t *, PCWSTR, const WCHAR *, _QWORD, _DWORD, ConnectedStorage::UserManager **, __int64 *))(*(_QWORD *)ppv + 464LL);
  ConnectedStorage::TaskMem<unsigned short>::Release(&v23);
  ConnectedStorage::TaskMem<unsigned short>::Release(&v22);
  StringRawBuffer = WindowsGetStringRawBuffer(*v27, 0);
  if ( v16(v15, v11, v14, L"GET", StringRawBuffer, &dword_1800983B4, 0, 0, &v22, &v23) >= 0 )
    std::wstring::operator=(v32, v22);
  ConnectedStorage::TaskMem<unsigned short>::Release(&v23);
  ConnectedStorage::TaskMem<unsigned short>::Release(&v22);
  ConnectedStorage::ScopedCallContext::~ScopedCallContext((ConnectedStorage::ScopedCallContext *)&ppOldObject);
LABEL_11:
  v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
  (*(void (__fastcall **)(__int64, __int64))(v19 + 232))(v20, v18);
  std::wstring::_Tidy_deallocate(v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
}

```

## disassembly

```asm
0x18002ca10  push    rbx
0x18002ca12  push    rsi
0x18002ca13  push    rdi
0x18002ca14  push    r14
0x18002ca16  sub     rsp, 148h
0x18002ca1d  mov     rax, cs:__security_cookie
0x18002ca24  xor     rax, rsp
0x18002ca27  mov     [rsp+168h+var_38], rax
0x18002ca2f  mov     rbx, rcx
0x18002ca32  mov     [rsp+168h+var_D8], rdx
0x18002ca3a  mov     [rsp+168h+var_108], rcx
0x18002ca3f  mov     [rsp+168h+var_E8], r8
0x18002ca47  mov     [rsp+168h+var_F0], r9
0x18002ca4c  mov     [rsp+168h+var_F8], 0
0x18002ca55  lea     rcx, [rsp+168h+var_F8]
0x18002ca5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ca5f  lea     rax, [rsp+168h+var_F8]
0x18002ca64  mov     [rsp+168h+ppv], rax; ppv
0x18002ca69  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x18002ca70  xor     edx, edx; pUnkOuter
0x18002ca72  lea     r8d, [rdx+4]; dwClsContext
0x18002ca76  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x18002ca7d  call    cs:__imp_CoCreateInstance
0x18002ca83  test    eax, eax
0x18002ca85  jns     short loc_18002CA96
0x18002ca87  lea     rdx, aCocreateinstan_0; "CoCreateInstance( __uuidof(XblAuthManag"...
0x18002ca8e  mov     ecx, eax; this
0x18002ca90  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002ca96  lea     rcx, [rsp+168h+var_98]
0x18002ca9e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002caa3  nop
0x18002caa4  mov     r9, [rsp+168h+var_F0]
0x18002caa9  mov     r8, [rsp+168h+var_E8]
0x18002cab1  lea     rdx, [rsp+168h+lpCriticalSection]
0x18002cab9  mov     rcx, rbx
0x18002cabc  call    ?GetAuthHeaderForCachedUser@UserManager@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVSimpleHStringWrapper@2@0@Z; ConnectedStorage::UserManager::GetAuthHeaderForCachedUser(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x18002cac1  mov     rdx, rax
0x18002cac4  lea     rcx, [rsp+168h+var_98]
0x18002cacc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002cad1  lea     rcx, [rsp+168h+lpCriticalSection]
0x18002cad9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cade  nop
0x18002cadf  jmp     short loc_18002CAED
0x18002cae1  mov     rbx, [rsp+168h+var_108]
0x18002cae6  cmp     dword ptr [rsp+168h+var_100], 0
0x18002caeb  jl      short loc_18002CB3D
0x18002caed  cmp     [rsp+168h+var_88], 0
0x18002caf6  jbe     short loc_18002CB3D
0x18002caf8  lea     rcx, [rsp+168h+lpCriticalSection]
0x18002cb00  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002cb05  nop
0x18002cb06  lea     r9, [rsp+168h+lpCriticalSection]
0x18002cb0e  mov     r8, [rsp+168h+var_F0]
0x18002cb13  mov     rdx, [rsp+168h+var_E8]
0x18002cb1b  mov     rcx, rbx
0x18002cb1e  call    ?UpdateAuthHeaderCache@UserManager@ConnectedStorage@@AEBAXAEBVSimpleHStringWrapper@2@0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::UserManager::UpdateAuthHeaderCache(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,std::wstring &)
0x18002cb23  nop
0x18002cb24  lea     rcx, [rsp+168h+lpCriticalSection]
0x18002cb2c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cb31  jmp     loc_18002CCB0
0x18002cb36  jmp     short $+2
0x18002cb38  mov     rbx, [rsp+168h+var_108]
0x18002cb3d  lea     rdx, [rbx+0A8h]; struct ConnectedStorage::Mutex *
0x18002cb44  lea     rcx, [rsp+168h+lpCriticalSection]; this
0x18002cb4c  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18002cb51  nop
0x18002cb52  lea     rcx, [rbx+0D8h]
0x18002cb59  lea     rdx, [rsp+168h+var_C8]
0x18002cb61  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002cb66  mov     r8, [rax]
0x18002cb69  lea     rdx, [rsp+168h+var_C0]
0x18002cb71  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18002cb76  mov     rcx, [rsp+168h+var_E8]
0x18002cb7e  mov     [rsp+168h+var_E8], rcx
0x18002cb86  mov     rcx, [rsp+168h+var_F0]
0x18002cb8b  mov     [rsp+168h+var_E0], rcx
0x18002cb93  lea     r9, [rsp+168h+var_E8]
0x18002cb9b  mov     rdx, [rax]
0x18002cb9e  lea     rcx, [rsp+168h+var_F0]
0x18002cba3  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ConnectedStorage__UserManager__UserInfo_______lambda_a717a87f1fe21e15a1e5700b403a2f5e___
0x18002cba8  mov     rax, [rsp+168h+var_F0]
0x18002cbad  mov     r14, [rax]
0x18002cbb0  mov     rcx, [rsp+168h+lpCriticalSection]; lpCriticalSection
0x18002cbb8  call    cs:__imp_LeaveCriticalSection
0x18002cbbe  lea     rcx, [rsp+168h+ppOldObject]; ppOldObject
0x18002cbc6  call    ??0ScopedCallContext@ConnectedStorage@@QEAA@PEAUIUnknown@@@Z; ConnectedStorage::ScopedCallContext::ScopedCallContext(IUnknown *)
0x18002cbcb  nop
0x18002cbcc  mov     [rsp+168h+var_108], 0
0x18002cbd5  mov     [rsp+168h+var_100], 0
0x18002cbde  call    ?IsRunningOnConsole@ConnectedStorage@@YA_NXZ; ConnectedStorage::IsRunningOnConsole(void)
0x18002cbe3  lea     rcx, a49312658; "49312658"
0x18002cbea  neg     al
0x18002cbec  sbb     rsi, rsi
0x18002cbef  and     rsi, rcx
0x18002cbf2  mov     rdi, [rsp+168h+var_F8]
0x18002cbf7  mov     rax, [rdi]
0x18002cbfa  mov     rbx, [rax+1D0h]
0x18002cc01  lea     rcx, [rsp+168h+var_100]
0x18002cc06  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002cc0b  lea     rcx, [rsp+168h+var_108]
0x18002cc10  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002cc15  xor     edx, edx; length
0x18002cc17  mov     rcx, [rsp+168h+var_D8]
0x18002cc1f  mov     rcx, [rcx]; string
0x18002cc22  call    cs:__imp_WindowsGetStringRawBuffer
0x18002cc28  lea     rcx, [rsp+168h+var_100]
0x18002cc2d  mov     [rsp+168h+var_120], rcx
0x18002cc32  lea     rcx, [rsp+168h+var_108]
0x18002cc37  mov     [rsp+168h+var_128], rcx
0x18002cc3c  mov     [rsp+168h+var_130], 0
0x18002cc44  mov     [rsp+168h+var_138], 0
0x18002cc4d  lea     rcx, dword_1800983B4
0x18002cc54  mov     [rsp+168h+var_140], rcx
0x18002cc59  mov     [rsp+168h+ppv], rax
0x18002cc5e  lea     r9, aGet; "GET"
0x18002cc65  mov     r8, rsi
0x18002cc68  mov     rdx, r14
0x18002cc6b  mov     rcx, rdi
0x18002cc6e  mov     rax, rbx
0x18002cc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc76  test    eax, eax
0x18002cc78  js      short loc_18002CC8D
0x18002cc7a  mov     rdx, [rsp+168h+var_108]
0x18002cc7f  lea     rcx, [rsp+168h+var_98]
0x18002cc87  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18002cc8c  nop
0x18002cc8d  lea     rcx, [rsp+168h+var_100]
0x18002cc92  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002cc97  nop
0x18002cc98  lea     rcx, [rsp+168h+var_108]
0x18002cc9d  call    ?Release@?$TaskMem@G@ConnectedStorage@@QEAAXXZ; ConnectedStorage::TaskMem<ushort>::Release(void)
0x18002cca2  nop
0x18002cca3  lea     rcx, [rsp+168h+ppOldObject]; this
0x18002ccab  call    ??1ScopedCallContext@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ScopedCallContext::~ScopedCallContext(void)
0x18002ccb0  mov     r9, [rsp+168h+var_F8]
0x18002ccb5  mov     r8, [r9]
0x18002ccb8  lea     rcx, [rsp+168h+var_98]
0x18002ccc0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ccc5  mov     rdx, rax
0x18002ccc8  mov     rcx, r9
0x18002cccb  mov     rax, [r8+0E8h]
0x18002ccd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccd7  nop
0x18002ccd8  lea     rcx, [rsp+168h+var_98]
0x18002cce0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cce5  nop
0x18002cce6  lea     rcx, [rsp+168h+var_F8]
0x18002cceb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ccf0  mov     rcx, [rsp+168h+var_38]
0x18002ccf8  xor     rcx, rsp; StackCookie
0x18002ccfb  call    __security_check_cookie
0x18002cd00  add     rsp, 148h
0x18002cd07  pop     r14
0x18002cd09  pop     rdi
0x18002cd0a  pop     rsi
0x18002cd0b  pop     rbx
0x18002cd0c  retn
```
