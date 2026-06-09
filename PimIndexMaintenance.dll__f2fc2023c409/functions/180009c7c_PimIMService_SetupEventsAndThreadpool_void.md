# PimIMService::SetupEventsAndThreadpool(void)

- ea: `0x180009c7c`
- end: `0x18000a153`
- name: `?SetupEventsAndThreadpool@PimIMService@@QEAAJXZ`
- size: `1239`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x1800089c4`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180009c7c`
- `0x18000b614`
- `0x18000b634`
- `0x18000b654`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c94`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009cfe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009c94`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a05c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a05c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a126`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009d8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009d8d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009f5e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009fc3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000a028`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000a08d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000a0f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009f5e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009fc3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000a028`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000a08d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000a0f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180009ee2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180009ee2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180009ec0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180009ec0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180009e6e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180009e6e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009d70`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009d70`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180009f7b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180009fe0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a045`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a0aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a10f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180009f7b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180009fe0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a045`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a0aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a10f`

## string_xrefs

- `0x180009cdb`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180009d45`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::SetupEventsAndThreadpool(char *pv)
{
  HANDLE *v2; // rsi
  HANDLE EventW; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  HANDLE *v8; // rsi
  __int64 v9; // rcx
  HANDLE v10; // rdi
  signed int v11; // eax
  PTP_TIMER ThreadpoolTimer; // rsi
  struct _TP_TIMER *v13; // rax
  signed int v14; // eax
  __int64 *v15; // rax
  __int64 *v16; // rax
  struct _TP_POOL **v17; // r14
  struct _TP_POOL *Threadpool; // rsi
  signed int v19; // eax
  PTP_CLEANUP_GROUP *v20; // r14
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rsi
  signed int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rcx
  PTP_WORK ThreadpoolWork; // rsi
  struct _TP_WORK *v26; // rax
  signed int v27; // eax
  PTP_WORK v28; // rsi
  struct _TP_WORK *v29; // rax
  signed int v30; // eax
  PTP_WORK v31; // rsi
  struct _TP_WORK *v32; // rax
  signed int v33; // eax
  PTP_WORK v34; // rsi
  struct _TP_WORK *v35; // rax
  signed int v36; // eax
  PTP_WORK v37; // rsi
  struct _TP_WORK *v38; // rax
  signed int v39; // eax

  v2 = (HANDLE *)(pv + 304);
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW == *v2 )
  {
    EventW = *v2;
  }
  else
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((void **)pv + 38);
    *v2 = EventW;
  }
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = 1012;
LABEL_8:
    Log_HREvent(
      v5,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v6);
    return v5;
  }
  v8 = (HANDLE *)(pv + 312);
  v10 = CreateEventW(0, 1, 0, 0);
  if ( v10 == *((HANDLE *)pv + 39) )
  {
    v10 = *v8;
  }
  else
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((void **)pv + 39);
    *v8 = v10;
  }
  if ( !v10 )
  {
    v11 = GetLastError();
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    v6 = 1017;
    goto LABEL_8;
  }
  if ( *((_QWORD *)pv + 61) )
    Log_AssertionEvent(
      v9,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      1019);
  ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)PimIMService::_AggregateCacheBackupTimerCallback, pv, 0);
  v13 = (struct _TP_TIMER *)*((_QWORD *)pv + 61);
  if ( ThreadpoolTimer == v13 )
  {
    ThreadpoolTimer = (PTP_TIMER)*((_QWORD *)pv + 61);
  }
  else
  {
    if ( v13 )
      CloseThreadpoolTimer(*((PTP_TIMER *)pv + 61));
    *((_QWORD *)pv + 61) = ThreadpoolTimer;
  }
  if ( !ThreadpoolTimer )
  {
    v14 = GetLastError();
    v5 = v14;
    if ( v14 > 0 )
      v5 = (unsigned __int16)v14 | 0x80070000;
    v6 = 1021;
    goto LABEL_8;
  }
  v15 = qword_18002DF40;
  if ( qword_18002DF40 == *((__int64 **)pv + 65) )
    v15 = (__int64 *)*((_QWORD *)pv + 65);
  else
    *((_QWORD *)pv + 65) = qword_18002DF40;
  v15[1] = 0;
  *(_DWORD *)v15 = 3;
  v15[2] = 0;
  v15[3] = 0;
  v15[4] = 0;
  *((_DWORD *)v15 + 16) = 72;
  v15[5] = 0;
  v15[6] = 0;
  *((_DWORD *)v15 + 14) = 0;
  *((_DWORD *)v15 + 15) = 1;
  v16 = qword_18002DF90;
  if ( qword_18002DF90 == *((__int64 **)pv + 66) )
    v16 = (__int64 *)*((_QWORD *)pv + 66);
  else
    *((_QWORD *)pv + 66) = qword_18002DF90;
  *(_DWORD *)v16 = 3;
  v16[1] = 0;
  v16[2] = 0;
  v16[3] = 0;
  v16[4] = 0;
  v16[5] = 0;
  v16[6] = 0;
  *((_DWORD *)v16 + 14) = 0;
  *((_DWORD *)v16 + 15) = 1;
  *((_DWORD *)v16 + 16) = 72;
  *(_DWORD *)(*((_QWORD *)pv + 66) + 60LL) = 2;
  v17 = (struct _TP_POOL **)(pv + 512);
  Threadpool = CreateThreadpool(0);
  if ( Threadpool == *((struct _TP_POOL **)pv + 64) )
  {
    Threadpool = *v17;
  }
  else
  {
    tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),0>::_Delete((struct _TP_POOL **)pv + 64);
    *v17 = Threadpool;
  }
  if ( !Threadpool )
  {
    v19 = GetLastError();
    v5 = v19;
    if ( v19 > 0 )
      v5 = (unsigned __int16)v19 | 0x80070000;
    v6 = 1034;
    goto LABEL_8;
  }
  SetThreadpoolThreadMaximum(Threadpool, 1u);
  *(_QWORD *)(*((_QWORD *)pv + 65) + 8LL) = *v17;
  *(_QWORD *)(*((_QWORD *)pv + 66) + 8LL) = *v17;
  v20 = (PTP_CLEANUP_GROUP *)(pv + 536);
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  if ( ThreadpoolCleanupGroup == *((PTP_CLEANUP_GROUP *)pv + 67) )
  {
    ThreadpoolCleanupGroup = *v20;
  }
  else
  {
    tlx::auto_xxx<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&void CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),0>::_Delete((struct _TP_CLEANUP_GROUP **)pv + 67);
    *v20 = ThreadpoolCleanupGroup;
  }
  if ( !ThreadpoolCleanupGroup )
  {
    v22 = GetLastError();
    v5 = v22;
    if ( v22 > 0 )
      v5 = (unsigned __int16)v22 | 0x80070000;
    v6 = 1044;
    goto LABEL_8;
  }
  v23 = *((_QWORD *)pv + 65);
  *(_QWORD *)(v23 + 16) = ThreadpoolCleanupGroup;
  *(_QWORD *)(v23 + 24) = 0;
  v24 = *((_QWORD *)pv + 66);
  *(_QWORD *)(v24 + 16) = *v20;
  *(_QWORD *)(v24 + 24) = 0;
  ThreadpoolWork = CreateThreadpoolWork(PimIMService::UpdateStoresCallback, pv, *((PTP_CALLBACK_ENVIRON *)pv + 65));
  v26 = (struct _TP_WORK *)*((_QWORD *)pv + 68);
  if ( ThreadpoolWork == v26 )
  {
    ThreadpoolWork = (PTP_WORK)*((_QWORD *)pv + 68);
  }
  else
  {
    if ( v26 )
      CloseThreadpoolWork(*((PTP_WORK *)pv + 68));
    *((_QWORD *)pv + 68) = ThreadpoolWork;
  }
  if ( !ThreadpoolWork )
  {
    v27 = GetLastError();
    v5 = v27;
    if ( v27 > 0 )
      v5 = (unsigned __int16)v27 | 0x80070000;
    v6 = 1050;
    goto LABEL_8;
  }
  v28 = CreateThreadpoolWork(PimIMService::UpdateItemsCallback, pv, *((PTP_CALLBACK_ENVIRON *)pv + 65));
  v29 = (struct _TP_WORK *)*((_QWORD *)pv + 70);
  if ( v28 == v29 )
  {
    v28 = (PTP_WORK)*((_QWORD *)pv + 70);
  }
  else
  {
    if ( v29 )
      CloseThreadpoolWork(*((PTP_WORK *)pv + 70));
    *((_QWORD *)pv + 70) = v28;
  }
  if ( !v28 )
  {
    v30 = GetLastError();
    v5 = v30;
    if ( v30 > 0 )
      v5 = (unsigned __int16)v30 | 0x80070000;
    v6 = 1053;
    goto LABEL_8;
  }
  v31 = CreateThreadpoolWork(PimIMService::RebuildAggregateCacheCallback, pv, *((PTP_CALLBACK_ENVIRON *)pv + 65));
  v32 = (struct _TP_WORK *)*((_QWORD *)pv + 72);
  if ( v31 == v32 )
  {
    v31 = (PTP_WORK)*((_QWORD *)pv + 72);
  }
  else
  {
    if ( v32 )
      CloseThreadpoolWork(*((PTP_WORK *)pv + 72));
    *((_QWORD *)pv + 72) = v31;
  }
  if ( !v31 )
  {
    v33 = GetLastError();
    v5 = v33;
    if ( v33 > 0 )
      v5 = (unsigned __int16)v33 | 0x80070000;
    v6 = 1056;
    goto LABEL_8;
  }
  v34 = CreateThreadpoolWork(PimIMService::SuspendCallback, pv, *((PTP_CALLBACK_ENVIRON *)pv + 65));
  v35 = (struct _TP_WORK *)*((_QWORD *)pv + 74);
  if ( v34 == v35 )
  {
    v34 = (PTP_WORK)*((_QWORD *)pv + 74);
  }
  else
  {
    if ( v35 )
      CloseThreadpoolWork(*((PTP_WORK *)pv + 74));
    *((_QWORD *)pv + 74) = v34;
  }
  if ( !v34 )
  {
    v36 = GetLastError();
    v5 = v36;
    if ( v36 > 0 )
      v5 = (unsigned __int16)v36 | 0x80070000;
    v6 = 1059;
    goto LABEL_8;
  }
  v37 = CreateThreadpoolWork(PimIMService::OnBootCallback, pv, *((PTP_CALLBACK_ENVIRON *)pv + 65));
  v38 = (struct _TP_WORK *)*((_QWORD *)pv + 76);
  if ( v37 == v38 )
  {
    v37 = (PTP_WORK)*((_QWORD *)pv + 76);
  }
  else
  {
    if ( v38 )
      CloseThreadpoolWork(*((PTP_WORK *)pv + 76));
    *((_QWORD *)pv + 76) = v37;
  }
  if ( !v37 )
  {
    v39 = GetLastError();
    v5 = v39;
    if ( v39 > 0 )
      v5 = (unsigned __int16)v39 | 0x80070000;
    v6 = 1062;
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x180009c7c  push    rbx
0x180009c7e  push    rbp
0x180009c7f  push    rsi
0x180009c80  push    rdi
0x180009c81  push    r14
0x180009c83  sub     rsp, 30h
0x180009c87  mov     rbx, rcx
0x180009c8a  xor     r9d, r9d; lpName
0x180009c8d  xor     ecx, ecx; lpEventAttributes
0x180009c8f  xor     r8d, r8d; bInitialState
0x180009c92  xor     edx, edx; bManualReset
0x180009c94  call    cs:__imp_CreateEventW
0x180009c9a  lea     rsi, [rbx+130h]
0x180009ca1  mov     rdi, rax
0x180009ca4  cmp     rax, [rsi]
0x180009ca7  jz      short loc_180009CB6
0x180009ca9  mov     rcx, rsi
0x180009cac  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180009cb1  mov     [rsi], rdi
0x180009cb4  jmp     short loc_180009CB9
0x180009cb6  mov     rdi, [rsi]
0x180009cb9  xor     ebp, ebp
0x180009cbb  test    rdi, rdi
0x180009cbe  jnz     short loc_180009CF2
0x180009cc0  call    cs:__imp_GetLastError
0x180009cc6  mov     ebx, eax
0x180009cc8  test    eax, eax
0x180009cca  jle     short loc_180009CD5
0x180009ccc  movzx   ebx, ax
0x180009ccf  or      ebx, 80070000h
0x180009cd5  mov     r9d, 3F4h
0x180009cdb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009ce2  xor     edx, edx
0x180009ce4  mov     ecx, ebx
0x180009ce6  call    Log_HREvent
0x180009ceb  mov     eax, ebx
0x180009ced  jmp     loc_18000A148
0x180009cf2  xor     r9d, r9d; lpName
0x180009cf5  xor     r8d, r8d; bInitialState
0x180009cf8  xor     ecx, ecx; lpEventAttributes
0x180009cfa  lea     edx, [r9+1]; bManualReset
0x180009cfe  call    cs:__imp_CreateEventW
0x180009d04  lea     rsi, [rbx+138h]
0x180009d0b  mov     rdi, rax
0x180009d0e  cmp     rax, [rsi]
0x180009d11  jz      short loc_180009D20
0x180009d13  mov     rcx, rsi
0x180009d16  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180009d1b  mov     [rsi], rdi
0x180009d1e  jmp     short loc_180009D23
0x180009d20  mov     rdi, [rsi]
0x180009d23  test    rdi, rdi
0x180009d26  jnz     short loc_180009D45
0x180009d28  call    cs:__imp_GetLastError
0x180009d2e  mov     ebx, eax
0x180009d30  test    eax, eax
0x180009d32  jle     short loc_180009D3D
0x180009d34  movzx   ebx, ax
0x180009d37  or      ebx, 80070000h
0x180009d3d  mov     r9d, 3F9h
0x180009d43  jmp     short loc_180009CDB
0x180009d45  lea     rdi, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009d4c  cmp     [rbx+1E8h], rbp
0x180009d53  jz      short loc_180009D63
0x180009d55  mov     r8d, 3FBh
0x180009d5b  mov     rdx, rdi
0x180009d5e  call    Log_AssertionEvent
0x180009d63  xor     r8d, r8d; pcbe
0x180009d66  lea     rcx, ?_AggregateCacheBackupTimerCallback@PimIMService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009d6d  mov     rdx, rbx; pv
0x180009d70  call    cs:__imp_CreateThreadpoolTimer
0x180009d76  mov     rsi, rax
0x180009d79  mov     rax, [rbx+1E8h]
0x180009d80  cmp     rsi, rax
0x180009d83  jz      short loc_180009D9C
0x180009d85  test    rax, rax
0x180009d88  jz      short loc_180009D93
0x180009d8a  mov     rcx, rax; pti
0x180009d8d  call    cs:__imp_CloseThreadpoolTimer
0x180009d93  mov     [rbx+1E8h], rsi
0x180009d9a  jmp     short loc_180009D9F
0x180009d9c  mov     rsi, rax
0x180009d9f  test    rsi, rsi
0x180009da2  jnz     short loc_180009DC7
0x180009da4  call    cs:__imp_GetLastError
0x180009daa  mov     ebx, eax
0x180009dac  test    eax, eax
0x180009dae  jle     short loc_180009DB9
0x180009db0  movzx   ebx, ax
0x180009db3  or      ebx, 80070000h
0x180009db9  mov     r9d, 3FDh
0x180009dbf  mov     r8, rdi
0x180009dc2  jmp     loc_180009CE2
0x180009dc7  mov     rcx, [rbx+208h]
0x180009dce  lea     rax, qword_18002DF40
0x180009dd5  cmp     rax, rcx
0x180009dd8  jz      short loc_180009DE3
0x180009dda  mov     [rbx+208h], rax
0x180009de1  jmp     short loc_180009DE6
0x180009de3  mov     rax, rcx
0x180009de6  mov     edx, 3
0x180009deb  mov     [rax+8], rbp
0x180009def  mov     [rax], edx
0x180009df1  mov     [rax+10h], rbp
0x180009df5  mov     [rax+18h], rbp
0x180009df9  mov     [rax+20h], rbp
0x180009dfd  lea     r8d, [rdx+45h]
0x180009e01  mov     [rax+40h], r8d
0x180009e05  mov     [rax+28h], rbp
0x180009e09  mov     [rax+30h], rbp
0x180009e0d  mov     [rax+38h], ebp
0x180009e10  mov     dword ptr [rax+3Ch], 1
0x180009e17  lea     rax, qword_18002DF90
0x180009e1e  mov     rcx, [rbx+210h]
0x180009e25  cmp     rax, rcx
0x180009e28  jz      short loc_180009E33
0x180009e2a  mov     [rbx+210h], rax
0x180009e31  jmp     short loc_180009E36
0x180009e33  mov     rax, rcx
0x180009e36  mov     [rax], edx
0x180009e38  xor     ecx, ecx; reserved
0x180009e3a  mov     [rax+8], rbp
0x180009e3e  mov     [rax+10h], rbp
0x180009e42  mov     [rax+18h], rbp
0x180009e46  mov     [rax+20h], rbp
0x180009e4a  mov     [rax+28h], rbp
0x180009e4e  mov     [rax+30h], rbp
0x180009e52  mov     [rax+38h], ebp
0x180009e55  mov     dword ptr [rax+3Ch], 1
0x180009e5c  mov     [rax+40h], r8d
0x180009e60  mov     rax, [rbx+210h]
0x180009e67  mov     dword ptr [rax+3Ch], 2
0x180009e6e  call    cs:__imp_CreateThreadpool
0x180009e74  lea     r14, [rbx+200h]
0x180009e7b  mov     rsi, rax
0x180009e7e  cmp     rax, [r14]
0x180009e81  jz      short loc_180009E90
0x180009e83  mov     rcx, r14
0x180009e86  call    ?_Delete@?$auto_xxx@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),0>::_Delete(void)
0x180009e8b  mov     [r14], rsi
0x180009e8e  jmp     short loc_180009E93
0x180009e90  mov     rsi, [r14]
0x180009e93  test    rsi, rsi
0x180009e96  jnz     short loc_180009EB8
0x180009e98  call    cs:__imp_GetLastError
0x180009e9e  mov     ebx, eax
0x180009ea0  test    eax, eax
0x180009ea2  jle     short loc_180009EAD
0x180009ea4  movzx   ebx, ax
0x180009ea7  or      ebx, 80070000h
0x180009ead  mov     r9d, 40Ah
0x180009eb3  jmp     loc_180009DBF
0x180009eb8  mov     edx, 1; cthrdMost
0x180009ebd  mov     rcx, rsi; ptpp
0x180009ec0  call    cs:__imp_SetThreadpoolThreadMaximum
0x180009ec6  mov     rcx, [rbx+208h]
0x180009ecd  mov     rax, [r14]
0x180009ed0  mov     [rcx+8], rax
0x180009ed4  mov     rcx, [rbx+210h]
0x180009edb  mov     rax, [r14]
0x180009ede  mov     [rcx+8], rax
0x180009ee2  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180009ee8  lea     r14, [rbx+218h]
0x180009eef  mov     rsi, rax
0x180009ef2  cmp     rax, [r14]
0x180009ef5  jz      short loc_180009F04
0x180009ef7  mov     rcx, r14
0x180009efa  call    ?_Delete@?$auto_xxx@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?CloseThreadpoolCleanupGroup@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),0>::_Delete(void)
0x180009eff  mov     [r14], rsi
0x180009f02  jmp     short loc_180009F07
0x180009f04  mov     rsi, [r14]
0x180009f07  test    rsi, rsi
0x180009f0a  jnz     short loc_180009F2C
0x180009f0c  call    cs:__imp_GetLastError
0x180009f12  mov     ebx, eax
0x180009f14  test    eax, eax
0x180009f16  jle     short loc_180009F21
0x180009f18  movzx   ebx, ax
0x180009f1b  or      ebx, 80070000h
0x180009f21  mov     r9d, 414h
0x180009f27  jmp     loc_180009DBF
0x180009f2c  mov     rax, [rbx+208h]
0x180009f33  mov     rdx, rbx; pv
0x180009f36  mov     [rax+10h], rsi
0x180009f3a  mov     [rax+18h], rbp
0x180009f3e  mov     rcx, [rbx+210h]
0x180009f45  mov     rax, [r14]
0x180009f48  mov     [rcx+10h], rax
0x180009f4c  mov     [rcx+18h], rbp
0x180009f50  lea     rcx, ?UpdateStoresCallback@PimIMService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180009f57  mov     r8, [rbx+208h]; pcbe
0x180009f5e  call    cs:__imp_CreateThreadpoolWork
0x180009f64  mov     rsi, rax
0x180009f67  mov     rax, [rbx+220h]
0x180009f6e  cmp     rsi, rax
0x180009f71  jz      short loc_180009F8A
0x180009f73  test    rax, rax
0x180009f76  jz      short loc_180009F81
0x180009f78  mov     rcx, rax; pwk
0x180009f7b  call    cs:__imp_CloseThreadpoolWork
0x180009f81  mov     [rbx+220h], rsi
0x180009f88  jmp     short loc_180009F8D
0x180009f8a  mov     rsi, rax
0x180009f8d  test    rsi, rsi
0x180009f90  jnz     short loc_180009FB2
0x180009f92  call    cs:__imp_GetLastError
0x180009f98  mov     ebx, eax
0x180009f9a  test    eax, eax
0x180009f9c  jle     short loc_180009FA7
0x180009f9e  movzx   ebx, ax
0x180009fa1  or      ebx, 80070000h
0x180009fa7  mov     r9d, 41Ah
0x180009fad  jmp     loc_180009DBF
0x180009fb2  mov     r8, [rbx+208h]; pcbe
0x180009fb9  lea     rcx, ?UpdateItemsCallback@PimIMService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180009fc0  mov     rdx, rbx; pv
0x180009fc3  call    cs:__imp_CreateThreadpoolWork
0x180009fc9  mov     rsi, rax
0x180009fcc  mov     rax, [rbx+230h]
0x180009fd3  cmp     rsi, rax
0x180009fd6  jz      short loc_180009FEF
0x180009fd8  test    rax, rax
0x180009fdb  jz      short loc_180009FE6
0x180009fdd  mov     rcx, rax; pwk
0x180009fe0  call    cs:__imp_CloseThreadpoolWork
0x180009fe6  mov     [rbx+230h], rsi
0x180009fed  jmp     short loc_180009FF2
0x180009fef  mov     rsi, rax
0x180009ff2  test    rsi, rsi
0x180009ff5  jnz     short loc_18000A017
0x180009ff7  call    cs:__imp_GetLastError
0x180009ffd  mov     ebx, eax
0x180009fff  test    eax, eax
0x18000a001  jle     short loc_18000A00C
0x18000a003  movzx   ebx, ax
0x18000a006  or      ebx, 80070000h
0x18000a00c  mov     r9d, 41Dh
0x18000a012  jmp     loc_180009DBF
0x18000a017  mov     r8, [rbx+208h]; pcbe
0x18000a01e  lea     rcx, ?RebuildAggregateCacheCallback@PimIMService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000a025  mov     rdx, rbx; pv
0x18000a028  call    cs:__imp_CreateThreadpoolWork
0x18000a02e  mov     rsi, rax
0x18000a031  mov     rax, [rbx+240h]
0x18000a038  cmp     rsi, rax
0x18000a03b  jz      short loc_18000A054
0x18000a03d  test    rax, rax
0x18000a040  jz      short loc_18000A04B
0x18000a042  mov     rcx, rax; pwk
0x18000a045  call    cs:__imp_CloseThreadpoolWork
0x18000a04b  mov     [rbx+240h], rsi
0x18000a052  jmp     short loc_18000A057
0x18000a054  mov     rsi, rax
0x18000a057  test    rsi, rsi
0x18000a05a  jnz     short loc_18000A07C
0x18000a05c  call    cs:__imp_GetLastError
0x18000a062  mov     ebx, eax
0x18000a064  test    eax, eax
0x18000a066  jle     short loc_18000A071
0x18000a068  movzx   ebx, ax
0x18000a06b  or      ebx, 80070000h
0x18000a071  mov     r9d, 420h
0x18000a077  jmp     loc_180009DBF
0x18000a07c  mov     r8, [rbx+208h]; pcbe
0x18000a083  lea     rcx, ?SuspendCallback@PimIMService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000a08a  mov     rdx, rbx; pv
0x18000a08d  call    cs:__imp_CreateThreadpoolWork
0x18000a093  mov     rsi, rax
0x18000a096  mov     rax, [rbx+250h]
0x18000a09d  cmp     rsi, rax
0x18000a0a0  jz      short loc_18000A0B9
0x18000a0a2  test    rax, rax
0x18000a0a5  jz      short loc_18000A0B0
0x18000a0a7  mov     rcx, rax; pwk
0x18000a0aa  call    cs:__imp_CloseThreadpoolWork
0x18000a0b0  mov     [rbx+250h], rsi
0x18000a0b7  jmp     short loc_18000A0BC
0x18000a0b9  mov     rsi, rax
0x18000a0bc  test    rsi, rsi
0x18000a0bf  jnz     short loc_18000A0E1
0x18000a0c1  call    cs:__imp_GetLastError
0x18000a0c7  mov     ebx, eax
0x18000a0c9  test    eax, eax
0x18000a0cb  jle     short loc_18000A0D6
0x18000a0cd  movzx   ebx, ax
0x18000a0d0  or      ebx, 80070000h
0x18000a0d6  mov     r9d, 423h
0x18000a0dc  jmp     loc_180009DBF
0x18000a0e1  mov     r8, [rbx+208h]; pcbe
0x18000a0e8  lea     rcx, ?OnBootCallback@PimIMService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000a0ef  mov     rdx, rbx; pv
0x18000a0f2  call    cs:__imp_CreateThreadpoolWork
0x18000a0f8  mov     rsi, rax
0x18000a0fb  mov     rax, [rbx+260h]
0x18000a102  cmp     rsi, rax
0x18000a105  jz      short loc_18000A11E
0x18000a107  test    rax, rax
0x18000a10a  jz      short loc_18000A115
0x18000a10c  mov     rcx, rax; pwk
0x18000a10f  call    cs:__imp_CloseThreadpoolWork
  ... truncated ...
```
