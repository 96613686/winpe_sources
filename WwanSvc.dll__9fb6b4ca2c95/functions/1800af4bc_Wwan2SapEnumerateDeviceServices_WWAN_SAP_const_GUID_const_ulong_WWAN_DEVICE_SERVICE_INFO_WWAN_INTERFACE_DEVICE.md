# Wwan2SapEnumerateDeviceServices(WWAN_SAP const *,_GUID const *,ulong,_WWAN_DEVICE_SERVICE_INFO *,_WWAN_INTERFACE_DEVICE_SERVICES_INFO *)

- ea: `0x1800af4bc`
- end: `0x1800af70c`
- name: `?Wwan2SapEnumerateDeviceServices@@YAKPEBUWWAN_SAP@@PEBU_GUID@@KPEAU_WWAN_DEVICE_SERVICE_INFO@@PEAU_WWAN_INTERFACE_DEVICE_SERVICES_INFO@@@Z`
- size: `592`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, unsigned int, struct _WWAN_DEVICE_SERVICE_INFO *, struct _WWAN_INTERFACE_DEVICE_SERVICES_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800abf10`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800af4bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af6c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af6c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af4f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af4f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af53b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af6ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af53b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af6ce`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800af531`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800af531`

## string_xrefs

- `0x1800af521`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800af550`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800af6e3`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800af515`: `CreateEvent`
- `0x1800af6ab`: `Wwan2SapEnumerateDeviceServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapEnumerateDeviceServices(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        unsigned int a3,
        struct _WWAN_DEVICE_SERVICE_INFO *a4,
        struct _WWAN_INTERFACE_DEVICE_SERVICES_INFO *a5)
{
  MessageParams *v6; // r12
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  DWORD v10; // eax
  MessageParams *v11; // rax
  MessageParams *v12; // rsi
  char *v13; // rdi
  MessageParams **v14; // rdx
  unsigned int **v15; // rdx
  _QWORD *v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  RPC_BINDING_HANDLE *v20; // rdx
  unsigned int v21; // edx
  unsigned int v22; // ebx
  DWORD v23; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+40h] BYREF
  MessageParams *v26; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v27; // [rsp+70h] [rbp+50h] BYREF
  MessageParams *v28; // [rsp+78h] [rbp+58h] BYREF

  v6 = (MessageParams *)a3;
  Binding = 0;
  v27 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v28 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x61Bu, "CreateEvent", LastError);
  }
  if ( RpcServerInqBindingHandle(&Binding) )
  {
    v10 = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x622u, "RpcServerInqBindingHandle", v10);
  }
  v26 = (MessageParams *)operator new(0x48u);
  v11 = MessageParams::MessageParams(v26);
  v12 = v11;
  v13 = (char *)v11 + 48;
  v26 = EventW;
  v14 = (MessageParams **)*((_QWORD *)v11 + 7);
  if ( v14 == *((MessageParams ***)v11 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v11 + 48, v14, &v26);
  }
  else
  {
    *v14 = EventW;
    *((_QWORD *)v11 + 7) += 8LL;
  }
  v26 = (MessageParams *)&v27;
  v15 = (unsigned int **)*((_QWORD *)v13 + 1);
  if ( v15 == *((unsigned int ***)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v15, &v26);
  }
  else
  {
    *v15 = &v27;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v26 = (MessageParams *)a2;
  v16 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v16 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v16, &v26);
  }
  else
  {
    *v16 = a2;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v26 = v6;
  v17 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v17 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v17, &v26);
  }
  else
  {
    *v17 = v6;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v26 = a4;
  v18 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v18 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v18, &v26);
  }
  else
  {
    *v18 = a4;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v19 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v19 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v19, &a5);
  }
  else
  {
    *v19 = a5;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v20 = (RPC_BINDING_HANDLE *)*((_QWORD *)v13 + 1);
  if ( v20 == *((RPC_BINDING_HANDLE **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v20, &Binding);
  }
  else
  {
    *v20 = Binding;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(26, v12) )
  {
    if ( v12 )
      MessageParams::`scalar deleting destructor'(v12, v21);
    WwanLog::Error("Wwan2SapEnumerateDeviceServices", 0, L"Notification dispatcher: Failed to Queue Message");
    v22 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v23 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x638u, "WaitForSingleObject", v23);
    }
    v22 = v27;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v28);
  return v22;
}

```

## disassembly

```asm
0x1800af4bc  mov     [rsp-38h+Binding], rcx
0x1800af4c1  push    rbp
0x1800af4c2  push    rbx
0x1800af4c3  push    rsi
0x1800af4c4  push    rdi
0x1800af4c5  push    r12
0x1800af4c7  push    r14
0x1800af4c9  push    r15
0x1800af4cb  mov     rbp, rsp
0x1800af4ce  sub     rsp, 20h
0x1800af4d2  mov     r15, r9
0x1800af4d5  mov     r12d, r8d
0x1800af4d8  mov     r14, rdx
0x1800af4db  mov     [rbp+Binding], 0
0x1800af4e3  mov     [rbp+arg_10], 0
0x1800af4ea  xor     r9d, r9d; lpName
0x1800af4ed  xor     r8d, r8d; bInitialState
0x1800af4f0  lea     edx, [r9+1]; bManualReset
0x1800af4f4  xor     ecx, ecx; lpEventAttributes
0x1800af4f6  call    cs:__imp_CreateEventW
0x1800af4fc  mov     rbx, rax
0x1800af4ff  mov     [rbp+arg_18], rax
0x1800af503  inc     rax
0x1800af506  cmp     rax, 1
0x1800af50a  ja      short loc_1800AF52D
0x1800af50c  call    cs:__imp_GetLastError
0x1800af512  mov     r9d, eax; unsigned int
0x1800af515  lea     r8, aCreateevent; "CreateEvent"
0x1800af51c  mov     edx, 61Bh; unsigned int
0x1800af521  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800af528  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800af52d  lea     rcx, [rbp+Binding]; Binding
0x1800af531  call    cs:__imp_RpcServerInqBindingHandle
0x1800af537  test    eax, eax
0x1800af539  jz      short loc_1800AF55C
0x1800af53b  call    cs:__imp_GetLastError
0x1800af541  mov     r9d, eax; unsigned int
0x1800af544  lea     r8, aRpcserverinqbi_0; "RpcServerInqBindingHandle"
0x1800af54b  mov     edx, 622h; unsigned int
0x1800af550  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800af557  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800af55c  mov     ecx, 48h ; 'H'; Size
0x1800af561  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800af566  mov     [rbp+arg_8], rax
0x1800af56a  mov     rcx, rax; this
0x1800af56d  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800af572  mov     rsi, rax
0x1800af575  lea     rdi, [rax+30h]
0x1800af579  mov     [rbp+arg_8], rbx
0x1800af57d  mov     rdx, [rdi+8]
0x1800af581  cmp     rdx, [rdi+10h]
0x1800af585  jz      short loc_1800AF591
0x1800af587  mov     [rdx], rbx
0x1800af58a  add     qword ptr [rdi+8], 8
0x1800af58f  jmp     short loc_1800AF59D
0x1800af591  lea     r8, [rbp+arg_8]
0x1800af595  mov     rcx, rdi
0x1800af598  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af59d  lea     rax, [rbp+arg_10]
0x1800af5a1  mov     [rbp+arg_8], rax
0x1800af5a5  mov     rdx, [rdi+8]
0x1800af5a9  cmp     rdx, [rdi+10h]
0x1800af5ad  jz      short loc_1800AF5BD
0x1800af5af  lea     rax, [rbp+arg_10]
0x1800af5b3  mov     [rdx], rax
0x1800af5b6  add     qword ptr [rdi+8], 8
0x1800af5bb  jmp     short loc_1800AF5C9
0x1800af5bd  lea     r8, [rbp+arg_8]
0x1800af5c1  mov     rcx, rdi
0x1800af5c4  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af5c9  mov     [rbp+arg_8], r14
0x1800af5cd  mov     rdx, [rdi+8]
0x1800af5d1  cmp     rdx, [rdi+10h]
0x1800af5d5  jz      short loc_1800AF5E1
0x1800af5d7  mov     [rdx], r14
0x1800af5da  add     qword ptr [rdi+8], 8
0x1800af5df  jmp     short loc_1800AF5ED
0x1800af5e1  lea     r8, [rbp+arg_8]
0x1800af5e5  mov     rcx, rdi
0x1800af5e8  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af5ed  mov     rax, r12
0x1800af5f0  mov     [rbp+arg_8], rax
0x1800af5f4  mov     rdx, [rdi+8]
0x1800af5f8  cmp     rdx, [rdi+10h]
0x1800af5fc  jz      short loc_1800AF608
0x1800af5fe  mov     [rdx], rax
0x1800af601  add     qword ptr [rdi+8], 8
0x1800af606  jmp     short loc_1800AF614
0x1800af608  lea     r8, [rbp+arg_8]
0x1800af60c  mov     rcx, rdi
0x1800af60f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af614  mov     [rbp+arg_8], r15
0x1800af618  mov     rdx, [rdi+8]
0x1800af61c  cmp     rdx, [rdi+10h]
0x1800af620  jz      short loc_1800AF62C
0x1800af622  mov     [rdx], r15
0x1800af625  add     qword ptr [rdi+8], 8
0x1800af62a  jmp     short loc_1800AF638
0x1800af62c  lea     r8, [rbp+arg_8]
0x1800af630  mov     rcx, rdi
0x1800af633  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af638  mov     rax, [rbp+arg_20]
0x1800af63c  mov     [rbp+arg_20], rax
0x1800af640  mov     rdx, [rdi+8]
0x1800af644  cmp     rdx, [rdi+10h]
0x1800af648  jz      short loc_1800AF654
0x1800af64a  mov     [rdx], rax
0x1800af64d  add     qword ptr [rdi+8], 8
0x1800af652  jmp     short loc_1800AF660
0x1800af654  lea     r8, [rbp+arg_20]
0x1800af658  mov     rcx, rdi
0x1800af65b  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af660  mov     rdx, [rdi+8]
0x1800af664  cmp     rdx, [rdi+10h]
0x1800af668  jz      short loc_1800AF678
0x1800af66a  mov     rax, [rbp+Binding]
0x1800af66e  mov     [rdx], rax
0x1800af671  add     qword ptr [rdi+8], 8
0x1800af676  jmp     short loc_1800AF684
0x1800af678  lea     r8, [rbp+Binding]
0x1800af67c  mov     rcx, rdi
0x1800af67f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af684  mov     rdx, rsi
0x1800af687  mov     ecx, 1Ah
0x1800af68c  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800af691  test    eax, eax
0x1800af693  jz      short loc_1800AF6BE
0x1800af695  test    rsi, rsi
0x1800af698  jz      short loc_1800AF6A2
0x1800af69a  mov     rcx, rsi; this
0x1800af69d  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800af6a2  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800af6a9  xor     edx, edx; struct _GUID *
0x1800af6ab  lea     rcx, aWwan2sapenumer; "Wwan2SapEnumerateDeviceServices"
0x1800af6b2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af6b7  mov     ebx, 1Fh
0x1800af6bc  jmp     short loc_1800AF6F2
0x1800af6be  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800af6c1  mov     rcx, rbx; hHandle
0x1800af6c4  call    cs:__imp_WaitForSingleObject
0x1800af6ca  test    eax, eax
0x1800af6cc  jz      short loc_1800AF6EF
0x1800af6ce  call    cs:__imp_GetLastError
0x1800af6d4  mov     r9d, eax; unsigned int
0x1800af6d7  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800af6de  mov     edx, 638h; unsigned int
0x1800af6e3  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800af6ea  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800af6ef  mov     ebx, [rbp+arg_10]
0x1800af6f2  lea     rcx, [rbp+arg_18]
0x1800af6f6  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800af6fb  mov     eax, ebx
0x1800af6fd  add     rsp, 20h
0x1800af701  pop     r15
0x1800af703  pop     r14
0x1800af705  pop     r12
0x1800af707  pop     rdi
0x1800af708  pop     rsi
0x1800af709  pop     rbx
0x1800af70a  pop     rbp
0x1800af70b  retn
```
