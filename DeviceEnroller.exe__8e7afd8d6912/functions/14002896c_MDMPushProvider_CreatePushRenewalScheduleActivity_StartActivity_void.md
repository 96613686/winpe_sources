# MDMPushProvider::CreatePushRenewalScheduleActivity::StartActivity(void)

- ea: `0x14002896c`
- end: `0x140028aa8`
- name: `?StartActivity@CreatePushRenewalScheduleActivity@MDMPushProvider@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(MDMPushProvider::CreatePushRenewalScheduleActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001f8a8`

## callees

- `0x14000206c`
- `0x1400042f0`
- `0x1400133c4`
- `0x1400147dc`
- `0x1400183fc`
- `0x14002896c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400289d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400289d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400289f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400289f2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400289bb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400289bb`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushRenewalScheduleActivity::StartActivity(
        MDMPushProvider::CreatePushRenewalScheduleActivity *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  const struct _tlgProvider_t *v4; // rdi
  __int64 v5; // r8
  const GUID *v6; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  __int64 v8; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v10; // [rsp+60h] [rbp+27h]
  __int64 v11; // [rsp+68h] [rbp+2Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+37h]
  __int64 v13; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)MDMPushProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = MDMPushProvider::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v8 = 0;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = (const GUID *)(v5 + 24), !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    p_SRWLock = &SRWLock;
    v13 = 4;
    v10 = &v8;
    v11 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v4,
      (unsigned __int8 *)byte_14006DE07,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (MDMPushProvider::CreatePushRenewalScheduleActivity *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x14002896c  mov     [rsp-8+arg_8], rbx
0x140028971  mov     [rsp-8+arg_10], rdi
0x140028976  push    rbp
0x140028977  lea     rbp, [rsp-57h]
0x14002897c  sub     rsp, 90h
0x140028983  mov     rax, cs:__security_cookie
0x14002898a  xor     rax, rsp
0x14002898d  mov     [rbp+57h+var_10], rax
0x140028991  mov     rbx, rcx
0x140028994  lea     rdx, [rbp+57h+SRWLock]
0x140028998  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002899d  mov     rdi, [rbx+110h]
0x1400289a4  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400289a9  mov     r8d, [rax]
0x1400289ac  cmp     r8d, 5
0x1400289b0  jbe     short loc_1400289C3
0x1400289b2  lea     rdx, [rdi+8]; ActivityId
0x1400289b6  mov     ecx, 3; ControlCode
0x1400289bb  call    cs:__imp_EventActivityIdControl
0x1400289c1  jmp     short loc_1400289CA
0x1400289c3  xorps   xmm0, xmm0
0x1400289c6  movups  xmmword ptr [rdi+8], xmm0
0x1400289ca  mov     dword ptr [rdi], 1
0x1400289d0  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400289d4  test    rcx, rcx
0x1400289d7  jz      short loc_1400289DF
0x1400289d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400289df  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400289e4  mov     rdi, rax
0x1400289e7  mov     ecx, [rax]
0x1400289e9  cmp     ecx, 5
0x1400289ec  jbe     loc_140028A74
0x1400289f2  call    cs:__imp_GetCurrentThreadId
0x1400289f8  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400289fb  mov     [rbp+57h+var_58], 0
0x140028a03  mov     r8, [rbx+110h]
0x140028a0a  cmp     byte ptr [r8+4], 0
0x140028a0f  jz      short loc_140028A30
0x140028a11  lea     r9, [r8+18h]
0x140028a15  cmp     dword ptr [r9], 0
0x140028a19  jnz     short loc_140028A33
0x140028a1b  cmp     dword ptr [r9+4], 0
0x140028a20  jnz     short loc_140028A33
0x140028a22  cmp     dword ptr [r9+8], 0
0x140028a27  jnz     short loc_140028A33
0x140028a29  cmp     dword ptr [r9+0Ch], 0
0x140028a2e  jnz     short loc_140028A33
0x140028a30  xor     r9d, r9d
0x140028a33  lea     rax, [rbp+57h+SRWLock]
0x140028a37  mov     [rbp+57h+var_20], rax
0x140028a3b  mov     ecx, 4
0x140028a40  mov     [rbp+57h+var_18], rcx
0x140028a44  lea     rax, [rbp+57h+var_58]
0x140028a48  mov     [rbp+57h+var_30], rax
0x140028a4c  mov     [rbp+57h+var_28], 8
0x140028a54  add     r8, 8
0x140028a58  lea     rax, [rbp+57h+var_50]
0x140028a5c  mov     [rsp+90h+var_68], rax
0x140028a61  mov     [rsp+90h+var_70], ecx
0x140028a65  lea     rdx, byte_14006DE07
0x140028a6c  mov     rcx, rdi
0x140028a6f  call    _tlgWriteTransfer_EventWriteTransfer
0x140028a74  lea     rcx, [rbx+120h]; this
0x140028a7b  cmp     dword ptr [rcx+18h], 0
0x140028a7f  jnz     short loc_140028A87
0x140028a81  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140028a86  nop
0x140028a87  mov     rcx, [rbp+57h+var_10]
0x140028a8b  xor     rcx, rsp; StackCookie
0x140028a8e  call    __security_check_cookie
0x140028a93  lea     r11, [rsp+90h+var_s0]
0x140028a9b  mov     rbx, [r11+18h]
0x140028a9f  mov     rdi, [r11+20h]
0x140028aa3  mov     rsp, r11
0x140028aa6  pop     rbp
0x140028aa7  retn
```
