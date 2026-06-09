# WxDiagnostics::PowerTelemetry::CreateSleepStudyHelperBlocker(_SLEEPSTUDY_BLOCKER_GUID *,_UNICODE_STRING *,_SLEEPSTUDY_BLOCKER * *)

- ea: `0x1400d4310`
- end: `0x1400d44cf`
- name: `?CreateSleepStudyHelperBlocker@PowerTelemetry@WxDiagnostics@@AEAAJPEAT_SLEEPSTUDY_BLOCKER_GUID@@PEAU_UNICODE_STRING@@PEAPEAU_SLEEPSTUDY_BLOCKER@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(WxDiagnostics::PowerTelemetry *__hidden this, union _SLEEPSTUDY_BLOCKER_GUID *, struct _UNICODE_STRING *, struct _SLEEPSTUDY_BLOCKER **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400d44d8`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x1400d4310`
- `0x1400dfd40`

## import_xrefs

- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperDestroyBlockerBuilder` at `0x1400d447c`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperDestroyBlockerBuilder` at `0x1400d447c`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperBuildBlocker` at `0x1400d442c`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperBuildBlocker` at `0x1400d442c`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperCreateBlockerFromGuid` at `0x1400d43f0`
- `ext-ms-win-sleepstudy-km-l1-1-0!SleepstudyHelperCreateBlockerFromGuid` at `0x1400d43f0`

## pseudocode

```c
__int64 __fastcall WxDiagnostics::PowerTelemetry::CreateSleepStudyHelperBlocker(
        WxDiagnostics::PowerTelemetry *this,
        union _SLEEPSTUDY_BLOCKER_GUID *a2,
        struct _UNICODE_STRING *a3,
        struct _SLEEPSTUDY_BLOCKER **a4)
{
  union _SLEEPSTUDY_BLOCKER_GUID *v6; // rbp
  _QWORD *v9; // rbx
  int v10; // eax
  int v11; // edx
  unsigned int v12; // edi
  int v13; // r9d
  int v14; // edx
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  *a4 = 0;
  v6 = a2;
  if ( *((_QWORD *)this + 76) )
  {
    v9 = (_QWORD *)((char *)this + 616);
    v15 = 0;
    if ( *((_QWORD *)this + 77) == *(_QWORD *)&GUID_SPR_NULL.Data1
      && *((_QWORD *)this + 78) == *(_QWORD *)GUID_SPR_NULL.Data4 )
    {
      *v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 264))(
              WdfDriverGlobals,
              *((_QWORD *)this + 75));
    }
    v10 = SleepstudyHelperCreateBlockerFromGuid(*((_QWORD *)this + 76), v9, v6, a3, 0, &v15);
    v12 = v10;
    if ( v10 >= 0 )
    {
      v10 = SleepstudyHelperBuildBlocker(v15, a4);
      v12 = v10;
      if ( v10 >= 0 )
        return v12;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 95;
        goto LABEL_14;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 93;
LABEL_14:
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        1,
        v13,
        (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
        v10);
    }
    if ( v15
      && (int)SleepstudyHelperDestroyBlockerBuilder() < 0
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        1,
        96,
        (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
        v12);
    }
    return v12;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      88,
      (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids);
  }
  return 3221225480LL;
}

```

## disassembly

```asm
0x1400d4310  mov     [rsp+arg_8], rbx
0x1400d4315  mov     [rsp+arg_10], rbp
0x1400d431a  push    rsi
0x1400d431b  push    rdi
0x1400d431c  push    r14
0x1400d431e  sub     rsp, 30h
0x1400d4322  mov     qword ptr [r9], 0
0x1400d4329  mov     r14, r9
0x1400d432c  cmp     qword ptr [rcx+260h], 0
0x1400d4334  mov     rsi, r8
0x1400d4337  mov     rbp, rdx
0x1400d433a  mov     rdi, rcx
0x1400d433d  jnz     short loc_1400D4381
0x1400d433f  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400d4346  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d434d  jz      short loc_1400D4377
0x1400d434f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d4356  lea     rbp, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d435d  mov     r9d, 58h ; 'X'
0x1400d4363  mov     [rsp+48h+var_28], rbp
0x1400d4368  mov     dl, 2
0x1400d436a  mov     rcx, [rcx+40h]
0x1400d436e  lea     r8d, [r9-57h]
0x1400d4372  call    WPP_RECORDER_SF_
0x1400d4377  mov     eax, 0C0000008h
0x1400d437c  jmp     loc_1400D44BB
0x1400d4381  lea     rbx, [rcx+268h]
0x1400d4388  mov     [rsp+48h+arg_0], 0
0x1400d4391  mov     rax, [rbx]
0x1400d4394  cmp     rax, qword ptr cs:GUID_SPR_NULL.Data1
0x1400d439b  jnz     short loc_1400D43CE
0x1400d439d  mov     rax, [rbx+8]
0x1400d43a1  cmp     rax, qword ptr cs:GUID_SPR_NULL.Data4
0x1400d43a8  jnz     short loc_1400D43CE
0x1400d43aa  mov     rax, cs:WdfFunctions_01031
0x1400d43b1  mov     rdx, [rcx+258h]
0x1400d43b8  mov     rcx, cs:WdfDriverGlobals
0x1400d43bf  mov     rax, [rax+108h]
0x1400d43c6  call    _guard_dispatch_icall
0x1400d43cb  mov     [rbx], rax
0x1400d43ce  mov     rcx, [rdi+260h]
0x1400d43d5  lea     rax, [rsp+48h+arg_0]
0x1400d43da  mov     [rsp+48h+var_20], rax
0x1400d43df  mov     r9, rsi
0x1400d43e2  mov     r8, rbp
0x1400d43e5  mov     dword ptr [rsp+48h+var_28], 0
0x1400d43ed  mov     rdx, rbx
0x1400d43f0  call    cs:__imp_SleepstudyHelperCreateBlockerFromGuid
0x1400d43f7  nop     dword ptr [rax+rax+00h]
0x1400d43fc  lea     rbp, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d4403  mov     esi, 1
0x1400d4408  mov     edi, eax
0x1400d440a  test    eax, eax
0x1400d440c  jns     short loc_1400D4424
0x1400d440e  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400d4415  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d441c  jz      short loc_1400D4472
0x1400d441e  lea     r9d, [rsi+5Ch]
0x1400d4422  jmp     short loc_1400D4454
0x1400d4424  mov     rcx, [rsp+48h+arg_0]
0x1400d4429  mov     rdx, r14
0x1400d442c  call    cs:__imp_SleepstudyHelperBuildBlocker
0x1400d4433  nop     dword ptr [rax+rax+00h]
0x1400d4438  mov     edi, eax
0x1400d443a  test    eax, eax
0x1400d443c  jns     short loc_1400D44B9
0x1400d443e  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400d4445  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d444c  jz      short loc_1400D4472
0x1400d444e  mov     r9d, 5Fh ; '_'
0x1400d4454  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d445b  mov     r8d, esi
0x1400d445e  mov     dword ptr [rsp+48h+var_20], eax
0x1400d4462  mov     dl, 2
0x1400d4464  mov     [rsp+48h+var_28], rbp
0x1400d4469  mov     rcx, [rcx+40h]
0x1400d446d  call    WPP_RECORDER_SF_d
0x1400d4472  mov     rcx, [rsp+48h+arg_0]
0x1400d4477  test    rcx, rcx
0x1400d447a  jz      short loc_1400D44B9
0x1400d447c  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x1400d4483  nop     dword ptr [rax+rax+00h]
0x1400d4488  test    eax, eax
0x1400d448a  jns     short loc_1400D44B9
0x1400d448c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d4493  jz      short loc_1400D44B9
0x1400d4495  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d449c  mov     r9d, 60h ; '`'
0x1400d44a2  mov     dword ptr [rsp+48h+var_20], edi
0x1400d44a6  mov     r8d, esi
0x1400d44a9  mov     dl, 2
0x1400d44ab  mov     [rsp+48h+var_28], rbp
0x1400d44b0  mov     rcx, [rcx+40h]
0x1400d44b4  call    WPP_RECORDER_SF_d
0x1400d44b9  mov     eax, edi
0x1400d44bb  mov     rbx, [rsp+48h+arg_8]
0x1400d44c0  mov     rbp, [rsp+48h+arg_10]
0x1400d44c5  add     rsp, 30h
0x1400d44c9  pop     r14
0x1400d44cb  pop     rdi
0x1400d44cc  pop     rsi
0x1400d44cd  retn
```
