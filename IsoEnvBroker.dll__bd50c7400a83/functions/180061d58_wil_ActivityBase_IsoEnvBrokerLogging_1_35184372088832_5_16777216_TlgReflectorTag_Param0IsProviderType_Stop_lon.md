# wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180061d58`
- end: `0x180061e7f`
- name: `?Stop@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `295`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180061100`
- `0x180062ba8`

## callees

- `0x18000176c`
- `0x1800030d0`
- `0x18000bb10`
- `0x180011d64`
- `0x18006019c`
- `0x18006075c`
- `0x180061d58`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061da7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061da7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061df7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061df7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  __int64 v5; // rdi
  __int64 v6; // r9
  const struct wil::FailureInfo *v7; // rdx
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v11[168]; // [rsp+60h] [rbp-A8h] BYREF

  wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
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
    v5 = *((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x200000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v10 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (__int64)byte_1800AB7F3,
        a1[34] + 8LL,
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
  wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180061d58  mov     [rsp+arg_8], rbx
0x180061d5d  push    rdi
0x180061d5e  sub     rsp, 100h
0x180061d65  mov     rbx, rcx
0x180061d68  lea     rdx, [rsp+108h+SRWLock]
0x180061d6d  call    ?LockExclusive@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180061d72  mov     rax, [rbx+110h]
0x180061d79  mov     edi, [rax+0F8h]
0x180061d7f  cmp     edi, 1
0x180061d82  jl      loc_180061E62
0x180061d88  cmp     dword ptr [rax+48h], 0
0x180061d8c  jl      short loc_180061D95
0x180061d8e  mov     dword ptr [rax+48h], 0
0x180061d95  dec     edi
0x180061d97  mov     [rax+0F8h], edi
0x180061d9d  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180061da2  test    rcx, rcx
0x180061da5  jz      short loc_180061DAD
0x180061da7  call    cs:__imp_ReleaseSRWLockExclusive
0x180061dad  test    edi, edi
0x180061daf  jnz     short loc_180061DC5
0x180061db1  mov     rax, [rbx]
0x180061db4  mov     rcx, rbx
0x180061db7  mov     rax, [rax+8]
0x180061dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061dc0  jmp     loc_180061E4A
0x180061dc5  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180061dca  mov     rdi, [rax+8]
0x180061dce  mov     eax, [rdi]
0x180061dd0  cmp     eax, 5
0x180061dd3  jbe     short loc_180061E4A
0x180061dd5  mov     rcx, [rdi+18h]
0x180061dd9  mov     rax, [rdi+10h]
0x180061ddd  mov     rdx, 200000000000h
0x180061de7  test    rdx, rax
0x180061dea  jz      short loc_180061E4A
0x180061dec  mov     rax, rcx
0x180061def  and     rax, rdx
0x180061df2  cmp     rax, rcx
0x180061df5  jnz     short loc_180061E4A
0x180061df7  call    cs:__imp_GetCurrentThreadId
0x180061dfd  mov     [rsp+108h+var_C8], eax
0x180061e01  mov     dword ptr [rsp+108h+SRWLock], 0
0x180061e09  mov     [rsp+108h+var_B8], 1000000h
0x180061e12  mov     r8, [rbx+110h]
0x180061e19  add     r8, 8
0x180061e1d  lea     rax, [rsp+108h+var_C8]
0x180061e22  mov     [rsp+108h+var_D8], rax
0x180061e27  lea     rax, [rsp+108h+SRWLock]
0x180061e2c  mov     [rsp+108h+var_E0], rax
0x180061e31  lea     rax, [rsp+108h+var_B8]
0x180061e36  mov     [rsp+108h+var_E8], rax
0x180061e3b  lea     rdx, byte_1800AB7F3
0x180061e42  mov     rcx, rdi
0x180061e45  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180061e4a  mov     rcx, rbx
0x180061e4d  mov     rbx, [rsp+108h+arg_8]
0x180061e55  add     rsp, 100h
0x180061e5c  pop     rdi
0x180061e5d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180061e62  xor     edx, edx; Val
0x180061e64  mov     r8d, 98h; Size
0x180061e6a  lea     rcx, [rsp+108h+var_A8]; void *
0x180061e6f  call    memset_0
0x180061e74  lea     rcx, [rsp+108h+var_A8]; this
0x180061e79  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
