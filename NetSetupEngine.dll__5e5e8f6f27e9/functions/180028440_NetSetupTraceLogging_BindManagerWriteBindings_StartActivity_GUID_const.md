# NetSetupTraceLogging::BindManagerWriteBindings::StartActivity(_GUID const &)

- ea: `0x180028440`
- end: `0x1800284ed`
- name: `?StartActivity@BindManagerWriteBindings@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z`
- size: `173`
- prototype: `void __fastcall(NetSetupTraceLogging::BindManagerWriteBindings *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180027b90`

## callees

- `0x180001be8`
- `0x180013aa4`
- `0x180028440`
- `0x180033720`
- `0x18003e218`
- `0x180046ed0`
- `0x180069144`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002847a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002847a`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::BindManagerWriteBindings::StartActivity(
        NetSetupTraceLogging::BindManagerWriteBindings *this,
        const struct _GUID *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  int v6; // edi
  __int64 v7; // r8
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // ecx
  __int64 v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = NetSetupTraceLogging::Provider();
  v6 = (int)v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v4, 1, v7, v5) )
  {
    v12 = (__int64)a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    LODWORD(v11) = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v6,
      (int)&dword_1800B31AC,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v11,
      &v12);
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180028440  push    rbx
0x180028442  push    rsi
0x180028443  push    rdi
0x180028444  sub     rsp, 40h
0x180028448  mov     rsi, rdx
0x18002844b  mov     rbx, rcx
0x18002844e  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180028453  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x180028458  mov     rdi, rax
0x18002845b  mov     r8d, [rax]
0x18002845e  cmp     r8d, 5
0x180028462  jbe     short loc_1800284DE
0x180028464  mov     edx, 1
0x180028469  mov     rcx, rax
0x18002846c  call    _tlgKeywordOn
0x180028471  test    al, al
0x180028473  jz      short loc_1800284DE
0x180028475  mov     [rsp+58h+arg_10], rsi
0x18002847a  call    cs:__imp_GetCurrentThreadId
0x180028480  mov     r8, [rbx+110h]
0x180028487  mov     dword ptr [rsp+58h+arg_0], eax
0x18002848b  mov     [rsp+58h+arg_18], 0
0x180028494  cmp     byte ptr [r8+4], 0
0x180028499  jz      short loc_1800284A8
0x18002849b  lea     rcx, [r8+18h]; struct _GUID *
0x18002849f  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800284a4  test    al, al
0x1800284a6  jz      short loc_1800284AA
0x1800284a8  xor     ecx, ecx
0x1800284aa  lea     rax, [rsp+58h+arg_10]
0x1800284af  mov     r9, rcx
0x1800284b2  mov     [rsp+58h+var_28], rax; __int64
0x1800284b7  lea     rdx, dword_1800B31AC
0x1800284be  lea     rax, [rsp+58h+arg_0]
0x1800284c3  add     r8, 8
0x1800284c7  mov     [rsp+58h+var_30], rax; __int64
0x1800284cc  mov     rcx, rdi; int
0x1800284cf  lea     rax, [rsp+58h+arg_18]
0x1800284d4  mov     [rsp+58h+var_38], rax; __int64
0x1800284d9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800284de  mov     rcx, rbx
0x1800284e1  add     rsp, 40h
0x1800284e5  pop     rdi
0x1800284e6  pop     rsi
0x1800284e7  pop     rbx
0x1800284e8  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
