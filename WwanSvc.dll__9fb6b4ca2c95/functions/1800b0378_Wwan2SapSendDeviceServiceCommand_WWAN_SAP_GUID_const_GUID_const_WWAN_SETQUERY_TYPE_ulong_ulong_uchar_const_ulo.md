# Wwan2SapSendDeviceServiceCommand(WWAN_SAP *,_GUID const *,_GUID const *,WWAN_SETQUERY_TYPE,ulong,ulong,uchar const *,ulong *)

- ea: `0x1800b0378`
- end: `0x1800b069e`
- name: `?Wwan2SapSendDeviceServiceCommand@@YAKPEAUWWAN_SAP@@PEBU_GUID@@1W4WWAN_SETQUERY_TYPE@@KKPEBEPEAK@Z`
- size: `806`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800ac290`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b0378`
- `0x1800b651c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0655`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0655`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b03e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b03e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b03f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b065f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b03f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b065f`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800b041b`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800b041b`

## string_xrefs

- `0x1800b040b`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b043a`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b0674`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b03ff`: `CreateEvent`
- `0x1800b03b8`: `Wwan2SapSendDeviceServiceCommand`
- `0x1800b0632`: `Wwan2SapSendDeviceServiceCommand`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapSendDeviceServiceCommand(
        struct WWAN_SAP *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        MessageParams *a7,
        MessageParams *a8)
{
  MessageParams *v8; // r13
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  DWORD v15; // eax
  MessageParams *v16; // rax
  MessageParams *v17; // r14
  char *v18; // rdi
  MessageParams **v19; // rdx
  unsigned int **v20; // rdx
  struct WWAN_SAP **v21; // rdx
  const struct _GUID **v22; // rdx
  const struct _GUID **v23; // rdx
  _QWORD *v24; // rdx
  _QWORD *v25; // rdx
  _QWORD *v26; // rdx
  MessageParams **v27; // rdx
  MessageParams **v28; // rdx
  RPC_BINDING_HANDLE *v29; // rdx
  unsigned int v30; // edx
  DWORD v31; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-28h] BYREF
  MessageParams *v33; // [rsp+28h] [rbp-20h] BYREF
  MessageParams *v34[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v35; // [rsp+90h] [rbp+48h] BYREF

  v8 = (MessageParams *)a4;
  v35 = 0;
  Binding = 0;
  if ( a1 )
  {
    v35 = _wwan2SapValidateCommandSessionOpen(a1, a2, a3);
    EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
    v33 = EventW;
    if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
    {
      LastError = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x8D3u, "CreateEvent", LastError);
    }
    if ( RpcServerInqBindingHandle(&Binding) )
    {
      v15 = GetLastError();
      __FatalError(
        "onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c",
        0x8DAu,
        "RpcServerInqBindingHandle",
        v15);
    }
    v34[0] = (MessageParams *)operator new(0x48u);
    v16 = MessageParams::MessageParams(v34[0]);
    v17 = v16;
    v18 = (char *)v16 + 48;
    v34[0] = EventW;
    v19 = (MessageParams **)*((_QWORD *)v16 + 7);
    if ( v19 == *((MessageParams ***)v16 + 8) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v16 + 48, v19, v34);
    }
    else
    {
      *v19 = EventW;
      *((_QWORD *)v16 + 7) += 8LL;
    }
    v34[0] = (MessageParams *)&v35;
    v20 = (unsigned int **)*((_QWORD *)v18 + 1);
    if ( v20 == *((unsigned int ***)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v20, v34);
    }
    else
    {
      *v20 = &v35;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    v34[0] = a1;
    v21 = (struct WWAN_SAP **)*((_QWORD *)v18 + 1);
    if ( v21 == *((struct WWAN_SAP ***)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v21, v34);
    }
    else
    {
      *v21 = a1;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    v34[0] = (MessageParams *)a2;
    v22 = (const struct _GUID **)*((_QWORD *)v18 + 1);
    if ( v22 == *((const struct _GUID ***)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v22, v34);
    }
    else
    {
      *v22 = a2;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    v34[0] = (MessageParams *)a3;
    v23 = (const struct _GUID **)*((_QWORD *)v18 + 1);
    if ( v23 == *((const struct _GUID ***)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v23, v34);
    }
    else
    {
      *v23 = a3;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    v34[0] = v8;
    v24 = (_QWORD *)*((_QWORD *)v18 + 1);
    if ( v24 == *((_QWORD **)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v24, v34);
    }
    else
    {
      *v24 = v8;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    v34[0] = (MessageParams *)a5;
    v25 = (_QWORD *)*((_QWORD *)v18 + 1);
    if ( v25 == *((_QWORD **)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v25, v34);
    }
    else
    {
      *v25 = a5;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    v34[0] = (MessageParams *)a6;
    v26 = (_QWORD *)*((_QWORD *)v18 + 1);
    if ( v26 == *((_QWORD **)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v26, v34);
    }
    else
    {
      *v26 = a6;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    v34[0] = a7;
    v27 = (MessageParams **)*((_QWORD *)v18 + 1);
    if ( v27 == *((MessageParams ***)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v27, v34);
    }
    else
    {
      *v27 = a7;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    v34[0] = a8;
    v28 = (MessageParams **)*((_QWORD *)v18 + 1);
    if ( v28 == *((MessageParams ***)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v28, v34);
    }
    else
    {
      *v28 = a8;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    v29 = (RPC_BINDING_HANDLE *)*((_QWORD *)v18 + 1);
    if ( v29 == *((RPC_BINDING_HANDLE **)v18 + 2) )
    {
      std::vector<void *>::_Emplace_reallocate<void * const &>(v18, v29, &Binding);
    }
    else
    {
      *v29 = Binding;
      *((_QWORD *)v18 + 1) += 8LL;
    }
    if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(30, v17) )
    {
      if ( v17 )
        MessageParams::`scalar deleting destructor'(v17, v30);
      WwanLog::Error("Wwan2SapSendDeviceServiceCommand", 0, L"Notification dispatcher: Failed to Queue Message");
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v33);
      return 31;
    }
    else
    {
      if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
      {
        v31 = GetLastError();
        __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x8F4u, "WaitForSingleObject", v31);
      }
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v33);
      return v35;
    }
  }
  else
  {
    WwanLog::Error("Wwan2SapSendDeviceServiceCommand", 0, L"[%p] Invalid parameters", 0);
    return 87;
  }
}

```

## disassembly

```asm
0x1800b0378  push    rbp
0x1800b037a  push    rbx
0x1800b037b  push    rsi
0x1800b037c  push    rdi
0x1800b037d  push    r12
0x1800b037f  push    r13
0x1800b0381  push    r14
0x1800b0383  push    r15
0x1800b0385  mov     rbp, rsp
0x1800b0388  sub     rsp, 48h
0x1800b038c  mov     r13d, r9d
0x1800b038f  mov     r12, r8
0x1800b0392  mov     r15, rdx
0x1800b0395  mov     rsi, rcx
0x1800b0398  mov     [rbp+arg_0], 0
0x1800b039f  mov     [rbp+Binding], 0
0x1800b03a7  test    rcx, rcx
0x1800b03aa  jnz     short loc_1800B03CC
0x1800b03ac  xor     r9d, r9d
0x1800b03af  lea     r8, aPInvalidParame; "[%p] Invalid parameters"
0x1800b03b6  xor     edx, edx; struct _GUID *
0x1800b03b8  lea     rcx, aWwan2sapsendde; "Wwan2SapSendDeviceServiceCommand"
0x1800b03bf  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b03c4  lea     eax, [rsi+57h]
0x1800b03c7  jmp     loc_1800B068D
0x1800b03cc  call    ?_wwan2SapValidateCommandSessionOpen@@YAKPEAUWWAN_SAP@@PEBU_GUID@@1@Z; _wwan2SapValidateCommandSessionOpen(WWAN_SAP *,_GUID const *,_GUID const *)
0x1800b03d1  mov     [rbp+arg_0], eax
0x1800b03d4  xor     r9d, r9d; lpName
0x1800b03d7  xor     r8d, r8d; bInitialState
0x1800b03da  lea     edx, [r9+1]; bManualReset
0x1800b03de  xor     ecx, ecx; lpEventAttributes
0x1800b03e0  call    cs:__imp_CreateEventW
0x1800b03e6  mov     rbx, rax
0x1800b03e9  mov     [rbp+var_20], rax
0x1800b03ed  inc     rax
0x1800b03f0  cmp     rax, 1
0x1800b03f4  ja      short loc_1800B0417
0x1800b03f6  call    cs:__imp_GetLastError
0x1800b03fc  mov     r9d, eax; unsigned int
0x1800b03ff  lea     r8, aCreateevent; "CreateEvent"
0x1800b0406  mov     edx, 8D3h; unsigned int
0x1800b040b  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b0412  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0417  lea     rcx, [rbp+Binding]; Binding
0x1800b041b  call    cs:__imp_RpcServerInqBindingHandle
0x1800b0421  test    eax, eax
0x1800b0423  jz      short loc_1800B0446
0x1800b0425  call    cs:__imp_GetLastError
0x1800b042b  mov     r9d, eax; unsigned int
0x1800b042e  lea     r8, aRpcserverinqbi_0; "RpcServerInqBindingHandle"
0x1800b0435  mov     edx, 8DAh; unsigned int
0x1800b043a  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b0441  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0446  mov     ecx, 48h ; 'H'; Size
0x1800b044b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b0450  mov     [rbp+var_18], rax
0x1800b0454  mov     rcx, rax; this
0x1800b0457  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b045c  mov     r14, rax
0x1800b045f  lea     rdi, [rax+30h]
0x1800b0463  mov     [rbp+var_18], rbx
0x1800b0467  mov     rdx, [rdi+8]
0x1800b046b  cmp     rdx, [rdi+10h]
0x1800b046f  jz      short loc_1800B047B
0x1800b0471  mov     [rdx], rbx
0x1800b0474  add     qword ptr [rdi+8], 8
0x1800b0479  jmp     short loc_1800B0487
0x1800b047b  lea     r8, [rbp+var_18]
0x1800b047f  mov     rcx, rdi
0x1800b0482  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0487  lea     rax, [rbp+arg_0]
0x1800b048b  mov     [rbp+var_18], rax
0x1800b048f  mov     rdx, [rdi+8]
0x1800b0493  cmp     rdx, [rdi+10h]
0x1800b0497  jz      short loc_1800B04A7
0x1800b0499  lea     rax, [rbp+arg_0]
0x1800b049d  mov     [rdx], rax
0x1800b04a0  add     qword ptr [rdi+8], 8
0x1800b04a5  jmp     short loc_1800B04B3
0x1800b04a7  lea     r8, [rbp+var_18]
0x1800b04ab  mov     rcx, rdi
0x1800b04ae  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b04b3  mov     [rbp+var_18], rsi
0x1800b04b7  mov     rdx, [rdi+8]
0x1800b04bb  cmp     rdx, [rdi+10h]
0x1800b04bf  jz      short loc_1800B04CB
0x1800b04c1  mov     [rdx], rsi
0x1800b04c4  add     qword ptr [rdi+8], 8
0x1800b04c9  jmp     short loc_1800B04D7
0x1800b04cb  lea     r8, [rbp+var_18]
0x1800b04cf  mov     rcx, rdi
0x1800b04d2  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b04d7  mov     [rbp+var_18], r15
0x1800b04db  mov     rdx, [rdi+8]
0x1800b04df  cmp     rdx, [rdi+10h]
0x1800b04e3  jz      short loc_1800B04EF
0x1800b04e5  mov     [rdx], r15
0x1800b04e8  add     qword ptr [rdi+8], 8
0x1800b04ed  jmp     short loc_1800B04FB
0x1800b04ef  lea     r8, [rbp+var_18]
0x1800b04f3  mov     rcx, rdi
0x1800b04f6  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b04fb  mov     [rbp+var_18], r12
0x1800b04ff  mov     rdx, [rdi+8]
0x1800b0503  cmp     rdx, [rdi+10h]
0x1800b0507  jz      short loc_1800B0513
0x1800b0509  mov     [rdx], r12
0x1800b050c  add     qword ptr [rdi+8], 8
0x1800b0511  jmp     short loc_1800B051F
0x1800b0513  lea     r8, [rbp+var_18]
0x1800b0517  mov     rcx, rdi
0x1800b051a  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b051f  mov     rax, r13
0x1800b0522  mov     [rbp+var_18], rax
0x1800b0526  mov     rdx, [rdi+8]
0x1800b052a  cmp     rdx, [rdi+10h]
0x1800b052e  jz      short loc_1800B053A
0x1800b0530  mov     [rdx], rax
0x1800b0533  add     qword ptr [rdi+8], 8
0x1800b0538  jmp     short loc_1800B0546
0x1800b053a  lea     r8, [rbp+var_18]
0x1800b053e  mov     rcx, rdi
0x1800b0541  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0546  mov     eax, [rbp+arg_20]
0x1800b0549  mov     [rbp+var_18], rax
0x1800b054d  mov     rdx, [rdi+8]
0x1800b0551  cmp     rdx, [rdi+10h]
0x1800b0555  jz      short loc_1800B0561
0x1800b0557  mov     [rdx], rax
0x1800b055a  add     qword ptr [rdi+8], 8
0x1800b055f  jmp     short loc_1800B056D
0x1800b0561  lea     r8, [rbp+var_18]
0x1800b0565  mov     rcx, rdi
0x1800b0568  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b056d  mov     eax, [rbp+arg_28]
0x1800b0570  mov     [rbp+var_18], rax
0x1800b0574  mov     rdx, [rdi+8]
0x1800b0578  cmp     rdx, [rdi+10h]
0x1800b057c  jz      short loc_1800B0588
0x1800b057e  mov     [rdx], rax
0x1800b0581  add     qword ptr [rdi+8], 8
0x1800b0586  jmp     short loc_1800B0594
0x1800b0588  lea     r8, [rbp+var_18]
0x1800b058c  mov     rcx, rdi
0x1800b058f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0594  mov     rax, [rbp+arg_30]
0x1800b0598  mov     [rbp+var_18], rax
0x1800b059c  mov     rdx, [rdi+8]
0x1800b05a0  cmp     rdx, [rdi+10h]
0x1800b05a4  jz      short loc_1800B05B0
0x1800b05a6  mov     [rdx], rax
0x1800b05a9  add     qword ptr [rdi+8], 8
0x1800b05ae  jmp     short loc_1800B05BC
0x1800b05b0  lea     r8, [rbp+var_18]
0x1800b05b4  mov     rcx, rdi
0x1800b05b7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b05bc  mov     rax, [rbp+arg_38]
0x1800b05c3  mov     [rbp+var_18], rax
0x1800b05c7  mov     rdx, [rdi+8]
0x1800b05cb  cmp     rdx, [rdi+10h]
0x1800b05cf  jz      short loc_1800B05DB
0x1800b05d1  mov     [rdx], rax
0x1800b05d4  add     qword ptr [rdi+8], 8
0x1800b05d9  jmp     short loc_1800B05E7
0x1800b05db  lea     r8, [rbp+var_18]
0x1800b05df  mov     rcx, rdi
0x1800b05e2  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b05e7  mov     rdx, [rdi+8]
0x1800b05eb  cmp     rdx, [rdi+10h]
0x1800b05ef  jz      short loc_1800B05FF
0x1800b05f1  mov     rax, [rbp+Binding]
0x1800b05f5  mov     [rdx], rax
0x1800b05f8  add     qword ptr [rdi+8], 8
0x1800b05fd  jmp     short loc_1800B060B
0x1800b05ff  lea     r8, [rbp+Binding]
0x1800b0603  mov     rcx, rdi
0x1800b0606  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b060b  mov     rdx, r14
0x1800b060e  mov     ecx, 1Eh
0x1800b0613  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b0618  test    eax, eax
0x1800b061a  jz      short loc_1800B064F
0x1800b061c  test    r14, r14
0x1800b061f  jz      short loc_1800B0629
0x1800b0621  mov     rcx, r14; this
0x1800b0624  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b0629  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b0630  xor     edx, edx; struct _GUID *
0x1800b0632  lea     rcx, aWwan2sapsendde; "Wwan2SapSendDeviceServiceCommand"
0x1800b0639  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b063e  nop
0x1800b063f  lea     rcx, [rbp+var_20]
0x1800b0643  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b0648  mov     eax, 1Fh
0x1800b064d  jmp     short loc_1800B068D
0x1800b064f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b0652  mov     rcx, rbx; hHandle
0x1800b0655  call    cs:__imp_WaitForSingleObject
0x1800b065b  test    eax, eax
0x1800b065d  jz      short loc_1800B0681
0x1800b065f  call    cs:__imp_GetLastError
0x1800b0665  mov     r9d, eax; unsigned int
0x1800b0668  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b066f  mov     edx, 8F4h; unsigned int
0x1800b0674  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b067b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0680  nop
0x1800b0681  lea     rcx, [rbp+var_20]
0x1800b0685  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b068a  mov     eax, [rbp+arg_0]
0x1800b068d  add     rsp, 48h
0x1800b0691  pop     r15
0x1800b0693  pop     r14
0x1800b0695  pop     r13
0x1800b0697  pop     r12
0x1800b0699  pop     rdi
0x1800b069a  pop     rsi
0x1800b069b  pop     rbx
0x1800b069c  pop     rbp
0x1800b069d  retn
```
