# ConnectedStorage::NtmWebService::DownloadContainerImpl(ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)>,ulong,std::shared_ptr<ConnectedStorage::NtmCancelCallback>)

- ea: `0x180042c1c`
- end: `0x180043067`
- name: `?DownloadContainerImpl@NtmWebService@ConnectedStorage@@AEBAXVContextDesc@2@AEBVSimpleHStringWrapper@2@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@1@Z@std@@KV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@6@@Z`
- size: `1099`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042590`
- `0x180042800`

## callees

- `0x180003c70`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x180011c0c`
- `0x180011c68`
- `0x1800125ec`
- `0x1800190f0`
- `0x180019128`
- `0x18001c090`
- `0x18001e678`
- `0x18002a2a0`
- `0x18003c420`
- `0x18003cf2c`
- `0x18003df24`
- `0x18003ee9c`
- `0x18003ef24`
- `0x180042c1c`
- `0x180043580`
- `0x180043824`
- `0x1800449b0`
- `0x180048720`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042d08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043008`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042d08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043008`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004301e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004301e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042cf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042e8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042fe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042cf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042e8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042fe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042f5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042f7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042f5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042f7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180042d13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180042d13`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
void __fastcall ConnectedStorage::NtmWebService::DownloadContainerImpl(
        __int64 a1,
        HSTRING *a2,
        char *a3,
        __int64 a4,
        char a5,
        ConnectedStorage::NtmCancelCallback **a6)
{
  __int64 v6; // rdi
  HSTRING *v8; // r14
  ConnectedStorage::NtmCancelCallback **v10; // r15
  struct ConnectedStorage::Mutex *v11; // r13
  char *v12; // r8
  HSTRING *v13; // rbx
  HSTRING *v14; // rax
  ULONGLONG TickCount64; // rax
  __int64 *v16; // r13
  __int64 v17; // rbx
  __int64 v18; // rax
  HSTRING v19; // rbx
  HSTRING *v20; // r12
  HSTRING *v21; // rax
  char *v22; // r8
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v24; // rbx
  ConnectedStorage *v25; // rax
  std::_Ref_count_base *v26; // rcx
  int v27; // [rsp+28h] [rbp-270h]
  HSTRING string; // [rsp+50h] [rbp-248h] BYREF
  HSTRING v29; // [rsp+58h] [rbp-240h] BYREF
  void (__fastcall *v30)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, _DWORD, int, HSTRING *); // [rsp+60h] [rbp-238h] BYREF
  HSTRING v31; // [rsp+68h] [rbp-230h] BYREF
  HSTRING v32; // [rsp+70h] [rbp-228h] BYREF
  HSTRING *v33; // [rsp+78h] [rbp-220h]
  __int64 v34; // [rsp+80h] [rbp-218h]
  ConnectedStorage::NtmCancelCallback **v35; // [rsp+88h] [rbp-210h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp-208h] BYREF
  std::_Ref_count_base *v37; // [rsp+98h] [rbp-200h]
  struct ConnectedStorage::Mutex *v38; // [rsp+A0h] [rbp-1F8h]
  HSTRING *v39; // [rsp+A8h] [rbp-1F0h]
  struct _GUID v40; // [rsp+B0h] [rbp-1E8h] BYREF
  LPCRITICAL_SECTION v41[2]; // [rsp+C0h] [rbp-1D8h] BYREF
  LPCRITICAL_SECTION v42[2]; // [rsp+D0h] [rbp-1C8h] BYREF
  _BYTE v43[32]; // [rsp+E0h] [rbp-1B8h] BYREF
  _BYTE v44[32]; // [rsp+100h] [rbp-198h] BYREF
  char v45[56]; // [rsp+120h] [rbp-178h] BYREF
  __int64 v46; // [rsp+158h] [rbp-140h]
  _DWORD v47[16]; // [rsp+160h] [rbp-138h] BYREF
  _BYTE v48[176]; // [rsp+1A0h] [rbp-F8h] BYREF

  v6 = a4;
  v8 = a2;
  v39 = (HSTRING *)a3;
  v33 = a2;
  v34 = a4;
  v10 = a6;
  v35 = a6;
  v11 = (struct ConnectedStorage::Mutex *)(a1 + 40);
  v38 = (struct ConnectedStorage::Mutex *)(a1 + 40);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)v41,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 40),
    a3);
  if ( *(_QWORD *)(a1 + 88) )
  {
    TickCount64 = GetTickCount64();
    try
    {
      v30 = (void (__fastcall *)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, _DWORD, int, HSTRING *))TickCount64;
      ConnectedStorage::MakeUrlForContainer(v43, v8, a3);
      ConnectedStorage::NtmWebService::MakeHeadersWithContext(a1, v44, v43, v8);
      Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(&v31);
      ConnectedStorage::NtmWebService::weak_from_this(a1, &lpCriticalSection);
      v16 = *(__int64 **)(a1 + 88);
      v17 = *v16;
      v18 = lambda_2effa635dd03e44d2c8bbe6d415323e3_::_lambda_2effa635dd03e44d2c8bbe6d415323e3__1(
              v48,
              v6,
              &v31,
              v8,
              a3,
              &a5,
              v10,
              &v30,
              &lpCriticalSection);
      v46 = 0;
      v46 = std::_Global_new_std::_Func_impl_no_alloc__lambda_2effa635dd03e44d2c8bbe6d415323e3__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_2effa635dd03e44d2c8bbe6d415323e3___(v18);
      v30 = *(void (__fastcall **)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, _DWORD, int, HSTRING *))(v17 + 8);
      *(_QWORD *)&v40.Data1 = &string;
      v19 = v31;
      string = v31;
      Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&string);
      v20 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v29, (__int64)v44);
      v21 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v32, (__int64)v43);
      LOWORD(v27) = 30;
      v30(v16, v42, v21, 80, 0, v27, v20);
      WindowsDeleteString(v32);
      v32 = 0;
      WindowsDeleteString(v29);
      v29 = 0;
      std::function<long (void)>::~function<long (void)>(v45);
      lambda_2effa635dd03e44d2c8bbe6d415323e3_::__lambda_2effa635dd03e44d2c8bbe6d415323e3_(v48);
      v40 = *(struct _GUID *)v42;
      ConnectedStorage::NtmCancelCallback::ReplaceCompletedTransfer(*v10, &v40);
      if ( v37 )
        std::_Ref_count_base::_Decwref(v37);
      if ( v19 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
      std::wstring::_Tidy_deallocate(v44);
      std::wstring::_Tidy_deallocate(v43);
    }
    catch ( ConnectedStorage::ComError v47 )
    {
      LODWORD(string) = v47[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v47);
      if ( (int)string < 0 )
      {
LABEL_11:
        ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)v42, v38, v22);
        StringRawBuffer = WindowsGetStringRawBuffer(*v39, 0);
        v8 = v33;
        v24 = WindowsGetStringRawBuffer(v33[2], 0);
        v25 = (ConnectedStorage *)WindowsGetStringRawBuffer(v8[3], 0);
        ConnectedStorage::EventWriteWebDownloadContainer(
          v25,
          v24,
          StringRawBuffer,
          0,
          0,
          (unsigned int)string,
          0,
          (unsigned int)&string);
        v29 = 0;
        string = 0;
        v6 = v34;
        std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
          v34,
          1,
          &string,
          &v29);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v29);
        EnterCriticalSection(v42[0]);
      }
      else
      {
        v8 = v33;
        v6 = v34;
      }
      v10 = v35;
    }
    catch ( std::bad_alloc )
    {
      LODWORD(string) = -2147024882;
      goto LABEL_11;
    }
    catch ( ... )
    {
      LODWORD(string) = -2147467259;
      goto LABEL_11;
    }
  }
  else
  {
    ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)&lpCriticalSection, v11, v12);
    v13 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v29, &dword_1800983B4);
    v14 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, &dword_1800983B4);
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      v6,
      1,
      v14,
      v13);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v29);
    EnterCriticalSection(lpCriticalSection);
  }
  LeaveCriticalSection(v41[0]);
  ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v8);
  std::function<long (void)>::~function<long (void)>(v6);
  v26 = v10[1];
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
}

```

## disassembly

```asm
0x180042c1c  push    rbx
0x180042c1e  push    rdi
0x180042c1f  push    r12
0x180042c21  push    r13
0x180042c23  push    r14
0x180042c25  push    r15
0x180042c27  sub     rsp, 268h
0x180042c2e  mov     rax, cs:__security_cookie
0x180042c35  xor     rax, rsp
0x180042c38  mov     [rsp+298h+var_48], rax
0x180042c40  mov     rdi, r9
0x180042c43  mov     r12, r8
0x180042c46  mov     r14, rdx
0x180042c49  mov     rbx, rcx
0x180042c4c  mov     [rsp+298h+var_1F0], r8
0x180042c54  mov     [rsp+298h+var_220], rdx
0x180042c59  mov     [rsp+298h+var_218], r9
0x180042c61  mov     r15, [rsp+298h+arg_28]
0x180042c69  mov     [rsp+298h+var_210], r15
0x180042c71  lea     r13, [rcx+28h]
0x180042c75  mov     [rsp+298h+var_1F8], r13
0x180042c7d  mov     rdx, r13; struct ConnectedStorage::Mutex *
0x180042c80  lea     rcx, [rsp+298h+var_1D8]; this
0x180042c88  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180042c8d  nop
0x180042c8e  cmp     qword ptr [rbx+58h], 0
0x180042c93  jnz     short loc_180042D13
0x180042c95  mov     rdx, r13; struct ConnectedStorage::Mutex *
0x180042c98  lea     rcx, [rsp+298h+lpCriticalSection]; this
0x180042ca0  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180042ca5  nop
0x180042ca6  lea     rdx, dword_1800983B4; sourceString
0x180042cad  lea     rcx, [rsp+298h+var_240]; string
0x180042cb2  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180042cb7  mov     rbx, rax
0x180042cba  lea     rdx, dword_1800983B4; sourceString
0x180042cc1  lea     rcx, [rsp+298h+string]; string
0x180042cc6  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180042ccb  nop
0x180042ccc  mov     r9, rbx
0x180042ccf  mov     r8, rax
0x180042cd2  mov     edx, 1
0x180042cd7  mov     rcx, rdi
0x180042cda  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@AEBV43@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@1@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180042cdf  nop
0x180042ce0  mov     rcx, [rsp+298h+string]; string
0x180042ce5  call    cs:__imp_WindowsDeleteString
0x180042ceb  mov     [rsp+298h+string], 0
0x180042cf4  mov     rcx, [rsp+298h+var_240]; string
0x180042cf9  call    cs:__imp_WindowsDeleteString
0x180042cff  nop
0x180042d00  mov     rcx, [rsp+298h+lpCriticalSection]; lpCriticalSection
0x180042d08  call    cs:__imp_EnterCriticalSection
0x180042d0e  jmp     loc_180043016
0x180042d13  call    cs:__imp_GetTickCount64
0x180042d19  mov     [rsp+298h+var_238], rax
0x180042d1e  mov     r8, r12
0x180042d21  mov     rdx, r14
0x180042d24  lea     rcx, [rsp+298h+var_1B8]
0x180042d2c  call    ?MakeUrlForContainer@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@AEBVSimpleHStringWrapper@1@@Z; ConnectedStorage::MakeUrlForContainer(ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180042d31  nop
0x180042d32  mov     r9, r14
0x180042d35  lea     r8, [rsp+298h+var_1B8]
0x180042d3d  lea     rdx, [rsp+298h+var_198]
0x180042d45  mov     rcx, rbx
0x180042d48  call    ?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x180042d4d  nop
0x180042d4e  lea     rcx, [rsp+298h+var_230]
0x180042d53  call    ??$Make@VStringStream@ConnectedStorage@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VStringStream@ConnectedStorage@@@12@XZ; Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(void)
0x180042d58  nop
0x180042d59  lea     rdx, [rsp+298h+lpCriticalSection]
0x180042d61  mov     rcx, rbx
0x180042d64  call    ?weak_from_this@NtmWebService@ConnectedStorage@@AEBA?AV?$weak_ptr@$$CBVNtmWebService@ConnectedStorage@@@std@@XZ; ConnectedStorage::NtmWebService::weak_from_this(void)
0x180042d69  nop
0x180042d6a  mov     r13, [rbx+58h]
0x180042d6e  mov     rbx, [r13+0]
0x180042d72  lea     rax, [rsp+298h+lpCriticalSection]
0x180042d7a  mov     [rsp+298h+var_258], rax
0x180042d7f  lea     rax, [rsp+298h+var_238]
0x180042d84  mov     [rsp+298h+var_260], rax
0x180042d89  mov     qword ptr [rsp+298h+var_268], r15
0x180042d8e  lea     rax, [rsp+298h+arg_20]
0x180042d96  mov     qword ptr [rsp+298h+var_270], rax
0x180042d9b  mov     qword ptr [rsp+298h+var_278], r12
0x180042da0  mov     r9, r14
0x180042da3  lea     r8, [rsp+298h+var_230]
0x180042da8  mov     rdx, rdi
0x180042dab  lea     rcx, [rsp+298h+var_F8]
0x180042db3  call    _lambda_2effa635dd03e44d2c8bbe6d415323e3____lambda_2effa635dd03e44d2c8bbe6d415323e3__1
0x180042db8  nop
0x180042db9  mov     [rsp+298h+var_140], 0
0x180042dc5  mov     rcx, rax
0x180042dc8  call    std___Global_new_std___Func_impl_no_alloc__lambda_2effa635dd03e44d2c8bbe6d415323e3__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_2effa635dd03e44d2c8bbe6d415323e3___
0x180042dcd  mov     [rsp+298h+var_140], rax
0x180042dd5  mov     rax, [rbx+8]
0x180042dd9  mov     [rsp+298h+var_238], rax
0x180042dde  lea     rcx, [rsp+298h+string]
0x180042de3  mov     qword ptr [rsp+298h+var_1E8.Data1], rcx
0x180042deb  mov     rbx, [rsp+298h+var_230]
0x180042df0  mov     [rsp+298h+string], rbx
0x180042df5  lea     rcx, [rsp+298h+string]
0x180042dfa  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x180042dff  nop
0x180042e00  lea     rdx, [rsp+298h+var_198]
0x180042e08  lea     rcx, [rsp+298h+var_240]; string
0x180042e0d  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180042e12  mov     r12, rax
0x180042e15  lea     rdx, [rsp+298h+var_1B8]
0x180042e1d  lea     rcx, [rsp+298h+var_228]; string
0x180042e22  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180042e27  nop
0x180042e28  lea     rcx, [rsp+298h+var_178]
0x180042e30  mov     [rsp+298h+var_258], rcx
0x180042e35  lea     rcx, [rsp+298h+string]
0x180042e3a  mov     [rsp+298h+var_260], rcx
0x180042e3f  mov     qword ptr [rsp+298h+var_268], r12
0x180042e44  mov     word ptr [rsp+298h+var_270], 1Eh
0x180042e4b  mov     [rsp+298h+var_278], 0
0x180042e53  mov     r9d, 50h ; 'P'
0x180042e59  mov     r8, rax
0x180042e5c  lea     rdx, [rsp+298h+var_1C8]
0x180042e64  mov     rcx, r13
0x180042e67  mov     rax, [rsp+298h+var_238]
0x180042e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e71  nop
0x180042e72  mov     rcx, [rsp+298h+var_228]; string
0x180042e77  call    cs:__imp_WindowsDeleteString
0x180042e7d  mov     [rsp+298h+var_228], 0
0x180042e86  mov     rcx, [rsp+298h+var_240]; string
0x180042e8b  call    cs:__imp_WindowsDeleteString
0x180042e91  mov     [rsp+298h+var_240], 0
0x180042e9a  lea     rcx, [rsp+298h+var_178]
0x180042ea2  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180042ea7  nop
0x180042ea8  lea     rcx, [rsp+298h+var_F8]
0x180042eb0  call    _lambda_2effa635dd03e44d2c8bbe6d415323e3_____lambda_2effa635dd03e44d2c8bbe6d415323e3_
0x180042eb5  movaps  xmm0, xmmword ptr [rsp+298h+var_1C8]
0x180042ebd  movdqa  xmmword ptr [rsp+298h+var_1E8.Data1], xmm0
0x180042ec6  lea     rdx, [rsp+298h+var_1E8]; struct _GUID
0x180042ece  mov     rcx, [r15]; this
0x180042ed1  call    ?ReplaceCompletedTransfer@NtmCancelCallback@ConnectedStorage@@QEAAXU_GUID@@@Z; ConnectedStorage::NtmCancelCallback::ReplaceCompletedTransfer(_GUID)
0x180042ed6  nop
0x180042ed7  mov     rcx, [rsp+298h+var_200]; this
0x180042edf  test    rcx, rcx
0x180042ee2  jz      short loc_180042EEA
0x180042ee4  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180042ee9  nop
0x180042eea  test    rbx, rbx
0x180042eed  jz      short loc_180042EFF
0x180042eef  mov     rax, [rbx]
0x180042ef2  mov     rcx, rbx
0x180042ef5  mov     rax, [rax+10h]
0x180042ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042efe  nop
0x180042eff  lea     rcx, [rsp+298h+var_198]
0x180042f07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042f0c  nop
0x180042f0d  lea     rcx, [rsp+298h+var_1B8]
0x180042f15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042f1a  nop
0x180042f1b  jmp     loc_180043016
0x180042f20  cmp     dword ptr [rsp+298h+string], 0
0x180042f25  jl      short loc_180042F39
0x180042f27  mov     r14, [rsp+298h+var_220]
0x180042f2c  mov     rdi, [rsp+298h+var_218]
0x180042f34  jmp     loc_18004300E
0x180042f39  mov     rdx, [rsp+298h+var_1F8]; struct ConnectedStorage::Mutex *
0x180042f41  lea     rcx, [rsp+298h+var_1C8]; this
0x180042f49  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180042f4e  nop
0x180042f4f  xor     edx, edx; length
0x180042f51  mov     rcx, [rsp+298h+var_1F0]
0x180042f59  mov     rcx, [rcx]; string
0x180042f5c  call    cs:__imp_WindowsGetStringRawBuffer
0x180042f62  mov     rdi, rax
0x180042f65  xor     edx, edx; length
0x180042f67  mov     r14, [rsp+298h+var_220]
0x180042f6c  mov     rcx, [r14+10h]; string
0x180042f70  call    cs:__imp_WindowsGetStringRawBuffer
0x180042f76  mov     rbx, rax
0x180042f79  xor     edx, edx; length
0x180042f7b  mov     rcx, [r14+18h]; string
0x180042f7f  call    cs:__imp_WindowsGetStringRawBuffer
0x180042f85  mov     [rsp+298h+var_268], 0; unsigned int
0x180042f8d  mov     ecx, dword ptr [rsp+298h+string]
0x180042f91  mov     [rsp+298h+var_270], ecx; unsigned int
0x180042f95  mov     [rsp+298h+var_278], 0; unsigned int
0x180042f9d  xor     r9d, r9d; unsigned __int16 *
0x180042fa0  mov     r8, rdi; unsigned __int16 *
0x180042fa3  mov     rdx, rbx; unsigned __int16 *
0x180042fa6  mov     rcx, rax; this
0x180042fa9  call    ?EventWriteWebDownloadContainer@ConnectedStorage@@YAXQEBG00IIII@Z; ConnectedStorage::EventWriteWebDownloadContainer(ushort const * const,ushort const * const,ushort const * const,uint,uint,uint,uint)
0x180042fae  mov     [rsp+298h+var_240], 0
0x180042fb7  mov     [rsp+298h+string], 0
0x180042fc0  lea     r9, [rsp+298h+var_240]
0x180042fc5  lea     r8, [rsp+298h+string]
0x180042fca  mov     edx, 1
0x180042fcf  mov     rdi, [rsp+298h+var_218]
0x180042fd7  mov     rcx, rdi
0x180042fda  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@AEBV43@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@1@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180042fdf  nop
0x180042fe0  mov     rcx, [rsp+298h+string]; string
0x180042fe5  call    cs:__imp_WindowsDeleteString
0x180042feb  mov     [rsp+298h+string], 0
0x180042ff4  mov     rcx, [rsp+298h+var_240]; string
0x180042ff9  call    cs:__imp_WindowsDeleteString
0x180042fff  nop
0x180043000  mov     rcx, [rsp+298h+var_1C8]; lpCriticalSection
0x180043008  call    cs:__imp_EnterCriticalSection
0x18004300e  mov     r15, [rsp+298h+var_210]
0x180043016  mov     rcx, [rsp+298h+var_1D8]; lpCriticalSection
0x18004301e  call    cs:__imp_LeaveCriticalSection
0x180043024  nop
0x180043025  mov     rcx, r14; this
0x180043028  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x18004302d  nop
0x18004302e  mov     rcx, rdi
0x180043031  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180043036  nop
0x180043037  mov     rcx, [r15+8]; this
0x18004303b  test    rcx, rcx
0x18004303e  jz      short loc_180043045
0x180043040  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180043045  mov     rcx, [rsp+298h+var_48]
0x18004304d  xor     rcx, rsp; StackCookie
0x180043050  call    __security_check_cookie
0x180043055  add     rsp, 268h
0x18004305c  pop     r15
0x18004305e  pop     r14
0x180043060  pop     r13
0x180043062  pop     r12
0x180043064  pop     rdi
0x180043065  pop     rbx
0x180043066  retn
```
