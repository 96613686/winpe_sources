# SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime::StartActivity(unsigned __int64,bool)

- ea: `0x140018dc4`
- end: `0x140018fa8`
- name: `?StartActivity@LifeTime@ActivityContainer@1SpeechOneSettingsTelemetry@@QEAAX_K_N@Z`
- size: `484`
- prototype: `void __fastcall(SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime *this, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140018fb0`

## callees

- `0x14000176c`
- `0x140002600`
- `0x1400068f0`
- `0x140018050`
- `0x140018914`
- `0x140018dc4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140018e42`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140018e42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140018e63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140018e63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018ea4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018f72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018ea4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140018f72`

## pseudocode

```c
void __fastcall SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime::StartActivity(
        SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime *this,
        __int64 a2,
        char a3)
{
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  RTL_SRWLOCK *v8; // rcx
  const struct _tlgProvider_t *v9; // rax
  const struct _tlgProvider_t *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  char *v16; // rbx
  _QWORD *Local; // rax
  char v18; // [rsp+30h] [rbp-59h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-51h] BYREF
  __int64 v20; // [rsp+40h] [rbp-49h] BYREF
  __int64 v21; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v23; // [rsp+70h] [rbp-19h]
  __int64 v24; // [rsp+78h] [rbp-11h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-9h]
  __int64 v26; // [rsp+88h] [rbp-1h]
  __int64 *v27; // [rsp+90h] [rbp+7h]
  __int64 v28; // [rsp+98h] [rbp+Fh]
  char *v29; // [rsp+A0h] [rbp+17h]
  __int64 v30; // [rsp+A8h] [rbp+1Fh]

  wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v6 = *((_QWORD *)this + 34);
  v7 = FlightDataRecorderActivityClass::Provider();
  if ( *(_DWORD *)v7 > 5u
    && (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v7 + 3) & 0x400000000000LL) == *((_QWORD *)v7 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  }
  else
  {
    *(_OWORD *)(v6 + 8) = 0;
  }
  v8 = SRWLock;
  *(_DWORD *)v6 = 1;
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  v9 = FlightDataRecorderActivityClass::Provider();
  v10 = v9;
  v11 = *(unsigned int *)v9;
  if ( (unsigned int)v11 > 5 )
  {
    v12 = *((_QWORD *)v9 + 3);
    v11 = *((_QWORD *)v10 + 2);
    if ( (v11 & 0x400000000000LL) != 0 )
    {
      v11 = v12 & 0x400000000000LL;
      if ( (v12 & 0x400000000000LL) == v12 )
      {
        v18 = a3;
        v20 = a2;
        CurrentThreadId = GetCurrentThreadId();
        v14 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v21 = 0;
        if ( !*(_BYTE *)(v14 + 4)
          || (v15 = v14 + 24, !*(_DWORD *)(v14 + 24))
          && !*(_DWORD *)(v14 + 28)
          && !*(_DWORD *)(v14 + 32)
          && !*(_DWORD *)(v14 + 36) )
        {
          v15 = 0;
        }
        v30 = 1;
        v29 = &v18;
        v28 = 8;
        v27 = &v20;
        v26 = 4;
        p_SRWLock = &SRWLock;
        v24 = 8;
        v23 = &v21;
        tlgWriteTransfer_EventWriteTransfer(v10, &word_14002A7F6, v14 + 8, v15, 6, v22);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v16 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v11,
                          1);
      *(_QWORD *)v16 = Local;
      if ( Local )
      {
        *((_QWORD *)v16 + 2) = *Local;
        *Local = v16;
        *((_DWORD *)v16 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v16 = 0;
    }
  }
}

```

## disassembly

```asm
0x140018dc4  mov     [rsp-8+arg_8], rbx
0x140018dc9  mov     [rsp-8+arg_10], rsi
0x140018dce  push    rbp
0x140018dcf  push    rdi
0x140018dd0  push    r12
0x140018dd2  push    r14
0x140018dd4  push    r15
0x140018dd6  lea     rbp, [rsp-37h]
0x140018ddb  sub     rsp, 0C0h
0x140018de2  mov     rax, cs:__security_cookie
0x140018de9  xor     rax, rsp
0x140018dec  mov     [rbp+57h+var_30], rax
0x140018df0  mov     r14, rdx
0x140018df3  mov     sil, r8b
0x140018df6  lea     rdx, [rbp+57h+SRWLock]
0x140018dfa  mov     rbx, rcx
0x140018dfd  call    ?LockExclusive@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140018e02  mov     rdi, [rbx+110h]
0x140018e09  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x140018e0e  mov     r12, 400000000000h
0x140018e18  mov     r9d, [rax]
0x140018e1b  cmp     r9d, 5
0x140018e1f  jbe     short loc_140018E4A
0x140018e21  mov     rcx, [rax+18h]
0x140018e25  mov     rax, [rax+10h]
0x140018e29  test    r12, rax
0x140018e2c  jz      short loc_140018E4A
0x140018e2e  mov     rax, rcx
0x140018e31  and     rax, r12
0x140018e34  cmp     rax, rcx
0x140018e37  jnz     short loc_140018E4A
0x140018e39  lea     rdx, [rdi+8]; ActivityId
0x140018e3d  mov     ecx, 3; ControlCode
0x140018e42  call    cs:__imp_EventActivityIdControl
0x140018e48  jmp     short loc_140018E51
0x140018e4a  xorps   xmm0, xmm0
0x140018e4d  movups  xmmword ptr [rdi+8], xmm0
0x140018e51  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140018e55  xor     r15d, r15d
0x140018e58  mov     dword ptr [rdi], 1
0x140018e5e  test    rcx, rcx
0x140018e61  jz      short loc_140018E69
0x140018e63  call    cs:__imp_ReleaseSRWLockExclusive
0x140018e69  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x140018e6e  mov     rdi, rax
0x140018e71  mov     ecx, [rax]
0x140018e73  cmp     ecx, 5
0x140018e76  jbe     loc_140018F40
0x140018e7c  mov     rax, [rax+18h]
0x140018e80  mov     rcx, [rdi+10h]
0x140018e84  test    r12, rcx
0x140018e87  jz      loc_140018F40
0x140018e8d  mov     rcx, rax
0x140018e90  and     rcx, r12
0x140018e93  cmp     rcx, rax
0x140018e96  jnz     loc_140018F40
0x140018e9c  mov     [rbp+57h+var_B0], sil
0x140018ea0  mov     [rbp+57h+var_A0], r14
0x140018ea4  call    cs:__imp_GetCurrentThreadId
0x140018eaa  mov     r8, [rbx+110h]
0x140018eb1  mov     dword ptr [rbp+57h+SRWLock], eax
0x140018eb4  mov     [rbp+57h+var_98], r15
0x140018eb8  cmp     [r8+4], r15b
0x140018ebc  jz      short loc_140018ED9
0x140018ebe  lea     r9, [r8+18h]
0x140018ec2  cmp     [r9], r15d
0x140018ec5  jnz     short loc_140018EDC
0x140018ec7  cmp     [r9+4], r15d
0x140018ecb  jnz     short loc_140018EDC
0x140018ecd  cmp     [r9+8], r15d
0x140018ed1  jnz     short loc_140018EDC
0x140018ed3  cmp     [r9+0Ch], r15d
0x140018ed7  jnz     short loc_140018EDC
0x140018ed9  mov     r9, r15
0x140018edc  lea     rax, [rbp+57h+var_B0]
0x140018ee0  mov     [rbp+57h+var_38], 1
0x140018ee8  mov     [rbp+57h+var_40], rax
0x140018eec  lea     rdx, word_14002A7F6
0x140018ef3  lea     rax, [rbp+57h+var_A0]
0x140018ef7  mov     [rbp+57h+var_48], 8
0x140018eff  mov     [rbp+57h+var_50], rax
0x140018f03  add     r8, 8
0x140018f07  lea     rax, [rbp+57h+SRWLock]
0x140018f0b  mov     [rbp+57h+var_58], 4
0x140018f13  mov     [rbp+57h+var_60], rax
0x140018f17  mov     rcx, rdi
0x140018f1a  lea     rax, [rbp+57h+var_98]
0x140018f1e  mov     [rbp+57h+var_68], 8
0x140018f26  mov     [rbp+57h+var_70], rax
0x140018f2a  lea     rax, [rbp+57h+var_90]
0x140018f2e  mov     [rsp+0E0h+var_B8], rax
0x140018f33  mov     [rsp+0E0h+var_C0], 6
0x140018f3b  call    _tlgWriteTransfer_EventWriteTransfer
0x140018f40  cmp     [rbx+138h], r15d
0x140018f47  jnz     short loc_140018F80
0x140018f49  add     rbx, 120h
0x140018f50  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140018f57  jz      short loc_140018F7D
0x140018f59  mov     dl, 1
0x140018f5b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140018f60  mov     [rbx], rax
0x140018f63  test    rax, rax
0x140018f66  jz      short loc_140018F80
0x140018f68  mov     rcx, [rax]
0x140018f6b  mov     [rbx+10h], rcx
0x140018f6f  mov     [rax], rbx
0x140018f72  call    cs:__imp_GetCurrentThreadId
0x140018f78  mov     [rbx+18h], eax
0x140018f7b  jmp     short loc_140018F80
0x140018f7d  mov     [rbx], r15
0x140018f80  mov     rcx, [rbp+57h+var_30]
0x140018f84  xor     rcx, rsp; StackCookie
0x140018f87  call    __security_check_cookie
0x140018f8c  lea     r11, [rsp+0E0h+var_20]
0x140018f94  mov     rbx, [r11+38h]
0x140018f98  mov     rsi, [r11+40h]
0x140018f9c  mov     rsp, r11
0x140018f9f  pop     r15
0x140018fa1  pop     r14
0x140018fa3  pop     r12
0x140018fa5  pop     rdi
0x140018fa6  pop     rbp
0x140018fa7  retn
```
