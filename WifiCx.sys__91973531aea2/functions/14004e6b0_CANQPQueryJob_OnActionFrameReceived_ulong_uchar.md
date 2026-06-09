# CANQPQueryJob::OnActionFrameReceived(ulong,uchar *)

- ea: `0x14004e6b0`
- end: `0x14004f034`
- name: `?OnActionFrameReceived@CANQPQueryJob@@AEAAXKPEAE@Z`
- size: `2436`
- prototype: `void __fastcall(enum _WDF_EXECUTION_LEVEL this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004f040`

## callees

- `0x140014b30`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140024004`
- `0x14002bd34`
- `0x14002ed50`
- `0x140040fcc`
- `0x14004d620`
- `0x14004e064`
- `0x14004e6b0`
- `0x140050660`
- `0x140050798`
- `0x1400508d4`
- `0x140050b88`
- `0x140050ec4`
- `0x14005124c`
- `0x140061544`
- `0x1400dfd00`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14004e82f`
- `ntoskrnl!RtlCompareMemory` at `0x14004e82f`

## pseudocode

```c
void __fastcall CANQPQueryJob::OnActionFrameReceived(__int64 this, int a2, unsigned __int8 *a3)
{
  int v4; // esi
  int v6; // eax
  unsigned int v7; // r15d
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  char v16; // r14
  int v17; // r11d
  unsigned __int8 *v18; // r10
  char v19; // al
  unsigned __int16 v20; // r13
  unsigned __int16 v21; // r12
  char v22; // cl
  unsigned __int8 v23; // dl
  unsigned int v24; // esi
  int v25; // edi
  unsigned int v26; // edx
  EventQueue *v27; // rcx
  __int64 v28; // rdx
  int v29; // r8d
  unsigned int v30; // r14d
  unsigned __int64 CurrentTime; // rax
  int v32; // edx
  int v33; // r8d
  unsigned int v34; // esi
  unsigned int v35; // ecx
  unsigned int v36; // edx
  EventQueue *v37; // rcx
  int v38; // edx
  int v39; // r8d
  int v40; // r9d
  int v41; // [rsp+20h] [rbp-89h]
  int v42; // [rsp+20h] [rbp-89h]
  enum _WDF_EXECUTION_LEVEL v43; // [rsp+28h] [rbp-81h]
  struct TimerRegistrationContext **v44; // [rsp+38h] [rbp-71h]
  bool v45; // [rsp+90h] [rbp-19h]
  unsigned __int8 v46; // [rsp+91h] [rbp-18h]
  unsigned __int8 *v47; // [rsp+98h] [rbp-11h]
  int Source1; // [rsp+A0h] [rbp-9h] BYREF
  __int16 v49; // [rsp+A4h] [rbp-5h]
  __int64 v50; // [rsp+A8h] [rbp-1h]
  unsigned int v51; // [rsp+B0h] [rbp+7h] BYREF
  unsigned __int8 *v52; // [rsp+B8h] [rbp+Fh]
  char v53; // [rsp+C0h] [rbp+17h]

  v50 = 0;
  v51 = 0;
  v4 = a2;
  v52 = 0;
  v53 = 0;
  Source1 = 0;
  v49 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      67,
      (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
      this,
      *(_DWORD *)(this + 16));
  }
  v6 = *(_DWORD *)(this + 668);
  if ( v6 == 3 )
  {
    v10 = ParseWdiIndicationActionFrameReceivedFromIhv(
            (unsigned int)(v4 - 48),
            a3 + 48,
            *(_QWORD *)(this + 536) + 5384LL,
            &Source1);
    v7 = v10;
    if ( v10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          69,
          (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
          this,
          *(_DWORD *)(this + 16),
          v10);
      }
      goto LABEL_11;
    }
    if ( RtlCompareMemory(&Source1, (const void *)(this + 612), 6u) != 6 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_92;
      WPP_RECORDER_SF_qDD_MAC__MAC_(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        v15,
        v41,
        this,
        *(_DWORD *)(this + 16),
        0,
        this + 612,
        (__int64)&Source1);
      goto LABEL_88;
    }
    v16 = v51;
    v17 = 13;
    if ( v51 < 0xD )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_92;
      WPP_RECORDER_SF_qDDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        71,
        (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
        this,
        *(_DWORD *)(this + 16),
        0,
        v51,
        13);
      goto LABEL_88;
    }
    v18 = v52;
    v19 = v52[1];
    if ( v19 == 11 )
    {
      LOBYTE(v15) = v52[10];
      v46 = 0;
      v23 = v52[7];
      v20 = v52[5] + (v52[6] << 8);
      v21 = v52[11] + (v52[12] << 8);
      v47 = v52 + 13;
      v24 = v52[3] + (v52[4] << 8);
      v22 = v20 != 0;
      v45 = v20 != 0;
    }
    else
    {
      if ( v19 != 13 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_92;
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          v14,
          73,
          (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
          this,
          *(_DWORD *)(this + 16),
          0,
          v19);
        goto LABEL_88;
      }
      v17 = 14;
      if ( v51 < 0xE )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            v14,
            72,
            (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
            this,
            *(_DWORD *)(this + 16),
            v4,
            14);
        }
        goto LABEL_11;
      }
      v20 = v52[6] + (v52[7] << 8);
      v21 = v52[12] + (v52[13] << 8);
      v46 = v52[5] & 0x7F;
      if ( (v52[5] & 0x80u) != 0 || (v45 = 0, v22 = 0, v20) )
      {
        v22 = 1;
        v45 = 1;
      }
      v23 = v52[8];
      LOBYTE(v15) = v52[11];
      v24 = v52[3] + (v52[4] << 8);
      v47 = v52 + 14;
    }
    v25 = 4;
    if ( *v52 != 4 || v52[2] != *(_BYTE *)(this + 5456) || v23 != 108 || (_BYTE)v15 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_92;
      WPP_RECORDER_SF_qDDddddddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        *(unsigned __int8 *)(this + 5456),
        v52[2],
        *v52,
        v41,
        this,
        *(_DWORD *)(this + 16),
        0,
        v52[1],
        *v52);
      goto LABEL_88;
    }
    if ( !v22 && !v21 || v51 < v17 + (unsigned int)v21 )
    {
      *(_DWORD *)(this + 652) = 5;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_92;
      WPP_RECORDER_SF_qDdDddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v18[1],
        0,
        v15,
        v41,
        this,
        *(_DWORD *)(this + 16),
        v18[1],
        v22,
        v16,
        v17,
        v21);
      goto LABEL_88;
    }
    v26 = *(_DWORD *)(this + 664);
    if ( v26 )
    {
      v27 = *(EventQueue **)(this + 32);
      *(_BYTE *)(this + 694) = 0;
      EventQueue::DeregisterTimeoutCallback(v27, v26);
      *(_DWORD *)(this + 664) = 0;
    }
    if ( v24 > 0x3F )
    {
      switch ( v24 )
      {
        case '@':
          goto LABEL_82;
        case 'A':
          goto LABEL_47;
        case 'C':
        case 'D':
LABEL_82:
          v25 = 7;
          goto LABEL_83;
      }
      if ( v24 != 79 )
      {
LABEL_80:
        v25 = 1;
        goto LABEL_83;
      }
    }
    else if ( v24 != 63 )
    {
      if ( !v24 )
      {
        v7 = CANQPQueryJob::CacheANQPFragment((CANQPQueryJob *)this, v46, v21, v47);
        if ( !v7 )
        {
          if ( v20 <= 1u )
          {
            if ( v45 )
            {
              *(_DWORD *)(this + 668) = 4;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v28) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v28,
                  v29,
                  82,
                  (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
                  this,
                  *(_DWORD *)(this + 16));
              }
            }
            else
            {
              *(_DWORD *)(this + 668) = 6;
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v28) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v28,
                  v29,
                  83,
                  (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
                  this,
                  *(_DWORD *)(this + 16));
              }
              CANQPQueryJob::HandleFinalANQPResponseReceived((CANQPQueryJob *)this, v28, v29);
            }
            goto LABEL_11;
          }
          v30 = (v20 << 10) / 0x3E8u;
          CurrentTime = CSystem::get_CurrentTime();
          if ( CurrentTime <= *(_QWORD *)(this + 640) )
          {
            v35 = *(_DWORD *)(this + 640) - CurrentTime;
            v32 = (3518437209u * (unsigned __int64)v35) >> 32;
            v34 = v35 / 0x2710;
          }
          else
          {
            v34 = 0;
          }
          if ( v34 < v30 )
          {
            if ( v34 < 0x3E8 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v32) = 2;
                WPP_RECORDER_SF_qDddd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v32,
                  v33,
                  78,
                  (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
                  this,
                  *(_DWORD *)(this + 16),
                  v20,
                  v30,
                  v34);
              }
              *(_DWORD *)(this + 652) = 2;
              v7 = -1073741823;
              *(_DWORD *)(this + 596) = -2147478641;
              goto LABEL_11;
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v32) = 4;
              WPP_RECORDER_SF_qDddd(
                WPP_GLOBAL_Control->DeviceExtension,
                v32,
                v33,
                79,
                (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
                this,
                *(_DWORD *)(this + 16),
                v30,
                v34 + 24,
                v34);
            }
            v30 = v34 - 1000;
          }
          v36 = *(_DWORD *)(this + 16);
          v37 = *(EventQueue **)(this + 32);
          *(_DWORD *)(this + 668) = 5;
          *(_BYTE *)(this + 693) = 1;
          *(_WORD *)(this + 690) = v30;
          v7 = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
                 v37,
                 v36,
                 (struct ITimerCallback *)(this + 584),
                 v30,
                 (void *)(this + 5532),
                 v43,
                 0,
                 0,
                 (unsigned int *)(this + 5532));
          if ( v7 )
          {
            *(_BYTE *)(this + 693) = 0;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v38) = 2;
              LODWORD(v44) = v7;
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                v38,
                v39,
                80,
                (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
                this,
                *(_DWORD *)(this + 16),
                v44);
            }
            *(_DWORD *)(this + 652) = 3;
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_qDqdd(
              WPP_GLOBAL_Control->DeviceExtension,
              v38,
              v39,
              v40,
              v42,
              this,
              *(_DWORD *)(this + 16),
              this - 100,
              v20,
              v30);
          }
          goto LABEL_11;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v28) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v28,
            v29,
            77,
            (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
            this,
            *(_DWORD *)(this + 16),
            v7);
        }
LABEL_11:
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)this + 16LL))(this, v7, this);
        goto LABEL_88;
      }
      if ( v24 == 59 )
      {
LABEL_83:
        *(_DWORD *)(this + 652) = v25;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qDDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v26,
            0,
            76,
            (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
            this,
            *(_DWORD *)(this + 16),
            0,
            v24,
            v25);
        *(_DWORD *)(this + 668) = 6;
        goto LABEL_11;
      }
      if ( v24 != 60 )
      {
        if ( v24 - 61 <= 1 )
        {
LABEL_47:
          v25 = 6;
          goto LABEL_83;
        }
        goto LABEL_80;
      }
    }
    v25 = 5;
    goto LABEL_83;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_92;
  LOBYTE(a2) = 2;
  v7 = 0;
  WPP_RECORDER_SF_qDdd(
    WPP_GLOBAL_Control->DeviceExtension,
    a2,
    (_DWORD)a3,
    68,
    (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
    this,
    *(_DWORD *)(this + 16),
    0,
    v6);
LABEL_88:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v8) = 5;
    LODWORD(v44) = v7;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v9,
      84,
      (__int64)WPP_42f27955ace430a2861f4465eb9690f7_Traceguids,
      this,
      *(_DWORD *)(this + 16),
      v44);
  }
LABEL_92:
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&v51);
}

```

## disassembly

```asm
0x14004e6b0  mov     [rsp-8+arg_18], rbx
0x14004e6b5  push    rbp
0x14004e6b6  push    rsi
0x14004e6b7  push    rdi
0x14004e6b8  push    r12
0x14004e6ba  push    r13
0x14004e6bc  push    r14
0x14004e6be  push    r15
0x14004e6c0  lea     rbp, [rsp-27h]
0x14004e6c5  sub     rsp, 0D0h
0x14004e6cc  mov     rax, cs:__security_cookie
0x14004e6d3  xor     rax, rsp
0x14004e6d6  mov     [rbp+57h+var_38], rax
0x14004e6da  xor     eax, eax
0x14004e6dc  mov     rdi, r8
0x14004e6df  xor     r12d, r12d
0x14004e6e2  mov     [rbp+57h+var_58], rax
0x14004e6e6  mov     [rbp+57h+var_50], r12d
0x14004e6ea  mov     esi, edx
0x14004e6ec  mov     [rbp+57h+var_48], r12
0x14004e6f0  mov     rbx, rcx
0x14004e6f3  mov     [rbp+57h+var_40], r12b
0x14004e6f7  mov     [rbp+57h+Source1], eax
0x14004e6fa  mov     [rbp+57h+var_5C], ax
0x14004e6fe  lea     r13, WPP_RECORDER_INITIALIZED
0x14004e705  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004e70c  lea     r14, WPP_42f27955ace430a2861f4465eb9690f7_Traceguids
0x14004e713  jz      short loc_14004E74B
0x14004e715  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e71c  cmp     byte ptr [rcx+29h], 5
0x14004e720  jnb     short loc_14004E729
0x14004e722  cmp     [rcx+48h], r12w
0x14004e727  jz      short loc_14004E74B
0x14004e729  mov     eax, [rbx+10h]
0x14004e72c  mov     r9d, 43h ; 'C'
0x14004e732  mov     rcx, [rcx+40h]
0x14004e736  mov     dl, 5
0x14004e738  mov     dword ptr [rsp+100h+var_D0], eax
0x14004e73c  mov     qword ptr [rsp+100h+var_D8], rbx
0x14004e741  mov     [rsp+100h+var_E0], r14
0x14004e746  call    WPP_RECORDER_SF_qD
0x14004e74b  mov     eax, [rbx+29Ch]
0x14004e751  cmp     eax, 3
0x14004e754  jz      short loc_14004E79F
0x14004e756  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004e75d  jz      loc_14004F003
0x14004e763  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e76a  mov     r9d, 44h ; 'D'
0x14004e770  mov     dword ptr [rsp+100h+var_C0], eax
0x14004e774  mov     dl, 2
0x14004e776  mov     eax, [rbx+10h]
0x14004e779  mov     r15d, r12d
0x14004e77c  mov     dword ptr [rsp+100h+var_C8], r12d
0x14004e781  mov     rcx, [rcx+40h]
0x14004e785  mov     dword ptr [rsp+100h+var_D0], eax
0x14004e789  mov     qword ptr [rsp+100h+var_D8], rbx
0x14004e78e  mov     [rsp+100h+var_E0], r14
0x14004e793  call    WPP_RECORDER_SF_qDdd
0x14004e798  xor     edi, edi
0x14004e79a  jmp     loc_14004EFB2
0x14004e79f  mov     r8, [rbx+218h]
0x14004e7a6  lea     rdx, [rdi+30h]
0x14004e7aa  add     r8, 1508h
0x14004e7b1  lea     ecx, [rsi-30h]
0x14004e7b4  lea     r9, [rbp+57h+Source1]
0x14004e7b8  call    ParseWdiIndicationActionFrameReceivedFromIhv
0x14004e7bd  mov     r15d, eax
0x14004e7c0  test    eax, eax
0x14004e7c2  jz      short loc_14004E81B
0x14004e7c4  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004e7cb  jz      short loc_14004E7FA
0x14004e7cd  mov     ecx, [rbx+10h]
0x14004e7d0  mov     r9d, 45h ; 'E'
0x14004e7d6  mov     dword ptr [rsp+100h+var_C8], eax
0x14004e7da  mov     dl, 2
0x14004e7dc  mov     dword ptr [rsp+100h+var_D0], ecx
0x14004e7e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e7e7  mov     qword ptr [rsp+100h+var_D8], rbx
0x14004e7ec  mov     [rsp+100h+var_E0], r14
0x14004e7f1  mov     rcx, [rcx+40h]
0x14004e7f5  call    WPP_RECORDER_SF_qDD
0x14004e7fa  lea     rsi, WPP_42f27955ace430a2861f4465eb9690f7_Traceguids
0x14004e801  mov     rax, [rbx]
0x14004e804  mov     r8, rbx
0x14004e807  mov     edx, r15d
0x14004e80a  mov     rcx, rbx
0x14004e80d  mov     rax, [rax+10h]
0x14004e811  call    _guard_dispatch_icall
0x14004e816  jmp     loc_14004E8D9
0x14004e81b  lea     rdi, [rbx+264h]
0x14004e822  mov     r8d, 6; Length
0x14004e828  mov     rdx, rdi; Source2
0x14004e82b  lea     rcx, [rbp+57h+Source1]; Source1
0x14004e82f  call    cs:__imp_RtlCompareMemory
0x14004e836  nop     dword ptr [rax+rax+00h]
0x14004e83b  cmp     rax, 6
0x14004e83f  jz      short loc_14004E882
0x14004e841  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004e848  jz      loc_14004F003
0x14004e84e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e855  lea     rax, [rbp+57h+Source1]
0x14004e859  mov     [rsp+100h+var_B8], rax
0x14004e85e  mov     eax, [rbx+10h]
0x14004e861  mov     [rsp+100h+var_C0], rdi
0x14004e866  mov     rcx, [rcx+40h]
0x14004e86a  mov     dword ptr [rsp+100h+var_C8], r12d
0x14004e86f  mov     dword ptr [rsp+100h+var_D0], eax
0x14004e873  mov     qword ptr [rsp+100h+var_D8], rbx
0x14004e878  call    WPP_RECORDER_SF_qDD_MAC__MAC_
0x14004e87d  jmp     loc_14004E798
0x14004e882  mov     r14d, [rbp+57h+var_50]
0x14004e886  mov     r11d, 0Dh
0x14004e88c  cmp     r14d, r11d
0x14004e88f  jnb     short loc_14004E8E0
0x14004e891  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004e898  jz      loc_14004F003
0x14004e89e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e8a5  lea     rsi, WPP_42f27955ace430a2861f4465eb9690f7_Traceguids
0x14004e8ac  mov     eax, [rbx+10h]
0x14004e8af  lea     r9d, [r11+3Ah]
0x14004e8b3  mov     dword ptr [rsp+100h+var_B8], r11d
0x14004e8b8  mov     dword ptr [rsp+100h+var_C0], r14d
0x14004e8bd  mov     rcx, [rcx+40h]
0x14004e8c1  mov     dword ptr [rsp+100h+var_C8], r12d
0x14004e8c6  mov     dword ptr [rsp+100h+var_D0], eax
0x14004e8ca  mov     qword ptr [rsp+100h+var_D8], rbx
0x14004e8cf  mov     [rsp+100h+var_E0], rsi
0x14004e8d4  call    WPP_RECORDER_SF_qDDdd
0x14004e8d9  xor     edi, edi
0x14004e8db  jmp     loc_14004EFB9
0x14004e8e0  mov     r10, [rbp+57h+var_48]
0x14004e8e4  movzx   eax, byte ptr [r10+1]
0x14004e8e9  cmp     al, 0Bh
0x14004e8eb  jz      loc_14004EA01
0x14004e8f1  cmp     al, r11b
0x14004e8f4  jz      short loc_14004E93E
0x14004e8f6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004e8fd  jz      loc_14004F003
0x14004e903  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e90a  lea     rsi, WPP_42f27955ace430a2861f4465eb9690f7_Traceguids
0x14004e911  mov     dword ptr [rsp+100h+var_C0], eax
0x14004e915  mov     r9d, 49h ; 'I'
0x14004e91b  mov     eax, [rbx+10h]
0x14004e91e  mov     dl, 2
0x14004e920  mov     dword ptr [rsp+100h+var_C8], r12d
0x14004e925  mov     rcx, [rcx+40h]
0x14004e929  mov     dword ptr [rsp+100h+var_D0], eax
0x14004e92d  mov     qword ptr [rsp+100h+var_D8], rbx
0x14004e932  mov     [rsp+100h+var_E0], rsi
0x14004e937  call    WPP_RECORDER_SF_qDdd
0x14004e93c  jmp     short loc_14004E8D9
0x14004e93e  mov     r11d, 0Eh
0x14004e944  cmp     r14d, r11d
0x14004e947  jnb     short loc_14004E992
0x14004e949  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004e950  jz      loc_14004E7FA
0x14004e956  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e95d  lea     r9d, [r11+3Ah]
0x14004e961  mov     eax, [rbx+10h]
0x14004e964  mov     dl, 2
0x14004e966  mov     dword ptr [rsp+100h+var_C0], r11d
0x14004e96b  mov     dword ptr [rsp+100h+var_C8], esi
0x14004e96f  lea     rsi, WPP_42f27955ace430a2861f4465eb9690f7_Traceguids
0x14004e976  mov     rcx, [rcx+40h]
0x14004e97a  mov     dword ptr [rsp+100h+var_D0], eax
0x14004e97e  mov     qword ptr [rsp+100h+var_D8], rbx
0x14004e983  mov     [rsp+100h+var_E0], rsi
0x14004e988  call    WPP_RECORDER_SF_qDdd
0x14004e98d  jmp     loc_14004E801
0x14004e992  movzx   eax, byte ptr [r10+6]
0x14004e997  mov     edx, 100h
0x14004e99c  movzx   r13d, byte ptr [r10+7]
0x14004e9a1  movzx   r12d, byte ptr [r10+0Dh]
0x14004e9a6  movzx   r8d, byte ptr [r10+3]
0x14004e9ab  movzx   edi, byte ptr [r10+4]
0x14004e9b0  imul    r13d, edx
0x14004e9b4  imul    r12d, edx
0x14004e9b8  xor     edx, edx
0x14004e9ba  add     r13w, ax
0x14004e9be  movzx   eax, byte ptr [r10+0Ch]
0x14004e9c3  add     r12w, ax
0x14004e9c7  mov     al, [r10+5]
0x14004e9cb  mov     cl, al
0x14004e9cd  and     cl, 7Fh
0x14004e9d0  mov     [rbp+57h+var_6F], cl
0x14004e9d3  test    al, al
0x14004e9d5  js      short loc_14004E9E2
0x14004e9d7  mov     [rbp+57h+var_70], dl
0x14004e9da  mov     cl, dl
0x14004e9dc  test    r13w, r13w
0x14004e9e0  jz      short loc_14004E9E7
0x14004e9e2  mov     cl, 1
0x14004e9e4  mov     [rbp+57h+var_70], cl
0x14004e9e7  mov     dl, [r10+8]
0x14004e9eb  lea     rax, [r10+0Eh]
0x14004e9ef  mov     r9b, [r10+0Bh]
0x14004e9f3  mov     esi, edi
0x14004e9f5  shl     esi, 8
0x14004e9f8  add     esi, r8d
0x14004e9fb  mov     [rbp+57h+var_68], rax
0x14004e9ff  jmp     short loc_14004EA5B
0x14004ea01  movzx   eax, byte ptr [r10+5]
0x14004ea06  mov     edx, 100h
0x14004ea0b  movzx   r8d, byte ptr [r10+6]
0x14004ea10  movzx   esi, byte ptr [r10+4]
0x14004ea15  mov     r9b, [r10+0Ah]
0x14004ea19  imul    r8d, edx
0x14004ea1d  mov     [rbp+57h+var_6F], r12b
0x14004ea21  movzx   r12d, byte ptr [r10+0Ch]
0x14004ea26  imul    r12d, edx
0x14004ea2a  mov     dl, [r10+7]
0x14004ea2e  add     r8w, ax
0x14004ea32  shl     esi, 8
0x14004ea35  movzx   eax, byte ptr [r10+0Bh]
0x14004ea3a  movzx   r13d, r8w
0x14004ea3e  add     r12w, ax
0x14004ea42  lea     rax, [r10+0Dh]
0x14004ea46  mov     [rbp+57h+var_68], rax
0x14004ea4a  movzx   eax, byte ptr [r10+3]
0x14004ea4f  add     esi, eax
0x14004ea51  test    r8w, r8w
0x14004ea55  setnz   cl
0x14004ea58  mov     [rbp+57h+var_70], cl
0x14004ea5b  mov     al, [r10]
0x14004ea5e  mov     edi, 4
0x14004ea63  mov     [rbp+57h+var_6E], al
0x14004ea66  cmp     al, dil
0x14004ea69  jnz     loc_14004EF44
0x14004ea6f  mov     al, [rbx+1550h]
0x14004ea75  cmp     [r10+2], al
0x14004ea79  jnz     loc_14004EF44
0x14004ea7f  cmp     dl, 6Ch ; 'l'
0x14004ea82  jnz     loc_14004EF44
0x14004ea88  xor     r8d, r8d
0x14004ea8b  test    r9b, r9b
0x14004ea8e  jnz     loc_14004EF44
0x14004ea94  test    cl, cl
0x14004ea96  jnz     short loc_14004EA9E
0x14004ea98  cmp     r8w, r12w
0x14004ea9c  jz      short loc_14004EAAA
0x14004ea9e  movzx   eax, r12w
0x14004eaa2  add     eax, r11d
0x14004eaa5  cmp     r14d, eax
0x14004eaa8  jnb     short loc_14004EB0B
0x14004eaaa  mov     dword ptr [rbx+28Ch], 5
0x14004eab4  lea     rax, WPP_RECORDER_INITIALIZED
0x14004eabb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004eac2  jz      loc_14004F003
0x14004eac8  movzx   edx, byte ptr [r10+1]
0x14004eacd  movzx   ecx, cl
0x14004ead0  movzx   eax, r12w
0x14004ead4  mov     [rsp+100h+var_A8], eax
0x14004ead8  mov     eax, [rbx+10h]
0x14004eadb  mov     [rsp+100h+var_B0], r11d
0x14004eae0  mov     dword ptr [rsp+100h+var_B8], r14d
0x14004eae5  mov     dword ptr [rsp+100h+var_C0], ecx
0x14004eae9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eaf0  mov     dword ptr [rsp+100h+var_C8], edx
0x14004eaf4  mov     dword ptr [rsp+100h+var_D0], eax
0x14004eaf8  mov     qword ptr [rsp+100h+var_D8], rbx
0x14004eafd  mov     rcx, [rcx+40h]
0x14004eb01  call    WPP_RECORDER_SF_qDdDddd
0x14004eb06  jmp     loc_14004E798
0x14004eb0b  mov     edx, [rbx+298h]; unsigned int
0x14004eb11  test    edx, edx
0x14004eb13  jz      short loc_14004EB2F
0x14004eb15  mov     rcx, [rbx+20h]; this
0x14004eb19  mov     [rbx+2B6h], r8b
0x14004eb20  call    ?DeregisterTimeoutCallback@EventQueue@@QEAAHI@Z; EventQueue::DeregisterTimeoutCallback(uint)
0x14004eb25  xor     r8d, r8d
0x14004eb28  mov     [rbx+298h], r8d
0x14004eb2f  cmp     esi, 3Fh ; '?'
0x14004eb32  ja      loc_14004EEA9
0x14004eb38  jz      loc_14004EECF
0x14004eb3e  mov     ecx, esi
0x14004eb40  test    esi, esi
0x14004eb42  jz      short loc_14004EB6E
0x14004eb44  sub     ecx, 3Bh ; ';'
0x14004eb47  jz      loc_14004EEDB
0x14004eb4d  sub     ecx, 1
0x14004eb50  jz      loc_14004EECF
0x14004eb56  sub     ecx, 1
0x14004eb59  jz      short loc_14004EB64
0x14004eb5b  cmp     ecx, 1
0x14004eb5e  jnz     loc_14004EEC8
0x14004eb64  mov     edi, 6
0x14004eb69  jmp     loc_14004EEDB
0x14004eb6e  mov     r9, [rbp+57h+var_68]; unsigned __int8 *
0x14004eb72  movzx   r8d, r12w; unsigned __int16
0x14004eb76  mov     dl, [rbp+57h+var_6F]; unsigned __int8
0x14004eb79  mov     rcx, rbx; this
0x14004eb7c  call    ?CacheANQPFragment@CANQPQueryJob@@AEAAHEGPEAE@Z; CANQPQueryJob::CacheANQPFragment(uchar,ushort,uchar *)
0x14004eb81  xor     r12d, r12d
0x14004eb84  mov     r15d, eax
0x14004eb87  test    eax, eax
0x14004eb89  jz      short loc_14004EBD8
0x14004eb8b  lea     rax, WPP_RECORDER_INITIALIZED
0x14004eb92  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004eb99  jz      loc_14004E7FA
0x14004eb9f  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
