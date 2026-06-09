# SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::StartActivity(void)

- ea: `0x18000a494`
- end: `0x18000a5cd`
- name: `?StartActivity@MarkTroublePageDisplayed@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXXZ`
- size: `313`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008d10`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800049bc`
- `0x1800068cc`
- `0x18000a494`
- `0x18000d774`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a4cf`
- `KERNEL32!GetCurrentThreadId` at `0x18000a593`
- `KERNEL32!GetCurrentThreadId` at `0x18000a4cf`
- `KERNEL32!GetCurrentThreadId` at `0x18000a593`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed::StartActivity(
        SpeechMicDiagnostic::SmdTraceProvider::MarkTroublePageDisplayed *this)
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
    tlgWriteTransfer_EventWriteTransfer(v4, byte_180013FC3, v5 + 8);
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
0x18000a494  mov     [rsp+arg_8], rbx
0x18000a499  push    rdi
0x18000a49a  sub     rsp, 90h
0x18000a4a1  mov     rax, cs:__security_cookie
0x18000a4a8  xor     rax, rsp
0x18000a4ab  mov     [rsp+98h+var_18], rax
0x18000a4b3  mov     rbx, rcx
0x18000a4b6  call    ?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000a4bb  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000a4c0  mov     rdi, [rax+8]
0x18000a4c4  mov     eax, [rdi]
0x18000a4c6  cmp     eax, 5
0x18000a4c9  jbe     loc_18000A560
0x18000a4cf  call    cs:__imp_GetCurrentThreadId
0x18000a4d6  nop     dword ptr [rax+rax+00h]
0x18000a4db  mov     [rsp+98h+var_68], eax
0x18000a4df  mov     [rsp+98h+var_60], 0
0x18000a4e8  mov     r8, [rbx+110h]
0x18000a4ef  cmp     byte ptr [r8+4], 0
0x18000a4f4  jz      short loc_18000A515
0x18000a4f6  lea     r9, [r8+18h]
0x18000a4fa  cmp     dword ptr [r9], 0
0x18000a4fe  jnz     short loc_18000A518
0x18000a500  cmp     dword ptr [r9+4], 0
0x18000a505  jnz     short loc_18000A518
0x18000a507  cmp     dword ptr [r9+8], 0
0x18000a50c  jnz     short loc_18000A518
0x18000a50e  cmp     dword ptr [r9+0Ch], 0
0x18000a513  jnz     short loc_18000A518
0x18000a515  xor     r9d, r9d
0x18000a518  lea     rax, [rsp+98h+var_68]
0x18000a51d  mov     [rsp+98h+var_28], rax
0x18000a522  mov     ecx, 4
0x18000a527  mov     [rsp+98h+var_20], rcx
0x18000a52c  lea     rax, [rsp+98h+var_60]
0x18000a531  mov     [rsp+98h+var_38], rax
0x18000a536  mov     [rsp+98h+var_30], 8
0x18000a53f  add     r8, 8
0x18000a543  lea     rax, [rsp+98h+var_58]
0x18000a548  mov     [rsp+98h+var_70], rax
0x18000a54d  mov     [rsp+98h+var_78], ecx
0x18000a551  lea     rdx, byte_180013FC3
0x18000a558  mov     rcx, rdi
0x18000a55b  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a560  cmp     dword ptr [rbx+138h], 0
0x18000a567  jnz     short loc_18000A5AB
0x18000a569  add     rbx, 120h
0x18000a570  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a578  jz      short loc_18000A5A4
0x18000a57a  mov     dl, 1
0x18000a57c  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000a581  mov     [rbx], rax
0x18000a584  test    rax, rax
0x18000a587  jz      short loc_18000A5AB
0x18000a589  mov     rcx, [rax]
0x18000a58c  mov     [rbx+10h], rcx
0x18000a590  mov     [rax], rbx
0x18000a593  call    cs:__imp_GetCurrentThreadId
0x18000a59a  nop     dword ptr [rax+rax+00h]
0x18000a59f  mov     [rbx+18h], eax
0x18000a5a2  jmp     short loc_18000A5AB
0x18000a5a4  mov     qword ptr [rbx], 0
0x18000a5ab  mov     rcx, [rsp+98h+var_18]
0x18000a5b3  xor     rcx, rsp; StackCookie
0x18000a5b6  call    __security_check_cookie
0x18000a5bb  mov     rbx, [rsp+98h+arg_8]
0x18000a5c3  add     rsp, 90h
0x18000a5ca  pop     rdi
0x18000a5cb  retn
```
