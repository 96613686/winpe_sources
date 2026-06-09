# MbbAdapterDispatchConfigureDeviceServiceSubscriptionRequest(void *,_MBB_REQUEST_CONTEXT *)

- ea: `0x1400026f0`
- end: `0x140002835`
- name: `?MbbAdapterDispatchConfigureDeviceServiceSubscriptionRequest@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `325`
- prototype: `int(void *, struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400026f0`
- `0x1400051ac`
- `0x14001ed10`
- `0x14001eee8`
- `0x1400206cc`
- `0x140020988`

## pseudocode

```c
__int64 __fastcall MbbAdapterDispatchConfigureDeviceServiceSubscriptionRequest(
        struct _MINIPORT_ADAPTER_CONTEXT *a1,
        struct _MBB_REQUEST_CONTEXT *a2)
{
  bool v2; // zf
  int v4; // eax
  unsigned int v5; // ebx
  struct _MBB_SUBSCRIBE_EVENT_LIST *v6; // r9
  unsigned int v7; // eax
  int v8; // edx
  int v9; // r9d
  unsigned int v10; // eax
  int v12; // [rsp+28h] [rbp-40h]
  char v13; // [rsp+30h] [rbp-38h]
  __int128 v14; // [rsp+40h] [rbp-28h] BYREF
  int v15; // [rsp+50h] [rbp-18h]
  unsigned int v16; // [rsp+78h] [rbp+10h] BYREF
  struct _MBB_SUBSCRIBE_EVENT_LIST *v17; // [rsp+80h] [rbp+18h] BYREF

  v2 = *((_BYTE *)a2 + 728) == 0;
  v17 = 0;
  v16 = 0;
  v14 = MBB_UUID_BASIC_CONNECT;
  v15 = 19;
  if ( v2 )
    v4 = MbbUtilGenerateLowPowerSubscribeEventList(a1, *((_DWORD *)a2 + 183), *((_DWORD *)a2 + 184), &v17, &v16);
  else
    v4 = MbbUtilGenerateFullPowerSubscribeEventList(
           **((struct _MINIPORT_ADAPTER_CONTEXT ***)a2 + 6),
           *(struct _MBB_SUBSCRIBE_EVENT_LIST **)(**((_QWORD **)a2 + 6) + 1128LL),
           *(_DWORD *)(**((_QWORD **)a2 + 6) + 1124LL),
           &v17,
           &v16);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = v17;
    v7 = v16;
    *((_QWORD *)a2 + 70) = v17;
    v5 = MbbUtilSetupCommandMessage((__int64)a2, (__int64)&v14, 1, (__int64)v6, v7);
    if ( v5 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = 46;
        v13 = v5;
        v12 = *((_DWORD *)a2 + 4);
LABEL_12:
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          1,
          v9,
          (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids,
          v12,
          v13);
      }
    }
    else
    {
      v10 = MbbUtilSendMessageFragmentsAndLog(a2);
      v5 = v10;
      if ( v10 && v10 != 259 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = 47;
        v13 = v10;
        v12 = *((_DWORD *)a2 + 4);
        goto LABEL_12;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400026f0  mov     rax, rsp
0x1400026f3  mov     [rax+8], rbx
0x1400026f7  push    rdi
0x1400026f8  sub     rsp, 60h
0x1400026fc  cmp     byte ptr [rdx+2D8h], 0
0x140002703  lea     r9, [rax+18h]; struct _MBB_SUBSCRIBE_EVENT_LIST **
0x140002707  movups  xmm0, cs:MBB_UUID_BASIC_CONNECT
0x14000270e  mov     rdi, rdx
0x140002711  mov     qword ptr [rax+18h], 0
0x140002719  mov     dword ptr [rax+10h], 0
0x140002720  movdqu  xmmword ptr [rax-28h], xmm0
0x140002725  mov     dword ptr [rax-18h], 13h
0x14000272c  jz      short loc_140002754
0x14000272e  mov     rax, [rdx+30h]
0x140002732  mov     rcx, [rax]; struct _MINIPORT_ADAPTER_CONTEXT *
0x140002735  lea     rax, [rsp+68h+arg_8]
0x14000273a  mov     [rsp+68h+var_48], rax; unsigned int *
0x14000273f  mov     r8d, [rcx+464h]; unsigned int
0x140002746  mov     rdx, [rcx+468h]; struct _MBB_SUBSCRIBE_EVENT_LIST *
0x14000274d  call    ?MbbUtilGenerateFullPowerSubscribeEventList@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MBB_SUBSCRIBE_EVENT_LIST@@KPEAPEAU2@PEAK@Z; MbbUtilGenerateFullPowerSubscribeEventList(_MINIPORT_ADAPTER_CONTEXT *,_MBB_SUBSCRIBE_EVENT_LIST *,ulong,_MBB_SUBSCRIBE_EVENT_LIST * *,ulong *)
0x140002752  jmp     short loc_140002770
0x140002754  mov     r8d, [rdx+2E0h]; unsigned int
0x14000275b  lea     rax, [rsp+68h+arg_8]
0x140002760  mov     edx, [rdx+2DCh]; unsigned int
0x140002766  mov     [rsp+68h+var_48], rax; unsigned int *
0x14000276b  call    ?MbbUtilGenerateLowPowerSubscribeEventList@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@KKPEAPEAU_MBB_SUBSCRIBE_EVENT_LIST@@PEAK@Z; MbbUtilGenerateLowPowerSubscribeEventList(_MINIPORT_ADAPTER_CONTEXT *,ulong,ulong,_MBB_SUBSCRIBE_EVENT_LIST * *,ulong *)
0x140002770  mov     ebx, eax
0x140002772  test    eax, eax
0x140002774  js      loc_140002827
0x14000277a  mov     r9, [rsp+68h+arg_10]
0x140002782  lea     rdx, [rsp+68h+var_28]
0x140002787  mov     eax, [rsp+68h+arg_8]
0x14000278b  mov     r8d, 1
0x140002791  mov     rcx, rdi
0x140002794  mov     [rdi+230h], r9
0x14000279b  mov     dword ptr [rsp+68h+var_48], eax
0x14000279f  call    ?MbbUtilSetupCommandMessage@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_COMMAND@@W4_MBB_COMMAND_TYPE@@PEAEK@Z; MbbUtilSetupCommandMessage(_MBB_REQUEST_CONTEXT *,_MBB_COMMAND *,_MBB_COMMAND_TYPE,uchar *,ulong)
0x1400027a4  mov     ebx, eax
0x1400027a6  test    eax, eax
0x1400027a8  jz      short loc_1400027CD
0x1400027aa  lea     rax, WPP_RECORDER_INITIALIZED
0x1400027b1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400027b8  jz      short loc_140002827
0x1400027ba  mov     ecx, [rdi+10h]
0x1400027bd  mov     r9d, 2Eh ; '.'
0x1400027c3  mov     dword ptr [rsp+68h+var_38], ebx
0x1400027c7  mov     [rsp+68h+var_40], ecx
0x1400027cb  jmp     short loc_140002803
0x1400027cd  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x1400027d0  call    ?MbbUtilSendMessageFragmentsAndLog@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilSendMessageFragmentsAndLog(_MBB_REQUEST_CONTEXT *)
0x1400027d5  mov     ebx, eax
0x1400027d7  test    eax, eax
0x1400027d9  jz      short loc_140002827
0x1400027db  cmp     eax, 103h
0x1400027e0  jz      short loc_140002827
0x1400027e2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400027e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400027f0  jz      short loc_140002827
0x1400027f2  mov     eax, [rdi+10h]
0x1400027f5  mov     r9d, 2Fh ; '/'
0x1400027fb  mov     dword ptr [rsp+68h+var_38], ebx
0x1400027ff  mov     [rsp+68h+var_40], eax
0x140002803  mov     rcx, cs:WPP_GLOBAL_Control
0x14000280a  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x140002811  mov     r8d, 1
0x140002817  mov     [rsp+68h+var_48], rax
0x14000281c  mov     dl, 2
0x14000281e  mov     rcx, [rcx+40h]
0x140002822  call    WPP_RECORDER_SF_DD
0x140002827  mov     eax, ebx
0x140002829  mov     rbx, [rsp+68h+arg_0]
0x14000282e  add     rsp, 60h
0x140002832  pop     rdi
0x140002833  retn
```
