# ConnectedStorage::NtmWebService::DeleteContainer(ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status)>)

- ea: `0x180041a50`
- end: `0x180041e30`
- name: `?DeleteContainer@NtmWebService@ConnectedStorage@@UEBA?AV?$shared_ptr@VWebServiceCancelCallback@ConnectedStorage@@@std@@VContextDesc@2@AEBVSimpleHStringWrapper@2@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@4@@Z`
- size: `992`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x180011c68`
- `0x1800125ec`
- `0x1800136a8`
- `0x1800190f0`
- `0x18001c090`
- `0x18001e3a0`
- `0x18002a1dc`
- `0x18003c420`
- `0x18003d03c`
- `0x18003db84`
- `0x18003e078`
- `0x18003ee9c`
- `0x18003ef9c`
- `0x180041a50`
- `0x180043580`
- `0x180043824`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041b37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041dc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041b37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041dc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041df3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041df3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041d72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041d81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041d5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041d72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041d81`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180041b42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180041b42`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
_QWORD *__fastcall ConnectedStorage::NtmWebService::DeleteContainer(
        __int64 a1,
        _QWORD *a2,
        char *a3,
        HSTRING *a4,
        __int64 a5)
{
  HSTRING *v6; // r14
  _QWORD *v7; // rbx
  __int64 v9; // rdi
  struct ConnectedStorage::Mutex *v10; // r12
  char *v11; // r8
  __int64 v12; // r8
  ULONGLONG TickCount64; // rax
  __int64 *v14; // r12
  __int64 v15; // r15
  __int64 v16; // rax
  __int64 v17; // r15
  unsigned int v18; // r13d
  HSTRING *v19; // rax
  __int64 v20; // rax
  char *v21; // r8
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v23; // rbx
  ConnectedStorage *v24; // rax
  __int64 v25; // r8
  int v27; // [rsp+28h] [rbp-260h]
  unsigned int v28; // [rsp+30h] [rbp-258h]
  unsigned int v29[2]; // [rsp+50h] [rbp-238h] BYREF
  void (__fastcall *v30)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, int, int); // [rsp+58h] [rbp-230h] BYREF
  __int64 v31; // [rsp+60h] [rbp-228h] BYREF
  HSTRING string; // [rsp+68h] [rbp-220h] BYREF
  HSTRING v33; // [rsp+70h] [rbp-218h] BYREF
  HSTRING *v34; // [rsp+78h] [rbp-210h]
  __int64 v35; // [rsp+80h] [rbp-208h]
  _QWORD *v36; // [rsp+88h] [rbp-200h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp-1F8h] BYREF
  std::_Ref_count_base *v38; // [rsp+98h] [rbp-1F0h]
  struct ConnectedStorage::Mutex *v39; // [rsp+A8h] [rbp-1E0h]
  HSTRING *v40; // [rsp+B0h] [rbp-1D8h]
  __int128 v41; // [rsp+B8h] [rbp-1D0h] BYREF
  LPCRITICAL_SECTION v42[2]; // [rsp+C8h] [rbp-1C0h] BYREF
  LPCRITICAL_SECTION v43[2]; // [rsp+D8h] [rbp-1B0h] BYREF
  unsigned __int16 v44[16]; // [rsp+E8h] [rbp-1A0h] BYREF
  HSTRING__ v45[10]; // [rsp+108h] [rbp-180h] BYREF
  _BYTE v46[56]; // [rsp+130h] [rbp-158h] BYREF
  __int64 v47; // [rsp+168h] [rbp-120h]
  _DWORD v48[16]; // [rsp+170h] [rbp-118h] BYREF
  _BYTE v49[144]; // [rsp+1B0h] [rbp-D8h] BYREF

  v6 = (HSTRING *)a3;
  v7 = a2;
  v40 = a4;
  v36 = a2;
  v34 = (HSTRING *)a3;
  v9 = a5;
  v35 = a5;
  v41 = 0;
  if ( *(_BYTE *)(a1 + 25) || *(_BYTE *)(a1 + 24) )
  {
    v10 = (struct ConnectedStorage::Mutex *)(a1 + 40);
    v39 = (struct ConnectedStorage::Mutex *)(a1 + 40);
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)v42,
      (struct _RTL_CRITICAL_SECTION *)(a1 + 40),
      a3);
    if ( !*(_QWORD *)(a1 + 88) )
    {
      ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)&lpCriticalSection, v10, v11);
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
        a5,
        1,
        v12);
      *v7 = 0;
      v7[1] = 0;
      EnterCriticalSection(lpCriticalSection);
LABEL_17:
      LeaveCriticalSection(v42[0]);
      goto LABEL_18;
    }
    TickCount64 = GetTickCount64();
    try
    {
      v30 = (void (__fastcall *)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, int, int))TickCount64;
      ConnectedStorage::MakeUrlForContainer(v44, v6, a4);
      ConnectedStorage::NtmWebService::MakeHeadersWithContext(a1, v45, v44, v6);
      Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(&v31);
      v14 = *(__int64 **)(a1 + 88);
      v15 = *v14;
      v16 = lambda_69617c1b0b98e85197265cdc98f2e7a2_::_lambda_69617c1b0b98e85197265cdc98f2e7a2__0(
              v49,
              a5,
              &v31,
              v6,
              a4,
              &v30);
      v47 = 0;
      v47 = std::_Global_new_std::_Func_impl_no_alloc__lambda_69617c1b0b98e85197265cdc98f2e7a2__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_69617c1b0b98e85197265cdc98f2e7a2___(v16);
      v30 = *(void (__fastcall **)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, int, int))(v15 + 8);
      lpCriticalSection = (LPCRITICAL_SECTION)v29;
      v17 = v31;
      *(_QWORD *)v29 = v31;
      Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(v29);
      v18 = (unsigned int)ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v33, (__int64)v45);
      v19 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, (__int64)v44);
      v28 = v18;
      LOWORD(v27) = 95;
      v30(v14, v43, v19, 320, 1, v27);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v33);
      v33 = 0;
      std::function<long (void)>::~function<long (void)>(v46);
      lambda_69617c1b0b98e85197265cdc98f2e7a2_::__lambda_69617c1b0b98e85197265cdc98f2e7a2_(v49);
      v20 = std::make_shared<ConnectedStorage::NtmCancelCallback,_GUID &>(&lpCriticalSection, v43);
      std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(&v41, v20);
      if ( v38 )
        std::_Ref_count_base::_Decref(v38);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      std::wstring::_Tidy_deallocate(v45);
      std::wstring::_Tidy_deallocate(v44);
    }
    catch ( ConnectedStorage::ComError v48 )
    {
      v29[0] = v48[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v48);
      if ( (v29[0] & 0x80000000) != 0 )
      {
LABEL_14:
        ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)v43, v39, v21);
        StringRawBuffer = WindowsGetStringRawBuffer(*v40, 0);
        v6 = v34;
        v23 = WindowsGetStringRawBuffer(v34[2], 0);
        v24 = (ConnectedStorage *)WindowsGetStringRawBuffer(v6[3], 0);
        ConnectedStorage::EventWriteWebDeleteContainer(v24, v23, StringRawBuffer, 0, v29[0], 0, v28);
        v9 = v35;
        std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
          v35,
          1,
          v25);
        EnterCriticalSection(v43[0]);
      }
      else
      {
        v6 = v34;
        v9 = v35;
      }
      v7 = v36;
    }
    catch ( std::bad_alloc )
    {
      v29[0] = -2147024882;
      goto LABEL_14;
    }
    catch ( ... )
    {
      v29[0] = -2147467259;
      goto LABEL_14;
    }
    *(_OWORD *)v7 = v41;
    goto LABEL_17;
  }
  std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
    a5,
    1,
    a3);
  *v7 = 0;
  v7[1] = 0;
LABEL_18:
  ConnectedStorage::ContextDesc::~ContextDesc(v6);
  std::function<long (void)>::~function<long (void)>(v9);
  return v7;
}

```

## disassembly

```asm
0x180041a50  push    rbx
0x180041a52  push    rdi
0x180041a53  push    r12
0x180041a55  push    r13
0x180041a57  push    r14
0x180041a59  push    r15
0x180041a5b  sub     rsp, 258h
0x180041a62  mov     rax, cs:__security_cookie
0x180041a69  xor     rax, rsp
0x180041a6c  mov     [rsp+288h+var_48], rax
0x180041a74  mov     r13, r9
0x180041a77  mov     r14, r8
0x180041a7a  mov     rbx, rdx
0x180041a7d  mov     r15, rcx
0x180041a80  mov     [rsp+288h+var_1D8], r9
0x180041a88  mov     [rsp+288h+var_200], rdx
0x180041a90  mov     [rsp+288h+var_210], r8
0x180041a95  mov     rdi, [rsp+288h+arg_20]
0x180041a9d  mov     [rsp+288h+var_208], rdi
0x180041aa5  xorps   xmm0, xmm0
0x180041aa8  movdqu  [rsp+288h+var_1D0], xmm0
0x180041ab1  cmp     byte ptr [rcx+19h], 0
0x180041ab5  jnz     short loc_180041ADE
0x180041ab7  cmp     byte ptr [rcx+18h], 0
0x180041abb  jnz     short loc_180041ADE
0x180041abd  mov     edx, 1
0x180041ac2  mov     rcx, rdi
0x180041ac5  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180041aca  mov     qword ptr [rbx], 0
0x180041ad1  mov     qword ptr [rbx+8], 0
0x180041ad9  jmp     loc_180041DFA
0x180041ade  lea     r12, [rcx+28h]
0x180041ae2  mov     [rsp+288h+var_1E0], r12
0x180041aea  mov     rdx, r12; struct ConnectedStorage::Mutex *
0x180041aed  lea     rcx, [rsp+288h+var_1C0]; this
0x180041af5  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180041afa  nop
0x180041afb  cmp     qword ptr [r15+58h], 0
0x180041b00  jnz     short loc_180041B42
0x180041b02  mov     rdx, r12; struct ConnectedStorage::Mutex *
0x180041b05  lea     rcx, [rsp+288h+lpCriticalSection]; this
0x180041b0d  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180041b12  nop
0x180041b13  mov     edx, 1
0x180041b18  mov     rcx, rdi
0x180041b1b  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180041b20  mov     qword ptr [rbx], 0
0x180041b27  mov     qword ptr [rbx+8], 0
0x180041b2f  mov     rcx, [rsp+288h+lpCriticalSection]; lpCriticalSection
0x180041b37  call    cs:__imp_EnterCriticalSection
0x180041b3d  jmp     loc_180041DEB
0x180041b42  call    cs:__imp_GetTickCount64
0x180041b48  mov     [rsp+288h+var_230], rax
0x180041b4d  mov     r8, r13
0x180041b50  mov     rdx, r14
0x180041b53  lea     rcx, [rsp+288h+var_1A0]
0x180041b5b  call    ?MakeUrlForContainer@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@AEBVSimpleHStringWrapper@1@@Z; ConnectedStorage::MakeUrlForContainer(ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180041b60  nop
0x180041b61  mov     r9, r14
0x180041b64  lea     r8, [rsp+288h+var_1A0]
0x180041b6c  lea     rdx, [rsp+288h+var_180]
0x180041b74  mov     rcx, r15
0x180041b77  call    ?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x180041b7c  nop
0x180041b7d  lea     rcx, [rsp+288h+var_228]
0x180041b82  call    ??$Make@VStringStream@ConnectedStorage@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VStringStream@ConnectedStorage@@@12@XZ; Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(void)
0x180041b87  nop
0x180041b88  mov     r12, [r15+58h]
0x180041b8c  mov     r15, [r12]
0x180041b90  lea     rax, [rsp+288h+var_230]
0x180041b95  mov     qword ptr [rsp+288h+var_260], rax
0x180041b9a  mov     qword ptr [rsp+288h+var_268], r13
0x180041b9f  mov     r9, r14
0x180041ba2  lea     r8, [rsp+288h+var_228]
0x180041ba7  mov     rdx, rdi
0x180041baa  lea     rcx, [rsp+288h+var_D8]
0x180041bb2  call    _lambda_69617c1b0b98e85197265cdc98f2e7a2____lambda_69617c1b0b98e85197265cdc98f2e7a2__0
0x180041bb7  nop
0x180041bb8  mov     [rsp+288h+var_120], 0
0x180041bc4  mov     rcx, rax
0x180041bc7  call    std___Global_new_std___Func_impl_no_alloc__lambda_69617c1b0b98e85197265cdc98f2e7a2__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_69617c1b0b98e85197265cdc98f2e7a2___
0x180041bcc  mov     [rsp+288h+var_120], rax
0x180041bd4  mov     rax, [r15+8]
0x180041bd8  mov     [rsp+288h+var_230], rax
0x180041bdd  lea     rcx, [rsp+288h+var_238]
0x180041be2  mov     [rsp+288h+lpCriticalSection], rcx
0x180041bea  mov     r15, [rsp+288h+var_228]
0x180041bef  mov     qword ptr [rsp+288h+var_238], r15
0x180041bf4  lea     rcx, [rsp+288h+var_238]
0x180041bf9  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x180041bfe  nop
0x180041bff  lea     rdx, [rsp+288h+var_180]
0x180041c07  lea     rcx, [rsp+288h+var_218]; string
0x180041c0c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180041c11  mov     r13, rax
0x180041c14  lea     rdx, [rsp+288h+var_1A0]
0x180041c1c  lea     rcx, [rsp+288h+string]; string
0x180041c21  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180041c26  nop
0x180041c27  lea     rcx, [rsp+288h+var_158]
0x180041c2f  mov     [rsp+288h+var_248], rcx
0x180041c34  lea     rcx, [rsp+288h+var_238]
0x180041c39  mov     [rsp+288h+var_250], rcx
0x180041c3e  mov     [rsp+288h+var_258], r13
0x180041c43  mov     word ptr [rsp+288h+var_260], 5Fh ; '_'
0x180041c4a  mov     [rsp+288h+var_268], 1
0x180041c52  mov     r9d, 140h
0x180041c58  mov     r8, rax
0x180041c5b  lea     rdx, [rsp+288h+var_1B0]
0x180041c63  mov     rcx, r12
0x180041c66  mov     rax, [rsp+288h+var_230]
0x180041c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c70  nop
0x180041c71  mov     rcx, [rsp+288h+string]; string
0x180041c76  call    cs:__imp_WindowsDeleteString
0x180041c7c  mov     [rsp+288h+string], 0
0x180041c85  mov     rcx, [rsp+288h+var_218]; string
0x180041c8a  call    cs:__imp_WindowsDeleteString
0x180041c90  mov     [rsp+288h+var_218], 0
0x180041c99  lea     rcx, [rsp+288h+var_158]
0x180041ca1  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180041ca6  nop
0x180041ca7  lea     rcx, [rsp+288h+var_D8]
0x180041caf  call    _lambda_69617c1b0b98e85197265cdc98f2e7a2_____lambda_69617c1b0b98e85197265cdc98f2e7a2_
0x180041cb4  lea     rdx, [rsp+288h+var_1B0]
0x180041cbc  lea     rcx, [rsp+288h+lpCriticalSection]
0x180041cc4  call    ??$make_shared@VNtmCancelCallback@ConnectedStorage@@AEAU_GUID@@@std@@YA?AV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@0@AEAU_GUID@@@Z; std::make_shared<ConnectedStorage::NtmCancelCallback,_GUID &>(_GUID &)
0x180041cc9  mov     rdx, rax
0x180041ccc  lea     rcx, [rsp+288h+var_1D0]
0x180041cd4  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x180041cd9  mov     rcx, [rsp+288h+var_1F0]; this
0x180041ce1  test    rcx, rcx
0x180041ce4  jz      short loc_180041CEC
0x180041ce6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041ceb  nop
0x180041cec  test    r15, r15
0x180041cef  jz      short loc_180041D01
0x180041cf1  mov     rax, [r15]
0x180041cf4  mov     rcx, r15
0x180041cf7  mov     rax, [rax+10h]
0x180041cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d00  nop
0x180041d01  lea     rcx, [rsp+288h+var_180]
0x180041d09  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041d0e  nop
0x180041d0f  lea     rcx, [rsp+288h+var_1A0]
0x180041d17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041d1c  nop
0x180041d1d  jmp     loc_180041DD4
0x180041d22  cmp     [rsp+288h+var_238], 0
0x180041d27  jl      short loc_180041D3B
0x180041d29  mov     r14, [rsp+288h+var_210]
0x180041d2e  mov     rdi, [rsp+288h+var_208]
0x180041d36  jmp     loc_180041DCC
0x180041d3b  mov     rdx, [rsp+288h+var_1E0]; struct ConnectedStorage::Mutex *
0x180041d43  lea     rcx, [rsp+288h+var_1B0]; this
0x180041d4b  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180041d50  nop
0x180041d51  xor     edx, edx; length
0x180041d53  mov     rcx, [rsp+288h+var_1D8]
0x180041d5b  mov     rcx, [rcx]; string
0x180041d5e  call    cs:__imp_WindowsGetStringRawBuffer
0x180041d64  mov     rdi, rax
0x180041d67  xor     edx, edx; length
0x180041d69  mov     r14, [rsp+288h+var_210]
0x180041d6e  mov     rcx, [r14+10h]; string
0x180041d72  call    cs:__imp_WindowsGetStringRawBuffer
0x180041d78  mov     rbx, rax
0x180041d7b  xor     edx, edx; length
0x180041d7d  mov     rcx, [r14+18h]; string
0x180041d81  call    cs:__imp_WindowsGetStringRawBuffer
0x180041d87  mov     [rsp+288h+var_260], 0; unsigned int
0x180041d8f  mov     ecx, [rsp+288h+var_238]
0x180041d93  mov     [rsp+288h+var_268], ecx; unsigned int
0x180041d97  xor     r9d, r9d; unsigned __int16 *
0x180041d9a  mov     r8, rdi; unsigned __int16 *
0x180041d9d  mov     rdx, rbx; unsigned __int16 *
0x180041da0  mov     rcx, rax; this
0x180041da3  call    ?EventWriteWebDeleteContainer@ConnectedStorage@@YAXQEBG00III@Z; ConnectedStorage::EventWriteWebDeleteContainer(ushort const * const,ushort const * const,ushort const * const,uint,uint,uint)
0x180041da8  mov     edx, 1
0x180041dad  mov     rdi, [rsp+288h+var_208]
0x180041db5  mov     rcx, rdi
0x180041db8  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180041dbd  nop
0x180041dbe  mov     rcx, [rsp+288h+var_1B0]; lpCriticalSection
0x180041dc6  call    cs:__imp_EnterCriticalSection
0x180041dcc  mov     rbx, [rsp+288h+var_200]
0x180041dd4  mov     rax, qword ptr [rsp+288h+var_1D0]
0x180041ddc  mov     [rbx], rax
0x180041ddf  mov     rax, qword ptr [rsp+288h+var_1D0+8]
0x180041de7  mov     [rbx+8], rax
0x180041deb  mov     rcx, [rsp+288h+var_1C0]; lpCriticalSection
0x180041df3  call    cs:__imp_LeaveCriticalSection
0x180041df9  nop
0x180041dfa  mov     rcx, r14; this
0x180041dfd  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180041e02  nop
0x180041e03  mov     rcx, rdi
0x180041e06  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180041e0b  mov     rax, rbx
0x180041e0e  mov     rcx, [rsp+288h+var_48]
0x180041e16  xor     rcx, rsp; StackCookie
0x180041e19  call    __security_check_cookie
0x180041e1e  add     rsp, 258h
0x180041e25  pop     r15
0x180041e27  pop     r14
0x180041e29  pop     r13
0x180041e2b  pop     r12
0x180041e2d  pop     rdi
0x180041e2e  pop     rbx
0x180041e2f  retn
```
