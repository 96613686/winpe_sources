# ConnectedStorage::ListAllContainersOperation::SubmitRequest(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004510c`
- end: `0x180045528`
- name: `?SubmitRequest@ListAllContainersOperation@ConnectedStorage@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1052`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800432b0`
- `0x18004389c`

## callees

- `0x180003c70`
- `0x18000c218`
- `0x18000cd1c`
- `0x18000d2b8`
- `0x18000d6bc`
- `0x180011c68`
- `0x1800190f0`
- `0x180019128`
- `0x18001c090`
- `0x18001ca40`
- `0x1800296a4`
- `0x18002e420`
- `0x180039348`
- `0x18003a228`
- `0x18003c068`
- `0x18003c420`
- `0x18003ee9c`
- `0x18003f174`
- `0x1800434d4`
- `0x180043580`
- `0x180043d14`
- `0x18004510c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045478`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800454dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045478`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800454dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004538b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004538b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045213`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045213`

## string_xrefs

- `0x180045177`: `continuationToken=`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall ConnectedStorage::ListAllContainersOperation::SubmitRequest(__int64 a1, __int64 a2)
{
  __int64 *v4; // rax
  __int64 v5; // rcx
  volatile signed __int32 *v6; // rdi
  ULONGLONG TickCount64; // rax
  char *v8; // r8
  ULONGLONG v9; // rbx
  __int64 *v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r15
  void (__fastcall *v13)(__int64, _BYTE *, HSTRING *, __int64, int, __int16, HSTRING *, __int64 *, _BYTE *); // r12
  __int64 v14; // r14
  HSTRING *v15; // rbx
  HSTRING *v16; // rax
  char *v17; // r8
  LPCRITICAL_SECTION v18; // rbx
  __int64 v19; // rdi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  std::_Ref_count_base *v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int16 v28; // [rsp+28h] [rbp-1B0h]
  __int64 v29; // [rsp+50h] [rbp-188h] BYREF
  __int64 *v30; // [rsp+58h] [rbp-180h] BYREF
  std::_Ref_count_base *v31; // [rsp+60h] [rbp-178h]
  __int128 v32; // [rsp+68h] [rbp-170h] BYREF
  HSTRING string; // [rsp+78h] [rbp-160h] BYREF
  HSTRING v34; // [rsp+80h] [rbp-158h] BYREF
  __int64 v35; // [rsp+88h] [rbp-150h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+90h] [rbp-148h] BYREF
  ULONGLONG v37; // [rsp+A0h] [rbp-138h]
  __int64 v38; // [rsp+A8h] [rbp-130h]
  LPCRITICAL_SECTION v39[2]; // [rsp+B0h] [rbp-128h] BYREF
  _QWORD v40[4]; // [rsp+C0h] [rbp-118h] BYREF
  unsigned __int16 Src[16]; // [rsp+E0h] [rbp-F8h] BYREF
  HSTRING__ v42[8]; // [rsp+100h] [rbp-D8h] BYREF
  _BYTE v43[56]; // [rsp+120h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+158h] [rbp-80h]
  _BYTE v45[16]; // [rsp+160h] [rbp-78h] BYREF
  _DWORD v46[16]; // [rsp+170h] [rbp-68h] BYREF

  v38 = a1;
  std::wstring::wstring(Src, a1 + 96);
  if ( *(_QWORD *)(a2 + 16) )
  {
    std::wstring::push_back(Src, *(unsigned __int16 *)(a1 + 128));
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Append<unsigned short>(Src);
  }
  v39[0] = (LPCRITICAL_SECTION)(a1 + 8);
  v4 = (__int64 *)std::enable_shared_from_this<ConnectedStorage::NtmOperation>::shared_from_this(a1 + 8, &v30);
  v5 = *v4;
  v6 = (volatile signed __int32 *)v4[1];
  *v4 = 0;
  v4[1] = 0;
  v32 = 0;
  if ( v6 )
  {
    *(_QWORD *)&v32 = v5;
    *((_QWORD *)&v32 + 1) = v6;
    _InterlockedIncrement(v6 + 3);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
  }
  else
  {
    v6 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  }
  if ( v31 )
    std::_Ref_count_base::_Decref(v31);
  TickCount64 = GetTickCount64();
  v9 = TickCount64;
  v10 = (__int64 *)(a1 + 24);
  lpCriticalSection[0] = (LPCRITICAL_SECTION)(a1 + 24);
  v11 = *(_QWORD *)(a1 + 24);
  if ( !*(_QWORD *)(v11 + 88) )
  {
    ConnectedStorage::Mutex::Unlock::Unlock(
      (ConnectedStorage::Mutex::Unlock *)v39,
      (struct ConnectedStorage::Mutex *)(v11 + 40),
      v8);
    v24 = *v10;
    v25 = std::enable_shared_from_this<ConnectedStorage::NtmOperation>::shared_from_this(a1 + 8, &v30);
    ConnectedStorage::NtmWebService::OperationCompleted(v24, v25);
    v26 = std::make_shared<std::vector<ConnectedStorage::ContainerInfo>,>(&v30);
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,std::shared_ptr<std::vector<ConnectedStorage::ContainerInfo>>>::operator()(
      a1 + 32,
      1,
      v26);
    EnterCriticalSection(v39[0]);
    goto LABEL_20;
  }
  v37 = TickCount64;
  Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(&v35);
  try
  {
    ConnectedStorage::NtmWebService::MakeHeadersWithContext(*v10, v42, Src, (HSTRING *)(a1 + 136));
    v12 = *(_QWORD *)(*v10 + 88);
    v13 = *(void (__fastcall **)(__int64, _BYTE *, HSTRING *, __int64, int, __int16, HSTRING *, __int64 *, _BYTE *))(*(_QWORD *)v12 + 8LL);
    std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(v40, &v32);
    v14 = v35;
    v40[2] = v35;
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
    v40[3] = v9;
    v44 = 0;
    v44 = std::_Func_impl_no_alloc<_lambda_d5f22529f4a3b4cb3792412671b43b67_,void,_NTM_TRANSFER_STATUS const &,unsigned int,long>::_Func_impl_no_alloc<_lambda_d5f22529f4a3b4cb3792412671b43b67_,void,_NTM_TRANSFER_STATUS const &,unsigned int,long>(
            v43,
            v40);
    v30 = &v29;
    v29 = v14;
    Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&v29);
    v15 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v34, (__int64)v42);
    v16 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, (__int64)Src);
    v28 = 30;
    v13(v12, v45, v16, 66, 1, v28, v15, &v29, v43);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v34);
    v34 = 0;
    std::function<long (void)>::~function<long (void)>(v43);
    _lambda_d5f22529f4a3b4cb3792412671b43b67_::~_lambda_d5f22529f4a3b4cb3792412671b43b67_((_lambda_d5f22529f4a3b4cb3792412671b43b67_ *)v40);
    std::wstring::_Tidy_deallocate(v42);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  catch ( ConnectedStorage::ComError v46 )
  {
    LODWORD(v29) = v46[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v46);
    if ( (int)v29 < 0 )
    {
LABEL_17:
      v18 = lpCriticalSection[0];
      ConnectedStorage::Mutex::Unlock::Unlock(
        (ConnectedStorage::Mutex::Unlock *)lpCriticalSection,
        (struct ConnectedStorage::Mutex *)&lpCriticalSection[0]->DebugInfo->Flags,
        v17);
      v19 = v38;
      ConnectedStorage::ListAllContainersOperation::LogCompletion(v38, 0, 0, v37, v29);
      DebugInfo = v18->DebugInfo;
      v21 = std::enable_shared_from_this<ConnectedStorage::NtmOperation>::shared_from_this(v39[0], &v30);
      ConnectedStorage::NtmWebService::OperationCompleted(DebugInfo, v21);
      v22 = std::make_shared<std::vector<ConnectedStorage::ContainerInfo>,>(&v30);
      std::_Func_class<void,enum ConnectedStorage::WebService::Status,std::shared_ptr<std::vector<ConnectedStorage::ContainerInfo>>>::operator()(
        v19 + 32,
        1,
        v22);
      EnterCriticalSection(lpCriticalSection[0]);
      v23 = (std::_Ref_count_base *)*((_QWORD *)&v32 + 1);
      if ( *((_QWORD *)&v32 + 1) )
        goto LABEL_22;
      return std::wstring::_Tidy_deallocate(Src);
    }
    v6 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v29) = -2147024882;
    goto LABEL_17;
  }
  catch ( ... )
  {
    LODWORD(v29) = -2147467259;
    goto LABEL_17;
  }
LABEL_20:
  if ( v6 )
  {
    v23 = (std::_Ref_count_base *)v6;
LABEL_22:
    std::_Ref_count_base::_Decwref(v23);
  }
  return std::wstring::_Tidy_deallocate(Src);
}

```

## disassembly

```asm
0x18004510c  mov     [rsp+arg_10], rbx
0x180045111  mov     [rsp+arg_18], rdi
0x180045116  push    r12
0x180045118  push    r14
0x18004511a  push    r15
0x18004511c  sub     rsp, 1C0h
0x180045123  mov     rax, cs:__security_cookie
0x18004512a  xor     rax, rsp
0x18004512d  mov     [rsp+1D8h+var_28], rax
0x180045135  mov     rbx, rdx
0x180045138  mov     r14, rcx
0x18004513b  mov     [rsp+1D8h+var_130], rcx
0x180045143  lea     rdx, [rcx+60h]
0x180045147  lea     rcx, [rsp+1D8h+Src]
0x18004514f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180045154  nop
0x180045155  cmp     qword ptr [rbx+10h], 0
0x18004515a  jz      short loc_1800451A9
0x18004515c  movzx   edx, word ptr [r14+80h]
0x180045164  lea     rcx, [rsp+1D8h+Src]
0x18004516c  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180045171  mov     r8d, 12h
0x180045177  lea     rdx, aContinuationto_1; "continuationToken="
0x18004517e  lea     rcx, [rsp+1D8h+Src]; Src
0x180045186  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004518b  mov     r8, [rbx+10h]
0x18004518f  cmp     qword ptr [rbx+18h], 7
0x180045194  jbe     short loc_180045199
0x180045196  mov     rbx, [rbx]
0x180045199  mov     rdx, rbx
0x18004519c  lea     rcx, [rsp+1D8h+Src]; Src
0x1800451a4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800451a9  lea     r12, [r14+8]
0x1800451ad  mov     [rsp+1D8h+var_128], r12
0x1800451b5  lea     rdx, [rsp+1D8h+var_180]
0x1800451ba  mov     rcx, r12
0x1800451bd  call    ?shared_from_this@?$enable_shared_from_this@VNtmOperation@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@$$CBVNtmOperation@ConnectedStorage@@@2@XZ; std::enable_shared_from_this<ConnectedStorage::NtmOperation>::shared_from_this(void)
0x1800451c2  mov     rcx, [rax]
0x1800451c5  mov     rdi, [rax+8]
0x1800451c9  mov     qword ptr [rax], 0
0x1800451d0  mov     qword ptr [rax+8], 0
0x1800451d8  xorps   xmm0, xmm0
0x1800451db  movdqu  [rsp+1D8h+var_170], xmm0
0x1800451e1  test    rdi, rdi
0x1800451e4  jz      short loc_1800451FE
0x1800451e6  mov     qword ptr [rsp+1D8h+var_170], rcx
0x1800451eb  mov     qword ptr [rsp+1D8h+var_170+8], rdi
0x1800451f0  lock inc dword ptr [rdi+0Ch]
0x1800451f4  mov     rcx, rdi; this
0x1800451f7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800451fc  jmp     short loc_180045203
0x1800451fe  mov     rdi, qword ptr [rsp+1D8h+var_170+8]
0x180045203  mov     rcx, [rsp+1D8h+var_178]; this
0x180045208  test    rcx, rcx
0x18004520b  jz      short loc_180045213
0x18004520d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180045212  nop
0x180045213  call    cs:__imp_GetTickCount64
0x180045219  mov     rbx, rax
0x18004521c  lea     r15, [r14+18h]
0x180045220  mov     [rsp+1D8h+lpCriticalSection], r15
0x180045228  mov     rdx, [r15]
0x18004522b  cmp     qword ptr [rdx+58h], 0
0x180045230  jz      loc_18004548B
0x180045236  mov     [rsp+1D8h+var_138], rax
0x18004523e  lea     rcx, [rsp+1D8h+var_150]
0x180045246  call    ??$Make@VStringStream@ConnectedStorage@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VStringStream@ConnectedStorage@@@12@XZ; Microsoft::WRL::Details::Make<ConnectedStorage::StringStream,>(void)
0x18004524b  nop
0x18004524c  lea     r9, [r14+88h]
0x180045253  lea     r8, [rsp+1D8h+Src]
0x18004525b  lea     rdx, [rsp+1D8h+var_D8]
0x180045263  mov     rcx, [r15]
0x180045266  call    ?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z; ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::wstring const &,ConnectedStorage::ContextDesc const &)
0x18004526b  nop
0x18004526c  mov     rax, [r15]
0x18004526f  mov     r15, [rax+58h]
0x180045273  mov     rax, [r15]
0x180045276  mov     r12, [rax+8]
0x18004527a  lea     rdx, [rsp+1D8h+var_170]
0x18004527f  lea     rcx, [rsp+1D8h+var_118]
0x180045287  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x18004528c  mov     r14, [rsp+1D8h+var_150]
0x180045294  mov     [rsp+1D8h+var_108], r14
0x18004529c  test    r14, r14
0x18004529f  jz      short loc_1800452B1
0x1800452a1  mov     rax, [r14]
0x1800452a4  mov     rcx, r14
0x1800452a7  mov     rax, [rax+8]
0x1800452ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452b0  nop
0x1800452b1  mov     [rsp+1D8h+var_100], rbx
0x1800452b9  mov     [rsp+1D8h+var_80], 0
0x1800452c5  lea     rdx, [rsp+1D8h+var_118]
0x1800452cd  lea     rcx, [rsp+1D8h+var_B8]
0x1800452d5  call    ??$?0V_lambda_d5f22529f4a3b4cb3792412671b43b67_@@$0A@@?$_Func_impl_no_alloc@V_lambda_d5f22529f4a3b4cb3792412671b43b67_@@XAEBU_NTM_TRANSFER_STATUS@@IJ@std@@QEAA@$$QEAV_lambda_d5f22529f4a3b4cb3792412671b43b67_@@@Z; std::_Func_impl_no_alloc<_lambda_d5f22529f4a3b4cb3792412671b43b67_,void,_NTM_TRANSFER_STATUS const &,uint,long>::_Func_impl_no_alloc<_lambda_d5f22529f4a3b4cb3792412671b43b67_,void,_NTM_TRANSFER_STATUS const &,uint,long>(_lambda_d5f22529f4a3b4cb3792412671b43b67_ &&)
0x1800452da  mov     [rsp+1D8h+var_80], rax
0x1800452e2  lea     rax, [rsp+1D8h+var_188]
0x1800452e7  mov     [rsp+1D8h+var_180], rax
0x1800452ec  mov     [rsp+1D8h+var_188], r14
0x1800452f1  lea     rcx, [rsp+1D8h+var_188]
0x1800452f6  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x1800452fb  nop
0x1800452fc  lea     rdx, [rsp+1D8h+var_D8]
0x180045304  lea     rcx, [rsp+1D8h+var_158]; string
0x18004530c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180045311  mov     rbx, rax
0x180045314  lea     rdx, [rsp+1D8h+Src]
0x18004531c  lea     rcx, [rsp+1D8h+string]; string
0x180045321  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(std::wstring const &)
0x180045326  nop
0x180045327  lea     rcx, [rsp+1D8h+var_B8]
0x18004532f  mov     [rsp+1D8h+var_198], rcx
0x180045334  lea     rcx, [rsp+1D8h+var_188]
0x180045339  mov     [rsp+1D8h+var_1A0], rcx
0x18004533e  mov     [rsp+1D8h+var_1A8], rbx
0x180045343  mov     [rsp+1D8h+var_1B0], 1Eh
0x18004534a  mov     [rsp+1D8h+var_1B8], 1
0x180045352  mov     r9d, 42h ; 'B'
0x180045358  mov     r8, rax
0x18004535b  lea     rdx, [rsp+1D8h+var_78]
0x180045363  mov     rcx, r15
0x180045366  mov     rax, r12
0x180045369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004536e  nop
0x18004536f  mov     rcx, [rsp+1D8h+string]; string
0x180045374  call    cs:__imp_WindowsDeleteString
0x18004537a  mov     [rsp+1D8h+string], 0
0x180045383  mov     rcx, [rsp+1D8h+var_158]; string
0x18004538b  call    cs:__imp_WindowsDeleteString
0x180045391  mov     [rsp+1D8h+var_158], 0
0x18004539d  lea     rcx, [rsp+1D8h+var_B8]
0x1800453a5  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x1800453aa  nop
0x1800453ab  lea     rcx, [rsp+1D8h+var_118]; this
0x1800453b3  call    ??1_lambda_d5f22529f4a3b4cb3792412671b43b67_@@QEAA@XZ; _lambda_d5f22529f4a3b4cb3792412671b43b67_::~_lambda_d5f22529f4a3b4cb3792412671b43b67_(void)
0x1800453b8  nop
0x1800453b9  lea     rcx, [rsp+1D8h+var_D8]
0x1800453c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800453c6  nop
0x1800453c7  test    r14, r14
0x1800453ca  jz      short loc_1800453DC
0x1800453cc  mov     rax, [r14]
0x1800453cf  mov     rcx, r14
0x1800453d2  mov     rax, [rax+10h]
0x1800453d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453db  nop
0x1800453dc  jmp     loc_1800454E3
0x1800453e1  cmp     dword ptr [rsp+1D8h+var_188], 0
0x1800453e6  jl      short loc_1800453F2
0x1800453e8  mov     rdi, qword ptr [rsp+1D8h+var_170+8]
0x1800453ed  jmp     loc_1800454E3
0x1800453f2  mov     rbx, [rsp+1D8h+lpCriticalSection]
0x1800453fa  mov     rdx, [rbx]
0x1800453fd  add     rdx, 28h ; '('; struct ConnectedStorage::Mutex *
0x180045401  lea     rcx, [rsp+1D8h+lpCriticalSection]; this
0x180045409  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x18004540e  nop
0x18004540f  mov     eax, dword ptr [rsp+1D8h+var_188]
0x180045413  mov     [rsp+1D8h+var_1B8], eax
0x180045417  mov     r9, [rsp+1D8h+var_138]
0x18004541f  xor     r8d, r8d
0x180045422  xor     edx, edx
0x180045424  mov     rdi, [rsp+1D8h+var_130]
0x18004542c  mov     rcx, rdi
0x18004542f  call    ?LogCompletion@ListAllContainersOperation@ConnectedStorage@@AEBAX_NIVTimer@2@J@Z; ConnectedStorage::ListAllContainersOperation::LogCompletion(bool,uint,ConnectedStorage::Timer,long)
0x180045434  mov     rbx, [rbx]
0x180045437  lea     rdx, [rsp+1D8h+var_180]
0x18004543c  mov     rcx, [rsp+1D8h+var_128]
0x180045444  call    ?shared_from_this@?$enable_shared_from_this@VNtmOperation@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@$$CBVNtmOperation@ConnectedStorage@@@2@XZ; std::enable_shared_from_this<ConnectedStorage::NtmOperation>::shared_from_this(void)
0x180045449  mov     rdx, rax
0x18004544c  mov     rcx, rbx
0x18004544f  call    ?OperationCompleted@NtmWebService@ConnectedStorage@@AEBAXV?$shared_ptr@$$CBVNtmOperation@ConnectedStorage@@@std@@@Z; ConnectedStorage::NtmWebService::OperationCompleted(std::shared_ptr<ConnectedStorage::NtmOperation const>)
0x180045454  lea     rcx, [rsp+1D8h+var_180]
0x180045459  call    ??$make_shared@V?$vector@UContainerInfo@ConnectedStorage@@V?$allocator@UContainerInfo@ConnectedStorage@@@std@@@std@@$$V@std@@YA?AV?$shared_ptr@V?$vector@UContainerInfo@ConnectedStorage@@V?$allocator@UContainerInfo@ConnectedStorage@@@std@@@std@@@0@XZ; std::make_shared<std::vector<ConnectedStorage::ContainerInfo>,>(void)
0x18004545e  lea     rcx, [rdi+20h]
0x180045462  mov     r8, rax
0x180045465  mov     edx, 1
0x18004546a  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@V?$shared_ptr@V?$vector@UContainerInfo@ConnectedStorage@@V?$allocator@UContainerInfo@ConnectedStorage@@@std@@@std@@@std@@@std@@QEBAXW4Status@WebService@ConnectedStorage@@V?$shared_ptr@V?$vector@UContainerInfo@ConnectedStorage@@V?$allocator@UContainerInfo@ConnectedStorage@@@std@@@std@@@1@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,std::shared_ptr<std::vector<ConnectedStorage::ContainerInfo>>>::operator()(ConnectedStorage::WebService::Status,std::shared_ptr<std::vector<ConnectedStorage::ContainerInfo>>)
0x18004546f  nop
0x180045470  mov     rcx, [rsp+1D8h+lpCriticalSection]; lpCriticalSection
0x180045478  call    cs:__imp_EnterCriticalSection
0x18004547e  nop
0x18004547f  mov     rcx, qword ptr [rsp+1D8h+var_170+8]
0x180045484  test    rcx, rcx
0x180045487  jz      short loc_1800454F1
0x180045489  jmp     short loc_1800454EB
0x18004548b  add     rdx, 28h ; '('; struct ConnectedStorage::Mutex *
0x18004548f  lea     rcx, [rsp+1D8h+var_128]; this
0x180045497  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x18004549c  nop
0x18004549d  mov     rbx, [r15]
0x1800454a0  lea     rdx, [rsp+1D8h+var_180]
0x1800454a5  mov     rcx, r12
0x1800454a8  call    ?shared_from_this@?$enable_shared_from_this@VNtmOperation@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@$$CBVNtmOperation@ConnectedStorage@@@2@XZ; std::enable_shared_from_this<ConnectedStorage::NtmOperation>::shared_from_this(void)
0x1800454ad  mov     rdx, rax
0x1800454b0  mov     rcx, rbx
0x1800454b3  call    ?OperationCompleted@NtmWebService@ConnectedStorage@@AEBAXV?$shared_ptr@$$CBVNtmOperation@ConnectedStorage@@@std@@@Z; ConnectedStorage::NtmWebService::OperationCompleted(std::shared_ptr<ConnectedStorage::NtmOperation const>)
0x1800454b8  lea     rcx, [rsp+1D8h+var_180]
0x1800454bd  call    ??$make_shared@V?$vector@UContainerInfo@ConnectedStorage@@V?$allocator@UContainerInfo@ConnectedStorage@@@std@@@std@@$$V@std@@YA?AV?$shared_ptr@V?$vector@UContainerInfo@ConnectedStorage@@V?$allocator@UContainerInfo@ConnectedStorage@@@std@@@std@@@0@XZ; std::make_shared<std::vector<ConnectedStorage::ContainerInfo>,>(void)
0x1800454c2  lea     rcx, [r14+20h]
0x1800454c6  mov     r8, rax
0x1800454c9  mov     edx, 1
0x1800454ce  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@V?$shared_ptr@V?$vector@UContainerInfo@ConnectedStorage@@V?$allocator@UContainerInfo@ConnectedStorage@@@std@@@std@@@std@@@std@@QEBAXW4Status@WebService@ConnectedStorage@@V?$shared_ptr@V?$vector@UContainerInfo@ConnectedStorage@@V?$allocator@UContainerInfo@ConnectedStorage@@@std@@@std@@@1@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,std::shared_ptr<std::vector<ConnectedStorage::ContainerInfo>>>::operator()(ConnectedStorage::WebService::Status,std::shared_ptr<std::vector<ConnectedStorage::ContainerInfo>>)
0x1800454d3  nop
0x1800454d4  mov     rcx, [rsp+1D8h+var_128]; lpCriticalSection
0x1800454dc  call    cs:__imp_EnterCriticalSection
0x1800454e2  nop
0x1800454e3  test    rdi, rdi
0x1800454e6  jz      short loc_1800454F1
0x1800454e8  mov     rcx, rdi; this
0x1800454eb  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800454f0  nop
0x1800454f1  lea     rcx, [rsp+1D8h+Src]
0x1800454f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800454fe  mov     rcx, [rsp+1D8h+var_28]
0x180045506  xor     rcx, rsp; StackCookie
0x180045509  call    __security_check_cookie
0x18004550e  lea     r11, [rsp+1D8h+var_18]
0x180045516  mov     rbx, [r11+30h]
0x18004551a  mov     rdi, [r11+38h]
0x18004551e  mov     rsp, r11
0x180045521  pop     r15
0x180045523  pop     r14
0x180045525  pop     r12
0x180045527  retn
```
