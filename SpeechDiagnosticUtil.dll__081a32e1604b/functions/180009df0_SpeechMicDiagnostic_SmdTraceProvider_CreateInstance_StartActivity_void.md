# SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::StartActivity(void *)

- ea: `0x180009df0`
- end: `0x180009f3b`
- name: `?StartActivity@CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z`
- size: `331`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007e38`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800049bc`
- `0x1800068cc`
- `0x180009df0`
- `0x18000d774`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009e3e`
- `KERNEL32!GetCurrentThreadId` at `0x180009f02`
- `KERNEL32!GetCurrentThreadId` at `0x180009e3e`
- `KERNEL32!GetCurrentThreadId` at `0x180009f02`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::StartActivity(
        SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *this,
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
    tlgWriteTransfer_EventWriteTransfer(v6, byte_1800140D9, v8 + 8);
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
0x180009df0  mov     [rsp-8+arg_8], rbx
0x180009df5  mov     [rsp-8+arg_10], rsi
0x180009dfa  push    rbp
0x180009dfb  push    rdi
0x180009dfc  push    r14
0x180009dfe  lea     rbp, [rsp-47h]
0x180009e03  sub     rsp, 0B0h
0x180009e0a  mov     rax, cs:__security_cookie
0x180009e11  xor     rax, rsp
0x180009e14  mov     [rbp+57h+var_20], rax
0x180009e18  mov     rdi, rdx
0x180009e1b  mov     rbx, rcx
0x180009e1e  call    ?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180009e23  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x180009e28  xor     r14d, r14d
0x180009e2b  mov     rsi, [rax+8]
0x180009e2f  mov     eax, [rsi]
0x180009e31  cmp     eax, 5
0x180009e34  jbe     loc_180009ED0
0x180009e3a  mov     [rbp+57h+var_88], rdi
0x180009e3e  call    cs:__imp_GetCurrentThreadId
0x180009e45  nop     dword ptr [rax+rax+00h]
0x180009e4a  mov     r8, [rbx+110h]
0x180009e51  mov     [rbp+57h+var_90], eax
0x180009e54  mov     [rbp+57h+var_80], r14
0x180009e58  cmp     [r8+4], r14b
0x180009e5c  jz      short loc_180009E79
0x180009e5e  lea     r9, [r8+18h]
0x180009e62  cmp     [r9], r14d
0x180009e65  jnz     short loc_180009E7C
0x180009e67  cmp     [r9+4], r14d
0x180009e6b  jnz     short loc_180009E7C
0x180009e6d  cmp     [r9+8], r14d
0x180009e71  jnz     short loc_180009E7C
0x180009e73  cmp     [r9+0Ch], r14d
0x180009e77  jnz     short loc_180009E7C
0x180009e79  mov     r9, r14
0x180009e7c  lea     rax, [rbp+57h+var_88]
0x180009e80  mov     [rbp+57h+var_28], 8
0x180009e88  mov     [rbp+57h+var_30], rax
0x180009e8c  lea     rdx, byte_1800140D9
0x180009e93  lea     rax, [rbp+57h+var_90]
0x180009e97  mov     [rbp+57h+var_38], 4
0x180009e9f  mov     [rbp+57h+var_40], rax
0x180009ea3  add     r8, 8
0x180009ea7  lea     rax, [rbp+57h+var_80]
0x180009eab  mov     [rbp+57h+var_48], 8
0x180009eb3  mov     [rbp+57h+var_50], rax
0x180009eb7  mov     rcx, rsi
0x180009eba  lea     rax, [rbp+57h+var_70]
0x180009ebe  mov     [rsp+0C0h+var_98], rax
0x180009ec3  mov     [rsp+0C0h+var_A0], 5
0x180009ecb  call    _tlgWriteTransfer_EventWriteTransfer
0x180009ed0  cmp     [rbx+138h], r14d
0x180009ed7  jnz     short loc_180009F16
0x180009ed9  add     rbx, 120h
0x180009ee0  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009ee7  jz      short loc_180009F13
0x180009ee9  mov     dl, 1
0x180009eeb  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180009ef0  mov     [rbx], rax
0x180009ef3  test    rax, rax
0x180009ef6  jz      short loc_180009F16
0x180009ef8  mov     rcx, [rax]
0x180009efb  mov     [rbx+10h], rcx
0x180009eff  mov     [rax], rbx
0x180009f02  call    cs:__imp_GetCurrentThreadId
0x180009f09  nop     dword ptr [rax+rax+00h]
0x180009f0e  mov     [rbx+18h], eax
0x180009f11  jmp     short loc_180009F16
0x180009f13  mov     [rbx], r14
0x180009f16  mov     rcx, [rbp+57h+var_20]
0x180009f1a  xor     rcx, rsp; StackCookie
0x180009f1d  call    __security_check_cookie
0x180009f22  lea     r11, [rsp+0C0h+var_10]
0x180009f2a  mov     rbx, [r11+28h]
0x180009f2e  mov     rsi, [r11+30h]
0x180009f32  mov     rsp, r11
0x180009f35  pop     r14
0x180009f37  pop     rdi
0x180009f38  pop     rbp
0x180009f39  retn
```
