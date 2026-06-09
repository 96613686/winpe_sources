# MbbUtilReportWakeCommand(_MINIPORT_ADAPTER_CONTEXT *,_MBB_WAKE_REASON *,ulong)

- ea: `0x14003fa34`
- end: `0x14003ffb4`
- name: `?MbbUtilReportWakeCommand@@YAJPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MBB_WAKE_REASON@@K@Z`
- size: `1408`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, struct _MBB_WAKE_REASON *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400296d0`

## callees

- `0x1400018f0`
- `0x140001abc`
- `0x140001cf8`
- `0x140001db8`
- `0x1400051ac`
- `0x14000d49c`
- `0x14000dab8`
- `0x14003e100`
- `0x14003fa34`
- `0x140041df0`
- `0x140047530`
- `0x140047e50`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003fc09`
- `ntoskrnl!RtlCompareMemory` at `0x14003fe8e`
- `ntoskrnl!RtlCompareMemory` at `0x14003fefd`
- `ntoskrnl!RtlCompareMemory` at `0x14003fc09`
- `ntoskrnl!RtlCompareMemory` at `0x14003fe8e`
- `ntoskrnl!RtlCompareMemory` at `0x14003fefd`

## pseudocode

```c
__int64 __fastcall MbbUtilReportWakeCommand(PKSPIN_LOCK SpinLock, struct _MBB_WAKE_REASON *a2, int a3)
{
  __int64 v6; // rax
  __int64 v7; // r14
  int v8; // edx
  struct _MBB_TLV_IE *v9; // r12
  unsigned int v10; // edi
  int v11; // edx
  struct _MINIPORT_INTERFACE_CONTEXT *v12; // r15
  char *v13; // rsi
  int v14; // ebx
  char (near **CommandString)[32]; // rax
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rcx
  __int64 v22; // rdx
  int v23; // r9d
  unsigned int v24; // ebx
  __int64 v25; // rdx
  int v26; // edx
  int v27; // r9d
  char v29; // [rsp+28h] [rbp-48h]
  char v30; // [rsp+28h] [rbp-48h]
  char v31; // [rsp+30h] [rbp-40h]
  unsigned int v32; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v33[12]; // [rsp+44h] [rbp-2Ch] BYREF
  __int128 Source1; // [rsp+50h] [rbp-20h] BYREF

  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, KSPIN_LOCK, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         SpinLock[145],
         off_14005DF70);
  v32 = 0;
  *(_QWORD *)&v33[4] = (char *)a2 + 8;
  v7 = v6;
  *(_DWORD *)v33 = a3 - 8;
  v9 = mbbcx_p::ExtractValidateNextTlv(
         (mbbcx_p *)&v33[4],
         (unsigned __int8 **)v33,
         &v32,
         (enum mbbcx_p::MbbTlvError *)0x10);
  if ( !v9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        9,
        99,
        (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
        v32);
    }
    return (unsigned int)-1073739509;
  }
  v12 = MbbWwanReferenceSessionForSessionId(SpinLock, *((_DWORD *)a2 + 1));
  if ( v12 )
  {
    v13 = (char *)v9 + 8;
    Source1 = 0;
    v10 = 0;
    LODWORD(Source1) = _byteswap_ulong(*((_DWORD *)v9 + 2));
    WORD2(Source1) = __ROR2__(*((_WORD *)v9 + 6), 8);
    WORD3(Source1) = __ROR2__(*((_WORD *)v9 + 7), 8);
    *((_QWORD *)&Source1 + 1) = *((_QWORD *)v9 + 2);
    if ( !*(_DWORD *)a2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = *((_DWORD *)v9 + 6);
        CommandString = MbbUtilGetCommandString((struct _MBB_TLV_IE *)((char *)v9 + 8));
        WPP_RECORDER_SF__guid_sd(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          9,
          101,
          (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
          (__int64)&Source1,
          (__int64)CommandString,
          v14);
      }
      goto LABEL_58;
    }
    if ( RtlCompareMemory(&Source1, &MBB_UUID_BASIC_CONNECT, 0x10u) == 16 )
    {
      switch ( *((_DWORD *)v9 + 6) )
      {
        case 2:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = 4;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              9,
              108,
              (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids);
          }
          v25 = 4;
          break;
        case 9:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = 4;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              9,
              106,
              (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids);
          }
          v25 = 0;
          break;
        case 0xA:
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = 4;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              9,
              107,
              (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids);
          }
          v25 = 3;
          break;
        case 0xC:
          v21 = *((unsigned int *)v9 + 7);
          if ( (unsigned int)v21 < 0x1C )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v17) = 2;
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v17,
                9,
                102,
                (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids);
            }
            goto LABEL_23;
          }
          v22 = *((unsigned int *)v9 + 7);
          if ( v21 + 4 <= (unsigned __int64)*((unsigned int *)v9 + 1) )
          {
            if ( *((_DWORD *)v9 + 8) == 4 )
            {
              v24 = (*(_DWORD *)&v13[v22] != 1) + 1;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v30 = (*(_DWORD *)&v13[v22] != 1) + 1;
                LOBYTE(v22) = 4;
                WPP_RECORDER_SF_d(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v22,
                  9,
                  105,
                  (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
                  v30);
              }
              ((void (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD, _QWORD))qword_14005F5E8)(
                NetDriverGlobals,
                *((_QWORD *)v12 + 1),
                v24);
              goto LABEL_58;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_23;
            v31 = 4;
            v23 = 104;
            v29 = *((_DWORD *)v9 + 8);
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
LABEL_23:
              v10 = -1073741811;
              goto LABEL_58;
            }
            v31 = *((_DWORD *)v9 + 1);
            v29 = v21 + 4;
            v23 = 103;
          }
          LOBYTE(v22) = 2;
          WPP_RECORDER_SF_DD(
            WPP_GLOBAL_Control->DeviceExtension,
            v22,
            9,
            v23,
            (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
            v29,
            v31);
          goto LABEL_23;
        default:
          v10 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
LABEL_58:
            DereferenceSession(v12);
            return v10;
          }
          MbbUtilGetCommandString((struct _MBB_TLV_IE *)((char *)v9 + 8));
          v20 = 109;
LABEL_19:
          WPP_RECORDER_SF_sd(WPP_GLOBAL_Control->DeviceExtension, v18, v19, v20);
          goto LABEL_58;
      }
LABEL_57:
      MbxDevice::ReportWakeReason(v7, v25);
      goto LABEL_58;
    }
    if ( RtlCompareMemory(&Source1, &MBB_UUID_SMS, 0x10u) == 16 )
    {
      if ( *((_DWORD *)v9 + 6) != 5 )
      {
        v10 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_58;
        MbbUtilGetCommandString((struct _MBB_TLV_IE *)((char *)v9 + 8));
        v20 = 111;
        goto LABEL_19;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v27 = 110;
    }
    else
    {
      if ( RtlCompareMemory(&Source1, &MBB_UUID_USSD, 0x10u) != 16 )
        goto LABEL_58;
      if ( *((_DWORD *)v9 + 6) != 1 )
      {
        v10 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_58;
        MbbUtilGetCommandString((struct _MBB_TLV_IE *)((char *)v9 + 8));
        v20 = 113;
        goto LABEL_19;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_56;
      v27 = 112;
    }
    LOBYTE(v26) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v26,
      9,
      v27,
      (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids);
LABEL_56:
    v25 = 1;
    goto LABEL_57;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 3;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      8,
      100,
      (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids,
      *((_DWORD *)a2 + 1));
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x14003fa34  mov     [rsp-38h+arg_18], rbx
0x14003fa39  push    rbp
0x14003fa3a  push    rsi
0x14003fa3b  push    rdi
0x14003fa3c  push    r12
0x14003fa3e  push    r13
0x14003fa40  push    r14
0x14003fa42  push    r15
0x14003fa44  mov     rbp, rsp
0x14003fa47  sub     rsp, 70h
0x14003fa4b  mov     rax, cs:__security_cookie
0x14003fa52  xor     rax, rsp
0x14003fa55  mov     [rbp+var_10], rax
0x14003fa59  mov     rax, cs:WdfFunctions_01031
0x14003fa60  mov     r13, rdx
0x14003fa63  mov     rdx, [rcx+488h]
0x14003fa6a  mov     ebx, r8d
0x14003fa6d  mov     r8, cs:off_14005DF70
0x14003fa74  mov     rdi, rcx
0x14003fa77  mov     rcx, cs:WdfDriverGlobals
0x14003fa7e  mov     rax, [rax+650h]
0x14003fa85  call    _guard_dispatch_icall
0x14003fa8a  lea     rcx, [r13+8]
0x14003fa8e  mov     [rbp+var_30], 0
0x14003fa95  mov     qword ptr [rbp+var_2C+4], rcx
0x14003fa99  lea     r8, [rbp+var_30]; unsigned int *
0x14003fa9d  lea     ecx, [rbx-8]
0x14003faa0  mov     r14, rax
0x14003faa3  mov     dword ptr [rbp+var_2C], ecx
0x14003faa6  lea     rdx, [rbp+var_2C]; unsigned __int8 **
0x14003faaa  mov     ebx, 10h
0x14003faaf  lea     rcx, [rbp+var_2C+4]; this
0x14003fab3  mov     r9d, ebx; enum mbbcx_p::MbbTlvError *
0x14003fab6  call    ?ExtractValidateNextTlv@mbbcx_p@@YAPEAU_MBB_TLV_IE@@AEAPEAEAEAKAEAW4MbbTlvError@1@G@Z; mbbcx_p::ExtractValidateNextTlv(uchar * &,ulong &,mbbcx_p::MbbTlvError &,ushort)
0x14003fabb  mov     r12, rax
0x14003fabe  test    rax, rax
0x14003fac1  jnz     short loc_14003FB0A
0x14003fac3  lea     rax, WPP_RECORDER_INITIALIZED
0x14003faca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fad1  jz      short loc_14003FB00
0x14003fad3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fada  lea     r9d, [rbx+53h]
0x14003fade  mov     eax, [rbp+var_30]
0x14003fae1  lea     r8d, [rbx-7]
0x14003fae5  mov     dword ptr [rsp+70h+var_48], eax
0x14003fae9  mov     dl, 2
0x14003faeb  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003faf2  mov     rcx, [rcx+40h]
0x14003faf6  mov     [rsp+70h+var_50], rax
0x14003fafb  call    WPP_RECORDER_SF_d
0x14003fb00  mov     edi, 0C000090Bh
0x14003fb05  jmp     loc_14003FF8D
0x14003fb0a  mov     edx, [r13+4]; unsigned int
0x14003fb0e  mov     rcx, rdi; SpinLock
0x14003fb11  call    ?MbbWwanReferenceSessionForSessionId@@YAPEAU_MINIPORT_INTERFACE_CONTEXT@@PEAU_MINIPORT_ADAPTER_CONTEXT@@K@Z; MbbWwanReferenceSessionForSessionId(_MINIPORT_ADAPTER_CONTEXT *,ulong)
0x14003fb16  mov     r15, rax
0x14003fb19  test    rax, rax
0x14003fb1c  jnz     short loc_14003FB66
0x14003fb1e  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fb25  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fb2c  jz      short loc_14003FB5C
0x14003fb2e  mov     eax, [r13+4]
0x14003fb32  lea     r9d, [r15+64h]
0x14003fb36  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fb3d  lea     r8d, [r15+8]
0x14003fb41  mov     dword ptr [rsp+70h+var_48], eax
0x14003fb45  mov     dl, 3
0x14003fb47  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003fb4e  mov     [rsp+70h+var_50], rax
0x14003fb53  mov     rcx, [rcx+40h]
0x14003fb57  call    WPP_RECORDER_SF_d
0x14003fb5c  mov     edi, 0C000000Dh
0x14003fb61  jmp     loc_14003FF8D
0x14003fb66  lea     rsi, [r12+8]
0x14003fb6b  xorps   xmm0, xmm0
0x14003fb6e  movups  [rbp+Source1], xmm0
0x14003fb72  mov     eax, [rsi]
0x14003fb74  xor     edi, edi
0x14003fb76  bswap   eax
0x14003fb78  mov     dword ptr [rbp+Source1], eax
0x14003fb7b  movzx   eax, word ptr [rsi+4]
0x14003fb7f  ror     ax, 8
0x14003fb83  mov     word ptr [rbp+Source1+4], ax
0x14003fb87  movzx   eax, word ptr [rsi+6]
0x14003fb8b  ror     ax, 8
0x14003fb8f  mov     word ptr [rbp+Source1+6], ax
0x14003fb93  mov     rax, [rsi+8]
0x14003fb97  mov     qword ptr [rbp+Source1+8], rax
0x14003fb9b  cmp     [r13+0], edi
0x14003fb9f  jnz     short loc_14003FBFB
0x14003fba1  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fba8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fbaf  jz      loc_14003FF85
0x14003fbb5  mov     ebx, [rsi+10h]
0x14003fbb8  mov     rcx, rsi; Source1
0x14003fbbb  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14003fbc0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fbc7  lea     r9d, [rdi+65h]
0x14003fbcb  mov     [rsp+70h+var_38], ebx
0x14003fbcf  lea     r8d, [rdi+9]
0x14003fbd3  mov     [rsp+70h+var_40], rax
0x14003fbd8  lea     rax, [rbp+Source1]
0x14003fbdc  mov     [rsp+70h+var_48], rax
0x14003fbe1  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003fbe8  mov     rcx, [rcx+40h]
0x14003fbec  mov     [rsp+70h+var_50], rax
0x14003fbf1  call    WPP_RECORDER_SF__guid_sd
0x14003fbf6  jmp     loc_14003FF85
0x14003fbfb  mov     r8, rbx; Length
0x14003fbfe  lea     rdx, MBB_UUID_BASIC_CONNECT; Source2
0x14003fc05  lea     rcx, [rbp+Source1]; Source1
0x14003fc09  call    cs:__imp_RtlCompareMemory
0x14003fc10  nop     dword ptr [rax+rax+00h]
0x14003fc15  cmp     rax, rbx
0x14003fc18  jnz     loc_14003FE80
0x14003fc1e  mov     ebx, [rsi+10h]
0x14003fc21  mov     eax, ebx
0x14003fc23  sub     eax, 2
0x14003fc26  jz      loc_14003FE3E
0x14003fc2c  sub     eax, 7
0x14003fc2f  jz      loc_14003FDFF
0x14003fc35  sub     eax, 1
0x14003fc38  jz      loc_14003FDBD
0x14003fc3e  cmp     eax, 2
0x14003fc41  jz      short loc_14003FC88
0x14003fc43  mov     edi, 0C000000Dh
0x14003fc48  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fc4f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fc56  jz      loc_14003FF85
0x14003fc5c  mov     rcx, rsi; Source1
0x14003fc5f  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14003fc64  mov     r9d, 6Dh ; 'm'
0x14003fc6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fc71  mov     dword ptr [rsp+70h+var_40], ebx
0x14003fc75  mov     [rsp+70h+var_48], rax
0x14003fc7a  mov     rcx, [rcx+40h]
0x14003fc7e  call    WPP_RECORDER_SF_sd
0x14003fc83  jmp     loc_14003FF85
0x14003fc88  mov     ecx, [rsi+14h]
0x14003fc8b  cmp     ecx, 1Ch
0x14003fc8e  jnb     short loc_14003FCD2
0x14003fc90  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fc97  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fc9e  jz      short loc_14003FCC8
0x14003fca0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fca7  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003fcae  mov     r9d, 66h ; 'f'
0x14003fcb4  mov     [rsp+70h+var_50], rax
0x14003fcb9  mov     dl, 2
0x14003fcbb  mov     rcx, [rcx+40h]
0x14003fcbf  lea     r8d, [r9-5Dh]
0x14003fcc3  call    WPP_RECORDER_SF_
0x14003fcc8  mov     edi, 0C000000Dh
0x14003fccd  jmp     loc_14003FF85
0x14003fcd2  mov     r8d, [r12+4]
0x14003fcd7  lea     rax, [rcx+4]
0x14003fcdb  mov     rdx, rcx
0x14003fcde  cmp     rax, r8
0x14003fce1  jbe     short loc_14003FD2B
0x14003fce3  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fcea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fcf1  jz      short loc_14003FCC8
0x14003fcf3  lea     eax, [rcx+4]
0x14003fcf6  mov     dword ptr [rsp+70h+var_40], r8d
0x14003fcfb  mov     dword ptr [rsp+70h+var_48], eax
0x14003fcff  mov     r9d, 67h ; 'g'
0x14003fd05  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fd0c  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003fd13  mov     r8d, 9
0x14003fd19  mov     [rsp+70h+var_50], rax
0x14003fd1e  mov     dl, 2
0x14003fd20  mov     rcx, [rcx+40h]
0x14003fd24  call    WPP_RECORDER_SF_DD
0x14003fd29  jmp     short loc_14003FCC8
0x14003fd2b  mov     ecx, [rsi+18h]
0x14003fd2e  cmp     ecx, 4
0x14003fd31  jz      short loc_14003FD57
0x14003fd33  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fd3a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fd41  jz      short loc_14003FCC8
0x14003fd43  mov     dword ptr [rsp+70h+var_40], 4
0x14003fd4b  mov     r9d, 68h ; 'h'
0x14003fd51  mov     dword ptr [rsp+70h+var_48], ecx
0x14003fd55  jmp     short loc_14003FD05
0x14003fd57  xor     ebx, ebx
0x14003fd59  cmp     dword ptr [rdx+rsi], 1
0x14003fd5d  setnz   bl
0x14003fd60  inc     ebx
0x14003fd62  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fd69  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fd70  jz      short loc_14003FD9E
0x14003fd72  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fd79  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003fd80  mov     r9d, 69h ; 'i'
0x14003fd86  mov     dword ptr [rsp+70h+var_48], ebx
0x14003fd8a  mov     dl, 4
0x14003fd8c  mov     [rsp+70h+var_50], rax
0x14003fd91  mov     rcx, [rcx+40h]
0x14003fd95  lea     r8d, [r9-60h]
0x14003fd99  call    WPP_RECORDER_SF_d
0x14003fd9e  mov     rax, cs:qword_14005F5E8
0x14003fda5  mov     r8d, ebx
0x14003fda8  mov     rdx, [r15+8]
0x14003fdac  mov     rcx, cs:NetDriverGlobals
0x14003fdb3  call    _guard_dispatch_icall
0x14003fdb8  jmp     loc_14003FF85
0x14003fdbd  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fdc4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fdcb  jz      short loc_14003FDF5
0x14003fdcd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fdd4  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003fddb  mov     r9d, 6Bh ; 'k'
0x14003fde1  mov     [rsp+70h+var_50], rax
0x14003fde6  mov     dl, 4
0x14003fde8  mov     rcx, [rcx+40h]
0x14003fdec  lea     r8d, [r9-62h]
0x14003fdf0  call    WPP_RECORDER_SF_
0x14003fdf5  mov     edx, 3
0x14003fdfa  jmp     loc_14003FF7D
0x14003fdff  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fe06  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fe0d  jz      short loc_14003FE37
0x14003fe0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fe16  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003fe1d  mov     r9d, 6Ah ; 'j'
0x14003fe23  mov     [rsp+70h+var_50], rax
0x14003fe28  mov     dl, 4
0x14003fe2a  mov     rcx, [rcx+40h]
0x14003fe2e  lea     r8d, [r9-61h]
0x14003fe32  call    WPP_RECORDER_SF_
0x14003fe37  xor     edx, edx
0x14003fe39  jmp     loc_14003FF7D
0x14003fe3e  lea     rax, WPP_RECORDER_INITIALIZED
0x14003fe45  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fe4c  jz      short loc_14003FE76
0x14003fe4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fe55  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003fe5c  mov     r9d, 6Ch ; 'l'
0x14003fe62  mov     [rsp+70h+var_50], rax
0x14003fe67  mov     dl, 4
0x14003fe69  mov     rcx, [rcx+40h]
0x14003fe6d  lea     r8d, [r9-63h]
0x14003fe71  call    WPP_RECORDER_SF_
0x14003fe76  mov     edx, 4
0x14003fe7b  jmp     loc_14003FF7D
0x14003fe80  mov     r8, rbx; Length
0x14003fe83  lea     rdx, MBB_UUID_SMS; Source2
0x14003fe8a  lea     rcx, [rbp+Source1]; Source1
0x14003fe8e  call    cs:__imp_RtlCompareMemory
0x14003fe95  nop     dword ptr [rax+rax+00h]
0x14003fe9a  cmp     rax, rbx
0x14003fe9d  jnz     short loc_14003FEEF
0x14003fe9f  mov     ebx, [rsi+10h]
0x14003fea2  cmp     ebx, 5
0x14003fea5  jz      short loc_14003FED3
0x14003fea7  mov     edi, 0C000000Dh
0x14003feac  lea     rax, WPP_RECORDER_INITIALIZED
0x14003feb3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003feba  jz      loc_14003FF85
0x14003fec0  mov     rcx, rsi; Source1
0x14003fec3  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14003fec8  mov     r9d, 6Fh ; 'o'
0x14003fece  jmp     loc_14003FC6A
0x14003fed3  lea     rax, WPP_RECORDER_INITIALIZED
0x14003feda  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003fee1  jz      loc_14003FF78
0x14003fee7  mov     r9d, 6Eh ; 'n'
0x14003feed  jmp     short loc_14003FF54
0x14003feef  mov     r8, rbx; Length
0x14003fef2  lea     rdx, MBB_UUID_USSD; Source2
0x14003fef9  lea     rcx, [rbp+Source1]; Source1
0x14003fefd  call    cs:__imp_RtlCompareMemory
0x14003ff04  nop     dword ptr [rax+rax+00h]
0x14003ff09  cmp     rax, rbx
0x14003ff0c  jnz     short loc_14003FF85
0x14003ff0e  mov     ebx, [rsi+10h]
0x14003ff11  cmp     ebx, 1
0x14003ff14  jz      short loc_14003FF3E
0x14003ff16  mov     edi, 0C000000Dh
0x14003ff1b  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ff22  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ff29  jz      short loc_14003FF85
0x14003ff2b  mov     rcx, rsi; Source1
0x14003ff2e  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14003ff33  mov     r9d, 71h ; 'q'
0x14003ff39  jmp     loc_14003FC6A
0x14003ff3e  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ff45  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ff4c  jz      short loc_14003FF78
0x14003ff4e  mov     r9d, 70h ; 'p'
0x14003ff54  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ff5b  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003ff62  mov     r8d, 9
0x14003ff68  mov     [rsp+70h+var_50], rax
0x14003ff6d  mov     dl, 4
0x14003ff6f  mov     rcx, [rcx+40h]
0x14003ff73  call    WPP_RECORDER_SF_
0x14003ff78  mov     edx, 1
0x14003ff7d  mov     rcx, r14
0x14003ff80  call    ?ReportWakeReason@MbxDevice@@QEAAXW4_MBB_WAKE_REASON_TYPE@@@Z; MbxDevice::ReportWakeReason(_MBB_WAKE_REASON_TYPE)
  ... truncated ...
```
