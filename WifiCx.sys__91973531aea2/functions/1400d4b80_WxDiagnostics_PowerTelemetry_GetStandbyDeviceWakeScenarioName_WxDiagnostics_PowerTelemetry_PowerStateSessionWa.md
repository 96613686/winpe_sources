# WxDiagnostics::PowerTelemetry::GetStandbyDeviceWakeScenarioName(WxDiagnostics::PowerTelemetry::PowerStateSessionWakeSource,_UNICODE_STRING *)

- ea: `0x1400d4b80`
- end: `0x1400d4d13`
- name: `?GetStandbyDeviceWakeScenarioName@PowerTelemetry@WxDiagnostics@@AEAAJW4PowerStateSessionWakeSource@12@PEAU_UNICODE_STRING@@@Z`
- size: `403`
- prototype: `int __high(enum WxDiagnostics::PowerTelemetry::PowerStateSessionWakeSource, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x1400d44d8`

## callees

- `0x140004d48`
- `0x14000c778`
- `0x14004bac8`
- `0x14004c000`
- `0x1400d4b80`
- `0x1400d983c`
- `0x1400dfd00`

## string_xrefs

- `0x1400d4c42`: `DataPathWake`

## pseudocode

```c
__int64 __fastcall WxDiagnostics::PowerTelemetry::GetStandbyDeviceWakeScenarioName(
        union _LARGE_INTEGER *a1,
        int a2,
        struct _UNICODE_STRING *a3)
{
  struct wificx::utils::TimeFields *v6; // r8
  wificx::utils *QuadPart; // rcx
  int v9; // eax
  int v10; // edx
  unsigned int v11; // esi
  const unsigned __int16 *v12; // r8
  int v13; // edx
  int v14; // edi
  int v15; // r9d
  int v16; // [rsp+20h] [rbp-48h]
  __int64 v17; // [rsp+28h] [rbp-40h]
  int v18; // [rsp+28h] [rbp-40h]
  unsigned __int64 v19[2]; // [rsp+30h] [rbp-38h] BYREF

  if ( !(unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(a1) )
    return WxDiagnostics::PowerTelemetry::CDRollback_GetStandbyDeviceWakeScenarioName(a1, a2, a3);
  QuadPart = (wificx::utils *)a1[82].QuadPart;
  *(_OWORD *)v19 = 0;
  v9 = wificx::utils::SystemTimeToLocalTimeFields(QuadPart, (unsigned __int64)v19, v6);
  v11 = v9;
  if ( v9 >= 0 )
  {
    if ( (unsigned int)(a2 - 2) <= 1 )
    {
      v16 = WORD2(v19[1]);
      v14 = wificx::utils::UnicodeStringPrint(
              (wificx::utils *)a3,
              (struct _UNICODE_STRING *)&stru_140103170,
              (const unsigned __int16 *)LOWORD(v19[1]),
              WORD1(v19[1]),
              v16,
              L"OS Wi-Fi Jobs Waked Up Device");
      if ( v14 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v15 = 78;
          goto LABEL_18;
        }
        return (unsigned int)v14;
      }
    }
    else if ( a2 == 1 || a2 == 4 )
    {
      v12 = L"DataPathWake";
      if ( a2 != 1 )
        v12 = L"SuspiciousIhvWake";
      v14 = wificx::utils::UnicodeStringPrint((wificx::utils *)a3, (struct _UNICODE_STRING *)&stru_140102F80, v12);
      if ( v14 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v15 = 79;
LABEL_18:
          LODWORD(v17) = v14;
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            1,
            v15,
            (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
            v17);
          return (unsigned int)v14;
        }
        return (unsigned int)v14;
      }
    }
    return 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v18 = v9;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      77,
      (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
      v18);
  }
  return v11;
}

```

## disassembly

```asm
0x1400d4b80  mov     [rsp+arg_18], rbx
0x1400d4b85  push    rbp
0x1400d4b86  push    rsi
0x1400d4b87  push    rdi
0x1400d4b88  sub     rsp, 50h
0x1400d4b8c  mov     rax, cs:__security_cookie
0x1400d4b93  xor     rax, rsp
0x1400d4b96  mov     [rsp+68h+var_28], rax
0x1400d4b9b  mov     rbp, r8
0x1400d4b9e  mov     edi, edx
0x1400d4ba0  mov     rbx, rcx
0x1400d4ba3  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1400d4ba8  test    eax, eax
0x1400d4baa  jnz     short loc_1400D4BBE
0x1400d4bac  mov     r8, rbp
0x1400d4baf  mov     edx, edi
0x1400d4bb1  mov     rcx, rbx
0x1400d4bb4  call    ?CDRollback_GetStandbyDeviceWakeScenarioName@PowerTelemetry@WxDiagnostics@@AEAAJW4PowerStateSessionWakeSource@12@PEAU_UNICODE_STRING@@@Z; WxDiagnostics::PowerTelemetry::CDRollback_GetStandbyDeviceWakeScenarioName(WxDiagnostics::PowerTelemetry::PowerStateSessionWakeSource,_UNICODE_STRING *)
0x1400d4bb9  jmp     loc_1400D4CF5
0x1400d4bbe  mov     rcx, [rbx+290h]; this
0x1400d4bc5  lea     rdx, [rsp+68h+var_38]; unsigned __int64
0x1400d4bca  xorps   xmm0, xmm0
0x1400d4bcd  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x1400d4bd2  call    ?SystemTimeToLocalTimeFields@utils@wificx@@YAJ_KPEAUTimeFields@12@@Z; wificx::utils::SystemTimeToLocalTimeFields(unsigned __int64,wificx::utils::TimeFields *)
0x1400d4bd7  mov     esi, eax
0x1400d4bd9  test    eax, eax
0x1400d4bdb  jns     short loc_1400D4C20
0x1400d4bdd  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400d4be4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d4beb  jz      short loc_1400D4C19
0x1400d4bed  lea     rcx, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d4bf4  mov     dword ptr [rsp+68h+var_40], eax
0x1400d4bf8  mov     [rsp+68h+var_48], rcx
0x1400d4bfd  mov     r9d, 4Dh ; 'M'
0x1400d4c03  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d4c0a  mov     dl, 2
0x1400d4c0c  lea     r8d, [r9-4Ch]
0x1400d4c10  mov     rcx, [rcx+40h]
0x1400d4c14  call    WPP_RECORDER_SF_d
0x1400d4c19  mov     eax, esi
0x1400d4c1b  jmp     loc_1400D4CF5
0x1400d4c20  lea     eax, [rdi-2]
0x1400d4c23  mov     ebx, 1
0x1400d4c28  cmp     eax, ebx
0x1400d4c2a  jbe     short loc_1400D4C7E
0x1400d4c2c  cmp     edi, ebx
0x1400d4c2e  jz      short loc_1400D4C39
0x1400d4c30  cmp     edi, 4
0x1400d4c33  jnz     loc_1400D4CF3
0x1400d4c39  lea     rax, aSuspiciousihvw; "SuspiciousIhvWake"
0x1400d4c40  cmp     edi, ebx
0x1400d4c42  lea     r8, aDatapathwake; "DataPathWake"
0x1400d4c49  mov     rcx, rbp; this
0x1400d4c4c  cmovnz  r8, rax; unsigned __int16 *
0x1400d4c50  lea     rdx, stru_140102F80; struct _UNICODE_STRING *
0x1400d4c57  call    ?UnicodeStringPrint@utils@wificx@@YAJPEAU_UNICODE_STRING@@PEBGZZ; wificx::utils::UnicodeStringPrint(_UNICODE_STRING *,ushort const *,...)
0x1400d4c5c  mov     edi, eax
0x1400d4c5e  test    eax, eax
0x1400d4c60  jns     loc_1400D4CF3
0x1400d4c66  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400d4c6d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d4c74  jz      short loc_1400D4CEF
0x1400d4c76  mov     r9d, 4Fh ; 'O'
0x1400d4c7c  jmp     short loc_1400D4CCA
0x1400d4c7e  movzx   eax, word ptr [rsp+68h+var_38+0Ch]
0x1400d4c83  lea     rcx, aOsWiFiJobsWake; "OS Wi-Fi Jobs Waked Up Device"
0x1400d4c8a  movzx   r9d, word ptr [rsp+68h+var_38+0Ah]
0x1400d4c90  lea     rdx, stru_140103170; struct _UNICODE_STRING *
0x1400d4c97  movzx   r8d, word ptr [rsp+68h+var_38+8]; unsigned __int16 *
0x1400d4c9d  mov     [rsp+68h+var_40], rcx
0x1400d4ca2  mov     rcx, rbp; this
0x1400d4ca5  mov     dword ptr [rsp+68h+var_48], eax
0x1400d4ca9  call    ?UnicodeStringPrint@utils@wificx@@YAJPEAU_UNICODE_STRING@@PEBGZZ; wificx::utils::UnicodeStringPrint(_UNICODE_STRING *,ushort const *,...)
0x1400d4cae  mov     edi, eax
0x1400d4cb0  test    eax, eax
0x1400d4cb2  jns     short loc_1400D4CF3
0x1400d4cb4  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400d4cbb  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400d4cc2  jz      short loc_1400D4CEF
0x1400d4cc4  mov     r9d, 4Eh ; 'N'
0x1400d4cca  lea     rcx, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d4cd1  mov     dword ptr [rsp+68h+var_40], edi
0x1400d4cd5  mov     [rsp+68h+var_48], rcx
0x1400d4cda  mov     r8d, ebx
0x1400d4cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d4ce4  mov     dl, 2
0x1400d4ce6  mov     rcx, [rcx+40h]
0x1400d4cea  call    WPP_RECORDER_SF_d
0x1400d4cef  mov     eax, edi
0x1400d4cf1  jmp     short loc_1400D4CF5
0x1400d4cf3  xor     eax, eax
0x1400d4cf5  mov     rcx, [rsp+68h+var_28]
0x1400d4cfa  xor     rcx, rsp; StackCookie
0x1400d4cfd  call    __security_check_cookie
0x1400d4d02  mov     rbx, [rsp+68h+arg_18]
0x1400d4d0a  add     rsp, 50h
0x1400d4d0e  pop     rdi
0x1400d4d0f  pop     rsi
0x1400d4d10  pop     rbp
0x1400d4d11  retn
```
