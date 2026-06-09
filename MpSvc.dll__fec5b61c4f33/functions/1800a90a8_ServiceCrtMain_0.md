# ServiceCrtMain_0

- ea: `0x1800a90a8`
- end: `0x1800a968d`
- name: `ServiceCrtMain_0`
- size: `1509`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a9fe0`

## callees

- `0x1800351ac`
- `0x180039034`
- `0x180039f80`
- `0x180039f9c`
- `0x18003b704`
- `0x18003b950`
- `0x18003b978`
- `0x180067aa0`
- `0x1800a35ac`
- `0x1800a571c`
- `0x1800a90a8`
- `0x1800a9750`
- `0x180107b38`
- `0x180107e50`
- `0x180350e30`
- `0x180473120`

## import_xrefs

- `MpClient!MpClientUtilExportFunctions` at `0x1800a90cd`
- `MpClient!MpClientUtilExportFunctions` at `0x1800a90cd`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a91c7`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a9247`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a92d4`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a93a4`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a9497`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a95aa`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a9654`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a91c7`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a9247`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a92d4`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a93a4`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a9497`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a95aa`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800a9654`
- `KERNEL32!CloseHandle` at `0x1800a9208`
- `KERNEL32!CloseHandle` at `0x1800a9286`
- `KERNEL32!CloseHandle` at `0x1800a9295`
- `KERNEL32!CloseHandle` at `0x1800a9356`
- `KERNEL32!CloseHandle` at `0x1800a9365`
- `KERNEL32!CloseHandle` at `0x1800a9449`
- `KERNEL32!CloseHandle` at `0x1800a9458`
- `KERNEL32!CloseHandle` at `0x1800a955c`
- `KERNEL32!CloseHandle` at `0x1800a956b`
- `KERNEL32!CloseHandle` at `0x1800a9606`
- `KERNEL32!CloseHandle` at `0x1800a9615`
- `KERNEL32!CloseHandle` at `0x1800a9208`
- `KERNEL32!CloseHandle` at `0x1800a9286`
- `KERNEL32!CloseHandle` at `0x1800a9295`
- `KERNEL32!CloseHandle` at `0x1800a9356`
- `KERNEL32!CloseHandle` at `0x1800a9365`
- `KERNEL32!CloseHandle` at `0x1800a9449`
- `KERNEL32!CloseHandle` at `0x1800a9458`
- `KERNEL32!CloseHandle` at `0x1800a955c`
- `KERNEL32!CloseHandle` at `0x1800a956b`
- `KERNEL32!CloseHandle` at `0x1800a9606`
- `KERNEL32!CloseHandle` at `0x1800a9615`

## pseudocode

```c
__int64 ServiceCrtMain_0()
{
  __int64 v0; // rax
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // eax
  unsigned int v5; // edi
  HANDLE v6; // rbx
  HANDLE v7; // rbx
  HANDLE v8; // rbx
  HANDLE v9; // rbx
  __int64 v10; // rbx
  int v11; // eax
  HANDLE v12; // rbx
  int v13; // eax
  __int64 v14; // rax
  HANDLE v15; // rbx
  __int64 v16; // rax
  HANDLE v17; // rbx
  __int64 v18; // [rsp+20h] [rbp-30h] BYREF
  __int64 v19; // [rsp+28h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+30h] [rbp-20h] BYREF
  HANDLE v21; // [rsp+38h] [rbp-18h] BYREF
  __int64 v22; // [rsp+40h] [rbp-10h] BYREF

  v0 = ((__int64 (*)(void))MpClientUtilExportFunctions)();
  (*(void (__fastcall **)(__int64))(v0 + 104))(1);
  sub_18003B704(0, 1, 0);
  v19 = 0;
  v1 = sub_18003B950(&v19);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 41, &MessageGuid, (unsigned int)v1);
    if ( v19 )
      sub_18003B978();
    return v2;
  }
  v4 = sub_1800A571C();
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 42, &MessageGuid, (unsigned int)v4);
    EnterCriticalSection(&stru_180600778);
    v6 = qword_1806007A8;
    qword_1806007A8 = 0;
    LeaveCriticalSection(&stru_180600778);
    sub_180350E30();
    if ( v6 )
      DeleteTimerQueueTimer(0, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( v19 )
      sub_18003B978();
    return v5;
  }
  hObject = 0;
  v5 = sub_1800351AC(&hObject, 0, 0, 0);
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( hObject )
      CloseHandle(hObject);
    EnterCriticalSection(&stru_180600778);
    v7 = qword_1806007A8;
    qword_1806007A8 = 0;
    LeaveCriticalSection(&stru_180600778);
    sub_180350E30();
    if ( v7 )
      DeleteTimerQueueTimer(0, v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( v19 )
      sub_18003B978();
    return v5;
  }
  v21 = 0;
  v5 = sub_1800351AC(&v21, 0, 0, 0);
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( v21 )
      CloseHandle(v21);
    if ( hObject )
      CloseHandle(hObject);
    EnterCriticalSection(&stru_180600778);
    v8 = qword_1806007A8;
    qword_1806007A8 = 0;
    LeaveCriticalSection(&stru_180600778);
    sub_180350E30();
    if ( v8 )
      DeleteTimerQueueTimer(0, v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( v19 )
      sub_18003B978();
    return v5;
  }
  v18 = 0;
  v5 = sub_1800A35AC(&v18);
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 43, &MessageGuid, v5);
    if ( v21 )
      CloseHandle(v21);
    if ( hObject )
      CloseHandle(hObject);
    EnterCriticalSection(&stru_180600778);
    v9 = qword_1806007A8;
    qword_1806007A8 = 0;
    LeaveCriticalSection(&stru_180600778);
    sub_180350E30();
    if ( v9 )
      DeleteTimerQueueTimer(0, v9, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( v19 )
      sub_18003B978();
    return v5;
  }
  v10 = v18;
  v22 = 0;
  v11 = sub_180039034(&v22, v18, L"WinDefend");
  v5 = v11;
  if ( v11 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 44, &MessageGuid, (unsigned int)v11);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    if ( v21 )
      CloseHandle(v21);
    if ( hObject )
      CloseHandle(hObject);
    EnterCriticalSection(&stru_180600778);
    v12 = qword_1806007A8;
    qword_1806007A8 = 0;
    LeaveCriticalSection(&stru_180600778);
    sub_180350E30();
    if ( v12 )
      DeleteTimerQueueTimer(0, v12, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( v19 )
      sub_18003B978();
    return v5;
  }
  qword_180600548 = hObject;
  hEvent = v21;
  qword_180600508 = v22;
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22);
  v5 = v13;
  if ( v13 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 45, &MessageGuid, (unsigned int)v13);
    v14 = sub_180107E50();
    sub_180107B38(v14);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    if ( v21 )
      CloseHandle(v21);
    if ( hObject )
      CloseHandle(hObject);
    EnterCriticalSection(&stru_180600778);
    v15 = qword_1806007A8;
    qword_1806007A8 = 0;
    LeaveCriticalSection(&stru_180600778);
    sub_180350E30();
    if ( v15 )
      DeleteTimerQueueTimer(0, v15, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( v19 )
      sub_18003B978();
    return v5;
  }
  v16 = sub_180107E50();
  sub_180107B38(v16);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  if ( v21 )
    CloseHandle(v21);
  if ( hObject )
    CloseHandle(hObject);
  EnterCriticalSection(&stru_180600778);
  v17 = qword_1806007A8;
  qword_1806007A8 = 0;
  LeaveCriticalSection(&stru_180600778);
  sub_180350E30();
  if ( v17 )
    DeleteTimerQueueTimer(0, v17, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( v19 )
    sub_18003B978();
  return 0;
}

```

## disassembly

```asm
0x1800a90a8  mov     [rsp-8+arg_0], rbx
0x1800a90ad  mov     [rsp-8+arg_8], rsi
0x1800a90b2  mov     [rsp-8+arg_10], rdi
0x1800a90b7  push    rbp
0x1800a90b8  mov     rbp, rsp
0x1800a90bb  sub     rsp, 50h
0x1800a90bf  mov     rax, cs:__security_cookie
0x1800a90c6  xor     rax, rsp
0x1800a90c9  mov     [rbp+var_8], rax
0x1800a90cd  call    cs:MpClientUtilExportFunctions
0x1800a90d3  mov     ecx, 1
0x1800a90d8  mov     rax, [rax+68h]
0x1800a90dc  call    cs:__guard_dispatch_icall_fptr
0x1800a90e2  xor     r9d, r9d
0x1800a90e5  xor     r8d, r8d
0x1800a90e8  lea     edx, [r9+1]
0x1800a90ec  xor     ecx, ecx
0x1800a90ee  call    sub_18003B704
0x1800a90f3  xor     esi, esi
0x1800a90f5  mov     [rbp+var_28], rsi
0x1800a90f9  lea     rcx, [rbp+var_28]
0x1800a90fd  call    sub_18003B950
0x1800a9102  mov     ebx, eax
0x1800a9104  test    eax, eax
0x1800a9106  jns     short loc_1800A914E
0x1800a9108  lea     rdx, NameType
0x1800a910f  mov     rcx, cs:NameType
0x1800a9116  cmp     rcx, rdx
0x1800a9119  jz      short loc_1800A9138
0x1800a911b  test    byte ptr [rcx+1Ch], 1
0x1800a911f  jz      short loc_1800A9138
0x1800a9121  lea     edx, [rsi+29h]
0x1800a9124  mov     r9d, eax
0x1800a9127  lea     r8, MessageGuid
0x1800a912e  mov     rcx, [rcx+10h]
0x1800a9132  call    sub_1800A9750
0x1800a9137  nop
0x1800a9138  mov     rcx, [rbp+var_28]
0x1800a913c  test    rcx, rcx
0x1800a913f  jz      short loc_1800A9147
0x1800a9141  call    sub_18003B978
0x1800a9146  nop
0x1800a9147  mov     eax, ebx
0x1800a9149  jmp     loc_1800A966C
0x1800a914e  call    sub_1800A571C
0x1800a9153  mov     edi, eax
0x1800a9155  test    eax, eax
0x1800a9157  jns     loc_1800A91E4
0x1800a915d  lea     rdx, NameType
0x1800a9164  mov     rcx, cs:NameType
0x1800a916b  cmp     rcx, rdx
0x1800a916e  jz      short loc_1800A918E
0x1800a9170  test    byte ptr [rcx+1Ch], 1
0x1800a9174  jz      short loc_1800A918E
0x1800a9176  mov     edx, 2Ah ; '*'
0x1800a917b  mov     r9d, eax
0x1800a917e  lea     r8, MessageGuid
0x1800a9185  mov     rcx, [rcx+10h]
0x1800a9189  call    sub_1800A9750
0x1800a918e  lea     rcx, stru_180600778; lpCriticalSection
0x1800a9195  call    EnterCriticalSection
0x1800a919a  mov     rbx, cs:qword_1806007A8
0x1800a91a1  mov     cs:qword_1806007A8, rsi
0x1800a91a8  lea     rcx, stru_180600778; lpCriticalSection
0x1800a91af  call    LeaveCriticalSection
0x1800a91b4  call    sub_180350E30
0x1800a91b9  test    rbx, rbx
0x1800a91bc  jz      short loc_1800A91CE
0x1800a91be  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800a91c2  mov     rdx, rbx; Timer
0x1800a91c5  xor     ecx, ecx; TimerQueue
0x1800a91c7  call    cs:DeleteTimerQueueTimer
0x1800a91cd  nop
0x1800a91ce  mov     rcx, [rbp+var_28]
0x1800a91d2  test    rcx, rcx
0x1800a91d5  jz      short loc_1800A91DD
0x1800a91d7  call    sub_18003B978
0x1800a91dc  nop
0x1800a91dd  mov     eax, edi
0x1800a91df  jmp     loc_1800A966C
0x1800a91e4  mov     [rbp+hObject], rsi
0x1800a91e8  xor     r9d, r9d
0x1800a91eb  xor     r8d, r8d
0x1800a91ee  xor     edx, edx
0x1800a91f0  lea     rcx, [rbp+hObject]
0x1800a91f4  call    sub_1800351AC
0x1800a91f9  mov     edi, eax
0x1800a91fb  test    eax, eax
0x1800a91fd  jns     short loc_1800A9262
0x1800a91ff  mov     rcx, [rbp+hObject]; hObject
0x1800a9203  test    rcx, rcx
0x1800a9206  jz      short loc_1800A920E
0x1800a9208  call    cs:CloseHandle
0x1800a920e  lea     rcx, stru_180600778; lpCriticalSection
0x1800a9215  call    EnterCriticalSection
0x1800a921a  mov     rbx, cs:qword_1806007A8
0x1800a9221  mov     cs:qword_1806007A8, rsi
0x1800a9228  lea     rcx, stru_180600778; lpCriticalSection
0x1800a922f  call    LeaveCriticalSection
0x1800a9234  call    sub_180350E30
0x1800a9239  test    rbx, rbx
0x1800a923c  jz      short loc_1800A924E
0x1800a923e  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800a9242  mov     rdx, rbx; Timer
0x1800a9245  xor     ecx, ecx; TimerQueue
0x1800a9247  call    cs:DeleteTimerQueueTimer
0x1800a924d  nop
0x1800a924e  mov     rcx, [rbp+var_28]
0x1800a9252  test    rcx, rcx
0x1800a9255  jz      short loc_1800A925D
0x1800a9257  call    sub_18003B978
0x1800a925c  nop
0x1800a925d  jmp     loc_1800A91DD
0x1800a9262  mov     [rbp+var_18], rsi
0x1800a9266  xor     r9d, r9d
0x1800a9269  xor     r8d, r8d
0x1800a926c  xor     edx, edx
0x1800a926e  lea     rcx, [rbp+var_18]
0x1800a9272  call    sub_1800351AC
0x1800a9277  mov     edi, eax
0x1800a9279  test    eax, eax
0x1800a927b  jns     short loc_1800A92EF
0x1800a927d  mov     rcx, [rbp+var_18]; hObject
0x1800a9281  test    rcx, rcx
0x1800a9284  jz      short loc_1800A928C
0x1800a9286  call    cs:CloseHandle
0x1800a928c  mov     rcx, [rbp+hObject]; hObject
0x1800a9290  test    rcx, rcx
0x1800a9293  jz      short loc_1800A929B
0x1800a9295  call    cs:CloseHandle
0x1800a929b  lea     rcx, stru_180600778; lpCriticalSection
0x1800a92a2  call    EnterCriticalSection
0x1800a92a7  mov     rbx, cs:qword_1806007A8
0x1800a92ae  mov     cs:qword_1806007A8, rsi
0x1800a92b5  lea     rcx, stru_180600778; lpCriticalSection
0x1800a92bc  call    LeaveCriticalSection
0x1800a92c1  call    sub_180350E30
0x1800a92c6  test    rbx, rbx
0x1800a92c9  jz      short loc_1800A92DB
0x1800a92cb  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800a92cf  mov     rdx, rbx; Timer
0x1800a92d2  xor     ecx, ecx; TimerQueue
0x1800a92d4  call    cs:DeleteTimerQueueTimer
0x1800a92da  nop
0x1800a92db  mov     rcx, [rbp+var_28]
0x1800a92df  test    rcx, rcx
0x1800a92e2  jz      short loc_1800A92EA
0x1800a92e4  call    sub_18003B978
0x1800a92e9  nop
0x1800a92ea  jmp     loc_1800A91DD
0x1800a92ef  mov     [rbp+var_30], rsi
0x1800a92f3  lea     rcx, [rbp+var_30]
0x1800a92f7  call    sub_1800A35AC
0x1800a92fc  mov     edi, eax
0x1800a92fe  test    eax, eax
0x1800a9300  jns     loc_1800A93BF
0x1800a9306  mov     rcx, [rbp+var_30]
0x1800a930a  test    rcx, rcx
0x1800a930d  jz      short loc_1800A931C
0x1800a930f  mov     rdx, [rcx]
0x1800a9312  mov     rax, [rdx+8]
0x1800a9316  call    cs:__guard_dispatch_icall_fptr
0x1800a931c  lea     rdx, NameType
0x1800a9323  mov     rcx, cs:NameType
0x1800a932a  cmp     rcx, rdx
0x1800a932d  jz      short loc_1800A934D
0x1800a932f  test    byte ptr [rcx+1Ch], 1
0x1800a9333  jz      short loc_1800A934D
0x1800a9335  mov     edx, 2Bh ; '+'
0x1800a933a  mov     r9d, edi
0x1800a933d  lea     r8, MessageGuid
0x1800a9344  mov     rcx, [rcx+10h]
0x1800a9348  call    sub_1800A9750
0x1800a934d  mov     rcx, [rbp+var_18]; hObject
0x1800a9351  test    rcx, rcx
0x1800a9354  jz      short loc_1800A935C
0x1800a9356  call    cs:CloseHandle
0x1800a935c  mov     rcx, [rbp+hObject]; hObject
0x1800a9360  test    rcx, rcx
0x1800a9363  jz      short loc_1800A936B
0x1800a9365  call    cs:CloseHandle
0x1800a936b  lea     rcx, stru_180600778; lpCriticalSection
0x1800a9372  call    EnterCriticalSection
0x1800a9377  mov     rbx, cs:qword_1806007A8
0x1800a937e  mov     cs:qword_1806007A8, rsi
0x1800a9385  lea     rcx, stru_180600778; lpCriticalSection
0x1800a938c  call    LeaveCriticalSection
0x1800a9391  call    sub_180350E30
0x1800a9396  test    rbx, rbx
0x1800a9399  jz      short loc_1800A93AB
0x1800a939b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800a939f  mov     rdx, rbx; Timer
0x1800a93a2  xor     ecx, ecx; TimerQueue
0x1800a93a4  call    cs:DeleteTimerQueueTimer
0x1800a93aa  nop
0x1800a93ab  mov     rcx, [rbp+var_28]
0x1800a93af  test    rcx, rcx
0x1800a93b2  jz      short loc_1800A93BA
0x1800a93b4  call    sub_18003B978
0x1800a93b9  nop
0x1800a93ba  jmp     loc_1800A91DD
0x1800a93bf  mov     rbx, [rbp+var_30]
0x1800a93c3  mov     [rbp+var_10], rsi
0x1800a93c7  lea     r8, aWindefend; "WinDefend"
0x1800a93ce  mov     rdx, rbx
0x1800a93d1  lea     rcx, [rbp+var_10]
0x1800a93d5  call    sub_180039034
0x1800a93da  mov     edi, eax
0x1800a93dc  test    eax, eax
0x1800a93de  jns     loc_1800A94B2
0x1800a93e4  lea     rdx, NameType
0x1800a93eb  mov     rcx, cs:NameType
0x1800a93f2  cmp     rcx, rdx
0x1800a93f5  jz      short loc_1800A9415
0x1800a93f7  test    byte ptr [rcx+1Ch], 1
0x1800a93fb  jz      short loc_1800A9415
0x1800a93fd  mov     edx, 2Ch ; ','
0x1800a9402  mov     r9d, eax
0x1800a9405  lea     r8, MessageGuid
0x1800a940c  mov     rcx, [rcx+10h]
0x1800a9410  call    sub_1800A9750
0x1800a9415  mov     rcx, [rbp+var_10]
0x1800a9419  test    rcx, rcx
0x1800a941c  jz      short loc_1800A942B
0x1800a941e  mov     rax, [rcx]
0x1800a9421  mov     rax, [rax+8]
0x1800a9425  call    cs:__guard_dispatch_icall_fptr
0x1800a942b  test    rbx, rbx
0x1800a942e  jz      short loc_1800A9440
0x1800a9430  mov     rax, [rbx]
0x1800a9433  mov     rcx, rbx
0x1800a9436  mov     rax, [rax+8]
0x1800a943a  call    cs:__guard_dispatch_icall_fptr
0x1800a9440  mov     rcx, [rbp+var_18]; hObject
0x1800a9444  test    rcx, rcx
0x1800a9447  jz      short loc_1800A944F
0x1800a9449  call    cs:CloseHandle
0x1800a944f  mov     rcx, [rbp+hObject]; hObject
0x1800a9453  test    rcx, rcx
0x1800a9456  jz      short loc_1800A945E
0x1800a9458  call    cs:CloseHandle
0x1800a945e  lea     rcx, stru_180600778; lpCriticalSection
0x1800a9465  call    EnterCriticalSection
0x1800a946a  mov     rbx, cs:qword_1806007A8
0x1800a9471  mov     cs:qword_1806007A8, rsi
0x1800a9478  lea     rcx, stru_180600778; lpCriticalSection
0x1800a947f  call    LeaveCriticalSection
0x1800a9484  call    sub_180350E30
0x1800a9489  test    rbx, rbx
0x1800a948c  jz      short loc_1800A949E
0x1800a948e  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800a9492  mov     rdx, rbx; Timer
0x1800a9495  xor     ecx, ecx; TimerQueue
0x1800a9497  call    cs:DeleteTimerQueueTimer
0x1800a949d  nop
0x1800a949e  mov     rcx, [rbp+var_28]
0x1800a94a2  test    rcx, rcx
0x1800a94a5  jz      short loc_1800A94AD
0x1800a94a7  call    sub_18003B978
0x1800a94ac  nop
0x1800a94ad  jmp     loc_1800A91DD
0x1800a94b2  mov     rax, [rbp+hObject]
0x1800a94b6  mov     cs:qword_180600548, rax
0x1800a94bd  mov     rax, [rbp+var_18]
0x1800a94c1  mov     cs:hEvent, rax
0x1800a94c8  mov     rcx, [rbp+var_10]
0x1800a94cc  mov     cs:qword_180600508, rcx
0x1800a94d3  mov     rax, [rcx]
0x1800a94d6  mov     rax, [rax+18h]
0x1800a94da  call    cs:__guard_dispatch_icall_fptr
0x1800a94e0  mov     edi, eax
0x1800a94e2  test    eax, eax
0x1800a94e4  jns     loc_1800A95C5
0x1800a94ea  lea     rdx, NameType
0x1800a94f1  mov     rcx, cs:NameType
0x1800a94f8  cmp     rcx, rdx
0x1800a94fb  jz      short loc_1800A951B
0x1800a94fd  test    byte ptr [rcx+1Ch], 1
0x1800a9501  jz      short loc_1800A951B
0x1800a9503  mov     edx, 2Dh ; '-'
0x1800a9508  mov     r9d, eax
0x1800a950b  lea     r8, MessageGuid
0x1800a9512  mov     rcx, [rcx+10h]
0x1800a9516  call    sub_1800A9750
0x1800a951b  call    sub_180107E50
0x1800a9520  mov     rcx, rax
0x1800a9523  call    sub_180107B38
0x1800a9528  mov     rcx, [rbp+var_10]
0x1800a952c  test    rcx, rcx
0x1800a952f  jz      short loc_1800A953E
0x1800a9531  mov     rax, [rcx]
0x1800a9534  mov     rax, [rax+8]
0x1800a9538  call    cs:__guard_dispatch_icall_fptr
0x1800a953e  test    rbx, rbx
0x1800a9541  jz      short loc_1800A9553
0x1800a9543  mov     rax, [rbx]
0x1800a9546  mov     rcx, rbx
0x1800a9549  mov     rax, [rax+8]
0x1800a954d  call    cs:__guard_dispatch_icall_fptr
0x1800a9553  mov     rcx, [rbp+var_18]; hObject
  ... truncated ...
```
