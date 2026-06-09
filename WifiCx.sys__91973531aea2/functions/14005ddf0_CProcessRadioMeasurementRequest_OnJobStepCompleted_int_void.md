# CProcessRadioMeasurementRequest::OnJobStepCompleted(int,void *)

- ea: `0x14005ddf0`
- end: `0x14005e1aa`
- name: `?OnJobStepCompleted@CProcessRadioMeasurementRequest@@UEAAXHPEAX@Z`
- size: `954`
- prototype: `void __fastcall(CProcessRadioMeasurementRequest *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140012f80`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x140050574`
- `0x14005ddf0`
- `0x14005e398`
- `0x14005ec00`
- `0x14005eff8`
- `0x14005f154`

## pseudocode

```c
void __fastcall CProcessRadioMeasurementRequest::OnJobStepCompleted(
        CProcessRadioMeasurementRequest *this,
        __int64 a2,
        __int64 a3,
        int a4)
{
  unsigned int v4; // edi
  unsigned int v6; // eax
  PDEVICE_OBJECT v7; // rcx
  int v8; // r9d
  unsigned int v9; // r8d
  int v10; // ecx
  unsigned int v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // edx
  unsigned int started; // eax
  __int64 v16; // [rsp+38h] [rbp-40h]

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        101,
        (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        102,
        (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        *((_DWORD *)this + 134),
        v4);
    }
  }
  if ( *((_BYTE *)this + 556) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        103,
        (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    v4 = -1073676276;
    goto LABEL_34;
  }
  if ( *((_DWORD *)this + 134) == 1 )
  {
    v13 = CProcessRadioMeasurementRequest::ParseMeasurementRequestMessage(this, a2, a3);
    v4 = v13;
    if ( v13 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v16) = v13;
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          a3,
          104,
          (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v16);
      }
      goto LABEL_34;
    }
    if ( *((_BYTE *)this + 3919) != 1 )
      goto LABEL_26;
    if ( *((_BYTE *)this + 3988) )
      goto LABEL_28;
    started = CProcessRadioMeasurementRequest::StartBeaconReportScanJob(this);
    v4 = started;
    if ( !started )
      goto LABEL_35;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v16) = started;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        105,
        (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v16);
    }
    *((_BYTE *)this + 3988) |= 2u;
    goto LABEL_49;
  }
  if ( *((_DWORD *)this + 134) == 2 )
  {
    if ( !v4 )
    {
LABEL_26:
      if ( !*((_BYTE *)this + 3988) )
        CProcessRadioMeasurementRequest::UpdateMatchingBSSList(this);
      goto LABEL_28;
    }
LABEL_49:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      LODWORD(v16) = v4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        106,
        (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v16);
    }
    *((_BYTE *)this + 3988) |= 2u;
LABEL_28:
    v9 = *((_DWORD *)this + 996) != 0 ? 2 : 20;
    *((_DWORD *)this + 1008) = v9;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = *((_DWORD *)this + 1007);
      v11 = (v9 + v10 - 1) % v9;
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF_dDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v9,
        107,
        (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
        v10,
        v9,
        (v9 + v10 - 1) / v9);
    }
    v12 = CProcessRadioMeasurementRequest::StartSendResponseJob(this);
    v4 = v12;
    if ( v12 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_34;
      v7 = WPP_GLOBAL_Control;
      v8 = 108;
      LODWORD(v16) = v12;
      LOBYTE(a2) = 2;
LABEL_33:
      WPP_RECORDER_SF_qDD(
        v7->DeviceExtension,
        a2,
        a3,
        v8,
        (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v16);
      goto LABEL_34;
    }
    goto LABEL_35;
  }
  if ( *((_DWORD *)this + 134) != 3 )
  {
    v4 = -1073741823;
LABEL_34:
    *((_DWORD *)this + 134) = 4;
    CJobBase::CompleteJob(this, v4, a3, a4);
    goto LABEL_35;
  }
  if ( *((_DWORD *)this + 1009) >= *((_DWORD *)this + 1007) )
    goto LABEL_21;
  v6 = CProcessRadioMeasurementRequest::StartSendResponseJob(this);
  v4 = v6;
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_34;
    LODWORD(v16) = v6;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      109,
      (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v16);
LABEL_21:
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_34;
    v7 = WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_34;
    v8 = 110;
    LODWORD(v16) = v4;
    LOBYTE(a2) = 5;
    goto LABEL_33;
  }
LABEL_35:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v16) = v4;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      111,
      (__int64)WPP_085fb23693d1371796aeda38c7d42f88_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v16);
  }
}

```

## disassembly

```asm
0x14005ddf0  push    rbx
0x14005ddf2  push    rbp
0x14005ddf3  push    rsi
0x14005ddf4  push    rdi
0x14005ddf5  push    r14
0x14005ddf7  sub     rsp, 50h
0x14005ddfb  mov     edi, edx
0x14005ddfd  mov     rbx, rcx
0x14005de00  lea     rbp, WPP_RECORDER_INITIALIZED
0x14005de07  xor     esi, esi
0x14005de09  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005de10  lea     r14, WPP_085fb23693d1371796aeda38c7d42f88_Traceguids
0x14005de17  jz      loc_14005DE9E
0x14005de1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005de24  cmp     byte ptr [rcx+29h], 5
0x14005de28  jnb     short loc_14005DE30
0x14005de2a  cmp     [rcx+48h], si
0x14005de2e  jz      short loc_14005DE52
0x14005de30  mov     eax, [rbx+10h]
0x14005de33  mov     r9d, 65h ; 'e'
0x14005de39  mov     rcx, [rcx+40h]
0x14005de3d  mov     dl, 5
0x14005de3f  mov     [rsp+78h+var_48], eax
0x14005de43  mov     [rsp+78h+var_50], rbx
0x14005de48  mov     [rsp+78h+var_58], r14
0x14005de4d  call    WPP_RECORDER_SF_qD
0x14005de52  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005de59  jz      short loc_14005DE9E
0x14005de5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005de62  cmp     byte ptr [rcx+29h], 5
0x14005de66  jnb     short loc_14005DE6E
0x14005de68  cmp     [rcx+48h], si
0x14005de6c  jz      short loc_14005DE9E
0x14005de6e  mov     eax, [rbx+218h]
0x14005de74  mov     r9d, 66h ; 'f'
0x14005de7a  mov     rcx, [rcx+40h]
0x14005de7e  mov     dl, 5
0x14005de80  mov     [rsp+78h+var_38], edi
0x14005de84  mov     dword ptr [rsp+78h+var_40], eax
0x14005de88  mov     eax, [rbx+10h]
0x14005de8b  mov     [rsp+78h+var_48], eax
0x14005de8f  mov     [rsp+78h+var_50], rbx
0x14005de94  mov     [rsp+78h+var_58], r14
0x14005de99  call    WPP_RECORDER_SF_qDdd
0x14005de9e  cmp     [rbx+22Ch], sil
0x14005dea5  jz      short loc_14005DEE3
0x14005dea7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005deae  jz      short loc_14005DED9
0x14005deb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005deb7  mov     r9d, 67h ; 'g'
0x14005debd  mov     eax, [rbx+10h]
0x14005dec0  mov     dl, 4
0x14005dec2  mov     [rsp+78h+var_48], eax
0x14005dec6  mov     [rsp+78h+var_50], rbx
0x14005decb  mov     rcx, [rcx+40h]
0x14005decf  mov     [rsp+78h+var_58], r14
0x14005ded4  call    WPP_RECORDER_SF_qD
0x14005ded9  mov     edi, 0C001000Ch
0x14005dede  jmp     loc_14005E054
0x14005dee3  mov     ecx, [rbx+218h]
0x14005dee9  sub     ecx, 1
0x14005deec  jz      loc_14005E0B6
0x14005def2  sub     ecx, 1
0x14005def5  jz      loc_14005DF99
0x14005defb  cmp     ecx, 1
0x14005defe  jz      short loc_14005DF0A
0x14005df00  mov     edi, 0C0000001h
0x14005df05  jmp     loc_14005E054
0x14005df0a  mov     eax, [rbx+0FBCh]
0x14005df10  cmp     [rbx+0FC4h], eax
0x14005df16  jnb     short loc_14005DF64
0x14005df18  mov     rcx, rbx; this
0x14005df1b  call    ?StartSendResponseJob@CProcessRadioMeasurementRequest@@AEAAHXZ; CProcessRadioMeasurementRequest::StartSendResponseJob(void)
0x14005df20  mov     edi, eax
0x14005df22  test    eax, eax
0x14005df24  jz      loc_14005E068
0x14005df2a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005df31  jz      loc_14005E054
0x14005df37  mov     rcx, cs:WPP_GLOBAL_Control
0x14005df3e  mov     r9d, 6Dh ; 'm'
0x14005df44  mov     dword ptr [rsp+78h+var_40], eax
0x14005df48  mov     dl, 2
0x14005df4a  mov     eax, [rbx+10h]
0x14005df4d  mov     [rsp+78h+var_48], eax
0x14005df51  mov     rcx, [rcx+40h]
0x14005df55  mov     [rsp+78h+var_50], rbx
0x14005df5a  mov     [rsp+78h+var_58], r14
0x14005df5f  call    WPP_RECORDER_SF_qDD
0x14005df64  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005df6b  jz      loc_14005E054
0x14005df71  mov     rcx, cs:WPP_GLOBAL_Control
0x14005df78  cmp     byte ptr [rcx+29h], 5
0x14005df7c  jnb     short loc_14005DF88
0x14005df7e  cmp     [rcx+48h], si
0x14005df82  jz      loc_14005E054
0x14005df88  mov     r9d, 6Eh ; 'n'
0x14005df8e  mov     dword ptr [rsp+78h+var_40], edi
0x14005df92  mov     dl, 5
0x14005df94  jmp     loc_14005E03A
0x14005df99  test    edi, edi
0x14005df9b  jnz     loc_14005E168
0x14005dfa1  cmp     [rbx+0F94h], sil
0x14005dfa8  jnz     short loc_14005DFB2
0x14005dfaa  mov     rcx, rbx; this
0x14005dfad  call    ?UpdateMatchingBSSList@CProcessRadioMeasurementRequest@@AEAAHXZ; CProcessRadioMeasurementRequest::UpdateMatchingBSSList(void)
0x14005dfb2  mov     eax, [rbx+0F90h]
0x14005dfb8  neg     eax
0x14005dfba  sbb     r8d, r8d
0x14005dfbd  and     r8d, 0FFFFFFEEh
0x14005dfc1  add     r8d, 14h
0x14005dfc5  mov     [rbx+0FC0h], r8d
0x14005dfcc  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005dfd3  jz      short loc_14005E010
0x14005dfd5  mov     ecx, [rbx+0FBCh]
0x14005dfdb  xor     edx, edx
0x14005dfdd  mov     r9d, 6Bh ; 'k'
0x14005dfe3  lea     eax, [rcx-1]
0x14005dfe6  add     eax, r8d
0x14005dfe9  div     r8d
0x14005dfec  mov     dl, 4
0x14005dfee  mov     dword ptr [rsp+78h+var_40], eax
0x14005dff2  mov     [rsp+78h+var_48], r8d
0x14005dff7  mov     dword ptr [rsp+78h+var_50], ecx
0x14005dffb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e002  mov     [rsp+78h+var_58], r14
0x14005e007  mov     rcx, [rcx+40h]
0x14005e00b  call    WPP_RECORDER_SF_dDd
0x14005e010  mov     rcx, rbx; this
0x14005e013  call    ?StartSendResponseJob@CProcessRadioMeasurementRequest@@AEAAHXZ; CProcessRadioMeasurementRequest::StartSendResponseJob(void)
0x14005e018  mov     edi, eax
0x14005e01a  test    eax, eax
0x14005e01c  jz      short loc_14005E068
0x14005e01e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005e025  jz      short loc_14005E054
0x14005e027  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e02e  mov     r9d, 6Ch ; 'l'
0x14005e034  mov     dword ptr [rsp+78h+var_40], eax
0x14005e038  mov     dl, 2
0x14005e03a  mov     eax, [rbx+10h]
0x14005e03d  mov     rcx, [rcx+40h]
0x14005e041  mov     [rsp+78h+var_48], eax
0x14005e045  mov     [rsp+78h+var_50], rbx
0x14005e04a  mov     [rsp+78h+var_58], r14
0x14005e04f  call    WPP_RECORDER_SF_qDD
0x14005e054  mov     edx, edi; int
0x14005e056  mov     dword ptr [rbx+218h], 4
0x14005e060  mov     rcx, rbx; this
0x14005e063  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x14005e068  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005e06f  jz      short loc_14005E0AA
0x14005e071  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e078  cmp     byte ptr [rcx+29h], 5
0x14005e07c  jnb     short loc_14005E084
0x14005e07e  cmp     [rcx+48h], si
0x14005e082  jz      short loc_14005E0AA
0x14005e084  mov     eax, [rbx+10h]
0x14005e087  mov     r9d, 6Fh ; 'o'
0x14005e08d  mov     rcx, [rcx+40h]
0x14005e091  mov     dl, 5
0x14005e093  mov     dword ptr [rsp+78h+var_40], edi
0x14005e097  mov     [rsp+78h+var_48], eax
0x14005e09b  mov     [rsp+78h+var_50], rbx
0x14005e0a0  mov     [rsp+78h+var_58], r14
0x14005e0a5  call    WPP_RECORDER_SF_qDD
0x14005e0aa  add     rsp, 50h
0x14005e0ae  pop     r14
0x14005e0b0  pop     rdi
0x14005e0b1  pop     rsi
0x14005e0b2  pop     rbp
0x14005e0b3  pop     rbx
0x14005e0b4  retn
0x14005e0b6  mov     rcx, rbx; this
0x14005e0b9  call    ?ParseMeasurementRequestMessage@CProcessRadioMeasurementRequest@@AEAAHXZ; CProcessRadioMeasurementRequest::ParseMeasurementRequestMessage(void)
0x14005e0be  mov     edi, eax
0x14005e0c0  test    eax, eax
0x14005e0c2  jz      short loc_14005E0FF
0x14005e0c4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005e0cb  jz      short loc_14005E054
0x14005e0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e0d4  mov     r9d, 68h ; 'h'
0x14005e0da  mov     dword ptr [rsp+78h+var_40], eax
0x14005e0de  mov     dl, 2
0x14005e0e0  mov     eax, [rbx+10h]
0x14005e0e3  mov     [rsp+78h+var_48], eax
0x14005e0e7  mov     rcx, [rcx+40h]
0x14005e0eb  mov     [rsp+78h+var_50], rbx
0x14005e0f0  mov     [rsp+78h+var_58], r14
0x14005e0f5  call    WPP_RECORDER_SF_qDD
0x14005e0fa  jmp     loc_14005E054
0x14005e0ff  cmp     byte ptr [rbx+0F4Fh], 1
0x14005e106  jnz     loc_14005DFA1
0x14005e10c  cmp     [rbx+0F94h], sil
0x14005e113  jnz     loc_14005DFB2
0x14005e119  mov     rcx, rbx; this
0x14005e11c  call    ?StartBeaconReportScanJob@CProcessRadioMeasurementRequest@@AEAAHXZ; CProcessRadioMeasurementRequest::StartBeaconReportScanJob(void)
0x14005e121  mov     edi, eax
0x14005e123  test    eax, eax
0x14005e125  jz      loc_14005E068
0x14005e12b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005e132  jz      short loc_14005E161
0x14005e134  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e13b  mov     r9d, 69h ; 'i'
0x14005e141  mov     dword ptr [rsp+78h+var_40], eax
0x14005e145  mov     dl, 2
0x14005e147  mov     eax, [rbx+10h]
0x14005e14a  mov     [rsp+78h+var_48], eax
0x14005e14e  mov     rcx, [rcx+40h]
0x14005e152  mov     [rsp+78h+var_50], rbx
0x14005e157  mov     [rsp+78h+var_58], r14
0x14005e15c  call    WPP_RECORDER_SF_qDD
0x14005e161  or      byte ptr [rbx+0F94h], 2
0x14005e168  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14005e16f  jz      short loc_14005E19E
0x14005e171  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e178  mov     r9d, 6Ah ; 'j'
0x14005e17e  mov     eax, [rbx+10h]
0x14005e181  mov     dl, 2
0x14005e183  mov     dword ptr [rsp+78h+var_40], edi
0x14005e187  mov     [rsp+78h+var_48], eax
0x14005e18b  mov     rcx, [rcx+40h]
0x14005e18f  mov     [rsp+78h+var_50], rbx
0x14005e194  mov     [rsp+78h+var_58], r14
0x14005e199  call    WPP_RECORDER_SF_qDD
0x14005e19e  or      byte ptr [rbx+0F94h], 2
0x14005e1a5  jmp     loc_14005DFB2
```
