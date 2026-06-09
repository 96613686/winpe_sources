# CloudExperienceHostSpeechTelemetry::SpeechRecoActivity::StartActivity(void)

- ea: `0x1800945a8`
- end: `0x18009470c`
- name: `?StartActivity@SpeechRecoActivity@CloudExperienceHostSpeechTelemetry@@QEAAXXZ`
- size: `356`
- prototype: `void __fastcall(CloudExperienceHostSpeechTelemetry::SpeechRecoActivity *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180082e20`

## callees

- `0x18000170c`
- `0x180001738`
- `0x1800193a8`
- `0x18001a540`
- `0x1800926e8`
- `0x180092de8`
- `0x1800945a8`
- `0x180094714`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18009460b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18009460b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094656`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094656`

## pseudocode

```c
void __fastcall CloudExperienceHostSpeechTelemetry::SpeechRecoActivity::StartActivity(
        CloudExperienceHostSpeechTelemetry::SpeechRecoActivity *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rbx
  __int64 v8; // r8
  const GUID *v9; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-9h] BYREF
  __int64 v11; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v13; // [rsp+60h] [rbp+27h]
  __int64 v14; // [rsp+68h] [rbp+2Fh]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp+37h]
  __int64 v16; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<SpeechLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = SpeechLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x800000000000LL, v4) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v5 = SpeechLogging::Provider();
  v7 = (__int64)v5;
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x800000000000LL, v6) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    v8 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v8 + 4)
      || (v9 = (const GUID *)(v8 + 24), !*(_DWORD *)(v8 + 24))
      && !*(_DWORD *)(v8 + 28)
      && !*(_DWORD *)(v8 + 32)
      && !*(_DWORD *)(v8 + 36) )
    {
      v9 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v16 = 4;
    v13 = &v11;
    v14 = 8;
    tlgWriteTransfer_EventWriteTransfer(v7, (unsigned __int8 *)word_18010BF62, (const GUID *)(v8 + 8), v9, 4u, &v12);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CloudExperienceHostSpeechTelemetry::SpeechRecoActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800945a8  mov     [rsp-8+arg_8], rbx
0x1800945ad  mov     [rsp-8+arg_10], rdi
0x1800945b2  push    rbp
0x1800945b3  lea     rbp, [rsp-57h]
0x1800945b8  sub     rsp, 90h
0x1800945bf  mov     rax, cs:__security_cookie
0x1800945c6  xor     rax, rsp
0x1800945c9  mov     [rbp+57h+var_10], rax
0x1800945cd  mov     rdi, rcx
0x1800945d0  lea     rdx, [rbp+57h+var_60]
0x1800945d4  call    ?LockExclusive@?$ActivityBase@VSpeechLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SpeechLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800945d9  mov     rbx, [rdi+110h]
0x1800945e0  call    ?Provider@SpeechLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechLogging::Provider(void)
0x1800945e5  mov     edx, [rax]
0x1800945e7  cmp     edx, 5
0x1800945ea  jbe     short loc_180094613
0x1800945ec  mov     rdx, 800000000000h
0x1800945f6  mov     rcx, rax
0x1800945f9  call    _tlgKeywordOn
0x1800945fe  test    al, al
0x180094600  jz      short loc_180094613
0x180094602  lea     rdx, [rbx+8]; ActivityId
0x180094606  mov     ecx, 3; ControlCode
0x18009460b  call    cs:__imp_EventActivityIdControl
0x180094611  jmp     short loc_18009461A
0x180094613  xorps   xmm0, xmm0
0x180094616  movups  xmmword ptr [rbx+8], xmm0
0x18009461a  mov     dword ptr [rbx], 1
0x180094620  lea     rcx, [rbp+57h+var_60]
0x180094624  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180094629  call    ?Provider@SpeechLogging@@SAPEBU_tlgProvider_t@@XZ; SpeechLogging::Provider(void)
0x18009462e  mov     rbx, rax
0x180094631  mov     ecx, [rax]
0x180094633  cmp     ecx, 5
0x180094636  jbe     loc_1800946D8
0x18009463c  mov     rdx, 800000000000h
0x180094646  mov     rcx, rax
0x180094649  call    _tlgKeywordOn
0x18009464e  test    al, al
0x180094650  jz      loc_1800946D8
0x180094656  call    cs:__imp_GetCurrentThreadId
0x18009465c  mov     [rbp+57h+var_60], eax
0x18009465f  mov     [rbp+57h+var_58], 0
0x180094667  mov     r8, [rdi+110h]
0x18009466e  cmp     byte ptr [r8+4], 0
0x180094673  jz      short loc_180094694
0x180094675  lea     r9, [r8+18h]
0x180094679  cmp     dword ptr [r9], 0
0x18009467d  jnz     short loc_180094697
0x18009467f  cmp     dword ptr [r9+4], 0
0x180094684  jnz     short loc_180094697
0x180094686  cmp     dword ptr [r9+8], 0
0x18009468b  jnz     short loc_180094697
0x18009468d  cmp     dword ptr [r9+0Ch], 0
0x180094692  jnz     short loc_180094697
0x180094694  xor     r9d, r9d
0x180094697  lea     rax, [rbp+57h+var_60]
0x18009469b  mov     [rbp+57h+var_20], rax
0x18009469f  mov     ecx, 4
0x1800946a4  mov     [rbp+57h+var_18], rcx
0x1800946a8  lea     rax, [rbp+57h+var_58]
0x1800946ac  mov     [rbp+57h+var_30], rax
0x1800946b0  mov     [rbp+57h+var_28], 8
0x1800946b8  add     r8, 8
0x1800946bc  lea     rax, [rbp+57h+var_50]
0x1800946c0  mov     [rsp+90h+var_68], rax
0x1800946c5  mov     [rsp+90h+var_70], ecx
0x1800946c9  lea     rdx, word_18010BF62
0x1800946d0  mov     rcx, rbx
0x1800946d3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800946d8  lea     rcx, [rdi+120h]; this
0x1800946df  cmp     dword ptr [rcx+18h], 0
0x1800946e3  jnz     short loc_1800946EB
0x1800946e5  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800946ea  nop
0x1800946eb  mov     rcx, [rbp+57h+var_10]
0x1800946ef  xor     rcx, rsp; StackCookie
0x1800946f2  call    __security_check_cookie
0x1800946f7  lea     r11, [rsp+90h+var_s0]
0x1800946ff  mov     rbx, [r11+18h]
0x180094703  mov     rdi, [r11+20h]
0x180094707  mov     rsp, r11
0x18009470a  pop     rbp
0x18009470b  retn
```
