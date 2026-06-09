# ScoChannelOpenAsync(WDFDEVICE__ *)

- ea: `0x14000dcf0`
- end: `0x14000df5e`
- name: `?ScoChannelOpenAsync@@YAJPEAUWDFDEVICE__@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(struct WDFDEVICE__ *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000fa40`
- `0x140013148`

## callees

- `0x1400041d0`
- `0x140004810`
- `0x14000dcf0`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall ScoChannelOpenAsync(struct WDFDEVICE__ *a1)
{
  bool v2; // dl
  __int64 *v3; // r9
  __int64 v4; // rsi
  int v5; // edx
  int v6; // edi
  int v7; // r8d
  __int64 v8; // rbx
  _QWORD v10[3]; // [rsp+50h] [rbp-29h] BYREF
  int v11; // [rsp+68h] [rbp-11h] BYREF
  __int128 v12; // [rsp+6Ch] [rbp-Dh]
  int v13; // [rsp+7Ch] [rbp+3h]
  int v14; // [rsp+80h] [rbp+7h]
  int v15; // [rsp+84h] [rbp+Bh]
  struct WDFDEVICE__ *v16; // [rsp+88h] [rbp+Fh]
  __int64 v17; // [rsp+90h] [rbp+17h]
  __int64 *v18; // [rsp+98h] [rbp+1Fh]
  __int64 v19; // [rsp+E0h] [rbp+67h] BYREF

  v2 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  v3 = WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      111,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *, __int64 *))(WdfFunctions_01015
                                                                                                  + 1616))(
         WdfDriverGlobals,
         a1,
         off_140022150,
         v3);
  v13 = 0;
  v17 = 0;
  v10[2] = 0;
  v10[0] = 24;
  v10[1] = ScoChannelOpenWorkItem;
  v18 = off_1400223A0;
  v12 = 0;
  v11 = 56;
  v14 = 1;
  v15 = 1;
  v16 = a1;
  v19 = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *, int *, __int64 *))(WdfFunctions_01015 + 3032))(
         WdfDriverGlobals,
         v10,
         &v11,
         &v19);
  if ( v6 < 0 )
  {
    LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer);
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v7,
        WPP_GLOBAL_Control->DeviceExtension,
        1,
        5,
        112,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
        v6);
    }
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           v19,
           off_1400223A0);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2528))(
      WdfDriverGlobals,
      *(_QWORD *)(v4 + 368));
    *(_OWORD *)v8 = *(_OWORD *)(v4 + 400);
    *(_OWORD *)(v8 + 16) = *(_OWORD *)(v4 + 416);
    *(_OWORD *)(v8 + 32) = *(_OWORD *)(v4 + 432);
    *(_QWORD *)(v8 + 48) = *(_QWORD *)(v4 + 448);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2536))(
      WdfDriverGlobals,
      *(_QWORD *)(v4 + 368));
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3040))(WdfDriverGlobals, v19);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000dcf0  push    rbp
0x14000dcf2  push    rbx
0x14000dcf3  push    rsi
0x14000dcf4  push    rdi
0x14000dcf5  push    r12
0x14000dcf7  push    r13
0x14000dcf9  lea     rbp, [rsp-2Fh]
0x14000dcfe  sub     rsp, 0A8h
0x14000dd05  mov     rbx, rcx
0x14000dd08  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd0f  lea     r12, WPP_GLOBAL_Control
0x14000dd16  cmp     rcx, r12
0x14000dd19  jz      short loc_14000DD2C
0x14000dd1b  mov     eax, [rcx+2Ch]
0x14000dd1e  test    al, 10h
0x14000dd20  jz      short loc_14000DD2C
0x14000dd22  cmp     byte ptr [rcx+29h], 4
0x14000dd26  jb      short loc_14000DD2C
0x14000dd28  mov     dl, 1
0x14000dd2a  jmp     short loc_14000DD2E
0x14000dd2c  xor     dl, dl
0x14000dd2e  lea     r13, WPP_RECORDER_INITIALIZED
0x14000dd35  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000dd3c  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000dd43  setnz   r8b
0x14000dd47  test    dl, dl
0x14000dd49  jnz     short loc_14000DD50
0x14000dd4b  test    r8b, r8b
0x14000dd4e  jz      short loc_14000DD76
0x14000dd50  mov     [rsp+0D0h+var_98], r9
0x14000dd55  mov     r9, [rcx+40h]
0x14000dd59  mov     rcx, [rcx+18h]
0x14000dd5d  mov     [rsp+0D0h+var_A0], 6Fh ; 'o'
0x14000dd64  mov     [rsp+0D0h+var_A8], 5
0x14000dd6c  mov     [rsp+0D0h+var_B0], 4
0x14000dd71  call    WPP_RECORDER_AND_TRACE_SF_
0x14000dd76  mov     rax, cs:WdfFunctions_01015
0x14000dd7d  mov     rdx, rbx
0x14000dd80  mov     r8, cs:off_140022150
0x14000dd87  mov     rcx, cs:WdfDriverGlobals
0x14000dd8e  mov     rax, [rax+650h]
0x14000dd95  call    _guard_dispatch_icall
0x14000dd9a  mov     rcx, cs:WdfDriverGlobals
0x14000dda1  lea     r9, [rbp+57h+arg_0]
0x14000dda5  mov     rsi, rax
0x14000dda8  mov     [rbp+57h+var_54], 0
0x14000ddaf  xor     eax, eax
0x14000ddb1  mov     [rbp+57h+var_40], 0
0x14000ddb9  mov     [rbp+57h+var_70], rax
0x14000ddbd  lea     r8, [rbp+57h+var_68]
0x14000ddc1  xorps   xmm0, xmm0
0x14000ddc4  mov     byte ptr [rbp+57h+var_70], 0
0x14000ddc8  movups  [rbp+57h+var_80], xmm0
0x14000ddcc  lea     rax, ?ScoChannelOpenWorkItem@@YAXPEAUWDFWORKITEM__@@@Z; ScoChannelOpenWorkItem(WDFWORKITEM__ *)
0x14000ddd3  mov     dword ptr [rbp+57h+var_80], 18h
0x14000ddda  mov     qword ptr [rbp+57h+var_80+8], rax
0x14000ddde  lea     rdx, [rbp+57h+var_80]
0x14000dde2  mov     rax, cs:off_1400223A0
0x14000dde9  mov     [rbp+57h+var_38], rax
0x14000dded  mov     rax, cs:WdfFunctions_01015
0x14000ddf4  movdqu  [rbp+57h+var_64], xmm0
0x14000ddf9  mov     [rbp+57h+var_68], 38h ; '8'
0x14000de00  mov     [rbp+57h+var_50], 1
0x14000de07  mov     [rbp+57h+var_4C], 1
0x14000de0e  mov     [rbp+57h+var_48], rbx
0x14000de12  mov     [rbp+57h+arg_0], 0
0x14000de1a  mov     rax, [rax+0BD8h]
0x14000de21  call    _guard_dispatch_icall
0x14000de26  mov     edi, eax
0x14000de28  test    eax, eax
0x14000de2a  js      loc_14000DEE7
0x14000de30  mov     rcx, cs:WdfFunctions_01015
0x14000de37  mov     r8, cs:off_1400223A0
0x14000de3e  mov     rdx, [rbp+57h+arg_0]
0x14000de42  mov     rax, [rcx+650h]
0x14000de49  mov     rcx, cs:WdfDriverGlobals
0x14000de50  call    _guard_dispatch_icall
0x14000de55  mov     rcx, cs:WdfFunctions_01015
0x14000de5c  mov     rbx, rax
0x14000de5f  mov     rdx, [rsi+170h]
0x14000de66  mov     rax, [rcx+9E0h]
0x14000de6d  mov     rcx, cs:WdfDriverGlobals
0x14000de74  call    _guard_dispatch_icall
0x14000de79  movups  xmm0, xmmword ptr [rsi+190h]
0x14000de80  movups  xmmword ptr [rbx], xmm0
0x14000de83  movups  xmm1, xmmword ptr [rsi+1A0h]
0x14000de8a  movups  xmmword ptr [rbx+10h], xmm1
0x14000de8e  movups  xmm0, xmmword ptr [rsi+1B0h]
0x14000de95  movups  xmmword ptr [rbx+20h], xmm0
0x14000de99  movsd   xmm1, qword ptr [rsi+1C0h]
0x14000dea1  movsd   qword ptr [rbx+30h], xmm1
0x14000dea6  mov     rax, cs:WdfFunctions_01015
0x14000dead  mov     rdx, [rsi+170h]
0x14000deb4  mov     rcx, cs:WdfDriverGlobals
0x14000debb  mov     rax, [rax+9E8h]
0x14000dec2  call    _guard_dispatch_icall
0x14000dec7  mov     rax, cs:WdfFunctions_01015
0x14000dece  mov     rdx, [rbp+57h+arg_0]
0x14000ded2  mov     rcx, cs:WdfDriverGlobals
0x14000ded9  mov     rax, [rax+0BE0h]
0x14000dee0  call    _guard_dispatch_icall
0x14000dee5  jmp     short loc_14000DF4B
0x14000dee7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000deee  cmp     rcx, r12
0x14000def1  jz      short loc_14000DF04
0x14000def3  mov     eax, [rcx+2Ch]
0x14000def6  test    al, 10h
0x14000def8  jz      short loc_14000DF04
0x14000defa  cmp     byte ptr [rcx+29h], 1
0x14000defe  jb      short loc_14000DF04
0x14000df00  mov     dl, 1
0x14000df02  jmp     short loc_14000DF06
0x14000df04  xor     dl, dl
0x14000df06  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000df0d  setnz   r8b
0x14000df11  test    dl, dl
0x14000df13  jnz     short loc_14000DF1A
0x14000df15  test    r8b, r8b
0x14000df18  jz      short loc_14000DF4B
0x14000df1a  mov     [rsp+0D0h+var_90], edi
0x14000df1e  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000df25  mov     [rsp+0D0h+var_98], r9
0x14000df2a  mov     r9, [rcx+40h]
0x14000df2e  mov     rcx, [rcx+18h]
0x14000df32  mov     [rsp+0D0h+var_A0], 70h ; 'p'
0x14000df39  mov     [rsp+0D0h+var_A8], 5
0x14000df41  mov     [rsp+0D0h+var_B0], 1
0x14000df46  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000df4b  mov     eax, edi
0x14000df4d  add     rsp, 0A8h
0x14000df54  pop     r13
0x14000df56  pop     r12
0x14000df58  pop     rdi
0x14000df59  pop     rsi
0x14000df5a  pop     rbx
0x14000df5b  pop     rbp
0x14000df5c  retn
```
