# _UpdateAppFromStore_::_3_::_lambda_1_::operator()

- ea: `0x18001174c`
- end: `0x1800119de`
- name: `_UpdateAppFromStore_::_3_::_lambda_1_::operator()`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001af60`

## callees

- `0x1800115c0`
- `0x18001162c`
- `0x180011684`
- `0x1800116e0`
- `0x18001174c`
- `0x180018664`
- `0x18002d1a4`
- `0x180035a50`
- `0x180036d78`
- `0x180036ed8`
- `0x180056119`
- `0x18005616d`
- `0x1800563c8`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011904`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800119a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011904`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800119a5`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800118ea`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800118ea`

## string_xrefs

- `0x180011831`: `PFN:{}, InstallState:{}, PercentComplete:{}, ErrorCode:{}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UpdateAppFromStore_::_3_::_lambda_1_::operator()(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rdx
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  unsigned __int128 v6; // kr00_16
  int v7; // ebx
  int v8; // eax
  __int64 v9; // rax
  const wchar_t *v10; // rax
  unsigned __int64 v11; // rdi
  void *v12; // r14
  int v13; // eax
  HANDLE ProcessHeap; // rax
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  bool v20; // zf
  int v21; // [rsp+30h] [rbp-50h] BYREF
  int v22; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v23; // [rsp+38h] [rbp-48h] BYREF
  int v24; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int128 v25; // [rsp+48h] [rbp-38h]
  double v26; // [rsp+58h] [rbp-28h] BYREF
  const wchar_t *v27; // [rsp+60h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v29[2]; // [rsp+70h] [rbp-10h] BYREF

  v25 = 0;
  v3 = a1[1];
  if ( v3 )
  {
    v4 = *(_DWORD *)(v3 + 8);
    while ( v4 )
    {
      v5 = v4;
      v4 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 8), v4 + 1, v4);
      if ( v5 == v4 )
      {
        *(_QWORD *)&v25 = *a1;
        v11 = a1[1];
        *((_QWORD *)&v25 + 1) = v11;
        v6 = __PAIR128__(v11, v25);
        goto LABEL_6;
      }
    }
  }
  v6 = v25;
LABEL_6:
  if ( (_QWORD)v6 )
  {
    winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::GetCurrentStatus(
      a2,
      &v23);
    v7 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::InstallState(&v23);
    v26 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(&v23);
    v21 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 80LL))(v23, &v21);
    if ( v8 < 0 )
      winrt::throw_hresult((unsigned int)v8);
    v24 = v21;
    v22 = v7;
    v9 = *(_QWORD *)winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::PackageFamilyName(
                      a2,
                      &lpMem);
    if ( v9 )
      v10 = *(const wchar_t **)(v9 + 16);
    else
      v10 = &S2;
    v27 = v10;
    v29[0] = L"PFN:{}, InstallState:{}, PercentComplete:{}, ErrorCode:{}";
    v29[1] = 57;
    ClientTelemetry::LogMessage<wchar_t const *,unsigned int,double &,long &>(
      (unsigned int)v29,
      (unsigned int)&v27,
      (unsigned int)&v22,
      (unsigned int)&v26,
      (__int64)&v24);
    v12 = lpMem;
    if ( lpMem )
    {
      v13 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v13 )
      {
        if ( v13 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v12);
      }
    }
    v15 = v7 - 6;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( !v16 || (v17 = v16 - 1) == 0 )
      {
LABEL_21:
        *(_DWORD *)(v6 + 4) = -2147467259;
        goto LABEL_22;
      }
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 && (unsigned int)(v19 - 1) > 1 )
        {
LABEL_26:
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
          goto LABEL_27;
        }
        goto LABEL_21;
      }
      if ( (unsigned int)mtx_do_lock(v6 + 80) )
        goto LABEL_41;
      if ( *(_DWORD *)(v6 + 156) == 0x7FFFFFFF )
        goto LABEL_38;
      *(_DWORD *)(v6 + 4) = v21;
      v20 = (*(_DWORD *)(v6 + 156))-- == 1;
      if ( v20 )
      {
        *(_DWORD *)(v6 + 152) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v6 + 96));
      }
    }
LABEL_22:
    if ( !(unsigned int)mtx_do_lock(v6 + 80) )
    {
      if ( *(_DWORD *)(v6 + 156) != 0x7FFFFFFF )
      {
        *(_BYTE *)v6 = 1;
        WakeConditionVariable((PCONDITION_VARIABLE)(v6 + 16));
        v20 = (*(_DWORD *)(v6 + 156))-- == 1;
        if ( v20 )
        {
          *(_DWORD *)(v6 + 152) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)(v6 + 96));
        }
        goto LABEL_26;
      }
LABEL_38:
      *(_DWORD *)(v6 + 156) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
LABEL_41:
    std::_Throw_Cpp_error(5);
  }
LABEL_27:
  if ( *((_QWORD *)&v6 + 1) && !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v6 + 1) + 8LL)) )
  {
    (***((void (__fastcall ****)(_QWORD))&v6 + 1))(*((_QWORD *)&v6 + 1));
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v6 + 1) + 12LL)) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v6 + 1) + 8LL))(*((_QWORD *)&v6 + 1));
  }
}

```

## disassembly

```asm
0x18001174c  mov     [rsp-28h+arg_10], rbx
0x180011751  push    rbp
0x180011752  push    rsi
0x180011753  push    rdi
0x180011754  push    r14
0x180011756  push    r15
0x180011758  mov     rbp, rsp
0x18001175b  sub     rsp, 80h
0x180011762  mov     r14, rdx
0x180011765  mov     rdi, rcx
0x180011768  xorps   xmm1, xmm1
0x18001176b  movdqu  [rbp+var_38], xmm1
0x180011770  mov     rdx, [rcx+8]
0x180011774  test    rdx, rdx
0x180011777  jz      short loc_180011790
0x180011779  mov     eax, [rdx+8]
0x18001177c  jmp     short loc_18001178C
0x18001177e  lea     ecx, [rax+1]
0x180011781  lock cmpxchg [rdx+8], ecx
0x180011786  jz      loc_180011812
0x18001178c  test    eax, eax
0x18001178e  jnz     short loc_18001177E
0x180011790  mov     rsi, qword ptr [rbp+var_38]
0x180011794  mov     rdi, qword ptr [rbp+var_38+8]
0x180011798  or      r15d, 0FFFFFFFFh
0x18001179c  test    rsi, rsi
0x18001179f  jz      loc_180011915
0x1800117a5  lea     rdx, [rbp+var_48]
0x1800117a9  mov     rcx, r14
0x1800117ac  call    ?GetCurrentStatus@?$consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem@UIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::GetCurrentStatus(void)
0x1800117b1  nop
0x1800117b2  lea     rcx, [rbp+var_48]
0x1800117b6  call    ?InstallState@?$consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus@UIAppInstallStatus@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::InstallState(void)
0x1800117bb  mov     ebx, eax
0x1800117bd  lea     rcx, [rbp+var_48]
0x1800117c1  call    ?PercentComplete@?$consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus@UIAppInstallStatus@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallStatus<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallStatus>::PercentComplete(void)
0x1800117c6  movsd   [rbp+var_28], xmm0
0x1800117cb  mov     [rbp+var_50], 0
0x1800117d2  mov     rcx, [rbp+var_48]
0x1800117d6  mov     rdx, [rcx]
0x1800117d9  mov     rax, [rdx+50h]
0x1800117dd  lea     rdx, [rbp+var_50]
0x1800117e1  call    _guard_dispatch_icall
0x1800117e6  test    eax, eax
0x1800117e8  js      loc_1800119CB
0x1800117ee  mov     eax, [rbp+var_50]
0x1800117f1  mov     [rbp+var_40], eax
0x1800117f4  mov     [rbp+var_4C], ebx
0x1800117f7  lea     rdx, [rbp+lpMem]
0x1800117fb  mov     rcx, r14
0x1800117fe  call    ?PackageFamilyName@?$consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem@UIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_IAppInstallItem<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::PackageFamilyName(void)
0x180011803  nop
0x180011804  mov     rax, [rax]
0x180011807  test    rax, rax
0x18001180a  jz      short loc_180011826
0x18001180c  mov     rax, [rax+10h]
0x180011810  jmp     short loc_18001182D
0x180011812  mov     rsi, [rdi]
0x180011815  mov     qword ptr [rbp+var_38], rsi
0x180011819  mov     rdi, [rdi+8]
0x18001181d  mov     qword ptr [rbp+var_38+8], rdi
0x180011821  jmp     loc_180011798
0x180011826  lea     rax, S2
0x18001182d  mov     [rbp+var_20], rax
0x180011831  lea     rax, aPfnInstallstat; "PFN:{}, InstallState:{}, PercentComplet"...
0x180011838  mov     [rbp+var_10], rax
0x18001183c  mov     [rbp+var_8], 39h ; '9'
0x180011844  lea     rax, [rbp+var_40]
0x180011848  mov     [rsp+80h+var_60], rax
0x18001184d  lea     r9, [rbp+var_28]
0x180011851  lea     r8, [rbp+var_4C]
0x180011855  lea     rdx, [rbp+var_20]
0x180011859  lea     rcx, [rbp+var_10]
0x18001185d  call    ??$LogMessage@PEB_WIAEANAEAJ@ClientTelemetry@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAPEB_W$$QEAIAEANAEAJ@Z; ClientTelemetry::LogMessage<wchar_t const *,uint,double &,long &>(std::wstring_view,wchar_t const * &&,uint &&,double &,long &)
0x180011862  nop
0x180011863  mov     r14, [rbp+lpMem]
0x180011867  test    r14, r14
0x18001186a  jz      short loc_180011891
0x18001186c  mov     eax, r15d
0x18001186f  lock xadd [r14+18h], eax
0x180011875  sub     eax, 1
0x180011878  jnz     loc_180011968
0x18001187e  nop
0x18001187f  call    WINRT_IMPL_GetProcessHeap
0x180011884  mov     rcx, rax; hHeap
0x180011887  mov     r8, r14; lpMem
0x18001188a  xor     edx, edx; dwFlags
0x18001188c  call    WINRT_IMPL_HeapFree
0x180011891  mov     r14d, 7FFFFFFFh
0x180011897  sub     ebx, 6
0x18001189a  jz      short loc_1800118C5
0x18001189c  sub     ebx, 1
0x18001189f  jz      short loc_1800118BE
0x1800118a1  sub     ebx, 1
0x1800118a4  jz      short loc_1800118BE
0x1800118a6  sub     ebx, 1
0x1800118a9  jz      loc_180011971
0x1800118af  sub     ebx, 1
0x1800118b2  jz      short loc_1800118BE
0x1800118b4  sub     ebx, 1
0x1800118b7  jz      short loc_1800118BE
0x1800118b9  cmp     ebx, 1
0x1800118bc  jnz     short loc_18001190B
0x1800118be  mov     dword ptr [rsi+4], 80004005h
0x1800118c5  lea     rcx, [rsi+50h]
0x1800118c9  call    mtx_do_lock
0x1800118ce  test    eax, eax
0x1800118d0  jnz     loc_1800119D3
0x1800118d6  cmp     [rsi+9Ch], r14d
0x1800118dd  jz      loc_1800119B0
0x1800118e3  mov     byte ptr [rsi], 1
0x1800118e6  lea     rcx, [rsi+10h]; ConditionVariable
0x1800118ea  call    cs:__imp_WakeConditionVariable
0x1800118f0  add     [rsi+9Ch], r15d
0x1800118f7  jnz     short loc_18001190B
0x1800118f9  mov     [rsi+98h], r15d
0x180011900  lea     rcx, [rsi+60h]; SRWLock
0x180011904  call    cs:__imp_ReleaseSRWLockExclusive
0x18001190a  nop
0x18001190b  lea     rcx, [rbp+var_48]
0x18001190f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011914  nop
0x180011915  test    rdi, rdi
0x180011918  jz      short loc_180011951
0x18001191a  mov     eax, r15d
0x18001191d  lock xadd [rdi+8], eax
0x180011922  add     eax, r15d
0x180011925  jnz     short loc_180011951
0x180011927  mov     rax, [rdi]
0x18001192a  mov     rcx, rdi
0x18001192d  mov     rax, [rax]
0x180011930  call    _guard_dispatch_icall
0x180011935  mov     eax, r15d
0x180011938  lock xadd [rdi+0Ch], eax
0x18001193d  add     eax, r15d
0x180011940  jnz     short loc_180011951
0x180011942  mov     rax, [rdi]
0x180011945  mov     rcx, rdi
0x180011948  mov     rax, [rax+8]
0x18001194c  call    _guard_dispatch_icall
0x180011951  mov     rbx, [rsp+80h+arg_10]
0x180011959  add     rsp, 80h
0x180011960  pop     r15
0x180011962  pop     r14
0x180011964  pop     rdi
0x180011965  pop     rsi
0x180011966  pop     rbp
0x180011967  retn
0x180011968  test    eax, eax
0x18001196a  js      short loc_1800119C5
0x18001196c  jmp     loc_180011891
0x180011971  lea     rcx, [rsi+50h]
0x180011975  call    mtx_do_lock
0x18001197a  test    eax, eax
0x18001197c  jnz     short loc_1800119D3
0x18001197e  cmp     [rsi+9Ch], r14d
0x180011985  jz      short loc_1800119B0
0x180011987  mov     eax, [rbp+var_50]
0x18001198a  mov     [rsi+4], eax
0x18001198d  add     [rsi+9Ch], r15d
0x180011994  jnz     loc_1800118C5
0x18001199a  mov     [rsi+98h], r15d
0x1800119a1  lea     rcx, [rsi+60h]; SRWLock
0x1800119a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800119ab  jmp     loc_1800118C5
0x1800119b0  mov     dword ptr [rsi+9Ch], 7FFFFFFEh
0x1800119ba  mov     ecx, 6; int
0x1800119bf  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800119c5  call    abort
0x1800119cb  mov     ecx, eax
0x1800119cd  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x1800119d3  mov     ecx, 5; int
0x1800119d8  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
