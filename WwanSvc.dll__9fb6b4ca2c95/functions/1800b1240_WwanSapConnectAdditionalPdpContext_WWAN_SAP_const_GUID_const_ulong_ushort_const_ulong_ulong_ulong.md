# WwanSapConnectAdditionalPdpContext(WWAN_SAP const *,_GUID const *,ulong,ushort const *,ulong,ulong *,ulong *)

- ea: `0x1800b1240`
- end: `0x1800b1484`
- name: `?WwanSapConnectAdditionalPdpContext@@YAKPEBUWWAN_SAP@@PEBU_GUID@@KPEBGKPEAK3@Z`
- size: `580`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ac660`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b1240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b143c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b143c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1272`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1446`

## string_xrefs

- `0x1800b129d`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b145b`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1291`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapConnectAdditionalPdpContext(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        unsigned int a3,
        MessageParams *a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int *a7)
{
  MessageParams *v8; // r12
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v12; // rax
  MessageParams *v13; // rsi
  char *v14; // rdi
  MessageParams **v15; // rdx
  unsigned int **v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  MessageParams **v19; // rdx
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdx
  unsigned int v23; // edx
  unsigned int v24; // ebx
  DWORD v25; // eax
  MessageParams *v27; // [rsp+60h] [rbp+40h] BYREF
  MessageParams *v28; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+70h] [rbp+50h] BYREF

  v27 = a1;
  v8 = (MessageParams *)a3;
  v29 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v28 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x305u, "CreateEvent", LastError);
  }
  v27 = (MessageParams *)operator new(0x48u);
  v12 = MessageParams::MessageParams(v27);
  v13 = v12;
  v14 = (char *)v12 + 48;
  v27 = EventW;
  v15 = (MessageParams **)*((_QWORD *)v12 + 7);
  if ( v15 == *((MessageParams ***)v12 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v12 + 48, v15, &v27);
  }
  else
  {
    *v15 = EventW;
    *((_QWORD *)v12 + 7) += 8LL;
  }
  v27 = (MessageParams *)&v29;
  v16 = (unsigned int **)*((_QWORD *)v14 + 1);
  if ( v16 == *((unsigned int ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v16, &v27);
  }
  else
  {
    *v16 = &v29;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = (MessageParams *)a2;
  v17 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v17 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v17, &v27);
  }
  else
  {
    *v17 = a2;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = v8;
  v18 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v18 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v18, &v27);
  }
  else
  {
    *v18 = v8;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = a4;
  v19 = (MessageParams **)*((_QWORD *)v14 + 1);
  if ( v19 == *((MessageParams ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v19, &v27);
  }
  else
  {
    *v19 = a4;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = (MessageParams *)a5;
  v20 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v20 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v20, &v27);
  }
  else
  {
    *v20 = a5;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = (MessageParams *)a6;
  v21 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v21 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v21, &v27);
  }
  else
  {
    *v21 = a6;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = (MessageParams *)a7;
  v22 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v22 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v22, &v27);
  }
  else
  {
    *v22 = a7;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(7, v13) )
  {
    if ( v13 )
      MessageParams::`scalar deleting destructor'(v13, v23);
    WwanLog::Error("WwanSapConnectAdditionalPdpContext", 0, L"Notification dispatcher: Failed to Queue Message");
    v24 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v25 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x31Cu, "WaitForSingleObject", v25);
    }
    v24 = v29;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v28);
  return v24;
}

```

## disassembly

```asm
0x1800b1240  mov     [rsp-38h+arg_0], rcx
0x1800b1245  push    rbp
0x1800b1246  push    rbx
0x1800b1247  push    rsi
0x1800b1248  push    rdi
0x1800b1249  push    r12
0x1800b124b  push    r14
0x1800b124d  push    r15
0x1800b124f  mov     rbp, rsp
0x1800b1252  sub     rsp, 20h
0x1800b1256  mov     r15, r9
0x1800b1259  mov     r12d, r8d
0x1800b125c  mov     r14, rdx
0x1800b125f  mov     [rbp+arg_10], 0
0x1800b1266  xor     r9d, r9d; lpName
0x1800b1269  xor     r8d, r8d; bInitialState
0x1800b126c  lea     edx, [r9+1]; bManualReset
0x1800b1270  xor     ecx, ecx; lpEventAttributes
0x1800b1272  call    cs:__imp_CreateEventW
0x1800b1278  mov     rbx, rax
0x1800b127b  mov     [rbp+arg_8], rax
0x1800b127f  inc     rax
0x1800b1282  cmp     rax, 1
0x1800b1286  ja      short loc_1800B12A9
0x1800b1288  call    cs:__imp_GetLastError
0x1800b128e  mov     r9d, eax; unsigned int
0x1800b1291  lea     r8, aCreateevent; "CreateEvent"
0x1800b1298  mov     edx, 305h; unsigned int
0x1800b129d  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b12a4  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b12a9  mov     ecx, 48h ; 'H'; Size
0x1800b12ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b12b3  mov     [rbp+arg_0], rax
0x1800b12b7  mov     rcx, rax; this
0x1800b12ba  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b12bf  mov     rsi, rax
0x1800b12c2  lea     rdi, [rax+30h]
0x1800b12c6  mov     [rbp+arg_0], rbx
0x1800b12ca  mov     rdx, [rdi+8]
0x1800b12ce  cmp     rdx, [rdi+10h]
0x1800b12d2  jz      short loc_1800B12DE
0x1800b12d4  mov     [rdx], rbx
0x1800b12d7  add     qword ptr [rdi+8], 8
0x1800b12dc  jmp     short loc_1800B12EA
0x1800b12de  lea     r8, [rbp+arg_0]
0x1800b12e2  mov     rcx, rdi
0x1800b12e5  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b12ea  lea     rax, [rbp+arg_10]
0x1800b12ee  mov     [rbp+arg_0], rax
0x1800b12f2  mov     rdx, [rdi+8]
0x1800b12f6  cmp     rdx, [rdi+10h]
0x1800b12fa  jz      short loc_1800B130A
0x1800b12fc  lea     rax, [rbp+arg_10]
0x1800b1300  mov     [rdx], rax
0x1800b1303  add     qword ptr [rdi+8], 8
0x1800b1308  jmp     short loc_1800B1316
0x1800b130a  lea     r8, [rbp+arg_0]
0x1800b130e  mov     rcx, rdi
0x1800b1311  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1316  mov     [rbp+arg_0], r14
0x1800b131a  mov     rdx, [rdi+8]
0x1800b131e  cmp     rdx, [rdi+10h]
0x1800b1322  jz      short loc_1800B132E
0x1800b1324  mov     [rdx], r14
0x1800b1327  add     qword ptr [rdi+8], 8
0x1800b132c  jmp     short loc_1800B133A
0x1800b132e  lea     r8, [rbp+arg_0]
0x1800b1332  mov     rcx, rdi
0x1800b1335  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b133a  mov     rax, r12
0x1800b133d  mov     [rbp+arg_0], rax
0x1800b1341  mov     rdx, [rdi+8]
0x1800b1345  cmp     rdx, [rdi+10h]
0x1800b1349  jz      short loc_1800B1355
0x1800b134b  mov     [rdx], rax
0x1800b134e  add     qword ptr [rdi+8], 8
0x1800b1353  jmp     short loc_1800B1361
0x1800b1355  lea     r8, [rbp+arg_0]
0x1800b1359  mov     rcx, rdi
0x1800b135c  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1361  mov     [rbp+arg_0], r15
0x1800b1365  mov     rdx, [rdi+8]
0x1800b1369  cmp     rdx, [rdi+10h]
0x1800b136d  jz      short loc_1800B1379
0x1800b136f  mov     [rdx], r15
0x1800b1372  add     qword ptr [rdi+8], 8
0x1800b1377  jmp     short loc_1800B1385
0x1800b1379  lea     r8, [rbp+arg_0]
0x1800b137d  mov     rcx, rdi
0x1800b1380  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1385  mov     eax, [rbp+arg_20]
0x1800b1388  mov     [rbp+arg_0], rax
0x1800b138c  mov     rdx, [rdi+8]
0x1800b1390  cmp     rdx, [rdi+10h]
0x1800b1394  jz      short loc_1800B13A0
0x1800b1396  mov     [rdx], rax
0x1800b1399  add     qword ptr [rdi+8], 8
0x1800b139e  jmp     short loc_1800B13AC
0x1800b13a0  lea     r8, [rbp+arg_0]
0x1800b13a4  mov     rcx, rdi
0x1800b13a7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b13ac  mov     rax, [rbp+arg_28]
0x1800b13b0  mov     [rbp+arg_0], rax
0x1800b13b4  mov     rdx, [rdi+8]
0x1800b13b8  cmp     rdx, [rdi+10h]
0x1800b13bc  jz      short loc_1800B13C8
0x1800b13be  mov     [rdx], rax
0x1800b13c1  add     qword ptr [rdi+8], 8
0x1800b13c6  jmp     short loc_1800B13D4
0x1800b13c8  lea     r8, [rbp+arg_0]
0x1800b13cc  mov     rcx, rdi
0x1800b13cf  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b13d4  mov     rax, [rbp+arg_30]
0x1800b13d8  mov     [rbp+arg_0], rax
0x1800b13dc  mov     rdx, [rdi+8]
0x1800b13e0  cmp     rdx, [rdi+10h]
0x1800b13e4  jz      short loc_1800B13F0
0x1800b13e6  mov     [rdx], rax
0x1800b13e9  add     qword ptr [rdi+8], 8
0x1800b13ee  jmp     short loc_1800B13FC
0x1800b13f0  lea     r8, [rbp+arg_0]
0x1800b13f4  mov     rcx, rdi
0x1800b13f7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b13fc  mov     rdx, rsi
0x1800b13ff  mov     ecx, 7
0x1800b1404  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b1409  test    eax, eax
0x1800b140b  jz      short loc_1800B1436
0x1800b140d  test    rsi, rsi
0x1800b1410  jz      short loc_1800B141A
0x1800b1412  mov     rcx, rsi; this
0x1800b1415  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b141a  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b1421  xor     edx, edx; struct _GUID *
0x1800b1423  lea     rcx, aWwansapconnect; "WwanSapConnectAdditionalPdpContext"
0x1800b142a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b142f  mov     ebx, 1Fh
0x1800b1434  jmp     short loc_1800B146A
0x1800b1436  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b1439  mov     rcx, rbx; hHandle
0x1800b143c  call    cs:__imp_WaitForSingleObject
0x1800b1442  test    eax, eax
0x1800b1444  jz      short loc_1800B1467
0x1800b1446  call    cs:__imp_GetLastError
0x1800b144c  mov     r9d, eax; unsigned int
0x1800b144f  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b1456  mov     edx, 31Ch; unsigned int
0x1800b145b  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1462  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b1467  mov     ebx, [rbp+arg_10]
0x1800b146a  lea     rcx, [rbp+arg_8]
0x1800b146e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b1473  mov     eax, ebx
0x1800b1475  add     rsp, 20h
0x1800b1479  pop     r15
0x1800b147b  pop     r14
0x1800b147d  pop     r12
0x1800b147f  pop     rdi
0x1800b1480  pop     rsi
0x1800b1481  pop     rbx
0x1800b1482  pop     rbp
0x1800b1483  retn
```
