# SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::StartActivity(void *)

- ea: `0x18000a340`
- end: `0x18000a48b`
- name: `?StartActivity@GetTroublePageShowStatus@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z`
- size: `331`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800084a0`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800049bc`
- `0x1800068cc`
- `0x18000a340`
- `0x18000d774`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a38e`
- `KERNEL32!GetCurrentThreadId` at `0x18000a452`
- `KERNEL32!GetCurrentThreadId` at `0x18000a38e`
- `KERNEL32!GetCurrentThreadId` at `0x18000a452`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::StartActivity(
        SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus *this,
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
    tlgWriteTransfer_EventWriteTransfer(v6, byte_180014071, v8 + 8);
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
0x18000a340  mov     [rsp-8+arg_8], rbx
0x18000a345  mov     [rsp-8+arg_10], rsi
0x18000a34a  push    rbp
0x18000a34b  push    rdi
0x18000a34c  push    r14
0x18000a34e  lea     rbp, [rsp-47h]
0x18000a353  sub     rsp, 0B0h
0x18000a35a  mov     rax, cs:__security_cookie
0x18000a361  xor     rax, rsp
0x18000a364  mov     [rbp+57h+var_20], rax
0x18000a368  mov     rdi, rdx
0x18000a36b  mov     rbx, rcx
0x18000a36e  call    ?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000a373  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000a378  xor     r14d, r14d
0x18000a37b  mov     rsi, [rax+8]
0x18000a37f  mov     eax, [rsi]
0x18000a381  cmp     eax, 5
0x18000a384  jbe     loc_18000A420
0x18000a38a  mov     [rbp+57h+var_88], rdi
0x18000a38e  call    cs:__imp_GetCurrentThreadId
0x18000a395  nop     dword ptr [rax+rax+00h]
0x18000a39a  mov     r8, [rbx+110h]
0x18000a3a1  mov     [rbp+57h+var_90], eax
0x18000a3a4  mov     [rbp+57h+var_80], r14
0x18000a3a8  cmp     [r8+4], r14b
0x18000a3ac  jz      short loc_18000A3C9
0x18000a3ae  lea     r9, [r8+18h]
0x18000a3b2  cmp     [r9], r14d
0x18000a3b5  jnz     short loc_18000A3CC
0x18000a3b7  cmp     [r9+4], r14d
0x18000a3bb  jnz     short loc_18000A3CC
0x18000a3bd  cmp     [r9+8], r14d
0x18000a3c1  jnz     short loc_18000A3CC
0x18000a3c3  cmp     [r9+0Ch], r14d
0x18000a3c7  jnz     short loc_18000A3CC
0x18000a3c9  mov     r9, r14
0x18000a3cc  lea     rax, [rbp+57h+var_88]
0x18000a3d0  mov     [rbp+57h+var_28], 8
0x18000a3d8  mov     [rbp+57h+var_30], rax
0x18000a3dc  lea     rdx, byte_180014071
0x18000a3e3  lea     rax, [rbp+57h+var_90]
0x18000a3e7  mov     [rbp+57h+var_38], 4
0x18000a3ef  mov     [rbp+57h+var_40], rax
0x18000a3f3  add     r8, 8
0x18000a3f7  lea     rax, [rbp+57h+var_80]
0x18000a3fb  mov     [rbp+57h+var_48], 8
0x18000a403  mov     [rbp+57h+var_50], rax
0x18000a407  mov     rcx, rsi
0x18000a40a  lea     rax, [rbp+57h+var_70]
0x18000a40e  mov     [rsp+0C0h+var_98], rax
0x18000a413  mov     [rsp+0C0h+var_A0], 5
0x18000a41b  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a420  cmp     [rbx+138h], r14d
0x18000a427  jnz     short loc_18000A466
0x18000a429  add     rbx, 120h
0x18000a430  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a437  jz      short loc_18000A463
0x18000a439  mov     dl, 1
0x18000a43b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000a440  mov     [rbx], rax
0x18000a443  test    rax, rax
0x18000a446  jz      short loc_18000A466
0x18000a448  mov     rcx, [rax]
0x18000a44b  mov     [rbx+10h], rcx
0x18000a44f  mov     [rax], rbx
0x18000a452  call    cs:__imp_GetCurrentThreadId
0x18000a459  nop     dword ptr [rax+rax+00h]
0x18000a45e  mov     [rbx+18h], eax
0x18000a461  jmp     short loc_18000A466
0x18000a463  mov     [rbx], r14
0x18000a466  mov     rcx, [rbp+57h+var_20]
0x18000a46a  xor     rcx, rsp; StackCookie
0x18000a46d  call    __security_check_cookie
0x18000a472  lea     r11, [rsp+0C0h+var_10]
0x18000a47a  mov     rbx, [r11+28h]
0x18000a47e  mov     rsi, [r11+30h]
0x18000a482  mov     rsp, r11
0x18000a485  pop     r14
0x18000a487  pop     rdi
0x18000a488  pop     rbp
0x18000a489  retn
```
