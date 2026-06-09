# IsoEnvBrokerTelemetry::ServiceStopActivity::StartActivity(void)

- ea: `0x180061aa0`
- end: `0x180061bf6`
- name: `?StartActivity@ServiceStopActivity@IsoEnvBrokerTelemetry@@QEAAXXZ`
- size: `342`
- prototype: `void __fastcall(IsoEnvBrokerTelemetry::ServiceStopActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180061100`

## callees

- `0x1800016cc`
- `0x180002520`
- `0x180007f60`
- `0x180011d64`
- `0x180061aa0`
- `0x180062a94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061b05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061bc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061b05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061bc3`

## pseudocode

```c
void __fastcall IsoEnvBrokerTelemetry::ServiceStopActivity::StartActivity(
        IsoEnvBrokerTelemetry::ServiceStopActivity *this)
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
      tlgWriteTransfer_EventWriteTransfer(v4, &dword_1800ABE8C, v5 + 8, v6, 4, v11);
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
0x180061aa0  mov     [rsp+arg_8], rbx
0x180061aa5  push    rdi
0x180061aa6  sub     rsp, 90h
0x180061aad  mov     rax, cs:__security_cookie
0x180061ab4  xor     rax, rsp
0x180061ab7  mov     [rsp+98h+var_18], rax
0x180061abf  mov     rbx, rcx
0x180061ac2  call    ?zInternalStart@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180061ac7  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180061acc  mov     rdi, [rax+8]
0x180061ad0  mov     eax, [rdi]
0x180061ad2  cmp     eax, 5
0x180061ad5  jbe     loc_180061B90
0x180061adb  mov     rcx, [rdi+18h]
0x180061adf  mov     rax, [rdi+10h]
0x180061ae3  mov     rdx, 200000000000h
0x180061aed  test    rdx, rax
0x180061af0  jz      loc_180061B90
0x180061af6  mov     rax, rcx
0x180061af9  and     rax, rdx
0x180061afc  cmp     rax, rcx
0x180061aff  jnz     loc_180061B90
0x180061b05  call    cs:__imp_GetCurrentThreadId
0x180061b0b  mov     [rsp+98h+var_68], eax
0x180061b0f  mov     [rsp+98h+var_60], 1000000h
0x180061b18  mov     r8, [rbx+110h]
0x180061b1f  cmp     byte ptr [r8+4], 0
0x180061b24  jz      short loc_180061B45
0x180061b26  lea     r9, [r8+18h]
0x180061b2a  cmp     dword ptr [r9], 0
0x180061b2e  jnz     short loc_180061B48
0x180061b30  cmp     dword ptr [r9+4], 0
0x180061b35  jnz     short loc_180061B48
0x180061b37  cmp     dword ptr [r9+8], 0
0x180061b3c  jnz     short loc_180061B48
0x180061b3e  cmp     dword ptr [r9+0Ch], 0
0x180061b43  jnz     short loc_180061B48
0x180061b45  xor     r9d, r9d
0x180061b48  lea     rax, [rsp+98h+var_68]
0x180061b4d  mov     [rsp+98h+var_28], rax
0x180061b52  mov     ecx, 4
0x180061b57  mov     [rsp+98h+var_20], rcx
0x180061b5c  lea     rax, [rsp+98h+var_60]
0x180061b61  mov     [rsp+98h+var_38], rax
0x180061b66  mov     [rsp+98h+var_30], 8
0x180061b6f  add     r8, 8
0x180061b73  lea     rax, [rsp+98h+var_58]
0x180061b78  mov     [rsp+98h+var_70], rax
0x180061b7d  mov     [rsp+98h+var_78], ecx
0x180061b81  lea     rdx, dword_1800ABE8C
0x180061b88  mov     rcx, rdi
0x180061b8b  call    _tlgWriteTransfer_EventWriteTransfer
0x180061b90  cmp     dword ptr [rbx+138h], 0
0x180061b97  jnz     short loc_180061BD5
0x180061b99  add     rbx, 120h
0x180061ba0  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180061ba8  jz      short loc_180061BCE
0x180061baa  mov     dl, 1
0x180061bac  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180061bb1  mov     [rbx], rax
0x180061bb4  test    rax, rax
0x180061bb7  jz      short loc_180061BD5
0x180061bb9  mov     rcx, [rax]
0x180061bbc  mov     [rbx+10h], rcx
0x180061bc0  mov     [rax], rbx
0x180061bc3  call    cs:__imp_GetCurrentThreadId
0x180061bc9  mov     [rbx+18h], eax
0x180061bcc  jmp     short loc_180061BD5
0x180061bce  mov     qword ptr [rbx], 0
0x180061bd5  mov     rcx, [rsp+98h+var_18]
0x180061bdd  xor     rcx, rsp; StackCookie
0x180061be0  call    __security_check_cookie
0x180061be5  mov     rbx, [rsp+98h+arg_8]
0x180061bed  add     rsp, 90h
0x180061bf4  pop     rdi
0x180061bf5  retn
```
