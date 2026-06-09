# CSetPowerJob::OnJobStepCompleted(int,void *)

- ea: `0x14006d380`
- end: `0x14006d6a8`
- name: `?OnJobStepCompleted@CSetPowerJob@@UEAAXHPEAX@Z`
- size: `808`
- prototype: `void __fastcall(CSetPowerJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x140012f80`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14005362c`
- `0x14006bbdc`
- `0x14006bd60`
- `0x14006c354`
- `0x14006d380`
- `0x14006dcb4`
- `0x14006df5c`
- `0x14006e514`
- `0x140083da4`

## pseudocode

```c
void __fastcall CSetPowerJob::OnJobStepCompleted(CSetPowerJob *this, __int64 a2, void *a3, int a4)
{
  int v4; // edi
  int v5; // esi
  int v7; // edx
  int v8; // eax
  int v9; // r9d
  struct CPort *NextNonStaPort; // rax
  int started; // eax
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // eax
  CPort *v16; // rcx
  __int64 v17; // [rsp+28h] [rbp-50h]

  v4 = a2;
  v5 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      50,
      (__int64)WPP_e7ec3f534b343484c256e8aee299bf69_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  switch ( *((_DWORD *)this + 1308) )
  {
    case 1:
      v12 = *((_DWORD *)this + 144);
      if ( v12 == 6 )
      {
        *(_BYTE *)(*((_QWORD *)this + 653) + 540LL) = 0;
        v13 = *((_QWORD *)this + 653);
        *(_OWORD *)(v13 + 520) = 0;
        *(_DWORD *)(v13 + 536) = 0;
      }
      else if ( v12 != 10 )
      {
        goto LABEL_43;
      }
      v14 = *((_QWORD *)this + 67);
      *((_DWORD *)this + 144) = 11;
      *(_BYTE *)(v14 + 4658) = 0;
      v15 = 0;
      *((_DWORD *)this + 1393) = 0;
      do
      {
        v16 = *(CPort **)(*((_QWORD *)this + 67) + 8LL * v15 + 4736);
        if ( v16 )
          CPort::HandleRoamAtResume(v16);
        v15 = *((_DWORD *)this + 1393) + 1;
        *((_DWORD *)this + 1393) = v15;
      }
      while ( v15 < 6 );
      goto LABEL_43;
    case 3:
      v8 = *((_DWORD *)this + 144);
      if ( v8 )
      {
        if ( v8 != 1 )
        {
          if ( v8 != 3 && v8 != 6 )
            break;
LABEL_43:
          CJobBase::CompleteJob(this, 0, (__int64)a3, a4);
          break;
        }
      }
      else
      {
        if ( !(unsigned int)Feature_57277348__private_IsEnabledDeviceUsageNoInline(
                              (unsigned int)(*((_DWORD *)this + 1308) - 3),
                              a2,
                              a3)
          && *(_DWORD *)(*((_QWORD *)this + 67) + 3560LL) == 2
          && (*(_DWORD *)(*((_QWORD *)this + 653) + 532LL) & 0x10) != 0 )
        {
          *((_DWORD *)this + 144) = 6;
          CJobBase::CompleteJob(this, 0, (__int64)a3, v9);
        }
        *((_DWORD *)this + 144) = 1;
      }
      if ( *((_DWORD *)this + 1304) )
        break;
      NextNonStaPort = CSetPowerJob::GetNextNonStaPort(this);
      if ( NextNonStaPort )
      {
        *((_DWORD *)this + 144) = 1;
        started = CSetPowerJob::StartDot11ResetSubJob(this, NextNonStaPort);
        v5 = started;
        if ( !started )
          break;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v17) = started;
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            1,
            51,
            (__int64)WPP_e7ec3f534b343484c256e8aee299bf69_Traceguids,
            v17);
        }
      }
      v5 = CSetPowerJob::StartReplumbNloCmd(this, *((struct CPort **)this + 653));
      if ( !v5 )
      {
        *((_DWORD *)this + 144) = 3;
        break;
      }
      *((_DWORD *)this + 144) = 6;
      goto LABEL_43;
    case 4:
      if ( !*((_DWORD *)this + 144) )
        *((_DWORD *)this + 144) = 7;
      v7 = *(unsigned __int8 *)(*((_QWORD *)this + 653) + 540LL);
      if ( (_BYTE)v7 && *(_BYTE *)(*((_QWORD *)this + 67) + 3553LL) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = 4;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            1,
            52,
            (__int64)WPP_e7ec3f534b343484c256e8aee299bf69_Traceguids);
        }
        CSetPowerJob::D3DefaultPortArmedStepCompleted(this, v4, a3);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_ll(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            (_DWORD)a3,
            53,
            (__int64)WPP_e7ec3f534b343484c256e8aee299bf69_Traceguids,
            v7,
            *(_BYTE *)(*((_QWORD *)this + 67) + 3553LL));
        CSetPowerJob::D3DefaultPortNoArmStepCompleted(this, v4, a3);
      }
      break;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      (_DWORD)a3,
      54,
      (__int64)WPP_e7ec3f534b343484c256e8aee299bf69_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v5);
  }
}

```

## disassembly

```asm
0x14006d380  push    rbx
0x14006d382  push    rbp
0x14006d383  push    rsi
0x14006d384  push    rdi
0x14006d385  push    r14
0x14006d387  push    r15
0x14006d389  sub     rsp, 48h
0x14006d38d  xor     ebp, ebp
0x14006d38f  mov     edi, edx
0x14006d391  mov     esi, ebp
0x14006d393  mov     rbx, rcx
0x14006d396  lea     r14, WPP_RECORDER_INITIALIZED
0x14006d39d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14006d3a4  lea     r15, WPP_e7ec3f534b343484c256e8aee299bf69_Traceguids
0x14006d3ab  jz      short loc_14006D3E2
0x14006d3ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d3b4  cmp     byte ptr [rcx+29h], 5
0x14006d3b8  jnb     short loc_14006D3C0
0x14006d3ba  cmp     [rcx+48h], bp
0x14006d3be  jz      short loc_14006D3E2
0x14006d3c0  mov     eax, [rbx+10h]
0x14006d3c3  mov     r9d, 32h ; '2'
0x14006d3c9  mov     rcx, [rcx+40h]
0x14006d3cd  mov     dl, 5
0x14006d3cf  mov     [rsp+78h+var_48], eax
0x14006d3d3  mov     [rsp+78h+var_50], rbx
0x14006d3d8  mov     [rsp+78h+var_58], r15
0x14006d3dd  call    WPP_RECORDER_SF_qD
0x14006d3e2  mov     ecx, [rbx+1470h]
0x14006d3e8  sub     ecx, 1
0x14006d3eb  jz      loc_14006D5C7
0x14006d3f1  sub     ecx, 2
0x14006d3f4  jz      loc_14006D4B9
0x14006d3fa  cmp     ecx, 1
0x14006d3fd  jnz     loc_14006D658
0x14006d403  cmp     [rbx+240h], ebp
0x14006d409  jnz     short loc_14006D415
0x14006d40b  mov     dword ptr [rbx+240h], 7
0x14006d415  mov     rax, [rbx+1468h]
0x14006d41c  movzx   edx, byte ptr [rax+21Ch]
0x14006d423  test    dl, dl
0x14006d425  jz      short loc_14006D470
0x14006d427  mov     rax, [rbx+218h]
0x14006d42e  cmp     [rax+0DE1h], bpl
0x14006d435  jz      short loc_14006D470
0x14006d437  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14006d43e  jz      short loc_14006D461
0x14006d440  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d447  mov     r9d, 34h ; '4'
0x14006d44d  mov     dl, 4
0x14006d44f  mov     [rsp+78h+var_58], r15
0x14006d454  mov     rcx, [rcx+40h]
0x14006d458  lea     r8d, [r9-33h]
0x14006d45c  call    WPP_RECORDER_SF_
0x14006d461  mov     edx, edi; int
0x14006d463  mov     rcx, rbx; this
0x14006d466  call    ?D3DefaultPortArmedStepCompleted@CSetPowerJob@@AEAAXHPEAX@Z; CSetPowerJob::D3DefaultPortArmedStepCompleted(int,void *)
0x14006d46b  jmp     loc_14006D658
0x14006d470  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14006d477  jz      short loc_14006D4AA
0x14006d479  mov     rax, [rbx+218h]
0x14006d480  mov     r9d, 35h ; '5'
0x14006d486  movzx   ecx, byte ptr [rax+0DE1h]
0x14006d48d  mov     [rsp+78h+var_48], ecx
0x14006d491  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d498  mov     dword ptr [rsp+78h+var_50], edx
0x14006d49c  mov     [rsp+78h+var_58], r15
0x14006d4a1  mov     rcx, [rcx+40h]
0x14006d4a5  call    WPP_RECORDER_SF_ll
0x14006d4aa  mov     edx, edi; int
0x14006d4ac  mov     rcx, rbx; this
0x14006d4af  call    ?D3DefaultPortNoArmStepCompleted@CSetPowerJob@@AEAAXHPEAX@Z; CSetPowerJob::D3DefaultPortNoArmStepCompleted(int,void *)
0x14006d4b4  jmp     loc_14006D658
0x14006d4b9  mov     eax, [rbx+240h]
0x14006d4bf  test    eax, eax
0x14006d4c1  jnz     short loc_14006D50E
0x14006d4c3  call    Feature_57277348__private_IsEnabledDeviceUsageNoInline
0x14006d4c8  test    eax, eax
0x14006d4ca  jnz     short loc_14006D502
0x14006d4cc  mov     rax, [rbx+218h]
0x14006d4d3  cmp     dword ptr [rax+0DE8h], 2
0x14006d4da  jnz     short loc_14006D502
0x14006d4dc  mov     rax, [rbx+1468h]
0x14006d4e3  mov     ecx, [rax+214h]
0x14006d4e9  test    cl, 10h
0x14006d4ec  jz      short loc_14006D502
0x14006d4ee  xor     edx, edx; int
0x14006d4f0  mov     dword ptr [rbx+240h], 6
0x14006d4fa  mov     rcx, rbx; this
0x14006d4fd  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x14006d502  mov     dword ptr [rbx+240h], 1
0x14006d50c  jmp     short loc_14006D517
0x14006d50e  cmp     eax, 1
0x14006d511  jnz     loc_14006D5B0
0x14006d517  cmp     [rbx+1460h], ebp
0x14006d51d  jnz     loc_14006D658
0x14006d523  mov     rcx, rbx; this
0x14006d526  call    ?GetNextNonStaPort@CSetPowerJob@@AEAAPEAVCPort@@XZ; CSetPowerJob::GetNextNonStaPort(void)
0x14006d52b  test    rax, rax
0x14006d52e  jz      short loc_14006D57D
0x14006d530  mov     rdx, rax; struct CPort *
0x14006d533  mov     dword ptr [rbx+240h], 1
0x14006d53d  mov     rcx, rbx; this
0x14006d540  call    ?StartDot11ResetSubJob@CSetPowerJob@@AEAAHPEAVCPort@@@Z; CSetPowerJob::StartDot11ResetSubJob(CPort *)
0x14006d545  mov     esi, eax
0x14006d547  test    eax, eax
0x14006d549  jz      loc_14006D658
0x14006d54f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14006d556  jz      short loc_14006D57D
0x14006d558  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d55f  mov     r9d, 33h ; '3'
0x14006d565  mov     dword ptr [rsp+78h+var_50], eax
0x14006d569  mov     dl, 2
0x14006d56b  mov     [rsp+78h+var_58], r15
0x14006d570  mov     rcx, [rcx+40h]
0x14006d574  lea     r8d, [r9-32h]
0x14006d578  call    WPP_RECORDER_SF_d
0x14006d57d  mov     rdx, [rbx+1468h]; struct CPort *
0x14006d584  mov     rcx, rbx; this
0x14006d587  call    ?StartReplumbNloCmd@CSetPowerJob@@AEAAHPEAVCPort@@@Z; CSetPowerJob::StartReplumbNloCmd(CPort *)
0x14006d58c  mov     esi, eax
0x14006d58e  test    eax, eax
0x14006d590  jnz     short loc_14006D5A1
0x14006d592  mov     dword ptr [rbx+240h], 3
0x14006d59c  jmp     loc_14006D658
0x14006d5a1  mov     dword ptr [rbx+240h], 6
0x14006d5ab  jmp     loc_14006D64E
0x14006d5b0  cmp     eax, 3
0x14006d5b3  jz      loc_14006D64E
0x14006d5b9  cmp     eax, 6
0x14006d5bc  jnz     loc_14006D658
0x14006d5c2  jmp     loc_14006D64E
0x14006d5c7  mov     eax, [rbx+240h]
0x14006d5cd  cmp     eax, 6
0x14006d5d0  jnz     short loc_14006D5FB
0x14006d5d2  mov     rax, [rbx+1468h]
0x14006d5d9  xorps   xmm0, xmm0
0x14006d5dc  xor     ecx, ecx
0x14006d5de  mov     [rax+21Ch], bpl
0x14006d5e5  mov     rax, [rbx+1468h]
0x14006d5ec  movups  xmmword ptr [rax+208h], xmm0
0x14006d5f3  mov     [rax+218h], ecx
0x14006d5f9  jmp     short loc_14006D600
0x14006d5fb  cmp     eax, 0Ah
0x14006d5fe  jnz     short loc_14006D64E
0x14006d600  mov     rax, [rbx+218h]
0x14006d607  mov     dword ptr [rbx+240h], 0Bh
0x14006d611  mov     [rax+1232h], bpl
0x14006d618  mov     eax, ebp
0x14006d61a  mov     [rbx+15C4h], ebp
0x14006d620  mov     ecx, eax
0x14006d622  mov     rax, [rbx+218h]
0x14006d629  mov     rcx, [rax+rcx*8+1280h]; this
0x14006d631  test    rcx, rcx
0x14006d634  jz      short loc_14006D63B
0x14006d636  call    ?HandleRoamAtResume@CPort@@QEAAXXZ; CPort::HandleRoamAtResume(void)
0x14006d63b  mov     eax, [rbx+15C4h]
0x14006d641  inc     eax
0x14006d643  mov     [rbx+15C4h], eax
0x14006d649  cmp     eax, 6
0x14006d64c  jb      short loc_14006D620
0x14006d64e  xor     edx, edx; int
0x14006d650  mov     rcx, rbx; this
0x14006d653  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x14006d658  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14006d65f  jz      short loc_14006D69A
0x14006d661  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d668  cmp     byte ptr [rcx+29h], 5
0x14006d66c  jnb     short loc_14006D674
0x14006d66e  cmp     [rcx+48h], bp
0x14006d672  jz      short loc_14006D69A
0x14006d674  mov     eax, [rbx+10h]
0x14006d677  mov     r9d, 36h ; '6'
0x14006d67d  mov     rcx, [rcx+40h]
0x14006d681  mov     dl, 5
0x14006d683  mov     [rsp+78h+var_40], esi
0x14006d687  mov     [rsp+78h+var_48], eax
0x14006d68b  mov     [rsp+78h+var_50], rbx
0x14006d690  mov     [rsp+78h+var_58], r15
0x14006d695  call    WPP_RECORDER_SF_qDD
0x14006d69a  add     rsp, 48h
0x14006d69e  pop     r15
0x14006d6a0  pop     r14
0x14006d6a2  pop     rdi
0x14006d6a3  pop     rsi
0x14006d6a4  pop     rbp
0x14006d6a5  pop     rbx
0x14006d6a6  retn
```
