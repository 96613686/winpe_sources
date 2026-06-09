# MDMPushProvider::CreatePushUpgradeScheduleActivity::StartActivity(void)

- ea: `0x140028ab0`
- end: `0x140028bec`
- name: `?StartActivity@CreatePushUpgradeScheduleActivity@MDMPushProvider@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(MDMPushProvider::CreatePushUpgradeScheduleActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140022620`

## callees

- `0x14000206c`
- `0x1400042f0`
- `0x1400133c4`
- `0x1400147dc`
- `0x1400183fc`
- `0x140028ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028b1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028b36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028b36`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140028aff`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140028aff`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushUpgradeScheduleActivity::StartActivity(
        MDMPushProvider::CreatePushUpgradeScheduleActivity *this)
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
      (unsigned __int8 *)byte_14006DFBF,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (MDMPushProvider::CreatePushUpgradeScheduleActivity *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x140028ab0  mov     [rsp-8+arg_8], rbx
0x140028ab5  mov     [rsp-8+arg_10], rdi
0x140028aba  push    rbp
0x140028abb  lea     rbp, [rsp-57h]
0x140028ac0  sub     rsp, 90h
0x140028ac7  mov     rax, cs:__security_cookie
0x140028ace  xor     rax, rsp
0x140028ad1  mov     [rbp+57h+var_10], rax
0x140028ad5  mov     rbx, rcx
0x140028ad8  lea     rdx, [rbp+57h+SRWLock]
0x140028adc  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140028ae1  mov     rdi, [rbx+110h]
0x140028ae8  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140028aed  mov     r8d, [rax]
0x140028af0  cmp     r8d, 5
0x140028af4  jbe     short loc_140028B07
0x140028af6  lea     rdx, [rdi+8]; ActivityId
0x140028afa  mov     ecx, 3; ControlCode
0x140028aff  call    cs:__imp_EventActivityIdControl
0x140028b05  jmp     short loc_140028B0E
0x140028b07  xorps   xmm0, xmm0
0x140028b0a  movups  xmmword ptr [rdi+8], xmm0
0x140028b0e  mov     dword ptr [rdi], 1
0x140028b14  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140028b18  test    rcx, rcx
0x140028b1b  jz      short loc_140028B23
0x140028b1d  call    cs:__imp_ReleaseSRWLockExclusive
0x140028b23  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140028b28  mov     rdi, rax
0x140028b2b  mov     ecx, [rax]
0x140028b2d  cmp     ecx, 5
0x140028b30  jbe     loc_140028BB8
0x140028b36  call    cs:__imp_GetCurrentThreadId
0x140028b3c  mov     dword ptr [rbp+57h+SRWLock], eax
0x140028b3f  mov     [rbp+57h+var_58], 0
0x140028b47  mov     r8, [rbx+110h]
0x140028b4e  cmp     byte ptr [r8+4], 0
0x140028b53  jz      short loc_140028B74
0x140028b55  lea     r9, [r8+18h]
0x140028b59  cmp     dword ptr [r9], 0
0x140028b5d  jnz     short loc_140028B77
0x140028b5f  cmp     dword ptr [r9+4], 0
0x140028b64  jnz     short loc_140028B77
0x140028b66  cmp     dword ptr [r9+8], 0
0x140028b6b  jnz     short loc_140028B77
0x140028b6d  cmp     dword ptr [r9+0Ch], 0
0x140028b72  jnz     short loc_140028B77
0x140028b74  xor     r9d, r9d
0x140028b77  lea     rax, [rbp+57h+SRWLock]
0x140028b7b  mov     [rbp+57h+var_20], rax
0x140028b7f  mov     ecx, 4
0x140028b84  mov     [rbp+57h+var_18], rcx
0x140028b88  lea     rax, [rbp+57h+var_58]
0x140028b8c  mov     [rbp+57h+var_30], rax
0x140028b90  mov     [rbp+57h+var_28], 8
0x140028b98  add     r8, 8
0x140028b9c  lea     rax, [rbp+57h+var_50]
0x140028ba0  mov     [rsp+90h+var_68], rax
0x140028ba5  mov     [rsp+90h+var_70], ecx
0x140028ba9  lea     rdx, byte_14006DFBF
0x140028bb0  mov     rcx, rdi
0x140028bb3  call    _tlgWriteTransfer_EventWriteTransfer
0x140028bb8  lea     rcx, [rbx+120h]; this
0x140028bbf  cmp     dword ptr [rcx+18h], 0
0x140028bc3  jnz     short loc_140028BCB
0x140028bc5  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140028bca  nop
0x140028bcb  mov     rcx, [rbp+57h+var_10]
0x140028bcf  xor     rcx, rsp; StackCookie
0x140028bd2  call    __security_check_cookie
0x140028bd7  lea     r11, [rsp+90h+var_s0]
0x140028bdf  mov     rbx, [r11+18h]
0x140028be3  mov     rdi, [r11+20h]
0x140028be7  mov     rsp, r11
0x140028bea  pop     rbp
0x140028beb  retn
```
