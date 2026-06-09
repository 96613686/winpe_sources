# WwanSapUiccOpenChannel(WWAN_SAP const *,_GUID const *,ulong,ulong,ulong,uchar const *,ulong,ulong *)

- ea: `0x1800b57a8`
- end: `0x1800b5a71`
- name: `?WwanSapUiccOpenChannel@@YAKPEBUWWAN_SAP@@PEBU_GUID@@KKKPEBEKPEAK@Z`
- size: `713`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, unsigned int, unsigned int, unsigned int, const unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ad960`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b57a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b5a29`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b5a29`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b57e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b57e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b57f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b57f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5a33`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800b581d`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800b581d`

## string_xrefs

- `0x1800b580d`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b583c`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5a48`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5801`: `CreateEvent`
- `0x1800b5a10`: `WwanSapUiccOpenChannel`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapUiccOpenChannel(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8)
{
  MessageParams *v8; // r12
  MessageParams *v9; // r15
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  DWORD v13; // eax
  MessageParams *v14; // rax
  MessageParams *v15; // rsi
  char *v16; // rdi
  MessageParams **v17; // rdx
  unsigned int **v18; // rdx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdx
  _QWORD *v23; // rdx
  _QWORD *v24; // rdx
  _QWORD *v25; // rdx
  RPC_BINDING_HANDLE *v26; // rdx
  unsigned int v27; // edx
  unsigned int v28; // ebx
  DWORD v29; // eax
  MessageParams *v31; // [rsp+20h] [rbp-10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+40h] BYREF
  MessageParams *v33; // [rsp+78h] [rbp+48h] BYREF
  unsigned int v34; // [rsp+80h] [rbp+50h] BYREF

  v8 = (MessageParams *)a4;
  v9 = (MessageParams *)a3;
  v34 = 0;
  Binding = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v31 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xB52u, "CreateEvent", LastError);
  }
  if ( RpcServerInqBindingHandle(&Binding) )
  {
    v13 = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xB59u, "RpcServerInqBindingHandle", v13);
  }
  v33 = (MessageParams *)operator new(0x48u);
  v14 = MessageParams::MessageParams(v33);
  v15 = v14;
  v16 = (char *)v14 + 48;
  v33 = EventW;
  v17 = (MessageParams **)*((_QWORD *)v14 + 7);
  if ( v17 == *((MessageParams ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v17, &v33);
  }
  else
  {
    *v17 = EventW;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v33 = (MessageParams *)&v34;
  v18 = (unsigned int **)*((_QWORD *)v16 + 1);
  if ( v18 == *((unsigned int ***)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v18, &v33);
  }
  else
  {
    *v18 = &v34;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v33 = (MessageParams *)a2;
  v19 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v19 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v19, &v33);
  }
  else
  {
    *v19 = a2;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v33 = v9;
  v20 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v20 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v20, &v33);
  }
  else
  {
    *v20 = v9;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v33 = v8;
  v21 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v21 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v21, &v33);
  }
  else
  {
    *v21 = v8;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v33 = (MessageParams *)a5;
  v22 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v22 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v22, &v33);
  }
  else
  {
    *v22 = a5;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v23 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v23 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v23, &a6);
  }
  else
  {
    *v23 = a6;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  a6 = (const unsigned __int8 *)a7;
  v24 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v24 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v24, &a6);
  }
  else
  {
    *v24 = a7;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  a6 = (const unsigned __int8 *)a8;
  v25 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v25 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v25, &a6);
  }
  else
  {
    *v25 = a8;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v26 = (RPC_BINDING_HANDLE *)*((_QWORD *)v16 + 1);
  if ( v26 == *((RPC_BINDING_HANDLE **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v26, &Binding);
  }
  else
  {
    *v26 = Binding;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(45, v15) )
  {
    if ( v15 )
      MessageParams::`scalar deleting destructor'(v15, v27);
    WwanLog::Error("WwanSapUiccOpenChannel", 0, L"Notification dispatcher: Failed to Queue Message");
    v28 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v29 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xB72u, "WaitForSingleObject", v29);
    }
    v28 = v34;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v31);
  return v28;
}

```

## disassembly

```asm
0x1800b57a8  mov     [rsp-38h+Binding], rcx
0x1800b57ad  push    rbp
0x1800b57ae  push    rbx
0x1800b57af  push    rsi
0x1800b57b0  push    rdi
0x1800b57b1  push    r12
0x1800b57b3  push    r14
0x1800b57b5  push    r15
0x1800b57b7  mov     rbp, rsp
0x1800b57ba  sub     rsp, 30h
0x1800b57be  mov     r12d, r9d
0x1800b57c1  mov     r15d, r8d
0x1800b57c4  mov     r14, rdx
0x1800b57c7  mov     [rbp+arg_10], 0
0x1800b57ce  mov     [rbp+Binding], 0
0x1800b57d6  xor     r9d, r9d; lpName
0x1800b57d9  xor     r8d, r8d; bInitialState
0x1800b57dc  lea     edx, [r9+1]; bManualReset
0x1800b57e0  xor     ecx, ecx; lpEventAttributes
0x1800b57e2  call    cs:__imp_CreateEventW
0x1800b57e8  mov     rbx, rax
0x1800b57eb  mov     [rbp+var_10], rax
0x1800b57ef  inc     rax
0x1800b57f2  cmp     rax, 1
0x1800b57f6  ja      short loc_1800B5819
0x1800b57f8  call    cs:__imp_GetLastError
0x1800b57fe  mov     r9d, eax; unsigned int
0x1800b5801  lea     r8, aCreateevent; "CreateEvent"
0x1800b5808  mov     edx, 0B52h; unsigned int
0x1800b580d  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5814  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5819  lea     rcx, [rbp+Binding]; Binding
0x1800b581d  call    cs:__imp_RpcServerInqBindingHandle
0x1800b5823  test    eax, eax
0x1800b5825  jz      short loc_1800B5848
0x1800b5827  call    cs:__imp_GetLastError
0x1800b582d  mov     r9d, eax; unsigned int
0x1800b5830  lea     r8, aRpcserverinqbi_0; "RpcServerInqBindingHandle"
0x1800b5837  mov     edx, 0B59h; unsigned int
0x1800b583c  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5843  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5848  mov     ecx, 48h ; 'H'; Size
0x1800b584d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b5852  mov     [rbp+arg_8], rax
0x1800b5856  mov     rcx, rax; this
0x1800b5859  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b585e  mov     rsi, rax
0x1800b5861  lea     rdi, [rax+30h]
0x1800b5865  mov     [rbp+arg_8], rbx
0x1800b5869  mov     rdx, [rdi+8]
0x1800b586d  cmp     rdx, [rdi+10h]
0x1800b5871  jz      short loc_1800B587D
0x1800b5873  mov     [rdx], rbx
0x1800b5876  add     qword ptr [rdi+8], 8
0x1800b587b  jmp     short loc_1800B5889
0x1800b587d  lea     r8, [rbp+arg_8]
0x1800b5881  mov     rcx, rdi
0x1800b5884  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5889  lea     rax, [rbp+arg_10]
0x1800b588d  mov     [rbp+arg_8], rax
0x1800b5891  mov     rdx, [rdi+8]
0x1800b5895  cmp     rdx, [rdi+10h]
0x1800b5899  jz      short loc_1800B58A9
0x1800b589b  lea     rax, [rbp+arg_10]
0x1800b589f  mov     [rdx], rax
0x1800b58a2  add     qword ptr [rdi+8], 8
0x1800b58a7  jmp     short loc_1800B58B5
0x1800b58a9  lea     r8, [rbp+arg_8]
0x1800b58ad  mov     rcx, rdi
0x1800b58b0  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b58b5  mov     [rbp+arg_8], r14
0x1800b58b9  mov     rdx, [rdi+8]
0x1800b58bd  cmp     rdx, [rdi+10h]
0x1800b58c1  jz      short loc_1800B58CD
0x1800b58c3  mov     [rdx], r14
0x1800b58c6  add     qword ptr [rdi+8], 8
0x1800b58cb  jmp     short loc_1800B58D9
0x1800b58cd  lea     r8, [rbp+arg_8]
0x1800b58d1  mov     rcx, rdi
0x1800b58d4  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b58d9  mov     rax, r15
0x1800b58dc  mov     [rbp+arg_8], rax
0x1800b58e0  mov     rdx, [rdi+8]
0x1800b58e4  cmp     rdx, [rdi+10h]
0x1800b58e8  jz      short loc_1800B58F4
0x1800b58ea  mov     [rdx], rax
0x1800b58ed  add     qword ptr [rdi+8], 8
0x1800b58f2  jmp     short loc_1800B5900
0x1800b58f4  lea     r8, [rbp+arg_8]
0x1800b58f8  mov     rcx, rdi
0x1800b58fb  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5900  mov     rax, r12
0x1800b5903  mov     [rbp+arg_8], rax
0x1800b5907  mov     rdx, [rdi+8]
0x1800b590b  cmp     rdx, [rdi+10h]
0x1800b590f  jz      short loc_1800B591B
0x1800b5911  mov     [rdx], rax
0x1800b5914  add     qword ptr [rdi+8], 8
0x1800b5919  jmp     short loc_1800B5927
0x1800b591b  lea     r8, [rbp+arg_8]
0x1800b591f  mov     rcx, rdi
0x1800b5922  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5927  mov     eax, [rbp+arg_20]
0x1800b592a  mov     [rbp+arg_8], rax
0x1800b592e  mov     rdx, [rdi+8]
0x1800b5932  cmp     rdx, [rdi+10h]
0x1800b5936  jz      short loc_1800B5942
0x1800b5938  mov     [rdx], rax
0x1800b593b  add     qword ptr [rdi+8], 8
0x1800b5940  jmp     short loc_1800B594E
0x1800b5942  lea     r8, [rbp+arg_8]
0x1800b5946  mov     rcx, rdi
0x1800b5949  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b594e  mov     rax, [rbp+arg_28]
0x1800b5952  mov     [rbp+arg_28], rax
0x1800b5956  mov     rdx, [rdi+8]
0x1800b595a  cmp     rdx, [rdi+10h]
0x1800b595e  jz      short loc_1800B596A
0x1800b5960  mov     [rdx], rax
0x1800b5963  add     qword ptr [rdi+8], 8
0x1800b5968  jmp     short loc_1800B5976
0x1800b596a  lea     r8, [rbp+arg_28]
0x1800b596e  mov     rcx, rdi
0x1800b5971  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5976  mov     eax, [rbp+arg_30]
0x1800b5979  mov     [rbp+arg_28], rax
0x1800b597d  mov     rdx, [rdi+8]
0x1800b5981  cmp     rdx, [rdi+10h]
0x1800b5985  jz      short loc_1800B5991
0x1800b5987  mov     [rdx], rax
0x1800b598a  add     qword ptr [rdi+8], 8
0x1800b598f  jmp     short loc_1800B599D
0x1800b5991  lea     r8, [rbp+arg_28]
0x1800b5995  mov     rcx, rdi
0x1800b5998  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b599d  mov     rax, [rbp+arg_38]
0x1800b59a1  mov     [rbp+arg_28], rax
0x1800b59a5  mov     rdx, [rdi+8]
0x1800b59a9  cmp     rdx, [rdi+10h]
0x1800b59ad  jz      short loc_1800B59B9
0x1800b59af  mov     [rdx], rax
0x1800b59b2  add     qword ptr [rdi+8], 8
0x1800b59b7  jmp     short loc_1800B59C5
0x1800b59b9  lea     r8, [rbp+arg_28]
0x1800b59bd  mov     rcx, rdi
0x1800b59c0  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b59c5  mov     rdx, [rdi+8]
0x1800b59c9  cmp     rdx, [rdi+10h]
0x1800b59cd  jz      short loc_1800B59DD
0x1800b59cf  mov     rax, [rbp+Binding]
0x1800b59d3  mov     [rdx], rax
0x1800b59d6  add     qword ptr [rdi+8], 8
0x1800b59db  jmp     short loc_1800B59E9
0x1800b59dd  lea     r8, [rbp+Binding]
0x1800b59e1  mov     rcx, rdi
0x1800b59e4  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b59e9  mov     rdx, rsi
0x1800b59ec  mov     ecx, 2Dh ; '-'
0x1800b59f1  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b59f6  test    eax, eax
0x1800b59f8  jz      short loc_1800B5A23
0x1800b59fa  test    rsi, rsi
0x1800b59fd  jz      short loc_1800B5A07
0x1800b59ff  mov     rcx, rsi; this
0x1800b5a02  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b5a07  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b5a0e  xor     edx, edx; struct _GUID *
0x1800b5a10  lea     rcx, aWwansapuiccope; "WwanSapUiccOpenChannel"
0x1800b5a17  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b5a1c  mov     ebx, 1Fh
0x1800b5a21  jmp     short loc_1800B5A57
0x1800b5a23  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b5a26  mov     rcx, rbx; hHandle
0x1800b5a29  call    cs:__imp_WaitForSingleObject
0x1800b5a2f  test    eax, eax
0x1800b5a31  jz      short loc_1800B5A54
0x1800b5a33  call    cs:__imp_GetLastError
0x1800b5a39  mov     r9d, eax; unsigned int
0x1800b5a3c  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b5a43  mov     edx, 0B72h; unsigned int
0x1800b5a48  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5a4f  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5a54  mov     ebx, [rbp+arg_10]
0x1800b5a57  lea     rcx, [rbp+var_10]
0x1800b5a5b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b5a60  mov     eax, ebx
0x1800b5a62  add     rsp, 30h
0x1800b5a66  pop     r15
0x1800b5a68  pop     r14
0x1800b5a6a  pop     r12
0x1800b5a6c  pop     rdi
0x1800b5a6d  pop     rsi
0x1800b5a6e  pop     rbx
0x1800b5a6f  pop     rbp
0x1800b5a70  retn
```
