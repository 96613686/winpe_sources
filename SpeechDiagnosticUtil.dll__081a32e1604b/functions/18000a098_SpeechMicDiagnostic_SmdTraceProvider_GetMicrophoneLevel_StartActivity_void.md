# SpeechMicDiagnostic::SmdTraceProvider::GetMicrophoneLevel::StartActivity(void *)

- ea: `0x18000a098`
- end: `0x18000a1e3`
- name: `?StartActivity@GetMicrophoneLevel@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z`
- size: `331`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetMicrophoneLevel *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008190`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800049bc`
- `0x1800068cc`
- `0x18000a098`
- `0x18000d774`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a0e6`
- `KERNEL32!GetCurrentThreadId` at `0x18000a1aa`
- `KERNEL32!GetCurrentThreadId` at `0x18000a0e6`
- `KERNEL32!GetCurrentThreadId` at `0x18000a1aa`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetMicrophoneLevel::StartActivity(
        SpeechMicDiagnostic::SmdTraceProvider::GetMicrophoneLevel *this,
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
    tlgWriteTransfer_EventWriteTransfer(v6, byte_180013E7D, v8 + 8);
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
0x18000a098  mov     [rsp-8+arg_8], rbx
0x18000a09d  mov     [rsp-8+arg_10], rsi
0x18000a0a2  push    rbp
0x18000a0a3  push    rdi
0x18000a0a4  push    r14
0x18000a0a6  lea     rbp, [rsp-47h]
0x18000a0ab  sub     rsp, 0B0h
0x18000a0b2  mov     rax, cs:__security_cookie
0x18000a0b9  xor     rax, rsp
0x18000a0bc  mov     [rbp+57h+var_20], rax
0x18000a0c0  mov     rdi, rdx
0x18000a0c3  mov     rbx, rcx
0x18000a0c6  call    ?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000a0cb  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000a0d0  xor     r14d, r14d
0x18000a0d3  mov     rsi, [rax+8]
0x18000a0d7  mov     eax, [rsi]
0x18000a0d9  cmp     eax, 5
0x18000a0dc  jbe     loc_18000A178
0x18000a0e2  mov     [rbp+57h+var_88], rdi
0x18000a0e6  call    cs:__imp_GetCurrentThreadId
0x18000a0ed  nop     dword ptr [rax+rax+00h]
0x18000a0f2  mov     r8, [rbx+110h]
0x18000a0f9  mov     [rbp+57h+var_90], eax
0x18000a0fc  mov     [rbp+57h+var_80], r14
0x18000a100  cmp     [r8+4], r14b
0x18000a104  jz      short loc_18000A121
0x18000a106  lea     r9, [r8+18h]
0x18000a10a  cmp     [r9], r14d
0x18000a10d  jnz     short loc_18000A124
0x18000a10f  cmp     [r9+4], r14d
0x18000a113  jnz     short loc_18000A124
0x18000a115  cmp     [r9+8], r14d
0x18000a119  jnz     short loc_18000A124
0x18000a11b  cmp     [r9+0Ch], r14d
0x18000a11f  jnz     short loc_18000A124
0x18000a121  mov     r9, r14
0x18000a124  lea     rax, [rbp+57h+var_88]
0x18000a128  mov     [rbp+57h+var_28], 8
0x18000a130  mov     [rbp+57h+var_30], rax
0x18000a134  lea     rdx, byte_180013E7D
0x18000a13b  lea     rax, [rbp+57h+var_90]
0x18000a13f  mov     [rbp+57h+var_38], 4
0x18000a147  mov     [rbp+57h+var_40], rax
0x18000a14b  add     r8, 8
0x18000a14f  lea     rax, [rbp+57h+var_80]
0x18000a153  mov     [rbp+57h+var_48], 8
0x18000a15b  mov     [rbp+57h+var_50], rax
0x18000a15f  mov     rcx, rsi
0x18000a162  lea     rax, [rbp+57h+var_70]
0x18000a166  mov     [rsp+0C0h+var_98], rax
0x18000a16b  mov     [rsp+0C0h+var_A0], 5
0x18000a173  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a178  cmp     [rbx+138h], r14d
0x18000a17f  jnz     short loc_18000A1BE
0x18000a181  add     rbx, 120h
0x18000a188  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a18f  jz      short loc_18000A1BB
0x18000a191  mov     dl, 1
0x18000a193  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000a198  mov     [rbx], rax
0x18000a19b  test    rax, rax
0x18000a19e  jz      short loc_18000A1BE
0x18000a1a0  mov     rcx, [rax]
0x18000a1a3  mov     [rbx+10h], rcx
0x18000a1a7  mov     [rax], rbx
0x18000a1aa  call    cs:__imp_GetCurrentThreadId
0x18000a1b1  nop     dword ptr [rax+rax+00h]
0x18000a1b6  mov     [rbx+18h], eax
0x18000a1b9  jmp     short loc_18000A1BE
0x18000a1bb  mov     [rbx], r14
0x18000a1be  mov     rcx, [rbp+57h+var_20]
0x18000a1c2  xor     rcx, rsp; StackCookie
0x18000a1c5  call    __security_check_cookie
0x18000a1ca  lea     r11, [rsp+0C0h+var_10]
0x18000a1d2  mov     rbx, [r11+28h]
0x18000a1d6  mov     rsi, [r11+30h]
0x18000a1da  mov     rsp, r11
0x18000a1dd  pop     r14
0x18000a1df  pop     rdi
0x18000a1e0  pop     rbp
0x18000a1e1  retn
```
