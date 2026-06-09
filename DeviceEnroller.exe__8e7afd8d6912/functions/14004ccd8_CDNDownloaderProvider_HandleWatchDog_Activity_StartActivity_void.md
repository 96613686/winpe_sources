# CDNDownloaderProvider::HandleWatchDog_Activity::StartActivity(void)

- ea: `0x14004ccd8`
- end: `0x14004ce47`
- name: `?StartActivity@HandleWatchDog_Activity@CDNDownloaderProvider@@QEAAXXZ`
- size: `367`
- prototype: `void __fastcall(CDNDownloaderProvider::HandleWatchDog_Activity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14004a9a4`

## callees

- `0x14000206c`
- `0x1400042f0`
- `0x1400133c4`
- `0x1400183fc`
- `0x14004bf84`
- `0x14004ccd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004cd60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004cd60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004cd99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004cd99`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14004cd42`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14004cd42`

## pseudocode

```c
void __fastcall CDNDownloaderProvider::HandleWatchDog_Activity::StartActivity(
        CDNDownloaderProvider::HandleWatchDog_Activity *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r8
  const GUID *v9; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v13; // [rsp+60h] [rbp+7h]
  __int64 v14; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = CDNDownloaderProvider::Provider();
  if ( *(_DWORD *)v3 > 5u
    && (*((_QWORD *)v3 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v3 + 3) & 0x400000000000LL) == *((_QWORD *)v3 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = CDNDownloaderProvider::Provider();
  v6 = (__int64)v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    v7 = *((_QWORD *)v4 + 3);
    if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v11 = 0;
      v8 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v8 + 4)
        || (v9 = (const GUID *)(v8 + 24), !*(_DWORD *)(v8 + 24))
        && !*(_DWORD *)(v8 + 28)
        && !*(_DWORD *)(v8 + 32)
        && !*(_DWORD *)(v8 + 36) )
      {
        v9 = 0;
      }
      p_SRWLock = &SRWLock;
      v16 = 4;
      v13 = &v11;
      v14 = 8;
      tlgWriteTransfer_EventWriteTransfer(v6, (unsigned __int8 *)word_140070F92, (const GUID *)(v8 + 8), v9, 4u, &v12);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (CDNDownloaderProvider::HandleWatchDog_Activity *)((char *)this + 288),
      v5);
}

```

## disassembly

```asm
0x14004ccd8  push    rbp
0x14004ccda  push    rbx
0x14004ccdb  push    rdi
0x14004ccdc  push    r14
0x14004ccde  lea     rbp, [rsp-3Fh]
0x14004cce3  sub     rsp, 98h
0x14004ccea  mov     rax, cs:__security_cookie
0x14004ccf1  xor     rax, rsp
0x14004ccf4  mov     [rbp+57h+var_30], rax
0x14004ccf8  mov     rdi, rcx
0x14004ccfb  lea     rdx, [rbp+57h+SRWLock]
0x14004ccff  call    ?LockExclusive@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004cd04  mov     rbx, [rdi+110h]
0x14004cd0b  call    ?Provider@CDNDownloaderProvider@@SAPEBU_tlgProvider_t@@XZ; CDNDownloaderProvider::Provider(void)
0x14004cd10  mov     edx, [rax]
0x14004cd12  mov     r14, 400000000000h
0x14004cd1c  cmp     edx, 5
0x14004cd1f  jbe     short loc_14004CD4A
0x14004cd21  mov     rcx, [rax+18h]
0x14004cd25  mov     rax, [rax+10h]
0x14004cd29  test    r14, rax
0x14004cd2c  jz      short loc_14004CD4A
0x14004cd2e  mov     rax, rcx
0x14004cd31  and     rax, r14
0x14004cd34  cmp     rax, rcx
0x14004cd37  jnz     short loc_14004CD4A
0x14004cd39  lea     rdx, [rbx+8]; ActivityId
0x14004cd3d  mov     ecx, 3; ControlCode
0x14004cd42  call    cs:__imp_EventActivityIdControl
0x14004cd48  jmp     short loc_14004CD51
0x14004cd4a  xorps   xmm0, xmm0
0x14004cd4d  movups  xmmword ptr [rbx+8], xmm0
0x14004cd51  mov     dword ptr [rbx], 1
0x14004cd57  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14004cd5b  test    rcx, rcx
0x14004cd5e  jz      short loc_14004CD66
0x14004cd60  call    cs:__imp_ReleaseSRWLockExclusive
0x14004cd66  call    ?Provider@CDNDownloaderProvider@@SAPEBU_tlgProvider_t@@XZ; CDNDownloaderProvider::Provider(void)
0x14004cd6b  mov     rbx, rax
0x14004cd6e  mov     ecx, [rax]
0x14004cd70  cmp     ecx, 5
0x14004cd73  jbe     loc_14004CE1B
0x14004cd79  mov     rax, [rax+18h]
0x14004cd7d  mov     rcx, [rbx+10h]
0x14004cd81  test    r14, rcx
0x14004cd84  jz      loc_14004CE1B
0x14004cd8a  mov     rcx, rax
0x14004cd8d  and     rcx, r14
0x14004cd90  cmp     rcx, rax
0x14004cd93  jnz     loc_14004CE1B
0x14004cd99  call    cs:__imp_GetCurrentThreadId
0x14004cd9f  mov     dword ptr [rbp+57h+SRWLock], eax
0x14004cda2  mov     [rbp+57h+var_78], 0
0x14004cdaa  mov     r8, [rdi+110h]
0x14004cdb1  cmp     byte ptr [r8+4], 0
0x14004cdb6  jz      short loc_14004CDD7
0x14004cdb8  lea     r9, [r8+18h]
0x14004cdbc  cmp     dword ptr [r9], 0
0x14004cdc0  jnz     short loc_14004CDDA
0x14004cdc2  cmp     dword ptr [r9+4], 0
0x14004cdc7  jnz     short loc_14004CDDA
0x14004cdc9  cmp     dword ptr [r9+8], 0
0x14004cdce  jnz     short loc_14004CDDA
0x14004cdd0  cmp     dword ptr [r9+0Ch], 0
0x14004cdd5  jnz     short loc_14004CDDA
0x14004cdd7  xor     r9d, r9d
0x14004cdda  lea     rax, [rbp+57h+SRWLock]
0x14004cdde  mov     [rbp+57h+var_40], rax
0x14004cde2  mov     ecx, 4
0x14004cde7  mov     [rbp+57h+var_38], rcx
0x14004cdeb  lea     rax, [rbp+57h+var_78]
0x14004cdef  mov     [rbp+57h+var_50], rax
0x14004cdf3  mov     [rbp+57h+var_48], 8
0x14004cdfb  add     r8, 8
0x14004cdff  lea     rax, [rbp+57h+var_70]
0x14004ce03  mov     [rsp+0B0h+var_88], rax
0x14004ce08  mov     [rsp+0B0h+var_90], ecx
0x14004ce0c  lea     rdx, word_140070F92
0x14004ce13  mov     rcx, rbx
0x14004ce16  call    _tlgWriteTransfer_EventWriteTransfer
0x14004ce1b  lea     rcx, [rdi+120h]; this
0x14004ce22  cmp     dword ptr [rcx+18h], 0
0x14004ce26  jnz     short loc_14004CE2E
0x14004ce28  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14004ce2d  nop
0x14004ce2e  mov     rcx, [rbp+57h+var_30]
0x14004ce32  xor     rcx, rsp; StackCookie
0x14004ce35  call    __security_check_cookie
0x14004ce3a  add     rsp, 98h
0x14004ce41  pop     r14
0x14004ce43  pop     rdi
0x14004ce44  pop     rbx
0x14004ce45  pop     rbp
0x14004ce46  retn
```
