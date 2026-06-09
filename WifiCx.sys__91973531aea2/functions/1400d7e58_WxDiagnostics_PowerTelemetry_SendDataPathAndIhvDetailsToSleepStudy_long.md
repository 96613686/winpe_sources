# WxDiagnostics::PowerTelemetry::SendDataPathAndIhvDetailsToSleepStudy(long)

- ea: `0x1400d7e58`
- end: `0x1400d81c3`
- name: `?SendDataPathAndIhvDetailsToSleepStudy@PowerTelemetry@WxDiagnostics@@AEAAXJ@Z`
- size: `875`
- prototype: `void __fastcall(WxDiagnostics::PowerTelemetry *__hidden this, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400d6d88`

## callees

- `0x14000c778`
- `0x14006f3a0`
- `0x1400d579c`
- `0x1400d58c8`
- `0x1400d72a8`
- `0x1400d7e58`
- `0x1400dfd00`
- `0x1400dfd40`

## import_xrefs

- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperDestroyBlocker` at `0x1400d80f5`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperDestroyBlocker` at `0x1400d8149`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperDestroyBlocker` at `0x1400d80f5`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperDestroyBlocker` at `0x1400d8149`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperGetBlockerGuid` at `0x1400d7eca`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperGetBlockerGuid` at `0x1400d7f1b`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperGetBlockerGuid` at `0x1400d7eca`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperGetBlockerGuid` at `0x1400d7f1b`

## pseudocode

```c
void __fastcall WxDiagnostics::PowerTelemetry::SendDataPathAndIhvDetailsToSleepStudy(
        WxDiagnostics::PowerTelemetry *this,
        int a2)
{
  unsigned __int64 v3; // rsi
  __int64 v4; // rcx
  int BlockerGuid; // eax
  int v6; // edx
  int v7; // r9d
  WxDiagnostics::PowerTelemetry *v8; // rcx
  unsigned int v9; // ebp
  int v10; // r8d
  unsigned int i; // edi
  __int64 v12; // rax
  _DWORD *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  struct _GUID *v19; // r8
  int v20; // eax
  int v21; // edx
  int v22; // eax
  int v23; // edx
  __int64 v24; // [rsp+28h] [rbp-60h]
  int v25; // [rsp+28h] [rbp-60h]
  struct _GUID v26; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v27; // [rsp+40h] [rbp-48h] BYREF

  v3 = a2;
  v4 = *((_QWORD *)this + 88);
  if ( v4 && *((_QWORD *)this + 89) )
  {
    v27 = 0;
    v26 = 0;
    BlockerGuid = SleepstudyHelperGetBlockerGuid(v4, &v27);
    if ( BlockerGuid < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_31;
      v7 = 112;
      goto LABEL_6;
    }
    BlockerGuid = SleepstudyHelperGetBlockerGuid(*((_QWORD *)this + 89), &v26);
    if ( BlockerGuid >= 0 )
    {
      if ( *((_DWORD *)this + 181)
        && (BlockerGuid = WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(
                            v8,
                            v3,
                            &v26,
                            L"SuspiciousIhvVictimWake",
                            *((unsigned int *)this + 181)),
            BlockerGuid < 0) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v7 = 114;
          goto LABEL_6;
        }
      }
      else
      {
        if ( !*((_DWORD *)this + 182)
          || (BlockerGuid = WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(
                              v8,
                              v3,
                              &v26,
                              L"SuspiciousIhvOffenderWake",
                              *((unsigned int *)this + 182)),
              BlockerGuid >= 0) )
        {
          v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 112))(
                 WdfDriverGlobals,
                 *((_QWORD *)this + 87));
          for ( i = 0; ; ++i )
          {
            if ( i >= v9 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_l(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v6,
                  v10,
                  117,
                  (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
                  v3);
              goto LABEL_31;
            }
            v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01031 + 144))(
                    WdfDriverGlobals,
                    *((_QWORD *)this + 87),
                    i);
            v13 = (_DWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031
                                                                                               + 1616))(
                              WdfDriverGlobals,
                              v12,
                              off_14010E3D0);
            v15 = (unsigned int)v13[3];
            if ( *v13 == 1 )
              v16 = MapWificxJobType(v15);
            else
              v16 = (const unsigned __int16 *)WxDiagnostics::WxHelpers::MapNetWakeReason(
                                                v15,
                                                v13,
                                                v14,
                                                (unsigned int)v13[1]);
            v19 = &v26;
            if ( *(_BYTE *)(v17 + 8) )
              v19 = &v27;
            BlockerGuid = WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(
                            (WxDiagnostics::PowerTelemetry *)&v27,
                            v3,
                            v19,
                            v16,
                            v18);
            if ( BlockerGuid < 0 )
              break;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_31;
          v7 = 116;
          goto LABEL_6;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v7 = 115;
          goto LABEL_6;
        }
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 113;
LABEL_6:
      v25 = BlockerGuid;
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        1,
        v7,
        (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
        v25,
        *(_QWORD *)&v26.Data1,
        *(_QWORD *)v26.Data4);
    }
  }
LABEL_31:
  if ( *((_QWORD *)this + 87) )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 1664))(WdfDriverGlobals);
    *((_QWORD *)this + 87) = 0;
  }
  if ( *((_QWORD *)this + 88) )
  {
    v20 = SleepstudyHelperDestroyBlocker();
    if ( v20 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v24) = v20;
      LOBYTE(v21) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        1,
        118,
        (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
        v24);
    }
    *((_QWORD *)this + 88) = 0;
  }
  if ( *((_QWORD *)this + 89) )
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
        119,
        (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
        v24);
    }
    *((_QWORD *)this + 89) = 0;
  }
  *(_QWORD *)((char *)this + 724) = 0;
}

```

## disassembly

```asm
0x1400d7e58  mov     [rsp+arg_10], rbx
0x1400d7e5d  mov     [rsp+arg_18], rbp
0x1400d7e62  push    rsi
0x1400d7e63  push    rdi
0x1400d7e64  push    r12
0x1400d7e66  push    r13
0x1400d7e68  push    r15
0x1400d7e6a  sub     rsp, 60h
0x1400d7e6e  mov     rax, cs:__security_cookie
0x1400d7e75  xor     rax, rsp
0x1400d7e78  mov     [rsp+88h+var_38], rax
0x1400d7e7d  mov     rbx, rcx
0x1400d7e80  movsxd  rsi, edx
0x1400d7e83  mov     rcx, [rcx+2C0h]
0x1400d7e8a  lea     r15, WPP_RECORDER_INITIALIZED
0x1400d7e91  lea     r13, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d7e98  mov     r12d, 1
0x1400d7e9e  test    rcx, rcx
0x1400d7ea1  jz      loc_1400D80B8
0x1400d7ea7  cmp     qword ptr [rbx+2C8h], 0
0x1400d7eaf  jz      loc_1400D80B8
0x1400d7eb5  xorps   xmm0, xmm0
0x1400d7eb8  lea     rdx, [rsp+88h+var_48]
0x1400d7ebd  xorps   xmm1, xmm1
0x1400d7ec0  movups  xmmword ptr [rsp+88h+var_48.Data1], xmm0
0x1400d7ec5  movups  xmmword ptr [rsp+88h+var_58.Data1], xmm1
0x1400d7eca  call    cs:__imp_SleepstudyHelperGetBlockerGuid
0x1400d7ed1  nop     dword ptr [rax+rax+00h]
0x1400d7ed6  test    eax, eax
0x1400d7ed8  jns     short loc_1400D7F0F
0x1400d7eda  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d7ee1  jz      loc_1400D80B8
0x1400d7ee7  lea     r9d, [r12+6Fh]
0x1400d7eec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7ef3  mov     r8d, r12d
0x1400d7ef6  mov     dword ptr [rsp+88h+var_60], eax
0x1400d7efa  mov     dl, 2
0x1400d7efc  mov     [rsp+88h+var_68], r13
0x1400d7f01  mov     rcx, [rcx+40h]
0x1400d7f05  call    WPP_RECORDER_SF_d
0x1400d7f0a  jmp     loc_1400D80B8
0x1400d7f0f  mov     rcx, [rbx+2C8h]
0x1400d7f16  lea     rdx, [rsp+88h+var_58]
0x1400d7f1b  call    cs:__imp_SleepstudyHelperGetBlockerGuid
0x1400d7f22  nop     dword ptr [rax+rax+00h]
0x1400d7f27  test    eax, eax
0x1400d7f29  jns     short loc_1400D7F40
0x1400d7f2b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d7f32  jz      loc_1400D80B8
0x1400d7f38  mov     r9d, 71h ; 'q'
0x1400d7f3e  jmp     short loc_1400D7EEC
0x1400d7f40  mov     eax, [rbx+2D4h]
0x1400d7f46  test    eax, eax
0x1400d7f48  jz      short loc_1400D7F7F
0x1400d7f4a  mov     rdx, rsi; unsigned __int64
0x1400d7f4d  mov     [rsp+88h+var_68], rax; unsigned __int64
0x1400d7f52  lea     r9, aSuspiciousihvv; "SuspiciousIhvVictimWake"
0x1400d7f59  lea     r8, [rsp+88h+var_58]; struct _GUID *
0x1400d7f5e  call    ?PublishSleepStudyCustomData@PowerTelemetry@WxDiagnostics@@AEAAJ_KPEBU_GUID@@PEBG0@Z; WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x1400d7f63  test    eax, eax
0x1400d7f65  jns     short loc_1400D7F7F
0x1400d7f67  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d7f6e  jz      loc_1400D80B8
0x1400d7f74  mov     r9d, 72h ; 'r'
0x1400d7f7a  jmp     loc_1400D7EEC
0x1400d7f7f  mov     eax, [rbx+2D8h]
0x1400d7f85  test    eax, eax
0x1400d7f87  jz      short loc_1400D7FBE
0x1400d7f89  mov     rdx, rsi; unsigned __int64
0x1400d7f8c  mov     [rsp+88h+var_68], rax; unsigned __int64
0x1400d7f91  lea     r9, aSuspiciousihvo; "SuspiciousIhvOffenderWake"
0x1400d7f98  lea     r8, [rsp+88h+var_58]; struct _GUID *
0x1400d7f9d  call    ?PublishSleepStudyCustomData@PowerTelemetry@WxDiagnostics@@AEAAJ_KPEBU_GUID@@PEBG0@Z; WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x1400d7fa2  test    eax, eax
0x1400d7fa4  jns     short loc_1400D7FBE
0x1400d7fa6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d7fad  jz      loc_1400D80B8
0x1400d7fb3  mov     r9d, 73h ; 's'
0x1400d7fb9  jmp     loc_1400D7EEC
0x1400d7fbe  mov     rax, cs:WdfFunctions_01031
0x1400d7fc5  mov     rdx, [rbx+2B8h]
0x1400d7fcc  mov     rcx, cs:WdfDriverGlobals
0x1400d7fd3  mov     rax, [rax+70h]
0x1400d7fd7  call    _guard_dispatch_icall
0x1400d7fdc  mov     ebp, eax
0x1400d7fde  xor     edi, edi
0x1400d7fe0  cmp     edi, ebp
0x1400d7fe2  jnb     loc_1400D8090
0x1400d7fe8  mov     rcx, cs:WdfFunctions_01031
0x1400d7fef  mov     r8d, edi
0x1400d7ff2  mov     rdx, [rbx+2B8h]
0x1400d7ff9  mov     rax, [rcx+90h]
0x1400d8000  mov     rcx, cs:WdfDriverGlobals
0x1400d8007  call    _guard_dispatch_icall
0x1400d800c  mov     rcx, cs:WdfFunctions_01031
0x1400d8013  mov     rdx, rax
0x1400d8016  mov     r8, cs:off_14010E3D0
0x1400d801d  mov     r9, [rcx+650h]
0x1400d8024  mov     rcx, cs:WdfDriverGlobals
0x1400d802b  mov     rax, r9
0x1400d802e  call    _guard_dispatch_icall
0x1400d8033  mov     rdx, rax
0x1400d8036  mov     r9d, [rax+4]
0x1400d803a  mov     ecx, [rax+0Ch]
0x1400d803d  cmp     [rax], r12d
0x1400d8040  jnz     short loc_1400D8049
0x1400d8042  call    ?MapWificxJobType@@YAPEBGW4_WFC_JOB_TYPE@@@Z; MapWificxJobType(_WFC_JOB_TYPE)
0x1400d8047  jmp     short loc_1400D804E
0x1400d8049  call    ?MapNetWakeReason@WxHelpers@WxDiagnostics@@YAPEBGW4_NET_WAKE_REASON_TYPE@@@Z; WxDiagnostics::WxHelpers::MapNetWakeReason(_NET_WAKE_REASON_TYPE)
0x1400d804e  cmp     byte ptr [rdx+8], 0
0x1400d8052  lea     rcx, [rsp+88h+var_48]; this
0x1400d8057  mov     [rsp+88h+var_68], r9; unsigned __int64
0x1400d805c  lea     r8, [rsp+88h+var_58]
0x1400d8061  cmovnz  r8, rcx; struct _GUID *
0x1400d8065  mov     rdx, rsi; unsigned __int64
0x1400d8068  mov     r9, rax; unsigned __int16 *
0x1400d806b  call    ?PublishSleepStudyCustomData@PowerTelemetry@WxDiagnostics@@AEAAJ_KPEBU_GUID@@PEBG0@Z; WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x1400d8070  test    eax, eax
0x1400d8072  js      short loc_1400D807C
0x1400d8074  add     edi, r12d
0x1400d8077  jmp     loc_1400D7FE0
0x1400d807c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d8083  jz      short loc_1400D80B8
0x1400d8085  mov     r9d, 74h ; 't'
0x1400d808b  jmp     loc_1400D7EEC
0x1400d8090  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d8097  jz      short loc_1400D80B8
0x1400d8099  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d80a0  mov     r9d, 75h ; 'u'
0x1400d80a6  mov     dword ptr [rsp+88h+var_60], esi
0x1400d80aa  mov     [rsp+88h+var_68], r13
0x1400d80af  mov     rcx, [rcx+40h]
0x1400d80b3  call    WPP_RECORDER_SF_l
0x1400d80b8  mov     rdx, [rbx+2B8h]
0x1400d80bf  test    rdx, rdx
0x1400d80c2  jz      short loc_1400D80E9
0x1400d80c4  mov     rax, cs:WdfFunctions_01031
0x1400d80cb  mov     rcx, cs:WdfDriverGlobals
0x1400d80d2  mov     rax, [rax+680h]
0x1400d80d9  call    _guard_dispatch_icall
0x1400d80de  mov     qword ptr [rbx+2B8h], 0
0x1400d80e9  mov     rcx, [rbx+2C0h]
0x1400d80f0  test    rcx, rcx
0x1400d80f3  jz      short loc_1400D813D
0x1400d80f5  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x1400d80fc  nop     dword ptr [rax+rax+00h]
0x1400d8101  test    eax, eax
0x1400d8103  jns     short loc_1400D8132
0x1400d8105  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d810c  jz      short loc_1400D8132
0x1400d810e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8115  mov     r9d, 76h ; 'v'
0x1400d811b  mov     dword ptr [rsp+88h+var_60], eax
0x1400d811f  mov     r8d, r12d
0x1400d8122  mov     dl, 2
0x1400d8124  mov     [rsp+88h+var_68], r13
0x1400d8129  mov     rcx, [rcx+40h]
0x1400d812d  call    WPP_RECORDER_SF_d
0x1400d8132  mov     qword ptr [rbx+2C0h], 0
0x1400d813d  mov     rcx, [rbx+2C8h]
0x1400d8144  test    rcx, rcx
0x1400d8147  jz      short loc_1400D8191
0x1400d8149  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x1400d8150  nop     dword ptr [rax+rax+00h]
0x1400d8155  test    eax, eax
0x1400d8157  jns     short loc_1400D8186
0x1400d8159  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400d8160  jz      short loc_1400D8186
0x1400d8162  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d8169  mov     r9d, 77h ; 'w'
0x1400d816f  mov     dword ptr [rsp+88h+var_60], eax
0x1400d8173  mov     r8d, r12d
0x1400d8176  mov     dl, 2
0x1400d8178  mov     [rsp+88h+var_68], r13
0x1400d817d  mov     rcx, [rcx+40h]
0x1400d8181  call    WPP_RECORDER_SF_d
0x1400d8186  mov     qword ptr [rbx+2C8h], 0
0x1400d8191  mov     qword ptr [rbx+2D4h], 0
0x1400d819c  mov     rcx, [rsp+88h+var_38]
0x1400d81a1  xor     rcx, rsp; StackCookie
0x1400d81a4  call    __security_check_cookie
0x1400d81a9  lea     r11, [rsp+88h+var_28]
0x1400d81ae  mov     rbx, [r11+40h]
0x1400d81b2  mov     rbp, [r11+48h]
0x1400d81b6  mov     rsp, r11
0x1400d81b9  pop     r15
0x1400d81bb  pop     r13
0x1400d81bd  pop     r12
0x1400d81bf  pop     rdi
0x1400d81c0  pop     rsi
0x1400d81c1  retn
```
