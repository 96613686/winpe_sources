# IsoEnvBrokerTelemetry::RegisterObjectsActivity::StartActivity(void)

- ea: `0x1800617e8`
- end: `0x18006193e`
- name: `?StartActivity@RegisterObjectsActivity@IsoEnvBrokerTelemetry@@QEAAXXZ`
- size: `342`
- prototype: `void __fastcall(IsoEnvBrokerTelemetry::RegisterObjectsActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180062ba8`

## callees

- `0x1800016cc`
- `0x180002520`
- `0x180007f60`
- `0x180011d64`
- `0x1800617e8`
- `0x180062a94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006184d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006190b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006184d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006190b`

## pseudocode

```c
void __fastcall IsoEnvBrokerTelemetry::RegisterObjectsActivity::StartActivity(
        IsoEnvBrokerTelemetry::RegisterObjectsActivity *this)
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
      tlgWriteTransfer_EventWriteTransfer(v4, &word_1800ABD0E, v5 + 8, v6, 4, v11);
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
0x1800617e8  mov     [rsp+arg_8], rbx
0x1800617ed  push    rdi
0x1800617ee  sub     rsp, 90h
0x1800617f5  mov     rax, cs:__security_cookie
0x1800617fc  xor     rax, rsp
0x1800617ff  mov     [rsp+98h+var_18], rax
0x180061807  mov     rbx, rcx
0x18006180a  call    ?zInternalStart@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18006180f  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180061814  mov     rdi, [rax+8]
0x180061818  mov     eax, [rdi]
0x18006181a  cmp     eax, 5
0x18006181d  jbe     loc_1800618D8
0x180061823  mov     rcx, [rdi+18h]
0x180061827  mov     rax, [rdi+10h]
0x18006182b  mov     rdx, 200000000000h
0x180061835  test    rdx, rax
0x180061838  jz      loc_1800618D8
0x18006183e  mov     rax, rcx
0x180061841  and     rax, rdx
0x180061844  cmp     rax, rcx
0x180061847  jnz     loc_1800618D8
0x18006184d  call    cs:__imp_GetCurrentThreadId
0x180061853  mov     [rsp+98h+var_68], eax
0x180061857  mov     [rsp+98h+var_60], 1000000h
0x180061860  mov     r8, [rbx+110h]
0x180061867  cmp     byte ptr [r8+4], 0
0x18006186c  jz      short loc_18006188D
0x18006186e  lea     r9, [r8+18h]
0x180061872  cmp     dword ptr [r9], 0
0x180061876  jnz     short loc_180061890
0x180061878  cmp     dword ptr [r9+4], 0
0x18006187d  jnz     short loc_180061890
0x18006187f  cmp     dword ptr [r9+8], 0
0x180061884  jnz     short loc_180061890
0x180061886  cmp     dword ptr [r9+0Ch], 0
0x18006188b  jnz     short loc_180061890
0x18006188d  xor     r9d, r9d
0x180061890  lea     rax, [rsp+98h+var_68]
0x180061895  mov     [rsp+98h+var_28], rax
0x18006189a  mov     ecx, 4
0x18006189f  mov     [rsp+98h+var_20], rcx
0x1800618a4  lea     rax, [rsp+98h+var_60]
0x1800618a9  mov     [rsp+98h+var_38], rax
0x1800618ae  mov     [rsp+98h+var_30], 8
0x1800618b7  add     r8, 8
0x1800618bb  lea     rax, [rsp+98h+var_58]
0x1800618c0  mov     [rsp+98h+var_70], rax
0x1800618c5  mov     [rsp+98h+var_78], ecx
0x1800618c9  lea     rdx, word_1800ABD0E
0x1800618d0  mov     rcx, rdi
0x1800618d3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800618d8  cmp     dword ptr [rbx+138h], 0
0x1800618df  jnz     short loc_18006191D
0x1800618e1  add     rbx, 120h
0x1800618e8  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800618f0  jz      short loc_180061916
0x1800618f2  mov     dl, 1
0x1800618f4  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800618f9  mov     [rbx], rax
0x1800618fc  test    rax, rax
0x1800618ff  jz      short loc_18006191D
0x180061901  mov     rcx, [rax]
0x180061904  mov     [rbx+10h], rcx
0x180061908  mov     [rax], rbx
0x18006190b  call    cs:__imp_GetCurrentThreadId
0x180061911  mov     [rbx+18h], eax
0x180061914  jmp     short loc_18006191D
0x180061916  mov     qword ptr [rbx], 0
0x18006191d  mov     rcx, [rsp+98h+var_18]
0x180061925  xor     rcx, rsp; StackCookie
0x180061928  call    __security_check_cookie
0x18006192d  mov     rbx, [rsp+98h+arg_8]
0x180061935  add     rsp, 90h
0x18006193c  pop     rdi
0x18006193d  retn
```
