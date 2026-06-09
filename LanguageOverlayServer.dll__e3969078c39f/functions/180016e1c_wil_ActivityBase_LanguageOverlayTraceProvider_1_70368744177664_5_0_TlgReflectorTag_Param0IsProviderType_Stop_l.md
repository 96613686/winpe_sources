# wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180016e1c`
- end: `0x180016f6d`
- name: `?Stop@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `337`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x1800180d8`
- `0x180019390`
- `0x180019570`
- `0x1800197f0`
- `0x180019b40`
- `0x18004c500`
- `0x18004e370`

## callees

- `0x180001a78`
- `0x1800044b8`
- `0x1800085dc`
- `0x180009e70`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180016e1c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016e72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016ec6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016ec6`

## pseudocode

```c
void __fastcall wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // edi
  int v5; // edi
  __int64 v6; // rdi
  __int64 v7; // r9
  const struct wil::FailureInfo *v8; // rdx
  _BYTE v9[168]; // [rsp+40h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v12; // [rsp+100h] [rbp+18h] BYREF

  CurrentThreadId = a2;
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v3 = *(_QWORD *)(a1 + 272);
  v4 = *(_DWORD *)(v3 + 248);
  if ( v4 < 1 )
  {
    memset_0(v9, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v9, v8);
  }
  if ( *(int *)(v3 + 72) >= 0 )
    *(_DWORD *)(v3 + 72) = 0;
  v5 = v4 - 1;
  *(_DWORD *)(v3 + 248) = v5;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
    v6 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&unk_1800766A8,
        *(_QWORD *)(a1 + 272) + 8LL,
        v7,
        (__int64)&v12,
        (__int64)&SRWLock,
        (__int64)&CurrentThreadId);
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
0x180016e1c  mov     rax, rsp
0x180016e1f  mov     [rax+20h], rbx
0x180016e23  mov     [rax+10h], edx
0x180016e26  push    rdi
0x180016e27  sub     rsp, 0E0h
0x180016e2e  mov     rbx, rcx
0x180016e31  lea     rdx, [rax+8]
0x180016e35  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016e3a  mov     rax, [rbx+110h]
0x180016e41  mov     edi, [rax+0F8h]
0x180016e47  cmp     edi, 1
0x180016e4a  jl      loc_180016F50
0x180016e50  cmp     dword ptr [rax+48h], 0
0x180016e54  jl      short loc_180016E5D
0x180016e56  mov     dword ptr [rax+48h], 0
0x180016e5d  dec     edi
0x180016e5f  mov     [rax+0F8h], edi
0x180016e65  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x180016e6d  test    rcx, rcx
0x180016e70  jz      short loc_180016E78
0x180016e72  call    cs:__imp_ReleaseSRWLockExclusive
0x180016e78  test    edi, edi
0x180016e7a  jnz     short loc_180016E90
0x180016e7c  mov     rax, [rbx]
0x180016e7f  mov     rcx, rbx
0x180016e82  mov     rax, [rax+8]
0x180016e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e8b  jmp     loc_180016F2C
0x180016e90  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180016e95  mov     rdi, [rax+8]
0x180016e99  mov     eax, [rdi]
0x180016e9b  cmp     eax, 5
0x180016e9e  jbe     loc_180016F2C
0x180016ea4  mov     rcx, [rdi+18h]
0x180016ea8  mov     rax, [rdi+10h]
0x180016eac  mov     rdx, 400000000000h
0x180016eb6  test    rdx, rax
0x180016eb9  jz      short loc_180016F2C
0x180016ebb  mov     rax, rcx
0x180016ebe  and     rax, rdx
0x180016ec1  cmp     rax, rcx
0x180016ec4  jnz     short loc_180016F2C
0x180016ec6  call    cs:__imp_GetCurrentThreadId
0x180016ecc  mov     [rsp+0E8h+arg_8], eax
0x180016ed3  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x180016ede  mov     [rsp+0E8h+arg_10], 1000000h
0x180016eea  mov     r8, [rbx+110h]
0x180016ef1  add     r8, 8
0x180016ef5  lea     rax, [rsp+0E8h+arg_8]
0x180016efd  mov     [rsp+0E8h+var_B8], rax
0x180016f02  lea     rax, [rsp+0E8h+SRWLock]
0x180016f0a  mov     [rsp+0E8h+var_C0], rax
0x180016f0f  lea     rax, [rsp+0E8h+arg_10]
0x180016f17  mov     [rsp+0E8h+var_C8], rax
0x180016f1c  lea     rdx, unk_1800766A8
0x180016f23  mov     rcx, rdi
0x180016f26  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016f2b  nop
0x180016f2c  lea     rcx, [rbx+120h]; this
0x180016f33  cmp     dword ptr [rcx+18h], 0
0x180016f37  jz      short loc_180016F3F
0x180016f39  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180016f3e  nop
0x180016f3f  mov     rbx, [rsp+0E8h+arg_18]
0x180016f47  add     rsp, 0E0h
0x180016f4e  pop     rdi
0x180016f4f  retn
0x180016f50  xor     edx, edx; Val
0x180016f52  mov     r8d, 98h; Size
0x180016f58  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180016f5d  call    memset_0
0x180016f62  lea     rcx, [rsp+0E8h+var_A8]; this
0x180016f67  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
