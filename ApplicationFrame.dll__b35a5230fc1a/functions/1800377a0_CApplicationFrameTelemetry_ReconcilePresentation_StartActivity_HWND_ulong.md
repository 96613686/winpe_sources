# CApplicationFrameTelemetry::ReconcilePresentation::StartActivity(HWND__ *,ulong)

- ea: `0x1800377a0`
- end: `0x1800378cc`
- name: `?StartActivity@ReconcilePresentation@CApplicationFrameTelemetry@@QEAAXPEAUHWND__@@K@Z`
- size: `300`
- prototype: `void __fastcall(CApplicationFrameTelemetry::ReconcilePresentation *__hidden this, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800376cc`

## callees

- `0x180010888`
- `0x180027c60`
- `0x180030190`
- `0x18003052c`
- `0x180032aa8`
- `0x1800377a0`
- `0x180039fec`
- `0x18003e394`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800377ed`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800377ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003783c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003783c`

## pseudocode

```c
void __fastcall CApplicationFrameTelemetry::ReconcilePresentation::StartActivity(
        CApplicationFrameTelemetry::ReconcilePresentation *this,
        HWND a2,
        int a3)
{
  int v3; // ebp
  __int64 v6; // rdi
  _DWORD *v7; // rcx
  _DWORD *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  const GUID *v11; // rcx
  DWORD v12; // [rsp+40h] [rbp-28h] BYREF
  __int64 v13[4]; // [rsp+48h] [rbp-20h] BYREF
  int v14; // [rsp+70h] [rbp+8h] BYREF
  int v15; // [rsp+88h] [rbp+20h] BYREF

  v3 = (int)a2;
  wil::ActivityBase<CApplicationFrameLogging,0,1,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v14);
  v6 = *((_QWORD *)this + 34);
  v7 = (_DWORD *)*((_QWORD *)CApplicationFrameLogging::Instance() + 1);
  if ( *v7 > 4u && (unsigned __int8)tlgKeywordOn(v7, 1) )
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  else
    *(_OWORD *)(v6 + 8) = 0;
  *(_DWORD *)v6 = 1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v14);
  v8 = (_DWORD *)*((_QWORD *)CApplicationFrameLogging::Instance() + 1);
  if ( *v8 > 4u && (unsigned __int8)tlgKeywordOn(v8, 1) )
  {
    v14 = a3;
    v15 = v3;
    CurrentThreadId = GetCurrentThreadId();
    v10 = *((_QWORD *)this + 34);
    v12 = CurrentThreadId;
    v13[0] = 0x1000000;
    if ( !*(_BYTE *)(v10 + 4) || _tlgGuidIsZero((const struct _GUID *)(v10 + 24)) )
      v11 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v8,
      (unsigned __int8 *)byte_18007EF9D,
      (const GUID *)(v10 + 8),
      v11,
      (__int64)v13,
      (__int64)&v12,
      (__int64)&v15,
      (__int64)&v14);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CApplicationFrameTelemetry::ReconcilePresentation *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800377a0  mov     [rsp+arg_8], rbx
0x1800377a5  push    rbp
0x1800377a6  push    rsi
0x1800377a7  push    rdi
0x1800377a8  sub     rsp, 50h
0x1800377ac  mov     rbp, rdx
0x1800377af  mov     esi, r8d
0x1800377b2  lea     rdx, [rsp+68h+arg_0]
0x1800377b7  mov     rbx, rcx
0x1800377ba  call    ?LockExclusive@?$ActivityBase@VCApplicationFrameLogging@@$0A@$00$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CApplicationFrameLogging,0,1,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800377bf  mov     rdi, [rbx+110h]
0x1800377c6  call    ?Instance@CApplicationFrameLogging@@KAPEAV1@XZ; CApplicationFrameLogging::Instance(void)
0x1800377cb  mov     rcx, [rax+8]
0x1800377cf  mov     eax, [rcx]
0x1800377d1  cmp     eax, 4
0x1800377d4  jbe     short loc_1800377F5
0x1800377d6  mov     edx, 1
0x1800377db  call    _tlgKeywordOn
0x1800377e0  test    al, al
0x1800377e2  jz      short loc_1800377F5
0x1800377e4  lea     rdx, [rdi+8]; ActivityId
0x1800377e8  mov     ecx, 3; ControlCode
0x1800377ed  call    cs:__imp_EventActivityIdControl
0x1800377f3  jmp     short loc_1800377FC
0x1800377f5  xorps   xmm0, xmm0
0x1800377f8  movups  xmmword ptr [rdi+8], xmm0
0x1800377fc  lea     rcx, [rsp+68h+arg_0]
0x180037801  mov     dword ptr [rdi], 1
0x180037807  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18003780c  call    ?Instance@CApplicationFrameLogging@@KAPEAV1@XZ; CApplicationFrameLogging::Instance(void)
0x180037811  mov     rdi, [rax+8]
0x180037815  mov     eax, [rdi]
0x180037817  cmp     eax, 4
0x18003781a  jbe     loc_1800378AD
0x180037820  mov     edx, 1
0x180037825  mov     rcx, rdi
0x180037828  call    _tlgKeywordOn
0x18003782d  test    al, al
0x18003782f  jz      short loc_1800378AD
0x180037831  mov     [rsp+68h+arg_0], esi
0x180037835  mov     [rsp+68h+arg_18], ebp
0x18003783c  call    cs:__imp_GetCurrentThreadId
0x180037842  mov     r8, [rbx+110h]
0x180037849  mov     [rsp+68h+var_28], eax
0x18003784d  mov     [rsp+68h+var_20], 1000000h
0x180037856  cmp     byte ptr [r8+4], 0
0x18003785b  jz      short loc_18003786A
0x18003785d  lea     rcx, [r8+18h]; struct _GUID *
0x180037861  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180037866  test    al, al
0x180037868  jz      short loc_18003786C
0x18003786a  xor     ecx, ecx
0x18003786c  lea     rax, [rsp+68h+arg_0]
0x180037871  mov     r9, rcx
0x180037874  mov     [rsp+68h+var_30], rax
0x180037879  lea     rdx, byte_18007EF9D
0x180037880  lea     rax, [rsp+68h+arg_18]
0x180037888  add     r8, 8
0x18003788c  mov     [rsp+68h+var_38], rax
0x180037891  mov     rcx, rdi
0x180037894  lea     rax, [rsp+68h+var_28]
0x180037899  mov     [rsp+68h+var_40], rax
0x18003789e  lea     rax, [rsp+68h+var_20]
0x1800378a3  mov     [rsp+68h+var_48], rax
0x1800378a8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800378ad  lea     rcx, [rbx+120h]; this
0x1800378b4  cmp     dword ptr [rcx+18h], 0
0x1800378b8  jnz     short loc_1800378BF
0x1800378ba  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800378bf  mov     rbx, [rsp+68h+arg_8]
0x1800378c4  add     rsp, 50h
0x1800378c8  pop     rdi
0x1800378c9  pop     rsi
0x1800378ca  pop     rbp
0x1800378cb  retn
```
