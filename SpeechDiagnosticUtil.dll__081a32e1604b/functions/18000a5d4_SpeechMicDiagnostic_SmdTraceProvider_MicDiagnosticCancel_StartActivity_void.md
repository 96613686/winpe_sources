# SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticCancel::StartActivity(void)

- ea: `0x18000a5d4`
- end: `0x18000a70d`
- name: `?StartActivity@MicDiagnosticCancel@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXXZ`
- size: `313`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticCancel *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008fe0`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800049bc`
- `0x1800068cc`
- `0x18000a5d4`
- `0x18000d774`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a60f`
- `KERNEL32!GetCurrentThreadId` at `0x18000a6d3`
- `KERNEL32!GetCurrentThreadId` at `0x18000a60f`
- `KERNEL32!GetCurrentThreadId` at `0x18000a6d3`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticCancel::StartActivity(
        SpeechMicDiagnostic::SmdTraceProvider::MicDiagnosticCancel *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  _DWORD *v4; // rdi
  __int64 v5; // r8
  char *v6; // rbx
  _QWORD *Local; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v9[9]; // [rsp+38h] [rbp-60h] BYREF

  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
  if ( *v4 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9[0] = 0;
    v5 = *((_QWORD *)this + 34);
    v9[7] = &CurrentThreadId;
    v9[8] = 4;
    v9[5] = v9;
    v9[6] = 8;
    tlgWriteTransfer_EventWriteTransfer(v4, &byte_180013ECF, v5 + 8);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v6 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v2) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          v2);
      *(_QWORD *)v6 = Local;
      if ( Local )
      {
        *((_QWORD *)v6 + 2) = *Local;
        *Local = v6;
        *((_DWORD *)v6 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v6 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000a5d4  mov     [rsp+arg_8], rbx
0x18000a5d9  push    rdi
0x18000a5da  sub     rsp, 90h
0x18000a5e1  mov     rax, cs:__security_cookie
0x18000a5e8  xor     rax, rsp
0x18000a5eb  mov     [rsp+98h+var_18], rax
0x18000a5f3  mov     rbx, rcx
0x18000a5f6  call    ?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000a5fb  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000a600  mov     rdi, [rax+8]
0x18000a604  mov     eax, [rdi]
0x18000a606  cmp     eax, 5
0x18000a609  jbe     loc_18000A6A0
0x18000a60f  call    cs:__imp_GetCurrentThreadId
0x18000a616  nop     dword ptr [rax+rax+00h]
0x18000a61b  mov     [rsp+98h+var_68], eax
0x18000a61f  mov     [rsp+98h+var_60], 0
0x18000a628  mov     r8, [rbx+110h]
0x18000a62f  cmp     byte ptr [r8+4], 0
0x18000a634  jz      short loc_18000A655
0x18000a636  lea     r9, [r8+18h]
0x18000a63a  cmp     dword ptr [r9], 0
0x18000a63e  jnz     short loc_18000A658
0x18000a640  cmp     dword ptr [r9+4], 0
0x18000a645  jnz     short loc_18000A658
0x18000a647  cmp     dword ptr [r9+8], 0
0x18000a64c  jnz     short loc_18000A658
0x18000a64e  cmp     dword ptr [r9+0Ch], 0
0x18000a653  jnz     short loc_18000A658
0x18000a655  xor     r9d, r9d
0x18000a658  lea     rax, [rsp+98h+var_68]
0x18000a65d  mov     [rsp+98h+var_28], rax
0x18000a662  mov     ecx, 4
0x18000a667  mov     [rsp+98h+var_20], rcx
0x18000a66c  lea     rax, [rsp+98h+var_60]
0x18000a671  mov     [rsp+98h+var_38], rax
0x18000a676  mov     [rsp+98h+var_30], 8
0x18000a67f  add     r8, 8
0x18000a683  lea     rax, [rsp+98h+var_58]
0x18000a688  mov     [rsp+98h+var_70], rax
0x18000a68d  mov     [rsp+98h+var_78], ecx
0x18000a691  lea     rdx, byte_180013ECF
0x18000a698  mov     rcx, rdi
0x18000a69b  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a6a0  cmp     dword ptr [rbx+138h], 0
0x18000a6a7  jnz     short loc_18000A6EB
0x18000a6a9  add     rbx, 120h
0x18000a6b0  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a6b8  jz      short loc_18000A6E4
0x18000a6ba  mov     dl, 1
0x18000a6bc  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000a6c1  mov     [rbx], rax
0x18000a6c4  test    rax, rax
0x18000a6c7  jz      short loc_18000A6EB
0x18000a6c9  mov     rcx, [rax]
0x18000a6cc  mov     [rbx+10h], rcx
0x18000a6d0  mov     [rax], rbx
0x18000a6d3  call    cs:__imp_GetCurrentThreadId
0x18000a6da  nop     dword ptr [rax+rax+00h]
0x18000a6df  mov     [rbx+18h], eax
0x18000a6e2  jmp     short loc_18000A6EB
0x18000a6e4  mov     qword ptr [rbx], 0
0x18000a6eb  mov     rcx, [rsp+98h+var_18]
0x18000a6f3  xor     rcx, rsp; StackCookie
0x18000a6f6  call    __security_check_cookie
0x18000a6fb  mov     rbx, [rsp+98h+arg_8]
0x18000a703  add     rsp, 90h
0x18000a70a  pop     rdi
0x18000a70b  retn
```
