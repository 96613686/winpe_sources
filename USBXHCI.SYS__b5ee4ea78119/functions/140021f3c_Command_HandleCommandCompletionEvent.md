# Command_HandleCommandCompletionEvent

- ea: `0x140021f3c`
- end: `0x1400224a1`
- name: `Command_HandleCommandCompletionEvent`
- size: `1381`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14002ed98`

## callees

- `0x140002568`
- `0x14000c264`
- `0x140010d40`
- `0x1400110e0`
- `0x14001ac48`
- `0x1400218a0`
- `0x1400219b0`
- `0x140021a74`
- `0x140021f3c`
- `0x1400224a8`
- `0x1400227a8`
- `0x14002390c`
- `0x14002b2c0`
- `0x140030690`
- `0x14003d3b4`
- `0x14003e8c8`
- `0x14003ed48`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140021f76`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021f76`

## string_xrefs

- `0x1400223c7`: `Controller completed a command out of order`

## pseudocode

```c
__int64 **__fastcall Command_HandleCommandCompletionEvent(__int64 a1, __int64 a2)
{
  bool v2; // zf
  char v5; // r12
  __int64 v6; // rcx
  int v7; // r9d
  __int64 ****v8; // r15
  __int64 ****i; // rdi
  __int64 *v10; // rdx
  __int64 *v11; // rdx
  __int64 v12; // rsi
  int v13; // r8d
  __int64 ***v14; // rdi
  int v15; // ecx
  __int64 **v16; // rax
  __int64 ****v17; // rcx
  _QWORD *v18; // rax
  int v19; // r8d
  __int64 *v20; // rdi
  __int64 **result; // rax
  __int64 *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // edx
  unsigned int v26; // esi
  _QWORD *v27; // rax
  _QWORD *v28; // rdx
  __int64 v29; // rcx
  void (__fastcall *v30)(__int64, __int64 *); // rax
  int v31; // [rsp+20h] [rbp-48h]
  __int64 v32; // [rsp+20h] [rbp-48h]
  __int64 *v33; // [rsp+50h] [rbp-18h] BYREF
  __int64 **v34; // [rsp+58h] [rbp-10h]

  v2 = *(_BYTE *)(a2 + 11) == 24;
  v34 = &v33;
  v33 = (__int64 *)&v33;
  if ( v2 )
    return (__int64 **)Command_HandleCommandRingStoppedEvent();
  v5 = 0;
  if ( KeGetCurrentIrql() == 2 )
  {
    v6 = *(_QWORD *)(a1 + 8);
    if ( *(_BYTE *)(v6 + 1041) )
    {
      Controller_LowerAndTrackIrql(v6);
      v5 = 1;
    }
  }
  DynamicLock_Acquire(*(_QWORD *)(a1 + 112));
  v8 = (__int64 ****)(a1 + 80);
  for ( i = *(__int64 *****)(a1 + 80); ; i = (__int64 ****)*i )
  {
    v10 = WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids;
    if ( i == v8 )
      break;
    v12 = XilCommand_GetCommandRingBufferLogicalAddress(a1, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids)
        + 16LL * *((unsigned int *)i + 5);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        WPP_RECORDER_SF_qii(*(_QWORD *)(a1 + 16), (_DWORD)v11, v13, v7, v31, (char)i, v12, *(_QWORD *)a2);
        v11 = WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        v32 = (__int64)v11;
        LOBYTE(v11) = 5;
        WPP_RECORDER_SF_DD(*(_QWORD *)(a1 + 16), (_DWORD)v11, 7, 45, v32, *(_DWORD *)(a1 + 44), *(_DWORD *)(a1 + 40));
      }
    }
    if ( *(_QWORD *)a2 == v12 )
    {
      *((_DWORD *)i + 4) = 2;
      *((_BYTE *)i + 60) = *(_BYTE *)(a2 + 11);
      *((_DWORD *)i + 16) = *(_DWORD *)(a2 + 8) & 0xFFFFFF;
      if ( (*(_DWORD *)(a2 + 12) & 0xFC00) == 0x8400 )
        *((_BYTE *)i + 61) = *(_BYTE *)(a2 + 15);
      v10 = WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids;
      if ( (*((_BYTE *)i + 62) & 2) != 0 )
        *(_OWORD *)(i + 3) = *(_OWORD *)a2;
      break;
    }
  }
  v14 = *v8;
  while ( v14 != (__int64 ***)v8 )
  {
    if ( *((_DWORD *)v14 + 4) != 2 )
    {
      if ( v33 == (__int64 *)&v33 && !*(_BYTE *)(a1 + 120) )
      {
        Controller_HwVerifierBreakIfEnabled(
          *(_QWORD *)(a1 + 8),
          0,
          0,
          0x10000,
          (__int64)"Controller completed a command out of order",
          *(_QWORD *)(a1 + 72) + 16LL * *(unsigned int *)(a1 + 44),
          a2);
        Controller_ReportFatalError(*(_QWORD *)(a1 + 8), 0, 4114, 0, 0, 0, 0);
        *(_BYTE *)(a1 + 120) = 1;
      }
      break;
    }
    v15 = ++*(_DWORD *)(a1 + 44);
    if ( v15 == *(_DWORD *)(a1 + 48) )
    {
      *(_DWORD *)(a1 + 44) = 0;
      LOBYTE(v15) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v10) = 5;
        WPP_RECORDER_SF_DD(
          *(_QWORD *)(a1 + 16),
          (_DWORD)v10,
          7,
          46,
          (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
          v15,
          *(_DWORD *)(a1 + 40));
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qLLdd(
          *(_QWORD *)(a1 + 16),
          *(unsigned __int8 *)(a2 + 15),
          *(_DWORD *)(a2 + 12) & 1,
          v7,
          v31,
          (char)v14,
          (unsigned __int16)*((_DWORD *)v14 + 9) >> 10,
          *(_BYTE *)(a2 + 11),
          *(_BYTE *)(a2 + 12) & 1,
          *(_BYTE *)(a2 + 15));
    }
    v16 = *v14;
    if ( (*v14)[1] != (__int64 *)v14
      || (v17 = (__int64 ****)v14[1], *v17 != v14)
      || (*v17 = (__int64 ***)v16, v16[1] = (__int64 *)v17, v18 = v34, *v34 != (__int64 *)&v33) )
    {
LABEL_31:
      __fastfail(3u);
    }
    v14[1] = v34;
    *v14 = &v33;
    *v18 = v14;
    v27 = (_QWORD *)(a1 + 96);
    v28 = *(_QWORD **)(a1 + 96);
    v34 = (__int64 **)v14;
    if ( v28 != (_QWORD *)(a1 + 96) )
    {
      if ( (_QWORD *)v28[1] != v27 )
        goto LABEL_31;
      v29 = *v28;
      if ( *(_QWORD **)(*v28 + 8LL) != v28 )
        goto LABEL_31;
      *v27 = v29;
      *(_QWORD *)(v29 + 8) = v27;
      Command_InternalSendCommand(a1);
    }
    v14 = *(__int64 ****)(a1 + 80);
    v10 = WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids;
  }
  if ( *(_QWORD *)(a1 + 80) == a1 + 80 )
  {
    if ( *(_BYTE *)(a1 + 121) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        WPP_RECORDER_SF_(
          *(_QWORD *)(a1 + 16),
          (_DWORD)v10,
          7,
          49,
          (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v10) = 5;
        WPP_RECORDER_SF_(
          *(_QWORD *)(a1 + 16),
          (_DWORD)v10,
          7,
          48,
          (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids);
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2560))(
        WdfDriverGlobals,
        *(_QWORD *)(a1 + 24),
        0);
    }
  }
  DynamicLock_Release(*(_QWORD *)(a1 + 112));
  if ( v5 )
    Controller_RaiseAndTrackIrql(*(_QWORD *)(a1 + 8));
  while ( 1 )
  {
    v20 = v33;
    result = &v33;
    if ( v33 == (__int64 *)&v33 )
      return result;
    if ( (__int64 **)v33[1] != &v33 )
      goto LABEL_31;
    v22 = (__int64 *)*v33;
    if ( *(__int64 **)(*v33 + 8) != v33 )
      goto LABEL_31;
    v33 = (__int64 *)*v33;
    v22[1] = (__int64)&v33;
    v23 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 168LL);
    if ( v23 )
    {
      v30 = *(void (__fastcall **)(__int64, __int64 *))(v23 + 24);
      if ( v30 )
        v30(v23, v20);
    }
    v24 = *((unsigned __int8 *)v20 + 60);
    v25 = *((unsigned __int8 *)v20 + 60) - 1;
    if ( *((_BYTE *)v20 + 60) == 1 )
    {
      v26 = 0;
    }
    else if ( *((_BYTE *)v20 + 60) == 25 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v25) = 4;
        WPP_RECORDER_SF_qL(
          *(_QWORD *)(a1 + 16),
          v25,
          7,
          50,
          (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids,
          (char)v20,
          (unsigned __int8)HIBYTE(*((_WORD *)v20 + 18)) >> 2);
        LOBYTE(v24) = *((_BYTE *)v20 + 60);
      }
      v26 = 2;
    }
    else
    {
      v26 = 1;
    }
    if ( (_BYTE)v24 == 1 )
    {
      if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc & 0x20) != 0 )
        McTemplateK0ppb16qu_EtwWriteTransfer(
          v24,
          (unsigned int)USBXHCI_ETW_EVENT_COMMAND_COMPLETE,
          v19,
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL),
          (char)v20,
          (__int64)(v20 + 3),
          v26,
          1);
    }
    else
    {
      Etw_CommandCompleteError(v24, a1, v20, v26);
    }
    ((void (__fastcall *)(__int64 *, _QWORD, __int64))v20[5])(v20, v26, a2);
  }
}

```

## disassembly

```asm
0x140021f3c  push    rbp
0x140021f3e  push    rbx
0x140021f3f  push    rsi
0x140021f40  push    rdi
0x140021f41  push    r12
0x140021f43  push    r13
0x140021f45  push    r14
0x140021f47  push    r15
0x140021f49  mov     rbp, rsp
0x140021f4c  sub     rsp, 68h
0x140021f50  cmp     byte ptr [rdx+0Bh], 18h
0x140021f54  lea     rax, [rbp+var_18]
0x140021f58  mov     [rbp+var_10], rax
0x140021f5c  mov     r14, rdx
0x140021f5f  lea     rax, [rbp+var_18]
0x140021f63  mov     rbx, rcx
0x140021f66  mov     [rbp+var_18], rax
0x140021f6a  jz      loc_1400221BD
0x140021f70  xor     r13d, r13d
0x140021f73  mov     r12b, r13b
0x140021f76  call    cs:__imp_KeGetCurrentIrql
0x140021f7d  nop     dword ptr [rax+rax+00h]
0x140021f82  cmp     al, 2
0x140021f84  jnz     short loc_140021F97
0x140021f86  mov     rcx, [rbx+8]
0x140021f8a  cmp     [rcx+411h], r13b
0x140021f91  jnz     loc_1400222F8
0x140021f97  mov     rcx, [rbx+70h]
0x140021f9b  call    DynamicLock_Acquire
0x140021fa0  lea     r15, [rbx+50h]
0x140021fa4  mov     rdi, [r15]
0x140021fa7  lea     rdx, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x140021fae  cmp     rdi, r15
0x140021fb1  jz      loc_140022058
0x140021fb7  mov     rcx, rbx
0x140021fba  call    XilCommand_GetCommandRingBufferLogicalAddress
0x140021fbf  mov     esi, [rdi+14h]
0x140021fc2  shl     rsi, 4
0x140021fc6  add     rsi, rax
0x140021fc9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140021fd0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021fd7  jz      short loc_14002200D
0x140021fd9  mov     rax, cs:WPP_GLOBAL_Control
0x140021fe0  cmp     [rax+48h], r13w
0x140021fe5  jnz     loc_140022305
0x140021feb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140021ff2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021ff9  jz      short loc_14002200D
0x140021ffb  mov     rax, cs:WPP_GLOBAL_Control
0x140022002  cmp     [rax+48h], r13w
0x140022007  jnz     loc_14002232C
0x14002200d  cmp     [r14], rsi
0x140022010  jnz     loc_140022359
0x140022016  mov     dword ptr [rdi+10h], 2
0x14002201d  mov     al, [r14+0Bh]
0x140022021  mov     [rdi+3Ch], al
0x140022024  mov     eax, [r14+8]
0x140022028  and     eax, 0FFFFFFh
0x14002202d  mov     [rdi+40h], eax
0x140022030  mov     eax, [r14+0Ch]
0x140022034  and     eax, 0FC00h
0x140022039  cmp     eax, 8400h
0x14002203e  jnz     short loc_140022047
0x140022040  mov     al, [r14+0Fh]
0x140022044  mov     [rdi+3Dh], al
0x140022047  test    byte ptr [rdi+3Eh], 2
0x14002204b  lea     rdx, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x140022052  jnz     loc_140022361
0x140022058  mov     rdi, [r15]
0x14002205b  lea     rsi, WPP_RECORDER_INITIALIZED
0x140022062  cmp     rdi, r15
0x140022065  jz      short loc_1400220E3
0x140022067  cmp     dword ptr [rdi+10h], 2
0x14002206b  jnz     short loc_1400220D5
0x14002206d  inc     dword ptr [rbx+2Ch]
0x140022070  mov     ecx, [rbx+2Ch]
0x140022073  cmp     ecx, [rbx+30h]
0x140022076  jz      loc_140022226
0x14002207c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140022083  jz      short loc_1400220A4
0x140022085  mov     rax, cs:WPP_GLOBAL_Control
0x14002208c  cmp     [rax+48h], r13w
0x140022091  jnz     loc_14002236F
0x140022097  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14002209e  jnz     loc_1400222B9
0x1400220a4  mov     rax, [rdi]
0x1400220a7  cmp     [rax+8], rdi
0x1400220ab  jnz     short loc_1400220CE
0x1400220ad  mov     rcx, [rdi+8]
0x1400220b1  cmp     [rcx], rdi
0x1400220b4  jnz     short loc_1400220CE
0x1400220b6  mov     [rcx], rax
0x1400220b9  mov     [rax+8], rcx
0x1400220bd  lea     rcx, [rbp+var_18]
0x1400220c1  mov     rax, [rbp+var_10]
0x1400220c5  cmp     [rax], rcx
0x1400220c8  jz      loc_140022232
0x1400220ce  mov     ecx, 3
0x1400220d3  int     29h; Win8: RtlFailFast(ecx)
0x1400220d5  lea     rax, [rbp+var_18]
0x1400220d9  cmp     [rbp+var_18], rax
0x1400220dd  jz      loc_140022399
0x1400220e3  lea     rax, [rbx+50h]
0x1400220e7  cmp     [rax], rax
0x1400220ea  jz      loc_1400221D4
0x1400220f0  lea     r15, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x1400220f7  mov     rcx, [rbx+70h]
0x1400220fb  call    DynamicLock_Release
0x140022100  test    r12b, r12b
0x140022103  jz      short loc_14002210E
0x140022105  mov     rcx, [rbx+8]
0x140022109  call    Controller_RaiseAndTrackIrql
0x14002210e  mov     rdi, [rbp+var_18]
0x140022112  lea     rax, [rbp+var_18]
0x140022116  cmp     rdi, rax
0x140022119  jz      loc_1400221C2
0x14002211f  lea     rax, [rbp+var_18]
0x140022123  cmp     [rdi+8], rax
0x140022127  jnz     short loc_1400220CE
0x140022129  mov     rax, [rdi]
0x14002212c  cmp     [rax+8], rdi
0x140022130  jnz     short loc_1400220CE
0x140022132  mov     [rbp+var_18], rax
0x140022136  lea     rcx, [rbp+var_18]
0x14002213a  mov     [rax+8], rcx
0x14002213e  mov     rax, [rbx+8]
0x140022142  mov     rcx, [rax+0A8h]
0x140022149  test    rcx, rcx
0x14002214c  jnz     loc_140022423
0x140022152  movzx   ecx, byte ptr [rdi+3Ch]
0x140022156  mov     edx, ecx
0x140022158  sub     edx, 1
0x14002215b  jnz     loc_14002243D
0x140022161  mov     esi, r13d
0x140022164  cmp     cl, 1
0x140022167  jnz     loc_14002248E
0x14002216d  test    byte ptr cs:WPP_MAIN_CB.Queue+40h, 20h
0x140022174  jz      short loc_1400221A0
0x140022176  mov     r9, [rbx+8]
0x14002217a  lea     rax, [rdi+18h]
0x14002217e  mov     byte ptr [rsp+68h+var_30], cl
0x140022182  lea     rdx, USBXHCI_ETW_EVENT_COMMAND_COMPLETE
0x140022189  mov     dword ptr [rsp+68h+var_38], esi
0x14002218d  mov     [rsp+68h+var_40], rax
0x140022192  mov     r9, [r9+8]
0x140022196  mov     [rsp+68h+var_48], rdi
0x14002219b  call    McTemplateK0ppb16qu_EtwWriteTransfer
0x1400221a0  mov     rax, [rdi+28h]
0x1400221a4  mov     r8, r14
0x1400221a7  mov     edx, esi
0x1400221a9  mov     rcx, rdi
0x1400221ac  call    _guard_dispatch_icall
0x1400221b1  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400221b8  jmp     loc_14002210E
0x1400221bd  call    Command_HandleCommandRingStoppedEvent
0x1400221c2  add     rsp, 68h
0x1400221c6  pop     r15
0x1400221c8  pop     r14
0x1400221ca  pop     r13
0x1400221cc  pop     r12
0x1400221ce  pop     rdi
0x1400221cf  pop     rsi
0x1400221d0  pop     rbx
0x1400221d1  pop     rbp
0x1400221d2  retn
0x1400221d4  cmp     [rbx+79h], r13b
0x1400221d8  jnz     loc_140022286
0x1400221de  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400221e5  lea     r15, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x1400221ec  jz      short loc_140022200
0x1400221ee  mov     rax, cs:WPP_GLOBAL_Control
0x1400221f5  cmp     [rax+48h], r13w
0x1400221fa  jnz     loc_140022404
0x140022200  mov     rax, cs:WdfFunctions_01033
0x140022207  xor     r8d, r8d
0x14002220a  mov     rdx, [rbx+18h]
0x14002220e  mov     rcx, cs:WdfDriverGlobals
0x140022215  mov     rax, [rax+0A00h]
0x14002221c  call    _guard_dispatch_icall
0x140022221  jmp     loc_1400220F7
0x140022226  mov     [rbx+2Ch], r13d
0x14002222a  mov     ecx, r13d
0x14002222d  jmp     loc_14002207C
0x140022232  mov     [rdi+8], rax
0x140022236  lea     rcx, [rbp+var_18]
0x14002223a  mov     [rdi], rcx
0x14002223d  mov     [rax], rdi
0x140022240  lea     rax, [rbx+60h]
0x140022244  mov     rdx, [rax]
0x140022247  mov     [rbp+var_10], rdi
0x14002224b  cmp     rdx, rax
0x14002224e  jz      short loc_140022276
0x140022250  cmp     [rdx+8], rax
0x140022254  jnz     loc_1400220CE
0x14002225a  mov     rcx, [rdx]
0x14002225d  cmp     [rcx+8], rdx
0x140022261  jnz     loc_1400220CE
0x140022267  mov     [rax], rcx
0x14002226a  mov     [rcx+8], rax
0x14002226e  mov     rcx, rbx
0x140022271  call    Command_InternalSendCommand
0x140022276  mov     rdi, [rbx+50h]
0x14002227a  lea     rdx, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x140022281  jmp     loc_140022062
0x140022286  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14002228d  lea     r15, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x140022294  jz      loc_1400220F7
0x14002229a  mov     rcx, [rbx+10h]
0x14002229e  mov     r9d, 31h ; '1'
0x1400222a4  mov     dl, 4
0x1400222a6  mov     [rsp+68h+var_48], r15
0x1400222ab  lea     r8d, [r9-2Ah]
0x1400222af  call    WPP_RECORDER_SF_
0x1400222b4  jmp     loc_1400220F7
0x1400222b9  mov     ecx, [rdi+24h]
0x1400222bc  mov     r8d, [r14+0Ch]
0x1400222c0  movzx   edx, byte ptr [r14+0Fh]
0x1400222c5  and     r8d, 1
0x1400222c9  movzx   eax, byte ptr [r14+0Bh]
0x1400222ce  mov     [rsp+68h+var_20], edx
0x1400222d2  mov     [rsp+68h+var_28], r8d
0x1400222d7  shr     ecx, 0Ah
0x1400222da  and     ecx, 3Fh
0x1400222dd  mov     dword ptr [rsp+68h+var_30], eax
0x1400222e1  mov     dword ptr [rsp+68h+var_38], ecx
0x1400222e5  mov     rcx, [rbx+10h]
0x1400222e9  mov     [rsp+68h+var_40], rdi
0x1400222ee  call    WPP_RECORDER_SF_qLLdd
0x1400222f3  jmp     loc_1400220A4
0x1400222f8  call    Controller_LowerAndTrackIrql
0x1400222fd  mov     r12b, 1
0x140022300  jmp     loc_140021F97
0x140022305  mov     rax, [r14]
0x140022308  mov     rcx, [rbx+10h]
0x14002230c  mov     [rsp+68h+var_30], rax
0x140022311  mov     [rsp+68h+var_38], rsi
0x140022316  mov     [rsp+68h+var_40], rdi
0x14002231b  call    WPP_RECORDER_SF_qii
0x140022320  lea     rdx, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x140022327  jmp     loc_140021FEB
0x14002232c  mov     eax, [rbx+28h]
0x14002232f  mov     r9d, 2Dh ; '-'
0x140022335  mov     rcx, [rbx+10h]
0x140022339  mov     dword ptr [rsp+68h+var_38], eax
0x14002233d  mov     eax, [rbx+2Ch]
0x140022340  mov     dword ptr [rsp+68h+var_40], eax
0x140022344  lea     r8d, [r9-26h]
0x140022348  mov     [rsp+68h+var_48], rdx
0x14002234d  mov     dl, 5
0x14002234f  call    WPP_RECORDER_SF_DD
0x140022354  jmp     loc_14002200D
0x140022359  mov     rdi, [rdi]
0x14002235c  jmp     loc_140021FA7
0x140022361  movups  xmm0, xmmword ptr [r14]
0x140022365  movdqu  xmmword ptr [rdi+18h], xmm0
0x14002236a  jmp     loc_140022058
0x14002236f  mov     eax, [rbx+28h]
0x140022372  mov     r9d, 2Eh ; '.'
0x140022378  mov     dword ptr [rsp+68h+var_38], eax
0x14002237c  mov     dword ptr [rsp+68h+var_40], ecx
0x140022380  mov     rcx, [rbx+10h]
0x140022384  mov     [rsp+68h+var_48], rdx
0x140022389  lea     r8d, [r9-27h]
0x14002238d  mov     dl, 5
0x14002238f  call    WPP_RECORDER_SF_DD
0x140022394  jmp     loc_140022097
0x140022399  cmp     [rbx+78h], r13b
0x14002239d  jnz     loc_1400220E3
0x1400223a3  mov     eax, [rbx+2Ch]
0x1400223a6  mov     r9d, 10000h
0x1400223ac  mov     rcx, [rbx+8]
0x1400223b0  xor     r8d, r8d
0x1400223b3  shl     rax, 4
0x1400223b7  xor     edx, edx
0x1400223b9  add     rax, [rbx+48h]
0x1400223bd  mov     [rsp+68h+var_38], r14
0x1400223c2  mov     [rsp+68h+var_40], rax
0x1400223c7  lea     rax, aControllerComp; "Controller completed a command out of o"...
0x1400223ce  mov     [rsp+68h+var_48], rax
0x1400223d3  call    Controller_HwVerifierBreakIfEnabled
0x1400223d8  mov     rcx, [rbx+8]
0x1400223dc  xor     r9d, r9d
0x1400223df  mov     [rsp+68h+var_38], r13
0x1400223e4  xor     edx, edx
0x1400223e6  mov     [rsp+68h+var_40], r13
0x1400223eb  mov     r8d, 1012h
0x1400223f1  mov     [rsp+68h+var_48], r13
0x1400223f6  call    Controller_ReportFatalError
0x1400223fb  mov     byte ptr [rbx+78h], 1
0x1400223ff  jmp     loc_1400220E3
0x140022404  mov     rcx, [rbx+10h]
0x140022408  mov     r9d, 30h ; '0'
0x14002240e  mov     dl, 5
0x140022410  mov     [rsp+68h+var_48], r15
0x140022415  lea     r8d, [r9-29h]
0x140022419  call    WPP_RECORDER_SF_
0x14002241e  jmp     loc_140022200
0x140022423  mov     rax, [rcx+18h]
0x140022427  test    rax, rax
0x14002242a  jz      loc_140022152
  ... truncated ...
```
