# CResetRecoveryJob::SetData(void *,uint,uint *,uint *)

- ea: `0x14006abe0`
- end: `0x14006ae56`
- name: `?SetData@CResetRecoveryJob@@UEAAHPEAXIPEAI1@Z`
- size: `630`
- prototype: `__int64 __fastcall(CResetRecoveryJob *__hidden this, void *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000688c`
- `0x14000c778`
- `0x14000d054`
- `0x14001e2c0`
- `0x14001ed44`
- `0x140022cb4`
- `0x140054650`
- `0x140055d18`
- `0x140058a10`
- `0x140058cdc`
- `0x14006abe0`
- `0x1400dfd40`

## import_xrefs

- `NDIS!NdisWriteErrorLogEntry` at `0x14006acaa`
- `NDIS!NdisWriteErrorLogEntry` at `0x14006acaa`

## pseudocode

```c
__int64 __fastcall CResetRecoveryJob::SetData(
        CResetRecoveryJob *this,
        void *a2,
        __int64 a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int v6; // esi
  unsigned int *v8; // rax
  __int64 v9; // rax
  struct CJobBase **v10; // rbx
  void *AdapterNdisHandleFromNdisPortNumber; // rax
  CPropertyCache *v12; // rax
  char PropertyBooleanOrDefault; // bp
  int v14; // r8d
  signed __int32 v15; // edx
  CAdapter *v16; // rcx
  unsigned int v17; // edx
  unsigned int v18; // ebx
  int v19; // edx
  unsigned int v21; // [rsp+90h] [rbp+8h] BYREF

  v6 = 0;
  v21 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      10,
      (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids);
  }
  v8 = a5;
  *a4 = 8;
  *v8 = 8;
  v9 = *((_QWORD *)this + 67);
  v10 = *(struct CJobBase ***)(v9 + 1160);
  if ( v10 )
  {
    DeviceCommand::get_CommandType(*(DeviceCommand **)(v9 + 1160), &v21);
    v6 = v21;
  }
  AdapterNdisHandleFromNdisPortNumber = CAdapter::GetAdapterNdisHandleFromNdisPortNumber(*((CAdapter **)this + 67), 0);
  NdisWriteErrorLogEntry(AdapterNdisHandleFromNdisPortNumber, 0xC000138A, 2u);
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 67) + 5360LL), 1u);
  v12 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 67) + 8LL) + 8LL))(*((_QWORD *)this + 67) + 8LL);
  PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(v12, 0x15u, 0);
  CAdapter::TraceLoggingResetRecovery(
    *((CAdapter **)this + 67),
    3u,
    v6,
    *(_DWORD *)(*((_QWORD *)this + 67) + 5360LL),
    *(_DWORD *)(*((_QWORD *)this + 67) + 5372LL),
    PropertyBooleanOrDefault);
  v15 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 67) + 5364LL), 1u);
  v16 = (CAdapter *)*((_QWORD *)this + 67);
  v17 = v15 + 1;
  if ( v17 <= 1 )
  {
    if ( v10 )
    {
      CAdapter::TriggerControlPathDiagnostics(v16, 3u, v6);
      CAdapter::CollectDebugData(*((CAdapter **)this + 67), (struct DeviceCommand *)v10, 0, v10[21]);
    }
    else
    {
      CAdapter::TriggerControlPathDiagnostics(v16, 3u, 0);
    }
    if ( PropertyBooleanOrDefault )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          1,
          12,
          (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids);
      v18 = -1073676276;
    }
    else
    {
      v18 = 0;
      CAdapter::ReenumerateFailedAdapter(*((CAdapter **)this + 67));
    }
    goto LABEL_21;
  }
  if ( *((_DWORD *)v16 + 1343) )
    v18 = PropertyBooleanOrDefault != 0 ? 0xC001000C : 0;
  else
    v18 = -1073741637;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v17) = 4;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      v14,
      11,
      (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v18);
LABEL_21:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v19) = 5;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        1,
        13,
        (__int64)WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids,
        v18);
    }
  }
  return v18;
}

```

## disassembly

```asm
0x14006abe0  mov     rax, rsp
0x14006abe3  push    rbx
0x14006abe4  push    rbp
0x14006abe5  push    rsi
0x14006abe6  push    rdi
0x14006abe7  push    r12
0x14006abe9  push    r13
0x14006abeb  push    r14
0x14006abed  push    r15
0x14006abef  sub     rsp, 48h
0x14006abf3  xor     r14d, r14d
0x14006abf6  mov     rbx, r9
0x14006abf9  mov     esi, r14d
0x14006abfc  mov     [rax+8], r14d
0x14006ac00  mov     rdi, rcx
0x14006ac03  lea     r15, WPP_RECORDER_INITIALIZED
0x14006ac0a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006ac11  lea     r12, WPP_27f5a9f1788d3cc5c5e48b313f264aa2_Traceguids
0x14006ac18  lea     r13d, [r14+1]
0x14006ac1c  jz      short loc_14006AC4B
0x14006ac1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ac25  cmp     byte ptr [rcx+29h], 5
0x14006ac29  jnb     short loc_14006AC32
0x14006ac2b  cmp     [rcx+48h], r14w
0x14006ac30  jz      short loc_14006AC4B
0x14006ac32  mov     rcx, [rcx+40h]
0x14006ac36  mov     r9d, 0Ah
0x14006ac3c  mov     r8d, r13d
0x14006ac3f  mov     qword ptr [rsp+88h+var_68], r12
0x14006ac44  mov     dl, 5
0x14006ac46  call    WPP_RECORDER_SF_
0x14006ac4b  mov     rax, [rsp+88h+arg_20]
0x14006ac53  mov     ecx, 8
0x14006ac58  mov     [rbx], ecx
0x14006ac5a  mov     [rax], ecx
0x14006ac5c  mov     rax, [rdi+218h]
0x14006ac63  mov     rbx, [rax+488h]
0x14006ac6a  test    rbx, rbx
0x14006ac6d  jz      short loc_14006AC86
0x14006ac6f  lea     rdx, [rsp+88h+arg_0]; unsigned int *
0x14006ac77  mov     rcx, rbx; this
0x14006ac7a  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x14006ac7f  mov     esi, [rsp+88h+arg_0]
0x14006ac86  mov     rcx, [rdi+218h]; this
0x14006ac8d  xor     edx, edx; unsigned int
0x14006ac8f  call    ?GetAdapterNdisHandleFromNdisPortNumber@CAdapter@@QEAAPEAXK@Z; CAdapter::GetAdapterNdisHandleFromNdisPortNumber(ulong)
0x14006ac94  mov     r9d, 3
0x14006ac9a  mov     [rsp+88h+var_68], esi
0x14006ac9e  mov     edx, 0C000138Ah; ErrorCode
0x14006aca3  mov     rcx, rax; NdisAdapterHandle
0x14006aca6  lea     r8d, [r9-1]; NumberOfErrorValues
0x14006acaa  call    cs:__imp_NdisWriteErrorLogEntry
0x14006acb1  nop     dword ptr [rax+rax+00h]
0x14006acb6  mov     rax, [rdi+218h]
0x14006acbd  lock add [rax+14F0h], r13d
0x14006acc5  mov     rcx, [rdi+218h]
0x14006accc  add     rcx, 8
0x14006acd0  mov     rax, [rcx]
0x14006acd3  mov     rax, [rax+8]
0x14006acd7  call    _guard_dispatch_icall
0x14006acdc  xor     r8d, r8d; unsigned __int8
0x14006acdf  mov     rcx, rax; this
0x14006ace2  lea     edx, [r8+15h]; unsigned int
0x14006ace6  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14006aceb  mov     rcx, [rdi+218h]; this
0x14006acf2  mov     r8d, esi; unsigned int
0x14006acf5  mov     [rsp+88h+var_60], al; char
0x14006acf9  mov     bpl, al
0x14006acfc  mov     edx, [rcx+14FCh]
0x14006ad02  mov     r9d, [rcx+14F0h]; unsigned int
0x14006ad09  mov     [rsp+88h+var_68], edx; unsigned int
0x14006ad0d  mov     edx, 3; unsigned int
0x14006ad12  call    ?TraceLoggingResetRecovery@CAdapter@@QEAAXKKKKE@Z; CAdapter::TraceLoggingResetRecovery(ulong,ulong,ulong,ulong,uchar)
0x14006ad17  mov     rcx, [rdi+218h]
0x14006ad1e  mov     edx, r13d
0x14006ad21  lock xadd [rcx+14F4h], edx
0x14006ad29  mov     rcx, [rdi+218h]; this
0x14006ad30  add     edx, r13d
0x14006ad33  cmp     edx, r13d
0x14006ad36  jbe     short loc_14006AD8F
0x14006ad38  cmp     [rcx+14FCh], r14d
0x14006ad3f  jnz     short loc_14006AD48
0x14006ad41  mov     ebx, 0C00000BBh
0x14006ad46  jmp     short loc_14006AD53
0x14006ad48  neg     bpl
0x14006ad4b  sbb     ebx, ebx
0x14006ad4d  and     ebx, 0C001000Ch
0x14006ad53  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006ad5a  jz      loc_14006AE42
0x14006ad60  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ad67  mov     r9d, 0Bh
0x14006ad6d  mov     eax, [rdi+10h]
0x14006ad70  mov     dl, 4
0x14006ad72  mov     [rsp+88h+var_50], ebx
0x14006ad76  mov     [rsp+88h+var_58], eax
0x14006ad7a  mov     rcx, [rcx+40h]
0x14006ad7e  mov     qword ptr [rsp+88h+var_60], rdi
0x14006ad83  mov     qword ptr [rsp+88h+var_68], r12
0x14006ad88  call    WPP_RECORDER_SF_qDD
0x14006ad8d  jmp     short loc_14006AE08
0x14006ad8f  mov     edx, 3; unsigned int
0x14006ad94  test    rbx, rbx
0x14006ad97  jz      short loc_14006ADBC
0x14006ad99  mov     r8d, esi; unsigned int
0x14006ad9c  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x14006ada1  mov     r9, [rbx+0A8h]; struct CJobBase *
0x14006ada8  xor     r8d, r8d; struct Task *
0x14006adab  mov     rcx, [rdi+218h]; this
0x14006adb2  mov     rdx, rbx; struct DeviceCommand *
0x14006adb5  call    ?CollectDebugData@CAdapter@@QEAAXPEAVDeviceCommand@@PEAVTask@@PEAVCJobBase@@@Z; CAdapter::CollectDebugData(DeviceCommand *,Task *,CJobBase *)
0x14006adba  jmp     short loc_14006ADC4
0x14006adbc  xor     r8d, r8d; unsigned int
0x14006adbf  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x14006adc4  test    bpl, bpl
0x14006adc7  jnz     short loc_14006ADDA
0x14006adc9  mov     rcx, [rdi+218h]; this
0x14006add0  mov     ebx, r14d
0x14006add3  call    ?ReenumerateFailedAdapter@CAdapter@@QEAAXXZ; CAdapter::ReenumerateFailedAdapter(void)
0x14006add8  jmp     short loc_14006AE08
0x14006adda  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006ade1  jz      short loc_14006AE03
0x14006ade3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006adea  mov     r9d, 0Ch
0x14006adf0  mov     r8d, r13d
0x14006adf3  mov     qword ptr [rsp+88h+var_68], r12
0x14006adf8  mov     dl, 2
0x14006adfa  mov     rcx, [rcx+40h]
0x14006adfe  call    WPP_RECORDER_SF_
0x14006ae03  mov     ebx, 0C001000Ch
0x14006ae08  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006ae0f  jz      short loc_14006AE42
0x14006ae11  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ae18  cmp     byte ptr [rcx+29h], 5
0x14006ae1c  jnb     short loc_14006AE25
0x14006ae1e  cmp     [rcx+48h], r14w
0x14006ae23  jz      short loc_14006AE42
0x14006ae25  mov     rcx, [rcx+40h]
0x14006ae29  mov     r9d, 0Dh
0x14006ae2f  mov     dword ptr [rsp+88h+var_60], ebx
0x14006ae33  mov     r8d, r13d
0x14006ae36  mov     dl, 5
0x14006ae38  mov     qword ptr [rsp+88h+var_68], r12
0x14006ae3d  call    WPP_RECORDER_SF_d
0x14006ae42  mov     eax, ebx
0x14006ae44  add     rsp, 48h
0x14006ae48  pop     r15
0x14006ae4a  pop     r14
0x14006ae4c  pop     r13
0x14006ae4e  pop     r12
0x14006ae50  pop     rdi
0x14006ae51  pop     rsi
0x14006ae52  pop     rbp
0x14006ae53  pop     rbx
0x14006ae54  retn
```
