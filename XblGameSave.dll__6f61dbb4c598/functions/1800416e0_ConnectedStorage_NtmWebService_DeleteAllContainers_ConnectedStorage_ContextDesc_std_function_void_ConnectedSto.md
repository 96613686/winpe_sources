# ConnectedStorage::NtmWebService::DeleteAllContainers(ConnectedStorage::ContextDesc,std::function<void (ConnectedStorage::WebService::Status)>)

- ea: `0x1800416e0`
- end: `0x180041a48`
- name: `?DeleteAllContainers@NtmWebService@ConnectedStorage@@UEBA?AV?$shared_ptr@VWebServiceCancelCallback@ConnectedStorage@@@std@@VContextDesc@2@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@4@@Z`
- size: `872`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
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
- `0x18002a1dc`
- `0x18003c420`
- `0x18003d428`
- `0x18003db84`
- `0x18003e440`
- `0x18003ee9c`
- `0x18003eee0`
- `0x1800416e0`
- `0x180043580`
- `0x180043758`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800417b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800419d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800417b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800419d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041a0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041a0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800418ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800418ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041902`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800417c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800417c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
_QWORD *__fastcall ConnectedStorage::NtmWebService::DeleteAllContainers(__int64 a1, _QWORD *a2, char *a3, __int64 a4)
{
  __int64 v4; // rsi
  HSTRING *v5; // r14
  _QWORD *v6; // rdi
  struct ConnectedStorage::Mutex *v8; // r12
  char *v9; // r8
  __int64 v10; // r8
  ULONGLONG TickCount64; // rax
  __int64 *v12; // r12
  __int64 v13; // r15
  __int64 v14; // rax
  __int64 v15; // r15
  HSTRING *v16; // r13
  HSTRING *v17; // rax
  __int64 v18; // rax
  char *v19; // r8
  __int64 v20; // r8
  __int16 v22; // [rsp+28h] [rbp-240h]
  __int64 v23; // [rsp+50h] [rbp-218h] BYREF
  void (__fastcall *v24)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, int, __int16, HSTRING *, __int64 *, _BYTE *); // [rsp+58h] [rbp-210h] BYREF
  __int64 v25; // [rsp+60h] [rbp-208h] BYREF
  HSTRING string; // [rsp+68h] [rbp-200h] BYREF
  HSTRING v27; // [rsp+70h] [rbp-1F8h] BYREF
  __int64 v28; // [rsp+78h] [rbp-1F0h]
  char *v29; // [rsp+80h] [rbp-1E8h]
  _QWORD *v30; // [rsp+88h] [rbp-1E0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp-1D8h] BYREF
  std::_Ref_count_base *v32; // [rsp+98h] [rbp-1D0h]
  struct ConnectedStorage::Mutex *v33; // [rsp+A8h] [rbp-1C0h]
  __int128 v34; // [rsp+B0h] [rbp-1B8h] BYREF
  LPCRITICAL_SECTION v35[2]; // [rsp+C0h] [rbp-1A8h] BYREF
  LPCRITICAL_SECTION v36[2]; // [rsp+D0h] [rbp-198h] BYREF
  unsigned __int16 v37[16]; // [rsp+E0h] [rbp-188h] BYREF
  HSTRING__ v38[8]; // [rsp+100h] [rbp-168h] BYREF
  _BYTE v39[56]; // [rsp+120h] [rbp-148h] BYREF
  __int64 v40; // [rsp+158h] [rbp-110h]
  _DWORD v41[16]; // [rsp+160h] [rbp-108h] BYREF
  _BYTE v42[128]; // [rsp+1A0h] [rbp-C8h] BYREF

  v4 = a4;
  v5 = (HSTRING *)a3;
  v6 = a2;
  v30 = a2;
  v29 = a3;
  v28 = a4;
  v34 = 0;
  if ( *(_BYTE *)(a1 + 25) || *(_BYTE *)(a1 + 24) )
  {
    v8 = (struct ConnectedStorage::Mutex *)(a1 + 40);
    v33 = (struct ConnectedStorage::Mutex *)(a1 + 40);
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)v35,
      (struct _RTL_CRITICAL_SECTION *)(a1 + 40),
      a3);
    if ( !*(_QWORD *)(a1 + 88) )
    {
      ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)&lpCriticalSection, v8, v9);
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
        v4,
        1,
        v10);
      *v6 = 0;
      v6[1] = 0;
      EnterCriticalSection(lpCriticalSection);
LABEL_17:
      LeaveCriticalSection(v35[0]);
      goto LABEL_18;
    }
    TickCount64 = GetTickCount64();
    try
    {
      v24 = (void (__fastcall *)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, int, __int16, HSTRING *, __int64 *, _BYTE *))TickCount64;
      ConnectedStorage::MakeUrl(v37, v5);
      ConnectedStorage::NtmWebService::MakeHeadersWithContext(a1, v38, v37, v5);
      Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(&v25);
      v12 = *(__int64 **)(a1 + 88);
      v13 = *v12;
      v14 = lambda_ca3efaf91aba89d7a60309b7b4b27852_::_lambda_ca3efaf91aba89d7a60309b7b4b27852_(v42, v4, &v25, v5, &v24);
      v40 = 0;
      v40 = std::_Global_new_std::_Func_impl_no_alloc__lambda_af36b16b5b276b53a346b8485ffec307__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_af36b16b5b276b53a346b8485ffec307___(v14);
      v24 = *(void (__fastcall **)(__int64 *, LPCRITICAL_SECTION *, HSTRING *, __int64, int, __int16, HSTRING *, __int64 *, _BYTE *))(v13 + 8);
      lpCriticalSection = (LPCRITICAL_SECTION)&v23;
      v15 = v25;
      v23 = v25;
      Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&v23);
      v16 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v27, (__int64)v38);
      v17 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, (__int64)v37);
      v22 = 30;
      v24(v12, v36, v17, 320, 1, v22, v16, &v23, v39);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v27);
      v27 = 0;
      std::function<long (void)>::~function<long (void)>(v39);
      lambda_ca3efaf91aba89d7a60309b7b4b27852_::__lambda_ca3efaf91aba89d7a60309b7b4b27852_(v42);
      v18 = std::make_shared<ConnectedStorage::NtmCancelCallback,_GUID &>(&lpCriticalSection, v36);
      std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(&v34, v18);
      if ( v32 )
        std::_Ref_count_base::_Decref(v32);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      std::wstring::_Tidy_deallocate(v38);
      std::wstring::_Tidy_deallocate(v37);
    }
    catch ( ConnectedStorage::ComError v41 )
    {
      LODWORD(v23) = v41[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v41);
      if ( (int)v23 < 0 )
      {
LABEL_14:
        ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)v36, v33, v19);
        v4 = v28;
        std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
          v28,
          1,
          v20);
        EnterCriticalSection(v36[0]);
      }
      else
      {
        v4 = v28;
      }
      v6 = v30;
      v5 = (HSTRING *)v29;
    }
    catch ( std::bad_alloc )
    {
      goto LABEL_14;
    }
    catch ( ... )
    {
      goto LABEL_14;
    }
    *(_OWORD *)v6 = v34;
    goto LABEL_17;
  }
  std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
    a4,
    1,
    a3);
  *v6 = 0;
  v6[1] = 0;
LABEL_18:
  ConnectedStorage::ContextDesc::~ContextDesc(v5);
  std::function<long (void)>::~function<long (void)>(v4);
  return v6;
}

```

## disassembly

```asm
0x1800416e0  push    rsi
0x1800416e2  push    rdi
0x1800416e3  push    r12
0x1800416e5  push    r13
0x1800416e7  push    r14
0x1800416e9  push    r15
0x1800416eb  sub     rsp, 238h
0x1800416f2  mov     rax, cs:__security_cookie
0x1800416f9  xor     rax, rsp
0x1800416fc  mov     [rsp+268h+var_48], rax
0x180041704  mov     rsi, r9
0x180041707  mov     r14, r8
0x18004170a  mov     rdi, rdx
0x18004170d  mov     r15, rcx
0x180041710  mov     [rsp+268h+var_1E0], rdx
0x180041718  mov     [rsp+268h+var_1E8], r8
0x180041720  mov     [rsp+268h+var_1F0], r9
0x180041725  xorps   xmm0, xmm0
0x180041728  movdqu  [rsp+268h+var_1B8], xmm0
0x180041731  cmp     byte ptr [rcx+19h], 0
0x180041735  jnz     short loc_18004175E
0x180041737  cmp     byte ptr [rcx+18h], 0
0x18004173b  jnz     short loc_18004175E
0x18004173d  mov     edx, 1
0x180041742  mov     rcx, r9
0x180041745  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x18004174a  mov     qword ptr [rdi], 0
0x180041751  mov     qword ptr [rdi+8], 0
0x180041759  jmp     loc_180041A12
0x18004175e  lea     r12, [rcx+28h]
0x180041762  mov     [rsp+268h+var_1C0], r12
0x18004176a  mov     rdx, r12; struct ConnectedStorage::Mutex *
0x18004176d  lea     rcx, [rsp+268h+var_1A8]; this
0x180041775  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18004177a  nop
0x18004177b  cmp     qword ptr [r15+58h], 0
0x180041780  jnz     short loc_1800417C2
0x180041782  mov     rdx, r12; struct ConnectedStorage::Mutex *
0x180041785  lea     rcx, [rsp+268h+lpCriticalSection]; this
0x18004178d  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180041792  nop
0x180041793  mov     edx, 1
0x180041798  mov     rcx, rsi
0x18004179b  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x1800417a0  mov     qword ptr [rdi], 0
0x1800417a7  mov     qword ptr [rdi+8], 0
0x1800417af  mov     rcx, [rsp+268h+lpCriticalSection]; lpCriticalSection
0x1800417b7  call    cs:__imp_EnterCriticalSection
0x1800417bd  jmp     loc_180041A03
0x1800417c2  call    cs:__imp_GetTickCount64
0x1800417c8  mov     [rsp+268h+var_210], rax
0x1800417cd  mov     rdx, r14
0x1800417d0  lea     rcx, [rsp+268h+var_188]
0x1800417d8  call    ?MakeUrl@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@@Z; ConnectedStorage::MakeUrl(ConnectedStorage::ContextDesc const &)
0x1800417dd  nop
0x1800417de  mov     r9, r14
0x1800417e1  lea     r8, [rsp+268h+var_188]
0x1800417e9  lea     rdx, [rsp+268h+var_168]
0x1800417f1  mov     rcx, r15
0x1800417f4  call    ?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x1800417f9  nop
0x1800417fa  lea     rcx, [rsp+268h+var_208]
0x1800417ff  call    ??$Make@VStringStream@ConnectedStorage@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VStringStream@ConnectedStorage@@@12@XZ; Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(void)
0x180041804  nop
0x180041805  mov     r12, [r15+58h]
0x180041809  mov     r15, [r12]
0x18004180d  lea     rax, [rsp+268h+var_210]
0x180041812  mov     [rsp+268h+var_248], rax
0x180041817  mov     r9, r14
0x18004181a  lea     r8, [rsp+268h+var_208]
0x18004181f  mov     rdx, rsi
0x180041822  lea     rcx, [rsp+268h+var_C8]
0x18004182a  call    _lambda_ca3efaf91aba89d7a60309b7b4b27852____lambda_ca3efaf91aba89d7a60309b7b4b27852_
0x18004182f  nop
0x180041830  mov     [rsp+268h+var_110], 0
0x18004183c  mov     rcx, rax
0x18004183f  call    std___Global_new_std___Func_impl_no_alloc__lambda_af36b16b5b276b53a346b8485ffec307__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_af36b16b5b276b53a346b8485ffec307___
0x180041844  mov     [rsp+268h+var_110], rax
0x18004184c  mov     rax, [r15+8]
0x180041850  mov     [rsp+268h+var_210], rax
0x180041855  lea     rcx, [rsp+268h+var_218]
0x18004185a  mov     [rsp+268h+lpCriticalSection], rcx
0x180041862  mov     r15, [rsp+268h+var_208]
0x180041867  mov     [rsp+268h+var_218], r15
0x18004186c  lea     rcx, [rsp+268h+var_218]
0x180041871  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x180041876  nop
0x180041877  lea     rdx, [rsp+268h+var_168]
0x18004187f  lea     rcx, [rsp+268h+var_1F8]; string
0x180041884  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180041889  mov     r13, rax
0x18004188c  lea     rdx, [rsp+268h+var_188]
0x180041894  lea     rcx, [rsp+268h+string]; string
0x180041899  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x18004189e  nop
0x18004189f  lea     rcx, [rsp+268h+var_148]
0x1800418a7  mov     [rsp+268h+var_228], rcx
0x1800418ac  lea     rcx, [rsp+268h+var_218]
0x1800418b1  mov     [rsp+268h+var_230], rcx
0x1800418b6  mov     [rsp+268h+var_238], r13
0x1800418bb  mov     [rsp+268h+var_240], 1Eh
0x1800418c2  mov     dword ptr [rsp+268h+var_248], 1
0x1800418ca  mov     r9d, 140h
0x1800418d0  mov     r8, rax
0x1800418d3  lea     rdx, [rsp+268h+var_198]
0x1800418db  mov     rcx, r12
0x1800418de  mov     rax, [rsp+268h+var_210]
0x1800418e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418e8  nop
0x1800418e9  mov     rcx, [rsp+268h+string]; string
0x1800418ee  call    cs:__imp_WindowsDeleteString
0x1800418f4  mov     [rsp+268h+string], 0
0x1800418fd  mov     rcx, [rsp+268h+var_1F8]; string
0x180041902  call    cs:__imp_WindowsDeleteString
0x180041908  mov     [rsp+268h+var_1F8], 0
0x180041911  lea     rcx, [rsp+268h+var_148]
0x180041919  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18004191e  nop
0x18004191f  lea     rcx, [rsp+268h+var_C8]
0x180041927  call    _lambda_ca3efaf91aba89d7a60309b7b4b27852_____lambda_ca3efaf91aba89d7a60309b7b4b27852_
0x18004192c  lea     rdx, [rsp+268h+var_198]
0x180041934  lea     rcx, [rsp+268h+lpCriticalSection]
0x18004193c  call    ??$make_shared@VNtmCancelCallback@ConnectedStorage@@AEAU_GUID@@@std@@YA?AV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@0@AEAU_GUID@@@Z; std::make_shared<ConnectedStorage::NtmCancelCallback,_GUID &>(_GUID &)
0x180041941  mov     rdx, rax
0x180041944  lea     rcx, [rsp+268h+var_1B8]
0x18004194c  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x180041951  mov     rcx, [rsp+268h+var_1D0]; this
0x180041959  test    rcx, rcx
0x18004195c  jz      short loc_180041964
0x18004195e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041963  nop
0x180041964  test    r15, r15
0x180041967  jz      short loc_180041979
0x180041969  mov     rax, [r15]
0x18004196c  mov     rcx, r15
0x18004196f  mov     rax, [rax+10h]
0x180041973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041978  nop
0x180041979  lea     rcx, [rsp+268h+var_168]
0x180041981  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041986  nop
0x180041987  lea     rcx, [rsp+268h+var_188]
0x18004198f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041994  nop
0x180041995  jmp     short loc_1800419EC
0x180041997  cmp     dword ptr [rsp+268h+var_218], 0
0x18004199c  jl      short loc_1800419A5
0x18004199e  mov     rsi, [rsp+268h+var_1F0]
0x1800419a3  jmp     short loc_1800419DC
0x1800419a5  mov     rdx, [rsp+268h+var_1C0]; struct ConnectedStorage::Mutex *
0x1800419ad  lea     rcx, [rsp+268h+var_198]; this
0x1800419b5  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x1800419ba  nop
0x1800419bb  mov     edx, 1
0x1800419c0  mov     rsi, [rsp+268h+var_1F0]
0x1800419c5  mov     rcx, rsi
0x1800419c8  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x1800419cd  nop
0x1800419ce  mov     rcx, [rsp+268h+var_198]; lpCriticalSection
0x1800419d6  call    cs:__imp_EnterCriticalSection
0x1800419dc  mov     rdi, [rsp+268h+var_1E0]
0x1800419e4  mov     r14, [rsp+268h+var_1E8]
0x1800419ec  mov     rax, qword ptr [rsp+268h+var_1B8]
0x1800419f4  mov     [rdi], rax
0x1800419f7  mov     rax, qword ptr [rsp+268h+var_1B8+8]
0x1800419ff  mov     [rdi+8], rax
0x180041a03  mov     rcx, [rsp+268h+var_1A8]; lpCriticalSection
0x180041a0b  call    cs:__imp_LeaveCriticalSection
0x180041a11  nop
0x180041a12  mov     rcx, r14; this
0x180041a15  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180041a1a  nop
0x180041a1b  mov     rcx, rsi
0x180041a1e  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180041a23  mov     rax, rdi
0x180041a26  mov     rcx, [rsp+268h+var_48]
0x180041a2e  xor     rcx, rsp; StackCookie
0x180041a31  call    __security_check_cookie
0x180041a36  add     rsp, 238h
0x180041a3d  pop     r15
0x180041a3f  pop     r14
0x180041a41  pop     r13
0x180041a43  pop     r12
0x180041a45  pop     rdi
0x180041a46  pop     rsi
0x180041a47  retn
```
