# AppListBackupLauncherTelemetry::AppListBackupLauncher::StartActivity(void)

- ea: `0x18000ca14`
- end: `0x18000cbb5`
- name: `?StartActivity@AppListBackupLauncher@AppListBackupLauncherTelemetry@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(AppListBackupLauncherTelemetry::AppListBackupLauncher *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000dfe0`

## callees

- `0x180001a4c`
- `0x180002300`
- `0x180008988`
- `0x1800091f0`
- `0x180009e0c`
- `0x18000ca14`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ca7e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000ca7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cad5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cad5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb8a`

## pseudocode

```c
void __fastcall AppListBackupLauncherTelemetry::AppListBackupLauncher::StartActivity(
        AppListBackupLauncherTelemetry::AppListBackupLauncher *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v15; // [rsp+60h] [rbp+7h]
  __int64 v16; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v18; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = AppListBackupLauncherTelemetry::Provider();
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
  v4 = AppListBackupLauncherTelemetry::Provider();
  v5 = v4;
  v6 = *(unsigned int *)v4;
  if ( (unsigned int)v6 > 5 )
  {
    v7 = *((_QWORD *)v4 + 3);
    v6 = *((_QWORD *)v5 + 2);
    if ( (v6 & 0x400000000000LL) != 0 )
    {
      v6 = v7 & 0x400000000000LL;
      if ( (v7 & 0x400000000000LL) == v7 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v13 = 0x1000000;
        v8 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v8 + 4)
          || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
          && !*(_DWORD *)(v8 + 28)
          && !*(_DWORD *)(v8 + 32)
          && !*(_DWORD *)(v8 + 36) )
        {
          v9 = 0;
        }
        p_SRWLock = &SRWLock;
        v18 = 4;
        v15 = &v13;
        v16 = 8;
        tlgWriteTransfer_EventWriteTransfer(v5, byte_180014F45, v8 + 8, v9, 4, v14);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v10 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v6,
                          1);
      *(_QWORD *)v10 = Local;
      if ( Local )
      {
        *((_QWORD *)v10 + 2) = *Local;
        *Local = v10;
        *((_DWORD *)v10 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v10 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000ca14  push    rbp
0x18000ca16  push    rbx
0x18000ca17  push    rdi
0x18000ca18  push    r14
0x18000ca1a  lea     rbp, [rsp-3Fh]
0x18000ca1f  sub     rsp, 98h
0x18000ca26  mov     rax, cs:__security_cookie
0x18000ca2d  xor     rax, rsp
0x18000ca30  mov     [rbp+57h+var_30], rax
0x18000ca34  mov     rbx, rcx
0x18000ca37  lea     rdx, [rbp+57h+SRWLock]
0x18000ca3b  call    ?LockExclusive@?$ActivityBase@VAppListBackupLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ca40  mov     rdi, [rbx+110h]
0x18000ca47  call    ?Provider@AppListBackupLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppListBackupLauncherTelemetry::Provider(void)
0x18000ca4c  mov     edx, [rax]
0x18000ca4e  mov     r14, 400000000000h
0x18000ca58  cmp     edx, 5
0x18000ca5b  jbe     short loc_18000CA86
0x18000ca5d  mov     rcx, [rax+18h]
0x18000ca61  mov     rax, [rax+10h]
0x18000ca65  test    r14, rax
0x18000ca68  jz      short loc_18000CA86
0x18000ca6a  mov     rax, rcx
0x18000ca6d  and     rax, r14
0x18000ca70  cmp     rax, rcx
0x18000ca73  jnz     short loc_18000CA86
0x18000ca75  lea     rdx, [rdi+8]; ActivityId
0x18000ca79  mov     ecx, 3; ControlCode
0x18000ca7e  call    cs:__imp_EventActivityIdControl
0x18000ca84  jmp     short loc_18000CA8D
0x18000ca86  xorps   xmm0, xmm0
0x18000ca89  movups  xmmword ptr [rdi+8], xmm0
0x18000ca8d  mov     dword ptr [rdi], 1
0x18000ca93  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000ca97  test    rcx, rcx
0x18000ca9a  jz      short loc_18000CAA2
0x18000ca9c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000caa2  call    ?Provider@AppListBackupLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppListBackupLauncherTelemetry::Provider(void)
0x18000caa7  mov     rdi, rax
0x18000caaa  mov     ecx, [rax]
0x18000caac  cmp     ecx, 5
0x18000caaf  jbe     loc_18000CB57
0x18000cab5  mov     rax, [rax+18h]
0x18000cab9  mov     rcx, [rdi+10h]
0x18000cabd  test    r14, rcx
0x18000cac0  jz      loc_18000CB57
0x18000cac6  mov     rcx, rax
0x18000cac9  and     rcx, r14
0x18000cacc  cmp     rcx, rax
0x18000cacf  jnz     loc_18000CB57
0x18000cad5  call    cs:__imp_GetCurrentThreadId
0x18000cadb  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000cade  mov     [rbp+57h+var_78], 1000000h
0x18000cae6  mov     r8, [rbx+110h]
0x18000caed  cmp     byte ptr [r8+4], 0
0x18000caf2  jz      short loc_18000CB13
0x18000caf4  lea     r9, [r8+18h]
0x18000caf8  cmp     dword ptr [r9], 0
0x18000cafc  jnz     short loc_18000CB16
0x18000cafe  cmp     dword ptr [r9+4], 0
0x18000cb03  jnz     short loc_18000CB16
0x18000cb05  cmp     dword ptr [r9+8], 0
0x18000cb0a  jnz     short loc_18000CB16
0x18000cb0c  cmp     dword ptr [r9+0Ch], 0
0x18000cb11  jnz     short loc_18000CB16
0x18000cb13  xor     r9d, r9d
0x18000cb16  lea     rax, [rbp+57h+SRWLock]
0x18000cb1a  mov     [rbp+57h+var_40], rax
0x18000cb1e  mov     ecx, 4
0x18000cb23  mov     [rbp+57h+var_38], rcx
0x18000cb27  lea     rax, [rbp+57h+var_78]
0x18000cb2b  mov     [rbp+57h+var_50], rax
0x18000cb2f  mov     [rbp+57h+var_48], 8
0x18000cb37  add     r8, 8
0x18000cb3b  lea     rax, [rbp+57h+var_70]
0x18000cb3f  mov     [rsp+0B0h+var_88], rax
0x18000cb44  mov     [rsp+0B0h+var_90], ecx
0x18000cb48  lea     rdx, byte_180014F45
0x18000cb4f  mov     rcx, rdi
0x18000cb52  call    _tlgWriteTransfer_EventWriteTransfer
0x18000cb57  cmp     dword ptr [rbx+138h], 0
0x18000cb5e  jnz     short loc_18000CB9C
0x18000cb60  add     rbx, 120h
0x18000cb67  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000cb6f  jz      short loc_18000CB95
0x18000cb71  mov     dl, 1
0x18000cb73  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000cb78  mov     [rbx], rax
0x18000cb7b  test    rax, rax
0x18000cb7e  jz      short loc_18000CB9C
0x18000cb80  mov     rcx, [rax]
0x18000cb83  mov     [rbx+10h], rcx
0x18000cb87  mov     [rax], rbx
0x18000cb8a  call    cs:__imp_GetCurrentThreadId
0x18000cb90  mov     [rbx+18h], eax
0x18000cb93  jmp     short loc_18000CB9C
0x18000cb95  mov     qword ptr [rbx], 0
0x18000cb9c  mov     rcx, [rbp+57h+var_30]
0x18000cba0  xor     rcx, rsp; StackCookie
0x18000cba3  call    __security_check_cookie
0x18000cba8  add     rsp, 98h
0x18000cbaf  pop     r14
0x18000cbb1  pop     rdi
0x18000cbb2  pop     rbx
0x18000cbb3  pop     rbp
0x18000cbb4  retn
```
