# wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001afd4`
- end: `0x18001b107`
- name: `?Stop@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180018d3c`
- `0x180024bbc`

## callees

- `0x180001e18`
- `0x180005bbc`
- `0x18000ca20`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x18001afd4`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b023`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b077`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b077`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  __int64 v7; // rdi
  int v8; // r9d
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[184]; // [rsp+40h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  int v12; // [rsp+110h] [rbp+18h] BYREF
  __int64 v13; // [rsp+118h] [rbp+20h] BYREF

  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = a1[34];
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
    v7 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v12 = a2;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&unk_1800926E1,
        a1[34] + 8,
        v8,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&SRWLock);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18001afd4  mov     rax, rsp
0x18001afd7  push    rbx
0x18001afd8  push    rsi
0x18001afd9  push    rdi
0x18001afda  sub     rsp, 0E0h
0x18001afe1  mov     esi, edx
0x18001afe3  mov     rbx, rcx
0x18001afe6  lea     rdx, [rax+8]
0x18001afea  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001afef  mov     rax, [rbx+110h]
0x18001aff6  mov     edi, [rax+0F8h]
0x18001affc  cmp     edi, 1
0x18001afff  jl      loc_18001B0EA
0x18001b005  cmp     dword ptr [rax+48h], 0
0x18001b009  jl      short loc_18001B00E
0x18001b00b  mov     [rax+48h], esi
0x18001b00e  dec     edi
0x18001b010  mov     [rax+0F8h], edi
0x18001b016  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x18001b01e  test    rcx, rcx
0x18001b021  jz      short loc_18001B029
0x18001b023  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b029  test    edi, edi
0x18001b02b  jnz     short loc_18001B041
0x18001b02d  mov     rax, [rbx]
0x18001b030  mov     rcx, rbx
0x18001b033  mov     rax, [rax+8]
0x18001b037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b03c  jmp     loc_18001B0D8
0x18001b041  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001b046  mov     rdi, [rax+8]
0x18001b04a  mov     eax, [rdi]
0x18001b04c  cmp     eax, 5
0x18001b04f  jbe     loc_18001B0D8
0x18001b055  mov     rcx, [rdi+18h]
0x18001b059  mov     rax, [rdi+10h]
0x18001b05d  mov     rdx, 400000000000h
0x18001b067  test    rdx, rax
0x18001b06a  jz      short loc_18001B0D8
0x18001b06c  mov     rax, rcx
0x18001b06f  and     rax, rdx
0x18001b072  cmp     rax, rcx
0x18001b075  jnz     short loc_18001B0D8
0x18001b077  call    cs:__imp_GetCurrentThreadId
0x18001b07d  mov     dword ptr [rsp+0F8h+SRWLock], eax
0x18001b084  mov     [rsp+0F8h+arg_10], esi
0x18001b08b  mov     [rsp+0F8h+arg_18], 1000000h
0x18001b097  mov     r8, [rbx+110h]
0x18001b09e  add     r8, 8
0x18001b0a2  lea     rax, [rsp+0F8h+SRWLock]
0x18001b0aa  mov     [rsp+0F8h+var_C8], rax
0x18001b0af  lea     rax, [rsp+0F8h+arg_10]
0x18001b0b7  mov     [rsp+0F8h+var_D0], rax
0x18001b0bc  lea     rax, [rsp+0F8h+arg_18]
0x18001b0c4  mov     [rsp+0F8h+var_D8], rax
0x18001b0c9  lea     rdx, unk_1800926E1
0x18001b0d0  mov     rcx, rdi
0x18001b0d3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001b0d8  mov     rcx, rbx
0x18001b0db  add     rsp, 0E0h
0x18001b0e2  pop     rdi
0x18001b0e3  pop     rsi
0x18001b0e4  pop     rbx
0x18001b0e5  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001b0ea  xor     edx, edx; Val
0x18001b0ec  mov     r8d, 98h; Size
0x18001b0f2  lea     rcx, [rsp+0F8h+var_B8]; void *
0x18001b0f7  call    memset_0
0x18001b0fc  lea     rcx, [rsp+0F8h+var_B8]; this
0x18001b101  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
