# NetSetupTraceLogging::InvokePlugin::StartActivity(_GUID const &,wchar_t const *,ulong)

- ea: `0x1800199b4`
- end: `0x180019aa9`
- name: `?StartActivity@InvokePlugin@NetSetupTraceLogging@@QEAAXAEBU_GUID@@PEB_WK@Z`
- size: `245`
- prototype: `void __fastcall(NetSetupTraceLogging::InvokePlugin *__hidden this, const struct _GUID *, const wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x1800194bc`
- `0x180019708`
- `0x18001aff4`

## callees

- `0x1800010c0`
- `0x180013aa4`
- `0x1800199b4`
- `0x180033720`
- `0x18003f3f4`
- `0x180046ed0`
- `0x180069144`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a12`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::InvokePlugin::StartActivity(
        NetSetupTraceLogging::InvokePlugin *this,
        const struct _GUID *a2,
        const wchar_t *a3,
        int a4)
{
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // ecx
  __int64 v15; // [rsp+50h] [rbp-38h] BYREF
  __int64 v16; // [rsp+58h] [rbp-30h] BYREF
  __int64 v17; // [rsp+60h] [rbp-28h] BYREF
  __int64 v18; // [rsp+68h] [rbp-20h] BYREF
  __int64 v19; // [rsp+90h] [rbp+8h] BYREF

  wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v8 = NetSetupTraceLogging::Provider();
  v11 = (int)v8;
  if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 4, v9, v10) )
  {
    LODWORD(v19) = a4;
    v16 = (__int64)a3;
    v17 = (__int64)a2;
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    LODWORD(v15) = CurrentThreadId;
    v18 = 0;
    if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v11,
      (int)byte_1800B1B93,
      v13 + 8,
      v14,
      (__int64)&v18,
      (__int64)&v15,
      &v17,
      (const WCHAR **)&v16,
      (__int64)&v19);
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x1800199b4  mov     [rsp+arg_8], rbx
0x1800199b9  mov     [rsp+arg_10], rbp
0x1800199be  push    rsi
0x1800199bf  push    rdi
0x1800199c0  push    r14
0x1800199c2  sub     rsp, 70h
0x1800199c6  mov     esi, r9d
0x1800199c9  mov     rbp, r8
0x1800199cc  mov     r14, rdx
0x1800199cf  mov     rbx, rcx
0x1800199d2  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800199d7  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800199dc  mov     rdi, rax
0x1800199df  mov     r10d, [rax]
0x1800199e2  cmp     r10d, 5
0x1800199e6  jbe     loc_180019A8D
0x1800199ec  mov     edx, 4
0x1800199f1  mov     rcx, rax
0x1800199f4  call    _tlgKeywordOn
0x1800199f9  test    al, al
0x1800199fb  jz      loc_180019A8D
0x180019a01  mov     dword ptr [rsp+88h+arg_0], esi
0x180019a08  mov     [rsp+88h+var_30], rbp
0x180019a0d  mov     [rsp+88h+var_28], r14
0x180019a12  call    cs:__imp_GetCurrentThreadId
0x180019a18  mov     r8, [rbx+110h]
0x180019a1f  mov     dword ptr [rsp+88h+var_38], eax
0x180019a23  mov     [rsp+88h+var_20], 0
0x180019a2c  cmp     byte ptr [r8+4], 0
0x180019a31  jz      short loc_180019A40
0x180019a33  lea     rcx, [r8+18h]; struct _GUID *
0x180019a37  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180019a3c  test    al, al
0x180019a3e  jz      short loc_180019A42
0x180019a40  xor     ecx, ecx
0x180019a42  lea     rax, [rsp+88h+arg_0]
0x180019a4a  mov     r9, rcx
0x180019a4d  mov     [rsp+88h+var_48], rax; __int64
0x180019a52  lea     rdx, byte_1800B1B93
0x180019a59  lea     rax, [rsp+88h+var_30]
0x180019a5e  add     r8, 8
0x180019a62  mov     [rsp+88h+var_50], rax; __int64
0x180019a67  mov     rcx, rdi; int
0x180019a6a  lea     rax, [rsp+88h+var_28]
0x180019a6f  mov     [rsp+88h+var_58], rax; __int64
0x180019a74  lea     rax, [rsp+88h+var_38]
0x180019a79  mov     [rsp+88h+var_60], rax; __int64
0x180019a7e  lea     rax, [rsp+88h+var_20]
0x180019a83  mov     [rsp+88h+var_68], rax; __int64
0x180019a88  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180019a8d  mov     rcx, rbx
0x180019a90  lea     r11, [rsp+88h+var_18]
0x180019a95  mov     rbx, [r11+28h]
0x180019a99  mov     rbp, [r11+30h]
0x180019a9d  mov     rsp, r11
0x180019aa0  pop     r14
0x180019aa2  pop     rdi
0x180019aa3  pop     rsi
0x180019aa4  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
