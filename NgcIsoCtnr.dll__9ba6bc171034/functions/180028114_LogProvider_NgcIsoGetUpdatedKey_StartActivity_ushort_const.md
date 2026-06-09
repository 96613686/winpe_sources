# LogProvider::NgcIsoGetUpdatedKey::StartActivity(ushort const *)

- ea: `0x180028114`
- end: `0x180028227`
- name: `?StartActivity@NgcIsoGetUpdatedKey@LogProvider@@QEAAXPEBG@Z`
- size: `275`
- prototype: `void __fastcall(LogProvider::NgcIsoGetUpdatedKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180026754`

## callees

- `0x1800019bc`
- `0x180003020`
- `0x18000a168`
- `0x18001133c`
- `0x180015108`
- `0x180016374`
- `0x180016828`
- `0x180028114`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800281a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800281a9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180028160`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180028160`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetUpdatedKey::StartActivity(
        LogProvider::NgcIsoGetUpdatedKey *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // ecx
  DWORD v15; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *v16; // [rsp+70h] [rbp+18h] BYREF
  __int64 v17; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v15);
  v4 = *((_QWORD *)this + 34);
  v5 = LogProvider::Provider();
  v7 = *(unsigned int *)v5;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v5, 0x800000000000LL, v7, v6) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  v8 = LogProvider::Provider();
  v11 = (int)v8;
  if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x800000000000LL, v9, v10) )
  {
    v16 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    v15 = CurrentThreadId;
    v17 = 0x1000000;
    if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v11,
      (unsigned int)&byte_1800AAA27,
      v13 + 8,
      v14,
      (__int64)&v17,
      (__int64)&v15,
      (__int64)&v16);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((LogProvider::NgcIsoGetUpdatedKey *)((char *)this + 288));
}

```

## disassembly

```asm
0x180028114  push    rbx
0x180028116  push    rsi
0x180028117  push    rdi
0x180028118  sub     rsp, 40h
0x18002811c  mov     rsi, rdx
0x18002811f  mov     rbx, rcx
0x180028122  lea     rdx, [rsp+58h+arg_0]
0x180028127  call    ?LockExclusive@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002812c  mov     rdi, [rbx+110h]
0x180028133  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x180028138  mov     r8d, [rax]
0x18002813b  cmp     r8d, 5
0x18002813f  jbe     short loc_180028168
0x180028141  mov     rdx, 800000000000h
0x18002814b  mov     rcx, rax
0x18002814e  call    _tlgKeywordOn
0x180028153  test    al, al
0x180028155  jz      short loc_180028168
0x180028157  lea     rdx, [rdi+8]; ActivityId
0x18002815b  mov     ecx, 3; ControlCode
0x180028160  call    cs:__imp_EventActivityIdControl
0x180028166  jmp     short loc_18002816F
0x180028168  xorps   xmm0, xmm0
0x18002816b  movups  xmmword ptr [rdi+8], xmm0
0x18002816f  lea     rcx, [rsp+58h+arg_0]
0x180028174  mov     dword ptr [rdi], 1
0x18002817a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002817f  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x180028184  mov     rdi, rax
0x180028187  mov     ecx, [rax]
0x180028189  cmp     ecx, 5
0x18002818c  jbe     short loc_18002820D
0x18002818e  mov     rdx, 800000000000h
0x180028198  mov     rcx, rax
0x18002819b  call    _tlgKeywordOn
0x1800281a0  test    al, al
0x1800281a2  jz      short loc_18002820D
0x1800281a4  mov     [rsp+58h+arg_10], rsi
0x1800281a9  call    cs:__imp_GetCurrentThreadId
0x1800281af  mov     r8, [rbx+110h]
0x1800281b6  mov     [rsp+58h+arg_0], eax
0x1800281ba  mov     [rsp+58h+arg_18], 1000000h
0x1800281c3  cmp     byte ptr [r8+4], 0
0x1800281c8  jz      short loc_1800281D7
0x1800281ca  lea     rcx, [r8+18h]; struct _GUID *
0x1800281ce  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800281d3  test    al, al
0x1800281d5  jz      short loc_1800281D9
0x1800281d7  xor     ecx, ecx
0x1800281d9  lea     rax, [rsp+58h+arg_10]
0x1800281de  mov     r9, rcx
0x1800281e1  mov     [rsp+58h+var_28], rax
0x1800281e6  lea     rdx, byte_1800AAA27
0x1800281ed  lea     rax, [rsp+58h+arg_0]
0x1800281f2  add     r8, 8
0x1800281f6  mov     [rsp+58h+var_30], rax
0x1800281fb  mov     rcx, rdi
0x1800281fe  lea     rax, [rsp+58h+arg_18]
0x180028203  mov     [rsp+58h+var_38], rax
0x180028208  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002820d  lea     rcx, [rbx+120h]; this
0x180028214  cmp     dword ptr [rcx+18h], 0
0x180028218  jnz     short loc_18002821F
0x18002821a  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002821f  add     rsp, 40h
0x180028223  pop     rdi
0x180028224  pop     rsi
0x180028225  pop     rbx
0x180028226  retn
```
