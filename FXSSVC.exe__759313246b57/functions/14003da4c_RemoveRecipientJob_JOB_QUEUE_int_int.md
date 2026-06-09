# RemoveRecipientJob(_JOB_QUEUE *,int,int)

- ea: `0x14003da4c`
- end: `0x14003de8f`
- name: `?RemoveRecipientJob@@YAHPEAU_JOB_QUEUE@@HH@Z`
- size: `1091`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x14003d3a0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004fe4`
- `0x140023a0c`
- `0x140037184`
- `0x14003a5d8`
- `0x14003d2b0`
- `0x14003da4c`
- `0x14003fda0`
- `0x14005900c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003db83`
- `KERNEL32!GetLastError` at `0x14003dc15`
- `KERNEL32!GetLastError` at `0x14003dcbb`
- `KERNEL32!GetLastError` at `0x14003dd5e`
- `KERNEL32!GetLastError` at `0x14003db83`
- `KERNEL32!GetLastError` at `0x14003dc15`
- `KERNEL32!GetLastError` at `0x14003dcbb`
- `KERNEL32!GetLastError` at `0x14003dd5e`
- `KERNEL32!DeleteFileW` at `0x14003dbed`
- `KERNEL32!DeleteFileW` at `0x14003dc93`
- `KERNEL32!DeleteFileW` at `0x14003dd36`
- `KERNEL32!DeleteFileW` at `0x14003dbed`
- `KERNEL32!DeleteFileW` at `0x14003dc93`
- `KERNEL32!DeleteFileW` at `0x14003dd36`
- `KERNEL32!EnterCriticalSection` at `0x14003dac8`
- `KERNEL32!EnterCriticalSection` at `0x14003dac8`
- `KERNEL32!LeaveCriticalSection` at `0x14003de72`
- `KERNEL32!LeaveCriticalSection` at `0x14003de72`
- `KERNEL32!CancelWaitableTimer` at `0x14003db5b`
- `KERNEL32!CancelWaitableTimer` at `0x14003db5b`

## pseudocode

```c
__int64 __fastcall RemoveRecipientJob(struct _LIST_ENTRY *a1)
{
  CMapDeviceId *v2; // rcx
  struct _LIST_ENTRY *i; // rbx
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rax
  HANDLE v6; // rcx
  CMapDeviceId *v7; // rcx
  DWORD v8; // eax
  char v9; // al
  char LastError; // al
  char v11; // al
  int QueueEvent; // eax
  int v13; // edx
  int v15; // [rsp+20h] [rbp-38h]

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 5u )
      WPP_SF_d(*((_QWORD *)v2 + 2), 265, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LODWORD(a1[2].Flink));
  }
  EnterCriticalSection(&g_CsQueue);
  for ( i = g_QueueListHead.Flink; ; i = i->Flink )
  {
    if ( i == &g_QueueListHead )
      goto LABEL_73;
    if ( i == a1 )
      break;
  }
  if ( !i )
    goto LABEL_73;
  if ( !LODWORD(i[3].Flink) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        266,
        &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        LODWORD(i[2].Flink));
    }
    Flink = i->Flink;
    Blink = i->Blink;
    Blink->Flink = i->Flink;
    Flink->Blink = Blink;
    v6 = g_hQueueTimer;
    i->Flink = 0;
    i->Blink = 0;
    if ( !CancelWaitableTimer(v6) )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_26:
        if ( !i[3].Blink )
          goto LABEL_37;
        if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 5u )
          WPP_SF_DS(
            *((_QWORD *)v7 + 2),
            269,
            (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
            i[2].Flink,
            (__int64)i[3].Blink);
        if ( !DeleteFileW((LPCWSTR)i[3].Blink) )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
          {
LABEL_37:
            if ( i[37].Blink )
            {
              if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)v7 + 28) & 4) != 0
                && *((_BYTE *)v7 + 25) >= 5u )
              {
                WPP_SF_DS(
                  *((_QWORD *)v7 + 2),
                  271,
                  (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                  i[2].Flink,
                  (__int64)i[37].Blink);
              }
              if ( !DeleteFileW((LPCWSTR)i[37].Blink) )
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
                {
                  goto LABEL_48;
                }
                LastError = GetLastError();
                WPP_SF_lSl(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  272,
                  (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                  i[2].Flink,
                  (__int64)i[37].Blink,
                  LastError);
              }
              v7 = WPP_GLOBAL_Control;
            }
LABEL_48:
            if ( i[4].Blink )
            {
              if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)v7 + 28) & 4) != 0
                && *((_BYTE *)v7 + 25) >= 5u )
              {
                WPP_SF_DS(
                  *((_QWORD *)v7 + 2),
                  273,
                  (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                  i[2].Flink,
                  (__int64)i[4].Blink);
              }
              if ( !DeleteFileW((LPCWSTR)i[4].Blink)
                && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v11 = GetLastError();
                WPP_SF_lSl(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  274,
                  (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                  i[2].Flink,
                  (__int64)i[4].Blink,
                  v11);
              }
            }
            SafeDecIdleCounter(&g_dwQueueCount);
            if ( !(unsigned int)RemoveParentRecipientRef((struct _JOB_QUEUE *)i[36].Blink, (struct _JOB_QUEUE *const)i)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = (int)i[2].Flink;
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 275, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
            }
            QueueEvent = CreateQueueEvent(1, a1);
            if ( QueueEvent
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LOWORD(v15) = QueueEvent;
              WPP_SF_lh(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                276,
                &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                LODWORD(a1[1].Flink),
                v15);
            }
            FreeRecipientQueueEntry((struct _JOB_QUEUE *)i, v13);
            goto LABEL_73;
          }
          v9 = GetLastError();
          WPP_SF_lSl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            270,
            (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
            i[2].Flink,
            (__int64)i[3].Blink,
            v9);
        }
        v7 = WPP_GLOBAL_Control;
        goto LABEL_37;
      }
      v8 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v8);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 277, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
LABEL_73:
  LeaveCriticalSection(&g_CsQueue);
  return 1;
}

```

## disassembly

```asm
0x14003da4c  push    rbx
0x14003da4e  push    rbp
0x14003da4f  push    rsi
0x14003da50  push    rdi
0x14003da51  push    r15
0x14003da53  sub     rsp, 30h
0x14003da57  mov     rdi, rcx
0x14003da5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003da61  lea     rbp, WPP_GLOBAL_Control
0x14003da68  lea     r15, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003da6f  mov     sil, 4
0x14003da72  cmp     rcx, rbp
0x14003da75  jz      short loc_14003DAC1
0x14003da77  test    [rcx+1Ch], sil
0x14003da7b  jz      short loc_14003DA9B
0x14003da7d  cmp     byte ptr [rcx+19h], 5
0x14003da81  jb      short loc_14003DA9B
0x14003da83  mov     rcx, [rcx+10h]
0x14003da87  mov     edx, 108h
0x14003da8c  mov     r8, r15
0x14003da8f  call    WPP_SF_
0x14003da94  mov     rcx, cs:WPP_GLOBAL_Control
0x14003da9b  cmp     rcx, rbp
0x14003da9e  jz      short loc_14003DAC1
0x14003daa0  test    [rcx+1Ch], sil
0x14003daa4  jz      short loc_14003DAC1
0x14003daa6  cmp     byte ptr [rcx+19h], 5
0x14003daaa  jb      short loc_14003DAC1
0x14003daac  mov     r9d, [rdi+20h]
0x14003dab0  mov     edx, 109h
0x14003dab5  mov     rcx, [rcx+10h]
0x14003dab9  mov     r8, r15
0x14003dabc  call    WPP_SF_d
0x14003dac1  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003dac8  call    cs:__imp_EnterCriticalSection
0x14003dacf  nop     dword ptr [rax+rax+00h]
0x14003dad4  mov     rbx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x14003dadb  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003dae2  jmp     short loc_14003DAEC
0x14003dae4  cmp     rbx, rdi
0x14003dae7  jz      short loc_14003DAF6
0x14003dae9  mov     rbx, [rbx]
0x14003daec  cmp     rbx, rax
0x14003daef  jnz     short loc_14003DAE4
0x14003daf1  jmp     loc_14003DE6B
0x14003daf6  test    rbx, rbx
0x14003daf9  jz      loc_14003DE6B
0x14003daff  mov     eax, [rbx+30h]
0x14003db02  test    eax, eax
0x14003db04  jnz     loc_14003DE3A
0x14003db0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003db11  cmp     rcx, rbp
0x14003db14  jz      short loc_14003DB37
0x14003db16  test    [rcx+1Ch], sil
0x14003db1a  jz      short loc_14003DB37
0x14003db1c  cmp     byte ptr [rcx+19h], 5
0x14003db20  jb      short loc_14003DB37
0x14003db22  mov     r9d, [rbx+20h]
0x14003db26  mov     edx, 10Ah
0x14003db2b  mov     rcx, [rcx+10h]
0x14003db2f  mov     r8, r15
0x14003db32  call    WPP_SF_d
0x14003db37  mov     rcx, [rbx]
0x14003db3a  mov     rax, [rbx+8]
0x14003db3e  mov     [rax], rcx
0x14003db41  mov     [rcx+8], rax
0x14003db45  mov     rcx, cs:?g_hQueueTimer@@3PEAXEA; hTimer
0x14003db4c  mov     qword ptr [rbx], 0
0x14003db53  mov     qword ptr [rbx+8], 0
0x14003db5b  call    cs:__imp_CancelWaitableTimer
0x14003db62  nop     dword ptr [rax+rax+00h]
0x14003db67  test    eax, eax
0x14003db69  jnz     short loc_14003DBAA
0x14003db6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003db72  cmp     rcx, rbp
0x14003db75  jz      short loc_14003DBB1
0x14003db77  test    [rcx+1Ch], sil
0x14003db7b  jz      short loc_14003DBB1
0x14003db7d  cmp     byte ptr [rcx+19h], 2
0x14003db81  jb      short loc_14003DBB1
0x14003db83  call    cs:__imp_GetLastError
0x14003db8a  nop     dword ptr [rax+rax+00h]
0x14003db8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003db96  mov     edx, 10Bh
0x14003db9b  mov     r9d, eax
0x14003db9e  mov     r8, r15
0x14003dba1  mov     rcx, [rcx+10h]
0x14003dba5  call    WPP_SF_d
0x14003dbaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dbb1  mov     rax, [rbx+38h]
0x14003dbb5  test    rax, rax
0x14003dbb8  jz      loc_14003DC51
0x14003dbbe  cmp     rcx, rbp
0x14003dbc1  jz      short loc_14003DBE9
0x14003dbc3  test    [rcx+1Ch], sil
0x14003dbc7  jz      short loc_14003DBE9
0x14003dbc9  cmp     byte ptr [rcx+19h], 5
0x14003dbcd  jb      short loc_14003DBE9
0x14003dbcf  mov     r9d, [rbx+20h]
0x14003dbd3  mov     edx, 10Dh
0x14003dbd8  mov     rcx, [rcx+10h]
0x14003dbdc  mov     r8, r15
0x14003dbdf  mov     [rsp+58h+var_38], rax
0x14003dbe4  call    WPP_SF_DS
0x14003dbe9  mov     rcx, [rbx+38h]; lpFileName
0x14003dbed  call    cs:__imp_DeleteFileW
0x14003dbf4  nop     dword ptr [rax+rax+00h]
0x14003dbf9  test    eax, eax
0x14003dbfb  jnz     short loc_14003DC4A
0x14003dbfd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dc04  cmp     rcx, rbp
0x14003dc07  jz      short loc_14003DC51
0x14003dc09  test    [rcx+1Ch], sil
0x14003dc0d  jz      short loc_14003DC51
0x14003dc0f  cmp     byte ptr [rcx+19h], 5
0x14003dc13  jb      short loc_14003DC51
0x14003dc15  call    cs:__imp_GetLastError
0x14003dc1c  nop     dword ptr [rax+rax+00h]
0x14003dc21  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dc28  mov     edx, 10Eh
0x14003dc2d  mov     r9d, [rbx+20h]
0x14003dc31  mov     r8, r15
0x14003dc34  mov     [rsp+58h+var_30], eax
0x14003dc38  mov     rax, [rbx+38h]
0x14003dc3c  mov     rcx, [rcx+10h]
0x14003dc40  mov     [rsp+58h+var_38], rax
0x14003dc45  call    WPP_SF_lSl
0x14003dc4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dc51  mov     rax, [rbx+258h]
0x14003dc58  test    rax, rax
0x14003dc5b  jz      loc_14003DCFA
0x14003dc61  cmp     rcx, rbp
0x14003dc64  jz      short loc_14003DC8C
0x14003dc66  test    [rcx+1Ch], sil
0x14003dc6a  jz      short loc_14003DC8C
0x14003dc6c  cmp     byte ptr [rcx+19h], 5
0x14003dc70  jb      short loc_14003DC8C
0x14003dc72  mov     r9d, [rbx+20h]
0x14003dc76  mov     edx, 10Fh
0x14003dc7b  mov     rcx, [rcx+10h]
0x14003dc7f  mov     r8, r15
0x14003dc82  mov     [rsp+58h+var_38], rax
0x14003dc87  call    WPP_SF_DS
0x14003dc8c  mov     rcx, [rbx+258h]; lpFileName
0x14003dc93  call    cs:__imp_DeleteFileW
0x14003dc9a  nop     dword ptr [rax+rax+00h]
0x14003dc9f  test    eax, eax
0x14003dca1  jnz     short loc_14003DCF3
0x14003dca3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dcaa  cmp     rcx, rbp
0x14003dcad  jz      short loc_14003DCFA
0x14003dcaf  test    [rcx+1Ch], sil
0x14003dcb3  jz      short loc_14003DCFA
0x14003dcb5  cmp     byte ptr [rcx+19h], 5
0x14003dcb9  jb      short loc_14003DCFA
0x14003dcbb  call    cs:__imp_GetLastError
0x14003dcc2  nop     dword ptr [rax+rax+00h]
0x14003dcc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dcce  mov     edx, 110h
0x14003dcd3  mov     r9d, [rbx+20h]
0x14003dcd7  mov     r8, r15
0x14003dcda  mov     [rsp+58h+var_30], eax
0x14003dcde  mov     rax, [rbx+258h]
0x14003dce5  mov     rcx, [rcx+10h]
0x14003dce9  mov     [rsp+58h+var_38], rax
0x14003dcee  call    WPP_SF_lSl
0x14003dcf3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dcfa  mov     rax, [rbx+48h]
0x14003dcfe  test    rax, rax
0x14003dd01  jz      loc_14003DD93
0x14003dd07  cmp     rcx, rbp
0x14003dd0a  jz      short loc_14003DD32
0x14003dd0c  test    [rcx+1Ch], sil
0x14003dd10  jz      short loc_14003DD32
0x14003dd12  cmp     byte ptr [rcx+19h], 5
0x14003dd16  jb      short loc_14003DD32
0x14003dd18  mov     r9d, [rbx+20h]
0x14003dd1c  mov     edx, 111h
0x14003dd21  mov     rcx, [rcx+10h]
0x14003dd25  mov     r8, r15
0x14003dd28  mov     [rsp+58h+var_38], rax
0x14003dd2d  call    WPP_SF_DS
0x14003dd32  mov     rcx, [rbx+48h]; lpFileName
0x14003dd36  call    cs:__imp_DeleteFileW
0x14003dd3d  nop     dword ptr [rax+rax+00h]
0x14003dd42  test    eax, eax
0x14003dd44  jnz     short loc_14003DD93
0x14003dd46  mov     rax, cs:WPP_GLOBAL_Control
0x14003dd4d  cmp     rax, rbp
0x14003dd50  jz      short loc_14003DD93
0x14003dd52  test    [rax+1Ch], sil
0x14003dd56  jz      short loc_14003DD93
0x14003dd58  cmp     byte ptr [rax+19h], 5
0x14003dd5c  jb      short loc_14003DD93
0x14003dd5e  call    cs:__imp_GetLastError
0x14003dd65  nop     dword ptr [rax+rax+00h]
0x14003dd6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dd71  mov     edx, 112h
0x14003dd76  mov     r9d, [rbx+20h]
0x14003dd7a  mov     r8, r15
0x14003dd7d  mov     [rsp+58h+var_30], eax
0x14003dd81  mov     rax, [rbx+48h]
0x14003dd85  mov     rcx, [rcx+10h]
0x14003dd89  mov     [rsp+58h+var_38], rax
0x14003dd8e  call    WPP_SF_lSl
0x14003dd93  lea     rcx, ?g_dwQueueCount@@3KA; unsigned int *
0x14003dd9a  call    ?SafeDecIdleCounter@@YAXPEAK@Z; SafeDecIdleCounter(ulong *)
0x14003dd9f  mov     rcx, [rbx+248h]; struct _JOB_QUEUE *
0x14003dda6  mov     rdx, rbx; struct _JOB_QUEUE *
0x14003dda9  call    ?RemoveParentRecipientRef@@YAHPEAU_JOB_QUEUE@@QEAU1@@Z; RemoveParentRecipientRef(_JOB_QUEUE *,_JOB_QUEUE * const)
0x14003ddae  test    eax, eax
0x14003ddb0  jnz     short loc_14003DDED
0x14003ddb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ddb9  cmp     rcx, rbp
0x14003ddbc  jz      short loc_14003DDED
0x14003ddbe  test    [rcx+1Ch], sil
0x14003ddc2  jz      short loc_14003DDED
0x14003ddc4  cmp     byte ptr [rcx+19h], 2
0x14003ddc8  jb      short loc_14003DDED
0x14003ddca  mov     r9, [rbx+248h]
0x14003ddd1  mov     edx, 113h
0x14003ddd6  mov     eax, [rbx+20h]
0x14003ddd9  mov     r8, r15
0x14003dddc  mov     rcx, [rcx+10h]
0x14003dde0  mov     dword ptr [rsp+58h+var_38], eax
0x14003dde4  mov     r9d, [r9+20h]
0x14003dde8  call    WPP_SF_dd
0x14003dded  mov     rdx, rdi
0x14003ddf0  mov     ecx, 1
0x14003ddf5  call    ?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z; CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)
0x14003ddfa  test    eax, eax
0x14003ddfc  jz      short loc_14003DE30
0x14003ddfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14003de05  cmp     rcx, rbp
0x14003de08  jz      short loc_14003DE30
0x14003de0a  test    [rcx+1Ch], sil
0x14003de0e  jz      short loc_14003DE30
0x14003de10  cmp     byte ptr [rcx+19h], 2
0x14003de14  jb      short loc_14003DE30
0x14003de16  mov     r9d, [rdi+10h]
0x14003de1a  mov     edx, 114h
0x14003de1f  mov     rcx, [rcx+10h]
0x14003de23  mov     r8, r15
0x14003de26  mov     word ptr [rsp+58h+var_38], ax
0x14003de2b  call    WPP_SF_lh
0x14003de30  mov     rcx, rbx; this
0x14003de33  call    ?FreeRecipientQueueEntry@@YAXPEAU_JOB_QUEUE@@H@Z; FreeRecipientQueueEntry(_JOB_QUEUE *,int)
0x14003de38  jmp     short loc_14003DE6B
0x14003de3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003de41  cmp     rcx, rbp
0x14003de44  jz      short loc_14003DE6B
0x14003de46  test    [rcx+1Ch], sil
0x14003de4a  jz      short loc_14003DE6B
0x14003de4c  cmp     byte ptr [rcx+19h], 2
0x14003de50  jb      short loc_14003DE6B
0x14003de52  mov     r9d, [rbx+20h]
0x14003de56  mov     edx, 115h
0x14003de5b  mov     rcx, [rcx+10h]
0x14003de5f  mov     r8, r15
0x14003de62  mov     dword ptr [rsp+58h+var_38], eax
0x14003de66  call    WPP_SF_dd
0x14003de6b  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003de72  call    cs:__imp_LeaveCriticalSection
0x14003de79  nop     dword ptr [rax+rax+00h]
0x14003de7e  mov     eax, 1
0x14003de83  add     rsp, 30h
0x14003de87  pop     r15
0x14003de89  pop     rdi
0x14003de8a  pop     rsi
0x14003de8b  pop     rbp
0x14003de8c  pop     rbx
0x14003de8d  retn
```
