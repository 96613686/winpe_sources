# MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO_EX3>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140028cb8`
- end: `0x1400291ba`
- name: `??$MbbNdisReadyInfoStatusHandlerHelper@U_MBB_SUBSCRIBER_READY_INFO_EX3@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `1282`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, int, unsigned int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x140033ef0`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x140017fb4`
- `0x140028cb8`
- `0x14002f228`
- `0x14003b2f8`
- `0x14003b670`
- `0x14003bacc`
- `0x14003bc04`
- `0x14003c4a0`
- `0x14003df70`
- `0x14003f7e4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140029048`
- `ntoskrnl!ExAllocatePool2` at `0x140029048`

## pseudocode

```c
__int64 __fastcall MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO_EX3>(
        struct _MBB_REQUEST_CONTEXT *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  int v6; // r15d
  int v7; // ebx
  int v9; // eax
  int v10; // edx
  int v11; // r14d
  unsigned int v12; // eax
  unsigned int v13; // r13d
  _DWORD *v14; // r14
  unsigned int v15; // r8d
  int v16; // edx
  int v17; // r9d
  unsigned int v18; // r8d
  __int64 v19; // r12
  int v20; // edx
  int v21; // r15d
  _DWORD *Pool2; // rax
  int v23; // edx
  int v25; // [rsp+20h] [rbp-78h]
  char v26; // [rsp+30h] [rbp-68h]
  __int64 v27; // [rsp+38h] [rbp-60h]
  __int64 v28; // [rsp+A0h] [rbp+8h]
  unsigned int v29; // [rsp+A8h] [rbp+10h]

  v6 = a3;
  v7 = a2;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v26 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        27,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4),
        v26);
    }
    goto LABEL_51;
  }
  v28 = **((_QWORD **)a1 + 6);
  v9 = MbbUtilMbbToWwanStatus(a3);
  v11 = v9;
  if ( v9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_DDL(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        a3,
        28,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4),
        v9,
        v6);
    }
    v7 = v11;
    goto LABEL_51;
  }
  if ( !a4 || a5 < 0x20 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        29,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *((_DWORD *)a1 + 4),
        a5,
        32);
    }
    goto LABEL_50;
  }
  v12 = *(_DWORD *)(a4 + 28);
  v13 = 100;
  if ( v12 <= 0x64 )
  {
    v13 = *(_DWORD *)(a4 + 28);
    v14 = (_DWORD *)((char *)a1 + 16);
  }
  else
  {
    v14 = (_DWORD *)((char *)a1 + 16);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 3;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        30,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *v14,
        v12);
    }
    *(_DWORD *)(a4 + 28) = 100;
  }
  if ( a5 < 8 * (unsigned __int64)v13 + 32 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DdId(WPP_GLOBAL_Control->DeviceExtension, v10, a3, 31);
    goto LABEL_50;
  }
  v15 = *(_DWORD *)(a4 + 12);
  if ( v15 > 0x1E )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        3,
        32,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *v14,
        v15,
        30);
      v14 = (_DWORD *)((char *)a1 + 16);
    }
    *(_DWORD *)(a4 + 12) = 30;
    v15 = 30;
  }
  if ( (unsigned int)MbbIsVariableFieldValid(a5, *(_DWORD *)(a4 + 8), v15, 0xFu, 2u, 1) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_50:
      v7 = -1073676267;
      goto LABEL_51;
    }
    v17 = 33;
LABEL_25:
    WPP_RECORDER_SF_Ddddd(WPP_GLOBAL_Control->DeviceExtension, v16, a3, v17);
    goto LABEL_50;
  }
  v18 = *(_DWORD *)(a4 + 20);
  if ( v18 > 0x28 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      LODWORD(v27) = 40;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        3,
        34,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *v14,
        v18,
        v27);
      v14 = (_DWORD *)((char *)a1 + 16);
    }
    *(_DWORD *)(a4 + 20) = 40;
    v18 = 40;
  }
  if ( (unsigned int)MbbIsVariableFieldValid(a5, *(_DWORD *)(a4 + 16), v18, 0x14u, 2u, 1) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_50;
    v17 = 35;
    goto LABEL_25;
  }
  v19 = 0;
  if ( v13 )
  {
    while ( 1 )
    {
      v29 = *(_BYTE *)(v28 + 88) != 0 ? 22 : 15;
      if ( (unsigned int)MbbIsVariableFieldValid(
                           a5,
                           *(_DWORD *)(a4 + 8 * v19 + 32),
                           *(_DWORD *)(a4 + 8 * v19 + 36),
                           v29,
                           2u,
                           1) )
        break;
      v19 = (unsigned int)(v19 + 1);
      if ( (unsigned int)v19 >= v13 )
      {
        v14 = (_DWORD *)((char *)a1 + 16);
        goto LABEL_37;
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Dddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v20,
        a3,
        36,
        v25,
        *((_DWORD *)a1 + 4),
        v19,
        *(_DWORD *)(a4 + 8 * v19 + 32),
        a5,
        *(_DWORD *)(a4 + 8 * v19 + 36),
        2 * v29);
    goto LABEL_50;
  }
LABEL_37:
  v21 = 46 * v13 + 104;
  Pool2 = (_DWORD *)ExAllocatePool2(64, 46LL * v13 + 104, 1683505741);
  if ( Pool2 )
  {
    *Pool2 = 6816384;
    *((_DWORD *)a1 + 183) = v21;
    *((_QWORD *)a1 + 92) = Pool2;
    MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO_EX3>((_DWORD *)a4, Pool2 + 1);
    if ( ((*(_DWORD *)a4 - 1) & 0xFFFFFFFA) != 0 || *(_DWORD *)a4 == 2 || (*(_BYTE *)(a4 + 24) & 1) != 0 )
      *(_DWORD *)(v28 + 1088) &= ~0x20u;
    else
      *(_DWORD *)(v28 + 1088) |= 0x20u;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DId(WPP_GLOBAL_Control->DeviceExtension, v23, a3, a4, v25, *v14, v21, *(_DWORD *)(a4 + 28));
    v7 = -1073741670;
  }
LABEL_51:
  MbbNdisIndicateReadyInfo(a1, v7, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x140028cb8  mov     [rsp+arg_10], rbx
0x140028cbd  push    rbp
0x140028cbe  push    rsi
0x140028cbf  push    rdi
0x140028cc0  push    r12
0x140028cc2  push    r13
0x140028cc4  push    r14
0x140028cc6  push    r15
0x140028cc8  sub     rsp, 60h
0x140028ccc  mov     rdi, r9
0x140028ccf  mov     r15d, r8d
0x140028cd2  mov     ebx, edx
0x140028cd4  mov     rbp, rcx
0x140028cd7  test    edx, edx
0x140028cd9  jz      short loc_140028D27
0x140028cdb  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028ce2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028ce9  jz      loc_140029195
0x140028cef  mov     eax, [rcx+10h]
0x140028cf2  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x140028d00  mov     r9d, 1Bh
0x140028d06  mov     dword ptr [rsp+98h+var_68], edx
0x140028d0a  mov     dl, 2
0x140028d0c  mov     [rsp+98h+var_70], eax
0x140028d10  mov     qword ptr [rsp+98h+var_78], r12
0x140028d15  mov     rcx, [rcx+40h]
0x140028d19  lea     r8d, [r9-18h]
0x140028d1d  call    WPP_RECORDER_SF_DD
0x140028d22  jmp     loc_140029195
0x140028d27  mov     rax, [rcx+30h]
0x140028d2b  mov     ecx, r15d
0x140028d2e  mov     rax, [rax]
0x140028d31  mov     [rsp+98h+arg_0], rax
0x140028d39  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140028d3e  mov     r14d, eax
0x140028d41  test    eax, eax
0x140028d43  jz      short loc_140028D91
0x140028d45  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028d4c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028d53  jz      short loc_140028D89
0x140028d55  mov     ecx, [rbp+10h]
0x140028d58  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028d5f  mov     dword ptr [rsp+98h+var_60], r15d
0x140028d64  mov     r9d, 1Ch
0x140028d6a  mov     dword ptr [rsp+98h+var_68], eax
0x140028d6e  mov     dl, 2
0x140028d70  mov     [rsp+98h+var_70], ecx
0x140028d74  mov     rcx, cs:WPP_GLOBAL_Control
0x140028d7b  mov     qword ptr [rsp+98h+var_78], r12
0x140028d80  mov     rcx, [rcx+40h]
0x140028d84  call    WPP_RECORDER_SF_DDL
0x140028d89  mov     ebx, r14d
0x140028d8c  jmp     loc_140029195
0x140028d91  mov     r15d, [rsp+98h+arg_20]
0x140028d99  test    rdi, rdi
0x140028d9c  jz      loc_140029144
0x140028da2  cmp     r15d, 20h ; ' '
0x140028da6  jb      loc_140029144
0x140028dac  mov     eax, [rdi+1Ch]
0x140028daf  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028db6  mov     r13d, 64h ; 'd'
0x140028dbc  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028dc3  cmp     eax, r13d
0x140028dc6  jbe     short loc_140028E06
0x140028dc8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028dcf  lea     r14, [rbp+10h]
0x140028dd3  jz      short loc_140028E00
0x140028dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140028ddc  lea     r8d, [r13-61h]
0x140028de0  mov     dword ptr [rsp+98h+var_68], eax
0x140028de4  lea     r9d, [r13-46h]
0x140028de8  mov     eax, [r14]
0x140028deb  mov     dl, r8b
0x140028dee  mov     [rsp+98h+var_70], eax
0x140028df2  mov     rcx, [rcx+40h]
0x140028df6  mov     qword ptr [rsp+98h+var_78], r12
0x140028dfb  call    WPP_RECORDER_SF_DD
0x140028e00  mov     [rdi+1Ch], r13d
0x140028e04  jmp     short loc_140028E0D
0x140028e06  mov     r13d, eax
0x140028e09  lea     r14, [rbp+10h]
0x140028e0d  mov     eax, r13d
0x140028e10  mov     [rsp+98h+arg_18], rax
0x140028e18  lea     rcx, ds:20h[rax*8]
0x140028e20  cmp     r15, rcx
0x140028e23  jnb     short loc_140028E63
0x140028e25  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028e2c  jz      loc_140029190
0x140028e32  mov     eax, [rbp+10h]
0x140028e35  mov     r9d, 1Fh
0x140028e3b  mov     [rsp+98h+var_58], r13d
0x140028e40  mov     [rsp+98h+var_60], rcx
0x140028e45  mov     rcx, cs:WPP_GLOBAL_Control
0x140028e4c  mov     dword ptr [rsp+98h+var_68], r15d
0x140028e51  mov     [rsp+98h+var_70], eax
0x140028e55  mov     rcx, [rcx+40h]
0x140028e59  call    WPP_RECORDER_SF_DdId
0x140028e5e  jmp     loc_140029190
0x140028e63  mov     r8d, [rdi+0Ch]
0x140028e67  cmp     r8d, 1Eh
0x140028e6b  jbe     short loc_140028EBC
0x140028e6d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028e74  jz      short loc_140028EAF
0x140028e76  mov     rcx, cs:WPP_GLOBAL_Control
0x140028e7d  mov     r9d, 20h ; ' '
0x140028e83  mov     eax, [r14]
0x140028e86  mov     dl, 2
0x140028e88  mov     dword ptr [rsp+98h+var_60], 1Eh
0x140028e90  mov     dword ptr [rsp+98h+var_68], r8d
0x140028e95  mov     rcx, [rcx+40h]
0x140028e99  lea     r8d, [r9-1Dh]
0x140028e9d  mov     [rsp+98h+var_70], eax
0x140028ea1  mov     qword ptr [rsp+98h+var_78], r12
0x140028ea6  call    WPP_RECORDER_SF_Ddd
0x140028eab  lea     r14, [rbp+10h]
0x140028eaf  mov     dword ptr [rdi+0Ch], 1Eh
0x140028eb6  mov     r8d, 1Eh; unsigned int
0x140028ebc  mov     edx, [rdi+8]; unsigned int
0x140028ebf  mov     r9d, 0Fh; unsigned int
0x140028ec5  mov     [rsp+98h+var_70], 1; int
0x140028ecd  mov     ecx, r15d; unsigned int
0x140028ed0  mov     [rsp+98h+var_78], 2; unsigned int
0x140028ed8  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x140028edd  test    eax, eax
0x140028edf  jz      short loc_140028F2B
0x140028ee1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028ee8  jz      loc_140029190
0x140028eee  mov     eax, [rdi+0Ch]
0x140028ef1  mov     r9d, 21h ; '!'
0x140028ef7  mov     [rsp+98h+var_50], 1Eh
0x140028eff  mov     [rsp+98h+var_58], eax
0x140028f03  mov     eax, [rdi+8]
0x140028f06  mov     rcx, cs:WPP_GLOBAL_Control
0x140028f0d  mov     dword ptr [rsp+98h+var_60], r15d
0x140028f12  mov     dword ptr [rsp+98h+var_68], eax
0x140028f16  mov     eax, [r14]
0x140028f19  mov     rcx, [rcx+40h]
0x140028f1d  mov     [rsp+98h+var_70], eax
0x140028f21  call    WPP_RECORDER_SF_Ddddd
0x140028f26  jmp     loc_140029190
0x140028f2b  mov     r8d, [rdi+14h]
0x140028f2f  cmp     r8d, 28h ; '('
0x140028f33  jbe     short loc_140028F84
0x140028f35  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028f3c  jz      short loc_140028F77
0x140028f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028f45  mov     r9d, 22h ; '"'
0x140028f4b  mov     eax, [r14]
0x140028f4e  mov     dl, 2
0x140028f50  mov     dword ptr [rsp+98h+var_60], 28h ; '('
0x140028f58  mov     dword ptr [rsp+98h+var_68], r8d
0x140028f5d  mov     rcx, [rcx+40h]
0x140028f61  lea     r8d, [r9-1Fh]
0x140028f65  mov     [rsp+98h+var_70], eax
0x140028f69  mov     qword ptr [rsp+98h+var_78], r12
0x140028f6e  call    WPP_RECORDER_SF_Ddd
0x140028f73  lea     r14, [rbp+10h]
0x140028f77  mov     dword ptr [rdi+14h], 28h ; '('
0x140028f7e  mov     r8d, 28h ; '('; unsigned int
0x140028f84  mov     edx, [rdi+10h]; unsigned int
0x140028f87  mov     r9d, 14h; unsigned int
0x140028f8d  mov     [rsp+98h+var_70], 1; int
0x140028f95  mov     ecx, r15d; unsigned int
0x140028f98  mov     [rsp+98h+var_78], 2; unsigned int
0x140028fa0  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x140028fa5  test    eax, eax
0x140028fa7  jz      short loc_140028FD3
0x140028fa9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028fb0  jz      loc_140029190
0x140028fb6  mov     eax, [rdi+14h]
0x140028fb9  mov     r9d, 23h ; '#'
0x140028fbf  mov     [rsp+98h+var_50], 28h ; '('
0x140028fc7  mov     [rsp+98h+var_58], eax
0x140028fcb  mov     eax, [rdi+10h]
0x140028fce  jmp     loc_140028F06
0x140028fd3  xor     r12d, r12d
0x140028fd6  test    r13d, r13d
0x140028fd9  jz      short loc_14002902D
0x140028fdb  mov     r14, [rsp+98h+arg_0]
0x140028fe3  mov     al, [r14+58h]
0x140028fe7  mov     r8d, [rdi+r12*8+24h]; unsigned int
0x140028fec  neg     al
0x140028fee  mov     edx, [rdi+r12*8+20h]; unsigned int
0x140028ff3  sbb     ecx, ecx
0x140028ff5  mov     [rsp+98h+var_70], 1; int
0x140028ffd  and     ecx, 7
0x140029000  mov     [rsp+98h+var_78], 2; unsigned int
0x140029008  add     ecx, 0Fh
0x14002900b  mov     [rsp+98h+arg_8], ecx
0x140029012  mov     r9d, ecx; unsigned int
0x140029015  mov     ecx, r15d; unsigned int
0x140029018  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x14002901d  test    eax, eax
0x14002901f  jnz     short loc_140029093
0x140029021  inc     r12d
0x140029024  cmp     r12d, r13d
0x140029027  jb      short loc_140028FE3
0x140029029  lea     r14, [rbp+10h]
0x14002902d  imul    r15, [rsp+98h+arg_18], 2Eh ; '.'
0x140029036  mov     r8d, 6458424Dh
0x14002903c  mov     ecx, 40h ; '@'
0x140029041  add     r15, 68h ; 'h'
0x140029045  mov     rdx, r15
0x140029048  call    cs:__imp_ExAllocatePool2
0x14002904f  nop     dword ptr [rax+rax+00h]
0x140029054  test    rax, rax
0x140029057  jnz     loc_1400290EB
0x14002905d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029064  jz      short loc_140029089
0x140029066  mov     eax, [rdi+1Ch]
0x140029069  mov     rcx, cs:WPP_GLOBAL_Control
0x140029070  mov     dword ptr [rsp+98h+var_60], eax
0x140029074  mov     eax, [r14]
0x140029077  mov     [rsp+98h+var_68], r15
0x14002907c  mov     rcx, [rcx+40h]
0x140029080  mov     [rsp+98h+var_70], eax
0x140029084  call    WPP_RECORDER_SF_DId
0x140029089  mov     ebx, 0C000009Ah
0x14002908e  jmp     loc_140029195
0x140029093  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002909a  jz      loc_140029190
0x1400290a0  mov     eax, [rsp+98h+arg_8]
0x1400290a7  mov     r9d, 24h ; '$'
0x1400290ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400290b4  add     eax, eax
0x1400290b6  mov     [rsp+98h+var_48], eax
0x1400290ba  mov     eax, [rdi+r12*8+24h]
0x1400290bf  mov     [rsp+98h+var_50], eax
0x1400290c3  mov     eax, [rdi+r12*8+20h]
0x1400290c8  mov     rcx, [rcx+40h]
0x1400290cc  mov     [rsp+98h+var_58], r15d
0x1400290d1  mov     dword ptr [rsp+98h+var_60], eax
0x1400290d5  mov     eax, [rbp+10h]
0x1400290d8  mov     dword ptr [rsp+98h+var_68], r12d
0x1400290dd  mov     [rsp+98h+var_70], eax
0x1400290e1  call    WPP_RECORDER_SF_Dddddd
0x1400290e6  jmp     loc_140029190
0x1400290eb  lea     rdx, [rax+4]
0x1400290ef  mov     dword ptr [rax], 680280h
0x1400290f5  mov     rcx, rdi
0x1400290f8  mov     [rbp+2DCh], r15d
0x1400290ff  mov     [rbp+2E0h], rax
0x140029106  call    ??$MbbUtilMbbToWwanReadyInfo@U_MBB_SUBSCRIBER_READY_INFO_EX3@@@@YAXPEAU_MBB_SUBSCRIBER_READY_INFO_EX3@@PEAU_WWAN_READY_INFO@@@Z; MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO_EX3>(_MBB_SUBSCRIBER_READY_INFO_EX3 *,_WWAN_READY_INFO *)
0x14002910b  mov     ecx, [rdi]
0x14002910d  lea     eax, [rcx-1]
0x140029110  test    eax, 0FFFFFFFAh
0x140029115  jnz     short loc_140029133
0x140029117  cmp     ecx, 2
0x14002911a  jz      short loc_140029133
0x14002911c  test    byte ptr [rdi+18h], 1
0x140029120  jnz     short loc_140029133
0x140029122  mov     rax, [rsp+98h+arg_0]
0x14002912a  or      dword ptr [rax+440h], 20h
0x140029131  jmp     short loc_140029195
0x140029133  mov     rax, [rsp+98h+arg_0]
0x14002913b  and     dword ptr [rax+440h], 0FFFFFFDFh
0x140029142  jmp     short loc_140029195
0x140029144  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002914b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029152  jz      short loc_140029190
0x140029154  mov     rcx, cs:WPP_GLOBAL_Control
0x14002915b  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140029162  mov     eax, [rbp+10h]
0x140029165  mov     r9d, 1Dh
0x14002916b  mov     dword ptr [rsp+98h+var_60], 20h ; ' '
0x140029173  mov     dl, 2
0x140029175  mov     dword ptr [rsp+98h+var_68], r15d
0x14002917a  mov     rcx, [rcx+40h]
0x14002917e  mov     [rsp+98h+var_70], eax
0x140029182  lea     r8d, [r9-1Ah]
0x140029186  mov     qword ptr [rsp+98h+var_78], r12
0x14002918b  call    WPP_RECORDER_SF_Ddd
0x140029190  mov     ebx, 0C0010015h
0x140029195  mov     edx, ebx; int
0x140029197  mov     rcx, rbp; struct _MBB_REQUEST_CONTEXT *
0x14002919a  call    ?MbbNdisIndicateReadyInfo@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; MbbNdisIndicateReadyInfo(_MBB_REQUEST_CONTEXT *,int)
0x14002919f  mov     rbx, [rsp+98h+arg_10]
0x1400291a7  xor     eax, eax
0x1400291a9  add     rsp, 60h
0x1400291ad  pop     r15
0x1400291af  pop     r14
0x1400291b1  pop     r13
0x1400291b3  pop     r12
0x1400291b5  pop     rdi
0x1400291b6  pop     rsi
0x1400291b7  pop     rbp
0x1400291b8  retn
```
