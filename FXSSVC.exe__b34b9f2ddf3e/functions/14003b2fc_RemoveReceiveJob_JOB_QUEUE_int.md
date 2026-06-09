# RemoveReceiveJob(_JOB_QUEUE *,int)

- ea: `0x14003b2fc`
- end: `0x14003b879`
- name: `?RemoveReceiveJob@@YAHPEAU_JOB_QUEUE@@H@Z`
- size: `1405`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x140037b14`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004ce4`
- `0x140004df0`
- `0x140004e68`
- `0x140022a4c`
- `0x1400354bc`
- `0x1400383e0`
- `0x14003a3d8`
- `0x14003b2fc`
- `0x14003da1c`
- `0x14003e488`
- `0x14005584c`
- `0x140055acc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003b41d`
- `KERNEL32!GetLastError` at `0x14003b45f`
- `KERNEL32!GetLastError` at `0x14003b4e5`
- `KERNEL32!GetLastError` at `0x14003b591`
- `KERNEL32!GetLastError` at `0x14003b622`
- `KERNEL32!GetLastError` at `0x14003b710`
- `KERNEL32!GetLastError` at `0x14003b7f0`
- `KERNEL32!GetLastError` at `0x14003b41d`
- `KERNEL32!GetLastError` at `0x14003b45f`
- `KERNEL32!GetLastError` at `0x14003b4e5`
- `KERNEL32!GetLastError` at `0x14003b591`
- `KERNEL32!GetLastError` at `0x14003b622`
- `KERNEL32!GetLastError` at `0x14003b710`
- `KERNEL32!GetLastError` at `0x14003b7f0`
- `KERNEL32!DeleteFileW` at `0x14003b4c3`
- `KERNEL32!DeleteFileW` at `0x14003b56f`
- `KERNEL32!DeleteFileW` at `0x14003b600`
- `KERNEL32!DeleteFileW` at `0x14003b6e7`
- `KERNEL32!DeleteFileW` at `0x14003b4c3`
- `KERNEL32!DeleteFileW` at `0x14003b56f`
- `KERNEL32!DeleteFileW` at `0x14003b600`
- `KERNEL32!DeleteFileW` at `0x14003b6e7`
- `KERNEL32!EnterCriticalSection` at `0x14003b353`
- `KERNEL32!EnterCriticalSection` at `0x14003b353`
- `KERNEL32!LeaveCriticalSection` at `0x14003b85e`
- `KERNEL32!LeaveCriticalSection` at `0x14003b85e`
- `KERNEL32!CancelWaitableTimer` at `0x14003b3fb`
- `KERNEL32!CancelWaitableTimer` at `0x14003b3fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=72 #try_helpers=1
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
            QueueEvent = CreateQueueEvent(1u, (__int64)a1);
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
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      296,
      &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      Flink,
      i[3].Flink);
  }
LABEL_102:
  LeaveCriticalSection(&g_CsQueue);
  return 1;
}

```

## disassembly

```asm
0x14003b2fc  push    rbx
0x14003b2fe  push    rsi
0x14003b2ff  push    rdi
0x14003b300  push    r12
0x14003b302  push    r13
0x14003b304  push    r14
0x14003b306  push    r15
0x14003b308  sub     rsp, 30h
0x14003b30c  mov     r12d, edx
0x14003b30f  mov     r13, rcx
0x14003b312  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b319  lea     rdi, WPP_GLOBAL_Control
0x14003b320  lea     rsi, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b327  mov     r14b, 5
0x14003b32a  cmp     rcx, rdi
0x14003b32d  jz      short loc_14003B34C
0x14003b32f  test    byte ptr [rcx+1Ch], 4
0x14003b333  jz      short loc_14003B34C
0x14003b335  cmp     [rcx+19h], r14b
0x14003b339  jb      short loc_14003B34C
0x14003b33b  mov     rcx, [rcx+10h]
0x14003b33f  mov     edx, 118h
0x14003b344  mov     r8, rsi
0x14003b347  call    WPP_SF_
0x14003b34c  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b353  call    cs:__imp_EnterCriticalSection
0x14003b359  mov     rbx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x14003b360  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003b367  jmp     short loc_14003B371
0x14003b369  cmp     rbx, r13
0x14003b36c  jz      short loc_14003B37B
0x14003b36e  mov     rbx, [rbx]
0x14003b371  cmp     rbx, rax
0x14003b374  jnz     short loc_14003B369
0x14003b376  jmp     loc_14003B857
0x14003b37b  test    rbx, rbx
0x14003b37e  jz      loc_14003B857
0x14003b384  cmp     dword ptr [rbx+34h], 0
0x14003b388  jbe     short loc_14003B39C
0x14003b38a  mov     edx, 4; unsigned int
0x14003b38f  mov     rcx, rbx; this
0x14003b392  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14003b397  jmp     loc_14003B857
0x14003b39c  mov     eax, [rbx+30h]
0x14003b39f  mov     r15d, [rbx+20h]
0x14003b3a3  test    eax, eax
0x14003b3a5  jnz     loc_14003B827
0x14003b3ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b3b2  cmp     rcx, rdi
0x14003b3b5  jz      short loc_14003B3D7
0x14003b3b7  test    byte ptr [rcx+1Ch], 4
0x14003b3bb  jz      short loc_14003B3D7
0x14003b3bd  cmp     [rcx+19h], r14b
0x14003b3c1  jb      short loc_14003B3D7
0x14003b3c3  mov     rcx, [rcx+10h]
0x14003b3c7  mov     edx, 119h
0x14003b3cc  mov     r9d, r15d
0x14003b3cf  mov     r8, rsi
0x14003b3d2  call    WPP_SF_d
0x14003b3d7  mov     rcx, [rbx]
0x14003b3da  mov     rax, [rbx+8]
0x14003b3de  mov     [rax], rcx
0x14003b3e1  mov     [rcx+8], rax
0x14003b3e5  mov     rcx, cs:?g_hQueueTimer@@3PEAXEA; hTimer
0x14003b3ec  mov     qword ptr [rbx], 0
0x14003b3f3  mov     qword ptr [rbx+8], 0
0x14003b3fb  call    cs:__imp_CancelWaitableTimer
0x14003b401  test    eax, eax
0x14003b403  jnz     short loc_14003B43E
0x14003b405  mov     rax, cs:WPP_GLOBAL_Control
0x14003b40c  cmp     rax, rdi
0x14003b40f  jz      short loc_14003B43E
0x14003b411  test    byte ptr [rax+1Ch], 4
0x14003b415  jz      short loc_14003B43E
0x14003b417  cmp     byte ptr [rax+19h], 2
0x14003b41b  jb      short loc_14003B43E
0x14003b41d  call    cs:__imp_GetLastError
0x14003b423  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b42a  mov     edx, 11Ah
0x14003b42f  mov     r9d, eax
0x14003b432  mov     r8, rsi
0x14003b435  mov     rcx, [rcx+10h]
0x14003b439  call    WPP_SF_d
0x14003b43e  call    ?StartJobQueueTimer@@YAHXZ; StartJobQueueTimer(void)
0x14003b443  test    eax, eax
0x14003b445  jnz     short loc_14003B480
0x14003b447  mov     rax, cs:WPP_GLOBAL_Control
0x14003b44e  cmp     rax, rdi
0x14003b451  jz      short loc_14003B487
0x14003b453  test    byte ptr [rax+1Ch], 4
0x14003b457  jz      short loc_14003B487
0x14003b459  cmp     byte ptr [rax+19h], 2
0x14003b45d  jb      short loc_14003B487
0x14003b45f  call    cs:__imp_GetLastError
0x14003b465  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b46c  mov     edx, 11Bh
0x14003b471  mov     r9d, eax
0x14003b474  mov     r8, rsi
0x14003b477  mov     rcx, [rcx+10h]
0x14003b47b  call    WPP_SF_d
0x14003b480  mov     rax, cs:WPP_GLOBAL_Control
0x14003b487  mov     r9, [rbx+48h]
0x14003b48b  test    r9, r9
0x14003b48e  jz      loc_14003B536
0x14003b494  cmp     dword ptr [rbx+730h], 1
0x14003b49b  jnz     short loc_14003B50D
0x14003b49d  cmp     rax, rdi
0x14003b4a0  jz      short loc_14003B4BF
0x14003b4a2  test    byte ptr [rax+1Ch], 4
0x14003b4a6  jz      short loc_14003B4BF
0x14003b4a8  cmp     [rax+19h], r14b
0x14003b4ac  jb      short loc_14003B4BF
0x14003b4ae  mov     rcx, [rax+10h]
0x14003b4b2  mov     edx, 11Ch
0x14003b4b7  mov     r8, rsi
0x14003b4ba  call    WPP_SF_S
0x14003b4bf  mov     rcx, [rbx+48h]; lpFileName
0x14003b4c3  call    cs:__imp_DeleteFileW
0x14003b4c9  test    eax, eax
0x14003b4cb  jnz     short loc_14003B52F
0x14003b4cd  mov     rax, cs:WPP_GLOBAL_Control
0x14003b4d4  cmp     rax, rdi
0x14003b4d7  jz      short loc_14003B536
0x14003b4d9  test    byte ptr [rax+1Ch], 4
0x14003b4dd  jz      short loc_14003B536
0x14003b4df  cmp     byte ptr [rax+19h], 2
0x14003b4e3  jb      short loc_14003B536
0x14003b4e5  call    cs:__imp_GetLastError
0x14003b4eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b4f2  mov     edx, 11Dh
0x14003b4f7  mov     r9, [rbx+48h]
0x14003b4fb  mov     r8, rsi
0x14003b4fe  mov     dword ptr [rsp+68h+var_48], eax
0x14003b502  mov     rcx, [rcx+10h]
0x14003b506  call    WPP_SF_Sd
0x14003b50b  jmp     short loc_14003B52F
0x14003b50d  cmp     rax, rdi
0x14003b510  jz      short loc_14003B536
0x14003b512  test    byte ptr [rax+1Ch], 4
0x14003b516  jz      short loc_14003B536
0x14003b518  cmp     byte ptr [rax+19h], 3
0x14003b51c  jb      short loc_14003B536
0x14003b51e  mov     rcx, [rax+10h]
0x14003b522  mov     edx, 11Eh
0x14003b527  mov     r8, rsi
0x14003b52a  call    WPP_SF_S
0x14003b52f  mov     rax, cs:WPP_GLOBAL_Control
0x14003b536  cmp     dword ptr [rbx+24h], 8
0x14003b53a  jnz     loc_14003B772
0x14003b540  mov     r9, [rbx+38h]
0x14003b544  test    r9, r9
0x14003b547  jz      short loc_14003B5BE
0x14003b549  cmp     rax, rdi
0x14003b54c  jz      short loc_14003B56B
0x14003b54e  test    byte ptr [rax+1Ch], 4
0x14003b552  jz      short loc_14003B56B
0x14003b554  cmp     [rax+19h], r14b
0x14003b558  jb      short loc_14003B56B
0x14003b55a  mov     rcx, [rax+10h]
0x14003b55e  mov     edx, 11Fh
0x14003b563  mov     r8, rsi
0x14003b566  call    WPP_SF_S
0x14003b56b  mov     rcx, [rbx+38h]; lpFileName
0x14003b56f  call    cs:__imp_DeleteFileW
0x14003b575  test    eax, eax
0x14003b577  jnz     short loc_14003B5B7
0x14003b579  mov     rax, cs:WPP_GLOBAL_Control
0x14003b580  cmp     rax, rdi
0x14003b583  jz      short loc_14003B5BE
0x14003b585  test    byte ptr [rax+1Ch], 4
0x14003b589  jz      short loc_14003B5BE
0x14003b58b  cmp     byte ptr [rax+19h], 2
0x14003b58f  jb      short loc_14003B5BE
0x14003b591  call    cs:__imp_GetLastError
0x14003b597  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b59e  mov     edx, 120h
0x14003b5a3  mov     r9, [rbx+38h]
0x14003b5a7  mov     r8, rsi
0x14003b5aa  mov     dword ptr [rsp+68h+var_48], eax
0x14003b5ae  mov     rcx, [rcx+10h]
0x14003b5b2  call    WPP_SF_Sd
0x14003b5b7  mov     rax, cs:WPP_GLOBAL_Control
0x14003b5be  mov     rcx, [rbx+258h]
0x14003b5c5  test    rcx, rcx
0x14003b5c8  jz      loc_14003B65B
0x14003b5ce  cmp     rax, rdi
0x14003b5d1  jz      short loc_14003B5F9
0x14003b5d3  test    byte ptr [rax+1Ch], 4
0x14003b5d7  jz      short loc_14003B5F9
0x14003b5d9  cmp     [rax+19h], r14b
0x14003b5dd  jb      short loc_14003B5F9
0x14003b5df  mov     r9d, [rbx+20h]
0x14003b5e3  mov     edx, 121h
0x14003b5e8  mov     [rsp+68h+var_48], rcx
0x14003b5ed  mov     r8, rsi
0x14003b5f0  mov     rcx, [rax+10h]
0x14003b5f4  call    WPP_SF_DS
0x14003b5f9  mov     rcx, [rbx+258h]; lpFileName
0x14003b600  call    cs:__imp_DeleteFileW
0x14003b606  test    eax, eax
0x14003b608  jnz     short loc_14003B654
0x14003b60a  mov     rax, cs:WPP_GLOBAL_Control
0x14003b611  cmp     rax, rdi
0x14003b614  jz      short loc_14003B684
0x14003b616  test    byte ptr [rax+1Ch], 4
0x14003b61a  jz      short loc_14003B65B
0x14003b61c  cmp     [rax+19h], r14b
0x14003b620  jb      short loc_14003B65B
0x14003b622  call    cs:__imp_GetLastError
0x14003b628  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b62f  mov     edx, 122h
0x14003b634  mov     r9d, [rbx+20h]
0x14003b638  mov     r8, rsi
0x14003b63b  mov     [rsp+68h+var_40], eax
0x14003b63f  mov     rax, [rbx+258h]
0x14003b646  mov     rcx, [rcx+10h]
0x14003b64a  mov     [rsp+68h+var_48], rax
0x14003b64f  call    WPP_SF_lSl
0x14003b654  mov     rax, cs:WPP_GLOBAL_Control
0x14003b65b  cmp     rax, rdi
0x14003b65e  jz      short loc_14003B684
0x14003b660  test    byte ptr [rax+1Ch], 4
0x14003b664  jz      short loc_14003B684
0x14003b666  cmp     [rax+19h], r14b
0x14003b66a  jb      short loc_14003B684
0x14003b66c  mov     rcx, [rax+10h]
0x14003b670  mov     edx, 123h
0x14003b675  mov     r8, rsi
0x14003b678  call    WPP_SF_
0x14003b67d  mov     rax, cs:WPP_GLOBAL_Control
0x14003b684  lea     r14, [rbx+6A0h]
0x14003b68b  mov     rdi, [r14]
0x14003b68e  test    rdi, rdi
0x14003b691  jz      loc_14003B76B
0x14003b697  mov     rdi, [rdi]
0x14003b69a  test    rdi, rdi
0x14003b69d  jz      loc_14003B76B
0x14003b6a3  cmp     rdi, r14
0x14003b6a6  jz      loc_14003B76B
0x14003b6ac  lea     rcx, WPP_GLOBAL_Control
0x14003b6b3  lea     rsi, [rdi]
0x14003b6b6  mov     rdi, [rdi]
0x14003b6b9  cmp     rax, rcx
0x14003b6bc  jz      short loc_14003B6E3
0x14003b6be  test    byte ptr [rax+1Ch], 4
0x14003b6c2  jz      short loc_14003B6E3
0x14003b6c4  cmp     byte ptr [rax+19h], 5
0x14003b6c8  jb      short loc_14003B6E3
0x14003b6ca  mov     r9, [rsi+10h]
0x14003b6ce  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b6d5  mov     rcx, [rax+10h]
0x14003b6d9  mov     edx, 124h
0x14003b6de  call    WPP_SF_S
0x14003b6e3  mov     rcx, [rsi+10h]; lpFileName
0x14003b6e7  call    cs:__imp_DeleteFileW
0x14003b6ed  test    eax, eax
0x14003b6ef  jnz     short loc_14003B74D
0x14003b6f1  mov     rax, cs:WPP_GLOBAL_Control
0x14003b6f8  lea     rcx, WPP_GLOBAL_Control
0x14003b6ff  cmp     rax, rcx
0x14003b702  jz      short loc_14003B75B
0x14003b704  test    byte ptr [rax+1Ch], 4
0x14003b708  jz      short loc_14003B75B
0x14003b70a  cmp     byte ptr [rax+19h], 2
0x14003b70e  jb      short loc_14003B75B
0x14003b710  call    cs:__imp_GetLastError
0x14003b716  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b71d  mov     edx, 125h
0x14003b722  mov     r9, [rsi+10h]
0x14003b726  lea     rsi, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b72d  mov     r8, rsi
0x14003b730  mov     dword ptr [rsp+68h+var_48], eax
0x14003b734  mov     rcx, [rcx+10h]
0x14003b738  call    WPP_SF_Sd
0x14003b73d  mov     rax, cs:WPP_GLOBAL_Control
0x14003b744  lea     rcx, WPP_GLOBAL_Control
0x14003b74b  jmp     short loc_14003B762
0x14003b74d  mov     rax, cs:WPP_GLOBAL_Control
0x14003b754  lea     rcx, WPP_GLOBAL_Control
0x14003b75b  lea     rsi, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b762  cmp     rdi, r14
0x14003b765  jnz     loc_14003B6B3
0x14003b76b  lea     rdi, WPP_GLOBAL_Control
0x14003b772  test    r12d, r12d
0x14003b775  jz      loc_14003B811
0x14003b77b  mov     rdx, r13
0x14003b77e  mov     ecx, 1
0x14003b783  call    ?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z; CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)
0x14003b788  test    eax, eax
0x14003b78a  jz      short loc_14003B7BE
0x14003b78c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b793  cmp     rcx, rdi
0x14003b796  jz      short loc_14003B7BE
0x14003b798  test    byte ptr [rcx+1Ch], 4
0x14003b79c  jz      short loc_14003B7BE
0x14003b79e  cmp     byte ptr [rcx+19h], 2
0x14003b7a2  jb      short loc_14003B7BE
0x14003b7a4  mov     r9d, [r13+10h]
0x14003b7a8  mov     edx, 126h
0x14003b7ad  mov     rcx, [rcx+10h]
  ... truncated ...
```
