# PrintWorkFlowTelemetry::SourceSessionFinalize::StartActivity(ulong,Microsoft::WRL::ComPtr<Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession> const &,Windows::Graphics::Internal::Printing::Workflow::_PWF_SESSION_STATE,long)

- ea: `0x18001c22c`
- end: `0x18001c36c`
- name: `?StartActivity@SourceSessionFinalize@PrintWorkFlowTelemetry@@QEAAXKAEBV?$ComPtr@UIWorkflowSession@Workflow@Printing@Internal@Graphics@Windows@@@WRL@Microsoft@@W4_PWF_SESSION_STATE@Workflow@Printing@Internal@Graphics@Windows@@J@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001ae40`

## callees

- `0x1800014bc`
- `0x180001efc`
- `0x18001ae18`
- `0x18001b9fc`
- `0x18001c22c`
- `0x18001cc40`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c2ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c2ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c2c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c2c2`

## pseudocode

```c
__int64 __fastcall PrintWorkFlowTelemetry::SourceSessionFinalize::StartActivity(
        __int64 a1,
        int a2,
        __int64 *a3,
        int a4,
        int a5)
{
  __int64 v6; // rcx
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v15; // [rsp+50h] [rbp-30h] BYREF
  DWORD v16; // [rsp+54h] [rbp-2Ch] BYREF
  PCWSTR StringRawBuffer; // [rsp+58h] [rbp-28h] BYREF
  __int64 v18; // [rsp+60h] [rbp-20h] BYREF
  HSTRING string[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v20; // [rsp+78h] [rbp-8h]
  int v21; // [rsp+A0h] [rbp+20h] BYREF
  int v22; // [rsp+B0h] [rbp+30h] BYREF

  v6 = *a3;
  v20 = 0;
  *(_OWORD *)string = 0;
  (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 152LL))(v6, string);
  wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
  v9 = PrintWorkFlowLogging::Provider();
  v10 = (__int64)v9;
  if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    v21 = a5;
    v22 = a4;
    v15 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v12 = *(_QWORD *)(a1 + 272);
    v16 = CurrentThreadId;
    v18 = 0;
    if ( !*(_BYTE *)(v12 + 4)
      || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
      && !*(_DWORD *)(v12 + 28)
      && !*(_DWORD *)(v12 + 32)
      && !*(_DWORD *)(v12 + 36) )
    {
      v13 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v10,
      (__int64)byte_180070E85,
      v12 + 8,
      v13,
      (__int64)&v18,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v22,
      (__int64)&v21,
      &StringRawBuffer);
  }
  return wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(a1);
}

```

## disassembly

```asm
0x18001c22c  mov     [rsp-18h+arg_8], rbx
0x18001c231  mov     [rsp-18h+arg_18], rsi
0x18001c236  push    rbp
0x18001c237  push    rdi
0x18001c238  push    r14
0x18001c23a  mov     rbp, rsp
0x18001c23d  sub     rsp, 80h
0x18001c244  xor     eax, eax
0x18001c246  mov     rbx, rcx
0x18001c249  mov     rcx, [r8]
0x18001c24c  xorps   xmm0, xmm0
0x18001c24f  mov     [rbp+var_8], rax
0x18001c253  mov     r14d, edx
0x18001c256  movups  xmmword ptr [rbp+string], xmm0
0x18001c25a  lea     rdx, [rbp+string]
0x18001c25e  mov     esi, r9d
0x18001c261  mov     rax, [rcx]
0x18001c264  mov     rax, [rax+98h]
0x18001c26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c270  mov     rcx, rbx
0x18001c273  call    ?zInternalStart@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c278  call    ?Provider@PrintWorkFlowLogging@@SAPEBU_tlgProvider_t@@XZ; PrintWorkFlowLogging::Provider(void)
0x18001c27d  mov     rdi, rax
0x18001c280  mov     ecx, [rax]
0x18001c282  cmp     ecx, 5
0x18001c285  jbe     loc_18001C34C
0x18001c28b  mov     rdx, 400000000000h
0x18001c295  mov     rcx, rax
0x18001c298  call    _tlgKeywordOn
0x18001c29d  test    al, al
0x18001c29f  jz      loc_18001C34C
0x18001c2a5  mov     rcx, [rbp+string]; string
0x18001c2a9  xor     edx, edx; length
0x18001c2ab  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c2b1  mov     [rbp+var_28], rax
0x18001c2b5  mov     eax, [rbp+arg_20]
0x18001c2b8  mov     [rbp+arg_0], eax
0x18001c2bb  mov     [rbp+arg_10], esi
0x18001c2be  mov     [rbp+var_30], r14d
0x18001c2c2  call    cs:__imp_GetCurrentThreadId
0x18001c2c8  mov     r8, [rbx+110h]
0x18001c2cf  mov     [rbp+var_2C], eax
0x18001c2d2  mov     [rbp+var_20], 0
0x18001c2da  cmp     byte ptr [r8+4], 0
0x18001c2df  jz      short loc_18001C300
0x18001c2e1  lea     r9, [r8+18h]
0x18001c2e5  cmp     dword ptr [r9], 0
0x18001c2e9  jnz     short loc_18001C303
0x18001c2eb  cmp     dword ptr [r9+4], 0
0x18001c2f0  jnz     short loc_18001C303
0x18001c2f2  cmp     dword ptr [r9+8], 0
0x18001c2f7  jnz     short loc_18001C303
0x18001c2f9  cmp     dword ptr [r9+0Ch], 0
0x18001c2fe  jnz     short loc_18001C303
0x18001c300  xor     r9d, r9d
0x18001c303  lea     rax, [rbp+var_28]
0x18001c307  add     r8, 8
0x18001c30b  mov     [rsp+80h+var_38], rax
0x18001c310  lea     rdx, byte_180070E85
0x18001c317  lea     rax, [rbp+arg_0]
0x18001c31b  mov     rcx, rdi
0x18001c31e  mov     [rsp+80h+var_40], rax
0x18001c323  lea     rax, [rbp+arg_10]
0x18001c327  mov     [rsp+80h+var_48], rax
0x18001c32c  lea     rax, [rbp+var_30]
0x18001c330  mov     [rsp+80h+var_50], rax
0x18001c335  lea     rax, [rbp+var_2C]
0x18001c339  mov     [rsp+80h+var_58], rax
0x18001c33e  lea     rax, [rbp+var_20]
0x18001c342  mov     [rsp+80h+var_60], rax
0x18001c347  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001c34c  mov     rcx, rbx
0x18001c34f  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001c354  lea     r11, [rsp+80h+var_s0]
0x18001c35c  mov     rbx, [r11+28h]
0x18001c360  mov     rsi, [r11+38h]
0x18001c364  mov     rsp, r11
0x18001c367  pop     r14
0x18001c369  pop     rdi
0x18001c36a  pop     rbp
0x18001c36b  retn
```
