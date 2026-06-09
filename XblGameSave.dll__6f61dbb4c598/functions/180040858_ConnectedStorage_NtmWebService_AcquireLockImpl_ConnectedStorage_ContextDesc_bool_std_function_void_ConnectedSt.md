# ConnectedStorage::NtmWebService::AcquireLockImpl(ConnectedStorage::ContextDesc,bool,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64)>)

- ea: `0x180040858`
- end: `0x180040c3d`
- name: `?AcquireLockImpl@NtmWebService@ConnectedStorage@@AEBAXVContextDesc@2@_NV?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@_K@Z@std@@@Z`
- size: `997`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004015c`
- `0x180040740`

## callees

- `0x180003c70`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x18000d6bc`
- `0x180011c68`
- `0x1800125ec`
- `0x18001c090`
- `0x18001e208`
- `0x18002cf5c`
- `0x18003a1e8`
- `0x18003c420`
- `0x18003cee0`
- `0x18003dcd8`
- `0x18003ee9c`
- `0x18003eee0`
- `0x180040858`
- `0x180043580`
- `0x180043758`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040bf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040bf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040c03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040c03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800408c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004095a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040ad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040be5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800408c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004095a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040ad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040be5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040b91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040b91`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040966`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040966`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall ConnectedStorage::NtmWebService::AcquireLockImpl(
        __int64 a1,
        ConnectedStorage::SimpleHStringWrapper *a2,
        char a3,
        __int64 a4)
{
  __int64 v4; // rbx
  HSTRING *v6; // rsi
  char *v8; // r8
  char *v9; // r8
  ULONGLONG TickCount64; // rax
  __int64 *v11; // r15
  __int64 v12; // r14
  __int64 v13; // rax
  void (__fastcall *v14)(__int64 *, _BYTE *, HSTRING *, __int64, int, int); // r13
  HSTRING v15; // r14
  unsigned int v16; // r12d
  HSTRING *v17; // rax
  char *v18; // r8
  const unsigned __int16 *StringRawBuffer; // rbx
  ConnectedStorage *v20; // rax
  const unsigned __int16 *v21; // r8
  int v23; // [rsp+28h] [rbp-230h]
  unsigned int v24; // [rsp+30h] [rbp-228h]
  unsigned __int16 *v25; // [rsp+50h] [rbp-208h] BYREF
  HSTRING string; // [rsp+58h] [rbp-200h] BYREF
  HSTRING v27; // [rsp+60h] [rbp-1F8h] BYREF
  HSTRING v28; // [rsp+68h] [rbp-1F0h] BYREF
  HSTRING v29; // [rsp+70h] [rbp-1E8h] BYREF
  HSTRING *v30; // [rsp+78h] [rbp-1E0h]
  __int64 v31; // [rsp+80h] [rbp-1D8h]
  HSTRING *p_string; // [rsp+88h] [rbp-1D0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+90h] [rbp-1C8h] BYREF
  LPCRITICAL_SECTION v34[2]; // [rsp+A0h] [rbp-1B8h] BYREF
  _BYTE Src[32]; // [rsp+B0h] [rbp-1A8h] BYREF
  _BYTE v36[32]; // [rsp+D0h] [rbp-188h] BYREF
  _BYTE v37[16]; // [rsp+F0h] [rbp-168h] BYREF
  _BYTE v38[56]; // [rsp+100h] [rbp-158h] BYREF
  __int64 v39; // [rsp+138h] [rbp-120h]
  _DWORD v40[16]; // [rsp+140h] [rbp-118h] BYREF
  _BYTE v41[144]; // [rsp+180h] [rbp-D8h] BYREF

  v4 = a4;
  v6 = (HSTRING *)a2;
  v30 = (HSTRING *)a2;
  LOBYTE(v25) = a3;
  v31 = a4;
  if ( !ConnectedStorage::SimpleHStringWrapper::IsEmpty(a2) )
  {
    if ( !*(_BYTE *)(a1 + 25) && !*(_BYTE *)(a1 + 24) )
    {
      string = 0;
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(
        v4,
        1,
        &string);
      goto LABEL_3;
    }
    lpCriticalSection[0] = (LPCRITICAL_SECTION)(a1 + 40);
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)v34,
      (struct _RTL_CRITICAL_SECTION *)(a1 + 40),
      v8);
    if ( !*(_QWORD *)(a1 + 88) )
    {
      ConnectedStorage::Mutex::Unlock::Unlock(
        (ConnectedStorage::Mutex::Unlock *)lpCriticalSection,
        (struct ConnectedStorage::Mutex *)(a1 + 40),
        v9);
      string = 0;
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(
        v4,
        1,
        &string);
      WindowsDeleteString(string);
LABEL_18:
      EnterCriticalSection(lpCriticalSection[0]);
      goto LABEL_19;
    }
    TickCount64 = GetTickCount64();
    try
    {
      p_string = (HSTRING *)TickCount64;
      ConnectedStorage::MakeUrl(Src, v6);
      std::wstring::_Append<unsigned short>(Src);
      if ( a3 )
        std::wstring::_Append<unsigned short>(Src);
      ConnectedStorage::NtmWebService::MakeHeadersWithContext(a1, v36, Src, v6);
      Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(&v28);
      v11 = *(__int64 **)(a1 + 88);
      v12 = *v11;
      v13 = lambda_1737a0e7fb134fea92332ee7c26f729c_::_lambda_1737a0e7fb134fea92332ee7c26f729c_(
              v41,
              v4,
              &v28,
              v6,
              &v25,
              &p_string);
      v39 = 0;
      v39 = std::_Global_new_std::_Func_impl_no_alloc__lambda_1737a0e7fb134fea92332ee7c26f729c__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_1737a0e7fb134fea92332ee7c26f729c___(v13);
      v14 = *(void (__fastcall **)(__int64 *, _BYTE *, HSTRING *, __int64, int, int))(v12 + 8);
      p_string = &string;
      v15 = v28;
      string = v28;
      Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&string);
      v16 = (unsigned int)ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v27, (__int64)v36);
      v17 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v29, (__int64)Src);
      v24 = v16;
      LOWORD(v23) = 30;
      v14(v11, v37, v17, 88, 1, v23);
      WindowsDeleteString(v29);
      v29 = 0;
      WindowsDeleteString(v27);
      v27 = 0;
      std::function<long (void)>::~function<long (void)>(v38);
      lambda_ca3efaf91aba89d7a60309b7b4b27852_::__lambda_ca3efaf91aba89d7a60309b7b4b27852_(v41);
      if ( v15 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
      std::wstring::_Tidy_deallocate(v36);
      std::wstring::_Tidy_deallocate(Src);
    }
    catch ( ConnectedStorage::ComError v40 )
    {
      LODWORD(string) = v40[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v40);
      if ( (int)string < 0 )
      {
LABEL_17:
        ConnectedStorage::Mutex::Unlock::Unlock(
          (ConnectedStorage::Mutex::Unlock *)lpCriticalSection,
          (struct ConnectedStorage::Mutex *)lpCriticalSection[0],
          v18);
        v6 = v30;
        StringRawBuffer = WindowsGetStringRawBuffer(v30[2], 0);
        v20 = (ConnectedStorage *)WindowsGetStringRawBuffer(v6[3], 0);
        LOBYTE(v21) = (_BYTE)v25;
        ConnectedStorage::EventWriteWebAcquireLock(v20, StringRawBuffer, v21, 0, (unsigned int)string, 0, v24);
        v27 = 0;
        v4 = v31;
        std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(
          v31,
          1,
          &v27);
        WindowsDeleteString(v27);
        goto LABEL_18;
      }
      v6 = v30;
      v4 = v31;
    }
    catch ( std::bad_alloc )
    {
      LODWORD(string) = -2147024882;
      goto LABEL_17;
    }
    catch ( ... )
    {
      LODWORD(string) = -2147467259;
      goto LABEL_17;
    }
LABEL_19:
    LeaveCriticalSection(v34[0]);
    goto LABEL_20;
  }
  string = 0;
  std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(
    v4,
    4,
    &string);
LABEL_3:
  WindowsDeleteString(string);
LABEL_20:
  ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v6);
  return std::function<long (void)>::~function<long (void)>(v4);
}

```

## disassembly

```asm
0x180040858  push    rbx
0x18004085a  push    rsi
0x18004085b  push    r12
0x18004085d  push    r13
0x18004085f  push    r14
0x180040861  push    r15
0x180040863  sub     rsp, 228h
0x18004086a  mov     rax, cs:__security_cookie
0x180040871  xor     rax, rsp
0x180040874  mov     [rsp+258h+var_48], rax
0x18004087c  mov     rbx, r9
0x18004087f  mov     r12b, r8b
0x180040882  mov     rsi, rdx
0x180040885  mov     r14, rcx
0x180040888  mov     [rsp+258h+var_1E0], rdx
0x18004088d  mov     byte ptr [rsp+258h+var_208], r8b
0x180040892  mov     [rsp+258h+var_1D8], rbx
0x18004089a  mov     rcx, rdx; this
0x18004089d  call    ?IsEmpty@SimpleHStringWrapper@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::SimpleHStringWrapper::IsEmpty(void)
0x1800408a2  test    al, al
0x1800408a4  jz      short loc_1800408D4
0x1800408a6  mov     [rsp+258h+string], 0
0x1800408af  xor     r9d, r9d
0x1800408b2  lea     r8, [rsp+258h+string]
0x1800408b7  lea     edx, [r9+4]
0x1800408bb  mov     rcx, rbx
0x1800408be  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@_K@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@_K@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64)
0x1800408c3  nop
0x1800408c4  mov     rcx, [rsp+258h+string]; string
0x1800408c9  call    cs:__imp_WindowsDeleteString
0x1800408cf  jmp     loc_180040C0A
0x1800408d4  cmp     byte ptr [r14+19h], 0
0x1800408d9  jnz     short loc_180040902
0x1800408db  cmp     byte ptr [r14+18h], 0
0x1800408e0  jnz     short loc_180040902
0x1800408e2  mov     [rsp+258h+string], 0
0x1800408eb  xor     r9d, r9d
0x1800408ee  lea     r8, [rsp+258h+string]
0x1800408f3  lea     edx, [r9+1]
0x1800408f7  mov     rcx, rbx
0x1800408fa  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@_K@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@_K@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64)
0x1800408ff  nop
0x180040900  jmp     short loc_1800408C4
0x180040902  lea     r15, [r14+28h]
0x180040906  mov     [rsp+258h+lpCriticalSection], r15
0x18004090e  mov     rdx, r15; struct ConnectedStorage::Mutex *
0x180040911  lea     rcx, [rsp+258h+var_1B8]; this
0x180040919  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18004091e  nop
0x18004091f  cmp     qword ptr [r14+58h], 0
0x180040924  jnz     short loc_180040966
0x180040926  mov     rdx, r15; struct ConnectedStorage::Mutex *
0x180040929  lea     rcx, [rsp+258h+lpCriticalSection]; this
0x180040931  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180040936  nop
0x180040937  mov     [rsp+258h+string], 0
0x180040940  xor     r9d, r9d
0x180040943  lea     r8, [rsp+258h+string]
0x180040948  lea     edx, [r9+1]
0x18004094c  mov     rcx, rbx
0x18004094f  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@_K@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@_K@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64)
0x180040954  nop
0x180040955  mov     rcx, [rsp+258h+string]; string
0x18004095a  call    cs:__imp_WindowsDeleteString
0x180040960  nop
0x180040961  jmp     loc_180040BEC
0x180040966  call    cs:__imp_GetTickCount64
0x18004096c  mov     [rsp+258h+var_1D0], rax
0x180040974  mov     rdx, rsi
0x180040977  lea     rcx, [rsp+258h+Src]
0x18004097f  call    ?MakeUrl@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@@Z; ConnectedStorage::MakeUrl(ConnectedStorage::ContextDesc const &)
0x180040984  nop
0x180040985  mov     r8d, 4
0x18004098b  lea     rdx, aLock; "lock"
0x180040992  lea     rcx, [rsp+258h+Src]; Src
0x18004099a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004099f  test    r12b, r12b
0x1800409a2  jz      short loc_1800409BE
0x1800409a4  mov     r8d, 0Fh
0x1800409aa  lea     rdx, aBreaklockTrue; "?breakLock=true"
0x1800409b1  lea     rcx, [rsp+258h+Src]; Src
0x1800409b9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800409be  mov     r9, rsi
0x1800409c1  lea     r8, [rsp+258h+Src]
0x1800409c9  lea     rdx, [rsp+258h+var_188]
0x1800409d1  mov     rcx, r14
0x1800409d4  call    ?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x1800409d9  nop
0x1800409da  lea     rcx, [rsp+258h+var_1F0]
0x1800409df  call    ??$Make@VStringStream@ConnectedStorage@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VStringStream@ConnectedStorage@@@12@XZ; Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(void)
0x1800409e4  nop
0x1800409e5  mov     r15, [r14+58h]
0x1800409e9  mov     r14, [r15]
0x1800409ec  lea     rax, [rsp+258h+var_1D0]
0x1800409f4  mov     qword ptr [rsp+258h+var_230], rax
0x1800409f9  lea     rax, [rsp+258h+var_208]
0x1800409fe  mov     qword ptr [rsp+258h+var_238], rax
0x180040a03  mov     r9, rsi
0x180040a06  lea     r8, [rsp+258h+var_1F0]
0x180040a0b  mov     rdx, rbx
0x180040a0e  lea     rcx, [rsp+258h+var_D8]
0x180040a16  call    _lambda_1737a0e7fb134fea92332ee7c26f729c____lambda_1737a0e7fb134fea92332ee7c26f729c_
0x180040a1b  nop
0x180040a1c  mov     [rsp+258h+var_120], 0
0x180040a28  mov     rcx, rax
0x180040a2b  call    std___Global_new_std___Func_impl_no_alloc__lambda_1737a0e7fb134fea92332ee7c26f729c__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_1737a0e7fb134fea92332ee7c26f729c___
0x180040a30  mov     [rsp+258h+var_120], rax
0x180040a38  mov     r13, [r14+8]
0x180040a3c  lea     rax, [rsp+258h+string]
0x180040a41  mov     [rsp+258h+var_1D0], rax
0x180040a49  mov     r14, [rsp+258h+var_1F0]
0x180040a4e  mov     [rsp+258h+string], r14
0x180040a53  lea     rcx, [rsp+258h+string]
0x180040a58  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x180040a5d  nop
0x180040a5e  lea     rdx, [rsp+258h+var_188]
0x180040a66  lea     rcx, [rsp+258h+var_1F8]; string
0x180040a6b  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180040a70  mov     r12, rax
0x180040a73  lea     rdx, [rsp+258h+Src]
0x180040a7b  lea     rcx, [rsp+258h+var_1E8]; string
0x180040a80  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180040a85  nop
0x180040a86  lea     rcx, [rsp+258h+var_158]
0x180040a8e  mov     [rsp+258h+var_218], rcx
0x180040a93  lea     rcx, [rsp+258h+string]
0x180040a98  mov     [rsp+258h+var_220], rcx
0x180040a9d  mov     [rsp+258h+var_228], r12
0x180040aa2  mov     word ptr [rsp+258h+var_230], 1Eh
0x180040aa9  mov     [rsp+258h+var_238], 1
0x180040ab1  mov     r9d, 58h ; 'X'
0x180040ab7  mov     r8, rax
0x180040aba  lea     rdx, [rsp+258h+var_168]
0x180040ac2  mov     rcx, r15
0x180040ac5  mov     rax, r13
0x180040ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040acd  nop
0x180040ace  mov     rcx, [rsp+258h+var_1E8]; string
0x180040ad3  call    cs:__imp_WindowsDeleteString
0x180040ad9  mov     [rsp+258h+var_1E8], 0
0x180040ae2  mov     rcx, [rsp+258h+var_1F8]; string
0x180040ae7  call    cs:__imp_WindowsDeleteString
0x180040aed  mov     [rsp+258h+var_1F8], 0
0x180040af6  lea     rcx, [rsp+258h+var_158]
0x180040afe  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180040b03  nop
0x180040b04  lea     rcx, [rsp+258h+var_D8]
0x180040b0c  call    _lambda_ca3efaf91aba89d7a60309b7b4b27852_____lambda_ca3efaf91aba89d7a60309b7b4b27852_
0x180040b11  nop
0x180040b12  test    r14, r14
0x180040b15  jz      short loc_180040B27
0x180040b17  mov     rax, [r14]
0x180040b1a  mov     rcx, r14
0x180040b1d  mov     rax, [rax+10h]
0x180040b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b26  nop
0x180040b27  lea     rcx, [rsp+258h+var_188]
0x180040b2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040b34  nop
0x180040b35  lea     rcx, [rsp+258h+Src]
0x180040b3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040b42  nop
0x180040b43  jmp     loc_180040BFB
0x180040b48  cmp     dword ptr [rsp+258h+string], 0
0x180040b4d  jl      short loc_180040B61
0x180040b4f  mov     rsi, [rsp+258h+var_1E0]
0x180040b54  mov     rbx, [rsp+258h+var_1D8]
0x180040b5c  jmp     loc_180040BFB
0x180040b61  mov     rdx, [rsp+258h+lpCriticalSection]; struct ConnectedStorage::Mutex *
0x180040b69  lea     rcx, [rsp+258h+lpCriticalSection]; this
0x180040b71  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180040b76  nop
0x180040b77  xor     edx, edx; length
0x180040b79  mov     rsi, [rsp+258h+var_1E0]
0x180040b7e  mov     rcx, [rsi+10h]; string
0x180040b82  call    cs:__imp_WindowsGetStringRawBuffer
0x180040b88  mov     rbx, rax
0x180040b8b  xor     edx, edx; length
0x180040b8d  mov     rcx, [rsi+18h]; string
0x180040b91  call    cs:__imp_WindowsGetStringRawBuffer
0x180040b97  mov     [rsp+258h+var_230], 0; unsigned int
0x180040b9f  mov     ecx, dword ptr [rsp+258h+string]
0x180040ba3  mov     [rsp+258h+var_238], ecx; unsigned int
0x180040ba7  xor     r9d, r9d; bool
0x180040baa  mov     r8b, byte ptr [rsp+258h+var_208]; unsigned __int16 *
0x180040baf  mov     rdx, rbx; unsigned __int16 *
0x180040bb2  mov     rcx, rax; this
0x180040bb5  call    ?EventWriteWebAcquireLock@ConnectedStorage@@YAXQEBG0_NIII@Z; ConnectedStorage::EventWriteWebAcquireLock(ushort const * const,ushort const * const,bool,uint,uint,uint)
0x180040bba  mov     [rsp+258h+var_1F8], 0
0x180040bc3  xor     r9d, r9d
0x180040bc6  lea     r8, [rsp+258h+var_1F8]
0x180040bcb  lea     edx, [r9+1]
0x180040bcf  mov     rbx, [rsp+258h+var_1D8]
0x180040bd7  mov     rcx, rbx
0x180040bda  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@_K@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@_K@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64)
0x180040bdf  nop
0x180040be0  mov     rcx, [rsp+258h+var_1F8]; string
0x180040be5  call    cs:__imp_WindowsDeleteString
0x180040beb  nop
0x180040bec  mov     rcx, [rsp+258h+lpCriticalSection]; lpCriticalSection
0x180040bf4  call    cs:__imp_EnterCriticalSection
0x180040bfa  nop
0x180040bfb  mov     rcx, [rsp+258h+var_1B8]; lpCriticalSection
0x180040c03  call    cs:__imp_LeaveCriticalSection
0x180040c09  nop
0x180040c0a  mov     rcx, rsi; this
0x180040c0d  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180040c12  nop
0x180040c13  mov     rcx, rbx
0x180040c16  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180040c1b  mov     rcx, [rsp+258h+var_48]
0x180040c23  xor     rcx, rsp; StackCookie
0x180040c26  call    __security_check_cookie
0x180040c2b  add     rsp, 228h
0x180040c32  pop     r15
0x180040c34  pop     r14
0x180040c36  pop     r13
0x180040c38  pop     r12
0x180040c3a  pop     rsi
0x180040c3b  pop     rbx
0x180040c3c  retn
```
