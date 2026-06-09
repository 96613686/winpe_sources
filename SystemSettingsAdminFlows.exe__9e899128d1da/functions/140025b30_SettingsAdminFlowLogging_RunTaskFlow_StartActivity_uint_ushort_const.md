# SettingsAdminFlowLogging::RunTaskFlow::StartActivity(uint,ushort const *)

- ea: `0x140025b30`
- end: `0x140025c66`
- name: `?StartActivity@RunTaskFlow@SettingsAdminFlowLogging@@QEAAXIPEBG@Z`
- size: `310`
- prototype: `void __fastcall(SettingsAdminFlowLogging::RunTaskFlow *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x14001b6c4`

## callees

- `0x140001814`
- `0x140001fcc`
- `0x14000ed94`
- `0x14001a814`
- `0x14001bd90`
- `0x140025b30`
- `0x140025c6c`
- `0x14002ad8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140025bd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140025bd3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140025b82`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140025b82`

## pseudocode

```c
void __fastcall SettingsAdminFlowLogging::RunTaskFlow::StartActivity(
        SettingsAdminFlowLogging::RunTaskFlow *this,
        int a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rbx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // rcx
  const WCHAR *v17; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18[4]; // [rsp+48h] [rbp-20h] BYREF
  RTL_SRWLOCK *v19; // [rsp+70h] [rbp+8h] BYREF
  DWORD v20; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v19);
  v6 = *((_QWORD *)this + 34);
  v7 = SettingsAdminFlowLogging::Provider();
  v9 = *(unsigned int *)v7;
  if ( (unsigned int)v9 > 5 && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v8, v9) )
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  else
    *(_OWORD *)(v6 + 8) = 0;
  *(_DWORD *)v6 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
  v10 = SettingsAdminFlowLogging::Provider();
  v13 = (__int64)v10;
  if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v11, v12) )
  {
    v17 = a3;
    LODWORD(v19) = a2;
    CurrentThreadId = GetCurrentThreadId();
    v15 = *((_QWORD *)this + 34);
    v20 = CurrentThreadId;
    v18[0] = 0x1000000;
    if ( !*(_BYTE *)(v15 + 4) || _tlgGuidIsZero((const struct _GUID *)(v15 + 24)) )
      v16 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v13,
      (__int64)&dword_1400954F4,
      v15 + 8,
      v16,
      (__int64)v18,
      (__int64)&v20,
      (__int64)&v19,
      &v17);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((SettingsAdminFlowLogging::RunTaskFlow *)((char *)this + 288));
}

```

## disassembly

```asm
0x140025b30  mov     [rsp+arg_8], rbx
0x140025b35  push    rbp
0x140025b36  push    rsi
0x140025b37  push    rdi
0x140025b38  sub     rsp, 50h
0x140025b3c  mov     ebp, edx
0x140025b3e  mov     rsi, r8
0x140025b41  lea     rdx, [rsp+68h+arg_0]
0x140025b46  mov     rdi, rcx
0x140025b49  call    ?LockExclusive@?$ActivityBase@VSettingsAdminFlowLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140025b4e  mov     rbx, [rdi+110h]
0x140025b55  call    ?Provider@SettingsAdminFlowLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsAdminFlowLogging::Provider(void)
0x140025b5a  mov     r9d, [rax]
0x140025b5d  cmp     r9d, 5
0x140025b61  jbe     short loc_140025B8A
0x140025b63  mov     rdx, 400000000000h
0x140025b6d  mov     rcx, rax
0x140025b70  call    _tlgKeywordOn
0x140025b75  test    al, al
0x140025b77  jz      short loc_140025B8A
0x140025b79  lea     rdx, [rbx+8]; ActivityId
0x140025b7d  mov     ecx, 3; ControlCode
0x140025b82  call    cs:__imp_EventActivityIdControl
0x140025b88  jmp     short loc_140025B91
0x140025b8a  xorps   xmm0, xmm0
0x140025b8d  movups  xmmword ptr [rbx+8], xmm0
0x140025b91  lea     rcx, [rsp+68h+arg_0]
0x140025b96  mov     dword ptr [rbx], 1
0x140025b9c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140025ba1  call    ?Provider@SettingsAdminFlowLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsAdminFlowLogging::Provider(void)
0x140025ba6  mov     rbx, rax
0x140025ba9  mov     ecx, [rax]
0x140025bab  cmp     ecx, 5
0x140025bae  jbe     loc_140025C47
0x140025bb4  mov     rdx, 400000000000h
0x140025bbe  mov     rcx, rax
0x140025bc1  call    _tlgKeywordOn
0x140025bc6  test    al, al
0x140025bc8  jz      short loc_140025C47
0x140025bca  mov     [rsp+68h+var_28], rsi
0x140025bcf  mov     dword ptr [rsp+68h+arg_0], ebp
0x140025bd3  call    cs:__imp_GetCurrentThreadId
0x140025bd9  mov     r8, [rdi+110h]
0x140025be0  mov     [rsp+68h+arg_18], eax
0x140025be7  mov     [rsp+68h+var_20], 1000000h
0x140025bf0  cmp     byte ptr [r8+4], 0
0x140025bf5  jz      short loc_140025C04
0x140025bf7  lea     rcx, [r8+18h]; struct _GUID *
0x140025bfb  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x140025c00  test    al, al
0x140025c02  jz      short loc_140025C06
0x140025c04  xor     ecx, ecx
0x140025c06  lea     rax, [rsp+68h+var_28]
0x140025c0b  mov     r9, rcx
0x140025c0e  mov     [rsp+68h+var_30], rax
0x140025c13  lea     rdx, dword_1400954F4
0x140025c1a  lea     rax, [rsp+68h+arg_0]
0x140025c1f  add     r8, 8
0x140025c23  mov     [rsp+68h+var_38], rax
0x140025c28  mov     rcx, rbx
0x140025c2b  lea     rax, [rsp+68h+arg_18]
0x140025c33  mov     [rsp+68h+var_40], rax
0x140025c38  lea     rax, [rsp+68h+var_20]
0x140025c3d  mov     [rsp+68h+var_48], rax
0x140025c42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x140025c47  lea     rcx, [rdi+120h]; this
0x140025c4e  cmp     dword ptr [rcx+18h], 0
0x140025c52  jnz     short loc_140025C59
0x140025c54  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140025c59  mov     rbx, [rsp+68h+arg_8]
0x140025c5e  add     rsp, 50h
0x140025c62  pop     rdi
0x140025c63  pop     rsi
0x140025c64  pop     rbp
0x140025c65  retn
```
