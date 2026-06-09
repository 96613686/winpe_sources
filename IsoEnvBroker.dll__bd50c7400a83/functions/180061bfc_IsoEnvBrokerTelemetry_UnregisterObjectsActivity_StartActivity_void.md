# IsoEnvBrokerTelemetry::UnregisterObjectsActivity::StartActivity(void)

- ea: `0x180061bfc`
- end: `0x180061d52`
- name: `?StartActivity@UnregisterObjectsActivity@IsoEnvBrokerTelemetry@@QEAAXXZ`
- size: `342`
- prototype: `void __fastcall(IsoEnvBrokerTelemetry::UnregisterObjectsActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180061100`

## callees

- `0x1800016cc`
- `0x180002520`
- `0x180007f60`
- `0x180011d64`
- `0x180061bfc`
- `0x180062a94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061c61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061c61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061d1f`

## pseudocode

```c
void __fastcall IsoEnvBrokerTelemetry::UnregisterObjectsActivity::StartActivity(
        IsoEnvBrokerTelemetry::UnregisterObjectsActivity *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  char *v7; // rbx
  _QWORD *Local; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v10; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v12; // [rsp+60h] [rbp-38h]
  __int64 v13; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v15; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = *((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
  if ( *(_DWORD *)v4 > 5u )
  {
    v3 = *(_QWORD *)(v4 + 24);
    v2 = 0x200000000000LL;
    if ( (*(_QWORD *)(v4 + 16) & 0x200000000000LL) != 0 && (v3 & 0x200000000000LL) == v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
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
      p_CurrentThreadId = &CurrentThreadId;
      v15 = 4;
      v12 = &v10;
      v13 = 8;
      tlgWriteTransfer_EventWriteTransfer(v4, word_1800ABADA, v5 + 8, v6, 4, v11);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v7 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v2) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          v2);
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
0x180061bfc  mov     [rsp+arg_8], rbx
0x180061c01  push    rdi
0x180061c02  sub     rsp, 90h
0x180061c09  mov     rax, cs:__security_cookie
0x180061c10  xor     rax, rsp
0x180061c13  mov     [rsp+98h+var_18], rax
0x180061c1b  mov     rbx, rcx
0x180061c1e  call    ?zInternalStart@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180061c23  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180061c28  mov     rdi, [rax+8]
0x180061c2c  mov     eax, [rdi]
0x180061c2e  cmp     eax, 5
0x180061c31  jbe     loc_180061CEC
0x180061c37  mov     rcx, [rdi+18h]
0x180061c3b  mov     rax, [rdi+10h]
0x180061c3f  mov     rdx, 200000000000h
0x180061c49  test    rdx, rax
0x180061c4c  jz      loc_180061CEC
0x180061c52  mov     rax, rcx
0x180061c55  and     rax, rdx
0x180061c58  cmp     rax, rcx
0x180061c5b  jnz     loc_180061CEC
0x180061c61  call    cs:__imp_GetCurrentThreadId
0x180061c67  mov     [rsp+98h+var_68], eax
0x180061c6b  mov     [rsp+98h+var_60], 1000000h
0x180061c74  mov     r8, [rbx+110h]
0x180061c7b  cmp     byte ptr [r8+4], 0
0x180061c80  jz      short loc_180061CA1
0x180061c82  lea     r9, [r8+18h]
0x180061c86  cmp     dword ptr [r9], 0
0x180061c8a  jnz     short loc_180061CA4
0x180061c8c  cmp     dword ptr [r9+4], 0
0x180061c91  jnz     short loc_180061CA4
0x180061c93  cmp     dword ptr [r9+8], 0
0x180061c98  jnz     short loc_180061CA4
0x180061c9a  cmp     dword ptr [r9+0Ch], 0
0x180061c9f  jnz     short loc_180061CA4
0x180061ca1  xor     r9d, r9d
0x180061ca4  lea     rax, [rsp+98h+var_68]
0x180061ca9  mov     [rsp+98h+var_28], rax
0x180061cae  mov     ecx, 4
0x180061cb3  mov     [rsp+98h+var_20], rcx
0x180061cb8  lea     rax, [rsp+98h+var_60]
0x180061cbd  mov     [rsp+98h+var_38], rax
0x180061cc2  mov     [rsp+98h+var_30], 8
0x180061ccb  add     r8, 8
0x180061ccf  lea     rax, [rsp+98h+var_58]
0x180061cd4  mov     [rsp+98h+var_70], rax
0x180061cd9  mov     [rsp+98h+var_78], ecx
0x180061cdd  lea     rdx, word_1800ABADA
0x180061ce4  mov     rcx, rdi
0x180061ce7  call    _tlgWriteTransfer_EventWriteTransfer
0x180061cec  cmp     dword ptr [rbx+138h], 0
0x180061cf3  jnz     short loc_180061D31
0x180061cf5  add     rbx, 120h
0x180061cfc  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180061d04  jz      short loc_180061D2A
0x180061d06  mov     dl, 1
0x180061d08  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180061d0d  mov     [rbx], rax
0x180061d10  test    rax, rax
0x180061d13  jz      short loc_180061D31
0x180061d15  mov     rcx, [rax]
0x180061d18  mov     [rbx+10h], rcx
0x180061d1c  mov     [rax], rbx
0x180061d1f  call    cs:__imp_GetCurrentThreadId
0x180061d25  mov     [rbx+18h], eax
0x180061d28  jmp     short loc_180061D31
0x180061d2a  mov     qword ptr [rbx], 0
0x180061d31  mov     rcx, [rsp+98h+var_18]
0x180061d39  xor     rcx, rsp; StackCookie
0x180061d3c  call    __security_check_cookie
0x180061d41  mov     rbx, [rsp+98h+arg_8]
0x180061d49  add     rsp, 90h
0x180061d50  pop     rdi
0x180061d51  retn
```
