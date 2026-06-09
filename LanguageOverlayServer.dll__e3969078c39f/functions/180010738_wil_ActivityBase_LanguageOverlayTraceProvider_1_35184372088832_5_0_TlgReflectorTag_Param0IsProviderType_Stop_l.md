# wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180010738`
- end: `0x180010889`
- name: `?Stop@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `337`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `8`
- tags: ``

## callers

- `0x18001021c`
- `0x1800129f0`
- `0x1800373fc`
- `0x180038bc0`
- `0x180039e68`
- `0x18003c680`
- `0x18003d368`
- `0x18003ed7c`

## callees

- `0x180001a78`
- `0x1800044b8`
- `0x1800085dc`
- `0x180009e70`
- `0x18000e1b8`
- `0x180010738`
- `0x180010dcc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001078e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001078e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800107e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<LanguageOverlayTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
        (__int64)&word_180075DAE,
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
0x180010738  mov     rax, rsp
0x18001073b  mov     [rax+20h], rbx
0x18001073f  mov     [rax+10h], edx
0x180010742  push    rdi
0x180010743  sub     rsp, 0E0h
0x18001074a  mov     rbx, rcx
0x18001074d  lea     rdx, [rax+8]
0x180010751  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010756  mov     rax, [rbx+110h]
0x18001075d  mov     edi, [rax+0F8h]
0x180010763  cmp     edi, 1
0x180010766  jl      loc_18001086C
0x18001076c  cmp     dword ptr [rax+48h], 0
0x180010770  jl      short loc_180010779
0x180010772  mov     dword ptr [rax+48h], 0
0x180010779  dec     edi
0x18001077b  mov     [rax+0F8h], edi
0x180010781  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x180010789  test    rcx, rcx
0x18001078c  jz      short loc_180010794
0x18001078e  call    cs:__imp_ReleaseSRWLockExclusive
0x180010794  test    edi, edi
0x180010796  jnz     short loc_1800107AC
0x180010798  mov     rax, [rbx]
0x18001079b  mov     rcx, rbx
0x18001079e  mov     rax, [rax+8]
0x1800107a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107a7  jmp     loc_180010848
0x1800107ac  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x1800107b1  mov     rdi, [rax+8]
0x1800107b5  mov     eax, [rdi]
0x1800107b7  cmp     eax, 5
0x1800107ba  jbe     loc_180010848
0x1800107c0  mov     rcx, [rdi+18h]
0x1800107c4  mov     rax, [rdi+10h]
0x1800107c8  mov     rdx, 200000000000h
0x1800107d2  test    rdx, rax
0x1800107d5  jz      short loc_180010848
0x1800107d7  mov     rax, rcx
0x1800107da  and     rax, rdx
0x1800107dd  cmp     rax, rcx
0x1800107e0  jnz     short loc_180010848
0x1800107e2  call    cs:__imp_GetCurrentThreadId
0x1800107e8  mov     [rsp+0E8h+arg_8], eax
0x1800107ef  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x1800107fa  mov     [rsp+0E8h+arg_10], 1000000h
0x180010806  mov     r8, [rbx+110h]
0x18001080d  add     r8, 8
0x180010811  lea     rax, [rsp+0E8h+arg_8]
0x180010819  mov     [rsp+0E8h+var_B8], rax
0x18001081e  lea     rax, [rsp+0E8h+SRWLock]
0x180010826  mov     [rsp+0E8h+var_C0], rax
0x18001082b  lea     rax, [rsp+0E8h+arg_10]
0x180010833  mov     [rsp+0E8h+var_C8], rax
0x180010838  lea     rdx, word_180075DAE
0x18001083f  mov     rcx, rdi
0x180010842  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010847  nop
0x180010848  lea     rcx, [rbx+120h]; this
0x18001084f  cmp     dword ptr [rcx+18h], 0
0x180010853  jz      short loc_18001085B
0x180010855  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001085a  nop
0x18001085b  mov     rbx, [rsp+0E8h+arg_18]
0x180010863  add     rsp, 0E0h
0x18001086a  pop     rdi
0x18001086b  retn
0x18001086c  xor     edx, edx; Val
0x18001086e  mov     r8d, 98h; Size
0x180010874  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180010879  call    memset_0
0x18001087e  lea     rcx, [rsp+0E8h+var_A8]; this
0x180010883  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
