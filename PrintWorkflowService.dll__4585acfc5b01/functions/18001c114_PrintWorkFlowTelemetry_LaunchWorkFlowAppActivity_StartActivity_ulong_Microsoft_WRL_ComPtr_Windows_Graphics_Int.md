# PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::StartActivity(ulong,Microsoft::WRL::ComPtr<Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession> const &)

- ea: `0x18001c114`
- end: `0x18001c223`
- name: `?StartActivity@LaunchWorkFlowAppActivity@PrintWorkFlowTelemetry@@QEAAXKAEBV?$ComPtr@UIWorkflowSession@Workflow@Printing@Internal@Graphics@Windows@@@WRL@Microsoft@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001b100`

## callees

- `0x1800014bc`
- `0x180001fdc`
- `0x18001ae18`
- `0x18001b9fc`
- `0x18001c114`
- `0x18001cc40`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c180`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c180`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c18f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c18f`

## pseudocode

```c
__int64 __fastcall PrintWorkFlowTelemetry::LaunchWorkFlowAppActivity::StartActivity(__int64 a1, int a2, _QWORD *a3)
{
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  PCWSTR StringRawBuffer; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v12[4]; // [rsp+48h] [rbp-20h] BYREF
  int v13; // [rsp+70h] [rbp+8h] BYREF
  DWORD v14; // [rsp+80h] [rbp+18h] BYREF
  HSTRING string; // [rsp+88h] [rbp+20h] BYREF

  string = 0;
  (*(void (__fastcall **)(_QWORD, HSTRING *))(*(_QWORD *)*a3 + 192LL))(*a3, &string);
  wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(a1);
  v5 = PrintWorkFlowLogging::Provider();
  v6 = (__int64)v5;
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v8 = *(_QWORD *)(a1 + 272);
    v14 = CurrentThreadId;
    v12[0] = 0;
    if ( !*(_BYTE *)(v8 + 4)
      || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
      && !*(_DWORD *)(v8 + 28)
      && !*(_DWORD *)(v8 + 32)
      && !*(_DWORD *)(v8 + 36) )
    {
      v9 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v6,
      (__int64)byte_18007107D,
      v8 + 8,
      v9,
      (__int64)v12,
      (__int64)&v14,
      (__int64)&v13,
      &StringRawBuffer);
  }
  return wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(a1);
}

```

## disassembly

```asm
0x18001c114  mov     r11, rsp
0x18001c117  push    rbx
0x18001c118  push    rsi
0x18001c119  push    rdi
0x18001c11a  sub     rsp, 50h
0x18001c11e  mov     rbx, rcx
0x18001c121  mov     qword ptr [r11+20h], 0
0x18001c129  mov     rcx, [r8]
0x18001c12c  mov     esi, edx
0x18001c12e  lea     rdx, [r11+20h]
0x18001c132  mov     rax, [rcx]
0x18001c135  mov     rax, [rax+0C0h]
0x18001c13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c141  mov     rcx, rbx
0x18001c144  call    ?zInternalStart@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c149  call    ?Provider@PrintWorkFlowLogging@@SAPEBU_tlgProvider_t@@XZ; PrintWorkFlowLogging::Provider(void)
0x18001c14e  mov     rdi, rax
0x18001c151  mov     ecx, [rax]
0x18001c153  cmp     ecx, 5
0x18001c156  jbe     loc_18001C213
0x18001c15c  mov     rdx, 400000000000h
0x18001c166  mov     rcx, rax
0x18001c169  call    _tlgKeywordOn
0x18001c16e  test    al, al
0x18001c170  jz      loc_18001C213
0x18001c176  mov     rcx, [rsp+68h+string]; string
0x18001c17e  xor     edx, edx; length
0x18001c180  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c186  mov     [rsp+68h+var_28], rax
0x18001c18b  mov     [rsp+68h+arg_0], esi
0x18001c18f  call    cs:__imp_GetCurrentThreadId
0x18001c195  mov     r8, [rbx+110h]
0x18001c19c  mov     [rsp+68h+arg_10], eax
0x18001c1a3  mov     [rsp+68h+var_20], 0
0x18001c1ac  cmp     byte ptr [r8+4], 0
0x18001c1b1  jz      short loc_18001C1D2
0x18001c1b3  lea     r9, [r8+18h]
0x18001c1b7  cmp     dword ptr [r9], 0
0x18001c1bb  jnz     short loc_18001C1D5
0x18001c1bd  cmp     dword ptr [r9+4], 0
0x18001c1c2  jnz     short loc_18001C1D5
0x18001c1c4  cmp     dword ptr [r9+8], 0
0x18001c1c9  jnz     short loc_18001C1D5
0x18001c1cb  cmp     dword ptr [r9+0Ch], 0
0x18001c1d0  jnz     short loc_18001C1D5
0x18001c1d2  xor     r9d, r9d
0x18001c1d5  lea     rax, [rsp+68h+var_28]
0x18001c1da  add     r8, 8
0x18001c1de  mov     [rsp+68h+var_30], rax
0x18001c1e3  lea     rdx, byte_18007107D
0x18001c1ea  lea     rax, [rsp+68h+arg_0]
0x18001c1ef  mov     rcx, rdi
0x18001c1f2  mov     [rsp+68h+var_38], rax
0x18001c1f7  lea     rax, [rsp+68h+arg_10]
0x18001c1ff  mov     [rsp+68h+var_40], rax
0x18001c204  lea     rax, [rsp+68h+var_20]
0x18001c209  mov     [rsp+68h+var_48], rax
0x18001c20e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001c213  mov     rcx, rbx
0x18001c216  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001c21b  add     rsp, 50h
0x18001c21f  pop     rdi
0x18001c220  pop     rsi
0x18001c221  pop     rbx
0x18001c222  retn
```
