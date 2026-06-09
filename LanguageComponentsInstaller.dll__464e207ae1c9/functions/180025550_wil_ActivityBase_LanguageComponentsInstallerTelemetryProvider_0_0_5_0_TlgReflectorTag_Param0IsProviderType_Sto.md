# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180025550`
- end: `0x180025659`
- name: `?Stop@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `265`
- prototype: `void __fastcall(_QWORD *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025d20`
- `0x180026020`

## callees

- `0x18000196c`
- `0x180004118`
- `0x18000a0b0`
- `0x180018580`
- `0x180018b8c`
- `0x1800195c0`
- `0x180025550`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002559f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002559f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800255c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800255c9`

## pseudocode

```c
void __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  const struct _tlgProvider_t *v7; // rax
  int v8; // edi
  __int64 v9; // r9
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[184]; // [rsp+40h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  int v13; // [rsp+110h] [rbp+18h] BYREF
  __int64 v14; // [rsp+118h] [rbp+20h] BYREF

  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v4 = a1[34];
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v10);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    v7 = LanguageComponentsInstallerTelemetryProvider::Provider();
    v8 = (int)v7;
    if ( *(_DWORD *)v7 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v13 = a2;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v8,
        (int)word_180030002,
        a1[34] + 8,
        v9,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&SRWLock);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180025550  mov     rax, rsp
0x180025553  push    rbx
0x180025554  push    rsi
0x180025555  push    rdi
0x180025556  sub     rsp, 0E0h
0x18002555d  mov     esi, edx
0x18002555f  mov     rbx, rcx
0x180025562  lea     rdx, [rax+8]
0x180025566  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002556b  mov     rax, [rbx+110h]
0x180025572  mov     edi, [rax+0F8h]
0x180025578  cmp     edi, 1
0x18002557b  jl      loc_18002563C
0x180025581  cmp     dword ptr [rax+48h], 0
0x180025585  jl      short loc_18002558A
0x180025587  mov     [rax+48h], esi
0x18002558a  dec     edi
0x18002558c  mov     [rax+0F8h], edi
0x180025592  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x18002559a  test    rcx, rcx
0x18002559d  jz      short loc_1800255A5
0x18002559f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800255a5  test    edi, edi
0x1800255a7  jnz     short loc_1800255BA
0x1800255a9  mov     rax, [rbx]
0x1800255ac  mov     rcx, rbx
0x1800255af  mov     rax, [rax+8]
0x1800255b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255b8  jmp     short loc_18002562A
0x1800255ba  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x1800255bf  mov     rdi, rax
0x1800255c2  mov     ecx, [rax]
0x1800255c4  cmp     ecx, 5
0x1800255c7  jbe     short loc_18002562A
0x1800255c9  call    cs:__imp_GetCurrentThreadId
0x1800255cf  mov     dword ptr [rsp+0F8h+SRWLock], eax
0x1800255d6  mov     [rsp+0F8h+arg_10], esi
0x1800255dd  mov     [rsp+0F8h+arg_18], 1000000h
0x1800255e9  mov     r8, [rbx+110h]
0x1800255f0  add     r8, 8
0x1800255f4  lea     rax, [rsp+0F8h+SRWLock]
0x1800255fc  mov     [rsp+0F8h+var_C8], rax
0x180025601  lea     rax, [rsp+0F8h+arg_10]
0x180025609  mov     [rsp+0F8h+var_D0], rax
0x18002560e  lea     rax, [rsp+0F8h+arg_18]
0x180025616  mov     [rsp+0F8h+var_D8], rax
0x18002561b  lea     rdx, word_180030002
0x180025622  mov     rcx, rdi
0x180025625  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002562a  mov     rcx, rbx
0x18002562d  add     rsp, 0E0h
0x180025634  pop     rdi
0x180025635  pop     rsi
0x180025636  pop     rbx
0x180025637  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18002563c  xor     edx, edx; Val
0x18002563e  mov     r8d, 98h; Size
0x180025644  lea     rcx, [rsp+0F8h+var_B8]; void *
0x180025649  call    memset_0
0x18002564e  lea     rcx, [rsp+0F8h+var_B8]; this
0x180025653  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
