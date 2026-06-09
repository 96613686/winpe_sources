# MbbUtilCommonCIDResponse(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong,_MBB_OID_HANDLER_ENTRY *)

- ea: `0x14001e250`
- end: `0x14001e6ef`
- name: `?MbbUtilCommonCIDResponse@@YAXPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEKPEAU_MBB_OID_HANDLER_ENTRY@@@Z`
- size: `1183`
- prototype: `void __fastcall(__int64, int, int, __int64, int, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ec40`
- `0x140011dd0`
- `0x14001f590`

## callees

- `0x140005778`
- `0x140019f78`
- `0x14001e250`
- `0x140024338`
- `0x14002473c`
- `0x14003e100`
- `0x140041664`
- `0x140047e50`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001e6ba`
- `ntoskrnl!KeSetEvent` at `0x14001e6ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e69a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e69a`

## pseudocode

```c
void __fastcall MbbUtilCommonCIDResponse(__int64 a1, int a2, int a3, __int64 a4, int a5, __int64 a6)
{
  __int64 v6; // r14
  const char *v7; // r12
  int v10; // edi
  bool v11; // zf
  __int64 v12; // r15
  __int64 (__fastcall *v13)(__int64); // r10
  char (near **CommandString)[32]; // rax
  __int128 v15; // xmm0
  char (near **v16)[32]; // rdx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  void *v20; // rax
  char (near **v21)[32]; // rax
  int v22; // edx
  int v23; // edx
  int v24; // r8d
  void *v25; // rcx
  __int64 v26; // [rsp+A8h] [rbp-98h]
  __int64 v27; // [rsp+B8h] [rbp-88h]
  int v28; // [rsp+C0h] [rbp-80h] BYREF
  int v29; // [rsp+C4h] [rbp-7Ch] BYREF
  int v30; // [rsp+C8h] [rbp-78h] BYREF
  int v31; // [rsp+D0h] [rbp-70h] BYREF
  int v32; // [rsp+D8h] [rbp-68h] BYREF
  int v33; // [rsp+E0h] [rbp-60h] BYREF
  int v34; // [rsp+E4h] [rbp-5Ch] BYREF
  __int128 v35; // [rsp+E8h] [rbp-58h] BYREF

  v6 = a6;
  v7 = "Unsolicited";
  v31 = a2;
  v32 = a3;
  v35 = 0u;
  v10 = 0;
  v28 = 0;
  v11 = *(_BYTE *)(a1 + 576) == 0;
  v30 = 0;
  if ( v11 )
    v7 = "Solicited";
  v29 = 0;
  v12 = -1;
  v34 = 1;
  v33 = 0;
  if ( a6 )
  {
    v13 = *(__int64 (__fastcall **)(__int64))(a6 + 72);
    if ( v13 )
    {
      v10 = v13(a1);
      v31 = v10;
    }
    CommandString = MbbUtilGetCommandString((struct _MBB_COMMAND *)(v6 + 48));
    v15 = *(_OWORD *)(v6 + 48);
    v28 = *(_DWORD *)(v6 + 64);
    v16 = CommandString;
    v35 = v15;
    if ( CommandString )
    {
      v17 = -1;
      do
        ++v17;
      while ( *((_BYTE *)v16 + v17) );
      v18 = v17 + 1;
      goto LABEL_12;
    }
  }
  else
  {
    v16 = 0;
  }
  v18 = 0;
  do
LABEL_12:
    ++v12;
  while ( v7[v12] );
  MbbWriteEvent(
    &CID_RESPONSE_RECVD,
    (LPCGUID)(a1 + 24),
    0,
    0xAu,
    v7,
    v12 + 1,
    a1 + 432,
    8,
    a1 + 16,
    4,
    &v35,
    16,
    v16,
    v18,
    &v28,
    4,
    &v32,
    4,
    &v31,
    4,
    &a5,
    4,
    a4,
    a5);
  if ( *(_BYTE *)(a1 + 576) )
  {
    LODWORD(v26) = a5;
    v30 = -2147483641;
    v29 = a5 + 44;
    MbbWriteEventOpn(
      &INDICATE_STATUS_MSG,
      (LPCGUID)(a1 + 24),
      0,
      9u,
      &v30,
      4,
      &v29,
      4,
      a1 + 20,
      4,
      &v34,
      4,
      &v33,
      4,
      &v35,
      16,
      &v28,
      4,
      &a5,
      4,
      a4,
      v26);
  }
  else
  {
    v19 = *(_QWORD *)(a1 + 80);
    if ( !v19
      || (v20 = *(void **)(v19 + 72), v20 != &MbbOpenDoneHandler)
      && v20 != MbbCloseDoneHandler
      && v20 != MbbModemNativeMBIMVersionHandler )
    {
      LODWORD(v27) = a5;
      v30 = -2147483645;
      v29 = a5 + 48;
      MbbWriteEventOpn(
        &COMMAND_DONE_MSG,
        (LPCGUID)(a1 + 24),
        0,
        0xAu,
        &v30,
        4,
        &v29,
        4,
        a1 + 20,
        4,
        &v34,
        4,
        &v33,
        4,
        &v35,
        16,
        &v28,
        4,
        &v32,
        4,
        &a5,
        4,
        a4,
        v27);
    }
  }
  if ( v10 == 259 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = MbbUtilGetCommandString((struct _MBB_COMMAND *)(a1 + 704));
      LOBYTE(v22) = 4;
      WPP_RECORDER_SF_Ds(
        WPP_GLOBAL_Control->DeviceExtension,
        v22,
        3,
        30,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
        *(_DWORD *)(a1 + 16),
        (__int64)v21);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MbbUtilGetCommandString((struct _MBB_COMMAND *)(a1 + 704));
      WPP_RECORDER_SF_Dsdq(WPP_GLOBAL_Control->DeviceExtension, v23, v24, 31);
    }
    v25 = *(void **)(a1 + 568);
    *(_DWORD *)(a1 + 696) = v31;
    if ( v25 )
    {
      ExFreePoolWithTag(v25, 0);
      *(_QWORD *)(a1 + 568) = 0;
    }
    KeSetEvent((PRKEVENT)(a1 + 56), 0, 0);
    MbbReqMgrDerefRequest((struct _MBB_REQUEST_CONTEXT *)a1);
  }
}

```

## disassembly

```asm
0x14001e250  push    rbp
0x14001e252  push    rbx
0x14001e253  push    rsi
0x14001e254  push    rdi
0x14001e255  push    r12
0x14001e257  push    r13
0x14001e259  push    r14
0x14001e25b  push    r15
0x14001e25d  lea     rbp, [rsp+38h]
0x14001e262  sub     rsp, 108h
0x14001e269  mov     rax, cs:__security_cookie
0x14001e270  xor     rax, rsp
0x14001e273  mov     [rbp+var_48], rax
0x14001e277  mov     r14, [rbp+arg_28]
0x14001e27b  lea     r12, aUnsolicited; "Unsolicited"
0x14001e282  xor     r11d, r11d
0x14001e285  mov     [rbp+var_70], edx
0x14001e288  mov     rsi, rcx
0x14001e28b  mov     [rbp+var_68], r8d
0x14001e28f  lea     rcx, aSolicited; "Solicited"
0x14001e296  mov     qword ptr [rbp+var_58], r11
0x14001e29a  mov     r13, r9
0x14001e29d  mov     qword ptr [rbp+var_58+8], r11
0x14001e2a1  mov     edi, r11d
0x14001e2a4  mov     [rbp+var_80], r11d
0x14001e2a8  cmp     [rsi+240h], r11b
0x14001e2af  mov     [rbp+var_78], r11d
0x14001e2b3  cmovz   r12, rcx
0x14001e2b7  mov     [rbp+var_7C], r11d
0x14001e2bb  or      r15, 0FFFFFFFFFFFFFFFFh
0x14001e2bf  mov     [rbp+var_5C], 1
0x14001e2c6  mov     [rbp+var_60], r11d
0x14001e2ca  test    r14, r14
0x14001e2cd  jz      short loc_14001E326
0x14001e2cf  mov     r10, [r14+48h]
0x14001e2d3  test    r10, r10
0x14001e2d6  jz      short loc_14001E2EF
0x14001e2d8  mov     eax, [rbp+arg_20]
0x14001e2db  mov     rcx, rsi
0x14001e2de  mov     dword ptr [rsp+140h+var_120], eax
0x14001e2e2  mov     rax, r10
0x14001e2e5  call    _guard_dispatch_icall
0x14001e2ea  mov     edi, eax
0x14001e2ec  mov     [rbp+var_70], eax
0x14001e2ef  lea     rcx, [r14+30h]; Source1
0x14001e2f3  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14001e2f8  movups  xmm0, xmmword ptr [r14+30h]
0x14001e2fd  mov     ecx, [r14+40h]
0x14001e301  xor     r11d, r11d
0x14001e304  mov     [rbp+var_80], ecx
0x14001e307  mov     rdx, rax
0x14001e30a  movdqu  [rbp+var_58], xmm0
0x14001e30f  test    rax, rax
0x14001e312  jz      short loc_14001E329
0x14001e314  mov     rax, r15
0x14001e317  inc     rax
0x14001e31a  cmp     [rdx+rax], r11b
0x14001e31e  jnz     short loc_14001E317
0x14001e320  lea     r8, [rax+1]
0x14001e324  jmp     short loc_14001E32C
0x14001e326  mov     rdx, r11
0x14001e329  mov     r8, r11
0x14001e32c  lea     r14, [rsi+10h]
0x14001e330  lea     r9, [rsi+1B0h]
0x14001e337  inc     r15
0x14001e33a  cmp     [r12+r15], r11b
0x14001e33e  jnz     short loc_14001E337
0x14001e340  mov     eax, [rbp+arg_20]
0x14001e343  lea     rcx, [r15+1]
0x14001e347  mov     dword ptr [rsp+140h+var_88], eax
0x14001e34e  lea     rbx, [rsi+18h]
0x14001e352  mov     [rsp+140h+var_90], r13
0x14001e35a  lea     rax, [rbp+arg_20]
0x14001e35e  mov     r10d, 0Ah
0x14001e364  lea     r15d, [r10-6]
0x14001e368  mov     [rsp+140h+var_98], r15
0x14001e370  mov     [rsp+140h+var_A0], rax
0x14001e378  lea     rax, [rbp+var_70]
0x14001e37c  mov     [rsp+140h+var_A8], r15
0x14001e384  mov     [rsp+140h+var_B0], rax
0x14001e38c  lea     rax, [rbp+var_68]
0x14001e390  mov     [rsp+140h+var_B8], r15
0x14001e398  mov     [rsp+140h+var_C0], rax
0x14001e3a0  lea     rax, [rbp+var_80]
0x14001e3a4  mov     [rsp+140h+var_C8], r15
0x14001e3a9  mov     [rsp+140h+var_D0], rax
0x14001e3ae  lea     rax, [rbp+var_58]
0x14001e3b2  mov     [rsp+140h+var_D8], r8
0x14001e3b7  xor     r8d, r8d; RelatedActivityId
0x14001e3ba  mov     [rsp+140h+var_E0], rdx
0x14001e3bf  mov     rdx, rbx; ActivityId
0x14001e3c2  mov     [rsp+140h+var_E8], 10h
0x14001e3cb  mov     [rsp+140h+var_F0], rax
0x14001e3d0  mov     [rsp+140h+var_F8], r15
0x14001e3d5  mov     [rsp+140h+var_100], r14
0x14001e3da  mov     [rsp+140h+var_108], 8
0x14001e3e3  mov     [rsp+140h+var_110], r9
0x14001e3e8  mov     r9d, r10d; unsigned __int16
0x14001e3eb  mov     [rsp+140h+var_118], rcx
0x14001e3f0  lea     rcx, CID_RESPONSE_RECVD; EventDescriptor
0x14001e3f7  mov     [rsp+140h+var_120], r12
0x14001e3fc  call    ?MbbWriteEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEvent(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x14001e401  cmp     byte ptr [rsi+240h], 0
0x14001e408  jz      loc_14001E4C8
0x14001e40e  mov     ecx, [rbp+arg_20]
0x14001e411  lea     r9d, [r15+5]; unsigned __int16
0x14001e415  mov     dword ptr [rsp+140h+var_98], ecx
0x14001e41c  xor     r8d, r8d; RelatedActivityId
0x14001e41f  mov     [rsp+140h+var_A0], r13
0x14001e427  mov     rdx, rbx; ActivityId
0x14001e42a  mov     [rsp+140h+var_A8], r15
0x14001e432  lea     eax, [rcx+2Ch]
0x14001e435  mov     [rbp+var_78], 80000007h
0x14001e43c  mov     [rbp+var_7C], eax
0x14001e43f  lea     rcx, [rbp+arg_20]
0x14001e443  mov     [rsp+140h+var_B0], rcx
0x14001e44b  lea     rax, [rsi+14h]
0x14001e44f  mov     [rsp+140h+var_B8], r15
0x14001e457  lea     rcx, [rbp+var_80]
0x14001e45b  mov     [rsp+140h+var_C0], rcx
0x14001e463  lea     rcx, [rbp+var_58]
0x14001e467  mov     [rsp+140h+var_C8], 10h
0x14001e470  mov     [rsp+140h+var_D0], rcx
0x14001e475  lea     rcx, [rbp+var_60]
0x14001e479  mov     [rsp+140h+var_D8], r15
0x14001e47e  mov     [rsp+140h+var_E0], rcx
0x14001e483  lea     rcx, [rbp+var_5C]
0x14001e487  mov     [rsp+140h+var_E8], r15
0x14001e48c  mov     [rsp+140h+var_F0], rcx
0x14001e491  lea     rcx, INDICATE_STATUS_MSG; EventDescriptor
0x14001e498  mov     [rsp+140h+var_F8], r15
0x14001e49d  mov     [rsp+140h+var_100], rax
0x14001e4a2  lea     rax, [rbp+var_7C]
0x14001e4a6  mov     [rsp+140h+var_108], r15
0x14001e4ab  mov     [rsp+140h+var_110], rax
0x14001e4b0  lea     rax, [rbp+var_78]
0x14001e4b4  mov     [rsp+140h+var_118], r15
0x14001e4b9  mov     [rsp+140h+var_120], rax
0x14001e4be  call    ?MbbWriteEventOpn@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEventOpn(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x14001e4c3  jmp     loc_14001E5D0
0x14001e4c8  mov     rax, [rsi+50h]
0x14001e4cc  test    rax, rax
0x14001e4cf  jz      short loc_14001E505
0x14001e4d1  mov     rax, [rax+48h]
0x14001e4d5  lea     rcx, ?MbbOpenDoneHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbOpenDoneHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x14001e4dc  cmp     rax, rcx
0x14001e4df  jz      loc_14001E5D0
0x14001e4e5  lea     rcx, ?MbbCloseDoneHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbCloseDoneHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x14001e4ec  cmp     rax, rcx
0x14001e4ef  jz      loc_14001E5D0
0x14001e4f5  lea     rcx, ?MbbModemNativeMBIMVersionHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbModemNativeMBIMVersionHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x14001e4fc  cmp     rax, rcx
0x14001e4ff  jz      loc_14001E5D0
0x14001e505  mov     ecx, [rbp+arg_20]
0x14001e508  mov     r9d, 0Ah; unsigned __int16
0x14001e50e  mov     dword ptr [rsp+140h+var_88], ecx
0x14001e515  xor     r8d, r8d; RelatedActivityId
0x14001e518  mov     [rsp+140h+var_90], r13
0x14001e520  mov     rdx, rbx; ActivityId
0x14001e523  mov     [rsp+140h+var_98], r15
0x14001e52b  lea     eax, [rcx+30h]
0x14001e52e  mov     [rbp+var_78], 80000003h
0x14001e535  mov     [rbp+var_7C], eax
0x14001e538  lea     rcx, [rbp+arg_20]
0x14001e53c  mov     [rsp+140h+var_A0], rcx
0x14001e544  lea     rax, [rsi+14h]
0x14001e548  mov     [rsp+140h+var_A8], r15
0x14001e550  lea     rcx, [rbp+var_68]
0x14001e554  mov     [rsp+140h+var_B0], rcx
0x14001e55c  lea     rcx, [rbp+var_80]
0x14001e560  mov     [rsp+140h+var_B8], r15
0x14001e568  mov     [rsp+140h+var_C0], rcx
0x14001e570  lea     rcx, [rbp+var_58]
0x14001e574  mov     [rsp+140h+var_C8], 10h
0x14001e57d  mov     [rsp+140h+var_D0], rcx
0x14001e582  lea     rcx, [rbp+var_60]
0x14001e586  mov     [rsp+140h+var_D8], r15
0x14001e58b  mov     [rsp+140h+var_E0], rcx
0x14001e590  lea     rcx, [rbp+var_5C]
0x14001e594  mov     [rsp+140h+var_E8], r15
0x14001e599  mov     [rsp+140h+var_F0], rcx
0x14001e59e  lea     rcx, COMMAND_DONE_MSG; EventDescriptor
0x14001e5a5  mov     [rsp+140h+var_F8], r15
0x14001e5aa  mov     [rsp+140h+var_100], rax
0x14001e5af  lea     rax, [rbp+var_7C]
0x14001e5b3  mov     [rsp+140h+var_108], r15
0x14001e5b8  mov     [rsp+140h+var_110], rax
0x14001e5bd  lea     rax, [rbp+var_78]
0x14001e5c1  mov     [rsp+140h+var_118], r15
0x14001e5c6  mov     [rsp+140h+var_120], rax
0x14001e5cb  call    ?MbbWriteEventOpn@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEventOpn(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x14001e5d0  cmp     edi, 103h
0x14001e5d6  jnz     short loc_14001E632
0x14001e5d8  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e5df  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e5e6  jz      loc_14001E6CE
0x14001e5ec  lea     rcx, [rsi+2C0h]; Source1
0x14001e5f3  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14001e5f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e5ff  mov     r9d, 1Eh
0x14001e605  mov     [rsp+140h+var_110], rax
0x14001e60a  mov     dl, r15b
0x14001e60d  mov     eax, [r14]
0x14001e610  mov     dword ptr [rsp+140h+var_118], eax
0x14001e614  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001e61b  mov     rcx, [rcx+40h]
0x14001e61f  lea     r8d, [r9-1Bh]
0x14001e623  mov     [rsp+140h+var_120], rax
0x14001e628  call    WPP_RECORDER_SF_Ds
0x14001e62d  jmp     loc_14001E6CE
0x14001e632  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e639  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e640  jz      short loc_14001E683
0x14001e642  mov     rbx, [rsi+238h]
0x14001e649  lea     rcx, [rsi+2C0h]; Source1
0x14001e650  mov     edi, [rbp+var_70]
0x14001e653  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14001e658  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e65f  mov     r9d, 1Fh
0x14001e665  mov     [rsp+140h+var_100], rbx
0x14001e66a  mov     dword ptr [rsp+140h+var_108], edi
0x14001e66e  mov     [rsp+140h+var_110], rax
0x14001e673  mov     eax, [r14]
0x14001e676  mov     rcx, [rcx+40h]
0x14001e67a  mov     dword ptr [rsp+140h+var_118], eax
0x14001e67e  call    WPP_RECORDER_SF_Dsdq
0x14001e683  mov     rcx, [rsi+238h]; P
0x14001e68a  mov     eax, [rbp+var_70]
0x14001e68d  mov     [rsi+2B8h], eax
0x14001e693  test    rcx, rcx
0x14001e696  jz      short loc_14001E6B1
0x14001e698  xor     edx, edx; Tag
0x14001e69a  call    cs:__imp_ExFreePoolWithTag
0x14001e6a1  nop     dword ptr [rax+rax+00h]
0x14001e6a6  mov     qword ptr [rsi+238h], 0
0x14001e6b1  lea     rcx, [rsi+38h]; Event
0x14001e6b5  xor     r8d, r8d; Wait
0x14001e6b8  xor     edx, edx; Increment
0x14001e6ba  call    cs:__imp_KeSetEvent
0x14001e6c1  nop     dword ptr [rax+rax+00h]
0x14001e6c6  mov     rcx, rsi; struct _MBB_REQUEST_CONTEXT *
0x14001e6c9  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14001e6ce  mov     rcx, [rbp+var_48]
0x14001e6d2  xor     rcx, rsp; StackCookie
0x14001e6d5  call    __security_check_cookie
0x14001e6da  add     rsp, 108h
0x14001e6e1  pop     r15
0x14001e6e3  pop     r14
0x14001e6e5  pop     r13
0x14001e6e7  pop     r12
0x14001e6e9  pop     rdi
0x14001e6ea  pop     rsi
0x14001e6eb  pop     rbx
0x14001e6ec  pop     rbp
0x14001e6ed  retn
```
