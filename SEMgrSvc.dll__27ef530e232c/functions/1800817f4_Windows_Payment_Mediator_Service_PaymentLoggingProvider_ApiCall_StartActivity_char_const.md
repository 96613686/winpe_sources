# Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall::StartActivity(char const *)

- ea: `0x1800817f4`
- end: `0x1800819bb`
- name: `?StartActivity@ApiCall@PaymentLoggingProvider@Service@Mediator@Payment@Windows@@QEAAXPEBD@Z`
- size: `455`
- prototype: `void __fastcall(Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1800806b0`

## callees

- `0x1800010f4`
- `0x1800049a0`
- `0x18000584c`
- `0x18001da08`
- `0x18001eb04`
- `0x18008079c`
- `0x180081704`
- `0x1800817f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800818bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800818bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800818df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800818df`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18008189d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18008189d`

## pseudocode

```c
void __fastcall Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall::StartActivity(
        Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall *this,
        const char *a2,
        __int64 a3)
{
  __int64 v3; // r14
  const unsigned __int16 *v4; // rbx
  size_t v5; // rdi
  char *v7; // rsi
  __int64 v8; // rdi
  RTL_SRWLOCK *v9; // rcx
  int v10; // esi
  const struct _tlgProvider_t *v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  const GUID *v14; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-39h] BYREF
  __int64 v16; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v18; // [rsp+60h] [rbp-9h]
  __int64 v19; // [rsp+68h] [rbp-1h]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+7h]
  __int64 v21; // [rsp+78h] [rbp+Fh]
  const unsigned __int16 *v22; // [rsp+80h] [rbp+17h]
  int v23; // [rsp+88h] [rbp+1Fh]
  int v24; // [rsp+8Ch] [rbp+23h]

  v3 = -1;
  v4 = (const unsigned __int16 *)((char *)this + 336);
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 > *((_QWORD *)this + 45) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV23_QEBD_K_Z_PEBD___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_D_01_AEAAAEAV01_QEBD0_Z_PEBD_Z(
      (char *)this + 336,
      v5,
      a3,
      a2);
  }
  else
  {
    if ( *((_QWORD *)this + 45) <= 0xFu )
      v7 = (char *)this + 336;
    else
      v7 = *(char **)v4;
    *((_QWORD *)this + 44) = v5;
    memmove_0(v7, a2, v5);
    v7[v5] = 0;
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v8 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)Windows::Payment::Mediator::Service::PaymentLoggingProvider::Provider() <= 5u )
    *(_OWORD *)(v8 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  v9 = SRWLock;
  v10 = 1;
  *(_DWORD *)v8 = 1;
  if ( v9 )
    ReleaseSRWLockExclusive(v9);
  v11 = Windows::Payment::Mediator::Service::PaymentLoggingProvider::Provider();
  if ( *(_DWORD *)v11 > 5u )
  {
    if ( *((_QWORD *)v4 + 3) > 0xFu )
      v4 = *(const unsigned __int16 **)v4;
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v16 = 0;
    if ( !*(_BYTE *)(v13 + 4)
      || (v14 = (const GUID *)(v13 + 24), !*(_DWORD *)(v13 + 24))
      && !*(_DWORD *)(v13 + 28)
      && !*(_DWORD *)(v13 + 32)
      && !*(_DWORD *)(v13 + 36) )
    {
      v14 = 0;
    }
    if ( v4 )
    {
      do
        ++v3;
      while ( *((_BYTE *)v4 + v3) );
      v10 = v3 + 1;
    }
    else
    {
      v4 = &word_1800A5AF2;
    }
    v22 = v4;
    p_SRWLock = &SRWLock;
    v23 = v10;
    v18 = &v16;
    v24 = 0;
    v21 = 4;
    v19 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v11,
      (unsigned __int8 *)byte_18011D6E1,
      (const GUID *)(v13 + 8),
      v14,
      5u,
      &v17);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Payment::Mediator::Service::PaymentLoggingProvider::ApiCall *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800817f4  mov     [rsp-8+arg_10], rbx
0x1800817f9  mov     [rsp-8+arg_18], rsi
0x1800817fe  push    rbp
0x1800817ff  push    rdi
0x180081800  push    r12
0x180081802  push    r14
0x180081804  push    r15
0x180081806  lea     rbp, [rsp-37h]
0x18008180b  sub     rsp, 0A0h
0x180081812  mov     rax, cs:__security_cookie
0x180081819  xor     rax, rsp
0x18008181c  mov     [rbp+57h+var_30], rax
0x180081820  or      r14, 0FFFFFFFFFFFFFFFFh
0x180081824  lea     rbx, [rcx+150h]
0x18008182b  mov     rdi, r14
0x18008182e  xor     r12d, r12d
0x180081831  mov     r15, rcx
0x180081834  inc     rdi
0x180081837  cmp     [rdx+rdi], r12b
0x18008183b  jnz     short loc_180081834
0x18008183d  cmp     rdi, [rbx+18h]
0x180081841  ja      short loc_180081867
0x180081843  cmp     qword ptr [rbx+18h], 0Fh
0x180081848  jbe     short loc_18008184F
0x18008184a  mov     rsi, [rbx]
0x18008184d  jmp     short loc_180081852
0x18008184f  mov     rsi, rbx
0x180081852  mov     r8, rdi; Size
0x180081855  mov     [rbx+10h], rdi
0x180081859  mov     rcx, rsi; void *
0x18008185c  call    memmove_0
0x180081861  mov     [rdi+rsi], r12b
0x180081865  jmp     short loc_180081875
0x180081867  mov     r9, rdx
0x18008186a  mov     rcx, rbx
0x18008186d  mov     rdx, rdi
0x180081870  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV23@QEBD_K@Z@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@D@01@AEAAAEAV01@QEBD0@Z@PEBD@Z; std::string::_Reallocate_for<`std::string::_Assign<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *>(unsigned __int64,`std::string::_Assign<char>(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *)
0x180081875  lea     rdx, [rbp+57h+SRWLock]
0x180081879  mov     rcx, r15
0x18008187c  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180081881  mov     rdi, [r15+110h]
0x180081888  call    ?Provider@PaymentLoggingProvider@Service@Mediator@Payment@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Payment::Mediator::Service::PaymentLoggingProvider::Provider(void)
0x18008188d  mov     ecx, [rax]
0x18008188f  cmp     ecx, 5
0x180081892  jbe     short loc_1800818A5
0x180081894  lea     rdx, [rdi+8]; ActivityId
0x180081898  mov     ecx, 3; ControlCode
0x18008189d  call    cs:__imp_EventActivityIdControl
0x1800818a3  jmp     short loc_1800818AC
0x1800818a5  xorps   xmm0, xmm0
0x1800818a8  movups  xmmword ptr [rdi+8], xmm0
0x1800818ac  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800818b0  mov     esi, 1
0x1800818b5  mov     [rdi], esi
0x1800818b7  test    rcx, rcx
0x1800818ba  jz      short loc_1800818C2
0x1800818bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800818c2  call    ?Provider@PaymentLoggingProvider@Service@Mediator@Payment@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Payment::Mediator::Service::PaymentLoggingProvider::Provider(void)
0x1800818c7  mov     rdi, rax
0x1800818ca  mov     ecx, [rax]
0x1800818cc  cmp     ecx, 5
0x1800818cf  jbe     loc_180081981
0x1800818d5  cmp     qword ptr [rbx+18h], 0Fh
0x1800818da  jbe     short loc_1800818DF
0x1800818dc  mov     rbx, [rbx]
0x1800818df  call    cs:__imp_GetCurrentThreadId
0x1800818e5  mov     r8, [r15+110h]
0x1800818ec  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800818ef  mov     [rbp+57h+var_88], r12
0x1800818f3  cmp     [r8+4], r12b
0x1800818f7  jz      short loc_180081914
0x1800818f9  lea     r9, [r8+18h]
0x1800818fd  cmp     [r9], r12d
0x180081900  jnz     short loc_180081917
0x180081902  cmp     [r9+4], r12d
0x180081906  jnz     short loc_180081917
0x180081908  cmp     [r9+8], r12d
0x18008190c  jnz     short loc_180081917
0x18008190e  cmp     [r9+0Ch], r12d
0x180081912  jnz     short loc_180081917
0x180081914  mov     r9, r12
0x180081917  test    rbx, rbx
0x18008191a  jz      short loc_18008192B
0x18008191c  inc     r14
0x18008191f  cmp     [rbx+r14], r12b
0x180081923  jnz     short loc_18008191C
0x180081925  lea     esi, [r14+1]
0x180081929  jmp     short loc_180081932
0x18008192b  lea     rbx, word_1800A5AF2
0x180081932  lea     rax, [rbp+57h+SRWLock]
0x180081936  mov     [rbp+57h+var_40], rbx
0x18008193a  mov     [rbp+57h+var_50], rax
0x18008193e  lea     rdx, byte_18011D6E1
0x180081945  lea     rax, [rbp+57h+var_88]
0x180081949  mov     [rbp+57h+var_38], esi
0x18008194c  mov     [rbp+57h+var_60], rax
0x180081950  add     r8, 8
0x180081954  lea     rax, [rbp+57h+var_80]
0x180081958  mov     [rbp+57h+var_34], r12d
0x18008195c  mov     [rsp+0C0h+var_98], rax
0x180081961  mov     rcx, rdi
0x180081964  mov     [rsp+0C0h+var_A0], 5
0x18008196c  mov     [rbp+57h+var_48], 4
0x180081974  mov     [rbp+57h+var_58], 8
0x18008197c  call    _tlgWriteTransfer_EventWriteTransfer
0x180081981  lea     rcx, [r15+120h]; this
0x180081988  cmp     [rcx+18h], r12d
0x18008198c  jnz     short loc_180081993
0x18008198e  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180081993  mov     rcx, [rbp+57h+var_30]
0x180081997  xor     rcx, rsp; StackCookie
0x18008199a  call    __security_check_cookie
0x18008199f  lea     r11, [rsp+0C0h+var_20]
0x1800819a7  mov     rbx, [r11+40h]
0x1800819ab  mov     rsi, [r11+48h]
0x1800819af  mov     rsp, r11
0x1800819b2  pop     r15
0x1800819b4  pop     r14
0x1800819b6  pop     r12
0x1800819b8  pop     rdi
0x1800819b9  pop     rbp
0x1800819ba  retn
```
