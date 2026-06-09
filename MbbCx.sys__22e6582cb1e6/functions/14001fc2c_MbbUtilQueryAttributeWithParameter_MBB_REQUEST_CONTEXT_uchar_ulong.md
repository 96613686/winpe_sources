# MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)

- ea: `0x14001fc2c`
- end: `0x14001fcee`
- name: `?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z`
- size: `194`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int)`
- caller_count: `31`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140002df0`
- `0x14000f9c0`
- `0x140010540`
- `0x140010600`
- `0x1400108b0`
- `0x140010b00`
- `0x140010d00`
- `0x140010e20`
- `0x140010e90`
- `0x140010f40`
- `0x140011000`
- `0x140011150`
- `0x1400111c0`
- `0x140011330`
- `0x1400114b0`
- `0x140011560`
- `0x1400115c0`
- `0x1400117c0`
- `0x140011830`
- `0x1400118a0`
- `0x140011910`
- `0x1400119c0`
- `0x140011a30`
- `0x140011b10`
- `0x140011c50`
- `0x140011d10`
- `0x140016450`
- `0x140016f50`
- `0x14001fc10`
- `0x140020a58`
- `0x140020b38`

## callees

- `0x14001fc2c`
- `0x1400206cc`
- `0x140020988`
- `0x1400245e0`
- `0x14003e100`

## pseudocode

```c
__int64 __fastcall MbbUtilQueryAttributeWithParameter(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int a3)
{
  unsigned int v4; // ebx
  char (near **CommandString)[32]; // rax
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // eax
  int v11; // [rsp+38h] [rbp-10h]

  v4 = MbbUtilSetupCommandMessage((__int64)a1, *((_QWORD *)a1 + 10) + 48LL, 0, (__int64)a2, a3);
  if ( v4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      CommandString = MbbUtilGetCommandString((struct _MBB_COMMAND *)(*((_QWORD *)a1 + 10) + 48LL));
      v8 = 32;
LABEL_8:
      v11 = v4;
      WPP_RECORDER_SF_Dsd(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        v7,
        v8,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
        *((_DWORD *)a1 + 4),
        (__int64)CommandString,
        v11);
    }
  }
  else
  {
    v9 = MbbUtilSendMessageFragmentsAndLog(a1);
    v4 = v9;
    if ( v9 && v9 != 259 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      CommandString = MbbUtilGetCommandString((struct _MBB_COMMAND *)(*((_QWORD *)a1 + 10) + 48LL));
      v8 = 33;
      goto LABEL_8;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14001fc2c  mov     [rsp+arg_0], rbx
0x14001fc31  push    rdi
0x14001fc32  sub     rsp, 40h
0x14001fc36  mov     r9, rdx
0x14001fc39  mov     dword ptr [rsp+48h+var_28], r8d
0x14001fc3e  mov     rdx, [rcx+50h]
0x14001fc42  xor     r8d, r8d
0x14001fc45  add     rdx, 30h ; '0'
0x14001fc49  mov     rdi, rcx
0x14001fc4c  call    ?MbbUtilSetupCommandMessage@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_COMMAND@@W4_MBB_COMMAND_TYPE@@PEAEK@Z; MbbUtilSetupCommandMessage(_MBB_REQUEST_CONTEXT *,_MBB_COMMAND *,_MBB_COMMAND_TYPE,uchar *,ulong)
0x14001fc51  mov     ebx, eax
0x14001fc53  test    eax, eax
0x14001fc55  jz      short loc_14001FC7C
0x14001fc57  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fc5e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fc65  jz      short loc_14001FCE0
0x14001fc67  mov     rcx, [rdi+50h]
0x14001fc6b  add     rcx, 30h ; '0'; Source1
0x14001fc6f  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14001fc74  mov     r9d, 20h ; ' '
0x14001fc7a  jmp     short loc_14001FCB4
0x14001fc7c  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x14001fc7f  call    ?MbbUtilSendMessageFragmentsAndLog@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilSendMessageFragmentsAndLog(_MBB_REQUEST_CONTEXT *)
0x14001fc84  mov     ebx, eax
0x14001fc86  test    eax, eax
0x14001fc88  jz      short loc_14001FCE0
0x14001fc8a  cmp     eax, 103h
0x14001fc8f  jz      short loc_14001FCE0
0x14001fc91  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fc98  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fc9f  jz      short loc_14001FCE0
0x14001fca1  mov     rcx, [rdi+50h]
0x14001fca5  add     rcx, 30h ; '0'; Source1
0x14001fca9  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14001fcae  mov     r9d, 21h ; '!'
0x14001fcb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fcbb  mov     [rsp+48h+var_10], ebx
0x14001fcbf  mov     [rsp+48h+var_18], rax
0x14001fcc4  mov     eax, [rdi+10h]
0x14001fcc7  mov     rcx, [rcx+40h]
0x14001fccb  mov     [rsp+48h+var_20], eax
0x14001fccf  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001fcd6  mov     [rsp+48h+var_28], rax
0x14001fcdb  call    WPP_RECORDER_SF_Dsd
0x14001fce0  mov     eax, ebx
0x14001fce2  mov     rbx, [rsp+48h+arg_0]
0x14001fce7  add     rsp, 40h
0x14001fceb  pop     rdi
0x14001fcec  retn
```
