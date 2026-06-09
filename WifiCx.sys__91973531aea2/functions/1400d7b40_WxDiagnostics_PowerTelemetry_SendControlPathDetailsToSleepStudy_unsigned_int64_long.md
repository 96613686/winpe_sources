# WxDiagnostics::PowerTelemetry::SendControlPathDetailsToSleepStudy(unsigned __int64,long)

- ea: `0x1400d7b40`
- end: `0x1400d7e4f`
- name: `?SendControlPathDetailsToSleepStudy@PowerTelemetry@WxDiagnostics@@AEAAX_KJ@Z`
- size: `783`
- prototype: `void(WxDiagnostics::PowerTelemetry *__hidden this, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1400d6924`

## callees

- `0x14000c778`
- `0x14002ed50`
- `0x14006f3a0`
- `0x1400d00ec`
- `0x1400d4d1c`
- `0x1400d58c8`
- `0x1400d72a8`
- `0x1400d73b8`
- `0x1400d7b40`
- `0x1400dfd00`
- `0x1400dfd40`

## import_xrefs

- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperDestroyBlocker` at `0x1400d7ddf`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperDestroyBlocker` at `0x1400d7ddf`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperGetBlockerGuid` at `0x1400d7ba2`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperGetBlockerGuid` at `0x1400d7ba2`

## pseudocode

```c
void __fastcall WxDiagnostics::PowerTelemetry::SendControlPathDetailsToSleepStudy(
        WxDiagnostics::PowerTelemetry *this,
        unsigned __int64 a2,
        int a3)
{
  unsigned __int64 v4; // r15
  __int64 v5; // rcx
  int BlockerGuid; // eax
  int v8; // edx
  int v9; // r9d
  unsigned __int64 CurrentTime; // rax
  WxDiagnostics::PowerTelemetry *v11; // rcx
  unsigned int v12; // r14d
  WxDiagnostics::PowerTelemetry *v13; // rcx
  int v14; // r8d
  unsigned int i; // edi
  __int64 v16; // rax
  _DWORD *v17; // rax
  int v18; // ecx
  const unsigned __int16 *v19; // rax
  unsigned __int64 v20; // rdx
  WxDiagnostics::PowerTelemetry *v21; // rcx
  int v22; // eax
  int v23; // edx
  __int64 v24; // [rsp+28h] [rbp-81h]
  int v25; // [rsp+28h] [rbp-81h]
  struct _UNICODE_STRING v26; // [rsp+30h] [rbp-79h] BYREF
  struct _GUID v27; // [rsp+40h] [rbp-69h] BYREF
  char v28; // [rsp+50h] [rbp-59h] BYREF

  v4 = a3;
  v5 = *((_QWORD *)this + 85);
  if ( v5 )
  {
    v27 = 0;
    BlockerGuid = SleepstudyHelperGetBlockerGuid(v5, &v27);
    if ( BlockerGuid < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_27;
      v9 = 101;
      goto LABEL_5;
    }
    *(_QWORD *)&v26.Length = 7077888;
    v26.Buffer = (wchar_t *)&v28;
    CurrentTime = CSystem::get_CurrentTime();
    BlockerGuid = WxDiagnostics::PowerTelemetry::GetStandbyDeviceWakeScenarioTimeRangeString(v11, a2, CurrentTime, &v26);
    if ( BlockerGuid >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 112))(
              WdfDriverGlobals,
              *((_QWORD *)this + 84));
      BlockerGuid = WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(
                      (WxDiagnostics::PowerTelemetry *)v26.Buffer,
                      v4,
                      &v27,
                      L"[Wake Session Time Range]",
                      v26.Buffer);
      if ( BlockerGuid >= 0 )
      {
        if ( !v12
          || (BlockerGuid = WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(
                              v13,
                              v4,
                              &v27,
                              L"[Name]",
                              L"[Count]"),
              BlockerGuid >= 0) )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v12 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_l(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v8,
                  v14,
                  106,
                  (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
                  v4);
              goto LABEL_27;
            }
            v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01031 + 144))(
                    WdfDriverGlobals,
                    *((_QWORD *)this + 84),
                    i);
            v17 = (_DWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031
                                                                                               + 1616))(
                              WdfDriverGlobals,
                              v16,
                              off_14010E3F8);
            v18 = v17[2];
            v19 = *v17 == 1 ? MapWificxJobType(v18) : WxDiagnostics::WxHelpers::MapWakeReason(v18);
            BlockerGuid = WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(v21, v4, &v27, v19, v20);
            if ( BlockerGuid < 0 )
              break;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_27;
          v9 = 105;
          goto LABEL_5;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v9 = 104;
          goto LABEL_5;
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = 103;
        goto LABEL_5;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 102;
LABEL_5:
      v25 = BlockerGuid;
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        1,
        v9,
        (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
        v25,
        *(_QWORD *)&v26.Length);
    }
  }
LABEL_27:
  if ( *((_QWORD *)this + 84) )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 1664))(WdfDriverGlobals);
    *((_QWORD *)this + 84) = 0;
  }
  if ( *((_QWORD *)this + 85) )
  {
    v22 = SleepstudyHelperDestroyBlocker();
    if ( v22 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v24) = v22;
      LOBYTE(v23) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v23,
        1,
        107,
        (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
        v24);
    }
    *((_QWORD *)this + 85) = 0;
  }
}

```

## disassembly

```asm
0x1400d7b40  mov     [rsp-8+arg_18], rbx
0x1400d7b45  push    rbp
0x1400d7b46  push    rsi
0x1400d7b47  push    rdi
0x1400d7b48  push    r12
0x1400d7b4a  push    r13
0x1400d7b4c  push    r14
0x1400d7b4e  push    r15
0x1400d7b50  lea     rbp, [rsp-27h]
0x1400d7b55  sub     rsp, 0D0h
0x1400d7b5c  mov     rax, cs:__security_cookie
0x1400d7b63  xor     rax, rsp
0x1400d7b66  mov     [rbp+57h+var_40], rax
0x1400d7b6a  mov     rbx, rcx
0x1400d7b6d  movsxd  r15, r8d
0x1400d7b70  mov     rcx, [rcx+2A8h]
0x1400d7b77  lea     r12, WPP_RECORDER_INITIALIZED
0x1400d7b7e  lea     rsi, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d7b85  mov     rdi, rdx
0x1400d7b88  mov     r13d, 1
0x1400d7b8e  test    rcx, rcx
0x1400d7b91  jz      loc_1400D7DA2
0x1400d7b97  xorps   xmm0, xmm0
0x1400d7b9a  lea     rdx, [rbp+57h+var_C0]
0x1400d7b9e  movups  xmmword ptr [rbp+57h+var_C0.Data1], xmm0
0x1400d7ba2  call    cs:__imp_SleepstudyHelperGetBlockerGuid
0x1400d7ba9  nop     dword ptr [rax+rax+00h]
0x1400d7bae  test    eax, eax
0x1400d7bb0  jns     short loc_1400D7BE6
0x1400d7bb2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400d7bb9  jz      loc_1400D7DA2
0x1400d7bbf  lea     r9d, [r13+64h]
0x1400d7bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7bca  mov     r8d, r13d
0x1400d7bcd  mov     dword ptr [rsp+100h+var_D8], eax
0x1400d7bd1  mov     dl, 2
0x1400d7bd3  mov     [rsp+100h+var_E0], rsi
0x1400d7bd8  mov     rcx, [rcx+40h]
0x1400d7bdc  call    WPP_RECORDER_SF_d
0x1400d7be1  jmp     loc_1400D7DA2
0x1400d7be6  lea     rax, [rbp+57h+var_B0]
0x1400d7bea  mov     qword ptr [rbp+57h+var_D0.Length], 6C0000h
0x1400d7bf2  mov     [rbp+57h+var_D0.Buffer], rax
0x1400d7bf6  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400d7bfb  mov     r8, rax; unsigned __int64
0x1400d7bfe  lea     r9, [rbp+57h+var_D0]; struct _UNICODE_STRING *
0x1400d7c02  mov     rdx, rdi; unsigned __int64
0x1400d7c05  call    ?GetStandbyDeviceWakeScenarioTimeRangeString@PowerTelemetry@WxDiagnostics@@AEAAJ_K0PEAU_UNICODE_STRING@@@Z; WxDiagnostics::PowerTelemetry::GetStandbyDeviceWakeScenarioTimeRangeString(unsigned __int64,unsigned __int64,_UNICODE_STRING *)
0x1400d7c0a  test    eax, eax
0x1400d7c0c  jns     short loc_1400D7C23
0x1400d7c0e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400d7c15  jz      loc_1400D7DA2
0x1400d7c1b  mov     r9d, 66h ; 'f'
0x1400d7c21  jmp     short loc_1400D7BC3
0x1400d7c23  mov     rax, cs:WdfFunctions_01031
0x1400d7c2a  mov     rdx, [rbx+2A0h]
0x1400d7c31  mov     rcx, cs:WdfDriverGlobals
0x1400d7c38  mov     rax, [rax+70h]
0x1400d7c3c  call    _guard_dispatch_icall
0x1400d7c41  mov     rcx, [rbp+57h+var_D0.Buffer]; this
0x1400d7c45  lea     r9, aWakeSessionTim; "[Wake Session Time Range]"
0x1400d7c4c  lea     r8, [rbp+57h+var_C0]; struct _GUID *
0x1400d7c50  mov     [rsp+100h+var_E0], rcx; unsigned __int16 *
0x1400d7c55  mov     rdx, r15; unsigned __int64
0x1400d7c58  mov     r14d, eax
0x1400d7c5b  call    ?PublishSleepStudyCustomData@PowerTelemetry@WxDiagnostics@@AEAAJ_KPEBU_GUID@@PEBG2@Z; WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,ushort const *)
0x1400d7c60  test    eax, eax
0x1400d7c62  jns     short loc_1400D7C83
0x1400d7c64  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400d7c6b  lea     rsi, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d7c72  jz      loc_1400D7DA2
0x1400d7c78  mov     r9d, 67h ; 'g'
0x1400d7c7e  jmp     loc_1400D7BC3
0x1400d7c83  test    r14d, r14d
0x1400d7c86  jz      short loc_1400D7CCA
0x1400d7c88  lea     rax, aCount; "[Count]"
0x1400d7c8f  mov     rdx, r15; unsigned __int64
0x1400d7c92  lea     r9, aName; "[Name]"
0x1400d7c99  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x1400d7c9e  lea     r8, [rbp+57h+var_C0]; struct _GUID *
0x1400d7ca2  call    ?PublishSleepStudyCustomData@PowerTelemetry@WxDiagnostics@@AEAAJ_KPEBU_GUID@@PEBG2@Z; WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,ushort const *)
0x1400d7ca7  test    eax, eax
0x1400d7ca9  jns     short loc_1400D7CCA
0x1400d7cab  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400d7cb2  lea     rsi, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d7cb9  jz      loc_1400D7DA2
0x1400d7cbf  mov     r9d, 68h ; 'h'
0x1400d7cc5  jmp     loc_1400D7BC3
0x1400d7cca  xor     edi, edi
0x1400d7ccc  cmp     edi, r14d
0x1400d7ccf  jnb     loc_1400D7D72
0x1400d7cd5  mov     rax, cs:WdfFunctions_01031
0x1400d7cdc  mov     r8d, edi
0x1400d7cdf  mov     rdx, [rbx+2A0h]
0x1400d7ce6  mov     rcx, cs:WdfDriverGlobals
0x1400d7ced  mov     rax, [rax+90h]
0x1400d7cf4  call    _guard_dispatch_icall
0x1400d7cf9  mov     rcx, cs:WdfFunctions_01031
0x1400d7d00  mov     rdx, rax
0x1400d7d03  mov     r8, cs:off_14010E3F8
0x1400d7d0a  mov     r9, [rcx+650h]
0x1400d7d11  mov     rcx, cs:WdfDriverGlobals
0x1400d7d18  mov     rax, r9
0x1400d7d1b  call    _guard_dispatch_icall
0x1400d7d20  mov     edx, [rax+4]
0x1400d7d23  mov     ecx, [rax+8]
0x1400d7d26  cmp     [rax], r13d
0x1400d7d29  jnz     short loc_1400D7D32
0x1400d7d2b  call    ?MapWificxJobType@@YAPEBGW4_WFC_JOB_TYPE@@@Z; MapWificxJobType(_WFC_JOB_TYPE)
0x1400d7d30  jmp     short loc_1400D7D37
0x1400d7d32  call    ?MapWakeReason@WxHelpers@WxDiagnostics@@YAPEBGW4_WIFI_WAKE_REASON_TYPE@@@Z; WxDiagnostics::WxHelpers::MapWakeReason(_WIFI_WAKE_REASON_TYPE)
0x1400d7d37  mov     [rsp+100h+var_E0], rdx; unsigned __int64
0x1400d7d3c  lea     r8, [rbp+57h+var_C0]; struct _GUID *
0x1400d7d40  mov     rdx, r15; unsigned __int64
0x1400d7d43  mov     r9, rax; unsigned __int16 *
0x1400d7d46  call    ?PublishSleepStudyCustomData@PowerTelemetry@WxDiagnostics@@AEAAJ_KPEBU_GUID@@PEBG0@Z; WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x1400d7d4b  test    eax, eax
0x1400d7d4d  js      short loc_1400D7D57
0x1400d7d4f  add     edi, r13d
0x1400d7d52  jmp     loc_1400D7CCC
0x1400d7d57  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400d7d5e  lea     rsi, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d7d65  jz      short loc_1400D7DA2
0x1400d7d67  mov     r9d, 69h ; 'i'
0x1400d7d6d  jmp     loc_1400D7BC3
0x1400d7d72  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400d7d79  lea     rsi, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d7d80  jz      short loc_1400D7DA2
0x1400d7d82  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7d89  mov     r9d, 6Ah ; 'j'
0x1400d7d8f  mov     dword ptr [rsp+100h+var_D8], r15d
0x1400d7d94  mov     [rsp+100h+var_E0], rsi
0x1400d7d99  mov     rcx, [rcx+40h]
0x1400d7d9d  call    WPP_RECORDER_SF_l
0x1400d7da2  mov     rdx, [rbx+2A0h]
0x1400d7da9  test    rdx, rdx
0x1400d7dac  jz      short loc_1400D7DD3
0x1400d7dae  mov     rax, cs:WdfFunctions_01031
0x1400d7db5  mov     rcx, cs:WdfDriverGlobals
0x1400d7dbc  mov     rax, [rax+680h]
0x1400d7dc3  call    _guard_dispatch_icall
0x1400d7dc8  mov     qword ptr [rbx+2A0h], 0
0x1400d7dd3  mov     rcx, [rbx+2A8h]
0x1400d7dda  test    rcx, rcx
0x1400d7ddd  jz      short loc_1400D7E27
0x1400d7ddf  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x1400d7de6  nop     dword ptr [rax+rax+00h]
0x1400d7deb  test    eax, eax
0x1400d7ded  jns     short loc_1400D7E1C
0x1400d7def  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400d7df6  jz      short loc_1400D7E1C
0x1400d7df8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7dff  mov     r9d, 6Bh ; 'k'
0x1400d7e05  mov     dword ptr [rsp+100h+var_D8], eax
0x1400d7e09  mov     r8d, r13d
0x1400d7e0c  mov     dl, 2
0x1400d7e0e  mov     [rsp+100h+var_E0], rsi
0x1400d7e13  mov     rcx, [rcx+40h]
0x1400d7e17  call    WPP_RECORDER_SF_d
0x1400d7e1c  mov     qword ptr [rbx+2A8h], 0
0x1400d7e27  mov     rcx, [rbp+57h+var_40]
0x1400d7e2b  xor     rcx, rsp; StackCookie
0x1400d7e2e  call    __security_check_cookie
0x1400d7e33  mov     rbx, [rsp+100h+arg_18]
0x1400d7e3b  add     rsp, 0D0h
0x1400d7e42  pop     r15
0x1400d7e44  pop     r14
0x1400d7e46  pop     r13
0x1400d7e48  pop     r12
0x1400d7e4a  pop     rdi
0x1400d7e4b  pop     rsi
0x1400d7e4c  pop     rbp
0x1400d7e4d  retn
```
