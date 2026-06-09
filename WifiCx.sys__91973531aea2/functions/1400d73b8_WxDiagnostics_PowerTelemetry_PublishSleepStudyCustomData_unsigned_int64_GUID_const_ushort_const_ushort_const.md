# WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,ushort const *)

- ea: `0x1400d73b8`
- end: `0x1400d751f`
- name: `?PublishSleepStudyCustomData@PowerTelemetry@WxDiagnostics@@AEAAJ_KPEBU_GUID@@PEBG2@Z`
- size: `359`
- prototype: `int(WxDiagnostics::PowerTelemetry *__hidden this, unsigned __int64, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400d72a8`
- `0x1400d7b40`

## callees

- `0x14000c778`
- `0x1400d73b8`
- `0x1400dfd00`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400d74a9`
- `ntoskrnl!EtwWrite` at `0x1400d74a9`

## pseudocode

```c
__int64 __fastcall WxDiagnostics::PowerTelemetry::PublishSleepStudyCustomData(
        WxDiagnostics::PowerTelemetry *this,
        __int64 a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // edx
  NTSTATUS v8; // ebx
  NTSTATUS v10; // [rsp+30h] [rbp-59h]
  char v11; // [rsp+38h] [rbp-51h] BYREF
  int v12; // [rsp+3Ch] [rbp-4Dh] BYREF
  int v13; // [rsp+40h] [rbp-49h] BYREF
  int v14; // [rsp+44h] [rbp-45h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-41h] BYREF
  int *v16; // [rsp+58h] [rbp-31h]
  __int64 v17; // [rsp+60h] [rbp-29h]
  const struct _GUID *v18; // [rsp+68h] [rbp-21h]
  __int64 v19; // [rsp+70h] [rbp-19h]
  int *v20; // [rsp+78h] [rbp-11h]
  __int64 v21; // [rsp+80h] [rbp-9h]
  const unsigned __int16 *v22; // [rsp+88h] [rbp-1h]
  int v23; // [rsp+90h] [rbp+7h]
  int v24; // [rsp+94h] [rbp+Bh]
  int *v25; // [rsp+98h] [rbp+Fh]
  __int64 v26; // [rsp+A0h] [rbp+17h]
  const unsigned __int16 *v27; // [rsp+A8h] [rbp+1Fh]
  int v28; // [rsp+B0h] [rbp+27h]
  int v29; // [rsp+B4h] [rbp+2Bh]
  __int64 *v30; // [rsp+B8h] [rbp+2Fh]
  __int64 v31; // [rsp+C0h] [rbp+37h]
  __int64 v32; // [rsp+F0h] [rbp+67h] BYREF

  v32 = a2;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a4[v6] );
  v13 = v6;
  do
    ++v5;
  while ( a5[v5] );
  v11 = a2;
  v23 = 2 * v6;
  UserData.Ptr = (ULONGLONG)&v11;
  v25 = &v14;
  v16 = &v12;
  v28 = 2 * v5;
  v22 = a4;
  v30 = &v32;
  v14 = v5;
  v20 = &v13;
  v27 = a5;
  v12 = 1;
  *(_QWORD *)&UserData.Size = 1;
  v17 = 4;
  v18 = a3;
  v19 = 16;
  v21 = 4;
  v24 = 0;
  v26 = 4;
  v29 = 0;
  v31 = 8;
  v8 = EtwWrite(SLEEPSTUDY_ETW_PROVIDER_Context, &SLEEPSTUDY_EVT_SCENARIO_BLOCKER_DATA, a3, 8u, &UserData);
  if ( v8 >= 0 )
    return 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = v8;
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      123,
      (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids,
      v10);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400d73b8  mov     rax, rsp
0x1400d73bb  mov     [rax+8], rbx
0x1400d73bf  mov     [rax+20h], rdi
0x1400d73c3  mov     [rax+10h], rdx
0x1400d73c7  push    rbp
0x1400d73c8  lea     rbp, [rax-57h]
0x1400d73cc  sub     rsp, 0D0h
0x1400d73d3  mov     rax, cs:__security_cookie
0x1400d73da  xor     rax, rsp
0x1400d73dd  mov     [rbp+4Fh+var_10], rax
0x1400d73e1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400d73e5  mov     r10, r8
0x1400d73e8  mov     rax, rcx
0x1400d73eb  xor     edi, edi
0x1400d73ed  mov     r8, rdx
0x1400d73f0  inc     rax
0x1400d73f3  cmp     [r9+rax*2], di
0x1400d73f8  jnz     short loc_1400D73F0
0x1400d73fa  mov     rdx, [rbp+4Fh+arg_20]
0x1400d73fe  mov     [rbp+4Fh+var_98], eax
0x1400d7401  inc     rcx
0x1400d7404  cmp     [rdx+rcx*2], di
0x1400d7408  jnz     short loc_1400D7401
0x1400d740a  add     eax, eax
0x1400d740c  mov     [rbp+4Fh+var_A0], r8b
0x1400d7410  mov     [rbp+4Fh+var_48], eax
0x1400d7413  lea     r8, [rbp+4Fh+var_A0]
0x1400d7417  mov     [rbp+4Fh+var_90.Ptr], r8
0x1400d741b  lea     rax, [rbp+4Fh+var_94]
0x1400d741f  mov     [rbp+4Fh+var_40], rax
0x1400d7423  lea     r8, [rbp+4Fh+var_9C]
0x1400d7427  lea     eax, [rcx+rcx]
0x1400d742a  mov     [rbp+4Fh+var_80], r8
0x1400d742e  mov     [rbp+4Fh+var_28], eax
0x1400d7431  lea     r8, [rbp+4Fh+var_98]
0x1400d7435  lea     rax, [rbp+4Fh+arg_8]
0x1400d7439  mov     [rbp+4Fh+var_50], r9
0x1400d743d  mov     [rbp+4Fh+var_20], rax
0x1400d7441  mov     r9d, 8; UserDataCount
0x1400d7447  lea     rax, [rbp+4Fh+var_90]
0x1400d744b  mov     [rbp+4Fh+var_94], ecx
0x1400d744e  mov     rcx, cs:SLEEPSTUDY_ETW_PROVIDER_Context; RegHandle
0x1400d7455  mov     [rbp+4Fh+var_60], r8
0x1400d7459  mov     r8, r10; ActivityId
0x1400d745c  mov     [rbp+4Fh+var_30], rdx
0x1400d7460  lea     rdx, SLEEPSTUDY_EVT_SCENARIO_BLOCKER_DATA; EventDescriptor
0x1400d7467  mov     [rsp+0D0h+UserData], rax; UserData
0x1400d746c  mov     [rbp+4Fh+var_9C], 1
0x1400d7473  mov     qword ptr [rbp+4Fh+var_90.Size], 1
0x1400d747b  mov     [rbp+4Fh+var_78], 4
0x1400d7483  mov     [rbp+4Fh+var_70], r10
0x1400d7487  mov     [rbp+4Fh+var_68], 10h
0x1400d748f  mov     [rbp+4Fh+var_58], 4
0x1400d7497  mov     [rbp+4Fh+var_44], edi
0x1400d749a  mov     [rbp+4Fh+var_38], 4
0x1400d74a2  mov     [rbp+4Fh+var_24], edi
0x1400d74a5  mov     [rbp+4Fh+var_18], r9
0x1400d74a9  call    cs:__imp_EtwWrite
0x1400d74b0  nop     dword ptr [rax+rax+00h]
0x1400d74b5  mov     ebx, eax
0x1400d74b7  test    eax, eax
0x1400d74b9  jns     short loc_1400D74FB
0x1400d74bb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d74c2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d74c9  jz      short loc_1400D74F7
0x1400d74cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d74d2  lea     rax, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d74d9  mov     r9d, 7Bh ; '{'
0x1400d74df  mov     [rsp+0D0h+var_A8], ebx
0x1400d74e3  mov     dl, 2
0x1400d74e5  mov     [rsp+0D0h+UserData], rax
0x1400d74ea  mov     rcx, [rcx+40h]
0x1400d74ee  lea     r8d, [r9-7Ah]
0x1400d74f2  call    WPP_RECORDER_SF_d
0x1400d74f7  mov     eax, ebx
0x1400d74f9  jmp     short loc_1400D74FD
0x1400d74fb  xor     eax, eax
0x1400d74fd  mov     rcx, [rbp+4Fh+var_10]
0x1400d7501  xor     rcx, rsp; StackCookie
0x1400d7504  call    __security_check_cookie
0x1400d7509  lea     r11, [rsp+0D0h+var_s0]
0x1400d7511  mov     rbx, [r11+10h]
0x1400d7515  mov     rdi, [r11+28h]
0x1400d7519  mov     rsp, r11
0x1400d751c  pop     rbp
0x1400d751d  retn
```
