# Wwan2SapWriteDeviceServiceData(WWAN_SAP *,_GUID const *,ulong,ulong,uchar const *,ulong *)

- ea: `0x1800b074c`
- end: `0x1800b09f0`
- name: `?Wwan2SapWriteDeviceServiceData@@YAKPEAUWWAN_SAP@@PEBU_GUID@@KKPEBEPEAK@Z`
- size: `676`
- prototype: `unsigned int __usercall@<eax>(LPCRITICAL_SECTION@<rcx>, const struct _GUID *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, const unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ac330`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800aaeec`
- `0x1800b074c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b099f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b099f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b07ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b07ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b09a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b09a9`

## string_xrefs

- `0x1800b081a`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b09be`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b080e`: `CreateEvent`
- `0x1800b0789`: `Wwan2SapWriteDeviceServiceData`
- `0x1800b07d2`: `Wwan2SapWriteDeviceServiceData`
- `0x1800b097c`: `Wwan2SapWriteDeviceServiceData`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapWriteDeviceServiceData(
        LPCRITICAL_SECTION a1,
        const struct _GUID *a2,
        unsigned int a3,
        unsigned int a4,
        const unsigned __int8 *a5,
        const struct _GUID *a6)
{
  const struct _GUID *v6; // r12
  const struct _GUID *v7; // r15
  struct _GUID *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v13; // rax
  MessageParams *v14; // rax
  MessageParams *v15; // rsi
  char *v16; // rdi
  struct _GUID **v17; // rdx
  unsigned int **v18; // rdx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdx
  const struct _GUID **v23; // rdx
  unsigned int v24; // edx
  DWORD v25; // eax
  struct _GUID *v26; // [rsp+30h] [rbp-10h] BYREF
  const struct _GUID *v27; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v28; // [rsp+70h] [rbp+30h] BYREF

  v6 = (const struct _GUID *)a4;
  v7 = (const struct _GUID *)a3;
  v28 = 0;
  if ( !a1 )
  {
    WwanLog::Error("Wwan2SapWriteDeviceServiceData", 0, L"[%p] Invalid parameters", 0);
    return 87;
  }
  v28 = WwanSapMgrValidateSessionOwnership(&g_sapMgr2, a1, a3, 2);
  if ( v28 )
  {
    WwanLog::Error("Wwan2SapWriteDeviceServiceData", 0, L"[%p] WwanSapMgrValidateSessionOwnership failed", a1);
    return v28;
  }
  EventW = (struct _GUID *)CreateEventW(0, 1, 0, 0);
  v26 = EventW;
  if ( EventW == (struct _GUID *)-1LL || (unsigned int *)((char *)&EventW->Data1 + 1) == (unsigned int *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x9B9u, "CreateEvent", LastError);
  }
  v13 = (MessageParams *)operator new(0x48u);
  v14 = MessageParams::MessageParams(v13);
  v15 = v14;
  v16 = (char *)v14 + 48;
  v27 = EventW;
  v17 = (struct _GUID **)*((_QWORD *)v14 + 7);
  if ( v17 == *((struct _GUID ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v17, &v27);
  }
  else
  {
    *v17 = EventW;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v27 = (const struct _GUID *)&v28;
  v18 = (unsigned int **)*((_QWORD *)v16 + 1);
  if ( v18 == *((unsigned int ***)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v18, &v27);
  }
  else
  {
    *v18 = &v28;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v27 = a2;
  v19 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v19 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v19, &v27);
  }
  else
  {
    *v19 = a2;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v27 = v7;
  v20 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v20 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v20, &v27);
  }
  else
  {
    *v20 = v7;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v27 = v6;
  v21 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v21 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v21, &v27);
  }
  else
  {
    *v21 = v6;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v27 = (const struct _GUID *)a5;
  v22 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v22 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v22, &v27);
  }
  else
  {
    *v22 = a5;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v27 = a6;
  v23 = (const struct _GUID **)*((_QWORD *)v16 + 1);
  if ( v23 == *((const struct _GUID ***)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v23, &v27);
  }
  else
  {
    *v23 = a6;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  if ( !(unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(34, v15) )
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v25 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x9CEu, "WaitForSingleObject", v25);
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v26);
    return v28;
  }
  if ( v15 )
    MessageParams::`scalar deleting destructor'(v15, v24);
  WwanLog::Error("Wwan2SapWriteDeviceServiceData", 0, L"Notification dispatcher: Failed to Queue Message");
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v26);
  return 31;
}

```

## disassembly

```asm
0x1800b074c  mov     [rsp-28h+arg_8], rbx
0x1800b0751  mov     [rsp-28h+arg_10], rsi
0x1800b0756  push    rbp
0x1800b0757  push    rdi
0x1800b0758  push    r12
0x1800b075a  push    r14
0x1800b075c  push    r15
0x1800b075e  mov     rbp, rsp
0x1800b0761  sub     rsp, 40h
0x1800b0765  mov     r12d, r9d
0x1800b0768  mov     r15d, r8d
0x1800b076b  mov     r14, rdx
0x1800b076e  mov     rbx, rcx
0x1800b0771  mov     [rbp+arg_0], 0
0x1800b0778  test    rcx, rcx
0x1800b077b  jnz     short loc_1800B079D
0x1800b077d  xor     r9d, r9d
0x1800b0780  lea     r8, aPInvalidParame; "[%p] Invalid parameters"
0x1800b0787  xor     edx, edx; struct _GUID *
0x1800b0789  lea     rcx, aWwan2sapwrited; "Wwan2SapWriteDeviceServiceData"
0x1800b0790  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b0795  lea     eax, [rbx+57h]
0x1800b0798  jmp     loc_1800B09D7
0x1800b079d  mov     r9d, 2
0x1800b07a3  mov     [rsp+40h+var_18], r9d; int
0x1800b07a8  mov     [rsp+40h+var_20], r15d; int
0x1800b07ad  mov     r8, r14
0x1800b07b0  mov     rdx, rbx; LPCRITICAL_SECTION
0x1800b07b3  lea     rcx, ?g_sapMgr2@@3U_WWAN_SAP_MGR@@A; lpCriticalSection
0x1800b07ba  call    _WwanSapMgrValidateSessionOwnership
0x1800b07bf  mov     [rbp+arg_0], eax
0x1800b07c2  test    eax, eax
0x1800b07c4  jz      short loc_1800B07E3
0x1800b07c6  mov     r9, rbx
0x1800b07c9  lea     r8, aPWwansapmgrval; "[%p] WwanSapMgrValidateSessionOwnership"...
0x1800b07d0  xor     edx, edx; struct _GUID *
0x1800b07d2  lea     rcx, aWwan2sapwrited; "Wwan2SapWriteDeviceServiceData"
0x1800b07d9  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b07de  jmp     loc_1800B09D4
0x1800b07e3  xor     r9d, r9d; lpName
0x1800b07e6  xor     r8d, r8d; bInitialState
0x1800b07e9  lea     edx, [r9+1]; bManualReset
0x1800b07ed  xor     ecx, ecx; lpEventAttributes
0x1800b07ef  call    cs:__imp_CreateEventW
0x1800b07f5  mov     rbx, rax
0x1800b07f8  mov     [rbp+var_10], rax
0x1800b07fc  inc     rax
0x1800b07ff  cmp     rax, 1
0x1800b0803  ja      short loc_1800B0826
0x1800b0805  call    cs:__imp_GetLastError
0x1800b080b  mov     r9d, eax; unsigned int
0x1800b080e  lea     r8, aCreateevent; "CreateEvent"
0x1800b0815  mov     edx, 9B9h; unsigned int
0x1800b081a  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b0821  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0826  mov     ecx, 48h ; 'H'; Size
0x1800b082b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b0830  mov     [rbp+var_8], rax
0x1800b0834  mov     rcx, rax; this
0x1800b0837  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b083c  mov     rsi, rax
0x1800b083f  lea     rdi, [rax+30h]
0x1800b0843  mov     [rbp+var_8], rbx
0x1800b0847  mov     rdx, [rdi+8]
0x1800b084b  cmp     rdx, [rdi+10h]
0x1800b084f  jz      short loc_1800B085B
0x1800b0851  mov     [rdx], rbx
0x1800b0854  add     qword ptr [rdi+8], 8
0x1800b0859  jmp     short loc_1800B0867
0x1800b085b  lea     r8, [rbp+var_8]
0x1800b085f  mov     rcx, rdi
0x1800b0862  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0867  lea     rax, [rbp+arg_0]
0x1800b086b  mov     [rbp+var_8], rax
0x1800b086f  mov     rdx, [rdi+8]
0x1800b0873  cmp     rdx, [rdi+10h]
0x1800b0877  jz      short loc_1800B0887
0x1800b0879  lea     rax, [rbp+arg_0]
0x1800b087d  mov     [rdx], rax
0x1800b0880  add     qword ptr [rdi+8], 8
0x1800b0885  jmp     short loc_1800B0893
0x1800b0887  lea     r8, [rbp+var_8]
0x1800b088b  mov     rcx, rdi
0x1800b088e  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0893  mov     [rbp+var_8], r14
0x1800b0897  mov     rdx, [rdi+8]
0x1800b089b  cmp     rdx, [rdi+10h]
0x1800b089f  jz      short loc_1800B08AB
0x1800b08a1  mov     [rdx], r14
0x1800b08a4  add     qword ptr [rdi+8], 8
0x1800b08a9  jmp     short loc_1800B08B7
0x1800b08ab  lea     r8, [rbp+var_8]
0x1800b08af  mov     rcx, rdi
0x1800b08b2  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b08b7  mov     rax, r15
0x1800b08ba  mov     [rbp+var_8], rax
0x1800b08be  mov     rdx, [rdi+8]
0x1800b08c2  cmp     rdx, [rdi+10h]
0x1800b08c6  jz      short loc_1800B08D2
0x1800b08c8  mov     [rdx], rax
0x1800b08cb  add     qword ptr [rdi+8], 8
0x1800b08d0  jmp     short loc_1800B08DE
0x1800b08d2  lea     r8, [rbp+var_8]
0x1800b08d6  mov     rcx, rdi
0x1800b08d9  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b08de  mov     rax, r12
0x1800b08e1  mov     [rbp+var_8], rax
0x1800b08e5  mov     rdx, [rdi+8]
0x1800b08e9  cmp     rdx, [rdi+10h]
0x1800b08ed  jz      short loc_1800B08F9
0x1800b08ef  mov     [rdx], rax
0x1800b08f2  add     qword ptr [rdi+8], 8
0x1800b08f7  jmp     short loc_1800B0905
0x1800b08f9  lea     r8, [rbp+var_8]
0x1800b08fd  mov     rcx, rdi
0x1800b0900  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0905  mov     rax, [rbp+arg_20]
0x1800b0909  mov     [rbp+var_8], rax
0x1800b090d  mov     rdx, [rdi+8]
0x1800b0911  cmp     rdx, [rdi+10h]
0x1800b0915  jz      short loc_1800B0921
0x1800b0917  mov     [rdx], rax
0x1800b091a  add     qword ptr [rdi+8], 8
0x1800b091f  jmp     short loc_1800B092D
0x1800b0921  lea     r8, [rbp+var_8]
0x1800b0925  mov     rcx, rdi
0x1800b0928  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b092d  mov     rax, [rbp+arg_28]
0x1800b0931  mov     [rbp+var_8], rax
0x1800b0935  mov     rdx, [rdi+8]
0x1800b0939  cmp     rdx, [rdi+10h]
0x1800b093d  jz      short loc_1800B0949
0x1800b093f  mov     [rdx], rax
0x1800b0942  add     qword ptr [rdi+8], 8
0x1800b0947  jmp     short loc_1800B0955
0x1800b0949  lea     r8, [rbp+var_8]
0x1800b094d  mov     rcx, rdi
0x1800b0950  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0955  mov     rdx, rsi
0x1800b0958  mov     ecx, 22h ; '"'
0x1800b095d  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b0962  test    eax, eax
0x1800b0964  jz      short loc_1800B0999
0x1800b0966  test    rsi, rsi
0x1800b0969  jz      short loc_1800B0973
0x1800b096b  mov     rcx, rsi; this
0x1800b096e  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b0973  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b097a  xor     edx, edx; struct _GUID *
0x1800b097c  lea     rcx, aWwan2sapwrited; "Wwan2SapWriteDeviceServiceData"
0x1800b0983  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b0988  nop
0x1800b0989  lea     rcx, [rbp+var_10]
0x1800b098d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b0992  mov     eax, 1Fh
0x1800b0997  jmp     short loc_1800B09D7
0x1800b0999  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b099c  mov     rcx, rbx; hHandle
0x1800b099f  call    cs:__imp_WaitForSingleObject
0x1800b09a5  test    eax, eax
0x1800b09a7  jz      short loc_1800B09CB
0x1800b09a9  call    cs:__imp_GetLastError
0x1800b09af  mov     r9d, eax; unsigned int
0x1800b09b2  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b09b9  mov     edx, 9CEh; unsigned int
0x1800b09be  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b09c5  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b09ca  nop
0x1800b09cb  lea     rcx, [rbp+var_10]
0x1800b09cf  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b09d4  mov     eax, [rbp+arg_0]
0x1800b09d7  lea     r11, [rsp+40h+var_s0]
0x1800b09dc  mov     rbx, [r11+38h]
0x1800b09e0  mov     rsi, [r11+40h]
0x1800b09e4  mov     rsp, r11
0x1800b09e7  pop     r15
0x1800b09e9  pop     r14
0x1800b09eb  pop     r12
0x1800b09ed  pop     rdi
0x1800b09ee  pop     rbp
0x1800b09ef  retn
```
