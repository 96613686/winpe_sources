# WaasMedic::TelemetryProvider::OneSettingsActivity::StartActivity(void)

- ea: `0x180024998`
- end: `0x180024b39`
- name: `?StartActivity@OneSettingsActivity@TelemetryProvider@WaasMedic@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::OneSettingsActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180024694`

## callees

- `0x1800017ac`
- `0x180003bb0`
- `0x1800085d0`
- `0x180016c9c`
- `0x180024274`
- `0x180024998`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024a20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024a20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024a59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024b0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024a59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024b0e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180024a02`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180024a02`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::OneSettingsActivity::StartActivity(
        WaasMedic::TelemetryProvider::OneSettingsActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v14; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v19; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = WaasMedic::TelemetryProvider::Provider();
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
  v4 = WaasMedic::TelemetryProvider::Provider();
  v6 = v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 )
  {
    v8 = *((_QWORD *)v4 + 3);
    v7 = *((_QWORD *)v6 + 2);
    if ( (v7 & 0x400000000000LL) != 0 )
    {
      v7 = v8 & 0x400000000000LL;
      if ( (v8 & 0x400000000000LL) == v8 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v14 = 0x1000000;
        v9 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v9 + 4)
          || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
          && !*(_DWORD *)(v9 + 28)
          && !*(_DWORD *)(v9 + 32)
          && !*(_DWORD *)(v9 + 36) )
        {
          v10 = 0;
        }
        p_SRWLock = &SRWLock;
        v19 = 4;
        v16 = &v14;
        v17 = 8;
        tlgWriteTransfer_EventWriteTransfer(v6, &unk_180088C70, v9 + 8, v10, 4, v15);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v11 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v5) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v7,
                          v5);
      *(_QWORD *)v11 = Local;
      if ( Local )
      {
        *((_QWORD *)v11 + 2) = *Local;
        *Local = v11;
        *((_DWORD *)v11 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v11 = 0;
    }
  }
}

```

## disassembly

```asm
0x180024998  push    rbp
0x18002499a  push    rbx
0x18002499b  push    rdi
0x18002499c  push    r14
0x18002499e  lea     rbp, [rsp-3Fh]
0x1800249a3  sub     rsp, 98h
0x1800249aa  mov     rax, cs:__security_cookie
0x1800249b1  xor     rax, rsp
0x1800249b4  mov     [rbp+57h+var_30], rax
0x1800249b8  mov     rbx, rcx
0x1800249bb  lea     rdx, [rbp+57h+SRWLock]
0x1800249bf  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800249c4  mov     rdi, [rbx+110h]
0x1800249cb  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x1800249d0  mov     edx, [rax]
0x1800249d2  mov     r14, 400000000000h
0x1800249dc  cmp     edx, 5
0x1800249df  jbe     short loc_180024A0A
0x1800249e1  mov     rcx, [rax+18h]
0x1800249e5  mov     rax, [rax+10h]
0x1800249e9  test    r14, rax
0x1800249ec  jz      short loc_180024A0A
0x1800249ee  mov     rax, rcx
0x1800249f1  and     rax, r14
0x1800249f4  cmp     rax, rcx
0x1800249f7  jnz     short loc_180024A0A
0x1800249f9  lea     rdx, [rdi+8]; ActivityId
0x1800249fd  mov     ecx, 3; ControlCode
0x180024a02  call    cs:__imp_EventActivityIdControl
0x180024a08  jmp     short loc_180024A11
0x180024a0a  xorps   xmm0, xmm0
0x180024a0d  movups  xmmword ptr [rdi+8], xmm0
0x180024a11  mov     dword ptr [rdi], 1
0x180024a17  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180024a1b  test    rcx, rcx
0x180024a1e  jz      short loc_180024A26
0x180024a20  call    cs:__imp_ReleaseSRWLockExclusive
0x180024a26  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180024a2b  mov     rdi, rax
0x180024a2e  mov     ecx, [rax]
0x180024a30  cmp     ecx, 5
0x180024a33  jbe     loc_180024ADB
0x180024a39  mov     rax, [rax+18h]
0x180024a3d  mov     rcx, [rdi+10h]
0x180024a41  test    r14, rcx
0x180024a44  jz      loc_180024ADB
0x180024a4a  mov     rcx, rax
0x180024a4d  and     rcx, r14
0x180024a50  cmp     rcx, rax
0x180024a53  jnz     loc_180024ADB
0x180024a59  call    cs:__imp_GetCurrentThreadId
0x180024a5f  mov     dword ptr [rbp+57h+SRWLock], eax
0x180024a62  mov     [rbp+57h+var_78], 1000000h
0x180024a6a  mov     r8, [rbx+110h]
0x180024a71  cmp     byte ptr [r8+4], 0
0x180024a76  jz      short loc_180024A97
0x180024a78  lea     r9, [r8+18h]
0x180024a7c  cmp     dword ptr [r9], 0
0x180024a80  jnz     short loc_180024A9A
0x180024a82  cmp     dword ptr [r9+4], 0
0x180024a87  jnz     short loc_180024A9A
0x180024a89  cmp     dword ptr [r9+8], 0
0x180024a8e  jnz     short loc_180024A9A
0x180024a90  cmp     dword ptr [r9+0Ch], 0
0x180024a95  jnz     short loc_180024A9A
0x180024a97  xor     r9d, r9d
0x180024a9a  lea     rax, [rbp+57h+SRWLock]
0x180024a9e  mov     [rbp+57h+var_40], rax
0x180024aa2  mov     ecx, 4
0x180024aa7  mov     [rbp+57h+var_38], rcx
0x180024aab  lea     rax, [rbp+57h+var_78]
0x180024aaf  mov     [rbp+57h+var_50], rax
0x180024ab3  mov     [rbp+57h+var_48], 8
0x180024abb  add     r8, 8
0x180024abf  lea     rax, [rbp+57h+var_70]
0x180024ac3  mov     [rsp+0B0h+var_88], rax
0x180024ac8  mov     [rsp+0B0h+var_90], ecx
0x180024acc  lea     rdx, unk_180088C70
0x180024ad3  mov     rcx, rdi
0x180024ad6  call    _tlgWriteTransfer_EventWriteTransfer
0x180024adb  cmp     dword ptr [rbx+138h], 0
0x180024ae2  jnz     short loc_180024B20
0x180024ae4  add     rbx, 120h
0x180024aeb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180024af3  jz      short loc_180024B19
0x180024af5  mov     dl, 1
0x180024af7  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180024afc  mov     [rbx], rax
0x180024aff  test    rax, rax
0x180024b02  jz      short loc_180024B20
0x180024b04  mov     rcx, [rax]
0x180024b07  mov     [rbx+10h], rcx
0x180024b0b  mov     [rax], rbx
0x180024b0e  call    cs:__imp_GetCurrentThreadId
0x180024b14  mov     [rbx+18h], eax
0x180024b17  jmp     short loc_180024B20
0x180024b19  mov     qword ptr [rbx], 0
0x180024b20  mov     rcx, [rbp+57h+var_30]
0x180024b24  xor     rcx, rsp; StackCookie
0x180024b27  call    __security_check_cookie
0x180024b2c  add     rsp, 98h
0x180024b33  pop     r14
0x180024b35  pop     rdi
0x180024b36  pop     rbx
0x180024b37  pop     rbp
0x180024b38  retn
```
