# MbbNdisAdapterReadParameters(_MINIPORT_ADAPTER_CONTEXT *)

- ea: `0x140005df4`
- end: `0x14000619c`
- name: `?MbbNdisAdapterReadParameters@@YAJPEAU_MINIPORT_ADAPTER_CONTEXT@@@Z`
- size: `936`
- prototype: `__int64 __fastcall(struct _MINIPORT_ADAPTER_CONTEXT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140005c24`

## callees

- `0x140001db8`
- `0x140005df4`
- `0x14001e030`
- `0x140047e90`

## pseudocode

```c
__int64 __fastcall MbbNdisAdapterReadParameters(struct _MINIPORT_ADAPTER_CONTEXT *a1)
{
  struct WDFDEVICE__ *v2; // rcx
  int v3; // eax
  int v4; // edx
  int v5; // r9d
  unsigned int v6; // eax
  int v7; // edx
  unsigned int v8; // ebx
  char v9; // al
  int v10; // ecx
  __int64 v11; // rcx
  _WORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  _WORD *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r9d
  __int64 v21; // rdx
  struct _UNICODE_STRING v23; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING v24; // [rsp+50h] [rbp-30h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h] BYREF
  __int64 v26; // [rsp+70h] [rbp-10h]
  unsigned int v27; // [rsp+C0h] [rbp+40h] BYREF
  int v28; // [rsp+C8h] [rbp+48h] BYREF
  int v29; // [rsp+D0h] [rbp+50h] BYREF

  *(_QWORD *)&v23.Length = 4194366;
  v23.Buffer = L"AllowDriverToOverrideDeviceName";
  *(_QWORD *)&v24.Length = 3407922;
  v24.Buffer = L"NumberOfNetworkInterfaces";
  v2 = (struct WDFDEVICE__ *)*((_QWORD *)a1 + 145);
  v27 = 0;
  v3 = MbbRegReadULongParameter(v2, &v27, &v23);
  if ( v3 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_7;
    v5 = 13;
    LOBYTE(v4) = 2;
  }
  else
  {
    LOBYTE(v3) = v27 != 0;
    *((_BYTE *)a1 + 36) = v27 != 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_7;
    v5 = 12;
    LOBYTE(v4) = 4;
  }
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    v4,
    1,
    v5,
    (__int64)WPP_580131d7d7b43bdf16d74a9ec3843100_Traceguids,
    v3);
LABEL_7:
  v6 = MbbRegReadULongParameter(*((struct WDFDEVICE__ **)a1 + 145), &v27, &v24);
  v8 = v6;
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        16,
        (__int64)WPP_580131d7d7b43bdf16d74a9ec3843100_Traceguids,
        v6);
    }
    v8 = 0;
    goto LABEL_16;
  }
  v9 = v27;
  *((_DWORD *)a1 + 10) = v27;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 4;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      v8 + 14,
      (__int64)WPP_580131d7d7b43bdf16d74a9ec3843100_Traceguids,
      v9);
  }
  v10 = *((_DWORD *)a1 + 10);
  if ( (unsigned int)(v10 - 1) > 0xFF )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        15,
        (__int64)WPP_580131d7d7b43bdf16d74a9ec3843100_Traceguids,
        v10);
    }
LABEL_16:
    *((_DWORD *)a1 + 10) = 256;
  }
  if ( a1 == (struct _MINIPORT_ADAPTER_CONTEXT *)-90LL )
    goto LABEL_23;
  v11 = 64;
  v12 = (_WORD *)((char *)a1 + 90);
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  if ( !v11 )
LABEL_23:
    v13 = 0;
  else
    v13 = (2 * (64 - v11)) & -(__int64)(v11 != 0);
  if ( a1 == (struct _MINIPORT_ADAPTER_CONTEXT *)-346LL )
    goto LABEL_30;
  v14 = 64;
  v15 = (_WORD *)((char *)a1 + 346);
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  if ( !v14 )
LABEL_30:
    v16 = 0;
  else
    v16 = (2 * (64 - v14)) & -(__int64)(v14 != 0);
  if ( !v13 && !v16 )
  {
    v29 = 0;
    v28 = 0;
    v25 = 0;
    v26 = 0;
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x13 )
        LODWORD(v25) = -1;
      else
        LODWORD(v25) = *(_DWORD *)(WdfStructures + 152);
    }
    else
    {
      LODWORD(v25) = 24;
    }
    v17 = *((_QWORD *)a1 + 145);
    *((_QWORD *)&v25 + 1) = &DEVPKEY_Device_DriverProvider;
    v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, __int64, char *, int *, int *))(WdfFunctions_01031 + 3464))(
            WdfDriverGlobals,
            v17,
            &v25,
            256,
            (char *)a1 + 90,
            &v29,
            &v28);
    v8 = v18;
    if ( v18 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = 17;
LABEL_49:
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          1,
          v20,
          (__int64)WPP_580131d7d7b43bdf16d74a9ec3843100_Traceguids,
          v18);
      }
    }
    else
    {
      v25 = 0;
      v26 = 0;
      if ( WdfClientVersionHigherThanFramework )
      {
        if ( (unsigned int)WdfStructureCount <= 0x13 )
          LODWORD(v25) = -1;
        else
          LODWORD(v25) = *(_DWORD *)(WdfStructures + 152);
      }
      else
      {
        LODWORD(v25) = 24;
      }
      v21 = *((_QWORD *)a1 + 145);
      *((_QWORD *)&v25 + 1) = &DEVPKEY_Device_DriverDesc;
      v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, __int64, char *, int *, int *))(WdfFunctions_01031 + 3464))(
              WdfDriverGlobals,
              v21,
              &v25,
              256,
              (char *)a1 + 346,
              &v29,
              &v28);
      v8 = v18;
      if ( v18 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = 18;
        goto LABEL_49;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140005df4  mov     [rsp-38h+arg_18], rbx
0x140005df9  push    rbp
0x140005dfa  push    rsi
0x140005dfb  push    rdi
0x140005dfc  push    r12
0x140005dfe  push    r13
0x140005e00  push    r14
0x140005e02  push    r15
0x140005e04  mov     rbp, rsp
0x140005e07  sub     rsp, 80h
0x140005e0e  lea     rax, aAllowdrivertoo; "AllowDriverToOverrideDeviceName"
0x140005e15  mov     qword ptr [rbp+var_40.Length], 40003Eh
0x140005e1d  mov     [rbp+var_40.Buffer], rax
0x140005e21  lea     r8, [rbp+var_40]; struct _UNICODE_STRING *
0x140005e25  lea     rax, aNumberofnetwor; "NumberOfNetworkInterfaces"
0x140005e2c  mov     qword ptr [rbp+var_30.Length], 340032h
0x140005e34  mov     rdi, rcx
0x140005e37  mov     [rbp+var_30.Buffer], rax
0x140005e3b  mov     rcx, [rcx+488h]; struct WDFDEVICE__ *
0x140005e42  lea     rdx, [rbp+arg_0]; unsigned int *
0x140005e46  xor     r12d, r12d
0x140005e49  mov     r14d, 40h ; '@'
0x140005e4f  mov     [rbp+arg_0], r12d
0x140005e53  call    ?MbbRegReadULongParameter@@YAJPEAUWDFDEVICE__@@AEAKPEBU_UNICODE_STRING@@@Z; MbbRegReadULongParameter(WDFDEVICE__ *,ulong &,_UNICODE_STRING const *)
0x140005e58  lea     r15, WPP_580131d7d7b43bdf16d74a9ec3843100_Traceguids
0x140005e5f  lea     r13d, [r14-3Fh]
0x140005e63  test    eax, eax
0x140005e65  jnz     short loc_140005E8C
0x140005e67  cmp     [rbp+arg_0], r12d
0x140005e6b  setnz   al
0x140005e6e  mov     [rdi+24h], al
0x140005e71  lea     rsi, WPP_RECORDER_INITIALIZED
0x140005e78  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140005e7f  jz      short loc_140005EC0
0x140005e81  movzx   eax, al
0x140005e84  lea     r9d, [r14-34h]
0x140005e88  mov     dl, 4
0x140005e8a  jmp     short loc_140005EA4
0x140005e8c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140005e93  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140005e9a  jz      short loc_140005EC0
0x140005e9c  mov     r9d, 0Dh
0x140005ea2  mov     dl, 2
0x140005ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140005eab  mov     r8d, r13d
0x140005eae  mov     dword ptr [rsp+80h+var_58], eax
0x140005eb2  mov     [rsp+80h+var_60], r15
0x140005eb7  mov     rcx, [rcx+40h]
0x140005ebb  call    WPP_RECORDER_SF_d
0x140005ec0  mov     rcx, [rdi+488h]; struct WDFDEVICE__ *
0x140005ec7  lea     r8, [rbp+var_30]; struct _UNICODE_STRING *
0x140005ecb  lea     rdx, [rbp+arg_0]; unsigned int *
0x140005ecf  call    ?MbbRegReadULongParameter@@YAJPEAUWDFDEVICE__@@AEAKPEBU_UNICODE_STRING@@@Z; MbbRegReadULongParameter(WDFDEVICE__ *,ulong &,_UNICODE_STRING const *)
0x140005ed4  mov     ebx, eax
0x140005ed6  test    eax, eax
0x140005ed8  jnz     short loc_140005F47
0x140005eda  mov     eax, [rbp+arg_0]
0x140005edd  mov     [rdi+28h], eax
0x140005ee0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140005ee7  jz      short loc_140005F0B
0x140005ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ef0  lea     r9d, [rbx+0Eh]
0x140005ef4  mov     dword ptr [rsp+80h+var_58], eax
0x140005ef8  mov     r8d, r13d
0x140005efb  mov     dl, 4
0x140005efd  mov     [rsp+80h+var_60], r15
0x140005f02  mov     rcx, [rcx+40h]
0x140005f06  call    WPP_RECORDER_SF_d
0x140005f0b  mov     ecx, [rdi+28h]
0x140005f0e  lea     eax, [rcx-1]
0x140005f11  cmp     eax, 0FFh
0x140005f16  jbe     short loc_140005F7E
0x140005f18  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140005f1f  jz      short loc_140005F77
0x140005f21  mov     dword ptr [rsp+80h+var_58], ecx
0x140005f25  mov     r9d, 0Fh
0x140005f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f32  mov     r8d, r13d
0x140005f35  mov     dl, 4
0x140005f37  mov     [rsp+80h+var_60], r15
0x140005f3c  mov     rcx, [rcx+40h]
0x140005f40  call    WPP_RECORDER_SF_d
0x140005f45  jmp     short loc_140005F77
0x140005f47  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140005f4e  jz      short loc_140005F74
0x140005f50  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f57  mov     r9d, 10h
0x140005f5d  mov     dword ptr [rsp+80h+var_58], eax
0x140005f61  mov     r8d, r13d
0x140005f64  mov     dl, 2
0x140005f66  mov     [rsp+80h+var_60], r15
0x140005f6b  mov     rcx, [rcx+40h]
0x140005f6f  call    WPP_RECORDER_SF_d
0x140005f74  mov     ebx, r12d
0x140005f77  mov     dword ptr [rdi+28h], 100h
0x140005f7e  lea     r8, [rdi+5Ah]
0x140005f82  test    r8, r8
0x140005f85  jz      short loc_140005FB5
0x140005f87  mov     rcx, r14
0x140005f8a  mov     rax, r8
0x140005f8d  cmp     [rax], r12w
0x140005f91  jz      short loc_140005F9C
0x140005f93  add     rax, 2
0x140005f97  sub     rcx, r13
0x140005f9a  jnz     short loc_140005F8D
0x140005f9c  test    rcx, rcx
0x140005f9f  jz      short loc_140005FB5
0x140005fa1  mov     rax, r14
0x140005fa4  sub     rax, rcx
0x140005fa7  add     rax, rax
0x140005faa  neg     rcx
0x140005fad  sbb     rdx, rdx
0x140005fb0  and     rdx, rax
0x140005fb3  jmp     short loc_140005FB8
0x140005fb5  mov     rdx, r12
0x140005fb8  lea     r15, [rdi+15Ah]
0x140005fbf  test    r15, r15
0x140005fc2  jz      short loc_140005FEF
0x140005fc4  mov     rax, r14
0x140005fc7  mov     rcx, r15
0x140005fca  cmp     [rcx], r12w
0x140005fce  jz      short loc_140005FD9
0x140005fd0  add     rcx, 2
0x140005fd4  sub     rax, r13
0x140005fd7  jnz     short loc_140005FCA
0x140005fd9  test    rax, rax
0x140005fdc  jz      short loc_140005FEF
0x140005fde  sub     r14, rax
0x140005fe1  add     r14, r14
0x140005fe4  neg     rax
0x140005fe7  sbb     rcx, rcx
0x140005fea  and     rcx, r14
0x140005fed  jmp     short loc_140005FF2
0x140005fef  mov     rcx, r12
0x140005ff2  test    rdx, rdx
0x140005ff5  jnz     loc_14000617E
0x140005ffb  test    rcx, rcx
0x140005ffe  jnz     loc_14000617E
0x140006004  xor     eax, eax
0x140006006  mov     [rbp+arg_10], r12d
0x14000600a  cmp     cs:WdfClientVersionHigherThanFramework, r12b
0x140006011  lea     r14d, [rdx+18h]
0x140006015  xorps   xmm0, xmm0
0x140006018  mov     [rbp+arg_8], r12d
0x14000601c  movups  [rbp+var_20], xmm0
0x140006020  mov     [rbp+var_10], rax
0x140006024  jz      short loc_14000604A
0x140006026  cmp     cs:WdfStructureCount, 13h
0x14000602d  jbe     short loc_140006041
0x14000602f  mov     rax, cs:WdfStructures
0x140006036  mov     ecx, [rax+98h]
0x14000603c  mov     dword ptr [rbp+var_20], ecx
0x14000603f  jmp     short loc_14000604E
0x140006041  mov     dword ptr [rbp+var_20], 0FFFFFFFFh
0x140006048  jmp     short loc_14000604E
0x14000604a  mov     dword ptr [rbp+var_20], r14d
0x14000604e  mov     rdx, [rdi+488h]
0x140006055  lea     rax, DEVPKEY_Device_DriverProvider
0x14000605c  mov     qword ptr [rbp+var_20+8], rax
0x140006060  lea     rcx, [rbp+arg_8]
0x140006064  mov     rax, cs:WdfFunctions_01031
0x14000606b  mov     r9d, 100h
0x140006071  mov     [rsp+80h+var_50], rcx
0x140006076  lea     rcx, [rbp+arg_10]
0x14000607a  mov     [rsp+80h+var_58], rcx
0x14000607f  mov     rcx, cs:WdfDriverGlobals
0x140006086  mov     rax, [rax+0D88h]
0x14000608d  mov     [rsp+80h+var_60], r8
0x140006092  lea     r8, [rbp+var_20]
0x140006096  call    _guard_dispatch_icall
0x14000609b  mov     ebx, eax
0x14000609d  test    eax, eax
0x14000609f  jz      short loc_1400060B9
0x1400060a1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400060a8  jz      loc_14000617E
0x1400060ae  mov     r9d, 11h
0x1400060b4  jmp     loc_140006159
0x1400060b9  xor     eax, eax
0x1400060bb  xorps   xmm0, xmm0
0x1400060be  cmp     cs:WdfClientVersionHigherThanFramework, r12b
0x1400060c5  movups  [rbp+var_20], xmm0
0x1400060c9  mov     [rbp+var_10], rax
0x1400060cd  jz      short loc_1400060F3
0x1400060cf  cmp     cs:WdfStructureCount, 13h
0x1400060d6  jbe     short loc_1400060EA
0x1400060d8  mov     rax, cs:WdfStructures
0x1400060df  mov     ecx, [rax+98h]
0x1400060e5  mov     dword ptr [rbp+var_20], ecx
0x1400060e8  jmp     short loc_1400060F7
0x1400060ea  mov     dword ptr [rbp+var_20], 0FFFFFFFFh
0x1400060f1  jmp     short loc_1400060F7
0x1400060f3  mov     dword ptr [rbp+var_20], r14d
0x1400060f7  mov     rdx, [rdi+488h]
0x1400060fe  lea     rax, DEVPKEY_Device_DriverDesc
0x140006105  mov     qword ptr [rbp+var_20+8], rax
0x140006109  lea     rcx, [rbp+arg_8]
0x14000610d  mov     rax, cs:WdfFunctions_01031
0x140006114  lea     r8, [rbp+var_20]
0x140006118  mov     [rsp+80h+var_50], rcx
0x14000611d  mov     r9d, 100h
0x140006123  lea     rcx, [rbp+arg_10]
0x140006127  mov     [rsp+80h+var_58], rcx
0x14000612c  mov     rax, [rax+0D88h]
0x140006133  mov     rcx, cs:WdfDriverGlobals
0x14000613a  mov     [rsp+80h+var_60], r15
0x14000613f  call    _guard_dispatch_icall
0x140006144  mov     ebx, eax
0x140006146  test    eax, eax
0x140006148  jz      short loc_14000617E
0x14000614a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140006151  jz      short loc_14000617E
0x140006153  mov     r9d, 12h
0x140006159  mov     rcx, cs:WPP_GLOBAL_Control
0x140006160  mov     r8d, r13d
0x140006163  mov     dword ptr [rsp+80h+var_58], eax
0x140006167  mov     dl, 2
0x140006169  lea     rax, WPP_580131d7d7b43bdf16d74a9ec3843100_Traceguids
0x140006170  mov     [rsp+80h+var_60], rax
0x140006175  mov     rcx, [rcx+40h]
0x140006179  call    WPP_RECORDER_SF_d
0x14000617e  mov     eax, ebx
0x140006180  mov     rbx, [rsp+80h+arg_18]
0x140006188  add     rsp, 80h
0x14000618f  pop     r15
0x140006191  pop     r14
0x140006193  pop     r13
0x140006195  pop     r12
0x140006197  pop     rdi
0x140006198  pop     rsi
0x140006199  pop     rbp
0x14000619a  retn
```
