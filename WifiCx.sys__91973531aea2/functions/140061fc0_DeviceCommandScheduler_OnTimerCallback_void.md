# DeviceCommandScheduler::OnTimerCallback(void *)

- ea: `0x140061fc0`
- end: `0x14006234c`
- name: `?OnTimerCallback@DeviceCommandScheduler@@UEAAXPEAX@Z`
- size: `908`
- prototype: `void __fastcall(DeviceCommandScheduler *__hidden this, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000688c`
- `0x14000c778`
- `0x14000d054`
- `0x14001b120`
- `0x14001e81c`
- `0x14001ed44`
- `0x140022cb4`
- `0x1400244e0`
- `0x140024a20`
- `0x140050574`
- `0x140054650`
- `0x140055d18`
- `0x140058a10`
- `0x140058cdc`
- `0x140061fc0`
- `0x1400dfd40`

## import_xrefs

- `NDIS!NdisWriteErrorLogEntry` at `0x140062094`
- `NDIS!NdisWriteErrorLogEntry` at `0x140062094`

## pseudocode

```c
void __fastcall DeviceCommandScheduler::OnTimerCallback(DeviceCommandScheduler *this, void *a2, int a3)
{
  struct CJobBase *v4; // r12
  unsigned int *v5; // r15
  void *AdapterNdisHandleFromNdisPortNumber; // rax
  CPropertyCache *v7; // rax
  char PropertyBooleanOrDefault; // al
  __int64 v9; // rcx
  struct DeviceCommand **v10; // rdi
  signed __int32 v11; // esi
  _DWORD *v12; // r14
  DeviceCommand *v13; // rcx
  int v14; // r8d
  int v15; // edx
  DeviceCommand *v16; // rcx
  int v17; // edx
  int v18; // r8d
  CAdapter *v19; // rcx
  unsigned int v20[2]; // [rsp+20h] [rbp-50h]
  _DWORD v21[2]; // [rsp+40h] [rbp-30h] BYREF
  int v22; // [rsp+48h] [rbp-28h]
  int v23; // [rsp+4Ch] [rbp-24h]
  int v24; // [rsp+50h] [rbp-20h]
  int v25; // [rsp+54h] [rbp-1Ch]
  __int64 v26; // [rsp+58h] [rbp-18h]
  __int16 v27; // [rsp+60h] [rbp-10h]
  int v28; // [rsp+68h] [rbp-8h]
  unsigned int v29; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v30; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int8 *v31; // [rsp+C8h] [rbp+58h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      38,
      (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids);
  }
  if ( !*((_QWORD *)this + 3) )
    goto LABEL_29;
  v4 = 0;
  v5 = (unsigned int *)((char *)this + 40);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      a3,
      39,
      (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
      *v5,
      *v5);
  AdapterNdisHandleFromNdisPortNumber = CAdapter::GetAdapterNdisHandleFromNdisPortNumber(*((CAdapter **)this + 20), 0);
  v20[0] = *v5;
  NdisWriteErrorLogEntry(AdapterNdisHandleFromNdisPortNumber, 0xC000138A, 2u, 1, *(_QWORD *)v20);
  v7 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 20) + 8LL) + 8LL))(*((_QWORD *)this + 20) + 8LL);
  PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(v7, 0x15u, 0);
  v9 = *((_QWORD *)this + 20);
  LOBYTE(v29) = PropertyBooleanOrDefault;
  _InterlockedAdd((volatile signed __int32 *)(v9 + 5360), 1u);
  CAdapter::TraceLoggingResetRecovery(
    *((CAdapter **)this + 20),
    1u,
    *v5,
    *(_DWORD *)(*((_QWORD *)this + 20) + 5360LL),
    *(_DWORD *)(*((_QWORD *)this + 20) + 5372LL),
    PropertyBooleanOrDefault);
  v10 = (struct DeviceCommand **)((char *)this + 24);
  if ( *v5 != 75 )
    v4 = (struct CJobBase *)*((_QWORD *)*v10 + 21);
  v11 = _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 20) + 5364LL));
  v12 = (_DWORD *)((char *)this + 36);
  if ( v11 == 1 )
  {
    CAdapter::TriggerControlPathDiagnostics(*((CAdapter **)this + 20), 1u, *v5);
    CAdapter::CollectDebugData(*((CAdapter **)this + 20), *v10, 0, v4);
    goto LABEL_12;
  }
  if ( !*v12 )
  {
LABEL_12:
    if ( *v5 == 75 || v4 && *((_DWORD *)v4 + 15) != 160 )
    {
      v13 = *v10;
      v22 &= 0xFFFFFFF8;
      v30 = 0;
      v31 = 0;
      v23 = 3;
      v26 = 0;
      DeviceCommand::get_InputBuffer(v13, &v30, &v31);
      if ( v31 && v30 >= 0x30 )
      {
        v15 = *(_DWORD *)v31;
        v24 = *((_DWORD *)v31 + 4);
        v27 = *((_WORD *)v31 + 16);
        v28 = *((_DWORD *)v31 + 10);
        v21[0] = v15;
      }
      else
      {
        LOBYTE(v15) = v21[0];
      }
      v21[1] = 48;
      v25 = -1073676280;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Ld(
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          v14,
          41,
          (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
          v15,
          v15);
      DeviceCommand::get_CommandType(*v10, (unsigned int *)this + 8);
      DeviceCommand::get_CommandToken(*v10, (unsigned int *)this + 9);
      DeviceCommandScheduler::CompleteSendCommand_PostHangCheck(
        (DeviceCommandScheduler *)((char *)this - 16),
        0x30u,
        (struct _WFC_MESSAGE_METADATA *)v21);
    }
    if ( v11 == 1 )
    {
      v19 = (CAdapter *)*((_QWORD *)this + 20);
      if ( *((_BYTE *)v19 + 4657) )
      {
        if ( !(_BYTE)v29 )
          CAdapter::ReenumerateFailedAdapter(v19);
      }
    }
    goto LABEL_29;
  }
  v16 = *v10;
  v29 = 0;
  DeviceCommand::get_CommandType(v16, &v29);
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return;
  LOBYTE(v17) = 2;
  WPP_RECORDER_SF_dDd(
    WPP_GLOBAL_Control->DeviceExtension,
    v17,
    v18,
    40,
    (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
    v11,
    v29,
    *v12);
LABEL_29:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      42,
      (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
      0);
  }
}

```

## disassembly

```asm
0x140061fc0  mov     [rsp-38h+arg_8], rbx
0x140061fc5  push    rbp
0x140061fc6  push    rsi
0x140061fc7  push    rdi
0x140061fc8  push    r12
0x140061fca  push    r13
0x140061fcc  push    r14
0x140061fce  push    r15
0x140061fd0  mov     rbp, rsp
0x140061fd3  sub     rsp, 70h
0x140061fd7  mov     rbx, rcx
0x140061fda  xor     eax, eax
0x140061fdc  lea     rcx, WPP_RECORDER_INITIALIZED
0x140061fe3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140061fea  lea     rdi, WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids
0x140061ff1  lea     r14d, [rax+1]
0x140061ff5  jz      short loc_14006202C
0x140061ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x140061ffe  cmp     byte ptr [rcx+29h], 5
0x140062002  jnb     short loc_14006200A
0x140062004  cmp     [rcx+48h], ax
0x140062008  jz      short loc_140062025
0x14006200a  mov     rcx, [rcx+40h]
0x14006200e  mov     r9d, 26h ; '&'
0x140062014  mov     r8d, r14d
0x140062017  mov     qword ptr [rsp+70h+var_50], rdi
0x14006201c  mov     dl, 5
0x14006201e  call    WPP_RECORDER_SF_
0x140062023  xor     eax, eax
0x140062025  lea     rcx, WPP_RECORDER_INITIALIZED
0x14006202c  cmp     [rbx+18h], rax
0x140062030  jz      loc_140062343
0x140062036  mov     r12, rax
0x140062039  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140062040  lea     r15, [rbx+28h]
0x140062044  jz      short loc_14006206E
0x140062046  mov     eax, [r15]
0x140062049  mov     r9d, 27h ; '''
0x14006204f  mov     rcx, cs:WPP_GLOBAL_Control
0x140062056  mov     dl, 2
0x140062058  mov     [rsp+70h+var_40], eax
0x14006205c  mov     dword ptr [rsp+70h+var_48], eax
0x140062060  mov     qword ptr [rsp+70h+var_50], rdi
0x140062065  mov     rcx, [rcx+40h]
0x140062069  call    WPP_RECORDER_SF_Ld
0x14006206e  mov     rcx, [rbx+0A0h]; this
0x140062075  xor     edx, edx; unsigned int
0x140062077  call    ?GetAdapterNdisHandleFromNdisPortNumber@CAdapter@@QEAAPEAXK@Z; CAdapter::GetAdapterNdisHandleFromNdisPortNumber(ulong)
0x14006207c  mov     ecx, [r15]
0x14006207f  mov     r9d, r14d
0x140062082  mov     [rsp+70h+var_50], ecx
0x140062086  mov     edx, 0C000138Ah; ErrorCode
0x14006208b  mov     rcx, rax; NdisAdapterHandle
0x14006208e  mov     r8d, 2; NumberOfErrorValues
0x140062094  call    cs:__imp_NdisWriteErrorLogEntry
0x14006209b  nop     dword ptr [rax+rax+00h]
0x1400620a0  mov     rcx, [rbx+0A0h]
0x1400620a7  add     rcx, 8
0x1400620ab  mov     rax, [rcx]
0x1400620ae  mov     rax, [rax+8]
0x1400620b2  call    _guard_dispatch_icall
0x1400620b7  xor     r8d, r8d; unsigned __int8
0x1400620ba  mov     rcx, rax; this
0x1400620bd  lea     edx, [r8+15h]; unsigned int
0x1400620c1  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400620c6  mov     rcx, [rbx+0A0h]
0x1400620cd  mov     byte ptr [rbp+arg_0], al
0x1400620d0  lock add [rcx+14F0h], r14d
0x1400620d8  mov     rcx, [rbx+0A0h]; this
0x1400620df  mov     r8d, [r15]; unsigned int
0x1400620e2  mov     [rsp+70h+var_48], al; char
0x1400620e6  mov     edx, [rcx+14FCh]
0x1400620ec  mov     r9d, [rcx+14F0h]; unsigned int
0x1400620f3  mov     [rsp+70h+var_50], edx; unsigned int
0x1400620f7  mov     edx, r14d; unsigned int
0x1400620fa  call    ?TraceLoggingResetRecovery@CAdapter@@QEAAXKKKKE@Z; CAdapter::TraceLoggingResetRecovery(ulong,ulong,ulong,ulong,uchar)
0x1400620ff  cmp     dword ptr [r15], 4Bh ; 'K'
0x140062103  lea     rdi, [rbx+18h]
0x140062107  jz      short loc_140062113
0x140062109  mov     rax, [rdi]
0x14006210c  mov     r12, [rax+0A8h]
0x140062113  mov     rax, [rbx+0A0h]
0x14006211a  mov     esi, r14d
0x14006211d  lock xadd [rax+14F4h], esi
0x140062125  add     esi, r14d
0x140062128  lea     r14, [rbx+24h]
0x14006212c  cmp     esi, 1
0x14006212f  jnz     loc_1400621D9
0x140062135  mov     r8d, [r15]; unsigned int
0x140062138  mov     edx, esi; unsigned int
0x14006213a  mov     rcx, [rbx+0A0h]; this
0x140062141  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x140062146  mov     rdx, [rdi]; struct DeviceCommand *
0x140062149  mov     r9, r12; struct CJobBase *
0x14006214c  mov     rcx, [rbx+0A0h]; this
0x140062153  xor     r8d, r8d; struct Task *
0x140062156  call    ?CollectDebugData@CAdapter@@QEAAXPEAVDeviceCommand@@PEAVTask@@PEAVCJobBase@@@Z; CAdapter::CollectDebugData(DeviceCommand *,Task *,CJobBase *)
0x14006215b  xor     eax, eax
0x14006215d  cmp     dword ptr [r15], 4Bh ; 'K'
0x140062161  jz      short loc_14006217B
0x140062163  test    r12, r12
0x140062166  jz      loc_1400622BD
0x14006216c  cmp     dword ptr [r12+3Ch], 0A0h
0x140062175  jz      loc_1400622BD
0x14006217b  mov     rcx, [rdi]; this
0x14006217e  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x140062182  and     [rbp+var_28], 0FFFFFFF8h
0x140062186  lea     rdx, [rbp+arg_10]; unsigned int *
0x14006218a  mov     [rbp+arg_10], eax
0x14006218d  mov     [rbp+arg_18], rax
0x140062191  mov     [rbp+var_24], 3
0x140062198  mov     [rbp+var_18], rax
0x14006219c  call    ?get_InputBuffer@DeviceCommand@@QEAAHPEAKPEAPEAE@Z; DeviceCommand::get_InputBuffer(ulong *,uchar * *)
0x1400621a1  mov     rcx, [rbp+arg_18]
0x1400621a5  mov     r12d, 30h ; '0'
0x1400621ab  test    rcx, rcx
0x1400621ae  jz      loc_140062248
0x1400621b4  cmp     [rbp+arg_10], r12d
0x1400621b8  jb      loc_140062248
0x1400621be  mov     eax, [rcx+10h]
0x1400621c1  mov     edx, [rcx]
0x1400621c3  mov     [rbp+var_20], eax
0x1400621c6  movzx   eax, word ptr [rcx+20h]
0x1400621ca  mov     [rbp+var_10], ax
0x1400621ce  mov     eax, [rcx+28h]
0x1400621d1  mov     [rbp+var_8], eax
0x1400621d4  mov     [rbp+var_30], edx
0x1400621d7  jmp     short loc_14006224B
0x1400621d9  xor     eax, eax
0x1400621db  cmp     [r14], eax
0x1400621de  jz      loc_14006215D
0x1400621e4  mov     rcx, [rdi]; this
0x1400621e7  lea     rdx, [rbp+arg_0]; unsigned int *
0x1400621eb  mov     [rbp+arg_0], eax
0x1400621ee  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x1400621f3  lea     r15, WPP_RECORDER_INITIALIZED
0x1400621fa  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140062201  jz      loc_14006232A
0x140062207  mov     eax, [r14]
0x14006220a  lea     rdi, WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids
0x140062211  mov     rcx, cs:WPP_GLOBAL_Control
0x140062218  mov     r9d, 28h ; '('
0x14006221e  mov     [rsp+70h+var_38], eax
0x140062222  mov     dl, 2
0x140062224  mov     eax, [rbp+arg_0]
0x140062227  mov     [rsp+70h+var_40], eax
0x14006222b  mov     rcx, [rcx+40h]
0x14006222f  mov     dword ptr [rsp+70h+var_48], esi
0x140062233  mov     qword ptr [rsp+70h+var_50], rdi
0x140062238  call    WPP_RECORDER_SF_dDd
0x14006223d  xor     eax, eax
0x14006223f  lea     r14d, [rax+1]
0x140062243  jmp     loc_1400622F1
0x140062248  mov     edx, [rbp+var_30]
0x14006224b  mov     [rbp+var_2C], r12d
0x14006224f  mov     [rbp+var_1C], 0C0010008h
0x140062256  lea     r15, WPP_RECORDER_INITIALIZED
0x14006225d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140062264  jz      short loc_140062292
0x140062266  mov     rcx, cs:WPP_GLOBAL_Control
0x14006226d  lea     rax, WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids
0x140062274  mov     [rsp+70h+var_40], edx
0x140062278  mov     r9d, 29h ; ')'
0x14006227e  mov     dword ptr [rsp+70h+var_48], edx
0x140062282  mov     dl, 4
0x140062284  mov     qword ptr [rsp+70h+var_50], rax
0x140062289  mov     rcx, [rcx+40h]
0x14006228d  call    WPP_RECORDER_SF_Ld
0x140062292  mov     rcx, [rdi]; this
0x140062295  lea     rdx, [rbx+20h]; unsigned int *
0x140062299  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x14006229e  mov     rcx, [rdi]; this
0x1400622a1  mov     rdx, r14; unsigned int *
0x1400622a4  call    ?get_CommandToken@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandToken(ulong *)
0x1400622a9  lea     r8, [rbp+var_30]; struct _WFC_MESSAGE_METADATA *
0x1400622ad  mov     edx, r12d; unsigned int
0x1400622b0  lea     rcx, [rbx-10h]; this
0x1400622b4  call    ?CompleteSendCommand_PostHangCheck@DeviceCommandScheduler@@IEAAXKPEAU_WFC_MESSAGE_METADATA@@@Z; DeviceCommandScheduler::CompleteSendCommand_PostHangCheck(ulong,_WFC_MESSAGE_METADATA *)
0x1400622b9  xor     eax, eax
0x1400622bb  jmp     short loc_1400622C4
0x1400622bd  lea     r15, WPP_RECORDER_INITIALIZED
0x1400622c4  mov     r14d, 1
0x1400622ca  cmp     esi, r14d
0x1400622cd  jnz     short loc_1400622EA
0x1400622cf  mov     rcx, [rbx+0A0h]; this
0x1400622d6  cmp     [rcx+1231h], al
0x1400622dc  jz      short loc_1400622EA
0x1400622de  cmp     byte ptr [rbp+arg_0], al
0x1400622e1  jnz     short loc_1400622EA
0x1400622e3  call    ?ReenumerateFailedAdapter@CAdapter@@QEAAXXZ; CAdapter::ReenumerateFailedAdapter(void)
0x1400622e8  xor     eax, eax
0x1400622ea  lea     rdi, WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids
0x1400622f1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400622f8  jz      short loc_14006232A
0x1400622fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140062301  cmp     byte ptr [rcx+29h], 5
0x140062305  jnb     short loc_14006230D
0x140062307  cmp     [rcx+48h], ax
0x14006230b  jz      short loc_14006232A
0x14006230d  mov     rcx, [rcx+40h]
0x140062311  mov     r9d, 2Ah ; '*'
0x140062317  mov     dword ptr [rsp+70h+var_48], eax
0x14006231b  mov     r8d, r14d
0x14006231e  mov     dl, 5
0x140062320  mov     qword ptr [rsp+70h+var_50], rdi
0x140062325  call    WPP_RECORDER_SF_d
0x14006232a  mov     rbx, [rsp+70h+arg_8]
0x140062332  add     rsp, 70h
0x140062336  pop     r15
0x140062338  pop     r14
0x14006233a  pop     r13
0x14006233c  pop     r12
0x14006233e  pop     rdi
0x14006233f  pop     rsi
0x140062340  pop     rbp
0x140062341  retn
0x140062343  lea     r15, WPP_RECORDER_INITIALIZED
0x14006234a  jmp     short loc_1400622F1
```
