# CRequestFtmChildJob::OnJobStepCompleted(int,void *)

- ea: `0x14009f9c0`
- end: `0x14009fca2`
- name: `?OnJobStepCompleted@CRequestFtmChildJob@@UEAAXHPEAX@Z`
- size: `738`
- prototype: `void __fastcall(CRequestFtmChildJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14001e2c0`
- `0x14001eed0`
- `0x14002073c`
- `0x140020860`
- `0x1400416ec`
- `0x14009f230`
- `0x14009f274`
- `0x14009f9c0`
- `0x1400a005c`

## pseudocode

```c
void __fastcall CRequestFtmChildJob::OnJobStepCompleted(CRequestFtmChildJob *this, int a2, void *a3)
{
  int StatusFromTaskOutput; // edi
  int v5; // r9d
  int OutputBuffer; // eax
  int v7; // edx
  int v8; // r8d
  __int64 v9; // [rsp+38h] [rbp-28h]
  unsigned __int8 *v10; // [rsp+40h] [rbp-20h] BYREF
  int v11; // [rsp+48h] [rbp-18h] BYREF
  __int64 v12; // [rsp+50h] [rbp-10h]
  char v13; // [rsp+58h] [rbp-8h]
  int v14; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v15; // [rsp+A8h] [rbp+48h] BYREF

  StatusFromTaskOutput = a2;
  v14 = 0;
  v15 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        27,
        (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        28,
        (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        StatusFromTaskOutput);
    }
  }
  if ( *((_BYTE *)this + 1097) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        29,
        (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    StatusFromTaskOutput = -2147478641;
    goto LABEL_38;
  }
  if ( !*((_BYTE *)this + 1096) )
  {
    if ( StatusFromTaskOutput )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_38;
      v5 = 31;
      goto LABEL_20;
    }
    StatusFromTaskOutput = CMessageHelper::GetStatusFromTaskOutput(
                             (CRequestFtmChildJob *)((char *)this + 560),
                             (unsigned int *)&v14);
    if ( StatusFromTaskOutput )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_38;
      OutputBuffer = v14;
      v5 = 32;
    }
    else
    {
      StatusFromTaskOutput = v14;
      if ( v14 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_38;
        v5 = 33;
LABEL_20:
        LODWORD(v9) = StatusFromTaskOutput;
LABEL_37:
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          (_DWORD)a3,
          v5,
          (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v9);
        goto LABEL_38;
      }
      OutputBuffer = Task::get_OutputBuffer((CRequestFtmChildJob *)((char *)this + 560), &v15, &v10);
      StatusFromTaskOutput = OutputBuffer;
      if ( OutputBuffer )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_38;
        v5 = 34;
      }
      else
      {
        OutputBuffer = ParseWdiIndicationRequestFtmCompleteFromIhv(
                         v15 - 48,
                         v10 + 48,
                         *((_QWORD *)this + 68) + 5384LL,
                         &v11);
        StatusFromTaskOutput = OutputBuffer;
        if ( OutputBuffer )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_38;
          v5 = 35;
        }
        else
        {
          OutputBuffer = CRequestFtmChildJob::ProcessFtmResponse(
                           this,
                           (struct _WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *)&v11,
                           (unsigned int)a3);
          StatusFromTaskOutput = OutputBuffer;
          if ( !OutputBuffer || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_38;
          v5 = 36;
        }
      }
    }
    LODWORD(v9) = OutputBuffer;
    goto LABEL_37;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      30,
      (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  StatusFromTaskOutput = -1073676276;
LABEL_38:
  CRequestFtmChildJob::CleanupAndCompleteJob(this, StatusFromTaskOutput);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v7) = 5;
    LODWORD(v9) = StatusFromTaskOutput;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      37,
      (__int64)WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v9);
  }
  ArrayOfElements<_WDI_FTM_RESPONSE_CONTAINER>::Cleanup(&v11);
}

```

## disassembly

```asm
0x14009f9c0  mov     [rsp-28h+arg_8], rbx
0x14009f9c5  mov     [rsp-28h+arg_10], rsi
0x14009f9ca  push    rbp
0x14009f9cb  push    rdi
0x14009f9cc  push    r12
0x14009f9ce  push    r14
0x14009f9d0  push    r15
0x14009f9d2  mov     rbp, rsp
0x14009f9d5  sub     rsp, 60h
0x14009f9d9  xor     r14d, r14d
0x14009f9dc  mov     edi, edx
0x14009f9de  mov     [rbp+arg_0], r14d
0x14009f9e2  mov     rbx, rcx
0x14009f9e5  mov     [rbp+arg_18], r14d
0x14009f9e9  mov     [rbp+var_20], r14
0x14009f9ed  mov     [rbp+var_18], r14d
0x14009f9f1  mov     [rbp+var_10], r14
0x14009f9f5  mov     [rbp+var_8], r14b
0x14009f9f9  lea     r15, WPP_RECORDER_INITIALIZED
0x14009fa00  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fa07  lea     r12, WPP_4a7a4caad0033b02f1cef042562e8ce8_Traceguids
0x14009fa0e  jz      short loc_14009FA89
0x14009fa10  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fa17  cmp     byte ptr [rcx+29h], 5
0x14009fa1b  jnb     short loc_14009FA24
0x14009fa1d  cmp     [rcx+48h], r14w
0x14009fa22  jz      short loc_14009FA46
0x14009fa24  mov     eax, [rbx+10h]
0x14009fa27  mov     r9d, 1Bh
0x14009fa2d  mov     rcx, [rcx+40h]
0x14009fa31  mov     dl, 5
0x14009fa33  mov     [rsp+60h+var_30], eax
0x14009fa37  mov     [rsp+60h+var_38], rbx
0x14009fa3c  mov     [rsp+60h+var_40], r12
0x14009fa41  call    WPP_RECORDER_SF_qD
0x14009fa46  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fa4d  jz      short loc_14009FA89
0x14009fa4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fa56  cmp     byte ptr [rcx+29h], 5
0x14009fa5a  jnb     short loc_14009FA63
0x14009fa5c  cmp     [rcx+48h], r14w
0x14009fa61  jz      short loc_14009FA89
0x14009fa63  mov     eax, [rbx+10h]
0x14009fa66  mov     r9d, 1Ch
0x14009fa6c  mov     rcx, [rcx+40h]
0x14009fa70  mov     dl, 5
0x14009fa72  mov     dword ptr [rsp+60h+var_28], edi
0x14009fa76  mov     [rsp+60h+var_30], eax
0x14009fa7a  mov     [rsp+60h+var_38], rbx
0x14009fa7f  mov     [rsp+60h+var_40], r12
0x14009fa84  call    WPP_RECORDER_SF_qDD
0x14009fa89  cmp     [rbx+449h], r14b
0x14009fa90  jz      short loc_14009FACE
0x14009fa92  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fa99  jz      short loc_14009FAC4
0x14009fa9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14009faa2  mov     r9d, 1Dh
0x14009faa8  mov     eax, [rbx+10h]
0x14009faab  mov     dl, 4
0x14009faad  mov     [rsp+60h+var_30], eax
0x14009fab1  mov     [rsp+60h+var_38], rbx
0x14009fab6  mov     rcx, [rcx+40h]
0x14009faba  mov     [rsp+60h+var_40], r12
0x14009fabf  call    WPP_RECORDER_SF_qD
0x14009fac4  mov     edi, 8000138Fh
0x14009fac9  jmp     loc_14009FC32
0x14009face  cmp     [rbx+448h], r14b
0x14009fad5  jz      short loc_14009FB13
0x14009fad7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fade  jz      short loc_14009FB09
0x14009fae0  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fae7  mov     r9d, 1Eh
0x14009faed  mov     eax, [rbx+10h]
0x14009faf0  mov     dl, 4
0x14009faf2  mov     [rsp+60h+var_30], eax
0x14009faf6  mov     [rsp+60h+var_38], rbx
0x14009fafb  mov     rcx, [rcx+40h]
0x14009faff  mov     [rsp+60h+var_40], r12
0x14009fb04  call    WPP_RECORDER_SF_qD
0x14009fb09  mov     edi, 0C001000Ch
0x14009fb0e  jmp     loc_14009FC32
0x14009fb13  test    edi, edi
0x14009fb15  jz      short loc_14009FB33
0x14009fb17  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fb1e  jz      loc_14009FC32
0x14009fb24  mov     r9d, 1Fh
0x14009fb2a  mov     dword ptr [rsp+60h+var_28], edi
0x14009fb2e  jmp     loc_14009FC0F
0x14009fb33  lea     rsi, [rbx+230h]
0x14009fb3a  mov     rcx, rsi; struct Task *
0x14009fb3d  lea     rdx, [rbp+arg_0]; int *
0x14009fb41  call    ?GetStatusFromTaskOutput@CMessageHelper@@SAHPEAVTask@@PEAH@Z; CMessageHelper::GetStatusFromTaskOutput(Task *,int *)
0x14009fb46  mov     edi, eax
0x14009fb48  test    eax, eax
0x14009fb4a  jz      short loc_14009FB67
0x14009fb4c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fb53  jz      loc_14009FC32
0x14009fb59  mov     eax, [rbp+arg_0]
0x14009fb5c  mov     r9d, 20h ; ' '
0x14009fb62  jmp     loc_14009FC0B
0x14009fb67  mov     edi, [rbp+arg_0]
0x14009fb6a  test    edi, edi
0x14009fb6c  jz      short loc_14009FB83
0x14009fb6e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fb75  jz      loc_14009FC32
0x14009fb7b  mov     r9d, 21h ; '!'
0x14009fb81  jmp     short loc_14009FB2A
0x14009fb83  lea     r8, [rbp+var_20]; unsigned __int8 **
0x14009fb87  mov     rcx, rsi; this
0x14009fb8a  lea     rdx, [rbp+arg_18]; unsigned int *
0x14009fb8e  call    ?get_OutputBuffer@Task@@QEAAHPEAKPEAPEAE@Z; Task::get_OutputBuffer(ulong *,uchar * *)
0x14009fb93  mov     edi, eax
0x14009fb95  test    eax, eax
0x14009fb97  jz      short loc_14009FBAE
0x14009fb99  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fba0  jz      loc_14009FC32
0x14009fba6  mov     r9d, 22h ; '"'
0x14009fbac  jmp     short loc_14009FC0B
0x14009fbae  mov     ecx, [rbp+arg_18]
0x14009fbb1  lea     r9, [rbp+var_18]
0x14009fbb5  mov     r8, [rbx+220h]
0x14009fbbc  add     ecx, 0FFFFFFD0h
0x14009fbbf  mov     rdx, [rbp+var_20]
0x14009fbc3  add     r8, 1508h
0x14009fbca  add     rdx, 30h ; '0'
0x14009fbce  call    ParseWdiIndicationRequestFtmCompleteFromIhv
0x14009fbd3  mov     edi, eax
0x14009fbd5  test    eax, eax
0x14009fbd7  jz      short loc_14009FBEA
0x14009fbd9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fbe0  jz      short loc_14009FC32
0x14009fbe2  mov     r9d, 23h ; '#'
0x14009fbe8  jmp     short loc_14009FC0B
0x14009fbea  lea     rdx, [rbp+var_18]; struct _WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *
0x14009fbee  mov     rcx, rbx; this
0x14009fbf1  call    ?ProcessFtmResponse@CRequestFtmChildJob@@AEAAHPEAU_WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS@@@Z; CRequestFtmChildJob::ProcessFtmResponse(_WDI_INDICATION_REQUEST_FTM_COMPLETE_PARAMETERS *)
0x14009fbf6  mov     edi, eax
0x14009fbf8  test    eax, eax
0x14009fbfa  jz      short loc_14009FC32
0x14009fbfc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fc03  jz      short loc_14009FC32
0x14009fc05  mov     r9d, 24h ; '$'
0x14009fc0b  mov     dword ptr [rsp+60h+var_28], eax
0x14009fc0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fc16  mov     dl, 2
0x14009fc18  mov     eax, [rbx+10h]
0x14009fc1b  mov     [rsp+60h+var_30], eax
0x14009fc1f  mov     [rsp+60h+var_38], rbx
0x14009fc24  mov     rcx, [rcx+40h]
0x14009fc28  mov     [rsp+60h+var_40], r12
0x14009fc2d  call    WPP_RECORDER_SF_qDD
0x14009fc32  mov     edx, edi; int
0x14009fc34  mov     rcx, rbx; this
0x14009fc37  call    ?CleanupAndCompleteJob@CRequestFtmChildJob@@AEAAXH@Z; CRequestFtmChildJob::CleanupAndCompleteJob(int)
0x14009fc3c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14009fc43  jz      short loc_14009FC7F
0x14009fc45  mov     rcx, cs:WPP_GLOBAL_Control
0x14009fc4c  cmp     byte ptr [rcx+29h], 5
0x14009fc50  jnb     short loc_14009FC59
0x14009fc52  cmp     [rcx+48h], r14w
0x14009fc57  jz      short loc_14009FC7F
0x14009fc59  mov     eax, [rbx+10h]
0x14009fc5c  mov     r9d, 25h ; '%'
0x14009fc62  mov     rcx, [rcx+40h]
0x14009fc66  mov     dl, 5
0x14009fc68  mov     dword ptr [rsp+60h+var_28], edi
0x14009fc6c  mov     [rsp+60h+var_30], eax
0x14009fc70  mov     [rsp+60h+var_38], rbx
0x14009fc75  mov     [rsp+60h+var_40], r12
0x14009fc7a  call    WPP_RECORDER_SF_qDD
0x14009fc7f  lea     rcx, [rbp+var_18]
0x14009fc83  call    ?Cleanup@?$ArrayOfElements@U_WDI_FTM_RESPONSE_CONTAINER@@@@QEAAXXZ; ArrayOfElements<_WDI_FTM_RESPONSE_CONTAINER>::Cleanup(void)
0x14009fc88  lea     r11, [rsp+60h+var_s0]
0x14009fc8d  mov     rbx, [r11+38h]
0x14009fc91  mov     rsi, [r11+40h]
0x14009fc95  mov     rsp, r11
0x14009fc98  pop     r15
0x14009fc9a  pop     r14
0x14009fc9c  pop     r12
0x14009fc9e  pop     rdi
0x14009fc9f  pop     rbp
0x14009fca0  retn
```
