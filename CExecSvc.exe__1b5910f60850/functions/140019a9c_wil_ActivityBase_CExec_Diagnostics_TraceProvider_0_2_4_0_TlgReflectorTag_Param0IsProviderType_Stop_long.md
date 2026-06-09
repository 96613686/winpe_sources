# wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140019a9c`
- end: `0x140019bbe`
- name: `?Stop@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `290`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140016cc0`

## callees

- `0x140001704`
- `0x140002ecc`
- `0x14000d9f0`
- `0x14001837c`
- `0x1400186e0`
- `0x140019190`
- `0x140019a9c`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019af4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019af4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019b36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019b36`

## pseudocode

```c
void __fastcall wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r9
  const struct wil::FailureInfo *v9; // rdx
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-C8h] BYREF
  DWORD CurrentThreadId; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v13[168]; // [rsp+60h] [rbp-A8h] BYREF

  SRWLock = 0;
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v2 = a1[34];
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v9);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    v5 = CExec::Diagnostics::TraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 2) != 0 && (v7 & 2) == v7 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v12 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v6,
          (int)&byte_14002A807,
          a1[34] + 8,
          v8,
          (__int64)&v12,
          (__int64)&SRWLock,
          (__int64)&CurrentThreadId);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x140019a9c  mov     [rsp+arg_8], rbx
0x140019aa1  push    rdi
0x140019aa2  sub     rsp, 100h
0x140019aa9  mov     rbx, rcx
0x140019aac  mov     [rsp+108h+SRWLock], 0
0x140019ab5  lea     rdx, [rsp+108h+SRWLock]
0x140019aba  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140019abf  mov     rax, [rbx+110h]
0x140019ac6  mov     edi, [rax+0F8h]
0x140019acc  cmp     edi, 1
0x140019acf  jl      loc_140019BA1
0x140019ad5  cmp     dword ptr [rax+48h], 0
0x140019ad9  jl      short loc_140019AE2
0x140019adb  mov     dword ptr [rax+48h], 0
0x140019ae2  dec     edi
0x140019ae4  mov     [rax+0F8h], edi
0x140019aea  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x140019aef  test    rcx, rcx
0x140019af2  jz      short loc_140019AFA
0x140019af4  call    cs:__imp_ReleaseSRWLockExclusive
0x140019afa  test    edi, edi
0x140019afc  jnz     short loc_140019B0F
0x140019afe  mov     rax, [rbx]
0x140019b01  mov     rcx, rbx
0x140019b04  mov     rax, [rax+8]
0x140019b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019b0d  jmp     short loc_140019B89
0x140019b0f  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x140019b14  mov     rdi, rax
0x140019b17  mov     ecx, [rax]
0x140019b19  cmp     ecx, 5
0x140019b1c  jbe     short loc_140019B89
0x140019b1e  mov     rax, [rax+18h]
0x140019b22  mov     rcx, [rdi+10h]
0x140019b26  test    cl, 2
0x140019b29  jz      short loc_140019B89
0x140019b2b  mov     rcx, rax
0x140019b2e  and     ecx, 2
0x140019b31  cmp     rcx, rax
0x140019b34  jnz     short loc_140019B89
0x140019b36  call    cs:__imp_GetCurrentThreadId
0x140019b3c  mov     [rsp+108h+var_C0], eax
0x140019b40  mov     dword ptr [rsp+108h+SRWLock], 0
0x140019b48  mov     [rsp+108h+var_B8], 1000000h
0x140019b51  mov     r8, [rbx+110h]
0x140019b58  add     r8, 8
0x140019b5c  lea     rax, [rsp+108h+var_C0]
0x140019b61  mov     [rsp+108h+var_D8], rax
0x140019b66  lea     rax, [rsp+108h+SRWLock]
0x140019b6b  mov     [rsp+108h+var_E0], rax
0x140019b70  lea     rax, [rsp+108h+var_B8]
0x140019b75  mov     [rsp+108h+var_E8], rax
0x140019b7a  lea     rdx, byte_14002A807
0x140019b81  mov     rcx, rdi
0x140019b84  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140019b89  mov     rcx, rbx
0x140019b8c  mov     rbx, [rsp+108h+arg_8]
0x140019b94  add     rsp, 100h
0x140019b9b  pop     rdi
0x140019b9c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x140019ba1  xor     edx, edx; Val
0x140019ba3  mov     r8d, 98h; Size
0x140019ba9  lea     rcx, [rsp+108h+var_A8]; void *
0x140019bae  call    memset_0
0x140019bb3  lea     rcx, [rsp+108h+var_A8]; this
0x140019bb8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
