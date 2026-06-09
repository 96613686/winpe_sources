# RemoveReceiveJob(_JOB_QUEUE *,int)

- ea: `0x14003d470`
- end: `0x14003da46`
- name: `?RemoveReceiveJob@@YAHPEAU_JOB_QUEUE@@H@Z`
- size: `1494`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1400399f0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004e48`
- `0x140004f64`
- `0x140004fe4`
- `0x140023a0c`
- `0x140037184`
- `0x14003a304`
- `0x14003c4ac`
- `0x14003d470`
- `0x14003fda0`
- `0x1400408a8`
- `0x140058d78`
- `0x14005900c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003d59d`
- `KERNEL32!GetLastError` at `0x14003d5e5`
- `KERNEL32!GetLastError` at `0x14003d677`
- `KERNEL32!GetLastError` at `0x14003d733`
- `KERNEL32!GetLastError` at `0x14003d7d0`
- `KERNEL32!GetLastError` at `0x14003d8ca`
- `KERNEL32!GetLastError` at `0x14003d9b0`
- `KERNEL32!GetLastError` at `0x14003d59d`
- `KERNEL32!GetLastError` at `0x14003d5e5`
- `KERNEL32!GetLastError` at `0x14003d677`
- `KERNEL32!GetLastError` at `0x14003d733`
- `KERNEL32!GetLastError` at `0x14003d7d0`
- `KERNEL32!GetLastError` at `0x14003d8ca`
- `KERNEL32!GetLastError` at `0x14003d9b0`
- `KERNEL32!DeleteFileW` at `0x14003d64f`
- `KERNEL32!DeleteFileW` at `0x14003d70b`
- `KERNEL32!DeleteFileW` at `0x14003d7a8`
- `KERNEL32!DeleteFileW` at `0x14003d89b`
- `KERNEL32!DeleteFileW` at `0x14003d64f`
- `KERNEL32!DeleteFileW` at `0x14003d70b`
- `KERNEL32!DeleteFileW` at `0x14003d7a8`
- `KERNEL32!DeleteFileW` at `0x14003d89b`
- `KERNEL32!EnterCriticalSection` at `0x14003d4c7`
- `KERNEL32!EnterCriticalSection` at `0x14003d4c7`
- `KERNEL32!LeaveCriticalSection` at `0x14003da24`
- `KERNEL32!LeaveCriticalSection` at `0x14003da24`
- `KERNEL32!CancelWaitableTimer` at `0x14003d575`
- `KERNEL32!CancelWaitableTimer` at `0x14003d575`

## pseudocode

```c
__int64 __fastcall RemoveReceiveJob(struct _LIST_ENTRY *a1, int a2)
{
  struct _LIST_ENTRY *i; // rbx
  DWORD Flink; // r15d
  struct _LIST_ENTRY *v6; // rcx
  struct _LIST_ENTRY *Blink; // rax
  HANDLE v8; // rcx
  DWORD LastError; // eax
  int v10; // edx
  CMapDeviceId *v11; // rax
  DWORD v12; // eax
  struct _LIST_ENTRY *v13; // r9
  char v14; // al
  struct _LIST_ENTRY *v15; // r9
  char v16; // al
  char v17; // al
  struct _LIST_ENTRY *v18; // r14
  struct _LIST_ENTRY *v19; // rdi
  struct _LIST_ENTRY *v20; // rdi
  struct _LIST_ENTRY *v21; // rsi
  char v22; // al
  int QueueEvent; // eax
  DWORD v24; // eax
  int v26; // [rsp+20h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 280, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  EnterCriticalSection(&g_CsQueue);
  for ( i = g_QueueListHead.Flink; ; i = i->Flink )
  {
    if ( i == &g_QueueListHead )
      goto LABEL_102;
    if ( i == a1 )
      break;
  }
  if ( !i )
    goto LABEL_102;
  if ( HIDWORD(i[3].Flink) )
  {
    _JOB_QUEUE::PutStatus((_JOB_QUEUE *)i, 4u);
    goto LABEL_102;
  }
  Flink = (DWORD)i[2].Flink;
  if ( !LODWORD(i[3].Flink) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, Flink);
    }
    v6 = i->Flink;
    Blink = i->Blink;
    Blink->Flink = i->Flink;
    v6->Blink = Blink;
    v8 = g_hQueueTimer;
    i->Flink = 0;
    i->Blink = 0;
    if ( !CancelWaitableTimer(v8)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 282, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
    }
    if ( !(unsigned int)StartJobQueueTimer() )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_29:
        v13 = i[4].Blink;
        if ( !v13 )
          goto LABEL_45;
        if ( LODWORD(i[115].Flink) == 1 )
        {
          if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v11 + 28) & 4) != 0
            && *((_BYTE *)v11 + 25) >= 5u )
          {
            WPP_SF_S(*((_QWORD *)v11 + 2), 284, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v13);
          }
          if ( DeleteFileW((LPCWSTR)i[4].Blink) )
            goto LABEL_44;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = GetLastError();
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              285,
              (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
              i[4].Blink,
              v14);
LABEL_44:
            v11 = WPP_GLOBAL_Control;
          }
        }
        else if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)v11 + 28) & 4) != 0
               && *((_BYTE *)v11 + 25) >= 3u )
        {
          WPP_SF_S(*((_QWORD *)v11 + 2), 286, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v13);
          goto LABEL_44;
        }
LABEL_45:
        if ( HIDWORD(i[2].Flink) != 8 )
        {
LABEL_86:
          if ( a2 )
          {
            QueueEvent = CreateQueueEvent(1, a1);
            if ( QueueEvent
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LOWORD(v26) = QueueEvent;
              WPP_SF_lh(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                294,
                &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                LODWORD(a1[1].Flink),
                v26);
            }
            if ( !(unsigned int)CreateFaxEvent(0, 0x17u, Flink, i[25].Blink)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v24 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 295, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v24);
            }
          }
          FreeReceiveQueueEntry((struct _JOB_QUEUE *)i, v10);
          SafeDecIdleCounter(&g_dwQueueCount);
          goto LABEL_102;
        }
        v15 = i[3].Blink;
        if ( v15 )
        {
          if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v11 + 28) & 4) != 0
            && *((_BYTE *)v11 + 25) >= 5u )
          {
            WPP_SF_S(*((_QWORD *)v11 + 2), 287, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v15);
          }
          if ( DeleteFileW((LPCWSTR)i[3].Blink) )
            goto LABEL_56;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = GetLastError();
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              288,
              (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
              i[3].Blink,
              v16);
LABEL_56:
            v11 = WPP_GLOBAL_Control;
          }
        }
        if ( i[37].Blink )
        {
          if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v11 + 28) & 4) != 0
            && *((_BYTE *)v11 + 25) >= 5u )
          {
            WPP_SF_DS(
              *((_QWORD *)v11 + 2),
              289,
              (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
              i[2].Flink,
              (__int64)i[37].Blink);
          }
          if ( DeleteFileW((LPCWSTR)i[37].Blink) )
            goto LABEL_67;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
          {
LABEL_72:
            v18 = i + 106;
            v19 = i[106].Flink;
            if ( v19 )
            {
              v20 = v19->Flink;
              if ( v20 )
              {
                while ( v20 != v18 )
                {
                  v21 = v20;
                  v20 = v20->Flink;
                  if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)v11 + 28) & 4) != 0
                    && *((_BYTE *)v11 + 25) >= 5u )
                  {
                    WPP_SF_S(*((_QWORD *)v11 + 2), 292, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v21[1].Flink);
                  }
                  if ( DeleteFileW((LPCWSTR)v21[1].Flink) )
                  {
                    v11 = WPP_GLOBAL_Control;
                  }
                  else
                  {
                    v11 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v22 = GetLastError();
                      WPP_SF_Sd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        293,
                        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                        v21[1].Flink,
                        v22);
                      v11 = WPP_GLOBAL_Control;
                    }
                  }
                }
              }
            }
            goto LABEL_86;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v17 = GetLastError();
            WPP_SF_lSl(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              290,
              (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
              i[2].Flink,
              (__int64)i[37].Blink,
              v17);
LABEL_67:
            v11 = WPP_GLOBAL_Control;
          }
        }
        if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)v11 + 2), 291, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
          v11 = WPP_GLOBAL_Control;
        }
        goto LABEL_72;
      }
      v12 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 283, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v12);
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 296, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
LABEL_102:
  LeaveCriticalSection(&g_CsQueue);
  return 1;
}

```

## disassembly

```asm
0x14003d470  push    rbx
0x14003d472  push    rsi
0x14003d473  push    rdi
0x14003d474  push    r12
0x14003d476  push    r13
0x14003d478  push    r14
0x14003d47a  push    r15
0x14003d47c  sub     rsp, 30h
0x14003d480  mov     r12d, edx
0x14003d483  mov     r13, rcx
0x14003d486  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d48d  lea     rdi, WPP_GLOBAL_Control
0x14003d494  lea     rsi, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003d49b  mov     r14b, 5
0x14003d49e  cmp     rcx, rdi
0x14003d4a1  jz      short loc_14003D4C0
0x14003d4a3  test    byte ptr [rcx+1Ch], 4
0x14003d4a7  jz      short loc_14003D4C0
0x14003d4a9  cmp     [rcx+19h], r14b
0x14003d4ad  jb      short loc_14003D4C0
0x14003d4af  mov     rcx, [rcx+10h]
0x14003d4b3  mov     edx, 118h
0x14003d4b8  mov     r8, rsi
0x14003d4bb  call    WPP_SF_
0x14003d4c0  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003d4c7  call    cs:__imp_EnterCriticalSection
0x14003d4ce  nop     dword ptr [rax+rax+00h]
0x14003d4d3  mov     rbx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x14003d4da  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003d4e1  jmp     short loc_14003D4EB
0x14003d4e3  cmp     rbx, r13
0x14003d4e6  jz      short loc_14003D4F5
0x14003d4e8  mov     rbx, [rbx]
0x14003d4eb  cmp     rbx, rax
0x14003d4ee  jnz     short loc_14003D4E3
0x14003d4f0  jmp     loc_14003DA1D
0x14003d4f5  test    rbx, rbx
0x14003d4f8  jz      loc_14003DA1D
0x14003d4fe  cmp     dword ptr [rbx+34h], 0
0x14003d502  jbe     short loc_14003D516
0x14003d504  mov     edx, 4; unsigned int
0x14003d509  mov     rcx, rbx; this
0x14003d50c  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14003d511  jmp     loc_14003DA1D
0x14003d516  mov     eax, [rbx+30h]
0x14003d519  mov     r15d, [rbx+20h]
0x14003d51d  test    eax, eax
0x14003d51f  jnz     loc_14003D9ED
0x14003d525  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d52c  cmp     rcx, rdi
0x14003d52f  jz      short loc_14003D551
0x14003d531  test    byte ptr [rcx+1Ch], 4
0x14003d535  jz      short loc_14003D551
0x14003d537  cmp     [rcx+19h], r14b
0x14003d53b  jb      short loc_14003D551
0x14003d53d  mov     rcx, [rcx+10h]
0x14003d541  mov     edx, 119h
0x14003d546  mov     r9d, r15d
0x14003d549  mov     r8, rsi
0x14003d54c  call    WPP_SF_d
0x14003d551  mov     rcx, [rbx]
0x14003d554  mov     rax, [rbx+8]
0x14003d558  mov     [rax], rcx
0x14003d55b  mov     [rcx+8], rax
0x14003d55f  mov     rcx, cs:?g_hQueueTimer@@3PEAXEA; hTimer
0x14003d566  mov     qword ptr [rbx], 0
0x14003d56d  mov     qword ptr [rbx+8], 0
0x14003d575  call    cs:__imp_CancelWaitableTimer
0x14003d57c  nop     dword ptr [rax+rax+00h]
0x14003d581  test    eax, eax
0x14003d583  jnz     short loc_14003D5C4
0x14003d585  mov     rax, cs:WPP_GLOBAL_Control
0x14003d58c  cmp     rax, rdi
0x14003d58f  jz      short loc_14003D5C4
0x14003d591  test    byte ptr [rax+1Ch], 4
0x14003d595  jz      short loc_14003D5C4
0x14003d597  cmp     byte ptr [rax+19h], 2
0x14003d59b  jb      short loc_14003D5C4
0x14003d59d  call    cs:__imp_GetLastError
0x14003d5a4  nop     dword ptr [rax+rax+00h]
0x14003d5a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d5b0  mov     edx, 11Ah
0x14003d5b5  mov     r9d, eax
0x14003d5b8  mov     r8, rsi
0x14003d5bb  mov     rcx, [rcx+10h]
0x14003d5bf  call    WPP_SF_d
0x14003d5c4  call    ?StartJobQueueTimer@@YAHXZ; StartJobQueueTimer(void)
0x14003d5c9  test    eax, eax
0x14003d5cb  jnz     short loc_14003D60C
0x14003d5cd  mov     rax, cs:WPP_GLOBAL_Control
0x14003d5d4  cmp     rax, rdi
0x14003d5d7  jz      short loc_14003D613
0x14003d5d9  test    byte ptr [rax+1Ch], 4
0x14003d5dd  jz      short loc_14003D613
0x14003d5df  cmp     byte ptr [rax+19h], 2
0x14003d5e3  jb      short loc_14003D613
0x14003d5e5  call    cs:__imp_GetLastError
0x14003d5ec  nop     dword ptr [rax+rax+00h]
0x14003d5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d5f8  mov     edx, 11Bh
0x14003d5fd  mov     r9d, eax
0x14003d600  mov     r8, rsi
0x14003d603  mov     rcx, [rcx+10h]
0x14003d607  call    WPP_SF_d
0x14003d60c  mov     rax, cs:WPP_GLOBAL_Control
0x14003d613  mov     r9, [rbx+48h]
0x14003d617  test    r9, r9
0x14003d61a  jz      loc_14003D6CE
0x14003d620  cmp     dword ptr [rbx+730h], 1
0x14003d627  jnz     short loc_14003D6A5
0x14003d629  cmp     rax, rdi
0x14003d62c  jz      short loc_14003D64B
0x14003d62e  test    byte ptr [rax+1Ch], 4
0x14003d632  jz      short loc_14003D64B
0x14003d634  cmp     [rax+19h], r14b
0x14003d638  jb      short loc_14003D64B
0x14003d63a  mov     rcx, [rax+10h]
0x14003d63e  mov     edx, 11Ch
0x14003d643  mov     r8, rsi
0x14003d646  call    WPP_SF_S
0x14003d64b  mov     rcx, [rbx+48h]; lpFileName
0x14003d64f  call    cs:__imp_DeleteFileW
0x14003d656  nop     dword ptr [rax+rax+00h]
0x14003d65b  test    eax, eax
0x14003d65d  jnz     short loc_14003D6C7
0x14003d65f  mov     rax, cs:WPP_GLOBAL_Control
0x14003d666  cmp     rax, rdi
0x14003d669  jz      short loc_14003D6CE
0x14003d66b  test    byte ptr [rax+1Ch], 4
0x14003d66f  jz      short loc_14003D6CE
0x14003d671  cmp     byte ptr [rax+19h], 2
0x14003d675  jb      short loc_14003D6CE
0x14003d677  call    cs:__imp_GetLastError
0x14003d67e  nop     dword ptr [rax+rax+00h]
0x14003d683  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d68a  mov     edx, 11Dh
0x14003d68f  mov     r9, [rbx+48h]
0x14003d693  mov     r8, rsi
0x14003d696  mov     dword ptr [rsp+68h+var_48], eax
0x14003d69a  mov     rcx, [rcx+10h]
0x14003d69e  call    WPP_SF_Sd
0x14003d6a3  jmp     short loc_14003D6C7
0x14003d6a5  cmp     rax, rdi
0x14003d6a8  jz      short loc_14003D6CE
0x14003d6aa  test    byte ptr [rax+1Ch], 4
0x14003d6ae  jz      short loc_14003D6CE
0x14003d6b0  cmp     byte ptr [rax+19h], 3
0x14003d6b4  jb      short loc_14003D6CE
0x14003d6b6  mov     rcx, [rax+10h]
0x14003d6ba  mov     edx, 11Eh
0x14003d6bf  mov     r8, rsi
0x14003d6c2  call    WPP_SF_S
0x14003d6c7  mov     rax, cs:WPP_GLOBAL_Control
0x14003d6ce  cmp     dword ptr [rbx+24h], 8
0x14003d6d2  jnz     loc_14003D932
0x14003d6d8  mov     r9, [rbx+38h]
0x14003d6dc  test    r9, r9
0x14003d6df  jz      loc_14003D766
0x14003d6e5  cmp     rax, rdi
0x14003d6e8  jz      short loc_14003D707
0x14003d6ea  test    byte ptr [rax+1Ch], 4
0x14003d6ee  jz      short loc_14003D707
0x14003d6f0  cmp     [rax+19h], r14b
0x14003d6f4  jb      short loc_14003D707
0x14003d6f6  mov     rcx, [rax+10h]
0x14003d6fa  mov     edx, 11Fh
0x14003d6ff  mov     r8, rsi
0x14003d702  call    WPP_SF_S
0x14003d707  mov     rcx, [rbx+38h]; lpFileName
0x14003d70b  call    cs:__imp_DeleteFileW
0x14003d712  nop     dword ptr [rax+rax+00h]
0x14003d717  test    eax, eax
0x14003d719  jnz     short loc_14003D75F
0x14003d71b  mov     rax, cs:WPP_GLOBAL_Control
0x14003d722  cmp     rax, rdi
0x14003d725  jz      short loc_14003D766
0x14003d727  test    byte ptr [rax+1Ch], 4
0x14003d72b  jz      short loc_14003D766
0x14003d72d  cmp     byte ptr [rax+19h], 2
0x14003d731  jb      short loc_14003D766
0x14003d733  call    cs:__imp_GetLastError
0x14003d73a  nop     dword ptr [rax+rax+00h]
0x14003d73f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d746  mov     edx, 120h
0x14003d74b  mov     r9, [rbx+38h]
0x14003d74f  mov     r8, rsi
0x14003d752  mov     dword ptr [rsp+68h+var_48], eax
0x14003d756  mov     rcx, [rcx+10h]
0x14003d75a  call    WPP_SF_Sd
0x14003d75f  mov     rax, cs:WPP_GLOBAL_Control
0x14003d766  mov     rcx, [rbx+258h]
0x14003d76d  test    rcx, rcx
0x14003d770  jz      loc_14003D80F
0x14003d776  cmp     rax, rdi
0x14003d779  jz      short loc_14003D7A1
0x14003d77b  test    byte ptr [rax+1Ch], 4
0x14003d77f  jz      short loc_14003D7A1
0x14003d781  cmp     [rax+19h], r14b
0x14003d785  jb      short loc_14003D7A1
0x14003d787  mov     r9d, [rbx+20h]
0x14003d78b  mov     edx, 121h
0x14003d790  mov     [rsp+68h+var_48], rcx
0x14003d795  mov     r8, rsi
0x14003d798  mov     rcx, [rax+10h]
0x14003d79c  call    WPP_SF_DS
0x14003d7a1  mov     rcx, [rbx+258h]; lpFileName
0x14003d7a8  call    cs:__imp_DeleteFileW
0x14003d7af  nop     dword ptr [rax+rax+00h]
0x14003d7b4  test    eax, eax
0x14003d7b6  jnz     short loc_14003D808
0x14003d7b8  mov     rax, cs:WPP_GLOBAL_Control
0x14003d7bf  cmp     rax, rdi
0x14003d7c2  jz      short loc_14003D838
0x14003d7c4  test    byte ptr [rax+1Ch], 4
0x14003d7c8  jz      short loc_14003D80F
0x14003d7ca  cmp     [rax+19h], r14b
0x14003d7ce  jb      short loc_14003D80F
0x14003d7d0  call    cs:__imp_GetLastError
0x14003d7d7  nop     dword ptr [rax+rax+00h]
0x14003d7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d7e3  mov     edx, 122h
0x14003d7e8  mov     r9d, [rbx+20h]
0x14003d7ec  mov     r8, rsi
0x14003d7ef  mov     [rsp+68h+var_40], eax
0x14003d7f3  mov     rax, [rbx+258h]
0x14003d7fa  mov     rcx, [rcx+10h]
0x14003d7fe  mov     [rsp+68h+var_48], rax
0x14003d803  call    WPP_SF_lSl
0x14003d808  mov     rax, cs:WPP_GLOBAL_Control
0x14003d80f  cmp     rax, rdi
0x14003d812  jz      short loc_14003D838
0x14003d814  test    byte ptr [rax+1Ch], 4
0x14003d818  jz      short loc_14003D838
0x14003d81a  cmp     [rax+19h], r14b
0x14003d81e  jb      short loc_14003D838
0x14003d820  mov     rcx, [rax+10h]
0x14003d824  mov     edx, 123h
0x14003d829  mov     r8, rsi
0x14003d82c  call    WPP_SF_
0x14003d831  mov     rax, cs:WPP_GLOBAL_Control
0x14003d838  lea     r14, [rbx+6A0h]
0x14003d83f  mov     rdi, [r14]
0x14003d842  test    rdi, rdi
0x14003d845  jz      loc_14003D92B
0x14003d84b  mov     rdi, [rdi]
0x14003d84e  test    rdi, rdi
0x14003d851  jz      loc_14003D92B
0x14003d857  cmp     rdi, r14
0x14003d85a  jz      loc_14003D92B
0x14003d860  lea     rcx, WPP_GLOBAL_Control
0x14003d867  lea     rsi, [rdi]
0x14003d86a  mov     rdi, [rdi]
0x14003d86d  cmp     rax, rcx
0x14003d870  jz      short loc_14003D897
0x14003d872  test    byte ptr [rax+1Ch], 4
0x14003d876  jz      short loc_14003D897
0x14003d878  cmp     byte ptr [rax+19h], 5
0x14003d87c  jb      short loc_14003D897
0x14003d87e  mov     r9, [rsi+10h]
0x14003d882  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003d889  mov     rcx, [rax+10h]
0x14003d88d  mov     edx, 124h
0x14003d892  call    WPP_SF_S
0x14003d897  mov     rcx, [rsi+10h]; lpFileName
0x14003d89b  call    cs:__imp_DeleteFileW
0x14003d8a2  nop     dword ptr [rax+rax+00h]
0x14003d8a7  test    eax, eax
0x14003d8a9  jnz     short loc_14003D90D
0x14003d8ab  mov     rax, cs:WPP_GLOBAL_Control
0x14003d8b2  lea     rcx, WPP_GLOBAL_Control
0x14003d8b9  cmp     rax, rcx
0x14003d8bc  jz      short loc_14003D91B
0x14003d8be  test    byte ptr [rax+1Ch], 4
0x14003d8c2  jz      short loc_14003D91B
0x14003d8c4  cmp     byte ptr [rax+19h], 2
0x14003d8c8  jb      short loc_14003D91B
0x14003d8ca  call    cs:__imp_GetLastError
0x14003d8d1  nop     dword ptr [rax+rax+00h]
0x14003d8d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d8dd  mov     edx, 125h
0x14003d8e2  mov     r9, [rsi+10h]
0x14003d8e6  lea     rsi, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003d8ed  mov     r8, rsi
0x14003d8f0  mov     dword ptr [rsp+68h+var_48], eax
0x14003d8f4  mov     rcx, [rcx+10h]
0x14003d8f8  call    WPP_SF_Sd
0x14003d8fd  mov     rax, cs:WPP_GLOBAL_Control
0x14003d904  lea     rcx, WPP_GLOBAL_Control
0x14003d90b  jmp     short loc_14003D922
0x14003d90d  mov     rax, cs:WPP_GLOBAL_Control
0x14003d914  lea     rcx, WPP_GLOBAL_Control
0x14003d91b  lea     rsi, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003d922  cmp     rdi, r14
0x14003d925  jnz     loc_14003D867
0x14003d92b  lea     rdi, WPP_GLOBAL_Control
0x14003d932  test    r12d, r12d
0x14003d935  jz      loc_14003D9D7
0x14003d93b  mov     rdx, r13
0x14003d93e  mov     ecx, 1
0x14003d943  call    ?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z; CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)
  ... truncated ...
```
