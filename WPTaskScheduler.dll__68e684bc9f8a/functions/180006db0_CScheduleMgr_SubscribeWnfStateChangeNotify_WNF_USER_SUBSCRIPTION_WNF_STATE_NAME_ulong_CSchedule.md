# CScheduleMgr::SubscribeWnfStateChangeNotify(_WNF_USER_SUBSCRIPTION * *,_WNF_STATE_NAME,ulong,CSchedule *)

- ea: `0x180006db0`
- end: `0x180007408`
- name: `?SubscribeWnfStateChangeNotify@CScheduleMgr@@QEAAJPEAPEAU_WNF_USER_SUBSCRIPTION@@U_WNF_STATE_NAME@@KPEAVCSchedule@@@Z`
- size: `1624`
- prototype: `__int64 __fastcall(CScheduleMgr *__hidden this, struct _WNF_USER_SUBSCRIPTION **, struct _WNF_STATE_NAME, unsigned int, struct CSchedule *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800068b0`

## callees

- `0x180006db0`
- `0x180008b60`
- `0x180008bf8`
- `0x180008c80`
- `0x18000e3d0`
- `0x18000e970`
- `0x18000ea40`
- `0x18000f0c0`
- `0x180010094`
- `0x180018560`
- `0x180019a34`
- `0x180019a9c`
- `0x180019b28`
- `0x180020c30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007090`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007090`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800070c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800070c0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000707f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000707f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800070b7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800070b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f82`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180006f4c`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180006f4c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800072d7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800072d7`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::SubscribeWnfStateChangeNotify(
        CScheduleMgr *this,
        struct _WNF_USER_SUBSCRIPTION **a2,
        struct _WNF_STATE_NAME a3,
        unsigned int a4,
        struct CSchedule *a5)
{
  struct _WNF_STATE_NAME v6; // rdi
  int v7; // r13d
  int v9; // ecx
  char v10; // r15
  struct CSchedule *v11; // r10
  struct CSchedule *v12; // rdx
  struct CSchedule *i; // rcx
  struct CSchedule *v14; // rax
  struct CSchedule *v15; // r9
  unsigned __int64 v16; // r8
  __int64 v17; // r8
  int v18; // eax
  struct _WNF_USER_SUBSCRIPTION **v19; // rcx
  unsigned int v20; // esi
  struct CSchedule *v22; // rax
  struct CSchedule *v23; // rbx
  struct _WNF_USER_SUBSCRIPTION **v24; // r15
  char v25; // al
  struct _WNF_USER_SUBSCRIPTION *j; // rbx
  struct _WNF_STATE_NAME *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  struct _WNF_STATE_NAME *v30; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v32; // r14
  int v33; // ebx
  struct _WNF_USER_SUBSCRIPTION *v34; // rax
  struct _WNF_USER_SUBSCRIPTION *v35; // rax
  __int64 v36; // rax
  int v37; // ecx
  _QWORD *v38; // rbx
  _QWORD *v39; // rax
  __int64 v40; // r8
  unsigned __int64 v41; // rbx
  _QWORD *v42; // rbx
  __int64 v43; // [rsp+40h] [rbp-98h] BYREF
  struct _WNF_STATE_NAME v44; // [rsp+48h] [rbp-90h]
  struct _WNF_STATE_NAME v45; // [rsp+50h] [rbp-88h] BYREF
  struct CSchedule *v46; // [rsp+58h] [rbp-80h] BYREF
  struct _WNF_USER_SUBSCRIPTION **v47; // [rsp+60h] [rbp-78h]
  struct CSchedule *v48; // [rsp+68h] [rbp-70h] BYREF
  int v49; // [rsp+70h] [rbp-68h]
  int v50; // [rsp+74h] [rbp-64h]
  _QWORD *v51; // [rsp+78h] [rbp-60h]
  struct CSchedule *v52; // [rsp+80h] [rbp-58h] BYREF
  __int64 v53; // [rsp+88h] [rbp-50h]

  LODWORD(v43) = a4;
  v6 = a3;
  v47 = a2;
  v44 = a3;
  v7 = (int)a5;
  v46 = a5;
  v45 = a3;
  if ( !a2 || !a5 )
    return 3221225473LL;
  EnterCriticalSection(&CriticalSection);
  v10 = v44.Data[1];
  if ( (byte_180030D07 & 4) != 0 )
    McTemplateU0jqqq_EventWriteTransfer(v9, (int)SubscribeWnf, (_DWORD)a5 + 16, v6.Data[0], v44.Data[1], a4);
  v11 = (struct CSchedule *)xmmword_180030BE0;
  v12 = *(struct CSchedule **)(xmmword_180030BE0 + 8);
  i = v12;
  v14 = (struct CSchedule *)xmmword_180030BE0;
  v15 = (struct CSchedule *)xmmword_180030BE0;
  while ( !*((_BYTE *)i + 25) )
  {
    v16 = *((_QWORD *)i + 4);
    if ( v16 < *(_QWORD *)&a3 )
    {
      i = (struct CSchedule *)*((_QWORD *)i + 2);
    }
    else
    {
      if ( *((_BYTE *)v15 + 25) && *(_QWORD *)&a3 < v16 )
        v15 = i;
      v14 = i;
      i = *(struct CSchedule **)i;
    }
  }
  if ( !*((_BYTE *)v15 + 25) )
    v12 = *(struct CSchedule **)v15;
  while ( !*((_BYTE *)v12 + 25) )
  {
    if ( *(unsigned __int64 *)&a3 < *((_QWORD *)v12 + 4) )
    {
      v15 = v12;
      v12 = *(struct CSchedule **)v12;
    }
    else
    {
      v12 = (struct CSchedule *)*((_QWORD *)v12 + 2);
    }
  }
  v17 = 0;
  while ( v14 != v15 )
  {
    ++v17;
    if ( !*((_BYTE *)v14 + 25) )
    {
      i = (struct CSchedule *)*((_QWORD *)v14 + 2);
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (struct CSchedule *)*((_QWORD *)v14 + 1); !*((_BYTE *)i + 25); i = (struct CSchedule *)*((_QWORD *)i + 1) )
        {
          if ( v14 != *((struct CSchedule **)i + 2) )
            break;
          v14 = i;
        }
LABEL_38:
        v14 = i;
      }
      else
      {
        v12 = *(struct CSchedule **)i;
        if ( *(_BYTE *)(*(_QWORD *)i + 25LL) )
          goto LABEL_38;
        do
        {
          v14 = v12;
          i = *(struct CSchedule **)v12;
          v12 = i;
        }
        while ( !*((_BYTE *)i + 25) );
      }
    }
  }
  if ( v17 )
  {
    v20 = 0;
    if ( (byte_180030D07 & 8) != 0 )
    {
      McTemplateU0jqqqq_EventWriteTransfer(
        (int)i,
        (int)NewWnfSubscriptionListener,
        (_DWORD)a5 + 16,
        (int)a5,
        v6.Data[0],
        v44.Data[1],
        a4);
      v11 = (struct CSchedule *)xmmword_180030BE0;
    }
    v22 = (struct CSchedule *)*((_QWORD *)v11 + 1);
    v23 = v11;
    while ( !*((_BYTE *)v22 + 25) )
    {
      if ( *((_QWORD *)v22 + 4) < *(unsigned __int64 *)&a3 )
      {
        v22 = (struct CSchedule *)*((_QWORD *)v22 + 2);
      }
      else
      {
        v23 = v22;
        v22 = *(struct CSchedule **)v22;
      }
    }
    if ( v23 == v11 || *(unsigned __int64 *)&a3 < *((_QWORD *)v23 + 4) )
    {
      v52 = (struct CSchedule *)a3;
      v53 = 0;
      v36 = std::_Tree_buy<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>::_Buynode<std::pair<unsigned __int64,_EVENT_SUBSCRIPTION *>>(
              &xmmword_180030BE0,
              &v52);
      std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::_Insert_hint<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *> &,std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *>(
        (int)&xmmword_180030BE0,
        (int)&v46,
        (int)v23,
        v36 + 32,
        v36);
      v23 = v46;
    }
    v24 = (struct _WNF_USER_SUBSCRIPTION **)*((_QWORD *)v23 + 5);
    v25 = 0;
    for ( j = v24[1]; j != v24[2]; j = (struct _WNF_USER_SUBSCRIPTION *)((char *)j + 16) )
    {
      v12 = *(struct CSchedule **)j;
      if ( *(struct CSchedule **)j == a5 )
      {
        i = (struct CSchedule *)(*((_QWORD *)v12 + 2) - *((_QWORD *)a5 + 2));
        if ( !i )
          i = (struct CSchedule *)(*((_QWORD *)v12 + 3) - *((_QWORD *)a5 + 3));
        if ( !i )
        {
          ++*((_DWORD *)j + 3);
          if ( (byte_180030D07 & 4) != 0 )
            McTemplateU0q_EventWriteTransfer(0, FoundScheduleSubscription, *((unsigned int *)j + 3));
          *((_DWORD *)j + 2) = 0;
          v25 = 1;
        }
      }
    }
    if ( !v25 )
    {
      if ( (byte_180030D07 & 4) != 0 )
        McTemplateU0jq_EventWriteTransfer(i, v12, (char *)a5 + 16, (unsigned int)a5);
      v48 = a5;
      v33 = v43;
      v49 = v43;
      v50 = 1;
      v34 = v24[2];
      if ( &v48 >= (struct CSchedule **)v34 || v24[1] > (struct _WNF_USER_SUBSCRIPTION *)&v48 )
      {
        if ( v34 == v24[3] )
          std::vector<_SCHEDULE_SUBSCRIPTION>::_Reserve(v24 + 1, v12);
        v35 = v24[2];
        *(_QWORD *)v35 = a5;
        *((_DWORD *)v35 + 2) = v33;
        *((_DWORD *)v35 + 3) = 1;
        v24[2] = (struct _WNF_USER_SUBSCRIPTION *)((char *)v24[2] + 16);
      }
      else
      {
        v41 = (char *)&v48 - (char *)v24[1];
        if ( v34 == v24[3] )
          std::vector<_SCHEDULE_SUBSCRIPTION>::_Reserve(v24 + 1, v12);
        *(_OWORD *)v24[2] = *(_OWORD *)((char *)v24[1] + (v41 & 0xFFFFFFFFFFFFFFF0uLL));
        v24[2] = (struct _WNF_USER_SUBSCRIPTION *)((char *)v24[2] + 16);
      }
    }
    v27 = (struct _WNF_STATE_NAME *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
    v30 = v27;
    if ( v27 )
    {
      *v27 = a3;
      if ( (byte_180030D07 & 8) != 0 )
        McGenEventWrite_EventWriteTransfer(v28, QueryWnfStateForSubscription, v29, 1, &v52);
      ThreadpoolWork = CreateThreadpoolWork(CScheduleMgr::QueryWNFStateWorker, v30, &ThreadpoolCallBackEnvironment);
      v32 = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        SubmitThreadpoolWork(ThreadpoolWork);
        CloseThreadpoolWork(v32);
      }
      else
      {
        operator delete(v30);
      }
    }
    LODWORD(v19) = (_DWORD)v47;
    *v47 = *v24;
  }
  else
  {
    if ( (byte_180030D07 & 8) != 0 )
      McTemplateU0jqqqq_EventWriteTransfer(
        (int)i,
        (int)NewWnfSubscription,
        (_DWORD)a5 + 16,
        (int)a5,
        v6.Data[0],
        v44.Data[1],
        a4);
    v52 = a5;
    v53 = a4 | 0x100000000LL;
    v43 = 0;
    v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RtlSubscribeWnfStateChangeNotification)(
            &v43,
            v6,
            a4,
            CScheduleMgr::BaseWnfCallback,
            &xmmword_180030BE0,
            0,
            0,
            0);
    v20 = v18;
    if ( v18 >= 0 )
    {
      v38 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      v51 = v38;
      if ( v38 )
      {
        v38[1] = 0;
        v38[3] = 0;
        *v38 = 0;
        v38[2] = 0;
        *v38 = v43;
        std::vector<_SCHEDULE_SUBSCRIPTION>::push_back(v38 + 1, &v52);
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          v39 = (_QWORD *)std::map<unsigned __int64,_EVENT_SUBSCRIPTION *>::operator[](&xmmword_180030BE0, &v45);
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
          {
            v42 = v51;
            RtlUnsubscribeWnfNotificationWaitForCompletion(*v51);
            *v42 = 0;
            LODWORD(v43) = -1073741823;
            v20 = -1073741823;
            v6.Data[0] = v44.Data[0];
            v7 = (int)v46;
            __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_18000729E);
            goto LABEL_32;
          }
        }
        *v39 = v38;
        v19 = v47;
        *v47 = (struct _WNF_USER_SUBSCRIPTION *)*v38;
        if ( (byte_180030D07 & 4) != 0 )
          McGenEventWrite_EventWriteTransfer(v19, NewSubscriptionSuccess, v40, 1, &v52);
      }
      else
      {
        if ( (byte_180030D07 & 0x10) != 0 )
          McTemplateU0jqq_EventWriteTransfer(
            v37,
            (int)FailedCreatingWnfSubscriptionNode,
            (_DWORD)a5 + 16,
            v6.Data[0],
            v10);
        RtlUnsubscribeWnfNotificationWaitForCompletion(v43);
        v20 = -1073741823;
      }
    }
    else
    {
      if ( (byte_180030D07 & 0x10) != 0 )
        McTemplateU0jqqq_EventWriteTransfer((int)v19, (int)FailedWnfSubscription, (_DWORD)a5 + 16, v6.Data[0], v10, v18);
      v20 = -1073741823;
    }
  }
LABEL_32:
  if ( (byte_180030D07 & 4) != 0 )
    McTemplateU0jqqq_EventWriteTransfer((int)v19, (int)CompletedSubscribeWnf, v7 + 16, v6.Data[0], v44.Data[1], v20);
  LeaveCriticalSection(&CriticalSection);
  return v20;
}

```

## disassembly

```asm
0x180006db0  push    rbx
0x180006db2  push    rsi
0x180006db3  push    rdi
0x180006db4  push    r12
0x180006db6  push    r13
0x180006db8  push    r14
0x180006dba  push    r15
0x180006dbc  sub     rsp, 0A0h
0x180006dc3  mov     rax, cs:__security_cookie
0x180006dca  xor     rax, rsp
0x180006dcd  mov     [rsp+0D8h+var_48], rax
0x180006dd5  mov     ebx, r9d
0x180006dd8  mov     dword ptr [rsp+0D8h+var_98], ebx
0x180006ddc  mov     rdi, r8
0x180006ddf  mov     [rsp+0D8h+var_78], rdx
0x180006de4  mov     [rsp+0D8h+var_90], r8
0x180006de9  mov     r13, [rsp+0D8h+arg_20]
0x180006df1  mov     [rsp+0D8h+var_80], r13
0x180006df6  mov     dword ptr [rsp+0D8h+var_88], edi
0x180006dfa  mov     rax, r8
0x180006dfd  shr     rax, 20h
0x180006e01  mov     dword ptr [rsp+0D8h+var_88+4], eax
0x180006e05  mov     r12, [rsp+0D8h+var_88]
0x180006e0a  mov     [rsp+0D8h+var_88], r12
0x180006e0f  test    rdx, rdx
0x180006e12  jz      loc_1800073FE
0x180006e18  test    r13, r13
0x180006e1b  jz      loc_1800073FE
0x180006e21  lea     rcx, CriticalSection; lpCriticalSection
0x180006e28  call    cs:__imp_EnterCriticalSection
0x180006e2e  mov     r15d, dword ptr [rsp+0D8h+var_90+4]
0x180006e33  test    cs:byte_180030D07, 4
0x180006e3a  jnz     loc_180007234
0x180006e40  mov     r10, qword ptr cs:xmmword_180030BE0
0x180006e47  mov     rdx, [r10+8]
0x180006e4b  mov     rcx, rdx
0x180006e4e  mov     rax, r10
0x180006e51  mov     r9, r10
0x180006e54  cmp     byte ptr [rdx+19h], 0
0x180006e58  jnz     short loc_180006E81
0x180006e5a  mov     r8, [rcx+20h]
0x180006e5e  cmp     r8, r12
0x180006e61  jb      loc_180006FD2
0x180006e67  cmp     byte ptr [r9+19h], 0
0x180006e6c  jz      short loc_180006E75
0x180006e6e  cmp     r12, r8
0x180006e71  cmovb   r9, rcx
0x180006e75  mov     rax, rcx
0x180006e78  mov     rcx, [rcx]
0x180006e7b  cmp     byte ptr [rcx+19h], 0
0x180006e7f  jz      short loc_180006E5A
0x180006e81  cmp     byte ptr [r9+19h], 0
0x180006e86  jz      loc_1800070A1
0x180006e8c  cmp     byte ptr [rdx+19h], 0
0x180006e90  jnz     short loc_180006EA6
0x180006e92  cmp     r12, [rdx+20h]
0x180006e96  jb      loc_1800070A9
0x180006e9c  mov     rdx, [rdx+10h]
0x180006ea0  cmp     byte ptr [rdx+19h], 0
0x180006ea4  jz      short loc_180006E92
0x180006ea6  xor     r14d, r14d
0x180006ea9  mov     r8d, r14d
0x180006eac  nop     dword ptr [rax+00h]
0x180006eb0  cmp     rax, r9
0x180006eb3  jz      short loc_180006EEA
0x180006eb5  inc     r8
0x180006eb8  cmp     [rax+19h], r14b
0x180006ebc  jnz     short loc_180006EB0
0x180006ebe  mov     rcx, [rax+10h]
0x180006ec2  cmp     [rcx+19h], r14b
0x180006ec6  jnz     loc_180006FAD
0x180006ecc  mov     rdx, [rcx]
0x180006ecf  cmp     [rdx+19h], r14b
0x180006ed3  jnz     loc_180006FCA
0x180006ed9  mov     rax, rdx
0x180006edc  mov     rcx, [rdx]
0x180006edf  mov     rdx, rcx
0x180006ee2  cmp     [rcx+19h], r14b
0x180006ee6  jnz     short loc_180006EB0
0x180006ee8  jmp     short loc_180006ED9
0x180006eea  test    r8, r8
0x180006eed  jnz     loc_180006FDB
0x180006ef3  test    cs:byte_180030D07, 8
0x180006efa  jnz     loc_180007255
0x180006f00  mov     [rsp+0D8h+var_58], r13
0x180006f08  mov     dword ptr [rsp+0D8h+var_50], ebx
0x180006f0f  mov     dword ptr [rsp+0D8h+var_50+4], 1
0x180006f1a  mov     [rsp+0D8h+var_98], r14
0x180006f1f  mov     [rsp+0D8h+var_A0], r14d
0x180006f24  mov     [rsp+0D8h+var_A8], r14d
0x180006f29  mov     [rsp+0D8h+var_B0], r14
0x180006f2e  lea     r14, xmmword_180030BE0
0x180006f35  mov     [rsp+0D8h+var_B8], r14
0x180006f3a  lea     r9, ?BaseWnfCallback@CScheduleMgr@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXQEAXK@Z; CScheduleMgr::BaseWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void * const,ulong)
0x180006f41  mov     r8d, ebx
0x180006f44  mov     rdx, rdi
0x180006f47  lea     rcx, [rsp+0D8h+var_98]
0x180006f4c  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180006f52  mov     esi, eax
0x180006f54  test    eax, eax
0x180006f56  jns     loc_18000718E
0x180006f5c  test    cs:byte_180030D07, 10h
0x180006f63  jnz     loc_1800072E7
0x180006f69  mov     esi, 0C0000001h
0x180006f6e  test    cs:byte_180030D07, 4
0x180006f75  jnz     loc_1800073DA
0x180006f7b  lea     rcx, CriticalSection; lpCriticalSection
0x180006f82  call    cs:__imp_LeaveCriticalSection
0x180006f88  mov     eax, esi
0x180006f8a  mov     rcx, [rsp+0D8h+var_48]
0x180006f92  xor     rcx, rsp; StackCookie
0x180006f95  call    __security_check_cookie
0x180006f9a  add     rsp, 0A0h
0x180006fa1  pop     r15
0x180006fa3  pop     r14
0x180006fa5  pop     r13
0x180006fa7  pop     r12
0x180006fa9  pop     rdi
0x180006faa  pop     rsi
0x180006fab  pop     rbx
0x180006fac  retn
0x180006fad  mov     rcx, [rax+8]
0x180006fb1  cmp     [rcx+19h], r14b
0x180006fb5  jnz     short loc_180006FCA
0x180006fb7  cmp     rax, [rcx+10h]
0x180006fbb  jnz     short loc_180006FCA
0x180006fbd  mov     rax, rcx
0x180006fc0  mov     rcx, [rcx+8]
0x180006fc4  cmp     [rcx+19h], r14b
0x180006fc8  jz      short loc_180006FB7
0x180006fca  mov     rax, rcx
0x180006fcd  jmp     loc_180006EB0
0x180006fd2  mov     rcx, [rcx+10h]
0x180006fd6  jmp     loc_180006E7B
0x180006fdb  mov     esi, r14d
0x180006fde  test    cs:byte_180030D07, 8
0x180006fe5  jnz     loc_180007308
0x180006feb  mov     rax, [r10+8]
0x180006fef  mov     rbx, r10
0x180006ff2  cmp     [rax+19h], sil
0x180006ff6  jnz     short loc_180007016
0x180006ff8  nop     dword ptr [rax+rax+00000000h]
0x180007000  cmp     [rax+20h], r12
0x180007004  jb      loc_180007098
0x18000700a  mov     rbx, rax
0x18000700d  mov     rax, [rax]
0x180007010  cmp     [rax+19h], sil
0x180007014  jz      short loc_180007000
0x180007016  cmp     rbx, r10
0x180007019  jz      loc_180007144
0x18000701f  cmp     r12, [rbx+20h]
0x180007023  jb      loc_180007144
0x180007029  mov     r15, [rbx+28h]
0x18000702d  xor     al, al
0x18000702f  mov     rbx, [r15+8]
0x180007033  cmp     rbx, [r15+10h]
0x180007037  jnz     loc_1800070D6
0x18000703d  test    al, al
0x18000703f  jz      loc_1800070EB
0x180007045  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000704c  mov     ecx, 8; unsigned __int64
0x180007051  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007056  mov     rbx, rax
0x180007059  test    rax, rax
0x18000705c  jz      short loc_1800070C6
0x18000705e  mov     [rax], r12
0x180007061  test    cs:byte_180030D07, 8
0x180007068  jnz     loc_1800073B6
0x18000706e  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180007075  mov     rdx, rbx; pv
0x180007078  lea     rcx, ?QueryWNFStateWorker@CScheduleMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000707f  call    cs:__imp_CreateThreadpoolWork
0x180007085  mov     r14, rax
0x180007088  test    rax, rax
0x18000708b  jnz     short loc_1800070B4
0x18000708d  mov     rcx, rbx
0x180007090  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007096  jmp     short loc_1800070C6
0x180007098  mov     rax, [rax+10h]
0x18000709c  jmp     loc_180007010
0x1800070a1  mov     rdx, [r9]
0x1800070a4  jmp     loc_180006E8C
0x1800070a9  mov     r9, rdx
0x1800070ac  mov     rdx, [rdx]
0x1800070af  jmp     loc_180006EA0
0x1800070b4  mov     rcx, r14; pwk
0x1800070b7  call    cs:__imp_SubmitThreadpoolWork
0x1800070bd  mov     rcx, r14; pwk
0x1800070c0  call    cs:__imp_CloseThreadpoolWork
0x1800070c6  mov     rax, [r15]
0x1800070c9  mov     rcx, [rsp+0D8h+var_78]
0x1800070ce  mov     [rcx], rax
0x1800070d1  jmp     loc_180006F6E
0x1800070d6  mov     rdx, [rbx]
0x1800070d9  cmp     rdx, r13
0x1800070dc  jz      loc_180007334
0x1800070e2  add     rbx, 10h
0x1800070e6  jmp     loc_180007033
0x1800070eb  test    cs:byte_180030D07, 4
0x1800070f2  jnz     loc_180007375
0x1800070f8  mov     [rsp+0D8h+var_70], r13
0x1800070fd  mov     ebx, dword ptr [rsp+0D8h+var_98]
0x180007101  mov     [rsp+0D8h+var_68], ebx
0x180007105  mov     [rsp+0D8h+var_64], 1
0x18000710d  mov     rax, [r15+10h]
0x180007111  lea     rcx, [rsp+0D8h+var_70]
0x180007116  cmp     rcx, rax
0x180007119  jb      loc_180007386
0x18000711f  cmp     rax, [r15+18h]
0x180007123  jz      loc_1800073A8
0x180007129  mov     rax, [r15+10h]
0x18000712d  mov     [rax], r13
0x180007130  mov     [rax+8], ebx
0x180007133  mov     dword ptr [rax+0Ch], 1
0x18000713a  add     qword ptr [r15+10h], 10h
0x18000713f  jmp     loc_180007045
0x180007144  mov     [rsp+0D8h+var_58], r12
0x18000714c  mov     [rsp+0D8h+var_50], r14
0x180007154  lea     rdx, [rsp+0D8h+var_58]
0x18000715c  lea     r14, xmmword_180030BE0
0x180007163  mov     rcx, r14
0x180007166  call    ??$_Buynode@U?$pair@_KPEAU_EVENT_SUBSCRIPTION@@@std@@@?$_Tree_buy@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@1@$$QEAU?$pair@_KPEAU_EVENT_SUBSCRIPTION@@@1@@Z; std::_Tree_buy<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>::_Buynode<std::pair<unsigned __int64,_EVENT_SUBSCRIPTION *>>(std::pair<unsigned __int64,_EVENT_SUBSCRIPTION *> &&)
0x18000716b  lea     r9, [rax+20h]
0x18000716f  mov     [rsp+0D8h+var_B8], rax
0x180007174  mov     r8, rbx
0x180007177  lea     rdx, [rsp+0D8h+var_80]
0x18000717c  mov     rcx, r14
0x18000717f  call    ??$_Insert_hint@AEAU?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@_KPEAU_EVENT_SUBSCRIPTION@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@std@@@std@@@1@AEAU?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::_Insert_hint<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *> &,std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>>>,std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *> &,std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *)
0x180007184  mov     rbx, [rsp+0D8h+var_80]
0x180007189  jmp     loc_180007029
0x18000718e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007195  mov     ecx, 20h ; ' '; unsigned __int64
0x18000719a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000719f  mov     rbx, rax
0x1800071a2  mov     [rsp+0D8h+var_60], rax
0x1800071a7  test    rax, rax
0x1800071aa  jz      loc_1800072B1
0x1800071b0  xor     eax, eax
0x1800071b2  mov     [rbx+8], rax
0x1800071b6  mov     [rbx+18h], rax
0x1800071ba  mov     [rbx], rax
0x1800071bd  mov     [rbx+10h], rax
0x1800071c1  mov     rcx, [rsp+0D8h+var_98]
0x1800071c6  mov     [rbx], rcx
0x1800071c9  lea     rdx, [rsp+0D8h+var_58]
0x1800071d1  lea     rcx, [rbx+8]
0x1800071d5  call    ?push_back@?$vector@U_SCHEDULE_SUBSCRIPTION@@V?$allocator@U_SCHEDULE_SUBSCRIPTION@@@std@@@std@@QEAAXAEBU_SCHEDULE_SUBSCRIPTION@@@Z; std::vector<_SCHEDULE_SUBSCRIPTION>::push_back(_SCHEDULE_SUBSCRIPTION const &)
0x1800071da  nop
0x1800071db  lea     rdx, [rsp+0D8h+var_88]
0x1800071e0  mov     rcx, r14
0x1800071e3  call    ??A?$map@_KPEAU_EVENT_SUBSCRIPTION@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@3@@std@@QEAAAEAPEAU_EVENT_SUBSCRIPTION@@AEB_K@Z; std::map<unsigned __int64,_EVENT_SUBSCRIPTION *>::operator[](unsigned __int64 const &)
0x1800071e8  mov     [rax], rbx
0x1800071eb  mov     rax, [rbx]
0x1800071ee  mov     rcx, [rsp+0D8h+var_78]
0x1800071f3  mov     [rcx], rax
0x1800071f6  test    cs:byte_180030D07, 4
0x1800071fd  jnz     short loc_18000727A
0x1800071ff  jmp     loc_180006F6E
0x180007204  lea     rbx, [rsp+0D8h+var_70]
0x180007209  sub     rbx, [r15+8]
0x18000720d  cmp     rax, [r15+18h]
0x180007211  jz      loc_18000739A
0x180007217  and     rbx, 0FFFFFFFFFFFFFFF0h
0x18000721b  mov     rax, [r15+8]
0x18000721f  mov     rcx, [r15+10h]
0x180007223  movups  xmm0, xmmword ptr [rbx+rax]
0x180007227  movups  xmmword ptr [rcx], xmm0
0x18000722a  add     qword ptr [r15+10h], 10h
0x18000722f  jmp     loc_180007045
0x180007234  lea     r8, [r13+10h]
0x180007238  mov     dword ptr [rsp+0D8h+var_B0], ebx
0x18000723c  mov     dword ptr [rsp+0D8h+var_B8], r15d
0x180007241  mov     r9d, edi
0x180007244  lea     rdx, SubscribeWnf
0x18000724b  call    McTemplateU0jqqq_EventWriteTransfer
0x180007250  jmp     loc_180006E40
0x180007255  mov     r9d, r13d
0x180007258  lea     r8, [r13+10h]
0x18000725c  mov     [rsp+0D8h+var_A8], ebx
0x180007260  mov     dword ptr [rsp+0D8h+var_B0], r15d
0x180007265  mov     dword ptr [rsp+0D8h+var_B8], edi
0x180007269  lea     rdx, NewWnfSubscription
0x180007270  call    McTemplateU0jqqqq_EventWriteTransfer
0x180007275  jmp     loc_180006F00
0x18000727a  lea     rax, [rsp+0D8h+var_58]
0x180007282  mov     [rsp+0D8h+var_B8], rax
0x180007287  mov     r9d, 1
0x18000728d  lea     rdx, NewSubscriptionSuccess
0x180007294  call    McGenEventWrite_EventWriteTransfer
0x180007299  jmp     loc_1800071FF
0x18000729e  mov     esi, dword ptr [rsp+0D8h+var_98]
0x1800072a2  mov     rdi, [rsp+0D8h+var_90]
0x1800072a7  mov     r13, [rsp+0D8h+var_80]
0x1800072ac  jmp     loc_180006F6E
0x1800072b1  test    cs:byte_180030D07, 10h
0x1800072b8  jz      short loc_1800072D2
0x1800072ba  lea     r8, [r13+10h]
0x1800072be  mov     dword ptr [rsp+0D8h+var_B8], r15d
0x1800072c3  mov     r9d, edi
0x1800072c6  lea     rdx, FailedCreatingWnfSubscriptionNode
  ... truncated ...
```
