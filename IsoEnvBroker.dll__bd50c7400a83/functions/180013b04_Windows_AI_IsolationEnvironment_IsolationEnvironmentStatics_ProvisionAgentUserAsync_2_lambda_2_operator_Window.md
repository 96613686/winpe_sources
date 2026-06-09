# _Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_2_::_lambda_2_::operator()_Windows::Internal::CMarshaledInterfaceResult_Windows::AI::IsolationEnvironment::IIsolationProvisionResult___

- ea: `0x180013b04`
- end: `0x180013f30`
- name: `_Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_2_::_lambda_2_::operator()_Windows::Internal::CMarshaledInterfaceResult_Windows::AI::IsolationEnvironment::IIsolationProvisionResult___`
- size: `1068`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029790`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x1800134e8`
- `0x180013b04`
- `0x1800142c4`
- `0x180020d48`
- `0x1800219dc`
- `0x1800297e8`
- `0x180037064`
- `0x18003783c`
- `0x18003c1c0`
- `0x18003c420`
- `0x180043484`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013cad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013d8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013ee2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013cad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013d8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013ee2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013bdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013cd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013dae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013f05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013bdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013cd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013dae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013f05`

## string_xrefs

- `0x180013de6`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180013e52`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x180013c34`: `Failed to allocate AgentUser. hr: %#x`
- `0x180013d12`: `Failed to add client process to AgentUser. hr: %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_2_::_lambda_2_::operator()_Windows::Internal::CMarshaledInterfaceResult_Windows::AI::IsolationEnvironment::IIsolationProvisionResult___(
        __int64 a1,
        __int64 a2)
{
  HANDLE v4; // rbx
  __int64 *v5; // rdi
  int DoesUserConsentToProvisionAgentUsers_NoLock; // eax
  __int64 v7; // rcx
  unsigned int v8; // edi
  int AgentUser; // eax
  unsigned int v11; // esi
  unsigned int v12; // r14d
  volatile signed __int32 *v13; // rsi
  RTL_SRWLOCK *v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // esi
  volatile signed __int32 *v18; // rbx
  RTL_SRWLOCK *v19; // rcx
  int v20; // eax
  int v21; // eax
  volatile signed __int32 *v22; // rsi
  RTL_SRWLOCK *v23; // rcx
  int v24; // [rsp+20h] [rbp-49h]
  __int64 v25; // [rsp+30h] [rbp-39h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-31h] BYREF
  AgentUser *v27[2]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v28; // [rsp+50h] [rbp-19h] BYREF
  __int64 v29; // [rsp+60h] [rbp-9h]
  __int64 v30; // [rsp+68h] [rbp-1h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+7h] BYREF
  _OWORD v32[2]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = *(HANDLE *)a1;
  hObject = *(HANDLE *)a1;
  v30 = a2;
  v32[0] = 0;
  v32[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v32[0]) = 0;
  v28 = 0;
  v29 = 0;
  v5 = (__int64 *)(a1 + 8);
  DoesUserConsentToProvisionAgentUsers_NoLock = AgentAccountHelpers::DoesUserConsentToProvisionAgentUsers_NoLock(
                                                  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL) + 16LL,
                                                  (_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 112LL)
                                                           + 168LL
                                                           + (-(__int64)(**(_BYTE **)(*(_QWORD *)(a1 + 8) + 112LL) != 0)
                                                            & 0xFFFFFFFFFFFFFFA0uLL)),
                                                  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 112LL) + 104LL,
                                                  *(_QWORD *)(a1 + 56),
                                                  (struct winrt::impl::shared_hstring_header ***)(a1 + 64),
                                                  (char ***)&v28);
  if ( DoesUserConsentToProvisionAgentUsers_NoLock < 0 )
  {
    v8 = _Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_2_::_lambda_2_::operator()_Windows::Internal::CMarshaledInterfaceResult_Windows::AI::IsolationEnvironment::IIsolationProvisionResult____::_2_::_lambda_1_::operator()(
           &v30,
           (unsigned int)DoesUserConsentToProvisionAgentUsers_NoLock,
           4,
           &v28);
    std::vector<std::wstring>::~vector<std::wstring>((__int64)&v28);
    std::wstring::~wstring((char **)v32);
    if ( v4 )
      CloseHandle(v4);
    return v8;
  }
  checked_srwlock::lock_exclusive(v7, &SRWLock);
  *(_OWORD *)v27 = 0;
  if ( (int)AgentManager::FindActiveAgentUserByProvisionId(*v5, a1 + 24, v27) < 0 )
  {
    AgentUser = AgentManager::AllocateAgentUser(v5, v32, (_QWORD *)(a1 + 24), v27);
    v11 = AgentUser;
    if ( AgentUser < 0 )
    {
      Log(2u, L"Failed to allocate AgentUser. hr: %#x", (unsigned int)AgentUser);
      v12 = _Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_2_::_lambda_2_::operator()_Windows::Internal::CMarshaledInterfaceResult_Windows::AI::IsolationEnvironment::IIsolationProvisionResult____::_2_::_lambda_1_::operator()(
              &v30,
              v11,
              1,
              &v28);
      v13 = (volatile signed __int32 *)v27[1];
      if ( v27[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v27[1] + 2, 0xFFFFFFFF) == 1 )
        goto LABEL_9;
      goto LABEL_11;
    }
  }
  if ( !AgentUser::ContainsActiveClientConnection(v27[0], v4, (const WCHAR *)*v5) )
  {
    v15 = AgentUser::AddClientProcess(v27[0], &hObject, v5);
    v16 = v15;
    if ( v15 < 0 )
    {
      Log(2u, L"Failed to add client process to AgentUser. hr: %#x", (unsigned int)v15);
      v17 = _Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_2_::_lambda_2_::operator()_Windows::Internal::CMarshaledInterfaceResult_Windows::AI::IsolationEnvironment::IIsolationProvisionResult____::_2_::_lambda_1_::operator()(
              &v30,
              v16,
              1,
              &v28);
      v18 = (volatile signed __int32 *)v27[1];
      if ( v27[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      v19 = SRWLock;
      if ( SRWLock )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v19);
      }
      std::vector<std::wstring>::~vector<std::wstring>((__int64)&v28);
      std::wstring::~wstring((char **)v32);
      if ( hObject )
        CloseHandle(hObject);
      return v17;
    }
    v4 = hObject;
  }
  v25 = 0;
  v20 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::ProvisionResult,Windows::AI::IsolationEnvironment::IIsolationProvisionResult,std::shared_ptr<AgentUser> &,std::vector<std::wstring> &>(
          &v25,
          (__int64)v27,
          (__int64)&v28);
  v12 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v20,
      v24);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    goto LABEL_31;
  }
  v21 = Windows::Internal::CMarshaledInterfaceResult<Windows::AI::IsolationEnvironment::IIsolationProvisionResult>::Set(
          a2,
          v25);
  v12 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v21,
      v24);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_31:
    v13 = (volatile signed __int32 *)v27[1];
    if ( v27[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v27[1] + 2, 0xFFFFFFFF) == 1 )
    {
LABEL_9:
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
LABEL_11:
    v14 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v14);
    }
    std::vector<std::wstring>::~vector<std::wstring>((__int64)&v28);
    std::wstring::~wstring((char **)v32);
    if ( v4 )
      CloseHandle(v4);
    return v12;
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v22 = (volatile signed __int32 *)v27[1];
  if ( v27[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  v23 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v23);
  }
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v28);
  std::wstring::~wstring((char **)v32);
  if ( v4 )
    CloseHandle(v4);
  return 0;
}

```

## disassembly

```asm
0x180013b04  mov     [rsp-8+arg_10], rbx
0x180013b09  push    rbp
0x180013b0a  push    rsi
0x180013b0b  push    rdi
0x180013b0c  push    r14
0x180013b0e  push    r15
0x180013b10  lea     rbp, [rsp-37h]
0x180013b15  sub     rsp, 0A0h
0x180013b1c  mov     rax, cs:__security_cookie
0x180013b23  xor     rax, rsp
0x180013b26  mov     [rbp+57h+var_28], rax
0x180013b2a  mov     r15, rdx
0x180013b2d  mov     rsi, rcx
0x180013b30  mov     rbx, [rcx]
0x180013b33  mov     [rbp+57h+hObject], rbx
0x180013b37  mov     [rbp+57h+var_58], rdx
0x180013b3b  xorps   xmm0, xmm0
0x180013b3e  movups  [rbp+57h+var_48], xmm0
0x180013b42  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180013b4a  movdqu  [rbp+57h+var_38], xmm1
0x180013b4f  xor     eax, eax
0x180013b51  mov     word ptr [rbp+57h+var_48], ax
0x180013b55  movdqu  [rbp+57h+var_70], xmm0
0x180013b5a  mov     [rbp+57h+var_60], rax
0x180013b5e  lea     rdi, [rcx+8]
0x180013b62  mov     r9, [rdi]
0x180013b65  mov     rcx, [r9+70h]
0x180013b69  lea     r10, [rsi+40h]
0x180013b6d  lea     r8, [rcx+68h]
0x180013b71  mov     al, [rcx]
0x180013b73  neg     al
0x180013b75  sbb     rdx, rdx
0x180013b78  and     rdx, 0FFFFFFFFFFFFFFA0h
0x180013b7c  add     rcx, 0A8h
0x180013b83  add     rdx, rcx
0x180013b86  mov     rcx, [r9+28h]
0x180013b8a  add     rcx, 10h
0x180013b8e  lea     rax, [rbp+57h+var_70]
0x180013b92  mov     [rsp+0C0h+var_98], rax
0x180013b97  mov     qword ptr [rsp+0C0h+var_A0], r10; int
0x180013b9c  mov     r9, [rsi+38h]
0x180013ba0  call    ?DoesUserConsentToProvisionAgentUsers_NoLock@AgentAccountHelpers@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00UWindowId@UI@Windows@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@AEAV73@@Z; AgentAccountHelpers::DoesUserConsentToProvisionAgentUsers_NoLock(std::wstring const &,std::wstring const &,std::wstring const &,Windows::UI::WindowId,std::vector<std::wstring> const &,std::vector<std::wstring> &)
0x180013ba5  test    eax, eax
0x180013ba7  jns     short loc_180013BE9
0x180013ba9  lea     r9, [rbp+57h+var_70]
0x180013bad  mov     r8d, 4
0x180013bb3  mov     edx, eax
0x180013bb5  lea     rcx, [rbp+57h+var_58]
0x180013bb9  call    __Windows__AI__IsolationEnvironment__IsolationEnvironmentStatics__ProvisionAgentUserAsync____2____lambda_2___operator___Windows__Internal__CMarshaledInterfaceResult_Windows__AI__IsolationEnvironment__IIsolationProvisionResult_______2____lambda_1___operator__
0x180013bbe  mov     edi, eax
0x180013bc0  lea     rcx, [rbp+57h+var_70]
0x180013bc4  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180013bc9  nop
0x180013bca  lea     rcx, [rbp+57h+var_48]
0x180013bce  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013bd3  nop
0x180013bd4  test    rbx, rbx
0x180013bd7  jz      short loc_180013BE2
0x180013bd9  mov     rcx, rbx; hObject
0x180013bdc  call    cs:__imp_CloseHandle
0x180013be2  mov     eax, edi
0x180013be4  jmp     loc_180013F0D
0x180013be9  lea     rdx, [rbp+57h+SRWLock]
0x180013bed  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180013bf2  nop
0x180013bf3  xorps   xmm0, xmm0
0x180013bf6  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180013bfb  lea     r8, [rbp+57h+var_80]
0x180013bff  lea     rdx, [rsi+18h]
0x180013c03  mov     rcx, [rdi]
0x180013c06  call    ?FindActiveAgentUserByProvisionId@AgentManager@@SAJPEBVClientIdentity@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VAgentUser@@@4@@Z; AgentManager::FindActiveAgentUserByProvisionId(ClientIdentity const *,std::wstring const &,std::shared_ptr<AgentUser> &)
0x180013c0b  test    eax, eax
0x180013c0d  jns     loc_180013CDE
0x180013c13  lea     r9, [rbp+57h+var_80]
0x180013c17  lea     r8, [rsi+18h]
0x180013c1b  lea     rdx, [rbp+57h+var_48]
0x180013c1f  mov     rcx, rdi
0x180013c22  call    ?AllocateAgentUser@AgentManager@@SAJAEBV?$shared_ptr@VClientIdentity@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@1AEAV?$shared_ptr@VAgentUser@@@3@@Z; AgentManager::AllocateAgentUser(std::shared_ptr<ClientIdentity> const &,std::wstring const &,std::wstring const &,std::shared_ptr<AgentUser> &)
0x180013c27  mov     esi, eax
0x180013c29  test    eax, eax
0x180013c2b  jns     loc_180013CDE
0x180013c31  mov     r8d, eax
0x180013c34  lea     rdx, aFailedToAlloca; "Failed to allocate AgentUser. hr: %#x"
0x180013c3b  mov     ecx, 2; unsigned __int8
0x180013c40  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180013c45  lea     r9, [rbp+57h+var_70]
0x180013c49  mov     r8d, 1
0x180013c4f  mov     edx, esi
0x180013c51  lea     rcx, [rbp+57h+var_58]
0x180013c55  call    __Windows__AI__IsolationEnvironment__IsolationEnvironmentStatics__ProvisionAgentUserAsync____2____lambda_2___operator___Windows__Internal__CMarshaledInterfaceResult_Windows__AI__IsolationEnvironment__IIsolationProvisionResult_______2____lambda_1___operator__
0x180013c5a  mov     r14d, eax
0x180013c5d  mov     rsi, [rbp+57h+var_80+8]
0x180013c61  test    rsi, rsi
0x180013c64  jz      short loc_180013C9D
0x180013c66  or      edi, 0FFFFFFFFh
0x180013c69  mov     ecx, edi
0x180013c6b  lock xadd [rsi+8], ecx
0x180013c70  add     ecx, edi
0x180013c72  jnz     short loc_180013C9D
0x180013c74  mov     rdx, [rsi]
0x180013c77  mov     rax, [rdx]
0x180013c7a  mov     rcx, rsi
0x180013c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c82  mov     eax, edi
0x180013c84  lock xadd [rsi+0Ch], eax
0x180013c89  add     eax, edi
0x180013c8b  jnz     short loc_180013C9D
0x180013c8d  mov     rax, [rsi]
0x180013c90  mov     rcx, rsi
0x180013c93  mov     rax, [rax+8]
0x180013c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c9c  nop
0x180013c9d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180013ca1  test    rcx, rcx
0x180013ca4  jz      short loc_180013CB4
0x180013ca6  mov     dword ptr [rcx+8], 0
0x180013cad  call    cs:__imp_ReleaseSRWLockExclusive
0x180013cb3  nop
0x180013cb4  lea     rcx, [rbp+57h+var_70]
0x180013cb8  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180013cbd  nop
0x180013cbe  lea     rcx, [rbp+57h+var_48]
0x180013cc2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013cc7  nop
0x180013cc8  test    rbx, rbx
0x180013ccb  jz      short loc_180013CD6
0x180013ccd  mov     rcx, rbx; hObject
0x180013cd0  call    cs:__imp_CloseHandle
0x180013cd6  mov     eax, r14d
0x180013cd9  jmp     loc_180013F0D
0x180013cde  mov     r8, [rdi]; struct ClientIdentity *
0x180013ce1  mov     rdx, rbx; void *
0x180013ce4  mov     rcx, [rbp+57h+var_80]; this
0x180013ce8  call    ?ContainsActiveClientConnection@AgentUser@@QEBA_NPEAXPEAVClientIdentity@@@Z; AgentUser::ContainsActiveClientConnection(void *,ClientIdentity *)
0x180013ced  test    al, al
0x180013cef  jnz     loc_180013DBF
0x180013cf5  mov     r8, rdi
0x180013cf8  lea     rdx, [rbp+57h+hObject]
0x180013cfc  mov     rcx, [rbp+57h+var_80]
0x180013d00  call    ?AddClientProcess@AgentUser@@QEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$shared_ptr@VClientIdentity@@@std@@@Z; AgentUser::AddClientProcess(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,std::shared_ptr<ClientIdentity> const &)
0x180013d05  mov     ebx, eax
0x180013d07  test    eax, eax
0x180013d09  jns     loc_180013DBB
0x180013d0f  mov     r8d, eax
0x180013d12  lea     rdx, aFailedToAddCli; "Failed to add client process to AgentUs"...
0x180013d19  mov     ecx, 2; unsigned __int8
0x180013d1e  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180013d23  lea     r9, [rbp+57h+var_70]
0x180013d27  mov     r8d, 1
0x180013d2d  mov     edx, ebx
0x180013d2f  lea     rcx, [rbp+57h+var_58]
0x180013d33  call    __Windows__AI__IsolationEnvironment__IsolationEnvironmentStatics__ProvisionAgentUserAsync____2____lambda_2___operator___Windows__Internal__CMarshaledInterfaceResult_Windows__AI__IsolationEnvironment__IIsolationProvisionResult_______2____lambda_1___operator__
0x180013d38  mov     esi, eax
0x180013d3a  mov     rbx, [rbp+57h+var_80+8]
0x180013d3e  test    rbx, rbx
0x180013d41  jz      short loc_180013D7A
0x180013d43  or      edi, 0FFFFFFFFh
0x180013d46  mov     ecx, edi
0x180013d48  lock xadd [rbx+8], ecx
0x180013d4d  add     ecx, edi
0x180013d4f  jnz     short loc_180013D7A
0x180013d51  mov     rdx, [rbx]
0x180013d54  mov     rcx, rbx
0x180013d57  mov     rax, [rdx]
0x180013d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d5f  mov     eax, edi
0x180013d61  lock xadd [rbx+0Ch], eax
0x180013d66  add     eax, edi
0x180013d68  jnz     short loc_180013D7A
0x180013d6a  mov     rax, [rbx]
0x180013d6d  mov     rcx, rbx
0x180013d70  mov     rax, [rax+8]
0x180013d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d79  nop
0x180013d7a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180013d7e  test    rcx, rcx
0x180013d81  jz      short loc_180013D91
0x180013d83  mov     dword ptr [rcx+8], 0
0x180013d8a  call    cs:__imp_ReleaseSRWLockExclusive
0x180013d90  nop
0x180013d91  lea     rcx, [rbp+57h+var_70]
0x180013d95  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180013d9a  nop
0x180013d9b  lea     rcx, [rbp+57h+var_48]
0x180013d9f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013da4  nop
0x180013da5  mov     rcx, [rbp+57h+hObject]; hObject
0x180013da9  test    rcx, rcx
0x180013dac  jz      short loc_180013DB4
0x180013dae  call    cs:__imp_CloseHandle
0x180013db4  mov     eax, esi
0x180013db6  jmp     loc_180013F0D
0x180013dbb  mov     rbx, [rbp+57h+hObject]
0x180013dbf  mov     [rbp+57h+var_90], 0
0x180013dc7  lea     r8, [rbp+57h+var_70]
0x180013dcb  lea     rdx, [rbp+57h+var_80]
0x180013dcf  lea     rcx, [rbp+57h+var_90]
0x180013dd3  call    ??$MakeAndInitialize@VProvisionResult@IsolationEnvironment@AI@Windows@@UIIsolationProvisionResult@234@AEAV?$shared_ptr@VAgentUser@@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@7@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationProvisionResult@IsolationEnvironment@AI@Windows@@AEAV?$shared_ptr@VAgentUser@@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@8@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::ProvisionResult,Windows::AI::IsolationEnvironment::IIsolationProvisionResult,std::shared_ptr<AgentUser> &,std::vector<std::wstring> &>(Windows::AI::IsolationEnvironment::IIsolationProvisionResult * *,std::shared_ptr<AgentUser> &,std::vector<std::wstring> &)
0x180013dd8  mov     r14d, eax
0x180013ddb  test    eax, eax
0x180013ddd  jns     short loc_180013E38
0x180013ddf  mov     rcx, [rbp+5Fh]; this
0x180013de3  mov     r9d, eax; char *
0x180013de6  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180013ded  mov     edx, 244h; void *
0x180013df2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013df7  nop
0x180013df8  mov     rcx, [rbp+57h+var_90]
0x180013dfc  test    rcx, rcx
0x180013dff  jz      short loc_180013E0E
0x180013e01  mov     rax, [rcx]
0x180013e04  mov     rax, [rax+10h]
0x180013e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e0d  nop
0x180013e0e  mov     rsi, [rbp+57h+var_80+8]
0x180013e12  test    rsi, rsi
0x180013e15  jz      loc_180013C9D
0x180013e1b  or      edi, 0FFFFFFFFh
0x180013e1e  mov     eax, edi
0x180013e20  lock xadd [rsi+8], eax
0x180013e25  add     eax, edi
0x180013e27  jnz     loc_180013C9D
0x180013e2d  mov     rax, [rsi]
0x180013e30  mov     rax, [rax]
0x180013e33  jmp     loc_180013C7A
0x180013e38  mov     rdx, [rbp+57h+var_90]
0x180013e3c  mov     rcx, r15
0x180013e3f  call    ?Set@?$CMarshaledInterfaceResult@UIIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Internal@Windows@@QEAAJPEAUIIsolationProvisionResult@IsolationEnvironment@AI@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::AI::IsolationEnvironment::IIsolationProvisionResult>::Set(Windows::AI::IsolationEnvironment::IIsolationProvisionResult *)
0x180013e44  mov     r14d, eax
0x180013e47  test    eax, eax
0x180013e49  jns     short loc_180013E7C
0x180013e4b  mov     rcx, [rbp+5Fh]; this
0x180013e4f  mov     r9d, eax; char *
0x180013e52  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180013e59  mov     edx, 246h; void *
0x180013e5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e63  nop
0x180013e64  mov     rcx, [rbp+57h+var_90]
0x180013e68  test    rcx, rcx
0x180013e6b  jz      short loc_180013E7A
0x180013e6d  mov     rax, [rcx]
0x180013e70  mov     rax, [rax+10h]
0x180013e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e79  nop
0x180013e7a  jmp     short loc_180013E0E
0x180013e7c  mov     rcx, [rbp+57h+var_90]
0x180013e80  test    rcx, rcx
0x180013e83  jz      short loc_180013E92
0x180013e85  mov     rax, [rcx]
0x180013e88  mov     rax, [rax+10h]
0x180013e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e91  nop
0x180013e92  mov     rsi, [rbp+57h+var_80+8]
0x180013e96  test    rsi, rsi
0x180013e99  jz      short loc_180013ED2
0x180013e9b  or      edi, 0FFFFFFFFh
0x180013e9e  mov     eax, edi
0x180013ea0  lock xadd [rsi+8], eax
0x180013ea5  add     eax, edi
0x180013ea7  jnz     short loc_180013ED2
0x180013ea9  mov     rax, [rsi]
0x180013eac  mov     rcx, rsi
0x180013eaf  mov     rax, [rax]
0x180013eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eb7  mov     eax, edi
0x180013eb9  lock xadd [rsi+0Ch], eax
0x180013ebe  add     eax, edi
0x180013ec0  jnz     short loc_180013ED2
0x180013ec2  mov     rax, [rsi]
0x180013ec5  mov     rcx, rsi
0x180013ec8  mov     rax, [rax+8]
0x180013ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ed1  nop
0x180013ed2  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180013ed6  test    rcx, rcx
0x180013ed9  jz      short loc_180013EE9
0x180013edb  mov     dword ptr [rcx+8], 0
0x180013ee2  call    cs:__imp_ReleaseSRWLockExclusive
0x180013ee8  nop
0x180013ee9  lea     rcx, [rbp+57h+var_70]
0x180013eed  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180013ef2  nop
0x180013ef3  lea     rcx, [rbp+57h+var_48]
0x180013ef7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013efc  nop
0x180013efd  test    rbx, rbx
0x180013f00  jz      short loc_180013F0B
0x180013f02  mov     rcx, rbx; hObject
0x180013f05  call    cs:__imp_CloseHandle
0x180013f0b  xor     eax, eax
0x180013f0d  mov     rcx, [rbp+57h+var_28]
0x180013f11  xor     rcx, rsp; StackCookie
0x180013f14  call    __security_check_cookie
0x180013f19  mov     rbx, [rsp+0C0h+arg_10]
0x180013f21  add     rsp, 0A0h
0x180013f28  pop     r15
0x180013f2a  pop     r14
0x180013f2c  pop     rdi
0x180013f2d  pop     rsi
0x180013f2e  pop     rbp
  ... truncated ...
```
