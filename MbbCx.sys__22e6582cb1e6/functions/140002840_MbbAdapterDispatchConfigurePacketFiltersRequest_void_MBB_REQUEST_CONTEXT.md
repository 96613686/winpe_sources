# MbbAdapterDispatchConfigurePacketFiltersRequest(void *,_MBB_REQUEST_CONTEXT *)

- ea: `0x140002840`
- end: `0x140002953`
- name: `?MbbAdapterDispatchConfigurePacketFiltersRequest@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(void *, struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140002840`
- `0x1400051ac`
- `0x1400206cc`
- `0x140020988`
- `0x14002253c`

## pseudocode

```c
__int64 __fastcall MbbAdapterDispatchConfigurePacketFiltersRequest(void *a1, struct _MBB_REQUEST_CONTEXT *a2)
{
  KSPIN_LOCK **v2; // rcx
  unsigned int v3; // r8d
  KSPIN_LOCK *v5; // rcx
  char v6; // dl
  int v7; // ebx
  struct _MBB_PACKET_FILTERS *v8; // r9
  unsigned int v9; // eax
  int v10; // edx
  int v11; // r9d
  int v12; // eax
  __int128 v14; // [rsp+40h] [rbp-28h] BYREF
  int v15; // [rsp+50h] [rbp-18h]
  unsigned int v16; // [rsp+78h] [rbp+10h] BYREF
  struct _MBB_PACKET_FILTERS *v17; // [rsp+80h] [rbp+18h] BYREF

  v2 = (KSPIN_LOCK **)*((_QWORD *)a2 + 6);
  v3 = *((_DWORD *)a2 + 183);
  v17 = 0;
  v5 = *v2;
  v6 = *((_BYTE *)a2 + 728);
  v16 = 0;
  v14 = MBB_UUID_BASIC_CONNECT;
  v15 = 23;
  v7 = MbbUtilWwanToMbbSetPacketFilter(v5, v6, v3, &v17, &v16);
  if ( v7 >= 0 )
  {
    v8 = v17;
    v9 = v16;
    *((_QWORD *)a2 + 70) = v17;
    v7 = MbbUtilSetupCommandMessage((__int64)a2, (__int64)&v14, 1, (__int64)v8, v9);
    if ( v7 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v11 = 42;
LABEL_9:
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_DD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          1,
          v11,
          (__int64)WPP_94691144733c3f1d26776b6e97df90bb_Traceguids,
          *((_DWORD *)a2 + 4),
          v7);
      }
    }
    else
    {
      v12 = MbbUtilSendMessageFragmentsAndLog(a2);
      v7 = v12;
      if ( v12 && v12 != 259 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v11 = 43;
        goto LABEL_9;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140002840  mov     r11, rsp
0x140002843  mov     [r11+8], rbx
0x140002847  push    rdi
0x140002848  sub     rsp, 60h
0x14000284c  mov     rcx, [rdx+30h]
0x140002850  lea     rax, [r11+10h]
0x140002854  movups  xmm0, cs:MBB_UUID_BASIC_CONNECT
0x14000285b  mov     r8d, [rdx+2DCh]; unsigned int
0x140002862  lea     r9, [r11+18h]; struct _MBB_PACKET_FILTERS **
0x140002866  mov     rdi, rdx
0x140002869  mov     qword ptr [r11+18h], 0
0x140002871  mov     rcx, [rcx]; SpinLock
0x140002874  mov     dl, [rdx+2D8h]; unsigned __int8
0x14000287a  mov     [rsp+68h+arg_8], 0
0x140002882  movdqu  [rsp+68h+var_28], xmm0
0x140002888  mov     [rsp+68h+var_18], 17h
0x140002890  mov     [r11-48h], rax
0x140002894  call    ?MbbUtilWwanToMbbSetPacketFilter@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@EKPEAPEAU_MBB_PACKET_FILTERS@@PEAK@Z; MbbUtilWwanToMbbSetPacketFilter(_MINIPORT_ADAPTER_CONTEXT *,uchar,ulong,_MBB_PACKET_FILTERS * *,ulong *)
0x140002899  mov     ebx, eax
0x14000289b  test    eax, eax
0x14000289d  js      loc_140002945
0x1400028a3  mov     r9, [rsp+68h+arg_10]
0x1400028ab  lea     rdx, [rsp+68h+var_28]
0x1400028b0  mov     eax, [rsp+68h+arg_8]
0x1400028b4  mov     r8d, 1
0x1400028ba  mov     rcx, rdi
0x1400028bd  mov     [rdi+230h], r9
0x1400028c4  mov     dword ptr [rsp+68h+var_48], eax
0x1400028c8  call    ?MbbUtilSetupCommandMessage@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_COMMAND@@W4_MBB_COMMAND_TYPE@@PEAEK@Z; MbbUtilSetupCommandMessage(_MBB_REQUEST_CONTEXT *,_MBB_COMMAND *,_MBB_COMMAND_TYPE,uchar *,ulong)
0x1400028cd  mov     ebx, eax
0x1400028cf  test    eax, eax
0x1400028d1  jz      short loc_1400028EB
0x1400028d3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400028da  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400028e1  jz      short loc_140002945
0x1400028e3  mov     r9d, 2Ah ; '*'
0x1400028e9  jmp     short loc_140002916
0x1400028eb  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x1400028ee  call    ?MbbUtilSendMessageFragmentsAndLog@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilSendMessageFragmentsAndLog(_MBB_REQUEST_CONTEXT *)
0x1400028f3  mov     ebx, eax
0x1400028f5  test    eax, eax
0x1400028f7  jz      short loc_140002945
0x1400028f9  cmp     eax, 103h
0x1400028fe  jz      short loc_140002945
0x140002900  lea     rax, WPP_RECORDER_INITIALIZED
0x140002907  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000290e  jz      short loc_140002945
0x140002910  mov     r9d, 2Bh ; '+'
0x140002916  mov     eax, [rdi+10h]
0x140002919  mov     r8d, 1
0x14000291f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002926  mov     dl, 2
0x140002928  mov     [rsp+68h+var_38], ebx
0x14000292c  mov     [rsp+68h+var_40], eax
0x140002930  lea     rax, WPP_94691144733c3f1d26776b6e97df90bb_Traceguids
0x140002937  mov     [rsp+68h+var_48], rax
0x14000293c  mov     rcx, [rcx+40h]
0x140002940  call    WPP_RECORDER_SF_DD
0x140002945  mov     eax, ebx
0x140002947  mov     rbx, [rsp+68h+arg_0]
0x14000294c  add     rsp, 60h
0x140002950  pop     rdi
0x140002951  retn
```
