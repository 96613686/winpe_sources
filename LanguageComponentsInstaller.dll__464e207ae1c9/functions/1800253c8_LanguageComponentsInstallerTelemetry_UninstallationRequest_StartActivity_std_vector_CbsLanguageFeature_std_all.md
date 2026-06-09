# LanguageComponentsInstallerTelemetry::UninstallationRequest::StartActivity(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &)

- ea: `0x1800253c8`
- end: `0x180025547`
- name: `?StartActivity@UninstallationRequest@LanguageComponentsInstallerTelemetry@@QEAAXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z`
- size: `383`
- prototype: `void __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026020`

## callees

- `0x180001f98`
- `0x180003520`
- `0x180006380`
- `0x1800080e0`
- `0x180018b8c`
- `0x1800195c0`
- `0x180024d34`
- `0x1800253c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002543e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002543e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025469`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002550b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025469`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002550b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180025420`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180025420`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::UninstallationRequest::StartActivity(__int64 a1, __int64 *a2)
{
  __int64 v3; // rdi
  const struct _tlgProvider_t *v4; // rax
  int v5; // edi
  __int64 v6; // rcx
  char **v7; // rcx
  __int64 v8; // r8
  int v9; // r9d
  __int64 v10; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-40h] BYREF
  __int64 v13; // [rsp+48h] [rbp-38h] BYREF
  __int64 v14; // [rsp+50h] [rbp-30h] BYREF
  char *Src[4]; // [rsp+58h] [rbp-28h] BYREF

  LanguageComponentsInstallerTelemetry::GetSerializedFeatureList(Src, a2);
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v3 = *(_QWORD *)(a1 + 272);
  if ( *(_DWORD *)LanguageComponentsInstallerTelemetryProvider::Provider() <= 5u )
    *(_OWORD *)(v3 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v3 + 8));
  *(_DWORD *)v3 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = LanguageComponentsInstallerTelemetryProvider::Provider();
  v5 = (int)v4;
  v6 = *(unsigned int *)v4;
  if ( (unsigned int)v6 > 5 )
  {
    v7 = Src;
    if ( Src[3] > (char *)7 )
      v7 = (char **)Src[0];
    v13 = (__int64)v7;
    LODWORD(SRWLock) = GetCurrentThreadId();
    v14 = 0;
    v8 = *(_QWORD *)(a1 + 272);
    if ( !*(_BYTE *)(v8 + 4)
      || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
      && !*(_DWORD *)(v8 + 28)
      && !*(_DWORD *)(v8 + 32)
      && !*(_DWORD *)(v8 + 36) )
    {
      v9 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v5,
      (int)word_18002FBF2,
      v8 + 8,
      v9,
      (__int64)&v14,
      (__int64)&SRWLock,
      (__int64 **)&v13);
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v10 = a1 + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v6,
                          1);
      *(_QWORD *)v10 = Local;
      if ( Local )
      {
        *(_QWORD *)(v10 + 16) = *Local;
        *Local = v10;
        *(_DWORD *)(v10 + 24) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v10 = 0;
    }
  }
  std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x1800253c8  mov     [rsp-8+arg_10], rbx
0x1800253cd  mov     [rsp-8+arg_18], rdi
0x1800253d2  push    rbp
0x1800253d3  mov     rbp, rsp
0x1800253d6  sub     rsp, 80h
0x1800253dd  mov     rax, cs:__security_cookie
0x1800253e4  xor     rax, rsp
0x1800253e7  mov     [rbp+var_8], rax
0x1800253eb  mov     rbx, rcx
0x1800253ee  lea     rcx, [rbp+Src]; Src
0x1800253f2  call    ?GetSerializedFeatureList@LanguageComponentsInstallerTelemetry@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z; LanguageComponentsInstallerTelemetry::GetSerializedFeatureList(std::vector<CbsLanguageFeature> const &)
0x1800253f7  nop
0x1800253f8  lea     rdx, [rbp+SRWLock]
0x1800253fc  mov     rcx, rbx
0x1800253ff  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025404  mov     rdi, [rbx+110h]
0x18002540b  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x180025410  mov     ecx, [rax]
0x180025412  cmp     ecx, 5
0x180025415  jbe     short loc_180025428
0x180025417  lea     rdx, [rdi+8]; ActivityId
0x18002541b  mov     ecx, 3; ControlCode
0x180025420  call    cs:__imp_EventActivityIdControl
0x180025426  jmp     short loc_18002542F
0x180025428  xorps   xmm0, xmm0
0x18002542b  movups  xmmword ptr [rdi+8], xmm0
0x18002542f  mov     dword ptr [rdi], 1
0x180025435  mov     rcx, [rbp+SRWLock]; SRWLock
0x180025439  test    rcx, rcx
0x18002543c  jz      short loc_180025444
0x18002543e  call    cs:__imp_ReleaseSRWLockExclusive
0x180025444  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x180025449  mov     rdi, rax
0x18002544c  mov     ecx, [rax]
0x18002544e  cmp     ecx, 5
0x180025451  jbe     loc_1800254D8
0x180025457  lea     rcx, [rbp+Src]
0x18002545b  cmp     [rbp+var_10], 7
0x180025460  cmova   rcx, [rbp+Src]
0x180025465  mov     [rbp+var_38], rcx
0x180025469  call    cs:__imp_GetCurrentThreadId
0x18002546f  mov     dword ptr [rbp+SRWLock], eax
0x180025472  mov     [rbp+var_30], 0
0x18002547a  mov     r8, [rbx+110h]
0x180025481  cmp     byte ptr [r8+4], 0
0x180025486  jz      short loc_1800254A7
0x180025488  lea     r9, [r8+18h]
0x18002548c  cmp     dword ptr [r9], 0
0x180025490  jnz     short loc_1800254AA
0x180025492  cmp     dword ptr [r9+4], 0
0x180025497  jnz     short loc_1800254AA
0x180025499  cmp     dword ptr [r9+8], 0
0x18002549e  jnz     short loc_1800254AA
0x1800254a0  cmp     dword ptr [r9+0Ch], 0
0x1800254a5  jnz     short loc_1800254AA
0x1800254a7  xor     r9d, r9d
0x1800254aa  add     r8, 8
0x1800254ae  lea     rax, [rbp+var_38]
0x1800254b2  mov     [rsp+80h+var_50], rax; __int64
0x1800254b7  lea     rax, [rbp+SRWLock]
0x1800254bb  mov     [rsp+80h+var_58], rax; __int64
0x1800254c0  lea     rax, [rbp+var_30]
0x1800254c4  mov     [rsp+80h+var_60], rax; __int64
0x1800254c9  lea     rdx, word_18002FBF2
0x1800254d0  mov     rcx, rdi; int
0x1800254d3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800254d8  cmp     dword ptr [rbx+138h], 0
0x1800254df  jnz     short loc_18002551D
0x1800254e1  add     rbx, 120h
0x1800254e8  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800254f0  jz      short loc_180025516
0x1800254f2  mov     dl, 1
0x1800254f4  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800254f9  mov     [rbx], rax
0x1800254fc  test    rax, rax
0x1800254ff  jz      short loc_18002551D
0x180025501  mov     rcx, [rax]
0x180025504  mov     [rbx+10h], rcx
0x180025508  mov     [rax], rbx
0x18002550b  call    cs:__imp_GetCurrentThreadId
0x180025511  mov     [rbx+18h], eax
0x180025514  jmp     short loc_18002551D
0x180025516  mov     qword ptr [rbx], 0
0x18002551d  lea     rcx, [rbp+Src]; void *
0x180025521  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025526  mov     rcx, [rbp+var_8]
0x18002552a  xor     rcx, rsp; StackCookie
0x18002552d  call    __security_check_cookie
0x180025532  lea     r11, [rsp+80h+var_s0]
0x18002553a  mov     rbx, [r11+20h]
0x18002553e  mov     rdi, [r11+28h]
0x180025542  mov     rsp, r11
0x180025545  pop     rbp
0x180025546  retn
```
