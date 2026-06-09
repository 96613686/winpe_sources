# RemoveParentJob(_JOB_QUEUE *,int,int)

- ea: `0x14003cd94`
- end: `0x14003d2a7`
- name: `?RemoveParentJob@@YAHPEAU_JOB_QUEUE@@HH@Z`
- size: `1299`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, int, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x14001dbc0`
- `0x1400399f0`
- `0x14003e168`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004fe4`
- `0x140037184`
- `0x14003a1bc`
- `0x14003c4ac`
- `0x14003cd94`
- `0x14003d3a0`
- `0x14003fda0`
- `0x1400408a8`
- `0x140058d78`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003cf22`
- `KERNEL32!GetLastError` at `0x14003cfbb`
- `KERNEL32!GetLastError` at `0x14003d04d`
- `KERNEL32!GetLastError` at `0x14003d0ed`
- `KERNEL32!GetLastError` at `0x14003d1a0`
- `KERNEL32!GetLastError` at `0x14003d21b`
- `KERNEL32!GetLastError` at `0x14003d27b`
- `KERNEL32!GetLastError` at `0x14003cf22`
- `KERNEL32!GetLastError` at `0x14003cfbb`
- `KERNEL32!GetLastError` at `0x14003d04d`
- `KERNEL32!GetLastError` at `0x14003d0ed`
- `KERNEL32!GetLastError` at `0x14003d1a0`
- `KERNEL32!GetLastError` at `0x14003d21b`
- `KERNEL32!GetLastError` at `0x14003d27b`
- `KERNEL32!DeleteFileW` at `0x14003d025`
- `KERNEL32!DeleteFileW` at `0x14003d0c5`
- `KERNEL32!DeleteFileW` at `0x14003d178`
- `KERNEL32!DeleteFileW` at `0x14003d025`
- `KERNEL32!DeleteFileW` at `0x14003d0c5`
- `KERNEL32!DeleteFileW` at `0x14003d178`
- `KERNEL32!EnterCriticalSection` at `0x14003cdef`
- `KERNEL32!EnterCriticalSection` at `0x14003cdef`
- `KERNEL32!LeaveCriticalSection` at `0x14003ce50`
- `KERNEL32!LeaveCriticalSection` at `0x14003ce50`
- `KERNEL32!CancelWaitableTimer` at `0x14003cef7`
- `KERNEL32!CancelWaitableTimer` at `0x14003cef7`

## pseudocode

```c
__int64 __fastcall RemoveParentJob(struct _LIST_ENTRY *a1, int a2, int a3)
{
  struct _LIST_ENTRY *i; // rbx
  int v8; // edx
  DWORD LastError; // eax
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *Flink; // rcx
  CMapDeviceId *v12; // rcx
  DWORD v13; // eax
  char v14; // al
  char v15; // al
  char v16; // al
  int v17; // edx
  DWORD v18; // eax
  DWORD v19; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  EnterCriticalSection(&g_CsQueue);
  for ( i = g_QueueListHead.Flink; ; i = i->Flink )
  {
    if ( i == &g_QueueListHead )
      goto LABEL_9;
    if ( i == a1 )
      break;
  }
  if ( !i )
  {
LABEL_9:
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
    }
    goto LABEL_13;
  }
  if ( LODWORD(i[3].Flink) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
    }
    goto LABEL_13;
  }
  if ( HIDWORD(i[3].Flink) )
  {
    _JOB_QUEUE::PutStatus((_JOB_QUEUE *)i, 4u);
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      250,
      &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      LODWORD(i[2].Flink));
  }
  if ( !CancelWaitableTimer(g_hQueueTimer)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
  }
  Blink = i->Blink;
  Flink = i->Flink;
  Blink->Flink = i->Flink;
  Flink->Blink = Blink;
  i->Flink = 0;
  i->Blink = 0;
  if ( !a2 )
    goto LABEL_41;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      252,
      &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      LODWORD(i[2].Flink));
  }
  if ( (unsigned int)RemoveParentRecipients((struct _JOB_QUEUE *)i, v8) )
    goto LABEL_41;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v13);
LABEL_41:
    v12 = WPP_GLOBAL_Control;
  }
  if ( !i[3].Blink )
    goto LABEL_53;
  if ( v12 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 5u )
    WPP_SF_DS(
      *((_QWORD *)v12 + 2),
      254,
      (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      i[2].Flink,
      (__int64)i[3].Blink);
  if ( DeleteFileW((LPCWSTR)i[3].Blink) )
    goto LABEL_52;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = GetLastError();
    WPP_SF_lSl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      255,
      (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      i[2].Flink,
      (__int64)i[3].Blink,
      v14);
LABEL_52:
    v12 = WPP_GLOBAL_Control;
  }
LABEL_53:
  if ( i[4].Blink )
  {
    if ( v12 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 5u )
      WPP_SF_DS(
        *((_QWORD *)v12 + 2),
        256,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        i[2].Flink,
        (__int64)i[4].Blink);
    if ( !DeleteFileW((LPCWSTR)i[4].Blink) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_64;
      }
      v15 = GetLastError();
      WPP_SF_lSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        257,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        i[2].Flink,
        (__int64)i[4].Blink,
        v15);
    }
    v12 = WPP_GLOBAL_Control;
  }
LABEL_64:
  if ( i[11].Blink && !LODWORD(i[12].Flink) )
  {
    if ( v12 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 5u )
      WPP_SF_DS(
        *((_QWORD *)v12 + 2),
        258,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        i[2].Flink,
        (__int64)i[11].Blink);
    if ( !DeleteFileW((LPCWSTR)i[11].Blink)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = GetLastError();
      WPP_SF_lSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        259,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        i[2].Flink,
        (__int64)i[11].Blink,
        v16);
    }
  }
  SafeDecIdleCounter(&g_dwQueueCount);
  if ( a3
    && !(unsigned int)CreateFaxEvent(0, 0x17u, (DWORD)i[2].Flink, i[25].Blink)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v18);
  }
  FreeParentQueueEntry((struct _JOB_QUEUE *)i, v17);
  if ( !(unsigned int)StartJobQueueTimer()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 261, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v19);
  }
LABEL_13:
  LeaveCriticalSection(&g_CsQueue);
  return 1;
}

```

## disassembly

```asm
0x14003cd94  push    rbx
0x14003cd96  push    rbp
0x14003cd97  push    rsi
0x14003cd98  push    rdi
0x14003cd99  push    r12
0x14003cd9b  push    r13
0x14003cd9d  push    r15
0x14003cd9f  sub     rsp, 30h
0x14003cda3  mov     ebp, r8d
0x14003cda6  mov     esi, edx
0x14003cda8  mov     rdi, rcx
0x14003cdab  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cdb2  lea     r12, WPP_GLOBAL_Control
0x14003cdb9  lea     r13, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003cdc0  mov     r15d, 4
0x14003cdc6  cmp     rcx, r12
0x14003cdc9  jz      short loc_14003CDE8
0x14003cdcb  test    [rcx+1Ch], r15b
0x14003cdcf  jz      short loc_14003CDE8
0x14003cdd1  cmp     byte ptr [rcx+19h], 5
0x14003cdd5  jb      short loc_14003CDE8
0x14003cdd7  mov     rcx, [rcx+10h]
0x14003cddb  mov     edx, 0F7h
0x14003cde0  mov     r8, r13
0x14003cde3  call    WPP_SF_
0x14003cde8  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003cdef  call    cs:__imp_EnterCriticalSection
0x14003cdf6  nop     dword ptr [rax+rax+00h]
0x14003cdfb  mov     rbx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x14003ce02  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003ce09  jmp     short loc_14003CE13
0x14003ce0b  cmp     rbx, rdi
0x14003ce0e  jz      short loc_14003CE71
0x14003ce10  mov     rbx, [rbx]
0x14003ce13  cmp     rbx, rax
0x14003ce16  jnz     short loc_14003CE0B
0x14003ce18  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ce1f  cmp     rcx, r12
0x14003ce22  jz      short loc_14003CE49
0x14003ce24  test    [rcx+1Ch], r15b
0x14003ce28  jz      short loc_14003CE49
0x14003ce2a  cmp     byte ptr [rcx+19h], 3
0x14003ce2e  jb      short loc_14003CE49
0x14003ce30  mov     r9d, [rdi+20h]
0x14003ce34  mov     edx, 0F8h
0x14003ce39  mov     rcx, [rcx+10h]
0x14003ce3d  mov     r8, r13
0x14003ce40  mov     dword ptr [rsp+68h+var_48], edi
0x14003ce44  call    WPP_SF_dd
0x14003ce49  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003ce50  call    cs:__imp_LeaveCriticalSection
0x14003ce57  nop     dword ptr [rax+rax+00h]
0x14003ce5c  mov     eax, 1
0x14003ce61  add     rsp, 30h
0x14003ce65  pop     r15
0x14003ce67  pop     r13
0x14003ce69  pop     r12
0x14003ce6b  pop     rdi
0x14003ce6c  pop     rsi
0x14003ce6d  pop     rbp
0x14003ce6e  pop     rbx
0x14003ce6f  retn
0x14003ce71  test    rbx, rbx
0x14003ce74  jz      short loc_14003CE18
0x14003ce76  mov     eax, [rbx+30h]
0x14003ce79  test    eax, eax
0x14003ce7b  jz      short loc_14003CEB0
0x14003ce7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ce84  cmp     rcx, r12
0x14003ce87  jz      short loc_14003CE49
0x14003ce89  test    [rcx+1Ch], r15b
0x14003ce8d  jz      short loc_14003CE49
0x14003ce8f  cmp     byte ptr [rcx+19h], 3
0x14003ce93  jb      short loc_14003CE49
0x14003ce95  mov     r9d, [rbx+20h]
0x14003ce99  mov     edx, 0F9h
0x14003ce9e  mov     rcx, [rcx+10h]
0x14003cea2  mov     r8, r13
0x14003cea5  mov     dword ptr [rsp+68h+var_48], eax
0x14003cea9  call    WPP_SF_dd
0x14003ceae  jmp     short loc_14003CE49
0x14003ceb0  cmp     dword ptr [rbx+34h], 0
0x14003ceb4  jbe     short loc_14003CEC3
0x14003ceb6  mov     edx, r15d; unsigned int
0x14003ceb9  mov     rcx, rbx; this
0x14003cebc  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14003cec1  jmp     short loc_14003CE49
0x14003cec3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ceca  cmp     rcx, r12
0x14003cecd  jz      short loc_14003CEF0
0x14003cecf  test    [rcx+1Ch], r15b
0x14003ced3  jz      short loc_14003CEF0
0x14003ced5  cmp     byte ptr [rcx+19h], 5
0x14003ced9  jb      short loc_14003CEF0
0x14003cedb  mov     r9d, [rbx+20h]
0x14003cedf  mov     edx, 0FAh
0x14003cee4  mov     rcx, [rcx+10h]
0x14003cee8  mov     r8, r13
0x14003ceeb  call    WPP_SF_d
0x14003cef0  mov     rcx, cs:?g_hQueueTimer@@3PEAXEA; hTimer
0x14003cef7  call    cs:__imp_CancelWaitableTimer
0x14003cefe  nop     dword ptr [rax+rax+00h]
0x14003cf03  mov     dil, 2
0x14003cf06  test    eax, eax
0x14003cf08  jnz     short loc_14003CF49
0x14003cf0a  mov     rax, cs:WPP_GLOBAL_Control
0x14003cf11  cmp     rax, r12
0x14003cf14  jz      short loc_14003CF49
0x14003cf16  test    [rax+1Ch], r15b
0x14003cf1a  jz      short loc_14003CF49
0x14003cf1c  cmp     [rax+19h], dil
0x14003cf20  jb      short loc_14003CF49
0x14003cf22  call    cs:__imp_GetLastError
0x14003cf29  nop     dword ptr [rax+rax+00h]
0x14003cf2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cf35  mov     edx, 0FBh
0x14003cf3a  mov     r9d, eax
0x14003cf3d  mov     r8, r13
0x14003cf40  mov     rcx, [rcx+10h]
0x14003cf44  call    WPP_SF_d
0x14003cf49  mov     rax, [rbx+8]
0x14003cf4d  mov     rcx, [rbx]
0x14003cf50  mov     [rax], rcx
0x14003cf53  mov     [rcx+8], rax
0x14003cf57  mov     qword ptr [rbx], 0
0x14003cf5e  mov     qword ptr [rbx+8], 0
0x14003cf66  test    esi, esi
0x14003cf68  jz      short loc_14003CFE2
0x14003cf6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cf71  cmp     rcx, r12
0x14003cf74  jz      short loc_14003CF97
0x14003cf76  test    [rcx+1Ch], r15b
0x14003cf7a  jz      short loc_14003CF97
0x14003cf7c  cmp     byte ptr [rcx+19h], 5
0x14003cf80  jb      short loc_14003CF97
0x14003cf82  mov     r9d, [rbx+20h]
0x14003cf86  mov     edx, 0FCh
0x14003cf8b  mov     rcx, [rcx+10h]
0x14003cf8f  mov     r8, r13
0x14003cf92  call    WPP_SF_d
0x14003cf97  mov     rcx, rbx; struct _JOB_QUEUE *
0x14003cf9a  call    ?RemoveParentRecipients@@YAHPEAU_JOB_QUEUE@@H@Z; RemoveParentRecipients(_JOB_QUEUE *,int)
0x14003cf9f  test    eax, eax
0x14003cfa1  jnz     short loc_14003CFE2
0x14003cfa3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cfaa  cmp     rcx, r12
0x14003cfad  jz      short loc_14003CFE9
0x14003cfaf  test    [rcx+1Ch], r15b
0x14003cfb3  jz      short loc_14003CFE9
0x14003cfb5  cmp     [rcx+19h], dil
0x14003cfb9  jb      short loc_14003CFE9
0x14003cfbb  call    cs:__imp_GetLastError
0x14003cfc2  nop     dword ptr [rax+rax+00h]
0x14003cfc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cfce  mov     edx, 0FDh
0x14003cfd3  mov     r9d, eax
0x14003cfd6  mov     r8, r13
0x14003cfd9  mov     rcx, [rcx+10h]
0x14003cfdd  call    WPP_SF_d
0x14003cfe2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cfe9  mov     rax, [rbx+38h]
0x14003cfed  test    rax, rax
0x14003cff0  jz      loc_14003D089
0x14003cff6  cmp     rcx, r12
0x14003cff9  jz      short loc_14003D021
0x14003cffb  test    [rcx+1Ch], r15b
0x14003cfff  jz      short loc_14003D021
0x14003d001  cmp     byte ptr [rcx+19h], 5
0x14003d005  jb      short loc_14003D021
0x14003d007  mov     r9d, [rbx+20h]
0x14003d00b  mov     edx, 0FEh
0x14003d010  mov     rcx, [rcx+10h]
0x14003d014  mov     r8, r13
0x14003d017  mov     [rsp+68h+var_48], rax
0x14003d01c  call    WPP_SF_DS
0x14003d021  mov     rcx, [rbx+38h]; lpFileName
0x14003d025  call    cs:__imp_DeleteFileW
0x14003d02c  nop     dword ptr [rax+rax+00h]
0x14003d031  test    eax, eax
0x14003d033  jnz     short loc_14003D082
0x14003d035  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d03c  cmp     rcx, r12
0x14003d03f  jz      short loc_14003D089
0x14003d041  test    [rcx+1Ch], r15b
0x14003d045  jz      short loc_14003D089
0x14003d047  cmp     [rcx+19h], dil
0x14003d04b  jb      short loc_14003D089
0x14003d04d  call    cs:__imp_GetLastError
0x14003d054  nop     dword ptr [rax+rax+00h]
0x14003d059  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d060  mov     edx, 0FFh
0x14003d065  mov     r9d, [rbx+20h]
0x14003d069  mov     r8, r13
0x14003d06c  mov     [rsp+68h+var_40], eax
0x14003d070  mov     rax, [rbx+38h]
0x14003d074  mov     rcx, [rcx+10h]
0x14003d078  mov     [rsp+68h+var_48], rax
0x14003d07d  call    WPP_SF_lSl
0x14003d082  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d089  mov     rax, [rbx+48h]
0x14003d08d  test    rax, rax
0x14003d090  jz      loc_14003D129
0x14003d096  cmp     rcx, r12
0x14003d099  jz      short loc_14003D0C1
0x14003d09b  test    [rcx+1Ch], r15b
0x14003d09f  jz      short loc_14003D0C1
0x14003d0a1  cmp     byte ptr [rcx+19h], 5
0x14003d0a5  jb      short loc_14003D0C1
0x14003d0a7  mov     r9d, [rbx+20h]
0x14003d0ab  mov     edx, 100h
0x14003d0b0  mov     rcx, [rcx+10h]
0x14003d0b4  mov     r8, r13
0x14003d0b7  mov     [rsp+68h+var_48], rax
0x14003d0bc  call    WPP_SF_DS
0x14003d0c1  mov     rcx, [rbx+48h]; lpFileName
0x14003d0c5  call    cs:__imp_DeleteFileW
0x14003d0cc  nop     dword ptr [rax+rax+00h]
0x14003d0d1  test    eax, eax
0x14003d0d3  jnz     short loc_14003D122
0x14003d0d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d0dc  cmp     rcx, r12
0x14003d0df  jz      short loc_14003D129
0x14003d0e1  test    [rcx+1Ch], r15b
0x14003d0e5  jz      short loc_14003D129
0x14003d0e7  cmp     [rcx+19h], dil
0x14003d0eb  jb      short loc_14003D129
0x14003d0ed  call    cs:__imp_GetLastError
0x14003d0f4  nop     dword ptr [rax+rax+00h]
0x14003d0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d100  mov     edx, 101h
0x14003d105  mov     r9d, [rbx+20h]
0x14003d109  mov     r8, r13
0x14003d10c  mov     [rsp+68h+var_40], eax
0x14003d110  mov     rax, [rbx+48h]
0x14003d114  mov     rcx, [rcx+10h]
0x14003d118  mov     [rsp+68h+var_48], rax
0x14003d11d  call    WPP_SF_lSl
0x14003d122  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d129  mov     rax, [rbx+0B8h]
0x14003d130  test    rax, rax
0x14003d133  jz      loc_14003D1D8
0x14003d139  cmp     dword ptr [rbx+0C0h], 0
0x14003d140  jnz     loc_14003D1D8
0x14003d146  cmp     rcx, r12
0x14003d149  jz      short loc_14003D171
0x14003d14b  test    [rcx+1Ch], r15b
0x14003d14f  jz      short loc_14003D171
0x14003d151  cmp     byte ptr [rcx+19h], 5
0x14003d155  jb      short loc_14003D171
0x14003d157  mov     r9d, [rbx+20h]
0x14003d15b  mov     edx, 102h
0x14003d160  mov     rcx, [rcx+10h]
0x14003d164  mov     r8, r13
0x14003d167  mov     [rsp+68h+var_48], rax
0x14003d16c  call    WPP_SF_DS
0x14003d171  mov     rcx, [rbx+0B8h]; lpFileName
0x14003d178  call    cs:__imp_DeleteFileW
0x14003d17f  nop     dword ptr [rax+rax+00h]
0x14003d184  test    eax, eax
0x14003d186  jnz     short loc_14003D1D8
0x14003d188  mov     rax, cs:WPP_GLOBAL_Control
0x14003d18f  cmp     rax, r12
0x14003d192  jz      short loc_14003D1D8
0x14003d194  test    [rax+1Ch], r15b
0x14003d198  jz      short loc_14003D1D8
0x14003d19a  cmp     [rax+19h], dil
0x14003d19e  jb      short loc_14003D1D8
0x14003d1a0  call    cs:__imp_GetLastError
0x14003d1a7  nop     dword ptr [rax+rax+00h]
0x14003d1ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d1b3  mov     edx, 103h
0x14003d1b8  mov     r9d, [rbx+20h]
0x14003d1bc  mov     r8, r13
0x14003d1bf  mov     [rsp+68h+var_40], eax
0x14003d1c3  mov     rax, [rbx+0B8h]
0x14003d1ca  mov     rcx, [rcx+10h]
0x14003d1ce  mov     [rsp+68h+var_48], rax
0x14003d1d3  call    WPP_SF_lSl
0x14003d1d8  lea     rcx, ?g_dwQueueCount@@3KA; unsigned int *
0x14003d1df  call    ?SafeDecIdleCounter@@YAXPEAK@Z; SafeDecIdleCounter(ulong *)
0x14003d1e4  test    ebp, ebp
0x14003d1e6  jz      short loc_14003D242
0x14003d1e8  mov     r9, [rbx+198h]; void *
0x14003d1ef  mov     edx, 17h; unsigned int
0x14003d1f4  mov     r8d, [rbx+20h]; unsigned int
0x14003d1f8  xor     ecx, ecx; unsigned int
0x14003d1fa  call    ?CreateFaxEvent@@YAHKKKPEAX@Z; CreateFaxEvent(ulong,ulong,ulong,void *)
0x14003d1ff  test    eax, eax
0x14003d201  jnz     short loc_14003D242
0x14003d203  mov     rax, cs:WPP_GLOBAL_Control
0x14003d20a  cmp     rax, r12
0x14003d20d  jz      short loc_14003D242
0x14003d20f  test    [rax+1Ch], r15b
0x14003d213  jz      short loc_14003D242
0x14003d215  cmp     [rax+19h], dil
0x14003d219  jb      short loc_14003D242
0x14003d21b  call    cs:__imp_GetLastError
0x14003d222  nop     dword ptr [rax+rax+00h]
0x14003d227  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d22e  mov     edx, 104h
  ... truncated ...
```
