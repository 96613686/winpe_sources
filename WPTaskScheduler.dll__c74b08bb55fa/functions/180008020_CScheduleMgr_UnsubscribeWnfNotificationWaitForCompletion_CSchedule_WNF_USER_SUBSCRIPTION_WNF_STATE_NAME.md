# CScheduleMgr::UnsubscribeWnfNotificationWaitForCompletion(CSchedule *,_WNF_USER_SUBSCRIPTION *,_WNF_STATE_NAME)

- ea: `0x180008020`
- end: `0x1800085b9`
- name: `?UnsubscribeWnfNotificationWaitForCompletion@CScheduleMgr@@QEAAJPEAVCSchedule@@PEAU_WNF_USER_SUBSCRIPTION@@U_WNF_STATE_NAME@@@Z`
- size: `1433`
- prototype: `__int64 __fastcall(CScheduleMgr *__hidden this, struct CSchedule *, struct _WNF_USER_SUBSCRIPTION *, struct _WNF_STATE_NAME)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180007f00`

## callees

- `0x180008020`
- `0x1800085c0`
- `0x180008bf8`
- `0x18000e970`
- `0x18000eeb0`
- `0x18000f0c0`
- `0x180018560`
- `0x180019a9c`
- `0x180019b28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800083e5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008406`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800083e5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008406`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180008308`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180008308`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800082ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800082ea`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800082ff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800082ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008077`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008262`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008262`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000842e`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000842e`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::UnsubscribeWnfNotificationWaitForCompletion(
        CScheduleMgr *this,
        struct CSchedule *a2,
        struct _WNF_USER_SUBSCRIPTION *a3,
        struct _WNF_STATE_NAME a4)
{
  ULONG v4; // edi
  char v5; // bl
  int v8; // ecx
  char v9; // bp
  struct CSchedule *v10; // rax
  struct CSchedule *v11; // r9
  __int64 v12; // r10
  __int64 v13; // rcx
  char v14; // si
  unsigned __int64 v15; // rdx
  struct CSchedule *i; // rcx
  __int64 v17; // r8
  struct CSchedule **v18; // rdx
  __int64 v19; // rbx
  __int64 v20; // r14
  __int64 v21; // rbx
  int v22; // r15d
  __int64 v23; // rax
  __int64 v24; // r8
  unsigned int v25; // ebp
  char v26; // si
  struct CSchedule *j; // rax
  __int128 v28; // xmm0
  __int64 v29; // r8
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v32; // rbx
  __int64 *v33; // rbx
  __int64 *v34; // rsi
  __int64 *v35; // rdx
  __int64 *v36; // rcx
  unsigned __int64 v37; // r8
  __int64 *v38; // r8
  __int64 *k; // rax
  __int64 *v40; // rcx
  void *v41; // rcx
  unsigned __int64 *v42; // rax
  __int64 *v43; // rdx
  _QWORD v44[2]; // [rsp+40h] [rbp-48h] BYREF
  CScheduleMgr *v45; // [rsp+90h] [rbp+8h] BYREF
  struct _WNF_USER_SUBSCRIPTION *v46; // [rsp+A0h] [rbp+18h] BYREF
  struct _WNF_STATE_NAME v47; // [rsp+A8h] [rbp+20h]

  v47 = a4;
  v46 = a3;
  v45 = this;
  v4 = a4.Data[0];
  v5 = (char)a3;
  if ( !a3 || !a2 )
    return 3221225473LL;
  EnterCriticalSection(&CriticalSection);
  v9 = v47.Data[1];
  if ( (byte_180030D07 & 8) != 0 )
    McTemplateU0jqqqq_EventWriteTransfer(
      v8,
      (unsigned int)UnsubscribeWnf,
      (_DWORD)a2 + 16,
      (_DWORD)a2,
      v4,
      v47.Data[1],
      v5);
  v10 = (struct CSchedule *)xmmword_180030BE0;
  v11 = (struct CSchedule *)xmmword_180030BE0;
  v12 = *(_QWORD *)(xmmword_180030BE0 + 8);
  v13 = v12;
  v14 = *(_BYTE *)(v12 + 25);
  if ( !v14 )
  {
    do
    {
      v15 = *(_QWORD *)(v13 + 32);
      if ( v15 < *(_QWORD *)&a4 )
      {
        v13 = *(_QWORD *)(v13 + 16);
      }
      else
      {
        if ( *((_BYTE *)v11 + 25) && *(_QWORD *)&a4 < v15 )
          v11 = (struct CSchedule *)v13;
        v10 = (struct CSchedule *)v13;
        v13 = *(_QWORD *)v13;
      }
    }
    while ( !*(_BYTE *)(v13 + 25) );
  }
  if ( *((_BYTE *)v11 + 25) )
    i = *(struct CSchedule **)(xmmword_180030BE0 + 8);
  else
    i = *(struct CSchedule **)v11;
  while ( !*((_BYTE *)i + 25) )
  {
    if ( *(unsigned __int64 *)&a4 < *((_QWORD *)i + 4) )
    {
      v11 = i;
      i = *(struct CSchedule **)i;
    }
    else
    {
      i = (struct CSchedule *)*((_QWORD *)i + 2);
    }
  }
  v17 = 0;
  while ( v10 != v11 )
  {
    ++v17;
    if ( !*((_BYTE *)v10 + 25) )
    {
      i = (struct CSchedule *)*((_QWORD *)v10 + 2);
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (struct CSchedule *)*((_QWORD *)v10 + 1); !*((_BYTE *)i + 25); i = (struct CSchedule *)*((_QWORD *)i + 1) )
        {
          if ( v10 != *((struct CSchedule **)i + 2) )
            break;
          v10 = i;
        }
LABEL_58:
        v10 = i;
      }
      else
      {
        v18 = *(struct CSchedule ***)i;
        if ( *(_BYTE *)(*(_QWORD *)i + 25LL) )
          goto LABEL_58;
        do
        {
          i = *v18;
          v10 = (struct CSchedule *)v18;
          v18 = (struct CSchedule **)i;
        }
        while ( !*((_BYTE *)i + 25) );
      }
    }
  }
  if ( !v17 )
  {
    v22 = (_DWORD)a2 + 16;
    if ( (byte_180030D07 & 0x10) != 0 )
    {
      v43 = ErrorNoWnfSubscription;
      goto LABEL_106;
    }
LABEL_102:
    v25 = -1073741823;
    goto LABEL_50;
  }
  v19 = xmmword_180030BE0;
  if ( !v14 )
  {
    do
    {
      if ( *(_QWORD *)(v12 + 32) < *(unsigned __int64 *)&a4 )
      {
        v12 = *(_QWORD *)(v12 + 16);
      }
      else
      {
        v19 = v12;
        v12 = *(_QWORD *)v12;
      }
    }
    while ( !*(_BYTE *)(v12 + 25) );
  }
  if ( v19 == (_QWORD)xmmword_180030BE0 || *(unsigned __int64 *)&a4 < *(_QWORD *)(v19 + 32) )
  {
    v44[0] = a4;
    v44[1] = 0;
    v42 = (unsigned __int64 *)std::_Tree_buy<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>::_Buynode<std::pair<unsigned __int64,_EVENT_SUBSCRIPTION *>>(
                                &xmmword_180030BE0,
                                v44);
    std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::_Insert_hint<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *> &,std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *>(
      (__int64)&xmmword_180030BE0,
      &v45,
      v19,
      v42 + 4,
      v42);
    v19 = (__int64)v45;
  }
  v20 = *(_QWORD *)(v19 + 40);
  v21 = *(_QWORD *)(v20 + 8);
  while ( 2 )
  {
    if ( v21 == *(_QWORD *)(v20 + 16) )
    {
      v22 = (_DWORD)a2 + 16;
      if ( (byte_180030D07 & 0x10) != 0 )
      {
        v43 = ErrorScheduleNotSubscribed;
LABEL_106:
        McTemplateU0jqq_EventWriteTransfer((_DWORD)i, (_DWORD)v43, v22, v4, v9);
        goto LABEL_102;
      }
      goto LABEL_102;
    }
    i = *(struct CSchedule **)v21;
    if ( *(struct CSchedule **)v21 != a2 )
      goto LABEL_54;
    v22 = (_DWORD)a2 + 16;
    v23 = *((_QWORD *)i + 2) - *((_QWORD *)a2 + 2);
    if ( !v23 )
      v23 = *((_QWORD *)i + 3) - *((_QWORD *)a2 + 3);
    if ( v23 )
    {
LABEL_54:
      v21 += 16;
      continue;
    }
    break;
  }
  v24 = *(unsigned int *)(v21 + 12);
  v25 = 0;
  if ( (_DWORD)v24 )
  {
    v24 = (unsigned int)(v24 - 1);
    *(_DWORD *)(v21 + 12) = v24;
  }
  if ( (byte_180030D07 & 8) != 0 )
    McTemplateU0q_EventWriteTransfer(i, WnfReferenceCount, v24);
  if ( !*(_DWORD *)(v21 + 12) )
  {
    v26 = v47.Data[1];
    if ( (byte_180030D07 & 8) != 0 )
      McTemplateU0jqqq_EventWriteTransfer(
        (_DWORD)i,
        (unsigned int)ScheduleNoLongerSubscribing,
        (_DWORD)a2 + 16,
        (_DWORD)a2,
        v4,
        v47.Data[1]);
    i = *(struct CSchedule **)(v20 + 16);
    for ( j = (struct CSchedule *)(v21 + 16); j != i; *(_OWORD *)(v21 - 16) = v28 )
    {
      v28 = *(_OWORD *)j;
      j = (struct CSchedule *)((char *)j + 16);
      v21 += 16;
    }
    *(_QWORD *)(v20 + 16) -= 16LL;
    v29 = (__int64)(*(_QWORD *)(v20 + 16) - *(_QWORD *)(v20 + 8)) >> 4;
    if ( v29 )
    {
      if ( (byte_180030D07 & 8) != 0 )
        McTemplateU0q_EventWriteTransfer(i, RemainingSubscribers, v29);
      goto LABEL_50;
    }
    if ( (byte_180030D07 & 8) != 0 )
      McTemplateU0jqqq_EventWriteTransfer(
        (_DWORD)i,
        (unsigned int)WNFEventNoLongerNeeded,
        (_DWORD)a2 + 16,
        (_DWORD)a2,
        v4,
        v26);
    ThreadpoolWork = CreateThreadpoolWork(
                       CScheduleMgr::UnsubscribeWnfNotificationWaitForCompletionWorker,
                       *(PVOID *)v20,
                       &ThreadpoolCallBackEnvironment);
    v32 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v32);
    }
    else
    {
      v25 = RtlUnsubscribeWnfNotificationWaitForCompletion(v46);
    }
    v33 = (__int64 *)xmmword_180030BE0;
    v34 = (__int64 *)xmmword_180030BE0;
    v35 = *(__int64 **)(xmmword_180030BE0 + 8);
    v36 = v35;
    while ( !*((_BYTE *)v36 + 25) )
    {
      v37 = v36[4];
      if ( v37 < *(_QWORD *)&a4 )
      {
        v36 = (__int64 *)v36[2];
      }
      else
      {
        if ( *((_BYTE *)v34 + 25) && *(_QWORD *)&a4 < v37 )
          v34 = v36;
        v33 = v36;
        v36 = (__int64 *)*v36;
      }
    }
    if ( !*((_BYTE *)v34 + 25) )
      v35 = (__int64 *)*v34;
    while ( !*((_BYTE *)v35 + 25) )
    {
      if ( *(unsigned __int64 *)&a4 >= v35[4] )
      {
        v35 = (__int64 *)v35[2];
      }
      else
      {
        v34 = v35;
        v35 = (__int64 *)*v35;
      }
    }
    if ( v33 != *(__int64 **)xmmword_180030BE0 || v34 != (__int64 *)xmmword_180030BE0 )
    {
      while ( 2 )
      {
        if ( v33 == v34 )
          goto LABEL_86;
        v38 = v33;
        if ( *((_BYTE *)v33 + 25) )
          goto LABEL_84;
        k = (__int64 *)v33[2];
        if ( *((_BYTE *)k + 25) )
        {
          for ( k = (__int64 *)v33[1]; !*((_BYTE *)k + 25); k = (__int64 *)k[1] )
          {
            if ( v33 != (__int64 *)k[2] )
              break;
            v33 = k;
          }
        }
        else
        {
          v40 = (__int64 *)*k;
          if ( !*(_BYTE *)(*k + 25) )
          {
            do
            {
              v33 = v40;
              v40 = (__int64 *)*v40;
            }
            while ( !*((_BYTE *)v40 + 25) );
            goto LABEL_84;
          }
        }
        v33 = k;
LABEL_84:
        std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::erase(
          &xmmword_180030BE0,
          &v46,
          v38);
        continue;
      }
    }
    std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(&xmmword_180030BE0);
LABEL_86:
    v41 = *(void **)(v20 + 8);
    if ( v41 )
    {
      operator delete(v41);
      *(_QWORD *)(v20 + 8) = 0;
      *(_QWORD *)(v20 + 16) = 0;
      *(_QWORD *)(v20 + 24) = 0;
    }
    operator delete((void *)v20);
  }
LABEL_50:
  if ( (byte_180030D07 & 4) != 0 )
    McTemplateU0jqqq_EventWriteTransfer((_DWORD)i, (unsigned int)CompletedUnsubscribeWnf, v22, v4, v47.Data[1], v25);
  LeaveCriticalSection(&CriticalSection);
  return v25;
}

```

## disassembly

```asm
0x180008020  mov     rax, rsp
0x180008023  mov     [rax+20h], r9
0x180008027  mov     [rax+18h], r8
0x18000802b  mov     [rax+8], rcx
0x18000802f  push    rbx
0x180008030  push    rbp
0x180008031  push    rdi
0x180008032  push    r13
0x180008034  sub     rsp, 68h
0x180008038  mov     rdi, r9
0x18000803b  mov     rbx, r8
0x18000803e  mov     r13, rdx
0x180008041  test    r8, r8
0x180008044  jz      loc_18000843B
0x18000804a  test    rdx, rdx
0x18000804d  jz      loc_18000843B
0x180008053  mov     [rax+10h], rsi
0x180008057  lea     rcx, CriticalSection; lpCriticalSection
0x18000805e  mov     [rax-28h], r12
0x180008062  mov     r12, r9
0x180008065  mov     rax, 0FFFFFFFF00000000h
0x18000806f  and     r12, rax
0x180008072  mov     eax, edi
0x180008074  or      r12, rax
0x180008077  call    cs:__imp_EnterCriticalSection
0x18000807d  test    cs:byte_180030D07, 8
0x180008084  mov     ebp, [rsp+88h+arg_1C]
0x18000808b  jnz     loc_1800084DA
0x180008091  mov     r11, qword ptr cs:xmmword_180030BE0
0x180008098  mov     rax, r11
0x18000809b  mov     r9, r11
0x18000809e  mov     r10, [r11+8]
0x1800080a2  mov     rcx, r10
0x1800080a5  movzx   esi, byte ptr [r10+19h]
0x1800080aa  test    sil, sil
0x1800080ad  jnz     short loc_1800080D6
0x1800080af  mov     rdx, [rcx+20h]
0x1800080b3  cmp     rdx, r12
0x1800080b6  jb      loc_1800082B0
0x1800080bc  cmp     byte ptr [r9+19h], 0
0x1800080c1  jz      short loc_1800080CA
0x1800080c3  cmp     r12, rdx
0x1800080c6  cmovb   r9, rcx
0x1800080ca  mov     rax, rcx
0x1800080cd  mov     rcx, [rcx]
0x1800080d0  cmp     byte ptr [rcx+19h], 0
0x1800080d4  jz      short loc_1800080AF
0x1800080d6  cmp     byte ptr [r9+19h], 0
0x1800080db  jz      loc_1800082B9
0x1800080e1  mov     rcx, r10
0x1800080e4  cmp     byte ptr [rcx+19h], 0
0x1800080e8  jnz     short loc_1800080FE
0x1800080ea  cmp     r12, [rcx+20h]
0x1800080ee  jb      loc_1800082C1
0x1800080f4  mov     rcx, [rcx+10h]
0x1800080f8  cmp     byte ptr [rcx+19h], 0
0x1800080fc  jz      short loc_1800080EA
0x1800080fe  xor     r8d, r8d
0x180008101  cmp     rax, r9
0x180008104  jz      short loc_18000813B
0x180008106  inc     r8
0x180008109  cmp     byte ptr [rax+19h], 0
0x18000810d  jnz     short loc_180008101
0x18000810f  mov     rcx, [rax+10h]
0x180008113  cmp     byte ptr [rcx+19h], 0
0x180008117  jnz     loc_18000828B
0x18000811d  mov     rdx, [rcx]
0x180008120  cmp     byte ptr [rdx+19h], 0
0x180008124  jnz     loc_1800082A8
0x18000812a  mov     rcx, [rdx]
0x18000812d  mov     rax, rdx
0x180008130  mov     rdx, rcx
0x180008133  cmp     byte ptr [rcx+19h], 0
0x180008137  jnz     short loc_180008101
0x180008139  jmp     short loc_18000812A
0x18000813b  mov     [rsp+88h+var_30], r14
0x180008140  mov     [rsp+88h+var_38], r15
0x180008145  test    r8, r8
0x180008148  jz      loc_1800084BF
0x18000814e  mov     rbx, r11
0x180008151  test    sil, sil
0x180008154  jnz     short loc_18000816D
0x180008156  cmp     [r10+20h], r12
0x18000815a  jb      loc_180008279
0x180008160  mov     rbx, r10
0x180008163  mov     r10, [r10]
0x180008166  cmp     byte ptr [r10+19h], 0
0x18000816b  jz      short loc_180008156
0x18000816d  cmp     rbx, r11
0x180008170  jz      loc_18000844E
0x180008176  cmp     r12, [rbx+20h]
0x18000817a  jb      loc_18000844E
0x180008180  mov     r14, [rbx+28h]
0x180008184  mov     rbx, [r14+8]
0x180008188  cmp     rbx, [r14+10h]
0x18000818c  jz      loc_18000855E
0x180008192  mov     rcx, [rbx]
0x180008195  cmp     rcx, r13
0x180008198  jnz     loc_180008282
0x18000819e  mov     rax, [rcx+10h]
0x1800081a2  lea     r15, [r13+10h]
0x1800081a6  sub     rax, [r15]
0x1800081a9  jnz     short loc_1800081B3
0x1800081ab  mov     rax, [rcx+18h]
0x1800081af  sub     rax, [r15+8]
0x1800081b3  test    rax, rax
0x1800081b6  jnz     loc_180008282
0x1800081bc  mov     r8d, [rbx+0Ch]
0x1800081c0  xor     ebp, ebp
0x1800081c2  test    r8d, r8d
0x1800081c5  jz      short loc_1800081CE
0x1800081c7  dec     r8d
0x1800081ca  mov     [rbx+0Ch], r8d
0x1800081ce  test    cs:byte_180030D07, 8
0x1800081d5  jnz     loc_1800084FE
0x1800081db  cmp     [rbx+0Ch], ebp
0x1800081de  jnz     short loc_18000823C
0x1800081e0  test    cs:byte_180030D07, 8
0x1800081e7  mov     esi, [rsp+88h+arg_1C]
0x1800081ee  jnz     loc_18000850F
0x1800081f4  mov     rcx, [r14+10h]
0x1800081f8  lea     rax, [rbx+10h]
0x1800081fc  cmp     rax, rcx
0x1800081ff  jz      short loc_180008215
0x180008201  movups  xmm0, xmmword ptr [rax]
0x180008204  add     rax, 10h
0x180008208  lea     rbx, [rbx+10h]
0x18000820c  movups  xmmword ptr [rbx-10h], xmm0
0x180008210  cmp     rax, rcx
0x180008213  jnz     short loc_180008201
0x180008215  add     qword ptr [r14+10h], 0FFFFFFFFFFFFFFF0h
0x18000821a  mov     r8, [r14+10h]
0x18000821e  sub     r8, [r14+8]
0x180008222  sar     r8, 4
0x180008226  test    r8, r8
0x180008229  jz      loc_1800082CC
0x18000822f  test    cs:byte_180030D07, 8
0x180008236  jnz     loc_18000854D
0x18000823c  test    cs:byte_180030D07, 4
0x180008243  mov     r14, [rsp+88h+var_30]
0x180008248  mov     r12, [rsp+88h+var_28]
0x18000824d  mov     rsi, [rsp+88h+arg_8]
0x180008255  jnz     loc_180008593
0x18000825b  lea     rcx, CriticalSection; lpCriticalSection
0x180008262  call    cs:__imp_LeaveCriticalSection
0x180008268  mov     r15, [rsp+88h+var_38]
0x18000826d  mov     eax, ebp
0x18000826f  add     rsp, 68h
0x180008273  pop     r13
0x180008275  pop     rdi
0x180008276  pop     rbp
0x180008277  pop     rbx
0x180008278  retn
0x180008279  mov     r10, [r10+10h]
0x18000827d  jmp     loc_180008166
0x180008282  add     rbx, 10h
0x180008286  jmp     loc_180008188
0x18000828b  mov     rcx, [rax+8]
0x18000828f  cmp     byte ptr [rcx+19h], 0
0x180008293  jnz     short loc_1800082A8
0x180008295  cmp     rax, [rcx+10h]
0x180008299  jnz     short loc_1800082A8
0x18000829b  mov     rax, rcx
0x18000829e  mov     rcx, [rcx+8]
0x1800082a2  cmp     byte ptr [rcx+19h], 0
0x1800082a6  jz      short loc_180008295
0x1800082a8  mov     rax, rcx
0x1800082ab  jmp     loc_180008101
0x1800082b0  mov     rcx, [rcx+10h]
0x1800082b4  jmp     loc_1800080D0
0x1800082b9  mov     rcx, [r9]
0x1800082bc  jmp     loc_1800080E4
0x1800082c1  mov     r9, rcx
0x1800082c4  mov     rcx, [rcx]
0x1800082c7  jmp     loc_1800080F8
0x1800082cc  test    cs:byte_180030D07, 8
0x1800082d3  jnz     loc_18000852E
0x1800082d9  mov     rdx, [r14]; pv
0x1800082dc  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1800082e3  lea     rcx, ?UnsubscribeWnfNotificationWaitForCompletionWorker@CScheduleMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800082ea  call    cs:__imp_CreateThreadpoolWork
0x1800082f0  mov     rbx, rax
0x1800082f3  test    rax, rax
0x1800082f6  jz      loc_180008426
0x1800082fc  mov     rcx, rax; pwk
0x1800082ff  call    cs:__imp_SubmitThreadpoolWork
0x180008305  mov     rcx, rbx; pwk
0x180008308  call    cs:__imp_CloseThreadpoolWork
0x18000830e  mov     r9, qword ptr cs:xmmword_180030BE0
0x180008315  mov     rbx, r9
0x180008318  mov     rsi, r9
0x18000831b  mov     rdx, [r9+8]
0x18000831f  mov     rcx, rdx
0x180008322  cmp     byte ptr [rdx+19h], 0
0x180008326  jnz     short loc_180008353
0x180008328  nop     dword ptr [rax+rax+00000000h]
0x180008330  mov     r8, [rcx+20h]
0x180008334  cmp     r8, r12
0x180008337  jb      loc_180008445
0x18000833d  cmp     byte ptr [rsi+19h], 0
0x180008341  jnz     loc_18000841A
0x180008347  mov     rbx, rcx
0x18000834a  mov     rcx, [rcx]
0x18000834d  cmp     byte ptr [rcx+19h], 0
0x180008351  jz      short loc_180008330
0x180008353  cmp     byte ptr [rsi+19h], 0
0x180008357  jnz     short loc_18000835C
0x180008359  mov     rdx, [rsi]
0x18000835c  cmp     byte ptr [rdx+19h], 0
0x180008360  jnz     short loc_180008378
0x180008362  cmp     r12, [rdx+20h]
0x180008366  jnb     loc_180008411
0x18000836c  mov     rsi, rdx
0x18000836f  mov     rdx, [rdx]
0x180008372  cmp     byte ptr [rdx+19h], 0
0x180008376  jz      short loc_180008362
0x180008378  cmp     rbx, [r9]
0x18000837b  jnz     short loc_180008382
0x18000837d  cmp     rsi, r9
0x180008380  jz      short loc_1800083D0
0x180008382  cmp     rbx, rsi
0x180008385  jz      short loc_1800083DC
0x180008387  cmp     byte ptr [rbx+19h], 0
0x18000838b  mov     r8, rbx
0x18000838e  jnz     short loc_1800083BA
0x180008390  mov     rax, [rbx+10h]
0x180008394  cmp     byte ptr [rax+19h], 0
0x180008398  jnz     loc_18000849A
0x18000839e  mov     rcx, [rax]
0x1800083a1  cmp     byte ptr [rcx+19h], 0
0x1800083a5  jnz     loc_1800084B7
0x1800083ab  mov     rax, [rcx]
0x1800083ae  mov     rbx, rcx
0x1800083b1  mov     rcx, rax
0x1800083b4  cmp     byte ptr [rax+19h], 0
0x1800083b8  jz      short loc_1800083AB
0x1800083ba  lea     rdx, [rsp+88h+arg_10]
0x1800083c2  lea     rcx, xmmword_180030BE0
0x1800083c9  call    ?erase@?$_Tree@V?$_Tmap_traits@_KPEAU_EVENT_SUBSCRIPTION@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>>>)
0x1800083ce  jmp     short loc_180008382
0x1800083d0  lea     rcx, xmmword_180030BE0
0x1800083d7  call    ?clear@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVPDC_ENTRY@@Uguidcomp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(void)
0x1800083dc  mov     rcx, [r14+8]
0x1800083e0  test    rcx, rcx
0x1800083e3  jz      short loc_180008403
0x1800083e5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800083eb  mov     qword ptr [r14+8], 0
0x1800083f3  mov     qword ptr [r14+10h], 0
0x1800083fb  mov     qword ptr [r14+18h], 0
0x180008403  mov     rcx, r14
0x180008406  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000840c  jmp     loc_18000823C
0x180008411  mov     rdx, [rdx+10h]
0x180008415  jmp     loc_180008372
0x18000841a  cmp     r12, r8
0x18000841d  cmovb   rsi, rcx
0x180008421  jmp     loc_180008347
0x180008426  mov     rcx, [rsp+88h+arg_10]
0x18000842e  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180008434  mov     ebp, eax
0x180008436  jmp     loc_18000830E
0x18000843b  mov     eax, 0C0000001h
0x180008440  jmp     loc_18000826F
0x180008445  mov     rcx, [rcx+10h]
0x180008449  jmp     loc_18000834D
0x18000844e  lea     rdx, [rsp+88h+var_48]
0x180008453  mov     [rsp+88h+var_48], r12
0x180008458  lea     rcx, xmmword_180030BE0
0x18000845f  mov     [rsp+88h+var_40], 0
0x180008468  call    ??$_Buynode@U?$pair@_KPEAU_EVENT_SUBSCRIPTION@@@std@@@?$_Tree_buy@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@1@$$QEAU?$pair@_KPEAU_EVENT_SUBSCRIPTION@@@1@@Z; std::_Tree_buy<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>::_Buynode<std::pair<unsigned __int64,_EVENT_SUBSCRIPTION *>>(std::pair<unsigned __int64,_EVENT_SUBSCRIPTION *> &&)
0x18000846d  mov     r8, rbx
0x180008470  mov     [rsp+88h+var_68], rax
0x180008475  lea     rdx, [rsp+88h+arg_0]
0x18000847d  lea     rcx, xmmword_180030BE0
0x180008484  lea     r9, [rax+20h]
0x180008488  call    ??$_Insert_hint@AEAU?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@_KPEAU_EVENT_SUBSCRIPTION@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@std@@@std@@@1@AEAU?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::_Insert_hint<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *> &,std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>>>,std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *> &,std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *)
0x18000848d  mov     rbx, [rsp+88h+arg_0]
0x180008495  jmp     loc_180008180
0x18000849a  mov     rax, [rbx+8]
0x18000849e  cmp     byte ptr [rax+19h], 0
0x1800084a2  jnz     short loc_1800084B7
0x1800084a4  cmp     rbx, [rax+10h]
0x1800084a8  jnz     short loc_1800084B7
0x1800084aa  mov     rbx, rax
0x1800084ad  mov     rax, [rax+8]
0x1800084b1  cmp     byte ptr [rax+19h], 0
0x1800084b5  jz      short loc_1800084A4
0x1800084b7  mov     rbx, rax
0x1800084ba  jmp     loc_1800083BA
0x1800084bf  test    cs:byte_180030D07, 10h
0x1800084c6  lea     r15, [r13+10h]
0x1800084ca  jnz     loc_180008578
0x1800084d0  mov     ebp, 0C0000001h
0x1800084d5  jmp     loc_18000823C
0x1800084da  mov     [rsp+88h+var_58], ebx
0x1800084de  lea     r8, [r13+10h]
0x1800084e2  mov     [rsp+88h+var_60], ebp
0x1800084e6  lea     rdx, UnsubscribeWnf
0x1800084ed  mov     r9d, r13d
0x1800084f0  mov     dword ptr [rsp+88h+var_68], edi
  ... truncated ...
```
