# WwanSapUiccSetTerminalCapability(WWAN_SAP const *,_GUID const *,ulong,_WWAN_UICC_TERMINAL_CAPABILITY_TLV const *,ulong,ulong *)

- ea: `0x1800b5d18`
- end: `0x1800b5f34`
- name: `?WwanSapUiccSetTerminalCapability@@YAKPEBUWWAN_SAP@@PEBU_GUID@@KPEBU_WWAN_UICC_TERMINAL_CAPABILITY_TLV@@KPEAK@Z`
- size: `540`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, unsigned int, const struct _WWAN_UICC_TERMINAL_CAPABILITY_TLV *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ada20`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b5d18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b5eec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b5eec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b5d4a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b5d4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5ef6`

## string_xrefs

- `0x1800b5d75`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5f0b`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5d69`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapUiccSetTerminalCapability(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        unsigned int a3,
        const struct _WWAN_UICC_TERMINAL_CAPABILITY_TLV *a4,
        unsigned int a5,
        unsigned int *a6)
{
  MessageParams *v7; // r12
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v11; // rax
  MessageParams *v12; // rsi
  char *v13; // rdi
  MessageParams **v14; // rdx
  unsigned int **v15; // rdx
  _QWORD *v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  unsigned int v21; // edx
  unsigned int v22; // ebx
  DWORD v23; // eax
  MessageParams *v25; // [rsp+60h] [rbp+40h] BYREF
  MessageParams *v26; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v27; // [rsp+70h] [rbp+50h] BYREF

  v25 = a1;
  v7 = (MessageParams *)a3;
  v27 = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v26 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xBE2u, "CreateEvent", LastError);
  }
  v25 = (MessageParams *)operator new(0x48u);
  v11 = MessageParams::MessageParams(v25);
  v12 = v11;
  v13 = (char *)v11 + 48;
  v25 = EventW;
  v14 = (MessageParams **)*((_QWORD *)v11 + 7);
  if ( v14 == *((MessageParams ***)v11 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v11 + 48, v14, &v25);
  }
  else
  {
    *v14 = EventW;
    *((_QWORD *)v11 + 7) += 8LL;
  }
  v25 = (MessageParams *)&v27;
  v15 = (unsigned int **)*((_QWORD *)v13 + 1);
  if ( v15 == *((unsigned int ***)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v15, &v25);
  }
  else
  {
    *v15 = &v27;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = (MessageParams *)a2;
  v16 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v16 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v16, &v25);
  }
  else
  {
    *v16 = a2;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = v7;
  v17 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v17 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v17, &v25);
  }
  else
  {
    *v17 = v7;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = a4;
  v18 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v18 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v18, &v25);
  }
  else
  {
    *v18 = a4;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = (MessageParams *)a5;
  v19 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v19 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v19, &v25);
  }
  else
  {
    *v19 = a5;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = (MessageParams *)a6;
  v20 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v20 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v20, &v25);
  }
  else
  {
    *v20 = a6;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(48, v12) )
  {
    if ( v12 )
      MessageParams::`scalar deleting destructor'(v12, v21);
    WwanLog::Error("WwanSapUiccSetTerminalCapability", 0, L"Notification dispatcher: Failed to Queue Message");
    v22 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v23 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xBF8u, "WaitForSingleObject", v23);
    }
    v22 = v27;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v26);
  return v22;
}

```

## disassembly

```asm
0x1800b5d18  mov     [rsp-38h+arg_0], rcx
0x1800b5d1d  push    rbp
0x1800b5d1e  push    rbx
0x1800b5d1f  push    rsi
0x1800b5d20  push    rdi
0x1800b5d21  push    r12
0x1800b5d23  push    r14
0x1800b5d25  push    r15
0x1800b5d27  mov     rbp, rsp
0x1800b5d2a  sub     rsp, 20h
0x1800b5d2e  mov     r15, r9
0x1800b5d31  mov     r12d, r8d
0x1800b5d34  mov     r14, rdx
0x1800b5d37  mov     [rbp+arg_10], 0
0x1800b5d3e  xor     r9d, r9d; lpName
0x1800b5d41  xor     r8d, r8d; bInitialState
0x1800b5d44  lea     edx, [r9+1]; bManualReset
0x1800b5d48  xor     ecx, ecx; lpEventAttributes
0x1800b5d4a  call    cs:__imp_CreateEventW
0x1800b5d50  mov     rbx, rax
0x1800b5d53  mov     [rbp+arg_8], rax
0x1800b5d57  inc     rax
0x1800b5d5a  cmp     rax, 1
0x1800b5d5e  ja      short loc_1800B5D81
0x1800b5d60  call    cs:__imp_GetLastError
0x1800b5d66  mov     r9d, eax; unsigned int
0x1800b5d69  lea     r8, aCreateevent; "CreateEvent"
0x1800b5d70  mov     edx, 0BE2h; unsigned int
0x1800b5d75  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5d7c  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5d81  mov     ecx, 48h ; 'H'; Size
0x1800b5d86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b5d8b  mov     [rbp+arg_0], rax
0x1800b5d8f  mov     rcx, rax; this
0x1800b5d92  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b5d97  mov     rsi, rax
0x1800b5d9a  lea     rdi, [rax+30h]
0x1800b5d9e  mov     [rbp+arg_0], rbx
0x1800b5da2  mov     rdx, [rdi+8]
0x1800b5da6  cmp     rdx, [rdi+10h]
0x1800b5daa  jz      short loc_1800B5DB6
0x1800b5dac  mov     [rdx], rbx
0x1800b5daf  add     qword ptr [rdi+8], 8
0x1800b5db4  jmp     short loc_1800B5DC2
0x1800b5db6  lea     r8, [rbp+arg_0]
0x1800b5dba  mov     rcx, rdi
0x1800b5dbd  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5dc2  lea     rax, [rbp+arg_10]
0x1800b5dc6  mov     [rbp+arg_0], rax
0x1800b5dca  mov     rdx, [rdi+8]
0x1800b5dce  cmp     rdx, [rdi+10h]
0x1800b5dd2  jz      short loc_1800B5DE2
0x1800b5dd4  lea     rax, [rbp+arg_10]
0x1800b5dd8  mov     [rdx], rax
0x1800b5ddb  add     qword ptr [rdi+8], 8
0x1800b5de0  jmp     short loc_1800B5DEE
0x1800b5de2  lea     r8, [rbp+arg_0]
0x1800b5de6  mov     rcx, rdi
0x1800b5de9  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5dee  mov     [rbp+arg_0], r14
0x1800b5df2  mov     rdx, [rdi+8]
0x1800b5df6  cmp     rdx, [rdi+10h]
0x1800b5dfa  jz      short loc_1800B5E06
0x1800b5dfc  mov     [rdx], r14
0x1800b5dff  add     qword ptr [rdi+8], 8
0x1800b5e04  jmp     short loc_1800B5E12
0x1800b5e06  lea     r8, [rbp+arg_0]
0x1800b5e0a  mov     rcx, rdi
0x1800b5e0d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5e12  mov     rax, r12
0x1800b5e15  mov     [rbp+arg_0], rax
0x1800b5e19  mov     rdx, [rdi+8]
0x1800b5e1d  cmp     rdx, [rdi+10h]
0x1800b5e21  jz      short loc_1800B5E2D
0x1800b5e23  mov     [rdx], rax
0x1800b5e26  add     qword ptr [rdi+8], 8
0x1800b5e2b  jmp     short loc_1800B5E39
0x1800b5e2d  lea     r8, [rbp+arg_0]
0x1800b5e31  mov     rcx, rdi
0x1800b5e34  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5e39  mov     [rbp+arg_0], r15
0x1800b5e3d  mov     rdx, [rdi+8]
0x1800b5e41  cmp     rdx, [rdi+10h]
0x1800b5e45  jz      short loc_1800B5E51
0x1800b5e47  mov     [rdx], r15
0x1800b5e4a  add     qword ptr [rdi+8], 8
0x1800b5e4f  jmp     short loc_1800B5E5D
0x1800b5e51  lea     r8, [rbp+arg_0]
0x1800b5e55  mov     rcx, rdi
0x1800b5e58  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5e5d  mov     eax, [rbp+arg_20]
0x1800b5e60  mov     [rbp+arg_0], rax
0x1800b5e64  mov     rdx, [rdi+8]
0x1800b5e68  cmp     rdx, [rdi+10h]
0x1800b5e6c  jz      short loc_1800B5E78
0x1800b5e6e  mov     [rdx], rax
0x1800b5e71  add     qword ptr [rdi+8], 8
0x1800b5e76  jmp     short loc_1800B5E84
0x1800b5e78  lea     r8, [rbp+arg_0]
0x1800b5e7c  mov     rcx, rdi
0x1800b5e7f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5e84  mov     rax, [rbp+arg_28]
0x1800b5e88  mov     [rbp+arg_0], rax
0x1800b5e8c  mov     rdx, [rdi+8]
0x1800b5e90  cmp     rdx, [rdi+10h]
0x1800b5e94  jz      short loc_1800B5EA0
0x1800b5e96  mov     [rdx], rax
0x1800b5e99  add     qword ptr [rdi+8], 8
0x1800b5e9e  jmp     short loc_1800B5EAC
0x1800b5ea0  lea     r8, [rbp+arg_0]
0x1800b5ea4  mov     rcx, rdi
0x1800b5ea7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5eac  mov     rdx, rsi
0x1800b5eaf  mov     ecx, 30h ; '0'
0x1800b5eb4  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b5eb9  test    eax, eax
0x1800b5ebb  jz      short loc_1800B5EE6
0x1800b5ebd  test    rsi, rsi
0x1800b5ec0  jz      short loc_1800B5ECA
0x1800b5ec2  mov     rcx, rsi; this
0x1800b5ec5  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b5eca  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b5ed1  xor     edx, edx; struct _GUID *
0x1800b5ed3  lea     rcx, aWwansapuiccset; "WwanSapUiccSetTerminalCapability"
0x1800b5eda  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b5edf  mov     ebx, 1Fh
0x1800b5ee4  jmp     short loc_1800B5F1A
0x1800b5ee6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b5ee9  mov     rcx, rbx; hHandle
0x1800b5eec  call    cs:__imp_WaitForSingleObject
0x1800b5ef2  test    eax, eax
0x1800b5ef4  jz      short loc_1800B5F17
0x1800b5ef6  call    cs:__imp_GetLastError
0x1800b5efc  mov     r9d, eax; unsigned int
0x1800b5eff  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b5f06  mov     edx, 0BF8h; unsigned int
0x1800b5f0b  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5f12  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5f17  mov     ebx, [rbp+arg_10]
0x1800b5f1a  lea     rcx, [rbp+arg_8]
0x1800b5f1e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b5f23  mov     eax, ebx
0x1800b5f25  add     rsp, 20h
0x1800b5f29  pop     r15
0x1800b5f2b  pop     r14
0x1800b5f2d  pop     r12
0x1800b5f2f  pop     rdi
0x1800b5f30  pop     rsi
0x1800b5f31  pop     rbx
0x1800b5f32  pop     rbp
0x1800b5f33  retn
```
