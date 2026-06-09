# Task::OnTimerCallback(void *)

- ea: `0x140062ef0`
- end: `0x140063238`
- name: `?OnTimerCallback@Task@@UEAAXPEAX@Z`
- size: `840`
- prototype: `void __fastcall(Task *__hidden this, void *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140001008`
- `0x140001484`
- `0x140004d48`
- `0x14000688c`
- `0x14000c778`
- `0x14000d054`
- `0x14001c100`
- `0x14001ed44`
- `0x14001eed0`
- `0x140022cb4`
- `0x1400257a0`
- `0x140039b80`
- `0x140054650`
- `0x140055d18`
- `0x140058a10`
- `0x140058cdc`
- `0x140062ef0`
- `0x1400632fc`
- `0x1400dfd40`

## import_xrefs

- `NDIS!NdisWriteErrorLogEntry` at `0x140062fd8`
- `NDIS!NdisWriteErrorLogEntry` at `0x140062fd8`

## pseudocode

```c
void __fastcall Task::OnTimerCallback(Task *this, void *a2)
{
  __int64 v3; // rbx
  int v4; // edx
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // edi
  void *AdapterNdisHandleFromNdisPortNumber; // rax
  int v9; // edx
  __int64 v10; // rcx
  CPropertyCache *v11; // rax
  char PropertyBooleanOrDefault; // r15
  const char *v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int16 *v17; // rdx
  int v18; // eax
  int v19; // edx
  int v20; // r8d
  int v21; // edx
  unsigned int v22[2]; // [rsp+20h] [rbp-40h]
  BOOL v23; // [rsp+50h] [rbp-10h] BYREF
  const char *v24; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 v26; // [rsp+B0h] [rbp+50h] BYREF
  int v27; // [rsp+B8h] [rbp+58h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      55,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids);
  }
  v25 = 0;
  v3 = *(_QWORD *)(*((_QWORD *)this + 28) + 176LL);
  DeviceCommand::get_CommandType((Task *)((char *)this + 32), &v25);
  v26 = 0;
  DeviceCommand::get_PortId((Task *)((char *)this + 32), &v26);
  v7 = v25;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDLd(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      v6,
      v22[0],
      (_BYTE)this - 24,
      *((_DWORD *)this + 2),
      v25,
      v25);
  AdapterNdisHandleFromNdisPortNumber = CAdapter::GetAdapterNdisHandleFromNdisPortNumber((CAdapter *)v3, 0);
  v22[0] = v7;
  NdisWriteErrorLogEntry(
    AdapterNdisHandleFromNdisPortNumber,
    0xC000138A,
    v9 + 2,
    (unsigned int)(v9 + 2),
    *(_QWORD *)v22);
  v10 = *(_QWORD *)(*((_QWORD *)this + 28) + 176LL) + 8LL;
  v11 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(v11, 0x15u, 0);
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 5360));
  if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (unsigned int)dword_14010EC48 > 2 && (unsigned __int8)tlgKeywordOn(&dword_14010EC48, 5) )
    {
      v27 = *(_DWORD *)(v3 + 5360);
      LOBYTE(v25) = PropertyBooleanOrDefault == 0;
      v23 = *(_DWORD *)(v3 + 5372) != 0;
      v13 = WDI_TLV::stringify::ToLogString(v7);
      v17 = &word_14010452E;
LABEL_14:
      v24 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        v14,
        (_DWORD)v17,
        v15,
        v16,
        (__int64)&v24,
        (__int64)&v26,
        (__int64)&v23,
        (__int64)&v25,
        (__int64)&v27);
    }
  }
  else if ( (unsigned int)dword_14010EC48 > 2 && (unsigned __int8)tlgKeywordOn(&dword_14010EC48, 5) )
  {
    v27 = *(_DWORD *)(v3 + 5360);
    v18 = *(_DWORD *)(v3 + 5372);
    LOBYTE(v25) = PropertyBooleanOrDefault == 0;
    v23 = v18;
    v13 = WDI_TLV::stringify::ToLogString(v7);
    v17 = &word_1401044B6;
    goto LABEL_14;
  }
  CAdapter::TraceLoggingResetRecovery(
    (CAdapter *)v3,
    2u,
    v7,
    *(_DWORD *)(v3 + 5360),
    *(_DWORD *)(v3 + 5372),
    PropertyBooleanOrDefault);
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(v3 + 5364)) <= 1 )
  {
    CAdapter::CollectDebugData(
      (CAdapter *)v3,
      (Task *)((char *)this + 32),
      (Task *)((char *)this - 24),
      *((struct CJobBase **)this + 55));
    CAdapter::TriggerControlPathDiagnostics((CAdapter *)v3, 2u, v7);
    if ( *(_BYTE *)(v3 + 4657) && !PropertyBooleanOrDefault )
      CAdapter::ReenumerateFailedAdapter((CAdapter *)v3);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      v20,
      57,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      (_BYTE)this - 24,
      *((_DWORD *)this + 2));
  }
  Task::OnTaskCompletedHandler((Task *)((char *)this - 24), -1073676280, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v21) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      1,
      58,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      0);
  }
}

```

## disassembly

```asm
0x140062ef0  mov     [rsp-38h+arg_8], rbx
0x140062ef5  push    rbp
0x140062ef6  push    rsi
0x140062ef7  push    rdi
0x140062ef8  push    r12
0x140062efa  push    r13
0x140062efc  push    r14
0x140062efe  push    r15
0x140062f00  mov     rbp, rsp
0x140062f03  sub     rsp, 60h
0x140062f07  mov     rsi, rcx
0x140062f0a  lea     r15, WPP_RECORDER_INITIALIZED
0x140062f11  xor     r13d, r13d
0x140062f14  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140062f1b  lea     rax, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x140062f22  jz      short loc_140062F52
0x140062f24  mov     rcx, cs:WPP_GLOBAL_Control
0x140062f2b  cmp     byte ptr [rcx+29h], 5
0x140062f2f  jnb     short loc_140062F38
0x140062f31  cmp     [rcx+48h], r13w
0x140062f36  jz      short loc_140062F52
0x140062f38  mov     rcx, [rcx+40h]
0x140062f3c  mov     r9d, 37h ; '7'
0x140062f42  mov     dl, 5
0x140062f44  mov     qword ptr [rsp+60h+var_40], rax
0x140062f49  lea     r8d, [r9-36h]
0x140062f4d  call    WPP_RECORDER_SF_
0x140062f52  lea     r14, [rsi-18h]
0x140062f56  mov     [rbp+arg_0], r13d
0x140062f5a  mov     rax, [r14+0F8h]
0x140062f61  lea     r12, [rsi+20h]
0x140062f65  lea     rdx, [rbp+arg_0]; unsigned int *
0x140062f69  mov     rcx, r12; this
0x140062f6c  mov     rbx, [rax+0B0h]
0x140062f73  call    ?get_CommandType@DeviceCommand@@QEAAHPEAK@Z; DeviceCommand::get_CommandType(ulong *)
0x140062f78  lea     rdx, [rbp+arg_10]; unsigned __int16 *
0x140062f7c  mov     [rbp+arg_10], r13w
0x140062f81  mov     rcx, r12; this
0x140062f84  call    ?get_PortId@DeviceCommand@@QEAAHPEAG@Z; DeviceCommand::get_PortId(ushort *)
0x140062f89  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140062f90  mov     edi, [rbp+arg_0]
0x140062f93  jz      short loc_140062FB9
0x140062f95  mov     rcx, cs:WPP_GLOBAL_Control
0x140062f9c  mov     eax, [rsi+8]
0x140062f9f  mov     dword ptr [rsp+60h+var_20], edi
0x140062fa3  mov     dword ptr [rsp+60h+var_28], edi
0x140062fa7  mov     rcx, [rcx+40h]
0x140062fab  mov     dword ptr [rsp+60h+var_30], eax
0x140062faf  mov     qword ptr [rsp+60h+var_38], r14
0x140062fb4  call    WPP_RECORDER_SF_qDLd
0x140062fb9  xor     edx, edx; unsigned int
0x140062fbb  mov     rcx, rbx; this
0x140062fbe  call    ?GetAdapterNdisHandleFromNdisPortNumber@CAdapter@@QEAAPEAXK@Z; CAdapter::GetAdapterNdisHandleFromNdisPortNumber(ulong)
0x140062fc3  lea     ecx, [rdx+2]
0x140062fc6  mov     [rsp+60h+var_40], edi
0x140062fca  mov     r9d, ecx
0x140062fcd  mov     r8d, ecx; NumberOfErrorValues
0x140062fd0  mov     rcx, rax; NdisAdapterHandle
0x140062fd3  mov     edx, 0C000138Ah; ErrorCode
0x140062fd8  call    cs:__imp_NdisWriteErrorLogEntry
0x140062fdf  nop     dword ptr [rax+rax+00h]
0x140062fe4  mov     rax, [rsi+0E0h]
0x140062feb  mov     rcx, [rax+0B0h]
0x140062ff2  add     rcx, 8
0x140062ff6  mov     rax, [rcx]
0x140062ff9  mov     rax, [rax+8]
0x140062ffd  call    _guard_dispatch_icall
0x140063002  xor     r8d, r8d; unsigned __int8
0x140063005  mov     rcx, rax; this
0x140063008  lea     edx, [r8+15h]; unsigned int
0x14006300c  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x140063011  mov     r15b, al
0x140063014  lock inc dword ptr [rbx+14F0h]
0x14006301b  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x140063020  test    eax, eax
0x140063022  jz      short loc_140063085
0x140063024  mov     ecx, cs:dword_14010EC48
0x14006302a  cmp     ecx, 2
0x14006302d  jbe     loc_14006310B
0x140063033  mov     edx, 5
0x140063038  lea     rcx, dword_14010EC48
0x14006303f  call    _tlgKeywordOn
0x140063044  test    al, al
0x140063046  jz      loc_14006310B
0x14006304c  mov     eax, [rbx+14F0h]
0x140063052  test    r15b, r15b
0x140063055  mov     [rbp+arg_18], eax
0x140063058  movzx   ecx, di
0x14006305b  mov     eax, r13d
0x14006305e  setz    byte ptr [rbp+arg_0]
0x140063062  cmp     [rbx+14FCh], r13d
0x140063069  setnz   al
0x14006306c  mov     [rbp+var_10], eax
0x14006306f  movzx   eax, [rbp+arg_10]
0x140063073  mov     [rbp+arg_10], ax
0x140063077  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x14006307c  lea     rdx, word_14010452E
0x140063083  jmp     short loc_1400630D5
0x140063085  mov     eax, cs:dword_14010EC48
0x14006308b  cmp     eax, 2
0x14006308e  jbe     short loc_14006310B
0x140063090  mov     edx, 5
0x140063095  lea     rcx, dword_14010EC48
0x14006309c  call    _tlgKeywordOn
0x1400630a1  test    al, al
0x1400630a3  jz      short loc_14006310B
0x1400630a5  mov     eax, [rbx+14F0h]
0x1400630ab  test    r15b, r15b
0x1400630ae  mov     [rbp+arg_18], eax
0x1400630b1  movzx   ecx, di
0x1400630b4  mov     eax, [rbx+14FCh]
0x1400630ba  setz    byte ptr [rbp+arg_0]
0x1400630be  mov     [rbp+var_10], eax
0x1400630c1  movzx   eax, [rbp+arg_10]
0x1400630c5  mov     [rbp+arg_10], ax
0x1400630c9  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x1400630ce  lea     rdx, word_1401044B6
0x1400630d5  mov     [rbp+var_8], rax
0x1400630d9  lea     rax, [rbp+arg_18]
0x1400630dd  mov     [rsp+60h+var_20], rax
0x1400630e2  lea     rax, [rbp+arg_0]
0x1400630e6  mov     [rsp+60h+var_28], rax
0x1400630eb  lea     rax, [rbp+var_10]
0x1400630ef  mov     [rsp+60h+var_30], rax
0x1400630f4  lea     rax, [rbp+arg_10]
0x1400630f8  mov     qword ptr [rsp+60h+var_38], rax
0x1400630fd  lea     rax, [rbp+var_8]
0x140063101  mov     qword ptr [rsp+60h+var_40], rax
0x140063106  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x14006310b  mov     eax, [rbx+14FCh]
0x140063111  mov     r8d, edi; unsigned int
0x140063114  mov     r9d, [rbx+14F0h]; unsigned int
0x14006311b  mov     edx, 2; unsigned int
0x140063120  mov     [rsp+60h+var_38], r15b; char
0x140063125  mov     rcx, rbx; this
0x140063128  mov     [rsp+60h+var_40], eax; unsigned int
0x14006312c  call    ?TraceLoggingResetRecovery@CAdapter@@QEAAXKKKKE@Z; CAdapter::TraceLoggingResetRecovery(ulong,ulong,ulong,ulong,uchar)
0x140063131  mov     eax, 1
0x140063136  lock xadd [rbx+14F4h], eax
0x14006313e  inc     eax
0x140063140  cmp     eax, 1
0x140063143  jbe     short loc_140063187
0x140063145  lea     rbx, WPP_RECORDER_INITIALIZED
0x14006314c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140063153  lea     rdi, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x14006315a  jz      short loc_1400631D0
0x14006315c  mov     rcx, cs:WPP_GLOBAL_Control
0x140063163  mov     r9d, 39h ; '9'
0x140063169  mov     eax, [rsi+8]
0x14006316c  mov     dl, 2
0x14006316e  mov     dword ptr [rsp+60h+var_30], eax
0x140063172  mov     qword ptr [rsp+60h+var_38], r14
0x140063177  mov     rcx, [rcx+40h]
0x14006317b  mov     qword ptr [rsp+60h+var_40], rdi
0x140063180  call    WPP_RECORDER_SF_qD
0x140063185  jmp     short loc_1400631D0
0x140063187  mov     r9, [rsi+1B8h]; struct CJobBase *
0x14006318e  mov     r8, r14; struct Task *
0x140063191  mov     rdx, r12; struct DeviceCommand *
0x140063194  mov     rcx, rbx; this
0x140063197  call    ?CollectDebugData@CAdapter@@QEAAXPEAVDeviceCommand@@PEAVTask@@PEAVCJobBase@@@Z; CAdapter::CollectDebugData(DeviceCommand *,Task *,CJobBase *)
0x14006319c  mov     r8d, edi; unsigned int
0x14006319f  mov     edx, 2; unsigned int
0x1400631a4  mov     rcx, rbx; this
0x1400631a7  call    ?TriggerControlPathDiagnostics@CAdapter@@QEAAXKK@Z; CAdapter::TriggerControlPathDiagnostics(ulong,ulong)
0x1400631ac  cmp     [rbx+1231h], r13b
0x1400631b3  jz      short loc_1400631C2
0x1400631b5  test    r15b, r15b
0x1400631b8  jnz     short loc_1400631C2
0x1400631ba  mov     rcx, rbx; this
0x1400631bd  call    ?ReenumerateFailedAdapter@CAdapter@@QEAAXXZ; CAdapter::ReenumerateFailedAdapter(void)
0x1400631c2  lea     rdi, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x1400631c9  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400631d0  xor     r9d, r9d; unsigned __int8 *
0x1400631d3  xor     r8d, r8d; unsigned int
0x1400631d6  mov     edx, 0C0010008h; int
0x1400631db  mov     rcx, r14; this
0x1400631de  call    ?OnTaskCompletedHandler@Task@@IEAAXHKPEAE@Z; Task::OnTaskCompletedHandler(int,ulong,uchar *)
0x1400631e3  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400631ea  jz      short loc_14006321F
0x1400631ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400631f3  cmp     byte ptr [rcx+29h], 5
0x1400631f7  jnb     short loc_140063200
0x1400631f9  cmp     [rcx+48h], r13w
0x1400631fe  jz      short loc_14006321F
0x140063200  mov     rcx, [rcx+40h]
0x140063204  mov     r9d, 3Ah ; ':'
0x14006320a  mov     dword ptr [rsp+60h+var_38], r13d
0x14006320f  mov     dl, 5
0x140063211  mov     qword ptr [rsp+60h+var_40], rdi
0x140063216  lea     r8d, [r9-39h]
0x14006321a  call    WPP_RECORDER_SF_d
0x14006321f  mov     rbx, [rsp+60h+arg_8]
0x140063227  add     rsp, 60h
0x14006322b  pop     r15
0x14006322d  pop     r14
0x14006322f  pop     r13
0x140063231  pop     r12
0x140063233  pop     rdi
0x140063234  pop     rsi
0x140063235  pop     rbp
0x140063236  retn
```
