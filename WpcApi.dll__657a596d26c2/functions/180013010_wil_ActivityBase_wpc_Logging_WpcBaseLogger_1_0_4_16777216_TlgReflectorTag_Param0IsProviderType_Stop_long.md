# wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180013010`
- end: `0x180013123`
- name: `?Stop@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `275`
- prototype: `void __fastcall(_QWORD *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000e560`
- `0x18001312c`

## callees

- `0x1800015d0`
- `0x180003d14`
- `0x18000a4f0`
- `0x180010794`
- `0x180010810`
- `0x180010d90`
- `0x180012240`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013066`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013066`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001308b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001308b`

## pseudocode

```c
void __fastcall wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // esi
  int v6; // edi
  int v7; // esi
  const struct _tlgProvider_t *v8; // rdi
  __int64 v9; // r9
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[184]; // [rsp+40h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  int v13; // [rsp+110h] [rbp+18h] BYREF
  __int64 v14; // [rsp+118h] [rbp+20h] BYREF

  wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v4 = a1[34];
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v10);
  }
  v6 = *(_DWORD *)(v4 + 72);
  if ( v6 >= 0 )
  {
    *(_DWORD *)(v4 + 72) = a2;
    v6 = a2;
  }
  v7 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v7;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v7 )
  {
    v8 = wpc::Logging::WpcBaseLogger::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v13 = a2;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (__int64)byte_18003C143,
        a1[34] + 8LL,
        v9,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&SRWLock);
    }
  }
  else
  {
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      v6);
  }
  wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180013010  mov     rax, rsp
0x180013013  mov     [rax+10h], rbx
0x180013017  push    rbp
0x180013018  push    rsi
0x180013019  push    rdi
0x18001301a  sub     rsp, 0E0h
0x180013021  mov     ebp, edx
0x180013023  mov     rbx, rcx
0x180013026  lea     rdx, [rax+8]
0x18001302a  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001302f  mov     rax, [rbx+110h]
0x180013036  mov     esi, [rax+0F8h]
0x18001303c  cmp     esi, 1
0x18001303f  jl      loc_180013106
0x180013045  mov     edi, [rax+48h]
0x180013048  test    edi, edi
0x18001304a  js      short loc_180013051
0x18001304c  mov     [rax+48h], ebp
0x18001304f  mov     edi, ebp
0x180013051  dec     esi
0x180013053  mov     [rax+0F8h], esi
0x180013059  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x180013061  test    rcx, rcx
0x180013064  jz      short loc_18001306C
0x180013066  call    cs:__imp_ReleaseSRWLockExclusive
0x18001306c  test    esi, esi
0x18001306e  jnz     short loc_18001307C
0x180013070  mov     edx, edi
0x180013072  mov     rcx, rbx
0x180013075  call    ?ReportStopActivity@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18001307a  jmp     short loc_1800130EC
0x18001307c  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180013081  mov     rdi, rax
0x180013084  mov     ecx, [rax]
0x180013086  cmp     ecx, 5
0x180013089  jbe     short loc_1800130EC
0x18001308b  call    cs:__imp_GetCurrentThreadId
0x180013091  mov     dword ptr [rsp+0F8h+SRWLock], eax
0x180013098  mov     [rsp+0F8h+arg_10], ebp
0x18001309f  mov     [rsp+0F8h+arg_18], 1000000h
0x1800130ab  mov     r8, [rbx+110h]
0x1800130b2  add     r8, 8
0x1800130b6  lea     rax, [rsp+0F8h+SRWLock]
0x1800130be  mov     [rsp+0F8h+var_C8], rax
0x1800130c3  lea     rax, [rsp+0F8h+arg_10]
0x1800130cb  mov     [rsp+0F8h+var_D0], rax
0x1800130d0  lea     rax, [rsp+0F8h+arg_18]
0x1800130d8  mov     [rsp+0F8h+var_D8], rax
0x1800130dd  lea     rdx, byte_18003C143
0x1800130e4  mov     rcx, rdi
0x1800130e7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800130ec  mov     rcx, rbx
0x1800130ef  mov     rbx, [rsp+0F8h+arg_8]
0x1800130f7  add     rsp, 0E0h
0x1800130fe  pop     rdi
0x1800130ff  pop     rsi
0x180013100  pop     rbp
0x180013101  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180013106  xor     edx, edx; Val
0x180013108  mov     r8d, 98h; Size
0x18001310e  lea     rcx, [rsp+0F8h+var_B8]; void *
0x180013113  call    memset_0
0x180013118  lea     rcx, [rsp+0F8h+var_B8]; this
0x18001311d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
