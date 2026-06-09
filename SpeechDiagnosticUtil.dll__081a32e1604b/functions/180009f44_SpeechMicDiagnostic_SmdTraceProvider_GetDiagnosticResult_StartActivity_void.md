# SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult::StartActivity(void *)

- ea: `0x180009f44`
- end: `0x18000a08f`
- name: `?StartActivity@GetDiagnosticResult@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z`
- size: `331`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008040`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800049bc`
- `0x1800068cc`
- `0x180009f44`
- `0x18000d774`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009f92`
- `KERNEL32!GetCurrentThreadId` at `0x18000a056`
- `KERNEL32!GetCurrentThreadId` at `0x180009f92`
- `KERNEL32!GetCurrentThreadId` at `0x18000a056`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult::StartActivity(
        SpeechMicDiagnostic::SmdTraceProvider::GetDiagnosticResult *this,
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
    tlgWriteTransfer_EventWriteTransfer(v6, &byte_180013F6F, v8 + 8);
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
0x180009f44  mov     [rsp-8+arg_8], rbx
0x180009f49  mov     [rsp-8+arg_10], rsi
0x180009f4e  push    rbp
0x180009f4f  push    rdi
0x180009f50  push    r14
0x180009f52  lea     rbp, [rsp-47h]
0x180009f57  sub     rsp, 0B0h
0x180009f5e  mov     rax, cs:__security_cookie
0x180009f65  xor     rax, rsp
0x180009f68  mov     [rbp+57h+var_20], rax
0x180009f6c  mov     rdi, rdx
0x180009f6f  mov     rbx, rcx
0x180009f72  call    ?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180009f77  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x180009f7c  xor     r14d, r14d
0x180009f7f  mov     rsi, [rax+8]
0x180009f83  mov     eax, [rsi]
0x180009f85  cmp     eax, 5
0x180009f88  jbe     loc_18000A024
0x180009f8e  mov     [rbp+57h+var_88], rdi
0x180009f92  call    cs:__imp_GetCurrentThreadId
0x180009f99  nop     dword ptr [rax+rax+00h]
0x180009f9e  mov     r8, [rbx+110h]
0x180009fa5  mov     [rbp+57h+var_90], eax
0x180009fa8  mov     [rbp+57h+var_80], r14
0x180009fac  cmp     [r8+4], r14b
0x180009fb0  jz      short loc_180009FCD
0x180009fb2  lea     r9, [r8+18h]
0x180009fb6  cmp     [r9], r14d
0x180009fb9  jnz     short loc_180009FD0
0x180009fbb  cmp     [r9+4], r14d
0x180009fbf  jnz     short loc_180009FD0
0x180009fc1  cmp     [r9+8], r14d
0x180009fc5  jnz     short loc_180009FD0
0x180009fc7  cmp     [r9+0Ch], r14d
0x180009fcb  jnz     short loc_180009FD0
0x180009fcd  mov     r9, r14
0x180009fd0  lea     rax, [rbp+57h+var_88]
0x180009fd4  mov     [rbp+57h+var_28], 8
0x180009fdc  mov     [rbp+57h+var_30], rax
0x180009fe0  lea     rdx, byte_180013F6F
0x180009fe7  lea     rax, [rbp+57h+var_90]
0x180009feb  mov     [rbp+57h+var_38], 4
0x180009ff3  mov     [rbp+57h+var_40], rax
0x180009ff7  add     r8, 8
0x180009ffb  lea     rax, [rbp+57h+var_80]
0x180009fff  mov     [rbp+57h+var_48], 8
0x18000a007  mov     [rbp+57h+var_50], rax
0x18000a00b  mov     rcx, rsi
0x18000a00e  lea     rax, [rbp+57h+var_70]
0x18000a012  mov     [rsp+0C0h+var_98], rax
0x18000a017  mov     [rsp+0C0h+var_A0], 5
0x18000a01f  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a024  cmp     [rbx+138h], r14d
0x18000a02b  jnz     short loc_18000A06A
0x18000a02d  add     rbx, 120h
0x18000a034  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a03b  jz      short loc_18000A067
0x18000a03d  mov     dl, 1
0x18000a03f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000a044  mov     [rbx], rax
0x18000a047  test    rax, rax
0x18000a04a  jz      short loc_18000A06A
0x18000a04c  mov     rcx, [rax]
0x18000a04f  mov     [rbx+10h], rcx
0x18000a053  mov     [rax], rbx
0x18000a056  call    cs:__imp_GetCurrentThreadId
0x18000a05d  nop     dword ptr [rax+rax+00h]
0x18000a062  mov     [rbx+18h], eax
0x18000a065  jmp     short loc_18000A06A
0x18000a067  mov     [rbx], r14
0x18000a06a  mov     rcx, [rbp+57h+var_20]
0x18000a06e  xor     rcx, rsp; StackCookie
0x18000a071  call    __security_check_cookie
0x18000a076  lea     r11, [rsp+0C0h+var_10]
0x18000a07e  mov     rbx, [r11+28h]
0x18000a082  mov     rsi, [r11+30h]
0x18000a086  mov     rsp, r11
0x18000a089  pop     r14
0x18000a08b  pop     rdi
0x18000a08c  pop     rbp
0x18000a08d  retn
```
