# WxDiagnostics::PowerTelemetry::CDRollback_GetStandbyDeviceWakeScenarioName(WxDiagnostics::PowerTelemetry::PowerStateSessionWakeSource,_UNICODE_STRING *)

- ea: `0x1400d983c`
- end: `0x1400d99e4`
- name: `?CDRollback_GetStandbyDeviceWakeScenarioName@PowerTelemetry@WxDiagnostics@@AEAAJW4PowerStateSessionWakeSource@12@PEAU_UNICODE_STRING@@@Z`
- size: `424`
- prototype: `int __high(enum WxDiagnostics::PowerTelemetry::PowerStateSessionWakeSource, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1400d4b80`

## callees

- `0x14000c778`
- `0x1400d9354`
- `0x1400d983c`
- `0x1400dfd00`

## import_xrefs

- `ntoskrnl!RtlSystemTimeToLocalTime` at `0x1400d9883`
- `ntoskrnl!RtlSystemTimeToLocalTime` at `0x1400d9883`
- `ntoskrnl!RtlTimeToTimeFields` at `0x1400d98e2`
- `ntoskrnl!RtlTimeToTimeFields` at `0x1400d98e2`

## string_xrefs

- `0x1400d990e`: `DataPathWake`

## pseudocode

```c
__int64 __fastcall WxDiagnostics::PowerTelemetry::CDRollback_GetStandbyDeviceWakeScenarioName(
        union _LARGE_INTEGER *a1,
        int a2,
        struct _UNICODE_STRING *a3)
{
  NTSTATUS v5; // eax
  int v6; // edx
  unsigned int v7; // esi
  const wchar_t *v9; // r8
  int v10; // edx
  int v11; // edi
  int v12; // r9d
  int Second; // [rsp+20h] [rbp-48h]
  __int64 v14; // [rsp+28h] [rbp-40h]
  NTSTATUS v15; // [rsp+28h] [rbp-40h]
  union _LARGE_INTEGER Time; // [rsp+30h] [rbp-38h] BYREF
  union _LARGE_INTEGER v17; // [rsp+38h] [rbp-30h] BYREF
  struct _TIME_FIELDS TimeFields; // [rsp+40h] [rbp-28h] BYREF

  v17 = a1[82];
  Time.QuadPart = 0;
  TimeFields = 0;
  v5 = RtlSystemTimeToLocalTime(&v17, &Time);
  v7 = v5;
  if ( v5 >= 0 )
  {
    RtlTimeToTimeFields(&Time, &TimeFields);
    if ( (unsigned int)(a2 - 2) <= 1 )
    {
      Second = TimeFields.Second;
      v11 = RtlUnicodeStringPrintf(
              a3,
              L"[Detailed][%02d:%02d:%02d][WIFICX]%ws",
              (unsigned int)TimeFields.Hour,
              (unsigned int)TimeFields.Minute,
              Second,
              L"OS Wi-Fi Jobs Waked Up Device");
      if ( v11 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v12 = 11;
          goto LABEL_16;
        }
        return (unsigned int)v11;
      }
    }
    else if ( a2 == 1 || a2 == 4 )
    {
      v9 = L"DataPathWake";
      if ( a2 != 1 )
        v9 = L"SuspiciousIhvWake";
      v11 = RtlUnicodeStringPrintf(a3, L"[Aggregated]OS Wi-Fi Jobs Joined %ws", v9);
      if ( v11 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v12 = 12;
LABEL_16:
          LODWORD(v14) = v11;
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            1,
            v12,
            (__int64)WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids,
            v14);
          return (unsigned int)v11;
        }
        return (unsigned int)v11;
      }
    }
    return 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = v5;
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      10,
      (__int64)WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids,
      v15);
  }
  return v7;
}

```

## disassembly

```asm
0x1400d983c  mov     r11, rsp
0x1400d983f  mov     [r11+10h], rbp
0x1400d9843  mov     [r11+20h], rsi
0x1400d9847  push    rdi
0x1400d9848  sub     rsp, 60h
0x1400d984c  mov     rax, cs:__security_cookie
0x1400d9853  xor     rax, rsp
0x1400d9856  mov     [rsp+68h+var_18], rax
0x1400d985b  mov     rax, [rcx+290h]
0x1400d9862  mov     edi, edx
0x1400d9864  xorps   xmm0, xmm0
0x1400d9867  mov     [r11-30h], rax
0x1400d986b  lea     rdx, [r11-38h]; LocalTime
0x1400d986f  mov     qword ptr [r11-38h], 0
0x1400d9877  lea     rcx, [r11-30h]; SystemTime
0x1400d987b  mov     rbp, r8
0x1400d987e  movups  xmmword ptr [rsp+68h+TimeFields.Year], xmm0
0x1400d9883  call    cs:__imp_RtlSystemTimeToLocalTime
0x1400d988a  nop     dword ptr [rax+rax+00h]
0x1400d988f  mov     esi, eax
0x1400d9891  test    eax, eax
0x1400d9893  jns     short loc_1400D98D8
0x1400d9895  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400d989c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d98a3  jz      short loc_1400D98D1
0x1400d98a5  lea     rcx, WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids
0x1400d98ac  mov     dword ptr [rsp+68h+var_40], eax
0x1400d98b0  mov     [rsp+68h+var_48], rcx
0x1400d98b5  mov     r9d, 0Ah
0x1400d98bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d98c2  mov     dl, 2
0x1400d98c4  lea     r8d, [r9-9]
0x1400d98c8  mov     rcx, [rcx+40h]
0x1400d98cc  call    WPP_RECORDER_SF_d
0x1400d98d1  mov     eax, esi
0x1400d98d3  jmp     loc_1400D99C4
0x1400d98d8  lea     rdx, [rsp+68h+TimeFields]; TimeFields
0x1400d98dd  lea     rcx, [rsp+68h+Time]; Time
0x1400d98e2  call    cs:__imp_RtlTimeToTimeFields
0x1400d98e9  nop     dword ptr [rax+rax+00h]
0x1400d98ee  lea     eax, [rdi-2]
0x1400d98f1  cmp     eax, 1
0x1400d98f4  jbe     short loc_1400D994A
0x1400d98f6  cmp     edi, 1
0x1400d98f9  jz      short loc_1400D9904
0x1400d98fb  cmp     edi, 4
0x1400d98fe  jnz     loc_1400D99C2
0x1400d9904  lea     rax, aSuspiciousihvw_0; "SuspiciousIhvWake"
0x1400d990b  cmp     edi, 1
0x1400d990e  lea     r8, aDatapathwake_0; "DataPathWake"
0x1400d9915  mov     rcx, rbp; struct _UNICODE_STRING *
0x1400d9918  cmovnz  r8, rax
0x1400d991c  lea     rdx, aAggregatedOsWi_0; "[Aggregated]OS Wi-Fi Jobs Joined %ws"
0x1400d9923  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x1400d9928  mov     edi, eax
0x1400d992a  test    eax, eax
0x1400d992c  jns     loc_1400D99C2
0x1400d9932  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400d9939  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d9940  jz      short loc_1400D99BE
0x1400d9942  mov     r9d, 0Ch
0x1400d9948  jmp     short loc_1400D9996
0x1400d994a  movsx   eax, [rsp+68h+TimeFields.Second]
0x1400d994f  lea     rcx, aOsWiFiJobsWake_0; "OS Wi-Fi Jobs Waked Up Device"
0x1400d9956  movsx   r9d, [rsp+68h+TimeFields.Minute]
0x1400d995c  lea     rdx, aDetailed02d02d_0; "[Detailed][%02d:%02d:%02d][WIFICX]%ws"
0x1400d9963  movsx   r8d, [rsp+68h+TimeFields.Hour]
0x1400d9969  mov     [rsp+68h+var_40], rcx
0x1400d996e  mov     rcx, rbp; struct _UNICODE_STRING *
0x1400d9971  mov     dword ptr [rsp+68h+var_48], eax
0x1400d9975  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x1400d997a  mov     edi, eax
0x1400d997c  test    eax, eax
0x1400d997e  jns     short loc_1400D99C2
0x1400d9980  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400d9987  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d998e  jz      short loc_1400D99BE
0x1400d9990  mov     r9d, 0Bh
0x1400d9996  lea     rcx, WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids
0x1400d999d  mov     dword ptr [rsp+68h+var_40], edi
0x1400d99a1  mov     [rsp+68h+var_48], rcx
0x1400d99a6  mov     r8d, 1
0x1400d99ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d99b3  mov     dl, 2
0x1400d99b5  mov     rcx, [rcx+40h]
0x1400d99b9  call    WPP_RECORDER_SF_d
0x1400d99be  mov     eax, edi
0x1400d99c0  jmp     short loc_1400D99C4
0x1400d99c2  xor     eax, eax
0x1400d99c4  mov     rcx, [rsp+68h+var_18]
0x1400d99c9  xor     rcx, rsp; StackCookie
0x1400d99cc  call    __security_check_cookie
0x1400d99d1  lea     r11, [rsp+68h+var_8]
0x1400d99d6  mov     rbp, [r11+18h]
0x1400d99da  mov     rsi, [r11+28h]
0x1400d99de  mov     rsp, r11
0x1400d99e1  pop     rdi
0x1400d99e2  retn
```
