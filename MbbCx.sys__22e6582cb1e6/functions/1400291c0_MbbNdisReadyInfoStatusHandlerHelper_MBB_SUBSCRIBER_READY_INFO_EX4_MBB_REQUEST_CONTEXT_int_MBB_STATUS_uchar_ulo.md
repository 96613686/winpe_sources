# MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO_EX4>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x1400291c0`
- end: `0x1400296c2`
- name: `??$MbbNdisReadyInfoStatusHandlerHelper@U_MBB_SUBSCRIBER_READY_INFO_EX4@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
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
- `0x1400291c0`
- `0x14002f228`
- `0x14003b2f8`
- `0x14003b670`
- `0x14003bacc`
- `0x14003bc04`
- `0x14003c588`
- `0x14003df70`
- `0x14003f7e4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140029550`
- `ntoskrnl!ExAllocatePool2` at `0x140029550`

## pseudocode

```c
__int64 __fastcall MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO_EX4>(
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
  if ( a5 < 8 * (unsigned __int64)v13 + 36 )
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
                           *(_DWORD *)(a4 + 8 * v19 + 36),
                           *(_DWORD *)(a4 + 8 * v19 + 40),
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
        *(_DWORD *)(a4 + 8 * v19 + 36),
        a5,
        *(_DWORD *)(a4 + 8 * v19 + 40),
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
    MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO_EX4>((_DWORD *)a4, Pool2 + 1);
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
0x1400291c0  mov     [rsp+arg_10], rbx
0x1400291c5  push    rbp
0x1400291c6  push    rsi
0x1400291c7  push    rdi
0x1400291c8  push    r12
0x1400291ca  push    r13
0x1400291cc  push    r14
0x1400291ce  push    r15
0x1400291d0  sub     rsp, 60h
0x1400291d4  mov     rdi, r9
0x1400291d7  mov     r15d, r8d
0x1400291da  mov     ebx, edx
0x1400291dc  mov     rbp, rcx
0x1400291df  test    edx, edx
0x1400291e1  jz      short loc_14002922F
0x1400291e3  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400291ea  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400291f1  jz      loc_14002969D
0x1400291f7  mov     eax, [rcx+10h]
0x1400291fa  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140029201  mov     rcx, cs:WPP_GLOBAL_Control
0x140029208  mov     r9d, 1Bh
0x14002920e  mov     dword ptr [rsp+98h+var_68], edx
0x140029212  mov     dl, 2
0x140029214  mov     [rsp+98h+var_70], eax
0x140029218  mov     qword ptr [rsp+98h+var_78], r12
0x14002921d  mov     rcx, [rcx+40h]
0x140029221  lea     r8d, [r9-18h]
0x140029225  call    WPP_RECORDER_SF_DD
0x14002922a  jmp     loc_14002969D
0x14002922f  mov     rax, [rcx+30h]
0x140029233  mov     ecx, r15d
0x140029236  mov     rax, [rax]
0x140029239  mov     [rsp+98h+arg_0], rax
0x140029241  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140029246  mov     r14d, eax
0x140029249  test    eax, eax
0x14002924b  jz      short loc_140029299
0x14002924d  lea     rsi, WPP_RECORDER_INITIALIZED
0x140029254  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002925b  jz      short loc_140029291
0x14002925d  mov     ecx, [rbp+10h]
0x140029260  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140029267  mov     dword ptr [rsp+98h+var_60], r15d
0x14002926c  mov     r9d, 1Ch
0x140029272  mov     dword ptr [rsp+98h+var_68], eax
0x140029276  mov     dl, 2
0x140029278  mov     [rsp+98h+var_70], ecx
0x14002927c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029283  mov     qword ptr [rsp+98h+var_78], r12
0x140029288  mov     rcx, [rcx+40h]
0x14002928c  call    WPP_RECORDER_SF_DDL
0x140029291  mov     ebx, r14d
0x140029294  jmp     loc_14002969D
0x140029299  mov     r15d, [rsp+98h+arg_20]
0x1400292a1  test    rdi, rdi
0x1400292a4  jz      loc_14002964C
0x1400292aa  cmp     r15d, 20h ; ' '
0x1400292ae  jb      loc_14002964C
0x1400292b4  mov     eax, [rdi+1Ch]
0x1400292b7  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400292be  mov     r13d, 64h ; 'd'
0x1400292c4  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400292cb  cmp     eax, r13d
0x1400292ce  jbe     short loc_14002930E
0x1400292d0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400292d7  lea     r14, [rbp+10h]
0x1400292db  jz      short loc_140029308
0x1400292dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400292e4  lea     r8d, [r13-61h]
0x1400292e8  mov     dword ptr [rsp+98h+var_68], eax
0x1400292ec  lea     r9d, [r13-46h]
0x1400292f0  mov     eax, [r14]
0x1400292f3  mov     dl, r8b
0x1400292f6  mov     [rsp+98h+var_70], eax
0x1400292fa  mov     rcx, [rcx+40h]
0x1400292fe  mov     qword ptr [rsp+98h+var_78], r12
0x140029303  call    WPP_RECORDER_SF_DD
0x140029308  mov     [rdi+1Ch], r13d
0x14002930c  jmp     short loc_140029315
0x14002930e  mov     r13d, eax
0x140029311  lea     r14, [rbp+10h]
0x140029315  mov     eax, r13d
0x140029318  mov     [rsp+98h+arg_18], rax
0x140029320  lea     rcx, ds:24h[rax*8]
0x140029328  cmp     r15, rcx
0x14002932b  jnb     short loc_14002936B
0x14002932d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029334  jz      loc_140029698
0x14002933a  mov     eax, [rbp+10h]
0x14002933d  mov     r9d, 1Fh
0x140029343  mov     [rsp+98h+var_58], r13d
0x140029348  mov     [rsp+98h+var_60], rcx
0x14002934d  mov     rcx, cs:WPP_GLOBAL_Control
0x140029354  mov     dword ptr [rsp+98h+var_68], r15d
0x140029359  mov     [rsp+98h+var_70], eax
0x14002935d  mov     rcx, [rcx+40h]
0x140029361  call    WPP_RECORDER_SF_DdId
0x140029366  jmp     loc_140029698
0x14002936b  mov     r8d, [rdi+0Ch]
0x14002936f  cmp     r8d, 1Eh
0x140029373  jbe     short loc_1400293C4
0x140029375  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002937c  jz      short loc_1400293B7
0x14002937e  mov     rcx, cs:WPP_GLOBAL_Control
0x140029385  mov     r9d, 20h ; ' '
0x14002938b  mov     eax, [r14]
0x14002938e  mov     dl, 2
0x140029390  mov     dword ptr [rsp+98h+var_60], 1Eh
0x140029398  mov     dword ptr [rsp+98h+var_68], r8d
0x14002939d  mov     rcx, [rcx+40h]
0x1400293a1  lea     r8d, [r9-1Dh]
0x1400293a5  mov     [rsp+98h+var_70], eax
0x1400293a9  mov     qword ptr [rsp+98h+var_78], r12
0x1400293ae  call    WPP_RECORDER_SF_Ddd
0x1400293b3  lea     r14, [rbp+10h]
0x1400293b7  mov     dword ptr [rdi+0Ch], 1Eh
0x1400293be  mov     r8d, 1Eh; unsigned int
0x1400293c4  mov     edx, [rdi+8]; unsigned int
0x1400293c7  mov     r9d, 0Fh; unsigned int
0x1400293cd  mov     [rsp+98h+var_70], 1; int
0x1400293d5  mov     ecx, r15d; unsigned int
0x1400293d8  mov     [rsp+98h+var_78], 2; unsigned int
0x1400293e0  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x1400293e5  test    eax, eax
0x1400293e7  jz      short loc_140029433
0x1400293e9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400293f0  jz      loc_140029698
0x1400293f6  mov     eax, [rdi+0Ch]
0x1400293f9  mov     r9d, 21h ; '!'
0x1400293ff  mov     [rsp+98h+var_50], 1Eh
0x140029407  mov     [rsp+98h+var_58], eax
0x14002940b  mov     eax, [rdi+8]
0x14002940e  mov     rcx, cs:WPP_GLOBAL_Control
0x140029415  mov     dword ptr [rsp+98h+var_60], r15d
0x14002941a  mov     dword ptr [rsp+98h+var_68], eax
0x14002941e  mov     eax, [r14]
0x140029421  mov     rcx, [rcx+40h]
0x140029425  mov     [rsp+98h+var_70], eax
0x140029429  call    WPP_RECORDER_SF_Ddddd
0x14002942e  jmp     loc_140029698
0x140029433  mov     r8d, [rdi+14h]
0x140029437  cmp     r8d, 28h ; '('
0x14002943b  jbe     short loc_14002948C
0x14002943d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140029444  jz      short loc_14002947F
0x140029446  mov     rcx, cs:WPP_GLOBAL_Control
0x14002944d  mov     r9d, 22h ; '"'
0x140029453  mov     eax, [r14]
0x140029456  mov     dl, 2
0x140029458  mov     dword ptr [rsp+98h+var_60], 28h ; '('
0x140029460  mov     dword ptr [rsp+98h+var_68], r8d
0x140029465  mov     rcx, [rcx+40h]
0x140029469  lea     r8d, [r9-1Fh]
0x14002946d  mov     [rsp+98h+var_70], eax
0x140029471  mov     qword ptr [rsp+98h+var_78], r12
0x140029476  call    WPP_RECORDER_SF_Ddd
0x14002947b  lea     r14, [rbp+10h]
0x14002947f  mov     dword ptr [rdi+14h], 28h ; '('
0x140029486  mov     r8d, 28h ; '('; unsigned int
0x14002948c  mov     edx, [rdi+10h]; unsigned int
0x14002948f  mov     r9d, 14h; unsigned int
0x140029495  mov     [rsp+98h+var_70], 1; int
0x14002949d  mov     ecx, r15d; unsigned int
0x1400294a0  mov     [rsp+98h+var_78], 2; unsigned int
0x1400294a8  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x1400294ad  test    eax, eax
0x1400294af  jz      short loc_1400294DB
0x1400294b1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400294b8  jz      loc_140029698
0x1400294be  mov     eax, [rdi+14h]
0x1400294c1  mov     r9d, 23h ; '#'
0x1400294c7  mov     [rsp+98h+var_50], 28h ; '('
0x1400294cf  mov     [rsp+98h+var_58], eax
0x1400294d3  mov     eax, [rdi+10h]
0x1400294d6  jmp     loc_14002940E
0x1400294db  xor     r12d, r12d
0x1400294de  test    r13d, r13d
0x1400294e1  jz      short loc_140029535
0x1400294e3  mov     r14, [rsp+98h+arg_0]
0x1400294eb  mov     al, [r14+58h]
0x1400294ef  mov     r8d, [rdi+r12*8+28h]; unsigned int
0x1400294f4  neg     al
0x1400294f6  mov     edx, [rdi+r12*8+24h]; unsigned int
0x1400294fb  sbb     ecx, ecx
0x1400294fd  mov     [rsp+98h+var_70], 1; int
0x140029505  and     ecx, 7
0x140029508  mov     [rsp+98h+var_78], 2; unsigned int
0x140029510  add     ecx, 0Fh
0x140029513  mov     [rsp+98h+arg_8], ecx
0x14002951a  mov     r9d, ecx; unsigned int
0x14002951d  mov     ecx, r15d; unsigned int
0x140029520  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x140029525  test    eax, eax
0x140029527  jnz     short loc_14002959B
0x140029529  inc     r12d
0x14002952c  cmp     r12d, r13d
0x14002952f  jb      short loc_1400294EB
0x140029531  lea     r14, [rbp+10h]
0x140029535  imul    r15, [rsp+98h+arg_18], 2Eh ; '.'
0x14002953e  mov     r8d, 6458424Dh
0x140029544  mov     ecx, 40h ; '@'
0x140029549  add     r15, 68h ; 'h'
0x14002954d  mov     rdx, r15
0x140029550  call    cs:__imp_ExAllocatePool2
0x140029557  nop     dword ptr [rax+rax+00h]
0x14002955c  test    rax, rax
0x14002955f  jnz     loc_1400295F3
0x140029565  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002956c  jz      short loc_140029591
0x14002956e  mov     eax, [rdi+1Ch]
0x140029571  mov     rcx, cs:WPP_GLOBAL_Control
0x140029578  mov     dword ptr [rsp+98h+var_60], eax
0x14002957c  mov     eax, [r14]
0x14002957f  mov     [rsp+98h+var_68], r15
0x140029584  mov     rcx, [rcx+40h]
0x140029588  mov     [rsp+98h+var_70], eax
0x14002958c  call    WPP_RECORDER_SF_DId
0x140029591  mov     ebx, 0C000009Ah
0x140029596  jmp     loc_14002969D
0x14002959b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400295a2  jz      loc_140029698
0x1400295a8  mov     eax, [rsp+98h+arg_8]
0x1400295af  mov     r9d, 24h ; '$'
0x1400295b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400295bc  add     eax, eax
0x1400295be  mov     [rsp+98h+var_48], eax
0x1400295c2  mov     eax, [rdi+r12*8+28h]
0x1400295c7  mov     [rsp+98h+var_50], eax
0x1400295cb  mov     eax, [rdi+r12*8+24h]
0x1400295d0  mov     rcx, [rcx+40h]
0x1400295d4  mov     [rsp+98h+var_58], r15d
0x1400295d9  mov     dword ptr [rsp+98h+var_60], eax
0x1400295dd  mov     eax, [rbp+10h]
0x1400295e0  mov     dword ptr [rsp+98h+var_68], r12d
0x1400295e5  mov     [rsp+98h+var_70], eax
0x1400295e9  call    WPP_RECORDER_SF_Dddddd
0x1400295ee  jmp     loc_140029698
0x1400295f3  lea     rdx, [rax+4]
0x1400295f7  mov     dword ptr [rax], 680280h
0x1400295fd  mov     rcx, rdi
0x140029600  mov     [rbp+2DCh], r15d
0x140029607  mov     [rbp+2E0h], rax
0x14002960e  call    ??$MbbUtilMbbToWwanReadyInfo@U_MBB_SUBSCRIBER_READY_INFO_EX4@@@@YAXPEAU_MBB_SUBSCRIBER_READY_INFO_EX4@@PEAU_WWAN_READY_INFO@@@Z; MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO_EX4>(_MBB_SUBSCRIBER_READY_INFO_EX4 *,_WWAN_READY_INFO *)
0x140029613  mov     ecx, [rdi]
0x140029615  lea     eax, [rcx-1]
0x140029618  test    eax, 0FFFFFFFAh
0x14002961d  jnz     short loc_14002963B
0x14002961f  cmp     ecx, 2
0x140029622  jz      short loc_14002963B
0x140029624  test    byte ptr [rdi+18h], 1
0x140029628  jnz     short loc_14002963B
0x14002962a  mov     rax, [rsp+98h+arg_0]
0x140029632  or      dword ptr [rax+440h], 20h
0x140029639  jmp     short loc_14002969D
0x14002963b  mov     rax, [rsp+98h+arg_0]
0x140029643  and     dword ptr [rax+440h], 0FFFFFFDFh
0x14002964a  jmp     short loc_14002969D
0x14002964c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140029653  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002965a  jz      short loc_140029698
0x14002965c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029663  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002966a  mov     eax, [rbp+10h]
0x14002966d  mov     r9d, 1Dh
0x140029673  mov     dword ptr [rsp+98h+var_60], 20h ; ' '
0x14002967b  mov     dl, 2
0x14002967d  mov     dword ptr [rsp+98h+var_68], r15d
0x140029682  mov     rcx, [rcx+40h]
0x140029686  mov     [rsp+98h+var_70], eax
0x14002968a  lea     r8d, [r9-1Ah]
0x14002968e  mov     qword ptr [rsp+98h+var_78], r12
0x140029693  call    WPP_RECORDER_SF_Ddd
0x140029698  mov     ebx, 0C0010015h
0x14002969d  mov     edx, ebx; int
0x14002969f  mov     rcx, rbp; struct _MBB_REQUEST_CONTEXT *
0x1400296a2  call    ?MbbNdisIndicateReadyInfo@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; MbbNdisIndicateReadyInfo(_MBB_REQUEST_CONTEXT *,int)
0x1400296a7  mov     rbx, [rsp+98h+arg_10]
0x1400296af  xor     eax, eax
0x1400296b1  add     rsp, 60h
0x1400296b5  pop     r15
0x1400296b7  pop     r14
0x1400296b9  pop     r13
0x1400296bb  pop     r12
0x1400296bd  pop     rdi
0x1400296be  pop     rsi
0x1400296bf  pop     rbp
0x1400296c0  retn
```
