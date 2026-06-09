# ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::StartActivity(ushort const *)

- ea: `0x180016838`
- end: `0x1800169b9`
- name: `?StartActivity@AutopilotHardwareDetectionChangeTaskTelemetry@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z`
- size: `385`
- prototype: `void __fastcall(ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180017100`

## callees

- `0x180001f74`
- `0x1800045b0`
- `0x18000d600`
- `0x180015898`
- `0x180016284`
- `0x180016838`
- `0x180017488`
- `0x180018024`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800168d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001698f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800168d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001698f`

## string_xrefs

- `0x1800168a1`: `taskArgument null`

## pseudocode

```c
void __fastcall ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::StartActivity(
        ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *this,
        const unsigned __int16 *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  const struct _tlgProvider_t *v7; // rsi
  __int64 v8; // rax
  _QWORD *AutopilotCorrelationVector; // rax
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  char *v13; // rbx
  _QWORD *Local; // rax
  DWORD v15; // [rsp+50h] [rbp-19h] BYREF
  __int64 v16; // [rsp+58h] [rbp-11h] BYREF
  const unsigned __int16 *v17; // [rsp+60h] [rbp-9h] BYREF
  _QWORD *v18; // [rsp+68h] [rbp-1h] BYREF
  __int64 v19; // [rsp+70h] [rbp+7h] BYREF
  _BYTE v20[32]; // [rsp+78h] [rbp+Fh] BYREF

  wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = AutoPilotTelemProvider::Provider();
  v7 = v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    v8 = *((_QWORD *)v4 + 3);
    v5 = 0x800000000000LL;
    v6 = *((_QWORD *)v7 + 2);
    if ( (v6 & 0x800000000000LL) != 0 )
    {
      v6 = v8 & 0x800000000000LL;
      if ( (v8 & 0x800000000000LL) == v8 )
      {
        v16 = 0x2000000;
        if ( !a2 )
          a2 = L"taskArgument null";
        v17 = a2;
        AutopilotCorrelationVector = (_QWORD *)ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(v20);
        if ( AutopilotCorrelationVector[3] > 0xFu )
          AutopilotCorrelationVector = (_QWORD *)*AutopilotCorrelationVector;
        v18 = AutopilotCorrelationVector;
        CurrentThreadId = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v15 = CurrentThreadId;
        v19 = 0;
        if ( !*(_BYTE *)(v11 + 4)
          || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
          && !*(_DWORD *)(v11 + 28)
          && !*(_DWORD *)(v11 + 32)
          && !*(_DWORD *)(v11 + 36) )
        {
          v12 = 0;
        }
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          (_DWORD)v7,
          (unsigned int)byte_18003A59B,
          v11 + 8,
          v12,
          (__int64)&v19,
          (__int64)&v15,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&v16);
        std::string::_Tidy_deallocate(v20);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v13 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v5) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v6,
                          v5);
      *(_QWORD *)v13 = Local;
      if ( Local )
      {
        *((_QWORD *)v13 + 2) = *Local;
        *Local = v13;
        *((_DWORD *)v13 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v13 = 0;
    }
  }
}

```

## disassembly

```asm
0x180016838  push    rbp
0x18001683a  push    rbx
0x18001683b  push    rsi
0x18001683c  push    rdi
0x18001683d  lea     rbp, [rsp-3Fh]
0x180016842  sub     rsp, 0A8h
0x180016849  mov     rax, cs:__security_cookie
0x180016850  xor     rax, rsp
0x180016853  mov     [rbp+57h+var_28], rax
0x180016857  mov     rdi, rdx
0x18001685a  mov     rbx, rcx
0x18001685d  call    ?zInternalStart@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180016862  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x180016867  mov     rsi, rax
0x18001686a  mov     r8d, [rax]
0x18001686d  cmp     r8d, 5
0x180016871  jbe     loc_18001695C
0x180016877  mov     rax, [rax+18h]
0x18001687b  mov     rdx, 800000000000h
0x180016885  mov     rcx, [rsi+10h]
0x180016889  test    rdx, rcx
0x18001688c  jz      loc_18001695C
0x180016892  mov     rcx, rax
0x180016895  and     rcx, rdx
0x180016898  cmp     rcx, rax
0x18001689b  jnz     loc_18001695C
0x1800168a1  lea     rax, aTaskargumentNu; "taskArgument null"
0x1800168a8  mov     [rbp+57h+var_68], 2000000h
0x1800168b0  test    rdi, rdi
0x1800168b3  lea     rcx, [rbp+57h+var_48]
0x1800168b7  cmovz   rdi, rax
0x1800168bb  mov     [rbp+57h+var_60], rdi
0x1800168bf  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x1800168c4  cmp     qword ptr [rax+18h], 0Fh
0x1800168c9  jbe     short loc_1800168CE
0x1800168cb  mov     rax, [rax]
0x1800168ce  mov     [rbp+57h+var_58], rax
0x1800168d2  call    cs:__imp_GetCurrentThreadId
0x1800168d8  mov     r8, [rbx+110h]
0x1800168df  mov     [rbp+57h+var_70], eax
0x1800168e2  mov     [rbp+57h+var_50], 0
0x1800168ea  cmp     byte ptr [r8+4], 0
0x1800168ef  jz      short loc_180016910
0x1800168f1  lea     r9, [r8+18h]
0x1800168f5  cmp     dword ptr [r9], 0
0x1800168f9  jnz     short loc_180016913
0x1800168fb  cmp     dword ptr [r9+4], 0
0x180016900  jnz     short loc_180016913
0x180016902  cmp     dword ptr [r9+8], 0
0x180016907  jnz     short loc_180016913
0x180016909  cmp     dword ptr [r9+0Ch], 0
0x18001690e  jnz     short loc_180016913
0x180016910  xor     r9d, r9d
0x180016913  lea     rax, [rbp+57h+var_68]
0x180016917  add     r8, 8
0x18001691b  mov     [rsp+0C0h+var_80], rax
0x180016920  lea     rdx, byte_18003A59B
0x180016927  lea     rax, [rbp+57h+var_60]
0x18001692b  mov     rcx, rsi
0x18001692e  mov     [rsp+0C0h+var_88], rax
0x180016933  lea     rax, [rbp+57h+var_58]
0x180016937  mov     [rsp+0C0h+var_90], rax
0x18001693c  lea     rax, [rbp+57h+var_70]
0x180016940  mov     [rsp+0C0h+var_98], rax
0x180016945  lea     rax, [rbp+57h+var_50]
0x180016949  mov     [rsp+0C0h+var_A0], rax
0x18001694e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180016953  lea     rcx, [rbp+57h+var_48]
0x180016957  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001695c  cmp     dword ptr [rbx+138h], 0
0x180016963  jnz     short loc_1800169A1
0x180016965  add     rbx, 120h
0x18001696c  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180016974  jz      short loc_18001699A
0x180016976  mov     dl, 1
0x180016978  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001697d  mov     [rbx], rax
0x180016980  test    rax, rax
0x180016983  jz      short loc_1800169A1
0x180016985  mov     rcx, [rax]
0x180016988  mov     [rbx+10h], rcx
0x18001698c  mov     [rax], rbx
0x18001698f  call    cs:__imp_GetCurrentThreadId
0x180016995  mov     [rbx+18h], eax
0x180016998  jmp     short loc_1800169A1
0x18001699a  mov     qword ptr [rbx], 0
0x1800169a1  mov     rcx, [rbp+57h+var_28]
0x1800169a5  xor     rcx, rsp; StackCookie
0x1800169a8  call    __security_check_cookie
0x1800169ad  add     rsp, 0A8h
0x1800169b4  pop     rdi
0x1800169b5  pop     rsi
0x1800169b6  pop     rbx
0x1800169b7  pop     rbp
0x1800169b8  retn
```
