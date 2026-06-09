# MDMPushProvider::GetChannelObjectHelperActivity::StartActivity(void)

- ea: `0x140028d38`
- end: `0x140028e74`
- name: `?StartActivity@GetChannelObjectHelperActivity@MDMPushProvider@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(MDMPushProvider::GetChannelObjectHelperActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140024bc4`

## callees

- `0x14000206c`
- `0x1400042f0`
- `0x1400133c4`
- `0x1400147dc`
- `0x1400183fc`
- `0x140028d38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028da5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028da5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028dbe`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140028d87`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140028d87`

## pseudocode

```c
void __fastcall MDMPushProvider::GetChannelObjectHelperActivity::StartActivity(
        MDMPushProvider::GetChannelObjectHelperActivity *this)
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
      (unsigned __int8 *)&unk_14006F000,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (MDMPushProvider::GetChannelObjectHelperActivity *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x140028d38  mov     [rsp-8+arg_8], rbx
0x140028d3d  mov     [rsp-8+arg_10], rdi
0x140028d42  push    rbp
0x140028d43  lea     rbp, [rsp-57h]
0x140028d48  sub     rsp, 90h
0x140028d4f  mov     rax, cs:__security_cookie
0x140028d56  xor     rax, rsp
0x140028d59  mov     [rbp+57h+var_10], rax
0x140028d5d  mov     rbx, rcx
0x140028d60  lea     rdx, [rbp+57h+SRWLock]
0x140028d64  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140028d69  mov     rdi, [rbx+110h]
0x140028d70  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140028d75  mov     r8d, [rax]
0x140028d78  cmp     r8d, 5
0x140028d7c  jbe     short loc_140028D8F
0x140028d7e  lea     rdx, [rdi+8]; ActivityId
0x140028d82  mov     ecx, 3; ControlCode
0x140028d87  call    cs:__imp_EventActivityIdControl
0x140028d8d  jmp     short loc_140028D96
0x140028d8f  xorps   xmm0, xmm0
0x140028d92  movups  xmmword ptr [rdi+8], xmm0
0x140028d96  mov     dword ptr [rdi], 1
0x140028d9c  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140028da0  test    rcx, rcx
0x140028da3  jz      short loc_140028DAB
0x140028da5  call    cs:__imp_ReleaseSRWLockExclusive
0x140028dab  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140028db0  mov     rdi, rax
0x140028db3  mov     ecx, [rax]
0x140028db5  cmp     ecx, 5
0x140028db8  jbe     loc_140028E40
0x140028dbe  call    cs:__imp_GetCurrentThreadId
0x140028dc4  mov     dword ptr [rbp+57h+SRWLock], eax
0x140028dc7  mov     [rbp+57h+var_58], 0
0x140028dcf  mov     r8, [rbx+110h]
0x140028dd6  cmp     byte ptr [r8+4], 0
0x140028ddb  jz      short loc_140028DFC
0x140028ddd  lea     r9, [r8+18h]
0x140028de1  cmp     dword ptr [r9], 0
0x140028de5  jnz     short loc_140028DFF
0x140028de7  cmp     dword ptr [r9+4], 0
0x140028dec  jnz     short loc_140028DFF
0x140028dee  cmp     dword ptr [r9+8], 0
0x140028df3  jnz     short loc_140028DFF
0x140028df5  cmp     dword ptr [r9+0Ch], 0
0x140028dfa  jnz     short loc_140028DFF
0x140028dfc  xor     r9d, r9d
0x140028dff  lea     rax, [rbp+57h+SRWLock]
0x140028e03  mov     [rbp+57h+var_20], rax
0x140028e07  mov     ecx, 4
0x140028e0c  mov     [rbp+57h+var_18], rcx
0x140028e10  lea     rax, [rbp+57h+var_58]
0x140028e14  mov     [rbp+57h+var_30], rax
0x140028e18  mov     [rbp+57h+var_28], 8
0x140028e20  add     r8, 8
0x140028e24  lea     rax, [rbp+57h+var_50]
0x140028e28  mov     [rsp+90h+var_68], rax
0x140028e2d  mov     [rsp+90h+var_70], ecx
0x140028e31  lea     rdx, unk_14006F000
0x140028e38  mov     rcx, rdi
0x140028e3b  call    _tlgWriteTransfer_EventWriteTransfer
0x140028e40  lea     rcx, [rbx+120h]; this
0x140028e47  cmp     dword ptr [rcx+18h], 0
0x140028e4b  jnz     short loc_140028E53
0x140028e4d  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140028e52  nop
0x140028e53  mov     rcx, [rbp+57h+var_10]
0x140028e57  xor     rcx, rsp; StackCookie
0x140028e5a  call    __security_check_cookie
0x140028e5f  lea     r11, [rsp+90h+var_s0]
0x140028e67  mov     rbx, [r11+18h]
0x140028e6b  mov     rdi, [r11+20h]
0x140028e6f  mov     rsp, r11
0x140028e72  pop     rbp
0x140028e73  retn
```
