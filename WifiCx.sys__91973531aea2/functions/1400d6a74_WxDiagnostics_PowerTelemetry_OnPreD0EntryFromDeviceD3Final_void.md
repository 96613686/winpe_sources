# WxDiagnostics::PowerTelemetry::OnPreD0EntryFromDeviceD3Final(void)

- ea: `0x1400d6a74`
- end: `0x1400d6be4`
- name: `?OnPreD0EntryFromDeviceD3Final@PowerTelemetry@WxDiagnostics@@QEAAXXZ`
- size: `368`
- prototype: `void __fastcall(WxDiagnostics::PowerTelemetry *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400ccb80`

## callees

- `0x140001008`
- `0x140002064`
- `0x140004d48`
- `0x14000d054`
- `0x14004c0cc`
- `0x1400d50a8`
- `0x1400d6a74`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400d6aea`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400d6aea`
- `ntoskrnl!DbgPrintEx` at `0x1400d6a9f`
- `ntoskrnl!DbgPrintEx` at `0x1400d6b06`
- `ntoskrnl!DbgPrintEx` at `0x1400d6a9f`
- `ntoskrnl!DbgPrintEx` at `0x1400d6b06`

## string_xrefs

- `0x1400d6a95`: `WIFI ADAPTER DISABLE/ENABLE HAPPENED DURING MODERN STANDBY SESSION!\n`
- `0x1400d6afc`: `WIFI ADAPTER DISABLE/ENABLE HAPPENED DURING MODERN STANDBY SESSION!\n`

## pseudocode

```c
void __fastcall WxDiagnostics::PowerTelemetry::OnPreD0EntryFromDeviceD3Final(WxDiagnostics::PowerTelemetry *this)
{
  __int64 v2; // rcx
  int v3; // edx
  wificx::utils *v4; // rcx
  int v5; // edx
  int v6; // r8d
  __int64 v7; // rcx
  __int64 v8; // [rsp+40h] [rbp-18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF
  __int64 v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  if ( WxDiagnostics::PowerTelemetry::IsSleepStudyReportEnabled(this) )
  {
    if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(v2) )
    {
      DbgPrintEx(0x65u, 0, "WIFI ADAPTER DISABLE/ENABLE HAPPENED DURING MODERN STANDBY SESSION!\n");
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v3) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v3,
          1,
          12,
          (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids);
      }
      wificx::utils::BreakIfDebuggerIsPresent(v4);
    }
    else if ( KdRefreshDebuggerNotPresent() )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          1,
          13,
          (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids);
      }
    }
    else
    {
      DbgPrintEx(0x65u, 0, "WIFI ADAPTER DISABLE/ENABLE HAPPENED DURING MODERN STANDBY SESSION!\n");
      __debugbreak();
    }
    *((_DWORD *)this + 166) = 2;
    if ( (unsigned int)dword_14010EBA8 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_14010EBA8, 0x400000000000LL) )
      {
        v7 = _InterlockedCompareExchange((volatile signed __int32 *)this + 180, 0, 0);
        v10 = *((_QWORD *)this + 54);
        v9 = v7;
        v11 = 2048;
        v8 = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          v7,
          (unsigned int)&byte_1401053BF,
          v6,
          (unsigned int)&v8,
          (__int64)&v11,
          (__int64)&v10,
          (__int64)&v9);
      }
    }
  }
}

```

## disassembly

```asm
0x1400d6a74  push    rbx
0x1400d6a76  sub     rsp, 50h
0x1400d6a7a  mov     rbx, rcx
0x1400d6a7d  call    ?IsSleepStudyReportEnabled@PowerTelemetry@WxDiagnostics@@AEAA_NXZ; WxDiagnostics::PowerTelemetry::IsSleepStudyReportEnabled(void)
0x1400d6a82  test    al, al
0x1400d6a84  jz      loc_1400D6BDD
0x1400d6a8a  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1400d6a8f  test    eax, eax
0x1400d6a91  jz      short loc_1400D6AEA
0x1400d6a93  xor     edx, edx; Level
0x1400d6a95  lea     r8, aWifiAdapterDis; "WIFI ADAPTER DISABLE/ENABLE HAPPENED DU"...
0x1400d6a9c  lea     ecx, [rdx+65h]; ComponentId
0x1400d6a9f  call    cs:__imp_DbgPrintEx
0x1400d6aa6  nop     dword ptr [rax+rax+00h]
0x1400d6aab  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d6ab2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d6ab9  jz      short loc_1400D6AE3
0x1400d6abb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6ac2  lea     rax, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d6ac9  mov     r9d, 0Ch
0x1400d6acf  mov     [rsp+58h+var_38], rax
0x1400d6ad4  mov     dl, 2
0x1400d6ad6  mov     rcx, [rcx+40h]
0x1400d6ada  lea     r8d, [r9-0Bh]
0x1400d6ade  call    WPP_RECORDER_SF_
0x1400d6ae3  call    ?BreakIfDebuggerIsPresent@utils@wificx@@YAXXZ; wificx::utils::BreakIfDebuggerIsPresent(void)
0x1400d6ae8  jmp     short loc_1400D6B4D
0x1400d6aea  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400d6af1  nop     dword ptr [rax+rax+00h]
0x1400d6af6  test    al, al
0x1400d6af8  jnz     short loc_1400D6B15
0x1400d6afa  xor     edx, edx; Level
0x1400d6afc  lea     r8, aWifiAdapterDis; "WIFI ADAPTER DISABLE/ENABLE HAPPENED DU"...
0x1400d6b03  lea     ecx, [rdx+65h]; ComponentId
0x1400d6b06  call    cs:__imp_DbgPrintEx
0x1400d6b0d  nop     dword ptr [rax+rax+00h]
0x1400d6b12  int     3; Trap to Debugger
0x1400d6b13  jmp     short loc_1400D6B4D
0x1400d6b15  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d6b1c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d6b23  jz      short loc_1400D6B4D
0x1400d6b25  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d6b2c  lea     rax, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d6b33  mov     r9d, 0Dh
0x1400d6b39  mov     [rsp+58h+var_38], rax
0x1400d6b3e  mov     dl, 2
0x1400d6b40  mov     rcx, [rcx+40h]
0x1400d6b44  lea     r8d, [r9-0Ch]
0x1400d6b48  call    WPP_RECORDER_SF_
0x1400d6b4d  mov     dword ptr [rbx+298h], 2
0x1400d6b57  mov     eax, cs:dword_14010EBA8
0x1400d6b5d  cmp     eax, 5
0x1400d6b60  jbe     short loc_1400D6BDD
0x1400d6b62  mov     rdx, 400000000000h
0x1400d6b6c  lea     rcx, dword_14010EBA8
0x1400d6b73  call    _tlgKeywordOn
0x1400d6b78  test    al, al
0x1400d6b7a  jz      short loc_1400D6BDD
0x1400d6b7c  xor     ecx, ecx
0x1400d6b7e  xor     eax, eax
0x1400d6b80  lock cmpxchg [rbx+2D0h], ecx
0x1400d6b88  movsxd  rcx, eax
0x1400d6b8b  lea     r9, [rsp+58h+var_18]
0x1400d6b90  mov     rax, [rbx+1B0h]
0x1400d6b97  lea     rdx, byte_1401053BF
0x1400d6b9e  mov     [rsp+58h+arg_10], rax
0x1400d6ba3  lea     rax, [rsp+58h+arg_8]
0x1400d6ba8  mov     [rsp+58h+var_28], rax
0x1400d6bad  lea     rax, [rsp+58h+arg_10]
0x1400d6bb2  mov     [rsp+58h+var_30], rax
0x1400d6bb7  lea     rax, [rsp+58h+arg_18]
0x1400d6bbc  mov     [rsp+58h+var_38], rax
0x1400d6bc1  mov     [rsp+58h+arg_8], rcx
0x1400d6bc6  mov     [rsp+58h+arg_18], 800h
0x1400d6bcf  mov     [rsp+58h+var_18], 1
0x1400d6bd8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2AEBU?$_tlgWrapSz@G@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1400d6bdd  add     rsp, 50h
0x1400d6be1  pop     rbx
0x1400d6be2  retn
```
