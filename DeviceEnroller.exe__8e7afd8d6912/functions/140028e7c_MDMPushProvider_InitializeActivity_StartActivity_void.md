# MDMPushProvider::InitializeActivity::StartActivity(void)

- ea: `0x140028e7c`
- end: `0x140028fb8`
- name: `?StartActivity@InitializeActivity@MDMPushProvider@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(MDMPushProvider::InitializeActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140026448`

## callees

- `0x14000206c`
- `0x1400042f0`
- `0x1400133c4`
- `0x1400147dc`
- `0x1400183fc`
- `0x140028e7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028ee9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028ee9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028f02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140028f02`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140028ecb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140028ecb`

## pseudocode

```c
void __fastcall MDMPushProvider::InitializeActivity::StartActivity(MDMPushProvider::InitializeActivity *this)
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
      (unsigned __int8 *)&unk_14006DE60,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (MDMPushProvider::InitializeActivity *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x140028e7c  mov     [rsp-8+arg_8], rbx
0x140028e81  mov     [rsp-8+arg_10], rdi
0x140028e86  push    rbp
0x140028e87  lea     rbp, [rsp-57h]
0x140028e8c  sub     rsp, 90h
0x140028e93  mov     rax, cs:__security_cookie
0x140028e9a  xor     rax, rsp
0x140028e9d  mov     [rbp+57h+var_10], rax
0x140028ea1  mov     rbx, rcx
0x140028ea4  lea     rdx, [rbp+57h+SRWLock]
0x140028ea8  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140028ead  mov     rdi, [rbx+110h]
0x140028eb4  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140028eb9  mov     r8d, [rax]
0x140028ebc  cmp     r8d, 5
0x140028ec0  jbe     short loc_140028ED3
0x140028ec2  lea     rdx, [rdi+8]; ActivityId
0x140028ec6  mov     ecx, 3; ControlCode
0x140028ecb  call    cs:__imp_EventActivityIdControl
0x140028ed1  jmp     short loc_140028EDA
0x140028ed3  xorps   xmm0, xmm0
0x140028ed6  movups  xmmword ptr [rdi+8], xmm0
0x140028eda  mov     dword ptr [rdi], 1
0x140028ee0  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140028ee4  test    rcx, rcx
0x140028ee7  jz      short loc_140028EEF
0x140028ee9  call    cs:__imp_ReleaseSRWLockExclusive
0x140028eef  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140028ef4  mov     rdi, rax
0x140028ef7  mov     ecx, [rax]
0x140028ef9  cmp     ecx, 5
0x140028efc  jbe     loc_140028F84
0x140028f02  call    cs:__imp_GetCurrentThreadId
0x140028f08  mov     dword ptr [rbp+57h+SRWLock], eax
0x140028f0b  mov     [rbp+57h+var_58], 0
0x140028f13  mov     r8, [rbx+110h]
0x140028f1a  cmp     byte ptr [r8+4], 0
0x140028f1f  jz      short loc_140028F40
0x140028f21  lea     r9, [r8+18h]
0x140028f25  cmp     dword ptr [r9], 0
0x140028f29  jnz     short loc_140028F43
0x140028f2b  cmp     dword ptr [r9+4], 0
0x140028f30  jnz     short loc_140028F43
0x140028f32  cmp     dword ptr [r9+8], 0
0x140028f37  jnz     short loc_140028F43
0x140028f39  cmp     dword ptr [r9+0Ch], 0
0x140028f3e  jnz     short loc_140028F43
0x140028f40  xor     r9d, r9d
0x140028f43  lea     rax, [rbp+57h+SRWLock]
0x140028f47  mov     [rbp+57h+var_20], rax
0x140028f4b  mov     ecx, 4
0x140028f50  mov     [rbp+57h+var_18], rcx
0x140028f54  lea     rax, [rbp+57h+var_58]
0x140028f58  mov     [rbp+57h+var_30], rax
0x140028f5c  mov     [rbp+57h+var_28], 8
0x140028f64  add     r8, 8
0x140028f68  lea     rax, [rbp+57h+var_50]
0x140028f6c  mov     [rsp+90h+var_68], rax
0x140028f71  mov     [rsp+90h+var_70], ecx
0x140028f75  lea     rdx, unk_14006DE60
0x140028f7c  mov     rcx, rdi
0x140028f7f  call    _tlgWriteTransfer_EventWriteTransfer
0x140028f84  lea     rcx, [rbx+120h]; this
0x140028f8b  cmp     dword ptr [rcx+18h], 0
0x140028f8f  jnz     short loc_140028F97
0x140028f91  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140028f96  nop
0x140028f97  mov     rcx, [rbp+57h+var_10]
0x140028f9b  xor     rcx, rsp; StackCookie
0x140028f9e  call    __security_check_cookie
0x140028fa3  lea     r11, [rsp+90h+var_s0]
0x140028fab  mov     rbx, [r11+18h]
0x140028faf  mov     rdi, [r11+20h]
0x140028fb3  mov     rsp, r11
0x140028fb6  pop     rbp
0x140028fb7  retn
```
