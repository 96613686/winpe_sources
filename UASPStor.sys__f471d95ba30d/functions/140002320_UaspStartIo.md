# UaspStartIo

- ea: `0x140002320`
- end: `0x14000295c`
- name: `UaspStartIo`
- size: `1596`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002320`
- `0x140002a24`
- `0x140002b10`
- `0x140002bec`
- `0x140002cdc`
- `0x140002dd8`
- `0x140005744`
- `0x140005d64`
- `0x140006dc8`
- `0x14000a2b8`
- `0x14000b89c`
- `0x14000c368`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002452`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002452`
- `ntoskrnl!RtlCompareMemory` at `0x140002753`
- `ntoskrnl!RtlCompareMemory` at `0x140002753`
- `storport!StorPortNotification` at `0x1400023fd`
- `storport!StorPortNotification` at `0x1400023fd`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400023c2`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400024e1`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002531`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400025a3`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002607`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002679`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400026fa`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002869`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002936`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400023c2`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400024e1`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002531`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400025a3`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002607`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002679`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400026fa`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002869`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140002936`

## pseudocode

```c
char __fastcall UaspStartIo(__int64 a1, __int64 a2)
{
  int v2; // ebp
  __int64 v3; // r13
  __int64 v4; // rsi
  unsigned __int16 v5; // di
  int v6; // eax
  int v7; // edx
  void *v9; // rbx
  unsigned int v10; // ecx
  int v11; // eax
  int v12; // eax
  int v13; // edx
  int v14; // r8d
  void *v15; // rdx
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  char v19; // bl
  int v20; // eax
  int v21; // edx
  int Default; // eax
  int v23; // edx
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  int v27; // edx
  __int64 v28; // r9
  int v29; // eax
  char v30; // di
  int v31; // eax
  int v32; // edx
  int v33; // r8d
  int v34; // r9d
  unsigned __int16 v35; // bx
  __int64 v36; // rbx
  char v37; // al
  int v38; // eax
  char v39; // dl
  char v40; // cl
  int v41; // eax
  int v42; // edx
  int v43; // r8d
  int v44; // r9d
  int v45; // eax
  int v46; // [rsp+20h] [rbp-C8h]

  v2 = *(unsigned __int8 *)(a2 + 2);
  v3 = a2;
  v4 = a1;
  if ( v2 )
  {
    if ( v2 == 2 )
    {
      if ( *(_DWORD *)(a2 + 16) >= 0x1Cu
        && (v36 = *(_QWORD *)(a2 + 24), RtlCompareMemory((const void *)(v36 + 4), "UASPSTOR", 8u) == 8)
        && *(_DWORD *)(v36 + 16) == 1771520
        && *(_DWORD *)(v3 + 16) >= 0x1Eu )
      {
        *(_WORD *)(*(_QWORD *)(v3 + 24) + 28LL) = *(_WORD *)(v4 + 1280);
        v37 = 1;
      }
      else
      {
        v37 = 6;
      }
      *(_BYTE *)(v3 + 3) = v37;
      goto LABEL_14;
    }
    if ( v2 == 16 )
    {
LABEL_14:
      StorPortNotification(0, v4, v3);
      return 1;
    }
    v5 = 13;
    if ( v2 != 19 && v2 != 32 )
    {
      if ( v2 == 36 )
      {
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          WPP_RECORDER_SF_PDD(Default, v23, v24, v25);
        }
        goto LABEL_14;
      }
      if ( v2 != 37 )
      {
        if ( v2 == 38 )
        {
          UaspGetDumpPointers(a1, a2);
          goto LABEL_14;
        }
        if ( v2 != 39 )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v6 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            LOBYTE(v7) = 3;
            WPP_RECORDER_SF_d(v6, v7, 2, 18, (__int64)WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids, v2);
          }
          goto LABEL_13;
        }
        v9 = *(void **)(*(_QWORD *)(a2 + 24) + 64LL);
        UaspInternalDeviceIoControl(*(PDEVICE_OBJECT *)(a1 + 16), 0, 0);
        ExFreePoolWithTag(v9, 0);
LABEL_17:
        *(_BYTE *)(v3 + 3) = 1;
        goto LABEL_14;
      }
      v10 = *(_DWORD *)(a2 + 8);
      if ( (*(_DWORD *)(a2 + 64) & 1) == 0 )
      {
        if ( v10 == 9 )
        {
          *(_DWORD *)(*(_QWORD *)(a2 + 24) + 4LL) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + 4LL) & 0xFFFFF5EF | 0xA00;
          goto LABEL_17;
        }
LABEL_13:
        *(_BYTE *)(v3 + 3) = 6;
        goto LABEL_14;
      }
      if ( v10 > 0x17 )
        goto LABEL_13;
      v11 = 8388628;
      if ( !_bittest(&v11, v10) )
        goto LABEL_13;
      if ( (*(_BYTE *)v4 & 2) != 0 )
      {
        if ( *(_BYTE *)(v4 + 986) )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v12 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            WPP_RECORDER_SF_SP(v12, v13, v14, 13, (__int64)WPP_b606bc35c7ef35d872dd65732ef04e06_Traceguids);
          }
          v15 = &QueueCancelSSWorkItem;
        }
        else
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v16 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            WPP_RECORDER_SF_SP(v16, v17, v18, 43, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids);
          }
          v15 = &QueueCancelHSWorkItem;
        }
        if ( (int)UaspQueueWorkItem(v4, v15, v3, 0) < 0
          && gTracingEnabled
          && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v19 = *(_BYTE *)(v3 + 7);
          v20 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v21) = 2;
          WPP_RECORDER_SF_d(v20, v21, 1, 16, (__int64)WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids, v19);
        }
        return 1;
      }
LABEL_67:
      *(_BYTE *)(a2 + 3) = 8;
      goto LABEL_14;
    }
    if ( (*(_DWORD *)(a1 + 120) & 1) != 0 )
      goto LABEL_67;
    if ( (_BYTE)v2 == 19 )
    {
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v5 = 12;
LABEL_48:
        v26 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        WPP_RECORDER_SF_P(v26, v27, 5, v5, (__int64)WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids, v3);
      }
    }
    else if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      goto LABEL_48;
    }
    v28 = 16;
    if ( (_BYTE)v2 != 19 )
      v28 = 8;
    v29 = UaspQueueWorkItem(v4, &QueueTaskWorkItem, v3, v28);
    v30 = v29;
    if ( v29 < 0 )
    {
      if ( (_BYTE)v2 == 19 )
      {
        if ( !gTracingEnabled || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 1;
        v31 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        v34 = 14;
LABEL_86:
        WPP_RECORDER_SF_DP(v31, v32, v33, v34, v46, v30, v3);
        return 1;
      }
      if ( !gTracingEnabled || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 1;
      v35 = 15;
LABEL_85:
      v31 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      v34 = v35;
      goto LABEL_86;
    }
    return 1;
  }
  v38 = *(_DWORD *)(a1 + 120);
  *(_QWORD *)(a1 + 344) = a2;
  *(_QWORD *)(a1 + 152) = a2;
  if ( (v38 & 1) != 0 )
    goto LABEL_67;
  v39 = *(_BYTE *)(a2 + 72);
  v40 = 1;
  if ( v39 == 18 && *(_BYTE *)(v3 + 74) == 0x8F )
  {
    *(_BYTE *)(v3 + 3) = 4;
    v40 = 0;
  }
  if ( (unsigned int)*(unsigned __int8 *)(v3 + 7) >= *(_DWORD *)(v4 + 1000) && v39 != -96 )
  {
    *(_BYTE *)(v3 + 3) = 32;
    goto LABEL_14;
  }
  if ( !v40 )
    goto LABEL_14;
  if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v41 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    v3 = a2;
    WPP_RECORDER_SF_PDDDDDDDDDDD(v41, v42, v43, v44);
    v4 = a1;
  }
  *(_BYTE *)(v3 + 3) = 0;
  if ( *(_BYTE *)(v4 + 986) )
    v45 = QueueCommandSS(v4, v4, v3);
  else
    v45 = QueueCommandHS(v4, v4, v3);
  v30 = v45;
  if ( v45 < 0 && gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v35 = 11;
    goto LABEL_85;
  }
  return 1;
}

```

## disassembly

```asm
0x140002320  mov     [rsp+arg_8], rdx
0x140002325  mov     [rsp+arg_0], rcx
0x14000232a  push    rbx
0x14000232b  push    rbp
0x14000232c  push    rsi
0x14000232d  push    rdi
0x14000232e  push    r12
0x140002330  push    r13
0x140002332  push    r14
0x140002334  push    r15
0x140002336  sub     rsp, 0A8h
0x14000233d  movzx   ebp, byte ptr [rdx+2]
0x140002341  xor     r15d, r15d
0x140002344  mov     r13, rdx
0x140002347  mov     rsi, rcx
0x14000234a  mov     edx, ebp
0x14000234c  test    ebp, ebp
0x14000234e  jz      loc_140002792
0x140002354  sub     edx, 2
0x140002357  jz      loc_140002735
0x14000235d  sub     edx, 0Eh
0x140002360  jz      loc_1400023F5
0x140002366  lea     edi, [r15+0Dh]
0x14000236a  sub     edx, 3
0x14000236d  jz      loc_14000262D
0x140002373  sub     edx, edi
0x140002375  jz      loc_14000262D
0x14000237b  sub     edx, 4
0x14000237e  jz      loc_1400025D6
0x140002384  sub     edx, 1
0x140002387  jz      loc_14000246F
0x14000238d  sub     edx, 1
0x140002390  jz      loc_140002465
0x140002396  cmp     edx, 1
0x140002399  jz      loc_140002420
0x14000239f  cmp     cs:gTracingEnabled, r15b
0x1400023a6  jz      short loc_1400023F0
0x1400023a8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400023af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400023b6  jz      short loc_1400023F0
0x1400023b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023bf  lea     ebx, [rdi+5]
0x1400023c2  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400023c9  nop     dword ptr [rax+rax+00h]
0x1400023ce  mov     [rsp+0E8h+var_C0], ebp
0x1400023d2  lea     r8d, [r15+2]
0x1400023d6  mov     rcx, rax
0x1400023d9  movzx   r9d, bx
0x1400023dd  lea     rax, WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids
0x1400023e4  mov     dl, 3
0x1400023e6  mov     [rsp+0E8h+var_C8], rax
0x1400023eb  call    WPP_RECORDER_SF_d
0x1400023f0  mov     byte ptr [r13+3], 6
0x1400023f5  mov     r8, r13
0x1400023f8  mov     rdx, rsi
0x1400023fb  xor     ecx, ecx
0x1400023fd  call    cs:__imp_StorPortNotification
0x140002404  nop     dword ptr [rax+rax+00h]
0x140002409  mov     al, 1
0x14000240b  add     rsp, 0A8h
0x140002412  pop     r15
0x140002414  pop     r14
0x140002416  pop     r13
0x140002418  pop     r12
0x14000241a  pop     rdi
0x14000241b  pop     rsi
0x14000241c  pop     rbp
0x14000241d  pop     rbx
0x14000241e  retn
0x140002420  mov     rax, [r13+18h]
0x140002424  mov     edx, 491408h
0x140002429  mov     rcx, [rcx+10h]; DeviceObject
0x14000242d  mov     r9d, 58h ; 'X'
0x140002433  mov     [rsp+0E8h+var_C0], r15d; int
0x140002438  mov     [rsp+0E8h+var_C8], r15; __int64
0x14000243d  mov     rbx, [rax+40h]
0x140002441  lea     r8, [rbx+3F0h]
0x140002448  call    UaspInternalDeviceIoControl
0x14000244d  xor     edx, edx; Tag
0x14000244f  mov     rcx, rbx; P
0x140002452  call    cs:__imp_ExFreePoolWithTag
0x140002459  nop     dword ptr [rax+rax+00h]
0x14000245e  mov     byte ptr [r13+3], 1
0x140002463  jmp     short loc_1400023F5
0x140002465  mov     rdx, r13
0x140002468  call    UaspGetDumpPointers
0x14000246d  jmp     short loc_1400023F5
0x14000246f  mov     eax, [r13+40h]
0x140002473  mov     ecx, [r13+8]
0x140002477  test    al, 1
0x140002479  jnz     short loc_140002498
0x14000247b  cmp     ecx, 9
0x14000247e  jnz     loc_1400023F0
0x140002484  mov     rcx, [r13+18h]
0x140002488  mov     eax, [rcx+4]
0x14000248b  and     eax, 0FFFFFFEFh
0x14000248e  or      eax, 0A00h
0x140002493  mov     [rcx+4], eax
0x140002496  jmp     short loc_14000245E
0x140002498  cmp     ecx, 17h
0x14000249b  ja      loc_1400023F0
0x1400024a1  mov     eax, 800014h
0x1400024a6  bt      eax, ecx
0x1400024a9  jnb     loc_1400023F0
0x1400024af  test    byte ptr [rsi], 2
0x1400024b2  jz      loc_1400027A7
0x1400024b8  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400024bf  cmp     [rsi+3DAh], r15b
0x1400024c6  jz      short loc_140002513
0x1400024c8  cmp     cs:gTracingEnabled, r15b
0x1400024cf  jz      short loc_14000250A
0x1400024d1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400024d8  jz      short loc_14000250A
0x1400024da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400024e1  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400024e8  nop     dword ptr [rax+rax+00h]
0x1400024ed  mov     [rsp+0E8h+var_B8], r13
0x1400024f2  movzx   r9d, di
0x1400024f6  mov     rcx, rax
0x1400024f9  lea     rax, WPP_b606bc35c7ef35d872dd65732ef04e06_Traceguids
0x140002500  mov     [rsp+0E8h+var_C8], rax
0x140002505  call    WPP_RECORDER_SF_SP
0x14000250a  lea     rdx, QueueCancelSSWorkItem
0x140002511  jmp     short loc_140002561
0x140002513  cmp     cs:gTracingEnabled, r15b
0x14000251a  jz      short loc_14000255A
0x14000251c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140002523  jz      short loc_14000255A
0x140002525  mov     rcx, cs:WPP_GLOBAL_Control
0x14000252c  mov     edi, 2Bh ; '+'
0x140002531  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140002538  nop     dword ptr [rax+rax+00h]
0x14000253d  mov     [rsp+0E8h+var_B8], r13
0x140002542  movzx   r9d, di
0x140002546  mov     rcx, rax
0x140002549  lea     rax, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x140002550  mov     [rsp+0E8h+var_C8], rax
0x140002555  call    WPP_RECORDER_SF_SP
0x14000255a  lea     rdx, QueueCancelHSWorkItem
0x140002561  xor     r9d, r9d
0x140002564  mov     r8, r13
0x140002567  mov     rcx, rsi
0x14000256a  call    UaspQueueWorkItem
0x14000256f  test    eax, eax
0x140002571  jns     loc_140002409
0x140002577  cmp     cs:gTracingEnabled, r15b
0x14000257e  jz      loc_140002409
0x140002584  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000258b  jz      loc_140002409
0x140002591  mov     rcx, cs:WPP_GLOBAL_Control
0x140002598  mov     r14d, 10h
0x14000259e  movzx   ebx, byte ptr [r13+7]
0x1400025a3  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400025aa  nop     dword ptr [rax+rax+00h]
0x1400025af  mov     [rsp+0E8h+var_C0], ebx
0x1400025b3  lea     r8d, [r14-0Fh]
0x1400025b7  mov     rcx, rax
0x1400025ba  movzx   r9d, r14w
0x1400025be  lea     rax, WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids
0x1400025c5  mov     dl, 2
0x1400025c7  mov     [rsp+0E8h+var_C8], rax
0x1400025cc  call    WPP_RECORDER_SF_d
0x1400025d1  jmp     loc_140002409
0x1400025d6  cmp     cs:gTracingEnabled, r15b
0x1400025dd  jz      loc_1400023F5
0x1400025e3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400025ea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400025f1  jz      loc_1400023F5
0x1400025f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025fe  movzx   ebx, byte ptr [r13+4]
0x140002603  mov     edi, [r13+8]
0x140002607  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000260e  nop     dword ptr [rax+rax+00h]
0x140002613  mov     [rsp+0E8h+var_B0], ebx
0x140002617  mov     rcx, rax
0x14000261a  mov     dword ptr [rsp+0E8h+var_B8], edi
0x14000261e  mov     qword ptr [rsp+0E8h+var_C0], r13
0x140002623  call    WPP_RECORDER_SF_PDD
0x140002628  jmp     loc_1400023F5
0x14000262d  mov     eax, [rcx+78h]
0x140002630  test    al, 1
0x140002632  jnz     loc_1400027A7
0x140002638  mov     r12b, 13h
0x14000263b  lea     rbx, WPP_RECORDER_INITIALIZED
0x140002642  cmp     bpl, r12b
0x140002645  jnz     short loc_140002660
0x140002647  cmp     cs:gTracingEnabled, r15b
0x14000264e  jz      short loc_1400026A8
0x140002650  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140002657  jz      short loc_1400026A8
0x140002659  mov     edi, 0Ch
0x14000265e  jmp     short loc_140002672
0x140002660  cmp     cs:gTracingEnabled, r15b
0x140002667  jz      short loc_1400026A8
0x140002669  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140002670  jz      short loc_1400026A8
0x140002672  mov     rcx, cs:WPP_GLOBAL_Control
0x140002679  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140002680  nop     dword ptr [rax+rax+00h]
0x140002685  mov     qword ptr [rsp+0E8h+var_C0], r13
0x14000268a  movzx   r9d, di
0x14000268e  mov     rcx, rax
0x140002691  mov     r8d, 5
0x140002697  lea     rax, WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids
0x14000269e  mov     [rsp+0E8h+var_C8], rax
0x1400026a3  call    WPP_RECORDER_SF_P
0x1400026a8  mov     edi, 8
0x1400026ad  lea     rdx, QueueTaskWorkItem
0x1400026b4  cmp     bpl, r12b
0x1400026b7  mov     r8, r13
0x1400026ba  mov     rcx, rsi
0x1400026bd  lea     r9d, [rdi+8]
0x1400026c1  cmovnz  r9d, edi
0x1400026c5  call    UaspQueueWorkItem
0x1400026ca  mov     edi, eax
0x1400026cc  test    eax, eax
0x1400026ce  jns     loc_140002409
0x1400026d4  cmp     bpl, r12b
0x1400026d7  jnz     short loc_140002711
0x1400026d9  cmp     cs:gTracingEnabled, r15b
0x1400026e0  jz      loc_140002409
0x1400026e6  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400026ed  jz      loc_140002409
0x1400026f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026fa  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140002701  nop     dword ptr [rax+rax+00h]
0x140002706  mov     r9d, 0Eh
0x14000270c  jmp     loc_140002946
0x140002711  cmp     cs:gTracingEnabled, r15b
0x140002718  jz      loc_140002409
0x14000271e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140002725  jz      loc_140002409
0x14000272b  mov     ebx, 0Fh
0x140002730  jmp     loc_14000292F
0x140002735  cmp     dword ptr [r13+10h], 1Ch
0x14000273a  jb      short loc_140002787
0x14000273c  mov     rbx, [r13+18h]
0x140002740  lea     rdx, aUaspstor; "UASPSTOR"
0x140002747  mov     edi, 8
0x14000274c  mov     r8d, edi; Length
0x14000274f  lea     rcx, [rbx+4]; Source1
0x140002753  call    cs:__imp_RtlCompareMemory
0x14000275a  nop     dword ptr [rax+rax+00h]
0x14000275f  cmp     rax, rdi
0x140002762  jnz     short loc_140002787
0x140002764  cmp     dword ptr [rbx+10h], 1B0800h
0x14000276b  jnz     short loc_140002787
0x14000276d  cmp     dword ptr [r13+10h], 1Eh
0x140002772  jb      short loc_140002787
0x140002774  movzx   eax, word ptr [rsi+500h]
0x14000277b  mov     rcx, [r13+18h]
0x14000277f  mov     [rcx+1Ch], ax
0x140002783  mov     al, 1
0x140002785  jmp     short loc_140002789
0x140002787  mov     al, 6
0x140002789  mov     [r13+3], al
0x14000278d  jmp     loc_1400023F5
0x140002792  mov     eax, [rcx+78h]
0x140002795  mov     [rcx+158h], r13
0x14000279c  mov     [rcx+98h], r13
0x1400027a3  test    al, 1
0x1400027a5  jz      short loc_1400027B1
0x1400027a7  mov     byte ptr [r13+3], 8
0x1400027ac  jmp     loc_1400023F5
0x1400027b1  movzx   edx, byte ptr [r13+48h]
0x1400027b6  mov     ebx, 12h
0x1400027bb  mov     cl, 1
0x1400027bd  cmp     dl, bl
0x1400027bf  jnz     short loc_1400027D0
0x1400027c1  cmp     byte ptr [r13+4Ah], 8Fh
0x1400027c6  jnz     short loc_1400027D0
0x1400027c8  mov     byte ptr [r13+3], 4
0x1400027cd  mov     cl, r15b
0x1400027d0  movzx   eax, byte ptr [r13+7]
0x1400027d5  cmp     eax, [rsi+3E8h]
0x1400027db  jb      short loc_1400027EC
0x1400027dd  cmp     dl, 0A0h
0x1400027e0  jz      short loc_1400027EC
0x1400027e2  mov     byte ptr [r13+3], 20h ; ' '
0x1400027e7  jmp     loc_1400023F5
0x1400027ec  test    cl, cl
0x1400027ee  jz      loc_1400023F5
0x1400027f4  cmp     cs:gTracingEnabled, r15b
0x1400027fb  lea     rbx, WPP_RECORDER_INITIALIZED
0x140002802  jz      loc_1400028E4
0x140002808  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000280f  jz      loc_1400028E4
0x140002815  mov     rcx, [rsp+0E8h+arg_8]
0x14000281d  mov     ebx, edx
0x14000281f  movzx   edi, byte ptr [r13+51h]
0x140002824  movzx   esi, byte ptr [r13+50h]
0x140002829  movzx   ebp, byte ptr [r13+4Fh]
0x14000282e  movzx   eax, byte ptr [rcx+4Ah]
0x140002832  movzx   r14d, byte ptr [r13+4Eh]
0x140002837  movzx   r15d, byte ptr [r13+4Dh]
0x14000283c  movzx   r12d, byte ptr [r13+4Ch]
0x140002841  movzx   r13d, byte ptr [r13+4Bh]
0x140002846  mov     [rsp+0E8h+arg_10], eax
0x14000284d  movzx   eax, byte ptr [rcx+49h]
0x140002851  mov     [rsp+0E8h+arg_18], eax
  ... truncated ...
```
