# LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity::StartActivity(bool)

- ea: `0x1800168e8`
- end: `0x180016a5b`
- name: `?StartActivity@EvaluatePendingUpdatesForSystemActivity@LanguageOverlayTraceProvider@@QEAAX_N@Z`
- size: `371`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800179d8`

## callees

- `0x18000163c`
- `0x180003a00`
- `0x1800085dc`
- `0x18000e1b8`
- `0x1800106c4`
- `0x1800168e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016974`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016974`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016956`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016956`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800169ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800169ae`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity::StartActivity(
        LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  RTL_SRWLOCK *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  const GUID *v9; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v13; // [rsp+60h] [rbp+7h]
  __int64 v14; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v3 > 5u
    && (*(_QWORD *)(v3 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(v3 + 24) & 0x200000000000LL) == *(_QWORD *)(v3 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  v4 = SRWLock;
  *(_DWORD *)v2 = 1;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  v6 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v6 > 5u
    && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v11 = 50331648;
    if ( !*(_BYTE *)(v8 + 4)
      || (v9 = (const GUID *)(v8 + 24), !*(_DWORD *)(v8 + 24))
      && !*(_DWORD *)(v8 + 28)
      && !*(_DWORD *)(v8 + 32)
      && !*(_DWORD *)(v8 + 36) )
    {
      v9 = 0;
    }
    v14 = 8;
    v16 = 4;
    p_SRWLock = &SRWLock;
    v13 = &v11;
    tlgWriteTransfer_EventWriteTransfer(v6, (unsigned __int8 *)byte_1800770A3, (const GUID *)(v8 + 8), v9, 4u, &v12);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (LanguageOverlayTraceProvider::EvaluatePendingUpdatesForSystemActivity *)((char *)this + 288),
      v5);
}

```

## disassembly

```asm
0x1800168e8  push    rbp
0x1800168ea  push    rbx
0x1800168eb  push    rdi
0x1800168ec  push    r14
0x1800168ee  lea     rbp, [rsp-3Fh]
0x1800168f3  sub     rsp, 98h
0x1800168fa  mov     rax, cs:__security_cookie
0x180016901  xor     rax, rsp
0x180016904  mov     [rbp+57h+var_30], rax
0x180016908  lea     rdx, [rbp+57h+SRWLock]
0x18001690c  mov     rdi, rcx
0x18001690f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016914  mov     rbx, [rdi+110h]
0x18001691b  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180016920  mov     r14, 200000000000h
0x18001692a  mov     rdx, [rax+8]
0x18001692e  mov     eax, [rdx]
0x180016930  cmp     eax, 5
0x180016933  jbe     short loc_18001695E
0x180016935  mov     rcx, [rdx+18h]
0x180016939  mov     rax, [rdx+10h]
0x18001693d  test    r14, rax
0x180016940  jz      short loc_18001695E
0x180016942  mov     rax, rcx
0x180016945  and     rax, r14
0x180016948  cmp     rax, rcx
0x18001694b  jnz     short loc_18001695E
0x18001694d  lea     rdx, [rbx+8]; ActivityId
0x180016951  mov     ecx, 3; ControlCode
0x180016956  call    cs:__imp_EventActivityIdControl
0x18001695c  jmp     short loc_180016965
0x18001695e  xorps   xmm0, xmm0
0x180016961  movups  xmmword ptr [rbx+8], xmm0
0x180016965  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180016969  mov     dword ptr [rbx], 1
0x18001696f  test    rcx, rcx
0x180016972  jz      short loc_18001697A
0x180016974  call    cs:__imp_ReleaseSRWLockExclusive
0x18001697a  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18001697f  mov     rbx, [rax+8]
0x180016983  mov     eax, [rbx]
0x180016985  cmp     eax, 5
0x180016988  jbe     loc_180016A30
0x18001698e  mov     rcx, [rbx+18h]
0x180016992  mov     rax, [rbx+10h]
0x180016996  test    r14, rax
0x180016999  jz      loc_180016A30
0x18001699f  mov     rax, rcx
0x1800169a2  and     rax, r14
0x1800169a5  cmp     rax, rcx
0x1800169a8  jnz     loc_180016A30
0x1800169ae  call    cs:__imp_GetCurrentThreadId
0x1800169b4  mov     r8, [rdi+110h]
0x1800169bb  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800169be  mov     [rbp+57h+var_78], 3000000h
0x1800169c6  cmp     byte ptr [r8+4], 0
0x1800169cb  jz      short loc_1800169EC
0x1800169cd  lea     r9, [r8+18h]
0x1800169d1  cmp     dword ptr [r9], 0
0x1800169d5  jnz     short loc_1800169EF
0x1800169d7  cmp     dword ptr [r9+4], 0
0x1800169dc  jnz     short loc_1800169EF
0x1800169de  cmp     dword ptr [r9+8], 0
0x1800169e3  jnz     short loc_1800169EF
0x1800169e5  cmp     dword ptr [r9+0Ch], 0
0x1800169ea  jnz     short loc_1800169EF
0x1800169ec  xor     r9d, r9d
0x1800169ef  mov     ecx, 4
0x1800169f4  mov     [rbp+57h+var_48], 8
0x1800169fc  lea     rax, [rbp+57h+SRWLock]
0x180016a00  mov     [rbp+57h+var_38], rcx
0x180016a04  mov     [rbp+57h+var_40], rax
0x180016a08  lea     rdx, byte_1800770A3
0x180016a0f  lea     rax, [rbp+57h+var_78]
0x180016a13  add     r8, 8
0x180016a17  mov     [rbp+57h+var_50], rax
0x180016a1b  lea     rax, [rbp+57h+var_70]
0x180016a1f  mov     [rsp+0B0h+var_88], rax
0x180016a24  mov     [rsp+0B0h+var_90], ecx
0x180016a28  mov     rcx, rbx
0x180016a2b  call    _tlgWriteTransfer_EventWriteTransfer
0x180016a30  lea     rcx, [rdi+120h]; this
0x180016a37  cmp     dword ptr [rcx+18h], 0
0x180016a3b  jnz     short loc_180016A42
0x180016a3d  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180016a42  mov     rcx, [rbp+57h+var_30]
0x180016a46  xor     rcx, rsp; StackCookie
0x180016a49  call    __security_check_cookie
0x180016a4e  add     rsp, 98h
0x180016a55  pop     r14
0x180016a57  pop     rdi
0x180016a58  pop     rbx
0x180016a59  pop     rbp
0x180016a5a  retn
```
