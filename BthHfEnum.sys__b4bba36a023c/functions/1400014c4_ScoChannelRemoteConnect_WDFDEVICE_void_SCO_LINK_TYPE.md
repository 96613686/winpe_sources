# ScoChannelRemoteConnect(WDFDEVICE__ *,void *,_SCO_LINK_TYPE)

- ea: `0x1400014c4`
- end: `0x1400016ce`
- name: `?ScoChannelRemoteConnect@@YAXPEAUWDFDEVICE__@@PEAXW4_SCO_LINK_TYPE@@@Z`
- size: `522`
- prototype: `void __fastcall(struct WDFDEVICE__ *, void *, enum _SCO_LINK_TYPE)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c5b0`

## callees

- `0x1400014c4`
- `0x14000498c`
- `0x1400112c4`
- `0x1400120a8`
- `0x14001ae00`

## pseudocode

```c
void __fastcall ScoChannelRemoteConnect(struct WDFDEVICE__ *a1, void *a2, enum _SCO_LINK_TYPE a3)
{
  __int64 v5; // rdx
  __int64 Timer_high; // rcx
  __int64 v7; // rbx
  __int64 v8; // r8
  int v9; // edx
  int v10; // ecx
  const struct ScoConfigurationOptions * near **v11; // rax
  bool v12; // zf
  __int64 v13; // xmm0_8
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rdx
  void (__fastcall *v17)(PWDF_DRIVER_GLOBALS, __int64); // rax
  __int64 v18; // rdx
  _DWORD *v19; // rax
  __int128 v20; // xmm1
  _DWORD v21[2]; // [rsp+50h] [rbp-9h] BYREF
  const struct ScoConfigurationOptions * near **v22; // [rsp+58h] [rbp-1h]
  __int128 v23; // [rsp+60h] [rbp+7h]
  _DWORD v24[2]; // [rsp+70h] [rbp+17h] BYREF
  const struct ScoConfigurationOptions * near **v25; // [rsp+78h] [rbp+1Fh]
  int v26; // [rsp+80h] [rbp+27h]
  _QWORD v27[5]; // [rsp+84h] [rbp+2Bh] BYREF

  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_140022150);
  LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer), (Timer_high & 0x10) != 0)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      56,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
      (char)a2);
  if ( !*(_DWORD *)(v7 + 376) )
  {
    DWORD1(v23) = 0;
    *((_QWORD *)&v23 + 1) = 0;
    if ( (unsigned int)Feature_59215879__private_IsEnabledDeviceUsageNoInline(Timer_high, v5, v8) )
    {
      v9 = 1;
      v10 = 1;
    }
    else
    {
      v9 = 0;
      v10 = 2;
    }
    v11 = &c_scoConfigs_RemoteEscoWbs;
    if ( !v9 )
      v11 = &c_scoConfigs_RemoteEscoWbsOld;
    v12 = *(_DWORD *)(v7 + 104) == 2;
    memset(v27, 0, 12);
    if ( v12 )
    {
      v13 = v27[0];
      v14 = 2;
      v15 = v27[1];
    }
    else
    {
      v13 = *(_QWORD *)((char *)&v23 + 4);
      v11 = &c_scoConfigs_RemoteEsco;
      v15 = HIDWORD(v23);
      v14 = 1;
      v10 = 1;
    }
    v25 = v11;
    v22 = &c_scoConfigs_RemoteSco;
    v24[0] = -1073741808;
    v16 = *(_QWORD *)(v7 + 368);
    v26 = v10;
    v17 = *(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2528);
    v24[1] = v14;
    v27[0] = v13;
    LODWORD(v27[1]) = v15;
    v21[0] = -1073741808;
    v21[1] = 1;
    v23 = 1u;
    v17(WdfDriverGlobals, v16);
    v18 = *(_QWORD *)(v7 + 368);
    *(_QWORD *)(v7 + 416) = 1;
    v19 = v21;
    *(_QWORD *)(v7 + 400) = a2;
    *(_QWORD *)(v7 + 408) = 0;
    if ( a3 == eScoLinkType )
      v19 = v24;
    v20 = *((_OWORD *)v19 + 1);
    *(_OWORD *)(v7 + 424) = *(_OWORD *)v19;
    *(_OWORD *)(v7 + 440) = v20;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2536))(WdfDriverGlobals, v18);
    SetScoState(v7, 3);
  }
}

```

## disassembly

```asm
0x1400014c4  push    rbp
0x1400014c6  push    rbx
0x1400014c7  push    rsi
0x1400014c8  push    rdi
0x1400014c9  push    r15
0x1400014cb  lea     rbp, [rsp-37h]
0x1400014d0  sub     rsp, 90h
0x1400014d7  mov     rax, cs:WdfFunctions_01015
0x1400014de  mov     rdi, rdx
0x1400014e1  mov     esi, r8d
0x1400014e4  mov     rdx, rcx
0x1400014e7  mov     r8, cs:off_140022150
0x1400014ee  mov     rcx, cs:WdfDriverGlobals
0x1400014f5  mov     rax, [rax+650h]
0x1400014fc  call    _guard_dispatch_icall
0x140001501  mov     rbx, rax
0x140001504  mov     r10, cs:WPP_GLOBAL_Control
0x14000150b  lea     rax, WPP_GLOBAL_Control
0x140001512  mov     r15d, 1
0x140001518  cmp     r10, rax
0x14000151b  jz      short loc_140001532
0x14000151d  mov     ecx, [r10+2Ch]
0x140001521  test    cl, 10h
0x140001524  jz      short loc_140001532
0x140001526  cmp     byte ptr [r10+29h], 4
0x14000152b  jb      short loc_140001532
0x14000152d  mov     dl, r15b
0x140001530  jmp     short loc_140001534
0x140001532  xor     dl, dl
0x140001534  lea     rax, WPP_RECORDER_INITIALIZED
0x14000153b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001542  setnz   r8b
0x140001546  test    dl, dl
0x140001548  jnz     short loc_14000154F
0x14000154a  test    r8b, r8b
0x14000154d  jz      short loc_140001581
0x14000154f  mov     r9, [r10+40h]
0x140001553  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000155a  mov     rcx, [r10+18h]
0x14000155e  mov     [rsp+0B0h+var_70], rdi
0x140001563  mov     [rsp+0B0h+var_78], rax
0x140001568  mov     [rsp+0B0h+var_80], 38h ; '8'
0x14000156f  mov     [rsp+0B0h+var_88], 5
0x140001577  mov     [rsp+0B0h+var_90], 4
0x14000157c  call    WPP_RECORDER_AND_TRACE_SF_q
0x140001581  cmp     dword ptr [rbx+178h], 0
0x140001588  jnz     loc_1400016BF
0x14000158e  xor     eax, eax
0x140001590  mov     dword ptr [rbp+57h+var_50+4], eax
0x140001593  mov     qword ptr [rbp+57h+var_50+8], rax
0x140001597  call    Feature_59215879__private_IsEnabledDeviceUsageNoInline
0x14000159c  test    eax, eax
0x14000159e  jnz     short loc_1400015A7
0x1400015a0  xor     edx, edx
0x1400015a2  lea     ecx, [rax+2]
0x1400015a5  jmp     short loc_1400015AD
0x1400015a7  mov     edx, r15d
0x1400015aa  mov     rcx, r15
0x1400015ad  test    edx, edx
0x1400015af  lea     r8, ?c_scoConfigs_RemoteEscoWbsOld@@3PAPEBUScoConfigurationOptions@@A; ScoConfigurationOptions const * near * c_scoConfigs_RemoteEscoWbsOld
0x1400015b6  lea     rax, ?c_scoConfigs_RemoteEscoWbs@@3PAPEBUScoConfigurationOptions@@A; ScoConfigurationOptions const * near * c_scoConfigs_RemoteEscoWbs
0x1400015bd  cmovz   rax, r8
0x1400015c1  xor     edx, edx
0x1400015c3  cmp     dword ptr [rbx+68h], 2
0x1400015c7  mov     dword ptr [rbp+57h+var_2C], edx
0x1400015ca  mov     [rbp+57h+var_2C+4], rdx
0x1400015ce  mov     edx, 0C0000010h
0x1400015d3  jnz     short loc_1400015E6
0x1400015d5  movsd   xmm0, [rbp+57h+var_2C]
0x1400015da  mov     r8d, 2
0x1400015e0  mov     r9d, [rbp+57h+var_24]
0x1400015e4  jmp     short loc_1400015FC
0x1400015e6  movsd   xmm0, qword ptr [rbp+57h+var_50+4]
0x1400015eb  lea     rax, ?c_scoConfigs_RemoteEsco@@3PAPEBUScoConfigurationOptions@@A; ScoConfigurationOptions const * near * c_scoConfigs_RemoteEsco
0x1400015f2  mov     r9d, dword ptr [rbp+57h+var_50+0Ch]
0x1400015f6  mov     r8d, r15d
0x1400015f9  mov     ecx, r15d
0x1400015fc  mov     [rbp+57h+var_38], rax
0x140001600  lea     rax, ?c_scoConfigs_RemoteSco@@3PAPEBUScoConfigurationOptions@@A; ScoConfigurationOptions const * near * c_scoConfigs_RemoteSco
0x140001607  mov     [rbp+57h+var_58], rax
0x14000160b  xor     eax, eax
0x14000160d  mov     qword ptr [rbp+57h+var_50+8], rax
0x140001611  mov     rax, cs:WdfFunctions_01015
0x140001618  mov     [rbp+57h+var_40], edx
0x14000161b  mov     rdx, [rbx+170h]
0x140001622  mov     [rbp+57h+var_30], ecx
0x140001625  mov     rax, [rax+9E0h]
0x14000162c  mov     rcx, cs:WdfDriverGlobals
0x140001633  mov     [rbp+57h+var_3C], r8d
0x140001637  movsd   [rbp+57h+var_2C], xmm0
0x14000163c  mov     [rbp+57h+var_24], r9d
0x140001640  mov     [rbp+57h+var_60], 0C0000010h
0x140001647  mov     [rbp+57h+var_5C], r15d
0x14000164b  mov     [rbp+7], r15
0x14000164f  call    _guard_dispatch_icall
0x140001654  mov     rdx, [rbx+170h]
0x14000165b  lea     rcx, [rbp+57h+var_40]
0x14000165f  mov     [rbx+1A0h], r15
0x140001666  lea     rax, [rbp+57h+var_60]
0x14000166a  mov     [rbx+190h], rdi
0x140001671  cmp     esi, 2
0x140001674  mov     qword ptr [rbx+198h], 0
0x14000167f  cmovz   rax, rcx
0x140001683  movups  xmm0, xmmword ptr [rax]
0x140001686  movups  xmm1, xmmword ptr [rax+10h]
0x14000168a  movups  xmmword ptr [rbx+1A8h], xmm0
0x140001691  movups  xmmword ptr [rbx+1B8h], xmm1
0x140001698  mov     rax, cs:WdfFunctions_01015
0x14000169f  mov     rcx, cs:WdfDriverGlobals
0x1400016a6  mov     rax, [rax+9E8h]
0x1400016ad  call    _guard_dispatch_icall
0x1400016b2  mov     edx, 3
0x1400016b7  mov     rcx, rbx
0x1400016ba  call    SetScoState
0x1400016bf  add     rsp, 90h
0x1400016c6  pop     r15
0x1400016c8  pop     rdi
0x1400016c9  pop     rsi
0x1400016ca  pop     rbx
0x1400016cb  pop     rbp
0x1400016cc  retn
```
