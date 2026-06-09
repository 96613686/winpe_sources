# wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180016f74`
- end: `0x1800170b4`
- name: `?Stop@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `8`
- tags: ``

## callers

- `0x180015410`
- `0x1800196c0`
- `0x18002ee00`
- `0x18002f100`
- `0x18002f410`
- `0x1800306c0`
- `0x180030ca0`
- `0x180030e34`
- `0x180030f64`
- `0x180031810`
- `0x180047070`
- `0x18005b100`

## callees

- `0x180001a78`
- `0x1800044b8`
- `0x1800085dc`
- `0x180009e70`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180016f74`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016fc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016fc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017017`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  __int64 v7; // rdi
  __int64 v8; // r9
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[184]; // [rsp+40h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  int v12; // [rsp+110h] [rbp+18h] BYREF
  __int64 v13; // [rsp+118h] [rbp+20h] BYREF

  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v10, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v10, v9);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    v7 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v12 = a2;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)&word_18007694E,
        *(_QWORD *)(a1 + 272) + 8LL,
        v8,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&SRWLock);
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180016f74  mov     rax, rsp
0x180016f77  push    rbx
0x180016f78  push    rsi
0x180016f79  push    rdi
0x180016f7a  sub     rsp, 0E0h
0x180016f81  mov     esi, edx
0x180016f83  mov     rbx, rcx
0x180016f86  lea     rdx, [rax+8]
0x180016f8a  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016f8f  mov     rax, [rbx+110h]
0x180016f96  mov     edi, [rax+0F8h]
0x180016f9c  cmp     edi, 1
0x180016f9f  jl      loc_180017097
0x180016fa5  cmp     dword ptr [rax+48h], 0
0x180016fa9  jl      short loc_180016FAE
0x180016fab  mov     [rax+48h], esi
0x180016fae  dec     edi
0x180016fb0  mov     [rax+0F8h], edi
0x180016fb6  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x180016fbe  test    rcx, rcx
0x180016fc1  jz      short loc_180016FC9
0x180016fc3  call    cs:__imp_ReleaseSRWLockExclusive
0x180016fc9  test    edi, edi
0x180016fcb  jnz     short loc_180016FE1
0x180016fcd  mov     rax, [rbx]
0x180016fd0  mov     rcx, rbx
0x180016fd3  mov     rax, [rax+8]
0x180016fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fdc  jmp     loc_180017079
0x180016fe1  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180016fe6  mov     rdi, [rax+8]
0x180016fea  mov     eax, [rdi]
0x180016fec  cmp     eax, 5
0x180016fef  jbe     loc_180017079
0x180016ff5  mov     rcx, [rdi+18h]
0x180016ff9  mov     rax, [rdi+10h]
0x180016ffd  mov     rdx, 400000000000h
0x180017007  test    rdx, rax
0x18001700a  jz      short loc_180017079
0x18001700c  mov     rax, rcx
0x18001700f  and     rax, rdx
0x180017012  cmp     rax, rcx
0x180017015  jnz     short loc_180017079
0x180017017  call    cs:__imp_GetCurrentThreadId
0x18001701d  mov     dword ptr [rsp+0F8h+SRWLock], eax
0x180017024  mov     [rsp+0F8h+arg_10], esi
0x18001702b  mov     [rsp+0F8h+arg_18], 1000000h
0x180017037  mov     r8, [rbx+110h]
0x18001703e  add     r8, 8
0x180017042  lea     rax, [rsp+0F8h+SRWLock]
0x18001704a  mov     [rsp+0F8h+var_C8], rax
0x18001704f  lea     rax, [rsp+0F8h+arg_10]
0x180017057  mov     [rsp+0F8h+var_D0], rax
0x18001705c  lea     rax, [rsp+0F8h+arg_18]
0x180017064  mov     [rsp+0F8h+var_D8], rax
0x180017069  lea     rdx, word_18007694E
0x180017070  mov     rcx, rdi
0x180017073  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017078  nop
0x180017079  lea     rcx, [rbx+120h]; this
0x180017080  cmp     dword ptr [rcx+18h], 0
0x180017084  jz      short loc_18001708C
0x180017086  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001708b  nop
0x18001708c  add     rsp, 0E0h
0x180017093  pop     rdi
0x180017094  pop     rsi
0x180017095  pop     rbx
0x180017096  retn
0x180017097  xor     edx, edx; Val
0x180017099  mov     r8d, 98h; Size
0x18001709f  lea     rcx, [rsp+0F8h+var_B8]; void *
0x1800170a4  call    memset_0
0x1800170a9  lea     rcx, [rsp+0F8h+var_B8]; this
0x1800170ae  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
