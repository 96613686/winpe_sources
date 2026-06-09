# WwanSapUiccCloseChannel(WWAN_SAP const *,_GUID const *,ulong,ulong,ulong,ulong,ulong *)

- ea: `0x1800b555c`
- end: `0x1800b57a2`
- name: `?WwanSapUiccCloseChannel@@YAKPEBUWWAN_SAP@@PEBU_GUID@@KKKKPEAK@Z`
- size: `582`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ad900`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b555c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b575a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b575a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b558e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b558e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b55a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b55a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5764`

## string_xrefs

- `0x1800b55b9`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5779`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b55ad`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapUiccCloseChannel(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7)
{
  MessageParams *v7; // r12
  MessageParams *v8; // r15
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v12; // rax
  MessageParams *v13; // rsi
  char *v14; // rdi
  MessageParams **v15; // rdx
  unsigned int **v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
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
  v7 = (MessageParams *)a4;
  v8 = (MessageParams *)a3;
  v29 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v28 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xB87u, "CreateEvent", LastError);
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
  v27 = v7;
  v19 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v19 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v19, &v27);
  }
  else
  {
    *v19 = v7;
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
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(46, v13) )
  {
    if ( v13 )
      MessageParams::`scalar deleting destructor'(v13, v23);
    WwanLog::Error("WwanSapUiccCloseChannel", 0, L"Notification dispatcher: Failed to Queue Message");
    v24 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v25 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xB9Eu, "WaitForSingleObject", v25);
    }
    v24 = v29;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v28);
  return v24;
}

```

## disassembly

```asm
0x1800b555c  mov     [rsp-38h+arg_0], rcx
0x1800b5561  push    rbp
0x1800b5562  push    rbx
0x1800b5563  push    rsi
0x1800b5564  push    rdi
0x1800b5565  push    r12
0x1800b5567  push    r14
0x1800b5569  push    r15
0x1800b556b  mov     rbp, rsp
0x1800b556e  sub     rsp, 20h
0x1800b5572  mov     r12d, r9d
0x1800b5575  mov     r15d, r8d
0x1800b5578  mov     r14, rdx
0x1800b557b  mov     [rbp+arg_10], 0
0x1800b5582  xor     r9d, r9d; lpName
0x1800b5585  xor     r8d, r8d; bInitialState
0x1800b5588  lea     edx, [r9+1]; bManualReset
0x1800b558c  xor     ecx, ecx; lpEventAttributes
0x1800b558e  call    cs:__imp_CreateEventW
0x1800b5594  mov     rbx, rax
0x1800b5597  mov     [rbp+arg_8], rax
0x1800b559b  inc     rax
0x1800b559e  cmp     rax, 1
0x1800b55a2  ja      short loc_1800B55C5
0x1800b55a4  call    cs:__imp_GetLastError
0x1800b55aa  mov     r9d, eax; unsigned int
0x1800b55ad  lea     r8, aCreateevent; "CreateEvent"
0x1800b55b4  mov     edx, 0B87h; unsigned int
0x1800b55b9  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b55c0  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b55c5  mov     ecx, 48h ; 'H'; Size
0x1800b55ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b55cf  mov     [rbp+arg_0], rax
0x1800b55d3  mov     rcx, rax; this
0x1800b55d6  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b55db  mov     rsi, rax
0x1800b55de  lea     rdi, [rax+30h]
0x1800b55e2  mov     [rbp+arg_0], rbx
0x1800b55e6  mov     rdx, [rdi+8]
0x1800b55ea  cmp     rdx, [rdi+10h]
0x1800b55ee  jz      short loc_1800B55FA
0x1800b55f0  mov     [rdx], rbx
0x1800b55f3  add     qword ptr [rdi+8], 8
0x1800b55f8  jmp     short loc_1800B5606
0x1800b55fa  lea     r8, [rbp+arg_0]
0x1800b55fe  mov     rcx, rdi
0x1800b5601  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5606  lea     rax, [rbp+arg_10]
0x1800b560a  mov     [rbp+arg_0], rax
0x1800b560e  mov     rdx, [rdi+8]
0x1800b5612  cmp     rdx, [rdi+10h]
0x1800b5616  jz      short loc_1800B5626
0x1800b5618  lea     rax, [rbp+arg_10]
0x1800b561c  mov     [rdx], rax
0x1800b561f  add     qword ptr [rdi+8], 8
0x1800b5624  jmp     short loc_1800B5632
0x1800b5626  lea     r8, [rbp+arg_0]
0x1800b562a  mov     rcx, rdi
0x1800b562d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5632  mov     [rbp+arg_0], r14
0x1800b5636  mov     rdx, [rdi+8]
0x1800b563a  cmp     rdx, [rdi+10h]
0x1800b563e  jz      short loc_1800B564A
0x1800b5640  mov     [rdx], r14
0x1800b5643  add     qword ptr [rdi+8], 8
0x1800b5648  jmp     short loc_1800B5656
0x1800b564a  lea     r8, [rbp+arg_0]
0x1800b564e  mov     rcx, rdi
0x1800b5651  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5656  mov     rax, r15
0x1800b5659  mov     [rbp+arg_0], rax
0x1800b565d  mov     rdx, [rdi+8]
0x1800b5661  cmp     rdx, [rdi+10h]
0x1800b5665  jz      short loc_1800B5671
0x1800b5667  mov     [rdx], rax
0x1800b566a  add     qword ptr [rdi+8], 8
0x1800b566f  jmp     short loc_1800B567D
0x1800b5671  lea     r8, [rbp+arg_0]
0x1800b5675  mov     rcx, rdi
0x1800b5678  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b567d  mov     rax, r12
0x1800b5680  mov     [rbp+arg_0], rax
0x1800b5684  mov     rdx, [rdi+8]
0x1800b5688  cmp     rdx, [rdi+10h]
0x1800b568c  jz      short loc_1800B5698
0x1800b568e  mov     [rdx], rax
0x1800b5691  add     qword ptr [rdi+8], 8
0x1800b5696  jmp     short loc_1800B56A4
0x1800b5698  lea     r8, [rbp+arg_0]
0x1800b569c  mov     rcx, rdi
0x1800b569f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b56a4  mov     eax, [rbp+arg_20]
0x1800b56a7  mov     [rbp+arg_0], rax
0x1800b56ab  mov     rdx, [rdi+8]
0x1800b56af  cmp     rdx, [rdi+10h]
0x1800b56b3  jz      short loc_1800B56BF
0x1800b56b5  mov     [rdx], rax
0x1800b56b8  add     qword ptr [rdi+8], 8
0x1800b56bd  jmp     short loc_1800B56CB
0x1800b56bf  lea     r8, [rbp+arg_0]
0x1800b56c3  mov     rcx, rdi
0x1800b56c6  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b56cb  mov     eax, [rbp+arg_28]
0x1800b56ce  mov     [rbp+arg_0], rax
0x1800b56d2  mov     rdx, [rdi+8]
0x1800b56d6  cmp     rdx, [rdi+10h]
0x1800b56da  jz      short loc_1800B56E6
0x1800b56dc  mov     [rdx], rax
0x1800b56df  add     qword ptr [rdi+8], 8
0x1800b56e4  jmp     short loc_1800B56F2
0x1800b56e6  lea     r8, [rbp+arg_0]
0x1800b56ea  mov     rcx, rdi
0x1800b56ed  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b56f2  mov     rax, [rbp+arg_30]
0x1800b56f6  mov     [rbp+arg_0], rax
0x1800b56fa  mov     rdx, [rdi+8]
0x1800b56fe  cmp     rdx, [rdi+10h]
0x1800b5702  jz      short loc_1800B570E
0x1800b5704  mov     [rdx], rax
0x1800b5707  add     qword ptr [rdi+8], 8
0x1800b570c  jmp     short loc_1800B571A
0x1800b570e  lea     r8, [rbp+arg_0]
0x1800b5712  mov     rcx, rdi
0x1800b5715  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b571a  mov     rdx, rsi
0x1800b571d  mov     ecx, 2Eh ; '.'
0x1800b5722  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b5727  test    eax, eax
0x1800b5729  jz      short loc_1800B5754
0x1800b572b  test    rsi, rsi
0x1800b572e  jz      short loc_1800B5738
0x1800b5730  mov     rcx, rsi; this
0x1800b5733  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b5738  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b573f  xor     edx, edx; struct _GUID *
0x1800b5741  lea     rcx, aWwansapuiccclo; "WwanSapUiccCloseChannel"
0x1800b5748  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b574d  mov     ebx, 1Fh
0x1800b5752  jmp     short loc_1800B5788
0x1800b5754  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b5757  mov     rcx, rbx; hHandle
0x1800b575a  call    cs:__imp_WaitForSingleObject
0x1800b5760  test    eax, eax
0x1800b5762  jz      short loc_1800B5785
0x1800b5764  call    cs:__imp_GetLastError
0x1800b576a  mov     r9d, eax; unsigned int
0x1800b576d  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b5774  mov     edx, 0B9Eh; unsigned int
0x1800b5779  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5780  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5785  mov     ebx, [rbp+arg_10]
0x1800b5788  lea     rcx, [rbp+arg_8]
0x1800b578c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b5791  mov     eax, ebx
0x1800b5793  add     rsp, 20h
0x1800b5797  pop     r15
0x1800b5799  pop     r14
0x1800b579b  pop     r12
0x1800b579d  pop     rdi
0x1800b579e  pop     rsi
0x1800b579f  pop     rbx
0x1800b57a0  pop     rbp
0x1800b57a1  retn
```
