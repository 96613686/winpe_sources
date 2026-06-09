# OfflineMapsTelemetry::ClientOpenConnectionActivity::StartActivity(void)

- ea: `0x18000b28c`
- end: `0x18000b3fa`
- name: `?StartActivity@ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAAXXZ`
- size: `366`
- prototype: `void __fastcall(OfflineMapsTelemetry::ClientOpenConnectionActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800080cc`

## callees

- `0x18000163c`
- `0x180002550`
- `0x180004fc0`
- `0x180005c50`
- `0x180009bb4`
- `0x18000b28c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2f9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b2db`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b2db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b312`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b312`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3c7`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::ClientOpenConnectionActivity::StartActivity(
        OfflineMapsTelemetry::ClientOpenConnectionActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  char *v7; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  __int64 v10; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v12; // [rsp+60h] [rbp+27h]
  __int64 v13; // [rsp+68h] [rbp+2Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+37h]
  __int64 v15; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)OfflineMapsTraceLogging::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = OfflineMapsTraceLogging::Provider();
  v4 = *(unsigned int *)v3;
  if ( (unsigned int)v4 > 5 )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v10 = 0x1000000;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    p_SRWLock = &SRWLock;
    v15 = 4;
    v12 = &v10;
    v13 = 8;
    tlgWriteTransfer_EventWriteTransfer(v3, byte_180017E89, v5 + 8, v6, 4, v11);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v7 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v4,
                          1);
      *(_QWORD *)v7 = Local;
      if ( Local )
      {
        *((_QWORD *)v7 + 2) = *Local;
        *Local = v7;
        *((_DWORD *)v7 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v7 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000b28c  mov     [rsp-8+arg_8], rbx
0x18000b291  mov     [rsp-8+arg_10], rdi
0x18000b296  push    rbp
0x18000b297  lea     rbp, [rsp-57h]
0x18000b29c  sub     rsp, 90h
0x18000b2a3  mov     rax, cs:__security_cookie
0x18000b2aa  xor     rax, rsp
0x18000b2ad  mov     [rbp+57h+var_10], rax
0x18000b2b1  mov     rbx, rcx
0x18000b2b4  lea     rdx, [rbp+57h+SRWLock]
0x18000b2b8  call    ?LockExclusive@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b2bd  mov     rdi, [rbx+110h]
0x18000b2c4  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18000b2c9  mov     r8d, [rax]
0x18000b2cc  cmp     r8d, 5
0x18000b2d0  jbe     short loc_18000B2E3
0x18000b2d2  lea     rdx, [rdi+8]; ActivityId
0x18000b2d6  mov     ecx, 3; ControlCode
0x18000b2db  call    cs:__imp_EventActivityIdControl
0x18000b2e1  jmp     short loc_18000B2EA
0x18000b2e3  xorps   xmm0, xmm0
0x18000b2e6  movups  xmmword ptr [rdi+8], xmm0
0x18000b2ea  mov     dword ptr [rdi], 1
0x18000b2f0  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000b2f4  test    rcx, rcx
0x18000b2f7  jz      short loc_18000B2FF
0x18000b2f9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b2ff  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18000b304  mov     rdi, rax
0x18000b307  mov     ecx, [rax]
0x18000b309  cmp     ecx, 5
0x18000b30c  jbe     loc_18000B394
0x18000b312  call    cs:__imp_GetCurrentThreadId
0x18000b318  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000b31b  mov     [rbp+57h+var_58], 1000000h
0x18000b323  mov     r8, [rbx+110h]
0x18000b32a  cmp     byte ptr [r8+4], 0
0x18000b32f  jz      short loc_18000B350
0x18000b331  lea     r9, [r8+18h]
0x18000b335  cmp     dword ptr [r9], 0
0x18000b339  jnz     short loc_18000B353
0x18000b33b  cmp     dword ptr [r9+4], 0
0x18000b340  jnz     short loc_18000B353
0x18000b342  cmp     dword ptr [r9+8], 0
0x18000b347  jnz     short loc_18000B353
0x18000b349  cmp     dword ptr [r9+0Ch], 0
0x18000b34e  jnz     short loc_18000B353
0x18000b350  xor     r9d, r9d
0x18000b353  lea     rax, [rbp+57h+SRWLock]
0x18000b357  mov     [rbp+57h+var_20], rax
0x18000b35b  mov     ecx, 4
0x18000b360  mov     [rbp+57h+var_18], rcx
0x18000b364  lea     rax, [rbp+57h+var_58]
0x18000b368  mov     [rbp+57h+var_30], rax
0x18000b36c  mov     [rbp+57h+var_28], 8
0x18000b374  add     r8, 8
0x18000b378  lea     rax, [rbp+57h+var_50]
0x18000b37c  mov     [rsp+90h+var_68], rax
0x18000b381  mov     [rsp+90h+var_70], ecx
0x18000b385  lea     rdx, byte_180017E89
0x18000b38c  mov     rcx, rdi
0x18000b38f  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b394  cmp     dword ptr [rbx+138h], 0
0x18000b39b  jnz     short loc_18000B3D9
0x18000b39d  add     rbx, 120h
0x18000b3a4  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b3ac  jz      short loc_18000B3D2
0x18000b3ae  mov     dl, 1
0x18000b3b0  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000b3b5  mov     [rbx], rax
0x18000b3b8  test    rax, rax
0x18000b3bb  jz      short loc_18000B3D9
0x18000b3bd  mov     rcx, [rax]
0x18000b3c0  mov     [rbx+10h], rcx
0x18000b3c4  mov     [rax], rbx
0x18000b3c7  call    cs:__imp_GetCurrentThreadId
0x18000b3cd  mov     [rbx+18h], eax
0x18000b3d0  jmp     short loc_18000B3D9
0x18000b3d2  mov     qword ptr [rbx], 0
0x18000b3d9  mov     rcx, [rbp+57h+var_10]
0x18000b3dd  xor     rcx, rsp; StackCookie
0x18000b3e0  call    __security_check_cookie
0x18000b3e5  lea     r11, [rsp+90h+var_s0]
0x18000b3ed  mov     rbx, [r11+18h]
0x18000b3f1  mov     rdi, [r11+20h]
0x18000b3f5  mov     rsp, r11
0x18000b3f8  pop     rbp
0x18000b3f9  retn
```
