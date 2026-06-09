# MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x1400287b0`
- end: `0x140028cb2`
- name: `??$MbbNdisReadyInfoStatusHandlerHelper@U_MBB_SUBSCRIBER_READY_INFO@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
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
- `0x1400287b0`
- `0x14002f228`
- `0x14003b2f8`
- `0x14003b670`
- `0x14003bacc`
- `0x14003bc04`
- `0x14003c3c0`
- `0x14003df70`
- `0x14003f7e4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140028b40`
- `ntoskrnl!ExAllocatePool2` at `0x140028b40`

## pseudocode

```c
__int64 __fastcall MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO>(
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
  if ( !a4 || a5 < 0x1C )
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
        28);
    }
    goto LABEL_50;
  }
  v12 = *(_DWORD *)(a4 + 24);
  v13 = 100;
  if ( v12 <= 0x64 )
  {
    v13 = *(_DWORD *)(a4 + 24);
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
    *(_DWORD *)(a4 + 24) = 100;
  }
  if ( a5 < 8 * (unsigned __int64)v13 + 28 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DdId(WPP_GLOBAL_Control->DeviceExtension, v10, a3, 31);
    goto LABEL_50;
  }
  v15 = *(_DWORD *)(a4 + 8);
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
    *(_DWORD *)(a4 + 8) = 30;
    v15 = 30;
  }
  if ( (unsigned int)MbbIsVariableFieldValid(a5, *(_DWORD *)(a4 + 4), v15, 0xFu, 2u, 1) )
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
  v18 = *(_DWORD *)(a4 + 16);
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
    *(_DWORD *)(a4 + 16) = 40;
    v18 = 40;
  }
  if ( (unsigned int)MbbIsVariableFieldValid(a5, *(_DWORD *)(a4 + 12), v18, 0x14u, 2u, 1) )
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
                           *(_DWORD *)(a4 + 8 * v19 + 28),
                           *(_DWORD *)(a4 + 8 * v19 + 32),
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
        *(_DWORD *)(a4 + 8 * v19 + 28),
        a5,
        *(_DWORD *)(a4 + 8 * v19 + 32),
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
    MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO>((_DWORD *)a4, Pool2 + 1);
    if ( ((*(_DWORD *)a4 - 1) & 0xFFFFFFFA) != 0 || *(_DWORD *)a4 == 2 || (*(_BYTE *)(a4 + 20) & 1) != 0 )
      *(_DWORD *)(v28 + 1088) &= ~0x20u;
    else
      *(_DWORD *)(v28 + 1088) |= 0x20u;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DId(WPP_GLOBAL_Control->DeviceExtension, v23, a3, a4, v25, *v14, v21, *(_DWORD *)(a4 + 24));
    v7 = -1073741670;
  }
LABEL_51:
  MbbNdisIndicateReadyInfo(a1, v7, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x1400287b0  mov     [rsp+arg_10], rbx
0x1400287b5  push    rbp
0x1400287b6  push    rsi
0x1400287b7  push    rdi
0x1400287b8  push    r12
0x1400287ba  push    r13
0x1400287bc  push    r14
0x1400287be  push    r15
0x1400287c0  sub     rsp, 60h
0x1400287c4  mov     rdi, r9
0x1400287c7  mov     r15d, r8d
0x1400287ca  mov     ebx, edx
0x1400287cc  mov     rbp, rcx
0x1400287cf  test    edx, edx
0x1400287d1  jz      short loc_14002881F
0x1400287d3  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400287da  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400287e1  jz      loc_140028C8D
0x1400287e7  mov     eax, [rcx+10h]
0x1400287ea  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400287f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400287f8  mov     r9d, 1Bh
0x1400287fe  mov     dword ptr [rsp+98h+var_68], edx
0x140028802  mov     dl, 2
0x140028804  mov     [rsp+98h+var_70], eax
0x140028808  mov     qword ptr [rsp+98h+var_78], r12
0x14002880d  mov     rcx, [rcx+40h]
0x140028811  lea     r8d, [r9-18h]
0x140028815  call    WPP_RECORDER_SF_DD
0x14002881a  jmp     loc_140028C8D
0x14002881f  mov     rax, [rcx+30h]
0x140028823  mov     ecx, r15d
0x140028826  mov     rax, [rax]
0x140028829  mov     [rsp+98h+arg_0], rax
0x140028831  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x140028836  mov     r14d, eax
0x140028839  test    eax, eax
0x14002883b  jz      short loc_140028889
0x14002883d  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028844  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002884b  jz      short loc_140028881
0x14002884d  mov     ecx, [rbp+10h]
0x140028850  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028857  mov     dword ptr [rsp+98h+var_60], r15d
0x14002885c  mov     r9d, 1Ch
0x140028862  mov     dword ptr [rsp+98h+var_68], eax
0x140028866  mov     dl, 2
0x140028868  mov     [rsp+98h+var_70], ecx
0x14002886c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028873  mov     qword ptr [rsp+98h+var_78], r12
0x140028878  mov     rcx, [rcx+40h]
0x14002887c  call    WPP_RECORDER_SF_DDL
0x140028881  mov     ebx, r14d
0x140028884  jmp     loc_140028C8D
0x140028889  mov     r15d, [rsp+98h+arg_20]
0x140028891  test    rdi, rdi
0x140028894  jz      loc_140028C3C
0x14002889a  cmp     r15d, 1Ch
0x14002889e  jb      loc_140028C3C
0x1400288a4  mov     eax, [rdi+18h]
0x1400288a7  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400288ae  mov     r13d, 64h ; 'd'
0x1400288b4  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x1400288bb  cmp     eax, r13d
0x1400288be  jbe     short loc_1400288FE
0x1400288c0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400288c7  lea     r14, [rbp+10h]
0x1400288cb  jz      short loc_1400288F8
0x1400288cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400288d4  lea     r8d, [r13-61h]
0x1400288d8  mov     dword ptr [rsp+98h+var_68], eax
0x1400288dc  lea     r9d, [r13-46h]
0x1400288e0  mov     eax, [r14]
0x1400288e3  mov     dl, r8b
0x1400288e6  mov     [rsp+98h+var_70], eax
0x1400288ea  mov     rcx, [rcx+40h]
0x1400288ee  mov     qword ptr [rsp+98h+var_78], r12
0x1400288f3  call    WPP_RECORDER_SF_DD
0x1400288f8  mov     [rdi+18h], r13d
0x1400288fc  jmp     short loc_140028905
0x1400288fe  mov     r13d, eax
0x140028901  lea     r14, [rbp+10h]
0x140028905  mov     eax, r13d
0x140028908  mov     [rsp+98h+arg_18], rax
0x140028910  lea     rcx, ds:1Ch[rax*8]
0x140028918  cmp     r15, rcx
0x14002891b  jnb     short loc_14002895B
0x14002891d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028924  jz      loc_140028C88
0x14002892a  mov     eax, [rbp+10h]
0x14002892d  mov     r9d, 1Fh
0x140028933  mov     [rsp+98h+var_58], r13d
0x140028938  mov     [rsp+98h+var_60], rcx
0x14002893d  mov     rcx, cs:WPP_GLOBAL_Control
0x140028944  mov     dword ptr [rsp+98h+var_68], r15d
0x140028949  mov     [rsp+98h+var_70], eax
0x14002894d  mov     rcx, [rcx+40h]
0x140028951  call    WPP_RECORDER_SF_DdId
0x140028956  jmp     loc_140028C88
0x14002895b  mov     r8d, [rdi+8]
0x14002895f  cmp     r8d, 1Eh
0x140028963  jbe     short loc_1400289B4
0x140028965  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002896c  jz      short loc_1400289A7
0x14002896e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028975  mov     r9d, 20h ; ' '
0x14002897b  mov     eax, [r14]
0x14002897e  mov     dl, 2
0x140028980  mov     dword ptr [rsp+98h+var_60], 1Eh
0x140028988  mov     dword ptr [rsp+98h+var_68], r8d
0x14002898d  mov     rcx, [rcx+40h]
0x140028991  lea     r8d, [r9-1Dh]
0x140028995  mov     [rsp+98h+var_70], eax
0x140028999  mov     qword ptr [rsp+98h+var_78], r12
0x14002899e  call    WPP_RECORDER_SF_Ddd
0x1400289a3  lea     r14, [rbp+10h]
0x1400289a7  mov     dword ptr [rdi+8], 1Eh
0x1400289ae  mov     r8d, 1Eh; unsigned int
0x1400289b4  mov     edx, [rdi+4]; unsigned int
0x1400289b7  mov     r9d, 0Fh; unsigned int
0x1400289bd  mov     [rsp+98h+var_70], 1; int
0x1400289c5  mov     ecx, r15d; unsigned int
0x1400289c8  mov     [rsp+98h+var_78], 2; unsigned int
0x1400289d0  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x1400289d5  test    eax, eax
0x1400289d7  jz      short loc_140028A23
0x1400289d9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400289e0  jz      loc_140028C88
0x1400289e6  mov     eax, [rdi+8]
0x1400289e9  mov     r9d, 21h ; '!'
0x1400289ef  mov     [rsp+98h+var_50], 1Eh
0x1400289f7  mov     [rsp+98h+var_58], eax
0x1400289fb  mov     eax, [rdi+4]
0x1400289fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140028a05  mov     dword ptr [rsp+98h+var_60], r15d
0x140028a0a  mov     dword ptr [rsp+98h+var_68], eax
0x140028a0e  mov     eax, [r14]
0x140028a11  mov     rcx, [rcx+40h]
0x140028a15  mov     [rsp+98h+var_70], eax
0x140028a19  call    WPP_RECORDER_SF_Ddddd
0x140028a1e  jmp     loc_140028C88
0x140028a23  mov     r8d, [rdi+10h]
0x140028a27  cmp     r8d, 28h ; '('
0x140028a2b  jbe     short loc_140028A7C
0x140028a2d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028a34  jz      short loc_140028A6F
0x140028a36  mov     rcx, cs:WPP_GLOBAL_Control
0x140028a3d  mov     r9d, 22h ; '"'
0x140028a43  mov     eax, [r14]
0x140028a46  mov     dl, 2
0x140028a48  mov     dword ptr [rsp+98h+var_60], 28h ; '('
0x140028a50  mov     dword ptr [rsp+98h+var_68], r8d
0x140028a55  mov     rcx, [rcx+40h]
0x140028a59  lea     r8d, [r9-1Fh]
0x140028a5d  mov     [rsp+98h+var_70], eax
0x140028a61  mov     qword ptr [rsp+98h+var_78], r12
0x140028a66  call    WPP_RECORDER_SF_Ddd
0x140028a6b  lea     r14, [rbp+10h]
0x140028a6f  mov     dword ptr [rdi+10h], 28h ; '('
0x140028a76  mov     r8d, 28h ; '('; unsigned int
0x140028a7c  mov     edx, [rdi+0Ch]; unsigned int
0x140028a7f  mov     r9d, 14h; unsigned int
0x140028a85  mov     [rsp+98h+var_70], 1; int
0x140028a8d  mov     ecx, r15d; unsigned int
0x140028a90  mov     [rsp+98h+var_78], 2; unsigned int
0x140028a98  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x140028a9d  test    eax, eax
0x140028a9f  jz      short loc_140028ACB
0x140028aa1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028aa8  jz      loc_140028C88
0x140028aae  mov     eax, [rdi+10h]
0x140028ab1  mov     r9d, 23h ; '#'
0x140028ab7  mov     [rsp+98h+var_50], 28h ; '('
0x140028abf  mov     [rsp+98h+var_58], eax
0x140028ac3  mov     eax, [rdi+0Ch]
0x140028ac6  jmp     loc_1400289FE
0x140028acb  xor     r12d, r12d
0x140028ace  test    r13d, r13d
0x140028ad1  jz      short loc_140028B25
0x140028ad3  mov     r14, [rsp+98h+arg_0]
0x140028adb  mov     al, [r14+58h]
0x140028adf  mov     r8d, [rdi+r12*8+20h]; unsigned int
0x140028ae4  neg     al
0x140028ae6  mov     edx, [rdi+r12*8+1Ch]; unsigned int
0x140028aeb  sbb     ecx, ecx
0x140028aed  mov     [rsp+98h+var_70], 1; int
0x140028af5  and     ecx, 7
0x140028af8  mov     [rsp+98h+var_78], 2; unsigned int
0x140028b00  add     ecx, 0Fh
0x140028b03  mov     [rsp+98h+arg_8], ecx
0x140028b0a  mov     r9d, ecx; unsigned int
0x140028b0d  mov     ecx, r15d; unsigned int
0x140028b10  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x140028b15  test    eax, eax
0x140028b17  jnz     short loc_140028B8B
0x140028b19  inc     r12d
0x140028b1c  cmp     r12d, r13d
0x140028b1f  jb      short loc_140028ADB
0x140028b21  lea     r14, [rbp+10h]
0x140028b25  imul    r15, [rsp+98h+arg_18], 2Eh ; '.'
0x140028b2e  mov     r8d, 6458424Dh
0x140028b34  mov     ecx, 40h ; '@'
0x140028b39  add     r15, 68h ; 'h'
0x140028b3d  mov     rdx, r15
0x140028b40  call    cs:__imp_ExAllocatePool2
0x140028b47  nop     dword ptr [rax+rax+00h]
0x140028b4c  test    rax, rax
0x140028b4f  jnz     loc_140028BE3
0x140028b55  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028b5c  jz      short loc_140028B81
0x140028b5e  mov     eax, [rdi+18h]
0x140028b61  mov     rcx, cs:WPP_GLOBAL_Control
0x140028b68  mov     dword ptr [rsp+98h+var_60], eax
0x140028b6c  mov     eax, [r14]
0x140028b6f  mov     [rsp+98h+var_68], r15
0x140028b74  mov     rcx, [rcx+40h]
0x140028b78  mov     [rsp+98h+var_70], eax
0x140028b7c  call    WPP_RECORDER_SF_DId
0x140028b81  mov     ebx, 0C000009Ah
0x140028b86  jmp     loc_140028C8D
0x140028b8b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028b92  jz      loc_140028C88
0x140028b98  mov     eax, [rsp+98h+arg_8]
0x140028b9f  mov     r9d, 24h ; '$'
0x140028ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x140028bac  add     eax, eax
0x140028bae  mov     [rsp+98h+var_48], eax
0x140028bb2  mov     eax, [rdi+r12*8+20h]
0x140028bb7  mov     [rsp+98h+var_50], eax
0x140028bbb  mov     eax, [rdi+r12*8+1Ch]
0x140028bc0  mov     rcx, [rcx+40h]
0x140028bc4  mov     [rsp+98h+var_58], r15d
0x140028bc9  mov     dword ptr [rsp+98h+var_60], eax
0x140028bcd  mov     eax, [rbp+10h]
0x140028bd0  mov     dword ptr [rsp+98h+var_68], r12d
0x140028bd5  mov     [rsp+98h+var_70], eax
0x140028bd9  call    WPP_RECORDER_SF_Dddddd
0x140028bde  jmp     loc_140028C88
0x140028be3  lea     rdx, [rax+4]
0x140028be7  mov     dword ptr [rax], 680280h
0x140028bed  mov     rcx, rdi
0x140028bf0  mov     [rbp+2DCh], r15d
0x140028bf7  mov     [rbp+2E0h], rax
0x140028bfe  call    ??$MbbUtilMbbToWwanReadyInfo@U_MBB_SUBSCRIBER_READY_INFO@@@@YAXPEAU_MBB_SUBSCRIBER_READY_INFO@@PEAU_WWAN_READY_INFO@@@Z; MbbUtilMbbToWwanReadyInfo<_MBB_SUBSCRIBER_READY_INFO>(_MBB_SUBSCRIBER_READY_INFO *,_WWAN_READY_INFO *)
0x140028c03  mov     ecx, [rdi]
0x140028c05  lea     eax, [rcx-1]
0x140028c08  test    eax, 0FFFFFFFAh
0x140028c0d  jnz     short loc_140028C2B
0x140028c0f  cmp     ecx, 2
0x140028c12  jz      short loc_140028C2B
0x140028c14  test    byte ptr [rdi+14h], 1
0x140028c18  jnz     short loc_140028C2B
0x140028c1a  mov     rax, [rsp+98h+arg_0]
0x140028c22  or      dword ptr [rax+440h], 20h
0x140028c29  jmp     short loc_140028C8D
0x140028c2b  mov     rax, [rsp+98h+arg_0]
0x140028c33  and     dword ptr [rax+440h], 0FFFFFFDFh
0x140028c3a  jmp     short loc_140028C8D
0x140028c3c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140028c43  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140028c4a  jz      short loc_140028C88
0x140028c4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028c53  lea     r12, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140028c5a  mov     eax, [rbp+10h]
0x140028c5d  mov     r9d, 1Dh
0x140028c63  mov     dword ptr [rsp+98h+var_60], 1Ch
0x140028c6b  mov     dl, 2
0x140028c6d  mov     dword ptr [rsp+98h+var_68], r15d
0x140028c72  mov     rcx, [rcx+40h]
0x140028c76  mov     [rsp+98h+var_70], eax
0x140028c7a  lea     r8d, [r9-1Ah]
0x140028c7e  mov     qword ptr [rsp+98h+var_78], r12
0x140028c83  call    WPP_RECORDER_SF_Ddd
0x140028c88  mov     ebx, 0C0010015h
0x140028c8d  mov     edx, ebx; int
0x140028c8f  mov     rcx, rbp; struct _MBB_REQUEST_CONTEXT *
0x140028c92  call    ?MbbNdisIndicateReadyInfo@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; MbbNdisIndicateReadyInfo(_MBB_REQUEST_CONTEXT *,int)
0x140028c97  mov     rbx, [rsp+98h+arg_10]
0x140028c9f  xor     eax, eax
0x140028ca1  add     rsp, 60h
0x140028ca5  pop     r15
0x140028ca7  pop     r14
0x140028ca9  pop     r13
0x140028cab  pop     r12
0x140028cad  pop     rdi
0x140028cae  pop     rsi
0x140028caf  pop     rbp
0x140028cb0  retn
```
