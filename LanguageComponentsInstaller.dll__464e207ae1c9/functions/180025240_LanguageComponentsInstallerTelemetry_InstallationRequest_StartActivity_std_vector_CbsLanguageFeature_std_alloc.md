# LanguageComponentsInstallerTelemetry::InstallationRequest::StartActivity(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &)

- ea: `0x180025240`
- end: `0x1800253bf`
- name: `?StartActivity@InstallationRequest@LanguageComponentsInstallerTelemetry@@QEAAXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z`
- size: `383`
- prototype: `void __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025d20`

## callees

- `0x180001f98`
- `0x180003520`
- `0x180006380`
- `0x1800080e0`
- `0x180018b8c`
- `0x1800195c0`
- `0x180024d34`
- `0x180025240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800252b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800252b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800252e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025383`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800252e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025383`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180025298`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180025298`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::InstallationRequest::StartActivity(__int64 a1, __int64 *a2)
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
      (int)word_18002FE72,
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
0x180025240  mov     [rsp-8+arg_10], rbx
0x180025245  mov     [rsp-8+arg_18], rdi
0x18002524a  push    rbp
0x18002524b  mov     rbp, rsp
0x18002524e  sub     rsp, 80h
0x180025255  mov     rax, cs:__security_cookie
0x18002525c  xor     rax, rsp
0x18002525f  mov     [rbp+var_8], rax
0x180025263  mov     rbx, rcx
0x180025266  lea     rcx, [rbp+Src]; Src
0x18002526a  call    ?GetSerializedFeatureList@LanguageComponentsInstallerTelemetry@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z; LanguageComponentsInstallerTelemetry::GetSerializedFeatureList(std::vector<CbsLanguageFeature> const &)
0x18002526f  nop
0x180025270  lea     rdx, [rbp+SRWLock]
0x180025274  mov     rcx, rbx
0x180025277  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002527c  mov     rdi, [rbx+110h]
0x180025283  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x180025288  mov     ecx, [rax]
0x18002528a  cmp     ecx, 5
0x18002528d  jbe     short loc_1800252A0
0x18002528f  lea     rdx, [rdi+8]; ActivityId
0x180025293  mov     ecx, 3; ControlCode
0x180025298  call    cs:__imp_EventActivityIdControl
0x18002529e  jmp     short loc_1800252A7
0x1800252a0  xorps   xmm0, xmm0
0x1800252a3  movups  xmmword ptr [rdi+8], xmm0
0x1800252a7  mov     dword ptr [rdi], 1
0x1800252ad  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800252b1  test    rcx, rcx
0x1800252b4  jz      short loc_1800252BC
0x1800252b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800252bc  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x1800252c1  mov     rdi, rax
0x1800252c4  mov     ecx, [rax]
0x1800252c6  cmp     ecx, 5
0x1800252c9  jbe     loc_180025350
0x1800252cf  lea     rcx, [rbp+Src]
0x1800252d3  cmp     [rbp+var_10], 7
0x1800252d8  cmova   rcx, [rbp+Src]
0x1800252dd  mov     [rbp+var_38], rcx
0x1800252e1  call    cs:__imp_GetCurrentThreadId
0x1800252e7  mov     dword ptr [rbp+SRWLock], eax
0x1800252ea  mov     [rbp+var_30], 0
0x1800252f2  mov     r8, [rbx+110h]
0x1800252f9  cmp     byte ptr [r8+4], 0
0x1800252fe  jz      short loc_18002531F
0x180025300  lea     r9, [r8+18h]
0x180025304  cmp     dword ptr [r9], 0
0x180025308  jnz     short loc_180025322
0x18002530a  cmp     dword ptr [r9+4], 0
0x18002530f  jnz     short loc_180025322
0x180025311  cmp     dword ptr [r9+8], 0
0x180025316  jnz     short loc_180025322
0x180025318  cmp     dword ptr [r9+0Ch], 0
0x18002531d  jnz     short loc_180025322
0x18002531f  xor     r9d, r9d
0x180025322  add     r8, 8
0x180025326  lea     rax, [rbp+var_38]
0x18002532a  mov     [rsp+80h+var_50], rax; __int64
0x18002532f  lea     rax, [rbp+SRWLock]
0x180025333  mov     [rsp+80h+var_58], rax; __int64
0x180025338  lea     rax, [rbp+var_30]
0x18002533c  mov     [rsp+80h+var_60], rax; __int64
0x180025341  lea     rdx, word_18002FE72
0x180025348  mov     rcx, rdi; int
0x18002534b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180025350  cmp     dword ptr [rbx+138h], 0
0x180025357  jnz     short loc_180025395
0x180025359  add     rbx, 120h
0x180025360  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180025368  jz      short loc_18002538E
0x18002536a  mov     dl, 1
0x18002536c  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180025371  mov     [rbx], rax
0x180025374  test    rax, rax
0x180025377  jz      short loc_180025395
0x180025379  mov     rcx, [rax]
0x18002537c  mov     [rbx+10h], rcx
0x180025380  mov     [rax], rbx
0x180025383  call    cs:__imp_GetCurrentThreadId
0x180025389  mov     [rbx+18h], eax
0x18002538c  jmp     short loc_180025395
0x18002538e  mov     qword ptr [rbx], 0
0x180025395  lea     rcx, [rbp+Src]; void *
0x180025399  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002539e  mov     rcx, [rbp+var_8]
0x1800253a2  xor     rcx, rsp; StackCookie
0x1800253a5  call    __security_check_cookie
0x1800253aa  lea     r11, [rsp+80h+var_s0]
0x1800253b2  mov     rbx, [r11+20h]
0x1800253b6  mov     rdi, [r11+28h]
0x1800253ba  mov     rsp, r11
0x1800253bd  pop     rbp
0x1800253be  retn
```
