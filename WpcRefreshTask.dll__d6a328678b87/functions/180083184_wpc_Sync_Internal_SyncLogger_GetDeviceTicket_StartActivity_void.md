# wpc::Sync::Internal::SyncLogger::GetDeviceTicket::StartActivity(void)

- ea: `0x180083184`
- end: `0x1800832c3`
- name: `?StartActivity@GetDeviceTicket@SyncLogger@Internal@Sync@wpc@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(wpc::Sync::Internal::SyncLogger::GetDeviceTicket *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18007f6c0`

## callees

- `0x1800010fc`
- `0x1800060a0`
- `0x18001a04c`
- `0x18002ae34`
- `0x18002bbb8`
- `0x180083184`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008320a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008320a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800831f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800831f1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800831d3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800831d3`

## pseudocode

```c
void __fastcall wpc::Sync::Internal::SyncLogger::GetDeviceTicket::StartActivity(
        wpc::Sync::Internal::SyncLogger::GetDeviceTicket *this)
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
      (unsigned __int8 *)byte_1800D7DC3,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wpc::Sync::Internal::SyncLogger::GetDeviceTicket *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x180083184  mov     [rsp-8+arg_8], rbx
0x180083189  mov     [rsp-8+arg_10], rdi
0x18008318e  push    rbp
0x18008318f  lea     rbp, [rsp-57h]
0x180083194  sub     rsp, 90h
0x18008319b  mov     rax, cs:__security_cookie
0x1800831a2  xor     rax, rsp
0x1800831a5  mov     [rbp+57h+var_10], rax
0x1800831a9  mov     rbx, rcx
0x1800831ac  lea     rdx, [rbp+57h+SRWLock]
0x1800831b0  call    ?LockExclusive@?$ActivityBase@VSyncLogger@Internal@Sync@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Sync::Internal::SyncLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800831b5  mov     rdi, [rbx+110h]
0x1800831bc  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x1800831c1  mov     r8d, [rax]
0x1800831c4  cmp     r8d, 4
0x1800831c8  jbe     short loc_1800831DB
0x1800831ca  lea     rdx, [rdi+8]; ActivityId
0x1800831ce  mov     ecx, 3; ControlCode
0x1800831d3  call    cs:__imp_EventActivityIdControl
0x1800831d9  jmp     short loc_1800831E2
0x1800831db  xorps   xmm0, xmm0
0x1800831de  movups  xmmword ptr [rdi+8], xmm0
0x1800831e2  mov     dword ptr [rdi], 1
0x1800831e8  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800831ec  test    rcx, rcx
0x1800831ef  jz      short loc_1800831F7
0x1800831f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800831f7  call    ?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Sync::Internal::SyncLogger::Provider(void)
0x1800831fc  mov     rdi, rax
0x1800831ff  mov     ecx, [rax]
0x180083201  cmp     ecx, 4
0x180083204  jbe     loc_18008328F
0x18008320a  call    cs:__imp_GetCurrentThreadId
0x180083210  mov     dword ptr [rbp+57h+SRWLock], eax
0x180083213  mov     [rbp+57h+var_58], 1000000h
0x18008321b  mov     r8, [rbx+110h]
0x180083222  cmp     byte ptr [r8+4], 0
0x180083227  jz      short loc_180083248
0x180083229  lea     r9, [r8+18h]
0x18008322d  cmp     dword ptr [r9], 0
0x180083231  jnz     short loc_18008324B
0x180083233  cmp     dword ptr [r9+4], 0
0x180083238  jnz     short loc_18008324B
0x18008323a  cmp     dword ptr [r9+8], 0
0x18008323f  jnz     short loc_18008324B
0x180083241  cmp     dword ptr [r9+0Ch], 0
0x180083246  jnz     short loc_18008324B
0x180083248  xor     r9d, r9d
0x18008324b  lea     rax, [rbp+57h+SRWLock]
0x18008324f  mov     [rbp+57h+var_20], rax
0x180083253  mov     [rbp+57h+var_18], 4
0x18008325b  lea     rax, [rbp+57h+var_58]
0x18008325f  mov     [rbp+57h+var_30], rax
0x180083263  mov     [rbp+57h+var_28], 8
0x18008326b  add     r8, 8
0x18008326f  lea     rax, [rbp+57h+var_50]
0x180083273  mov     [rsp+90h+var_68], rax
0x180083278  mov     [rsp+90h+var_70], 4
0x180083280  lea     rdx, byte_1800D7DC3
0x180083287  mov     rcx, rdi
0x18008328a  call    _tlgWriteTransfer_EventWriteTransfer
0x18008328f  lea     rcx, [rbx+120h]; this
0x180083296  cmp     dword ptr [rcx+18h], 0
0x18008329a  jnz     short loc_1800832A2
0x18008329c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800832a1  nop
0x1800832a2  mov     rcx, [rbp+57h+var_10]
0x1800832a6  xor     rcx, rsp; StackCookie
0x1800832a9  call    __security_check_cookie
0x1800832ae  lea     r11, [rsp+90h+var_s0]
0x1800832b6  mov     rbx, [r11+18h]
0x1800832ba  mov     rdi, [r11+20h]
0x1800832be  mov     rsp, r11
0x1800832c1  pop     rbp
0x1800832c2  retn
```
