# SystemSettings::DataModel::TokenBrokerSingleton::_GetDefaultAccount(void)

- ea: `0x180020698`
- end: `0x1800207d4`
- name: `?_GetDefaultAccount@TokenBrokerSingleton@DataModel@SystemSettings@@AEAAJXZ`
- size: `316`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::TokenBrokerSingleton *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dde0`
- `0x180020c1c`

## callees

- `0x1800045ec`
- `0x1800076ac`
- `0x1800096ec`
- `0x18000c3f8`
- `0x18000f074`
- `0x1800189c4`
- `0x18001977c`
- `0x1800201e0`
- `0x180020698`
- `0x18002099c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002076a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002076a`

## string_xrefs

- `0x1800206bd`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x180020738`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x1800207a8`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::TokenBrokerSingleton::_GetDefaultAccount(
        SystemSettings::DataModel::TokenBrokerSingleton *this)
{
  int v2; // eax
  unsigned int v3; // edi
  __int64 v4; // rax
  int v5; // eax
  _lambda_d499bb7c7bb9030fdb66f37c3eece255_ *v6; // rax
  __int64 v7; // r8
  int DefaultSignInAccount; // eax
  __int128 v10; // [rsp+20h] [rbp-59h] BYREF
  _BYTE v11[16]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v12[144]; // [rsp+40h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v14; // [rsp+E8h] [rbp+6Fh] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp+77h] BYREF
  char v16; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = SystemSettings::DataModel::TokenBrokerSingleton::_EnsureTokenBrokerInternalStatics(this);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v14 = 0;
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 232);
    if ( *((_BYTE *)this + 240)
      || *((_BYTE *)this + 241)
      || (v10 = *(_OWORD *)_lambda_9dece6d741847fb774fb9364fa73d27b_::_lambda_9dece6d741847fb774fb9364fa73d27b_(
                             v11,
                             this,
                             &v14),
          v4 = wistd::function<long (void)>::function<long (void)>(v12, &v10),
          v5 = SystemSettings::DataModel::TokenBrokerSingleton::_SwitchToBrokerCallingContext(v4),
          v3 = v5,
          v5 >= 0) )
    {
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      if ( v14
        && (SRWLock = (PSRWLOCK)this,
            v6 = _lambda_d499bb7c7bb9030fdb66f37c3eece255_::_lambda_d499bb7c7bb9030fdb66f37c3eece255_(
                   (_lambda_d499bb7c7bb9030fdb66f37c3eece255_ *)&v16,
                   (struct SystemSettings::DataModel::TokenBrokerSingleton *const *)&SRWLock),
            DefaultSignInAccount = StartOperationAndThen<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,_lambda_d499bb7c7bb9030fdb66f37c3eece255_>(
                                     v7,
                                     v6),
            v3 = DefaultSignInAccount,
            DefaultSignInAccount < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x165,
          (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
          (const char *)(unsigned int)DefaultSignInAccount,
          v10);
      }
      else
      {
        v3 = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
        (const char *)(unsigned int)v5,
        v10);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
      (const char *)(unsigned int)v2,
      v10);
  }
  return v3;
}

```

## disassembly

```asm
0x180020698  push    rbp
0x18002069a  push    rbx
0x18002069b  push    rdi
0x18002069c  lea     rbp, [rsp-47h]
0x1800206a1  sub     rsp, 0C0h
0x1800206a8  mov     rbx, rcx
0x1800206ab  call    ?_EnsureTokenBrokerInternalStatics@TokenBrokerSingleton@DataModel@SystemSettings@@AEAAJXZ; SystemSettings::DataModel::TokenBrokerSingleton::_EnsureTokenBrokerInternalStatics(void)
0x1800206b0  mov     edi, eax
0x1800206b2  test    eax, eax
0x1800206b4  jns     short loc_1800206D3
0x1800206b6  mov     rcx, [rbp+5Fh]; this
0x1800206ba  mov     r9d, eax; char *
0x1800206bd  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x1800206c4  mov     edx, 0FAh; void *
0x1800206c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206ce  jmp     loc_1800207C6
0x1800206d3  mov     [rbp+57h+arg_8], 0
0x1800206db  lea     rdx, [rbx+0E8h]
0x1800206e2  lea     rcx, [rbp+57h+SRWLock]
0x1800206e6  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800206eb  nop
0x1800206ec  cmp     byte ptr [rbx+0F0h], 0
0x1800206f3  jnz     short loc_180020761
0x1800206f5  cmp     byte ptr [rbx+0F1h], 0
0x1800206fc  jnz     short loc_180020761
0x1800206fe  lea     r8, [rbp+57h+arg_8]
0x180020702  mov     rdx, rbx
0x180020705  lea     rcx, [rbp+57h+var_A0]
0x180020709  call    ??0_lambda_9dece6d741847fb774fb9364fa73d27b_@@QEAA@PEAVTokenBrokerSingleton@DataModel@SystemSettings@@AEAV?$ComPtr@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Z; _lambda_9dece6d741847fb774fb9364fa73d27b_::_lambda_9dece6d741847fb774fb9364fa73d27b_(SystemSettings::DataModel::TokenBrokerSingleton *,Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>> &)
0x18002070e  movups  xmm0, xmmword ptr [rax]
0x180020711  movdqu  [rbp+57h+var_B0], xmm0
0x180020716  lea     rdx, [rbp+57h+var_B0]
0x18002071a  lea     rcx, [rbp+57h+var_90]
0x18002071e  call    ??$?0V_lambda_9dece6d741847fb774fb9364fa73d27b_@@X@?$function@$$A6AJXZ@wistd@@QEAA@V_lambda_9dece6d741847fb774fb9364fa73d27b_@@@Z; wistd::function<long (void)>::function<long (void)>(_lambda_9dece6d741847fb774fb9364fa73d27b_)
0x180020723  mov     rcx, rax
0x180020726  call    ?_SwitchToBrokerCallingContext@TokenBrokerSingleton@DataModel@SystemSettings@@CAJV?$function@$$A6AJXZ@wistd@@@Z; SystemSettings::DataModel::TokenBrokerSingleton::_SwitchToBrokerCallingContext(wistd::function<long (void)>)
0x18002072b  mov     edi, eax
0x18002072d  test    eax, eax
0x18002072f  jns     short loc_180020761
0x180020731  mov     rcx, [rbp+5Fh]; this
0x180020735  mov     r9d, eax; char *
0x180020738  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x18002073f  mov     edx, 108h; void *
0x180020744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020749  nop
0x18002074a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002074e  test    rcx, rcx
0x180020751  jz      short loc_1800207BD
0x180020753  call    cs:__imp_ReleaseSRWLockExclusive
0x18002075a  nop     dword ptr [rax+rax+00h]
0x18002075f  jmp     short loc_1800207BD
0x180020761  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180020765  test    rcx, rcx
0x180020768  jz      short loc_180020776
0x18002076a  call    cs:__imp_ReleaseSRWLockExclusive
0x180020771  nop     dword ptr [rax+rax+00h]
0x180020776  mov     r8, [rbp+57h+arg_8]
0x18002077a  test    r8, r8
0x18002077d  jz      short loc_1800207BB
0x18002077f  mov     [rbp+57h+SRWLock], rbx
0x180020783  lea     rdx, [rbp+57h+SRWLock]; struct SystemSettings::DataModel::TokenBrokerSingleton **
0x180020787  lea     rcx, [rbp+57h+arg_18]; this
0x18002078b  call    ??0_lambda_d499bb7c7bb9030fdb66f37c3eece255_@@QEAA@AEBQEAVTokenBrokerSingleton@DataModel@SystemSettings@@@Z; _lambda_d499bb7c7bb9030fdb66f37c3eece255_::_lambda_d499bb7c7bb9030fdb66f37c3eece255_(SystemSettings::DataModel::TokenBrokerSingleton * const &)
0x180020790  mov     rdx, rax
0x180020793  mov     rcx, r8
0x180020796  call    ??$StartOperationAndThen@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@V_lambda_d499bb7c7bb9030fdb66f37c3eece255_@@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@$$QEAV_lambda_d499bb7c7bb9030fdb66f37c3eece255_@@@Z; StartOperationAndThen<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,_lambda_d499bb7c7bb9030fdb66f37c3eece255_>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,_lambda_d499bb7c7bb9030fdb66f37c3eece255_ &&)
0x18002079b  mov     edi, eax
0x18002079d  test    eax, eax
0x18002079f  jns     short loc_1800207BB
0x1800207a1  mov     rcx, [rbp+5Fh]; this
0x1800207a5  mov     r9d, eax; char *
0x1800207a8  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x1800207af  mov     edx, 165h; void *
0x1800207b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800207b9  jmp     short loc_1800207BD
0x1800207bb  xor     edi, edi
0x1800207bd  lea     rcx, [rbp+57h+arg_8]
0x1800207c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800207c6  mov     eax, edi
0x1800207c8  add     rsp, 0C0h
0x1800207cf  pop     rdi
0x1800207d0  pop     rbx
0x1800207d1  pop     rbp
0x1800207d2  retn
```
