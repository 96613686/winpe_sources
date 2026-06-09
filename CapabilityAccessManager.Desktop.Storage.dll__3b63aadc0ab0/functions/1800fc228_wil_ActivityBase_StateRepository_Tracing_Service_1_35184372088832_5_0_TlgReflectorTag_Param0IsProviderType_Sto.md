# wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800fc228`
- end: `0x1800fc36c`
- name: `?Stop@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800f8b68`

## callees

- `0x180001e6c`
- `0x180003a40`
- `0x1800ec390`
- `0x1800f9cac`
- `0x1800f9e44`
- `0x1800fb134`
- `0x1800fc228`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fc27e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fc27e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fc2d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fc2d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // edi
  int v5; // edi
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // r9
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[168]; // [rsp+40h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v14; // [rsp+100h] [rbp+18h] BYREF

  CurrentThreadId = a2;
  wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v3 = a1[34];
  v4 = *(_DWORD *)(v3 + 248);
  if ( v4 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v10);
  }
  if ( *(int *)(v3 + 72) >= 0 )
    *(_DWORD *)(v3 + 72) = 0;
  v5 = v4 - 1;
  *(_DWORD *)(v3 + 248) = v5;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
    v6 = StateRepository::Tracing::Service::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0 && (v8 & 0x200000000000LL) == v8 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v14 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v7,
          (__int64)byte_180129BCB,
          a1[34] + 8LL,
          v9,
          (__int64)&v14,
          (__int64)&SRWLock,
          (__int64)&CurrentThreadId);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x1800fc228  mov     rax, rsp
0x1800fc22b  mov     [rax+20h], rbx
0x1800fc22f  mov     [rax+10h], edx
0x1800fc232  push    rdi
0x1800fc233  sub     rsp, 0E0h
0x1800fc23a  mov     rbx, rcx
0x1800fc23d  lea     rdx, [rax+8]
0x1800fc241  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800fc246  mov     rax, [rbx+110h]
0x1800fc24d  mov     edi, [rax+0F8h]
0x1800fc253  cmp     edi, 1
0x1800fc256  jl      loc_1800FC34F
0x1800fc25c  cmp     dword ptr [rax+48h], 0
0x1800fc260  jl      short loc_1800FC269
0x1800fc262  mov     dword ptr [rax+48h], 0
0x1800fc269  dec     edi
0x1800fc26b  mov     [rax+0F8h], edi
0x1800fc271  mov     rcx, [rsp+0E8h+SRWLock]; SRWLock
0x1800fc279  test    rcx, rcx
0x1800fc27c  jz      short loc_1800FC285
0x1800fc27e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800fc284  nop
0x1800fc285  test    edi, edi
0x1800fc287  jnz     short loc_1800FC29D
0x1800fc289  mov     rax, [rbx]
0x1800fc28c  mov     rcx, rbx
0x1800fc28f  mov     rax, [rax+8]
0x1800fc293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc298  jmp     loc_1800FC337
0x1800fc29d  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x1800fc2a2  mov     rdi, rax
0x1800fc2a5  mov     ecx, [rax]
0x1800fc2a7  cmp     ecx, 5
0x1800fc2aa  jbe     loc_1800FC337
0x1800fc2b0  mov     rax, [rax+18h]
0x1800fc2b4  mov     rcx, [rdi+10h]
0x1800fc2b8  mov     rdx, 200000000000h
0x1800fc2c2  test    rdx, rcx
0x1800fc2c5  jz      short loc_1800FC337
0x1800fc2c7  mov     rcx, rax
0x1800fc2ca  and     rcx, rdx
0x1800fc2cd  cmp     rcx, rax
0x1800fc2d0  jnz     short loc_1800FC337
0x1800fc2d2  call    cs:__imp_GetCurrentThreadId
0x1800fc2d8  mov     [rsp+0E8h+arg_8], eax
0x1800fc2df  mov     dword ptr [rsp+0E8h+SRWLock], 0
0x1800fc2ea  mov     [rsp+0E8h+arg_10], 1000000h
0x1800fc2f6  mov     r8, [rbx+110h]
0x1800fc2fd  add     r8, 8
0x1800fc301  lea     rax, [rsp+0E8h+arg_8]
0x1800fc309  mov     [rsp+0E8h+var_B8], rax
0x1800fc30e  lea     rax, [rsp+0E8h+SRWLock]
0x1800fc316  mov     [rsp+0E8h+var_C0], rax
0x1800fc31b  lea     rax, [rsp+0E8h+arg_10]
0x1800fc323  mov     [rsp+0E8h+var_C8], rax
0x1800fc328  lea     rdx, byte_180129BCB
0x1800fc32f  mov     rcx, rdi
0x1800fc332  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800fc337  mov     rcx, rbx
0x1800fc33a  mov     rbx, [rsp+0E8h+arg_18]
0x1800fc342  add     rsp, 0E0h
0x1800fc349  pop     rdi
0x1800fc34a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800fc34f  xor     edx, edx; Val
0x1800fc351  mov     r8d, 98h; Size
0x1800fc357  lea     rcx, [rsp+0E8h+var_A8]; void *
0x1800fc35c  call    memset_0
0x1800fc361  lea     rcx, [rsp+0E8h+var_A8]; this
0x1800fc366  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
