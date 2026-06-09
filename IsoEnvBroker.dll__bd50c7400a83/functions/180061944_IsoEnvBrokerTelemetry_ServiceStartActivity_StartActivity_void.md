# IsoEnvBrokerTelemetry::ServiceStartActivity::StartActivity(void)

- ea: `0x180061944`
- end: `0x180061a9a`
- name: `?StartActivity@ServiceStartActivity@IsoEnvBrokerTelemetry@@QEAAXXZ`
- size: `342`
- prototype: `void __fastcall(IsoEnvBrokerTelemetry::ServiceStartActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062ba8`

## callees

- `0x1800016cc`
- `0x180002520`
- `0x180007f60`
- `0x180011d64`
- `0x180061944`
- `0x180062a94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800619a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061a67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800619a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061a67`

## pseudocode

```c
void __fastcall IsoEnvBrokerTelemetry::ServiceStartActivity::StartActivity(
        IsoEnvBrokerTelemetry::ServiceStartActivity *this)
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
      tlgWriteTransfer_EventWriteTransfer(v4, &word_1800AC056, v5 + 8, v6, 4, v11);
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
0x180061944  mov     [rsp+arg_8], rbx
0x180061949  push    rdi
0x18006194a  sub     rsp, 90h
0x180061951  mov     rax, cs:__security_cookie
0x180061958  xor     rax, rsp
0x18006195b  mov     [rsp+98h+var_18], rax
0x180061963  mov     rbx, rcx
0x180061966  call    ?zInternalStart@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18006196b  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180061970  mov     rdi, [rax+8]
0x180061974  mov     eax, [rdi]
0x180061976  cmp     eax, 5
0x180061979  jbe     loc_180061A34
0x18006197f  mov     rcx, [rdi+18h]
0x180061983  mov     rax, [rdi+10h]
0x180061987  mov     rdx, 200000000000h
0x180061991  test    rdx, rax
0x180061994  jz      loc_180061A34
0x18006199a  mov     rax, rcx
0x18006199d  and     rax, rdx
0x1800619a0  cmp     rax, rcx
0x1800619a3  jnz     loc_180061A34
0x1800619a9  call    cs:__imp_GetCurrentThreadId
0x1800619af  mov     [rsp+98h+var_68], eax
0x1800619b3  mov     [rsp+98h+var_60], 1000000h
0x1800619bc  mov     r8, [rbx+110h]
0x1800619c3  cmp     byte ptr [r8+4], 0
0x1800619c8  jz      short loc_1800619E9
0x1800619ca  lea     r9, [r8+18h]
0x1800619ce  cmp     dword ptr [r9], 0
0x1800619d2  jnz     short loc_1800619EC
0x1800619d4  cmp     dword ptr [r9+4], 0
0x1800619d9  jnz     short loc_1800619EC
0x1800619db  cmp     dword ptr [r9+8], 0
0x1800619e0  jnz     short loc_1800619EC
0x1800619e2  cmp     dword ptr [r9+0Ch], 0
0x1800619e7  jnz     short loc_1800619EC
0x1800619e9  xor     r9d, r9d
0x1800619ec  lea     rax, [rsp+98h+var_68]
0x1800619f1  mov     [rsp+98h+var_28], rax
0x1800619f6  mov     ecx, 4
0x1800619fb  mov     [rsp+98h+var_20], rcx
0x180061a00  lea     rax, [rsp+98h+var_60]
0x180061a05  mov     [rsp+98h+var_38], rax
0x180061a0a  mov     [rsp+98h+var_30], 8
0x180061a13  add     r8, 8
0x180061a17  lea     rax, [rsp+98h+var_58]
0x180061a1c  mov     [rsp+98h+var_70], rax
0x180061a21  mov     [rsp+98h+var_78], ecx
0x180061a25  lea     rdx, word_1800AC056
0x180061a2c  mov     rcx, rdi
0x180061a2f  call    _tlgWriteTransfer_EventWriteTransfer
0x180061a34  cmp     dword ptr [rbx+138h], 0
0x180061a3b  jnz     short loc_180061A79
0x180061a3d  add     rbx, 120h
0x180061a44  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180061a4c  jz      short loc_180061A72
0x180061a4e  mov     dl, 1
0x180061a50  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180061a55  mov     [rbx], rax
0x180061a58  test    rax, rax
0x180061a5b  jz      short loc_180061A79
0x180061a5d  mov     rcx, [rax]
0x180061a60  mov     [rbx+10h], rcx
0x180061a64  mov     [rax], rbx
0x180061a67  call    cs:__imp_GetCurrentThreadId
0x180061a6d  mov     [rbx+18h], eax
0x180061a70  jmp     short loc_180061A79
0x180061a72  mov     qword ptr [rbx], 0
0x180061a79  mov     rcx, [rsp+98h+var_18]
0x180061a81  xor     rcx, rsp; StackCookie
0x180061a84  call    __security_check_cookie
0x180061a89  mov     rbx, [rsp+98h+arg_8]
0x180061a91  add     rsp, 90h
0x180061a98  pop     rdi
0x180061a99  retn
```
