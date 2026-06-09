# CANQPQueryJob::OnActionFrameReceived(ulong,uchar *)

- ea: `0x140098d10`
- end: `0x1400996b5`
- name: `?OnActionFrameReceived@CANQPQueryJob@@AEAAXKPEAE@Z`
- size: `2469`
- prototype: `void __fastcall(__int64 this, int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400996c0`

## callees

- `0x1400122e0`
- `0x14001a808`
- `0x140023cf0`
- `0x140025d38`
- `0x1400297a0`
- `0x14002aa28`
- `0x14004ff88`
- `0x140061328`
- `0x14007b02c`
- `0x14008d840`
- `0x1400986a8`
- `0x140098a08`
- `0x140098d10`
- `0x140099cf8`
- `0x140099e34`
- `0x14009a0e8`
- `0x14009a328`
- `0x1400da4f0`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140098e8f`
- `ntoskrnl!RtlCompareMemory` at `0x140098e8f`

## pseudocode

```c
void __fastcall CANQPQueryJob::OnActionFrameReceived(__int64 this, int a2, unsigned __int8 *a3)
{
  int v4; // esi
  int v6; // eax
  unsigned int v7; // r14d
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  char v16; // r15
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
  int v28; // edx
  int v29; // r8d
  unsigned int v30; // ecx
  int v31; // edx
  unsigned int v32; // r15d
  unsigned int v33; // esi
  unsigned int v34; // ecx
  unsigned int v35; // edx
  EventQueue *v36; // rcx
  int v37; // edx
  int v38; // r8d
  int v39; // [rsp+20h] [rbp-89h]
  enum _WDF_EXECUTION_LEVEL v40; // [rsp+28h] [rbp-81h]
  bool v41; // [rsp+90h] [rbp-19h]
  unsigned __int8 v42; // [rsp+91h] [rbp-18h]
  unsigned __int8 *v43; // [rsp+98h] [rbp-11h]
  int Source1; // [rsp+A0h] [rbp-9h] BYREF
  __int16 v45; // [rsp+A4h] [rbp-5h]
  __int64 v46; // [rsp+A8h] [rbp-1h]
  unsigned int v47; // [rsp+B0h] [rbp+7h] BYREF
  unsigned __int8 *v48; // [rsp+B8h] [rbp+Fh]
  char v49; // [rsp+C0h] [rbp+17h]

  v46 = 0;
  v47 = 0;
  v4 = a2;
  v48 = 0;
  v49 = 0;
  Source1 = 0;
  v45 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      66,
      (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
      this,
      *(_DWORD *)(this + 16));
  }
  v6 = *(_DWORD *)(this + 644);
  if ( v6 == 3 )
  {
    v10 = ParseWdiIndicationActionFrameReceivedFromIhv(
            (unsigned int)(v4 - 48),
            a3 + 48,
            *(_QWORD *)(this + 512) + 16376LL,
            &Source1);
    v7 = v10;
    if ( v10 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          68,
          (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
          this,
          *(_DWORD *)(this + 16),
          v10);
      }
      goto LABEL_11;
    }
    if ( RtlCompareMemory(&Source1, (const void *)(this + 588), 6u) != 6 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_92;
      WPP_RECORDER_SF_qDD_MAC__MAC_(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        v15,
        v39,
        this,
        *(_DWORD *)(this + 16),
        0,
        this + 588,
        (__int64)&Source1);
      goto LABEL_88;
    }
    v16 = v47;
    v17 = 13;
    if ( v47 < 0xD )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_92;
      WPP_RECORDER_SF_qDDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        70,
        (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
        this,
        *(_DWORD *)(this + 16),
        0,
        v47,
        13);
      goto LABEL_88;
    }
    v18 = v48;
    v19 = v48[1];
    if ( v19 == 11 )
    {
      LOBYTE(v15) = v48[10];
      v42 = 0;
      v23 = v48[7];
      v20 = v48[5] + (v48[6] << 8);
      v21 = v48[11] + (v48[12] << 8);
      v43 = v48 + 13;
      v24 = v48[3] + (v48[4] << 8);
      v22 = v20 != 0;
      v41 = v20 != 0;
    }
    else
    {
      if ( v19 != 13 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_92;
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_qDDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          v14,
          72,
          (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
          this,
          *(_DWORD *)(this + 16),
          0,
          v19);
        goto LABEL_88;
      }
      v17 = 14;
      if ( v47 < 0xE )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            v14,
            71,
            (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
            this,
            *(_DWORD *)(this + 16),
            v4,
            14);
        }
        goto LABEL_11;
      }
      v20 = v48[6] + (v48[7] << 8);
      v21 = v48[12] + (v48[13] << 8);
      v42 = v48[5] & 0x7F;
      if ( (v48[5] & 0x80u) != 0 || (v41 = 0, v22 = 0, v20) )
      {
        v22 = 1;
        v41 = 1;
      }
      v23 = v48[8];
      LOBYTE(v15) = v48[11];
      v24 = v48[3] + (v48[4] << 8);
      v43 = v48 + 14;
    }
    v25 = 4;
    if ( *v48 != 4 || v48[2] != *(_BYTE *)(this + 5136) || v23 != 108 || (_BYTE)v15 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_92;
      WPP_RECORDER_SF_qDDddddddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        *(unsigned __int8 *)(this + 5136),
        v48[2],
        *v48,
        v39,
        this,
        *(_DWORD *)(this + 16),
        0,
        v48[1],
        *v48);
      goto LABEL_88;
    }
    if ( !v22 && !v21 || v47 < v17 + (unsigned int)v21 )
    {
      *(_DWORD *)(this + 628) = 5;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_92;
      WPP_RECORDER_SF_qDdDddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v18[1],
        0,
        v15,
        v39,
        this,
        *(_DWORD *)(this + 16),
        v18[1],
        v22,
        v16,
        v17,
        v21);
      goto LABEL_88;
    }
    v26 = *(_DWORD *)(this + 640);
    if ( v26 )
    {
      v27 = *(EventQueue **)(this + 32);
      *(_BYTE *)(this + 670) = 0;
      EventQueue::DeregisterTimeoutCallback(v27, v26);
      *(_DWORD *)(this + 640) = 0;
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
        v7 = CANQPQueryJob::CacheANQPFragment((CANQPQueryJob *)this, v42, v21, v43);
        if ( !v7 )
        {
          if ( v20 <= 1u )
          {
            if ( v41 )
            {
              *(_DWORD *)(this + 644) = 4;
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v28) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v28,
                  v29,
                  81,
                  (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
                  this,
                  *(_DWORD *)(this + 16));
              }
            }
            else
            {
              *(_DWORD *)(this + 644) = 6;
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v28) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v28,
                  v29,
                  82,
                  (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
                  this,
                  *(_DWORD *)(this + 16));
              }
              CANQPQueryJob::HandleFinalANQPResponseReceived((CANQPQueryJob *)this);
            }
            goto LABEL_11;
          }
          v30 = v20 << 10;
          v31 = (274877907 * (unsigned __int64)v30) >> 32;
          v32 = v30 / 0x3E8;
          if ( MEMORY[0xFFFFF78000000014] <= *(_QWORD *)(this + 616) )
          {
            v34 = *(_DWORD *)(this + 616) - MEMORY[0xFFFFF78000000014];
            v31 = (3518437209u * (unsigned __int64)v34) >> 32;
            v33 = v34 / 0x2710;
          }
          else
          {
            v33 = 0;
          }
          if ( v33 < v32 )
          {
            if ( v33 < 0x3E8 )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v31) = 2;
                WPP_RECORDER_SF_qDddd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v31,
                  v20,
                  77,
                  (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
                  this,
                  *(_DWORD *)(this + 16),
                  v20,
                  v32,
                  v33);
              }
              *(_DWORD *)(this + 628) = 2;
              v7 = -1073741823;
              *(_DWORD *)(this + 572) = -2147478641;
              goto LABEL_11;
            }
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v31) = 4;
              WPP_RECORDER_SF_qDddd(
                WPP_GLOBAL_Control->DeviceExtension,
                v31,
                v20,
                78,
                (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
                this,
                *(_DWORD *)(this + 16),
                v32,
                v33 + 24,
                v33);
            }
            v32 = v33 - 1000;
          }
          v35 = *(_DWORD *)(this + 16);
          v36 = *(EventQueue **)(this + 32);
          *(_BYTE *)(this + 669) = 1;
          *(_DWORD *)(this + 644) = 5;
          *(_WORD *)(this + 666) = v32;
          v7 = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
                 v36,
                 v35,
                 (struct ITimerCallback *)(this + 560),
                 v32,
                 (void *)(this + 5212),
                 v40,
                 0,
                 0,
                 (unsigned int *)(this + 5212));
          if ( v7 )
          {
            *(_BYTE *)(this + 669) = 0;
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v37) = 2;
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                v37,
                v38,
                79,
                (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
                this,
                *(_DWORD *)(this + 16),
                v7);
            }
            *(_DWORD *)(this + 628) = 3;
          }
          else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_qDqdd(
              WPP_GLOBAL_Control->DeviceExtension,
              v37,
              v38,
              80,
              (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
              this,
              *(_DWORD *)(this + 16),
              this + 92,
              v20,
              v32);
          }
          goto LABEL_11;
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v28) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v28,
            v29,
            76,
            (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
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
        *(_DWORD *)(this + 628) = v25;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qDDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v26,
            0,
            75,
            (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
            this,
            *(_DWORD *)(this + 16),
            0,
            v24,
            v25);
        *(_DWORD *)(this + 644) = 6;
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
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    goto LABEL_92;
  LOBYTE(a2) = 2;
  LOBYTE(v7) = 0;
  WPP_RECORDER_SF_qDDd(
    WPP_GLOBAL_Control->DeviceExtension,
    a2,
    (_DWORD)a3,
    67,
    (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
    this,
    *(_DWORD *)(this + 16),
    0,
    v6);
LABEL_88:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v9,
      83,
      (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
      this,
      *(_DWORD *)(this + 16),
      v7);
  }
LABEL_92:
  ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(&v47);
}

```

## disassembly

```asm
0x140098d10  mov     [rsp-8+arg_18], rbx
0x140098d15  push    rbp
0x140098d16  push    rsi
0x140098d17  push    rdi
0x140098d18  push    r12
0x140098d1a  push    r13
0x140098d1c  push    r14
0x140098d1e  push    r15
0x140098d20  lea     rbp, [rsp-27h]
0x140098d25  sub     rsp, 0D0h
0x140098d2c  mov     rax, cs:__security_cookie
0x140098d33  xor     rax, rsp
0x140098d36  mov     [rbp+57h+var_38], rax
0x140098d3a  xor     eax, eax
0x140098d3c  mov     rdi, r8
0x140098d3f  xor     r12d, r12d
0x140098d42  mov     [rbp+57h+var_58], rax
0x140098d46  mov     [rbp+57h+var_50], r12d
0x140098d4a  mov     esi, edx
0x140098d4c  mov     [rbp+57h+var_48], r12
0x140098d50  mov     rbx, rcx
0x140098d53  mov     [rbp+57h+var_40], r12b
0x140098d57  mov     [rbp+57h+Source1], eax
0x140098d5a  mov     [rbp+57h+var_5C], ax
0x140098d5e  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140098d65  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140098d6c  lea     r15, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x140098d73  jz      short loc_140098DAB
0x140098d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140098d7c  cmp     byte ptr [rcx+29h], 5
0x140098d80  jnb     short loc_140098D89
0x140098d82  cmp     [rcx+48h], r12w
0x140098d87  jz      short loc_140098DAB
0x140098d89  mov     eax, [rbx+10h]
0x140098d8c  mov     r9d, 42h ; 'B'
0x140098d92  mov     rcx, [rcx+40h]
0x140098d96  mov     dl, 5
0x140098d98  mov     dword ptr [rsp+100h+var_D0], eax
0x140098d9c  mov     qword ptr [rsp+100h+var_D8], rbx
0x140098da1  mov     [rsp+100h+var_E0], r15
0x140098da6  call    WPP_RECORDER_SF_qD
0x140098dab  mov     eax, [rbx+284h]
0x140098db1  cmp     eax, 3
0x140098db4  jz      short loc_140098DFF
0x140098db6  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140098dbd  jz      loc_140099684
0x140098dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140098dca  mov     r9d, 43h ; 'C'
0x140098dd0  mov     dword ptr [rsp+100h+var_C0], eax
0x140098dd4  mov     dl, 2
0x140098dd6  mov     eax, [rbx+10h]
0x140098dd9  mov     r14d, r12d
0x140098ddc  mov     dword ptr [rsp+100h+var_C8], r12d
0x140098de1  mov     rcx, [rcx+40h]
0x140098de5  mov     dword ptr [rsp+100h+var_D0], eax
0x140098de9  mov     qword ptr [rsp+100h+var_D8], rbx
0x140098dee  mov     [rsp+100h+var_E0], r15
0x140098df3  call    WPP_RECORDER_SF_qDDd
0x140098df8  xor     edi, edi
0x140098dfa  jmp     loc_140099633
0x140098dff  mov     r8, [rbx+200h]
0x140098e06  lea     rdx, [rdi+30h]
0x140098e0a  add     r8, 3FF8h
0x140098e11  lea     ecx, [rsi-30h]
0x140098e14  lea     r9, [rbp+57h+Source1]
0x140098e18  call    ParseWdiIndicationActionFrameReceivedFromIhv
0x140098e1d  mov     r14d, eax
0x140098e20  test    eax, eax
0x140098e22  jz      short loc_140098E7B
0x140098e24  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140098e2b  jz      short loc_140098E5A
0x140098e2d  mov     ecx, [rbx+10h]
0x140098e30  mov     r9d, 44h ; 'D'
0x140098e36  mov     dword ptr [rsp+100h+var_C8], eax
0x140098e3a  mov     dl, 2
0x140098e3c  mov     dword ptr [rsp+100h+var_D0], ecx
0x140098e40  mov     rcx, cs:WPP_GLOBAL_Control
0x140098e47  mov     qword ptr [rsp+100h+var_D8], rbx
0x140098e4c  mov     [rsp+100h+var_E0], r15
0x140098e51  mov     rcx, [rcx+40h]
0x140098e55  call    WPP_RECORDER_SF_qDD
0x140098e5a  lea     rsi, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x140098e61  mov     rax, [rbx]
0x140098e64  mov     r8, rbx
0x140098e67  mov     edx, r14d
0x140098e6a  mov     rcx, rbx
0x140098e6d  mov     rax, [rax+10h]
0x140098e71  call    _guard_dispatch_icall
0x140098e76  jmp     loc_140098F39
0x140098e7b  lea     rdi, [rbx+24Ch]
0x140098e82  mov     r8d, 6; Length
0x140098e88  mov     rdx, rdi; Source2
0x140098e8b  lea     rcx, [rbp+57h+Source1]; Source1
0x140098e8f  call    cs:__imp_RtlCompareMemory
0x140098e96  nop     dword ptr [rax+rax+00h]
0x140098e9b  cmp     rax, 6
0x140098e9f  jz      short loc_140098EE2
0x140098ea1  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140098ea8  jz      loc_140099684
0x140098eae  mov     rcx, cs:WPP_GLOBAL_Control
0x140098eb5  lea     rax, [rbp+57h+Source1]
0x140098eb9  mov     [rsp+100h+var_B8], rax
0x140098ebe  mov     eax, [rbx+10h]
0x140098ec1  mov     [rsp+100h+var_C0], rdi
0x140098ec6  mov     rcx, [rcx+40h]
0x140098eca  mov     dword ptr [rsp+100h+var_C8], r12d
0x140098ecf  mov     dword ptr [rsp+100h+var_D0], eax
0x140098ed3  mov     qword ptr [rsp+100h+var_D8], rbx
0x140098ed8  call    WPP_RECORDER_SF_qDD_MAC__MAC_
0x140098edd  jmp     loc_140098DF8
0x140098ee2  mov     r15d, [rbp+57h+var_50]
0x140098ee6  mov     r11d, 0Dh
0x140098eec  cmp     r15d, r11d
0x140098eef  jnb     short loc_140098F40
0x140098ef1  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140098ef8  jz      loc_140099684
0x140098efe  mov     rcx, cs:WPP_GLOBAL_Control
0x140098f05  lea     rsi, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x140098f0c  mov     eax, [rbx+10h]
0x140098f0f  lea     r9d, [r11+39h]
0x140098f13  mov     dword ptr [rsp+100h+var_B8], r11d
0x140098f18  mov     dword ptr [rsp+100h+var_C0], r15d
0x140098f1d  mov     rcx, [rcx+40h]
0x140098f21  mov     dword ptr [rsp+100h+var_C8], r12d
0x140098f26  mov     dword ptr [rsp+100h+var_D0], eax
0x140098f2a  mov     qword ptr [rsp+100h+var_D8], rbx
0x140098f2f  mov     [rsp+100h+var_E0], rsi
0x140098f34  call    WPP_RECORDER_SF_qDDdd
0x140098f39  xor     edi, edi
0x140098f3b  jmp     loc_14009963A
0x140098f40  mov     r10, [rbp+57h+var_48]
0x140098f44  movzx   eax, byte ptr [r10+1]
0x140098f49  cmp     al, 0Bh
0x140098f4b  jz      loc_140099061
0x140098f51  cmp     al, r11b
0x140098f54  jz      short loc_140098F9E
0x140098f56  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140098f5d  jz      loc_140099684
0x140098f63  mov     rcx, cs:WPP_GLOBAL_Control
0x140098f6a  lea     rsi, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x140098f71  mov     dword ptr [rsp+100h+var_C0], eax
0x140098f75  mov     r9d, 48h ; 'H'
0x140098f7b  mov     eax, [rbx+10h]
0x140098f7e  mov     dl, 2
0x140098f80  mov     dword ptr [rsp+100h+var_C8], r12d
0x140098f85  mov     rcx, [rcx+40h]
0x140098f89  mov     dword ptr [rsp+100h+var_D0], eax
0x140098f8d  mov     qword ptr [rsp+100h+var_D8], rbx
0x140098f92  mov     [rsp+100h+var_E0], rsi
0x140098f97  call    WPP_RECORDER_SF_qDDd
0x140098f9c  jmp     short loc_140098F39
0x140098f9e  mov     r11d, 0Eh
0x140098fa4  cmp     r15d, r11d
0x140098fa7  jnb     short loc_140098FF2
0x140098fa9  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140098fb0  jz      loc_140098E5A
0x140098fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140098fbd  lea     r9d, [r11+39h]
0x140098fc1  mov     eax, [rbx+10h]
0x140098fc4  mov     dl, 2
0x140098fc6  mov     dword ptr [rsp+100h+var_C0], r11d
0x140098fcb  mov     dword ptr [rsp+100h+var_C8], esi
0x140098fcf  lea     rsi, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x140098fd6  mov     rcx, [rcx+40h]
0x140098fda  mov     dword ptr [rsp+100h+var_D0], eax
0x140098fde  mov     qword ptr [rsp+100h+var_D8], rbx
0x140098fe3  mov     [rsp+100h+var_E0], rsi
0x140098fe8  call    WPP_RECORDER_SF_qDdd
0x140098fed  jmp     loc_140098E61
0x140098ff2  movzx   eax, byte ptr [r10+6]
0x140098ff7  mov     edx, 100h
0x140098ffc  movzx   r13d, byte ptr [r10+7]
0x140099001  movzx   r12d, byte ptr [r10+0Dh]
0x140099006  movzx   r8d, byte ptr [r10+3]
0x14009900b  movzx   edi, byte ptr [r10+4]
0x140099010  imul    r13d, edx
0x140099014  imul    r12d, edx
0x140099018  xor     edx, edx
0x14009901a  add     r13w, ax
0x14009901e  movzx   eax, byte ptr [r10+0Ch]
0x140099023  add     r12w, ax
0x140099027  mov     al, [r10+5]
0x14009902b  mov     cl, al
0x14009902d  and     cl, 7Fh
0x140099030  mov     [rbp+57h+var_6F], cl
0x140099033  test    al, al
0x140099035  js      short loc_140099042
0x140099037  mov     [rbp+57h+var_70], dl
0x14009903a  mov     cl, dl
0x14009903c  test    r13w, r13w
0x140099040  jz      short loc_140099047
0x140099042  mov     cl, 1
0x140099044  mov     [rbp+57h+var_70], cl
0x140099047  mov     dl, [r10+8]
0x14009904b  lea     rax, [r10+0Eh]
0x14009904f  mov     r9b, [r10+0Bh]
0x140099053  mov     esi, edi
0x140099055  shl     esi, 8
0x140099058  add     esi, r8d
0x14009905b  mov     [rbp+57h+var_68], rax
0x14009905f  jmp     short loc_1400990BB
0x140099061  movzx   eax, byte ptr [r10+5]
0x140099066  mov     edx, 100h
0x14009906b  movzx   r8d, byte ptr [r10+6]
0x140099070  movzx   esi, byte ptr [r10+4]
0x140099075  mov     r9b, [r10+0Ah]
0x140099079  imul    r8d, edx
0x14009907d  mov     [rbp+57h+var_6F], r12b
0x140099081  movzx   r12d, byte ptr [r10+0Ch]
0x140099086  imul    r12d, edx
0x14009908a  mov     dl, [r10+7]
0x14009908e  add     r8w, ax
0x140099092  shl     esi, 8
0x140099095  movzx   eax, byte ptr [r10+0Bh]
0x14009909a  movzx   r13d, r8w
0x14009909e  add     r12w, ax
0x1400990a2  lea     rax, [r10+0Dh]
0x1400990a6  mov     [rbp+57h+var_68], rax
0x1400990aa  movzx   eax, byte ptr [r10+3]
0x1400990af  add     esi, eax
0x1400990b1  test    r8w, r8w
0x1400990b5  setnz   cl
0x1400990b8  mov     [rbp+57h+var_70], cl
0x1400990bb  mov     al, [r10]
0x1400990be  mov     edi, 4
0x1400990c3  mov     [rbp+57h+var_6E], al
0x1400990c6  cmp     al, dil
0x1400990c9  jnz     loc_1400995C5
0x1400990cf  mov     al, [rbx+1410h]
0x1400990d5  cmp     [r10+2], al
0x1400990d9  jnz     loc_1400995C5
0x1400990df  cmp     dl, 6Ch ; 'l'
0x1400990e2  jnz     loc_1400995C5
0x1400990e8  xor     r8d, r8d
0x1400990eb  test    r9b, r9b
0x1400990ee  jnz     loc_1400995C5
0x1400990f4  test    cl, cl
0x1400990f6  jnz     short loc_1400990FE
0x1400990f8  cmp     r8w, r12w
0x1400990fc  jz      short loc_14009910A
0x1400990fe  movzx   eax, r12w
0x140099102  add     eax, r11d
0x140099105  cmp     r15d, eax
0x140099108  jnb     short loc_14009916B
0x14009910a  mov     dword ptr [rbx+274h], 5
0x140099114  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009911b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140099122  jz      loc_140099684
0x140099128  movzx   edx, byte ptr [r10+1]
0x14009912d  movzx   ecx, cl
0x140099130  movzx   eax, r12w
0x140099134  mov     [rsp+100h+var_A8], eax
0x140099138  mov     eax, [rbx+10h]
0x14009913b  mov     [rsp+100h+var_B0], r11d
0x140099140  mov     dword ptr [rsp+100h+var_B8], r15d
0x140099145  mov     dword ptr [rsp+100h+var_C0], ecx
0x140099149  mov     rcx, cs:WPP_GLOBAL_Control
0x140099150  mov     dword ptr [rsp+100h+var_C8], edx
0x140099154  mov     dword ptr [rsp+100h+var_D0], eax
0x140099158  mov     qword ptr [rsp+100h+var_D8], rbx
0x14009915d  mov     rcx, [rcx+40h]
0x140099161  call    WPP_RECORDER_SF_qDdDddd
0x140099166  jmp     loc_140098DF8
0x14009916b  mov     edx, [rbx+280h]; unsigned int
0x140099171  test    edx, edx
0x140099173  jz      short loc_14009918F
0x140099175  mov     rcx, [rbx+20h]; this
0x140099179  mov     [rbx+29Eh], r8b
0x140099180  call    ?DeregisterTimeoutCallback@EventQueue@@QEAAHI@Z; EventQueue::DeregisterTimeoutCallback(uint)
0x140099185  xor     r8d, r8d
0x140099188  mov     [rbx+280h], r8d
0x14009918f  cmp     esi, 3Fh ; '?'
0x140099192  ja      loc_14009952A
0x140099198  jz      loc_140099550
0x14009919e  mov     ecx, esi
0x1400991a0  test    esi, esi
0x1400991a2  jz      short loc_1400991CE
0x1400991a4  sub     ecx, 3Bh ; ';'
0x1400991a7  jz      loc_14009955C
0x1400991ad  sub     ecx, 1
0x1400991b0  jz      loc_140099550
0x1400991b6  sub     ecx, 1
0x1400991b9  jz      short loc_1400991C4
0x1400991bb  cmp     ecx, 1
0x1400991be  jnz     loc_140099549
0x1400991c4  mov     edi, 6
0x1400991c9  jmp     loc_14009955C
0x1400991ce  mov     r9, [rbp+57h+var_68]; unsigned __int8 *
0x1400991d2  movzx   r8d, r12w; unsigned __int16
0x1400991d6  mov     dl, [rbp+57h+var_6F]; unsigned __int8
0x1400991d9  mov     rcx, rbx; this
0x1400991dc  call    ?CacheANQPFragment@CANQPQueryJob@@AEAAHEGPEAE@Z; CANQPQueryJob::CacheANQPFragment(uchar,ushort,uchar *)
0x1400991e1  xor     r12d, r12d
0x1400991e4  mov     r14d, eax
0x1400991e7  test    eax, eax
0x1400991e9  jz      short loc_140099238
0x1400991eb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400991f2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400991f9  jz      loc_140098E5A
0x1400991ff  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
