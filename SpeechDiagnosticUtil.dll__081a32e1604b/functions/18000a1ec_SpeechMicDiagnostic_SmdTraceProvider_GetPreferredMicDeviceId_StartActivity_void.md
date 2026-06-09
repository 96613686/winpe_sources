# SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId::StartActivity(void *)

- ea: `0x18000a1ec`
- end: `0x18000a337`
- name: `?StartActivity@GetPreferredMicDeviceId@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z`
- size: `331`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800082d0`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800049bc`
- `0x1800068cc`
- `0x18000a1ec`
- `0x18000d774`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a23a`
- `KERNEL32!GetCurrentThreadId` at `0x18000a2fe`
- `KERNEL32!GetCurrentThreadId` at `0x18000a23a`
- `KERNEL32!GetCurrentThreadId` at `0x18000a2fe`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId::StartActivity(
        SpeechMicDiagnostic::SmdTraceProvider::GetPreferredMicDeviceId *this,
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
    tlgWriteTransfer_EventWriteTransfer(v6, byte_180014013, v8 + 8);
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
0x18000a1ec  mov     [rsp-8+arg_8], rbx
0x18000a1f1  mov     [rsp-8+arg_10], rsi
0x18000a1f6  push    rbp
0x18000a1f7  push    rdi
0x18000a1f8  push    r14
0x18000a1fa  lea     rbp, [rsp-47h]
0x18000a1ff  sub     rsp, 0B0h
0x18000a206  mov     rax, cs:__security_cookie
0x18000a20d  xor     rax, rsp
0x18000a210  mov     [rbp+57h+var_20], rax
0x18000a214  mov     rdi, rdx
0x18000a217  mov     rbx, rcx
0x18000a21a  call    ?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000a21f  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000a224  xor     r14d, r14d
0x18000a227  mov     rsi, [rax+8]
0x18000a22b  mov     eax, [rsi]
0x18000a22d  cmp     eax, 5
0x18000a230  jbe     loc_18000A2CC
0x18000a236  mov     [rbp+57h+var_88], rdi
0x18000a23a  call    cs:__imp_GetCurrentThreadId
0x18000a241  nop     dword ptr [rax+rax+00h]
0x18000a246  mov     r8, [rbx+110h]
0x18000a24d  mov     [rbp+57h+var_90], eax
0x18000a250  mov     [rbp+57h+var_80], r14
0x18000a254  cmp     [r8+4], r14b
0x18000a258  jz      short loc_18000A275
0x18000a25a  lea     r9, [r8+18h]
0x18000a25e  cmp     [r9], r14d
0x18000a261  jnz     short loc_18000A278
0x18000a263  cmp     [r9+4], r14d
0x18000a267  jnz     short loc_18000A278
0x18000a269  cmp     [r9+8], r14d
0x18000a26d  jnz     short loc_18000A278
0x18000a26f  cmp     [r9+0Ch], r14d
0x18000a273  jnz     short loc_18000A278
0x18000a275  mov     r9, r14
0x18000a278  lea     rax, [rbp+57h+var_88]
0x18000a27c  mov     [rbp+57h+var_28], 8
0x18000a284  mov     [rbp+57h+var_30], rax
0x18000a288  lea     rdx, byte_180014013
0x18000a28f  lea     rax, [rbp+57h+var_90]
0x18000a293  mov     [rbp+57h+var_38], 4
0x18000a29b  mov     [rbp+57h+var_40], rax
0x18000a29f  add     r8, 8
0x18000a2a3  lea     rax, [rbp+57h+var_80]
0x18000a2a7  mov     [rbp+57h+var_48], 8
0x18000a2af  mov     [rbp+57h+var_50], rax
0x18000a2b3  mov     rcx, rsi
0x18000a2b6  lea     rax, [rbp+57h+var_70]
0x18000a2ba  mov     [rsp+0C0h+var_98], rax
0x18000a2bf  mov     [rsp+0C0h+var_A0], 5
0x18000a2c7  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a2cc  cmp     [rbx+138h], r14d
0x18000a2d3  jnz     short loc_18000A312
0x18000a2d5  add     rbx, 120h
0x18000a2dc  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a2e3  jz      short loc_18000A30F
0x18000a2e5  mov     dl, 1
0x18000a2e7  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000a2ec  mov     [rbx], rax
0x18000a2ef  test    rax, rax
0x18000a2f2  jz      short loc_18000A312
0x18000a2f4  mov     rcx, [rax]
0x18000a2f7  mov     [rbx+10h], rcx
0x18000a2fb  mov     [rax], rbx
0x18000a2fe  call    cs:__imp_GetCurrentThreadId
0x18000a305  nop     dword ptr [rax+rax+00h]
0x18000a30a  mov     [rbx+18h], eax
0x18000a30d  jmp     short loc_18000A312
0x18000a30f  mov     [rbx], r14
0x18000a312  mov     rcx, [rbp+57h+var_20]
0x18000a316  xor     rcx, rsp; StackCookie
0x18000a319  call    __security_check_cookie
0x18000a31e  lea     r11, [rsp+0C0h+var_10]
0x18000a326  mov     rbx, [r11+28h]
0x18000a32a  mov     rsi, [r11+30h]
0x18000a32e  mov     rsp, r11
0x18000a331  pop     r14
0x18000a333  pop     rdi
0x18000a334  pop     rbp
0x18000a335  retn
```
