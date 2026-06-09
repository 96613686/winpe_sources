# Wwan2SapCloseDeviceServiceDataSession(WWAN_SAP *,_GUID const *,ulong,ulong *)

- ea: `0x1800af264`
- end: `0x1800af4b5`
- name: `?Wwan2SapCloseDeviceServiceDataSession@@YAKPEAUWWAN_SAP@@PEBU_GUID@@KPEAK@Z`
- size: `593`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION, const struct _GUID *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800abe70`
- `0x1800b148c`

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
- `0x1800af264`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af464`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af464`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af307`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800af307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af46e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af46e`

## string_xrefs

- `0x1800af332`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800af483`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800af326`: `CreateEvent`
- `0x1800af2a1`: `Wwan2SapCloseDeviceServiceDataSession`
- `0x1800af2ea`: `Wwan2SapCloseDeviceServiceDataSession`
- `0x1800af441`: `Wwan2SapCloseDeviceServiceDataSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapCloseDeviceServiceDataSession(
        LPCRITICAL_SECTION a1,
        const struct _GUID *a2,
        unsigned int a3,
        const struct _GUID *a4)
{
  const struct _GUID *v5; // r12
  struct _GUID *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v11; // rax
  MessageParams *v12; // rax
  MessageParams *v13; // rsi
  char *v14; // rdi
  struct _GUID **v15; // rdx
  unsigned int **v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  const struct _GUID **v19; // rdx
  unsigned int v20; // edx
  DWORD v21; // eax
  struct _GUID *v22; // [rsp+30h] [rbp-10h] BYREF
  const struct _GUID *v23; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v24; // [rsp+70h] [rbp+30h] BYREF

  v5 = (const struct _GUID *)a3;
  v24 = 0;
  if ( !a1 )
  {
    WwanLog::Error("Wwan2SapCloseDeviceServiceDataSession", 0, L"[%p] Invalid parameters", 0);
    return 87;
  }
  v24 = WwanSapMgrValidateSessionOwnership(&g_sapMgr2, a1, a3, 2);
  if ( v24 )
  {
    WwanLog::Error("Wwan2SapCloseDeviceServiceDataSession", 0, L"[%p] WwanSapMgrValidateSessionOwnership failed", a1);
    return v24;
  }
  EventW = (struct _GUID *)CreateEventW(0, 1, 0, 0);
  v22 = EventW;
  if ( EventW == (struct _GUID *)-1LL || (unsigned int *)((char *)&EventW->Data1 + 1) == (unsigned int *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x980u, "CreateEvent", LastError);
  }
  v11 = (MessageParams *)operator new(0x48u);
  v12 = MessageParams::MessageParams(v11);
  v13 = v12;
  v14 = (char *)v12 + 48;
  v23 = EventW;
  v15 = (struct _GUID **)*((_QWORD *)v12 + 7);
  if ( v15 == *((struct _GUID ***)v12 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v12 + 48, v15, &v23);
  }
  else
  {
    *v15 = EventW;
    *((_QWORD *)v12 + 7) += 8LL;
  }
  v23 = (const struct _GUID *)&v24;
  v16 = (unsigned int **)*((_QWORD *)v14 + 1);
  if ( v16 == *((unsigned int ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v16, &v23);
  }
  else
  {
    *v16 = &v24;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v23 = a2;
  v17 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v17 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v17, &v23);
  }
  else
  {
    *v17 = a2;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v23 = v5;
  v18 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v18 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v18, &v23);
  }
  else
  {
    *v18 = v5;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v23 = a4;
  v19 = (const struct _GUID **)*((_QWORD *)v14 + 1);
  if ( v19 == *((const struct _GUID ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v19, &v23);
  }
  else
  {
    *v19 = a4;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  if ( !(unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(33, v13) )
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v21 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x993u, "WaitForSingleObject", v21);
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v22);
    return v24;
  }
  if ( v13 )
    MessageParams::`scalar deleting destructor'(v13, v20);
  WwanLog::Error("Wwan2SapCloseDeviceServiceDataSession", 0, L"Notification dispatcher: Failed to Queue Message");
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v22);
  return 31;
}

```

## disassembly

```asm
0x1800af264  mov     [rsp-28h+arg_8], rbx
0x1800af269  mov     [rsp-28h+arg_10], rsi
0x1800af26e  push    rbp
0x1800af26f  push    rdi
0x1800af270  push    r12
0x1800af272  push    r14
0x1800af274  push    r15
0x1800af276  mov     rbp, rsp
0x1800af279  sub     rsp, 40h
0x1800af27d  mov     r15, r9
0x1800af280  mov     r12d, r8d
0x1800af283  mov     r14, rdx
0x1800af286  mov     rbx, rcx
0x1800af289  mov     [rbp+arg_0], 0
0x1800af290  test    rcx, rcx
0x1800af293  jnz     short loc_1800AF2B5
0x1800af295  xor     r9d, r9d
0x1800af298  lea     r8, aPInvalidParame; "[%p] Invalid parameters"
0x1800af29f  xor     edx, edx; struct _GUID *
0x1800af2a1  lea     rcx, aWwan2sapclosed_0; "Wwan2SapCloseDeviceServiceDataSession"
0x1800af2a8  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af2ad  lea     eax, [rbx+57h]
0x1800af2b0  jmp     loc_1800AF49C
0x1800af2b5  mov     r9d, 2
0x1800af2bb  mov     [rsp+40h+var_18], r9d; int
0x1800af2c0  mov     [rsp+40h+var_20], r12d; int
0x1800af2c5  mov     r8, r14
0x1800af2c8  mov     rdx, rbx; LPCRITICAL_SECTION
0x1800af2cb  lea     rcx, ?g_sapMgr2@@3U_WWAN_SAP_MGR@@A; lpCriticalSection
0x1800af2d2  call    _WwanSapMgrValidateSessionOwnership
0x1800af2d7  mov     [rbp+arg_0], eax
0x1800af2da  test    eax, eax
0x1800af2dc  jz      short loc_1800AF2FB
0x1800af2de  mov     r9, rbx
0x1800af2e1  lea     r8, aPWwansapmgrval; "[%p] WwanSapMgrValidateSessionOwnership"...
0x1800af2e8  xor     edx, edx; struct _GUID *
0x1800af2ea  lea     rcx, aWwan2sapclosed_0; "Wwan2SapCloseDeviceServiceDataSession"
0x1800af2f1  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af2f6  jmp     loc_1800AF499
0x1800af2fb  xor     r9d, r9d; lpName
0x1800af2fe  xor     r8d, r8d; bInitialState
0x1800af301  lea     edx, [r9+1]; bManualReset
0x1800af305  xor     ecx, ecx; lpEventAttributes
0x1800af307  call    cs:__imp_CreateEventW
0x1800af30d  mov     rbx, rax
0x1800af310  mov     [rbp+var_10], rax
0x1800af314  inc     rax
0x1800af317  cmp     rax, 1
0x1800af31b  ja      short loc_1800AF33E
0x1800af31d  call    cs:__imp_GetLastError
0x1800af323  mov     r9d, eax; unsigned int
0x1800af326  lea     r8, aCreateevent; "CreateEvent"
0x1800af32d  mov     edx, 980h; unsigned int
0x1800af332  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800af339  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800af33e  mov     ecx, 48h ; 'H'; Size
0x1800af343  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800af348  mov     [rbp+var_8], rax
0x1800af34c  mov     rcx, rax; this
0x1800af34f  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800af354  mov     rsi, rax
0x1800af357  lea     rdi, [rax+30h]
0x1800af35b  mov     [rbp+var_8], rbx
0x1800af35f  mov     rdx, [rdi+8]
0x1800af363  cmp     rdx, [rdi+10h]
0x1800af367  jz      short loc_1800AF373
0x1800af369  mov     [rdx], rbx
0x1800af36c  add     qword ptr [rdi+8], 8
0x1800af371  jmp     short loc_1800AF37F
0x1800af373  lea     r8, [rbp+var_8]
0x1800af377  mov     rcx, rdi
0x1800af37a  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af37f  lea     rax, [rbp+arg_0]
0x1800af383  mov     [rbp+var_8], rax
0x1800af387  mov     rdx, [rdi+8]
0x1800af38b  cmp     rdx, [rdi+10h]
0x1800af38f  jz      short loc_1800AF39F
0x1800af391  lea     rax, [rbp+arg_0]
0x1800af395  mov     [rdx], rax
0x1800af398  add     qword ptr [rdi+8], 8
0x1800af39d  jmp     short loc_1800AF3AB
0x1800af39f  lea     r8, [rbp+var_8]
0x1800af3a3  mov     rcx, rdi
0x1800af3a6  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af3ab  mov     [rbp+var_8], r14
0x1800af3af  mov     rdx, [rdi+8]
0x1800af3b3  cmp     rdx, [rdi+10h]
0x1800af3b7  jz      short loc_1800AF3C3
0x1800af3b9  mov     [rdx], r14
0x1800af3bc  add     qword ptr [rdi+8], 8
0x1800af3c1  jmp     short loc_1800AF3CF
0x1800af3c3  lea     r8, [rbp+var_8]
0x1800af3c7  mov     rcx, rdi
0x1800af3ca  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af3cf  mov     rax, r12
0x1800af3d2  mov     [rbp+var_8], rax
0x1800af3d6  mov     rdx, [rdi+8]
0x1800af3da  cmp     rdx, [rdi+10h]
0x1800af3de  jz      short loc_1800AF3EA
0x1800af3e0  mov     [rdx], rax
0x1800af3e3  add     qword ptr [rdi+8], 8
0x1800af3e8  jmp     short loc_1800AF3F6
0x1800af3ea  lea     r8, [rbp+var_8]
0x1800af3ee  mov     rcx, rdi
0x1800af3f1  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af3f6  mov     [rbp+var_8], r15
0x1800af3fa  mov     rdx, [rdi+8]
0x1800af3fe  cmp     rdx, [rdi+10h]
0x1800af402  jz      short loc_1800AF40E
0x1800af404  mov     [rdx], r15
0x1800af407  add     qword ptr [rdi+8], 8
0x1800af40c  jmp     short loc_1800AF41A
0x1800af40e  lea     r8, [rbp+var_8]
0x1800af412  mov     rcx, rdi
0x1800af415  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800af41a  mov     rdx, rsi
0x1800af41d  mov     ecx, 21h ; '!'
0x1800af422  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800af427  test    eax, eax
0x1800af429  jz      short loc_1800AF45E
0x1800af42b  test    rsi, rsi
0x1800af42e  jz      short loc_1800AF438
0x1800af430  mov     rcx, rsi; this
0x1800af433  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800af438  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800af43f  xor     edx, edx; struct _GUID *
0x1800af441  lea     rcx, aWwan2sapclosed_0; "Wwan2SapCloseDeviceServiceDataSession"
0x1800af448  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af44d  nop
0x1800af44e  lea     rcx, [rbp+var_10]
0x1800af452  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800af457  mov     eax, 1Fh
0x1800af45c  jmp     short loc_1800AF49C
0x1800af45e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800af461  mov     rcx, rbx; hHandle
0x1800af464  call    cs:__imp_WaitForSingleObject
0x1800af46a  test    eax, eax
0x1800af46c  jz      short loc_1800AF490
0x1800af46e  call    cs:__imp_GetLastError
0x1800af474  mov     r9d, eax; unsigned int
0x1800af477  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800af47e  mov     edx, 993h; unsigned int
0x1800af483  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800af48a  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800af48f  nop
0x1800af490  lea     rcx, [rbp+var_10]
0x1800af494  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800af499  mov     eax, [rbp+arg_0]
0x1800af49c  lea     r11, [rsp+40h+var_s0]
0x1800af4a1  mov     rbx, [r11+38h]
0x1800af4a5  mov     rsi, [r11+40h]
0x1800af4a9  mov     rsp, r11
0x1800af4ac  pop     r15
0x1800af4ae  pop     r14
0x1800af4b0  pop     r12
0x1800af4b2  pop     rdi
0x1800af4b3  pop     rbp
0x1800af4b4  retn
```
