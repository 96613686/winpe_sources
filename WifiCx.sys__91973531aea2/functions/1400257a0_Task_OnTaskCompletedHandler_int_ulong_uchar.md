# Task::OnTaskCompletedHandler(int,ulong,uchar *)

- ea: `0x1400257a0`
- end: `0x140025d3d`
- name: `?OnTaskCompletedHandler@Task@@IEAAXHKPEAE@Z`
- size: `1437`
- prototype: `void(Task *__hidden this, int, unsigned int, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140062a60`
- `0x140062b18`
- `0x140062cb8`
- `0x140062ef0`

## callees

- `0x140009420`
- `0x14000c940`
- `0x14001a8c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x1400257a0`
- `0x1400332d0`
- `0x140039b80`
- `0x140050660`
- `0x14005113c`
- `0x140060f7c`
- `0x1400dfd00`
- `0x1400dfe00`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140025cb8`
- `ntoskrnl!EtwWriteTransfer` at `0x140025cb8`

## pseudocode

```c
void __fastcall Task::OnTaskCompletedHandler(Task *this, int a2, unsigned int a3, unsigned __int8 *a4)
{
  unsigned __int64 v5; // r14
  Task *v7; // rbx
  __int64 *v8; // rdx
  int v9; // esi
  unsigned int v10; // edx
  void *v11; // rcx
  void *v12; // rax
  int v13; // r15d
  __int16 v14; // r14
  const char *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  int v19; // edx
  __int64 v20; // [rsp+38h] [rbp-71h]
  __int16 v21; // [rsp+50h] [rbp-59h] BYREF
  _DWORD v22[3]; // [rsp+54h] [rbp-55h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-39h] BYREF
  char *v25; // [rsp+80h] [rbp-29h]
  int v26; // [rsp+88h] [rbp-21h]
  int v27; // [rsp+8Ch] [rbp-1Dh]
  const char *v28; // [rsp+90h] [rbp-19h]
  int v29; // [rsp+98h] [rbp-11h]
  int v30; // [rsp+9Ch] [rbp-Dh]
  _DWORD *v31; // [rsp+A0h] [rbp-9h]
  __int64 v32; // [rsp+A8h] [rbp-1h]
  __int16 *v33; // [rsp+B0h] [rbp+7h]
  __int64 v34; // [rsp+B8h] [rbp+Fh]

  v5 = a3;
  v7 = this;
  v8 = WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    this = (Task *)WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v8) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        a3,
        44,
        (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
        (char)v7,
        *((_DWORD *)v7 + 8));
      v8 = WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids;
    }
  }
  if ( *((_DWORD *)v7 + 12) == 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        a3,
        45,
        (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
        (char)v7,
        *((_DWORD *)v7 + 8));
    }
    if ( *((_DWORD *)v7 + 110) )
      a2 = 0;
    v9 = a2;
    if ( !a2 )
      goto LABEL_11;
LABEL_37:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      this = (Task *)WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v8) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v8,
          a3,
          27,
          (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
          (_BYTE)v7 + 56,
          *((_DWORD *)v7 + 16));
      }
    }
    v13 = *((_DWORD *)v7 + 38);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      this = (Task *)WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v8) = 5;
        LODWORD(v20) = 0;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v8,
          a3,
          29,
          (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
          (_BYTE)v7 + 56,
          *((_DWORD *)v7 + 16),
          v20);
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      this = (Task *)WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v8) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v8,
          a3,
          24,
          (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
          (_BYTE)v7 + 56,
          *((_DWORD *)v7 + 16));
      }
    }
    v14 = *((_WORD *)v7 + 110);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      this = (Task *)WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v8) = 5;
        LODWORD(v20) = 0;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v8,
          a3,
          26,
          (__int64)WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids,
          (_BYTE)v7 + 56,
          *((_DWORD *)v7 + 16),
          v20);
      }
    }
    if ( (unsigned int)dword_14010EC48 > 2 && (qword_14010EC58 & 5) != 0 && (qword_14010EC60 & 5) == qword_14010EC60 )
    {
      v21 = v14;
      v22[0] = v9;
      v15 = WDI_TLV::stringify::ToLogString(v13);
      v34 = 2;
      v32 = 4;
      v33 = &v21;
      v31 = v22;
      if ( v15 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        v17 = v16 + 1;
      }
      else
      {
        v15 = (const char *)&qword_1400FC9C8;
        v17 = 1;
      }
      v29 = v17;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_14010EC50;
      v28 = v15;
      v30 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 5;
      UserData.Size = *(unsigned __int16 *)off_14010EC50;
      v25 = byte_1401045B9;
      UserData.Reserved = 2;
      v26 = 86;
      v27 = 1;
      v22[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
    goto LABEL_11;
  }
  if ( !a2 && (!a4 || (unsigned int)v5 < 0x30) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qDqD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        a3,
        46,
        (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
        (char)v7,
        *((_DWORD *)v7 + 8),
        (char)a4,
        v5);
    }
    v9 = -1073676267;
    goto LABEL_37;
  }
  v9 = a2;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        a3,
        47,
        (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
        (char)v7,
        *((_DWORD *)v7 + 8),
        a2);
    }
    goto LABEL_37;
  }
  v11 = (void *)*((_QWORD *)v7 + 54);
  if ( v11 )
  {
    operator delete(v11);
    *((_QWORD *)v7 + 54) = 0;
    *((_DWORD *)v7 + 107) = 0;
  }
  v12 = operator new(v5);
  *((_QWORD *)v7 + 54) = v12;
  if ( !v12 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        a3,
        48,
        (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
        (char)v7,
        *((_DWORD *)v7 + 8));
    }
    v9 = -1073741670;
    goto LABEL_37;
  }
  *((_DWORD *)v7 + 107) = v5;
  memmove(v12, a4, v5);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v18 = *((_QWORD *)v7 + 54);
    v19 = *(unsigned __int16 *)(v18 + 32);
    LOBYTE(v19) = 4;
    WPP_RECORDER_SF_qDddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      a3,
      49,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      (char)v7,
      *((_DWORD *)v7 + 8),
      *(_WORD *)(v18 + 32),
      *(_DWORD *)(v18 + 40),
      *(_DWORD *)(v18 + 36));
  }
LABEL_11:
  if ( !*((_BYTE *)v7 + 424) )
    v9 = EventQueue::PopulateAndQueueDeferredCallback(
           *((_QWORD *)v7 + 30),
           1,
           *((_QWORD *)v7 + 32),
           v7,
           v9,
           (char *)v7 + 72);
  v10 = *((_DWORD *)v7 + 66);
  *((_DWORD *)v7 + 110) = v9;
  *((_DWORD *)v7 + 12) = 3;
  if ( v10 )
  {
    v9 = NotificationManager::DeregisterNotificationHandler(*((NotificationManager **)v7 + 34), v10);
    *((_DWORD *)v7 + 66) = 0;
  }
  if ( !*((_BYTE *)v7 + 456) )
  {
    EventQueue::StopTimer(this, *((struct TimerRegistrationContext **)v7 + 56));
    *((_BYTE *)v7 + 456) = 1;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    LODWORD(v20) = v9;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      a3,
      50,
      (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
      (char)v7,
      *((_DWORD *)v7 + 8),
      v20);
  }
}

```

## disassembly

```asm
0x1400257a0  mov     [rsp-8+arg_8], rbx
0x1400257a5  push    rbp
0x1400257a6  push    rsi
0x1400257a7  push    rdi
0x1400257a8  push    r12
0x1400257aa  push    r13
0x1400257ac  push    r14
0x1400257ae  push    r15
0x1400257b0  lea     rbp, [rsp-27h]
0x1400257b5  sub     rsp, 0D0h
0x1400257bc  mov     rax, cs:__security_cookie
0x1400257c3  xor     rax, rsp
0x1400257c6  mov     [rbp+57h+var_40], rax
0x1400257ca  mov     r15, r9
0x1400257cd  mov     r14d, r8d
0x1400257d0  mov     edi, edx
0x1400257d2  mov     rbx, rcx
0x1400257d5  lea     r12, WPP_RECORDER_INITIALIZED
0x1400257dc  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400257e3  lea     rdx, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x1400257ea  jz      short loc_140025829
0x1400257ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400257f3  cmp     byte ptr [rcx+29h], 5
0x1400257f7  jnb     short loc_140025800
0x1400257f9  cmp     word ptr [rcx+48h], 0
0x1400257fe  jz      short loc_140025829
0x140025800  mov     eax, [rbx+20h]
0x140025803  mov     r9d, 2Ch ; ','
0x140025809  mov     rcx, [rcx+40h]
0x14002580d  mov     [rsp+100h+var_D0], eax
0x140025811  mov     [rsp+100h+UserData], rbx
0x140025816  mov     qword ptr [rsp+100h+UserDataCount], rdx
0x14002581b  mov     dl, 5
0x14002581d  call    WPP_RECORDER_SF_qD
0x140025822  lea     rdx, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x140025829  xor     r13d, r13d
0x14002582c  cmp     dword ptr [rbx+30h], 3
0x140025830  jnz     loc_14002596A
0x140025836  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002583d  jz      short loc_140025868
0x14002583f  mov     rcx, cs:WPP_GLOBAL_Control
0x140025846  mov     r9d, 2Dh ; '-'
0x14002584c  mov     eax, [rbx+20h]
0x14002584f  mov     [rsp+100h+var_D0], eax
0x140025853  mov     [rsp+100h+UserData], rbx
0x140025858  mov     rcx, [rcx+40h]
0x14002585c  mov     qword ptr [rsp+100h+UserDataCount], rdx
0x140025861  mov     dl, 4
0x140025863  call    WPP_RECORDER_SF_qD
0x140025868  cmp     [rbx+1B8h], r13d
0x14002586f  cmovnz  edi, r13d
0x140025873  mov     esi, edi
0x140025875  test    edi, edi
0x140025877  jnz     loc_140025A76
0x14002587d  lea     rdi, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x140025884  cmp     [rbx+1A8h], r13b
0x14002588b  jnz     short loc_1400258B7
0x14002588d  mov     r8, [rbx+100h]
0x140025894  lea     rax, [rbx+48h]
0x140025898  mov     rcx, [rbx+0F0h]
0x14002589f  mov     r9, rbx
0x1400258a2  mov     [rsp+100h+UserData], rax
0x1400258a7  mov     edx, 1
0x1400258ac  mov     [rsp+100h+UserDataCount], esi
0x1400258b0  call    ?PopulateAndQueueDeferredCallback@EventQueue@@IEAAHW4_WFC_EVENT_TYPE@@PEAX1HPEAVEvent@@@Z; EventQueue::PopulateAndQueueDeferredCallback(_WFC_EVENT_TYPE,void *,void *,int,Event *)
0x1400258b5  mov     esi, eax
0x1400258b7  mov     edx, [rbx+108h]; unsigned int
0x1400258bd  mov     [rbx+1B8h], esi
0x1400258c3  mov     dword ptr [rbx+30h], 3
0x1400258ca  test    edx, edx
0x1400258cc  jz      short loc_1400258E3
0x1400258ce  mov     rcx, [rbx+110h]; this
0x1400258d5  call    ?DeregisterNotificationHandler@NotificationManager@@QEAAHK@Z; NotificationManager::DeregisterNotificationHandler(ulong)
0x1400258da  mov     esi, eax
0x1400258dc  mov     [rbx+108h], r13d
0x1400258e3  cmp     [rbx+1C8h], r13b
0x1400258ea  jnz     short loc_1400258FF
0x1400258ec  mov     rdx, [rbx+1C0h]; struct TimerRegistrationContext *
0x1400258f3  call    ?StopTimer@EventQueue@@QEAAXPEAVTimerRegistrationContext@@@Z; EventQueue::StopTimer(TimerRegistrationContext *)
0x1400258f8  mov     byte ptr [rbx+1C8h], 1
0x1400258ff  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140025906  jz      short loc_140025942
0x140025908  mov     rcx, cs:WPP_GLOBAL_Control
0x14002590f  cmp     byte ptr [rcx+29h], 5
0x140025913  jnb     short loc_14002591C
0x140025915  cmp     [rcx+48h], r13w
0x14002591a  jz      short loc_140025942
0x14002591c  mov     eax, [rbx+20h]
0x14002591f  mov     r9d, 32h ; '2'
0x140025925  mov     rcx, [rcx+40h]
0x140025929  mov     dl, 5
0x14002592b  mov     dword ptr [rsp+100h+var_C8], esi
0x14002592f  mov     [rsp+100h+var_D0], eax
0x140025933  mov     [rsp+100h+UserData], rbx
0x140025938  mov     qword ptr [rsp+100h+UserDataCount], rdi
0x14002593d  call    WPP_RECORDER_SF_qDD
0x140025942  mov     rcx, [rbp+57h+var_40]
0x140025946  xor     rcx, rsp; StackCookie
0x140025949  call    __security_check_cookie
0x14002594e  mov     rbx, [rsp+100h+arg_8]
0x140025956  add     rsp, 0D0h
0x14002595d  pop     r15
0x14002595f  pop     r14
0x140025961  pop     r13
0x140025963  pop     r12
0x140025965  pop     rdi
0x140025966  pop     rsi
0x140025967  pop     rbp
0x140025968  retn
0x14002596a  test    edi, edi
0x14002596c  jnz     short loc_1400259BF
0x14002596e  test    r15, r15
0x140025971  jz      short loc_140025979
0x140025973  cmp     r14d, 30h ; '0'
0x140025977  jnb     short loc_1400259BF
0x140025979  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140025980  jz      short loc_1400259B5
0x140025982  mov     rcx, cs:WPP_GLOBAL_Control
0x140025989  mov     r9d, 2Eh ; '.'
0x14002598f  mov     eax, [rbx+20h]
0x140025992  mov     [rsp+100h+var_C0], r14d
0x140025997  mov     [rsp+100h+var_C8], r15
0x14002599c  mov     rcx, [rcx+40h]
0x1400259a0  mov     [rsp+100h+var_D0], eax
0x1400259a4  mov     [rsp+100h+UserData], rbx
0x1400259a9  mov     qword ptr [rsp+100h+UserDataCount], rdx
0x1400259ae  mov     dl, 2
0x1400259b0  call    WPP_RECORDER_SF_qDqD
0x1400259b5  mov     esi, 0C0010015h
0x1400259ba  jmp     loc_140025A76
0x1400259bf  mov     esi, edi
0x1400259c1  test    edi, edi
0x1400259c3  jz      short loc_140025A01
0x1400259c5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400259cc  jz      loc_140025A76
0x1400259d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400259d9  mov     r9d, 2Fh ; '/'
0x1400259df  mov     eax, [rbx+20h]
0x1400259e2  mov     dword ptr [rsp+100h+var_C8], edi
0x1400259e6  mov     [rsp+100h+var_D0], eax
0x1400259ea  mov     rcx, [rcx+40h]
0x1400259ee  mov     [rsp+100h+UserData], rbx
0x1400259f3  mov     qword ptr [rsp+100h+UserDataCount], rdx
0x1400259f8  mov     dl, 2
0x1400259fa  call    WPP_RECORDER_SF_qDD
0x1400259ff  jmp     short loc_140025A76
0x140025a01  mov     rcx, [rbx+1B0h]; void *
0x140025a08  test    rcx, rcx
0x140025a0b  jz      short loc_140025A20
0x140025a0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140025a12  mov     [rbx+1B0h], r13
0x140025a19  mov     [rbx+1ACh], r13d
0x140025a20  mov     rcx, r14; unsigned __int64
0x140025a23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140025a28  mov     [rbx+1B0h], rax
0x140025a2f  test    rax, rax
0x140025a32  jnz     loc_140025CC9
0x140025a38  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140025a3f  jz      short loc_140025A71
0x140025a41  mov     eax, [rbx+20h]
0x140025a44  mov     r9d, 30h ; '0'
0x140025a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025a51  mov     dl, 2
0x140025a53  mov     [rsp+100h+var_D0], eax
0x140025a57  lea     rax, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x140025a5e  mov     [rsp+100h+UserData], rbx
0x140025a63  mov     qword ptr [rsp+100h+UserDataCount], rax
0x140025a68  mov     rcx, [rcx+40h]
0x140025a6c  call    WPP_RECORDER_SF_qD
0x140025a71  mov     esi, 0C000009Ah
0x140025a76  lea     rdi, [rbx+38h]
0x140025a7a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140025a81  lea     r14, WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids
0x140025a88  jz      short loc_140025AC0
0x140025a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025a91  cmp     byte ptr [rcx+29h], 5
0x140025a95  jnb     short loc_140025A9E
0x140025a97  cmp     [rcx+48h], r13w
0x140025a9c  jz      short loc_140025AC0
0x140025a9e  mov     eax, [rdi+8]
0x140025aa1  mov     r9d, 1Bh
0x140025aa7  mov     rcx, [rcx+40h]
0x140025aab  mov     dl, 5
0x140025aad  mov     [rsp+100h+var_D0], eax
0x140025ab1  mov     [rsp+100h+UserData], rdi
0x140025ab6  mov     qword ptr [rsp+100h+UserDataCount], r14
0x140025abb  call    WPP_RECORDER_SF_qD
0x140025ac0  mov     r15d, [rdi+60h]
0x140025ac4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140025acb  jz      short loc_140025B08
0x140025acd  mov     rcx, cs:WPP_GLOBAL_Control
0x140025ad4  cmp     byte ptr [rcx+29h], 5
0x140025ad8  jnb     short loc_140025AE1
0x140025ada  cmp     [rcx+48h], r13w
0x140025adf  jz      short loc_140025B08
0x140025ae1  mov     eax, [rdi+8]
0x140025ae4  mov     r9d, 1Dh
0x140025aea  mov     rcx, [rcx+40h]
0x140025aee  mov     dl, 5
0x140025af0  mov     dword ptr [rsp+100h+var_C8], r13d
0x140025af5  mov     [rsp+100h+var_D0], eax
0x140025af9  mov     [rsp+100h+UserData], rdi
0x140025afe  mov     qword ptr [rsp+100h+UserDataCount], r14
0x140025b03  call    WPP_RECORDER_SF_qDD
0x140025b08  lea     rdi, [rbx+38h]
0x140025b0c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140025b13  jz      short loc_140025B4B
0x140025b15  mov     rcx, cs:WPP_GLOBAL_Control
0x140025b1c  cmp     byte ptr [rcx+29h], 5
0x140025b20  jnb     short loc_140025B29
0x140025b22  cmp     [rcx+48h], r13w
0x140025b27  jz      short loc_140025B4B
0x140025b29  mov     eax, [rdi+8]
0x140025b2c  mov     r9d, 18h
0x140025b32  mov     rcx, [rcx+40h]
0x140025b36  mov     dl, 5
0x140025b38  mov     [rsp+100h+var_D0], eax
0x140025b3c  mov     [rsp+100h+UserData], rdi
0x140025b41  mov     qword ptr [rsp+100h+UserDataCount], r14
0x140025b46  call    WPP_RECORDER_SF_qD
0x140025b4b  movzx   r14d, word ptr [rdi+0A4h]
0x140025b53  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140025b5a  jz      short loc_140025B9E
0x140025b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140025b63  cmp     byte ptr [rcx+29h], 5
0x140025b67  jnb     short loc_140025B70
0x140025b69  cmp     [rcx+48h], r13w
0x140025b6e  jz      short loc_140025B9E
0x140025b70  mov     eax, [rdi+8]
0x140025b73  mov     r9d, 1Ah
0x140025b79  mov     rcx, [rcx+40h]
0x140025b7d  mov     dl, 5
0x140025b7f  mov     dword ptr [rsp+100h+var_C8], r13d
0x140025b84  mov     [rsp+100h+var_D0], eax
0x140025b88  lea     rax, WPP_c68f3bb5a1b239f184b6030665abb396_Traceguids
0x140025b8f  mov     [rsp+100h+UserData], rdi
0x140025b94  mov     qword ptr [rsp+100h+UserDataCount], rax
0x140025b99  call    WPP_RECORDER_SF_qDD
0x140025b9e  mov     eax, cs:dword_14010EC48
0x140025ba4  cmp     eax, 2
0x140025ba7  jbe     loc_14002587D
0x140025bad  mov     rdx, cs:qword_14010EC60
0x140025bb4  mov     rax, cs:qword_14010EC58
0x140025bbb  test    al, 5
0x140025bbd  jz      loc_14002587D
0x140025bc3  mov     rax, rdx
0x140025bc6  and     eax, 5
0x140025bc9  cmp     rax, rdx
0x140025bcc  jnz     loc_14002587D
0x140025bd2  movzx   ecx, r15w
0x140025bd6  mov     [rbp+57h+var_B0], r14w
0x140025bdb  mov     [rbp+57h+var_AC], esi
0x140025bde  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x140025be3  mov     rcx, rax
0x140025be6  mov     [rbp+57h+var_48], 2
0x140025bee  mov     [rbp+57h+var_58], 4
0x140025bf6  lea     rax, [rbp+57h+var_B0]
0x140025bfa  mov     [rbp+57h+var_50], rax
0x140025bfe  lea     rax, [rbp+57h+var_AC]
0x140025c02  mov     [rbp+57h+var_60], rax
0x140025c06  test    rcx, rcx
0x140025c09  jz      short loc_140025C1F
0x140025c0b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140025c12  inc     rax
0x140025c15  cmp     [rcx+rax], r13b
0x140025c19  jnz     short loc_140025C12
0x140025c1b  inc     eax
0x140025c1d  jmp     short loc_140025C2B
0x140025c1f  lea     rcx, qword_1400FC9C8
0x140025c26  mov     eax, 1
0x140025c2b  mov     [rbp+57h+var_68], eax
0x140025c2e  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140025c32  movzx   eax, cs:word_1401045AF
0x140025c39  xor     r9d, r9d; RelatedActivityId
0x140025c3c  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140025c3f  xor     r8d, r8d; ActivityId
0x140025c42  mov     rax, cs:off_14010EC50
0x140025c49  mov     [rbp+57h+var_90.Ptr], rax
0x140025c4d  mov     [rbp+57h+var_70], rcx
0x140025c51  lea     rcx, _TraceLoggingMetadata
0x140025c58  mov     [rbp+57h+var_64], r13d
0x140025c5c  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140025c63  mov     [rbp+57h+EventDescriptor.Keyword], 5
0x140025c6b  movzx   eax, word ptr [rax]
0x140025c6e  mov     [rbp+57h+var_90.Size], eax
0x140025c71  lea     rax, byte_1401045B9
0x140025c78  mov     [rbp+57h+var_80], rax
0x140025c7c  lea     rax, _TraceLoggingMetadataEnd
0x140025c83  sub     eax, ecx
0x140025c85  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x140025c8c  mov     [rbp+57h+var_78], 56h ; 'V'
0x140025c93  mov     [rbp+57h+var_74], 1
0x140025c9a  mov     [rbp+57h+var_A8], eax
0x140025c9d  mov     eax, [rbp+57h+var_A8]
0x140025ca0  mov     rcx, cs:RegHandle; RegHandle
0x140025ca7  lea     rax, [rbp+57h+var_90]
0x140025cab  mov     [rsp+100h+UserData], rax; UserData
0x140025cb0  mov     [rsp+100h+UserDataCount], 5; UserDataCount
0x140025cb8  call    cs:__imp_EtwWriteTransfer
0x140025cbf  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
