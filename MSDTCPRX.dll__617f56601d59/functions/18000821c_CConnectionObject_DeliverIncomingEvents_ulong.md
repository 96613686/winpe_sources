# CConnectionObject::DeliverIncomingEvents(ulong *)

- ea: `0x18000821c`
- end: `0x180008930`
- name: `?DeliverIncomingEvents@CConnectionObject@@QEAAXPEAK@Z`
- size: `1812`
- prototype: `void __fastcall(CConnectionObject *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000fcbc`
- `0x18005c47c`

## callees

- `0x180003cf0`
- `0x180007270`
- `0x18000821c`
- `0x18000e75c`
- `0x1800682ac`
- `0x180085010`

## string_xrefs

- `0x180008270`: `CCO:Notification :       Received Incoming Event on Connection`
- `0x180008281`: `CConnectionObject::DeliverIncomingEvents`
- `0x180008397`: `CConnectionObject::DeliverIncomingEvents`
- `0x180008460`: `CConnectionObject::DeliverIncomingEvents`
- `0x18000858c`: `CConnectionObject::DeliverIncomingEvents`
- `0x1800086a9`: `CConnectionObject::DeliverIncomingEvents`
- `0x18000882a`: `CConnectionObject::DeliverIncomingEvents`
- `0x180008293`: `com\complus\dtc\dtc\cm\src\cco.cpp`
- `0x1800083a9`: `com\complus\dtc\dtc\cm\src\cco.cpp`
- `0x180008472`: `com\complus\dtc\dtc\cm\src\cco.cpp`
- `0x18000859e`: `com\complus\dtc\dtc\cm\src\cco.cpp`
- `0x1800086bb`: `com\complus\dtc\dtc\cm\src\cco.cpp`
- `0x18000883c`: `com\complus\dtc\dtc\cm\src\cco.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CConnectionObject::DeliverIncomingEvents(CConnectionObject *this, unsigned int *a2)
{
  int v4; // r15d
  int v5; // r13d
  char *v6; // rdi
  __int64 v7; // rdx
  _DWORD *v8; // r12
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int *v14; // rcx
  unsigned int v15; // r14d
  unsigned int v16; // r15d
  int v17; // eax
  int v18; // ecx
  int v19; // ecx
  __int64 v20; // [rsp+38h] [rbp-30h]
  void **v21; // [rsp+40h] [rbp-28h] BYREF
  __int64 v22; // [rsp+48h] [rbp-20h]
  __int64 v23; // [rsp+50h] [rbp-18h]
  char *v24; // [rsp+58h] [rbp-10h]
  int v25; // [rsp+B0h] [rbp+48h] BYREF
  int v26; // [rsp+B8h] [rbp+50h]
  int v27; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v28; // [rsp+C8h] [rbp+60h] BYREF

  v28 = 0;
  v21 = &UTStaticListIterator<CXaRm *>::`vftable';
  v24 = (char *)this + 128;
  v23 = 0;
  v22 = *((_QWORD *)this + 18);
  v25 = 1;
  v4 = 0;
  v26 = 0;
  v5 = 1;
  TraceStringInline(
    1,
    6,
    L"com\\complus\\dtc\\dtc\\cm\\src\\cco.cpp",
    2011,
    L"CConnectionObject::DeliverIncomingEvents",
    0,
    L"CCO:Notification :       Received Incoming Event on Connection");
  *a2 = 1;
  v6 = (char *)this + 160;
  (**((void (__fastcall ***)(char *))this + 20))((char *)this + 160);
  v8 = (_DWORD *)((char *)this + 76);
  while ( 1 )
  {
    while ( 1 )
    {
      v9 = 10;
      if ( v5 != 1 )
        goto LABEL_71;
      v27 = 1;
      if ( *((_DWORD *)this + 3) )
      {
        v7 = 6;
        *((_DWORD *)this + 13) = 6;
        v10 = *((_QWORD *)this + 13);
        if ( v10 )
        {
          if ( *v8 == 1 )
          {
            *((_DWORD *)this + 8) = 2;
            *((_DWORD *)this + 3) = 0;
            (*(void (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v10 + 8LL))(v10, 6, 0, &v27);
            *a2 = 2;
            goto LABEL_71;
          }
        }
      }
      if ( *((_DWORD *)this + 7) )
      {
        *((_DWORD *)this + 13) = 5;
        *((_DWORD *)this + 7) = 0;
        if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 648LL) + 80LL) == 1 )
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 15) + 8LL))(
            *((_QWORD *)this + 15),
            v7,
            10);
        v11 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 648LL) + 104LL);
        if ( (*(int (__fastcall **)(__int64, CConnectionObject *, _QWORD, _QWORD, char *))(*(_QWORD *)v11 + 24LL))(
               v11,
               this,
               *((_QWORD *)this + 15),
               *((unsigned int *)this + 11),
               (char *)this + 88) < 0 )
        {
          TraceStringInline(
            1,
            240,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cco.cpp",
            2086,
            L"CConnectionObject::DeliverIncomingEvents",
            0,
            L"ZZZZZZZZZZZZZZZZZ       CONNECTION REFUSED BY USER  ZZZZZZZZ");
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*((_QWORD *)this + 14) + 168LL) + 24LL))(
            *(_QWORD *)(*((_QWORD *)this + 14) + 168LL),
            28,
            3);
          *((_DWORD *)this + 18) = 0;
          goto LABEL_69;
        }
        v9 = 10;
      }
      if ( *((_DWORD *)this + 4) )
      {
        *((_DWORD *)this + 4) = 0;
        if ( *((_DWORD *)this + 8) == 5 )
        {
          *((_DWORD *)this + 8) = 4;
        }
        else if ( *((_DWORD *)this + 8) == 6 )
        {
          *((_DWORD *)this + 8) = 10;
        }
        else
        {
          LODWORD(v20) = *((_DWORD *)this + 8);
          TraceStringInline(
            1,
            240,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cco.cpp",
            2141,
            L"CConnectionObject::DeliverIncomingEvents",
            0,
            L"ERROR*****ConnState was %d ",
            v20);
        }
        *((_DWORD *)this + 13) = 7;
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 20) + 8LL))((char *)this + 160);
        v12 = 7;
        goto LABEL_18;
      }
      if ( !*((_DWORD *)this + 5) )
        break;
      *((_DWORD *)this + 13) = 8;
      if ( !*((_QWORD *)this + 13) )
        break;
      *((_DWORD *)this + 5) = 0;
      *((_DWORD *)this + 8) = 4;
      TraceStringInline(
        1,
        240,
        L"com\\complus\\dtc\\dtc\\cm\\src\\cco.cpp",
        2186,
        L"CConnectionObject::DeliverIncomingEvents",
        0,
        L"DELIVERING: MTAG_CONNECTION_UP");
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 20) + 8LL))((char *)this + 160);
      v12 = 8;
LABEL_18:
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 13) + 8LL))(
        *((_QWORD *)this + 13),
        v12,
        0,
        &v25);
      (**((void (__fastcall ***)(char *))this + 20))((char *)this + 160);
      v8 = (_DWORD *)((char *)this + 76);
      if ( !*((_DWORD *)this + 19) )
        goto LABEL_19;
    }
    if ( *((_DWORD *)this + 20) == 1 )
      goto LABEL_70;
    if ( *((_DWORD *)this + 6) && *((_DWORD *)this + 19) == 1 )
    {
      *((_DWORD *)this + 13) = 9;
      v19 = *((_DWORD *)this + 8);
      if ( (unsigned int)(v19 - 5) > 1 && (unsigned int)(v19 - 10) > 2 )
      {
        *((_DWORD *)this + 8) = 7;
        if ( *((_QWORD *)this + 13) )
        {
          *((_DWORD *)this + 6) = 0;
          (*(void (__fastcall **)(char *, __int64, __int64))(*(_QWORD *)v6 + 8LL))((char *)this + 160, v7, 10);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 13) + 8LL))(
            *((_QWORD *)this + 13),
            9,
            0,
            &v25);
          (**(void (__fastcall ***)(char *))v6)((char *)this + 160);
        }
LABEL_69:
        CConnectionObject::DrainTheIncomingMessageQueue(this);
      }
LABEL_70:
      *a2 = 2;
      goto LABEL_71;
    }
    v5 = 0;
    v23 = 0;
    v22 = *((_QWORD *)v24 + 2);
    if ( ((unsigned int (__fastcall *)(void ***, __int64, __int64))v21[2])(&v21, v7, 10) )
    {
      if ( *((_DWORD *)this + 19) == 1 )
        break;
    }
LABEL_52:
    if ( !*v8 )
      goto LABEL_19;
    if ( *((_DWORD *)this + 4) && *v8 == 1 )
    {
      *((_DWORD *)this + 4) = 0;
      if ( *((_DWORD *)this + 8) == 5 )
      {
        *((_DWORD *)this + 8) = 4;
      }
      else if ( *((_DWORD *)this + 8) == 6 )
      {
        *((_DWORD *)this + 8) = 10;
      }
      *((_DWORD *)this + 13) = 7;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))((char *)this + 160);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 13) + 8LL))(
        *((_QWORD *)this + 13),
        7,
        0,
        &v25);
      (**(void (__fastcall ***)(char *))v6)((char *)this + 160);
      if ( !*v8 )
      {
LABEL_19:
        *a2 = 4;
        goto LABEL_71;
      }
    }
    if ( *((_DWORD *)this + 6) && *v8 == 1 )
    {
      *((_DWORD *)this + 13) = 9;
      v18 = *((_DWORD *)this + 8);
      if ( (unsigned int)(v18 - 5) <= 1 || (unsigned int)(v18 - 10) <= 2 )
      {
        *((_DWORD *)this + 6) = 0;
        goto LABEL_70;
      }
      *((_DWORD *)this + 8) = 7;
      if ( *((_QWORD *)this + 13) )
      {
        *((_DWORD *)this + 6) = 0;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))((char *)this + 160);
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 13) + 8LL))(
          *((_QWORD *)this + 13),
          9,
          0,
          &v25);
        (**(void (__fastcall ***)(char *))v6)((char *)this + 160);
      }
      CConnectionObject::DrainTheIncomingMessageQueue(this);
      v5 = 0;
    }
  }
  if ( (unsigned int)(*((_DWORD *)this + 8) - 5) <= 1 )
  {
    *a2 = 2;
    goto LABEL_52;
  }
  v13 = *((_QWORD *)this + 15);
  if ( !v13 || (unsigned int)CClique::NoNeedToSkip(*(CClique **)(v13 + 8)) )
  {
    v5 = 1;
    UTStaticListIterator<CSessionObject *>::RemoveCurrent(&v21, &v28);
    v14 = *(unsigned int **)(v28 + 8);
    *((_QWORD *)this + 12) = v14;
    v15 = *v14;
    *((_DWORD *)this + 13) = *v14;
    *((_DWORD *)this + 20) = 1;
    if ( v15 != 1 )
    {
      if ( v15 == 2 )
      {
        *((_DWORD *)this + 8) = 11;
      }
      else if ( v15 == 4095 )
      {
        v15 = v14[3];
        *((_DWORD *)this + 13) = v15;
        if ( v14[3] == 4145 )
        {
          LODWORD(v20) = 4145;
          TraceStringInline(
            1,
            4,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cco.cpp",
            2390,
            L"CConnectionObject::DeliverIncomingEvents",
            0,
            L"DELIVERING: UMT= 0x%x",
            v20);
        }
      }
      goto LABEL_36;
    }
    v17 = 6;
    if ( *((_DWORD *)this + 8) != 5 )
      v17 = 10;
    *((_DWORD *)this + 8) = v17;
    if ( *((_DWORD *)this + 18) )
    {
LABEL_36:
      if ( !v4 )
      {
        v16 = *(_DWORD *)(*((_QWORD *)this + 12) + 16LL);
        if ( v16 )
        {
          _InterlockedIncrement((volatile signed __int32 *)this + 16);
        }
        else
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 14) + 160LL) + 24LL))(*(_QWORD *)(*((_QWORD *)this + 14) + 160LL));
          *((_QWORD *)this + 12) = 0;
        }
        if ( *((_QWORD *)this + 13) )
        {
          (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))((char *)this + 160);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 13) + 8LL))(
            *((_QWORD *)this + 13),
            v15,
            v16,
            &v25);
          (**(void (__fastcall ***)(char *))v6)((char *)this + 160);
        }
        LODWORD(v20) = v15;
        TraceStringInline(
          1,
          240,
          L"com\\complus\\dtc\\dtc\\cm\\src\\cco.cpp",
          2458,
          L"CConnectionObject::DeliverIncomingEvents",
          0,
          L"DELIVERED: MT= 0x%x",
          v20);
        v4 = v26;
      }
    }
    else
    {
      v4 = 1;
      v26 = 1;
      (*(void (__fastcall **)(CConnectionObject *))(*(_QWORD *)this + 40LL))(this);
    }
    v7 = *((_QWORD *)this + 12);
    if ( v7 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 14) + 160LL) + 24LL))(*(_QWORD *)(*((_QWORD *)this + 14) + 160LL));
      *((_QWORD *)this + 12) = 0;
    }
    *((_DWORD *)this + 20) = 0;
    goto LABEL_52;
  }
  *a2 = 3;
LABEL_71:
  (*(void (__fastcall **)(char *, __int64, __int64))(*(_QWORD *)v6 + 8LL))((char *)this + 160, v7, v9);
}

```

## disassembly

```asm
0x18000821c  push    rbp
0x18000821e  push    rbx
0x18000821f  push    rsi
0x180008220  push    rdi
0x180008221  push    r12
0x180008223  push    r13
0x180008225  push    r14
0x180008227  push    r15
0x180008229  mov     rbp, rsp
0x18000822c  sub     rsp, 68h
0x180008230  mov     rsi, rdx
0x180008233  mov     rbx, rcx
0x180008236  xor     r14d, r14d
0x180008239  mov     [rbp+arg_18], r14
0x18000823d  lea     rax, ??_7?$UTStaticListIterator@PEAVCXaRm@@@@6B@; const UTStaticListIterator<CXaRm *>::`vftable'
0x180008244  mov     [rbp+var_28], rax
0x180008248  lea     rax, [rcx+80h]
0x18000824f  mov     [rbp+var_10], rax
0x180008253  mov     [rbp+var_18], r14
0x180008257  mov     rax, [rax+10h]
0x18000825b  mov     [rbp+var_20], rax
0x18000825f  lea     edi, [r14+1]
0x180008263  mov     [rbp+arg_0], edi
0x180008266  mov     r15d, r14d
0x180008269  mov     [rbp+arg_8], r14d
0x18000826d  mov     r13d, edi
0x180008270  lea     rax, aCcoNotificatio; "CCO:Notification :       Received Incom"...
0x180008277  mov     [rsp+68h+var_38], rax
0x18000827c  mov     [rsp+68h+var_40], r14
0x180008281  lea     rax, aCconnectionobj_5; "CConnectionObject::DeliverIncomingEvent"...
0x180008288  mov     [rsp+68h+var_48], rax
0x18000828d  mov     r9d, 7DBh
0x180008293  lea     r8, aComComplusDtcD_45; "com\\complus\\dtc\\dtc\\cm\\src\\cco.cp"...
0x18000829a  lea     edx, [rdi+5]
0x18000829d  mov     ecx, edi
0x18000829f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800082a4  mov     [rsi], edi
0x1800082a6  lea     rdi, [rbx+0A0h]
0x1800082ad  mov     rax, [rdi]
0x1800082b0  mov     rcx, rdi
0x1800082b3  mov     rax, [rax]
0x1800082b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082bb  lea     r12, [rbx+4Ch]
0x1800082bf  mov     r8d, 0Ah
0x1800082c5  cmp     r13d, 1
0x1800082c9  jnz     loc_180008890
0x1800082cf  mov     [rbp+arg_10], r13d
0x1800082d3  mov     eax, [rbx+0Ch]
0x1800082d6  test    eax, eax
0x1800082d8  jz      short loc_1800082F4
0x1800082da  lea     edx, [r8-4]
0x1800082de  mov     [rbx+34h], edx
0x1800082e1  mov     rcx, [rbx+68h]
0x1800082e5  test    rcx, rcx
0x1800082e8  jz      short loc_1800082F4
0x1800082ea  cmp     [r12], r13d
0x1800082ee  jz      loc_1800087F3
0x1800082f4  mov     eax, [rbx+1Ch]
0x1800082f7  test    eax, eax
0x1800082f9  jz      short loc_180008364
0x1800082fb  mov     dword ptr [rbx+34h], 5
0x180008302  mov     [rbx+1Ch], r14d
0x180008306  mov     rax, [rbx+70h]
0x18000830a  mov     rcx, [rax+288h]
0x180008311  cmp     dword ptr [rcx+50h], 1
0x180008315  jnz     short loc_180008327
0x180008317  mov     rcx, [rbx+78h]
0x18000831b  mov     rax, [rcx]
0x18000831e  mov     rax, [rax+8]
0x180008322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008327  mov     rax, [rbx+70h]
0x18000832b  mov     rcx, [rax+288h]
0x180008332  mov     rcx, [rcx+68h]
0x180008336  mov     rax, [rcx]
0x180008339  lea     rdx, [rbx+58h]
0x18000833d  mov     [rsp+68h+var_48], rdx
0x180008342  mov     r9d, [rbx+2Ch]
0x180008346  mov     r8, [rbx+78h]
0x18000834a  mov     rdx, rbx
0x18000834d  mov     rax, [rax+18h]
0x180008351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008356  test    eax, eax
0x180008358  js      loc_180008819
0x18000835e  mov     r8d, 0Ah
0x180008364  mov     eax, [rbx+10h]
0x180008367  test    eax, eax
0x180008369  jz      loc_180008430
0x18000836f  mov     [rbx+10h], r14d
0x180008373  mov     edx, [rbx+20h]
0x180008376  mov     ecx, edx
0x180008378  sub     ecx, 5
0x18000837b  jz      short loc_1800083C7
0x18000837d  cmp     ecx, 1
0x180008380  jz      short loc_1800083C1
0x180008382  mov     dword ptr [rsp+68h+var_30], edx
0x180008386  lea     rax, aErrorConnstate; "ERROR*****ConnState was %d "
0x18000838d  mov     [rsp+68h+var_38], rax
0x180008392  mov     [rsp+68h+var_40], r14
0x180008397  lea     rax, aCconnectionobj_5; "CConnectionObject::DeliverIncomingEvent"...
0x18000839e  mov     [rsp+68h+var_48], rax
0x1800083a3  mov     r9d, 85Dh
0x1800083a9  lea     r8, aComComplusDtcD_45; "com\\complus\\dtc\\dtc\\cm\\src\\cco.cp"...
0x1800083b0  mov     edx, 0F0h
0x1800083b5  mov     ecx, 1
0x1800083ba  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800083bf  jmp     short loc_1800083CE
0x1800083c1  mov     [rbx+20h], r8d
0x1800083c5  jmp     short loc_1800083CE
0x1800083c7  mov     dword ptr [rbx+20h], 4
0x1800083ce  mov     r12d, 7
0x1800083d4  mov     [rbx+34h], r12d
0x1800083d8  mov     rax, [rbx+0A0h]
0x1800083df  mov     rcx, rdi
0x1800083e2  mov     rax, [rax+8]
0x1800083e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083eb  mov     edx, r12d
0x1800083ee  mov     rcx, [rbx+68h]
0x1800083f2  xor     r8d, r8d
0x1800083f5  lea     r9, [rbp+arg_0]
0x1800083f9  mov     rax, [rcx]
0x1800083fc  mov     rax, [rax+8]
0x180008400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008405  mov     rax, [rbx+0A0h]
0x18000840c  mov     rcx, rdi
0x18000840f  mov     rax, [rax]
0x180008412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008417  lea     r12, [rbx+4Ch]
0x18000841b  cmp     [r12], r14d
0x18000841f  jnz     loc_1800082BF
0x180008425  mov     dword ptr [rsi], 4
0x18000842b  jmp     loc_180008890
0x180008430  mov     eax, [rbx+14h]
0x180008433  test    eax, eax
0x180008435  jz      short loc_1800084A5
0x180008437  mov     dword ptr [rbx+34h], 8
0x18000843e  cmp     [rbx+68h], r14
0x180008442  jz      short loc_1800084A5
0x180008444  mov     [rbx+14h], r14d
0x180008448  mov     dword ptr [rbx+20h], 4
0x18000844f  lea     rax, aDeliveringMtag; "DELIVERING: MTAG_CONNECTION_UP"
0x180008456  mov     [rsp+68h+var_38], rax
0x18000845b  mov     [rsp+68h+var_40], r14
0x180008460  lea     rax, aCconnectionobj_5; "CConnectionObject::DeliverIncomingEvent"...
0x180008467  mov     [rsp+68h+var_48], rax
0x18000846c  mov     r9d, 88Ah
0x180008472  lea     r8, aComComplusDtcD_45; "com\\complus\\dtc\\dtc\\cm\\src\\cco.cp"...
0x180008479  mov     edx, 0F0h
0x18000847e  mov     ecx, 1
0x180008483  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180008488  mov     rax, [rbx+0A0h]
0x18000848f  mov     rcx, rdi
0x180008492  mov     rax, [rax+8]
0x180008496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000849b  mov     edx, 8
0x1800084a0  jmp     loc_1800083EE
0x1800084a5  cmp     dword ptr [rbx+50h], 1
0x1800084a9  jz      loc_18000888A
0x1800084af  mov     eax, [rbx+18h]
0x1800084b2  test    eax, eax
0x1800084b4  jz      short loc_1800084C0
0x1800084b6  cmp     dword ptr [rbx+4Ch], 1
0x1800084ba  jz      loc_1800088B1
0x1800084c0  mov     r13d, r14d
0x1800084c3  mov     [rbp+var_18], r14
0x1800084c7  mov     rax, [rbp+var_10]
0x1800084cb  mov     rcx, [rax+10h]
0x1800084cf  mov     [rbp+var_20], rcx
0x1800084d3  mov     rax, [rbp+var_28]
0x1800084d7  lea     rcx, [rbp+var_28]
0x1800084db  mov     rax, [rax+10h]
0x1800084df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084e4  test    eax, eax
0x1800084e6  jz      loc_1800086DE
0x1800084ec  cmp     dword ptr [rbx+4Ch], 1
0x1800084f0  jnz     loc_1800086DE
0x1800084f6  mov     eax, [rbx+20h]
0x1800084f9  sub     eax, 5
0x1800084fc  cmp     eax, 1
0x1800084ff  jbe     loc_1800086D8
0x180008505  mov     rcx, [rbx+78h]
0x180008509  test    rcx, rcx
0x18000850c  jz      short loc_18000851F
0x18000850e  mov     rcx, [rcx+8]; this
0x180008512  call    ?NoNeedToSkip@CClique@@QEAAHXZ; CClique::NoNeedToSkip(void)
0x180008517  test    eax, eax
0x180008519  jz      loc_18000891B
0x18000851f  mov     r13d, 1
0x180008525  lea     rdx, [rbp+arg_18]
0x180008529  lea     rcx, [rbp+var_28]
0x18000852d  call    ?RemoveCurrent@?$UTStaticListIterator@PEAVCSessionObject@@@@UEAAHPEAPEAV?$UTLink@PEAVCSessionObject@@@@@Z; UTStaticListIterator<CSessionObject *>::RemoveCurrent(UTLink<CSessionObject *> * *)
0x180008532  mov     rax, [rbp+arg_18]
0x180008536  mov     rcx, [rax+8]
0x18000853a  mov     [rbx+60h], rcx
0x18000853e  mov     r14d, [rcx]
0x180008541  mov     [rbx+34h], r14d
0x180008545  mov     [rbx+50h], r13d
0x180008549  mov     eax, r14d
0x18000854c  sub     eax, r13d
0x18000854f  jz      loc_1800085D5
0x180008555  sub     eax, r13d
0x180008558  jz      short loc_1800085CC
0x18000855a  cmp     eax, 0FFDh
0x18000855f  jnz     short loc_1800085B1
0x180008561  mov     r14d, [rcx+0Ch]
0x180008565  mov     [rbx+34h], r14d
0x180008569  mov     eax, 1031h
0x18000856e  cmp     [rcx+0Ch], eax
0x180008571  jnz     short loc_1800085B1
0x180008573  mov     dword ptr [rsp+68h+var_30], eax
0x180008577  lea     rax, aDeliveringUmt0; "DELIVERING: UMT= 0x%x"
0x18000857e  mov     [rsp+68h+var_38], rax
0x180008583  mov     [rsp+68h+var_40], 0
0x18000858c  lea     rax, aCconnectionobj_5; "CConnectionObject::DeliverIncomingEvent"...
0x180008593  mov     [rsp+68h+var_48], rax
0x180008598  mov     r9d, 956h
0x18000859e  lea     r8, aComComplusDtcD_45; "com\\complus\\dtc\\dtc\\cm\\src\\cco.cp"...
0x1800085a5  lea     edx, [r13+3]
0x1800085a9  mov     ecx, r13d
0x1800085ac  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800085b1  test    r15d, r15d
0x1800085b4  jnz     short loc_180008603
0x1800085b6  mov     rdx, [rbx+60h]
0x1800085ba  mov     r15d, [rdx+10h]
0x1800085be  test    r15d, r15d
0x1800085c1  jz      short loc_180008633
0x1800085c3  lock inc dword ptr [rbx+40h]
0x1800085c7  jmp     loc_180008652
0x1800085cc  mov     dword ptr [rbx+20h], 0Bh
0x1800085d3  jmp     short loc_1800085B1
0x1800085d5  mov     eax, 6
0x1800085da  cmp     dword ptr [rbx+20h], 5
0x1800085de  lea     ecx, [rax+4]
0x1800085e1  cmovnz  eax, ecx
0x1800085e4  mov     [rbx+20h], eax
0x1800085e7  cmp     dword ptr [rbx+48h], 0
0x1800085eb  jnz     short loc_1800085B1
0x1800085ed  mov     r15d, r13d
0x1800085f0  mov     [rbp+arg_8], r13d
0x1800085f4  mov     rax, [rbx]
0x1800085f7  mov     rcx, rbx
0x1800085fa  mov     rax, [rax+28h]
0x1800085fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008603  xor     r14d, r14d
0x180008606  mov     rdx, [rbx+60h]
0x18000860a  test    rdx, rdx
0x18000860d  jz      short loc_18000862A
0x18000860f  mov     rax, [rbx+70h]
0x180008613  mov     rcx, [rax+0A0h]
0x18000861a  mov     rax, [rcx]
0x18000861d  mov     rax, [rax+18h]
0x180008621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008626  mov     [rbx+60h], r14
0x18000862a  mov     [rbx+50h], r14d
0x18000862e  jmp     loc_1800086DE
0x180008633  mov     rax, [rbx+70h]
0x180008637  mov     rcx, [rax+0A0h]
0x18000863e  mov     rax, [rcx]
0x180008641  mov     rax, [rax+18h]
0x180008645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000864a  mov     qword ptr [rbx+60h], 0
0x180008652  cmp     qword ptr [rbx+68h], 0
0x180008657  jz      short loc_180008690
0x180008659  mov     rax, [rdi]
0x18000865c  mov     rcx, rdi
0x18000865f  mov     rax, [rax+8]
0x180008663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008668  mov     rcx, [rbx+68h]
0x18000866c  mov     rax, [rcx]
0x18000866f  lea     r9, [rbp+arg_0]
0x180008673  mov     r8d, r15d
0x180008676  mov     edx, r14d
0x180008679  mov     rax, [rax+8]
0x18000867d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008682  mov     rax, [rdi]
0x180008685  mov     rcx, rdi
0x180008688  mov     rax, [rax]
0x18000868b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008690  mov     dword ptr [rsp+68h+var_30], r14d
0x180008695  lea     rax, aDeliveredMt0xX; "DELIVERED: MT= 0x%x"
0x18000869c  mov     [rsp+68h+var_38], rax
0x1800086a1  xor     r14d, r14d
0x1800086a4  mov     [rsp+68h+var_40], r14
0x1800086a9  lea     rax, aCconnectionobj_5; "CConnectionObject::DeliverIncomingEvent"...
0x1800086b0  mov     [rsp+68h+var_48], rax
0x1800086b5  mov     r9d, 99Ah
0x1800086bb  lea     r8, aComComplusDtcD_45; "com\\complus\\dtc\\dtc\\cm\\src\\cco.cp"...
0x1800086c2  mov     edx, 0F0h
0x1800086c7  mov     ecx, r13d
0x1800086ca  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800086cf  mov     r15d, [rbp+arg_8]
0x1800086d3  jmp     loc_180008606
0x1800086d8  mov     dword ptr [rsi], 2
0x1800086de  cmp     [r12], r14d
0x1800086e2  jz      loc_180008425
0x1800086e8  mov     eax, [rbx+10h]
0x1800086eb  test    eax, eax
0x1800086ed  jz      short loc_180008760
0x1800086ef  cmp     dword ptr [r12], 1
0x1800086f4  jnz     short loc_180008760
0x1800086f6  mov     [rbx+10h], r14d
  ... truncated ...
```
