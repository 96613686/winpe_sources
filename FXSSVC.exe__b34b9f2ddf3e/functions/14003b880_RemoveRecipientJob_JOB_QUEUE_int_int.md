# RemoveRecipientJob(_JOB_QUEUE *,int,int)

- ea: `0x14003b880`
- end: `0x14003bc86`
- name: `?RemoveRecipientJob@@YAHPEAU_JOB_QUEUE@@HH@Z`
- size: `1030`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x14003b234`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004e68`
- `0x140022a4c`
- `0x1400354bc`
- `0x1400386b4`
- `0x14003b144`
- `0x14003b880`
- `0x14003da1c`
- `0x140055acc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003b9ab`
- `KERNEL32!GetLastError` at `0x14003ba31`
- `KERNEL32!GetLastError` at `0x14003bacb`
- `KERNEL32!GetLastError` at `0x14003bb62`
- `KERNEL32!GetLastError` at `0x14003b9ab`
- `KERNEL32!GetLastError` at `0x14003ba31`
- `KERNEL32!GetLastError` at `0x14003bacb`
- `KERNEL32!GetLastError` at `0x14003bb62`
- `KERNEL32!DeleteFileW` at `0x14003ba0f`
- `KERNEL32!DeleteFileW` at `0x14003baa9`
- `KERNEL32!DeleteFileW` at `0x14003bb40`
- `KERNEL32!DeleteFileW` at `0x14003ba0f`
- `KERNEL32!DeleteFileW` at `0x14003baa9`
- `KERNEL32!DeleteFileW` at `0x14003bb40`
- `KERNEL32!EnterCriticalSection` at `0x14003b8fc`
- `KERNEL32!EnterCriticalSection` at `0x14003b8fc`
- `KERNEL32!LeaveCriticalSection` at `0x14003bc70`
- `KERNEL32!LeaveCriticalSection` at `0x14003bc70`
- `KERNEL32!CancelWaitableTimer` at `0x14003b989`
- `KERNEL32!CancelWaitableTimer` at `0x14003b989`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  int v14; // [rsp+20h] [rbp-38h]

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
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                275,
                &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                LODWORD(i[36].Blink[2].Flink),
                i[2].Flink);
            }
            QueueEvent = CreateQueueEvent(1u, (__int64)a1);
            if ( QueueEvent
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LOWORD(v14) = QueueEvent;
              WPP_SF_lh(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                276,
                &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                LODWORD(a1[1].Flink),
                v14);
            }
            FreeRecipientQueueEntry((struct _JOB_QUEUE *)i);
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
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      277,
      &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      LODWORD(i[2].Flink),
      i[3].Flink);
  }
LABEL_73:
  LeaveCriticalSection(&g_CsQueue);
  return 1;
}

```

## disassembly

```asm
0x14003b880  push    rbx
0x14003b882  push    rbp
0x14003b883  push    rsi
0x14003b884  push    rdi
0x14003b885  push    r15
0x14003b887  sub     rsp, 30h
0x14003b88b  mov     rdi, rcx
0x14003b88e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b895  lea     rbp, WPP_GLOBAL_Control
0x14003b89c  lea     r15, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b8a3  mov     sil, 4
0x14003b8a6  cmp     rcx, rbp
0x14003b8a9  jz      short loc_14003B8F5
0x14003b8ab  test    [rcx+1Ch], sil
0x14003b8af  jz      short loc_14003B8CF
0x14003b8b1  cmp     byte ptr [rcx+19h], 5
0x14003b8b5  jb      short loc_14003B8CF
0x14003b8b7  mov     rcx, [rcx+10h]
0x14003b8bb  mov     edx, 108h
0x14003b8c0  mov     r8, r15
0x14003b8c3  call    WPP_SF_
0x14003b8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b8cf  cmp     rcx, rbp
0x14003b8d2  jz      short loc_14003B8F5
0x14003b8d4  test    [rcx+1Ch], sil
0x14003b8d8  jz      short loc_14003B8F5
0x14003b8da  cmp     byte ptr [rcx+19h], 5
0x14003b8de  jb      short loc_14003B8F5
0x14003b8e0  mov     r9d, [rdi+20h]
0x14003b8e4  mov     edx, 109h
0x14003b8e9  mov     rcx, [rcx+10h]
0x14003b8ed  mov     r8, r15
0x14003b8f0  call    WPP_SF_d
0x14003b8f5  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b8fc  call    cs:__imp_EnterCriticalSection
0x14003b902  mov     rbx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x14003b909  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003b910  jmp     short loc_14003B91A
0x14003b912  cmp     rbx, rdi
0x14003b915  jz      short loc_14003B924
0x14003b917  mov     rbx, [rbx]
0x14003b91a  cmp     rbx, rax
0x14003b91d  jnz     short loc_14003B912
0x14003b91f  jmp     loc_14003BC69
0x14003b924  test    rbx, rbx
0x14003b927  jz      loc_14003BC69
0x14003b92d  mov     eax, [rbx+30h]
0x14003b930  test    eax, eax
0x14003b932  jnz     loc_14003BC38
0x14003b938  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b93f  cmp     rcx, rbp
0x14003b942  jz      short loc_14003B965
0x14003b944  test    [rcx+1Ch], sil
0x14003b948  jz      short loc_14003B965
0x14003b94a  cmp     byte ptr [rcx+19h], 5
0x14003b94e  jb      short loc_14003B965
0x14003b950  mov     r9d, [rbx+20h]
0x14003b954  mov     edx, 10Ah
0x14003b959  mov     rcx, [rcx+10h]
0x14003b95d  mov     r8, r15
0x14003b960  call    WPP_SF_d
0x14003b965  mov     rcx, [rbx]
0x14003b968  mov     rax, [rbx+8]
0x14003b96c  mov     [rax], rcx
0x14003b96f  mov     [rcx+8], rax
0x14003b973  mov     rcx, cs:?g_hQueueTimer@@3PEAXEA; hTimer
0x14003b97a  mov     qword ptr [rbx], 0
0x14003b981  mov     qword ptr [rbx+8], 0
0x14003b989  call    cs:__imp_CancelWaitableTimer
0x14003b98f  test    eax, eax
0x14003b991  jnz     short loc_14003B9CC
0x14003b993  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b99a  cmp     rcx, rbp
0x14003b99d  jz      short loc_14003B9D3
0x14003b99f  test    [rcx+1Ch], sil
0x14003b9a3  jz      short loc_14003B9D3
0x14003b9a5  cmp     byte ptr [rcx+19h], 2
0x14003b9a9  jb      short loc_14003B9D3
0x14003b9ab  call    cs:__imp_GetLastError
0x14003b9b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b9b8  mov     edx, 10Bh
0x14003b9bd  mov     r9d, eax
0x14003b9c0  mov     r8, r15
0x14003b9c3  mov     rcx, [rcx+10h]
0x14003b9c7  call    WPP_SF_d
0x14003b9cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b9d3  mov     rax, [rbx+38h]
0x14003b9d7  test    rax, rax
0x14003b9da  jz      loc_14003BA67
0x14003b9e0  cmp     rcx, rbp
0x14003b9e3  jz      short loc_14003BA0B
0x14003b9e5  test    [rcx+1Ch], sil
0x14003b9e9  jz      short loc_14003BA0B
0x14003b9eb  cmp     byte ptr [rcx+19h], 5
0x14003b9ef  jb      short loc_14003BA0B
0x14003b9f1  mov     r9d, [rbx+20h]
0x14003b9f5  mov     edx, 10Dh
0x14003b9fa  mov     rcx, [rcx+10h]
0x14003b9fe  mov     r8, r15
0x14003ba01  mov     [rsp+58h+var_38], rax
0x14003ba06  call    WPP_SF_DS
0x14003ba0b  mov     rcx, [rbx+38h]; lpFileName
0x14003ba0f  call    cs:__imp_DeleteFileW
0x14003ba15  test    eax, eax
0x14003ba17  jnz     short loc_14003BA60
0x14003ba19  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ba20  cmp     rcx, rbp
0x14003ba23  jz      short loc_14003BA67
0x14003ba25  test    [rcx+1Ch], sil
0x14003ba29  jz      short loc_14003BA67
0x14003ba2b  cmp     byte ptr [rcx+19h], 5
0x14003ba2f  jb      short loc_14003BA67
0x14003ba31  call    cs:__imp_GetLastError
0x14003ba37  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ba3e  mov     edx, 10Eh
0x14003ba43  mov     r9d, [rbx+20h]
0x14003ba47  mov     r8, r15
0x14003ba4a  mov     [rsp+58h+var_30], eax
0x14003ba4e  mov     rax, [rbx+38h]
0x14003ba52  mov     rcx, [rcx+10h]
0x14003ba56  mov     [rsp+58h+var_38], rax
0x14003ba5b  call    WPP_SF_lSl
0x14003ba60  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ba67  mov     rax, [rbx+258h]
0x14003ba6e  test    rax, rax
0x14003ba71  jz      loc_14003BB04
0x14003ba77  cmp     rcx, rbp
0x14003ba7a  jz      short loc_14003BAA2
0x14003ba7c  test    [rcx+1Ch], sil
0x14003ba80  jz      short loc_14003BAA2
0x14003ba82  cmp     byte ptr [rcx+19h], 5
0x14003ba86  jb      short loc_14003BAA2
0x14003ba88  mov     r9d, [rbx+20h]
0x14003ba8c  mov     edx, 10Fh
0x14003ba91  mov     rcx, [rcx+10h]
0x14003ba95  mov     r8, r15
0x14003ba98  mov     [rsp+58h+var_38], rax
0x14003ba9d  call    WPP_SF_DS
0x14003baa2  mov     rcx, [rbx+258h]; lpFileName
0x14003baa9  call    cs:__imp_DeleteFileW
0x14003baaf  test    eax, eax
0x14003bab1  jnz     short loc_14003BAFD
0x14003bab3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003baba  cmp     rcx, rbp
0x14003babd  jz      short loc_14003BB04
0x14003babf  test    [rcx+1Ch], sil
0x14003bac3  jz      short loc_14003BB04
0x14003bac5  cmp     byte ptr [rcx+19h], 5
0x14003bac9  jb      short loc_14003BB04
0x14003bacb  call    cs:__imp_GetLastError
0x14003bad1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bad8  mov     edx, 110h
0x14003badd  mov     r9d, [rbx+20h]
0x14003bae1  mov     r8, r15
0x14003bae4  mov     [rsp+58h+var_30], eax
0x14003bae8  mov     rax, [rbx+258h]
0x14003baef  mov     rcx, [rcx+10h]
0x14003baf3  mov     [rsp+58h+var_38], rax
0x14003baf8  call    WPP_SF_lSl
0x14003bafd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bb04  mov     rax, [rbx+48h]
0x14003bb08  test    rax, rax
0x14003bb0b  jz      loc_14003BB91
0x14003bb11  cmp     rcx, rbp
0x14003bb14  jz      short loc_14003BB3C
0x14003bb16  test    [rcx+1Ch], sil
0x14003bb1a  jz      short loc_14003BB3C
0x14003bb1c  cmp     byte ptr [rcx+19h], 5
0x14003bb20  jb      short loc_14003BB3C
0x14003bb22  mov     r9d, [rbx+20h]
0x14003bb26  mov     edx, 111h
0x14003bb2b  mov     rcx, [rcx+10h]
0x14003bb2f  mov     r8, r15
0x14003bb32  mov     [rsp+58h+var_38], rax
0x14003bb37  call    WPP_SF_DS
0x14003bb3c  mov     rcx, [rbx+48h]; lpFileName
0x14003bb40  call    cs:__imp_DeleteFileW
0x14003bb46  test    eax, eax
0x14003bb48  jnz     short loc_14003BB91
0x14003bb4a  mov     rax, cs:WPP_GLOBAL_Control
0x14003bb51  cmp     rax, rbp
0x14003bb54  jz      short loc_14003BB91
0x14003bb56  test    [rax+1Ch], sil
0x14003bb5a  jz      short loc_14003BB91
0x14003bb5c  cmp     byte ptr [rax+19h], 5
0x14003bb60  jb      short loc_14003BB91
0x14003bb62  call    cs:__imp_GetLastError
0x14003bb68  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bb6f  mov     edx, 112h
0x14003bb74  mov     r9d, [rbx+20h]
0x14003bb78  mov     r8, r15
0x14003bb7b  mov     [rsp+58h+var_30], eax
0x14003bb7f  mov     rax, [rbx+48h]
0x14003bb83  mov     rcx, [rcx+10h]
0x14003bb87  mov     [rsp+58h+var_38], rax
0x14003bb8c  call    WPP_SF_lSl
0x14003bb91  lea     rcx, ?g_dwQueueCount@@3KA; unsigned int *
0x14003bb98  call    ?SafeDecIdleCounter@@YAXPEAK@Z; SafeDecIdleCounter(ulong *)
0x14003bb9d  mov     rcx, [rbx+248h]; struct _JOB_QUEUE *
0x14003bba4  mov     rdx, rbx; struct _JOB_QUEUE *
0x14003bba7  call    ?RemoveParentRecipientRef@@YAHPEAU_JOB_QUEUE@@QEAU1@@Z; RemoveParentRecipientRef(_JOB_QUEUE *,_JOB_QUEUE * const)
0x14003bbac  test    eax, eax
0x14003bbae  jnz     short loc_14003BBEB
0x14003bbb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bbb7  cmp     rcx, rbp
0x14003bbba  jz      short loc_14003BBEB
0x14003bbbc  test    [rcx+1Ch], sil
0x14003bbc0  jz      short loc_14003BBEB
0x14003bbc2  cmp     byte ptr [rcx+19h], 2
0x14003bbc6  jb      short loc_14003BBEB
0x14003bbc8  mov     r9, [rbx+248h]
0x14003bbcf  mov     edx, 113h
0x14003bbd4  mov     eax, [rbx+20h]
0x14003bbd7  mov     r8, r15
0x14003bbda  mov     rcx, [rcx+10h]
0x14003bbde  mov     dword ptr [rsp+58h+var_38], eax
0x14003bbe2  mov     r9d, [r9+20h]
0x14003bbe6  call    WPP_SF_dd
0x14003bbeb  mov     rdx, rdi
0x14003bbee  mov     ecx, 1
0x14003bbf3  call    ?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z; CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)
0x14003bbf8  test    eax, eax
0x14003bbfa  jz      short loc_14003BC2E
0x14003bbfc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bc03  cmp     rcx, rbp
0x14003bc06  jz      short loc_14003BC2E
0x14003bc08  test    [rcx+1Ch], sil
0x14003bc0c  jz      short loc_14003BC2E
0x14003bc0e  cmp     byte ptr [rcx+19h], 2
0x14003bc12  jb      short loc_14003BC2E
0x14003bc14  mov     r9d, [rdi+10h]
0x14003bc18  mov     edx, 114h
0x14003bc1d  mov     rcx, [rcx+10h]
0x14003bc21  mov     r8, r15
0x14003bc24  mov     word ptr [rsp+58h+var_38], ax
0x14003bc29  call    WPP_SF_lh
0x14003bc2e  mov     rcx, rbx; this
0x14003bc31  call    ?FreeRecipientQueueEntry@@YAXPEAU_JOB_QUEUE@@H@Z; FreeRecipientQueueEntry(_JOB_QUEUE *,int)
0x14003bc36  jmp     short loc_14003BC69
0x14003bc38  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bc3f  cmp     rcx, rbp
0x14003bc42  jz      short loc_14003BC69
0x14003bc44  test    [rcx+1Ch], sil
0x14003bc48  jz      short loc_14003BC69
0x14003bc4a  cmp     byte ptr [rcx+19h], 2
0x14003bc4e  jb      short loc_14003BC69
0x14003bc50  mov     r9d, [rbx+20h]
0x14003bc54  mov     edx, 115h
0x14003bc59  mov     rcx, [rcx+10h]
0x14003bc5d  mov     r8, r15
0x14003bc60  mov     dword ptr [rsp+58h+var_38], eax
0x14003bc64  call    WPP_SF_dd
0x14003bc69  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003bc70  call    cs:__imp_LeaveCriticalSection
0x14003bc76  mov     eax, 1
0x14003bc7b  add     rsp, 30h
0x14003bc7f  pop     r15
0x14003bc81  pop     rdi
0x14003bc82  pop     rsi
0x14003bc83  pop     rbp
0x14003bc84  pop     rbx
0x14003bc85  retn
```
