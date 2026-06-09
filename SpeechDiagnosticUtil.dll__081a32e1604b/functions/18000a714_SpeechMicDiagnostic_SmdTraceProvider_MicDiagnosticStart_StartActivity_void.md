# SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticStart::StartActivity(void *)

- ea: `0x18000a714`
- end: `0x18000a85f`
- name: `?StartActivity@MicDiagnosticStart@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z`
- size: `331`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticStart *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009330`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800049bc`
- `0x1800068cc`
- `0x18000a714`
- `0x18000d774`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a762`
- `KERNEL32!GetCurrentThreadId` at `0x18000a826`
- `KERNEL32!GetCurrentThreadId` at `0x18000a762`
- `KERNEL32!GetCurrentThreadId` at `0x18000a826`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticStart::StartActivity(
        SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticStart *this,
        void *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  _DWORD *v6; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  char *v9; // rbx
  _QWORD *Local; // rax
  DWORD v11; // [rsp+30h] [rbp-39h] BYREF
  void *v12; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v13[12]; // [rsp+40h] [rbp-29h] BYREF

  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
  if ( *v6 > 5u )
  {
    v12 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)this + 34);
    v11 = CurrentThreadId;
    v13[0] = 0;
    v13[11] = 8;
    v13[10] = &v12;
    v13[9] = 4;
    v13[8] = &v11;
    v13[7] = 8;
    v13[6] = v13;
    tlgWriteTransfer_EventWriteTransfer(v6, word_180013F1A, v8 + 8);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v9 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v4) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v5,
                          v4);
      *(_QWORD *)v9 = Local;
      if ( Local )
      {
        *((_QWORD *)v9 + 2) = *Local;
        *Local = v9;
        *((_DWORD *)v9 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v9 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000a714  mov     [rsp-8+arg_8], rbx
0x18000a719  mov     [rsp-8+arg_10], rsi
0x18000a71e  push    rbp
0x18000a71f  push    rdi
0x18000a720  push    r14
0x18000a722  lea     rbp, [rsp-47h]
0x18000a727  sub     rsp, 0B0h
0x18000a72e  mov     rax, cs:__security_cookie
0x18000a735  xor     rax, rsp
0x18000a738  mov     [rbp+57h+var_20], rax
0x18000a73c  mov     rdi, rdx
0x18000a73f  mov     rbx, rcx
0x18000a742  call    ?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000a747  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000a74c  xor     r14d, r14d
0x18000a74f  mov     rsi, [rax+8]
0x18000a753  mov     eax, [rsi]
0x18000a755  cmp     eax, 5
0x18000a758  jbe     loc_18000A7F4
0x18000a75e  mov     [rbp+57h+var_88], rdi
0x18000a762  call    cs:__imp_GetCurrentThreadId
0x18000a769  nop     dword ptr [rax+rax+00h]
0x18000a76e  mov     r8, [rbx+110h]
0x18000a775  mov     [rbp+57h+var_90], eax
0x18000a778  mov     [rbp+57h+var_80], r14
0x18000a77c  cmp     [r8+4], r14b
0x18000a780  jz      short loc_18000A79D
0x18000a782  lea     r9, [r8+18h]
0x18000a786  cmp     [r9], r14d
0x18000a789  jnz     short loc_18000A7A0
0x18000a78b  cmp     [r9+4], r14d
0x18000a78f  jnz     short loc_18000A7A0
0x18000a791  cmp     [r9+8], r14d
0x18000a795  jnz     short loc_18000A7A0
0x18000a797  cmp     [r9+0Ch], r14d
0x18000a79b  jnz     short loc_18000A7A0
0x18000a79d  mov     r9, r14
0x18000a7a0  lea     rax, [rbp+57h+var_88]
0x18000a7a4  mov     [rbp+57h+var_28], 8
0x18000a7ac  mov     [rbp+57h+var_30], rax
0x18000a7b0  lea     rdx, word_180013F1A
0x18000a7b7  lea     rax, [rbp+57h+var_90]
0x18000a7bb  mov     [rbp+57h+var_38], 4
0x18000a7c3  mov     [rbp+57h+var_40], rax
0x18000a7c7  add     r8, 8
0x18000a7cb  lea     rax, [rbp+57h+var_80]
0x18000a7cf  mov     [rbp+57h+var_48], 8
0x18000a7d7  mov     [rbp+57h+var_50], rax
0x18000a7db  mov     rcx, rsi
0x18000a7de  lea     rax, [rbp+57h+var_70]
0x18000a7e2  mov     [rsp+0C0h+var_98], rax
0x18000a7e7  mov     [rsp+0C0h+var_A0], 5
0x18000a7ef  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a7f4  cmp     [rbx+138h], r14d
0x18000a7fb  jnz     short loc_18000A83A
0x18000a7fd  add     rbx, 120h
0x18000a804  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a80b  jz      short loc_18000A837
0x18000a80d  mov     dl, 1
0x18000a80f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000a814  mov     [rbx], rax
0x18000a817  test    rax, rax
0x18000a81a  jz      short loc_18000A83A
0x18000a81c  mov     rcx, [rax]
0x18000a81f  mov     [rbx+10h], rcx
0x18000a823  mov     [rax], rbx
0x18000a826  call    cs:__imp_GetCurrentThreadId
0x18000a82d  nop     dword ptr [rax+rax+00h]
0x18000a832  mov     [rbx+18h], eax
0x18000a835  jmp     short loc_18000A83A
0x18000a837  mov     [rbx], r14
0x18000a83a  mov     rcx, [rbp+57h+var_20]
0x18000a83e  xor     rcx, rsp; StackCookie
0x18000a841  call    __security_check_cookie
0x18000a846  lea     r11, [rsp+0C0h+var_10]
0x18000a84e  mov     rbx, [r11+28h]
0x18000a852  mov     rsi, [r11+30h]
0x18000a856  mov     rsp, r11
0x18000a859  pop     r14
0x18000a85b  pop     rdi
0x18000a85c  pop     rbp
0x18000a85d  retn
```
