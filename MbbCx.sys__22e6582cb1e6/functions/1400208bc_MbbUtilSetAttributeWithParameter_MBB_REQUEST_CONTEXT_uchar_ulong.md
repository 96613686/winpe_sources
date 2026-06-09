# MbbUtilSetAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)

- ea: `0x1400208bc`
- end: `0x140020981`
- name: `?MbbUtilSetAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z`
- size: `197`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int)`
- caller_count: `39`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140002d70`
- `0x140002e10`
- `0x140002eb0`
- `0x1400142f0`
- `0x140014490`
- `0x140014540`
- `0x140014730`
- `0x140014a30`
- `0x140014d50`
- `0x140014ea0`
- `0x140015190`
- `0x140015290`
- `0x1400153a0`
- `0x140015560`
- `0x140015710`
- `0x140015a40`
- `0x140015c20`
- `0x140015c80`
- `0x140015d90`
- `0x140015e10`
- `0x140015f00`
- `0x140015fc0`
- `0x140016140`
- `0x140016200`
- `0x140016370`
- `0x1400164c0`
- `0x140016560`
- `0x1400166d0`
- `0x1400167c0`
- `0x1400168f0`
- `0x1400169e0`
- `0x140016ab0`
- `0x140016ed0`
- `0x140016fd0`
- `0x140017110`
- `0x140017230`
- `0x14001c400`
- `0x14001c834`
- `0x14001f834`

## callees

- `0x1400206cc`
- `0x1400208bc`
- `0x140020988`
- `0x1400245e0`
- `0x14003e100`

## pseudocode

```c
__int64 __fastcall MbbUtilSetAttributeWithParameter(
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

  v4 = MbbUtilSetupCommandMessage((__int64)a1, *((_QWORD *)a1 + 10) + 48LL, 1, (__int64)a2, a3);
  if ( v4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      CommandString = MbbUtilGetCommandString((struct _MBB_COMMAND *)(*((_QWORD *)a1 + 10) + 48LL));
      v8 = 34;
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
      v8 = 35;
      goto LABEL_8;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400208bc  mov     [rsp+arg_0], rbx
0x1400208c1  push    rdi
0x1400208c2  sub     rsp, 40h
0x1400208c6  mov     r9, rdx
0x1400208c9  mov     dword ptr [rsp+48h+var_28], r8d
0x1400208ce  mov     rdx, [rcx+50h]
0x1400208d2  mov     r8d, 1
0x1400208d8  add     rdx, 30h ; '0'
0x1400208dc  mov     rdi, rcx
0x1400208df  call    ?MbbUtilSetupCommandMessage@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_COMMAND@@W4_MBB_COMMAND_TYPE@@PEAEK@Z; MbbUtilSetupCommandMessage(_MBB_REQUEST_CONTEXT *,_MBB_COMMAND *,_MBB_COMMAND_TYPE,uchar *,ulong)
0x1400208e4  mov     ebx, eax
0x1400208e6  test    eax, eax
0x1400208e8  jz      short loc_14002090F
0x1400208ea  lea     rax, WPP_RECORDER_INITIALIZED
0x1400208f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400208f8  jz      short loc_140020973
0x1400208fa  mov     rcx, [rdi+50h]
0x1400208fe  add     rcx, 30h ; '0'; Source1
0x140020902  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x140020907  mov     r9d, 22h ; '"'
0x14002090d  jmp     short loc_140020947
0x14002090f  mov     rcx, rdi; struct _MBB_REQUEST_CONTEXT *
0x140020912  call    ?MbbUtilSendMessageFragmentsAndLog@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilSendMessageFragmentsAndLog(_MBB_REQUEST_CONTEXT *)
0x140020917  mov     ebx, eax
0x140020919  test    eax, eax
0x14002091b  jz      short loc_140020973
0x14002091d  cmp     eax, 103h
0x140020922  jz      short loc_140020973
0x140020924  lea     rax, WPP_RECORDER_INITIALIZED
0x14002092b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020932  jz      short loc_140020973
0x140020934  mov     rcx, [rdi+50h]
0x140020938  add     rcx, 30h ; '0'; Source1
0x14002093c  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x140020941  mov     r9d, 23h ; '#'
0x140020947  mov     rcx, cs:WPP_GLOBAL_Control
0x14002094e  mov     [rsp+48h+var_10], ebx
0x140020952  mov     [rsp+48h+var_18], rax
0x140020957  mov     eax, [rdi+10h]
0x14002095a  mov     rcx, [rcx+40h]
0x14002095e  mov     [rsp+48h+var_20], eax
0x140020962  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x140020969  mov     [rsp+48h+var_28], rax
0x14002096e  call    WPP_RECORDER_SF_Dsd
0x140020973  mov     eax, ebx
0x140020975  mov     rbx, [rsp+48h+arg_0]
0x14002097a  add     rsp, 40h
0x14002097e  pop     rdi
0x14002097f  retn
```
