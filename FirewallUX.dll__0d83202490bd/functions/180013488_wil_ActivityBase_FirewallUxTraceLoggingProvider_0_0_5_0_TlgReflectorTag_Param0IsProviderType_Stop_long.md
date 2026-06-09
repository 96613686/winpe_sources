# wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180013488`
- end: `0x18001358c`
- name: `?Stop@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x1800123e0`
- `0x180019ec0`
- `0x18001cdc0`
- `0x1800209d4`
- `0x1800229a0`

## callees

- `0x1800015d0`
- `0x180002c04`
- `0x1800080a4`
- `0x18000812c`
- `0x180008820`
- `0x18000a7b0`
- `0x180013488`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800134da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800134da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013504`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013504`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  const struct _tlgProvider_t *v7; // rdi
  __int64 v8; // r9
  const struct wil::FailureInfo *v9; // rdx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v13[160]; // [rsp+60h] [rbp-A8h] BYREF

  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = a1[34];
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v9);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    v7 = FirewallUxTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = a2;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v7,
        (__int64)&unk_180032BF8,
        a1[34] + 8LL,
        v8,
        (__int64)&v12,
        (__int64)&SRWLock,
        (__int64)&CurrentThreadId);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180013488  mov     [rsp+arg_8], rbx
0x18001348d  mov     [rsp+arg_10], rsi
0x180013492  push    rdi
0x180013493  sub     rsp, 100h
0x18001349a  mov     esi, edx
0x18001349c  mov     rbx, rcx
0x18001349f  lea     rdx, [rsp+108h+SRWLock]
0x1800134a4  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800134a9  mov     rax, [rbx+110h]
0x1800134b0  mov     edi, [rax+0F8h]
0x1800134b6  cmp     edi, 1
0x1800134b9  jl      loc_18001356F
0x1800134bf  cmp     dword ptr [rax+48h], 0
0x1800134c3  jl      short loc_1800134C8
0x1800134c5  mov     [rax+48h], esi
0x1800134c8  dec     edi
0x1800134ca  mov     [rax+0F8h], edi
0x1800134d0  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x1800134d5  test    rcx, rcx
0x1800134d8  jz      short loc_1800134E0
0x1800134da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800134e0  test    edi, edi
0x1800134e2  jnz     short loc_1800134F5
0x1800134e4  mov     rax, [rbx]
0x1800134e7  mov     rcx, rbx
0x1800134ea  mov     rax, [rax+8]
0x1800134ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134f3  jmp     short loc_180013553
0x1800134f5  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x1800134fa  mov     rdi, rax
0x1800134fd  mov     ecx, [rax]
0x1800134ff  cmp     ecx, 5
0x180013502  jbe     short loc_180013553
0x180013504  call    cs:__imp_GetCurrentThreadId
0x18001350a  mov     [rsp+108h+var_C8], eax
0x18001350e  mov     dword ptr [rsp+108h+SRWLock], esi
0x180013512  mov     [rsp+108h+var_B8], 1000000h
0x18001351b  mov     r8, [rbx+110h]
0x180013522  add     r8, 8
0x180013526  lea     rax, [rsp+108h+var_C8]
0x18001352b  mov     [rsp+108h+var_D8], rax
0x180013530  lea     rax, [rsp+108h+SRWLock]
0x180013535  mov     [rsp+108h+var_E0], rax
0x18001353a  lea     rax, [rsp+108h+var_B8]
0x18001353f  mov     [rsp+108h+var_E8], rax
0x180013544  lea     rdx, unk_180032BF8
0x18001354b  mov     rcx, rdi
0x18001354e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013553  mov     rcx, rbx
0x180013556  lea     r11, [rsp+108h+var_8]
0x18001355e  mov     rbx, [r11+18h]
0x180013562  mov     rsi, [r11+20h]
0x180013566  mov     rsp, r11
0x180013569  pop     rdi
0x18001356a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001356f  xor     edx, edx; Val
0x180013571  mov     r8d, 98h; Size
0x180013577  lea     rcx, [rsp+108h+var_A8]; void *
0x18001357c  call    memset_0
0x180013581  lea     rcx, [rsp+108h+var_A8]; this
0x180013586  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
