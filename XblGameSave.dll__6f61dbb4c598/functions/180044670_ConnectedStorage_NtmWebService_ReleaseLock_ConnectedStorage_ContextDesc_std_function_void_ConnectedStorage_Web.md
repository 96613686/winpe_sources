# ConnectedStorage::NtmWebService::ReleaseLock(ConnectedStorage::ContextDesc,std::function<void (ConnectedStorage::WebService::Status)>)

- ea: `0x180044670`
- end: `0x1800449a9`
- name: `?ReleaseLock@NtmWebService@ConnectedStorage@@UEBAXVContextDesc@2@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@Z`
- size: `825`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000c218`
- `0x18000cb9c`
- `0x18000cd1c`
- `0x18000d6bc`
- `0x180011c68`
- `0x1800125ec`
- `0x1800136a8`
- `0x18001c090`
- `0x18001e958`
- `0x18002cf5c`
- `0x18003c420`
- `0x18003d56c`
- `0x18003e440`
- `0x18003ee9c`
- `0x18003eee0`
- `0x180043580`
- `0x180043758`
- `0x180044670`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004495a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004495a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044969`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044969`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004487a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004487a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004490f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004491e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004490f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004491e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180044722`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180044722`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall ConnectedStorage::NtmWebService::ReleaseLock(
        __int64 a1,
        ConnectedStorage::SimpleHStringWrapper *a2,
        __int64 a3)
{
  __int64 v3; // rbx
  HSTRING *v4; // rdi
  char *v6; // r8
  __int64 v7; // rdx
  char *v8; // r8
  __int64 v9; // r8
  ULONGLONG TickCount64; // rax
  __int64 *v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rax
  void (__fastcall *v14)(__int64 *, _BYTE *, HSTRING *, __int64, int); // r12
  __int64 v15; // rsi
  HSTRING *v16; // rax
  char *v17; // r8
  const unsigned __int16 *StringRawBuffer; // rbx
  ConnectedStorage *v19; // rax
  __int64 v20; // r8
  unsigned int v22; // [rsp+28h] [rbp-210h]
  unsigned int v23[2]; // [rsp+50h] [rbp-1E8h] BYREF
  __int64 v24; // [rsp+58h] [rbp-1E0h] BYREF
  HSTRING string; // [rsp+60h] [rbp-1D8h] BYREF
  HSTRING v26; // [rsp+68h] [rbp-1D0h] BYREF
  HSTRING *v27; // [rsp+70h] [rbp-1C8h]
  __int64 v28; // [rsp+78h] [rbp-1C0h]
  unsigned int *v29; // [rsp+80h] [rbp-1B8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+88h] [rbp-1B0h] BYREF
  LPCRITICAL_SECTION v31[2]; // [rsp+98h] [rbp-1A0h] BYREF
  unsigned __int16 Src[16]; // [rsp+A8h] [rbp-190h] BYREF
  HSTRING__ v33[8]; // [rsp+C8h] [rbp-170h] BYREF
  _BYTE v34[24]; // [rsp+E8h] [rbp-150h] BYREF
  _BYTE v35[56]; // [rsp+100h] [rbp-138h] BYREF
  __int64 v36; // [rsp+138h] [rbp-100h]
  _DWORD v37[16]; // [rsp+140h] [rbp-F8h] BYREF
  _BYTE v38[128]; // [rsp+180h] [rbp-B8h] BYREF

  v3 = a3;
  v4 = (HSTRING *)a2;
  v27 = (HSTRING *)a2;
  v28 = a3;
  if ( !ConnectedStorage::SimpleHStringWrapper::IsEmpty(a2) )
  {
    if ( !*(_BYTE *)(a1 + 25) && !*(_BYTE *)(a1 + 24) )
    {
      v7 = 1;
      goto LABEL_3;
    }
    lpCriticalSection[0] = (LPCRITICAL_SECTION)(a1 + 40);
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)v31,
      (struct _RTL_CRITICAL_SECTION *)(a1 + 40),
      v6);
    if ( !*(_QWORD *)(a1 + 88) )
    {
      ConnectedStorage::Mutex::Unlock::Unlock(
        (ConnectedStorage::Mutex::Unlock *)lpCriticalSection,
        (struct ConnectedStorage::Mutex *)(a1 + 40),
        v8);
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
        v3,
        1,
        v9);
LABEL_16:
      EnterCriticalSection(lpCriticalSection[0]);
      goto LABEL_17;
    }
    TickCount64 = GetTickCount64();
    try
    {
      v29 = (unsigned int *)TickCount64;
      ConnectedStorage::MakeUrl(Src, v4);
      std::wstring::_Append<unsigned short>(Src);
      ConnectedStorage::NtmWebService::MakeHeadersWithContext(a1, v33, Src, v4);
      Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(&v24);
      v11 = *(__int64 **)(a1 + 88);
      v12 = *v11;
      v13 = lambda_ca3efaf91aba89d7a60309b7b4b27852_::_lambda_ca3efaf91aba89d7a60309b7b4b27852_(v38, v3, &v24, v4, &v29);
      v36 = 0;
      v36 = std::_Global_new_std::_Func_impl_no_alloc__lambda_ca3efaf91aba89d7a60309b7b4b27852__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_ca3efaf91aba89d7a60309b7b4b27852___(v13);
      v14 = *(void (__fastcall **)(__int64 *, _BYTE *, HSTRING *, __int64, int))(v12 + 8);
      v29 = v23;
      v15 = v24;
      *(_QWORD *)v23 = v24;
      Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(v23);
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v26, (__int64)v33);
      v16 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, (__int64)Src);
      LOWORD(v22) = 45;
      v14(v11, v34, v16, 320, 1);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v26);
      v26 = 0;
      std::function<long (void)>::~function<long (void)>(v35);
      lambda_ca3efaf91aba89d7a60309b7b4b27852_::__lambda_ca3efaf91aba89d7a60309b7b4b27852_(v38);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      std::wstring::_Tidy_deallocate(v33);
      std::wstring::_Tidy_deallocate(Src);
    }
    catch ( ConnectedStorage::ComError v37 )
    {
      v23[0] = v37[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v37);
      if ( (v23[0] & 0x80000000) != 0 )
      {
LABEL_15:
        ConnectedStorage::Mutex::Unlock::Unlock(
          (ConnectedStorage::Mutex::Unlock *)lpCriticalSection,
          (struct ConnectedStorage::Mutex *)lpCriticalSection[0],
          v17);
        v4 = v27;
        StringRawBuffer = WindowsGetStringRawBuffer(v27[2], 0);
        v19 = (ConnectedStorage *)WindowsGetStringRawBuffer(v4[3], 0);
        ConnectedStorage::EventWriteWebReleaseLock(v19, StringRawBuffer, 0, v23[0], 0, v22);
        v3 = v28;
        std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
          v28,
          1,
          v20);
        goto LABEL_16;
      }
      v4 = v27;
      v3 = v28;
    }
    catch ( std::bad_alloc )
    {
      v23[0] = -2147024882;
      goto LABEL_15;
    }
    catch ( ... )
    {
      v23[0] = -2147467259;
      goto LABEL_15;
    }
LABEL_17:
    LeaveCriticalSection(v31[0]);
    goto LABEL_18;
  }
  v7 = 7;
LABEL_3:
  std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
    v3,
    v7,
    v6);
LABEL_18:
  ConnectedStorage::ContextDesc::~ContextDesc(v4);
  return std::function<long (void)>::~function<long (void)>(v3);
}

```

## disassembly

```asm
0x180044670  mov     [rsp+arg_18], rbx
0x180044675  push    rsi
0x180044676  push    rdi
0x180044677  push    r12
0x180044679  push    r14
0x18004467b  push    r15
0x18004467d  sub     rsp, 210h
0x180044684  mov     rax, cs:__security_cookie
0x18004468b  xor     rax, rsp
0x18004468e  mov     [rsp+238h+var_38], rax
0x180044696  mov     rbx, r8
0x180044699  mov     rdi, rdx
0x18004469c  mov     rsi, rcx
0x18004469f  mov     [rsp+238h+var_1C8], rdx
0x1800446a4  mov     [rsp+238h+var_1C0], rbx
0x1800446a9  mov     rcx, rdx; this
0x1800446ac  call    ?IsEmpty@SimpleHStringWrapper@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::SimpleHStringWrapper::IsEmpty(void)
0x1800446b1  test    al, al
0x1800446b3  jz      short loc_1800446C7
0x1800446b5  mov     edx, 7
0x1800446ba  mov     rcx, rbx
0x1800446bd  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x1800446c2  jmp     loc_180044970
0x1800446c7  cmp     byte ptr [rsi+19h], 0
0x1800446cb  jnz     short loc_1800446DA
0x1800446cd  cmp     byte ptr [rsi+18h], 0
0x1800446d1  jnz     short loc_1800446DA
0x1800446d3  mov     edx, 1
0x1800446d8  jmp     short loc_1800446BA
0x1800446da  lea     r14, [rsi+28h]
0x1800446de  mov     [rsp+238h+lpCriticalSection], r14
0x1800446e6  mov     rdx, r14; struct ConnectedStorage::Mutex *
0x1800446e9  lea     rcx, [rsp+238h+var_1A0]; this
0x1800446f1  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800446f6  nop
0x1800446f7  cmp     qword ptr [rsi+58h], 0
0x1800446fc  jnz     short loc_180044722
0x1800446fe  mov     rdx, r14; struct ConnectedStorage::Mutex *
0x180044701  lea     rcx, [rsp+238h+lpCriticalSection]; this
0x180044709  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x18004470e  nop
0x18004470f  mov     edx, 1
0x180044714  mov     rcx, rbx
0x180044717  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x18004471c  nop
0x18004471d  jmp     loc_180044952
0x180044722  call    cs:__imp_GetTickCount64
0x180044728  mov     [rsp+238h+var_1B8], rax
0x180044730  mov     rdx, rdi
0x180044733  lea     rcx, [rsp+238h+Src]
0x18004473b  call    ?MakeUrl@ConnectedStorage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVContextDesc@1@@Z; ConnectedStorage::MakeUrl(ConnectedStorage::ContextDesc const &)
0x180044740  nop
0x180044741  mov     r8d, 4
0x180044747  lea     rdx, aLock; "lock"
0x18004474e  lea     rcx, [rsp+238h+Src]; Src
0x180044756  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004475b  mov     r9, rdi
0x18004475e  lea     r8, [rsp+238h+Src]
0x180044766  lea     rdx, [rsp+238h+var_170]
0x18004476e  mov     rcx, rsi
0x180044771  call    ?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x180044776  nop
0x180044777  lea     rcx, [rsp+238h+var_1E0]
0x18004477c  call    ??$Make@VStringStream@ConnectedStorage@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VStringStream@ConnectedStorage@@@12@XZ; Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(void)
0x180044781  nop
0x180044782  mov     r14, [rsi+58h]
0x180044786  mov     rsi, [r14]
0x180044789  lea     rax, [rsp+238h+var_1B8]
0x180044791  mov     qword ptr [rsp+238h+var_218], rax
0x180044796  mov     r9, rdi
0x180044799  lea     r8, [rsp+238h+var_1E0]
0x18004479e  mov     rdx, rbx
0x1800447a1  lea     rcx, [rsp+238h+var_B8]
0x1800447a9  call    _lambda_ca3efaf91aba89d7a60309b7b4b27852____lambda_ca3efaf91aba89d7a60309b7b4b27852_
0x1800447ae  nop
0x1800447af  mov     [rsp+238h+var_100], 0
0x1800447bb  mov     rcx, rax
0x1800447be  call    std___Global_new_std___Func_impl_no_alloc__lambda_ca3efaf91aba89d7a60309b7b4b27852__void__NTM_TRANSFER_STATUS_const___unsigned_int_long___lambda_ca3efaf91aba89d7a60309b7b4b27852___
0x1800447c3  mov     [rsp+238h+var_100], rax
0x1800447cb  mov     r12, [rsi+8]
0x1800447cf  lea     rax, [rsp+238h+var_1E8]
0x1800447d4  mov     [rsp+238h+var_1B8], rax
0x1800447dc  mov     rsi, [rsp+238h+var_1E0]
0x1800447e1  mov     qword ptr [rsp+238h+var_1E8], rsi
0x1800447e6  lea     rcx, [rsp+238h+var_1E8]
0x1800447eb  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x1800447f0  nop
0x1800447f1  lea     rdx, [rsp+238h+var_170]
0x1800447f9  lea     rcx, [rsp+238h+var_1D0]; string
0x1800447fe  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180044803  mov     r15, rax
0x180044806  lea     rdx, [rsp+238h+Src]
0x18004480e  lea     rcx, [rsp+238h+string]; string
0x180044813  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180044818  nop
0x180044819  lea     rcx, [rsp+238h+var_138]
0x180044821  mov     [rsp+238h+var_1F8], rcx
0x180044826  lea     rcx, [rsp+238h+var_1E8]
0x18004482b  mov     [rsp+238h+var_200], rcx
0x180044830  mov     [rsp+238h+var_208], r15
0x180044835  mov     [rsp+238h+var_210], 2Dh ; '-'
0x18004483c  mov     [rsp+238h+var_218], 1
0x180044844  mov     r9d, 140h
0x18004484a  mov     r8, rax
0x18004484d  lea     rdx, [rsp+238h+var_150]
0x180044855  mov     rcx, r14
0x180044858  mov     rax, r12
0x18004485b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044860  nop
0x180044861  mov     rcx, [rsp+238h+string]; string
0x180044866  call    cs:__imp_WindowsDeleteString
0x18004486c  mov     [rsp+238h+string], 0
0x180044875  mov     rcx, [rsp+238h+var_1D0]; string
0x18004487a  call    cs:__imp_WindowsDeleteString
0x180044880  mov     [rsp+238h+var_1D0], 0
0x180044889  lea     rcx, [rsp+238h+var_138]
0x180044891  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180044896  nop
0x180044897  lea     rcx, [rsp+238h+var_B8]
0x18004489f  call    _lambda_ca3efaf91aba89d7a60309b7b4b27852_____lambda_ca3efaf91aba89d7a60309b7b4b27852_
0x1800448a4  nop
0x1800448a5  test    rsi, rsi
0x1800448a8  jz      short loc_1800448BA
0x1800448aa  mov     rax, [rsi]
0x1800448ad  mov     rcx, rsi
0x1800448b0  mov     rax, [rax+10h]
0x1800448b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448b9  nop
0x1800448ba  lea     rcx, [rsp+238h+var_170]
0x1800448c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800448c7  nop
0x1800448c8  lea     rcx, [rsp+238h+Src]
0x1800448d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800448d5  nop
0x1800448d6  jmp     loc_180044961
0x1800448db  cmp     [rsp+238h+var_1E8], 0
0x1800448e0  jl      short loc_1800448EE
0x1800448e2  mov     rdi, [rsp+238h+var_1C8]
0x1800448e7  mov     rbx, [rsp+238h+var_1C0]
0x1800448ec  jmp     short loc_180044961
0x1800448ee  mov     rdx, [rsp+238h+lpCriticalSection]; struct ConnectedStorage::Mutex *
0x1800448f6  lea     rcx, [rsp+238h+lpCriticalSection]; this
0x1800448fe  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180044903  nop
0x180044904  xor     edx, edx; length
0x180044906  mov     rdi, [rsp+238h+var_1C8]
0x18004490b  mov     rcx, [rdi+10h]; string
0x18004490f  call    cs:__imp_WindowsGetStringRawBuffer
0x180044915  mov     rbx, rax
0x180044918  xor     edx, edx; length
0x18004491a  mov     rcx, [rdi+18h]; string
0x18004491e  call    cs:__imp_WindowsGetStringRawBuffer
0x180044924  mov     [rsp+238h+var_218], 0; unsigned int
0x18004492c  mov     r9d, [rsp+238h+var_1E8]; unsigned int
0x180044931  xor     r8d, r8d; unsigned __int16 *
0x180044934  mov     rdx, rbx; unsigned __int16 *
0x180044937  mov     rcx, rax; this
0x18004493a  call    ?EventWriteWebReleaseLock@ConnectedStorage@@YAXQEBG0III@Z; ConnectedStorage::EventWriteWebReleaseLock(ushort const * const,ushort const * const,uint,uint,uint)
0x18004493f  mov     edx, 1
0x180044944  mov     rbx, [rsp+238h+var_1C0]
0x180044949  mov     rcx, rbx
0x18004494c  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x180044951  nop
0x180044952  mov     rcx, [rsp+238h+lpCriticalSection]; lpCriticalSection
0x18004495a  call    cs:__imp_EnterCriticalSection
0x180044960  nop
0x180044961  mov     rcx, [rsp+238h+var_1A0]; lpCriticalSection
0x180044969  call    cs:__imp_LeaveCriticalSection
0x18004496f  nop
0x180044970  mov     rcx, rdi; this
0x180044973  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180044978  nop
0x180044979  mov     rcx, rbx
0x18004497c  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180044981  mov     rcx, [rsp+238h+var_38]
0x180044989  xor     rcx, rsp; StackCookie
0x18004498c  call    __security_check_cookie
0x180044991  mov     rbx, [rsp+238h+arg_18]
0x180044999  add     rsp, 210h
0x1800449a0  pop     r15
0x1800449a2  pop     r14
0x1800449a4  pop     r12
0x1800449a6  pop     rdi
0x1800449a7  pop     rsi
0x1800449a8  retn
```
