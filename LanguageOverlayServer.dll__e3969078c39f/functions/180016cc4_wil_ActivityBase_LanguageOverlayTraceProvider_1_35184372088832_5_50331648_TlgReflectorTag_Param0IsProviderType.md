# wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180016cc4`
- end: `0x180016e15`
- name: `?Stop@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0CAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `337`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x1800179d8`
- `0x1800192c0`
- `0x180019490`
- `0x180019a20`

## callees

- `0x180001a78`
- `0x1800044b8`
- `0x1800085dc`
- `0x180009e70`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180016cc4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016d1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016d1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d6e`

## pseudocode

```c
void __fastcall wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
      && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&dword_180076BF4,
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
0x180016cc4  mov     rax, rsp
0x180016cc7  mov     [rax+20h], rbx
0x180016ccb  mov     [rax+10h], edx
0x180016cce  push    rdi
0x180016ccf  sub     rsp, 0E0h
0x180016cd6  mov     rbx, rcx
0x180016cd9  lea     rdx, [rax+8]
0x180016cdd  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016ce2  mov     rax, [rbx+110h]
0x180016ce9  mov     edi, [rax+0F8h]
0x180016cef  cmp     edi, 1
0x180016cf2  jl      loc_180016DF8
0x180016cf8  cmp     dword ptr [rax+48h], 0
0x180016cfc  jl      short loc_180016D05
0x180016cfe  mov     dword ptr [rax+48h], 0
0x180016d05  dec     edi
0x180016d07  mov     [rax+0F8h], edi
0x180016d0d  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x180016d15  test    rcx, rcx
0x180016d18  jz      short loc_180016D20
0x180016d1a  call    cs:__imp_ReleaseSRWLockExclusive
0x180016d20  test    edi, edi
0x180016d22  jnz     short loc_180016D38
0x180016d24  mov     rax, [rbx]
0x180016d27  mov     rcx, rbx
0x180016d2a  mov     rax, [rax+8]
0x180016d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d33  jmp     loc_180016DD4
0x180016d38  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180016d3d  mov     rdi, [rax+8]
0x180016d41  mov     eax, [rdi]
0x180016d43  cmp     eax, 5
0x180016d46  jbe     loc_180016DD4
0x180016d4c  mov     rcx, [rdi+18h]
0x180016d50  mov     rax, [rdi+10h]
0x180016d54  mov     rdx, 200000000000h
0x180016d5e  test    rdx, rax
0x180016d61  jz      short loc_180016DD4
0x180016d63  mov     rax, rcx
0x180016d66  and     rax, rdx
0x180016d69  cmp     rax, rcx
0x180016d6c  jnz     short loc_180016DD4
0x180016d6e  call    cs:__imp_GetCurrentThreadId
0x180016d74  mov     [rsp+0E8h+arg_8], eax
0x180016d7b  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x180016d86  mov     [rsp+0E8h+arg_10], 1000000h
0x180016d92  mov     r8, [rbx+110h]
0x180016d99  add     r8, 8
0x180016d9d  lea     rax, [rsp+0E8h+arg_8]
0x180016da5  mov     [rsp+0E8h+var_B8], rax
0x180016daa  lea     rax, [rsp+0E8h+SRWLock]
0x180016db2  mov     [rsp+0E8h+var_C0], rax
0x180016db7  lea     rax, [rsp+0E8h+arg_10]
0x180016dbf  mov     [rsp+0E8h+var_C8], rax
0x180016dc4  lea     rdx, dword_180076BF4
0x180016dcb  mov     rcx, rdi
0x180016dce  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016dd3  nop
0x180016dd4  lea     rcx, [rbx+120h]; this
0x180016ddb  cmp     dword ptr [rcx+18h], 0
0x180016ddf  jz      short loc_180016DE7
0x180016de1  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180016de6  nop
0x180016de7  mov     rbx, [rsp+0E8h+arg_18]
0x180016def  add     rsp, 0E0h
0x180016df6  pop     rdi
0x180016df7  retn
0x180016df8  xor     edx, edx; Val
0x180016dfa  mov     r8d, 98h; Size
0x180016e00  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180016e05  call    memset_0
0x180016e0a  lea     rcx, [rsp+0E8h+var_A8]; this
0x180016e0f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
