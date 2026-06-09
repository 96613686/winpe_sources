# wpc::Sync::Internal::SyncLogger::AppDeviceInfo::StartActivity(void)

- ea: `0x18008303c`
- end: `0x18008317b`
- name: `?StartActivity@AppDeviceInfo@SyncLogger@Internal@Sync@wpc@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::AppDeviceInfo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18007f4e0`

## callees

- `0x1800010fc`
- `0x1800060a0`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002bbb8`
- `0x18008303c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800830c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800830c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800830a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800830a9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18008308b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18008308b`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::AppDeviceInfo::StartActivity(
        wpc::Sync::Internal::SyncLogger::AppDeviceInfo *this)
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

  wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)wpc::Sync::Internal::SyncLogger::Provider() <= 4u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = wpc::Sync::Internal::SyncLogger::Provider();
  if ( *(_DWORD *)v4 > 4u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v8 = 0x1000000;
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
      (unsigned __int8 *)qword_1800D6C60,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wpc::Sync::Internal::SyncLogger::AppDeviceInfo *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x18008303c  mov     [rsp-8+arg_8], rbx
0x180083041  mov     [rsp-8+arg_10], rdi
0x180083046  push    rbp
0x180083047  lea     rbp, [rsp-57h]
0x18008304c  sub     rsp, 90h
0x180083053  mov     rax, cs:__security_cookie
0x18008305a  xor     rax, rsp
0x18008305d  mov     [rbp+57h+var_10], rax
0x180083061  mov     rbx, rcx
0x180083064  lea     rdx, [rbp+57h+SRWLock]
0x180083068  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18008306d  mov     rdi, [rbx+110h]
0x180083074  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x180083079  mov     r8d, [rax]
0x18008307c  cmp     r8d, 4
0x180083080  jbe     short loc_180083093
0x180083082  lea     rdx, [rdi+8]; ActivityId
0x180083086  mov     ecx, 3; ControlCode
0x18008308b  call    cs:__imp_EventActivityIdControl
0x180083091  jmp     short loc_18008309A
0x180083093  xorps   xmm0, xmm0
0x180083096  movups  xmmword ptr [rdi+8], xmm0
0x18008309a  mov     dword ptr [rdi], 1
0x1800830a0  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800830a4  test    rcx, rcx
0x1800830a7  jz      short loc_1800830AF
0x1800830a9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800830af  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x1800830b4  mov     rdi, rax
0x1800830b7  mov     ecx, [rax]
0x1800830b9  cmp     ecx, 4
0x1800830bc  jbe     loc_180083147
0x1800830c2  call    cs:__imp_GetCurrentThreadId
0x1800830c8  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800830cb  mov     [rbp+57h+var_58], 1000000h
0x1800830d3  mov     r8, [rbx+110h]
0x1800830da  cmp     byte ptr [r8+4], 0
0x1800830df  jz      short loc_180083100
0x1800830e1  lea     r9, [r8+18h]
0x1800830e5  cmp     dword ptr [r9], 0
0x1800830e9  jnz     short loc_180083103
0x1800830eb  cmp     dword ptr [r9+4], 0
0x1800830f0  jnz     short loc_180083103
0x1800830f2  cmp     dword ptr [r9+8], 0
0x1800830f7  jnz     short loc_180083103
0x1800830f9  cmp     dword ptr [r9+0Ch], 0
0x1800830fe  jnz     short loc_180083103
0x180083100  xor     r9d, r9d
0x180083103  lea     rax, [rbp+57h+SRWLock]
0x180083107  mov     [rbp+57h+var_20], rax
0x18008310b  mov     [rbp+57h+var_18], 4
0x180083113  lea     rax, [rbp+57h+var_58]
0x180083117  mov     [rbp+57h+var_30], rax
0x18008311b  mov     [rbp+57h+var_28], 8
0x180083123  add     r8, 8
0x180083127  lea     rax, [rbp+57h+var_50]
0x18008312b  mov     [rsp+90h+var_68], rax
0x180083130  mov     [rsp+90h+var_70], 4
0x180083138  lea     rdx, qword_1800D6C60
0x18008313f  mov     rcx, rdi
0x180083142  call    _tlgWriteTransfer_EventWriteTransfer
0x180083147  lea     rcx, [rbx+120h]; this
0x18008314e  cmp     dword ptr [rcx+18h], 0
0x180083152  jnz     short loc_18008315A
0x180083154  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180083159  nop
0x18008315a  mov     rcx, [rbp+57h+var_10]
0x18008315e  xor     rcx, rsp; StackCookie
0x180083161  call    __security_check_cookie
0x180083166  lea     r11, [rsp+90h+var_s0]
0x18008316e  mov     rbx, [r11+18h]
0x180083172  mov     rdi, [r11+20h]
0x180083176  mov     rsp, r11
0x180083179  pop     rbp
0x18008317a  retn
```
