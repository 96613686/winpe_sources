# CRequestFtmChildJob::ProcessFtmResponse(_WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *)

- ea: `0x1400a005c`
- end: `0x1400a090e`
- name: `?ProcessFtmResponse@CRequestFtmChildJob@@AEAAHPEAU_WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS@@@Z`
- size: `2226`
- prototype: `__int64 __fastcall(CRequestFtmChildJob *__hidden this, struct _WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14009f9c0`

## callees

- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x140050dc8`
- `0x14009fdc4`
- `0x14009ff44`
- `0x1400a005c`
- `0x1400a0adc`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400a0180`
- `ntoskrnl!RtlCompareMemory` at `0x1400a0180`

## pseudocode

```c
__int64 __fastcall CRequestFtmChildJob::ProcessFtmResponse(
        CRequestFtmChildJob *this,
        struct _WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *a2,
        unsigned int a3)
{
  struct _WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *v3; // r14
  __int64 *v5; // rdx
  int v6; // ecx
  int v7; // eax
  unsigned int v8; // edi
  unsigned int v9; // ebp
  __int64 v10; // rax
  char v11; // r12
  __int64 v12; // rbp
  unsigned int v13; // r13d
  __int64 v14; // rdi
  const void *v15; // r14
  __int64 v16; // rsi
  int v17; // r9d
  int v18; // ecx
  __int64 v19; // rax
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  unsigned __int8 *v28; // r14
  int v30; // r9d
  int v31; // [rsp+20h] [rbp-68h]
  char v32; // [rsp+28h] [rbp-60h]
  int v33; // [rsp+30h] [rbp-58h]
  __int64 v34; // [rsp+38h] [rbp-50h]
  unsigned int v35; // [rsp+90h] [rbp+8h]

  v3 = a2;
  v5 = WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v5,
      a3,
      38,
      (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    v5 = WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids;
  }
  v6 = *((_DWORD *)this + 265);
  v7 = *(_DWORD *)v3;
  if ( *(_DWORD *)v3 == v6 )
  {
    v8 = 0;
    v35 = 0;
    v9 = 0;
    if ( !v7 )
      goto LABEL_112;
    while ( 2 )
    {
      v10 = v9;
      v11 = 0;
      v12 = *((_QWORD *)v3 + 1);
      v13 = 0;
      v14 = 80 * v10;
      v15 = (const void *)(80 * v10 + v12 + 4);
      while ( 1 )
      {
        if ( v13 >= *((_DWORD *)this + 264) )
        {
          if ( !v11 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v5) = 2;
            WPP_RECORDER_SF_qD_MAC_(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v5,
              a3,
              53,
              (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
              (char)this,
              *((_DWORD *)this + 4),
              (__int64)v15);
          }
          goto LABEL_110;
        }
        v16 = 104LL * v13;
        if ( RtlCompareMemory(v15, (const void *)(v16 + *((_QWORD *)this + 131)), 6u) == 6 )
          break;
LABEL_105:
        ++v13;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v17 = 0;
      }
      else if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || (v17 = 0, LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_qD_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          40,
          (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          (__int64)v15);
        v17 = 0;
      }
      v18 = *(_DWORD *)(v14 + v12 + 12);
      v19 = *((_QWORD *)this + 131);
      if ( v18 )
      {
        v20 = v18 - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              v23 = v22 - 1;
              if ( v23 )
              {
                v24 = v23 - 1;
                if ( v24 )
                {
                  if ( v24 == 1 )
                    *(_DWORD *)(v19 + v16 + 8) = 6;
                  else
                    *(_DWORD *)(v19 + v16 + 8) = 7;
                }
                else
                {
                  *(_DWORD *)(v19 + v16 + 8) = 5;
                }
              }
              else
              {
                *(_DWORD *)(v19 + v16 + 8) = 4;
              }
            }
            else
            {
              *(_DWORD *)(v19 + v16 + 8) = 3;
            }
          }
          else
          {
            *(_DWORD *)(v19 + v16 + 8) = 2;
          }
        }
        else
        {
          *(_DWORD *)(v19 + v16 + 8) = 1;
        }
      }
      else
      {
        *(_DWORD *)(v19 + v16 + 8) = 0;
      }
      if ( *(_DWORD *)(v14 + v12 + 12) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v34) = *(_DWORD *)(v14 + v12 + 12);
          v30 = 41;
          v33 = *((_DWORD *)this + 4);
          v32 = (char)this;
LABEL_121:
          LOBYTE(v5) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v5,
            a3,
            v30,
            (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
            v32,
            v33,
            v34);
        }
LABEL_110:
        v3 = a2;
        v9 = v35 + 1;
        v35 = v9;
        if ( v9 >= *(_DWORD *)a2 )
        {
          v8 = 0;
          goto LABEL_112;
        }
        continue;
      }
      break;
    }
    v25 = *(_DWORD *)(v14 + v12);
    if ( (v25 & 0x10) == 0 || (v25 & 2) == 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          42,
          (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          (*(_DWORD *)(v14 + v12) & 0x10) != 0,
          (*(_DWORD *)(v14 + v12) & 2) != 0);
      }
      *(_DWORD *)(*((_QWORD *)this + 131) + v16 + 8) = 7;
      goto LABEL_110;
    }
    v11 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v5,
        a3,
        43,
        (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        *(_DWORD *)(v14 + v12 + 32),
        *(_WORD *)(v14 + v12 + 18));
      v17 = 0;
    }
    *(_DWORD *)(*((_QWORD *)this + 131) + v16 + 28) = *(_DWORD *)(v14 + v12 + 32);
    *(_WORD *)(*((_QWORD *)this + 131) + v16 + 14) = *(_WORD *)(v14 + v12 + 18);
    if ( (*(_DWORD *)(v14 + v12) & 1) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v5) = 5;
        LODWORD(v34) = *(unsigned __int16 *)(v14 + v12 + 16);
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          44,
          (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v34);
      }
      *(_WORD *)(*((_QWORD *)this + 131) + v16 + 12) = *(_WORD *)(v14 + v12 + 16);
    }
    if ( (*(_DWORD *)(v14 + v12) & 4) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v5) = 5;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          45,
          (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          *(_DWORD *)(v14 + v12 + 20),
          *(_DWORD *)(v14 + v12 + 24));
      }
      *(_DWORD *)(*((_QWORD *)this + 131) + v16 + 16) = *(_DWORD *)(v14 + v12 + 20);
      *(_DWORD *)(*((_QWORD *)this + 131) + v16 + 20) = *(_DWORD *)(v14 + v12 + 24);
    }
    if ( (*(_DWORD *)(v14 + v12) & 0x20) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        WPP_RECORDER_SF_qDI(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          v17,
          v31,
          (char)this,
          *((_DWORD *)this + 4),
          *(_QWORD *)(v14 + v12 + 40));
      }
      *(_QWORD *)(*((_QWORD *)this + 131) + v16 + 32) = *(_QWORD *)(v14 + v12 + 40);
    }
    if ( (*(_DWORD *)(v14 + v12) & 8) == 0 )
    {
LABEL_81:
      if ( (*(_DWORD *)(v14 + v12) & 0x40) == 0 )
        goto LABEL_92;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v5) = 5;
        LODWORD(v34) = *(_DWORD *)(v14 + v12 + 48);
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v5,
          a3,
          48,
          (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v34);
      }
      v26 = *(_DWORD *)(v14 + v12 + 48);
      v5 = (__int64 *)*((_QWORD *)this + 131);
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( !v27 )
        {
          LODWORD(v5[(unsigned __int64)v16 / 8 + 5]) = 1;
          goto LABEL_92;
        }
        if ( v27 == 1 )
        {
          LODWORD(v5[(unsigned __int64)v16 / 8 + 5]) = 2;
          goto LABEL_92;
        }
      }
      LODWORD(v5[(unsigned __int64)v16 / 8 + 5]) = 0;
LABEL_92:
      if ( (*(_DWORD *)(v14 + v12) & 0x80u) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v5) = 5;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v5,
            a3,
            49,
            (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
            (char)this,
            *((_DWORD *)this + 4));
        }
        *(_DWORD *)(*((_QWORD *)this + 131) + v16 + 44) = 0;
        if ( *(_DWORD *)(v14 + v12 + 52) )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_110;
          LODWORD(v34) = *(_DWORD *)(v14 + v12 + 52);
          v30 = 50;
          v33 = *((_DWORD *)this + 4);
          v32 = (char)this;
          goto LABEL_121;
        }
        if ( (*(_DWORD *)(v14 + v12) & 0x100) == 0 || (a3 = *(_DWORD *)(v14 + v12 + 56), a3 < 2) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v5) = 2;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v5,
              a3,
              51,
              (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
          goto LABEL_110;
        }
        v28 = *(unsigned __int8 **)(v14 + v12 + 64);
        if ( a3 == 2 && !*v28 && !v28[1] )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v5) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v5,
              2,
              52,
              (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
          goto LABEL_110;
        }
        if ( !CRequestFtmChildJob::ParseLCISubelement(
                this,
                *(unsigned __int8 **)(v14 + v12 + 64),
                a3,
                (struct _DOT11_FTM_RESPONSE *)(v16 + *((_QWORD *)this + 131))) )
          goto LABEL_110;
        CRequestFtmChildJob::ParseZSubelement(
          this,
          v28,
          *(_DWORD *)(v14 + v12 + 56),
          (struct _DOT11_FTM_RESPONSE *)(v16 + *((_QWORD *)this + 131)));
        v15 = (const void *)(v14 + v12 + 4);
      }
      goto LABEL_105;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        a3 = 0;
        if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_64;
      }
      LOBYTE(v5) = 5;
      LODWORD(v34) = *(_DWORD *)(v14 + v12 + 28);
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v5,
        a3,
        47,
        (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v34);
    }
    a3 = 0;
LABEL_64:
    v5 = (__int64 *)*((_QWORD *)this + 131);
    switch ( *(_DWORD *)(v14 + v12 + 28) )
    {
      case 1:
        LODWORD(v5[(unsigned __int64)v16 / 8 + 3]) = 1;
        break;
      case 2:
        LODWORD(v5[(unsigned __int64)v16 / 8 + 3]) = 2;
        break;
      case 3:
        LODWORD(v5[(unsigned __int64)v16 / 8 + 3]) = 3;
        break;
      case 4:
        LODWORD(v5[(unsigned __int64)v16 / 8 + 3]) = 4;
        break;
      case 5:
        LODWORD(v5[(unsigned __int64)v16 / 8 + 3]) = 5;
        break;
      case 6:
        LODWORD(v5[(unsigned __int64)v16 / 8 + 3]) = 6;
        break;
      case 7:
        LODWORD(v5[(unsigned __int64)v16 / 8 + 3]) = 7;
        break;
      case 8:
        LODWORD(v5[(unsigned __int64)v16 / 8 + 3]) = 8;
        break;
      default:
        LODWORD(v5[(unsigned __int64)v16 / 8 + 3]) = 0;
        break;
    }
    goto LABEL_81;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v5,
      a3,
      39,
      (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v7,
      v6);
  }
  v8 = -1073676267;
LABEL_112:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v34) = v8;
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v5,
      *((_DWORD *)this + 4),
      54,
      (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v34);
  }
  return v8;
}

```

## disassembly

```asm
0x1400a005c  mov     [rsp+arg_8], rdx
0x1400a0061  push    rbx
0x1400a0062  push    rbp
0x1400a0063  push    rsi
0x1400a0064  push    rdi
0x1400a0065  push    r12
0x1400a0067  push    r13
0x1400a0069  push    r14
0x1400a006b  sub     rsp, 50h
0x1400a006f  mov     r14, rdx
0x1400a0072  mov     rbx, rcx
0x1400a0075  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400a007c  xor     r9d, r9d
0x1400a007f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a0086  lea     rdx, WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids
0x1400a008d  jz      short loc_1400A00CF
0x1400a008f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0096  cmp     byte ptr [rcx+29h], 5
0x1400a009a  jnb     short loc_1400A00A3
0x1400a009c  cmp     [rcx+48h], r9w
0x1400a00a1  jz      short loc_1400A00CF
0x1400a00a3  mov     eax, [rbx+10h]
0x1400a00a6  mov     r9d, 26h ; '&'
0x1400a00ac  mov     rcx, [rcx+40h]
0x1400a00b0  mov     [rsp+88h+var_58], eax
0x1400a00b4  mov     [rsp+88h+var_60], rbx
0x1400a00b9  mov     [rsp+88h+var_68], rdx
0x1400a00be  mov     dl, 5
0x1400a00c0  call    WPP_RECORDER_SF_qD
0x1400a00c5  xor     r9d, r9d
0x1400a00c8  lea     rdx, WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids
0x1400a00cf  mov     ecx, [rbx+424h]
0x1400a00d5  mov     eax, [r14]
0x1400a00d8  cmp     eax, ecx
0x1400a00da  jz      short loc_1400A0120
0x1400a00dc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a00e3  jz      short loc_1400A0116
0x1400a00e5  mov     [rsp+88h+var_48], ecx
0x1400a00e9  mov     r9d, 27h ; '''
0x1400a00ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a00f6  mov     dword ptr [rsp+88h+var_50], eax
0x1400a00fa  mov     eax, [rbx+10h]
0x1400a00fd  mov     [rsp+88h+var_58], eax
0x1400a0101  mov     rcx, [rcx+40h]
0x1400a0105  mov     [rsp+88h+var_60], rbx
0x1400a010a  mov     [rsp+88h+var_68], rdx
0x1400a010f  mov     dl, 2
0x1400a0111  call    WPP_RECORDER_SF_qDdd
0x1400a0116  mov     edi, 0C0010015h
0x1400a011b  jmp     loc_1400A0759
0x1400a0120  mov     [rsp+88h+arg_10], r9d
0x1400a0128  mov     edi, r9d
0x1400a012b  mov     [rsp+88h+arg_0], r9d
0x1400a0133  mov     ebp, r9d
0x1400a0136  test    eax, eax
0x1400a0138  jz      loc_1400A0759
0x1400a013e  mov     eax, ebp
0x1400a0140  mov     r12b, r9b
0x1400a0143  mov     rbp, [r14+8]
0x1400a0147  mov     r13d, r9d
0x1400a014a  lea     rdi, [rax+rax*4]
0x1400a014e  shl     rdi, 4
0x1400a0152  lea     r14, [rbp+4]
0x1400a0156  add     r14, rdi
0x1400a0159  cmp     r13d, [rbx+420h]
0x1400a0160  jnb     loc_1400A08B4
0x1400a0166  mov     rdx, [rbx+418h]
0x1400a016d  mov     r8d, 6; Length
0x1400a0173  mov     eax, r13d
0x1400a0176  mov     rcx, r14; Source1
0x1400a0179  imul    rsi, rax, 68h ; 'h'
0x1400a017d  add     rdx, rsi; Source2
0x1400a0180  call    cs:__imp_RtlCompareMemory
0x1400a0187  nop     dword ptr [rax+rax+00h]
0x1400a018c  cmp     rax, 6
0x1400a0190  jnz     loc_1400A06D6
0x1400a0196  lea     r10, WPP_RECORDER_INITIALIZED
0x1400a019d  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400a01a4  jz      short loc_1400A01F7
0x1400a01a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a01ad  cmp     byte ptr [rcx+29h], 5
0x1400a01b1  jnb     short loc_1400A01BD
0x1400a01b3  xor     r9d, r9d
0x1400a01b6  cmp     [rcx+48h], r9w
0x1400a01bb  jz      short loc_1400A01FA
0x1400a01bd  mov     eax, [rbx+10h]
0x1400a01c0  lea     r12, WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids
0x1400a01c7  mov     rcx, [rcx+40h]
0x1400a01cb  mov     r9d, 28h ; '('
0x1400a01d1  mov     [rsp+88h+var_50], r14
0x1400a01d6  mov     dl, 5
0x1400a01d8  mov     [rsp+88h+var_58], eax
0x1400a01dc  mov     [rsp+88h+var_60], rbx
0x1400a01e1  mov     [rsp+88h+var_68], r12
0x1400a01e6  call    WPP_RECORDER_SF_qD_MAC_
0x1400a01eb  xor     r9d, r9d
0x1400a01ee  lea     r10, WPP_RECORDER_INITIALIZED
0x1400a01f5  jmp     short loc_1400A0201
0x1400a01f7  xor     r9d, r9d
0x1400a01fa  lea     r12, WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids
0x1400a0201  mov     ecx, [rdi+rbp+0Ch]
0x1400a0205  mov     rax, [rbx+418h]
0x1400a020c  test    ecx, ecx
0x1400a020e  jz      short loc_1400A0274
0x1400a0210  sub     ecx, 1
0x1400a0213  jz      short loc_1400A026A
0x1400a0215  sub     ecx, 1
0x1400a0218  jz      short loc_1400A0260
0x1400a021a  sub     ecx, 1
0x1400a021d  jz      short loc_1400A0256
0x1400a021f  sub     ecx, 1
0x1400a0222  jz      short loc_1400A024C
0x1400a0224  sub     ecx, 1
0x1400a0227  jz      short loc_1400A0242
0x1400a0229  cmp     ecx, 1
0x1400a022c  jz      short loc_1400A0238
0x1400a022e  mov     dword ptr [rax+rsi+8], 7
0x1400a0236  jmp     short loc_1400A0279
0x1400a0238  mov     dword ptr [rax+rsi+8], 6
0x1400a0240  jmp     short loc_1400A0279
0x1400a0242  mov     dword ptr [rax+rsi+8], 5
0x1400a024a  jmp     short loc_1400A0279
0x1400a024c  mov     dword ptr [rax+rsi+8], 4
0x1400a0254  jmp     short loc_1400A0279
0x1400a0256  mov     dword ptr [rax+rsi+8], 3
0x1400a025e  jmp     short loc_1400A0279
0x1400a0260  mov     dword ptr [rax+rsi+8], 2
0x1400a0268  jmp     short loc_1400A0279
0x1400a026a  mov     dword ptr [rax+rsi+8], 1
0x1400a0272  jmp     short loc_1400A0279
0x1400a0274  mov     [rax+rsi+8], r9d
0x1400a0279  mov     eax, [rdi+rbp+0Ch]
0x1400a027d  test    eax, eax
0x1400a027f  jnz     loc_1400A0887
0x1400a0285  mov     ecx, [rdi+rbp]
0x1400a0288  test    cl, 10h
0x1400a028b  jz      loc_1400A0829
0x1400a0291  test    cl, 2
0x1400a0294  jz      loc_1400A0829
0x1400a029a  mov     r12b, 1
0x1400a029d  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400a02a4  jz      short loc_1400A02FE
0x1400a02a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a02ad  cmp     byte ptr [rcx+29h], 5
0x1400a02b1  jnb     short loc_1400A02BA
0x1400a02b3  cmp     [rcx+48h], r9w
0x1400a02b8  jz      short loc_1400A02FE
0x1400a02ba  movzx   eax, word ptr [rdi+rbp+12h]
0x1400a02bf  mov     r9d, 2Bh ; '+'
0x1400a02c5  mov     rcx, [rcx+40h]
0x1400a02c9  mov     dl, 5
0x1400a02cb  mov     [rsp+88h+var_48], eax
0x1400a02cf  mov     eax, [rdi+rbp+20h]
0x1400a02d3  mov     dword ptr [rsp+88h+var_50], eax
0x1400a02d7  mov     eax, [rbx+10h]
0x1400a02da  mov     [rsp+88h+var_58], eax
0x1400a02de  lea     rax, WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids
0x1400a02e5  mov     [rsp+88h+var_60], rbx
0x1400a02ea  mov     [rsp+88h+var_68], rax
0x1400a02ef  call    WPP_RECORDER_SF_qDdd
0x1400a02f4  xor     r9d, r9d
0x1400a02f7  lea     r10, WPP_RECORDER_INITIALIZED
0x1400a02fe  mov     eax, [rdi+rbp+20h]
0x1400a0302  mov     rcx, [rbx+418h]
0x1400a0309  mov     [rcx+rsi+1Ch], eax
0x1400a030d  movzx   eax, word ptr [rdi+rbp+12h]
0x1400a0312  mov     rcx, [rbx+418h]
0x1400a0319  mov     [rcx+rsi+0Eh], ax
0x1400a031e  mov     eax, [rdi+rbp]
0x1400a0321  test    r12b, al
0x1400a0324  jz      short loc_1400A038D
0x1400a0326  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400a032d  jz      short loc_1400A037C
0x1400a032f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0336  cmp     byte ptr [rcx+29h], 5
0x1400a033a  jnb     short loc_1400A0343
0x1400a033c  cmp     [rcx+48h], r9w
0x1400a0341  jz      short loc_1400A037C
0x1400a0343  movzx   eax, word ptr [rdi+rbp+10h]
0x1400a0348  mov     r9d, 2Ch ; ','
0x1400a034e  mov     rcx, [rcx+40h]
0x1400a0352  mov     dl, 5
0x1400a0354  mov     dword ptr [rsp+88h+var_50], eax
0x1400a0358  mov     eax, [rbx+10h]
0x1400a035b  mov     [rsp+88h+var_58], eax
0x1400a035f  lea     rax, WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids
0x1400a0366  mov     [rsp+88h+var_60], rbx
0x1400a036b  mov     [rsp+88h+var_68], rax
0x1400a0370  call    WPP_RECORDER_SF_qDD
0x1400a0375  lea     r10, WPP_RECORDER_INITIALIZED
0x1400a037c  mov     rcx, [rbx+418h]
0x1400a0383  movzx   eax, word ptr [rdi+rbp+10h]
0x1400a0388  mov     [rcx+rsi+0Ch], ax
0x1400a038d  mov     eax, [rdi+rbp]
0x1400a0390  test    al, 4
0x1400a0392  jz      short loc_1400A0410
0x1400a0394  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400a039b  jz      short loc_1400A03F2
0x1400a039d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a03a4  cmp     byte ptr [rcx+29h], 5
0x1400a03a8  jnb     short loc_1400A03B2
0x1400a03aa  xor     eax, eax
0x1400a03ac  cmp     [rcx+48h], ax
0x1400a03b0  jz      short loc_1400A03F2
0x1400a03b2  mov     eax, [rdi+rbp+18h]
0x1400a03b6  mov     r9d, 2Dh ; '-'
0x1400a03bc  mov     rcx, [rcx+40h]
0x1400a03c0  mov     dl, 5
0x1400a03c2  mov     [rsp+88h+var_48], eax
0x1400a03c6  mov     eax, [rdi+rbp+14h]
0x1400a03ca  mov     dword ptr [rsp+88h+var_50], eax
0x1400a03ce  mov     eax, [rbx+10h]
0x1400a03d1  mov     [rsp+88h+var_58], eax
0x1400a03d5  lea     rax, WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids
0x1400a03dc  mov     [rsp+88h+var_60], rbx
0x1400a03e1  mov     [rsp+88h+var_68], rax
0x1400a03e6  call    WPP_RECORDER_SF_qDdd
0x1400a03eb  lea     r10, WPP_RECORDER_INITIALIZED
0x1400a03f2  mov     rcx, [rbx+418h]
0x1400a03f9  mov     eax, [rdi+rbp+14h]
0x1400a03fd  mov     [rcx+rsi+10h], eax
0x1400a0401  mov     rcx, [rbx+418h]
0x1400a0408  mov     eax, [rdi+rbp+18h]
0x1400a040c  mov     [rcx+rsi+14h], eax
0x1400a0410  mov     eax, [rdi+rbp]
0x1400a0413  test    al, 20h
0x1400a0415  jz      short loc_1400A046C
0x1400a0417  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400a041e  jz      short loc_1400A045B
0x1400a0420  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0427  cmp     byte ptr [rcx+29h], 5
0x1400a042b  jnb     short loc_1400A0435
0x1400a042d  xor     eax, eax
0x1400a042f  cmp     [rcx+48h], ax
0x1400a0433  jz      short loc_1400A045B
0x1400a0435  mov     rax, [rdi+rbp+28h]
0x1400a043a  mov     rcx, [rcx+40h]
0x1400a043e  mov     [rsp+88h+var_50], rax
0x1400a0443  mov     eax, [rbx+10h]
0x1400a0446  mov     [rsp+88h+var_58], eax
0x1400a044a  mov     [rsp+88h+var_60], rbx
0x1400a044f  call    WPP_RECORDER_SF_qDI
0x1400a0454  lea     r10, WPP_RECORDER_INITIALIZED
0x1400a045b  mov     rcx, [rbx+418h]
0x1400a0462  mov     rax, [rdi+rbp+28h]
0x1400a0467  mov     [rcx+rsi+20h], rax
0x1400a046c  mov     eax, [rdi+rbp]
0x1400a046f  test    al, 8
0x1400a0471  jz      loc_1400A055A
0x1400a0477  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400a047e  jz      short loc_1400A04CF
0x1400a0480  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a0487  cmp     byte ptr [rcx+29h], 5
0x1400a048b  jnb     short loc_1400A0497
0x1400a048d  xor     r8d, r8d
0x1400a0490  cmp     [rcx+48h], r8w
0x1400a0495  jz      short loc_1400A04D2
0x1400a0497  mov     eax, [rdi+rbp+1Ch]
0x1400a049b  mov     r9d, 2Fh ; '/'
0x1400a04a1  mov     rcx, [rcx+40h]
0x1400a04a5  mov     dl, 5
0x1400a04a7  mov     dword ptr [rsp+88h+var_50], eax
0x1400a04ab  mov     eax, [rbx+10h]
0x1400a04ae  mov     [rsp+88h+var_58], eax
0x1400a04b2  lea     rax, WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids
0x1400a04b9  mov     [rsp+88h+var_60], rbx
0x1400a04be  mov     [rsp+88h+var_68], rax
0x1400a04c3  call    WPP_RECORDER_SF_qDD
0x1400a04c8  lea     r10, WPP_RECORDER_INITIALIZED
0x1400a04cf  xor     r8d, r8d
0x1400a04d2  mov     ecx, [rdi+rbp+1Ch]
0x1400a04d6  mov     rdx, [rbx+418h]
0x1400a04dd  sub     ecx, 1
0x1400a04e0  jz      short loc_1400A0552
0x1400a04e2  sub     ecx, 1
0x1400a04e5  jz      short loc_1400A0548
0x1400a04e7  sub     ecx, 1
0x1400a04ea  jz      short loc_1400A053E
0x1400a04ec  sub     ecx, 1
0x1400a04ef  jz      short loc_1400A0534
0x1400a04f1  sub     ecx, 1
0x1400a04f4  jz      short loc_1400A052A
0x1400a04f6  sub     ecx, 1
0x1400a04f9  jz      short loc_1400A0520
0x1400a04fb  sub     ecx, 1
0x1400a04fe  jz      short loc_1400A0516
0x1400a0500  cmp     ecx, 1
0x1400a0503  jz      short loc_1400A050C
0x1400a0505  mov     [rdx+rsi+18h], r8d
0x1400a050a  jmp     short loc_1400A055A
0x1400a050c  mov     dword ptr [rdx+rsi+18h], 8
0x1400a0514  jmp     short loc_1400A055A
0x1400a0516  mov     dword ptr [rdx+rsi+18h], 7
0x1400a051e  jmp     short loc_1400A055A
0x1400a0520  mov     dword ptr [rdx+rsi+18h], 6
0x1400a0528  jmp     short loc_1400A055A
0x1400a052a  mov     dword ptr [rdx+rsi+18h], 5
0x1400a0532  jmp     short loc_1400A055A
0x1400a0534  mov     dword ptr [rdx+rsi+18h], 4
0x1400a053c  jmp     short loc_1400A055A
  ... truncated ...
```
