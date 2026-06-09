# SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues::StartActivity(bool)

- ea: `0x18000a868`
- end: `0x18000a95d`
- name: `?StartActivity@UpdateRegistryValues@SmdTraceProvider@SpeechMicDiagnostic@@QEAAX_N@Z`
- size: `245`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000d2a0`

## callees

- `0x1800023a4`
- `0x1800049bc`
- `0x1800068cc`
- `0x18000a868`
- `0x18000d774`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a88f`
- `KERNEL32!GetCurrentThreadId` at `0x18000a93c`
- `KERNEL32!GetCurrentThreadId` at `0x18000a88f`
- `KERNEL32!GetCurrentThreadId` at `0x18000a93c`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues::StartActivity(
        SpeechMicDiagnostic::SmdTraceProvider::UpdateRegistryValues *this,
        unsigned __int8 a2)
{
  int v2; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx
  _DWORD *v6; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  int v9; // r9d
  char *v10; // rbx
  _QWORD *Local; // rax
  int v12; // [rsp+60h] [rbp+8h] BYREF
  DWORD v13; // [rsp+70h] [rbp+18h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  v2 = a2;
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
  if ( *v6 > 5u )
  {
    v12 = v2;
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)this + 34);
    v13 = CurrentThreadId;
    v14 = 0;
    if ( !*(_BYTE *)(v8 + 4)
      || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
      && !*(_DWORD *)(v8 + 28)
      && !*(_DWORD *)(v8 + 32)
      && !*(_DWORD *)(v8 + 36) )
    {
      v9 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v6,
      (unsigned int)word_180013E22,
      v8 + 8,
      v9,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v10 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v4) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v5,
                          v4);
      *(_QWORD *)v10 = Local;
      if ( Local )
      {
        *((_QWORD *)v10 + 2) = *Local;
        *Local = v10;
        *((_DWORD *)v10 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v10 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000a868  push    rbx
0x18000a86a  push    rsi
0x18000a86b  push    rdi
0x18000a86c  sub     rsp, 40h
0x18000a870  movzx   edi, dl
0x18000a873  mov     rbx, rcx
0x18000a876  call    ?zInternalStart@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000a87b  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000a880  mov     rsi, [rax+8]
0x18000a884  mov     eax, [rsi]
0x18000a886  cmp     eax, 5
0x18000a889  jbe     short loc_18000A909
0x18000a88b  mov     [rsp+58h+arg_0], edi
0x18000a88f  call    cs:__imp_GetCurrentThreadId
0x18000a896  nop     dword ptr [rax+rax+00h]
0x18000a89b  mov     r8, [rbx+110h]
0x18000a8a2  mov     [rsp+58h+arg_10], eax
0x18000a8a6  mov     [rsp+58h+arg_18], 0
0x18000a8af  cmp     byte ptr [r8+4], 0
0x18000a8b4  jz      short loc_18000A8D5
0x18000a8b6  lea     r9, [r8+18h]
0x18000a8ba  cmp     dword ptr [r9], 0
0x18000a8be  jnz     short loc_18000A8D8
0x18000a8c0  cmp     dword ptr [r9+4], 0
0x18000a8c5  jnz     short loc_18000A8D8
0x18000a8c7  cmp     dword ptr [r9+8], 0
0x18000a8cc  jnz     short loc_18000A8D8
0x18000a8ce  cmp     dword ptr [r9+0Ch], 0
0x18000a8d3  jnz     short loc_18000A8D8
0x18000a8d5  xor     r9d, r9d
0x18000a8d8  lea     rax, [rsp+58h+arg_0]
0x18000a8dd  add     r8, 8
0x18000a8e1  mov     [rsp+58h+var_28], rax
0x18000a8e6  lea     rdx, word_180013E22
0x18000a8ed  lea     rax, [rsp+58h+arg_10]
0x18000a8f2  mov     rcx, rsi
0x18000a8f5  mov     [rsp+58h+var_30], rax
0x18000a8fa  lea     rax, [rsp+58h+arg_18]
0x18000a8ff  mov     [rsp+58h+var_38], rax
0x18000a904  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000a909  cmp     dword ptr [rbx+138h], 0
0x18000a910  jnz     short loc_18000A954
0x18000a912  add     rbx, 120h
0x18000a919  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a921  jz      short loc_18000A94D
0x18000a923  mov     dl, 1
0x18000a925  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000a92a  mov     [rbx], rax
0x18000a92d  test    rax, rax
0x18000a930  jz      short loc_18000A954
0x18000a932  mov     rcx, [rax]
0x18000a935  mov     [rbx+10h], rcx
0x18000a939  mov     [rax], rbx
0x18000a93c  call    cs:__imp_GetCurrentThreadId
0x18000a943  nop     dword ptr [rax+rax+00h]
0x18000a948  mov     [rbx+18h], eax
0x18000a94b  jmp     short loc_18000A954
0x18000a94d  mov     qword ptr [rbx], 0
0x18000a954  add     rsp, 40h
0x18000a958  pop     rdi
0x18000a959  pop     rsi
0x18000a95a  pop     rbx
0x18000a95b  retn
```
