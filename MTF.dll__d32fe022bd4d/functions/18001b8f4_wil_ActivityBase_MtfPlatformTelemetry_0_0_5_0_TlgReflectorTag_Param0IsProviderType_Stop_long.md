# wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001b8f4`
- end: `0x18001b9f6`
- name: `?Stop@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `258`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x180017a40`
- `0x180018f80`
- `0x18001a450`
- `0x18001c840`
- `0x18001cae0`

## callees

- `0x1800019f0`
- `0x1800053cc`
- `0x180006c80`
- `0x180018c84`
- `0x180018d00`
- `0x18001b8f4`
- `0x18002bc62`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b943`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b943`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b96e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b96e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(_QWORD *a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  _DWORD *v5; // rdi
  int v6; // r9d
  const struct wil::FailureInfo *v7; // rdx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v11[168]; // [rsp+60h] [rbp-A8h] BYREF

  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &SRWLock);
  v2 = a1[34];
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v7);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    v5 = (_DWORD *)*((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
    if ( *v5 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v10 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v5,
        (unsigned int)byte_1800367C9,
        a1[34] + 8,
        v6,
        (__int64)&v10,
        (__int64)&SRWLock,
        (__int64)&CurrentThreadId);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18001b8f4  mov     [rsp+arg_8], rbx
0x18001b8f9  push    rdi
0x18001b8fa  sub     rsp, 100h
0x18001b901  mov     rbx, rcx
0x18001b904  lea     rdx, [rsp+108h+SRWLock]
0x18001b909  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b90e  mov     rax, [rbx+110h]
0x18001b915  mov     edi, [rax+0F8h]
0x18001b91b  cmp     edi, 1
0x18001b91e  jl      loc_18001B9D9
0x18001b924  cmp     dword ptr [rax+48h], 0
0x18001b928  jl      short loc_18001B931
0x18001b92a  mov     dword ptr [rax+48h], 0
0x18001b931  dec     edi
0x18001b933  mov     [rax+0F8h], edi
0x18001b939  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x18001b93e  test    rcx, rcx
0x18001b941  jz      short loc_18001B949
0x18001b943  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b949  test    edi, edi
0x18001b94b  jnz     short loc_18001B95E
0x18001b94d  mov     rax, [rbx]
0x18001b950  mov     rcx, rbx
0x18001b953  mov     rax, [rax+8]
0x18001b957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b95c  jmp     short loc_18001B9C1
0x18001b95e  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b963  mov     rdi, [rax+8]
0x18001b967  mov     eax, [rdi]
0x18001b969  cmp     eax, 5
0x18001b96c  jbe     short loc_18001B9C1
0x18001b96e  call    cs:__imp_GetCurrentThreadId
0x18001b974  mov     [rsp+108h+var_C8], eax
0x18001b978  mov     dword ptr [rsp+108h+SRWLock], 0
0x18001b980  mov     [rsp+108h+var_B8], 1000000h
0x18001b989  mov     r8, [rbx+110h]
0x18001b990  add     r8, 8
0x18001b994  lea     rax, [rsp+108h+var_C8]
0x18001b999  mov     [rsp+108h+var_D8], rax
0x18001b99e  lea     rax, [rsp+108h+SRWLock]
0x18001b9a3  mov     [rsp+108h+var_E0], rax
0x18001b9a8  lea     rax, [rsp+108h+var_B8]
0x18001b9ad  mov     [rsp+108h+var_E8], rax
0x18001b9b2  lea     rdx, byte_1800367C9
0x18001b9b9  mov     rcx, rdi
0x18001b9bc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001b9c1  mov     rcx, rbx
0x18001b9c4  mov     rbx, [rsp+108h+arg_8]
0x18001b9cc  add     rsp, 100h
0x18001b9d3  pop     rdi
0x18001b9d4  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001b9d9  xor     edx, edx; Val
0x18001b9db  mov     r8d, 98h; Size
0x18001b9e1  lea     rcx, [rsp+108h+var_A8]; void *
0x18001b9e6  call    memset_0
0x18001b9eb  lea     rcx, [rsp+108h+var_A8]; this
0x18001b9f0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
