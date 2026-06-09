# MDMPushProvider::GetChannelObjectActivity::StartActivity(void)

- ea: `0x140028bf4`
- end: `0x140028d30`
- name: `?StartActivity@GetChannelObjectActivity@MDMPushProvider@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(MDMPushProvider::GetChannelObjectActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400249a4`

## callees

- `0x14000206c`
- `0x1400042f0`
- `0x1400133c4`
- `0x1400147dc`
- `0x1400183fc`
- `0x140028bf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028c61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028c61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028c7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028c7a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140028c43`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140028c43`

## pseudocode

```c
void __fastcall MDMPushProvider::GetChannelObjectActivity::StartActivity(
        MDMPushProvider::GetChannelObjectActivity *this)
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
      (unsigned __int8 *)byte_14006EEF5,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (MDMPushProvider::GetChannelObjectActivity *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x140028bf4  mov     [rsp-8+arg_8], rbx
0x140028bf9  mov     [rsp-8+arg_10], rdi
0x140028bfe  push    rbp
0x140028bff  lea     rbp, [rsp-57h]
0x140028c04  sub     rsp, 90h
0x140028c0b  mov     rax, cs:__security_cookie
0x140028c12  xor     rax, rsp
0x140028c15  mov     [rbp+57h+var_10], rax
0x140028c19  mov     rbx, rcx
0x140028c1c  lea     rdx, [rbp+57h+SRWLock]
0x140028c20  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140028c25  mov     rdi, [rbx+110h]
0x140028c2c  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140028c31  mov     r8d, [rax]
0x140028c34  cmp     r8d, 5
0x140028c38  jbe     short loc_140028C4B
0x140028c3a  lea     rdx, [rdi+8]; ActivityId
0x140028c3e  mov     ecx, 3; ControlCode
0x140028c43  call    cs:__imp_EventActivityIdControl
0x140028c49  jmp     short loc_140028C52
0x140028c4b  xorps   xmm0, xmm0
0x140028c4e  movups  xmmword ptr [rdi+8], xmm0
0x140028c52  mov     dword ptr [rdi], 1
0x140028c58  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140028c5c  test    rcx, rcx
0x140028c5f  jz      short loc_140028C67
0x140028c61  call    cs:__imp_ReleaseSRWLockExclusive
0x140028c67  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140028c6c  mov     rdi, rax
0x140028c6f  mov     ecx, [rax]
0x140028c71  cmp     ecx, 5
0x140028c74  jbe     loc_140028CFC
0x140028c7a  call    cs:__imp_GetCurrentThreadId
0x140028c80  mov     dword ptr [rbp+57h+SRWLock], eax
0x140028c83  mov     [rbp+57h+var_58], 0
0x140028c8b  mov     r8, [rbx+110h]
0x140028c92  cmp     byte ptr [r8+4], 0
0x140028c97  jz      short loc_140028CB8
0x140028c99  lea     r9, [r8+18h]
0x140028c9d  cmp     dword ptr [r9], 0
0x140028ca1  jnz     short loc_140028CBB
0x140028ca3  cmp     dword ptr [r9+4], 0
0x140028ca8  jnz     short loc_140028CBB
0x140028caa  cmp     dword ptr [r9+8], 0
0x140028caf  jnz     short loc_140028CBB
0x140028cb1  cmp     dword ptr [r9+0Ch], 0
0x140028cb6  jnz     short loc_140028CBB
0x140028cb8  xor     r9d, r9d
0x140028cbb  lea     rax, [rbp+57h+SRWLock]
0x140028cbf  mov     [rbp+57h+var_20], rax
0x140028cc3  mov     ecx, 4
0x140028cc8  mov     [rbp+57h+var_18], rcx
0x140028ccc  lea     rax, [rbp+57h+var_58]
0x140028cd0  mov     [rbp+57h+var_30], rax
0x140028cd4  mov     [rbp+57h+var_28], 8
0x140028cdc  add     r8, 8
0x140028ce0  lea     rax, [rbp+57h+var_50]
0x140028ce4  mov     [rsp+90h+var_68], rax
0x140028ce9  mov     [rsp+90h+var_70], ecx
0x140028ced  lea     rdx, byte_14006EEF5
0x140028cf4  mov     rcx, rdi
0x140028cf7  call    _tlgWriteTransfer_EventWriteTransfer
0x140028cfc  lea     rcx, [rbx+120h]; this
0x140028d03  cmp     dword ptr [rcx+18h], 0
0x140028d07  jnz     short loc_140028D0F
0x140028d09  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140028d0e  nop
0x140028d0f  mov     rcx, [rbp+57h+var_10]
0x140028d13  xor     rcx, rsp; StackCookie
0x140028d16  call    __security_check_cookie
0x140028d1b  lea     r11, [rsp+90h+var_s0]
0x140028d23  mov     rbx, [r11+18h]
0x140028d27  mov     rdi, [r11+20h]
0x140028d2b  mov     rsp, r11
0x140028d2e  pop     rbp
0x140028d2f  retn
```
