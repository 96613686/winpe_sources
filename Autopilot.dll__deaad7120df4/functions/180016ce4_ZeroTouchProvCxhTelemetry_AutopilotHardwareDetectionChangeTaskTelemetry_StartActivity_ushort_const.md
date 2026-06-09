# ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::StartActivity(ushort const *)

- ea: `0x180016ce4`
- end: `0x180016e39`
- name: `?StartActivity@AutopilotHardwareDetectionChangeTaskTelemetry@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z`
- size: `341`
- prototype: `void __fastcall(ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180017620`

## callees

- `0x180001f80`
- `0x1800045d0`
- `0x180015cd4`
- `0x18001670c`
- `0x180016ce4`
- `0x180016e40`
- `0x1800179b8`
- `0x180018568`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016d7e`

## string_xrefs

- `0x180016d4d`: `taskArgument null`

## pseudocode

```c
void __fastcall ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::StartActivity(
        ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *this,
        const unsigned __int16 *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 AutopilotCorrelationVector; // rax
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD v11; // [rsp+50h] [rbp-19h] BYREF
  __int64 v12; // [rsp+58h] [rbp-11h] BYREF
  int *v13; // [rsp+60h] [rbp-9h] BYREF
  const unsigned __int16 *v14; // [rsp+68h] [rbp-1h] BYREF
  __int64 v15; // [rsp+70h] [rbp+7h] BYREF
  char *v16[4]; // [rsp+78h] [rbp+Fh] BYREF

  wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = AutoPilotTelemProvider::Provider();
  v5 = (__int64)v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    v6 = *((_QWORD *)v4 + 3);
    if ( (*(_QWORD *)(v5 + 16) & 0x800000000000LL) != 0 && (v6 & 0x800000000000LL) == v6 )
    {
      v12 = 0x2000000;
      if ( !a2 )
        a2 = L"taskArgument null";
      v13 = (int *)a2;
      AutopilotCorrelationVector = ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector((__int64)v16);
      if ( *(_QWORD *)(AutopilotCorrelationVector + 24) > 0xFu )
        AutopilotCorrelationVector = *(_QWORD *)AutopilotCorrelationVector;
      v14 = (const unsigned __int16 *)AutopilotCorrelationVector;
      CurrentThreadId = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 34);
      v11 = CurrentThreadId;
      v15 = 0;
      if ( !*(_BYTE *)(v9 + 4)
        || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
        && !*(_DWORD *)(v9 + 28)
        && !*(_DWORD *)(v9 + 32)
        && !*(_DWORD *)(v9 + 36) )
      {
        v10 = 0;
      }
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v5,
        (__int64)byte_18003B59B,
        v9 + 8,
        v10,
        (__int64)&v15,
        (__int64)&v11,
        &v14,
        &v13,
        (__int64)&v12);
      std::string::_Tidy_deallocate(v16);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *)((char *)this + 288));
}

```

## disassembly

```asm
0x180016ce4  push    rbp
0x180016ce6  push    rbx
0x180016ce7  push    rsi
0x180016ce8  push    rdi
0x180016ce9  lea     rbp, [rsp-3Fh]
0x180016cee  sub     rsp, 0A8h
0x180016cf5  mov     rax, cs:__security_cookie
0x180016cfc  xor     rax, rsp
0x180016cff  mov     [rbp+57h+var_28], rax
0x180016d03  mov     rbx, rdx
0x180016d06  mov     rdi, rcx
0x180016d09  call    ?zInternalStart@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180016d0e  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x180016d13  mov     rsi, rax
0x180016d16  mov     r8d, [rax]
0x180016d19  cmp     r8d, 5
0x180016d1d  jbe     loc_180016E0E
0x180016d23  mov     rax, [rax+18h]
0x180016d27  mov     rdx, 800000000000h
0x180016d31  mov     rcx, [rsi+10h]
0x180016d35  test    rdx, rcx
0x180016d38  jz      loc_180016E0E
0x180016d3e  mov     rcx, rax
0x180016d41  and     rcx, rdx
0x180016d44  cmp     rcx, rax
0x180016d47  jnz     loc_180016E0E
0x180016d4d  lea     rax, aTaskargumentNu; "taskArgument null"
0x180016d54  mov     [rbp+57h+var_68], 2000000h
0x180016d5c  test    rbx, rbx
0x180016d5f  lea     rcx, [rbp+57h+var_48]
0x180016d63  cmovz   rbx, rax
0x180016d67  mov     [rbp+57h+var_60], rbx
0x180016d6b  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180016d70  cmp     qword ptr [rax+18h], 0Fh
0x180016d75  jbe     short loc_180016D7A
0x180016d77  mov     rax, [rax]
0x180016d7a  mov     [rbp+57h+var_58], rax
0x180016d7e  call    cs:__imp_GetCurrentThreadId
0x180016d85  nop     dword ptr [rax+rax+00h]
0x180016d8a  mov     r8, [rdi+110h]
0x180016d91  mov     [rbp+57h+var_70], eax
0x180016d94  mov     [rbp+57h+var_50], 0
0x180016d9c  cmp     byte ptr [r8+4], 0
0x180016da1  jz      short loc_180016DC2
0x180016da3  lea     r9, [r8+18h]
0x180016da7  cmp     dword ptr [r9], 0
0x180016dab  jnz     short loc_180016DC5
0x180016dad  cmp     dword ptr [r9+4], 0
0x180016db2  jnz     short loc_180016DC5
0x180016db4  cmp     dword ptr [r9+8], 0
0x180016db9  jnz     short loc_180016DC5
0x180016dbb  cmp     dword ptr [r9+0Ch], 0
0x180016dc0  jnz     short loc_180016DC5
0x180016dc2  xor     r9d, r9d
0x180016dc5  lea     rax, [rbp+57h+var_68]
0x180016dc9  add     r8, 8
0x180016dcd  mov     [rsp+0C0h+var_80], rax
0x180016dd2  lea     rdx, byte_18003B59B
0x180016dd9  lea     rax, [rbp+57h+var_60]
0x180016ddd  mov     rcx, rsi
0x180016de0  mov     [rsp+0C0h+var_88], rax
0x180016de5  lea     rax, [rbp+57h+var_58]
0x180016de9  mov     [rsp+0C0h+var_90], rax
0x180016dee  lea     rax, [rbp+57h+var_70]
0x180016df2  mov     [rsp+0C0h+var_98], rax
0x180016df7  lea     rax, [rbp+57h+var_50]
0x180016dfb  mov     [rsp+0C0h+var_A0], rax
0x180016e00  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180016e05  lea     rcx, [rbp+57h+var_48]
0x180016e09  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016e0e  lea     rcx, [rdi+120h]; this
0x180016e15  cmp     dword ptr [rcx+18h], 0
0x180016e19  jnz     short loc_180016E20
0x180016e1b  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180016e20  mov     rcx, [rbp+57h+var_28]
0x180016e24  xor     rcx, rsp; StackCookie
0x180016e27  call    __security_check_cookie
0x180016e2c  add     rsp, 0A8h
0x180016e33  pop     rdi
0x180016e34  pop     rsi
0x180016e35  pop     rbx
0x180016e36  pop     rbp
0x180016e37  retn
```
